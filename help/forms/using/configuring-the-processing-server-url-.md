---
title: AEM DS-instellingen configureren
seo-title: AEM DS-instellingen configureren
description: U moet de URL van de verwerkingsserver opgeven voordat u een formulier verzendt.
seo-description: U moet de URL van de verwerkingsserver opgeven voordat u een formulier verzendt.
uuid: 2b415c99-275b-4b67-bb8e-35329514ecbb
contentOwner: amgoyal
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: Configuration
discoiquuid: fbb9044a-a737-45f6-8062-0ef5424a92f8
translation-type: tm+mt
source-git-commit: 1ebe1e871767605dd4295429c3d0b4de4dd66939

---


# AEM DS-instellingen configureren {#configuring-aem-ds-settings}

In dit artikel wordt beschreven hoe u **AEM DS Settings Service** configureert. Deze instelling kan in meerdere scenario&#39;s worden gebruikt, bijvoorbeeld:

* In het Correspondentenbeheer

   * Voor het configureren van AEM Forms Workflow
   * Tijdens het gebruik van de portal Formulieren voor het op afstand opslaan van concepten/verzenden

* In adaptieve formulieren voor gevallen waarin een adaptief formulier wordt ingediend vanuit een publicatie-instantie

Hier volgen de stappen voor het configureren van de **[!UICONTROL AEM DS-instellingen]**:

1. Open de Manager van de Configuratie op publiceer instantie gebruikend URL:

   *http://localhost:port/system/console/configMgr*.

   ![aem_web_configuration_console](assets/aem_web_configuration_console.png)

1. Zoek en klik in het venster Configuratie **[!UICONTROL webconsole van]** Adobe Experience Manager op de optie **[!UICONTROL AEM DS Settings]** .

   ![ds_settings](assets/ds_settings.png)

1. In het venster **[!UICONTROL AEM DS Settings Service]** worden de algemene configuratie-instellingen voor AEM DS Components weergegeven.

   ![ds_settings_1](assets/ds_settings_1.png)

1. Voeg de volgende informatie in de respectieve gebieden toe:

   **[!UICONTROL URL]** verwerkingsserver: De Verwerkingsserver is de server waarop de Forms of AEM-workflow moet worden geactiveerd. Dit kan gelijk zijn aan de URL van de AEM-auteurinstantie of de andere Server-URL (http:// localhost:port/).

   **[!UICONTROL Gebruikersnaam]** server verwerken: Gebruikersnaam van workflowgebruiker [gebaseerd op de server-URL die wordt gebruikt]

   **[!UICONTROL Wachtwoord]** verwerkingsserver: Wachtwoord workflowgebruiker

   >[!NOTE]
   >
   >* Wanneer u Forms of AEM-workflows gebruikt, voordat u een verzending vanaf de publicatieserver maakt, is het nodig de service DS-instellingen te configureren. Anders zal de indiening van het formulier mislukken.

