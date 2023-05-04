---
title: Configuraties van Cloud Servicen
description: U kunt de bestaande instanties uitbreiden om uw eigen configuraties tot stand te brengen.
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: extending-aem
content-type: reference
exl-id: d2b8503e-8ac1-4617-ad76-b05d1e80a6b6
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 0%

---

# Configuraties van Cloud Servicen{#cloud-service-configurations}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Configuraties zijn ontworpen om de logica en structuur te bieden voor het opslaan van serviceconfiguraties.

U kunt de bestaande instanties uitbreiden om uw eigen configuraties tot stand te brengen.

## Concepten {#concepts}

De beginselen die bij de ontwikkeling van de configuraties worden gebruikt, zijn gebaseerd op de volgende concepten:

* Services/adapters worden gebruikt om de configuratie(s) op te halen.
* Configuraties (bijvoorbeeld eigenschappen/alinea&#39;s) worden overgenomen van de bovenliggende elementen.
* Verwezen van analytische node(s) per pad.
* Gemakkelijk uitbreidbaar.
* Heeft de flexibiliteit om voor complexere configuraties, zoals te behandelen [Adobe Analytics](/help/sites-administering/marketing-cloud.md#integrating-with-adobe-analytics).
* Ondersteuning van afhankelijkheden (bv. [Adobe Analytics](/help/sites-administering/marketing-cloud.md#integrating-with-adobe-analytics) plug-ins hebben een [Adobe Analytics](/help/sites-administering/marketing-cloud.md#integrating-with-adobe-analytics) configuratie).

## Structuur {#structure}

Het basispad van de configuraties is:

`/etc/cloudservices`.

Voor elk type van configuratie zullen een malplaatje en een component worden verstrekt.Dit maakt het mogelijk om configuratiemalplaatjes te hebben die aan de meeste behoeften kunnen voldoen nadat wordt aangepast.

Om een configuratie voor de nieuwe diensten te verstrekken moet u:

* een servicepagina maken in

   `/etc/cloudservices`

* in dit verband :

   * een configuratiesjabloon
   * een configuratiecomponent

De sjabloon en component moeten de `sling:resourceSuperType` uit het basissjabloon:

`cq/cloudserviceconfigs/templates/configpage`

of basiscomponent

`cq/cloudserviceconfigs/components/configpage`

De dienstverlener zou ook de de dienstpagina moeten verstrekken:

`/etc/cloudservices/<service-name>`

### Sjabloon {#template}

Uw sjabloon breidt de basissjabloon uit:

`cq/cloudserviceconfigs/templates/configpage`

en een `resourceType` dat naar de aangepaste component wijst.

```xml
/libs/cq/analytics/templates/sitecatalyst
sling:resourceSuperType = cq/cloudserviceconfigs/templates/configpage
allowedChildren = /libs/cq/analytics/templates/sitecatalyst
allowedPaths = /etc/cloudservices/analytics/*, /etc/cloudservices/analytics/.*
componentReference = cq/analytics/components/sitecatalyst
jcr:content/
cq:designPath = /etc/designs/cloudservices
sling:resourceType = cq/analytics/components/sitecatalystpage

/libs/cq/analytics/templates/generictracker
sling:resourceSuperType = cq/cloudservices/templates/configpage
allowedChildren = /libs/cq/analytics/templates/generictracker
allowedPaths = /etc/cloudservices/analytics/*, /etc/cloudservices/analytics/.*
jcr:content/
cq:designPath = /etc/designs/cloudservices
sling:resourceType = cq/analytics/components/generictrackerpage
```

### Onderdelen {#components}

De component moet de basiscomponent uitbreiden:

`cq/cloudserviceconfigs/templates/configpage`

```xml
/libs/cq/analytics/components/sitecatalystpage

/libs/cq/analytics/components/generictrackerpage
```

Nadat u de sjabloon en de component hebt ingesteld, kunt u de configuratie toevoegen door subpagina&#39;s toe te voegen onder:

`/etc/cloudservices/<service-name>`

### Inhoudsmodel {#content-model}

Het inhoudsmodel wordt opgeslagen als `cq:Page` onder:

`/etc/cloudservices/<service-name>(/*)`

```xml
/etc/cloudservices
/etc/cloudservices/service-name
/etc/cloudservices/service-name/config
/etc/cloudservices/service-name/config/inherited-config
```

De configuraties worden opgeslagen onder het subknooppunt `jcr:content`.

* Vaste eigenschappen, gedefinieerd in een dialoogvenster, moeten worden opgeslagen op het tabblad `jcr:node` rechtstreeks.
* Dynamische elementen (gebruiken `parsys` of `iparsys`) gebruikt u een subknooppunt om de componentgegevens op te slaan.

```xml
/etc/cloudservices/service/config/jcr:content as nt:unstructured
propertyname
*
par/component/ as cq:Component
propertyname
*
```

### API {#api}

Zie voor documentatie over de API [com.day.cq.wcm.webservicesSupport](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/wcm/webservicesupport/package-summary.html).

### AEM integratie {#aem-integration}

Beschikbare services worden vermeld in de **Cloud Services** tabblad van het dialoogvenster **Pagina-eigenschappen** (van elke pagina die overerft van `foundation/components/page` of `wcm/mobile/components/page`).

Het tabblad bevat ook:

* een koppeling naar de locatie waar u de service kunt inschakelen
* Kies een configuratie (subknooppunt van de service) in een padveld

#### Wachtwoordversleuteling {#password-encryption}

Wanneer het opslaan van gebruikersgeloofsbrieven voor de dienst, zouden alle wachtwoorden moeten worden gecodeerd.

U kunt dit bereiken door een verborgen formulierveld toe te voegen. Dit veld moet de annotatie hebben `@Encrypted` in de naam van de eigenschap; d.w.z. voor de `password` in het veld zou de naam worden geschreven als:

`password@Encrypted`

De eigenschap wordt dan automatisch gecodeerd (met de opdracht `CryptoSupport` door de `EncryptionPostProcessor`.

>[!NOTE]
>
>Dit is vergelijkbaar met de standaard ` [SlingPostServlet](https://sling.apache.org/site/manipulating-content-the-slingpostservlet-servletspost.html)` annotaties.

>[!NOTE]
>
>Standaard worden de `EcryptionPostProcessor` alleen versleutelen `POST` verzoeken aan `/etc/cloudservices`.

#### Aanvullende eigenschappen voor servicepagina jcr:inhoudsknooppunten {#additional-properties-for-service-page-jcr-content-nodes}

<table> 
 <tbody> 
  <tr> 
   <td><strong>Eigenschap</strong></td> 
   <td><strong>Beschrijving</strong></td> 
  </tr> 
  <tr> 
   <td>componentReference</td> 
   <td>Verwijzingspad naar een component die automatisch op de pagina moet worden opgenomen.<br /> Dit wordt gebruikt voor extra functionaliteit en JS inbegrepen.<br /> Dit omvat de component op de pagina waar<br /> <code> cq/cloudserviceconfigs/components/servicecomponents</code><br /> wordt opgenomen (gewoonlijk vóór de <code>body</code> -tag).<br /> Voor het geval dat Analytics en Target dit gebruiken om extra functionaliteit op te nemen, zoals JavaScript-aanroepen om het gedrag van bezoekers te volgen.</td> 
  </tr> 
  <tr> 
   <td>beschrijving</td> 
   <td>Korte beschrijving van de dienst.<br /> </td> 
  </tr> 
  <tr> 
   <td>descriptionExtended</td> 
   <td>Uitgebreide beschrijving van de service.</td> 
  </tr> 
  <tr> 
   <td>rangschikking</td> 
   <td>Servicerangschikking voor gebruik in aanbiedingen.</td> 
  </tr> 
  <tr> 
   <td>selectableChildren</td> 
   <td>Filter voor het weergeven van configuraties in het dialoogvenster Pagina-eigenschappen.</td> 
  </tr> 
  <tr> 
   <td>serviceUrl</td> 
   <td>URL naar servicewebsite.</td> 
  </tr> 
  <tr> 
   <td>serviceUrlLabel</td> 
   <td>Label voor service-URL.</td> 
  </tr> 
  <tr> 
   <td>miniatuurPath</td> 
   <td>Pad naar miniatuur voor service.</td> 
  </tr> 
  <tr> 
   <td>visible</td> 
   <td>Zichtbaarheid in dialoogvenster Pagina-eigenschappen standaard zichtbaar (optioneel)</td> 
  </tr> 
 </tbody> 
</table>

### Gevallen gebruiken {#use-cases}

Deze services worden standaard geleverd:

* [Fragmenten voor Beheer](/help/sites-administering/external-providers.md) (Google, WebTrends enz.)
* [Adobe Analytics](/help/sites-administering/marketing-cloud.md#integrating-with-adobe-analytics)
* [&amp;Doel testen](/help/sites-administering/marketing-cloud.md#integrating-with-adobe-target)
* [ Dynamic Media ](/help/sites-administering/marketing-cloud.md#integrating-with-scene)

>[!NOTE]
>
>Zie ook [Een aangepaste Cloud Service maken](/help/sites-developing/extending-cloud-config-custom-cloud.md).
