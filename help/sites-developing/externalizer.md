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

In AEM, is **ExternalAlizer** de dienst OSGI die u toestaat om een middelweg programmatically om te zetten (b.v. `/path/to/my/page`) in een externe en absolute URL (bijvoorbeeld `https://www.mycompany.com/path/to/my/page`) door het pad vooraf te definiëren met een vooraf geconfigureerde DNS.

Omdat een instantie zijn uiterlijk zichtbare URL niet kan kennen als het achter een Weblaag loopt, en omdat soms een verbinding buiten het verzoekwerkingsgebied moet worden gecreeerd, verstrekt deze dienst een centrale plaats om die externe URLs te vormen en hen te bouwen.

Deze pagina verklaart hoe te om de **dienst te vormen External** en hoe te om het te gebruiken. Raadpleeg de [JavaDocs voor meer informatie](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/commons/Externalizer.html).

## De service ExternalAlizer configureren {#configuring-the-externalizer-service}

De dienst **External** staat u toe om veelvoudige domeinen centraal te bepalen die kunnen worden gebruikt om middelwegen programmatically voor te stellen. Elk domein wordt geïdentificeerd door een unieke naam die wordt gebruikt om programmatically naar het domein te verwijzen.

Om een domeinafbeelding voor de dienst **Externalzer** te bepalen:

1. Navigeer aan de configuratiemanager via **Hulpmiddelen**, dan de Console **van het** Web, of ga binnen `https://<host>:<port>/system/console/configMgr.`
1. Klik op **Day CQ Link Externalzer** om het configuratiedialoogvenster te openen.

   >[!NOTE]
   >
   >De directe koppeling naar de configuratie is `https://<host>:<port>/system/console/configMgr/com.day.cq.commons.impl.ExternalizerImpl`

   ![chlimage_1-44](assets/chlimage_1-44.png)

1. Een domeintoewijzing definiëren: een toewijzing bestaat uit een unieke naam die in de code kan worden gebruikt om naar het domein, een ruimte en het domein te verwijzen:

   `<unique-name> [scheme://]server[:port][/contextpath]`, waarbij:

   * **het schema** is meestal http of https, maar kan ook ftp enz. zijn.; gebruik https om https-koppelingen af te dwingen, indien gewenst; wordt gebruikt als de clientcode het schema niet overschrijft wanneer wordt gevraagd om externalisatie van een URL.
   * **server** is de hostnaam (kan een domeinnaam of ip-adres zijn).
   * **poort** (optioneel) is het poortnummer.
   * **contextpath** (optioneel) wordt alleen ingesteld als AEM is geïnstalleerd als een webapp onder een ander contextpad.

   Bijvoorbeeld: `production https://my.production.instance`

   De volgende toewijzingsnamen zijn vooraf gedefinieerd en moeten altijd worden ingesteld op basis van AEM:

   * **lokaal** - de lokale instantie
   * **auteur** - het auteurssysteem DNS
   * **publish** - het publiek onder ogen ziet website DNS

   >[!NOTE]
   >
   >Met een aangepaste configuratie kunt u een nieuwe categorie toevoegen, zoals &quot;productie&quot;, &quot;staging&quot; of zelfs externe niet-AEM systemen, zoals &quot;mijn-interne webservice&quot;. Dit is handig om hardcodering van dergelijke URL&#39;s op verschillende plaatsen in de codebase van een project te voorkomen.

1. Klik op **Opslaan** om de wijzigingen op te slaan.

>[!NOTE]
>
>Adobe raadt u aan de configuratie [toe te voegen aan de opslagplaats](/help/sites-deploying/configuring-osgi.md#adding-a-new-configuration-to-the-repository).

## De service ExternalAlizer gebruiken {#using-the-externalizer-service}

Deze sectie toont een paar voorbeelden van hoe de dienst **External** kan worden gebruikt.

**Om de dienst Externalzer in JSP te krijgen:**

`Externalizer externalizer = resourceResolver.adaptTo(Externalizer.class);`

**Een pad extern maken met het domein &#39;publish&#39;:**

`String myExternalizedUrl = externalizer.publishLink(resolver, "/my/page") + ".html";`

Ervan uitgaande dat de domeintoewijzing &quot; `publish https://www.website.com`&quot; is, eindigt myExternalUrl met de waarde &quot; `https://www.website.com/contextpath/my/page.html`&quot;.

**Een pad extern maken met het domein &#39;auteur&#39;:**

`String myExternalizedUrl = externalizer.authorLink(resolver, "/my/page") + ".html";`

Ervan uitgaande dat de domeintoewijzing &quot; `author https://author.website.com`&quot; is, eindigt myExternalUrl met de waarde &quot; `https://author.website.com/contextpath/my/page.html`&quot;.

**Een pad extern maken met het &#39;lokale&#39; domein:**

`String myExternalizedUrl = externalizer.externalLink(resolver, Externalizer.LOCAL, "/my/page") + ".html";`

Ervan uitgaande dat de domeintoewijzing &quot; `local https://publish-3.internal`&quot; is, eindigt myExternalUrl met de waarde &quot; `https://publish-3.internal/contextpath/my/page.html`&quot;.

Meer voorbeelden vindt u in de [JavaDocs](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/commons/Externalizer.html).
