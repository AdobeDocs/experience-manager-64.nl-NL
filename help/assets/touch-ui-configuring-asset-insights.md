---
title: Elementinzichten configureren
description: Leer hoe u Assets Insights configureert in [!DNL Experience Manager] Elementen.
contentOwner: AG
feature: Asset Insights,Asset Reports
role: User,Admin
exl-id: b0d62dd3-1868-4d73-95f7-3d6c3ff474d9
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 1%

---

# Elementinzichten configureren {#configuring-asset-insights}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Adobe Experience Manager Assets haalt gebruiksgegevens rond [!DNL Experience Manager] middelen die door websites van derden van Adobe Analytics worden gebruikt. Om Assets Insights toe te laten om deze gegevens terug te winnen en inzichten te produceren, vorm eerst de eigenschap om met Adobe Analytics te integreren.

>[!NOTE]
>
>Inzichten worden alleen ondersteund en opgegeven voor afbeeldingen.

1. Klik in AEM op **[!UICONTROL Tools > Assets]**.

   ![chlimage_1-210](assets/chlimage_1-210.png)

1. Klik op de knop **[!UICONTROL Insights Configuration]** kaart.
1. Selecteer een datacenter in de wizard en geef uw gegevens op, inclusief de naam van uw organisatie, gebruikersnaam en wachtwoord.

   ![chlimage_1-211](assets/insights_config2.png)

1. Klik of tik op **[!UICONTROL Authenticate]**.
1. Na [!DNL Experience Manager] verifieert uw geloofsbrieven, van **[!UICONTROL Report Suite]** kiest u een Adobe Analytics-rapportsuite waaruit u gegevens wilt ophalen met behulp van Assets. Klik op **[!UICONTROL Add]**.
1. Na [!DNL Experience Manager] stelt uw rapportsuite in, klikt/tikt **[!UICONTROL Done]**.

## Paginanummering {#page-tracker}

Nadat u uw account Analytics hebt geconfigureerd, wordt de code van Paginanummering voor u gegenereerd. Elementeninzichten bijhouden [!DNL Experience Manager] elementen die in websites van derden worden gebruikt, nemen de paginacontrackercode in de websitecode op. Gebruik het hulpprogramma Paginanummering in [!DNL Experience Manager] Middelen om de code van de paginacontracker te produceren. Ga voor meer informatie over het opnemen van uw code in Paginanummering in externe webpagina&#39;s naar [Paginanummering gebruiken en code insluiten in webpagina&#39;s](touch-ui-using-page-tracker.md).

1. Klik in AEM op de knop **[!UICONTROL Tools > Assets]**.

   ![chlimage_1-214](assets/chlimage_1-214.png)

1. Van de **[!UICONTROL Navigation]** pagina, klikt u op de knop **[!UICONTROL Insights Page Tracker]** kaart.
1. Klik op de knop **[!UICONTROL Download]** pictogram om de code van de paginacontracker te downloaden.
