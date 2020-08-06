---
title: De toegang van de regelredacteur van de subsidie tot uitgezochte gebruikersgroepen
seo-title: De toegang van de regelredacteur van de subsidie tot uitgezochte gebruikersgroepen
description: Verleen beperkte toegang tot regelredacteur om gebruikersgroepen te selecteren.
seo-description: Verleen beperkte toegang tot regelredacteur om gebruikersgroepen te selecteren.
uuid: 3d982858-b2b5-4370-a9d7-5a95842a7897
content-type: reference
topic-tags: develop
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 6bd58e37-085e-4057-8200-1404d54f41cc
translation-type: tm+mt
source-git-commit: 73d0dea62c294bea435364fb9c6892d80751d90d
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 0%

---


# De toegang van de regelredacteur van de subsidie tot uitgezochte gebruikersgroepen {#grant-rule-editor-access-to-select-user-groups}

## Overzicht {#overview}

U kunt verschillende typen gebruikers hebben met verschillende vaardigheden die werken met Adaptive Forms. Hoewel ervaren gebruikers de juiste kennis hebben om met scripts en complexe regels te werken, kunnen er gebruikers op basisniveau zijn die alleen met de indeling en basiseigenschappen van adaptieve formulieren moeten werken.

AEM Forms staat u toe om de toegang van de regelredacteur tot gebruikers te beperken die op hun rol of functie wordt gebaseerd. In de Adaptive Forms Configuration Service-instellingen kunt u de [gebruikersgroepen](/help/sites-administering/security.md) opgeven die de regeleditor kunnen weergeven en openen.

## Geef gebruikersgroepen op die toegang kunnen krijgen tot de regeleditor {#specify-user-groups-that-can-access-rule-editor}

1. Meld u als beheerder aan bij AEM Forms.
1. Klik in de auteurinstantie op ![](assets/adobeexperiencemanager.png)adobeexperienceAdobe Experience Manager > ![Tools hammer](assets/hammer.png) > Operations > Web Console. De webconsole wordt in een nieuw venster geopend.

   ![1](assets/1.png)

1. Zoek en klik op **Adaptieve formulierconfiguratieservice** in het venster Webconsole. **Het dialoogvenster Adaptive Form Configuration Service** wordt weergegeven. Wijzig geen waarde en klik op **Opslaan**.

   Het leidt tot een dossier /apps/system/config/com.adobe.aemds.guide.service.impl.AdaptiveFormConfigurationServiceImpl.config in CRX-bewaarplaats.

1. Meld u als beheerder aan bij CRXDE. Open het bestand /apps/system/config/com.adobe.aemds.guide.service.impl.AdaptiveFormConfigurationServiceImpl.config voor bewerking.
1. Gebruik het volgende bezit om de naam van een groep te specificeren die tot regelredacteur (bijvoorbeeld, RuleEditorsUserGroup) kan toegang hebben en klik **sparen allen**.

   `af.ruleeditor.custom.groups=["RuleEditorsUserGroup"]`

   Als u toegang voor meerdere groepen wilt inschakelen, geeft u een lijst op met door komma&#39;s gescheiden waarden:

   `af.ruleeditor.custom.groups=["RuleEditorsUserGroup", "PermittedUserGroup"]`

   ![aanmaken-gebruiker](assets/create-user.png)

   Nu, wanneer een gebruiker die geen deel van de gespecificeerde gebruikersgroep (hier RuleEditorsUserGroup) uitmaakt een gebied tikt, is het Edit pictogram van de Regel ( ![geef-rules1](assets/edit-rules1.png)) niet beschikbaar voor haar in de componententoolbar:

   ![componentstoolbarwither](assets/componentstoolbarwithre.png)

   De toolbar van componenten zoals zichtbaar aan een gebruiker met de toegang van de regelredacteur

   ![componentstoolbarwithouding](assets/componentstoolbarwithoutre.png)

   De toolbar van Componenten zoals zichtbaar aan een gebruiker zonder de toegang van de regelredacteur

   Voor instructies bij het toevoegen van gebruikers aan groepen, zie het Beleid van de [Gebruiker en Veiligheid](/help/sites-administering/security.md).

