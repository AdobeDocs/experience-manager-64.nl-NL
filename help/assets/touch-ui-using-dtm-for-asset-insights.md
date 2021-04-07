---
title: Asset Insights inschakelen via DTM
description: Leer hoe u DTM (Adobe Dynamic Tag Management) gebruikt om Asset Insights in te schakelen.
contentOwner: AG
feature: Asset Insights, Asset Reports
role: Business Practitioner,Administrator
exl-id: d19cea4d-5395-479d-b303-4529ae2c0bf2
translation-type: tm+mt
source-git-commit: bd94d3949f0117aa3e1c9f0e84f7293a5d6b03b4
workflow-type: tm+mt
source-wordcount: '627'
ht-degree: 3%

---

# Asset Insights inschakelen via DTM {#enabling-asset-insights-through-dtm}

Adobe Dynamisch tagbeheer is een programma waarmee u uw digitale marketingtools kunt activeren. Deze service wordt gratis aan Adobe Analytics-klanten aangeboden. U kunt uw trackingcode aanpassen om CMS-oplossingen van derden in staat te stellen Asset Insights te gebruiken, of u kunt DTM gebruiken om labels voor Asset Insights in te voegen. Inzichten worden alleen ondersteund en opgegeven voor afbeeldingen.

>[!CAUTION]
>
>Adobe DTM is vervangen door Adobe Experience Platform Launch en zal binnenkort [einde van leven](https://medium.com/launch-by-adobe/dtm-plans-for-a-sunset-3c6aab003a6f) bereiken. Adobe raadt u aan [Launch te gebruiken voor elementinzichten](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/advanced/asset-insights-launch-tutorial.html).

Voer deze stappen uit om Asset Insights in te schakelen via DTM:

1. Tik of klik op het AEM-logo en ga naar **[!UICONTROL Tools > Assets > Insights Configuration]**.
1. [AEM instantie configureren met DTM Cloud Service](../sites-administering/dtm.md)

   De API-token moet beschikbaar zijn wanneer u zich aanmeldt bij [https://dtm.adobe.com](https://dtm.adobe.com/) en **[!UICONTROL Account Settings]** bezoekt via het pictogram Profiel. Deze stap is niet vereist vanuit het standpunt van Asset Insights, omdat de integratie van AEM Sites met Asset Insights nog steeds in de werkzaamheden plaatsvindt.

1. Meld u aan bij [https://dtm.adobe.com](https://dtm.adobe.com/) en selecteer een bedrijf.
1. Een bestaande webeigenschap maken/openen

   * Selecteer de tab **[!UICONTROL Web Properties]** en tik op **[!UICONTROL Add Property]**.
   * Werk de velden naar wens bij en tik/klik op **[!UICONTROL Create Property]** (zie [documentatie](https://helpx.adobe.com/experience-manager/using/dtm.html)).

   ![chlimage_1-193](assets/chlimage_1-193.png)

1. Selecteer op het tabblad **[!UICONTROL Rules]** **[!UICONTROL Page Load Rules]** in het navigatievenster en tik/klik **[!UICONTROL Create New Rule]**.

   ![chlimage_1-194](assets/chlimage_1-194.png)

1. **[!UICONTROL Javascript /Third Party Tags]** uitbreiden. Tik vervolgens op **[!UICONTROL Add New Script]** op het tabblad **[!UICONTROL Sequential HTML]** om het dialoogvenster Script te openen.

   ![chlimage_1-195](assets/chlimage_1-195.png)

1. Tik of klik op het AEM-logo en ga naar **[!UICONTROL Tools > Assets]**.
1. Tik/klik op **[!UICONTROL Insights Page Tracker]**, kopieer de trackercode en plak deze vervolgens in het dialoogvenster Script dat u in stap 6 hebt geopend. Sla de wijzigingen op.

   >[!NOTE]
   >
   >* `AppMeasurement.js` is verwijderd. Naar verwachting is het beschikbaar via het Adobe Analytics-hulpprogramma van DTM.
   >* De vraag aan `assetAnalytics.dispatcher.init()` wordt verwijderd. De functie wordt naar verwachting aangeroepen zodra het Adobe Analytics-hulpprogramma van DTM is voltooid.
   >* Afhankelijk van de plaats waar Asset Insights Page Tracker wordt gehost (bijvoorbeeld AEM, CDN enzovoort), kan de oorsprong van de scriptbron wijzigingen vereisen.
   >* Voor AEM paginanummering moet de bron verwijzen naar een publicatie-instantie met de hostnaam van de verzendingsinstantie.


1. Open [https://dtm.adobe.com](https://dtm.adobe.com). Klik op Overzicht in de webeigenschap en klik op Gereedschap toevoegen of open een bestaand Adobe Analytics-gereedschap. Tijdens het creëren van het hulpmiddel, kunt u de Methode van de Configuratie aan Automatisch plaatsen.

   ![chlimage_1-196](assets/chlimage_1-196.png)

   Selecteer de gewenste opties voor het rapport Staging/Productie.

1. Vouw **[!UICONTROL Library Management]** uit en controleer of **[!UICONTROL Load Library at]** is ingesteld op **[!UICONTROL Page Top]**.

   ![chlimage_1-197](assets/chlimage_1-197.png)

1. Vouw **[!UICONTROL Customize Page Code]** uit en klik of tik **[!UICONTROL Open Editor]**.

   ![chlimage_1-198](assets/chlimage_1-198.png)

1. Plak de volgende code in het venster:

   ```java
   var sObj;
   
   if (arguments.length > 0) {
     sObj = arguments[0];
   } else {
     sObj = _satellite.getToolsByType('sc')[0].getS();
   }
   _satellite.notify('in assetAnalytics customInit');
   (function initializeAssetAnalytics() {
     if ((!!window.assetAnalytics) && (!!assetAnalytics.dispatcher)) {
       _satellite.notify('assetAnalytics ready');
       /** NOTE:
           Copy over the call to 'assetAnalytics.dispatcher.init()' from Assets Pagetracker
           Be mindful about changing the AppMeasurement object as retrieved above.
       */
       assetAnalytics.dispatcher.init(
             "",  /** RSID to send tracking-call to */
             "",  /** Tracking Server to send tracking-call to */
             "",  /** Visitor Namespace to send tracking-call to */
             "",  /** listVar to put comma-separated-list of Asset IDs for Asset Impression Events in tracking-call, e.g. 'listVar1' */
             "",  /** eVar to put Asset ID for Asset Click Events in, e.g. 'eVar3' */
             "",  /** event to include in tracking-calls for Asset Impression Events, e.g. 'event8' */
             "",  /** event to include in tracking-calls for Asset Click Events, e.g. 'event7' */
             sObj  /** [OPTIONAL] if the webpage already has an AppMeasurement object, please include the object here. If unspecified, Pagetracker Core shall create its own AppMeasurement object */
             );
       sObj.usePlugins = true;
       sObj.doPlugins = assetAnalytics.core.updateContextData;
       assetAnalytics.core.optimizedAssetInsights();
     }
     else {
       _satellite.notify('assetAnalytics not available. Consider updating the Custom Page Code', 4);
     }
   })();
   ```

   * De regel voor het laden van pagina&#39;s in DTM bevat alleen de code pagetracker.js. Alle `assetAnalytics`-velden worden beschouwd als overschrijvingen voor standaardwaarden. Deze zijn niet standaard vereist.
   * De code roept `assetAnalytics.dispatcher.init()` na ervoor te zorgen dat `_satellite.getToolsByType('sc')[0].getS()` wordt geïnitialiseerd en `assetAnalytics,dispatcher.init` beschikbaar is. Daarom kunt u overslaan toevoegend het in stap 11.
   * Zoals aangegeven in opmerkingen in de code voor Paginanummering met inzichten (**[!UICONTROL Tools > Assets > Insights Page Tracker]**), zijn de eerste drie argumenten (RSID, Tracking Server en Naamruimte bezoeker) irrelevant wanneer Paginanummering geen `AppMeasurement`-object maakt. Lege tekenreeksen worden doorgegeven om dit te markeren.

      De resterende argumenten beantwoorden aan wat in de pagina van de Configuratie van Inzichten (**[!UICONTROL Tools > Assets > Insights Configuration]**) wordt gevormd.

   * Het object AppMeasurement wordt opgehaald door `satelliteLib` te vragen voor alle beschikbare SiteCatalyst engines. Als er meerdere tags zijn geconfigureerd, wijzigt u de index van de arraykiezer op de juiste manier. Items in de array worden geordend volgens de SiteCatalyst-gereedschappen die beschikbaar zijn in de DTM-interface.

1. Sla het venster Code-editor op, sluit dit en sla de wijzigingen vervolgens op in de configuratie van het gereedschap.
1. Goedkeuren beide goedkeuringen die in behandeling zijn op het tabblad **[!UICONTROL Approvals]**. De tag DTM kan worden ingevoegd in uw webpagina. Zie [DTM integreren in aangepaste paginasjablonen](https://blogs.adobe.com/experiencedelivers/experience-management/integrating-dtm-custom-aem6-page-template/) voor meer informatie over het invoegen van DTM-tags in webpagina&#39;s.
