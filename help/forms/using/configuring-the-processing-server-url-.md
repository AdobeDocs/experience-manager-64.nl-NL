---
title: AEM DS-instellingen configureren
seo-title: Configuring AEM DS settings
description: U moet de URL van de verwerkingsserver opgeven voordat u een formulier verzendt.
seo-description: You need to specify the processing server URL before you submit a form.
uuid: 2b415c99-275b-4b67-bb8e-35329514ecbb
contentOwner: amgoyal
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: Configuration
discoiquuid: fbb9044a-a737-45f6-8062-0ef5424a92f8
role: Admin
exl-id: f60beaae-4082-4165-8a37-9d9c94e360b2
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 0%

---

# AEM DS-instellingen configureren {#configuring-aem-ds-settings}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Dit artikel beschrijft hoe te vormen **AEM DS Settings Service**. Deze instelling kan in meerdere scenario&#39;s worden gebruikt, bijvoorbeeld:

* In het Correspondentenbeheer

   * Voor het configureren van de AEM Forms-workflow
   * Tijdens het gebruik van de portal Formulieren voor het op afstand opslaan van concepten/verzenden

* In adaptieve formulieren voor gevallen waarin een adaptief formulier wordt ingediend vanuit een publicatie-instantie

Hier volgen de stappen voor het configureren van de **[!UICONTROL AEM DS Settings]**:

1. Open de Manager van de Configuratie op publiceer instantie gebruikend URL:

   *http://localhost:port/system/console/configMgr*.

   ![aem_web_configuration_console](assets/aem_web_configuration_console.png)

1. In de **[!UICONTROL Adobe Experience Manager Web Console Configuration]** venster, zoek en klik op **[!UICONTROL AEM DS Settings]** optie.

   ![ds_settings](assets/ds_settings.png)

1. De **[!UICONTROL AEM DS Settings Service]** toont de gemeenschappelijke configuratiemontages voor AEM DS Componenten.

   ![ds_settings_1](assets/ds_settings_1.png)

1. Voeg de volgende informatie in de respectieve gebieden toe:

   **[!UICONTROL Processing Server URL]**: De Verwerkingsserver is de server waarop de Forms- of AEM-workflow moet worden geactiveerd. Dit kan gelijk zijn aan de URL van de AEM auteur-instantie of de andere server-URL (http:// localhost:port/).

   **[!UICONTROL Processing Server User Name]**: Gebruikersnaam werkstroomgebruiker [gebaseerd op de server-URL die wordt gebruikt]

   **[!UICONTROL Processing Server Password]**: Wachtwoord workflowgebruiker

   >[!NOTE]
   >
   >* Voordat u Forms- of AEM-workflows gebruikt, moet u de service voor DS-instellingen configureren voordat u gegevens van de publicatieserver verzendt. Anders zal de indiening van het formulier mislukken.

