---
title: Ontwikkeling van proxy's
description: Een proxy is een [!DNL Experience Manager] instantie die proxyworkers gebruikt om taken te verwerken. Leer hoe u een [!DNL Experience Manager] proxy, ondersteunde bewerkingen, proxycomponenten en hoe een aangepaste proxyworker te ontwikkelen.
contentOwner: AG
feature: Asset Processing
role: Admin, Architect
exl-id: c7511326-697e-4749-ab46-513cdbaa00d8
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '918'
ht-degree: 0%

---

# Ontwikkeling van proxy&#39;s {#assets-proxy-development}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Adobe Experience Manager Assets gebruikt een proxy om verwerking voor bepaalde taken te distribueren.

Een proxy is een specifieke (en soms aparte) proxy [!DNL Experience Manager] -instantie die proxyworkers gebruikt als processors die verantwoordelijk zijn voor het afhandelen van een taak en het maken van een resultaat. Een volmachtsarbeider kan voor een grote verscheidenheid van taken worden gebruikt. In het geval van een [!DNL Experience Manager] Assets-proxy kan worden gebruikt voor het laden van elementen voor rendering binnen [!DNL Experience Manager] Elementen. De [IDS-proxyworker](indesign.md) gebruikt een InDesign Server om bestanden te verwerken die kunnen worden gebruikt in [!DNL Experience Manager] Elementen.

Wanneer de proxy een aparte [!DNL Experience Manager] -instantie wordt de belasting op de [!DNL Experience Manager] ontwerpinstantie(s). Standaard, [!DNL Experience Manager] Elementen voeren de elementverwerkingstaken uit in dezelfde JVM (extern via Proxy) om de belasting op de [!DNL Experience Manager] ontwerpinstantie.

## Proxy (HTTP-toegang) {#proxy-http-access}

Een volmacht is beschikbaar via de Server van HTTP wanneer het wordt gevormd om verwerkingstaken goed te keuren bij: `/libs/dam/cloud/proxy`. Deze servlet maakt een slingertaak van de geposte parameters. Deze wordt vervolgens toegevoegd aan de wachtrij van de proxytaak en verbonden met de desbetreffende proxyworker.

### Ondersteunde bewerkingen {#supported-operations}

* `job`

   **Vereisten**: de parameter `jobevent` moet als geserialiseerde waardekaart worden geplaatst. Hiermee maakt u een `Event` voor een taakprocessor.

   **Resultaat**: Hiermee wordt een nieuwe taak toegevoegd. Als dit lukt, wordt een unieke taak-id geretourneerd.

```shell
curl -u admin:admin -F":operation=job" -F"someproperty=xxxxxxxxxxxx"
    -F"jobevent=serialized value map" http://localhost:4502/libs/dam/cloud/proxy
```

* `result`

   **Vereisten**: de parameter `jobid` moet worden ingesteld.

   **Resultaat**: Retourneert een JSON-representatie van het resultaatknooppunt zoals gemaakt door de taakprocessor.

```shell
curl -u admin:admin -F":operation=result" -F"jobid=xxxxxxxxxxxx"
    http://localhost:4502   /libs/dam/cloud/proxy
```

* `resource`

   **Vereisten**: de parameter jobid moet worden ingesteld.

   **Resultaat**: Retourneert een resource die aan de opgegeven taak is gekoppeld.

```shell
curl -u admin:admin -F":operation=resource" -F"jobid=xxxxxxxxxxxx"
    -F"resourcePath=something.pdf" http://localhost:4502/libs/dam/cloud/proxy
```

* `remove`

   **Vereisten**: de parameter jobid moet worden ingesteld.

   **Resultaten**: Hiermee wordt een taak verwijderd als deze wordt gevonden.

```shell
curl -u admin:admin -F":operation=remove" -F"jobid=xxxxxxxxxxxx"
    http://localhost:4502/libs/dam/cloud/proxy
```

### Proxy Worker {#proxy-worker}

