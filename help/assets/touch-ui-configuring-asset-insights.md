---
title: Elementinzichten configureren
description: Leer hoe u Assets Insights configureert in AEM Assets.
contentOwner: AG
feature: Asset Insights, Asset Reports
role: Business Practitioner,Administrator
exl-id: b0d62dd3-1868-4d73-95f7-3d6c3ff474d9
source-git-commit: edba9586711ee5c0e5549dbe374226e878803178
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 1%

---

# Elementinzichten configureren {#configuring-asset-insights}

Met Adobe Experience Manager (AEM) worden gebruiksgegevens opgehaald van AEM middelen die door websites van derden van Adobe Analytics worden gebruikt. Om Assets Insights toe te laten om deze gegevens terug te winnen en inzichten te produceren, vorm eerst de eigenschap om met Adobe Analytics te integreren.

>[!NOTE]
>
>Inzichten worden alleen ondersteund en opgegeven voor afbeeldingen.

1. Klik in AEM op **[!UICONTROL Tools > Assets]**.

   ![chlimage_1-210](assets/chlimage_1-210.png)

1. Klik op de **[!UICONTROL Insights Configuration]**-kaart.
1. Selecteer een datacenter in de wizard en geef uw gegevens op, inclusief de naam van uw organisatie, gebruikersnaam en wachtwoord.

   ![chlimage_1-211](assets/insights_config2.png)

1. Klik of tik op **[!UICONTROL Authenticate]**.
1. Nadat AEM uw geloofsbrieven voor authentiek verklaart, van de **[!UICONTROL Report Suite]** lijst, kies een het rapportreeks van Adobe Analytics van waar u de Inzichten van Activa wilt om gegevens te halen. Klik op **[!UICONTROL Add]**.
1. Nadat AEM de rapportsuite hebt ingesteld, klikt of tikt u op **[!UICONTROL Done]**.

## Paginanummering {#page-tracker}

Nadat u uw account Analytics hebt geconfigureerd, wordt de code van Paginanummering voor u gegenereerd. Neem de paginacontrackercode in de websitecode op om Elementen inzicht te geven in AEM elementen die worden gebruikt op websites van derden. Gebruik het hulpprogramma Paginanummering in AEM Assets om de code van de paginatracker te genereren. Zie [Paginanummering gebruiken en code insluiten in webpagina&#39;s van derden](touch-ui-using-page-tracker.md) voor meer informatie over het opnemen van de code in Paginanummering in webpagina&#39;s.

1. Klik in AEM op **[!UICONTROL Tools > Assets]**.

   ![chlimage_1-214](assets/chlimage_1-214.png)

1. Klik op de **[!UICONTROL Navigation]**-pagina op de **[!UICONTROL Insights Page Tracker]**-kaart.
1. Klik op het pictogram **[!UICONTROL Download]** om de code van de paginacontracker te downloaden.
