---
title: Met de functie Asset Insights kunt u het gebruik van uw afbeeldingen bijhouden
description: Met de functie Asset Insights kunt u gebruikersbeoordelingen en gebruiksstatistieken bijhouden van afbeeldingen die worden gebruikt in websites van derden, marketingcampagnes en creatieve oplossingen voor Adobe.
contentOwner: AG
feature: Asset Insights, Asset Reports
role: Business Practice,Administrator
translation-type: tm+mt
source-git-commit: 29e3cd92d6c7a4917d7ee2aa8d9963aa16581633
workflow-type: tm+mt
source-wordcount: '738'
ht-degree: 2%

---


# Asset Insights {#asset-insights}

Leer hoe u met Asset Insights gebruikersbeoordelingen en gebruiksstatistieken kunt bijhouden van middelen die worden gebruikt in websites van derden, marketingcampagnes en creatieve oplossingen voor Adobe.

Met Asset Insights kunt u gebruikersbeoordelingen en gebruiksstatistieken bijhouden van elementen die in externe marketingcampagnes worden gebruikt, en creatieve oplossingen van Adobe bijhouden om inzicht te krijgen in de prestaties en populariteit van deze websites.

Met Elementinzichten worden details van gebruikersactiviteiten vastgelegd, zoals het aantal keren dat een element wordt beoordeeld, geklikt en afbeeldingen (het aantal keren dat het element op de website wordt geladen). Er worden op basis van deze statistieken scores toegekend aan activa. U kunt de scores en de prestatiesstatistieken gebruiken om populaire activa voor opneming in catalogi, marketing campagnes, etc. te selecteren. U kunt zelfs archiverings en vergunningsvernieuwing beleid voor activa formuleren die op deze statistieken worden gebaseerd.

Als u met behulp van Assets gebruiksstatistieken wilt vastleggen voor elementen van een website, moet u de insluitcode voor het element opnemen in de websitecode.

Om de statistieken van het de vertoningsgebruik van Activa van Inzichten voor activa te laten, vorm eerst de eigenschap om rapportgegevens van [!DNL Adobe Analytics] te halen. Zie [Elementinzichten configureren](touch-ui-configuring-asset-insights.md) voor meer informatie.

>[!NOTE]
>
>Inzichten worden ondersteund en alleen voor afbeeldingen verstrekt.

## Statistieken weergeven voor een element {#viewing-statistics-for-an-asset}

U kunt de Asset Insights-scores van de metagegevenspagina weergeven.

1. Selecteer in de gebruikersinterface Elementen (UI) het element en tik op het pictogram **[!UICONTROL Properties]** op de werkbalk.
1. Tik/klik op het tabblad **[!UICONTROL Insights]** op de pagina Eigenschappen.
1. Controleer de gebruiksdetails voor het element op het tabblad **[!UICONTROL Insights]**. In de sectie **[!UICONTROL Score]** worden het totale gebruik en de prestatiesbronnen van een element beschreven.

   De score van het gebruik beschrijft het aantal tijden activa wordt gebruikt in diverse oplossingen.

   De **[!UICONTROL Impressions]** score is het aantal keren dat het element op de website wordt geladen. Het getal dat onder **[!UICONTROL Clicks]** wordt weergegeven, is het aantal keren dat op het element wordt geklikt.

1. Controleer de sectie **[!UICONTROL Usage Statistics]** om te weten van welke entiteiten het middel deel uitmaakte en welke creatieve oplossingen het onlangs gebruikten. Hoe hoger het gebruik, hoe groter de kans dat het middel populair is bij gebruikers. Gebruiksgegevens worden onder de volgende koppen weergegeven:

   * **[!UICONTROL Asset]**: Het aantal keren dat het actief deel uitmaakte van een collectie of samengesteld actief
   * **[!UICONTROL Web & Mobile]**: Het aantal keren dat het middel deel uitmaakte van websites en apps
   * **[!UICONTROL Social]**: Het aantal keren dat het middel is gebruikt in oplossingen, zoals Adobe Social en Adobe Campaign
   * **[!UICONTROL Email]**: Het aantal keren dat het middel in e-mailcampagnes is gebruikt

   ![usage_statistics](assets/usage_statistics.png)

   >[!NOTE]
   >
   >Omdat de functie Asset Insights doorgaans de gegevens van Solutions van Adobe Analytics ophaalt, wordt in de sectie Oplossingen mogelijk niet de meest recente gegevens weergegeven. De tijdspanne waarvoor de gegevens worden getoond hangt het programma van de haalverrichting af die de Inzichten van Activa loopt om de gegevens van de Analyse terug te winnen.

1. Als u de prestatiestatistieken voor het element gedurende een bepaalde periode grafisch wilt weergeven, selecteert u een punt in de sectie **[!UICONTROL Performance Statistics]**. De details, inclusief klikken en impressies, worden getoond als trendlijnen van een grafiek.

   ![chlimage_1-3](assets/chlimage_1-3.jpeg)

   >[!NOTE]
   >
   >In tegenstelling tot de gegevens in de sectie van Oplossingen, toont de sectie van de Statistieken van Prestaties de meest recente gegevens.

1. Tik op **[!UICONTROL Get Embed Code]** onder de elementminiatuur om de insluitcode te verkrijgen voor het element dat u in websites opneemt om prestatiegegevens op te halen. Voor meer informatie over hoe te om uw Embed code in derdeWeb-pagina&#39;s op te nemen, zie [Gebruikend de Traceur van de Pagina en bedt code in Web-pagina&#39;s](touch-ui-using-page-tracker.md) in.

   ![chlimage_1-303](assets/chlimage_1-303.png)

## Samengevoegde statistieken weergeven voor activa {#viewing-aggregate-statistics-for-assets}

U kunt de scores van alle elementen in een map tegelijkertijd weergeven met **[!UICONTROL Insights View]**.

1. Navigeer in de interface Elementen naar de map met de elementen waarvoor u inzichten wilt weergeven.
1. Tik/klik op het pictogram Lay-out op de werkbalk en kies **[!UICONTROL Insights View]**.
1. Op de pagina worden gebruiksscores voor de elementen weergegeven. Vergelijk de ratings van de verschillende activa en teken inzichten.

## De achtergrondtaak {#scheduling-background-job} plannen

Asset Insights haalt op periodieke wijze gebruiksgegevens voor middelen van Adobe Analytics-rapportensuites op. Door gebrek, stelt de Inzichten van Activa een achtergrondbaan om de 24 uur bij 2 AM aan de ophaalgegevens in werking. Nochtans, kunt u zowel de frequentie als de tijd wijzigen door de **[!UICONTROL Adobe CQ DAM Asset Performance Report Sync Job]** dienst van de Webconsole te vormen.

1. Tik op het AEM en ga naar **[!UICONTROL Tools > Operations > Web Console]**.
1. Open de serviceconfiguratie **[!UICONTROL Adobe CQ DAM Asset Performance Report Sync Job]**.

   ![chlimage_1-304](assets/chlimage_1-304.png)

1. Specificeer de gewenste plannerfrequentie en de begintijd voor de baan in de uitdrukking van de bezitsplanner. Sla de wijzigingen op.