Een proxyworker is een processor die verantwoordelijk is voor het afhandelen van een taak en het maken van een resultaat. De werknemers verblijven op de volmachtsinstantie en moeten uitvoeren [Taakprocessor verkopen](https://sling.apache.org/site/eventing-and-jobs.html) om te worden herkend als een proxyworker.

>[!NOTE]
>
>De worker moet [Taakprocessor verkopen](https://sling.apache.org/site/eventing-and-jobs.html) om te worden herkend als een proxyworker.

### Client-API {#client-api}

[`JobService`](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/index.html) is beschikbaar als dienst OSGi die methodes verstrekt om banen tot stand te brengen, banen te verwijderen en resultaten van die banen te krijgen. De standaardimplementatie van deze service (`JobServiceImpl`) gebruikt de HTTP-client om te communiceren met de externe proxyserver.

Hieronder ziet u een voorbeeld van API-gebruik:

```java
@Reference
 JobService proxyJobService;

 // to create a new job
 final Hashtable props = new Hashtable();
 props.put("someproperty", "some value");
 props.put(JobUtil.PROPERTY_JOB_TOPIC, "myworker/job"); // this is an identifier of the worker
 final String jobId = proxyJobService.addJob(props, new Asset[]{asset});

 // to check status (returns JobService.STATUS_FINISHED or JobService.STATUS_INPROGRESS)
 int status = proxyJobService.getStatus(jobId)

 // to get the result
 final String jsonString = proxyJobService.getResult(jobId);

 // to remove job and cleanup
 proxyJobService.removeJob(jobId);
```

### Configuraties van Cloud Servicen {#cloud-service-configurations}

>[!NOTE]
>
>Referentiedocumentatie voor de proxy-API is beschikbaar onder [`com.day.cq.dam.api.proxy`](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/dam/commons/proxy/package-summary.html).

Zowel proxyconfiguraties als proxyarbeidersconfiguraties zijn beschikbaar via cloudservices die toegankelijk zijn via de [!DNL Experience Manager] Activa **Gereedschappen** console of onder `/etc/cloudservices/proxy`. Elke proxyworker moet een knooppunt toevoegen onder `/etc/cloudservices/proxy` voor arbeidersspecifieke configuratiedetails (bijvoorbeeld `/etc/cloudservices/proxy/workername`).

>[!NOTE]
>
>Zie [Configuratie van InDesign Server Proxy Worker](indesign.md#configuring-the-proxy-worker-for-indesign-server) en [Configuratie Cloud Services](../sites-developing/extending-cloud-config.md) voor meer informatie .

Hieronder ziet u een voorbeeld van API-gebruik:

```java
@Reference(policy = ReferencePolicy.STATIC)
 ProxyConfig proxyConfig;
 
 // to get proxy config
 Configuration cloudConfig = proxyConfig.getConfiguration();
 final String value = cloudConfig.get("someProperty", "defaultValue");

 // to get worker config
 Configuration cloudConfig = proxyConfig.getConfiguration("workername");
 final String value = cloudConfig.get("someProperty", "defaultValue");
```

### Een aangepaste proxyworker ontwikkelen {#developing-a-customized-proxy-worker}

De [IDS-proxyworker](indesign.md) is een voorbeeld van een [!DNL Experience Manager] De volmachtsarbeider van activa die reeds uit-van-de-doos wordt verstrekt om de verwerking van activa uit te besteden InDesign.

U kunt ook uw eigen [!DNL Experience Manager] De volmachtsarbeider van activa om een gespecialiseerde arbeider tot stand te brengen om uw te verzenden en uit te besteden [!DNL Experience Manager] Elementverwerkingstaken.

Als u uw eigen aangepaste proxyworker wilt instellen, moet u:

* Instellen en implementeren (met gebruik van Gebeurtenis splitsen):

   * een aangepast taakonderwerp
   * een aangepaste taakgebeurtenishandler

* Gebruik vervolgens de JobService-API om:

   * Verzend uw aangepaste taak naar de proxy
   * uw taak beheren

* Als u de proxy uit een workflow wilt gebruiken, moet u een aangepaste externe stap implementeren met de WorkflowExternalProcess-API en de JobService-API.

In het volgende diagram en in de volgende stappen wordt gedetailleerd beschreven hoe u moet doorgaan:

![chlimage_1-249](assets/chlimage_1-249.png)

>[!NOTE]
>
>In de volgende stappen worden equivalenten van InDesign als referentievoorbeelden aangegeven.

1. A [Verkooptaak](https://sling.apache.org/site/eventing-and-jobs.html) wordt gebruikt, zodat moet u een baanonderwerp voor uw gebruiksgeval bepalen.

   Zie als voorbeeld `IDSJob.IDS_EXTENDSCRIPT_JOB` voor de IDS-proxyworker.

1. De externe stap wordt gebruikt om de gebeurtenis te activeren en dan te wachten tot dat wordt gebeëindigd; dit wordt gedaan door opiniepeilingen over de id . U moet uw eigen stap ontwikkelen om nieuwe functionaliteit uit te voeren.

   Een `WorkflowExternalProcess`, dan gebruik de API JobService en uw baanonderwerp om een baangebeurtenis voor te bereiden en het te verzenden naar JobService (een dienst OSGi).

   Zie als voorbeeld `INDDMediaExtractProcess`.java voor de IDS volmachtsarbeider.

1. Voer een baanmanager voor uw onderwerp uit. Deze manager vereist ontwikkeling zodat het uw specifieke actie uitvoert en beschouwd wordt als om de arbeidersimplementatie.

   Zie als voorbeeld `IDSJobProcessor.java` voor de IDS-proxyworker.

1. Gebruik van `ProxyUtil.java` in dam-commons. Hierdoor kunt u taken naar werknemers verzenden met de proxy voor moederdieren.

>[!NOTE]
>
>Wat de [!DNL Experience Manager] Het raamwerk van de volmacht van activa verstrekt geen out-of-the-box is het poolmechanisme.
>
>De integratie van InDesign staat de toegang van een pool van indesign servers (IDSPool) toe. Deze pooling is specifiek voor InDesign-integratie en maakt geen deel uit van de [!DNL Experience Manager] Elementenproxyframework.

>[!NOTE]
>
>Synchronisatie van resultaten:
>
>Bij n instanties die dezelfde proxy gebruiken, blijft het verwerkingsresultaat bij de proxy. Dit is de taak van de client ([!DNL Experience Manager] Auteur) om het resultaat aan te vragen met dezelfde unieke taak-id als die aan de client is gegeven bij het maken van een taak. De proxy haalt de taak gewoon uit en zorgt ervoor dat het resultaat klaar is om te worden aangevraagd.
