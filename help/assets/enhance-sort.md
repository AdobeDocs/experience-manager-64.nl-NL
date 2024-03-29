---
title: Verbeterde sortering van elementen in AEM
description: Meer informatie [!DNL Experience Manager] Middelen gebruiken sortering op de server om mapelementen of een zoekquery tegelijk te sorteren in plaats van ze in batches aan de clientzijde te sorteren.
contentOwner: AG
feature: Search
role: User
exl-id: aa24ca68-d94e-4bd4-a5cc-113906650a2e
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 0%

---

# Verbeterde sortering van elementen in [!DNL Experience Manager] {#enhanced-sorting-of-assets-in-aem}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Meer informatie [!DNL Experience Manager] Middelen gebruiken sortering op de server om mapelementen of een zoekquery tegelijk te sorteren in plaats van ze in batches aan de clientzijde te sorteren.

De zoekfunctie van Adobe Experience Manager Assets is verbeterd en biedt nu een efficiënte manier om een groot aantal elementen te sorteren in de weergave met de mappenlijst en pagina&#39;s met zoekresultaten. U kunt ook tijdlijnitems sorteren.

[!DNL Experience Manager] Middelen plaatsen server-zijhet sorteren om de volledige reeks activa (hoe groot ook) binnen een omslag of een onderzoeksvraag bij één keer te sorteren in plaats van hen in partijen op de cliëntkant te sorteren. Op deze manier kunnen vooraf ingestelde resultaten snel worden weergegeven in de gebruikersinterface, waardoor de sorteerbewerking responsiever en kwetsbaarder wordt.

## Elementen sorteren in de lijstweergave {#sorting-assets-in-list-view}

[!DNL Experience Manager] Met middelen kunt u mapelementen sorteren op basis van de volgende velden:

* Landinstelling
* Status
* Type
* Grootte
* Classificatie
* Datum gewijzigd
* Datum gepubliceerd
* Gebruik
* Klikken
* Impressies
* Uitgecheckt

1. Navigeer naar een map met een groot aantal elementen.
1. Klik op het pictogram Lay-out of tik erop en schakel over naar de lijstweergave.

   ![chlimage_1-394](assets/chlimage_1-394.png)

1. Klik of tik op het pictogram Sorteren naast een kolomkop in de lijst met elementen.

   ![chlimage_1-395](assets/chlimage_1-395.png)

   De lijst met elementen wordt gesorteerd op basis van de veldwaarden.

   ![chlimage_1-396](assets/chlimage_1-396.png)

>[!NOTE]
>
>De waarden sorteren in het dialoogvenster `Name` of de `Title`kolommen, bedekking `/libs/dam/gui/content/commons/availablecolumns` en wijzigt u de waarde van `sortable` tot `True`.

## Elementen sorteren in zoekresultaten {#sorting-assets-in-search-results}

U kunt zoekresultaten sorteren op basis van de volgende velden:

* Titel
* Status
* Type
* Grootte
* Datum gewijzigd
* Datum gepubliceerd

1. Zoek in het vak Universeel zoeken naar elementen op basis van de gewenste criteria.

   ![chlimage_1-397](assets/chlimage_1-397.png)

1. Klik op het pictogram Lay-out of tik erop en schakel over naar de lijstweergave. Als de zoekresultaten al in de lijstweergave worden weergegeven, slaat u deze stap over.
1. Klik of tik op het pictogram Sorteren naast een kolomkop in de lijst met elementen. De lijst met elementen wordt gesorteerd op basis van de veldwaarden.

   ![chlimage_1-398](assets/chlimage_1-398.png)

## Elementen in tijdlijn sorteren {#sorting-assets-in-timeline}

[!DNL Assets] Hiermee kunt u tijdlijnitems chronologisch sorteren, zoals annotaties, versies, workflows en activiteiten.

1. Selecteer in de interface Elementen een element waarvoor u de tijdlijn wilt weergeven.
1. Klik op het pictogram GolbalNav of tik erop en selecteer **[!UICONTROL Timeline]**.

   ![chlimage_1-399](assets/chlimage_1-399.png)

1. Selecteer een item in de lijst in de tijdlijn. Selecteer bijvoorbeeld **[!UICONTROL Comments]** om de lijst met annotaties weer te geven die aan het element zijn gekoppeld.

   ![chlimage_1-400](assets/chlimage_1-400.png)

1. Klik/tik op de knop **[!UICONTROL Sort]** pictogram naast **[!UICONTROL Date]** label. Op basis van uw selectie worden de annotaties weergegeven in de chronologische volgorde/omgekeerde chronologische volgorde waarin ze aan het element zijn toegevoegd.

   ![chlimage_1-401](assets/chlimage_1-401.png)
