---
title: Elementeninzicht inschakelen via DTM
description: Leer hoe u Adobe Dynamic Tag Management (DTM) gebruikt om Assets Insights in te schakelen.
contentOwner: AG
feature: Asset Insights,Asset Reports
role: User,Admin
exl-id: d19cea4d-5395-479d-b303-4529ae2c0bf2
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 0%

---

# Elementeninzicht inschakelen via DTM {#enabling-asset-insights-through-dtm}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Adobe Dynamic Tag Management is een programma waarmee u uw digitale marketingtools kunt activeren. Deze service wordt gratis aan Adobe Analytics-klanten aangeboden. U kunt de trackingcode aanpassen om CMS-oplossingen van derden in staat te stellen om Assets Insights te gebruiken, of u kunt DTM gebruiken om asset Insights-tags in te voegen. Inzichten worden alleen ondersteund en opgegeven voor afbeeldingen.

>[!CAUTION]
>
>Adobe DTM is vervangen door [!DNL Adobe Experience Platform] en zal binnenkort [einde van leven](https://medium.com/launch-by-adobe/dtm-plans-for-a-sunset-3c6aab003a6f). Adobe raadt u aan [gebruiken [!DNL Adobe Experience Platform] voor informatie over activa](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/advanced/asset-insights-launch-tutorial.html).

Voer deze stappen uit om Elementeninzichten door DTM toe te laten:

1. Tik/klik op de knop [!DNL Experience Manager] logo en ga naar **[!UICONTROL Tools]** > **[!UICONTROL Assets]** > **[!UICONTROL Insights Configuration]**.
1. [Configureren [!DNL Experience Manager] -instantie met DTM-Cloud Service](../sites-administering/dtm.md)

   De API-token moet beschikbaar zijn wanneer u zich aanmeldt bij [https://dtm.adobe.com](https://dtm.adobe.com/) en bezoek **[!UICONTROL Account Settings]** van het pictogram Profiel. Deze stap is niet vereist vanuit het standpunt van Assets Insights, omdat de integratie van [!DNL Experience Manager Sites] met Assets Insights bevindt zich nog in de werkzaamheden.

1. Aanmelden bij [https://dtm.adobe.com](https://dtm.adobe.com/)en selecteert u, naar gelang van het geval, een maatschappij.
1. Een bestaande webeigenschap maken/openen

   * Selecteer **[!UICONTROL Web Properties]** en tikken/klikken **[!UICONTROL Add Property]**.
   * Werk de velden naar wens bij en tik/klik op **[!UICONTROL Create Property]** (zie [documentatie](https://helpx.adobe.com/experience-manager/using/dtm.html)).

   ![chlimage_1-193](assets/chlimage_1-193.png)

1. In de **[!UICONTROL Rules]** tab, selecteert u **[!UICONTROL Page Load Rules]** vanuit het navigatievenster en tik/klik **[!UICONTROL Create New Rule]**.

   ![chlimage_1-194](assets/chlimage_1-194.png)

1. Uitbreiden **[!UICONTROL Javascript /Third Party Tags]**. Tik/klik op **[!UICONTROL Add New Script]** in de **[!UICONTROL Sequential HTML]** om het dialoogvenster Script te openen.

   ![chlimage_1-195](assets/chlimage_1-195.png)

1. Tik/klik op de knop [!DNL Experience Manager] logo en ga naar **[!UICONTROL Tools > Assets]**.
1. Tikken/klikken **[!UICONTROL Insights Page Tracker]**, kopieert u de trackercode en plakt u deze in het dialoogvenster Script dat u in stap 6 hebt geopend. Sla de wijzigingen op.

   >[!NOTE]
   >
   >* `AppMeasurement.js` is verwijderd. Naar verwachting is het beschikbaar via het Adobe Analytics-hulpprogramma van DTM.
   >* De oproep tot `assetAnalytics.dispatcher.init()` wordt verwijderd. De functie wordt naar verwachting aangeroepen zodra het Adobe Analytics-hulpprogramma van DTM is voltooid.
   >* Afhankelijk van de locatie waar Assets Insights Page Tracker wordt gehost (bijvoorbeeld AEM, CDN enzovoort), kan de oorsprong van de scriptbron wijzigingen vereisen.
   >* Voor AEM paginanummering moet de bron verwijzen naar een publicatie-instantie met de hostnaam van de verzendingsinstantie.


1. Openen [https://dtm.adobe.com](https://dtm.adobe.com). Klik op Overzicht in de webeigenschap en klik op Gereedschap toevoegen of open een bestaand Adobe Analytics-gereedschap. Tijdens het creëren van het hulpmiddel, kunt u de Methode van de Configuratie aan Automatisch plaatsen.

   ![chlimage_1-196](assets/chlimage_1-196.png)

   Selecteer de gewenste opties voor het rapport Staging/Productie.

1. Uitbreiden **[!UICONTROL Library Management]** en ervoor zorgen dat **[!UICONTROL Load Library at]** is ingesteld op **[!UICONTROL Page Top]**.

   ![chlimage_1-197](assets/chlimage_1-197.png)

1. Uitbreiden **[!UICONTROL Customize Page Code]** en klik of tik op **[!UICONTROL Open Editor]**.

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

   * De regel voor het laden van pagina&#39;s in DTM bevat alleen de code pagetracker.js. Alle `assetAnalytics` velden worden beschouwd als overschrijvingen voor standaardwaarden. Deze zijn niet standaard vereist.
   * De codeaanroepen `assetAnalytics.dispatcher.init()` na te gaan of `_satellite.getToolsByType('sc')[0].getS()` is geïnitialiseerd en `assetAnalytics,dispatcher.init` is beschikbaar. Daarom kunt u overslaan toevoegend het in stap 11.
   * Zoals aangegeven in opmerkingen binnen de code voor Inzichten van paginanummers (**[!UICONTROL Tools > Assets > Insights Page Tracker]**), wanneer Paginanummer geen `AppMeasurement` -object, zijn de eerste drie argumenten (RSID, Tracking Server en Visitor Namespace) irrelevant. Lege tekenreeksen worden doorgegeven om dit te markeren.

      De resterende argumenten komen overeen met wat is geconfigureerd in de pagina voor Inzichten configureren (**[!UICONTROL Tools > Assets > Insights Configuration]**).

   * Het object AppMeasurement wordt opgehaald door een query uit te voeren `satelliteLib` voor alle beschikbare SiteCatalyst-motoren. Als er meerdere tags zijn geconfigureerd, wijzigt u de index van de arraykiezer op de juiste manier. Items in de array worden geordend volgens de SiteCatalyst-gereedschappen die beschikbaar zijn in de DTM-interface.

1. Sla het venster Code-editor op, sluit dit en sla de wijzigingen vervolgens op in de configuratie van het gereedschap.
1. In de **[!UICONTROL Approvals]** , keurt beide goedkeuringen goed die in behandeling zijn. De tag DTM kan worden ingevoegd in uw webpagina. Zie de gearchiveerde pagina over informatie over het invoegen van DTM-tags in webpagina&#39;s voor meer informatie over [DTM integreren in aangepaste paginasjablonen](https://web.archive.org/web/20180816221834/https://blogs.adobe.com/experiencedelivers/experience-management/integrating-dtm-custom-aem6-page-template).
