---
title: Met de functie Asset Insights kunt u het gebruik van uw afbeeldingen bijhouden
description: Met de functie Asset Insights kunt u gebruikersbeoordelingen en gebruiksstatistieken bijhouden van afbeeldingen die worden gebruikt in websites van derden, marketingcampagnes en de creatieve oplossingen van Adobe.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 0e0e2aa693c30c8e1ef1033b936b82d83e5b348e

---


# Asset Insights {#asset-insights}

Leer hoe u met de functie Asset Insights gebruikersbeoordelingen en gebruiksstatistieken kunt bijhouden van middelen die worden gebruikt in websites van derden, marketingcampagnes en creatieve oplossingen van Adobe.

Met de functie Asset Insights kunt u gebruikersbeoordelingen en gebruiksstatistieken bijhouden van middelen die worden gebruikt in websites van derden, marketingcampagnes en creatieve oplossingen van Adobe om inzicht te krijgen in de prestaties en populariteit van deze middelen.

Met Elementinzichten worden details van gebruikersactiviteiten vastgelegd, zoals het aantal keren dat een element wordt beoordeeld, geklikt en afbeeldingen (het aantal keren dat het element op de website wordt geladen). Er worden op basis van deze statistieken scores toegekend aan activa. U kunt de scores en de prestatiesstatistieken gebruiken om populaire activa voor opneming in catalogi, marketing campagnes, etc. te selecteren. U kunt zelfs archiverings en vergunningsvernieuwing beleid voor activa formuleren die op deze statistieken worden gebaseerd.

Als u met behulp van Assets gebruiksstatistieken wilt vastleggen voor elementen van een website, moet u de insluitcode voor het element opnemen in de websitecode.

Om de statistieken van het vertoningsgebruik van Activa voor activa te laten, vorm eerst de eigenschap om rapportgegevens van te halen [!DNL Adobe Analytics]. Zie [Elementinzichten](touch-ui-configuring-asset-insights.md)configureren voor meer informatie.

>[!NOTE]
>
>Inzichten worden ondersteund en alleen voor afbeeldingen verstrekt.

## Statistieken voor een element weergeven {#viewing-statistics-for-an-asset}

U kunt de Asset Insights-scores van de metagegevenspagina weergeven.

1. Selecteer in de gebruikersinterface Elementen (UI) het element en tik op het pictogram **[!UICONTROL Eigenschappen]** /klik op de werkbalk.
1. Tik op of klik op het tabblad **[!UICONTROL Inzichten]** op de pagina Eigenschappen.
1. Controleer de gebruiksdetails voor het element op het tabblad **[!UICONTROL Inzichten]** . De sectie **[!UICONTROL Score]** beschrijft het totale gebruik en de prestatiesbronnen van activa van een activa.

   De score van het gebruik beschrijft het aantal tijden activa wordt gebruikt in diverse oplossingen.

   De **[!UICONTROL score Impressions]** is het aantal keren dat het element op de website wordt geladen. Het getal dat onder **[!UICONTROL Klikken]** wordt weergegeven, is het aantal keren dat op het element wordt geklikt.

1. Controleer de sectie **[!UICONTROL Gebruiksstatistieken]** om te weten bij welke entiteiten het element hoort en welke creatieve oplossingen het onlangs hebben gebruikt. Hoe hoger het gebruik, hoe groter de kans dat het middel populair is bij gebruikers. Gebruiksgegevens worden onder de volgende koppen weergegeven:

   * **[!UICONTROL Element]**: Het aantal keren dat het actief deel uitmaakte van een collectie of samengesteld actief
   * **[!UICONTROL Web en mobiel]**: Het aantal keren dat het middel deel uitmaakte van websites en apps
   * **[!UICONTROL Sociaal]**: Het aantal keren dat het middel is gebruikt in oplossingen, zoals Adobe Social en Adobe Campaign
   * **[!UICONTROL E-mail]**: Het aantal keren dat het middel in e-mailcampagnes is gebruikt
   ![usage_statistics](assets/usage_statistics.png)

   >[!NOTE]
   >
   >Omdat de functie Asset Insights de gegevens van Oplossingen gewoonlijk periodiek ophaalt van Adobe Analytics, wordt in de sectie Oplossingen mogelijk niet de meest recente gegevens weergegeven. De tijdspanne waarvoor de gegevens worden getoond hangt het programma van de haalverrichting af die de Inzichten van Activa loopt om de gegevens van de Analyse terug te winnen.

1. Om prestatiesstatistieken voor het actief grafisch over een periode te bekijken, selecteer periode in de sectie van de Statistieken **[!UICONTROL van]** Prestaties. De details, met inbegrip van kliks en impressies worden getoond als trendlijnen van een grafiek.

   ![chlimage_1-3](assets/chlimage_1-3.jpeg)

   >[!NOTE]
   >
   >In tegenstelling tot de gegevens in de sectie van Oplossingen, toont de sectie van de Statistieken van Prestaties de meest recente gegevens.

1. Tik op de **[!UICONTROL knop Insluitcode]** ophalen onder de elementminiatuur om de insluitcode te verkrijgen voor het element dat u in websites opneemt om prestatiegegevens op te halen. Zie [Werken met paginanummering en code insluiten in webpagina&#39;s van derden voor meer informatie over het opnemen van uw insluitcode in webpagina&#39;s](touch-ui-using-page-tracker.md).

   ![chlimage_1-303](assets/chlimage_1-303.png)

## Samengevoegde statistieken voor activa weergeven {#viewing-aggregate-statistics-for-assets}

U kunt scores van alle elementen in een map tegelijk weergeven met de **[!UICONTROL weergave]** Inzichten.

1. Navigeer in de interface Elementen naar de map met de elementen waarvoor u inzichten wilt weergeven.
1. Tik/klik op het pictogram Lay-out op de werkbalk en kies vervolgens **[!UICONTROL Inzichtsweergave]**.
1. Op de pagina worden gebruiksscores voor de elementen weergegeven. Vergelijk de ratings van de verschillende activa en teken inzichten.

## Achtergrondtaak plannen {#scheduling-background-job}

Asset Insights haalt op periodieke wijze gebruiksgegevens voor middelen op uit Adobe Analytics-rapportreeksen. Door gebrek, stelt de Inzichten van Activa een achtergrondbaan om de 24 uur bij 2 AM aan de ophaalgegevens in werking. U kunt echter zowel de frequentie als de tijd aanpassen door de **[!UICONTROL Adobe CQ DAM Asset Performance Report Sync Job]** Service via de webconsole te configureren.

1. Tik op het AEM-logo en ga naar **[!UICONTROL Gereedschappen > Bewerkingen > Webconsole]**.
1. Open de configuratie van de **[!UICONTROL Adobe CQ DAM Asset Performance Report Sync Job]** Service.

   ![chlimage_1-304](assets/chlimage_1-304.png)

1. Specificeer de gewenste plannerfrequentie en de begintijd voor de baan in de uitdrukking van de bezitsplanner. Sla de wijzigingen op.
