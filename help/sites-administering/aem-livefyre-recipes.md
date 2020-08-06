---
title: AEM leverontvangers
seo-title: AEM leverontvangers
description: 'Stapsgewijze instructies over gangbare gebruiksgevallen voor Adobe Experience Manager Livefyre. '
seo-description: 'Stapsgewijze instructies over gangbare gebruiksgevallen voor Adobe Experience Manager Livefyre. '
uuid: 78695a63-fca6-4990-9755-0aeaae4a7f64
contentOwner: alba
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: integration
content-type: reference
discoiquuid: fdea5ede-d44f-463e-af8a-111ee7469ede
translation-type: tm+mt
source-git-commit: f1bf1545689b977a0f5074954df224db58cbd695
workflow-type: tm+mt
source-wordcount: '1559'
ht-degree: 0%

---


# AEM leverontvangers{#aem-livefyre-recipes}

Stapsgewijze instructies over gangbare gebruiksgevallen voor Adobe Experience Manager Livefyre.

## UGC krommen met de uit-van-de-doos AEM componenten en vertoning gebruikend de Muur van de Media van de Livefyre {#curate-ugc-using-the-out-of-the-box-livefyre-aem-components-and-display-using-livefyre-media-wall}

Media Wall streamt sociale en native Livefyre-inhoud naar een sociale muur in real time. Er zijn veelvoudige manieren om de Muur van Media in AEM afhankelijk van uw gebruiksgeval en vereisten uit te voeren.

Het AEM LiveCycle-pakket biedt een out-of-box implementatie, terwijl de traditionele integratie de mogelijkheid biedt om aangepaste Livefyre-AEM te maken.

### AEM integratie {#aem-integration}

Het Livefyre Adobe Experience Manager-pakket is beschikbaar voor AEM 6.1, 6.2SP1, 6.3, 6.4 en 6.4 SP1. AEM 5.x en 6.0 worden niet ondersteund. Zie [Integratie met Livefyre](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/livefyre.html)voor gedetailleerde instructies.

