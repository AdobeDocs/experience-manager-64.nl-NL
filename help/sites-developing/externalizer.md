---
title: URL's extern maken
seo-title: Externalizing URLs
description: De Externalzer is de dienst OSGI die u toestaat om een middelweg in een externe en absolute URL programmatically om te zetten
seo-description: The Externalizer is an OSGI service that allows you to programmatically transform a resource path into an external and absolute URL
uuid: ea887096-1a48-4bdb-bc5c-e4fe719e5632
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: platform
content-type: reference
discoiquuid: 53342acb-c1a5-443d-8727-cb27cc9d6845
exl-id: 123ef72b-f09b-47eb-9b5a-e0deb38799df
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 0%

---

# URL&#39;s extern maken{#externalizing-urls}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

In AEM **ExternalAlizer** is een dienst OSGI die u toestaat om een middelweg programmatically om te zetten (b.v. `/path/to/my/page`) in een externe en absolute URL (bijvoorbeeld `https://www.mycompany.com/path/to/my/page`) door het pad vooraf te bevestigen met een vooraf geconfigureerde DNS.

Omdat een instantie zijn uiterlijk zichtbare URL niet kan kennen als het achter een Weblaag loopt, en omdat soms een verbinding buiten het verzoekwerkingsgebied moet worden gecreeerd, verstrekt deze dienst een centrale plaats om die externe URLs te vormen en hen te bouwen.

Deze pagina verklaart hoe te om te vormen **ExternalAlizer** en hoe deze te gebruiken. Raadpleeg voor meer informatie de [Javadocs](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/commons/Externalizer.html).

## De service ExternalAlizer configureren {#configuring-the-externalizer-service}

De **ExternalAlizer** De dienst staat u toe om veelvoudige domeinen centraal te bepalen die aan programmatically prefixmiddelwegen kunnen worden gebruikt. Elk domein wordt geïdentificeerd door een unieke naam die wordt gebruikt om programmatically naar het domein te verwijzen.

Een domeintoewijzing definiëren voor de **ExternalAlizer** service:

1. Navigeer naar de configuratiemanager via **Gereedschappen** vervolgens **Webconsole**, of voer `https://<host>:<port>/system/console/configMgr.`
1. Klikken **Day CQ Link ExternalAlizer** om het dialoogvenster Configuratie te openen.

   >[!NOTE]
   >
   >De directe koppeling naar de configuratie is `https://<host>:<port>/system/console/configMgr/com.day.cq.commons.impl.ExternalizerImpl`

   ![chlimage_1-44](assets/chlimage_1-44.png)

1. Een domeintoewijzing definiëren: een toewijzing bestaat uit een unieke naam die in de code kan worden gebruikt om naar het domein, een ruimte en het domein te verwijzen:

   `<unique-name> [scheme://]server[:port][/contextpath]`, waarbij:

   * **regeling** is meestal http of https, maar kan ook ftp enz. zijn.; gebruik https om https-koppelingen af te dwingen, indien gewenst; wordt gebruikt als de clientcode het schema niet overschrijft wanneer wordt gevraagd om externalisatie van een URL.
   * **server** is de gastheernaam (kan een domeinnaam of ip adres zijn).
   * **poort** (optioneel) is het poortnummer.
   * **contextpad** (optioneel) wordt alleen ingesteld als AEM is geïnstalleerd als een webapp onder een ander contextpad.

   Bijvoorbeeld: `production https://my.production.instance`

   De volgende toewijzingsnamen zijn vooraf gedefinieerd en moeten altijd worden ingesteld op basis van AEM:

   * **lokaal** - de lokale instantie
   * **auteur** - DNS van het ontwerpsysteem
   * **publish** - het publiek met de website DNS geconfronteerd

   >[!NOTE]
   >
   >Met een aangepaste configuratie kunt u een nieuwe categorie toevoegen, zoals &quot;productie&quot;, &quot;staging&quot; of zelfs externe niet-AEM systemen, zoals &quot;mijn-interne webservice&quot;. Dit is handig om hardcodering van dergelijke URL&#39;s op verschillende plaatsen in de codebase van een project te voorkomen.

1. Klikken **Opslaan** om uw wijzigingen op te slaan.

>[!NOTE]
>
>Adobe raadt u aan [de configuratie toevoegen aan de repository](/help/sites-deploying/configuring-osgi.md#adding-a-new-configuration-to-the-repository).

## De service ExternalAlizer gebruiken {#using-the-externalizer-service}

In deze sectie worden enkele voorbeelden getoond van de manier waarop **ExternalAlizer** kan worden gebruikt.

**Om de dienst Externalzer in JSP te krijgen:**

`Externalizer externalizer = resourceResolver.adaptTo(Externalizer.class);`

**Een pad extern maken met het domein &#39;publish&#39;:**

`String myExternalizedUrl = externalizer.publishLink(resolver, "/my/page") + ".html";`

Het veronderstellen van de domeinafbeelding &quot; `publish https://www.website.com`&quot;, eindigt myExternalUrl met de waarde &quot; `https://www.website.com/contextpath/my/page.html`&quot;.

**Een pad extern maken met het domein &#39;auteur&#39;:**

`String myExternalizedUrl = externalizer.authorLink(resolver, "/my/page") + ".html";`

Het veronderstellen van de domeinafbeelding &quot; `author https://author.website.com`&quot;, eindigt myExternalUrl met de waarde &quot; `https://author.website.com/contextpath/my/page.html`&quot;.

**Een pad extern maken met het &#39;lokale&#39; domein:**

`String myExternalizedUrl = externalizer.externalLink(resolver, Externalizer.LOCAL, "/my/page") + ".html";`

Het veronderstellen van de domeinafbeelding &quot; `local https://publish-3.internal`&quot;, eindigt myExternalUrl met de waarde &quot; `https://publish-3.internal/contextpath/my/page.html`&quot;.

Meer voorbeelden vindt u in het gedeelte [Javadocs](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/commons/Externalizer.html).
