---
title: Onderdelenconsole
seo-title: Onderdelenconsole
description: 'null'
seo-description: 'null'
uuid: 308b7fa1-9525-43f3-8c15-1076485b3f8c
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: page-authoring
content-type: reference
discoiquuid: 8774c38a-abd2-4dc2-868e-d6760c96f3f6
translation-type: tm+mt
source-git-commit: cdec5b3c57ce1c80c0ed6b5cb7650b52cf9bc340
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 20%

---


# Onderdelenconsole{#components-console}

Met de componentenconsole kunt u door alle componenten bladeren die voor uw instantie zijn gedefinieerd en sleutelinformatie voor elke component bekijken.

Deze kan worden geopend via **Tools** -> **General** -> **Components**. In de console zijn de kaart- en de lijstweergave beschikbaar. Omdat er geen boomstructuur voor componenten is, is de kolomweergave niet beschikbaar.

![chlimage_1-301](assets/chlimage_1-301.png)

>[!NOTE]
>
>In de componentconsole worden alle componenten in het systeem weergegeven. In de [Componentbrowser](/help/sites-authoring/author-environment-tools.md#components-browser) worden componenten weergegeven die beschikbaar zijn voor auteurs en worden componentgroepen verborgen die met een punt ( `.`) beginnen.

## Zoeken {#search-features}

Met het pictogram **Alleen content** (linksboven) kunt u het deelvenster **Zoeken** openen om de componenten te zoeken en/of te filteren:

![chlimage_1-302](assets/chlimage_1-302.png)

## Componentdetails {#component-details}

Als u details over een bepaalde component wilt weergeven, tikt u op de gewenste bron of klikt u op deze. Drie tabbladen bieden:

* **Eigenschappen**

   ![screen_shot_2018-03-27at165847](assets/screen_shot_2018-03-27at165847.png)

   Op het tabblad Eigenschappen kunt u het volgende doen:

   * De algemene eigenschappen van de component weergeven.
   * Bekijk hoe het pictogram of de afkorting [is gedefinieerd](/help/sites-developing/components-basics.md#component-icon-in-touch-ui) voor de component.

      * Als u op de bron van het pictogram klikt, gaat u naar die component.
   * Bekijk **Resourcetype** en **Resourcesupertype** (indien gedefinieerd) voor de component.

      * Als u op het Super Type van Middel klikt, gaat u naar die component.
   >[!NOTE]
   >
   >Omdat `/apps` niet bewerkbaar is bij uitvoering, is de Componentenconsole alleen-lezen.

* **Beleid**

   ![chlimage_1-303](assets/chlimage_1-303.png)

* **Live-gebruik**

   ![chlimage_1-304](assets/chlimage_1-304.png)

   >[!CAUTION]
   >
   >Vanwege de aard van de informatie die voor deze weergave wordt verzameld, kan het enige tijd duren voordat deze wordt gesorteerd of weergegeven.

* **Documentatie**

   Als de ontwikkelaar [documentatie voor de component](/help/sites-developing/developing-components.md#documenting-your-component) heeft verstrekt, zal het op **Documentatie** tabel verschijnen. Als er geen documentatie beschikbaar is, zal **Documentatie** tabel niet worden getoond.

   ![chlimage_1-305](assets/chlimage_1-305.png)

