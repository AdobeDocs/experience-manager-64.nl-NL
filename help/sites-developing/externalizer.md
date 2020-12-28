---
title: URL's extern maken
seo-title: URL's extern maken
description: De Externalzer is de dienst OSGI die u toestaat om een middelweg in een externe en absolute URL programmatically om te zetten
seo-description: De Externalzer is de dienst OSGI die u toestaat om een middelweg in een externe en absolute URL programmatically om te zetten
uuid: ea887096-1a48-4bdb-bc5c-e4fe719e5632
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: platform
content-type: reference
discoiquuid: 53342acb-c1a5-443d-8727-cb27cc9d6845
translation-type: tm+mt
source-git-commit: 8e2bd579e4c5edaaf86be36bd9d81dfffa13a573
workflow-type: tm+mt
source-wordcount: '533'
ht-degree: 0%

---


# URL&#39;s extern maken{#externalizing-urls}

In AEM, is **ExternalAlizer** de dienst OSGI die u toestaat om een middelweg programmatically om te zetten (b.v. `/path/to/my/page`) in een externe en absolute URL (bijvoorbeeld `https://www.mycompany.com/path/to/my/page`) door de weg met vooraf gevormde DNS te bevestigen.

Omdat een instantie zijn uiterlijk zichtbare URL niet kan kennen als het achter een Weblaag loopt, en omdat soms een verbinding buiten het verzoekwerkingsgebied moet worden gecreeerd, verstrekt deze dienst een centrale plaats om die externe URLs te vormen en hen te bouwen.

Deze pagina verklaart hoe te om de **Externalzer** dienst te vormen en hoe te om het te gebruiken. Raadpleeg [Javadocs](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/commons/Externalizer.html) voor meer informatie.

## De service ExternalAlizer {#configuring-the-externalizer-service} configureren

Met de service **ExternalAlizer** kunt u meerdere domeinen centraal definiëren die kunnen worden gebruikt om programmatisch een voorvoegsel voor bronnenpaden toe te voegen. Elk domein wordt geïdentificeerd door een unieke naam die wordt gebruikt om programmatically naar het domein te verwijzen.

Een domeinafbeelding definiëren voor de service **Externalalizer**:

1. Navigeer naar de configuratiemanager via **Tools**, dan **Webconsole**, of ga `https://<host>:<port>/system/console/configMgr.` in
1. Klik **De Verbinding van CQ van de Dag uiterlijk** om de doos van de configuratiedialoog te openen.

   >[!NOTE]
   >
   >De directe verbinding aan de configuratie is `https://<host>:<port>/system/console/configMgr/com.day.cq.commons.impl.ExternalizerImpl`

   ![chlimage_1-44](assets/chlimage_1-44.png)

1. Een domeintoewijzing definiëren: een toewijzing bestaat uit een unieke naam die in de code kan worden gebruikt om naar het domein, een ruimte en het domein te verwijzen:

   `<unique-name> [scheme://]server[:port][/contextpath]`, waarbij:

   * **De** schema&#39;s zijn gewoonlijk http of https, maar kunnen ook ftp etc. zijn.; gebruik https om https-koppelingen af te dwingen, indien gewenst; wordt gebruikt als de clientcode het schema niet overschrijft wanneer wordt gevraagd om externalisatie van een URL.
   * **De** server is de hostnaam (kan een domeinnaam of ip-adres zijn).
   * **port**  (optioneel) is het poortnummer.
   * **contextpath**  (optioneel) wordt alleen ingesteld als AEM is geïnstalleerd als een webapp onder een ander contextpad.

   Bijvoorbeeld: `production https://my.production.instance`

   De volgende toewijzingsnamen zijn vooraf gedefinieerd en moeten altijd worden ingesteld op basis van AEM:

   * **lokaal**  - de lokale instantie
   * **auteur**  - het auteurssysteem DNS
   * **publiceer**  - het publiek onder ogen ziet website DNS

   >[!NOTE]
   >
   >Met een aangepaste configuratie kunt u een nieuwe categorie toevoegen, zoals &quot;productie&quot;, &quot;staging&quot; of zelfs externe niet-AEM systemen, zoals &quot;mijn-interne webservice&quot;. Dit is handig om hardcodering van dergelijke URL&#39;s op verschillende plaatsen in de codebase van een project te voorkomen.

1. Klik **Opslaan** om uw wijzigingen op te slaan.

>[!NOTE]
>
>Adobe raadt aan dat u [de configuratie toevoegt aan de gegevensopslagruimte](/help/sites-deploying/configuring-osgi.md#adding-a-new-configuration-to-the-repository).

## De service ExternalAlizer gebruiken {#using-the-externalizer-service}

Deze sectie toont een paar voorbeelden van hoe de **Externalzer** dienst kan worden gebruikt.

**Om de dienst Externalzer in JSP te krijgen:**

`Externalizer externalizer = resourceResolver.adaptTo(Externalizer.class);`

**Een pad extern maken met het domein &#39;publish&#39;:**

`String myExternalizedUrl = externalizer.publishLink(resolver, "/my/page") + ".html";`

Ervan uitgaande dat de domeintoewijzing &quot; `publish https://www.website.com`&quot;, mijnExternalUrl eindigt met de waarde &quot; `https://www.website.com/contextpath/my/page.html`&quot;.

**Een pad extern maken met het domein &#39;auteur&#39;:**

`String myExternalizedUrl = externalizer.authorLink(resolver, "/my/page") + ".html";`

Ervan uitgaande dat de domeintoewijzing &quot; `author https://author.website.com`&quot;, mijnExternalUrl eindigt met de waarde &quot; `https://author.website.com/contextpath/my/page.html`&quot;.

**Een pad extern maken met het &#39;lokale&#39; domein:**

`String myExternalizedUrl = externalizer.externalLink(resolver, Externalizer.LOCAL, "/my/page") + ".html";`

Ervan uitgaande dat de domeintoewijzing &quot; `local https://publish-3.internal`&quot;, mijnExternalUrl eindigt met de waarde &quot; `https://publish-3.internal/contextpath/my/page.html`&quot;.

U kunt meer voorbeelden in [Javadocs](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/commons/Externalizer.html) vinden.
