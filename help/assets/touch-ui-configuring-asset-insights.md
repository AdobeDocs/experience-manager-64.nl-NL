---
title: Elementinzichten configureren
description: Leer hoe u Asset Insights in AEM Assets configureert.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 0d70a672a2944e2c03b54beb3b5f734136792ab1

---


# Elementinzichten configureren {#configuring-asset-insights}

Met Adobe Experience Manager (AEM) worden gebruiksgegevens opgehaald van AEM-elementen die door websites van derden worden gebruikt met Adobe Analytics. Als u Asset Insights wilt inschakelen om deze gegevens op te halen en inzichten te genereren, moet u eerst de functie configureren voor integratie met Adobe Analytics.

>[!NOTE]
>
>Inzichten worden alleen ondersteund en opgegeven voor afbeeldingen.

1. Klik in AEM op **[!UICONTROL Gereedschappen > Elementen]**.

   ![chlimage_1-210](assets/chlimage_1-210.png)

1. Klik op de **[!UICONTROL inzichten Configuration]** -kaart.
1. Selecteer een datacenter in de wizard en geef uw gegevens op, inclusief de naam van uw organisatie, gebruikersnaam en wachtwoord.

   ![chlimage_1-211](assets/insights_config2.png)

1. Klik/tik **[!UICONTROL voor verifiëren]**.
1. Nadat AEM uw gegevens heeft geverifieerd, kiest u in de lijst **[!UICONTROL Report Suite]** een Adobe Analytics-rapportsuite waaruit u gegevens wilt ophalen met behulp van Asset Insights. Click **[!UICONTROL Add]**.
1. Nadat AEM uw rapportsuite heeft ingesteld, klikt of tikt u op **[!UICONTROL Gereed]**.

## Paginanummering {#page-tracker}

Nadat u uw account Analytics hebt geconfigureerd, wordt de code van Paginanummering voor u gegenereerd. Als u Assets Insights wilt inschakelen om AEM-elementen die worden gebruikt op websites van derden bij te houden, neemt u de paginacontrackercode op in de websitecode. Gebruik het hulpprogramma Paginanummering in AEM Assets om de code van de paginacontracker te genereren. Zie [Paginanummering gebruiken en code insluiten in webpagina&#39;s van derden voor meer informatie over het opnemen van de code in Paginanummers](touch-ui-using-page-tracker.md).

1. Klik in AEM op **[!UICONTROL Gereedschappen > Elementen]**.

   ![chlimage_1-214](assets/chlimage_1-214.png)

1. Klik op de **[!UICONTROL navigatiepagina]** op de kaart voor **[!UICONTROL inzichten in paginanummering]** .
1. Klik op het pictogram **[!UICONTROL Downloaden]** om de code van de paginacontracker te downloaden.