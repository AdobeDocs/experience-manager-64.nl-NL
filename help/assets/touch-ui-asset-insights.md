---
title: Met de functie Asset Insights kunt u het gebruik van uw afbeeldingen bijhouden
description: Met de functie Asset Insights kunt u gebruikersbeoordelingen en gebruiksstatistieken bijhouden van afbeeldingen die worden gebruikt in websites van derden, marketingcampagnes en creatieve oplossingen voor Adobe.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 0e0e2aa693c30c8e1ef1033b936b82d83e5b348e
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 2%

---


# Asset Insights {#asset-insights}

Leer hoe u met Asset Insights gebruikersbeoordelingen en gebruiksstatistieken kunt bijhouden van middelen die worden gebruikt in websites van derden, marketingcampagnes en creatieve oplossingen voor Adobe.

Met Asset Insights kunt u gebruikersbeoordelingen en gebruiksstatistieken bijhouden van elementen die in externe marketingcampagnes worden gebruikt, en creatieve oplossingen van Adobe bijhouden om inzicht te krijgen in de prestaties en populariteit van deze websites.

Met Elementinzichten worden details van gebruikersactiviteiten vastgelegd, zoals het aantal keren dat een element wordt beoordeeld, geklikt en afbeeldingen (het aantal keren dat het element op de website wordt geladen). Er worden op basis van deze statistieken scores toegekend aan activa. U kunt de scores en de prestatiesstatistieken gebruiken om populaire activa voor opneming in catalogi, marketing campagnes, etc. te selecteren. U kunt zelfs archiverings en vergunningsvernieuwing beleid voor activa formuleren die op deze statistieken worden gebaseerd.

Als u met behulp van Assets gebruiksstatistieken wilt vastleggen voor elementen van een website, moet u de insluitcode voor het element opnemen in de websitecode.

Om de statistieken van het vertoningsgebruik van Activa voor activa te laten, vorm eerst de eigenschap om rapportgegevens van te halen [!DNL Adobe Analytics]. Zie [Elementinzichten](touch-ui-configuring-asset-insights.md)configureren voor meer informatie.

>[!NOTE]
>
>Inzichten worden ondersteund en alleen voor afbeeldingen verstrekt.

## Statistieken voor een element weergeven {#viewing-statistics-for-an-asset}

U kunt de Asset Insights-scores van de metagegevenspagina weergeven.

1. Selecteer in de gebruikersinterface Elementen (UI) het element en tik op het **[!UICONTROL Properties]** pictogram op de werkbalk.
1. Tik of klik op de **[!UICONTROL Insights]** tab op de pagina Eigenschappen.
1. Controleer de gebruiksdetails voor het element op het **[!UICONTROL Insights]** tabblad. De **[!UICONTROL Score]** sectie beschrijft het totale gebruik en de prestatiesbronnen van activa van een activa.

   De score van het gebruik beschrijft het aantal tijden activa wordt gebruikt in diverse oplossingen.

   De **[!UICONTROL Impressions]** score is het aantal keren dat het element op de website wordt geladen. Het getal dat onder **[!UICONTROL Clicks]** wordt weergegeven, is het aantal keren dat op het element wordt geklikt.

1. Controleer de **[!UICONTROL Usage Statistics]** sectie om te weten bij welke entiteiten het actief hoort en welke creatieve oplossingen het onlangs heeft gebruikt. Hoe hoger het gebruik, hoe groter de kans dat het middel populair is bij gebruikers. Gebruiksgegevens worden onder de volgende koppen weergegeven:

   * **[!UICONTROL Asset]**: Het aantal keren dat het actief deel uitmaakte van een collectie of samengesteld actief
   * **[!UICONTROL Web & Mobile]**: Het aantal keren dat het middel deel uitmaakte van websites en apps
   * **[!UICONTROL Social]**: Het aantal keren dat het middel is gebruikt in oplossingen, zoals Adobe Social en Adobe Campaign
   * **[!UICONTROL Email]**: Het aantal keren dat het middel in e-mailcampagnes is gebruikt

   ![usage_statistics](assets/usage_statistics.png)

   >[!NOTE]
   >
   >Omdat de functie Asset Insights doorgaans de gegevens van Solutions van Adobe Analytics ophaalt, wordt in de sectie Oplossingen mogelijk niet de meest recente gegevens weergegeven. De tijdspanne waarvoor de gegevens worden getoond hangt het programma van de haalverrichting af die de Inzichten van Activa loopt om de gegevens van de Analyse terug te winnen.

1. To view performance statistics for the asset graphically over a period of time, select period in the **[!UICONTROL Performance Statistics]** section. De details, inclusief klikken en impressies, worden getoond als trendlijnen van een grafiek.

   ![chlimage_1-3](assets/chlimage_1-3.jpeg)

   >[!NOTE]
   >
   >In tegenstelling tot de gegevens in de sectie van Oplossingen, toont de sectie van de Statistieken van Prestaties de meest recente gegevens.

1. Tik op of klik **[!UICONTROL Get Embed Code]** onder de elementminiatuur om de insluitcode te verkrijgen voor het element dat u in websites opneemt om prestatiegegevens op te halen. Zie [Werken met paginanummering en code insluiten in webpagina&#39;s van derden voor meer informatie over het opnemen van uw insluitcode in webpagina&#39;s](touch-ui-using-page-tracker.md).

   ![chlimage_1-303](assets/chlimage_1-303.png)

## Samengevoegde statistieken voor activa weergeven {#viewing-aggregate-statistics-for-assets}

You can view scores of all assets within a folder simultaneously using **[!UICONTROL Insights View]**.

1. Navigeer in de interface Elementen naar de map met de elementen waarvoor u inzichten wilt weergeven.
1. Tik op het pictogram Lay-out of klik op het pictogram Lay-out op de werkbalk en kies **[!UICONTROL Insights View]**.
1. Op de pagina worden gebruiksscores voor de elementen weergegeven. Vergelijk de ratings van de verschillende activa en teken inzichten.

## Achtergrondtaak plannen {#scheduling-background-job}

Asset Insights haalt op periodieke wijze gebruiksgegevens voor middelen van Adobe Analytics-rapportensuites. Door gebrek, stelt de Inzichten van Activa een achtergrondbaan om de 24 uur bij 2 AM aan de ophaalgegevens in werking. Nochtans, kunt u zowel de frequentie als de tijd wijzigen door de **[!UICONTROL Adobe CQ DAM Asset Performance Report Sync Job]** dienst van de Webconsole te vormen.

1. Tap the AEM logo, and go to **[!UICONTROL Tools > Operations > Web Console]**.
1. Open de **[!UICONTROL Adobe CQ DAM Asset Performance Report Sync Job]** serviceconfiguratie.

   ![chlimage_1-304](assets/chlimage_1-304.png)

1. Specificeer de gewenste plannerfrequentie en de begintijd voor de baan in de uitdrukking van de bezitsplanner. Sla de wijzigingen op.
