---
title: Brontoewijzing
seo-title: Resource Mapping
description: Leer hoe te om omleidingen, ijdelheid URLs en virtuele gastheren voor AEM te bepalen door middel van middeltoewijzing.
seo-description: Learn how to define redirects, vanity URLs and virtual hosts for AEM by using resource mapping.
uuid: 33de7e92-8144-431b-badd-e6a667cd78e1
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: configuring
content-type: reference
discoiquuid: ddfacc63-1840-407e-8802-3730009c84f0
feature: Configuring
exl-id: 81dddbab-1a9e-49ee-b2a5-a8e4de3630d1
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '557'
ht-degree: 0%

---

# Brontoewijzing{#resource-mapping}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

De afbeelding van het middel wordt gebruikt om omleidingen, ijdelheid URLs en virtuele gastheren voor AEM te bepalen.

U kunt bijvoorbeeld de volgende toewijzingen gebruiken:

* Alle aanvragen vooraf bevestigen met `/content` zodat de interne structuur verborgen is voor de bezoekers van uw website.
* Definieer een omleiding, zodat alle verzoeken aan de `/content/en/gateway` pagina van uw website wordt omgeleid naar `https://gbiv.com/`.

Eén mogelijke HTTP-toewijzing [fixes all request to localhost:4503 with /content](#configuring-an-internal-redirect-to-content). Een dergelijke afbeelding kan worden gebruikt om de interne structuur te verbergen voor bezoekers van de website, voor zover dat mogelijk is:

`localhost:4503/content/geometrixx/en/products.html`

die toegankelijk zijn via:

`localhost:4503/geometrixx/en/products.html`

als de toewijzing automatisch het voorvoegsel toevoegt `/content` tot `/geometrixx/en/products.html`.

>[!CAUTION]
>
>Vanity URLs steunt geen regex patronen.

>[!NOTE]
>
>Zie de documentatie over verkopers, en [Toewijzingen voor resolutie van bronnen](https://sling.apache.org/site/resources.html) en [Bronnen](https://sling.apache.org/site/mappings-for-resource-resolution.html) voor nadere informatie.

## Definities voor weergavetoewijzing {#viewing-mapping-definitions}

De toewijzingen uit twee lijsten die de Resolver van het Middel JCR (top-down) evalueert om een gelijke te vinden.

Deze lijsten kunnen (samen met configuratiegegevens) onder de **JCR ResourceResolver** optie van de Felix-console; bijvoorbeeld: `https://<host>:<port>/system/console/jcrresolver`:

* Configuratie

   Hiermee wordt de huidige configuratie weergegeven (zoals gedefinieerd voor de [Resolver Apache Sling-resource](/help/sites-deploying/osgi-configuration-settings.md).

* Configuratietest

   Op deze manier kunt u een URL- of bronpad invoeren. Klikken **Oplossen** of **Kaart** om te bevestigen hoe het systeem de ingang zal omzetten.

* **Resolver Map-items**
De lijst van ingangen die door de methodes ResourceResolver.resolve worden gebruikt om URLs aan Middelen in kaart te brengen.

* **Toewijzingskaartitems**
De lijst van ingangen die door de methodes ResourceResolver.map worden gebruikt om de Wegen van het Middel aan URLs in kaart te brengen.

De twee lijsten bevatten verschillende items, waaronder items die door de toepassing(en) als standaardwaarden zijn gedefinieerd. Deze zijn vaak bedoeld om URL&#39;s voor de gebruiker te vereenvoudigen.

De lijsten vormen een paar **Patroon**, een reguliere expressie die overeenkomt met de aanvraag, met een **Vervanging** Hiermee definieert u de omleiding die moet worden toegepast.

Bijvoorbeeld:

**Patroon** `^[^/]+/[^/]+/welcome$`

wordt geactiveerd voor:

**Vervanging** `/libs/cq/core/content/welcome.html`.

om een verzoek om te leiden:

`http://localhost:4503/welcome`

tot:

`http://localhost:4503/libs/cq/core/content/welcome.html`

Er worden nieuwe toewijzingsdefinities gemaakt in de repository.

>[!NOTE]
>
>Er zijn vele beschikbare middelen die helpen verklaren hoe te om regelmatige uitdrukkingen te bepalen; bijvoorbeeld [https://www.regular-expressions.info/](https://www.regular-expressions.info/).

## Toewijzingsdefinities maken in AEM {#creating-mapping-definitions-in-aem}

In een standaardinstallatie van AEM kunt u de map vinden:

`/etc/map/http`

Dit is de structuur die wordt gebruikt bij het definiëren van toewijzingen voor het HTTP-protocol. Overige mappen ( `sling:Folder`) kan worden gemaakt onder `/etc/map` voor andere protocollen die u in kaart wilt brengen.

### Het vormen van Interne Redirect aan /content {#configuring-an-internal-redirect-to-content}

Om de afbeelding tot stand te brengen die om het even welk verzoek aan http://localhost:4503/ met prefixen `/content`:

1. Met CRXDE navigeert u naar `/etc/map/http`.

1. Een nieuw knooppunt maken:

   * **Type** `sling:Mapping`

      Dit knooppunttype is bedoeld voor dergelijke afbeeldingen, hoewel het gebruik ervan niet verplicht is.

   * **Naam** `localhost_any`

1. Klikken **Alles opslaan**.
1. **Toevoegen** de volgende eigenschappen voor dit knooppunt:

   * **Naam** `sling:match`

      * **Type** `String`
      * **Waarde** `localhost.4503/`
   * **Naam** `sling:internalRedirect`

      * **Type** `String`
      * **Waarde** `/content/`


1. Klikken **Alles opslaan**.

Dit behandelt een verzoek zoals:\
`localhost:4503/geometrixx/en/products.html`\
alsof:\
`localhost:4503/content/geometrixx/en/products.html`\
is aangevraagd.

>[!NOTE]
>
>Zie [Bronnen](https://sling.apache.org/site/mappings-for-resource-resolution.html) in de Verschuivende Documentatie voor verdere informatie over de beschikbare hellingseigenschappen en hoe zij kunnen worden gevormd.

>[!NOTE]
>
>U kunt `/etc/map.publish` om de configuraties voor het publicatiemilieu te houden. Deze moeten vervolgens worden gerepliceerd en de nieuwe locatie ( `/etc/map.publish`) geconfigureerd voor de **Toewijzingslocatie** van de [Resolver Apache Sling-resource](/help/sites-deploying/osgi-configuration-settings.md#apacheslingresourceresolver) van de publicatieomgeving.
