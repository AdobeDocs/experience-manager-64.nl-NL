---
title: Elementinzichten configureren
description: Leer hoe u Asset Insights configureert in AEM Assets.
contentOwner: AG
feature: Asset Insights, Asset Reports
role: Business Practice,Administrator
translation-type: tm+mt
source-git-commit: 29e3cd92d6c7a4917d7ee2aa8d9963aa16581633
workflow-type: tm+mt
source-wordcount: '228'
ht-degree: 1%

---


# Elementinzichten configureren {#configuring-asset-insights}

Met Adobe Experience Manager (AEM) worden gebruiksgegevens opgehaald van AEM middelen die door websites van derden van Adobe Analytics worden gebruikt. Om Asset Insights in in staat te stellen deze gegevens op te halen en inzichten te genereren, dient u eerst de functie te configureren voor integratie met Adobe Analytics.

>[!NOTE]
>
>Inzichten worden alleen ondersteund en opgegeven voor afbeeldingen.

1. Klik in AEM op **[!UICONTROL Tools > Assets]**.

   ![chlimage_1-210](assets/chlimage_1-210.png)

1. Klik op de **[!UICONTROL Insights Configuration]**-kaart.
1. Selecteer een datacenter in de wizard en geef uw gegevens op, inclusief de naam van uw organisatie, gebruikersnaam en wachtwoord.

   ![chlimage_1-211](assets/insights_config2.png)

1. Klik of tik op **[!UICONTROL Authenticate]**.
1. Nadat AEM uw geloofsbrieven voor authentiek verklaart, van de **[!UICONTROL Report Suite]** lijst, kies een het rapportsuite van Adobe Analytics van waar u de Inzichten van Activa wilt halen om gegevens te halen. Klik op **[!UICONTROL Add]**.
1. Nadat AEM de rapportsuite hebt ingesteld, klikt of tikt u op **[!UICONTROL Done]**.

## Paginanummering {#page-tracker}

Nadat u uw account Analytics hebt geconfigureerd, wordt de code van Paginanummering voor u gegenereerd. Neem de paginacontrackercode in de websitecode op om Elementen inzicht te geven in AEM elementen die worden gebruikt op websites van derden. Gebruik het hulpprogramma Paginanummering in AEM Assets om de code van de paginatracker te genereren. Zie [Paginanummering gebruiken en code insluiten in webpagina&#39;s van derden](touch-ui-using-page-tracker.md) voor meer informatie over het opnemen van de code in Paginanummering in webpagina&#39;s.

1. Klik in AEM op **[!UICONTROL Tools > Assets]**.

   ![chlimage_1-214](assets/chlimage_1-214.png)

1. Klik op de **[!UICONTROL Navigation]**-pagina op de **[!UICONTROL Insights Page Tracker]**-kaart.
1. Klik op het pictogram **[!UICONTROL Download]** om de code van de paginacontracker te downloaden.