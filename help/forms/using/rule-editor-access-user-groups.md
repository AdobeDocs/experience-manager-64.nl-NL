---
title: De toegang van de regelredacteur van de subsidie tot uitgezochte gebruikersgroepen
seo-title: Grant rule editor access to select user groups
description: Verleen beperkte toegang tot regelredacteur om gebruikersgroepen te selecteren.
seo-description: Grant restricted access to rule editor to select user groups.
uuid: 3d982858-b2b5-4370-a9d7-5a95842a7897
content-type: reference
topic-tags: adaptive_forms, develop
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 6bd58e37-085e-4057-8200-1404d54f41cc
feature: Adaptive Forms
exl-id: 5e2960f2-b172-48a7-bba3-4561a5f9c7bc
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 0%

---

# De toegang van de regelredacteur van de subsidie tot uitgezochte gebruikersgroepen {#grant-rule-editor-access-to-select-user-groups}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Overzicht {#overview}

U kunt verschillende typen gebruikers hebben met verschillende vaardigheden die werken met Adaptive Forms. Hoewel ervaren gebruikers de juiste kennis hebben om met scripts en complexe regels te werken, kunnen er gebruikers op basisniveau zijn die alleen met de indeling en basiseigenschappen van adaptieve formulieren moeten werken.

AEM Forms staat u toe om de toegang van de regelredacteur tot gebruikers te beperken die op hun rol of functie wordt gebaseerd. In de instellingen van de Adaptive Forms Configuration Service kunt u de [gebruikersgroepen](/help/sites-administering/security.md) die tot regelredacteur kunnen bekijken en toegang hebben.

## Geef gebruikersgroepen op die toegang kunnen krijgen tot de regeleditor {#specify-user-groups-that-can-access-rule-editor}

1. Meld u als beheerder aan bij AEM Forms.
1. Klik in de auteurinstantie op ![adobeexperienceManager](assets/adobeexperiencemanager.png)Adobe Experience Manager > Gereedschappen ![hamer](assets/hammer.png) > Bewerkingen > Webconsole. De webconsole wordt in een nieuw venster geopend.

   ![1](assets/1.png)

1. Zoek en klik in het venster Webconsole op **[!UICONTROL Adaptive Form and Interactive Communication Web Channel Configuration]**. **[!UICONTROL Adaptive Form and Interactive Communication Web Channel Configuration]** wordt weergegeven. Wijzig geen waarde en klik op **[!UICONTROL Save]**.

   Het leidt tot een dossier /apps/system/config/com.adobe.aemds.guide.service.impl.AdaptiveFormConfigurationServiceImpl.config in CRX-bewaarplaats.

1. Meld u als beheerder aan bij CRXDE. Open het bestand /apps/system/config/com.adobe.aemds.guide.service.impl.AdaptiveFormConfigurationServiceImpl.config voor bewerking.
1. Gebruik het volgende bezit om de naam van een groep te specificeren die tot regelredacteur (bijvoorbeeld, RuleEditorsUserGroup) kan toegang hebben en klik **Alles opslaan**.

   `af.ruleeditor.custom.groups=["RuleEditorsUserGroup"]`

   Als u toegang voor meerdere groepen wilt inschakelen, geeft u een lijst op met door komma&#39;s gescheiden waarden:

   `af.ruleeditor.custom.groups=["RuleEditorsUserGroup", "PermittedUserGroup"]`

   ![aanmaken-gebruiker](assets/create-user.png)

   Nu, wanneer een gebruiker die geen deel van de gespecificeerde gebruikersgroep (hier RuleEditorsUserGroup) uitmaakt een gebied tikt, geeft het Edit pictogram van de Regel ( ![edit-rules1](assets/edit-rules1.png)) is niet beschikbaar voor haar op de componentenwerkbalk:

   ![componentstoolbarwither](assets/componentstoolbarwithre.png)

   De toolbar van componenten zoals zichtbaar aan een gebruiker met de toegang van de regelredacteur

   ![componentstoolbarwithouding](assets/componentstoolbarwithoutre.png)

   De toolbar van Componenten zoals zichtbaar aan een gebruiker zonder de toegang van de regelredacteur

   Voor instructies over het toevoegen van gebruikers aan groepen raadpleegt u [Gebruikersbeheer en beveiliging](/help/sites-administering/security.md).
