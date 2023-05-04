---
title: Met de functie Assets Insights kunt u het gebruik van uw afbeeldingen bijhouden
description: Met de functie Middelen-inzichten kunt u gebruikersbeoordelingen en gebruiksstatistieken bijhouden van afbeeldingen die worden gebruikt in websites van derden, marketingcampagnes en creatieve oplossingen voor Adobe.
contentOwner: AG
feature: Asset Insights,Asset Reports
role: User,Admin
exl-id: a9604b09-1c83-4c1e-aff7-13107b898cb3
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '787'
ht-degree: 2%

---

# Assets Insights {#asset-insights}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Leer hoe u met behulp van Assets Insights gebruikersbeoordelingen en gebruiksstatistieken kunt bijhouden van middelen die worden gebruikt in websites van derden, marketingcampagnes en creatieve oplossingen voor Adobe.

Met de Assets Insights-functie kunt u gebruikersbeoordelingen en gebruiksstatistieken bijhouden van elementen die worden gebruikt in externe marketingcampagnes en creatieve Adobe om inzicht te krijgen in de prestaties en populariteit van deze websites.

Met Elementinzichten worden details van gebruikersactiviteiten vastgelegd, zoals het aantal keren dat een element wordt beoordeeld, geklikt en afbeeldingen (het aantal keren dat het element op de website wordt geladen). Er worden op basis van deze statistieken scores toegekend aan activa. U kunt de scores en de prestatiesstatistieken gebruiken om populaire activa voor opneming in catalogi, marketing campagnes, etc. te selecteren. U kunt zelfs archiverings en vergunningsvernieuwing beleid voor activa formuleren die op deze statistieken worden gebaseerd.

Als u met behulp van Assets gebruiksstatistieken wilt vastleggen voor elementen van een website, moet u de insluitcode voor het element opnemen in de websitecode.

Om de statistieken van het vertoningsgebruik van Activa van Inzichten voor activa te laten, vorm eerst de eigenschap om rapportgegevens van te halen [!DNL Adobe Analytics]. Zie voor meer informatie [Elementengegevens configureren](touch-ui-configuring-asset-insights.md). Aanschaf als u deze functie wilt gebruiken in een installatie op locatie [!DNL Adobe Analytics] licentie afzonderlijk. Klanten op [!DNL Managed Services] ontvangen [!DNL Analytics] licentie gebundeld met [!DNL Experience Manager]. Zie [Managed Services-productbeschrijving](https://helpx.adobe.com/legal/product-descriptions/adobe-experience-manager-managed-services.html).

>[!NOTE]
>
>Inzichten worden ondersteund en alleen voor afbeeldingen verstrekt.

## Statistieken voor een element weergeven {#viewing-statistics-for-an-asset}

U kunt de elementinzichten van de metagegevenspagina weergeven.

1. Selecteer het element in de gebruikersinterface Elementen (UI) en tik op het element **[!UICONTROL Properties]** op de werkbalk.
1. Tik op de pagina Eigenschappen of klik op de knop **[!UICONTROL Insights]** tab.
1. Bekijk de gebruiksdetails voor het element in de **[!UICONTROL Insights]** tab. De **[!UICONTROL Score]** in deze sectie wordt het totale gebruik en de prestatiesbronnen van een actief beschreven.

   De score van het gebruik beschrijft het aantal tijden activa wordt gebruikt in diverse oplossingen.

   De **[!UICONTROL Impressions]** De score is het aantal keren dat het element op de website wordt geladen. Het nummer dat onder wordt weergegeven **[!UICONTROL Clicks]** is het aantal keren dat op het element wordt geklikt.

1. Controleer de **[!UICONTROL Usage Statistics]** sectie om te weten van welke entiteiten het actief deel uitmaakte en welke creatieve oplossingen het onlangs gebruikten. Hoe hoger het gebruik, hoe groter de kans dat het middel populair is bij gebruikers. Gebruiksgegevens worden onder de volgende koppen weergegeven:

   * **[!UICONTROL Asset]**: Het aantal keren dat het actief deel uitmaakte van een collectie of samengesteld actief
   * **[!UICONTROL Web & Mobile]**: Het aantal keren dat het middel deel uitmaakte van websites en apps
   * **[!UICONTROL Social]**: Het aantal keren dat het middel is gebruikt in oplossingen, zoals Adobe Social en Adobe Campaign
   * **[!UICONTROL Email]**: Het aantal keren dat het middel in e-mailcampagnes is gebruikt

   ![usage_statistics](assets/usage_statistics.png)

   >[!NOTE]
   >
   >Met de functie Assets Insights haalt u de oplossingsgegevens op van [!DNL Adobe Analytics] in de sectie Oplossingen worden de meest recente gegevens mogelijk niet periodiek weergegeven. De tijdspanne waarvoor de gegevens worden getoond hangt het programma van de haalverrichting af die de Inzichten van Activa in werking stellen om terug te winnen [!DNL Analytics] gegevens.

1. Als u de prestatiestatistieken voor het actief grafisch wilt weergeven over een tijdsperiode, selecteert u de periode in het dialoogvenster **[!UICONTROL Performance Statistics]** sectie. De details, inclusief klikken en impressies, worden getoond als trendlijnen van een grafiek.

   ![chlimage_1-3](assets/chlimage_1-3.jpeg)

   >[!NOTE]
   >
   >In tegenstelling tot de gegevens in de oplossingssectie, toont de sectie van prestatiesstatistieken de meest recente gegevens.

1. Klik op **[!UICONTROL Get Embed Code]** onder de elementminiatuur. Ga voor meer informatie over het opnemen van uw insluitcode in externe webpagina&#39;s naar [Paginanummering gebruiken en code insluiten in webpagina&#39;s](touch-ui-using-page-tracker.md).

   ![chlimage_1-303](assets/chlimage_1-303.png)

## Samengevoegde statistieken voor activa weergeven {#viewing-aggregate-statistics-for-assets}

U kunt de scores van alle elementen in een map tegelijk weergeven met **[!UICONTROL Insights View]**.

1. Navigeer in de interface Elementen naar de map met de elementen waarvoor u inzichten wilt weergeven.
1. Tik/klik op het pictogram Lay-out op de werkbalk en kies **[!UICONTROL Insights View]**.
1. Op de pagina worden gebruiksscores voor de elementen weergegeven. Vergelijk de ratings van de verschillende activa en teken inzichten.

## Achtergrondtaak plannen {#scheduling-background-job}

Assets Insights haalt gebruiksgegevens voor middelen van Adobe Analytics op periodieke wijze. Door gebrek, stelt de Inzichten van Activa een achtergrondbaan om de 24 uur bij 2 AM in werking aan de ophaalgegevens. Nochtans, kunt u zowel de frequentie als de tijd wijzigen door te vormen **[!UICONTROL Adobe CQ DAM Asset Performance Report Sync Job]** van de webconsole.

1. Tik op de knop [!DNL Experience Manager] logo en ga naar **[!UICONTROL Tools > Operations > Web Console]**.
1. Open de **[!UICONTROL Adobe CQ DAM Asset Performance Report Sync Job]** serviceconfiguratie.

   ![chlimage_1-304](assets/chlimage_1-304.png)

1. Specificeer de gewenste plannerfrequentie en de begintijd voor de baan in de uitdrukking van de bezitsplanner. Sla de wijzigingen op.
