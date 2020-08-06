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
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 0%

---


# AEM DS-instellingen configureren {#configuring-aem-ds-settings}

In dit artikel wordt beschreven hoe u **AEM DS Settings Service** kunt configureren. Deze instelling kan in meerdere scenario&#39;s worden gebruikt, bijvoorbeeld:

* In het Correspondentenbeheer

   * Voor het configureren van de AEM Forms-workflow
   * Tijdens het gebruik van de portal Formulieren voor het op afstand opslaan van concepten/verzenden

* In adaptieve formulieren voor gevallen waarin een adaptief formulier wordt ingediend vanuit een publicatie-instantie

Hieronder vindt u de stappen voor het configureren van het **[!UICONTROL AEM DS Settings]** volgende:

1. Open de Manager van de Configuratie op publiceer instantie gebruikend URL:

   *http://localhost:port/system/console/configMgr*.

   ![aem_web_configuration_console](assets/aem_web_configuration_console.png)

1. Zoek in het **[!UICONTROL Adobe Experience Manager Web Console Configuration]** venster de **[!UICONTROL AEM DS Settings]** optie en klik erop.

   ![ds_settings](assets/ds_settings.png)

1. In het **[!UICONTROL AEM DS Settings Service]** venster worden de algemene configuratie-instellingen voor AEM DS-componenten weergegeven.

   ![ds_settings_1](assets/ds_settings_1.png)

1. Voeg de volgende informatie in de respectieve gebieden toe:

   **[!UICONTROL Processing Server URL]**: De Verwerkingsserver is de server waarop de Forms- of AEM-workflow moet worden geactiveerd. Dit kan gelijk zijn aan de URL van de AEM auteur-instantie of de andere server-URL (http:// localhost:port/).

   **[!UICONTROL Processing Server User Name]**: Gebruikersnaam van workflowgebruiker [gebaseerd op de server-URL die wordt gebruikt]

   **[!UICONTROL Processing Server Password]**: Wachtwoord workflowgebruiker

   >[!NOTE]
   >
   >* Voordat u Forms- of AEM-workflows gebruikt, moet u de service voor DS-instellingen configureren voordat u gegevens van de publicatieserver verzendt. Anders zal de indiening van het formulier mislukken.

