---
title: Uw Adobe Mobile Services-Cloud Service configureren
seo-title: Configure your Adobe Mobile Services Cloud Service
description: Volg deze pagina om uw Adobe Mobiele Cloud Service van de Diensten te vormen.
seo-description: Follow this page to configure your Adobe Mobile Services Cloud Service.
uuid: 21fe5b24-dc4d-4ee4-9e7f-ed4783baf276
contentOwner: User
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/MOBILE
topic-tags: administering-adobe-phonegap-enterprise
discoiquuid: 962e9e98-a303-435b-a938-31319282e022
legacypath: /content/docs/en/aem/6-1/develop/mobile-apps/apps/managing-aem-mobile-apps/configure-your-adobe-phonegap-build-cloud-service1
exl-id: 360c0ba9-ea49-495c-86d0-6d1db3f806a5
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 0%

---

# Uw Adobe Mobile Services-Cloud Service configureren {#configure-your-adobe-mobile-services-cloud-service}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

>[!NOTE]
>
>Adobe raadt aan de SPA Editor te gebruiken voor projecten die renderen op basis van één pagina voor toepassingsframework op de client-side vereisen (bijvoorbeeld Reageren). [Meer informatie](/help/sites-developing/spa-overview.md).

De **Mobiele metrische tegel** in het opdrachtcentrum levert realtime analyses voor uw mobiele toepassing.

De [Adobe Mobile Analytics](https://www.adobe.com/ca/solutions/digital-analytics/mobile-web-apps-analytics.html) SDK wordt beschikbaar gesteld via een PhoneGap-plug-in. Metrische gegevens worden verzameld en in cache geplaatst op het apparaat totdat het apparaat is aangesloten. Op dat moment worden de gegevens naar de Adobe Mobile Services Cloud geduwd voor rapportage en analyse.

Adobe Mobile Analytics SDK biedt het volgende:

1. **Gegevensverzameling voor mobiele kanalen** - Verzamel uitgebreide gegevens voor uw mobiele websites en toepassingen op alle grote besturingssystemen.
1. **Analyse van mobiele betrokkenheid** - Begrijp de betrokkenheid van gebruikers binnen uw mobiele app, website of video, inclusief hoe vaak consumenten het kanaal starten, of ze er aankopen van maken en meer.
1. **Mobiele toepassingsdashboards en -rapporten** - Gebruik gebruiksrapporten die levenscyclusmetriek voor uw apps en de gegevens van de App store bevatten — zie trends voor gebruikers, lanceringen, gemiddelde zittingslengte, retentielengte, en neerstortingen.
1. **Mobiele campagneanalyse** - De doeltreffendheid van specifieke campagnes voor mobiele apparaten, zoals SMS, mobiele zoekadvertenties, advertenties voor mobiele schermen en QR-codes, kwantificeren.
1. **Geolocatieanalyse** - Zoek waar uw gebruikers van de app uw mobiele beleving kunnen starten en interactief kunnen gebruiken op basis van de GPS-locatie of -punten.
1. **Padeanalyse** - Bekijk hoe gebruikers door uw app navigeren om te bepalen welke schermen en UI-elementen gebruikers aantrekken en welke ertoe leiden dat gebruikers wegvallen.

>[!CAUTION]
>
>De **Metrische gegevens analyseren** De tegelweergave wordt alleen weergegeven in het dashboard als u de cloudservices hebt geconfigureerd.

![chlimage_1-22](assets/chlimage_1-22.png)

Metrische tegel AEM Command Center

## De Cloud Service configureren {#configuring-the-cloud-service}

Als u gebruik wilt maken van Adobe Mobile Services Analytics, moet u de AEM Mobile Analytics Cloud Service configureren met uw Adobe Analytics-accountgegevens.

1. Klik op het pictogram aan de rechterbovenzijde om de Cloud Services toe te voegen of te bewerken vanuit het menu **Cloud Services beheren** element uit het dashboard van de app.

   ![chlimage_1-23](assets/chlimage_1-23.png)

1. De **Cloud Services toevoegen of bewerken** weergegeven. Selecteren **Adobe mobiele services** en klik op **Volgende**.

   ![chlimage_1-24](assets/chlimage_1-24.png)

1. Kies een bestaande configuratie in het menu **Mobiele services** of kies **Configuratie maken** om een nieuwe te maken.

   Voor nieuwe configuratie voert u de **Eigenschappen van mobiele services** en klik op **Verifiëren.**

   ![chlimage_1-25](assets/chlimage_1-25.png)

   Als de referenties zijn geverifieerd, worden de **Verifiëren** knop verandert in **Geverifieerd**. U kunt een mobiele service-app kiezen vanuit **Selecteer een Mobile App Service**.

   Klikken **Verzenden** voor het instellen van uw configuratie.

   ![chlimage_1-26](assets/chlimage_1-26.png)

1. Als u een cloudconfiguratie hebt ingesteld, kunt u deze ook in het dashboard weergeven.

   ![chlimage_1-27](assets/chlimage_1-27.png)

   >[!NOTE]
   >
   >Nadat u de cloudconfiguratie hebt ingesteld, kunt u de **Metrische gegevens analyseren** Tegel in het dashboard van de app.

   ![chlimage_1-28](assets/chlimage_1-28.png)
