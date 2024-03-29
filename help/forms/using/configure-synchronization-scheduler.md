---
title: De synchronisatieplanner configureren
seo-title: Configuring the synchronization scheduler
description: Leer hoe u elementen kunt migreren en synchroniseren, synchronisatieplanner kunt configureren en mappen kunt gebruiken om elementen te rangschikken.
seo-description: Learn how to migrate and sync assets, configure sync scheduler, and use folders to arrange assets.
uuid: a6445b45-9c1c-4483-a32e-453648c488c5
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: Configuration
discoiquuid: 2c8cea3c-8d8b-41d4-8ef9-a0ada8f86be6
role: Admin
exl-id: 7f1c4bac-accf-43e4-9439-89c5420d50f2
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 0%

---

# De synchronisatieplanner configureren {#configuring-the-synchronization-scheduler}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Standaard wordt de synchronisatieplanner na elke 3 minuten uitgevoerd om alle elementen te synchroniseren die via LiveCycle Workbench 11 zijn gewijzigd en bijgewerkt in de opslagplaats. Toepassingen die formulieren en bronnen bevatten, zijn zichtbaar in de AEM Forms-gebruikersinterface nadat het synchronisatieproces is voltooid.

## Het interval van de synchronisatieplanner van de verandering {#change-interval-of-the-synchronization-scheduler}

Voer de volgende stappen uit om het interval van de synchronisatieplanner te veranderen:

1. Meld u aan bij AEM Configuratiebeheer. De URL van Configuration Manager is `https://[Server]:[Port]/lc/system/console/configMgr`

1. Zoek en open de **FormsManagerConfiguration** bundel.

1. Geef een nieuwe waarde op voor de **Frequentie synchronisatieplanning** optie.

   De eenheid van de frequentie is minuten. Bijvoorbeeld, om de planner te vormen om na elke 60 minuten te lopen, specificeer 60.

## Elementen synchroniseren {#synchronizing-assets}

U kunt de **Elementen synchroniseren vanuit gegevensopslagruimte** om de elementen handmatig te synchroniseren. Voer de volgende stappen uit om de elementen handmatig te synchroniseren:

1. Meld u aan bij AEM Forms. De standaard-URL is `https://[Server]:[Port]/lc/aem/forms/`.

   ![AEM Forms-gebruikersinterface](assets/aem_forms_ui.png)

   **Afbeelding:** *AEM Forms-gebruikersinterface*

1. Klik op de knop ![aem6forms_sync](assets/aem6forms_sync.png) in de werkbalk. Als u geen elementen hebt bij het laatste geconfigureerde pad, wordt het dialoogvenster weergegeven zoals hieronder. Klikken **Start** om de synchronisatie te starten.

   ![Synchronisatie, dialoogvenster](assets/migrate-and-syncronize.png)

   **Afbeelding:** *Synchronisatie, dialoogvenster*

## Synchronisatiefout voor probleemoplossing {#troubleshooting-synchronization-error}

U kunt nieuwe toepassingen maken in de werkstroomontwerper (LiveCycle Workbench).

Als de nieuwe toepassing en een map in /content/dam/formsanddocuments dezelfde naam hebben, wordt een fout &quot;*Middelen met dezelfde naam als deze toepassing bestaan al op hoofdniveau.*&quot; is geregistreerd.

U lost het conflict op door de naam van de toepassing te wijzigen en de elementen handmatig te synchroniseren.

![Conflicten in dialoogvenster voor synchronisatie van elementen](assets/sync-conflict.png)

**Afbeelding:** *Conflicten in dialoogvenster voor synchronisatie van elementen*
