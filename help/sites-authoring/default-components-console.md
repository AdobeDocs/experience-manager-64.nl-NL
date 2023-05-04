---
title: Onderdelenconsole
seo-title: Components Console
description: Onderdelenconsole
seo-description: null
uuid: 308b7fa1-9525-43f3-8c15-1076485b3f8c
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: page-authoring
content-type: reference
discoiquuid: 8774c38a-abd2-4dc2-868e-d6760c96f3f6
exl-id: fa583a06-e75c-41de-a977-7e459ab8bca9
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 16%

---

# Onderdelenconsole{#components-console}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Met de componentenconsole kunt u door alle componenten bladeren die voor uw instantie zijn gedefinieerd en sleutelinformatie voor elke component bekijken.

Het kan worden benaderd van **Gereedschappen** -> **Algemeen** -> **Componenten**. In de console zijn de kaart- en de lijstweergave beschikbaar. Omdat er geen boomstructuur voor componenten is, is de kolomweergave niet beschikbaar.

![chlimage_1-301](assets/chlimage_1-301.png)

>[!NOTE]
>
>In de componentconsole worden alle componenten in het systeem weergegeven. De [Componentbrowser](/help/sites-authoring/author-environment-tools.md#components-browser) toont componenten die aan auteurs beschikbaar zijn en verbergt om het even welke componentengroepen die met een periode beginnen ( `.`).

## Zoeken {#search-features}

Met het pictogram **Alleen content** (linksboven) kunt u het deelvenster **Zoeken** openen om de componenten te zoeken en/of te filteren:

![chlimage_1-302](assets/chlimage_1-302.png)

## Componentdetails {#component-details}

Als u details over een bepaalde component wilt weergeven, tikt u op de gewenste bron of klikt u op deze. Drie tabbladen bieden:

* **Eigenschappen**

   ![screen_shot_2018-03-27at165847](assets/screen_shot_2018-03-27at165847.png)

   Op het tabblad Eigenschappen kunt u het volgende doen:

   * De algemene eigenschappen van de component weergeven.
   * Weergeven hoe de [pictogram of afkorting is gedefinieerd](/help/sites-developing/components-basics.md#component-icon-in-touch-ui) voor de component.

      * Als u op de bron van het pictogram klikt, gaat u naar die component.
   * De weergave van **Type bron** en **Super Type resource** (indien gedefinieerd) voor de component.

      * Als u op het Super Type van Middel klikt, gaat u naar die component.
   >[!NOTE]
   >
   >Omdat `/apps` kan tijdens runtime niet worden bewerkt, is de Componentenconsole alleen-lezen.

* **Beleid**

   ![chlimage_1-303](assets/chlimage_1-303.png)

* **Live-gebruik**

   ![chlimage_1-304](assets/chlimage_1-304.png)

   >[!CAUTION]
   >
   >Vanwege de aard van de informatie die voor deze weergave wordt verzameld, kan het enige tijd duren voordat deze wordt gesorteerd of weergegeven.

* **Documentatie**

   Als de ontwikkelaar [documentatie voor de component](/help/sites-developing/developing-components.md#documenting-your-component), verschijnt het op de **Documentatie** tab. Als er geen documentatie beschikbaar is, **Documentatie** wordt niet weergegeven.

   ![chlimage_1-305](assets/chlimage_1-305.png)