Zie de [AEM Ondersteuningsmatrix voor LiveCyre-apps](https://helpx.adobe.com/experience-manager/6-3/sites/administering/using/livefyre.html#AEMSupportMatrixforLivefyreApps)voor informatie over de ondersteunde Livefyre-apps.

### Traditionele implementatie (voor aangepaste AEM componenten) {#traditional-implementation-for-customized-aem-components}

Er zijn drie manieren om Livefy in een douane AEM component of andere CMSs zoals WordPress, Sitecore, of DemandWare uit te voeren. Een traditionele Livefyre-integratie is CMS agnostic.

**Methode 1: Designer-app-implementatie**

* **Wat:** Eenvoudige en snelste manier om een LiveCycle-app te integreren. U kunt een aangepaste JavaScript-insluitcode ontwerpen, configureren en genereren om een Media Wall-app op een pagina in minuten te integreren.
* **Hoe:**  [Een Media Wall-app maken, voorvertonen, publiceren en insluiten](https://docs.adobe.com/content/help/en/livefyre/using/apps/c-create-an-app.html)

* **Voorbeeld:** [https://codepen.io/dharafyre/pen/bvGrLo](https://codepen.io/dharafyre/pen/bvGrLo)

**Methode 2: SDK-implementatie**

* **Wat:** [Livefyre.js](https://docs.adobe.com/content/help/en/livefyre/implementation/c-livefyre_js.html) is de kernbibliotheek die Apps en Auth op een plaats macht. Het definieert het globale *window.Livefyre* -object en één openbare methode, *Livefyre.require*, die kan worden gebruikt om andere LiveScript-bibliotheken te laden die helpen bij het insluiten van Livefyre Apps en het integreren met externe gebruikersverificatieplatforms.

* **Hoe**: [Gebruik het streamhub-wallpakket van de Livefyre JavaScript SDK](https://docs.adobe.com/content/help/en/livefyre/implementation/app-integrations/c-media-wall-integration.html)

* **Voorbeeld**: [https://codepen.io/dharafyre/pen/KZKBNv?editors=1010](https://codepen.io/dharafyre/pen/KZKBNv?editors=1010)

Voor geavanceerde aanpassingen die SDK gebruiken, gelieve te verwijzen naar [StreamHub SDKs](https://github.com/Livefyre/streamhub-sdk).

**Methode 3: API-implementatie**

* Voor het maken van aangepaste ervaringen en gegevensvisualisaties kunnen LiveCyre-apps helemaal vanaf het begin worden gemaakt door LiveCycle- en sociale gegevens te gebruiken met de [Bootstrap- en Stream-API](https://docs.adobe.com/content/help/en/livefyre/implementation/advanced-topics/bootstrap-stream-api.html).

Volg de [Twitter](https://developer.twitter.com/en/developer-terms/display-requirements.html)-, [Facebook](https://en.facebookbrand.com/guidelines/brand)- en [Instagram](https://en.instagram-brand.com/) -weergaverichtlijnen bij het maken van de gebruikersinterface voor UGC.

### Integratie van mediumwand {#media-wall-authentication-integration}

Voor de Integraties van de Muur van Media die authentificatie vereisen, gelieve te verwijzen naar:

* [Single Sign on Integration](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/livefyre.html#CustomizeSingleSignonIntegration) aanpassen voor AEM Identity Management
* [Identiteitsintegratie](https://docs.adobe.com/content/help/en/livefyre/implementation/identity-integration/t-about-identity-integration.html) voor externe verificatieplatforms

### Hoofdlettergebruik - overzicht {#use-case-overview}

Als AEM klant, wil ik UGC leiden gebruikend de uit-van-de-doos AEM componenten en vertoning gebruikend de Muur van de Media van de Livefyre:

Uitvoeringsmaatregelen:

1. [Aan de slag](https://helpx.adobe.com/experience-manager/6-3/sites/administering/using/livefyre.html)
1. [AEM configureren voor gebruik van Livefyre](https://helpx.adobe.com/experience-manager/6-3/sites/administering/using/livefyre.html)
1. [Sleep AEM Media Wall-component naar de pagina](https://helpx.adobe.com/experience-manager/6-3/sites/administering/using/livefyre.html#UseLivefyrewithAEMSites)
1. [Vorm Streams en voeg regels toe om UGC en vertoning op de component van de Muur van Media te leiden](https://docs.adobe.com/content/help/en/livefyre/using/streams/c-streams.html)

Zie Automatische inhoudsstromen [maken en sociale inhoud zoeken in Adobe Experience Manager Live voor trainingsvideo&#39;s over het streamen van UGC](https://helpx.adobe.com/experience-manager/tutorials.html).

### Voorbeelden van klanten {#customer-examples}

* [CNN Media Wall](https://edition.cnn.com/specials/nepal-earthquake-media-wall)
* [PGA-kleurendrukschijf](https://www.pgatour.com/social-hub.html)

Voor het maken van aangepaste ervaringen en gegevensvisualisaties kunnen LiveCyre-apps helemaal vanaf het begin worden gemaakt door LiveCycle- en sociale gegevens te gebruiken met de [Bootstrap- en Stream-API](https://docs.adobe.com/content/help/en/livefyre/implementation/advanced-topics/bootstrap-stream-api.html).

Raadpleeg [Identiteitsintegratie](https://docs.adobe.com/content/help/en/livefyre/implementation/identity-integration/t-about-identity-integration.html) voor externe verificatieplatforms voor LiveCyre-apps die verificatie vereisen.

* [PGA-kleurendrukschijf](https://www.pgatour.com/social-hub.html)
* [TimeOut](https://www.timeout.com/london/restaurants/forest-bar-kitchen#tab_panel_3)

## Livefyre-opmerkingen integreren met AEM of traditionele Livefyre-integratie {#integrate-livefyre-comments-using-aem-components-or-traditional-livefyre-integration}

### AEM integratie {#aem-integration-1}

Het Livefyre Adobe Experience Manager-pakket is beschikbaar voor AEM 6.1, 6.2SP1, 6.3, 6.4 en 6.4 SP1. AEM 5.x en 6.0 worden niet ondersteund. Zie [Integratie met Livefyre](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/livefyre.html)voor gedetailleerde instructies.

### Traditionele implementatie (voor aangepaste AEM componenten) {#traditional-implementation-for-customized-aem-components-1}

Er zijn drie manieren om Livefyre Commentaar App in een douane AEM component of andere CMSs zoals WordPress, Sitecore, of DemandWare uit te voeren. Een traditionele Livefyre-integratie is CMS agnostic.

**Methode 1: Designer-app-implementatie**

* **Wat:** Eenvoudige en snelste manier om een LiveCycle-app te integreren. U kunt een aangepaste JavaScript-insluitcode ontwerpen, configureren en genereren om een Media Wall-app op een pagina in minuten te integreren.
* **Hoe:** [Een app voor opmerkingen maken, voorvertonen, publiceren en insluiten](https://docs.adobe.com/content/help/en/livefyre/using/apps/c-create-an-app.html)

* **Voorbeeld:** [https://codepen.io/dharafyre/pen/oYoJdP](https://codepen.io/dharafyre/pen/oYoJdP)

**Methode 2: SDK-implementatie**

* **Wat:** [Livefyre.js](https://docs.adobe.com/content/help/en/livefyre/implementation/c-livefyre_js.html) is de kernbibliotheek die Apps en Auth op een plaats macht. Het definieert het globale *window.Livefyre* -object en één openbare methode, *Livefyre.require*, die kan worden gebruikt om andere LiveScript-bibliotheken te laden die helpen bij het insluiten van Livefyre Apps en het integreren met externe gebruikersverificatieplatforms.

* **Hoe:**

   * Maak een verzameling/app met [token](https://docs.adobe.com/content/help/en/livefyre/implementation/getting-started/implementation-process/c-collectionmeta-tokent.html)CollectionMeta.
   * Integreer de [Commentaar-app](https://docs.adobe.com/content/help/en/livefyre/implementation/app-integrations/comments/c-comments-integration.html) in sites met behulp van de insluitcodestructuur van Livefyre.js.

* **Voorbeeld:**  [https://codepen.io/dharafyre/pen/oYoJdP](https://codepen.io/dharafyre/pen/oYoJdP)

Voor geavanceerde aanpassingen die SDK gebruiken, gelieve te zien [StreamHub SDKs](https://github.com/Livefyre/streamhub-sdk).

**Methode 3: API-implementatie**

* Voor het maken van aangepaste ervaringen en gegevensvisualisaties kunnen LiveCyre-apps helemaal vanaf het begin worden gemaakt door LiveCycle- en sociale gegevens te gebruiken met de [Bootstrap- en Stream-API](https://docs.adobe.com/content/help/en/livefyre/implementation/advanced-topics/bootstrap-stream-api.html).

### Integratie van verificatie van opmerkingen {#comments-app-authentication-integration}

* [Single Sign on Integration](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/livefyre.html#CustomizeSingleSignonIntegration) aanpassen voor AEM Identity Management
* [Identiteitsintegratie](https://docs.adobe.com/content/help/en/livefyre/implementation/identity-integration/t-about-identity-integration.html) voor externe verificatieplatforms

### Voorbeelden van klanten {#customer-examples-1}

* [Poise (Kimberly Klark)](https://www.poise.com/en-us/advice-and-support/blog-and-podcast/blog/5-holiday-party-tips-for-managing-lbl)

## De Livefyre AEM Assets-integratie gebruiken om UGC te importeren in AEM Assets {#use-livefyre-aem-assets-integration-to-import-ugc-in-aem-assets}

**Livefyre Setup (voor UGC Curation and Rights Management):**

1. [Vorm Streams en voeg Regels toe om UGC aan de Omslagen](https://docs.adobe.com/content/help/en/livefyre/using/streams/c-streams.html)van de Bibliotheek van Activa van LiveCycle te leiden.

   1. Zie Automatische inhoudsstromen [maken en sociale inhoud zoeken in Adobe Experience Manager Live voor trainingsvideo&#39;s over het streamen van UGC](https://helpx.adobe.com/experience-manager/tutorials.html).

1. [Geleide UGC verzamelen, ordenen en beheren in de mappen](https://docs.adobe.com/content/help/en/livefyre/using/library/assets/c-assets.html)van de bibliotheek van Livefyre Asset Library.

   1. Zie [Werken met middelen in Adobe Experience Manager LiveCycle voor trainingsvideo&#39;s over het maken en beheren van mappen in de LiveCycle Studio Asset Library](https://helpx.adobe.com/experience-manager/tutorials.html).

1. [Rechten aanvragen voor curated UGC met gebruik van LiveCyre Studio](https://docs.adobe.com/content/help/en/livefyre/using/rights-requests/c-how-requesting-rights-works.html).

**AEM instellen (voor het importeren van UGC naar AEM Assets):**

1. [Aan de slag](https://helpx.adobe.com/experience-manager/6-3/sites/administering/using/livefyre.html#GettingStarted)
1. [AEM configureren voor gebruik van Livefyre](https://helpx.adobe.com/experience-manager/6-3/sites/administering/using/livefyre.html#ConfigureAEMtouseLivefyre)
1. [UGC die door Livefyre in aan AEM Assets wordt beheerd importeren](https://helpx.adobe.com/experience-manager/6-3/sites/administering/using/livefyre.html#UseLivefyrewithAEMAssets)

* [Toerisme Australië](https://www.australia.com/en-us)

## LiveCyre Reviews integreren met AEM of traditionele LiveCyre-integratie {#integrate-livefyre-reviews-using-aem-components-or-traditional-livefyre-integration}

### AEM integratie {#aem-integration-2}

Het Livefyre Adobe Experience Manager-pakket is beschikbaar voor AEM 6.1, 6.2SP1, 6.3, 6.4 en 6.4 SP1. AEM 5.x en 6.0 worden niet ondersteund. Zie [Integratie met Livefyre](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/livefyre.html)voor gedetailleerde instructies.

De Component Reviews is geen ondersteunde component voor AEM 6.1. Controleer de [AEM-ondersteuningsmatrix voor alle Livefyre-apps](https://helpx.adobe.com/experience-manager/6-3/sites/administering/using/livefyre.html#AEMSupportMatrixforLivefyreApps).

### Traditionele implementatie (voor aangepaste AEM componenten) {#traditional-implementation-for-customized-aem-components-2}

Er zijn twee manieren om de app van de Revisies van Livefy in een douane AEM component of andere CMSs zoals WordPress, Sitecore, of DemandWare uit te voeren. Een traditionele Livefyre-integratie is CMS agnostic.

**Methode 1: SDK-implementatie**

* **Wat:** [Livefyre.js](https://docs.adobe.com/content/help/en/livefyre/implementation/c-livefyre_js.html) is de kernbibliotheek die Apps en Auth op een plaats macht. Het definieert het globale *window.Livefyre* -object en één openbare methode, *Livefyre.require*, die kan worden gebruikt om andere LiveScript-bibliotheken te laden die helpen bij het insluiten van Livefyre Apps en het integreren met externe gebruikersverificatieplatforms.

* **Hoe:**

   * Maak het token [Reviews](https://docs.adobe.com/content/help/en/livefyre/implementation/app-integrations/c-reviews-integration.html) CollectionMeta om metagegevens op te geven die moeten worden opgeslagen in de verzameling Revisies.
   * De [Revisies-app](https://docs.adobe.com/content/help/en/livefyre/implementation/app-integrations/c-reviews-integration.html) integreren in Sites met behulp van de codestructuur *Livefyre.js* .

* **Voorbeeld:**  [https://codepen.io/dharafyre/pen/GXgvvd](https://codepen.io/dharafyre/pen/GXgvvd)

Voor geavanceerde aanpassingen die SDK gebruiken, gelieve te zien [StreamHub SDKs](https://github.com/Livefyre/streamhub-sdk).

**Methode 2: API-implementatie**

* Voor het maken van aangepaste ervaringen en gegevensvisualisaties kunnen LiveCyre-apps helemaal vanaf het begin worden gemaakt door LiveCycle- en sociale gegevens te gebruiken met de API voor Bootstrap en streamen.

Aanvullende API&#39;s voor beoordelingen en revisies vindt u [hier](https://api.livefyre.com/docs/apis/by-category/ratings-and-reviews).

### Integratie van verificatie van opmerkingen {#comments-app-authentication-integration-1}

* [Single Sign on Integration](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/livefyre.html#CustomizeSingleSignonIntegration) aanpassen voor AEM Identity Management
* [Identiteitsintegratie](https://docs.adobe.com/content/help/en/livefyre/implementation/identity-integration/t-about-identity-integration.html) voor externe verificatieplatforms

### Voorbeelden van klanten {#customer-examples-2}

* [TimeOut](https://www.timeout.com/london/restaurants/forest-bar-kitchen#tab_panel_3)
* [myrecipes](https://www.myrecipes.com/recipe/shrimp-florentine-pasta)

