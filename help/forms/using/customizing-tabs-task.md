---
title: Tabs aanpassen voor een taak
seo-title: Customizing tabs for a task
description: Hoe kan ik de namen van de tabbladen voor uw taken aanpassen in de werkruimte van LiveCycle AEM Forms.
seo-description: How-to customize the names of the tabs for your tasks, in LiveCycle AEM Forms workspace.
uuid: 77eabb63-f8ea-4ec0-8a41-b51c65cdecc0
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: ac0a281f-f589-4a70-9bc7-1a23e054b02f
exl-id: 42671435-e0f0-41db-af83-182b01742954
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 0%

---

# Tabs aanpassen voor een taak {#customizing-tabs-for-a-task}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

U kunt tabnamen aanpassen voor de `Start Process` in de `Start Process` De Uberweergave en de `Task Details` in de `ToDo` Uberweergave.

1. Volg de [Algemene stappen voor aanpassing van de AEM Forms-werkruimte](/help/forms/using/generic-steps-html-workspace-customization.md).
1. De waarde wijzigen van `tabname`in de `translation.json` bestand.

   Bijvoorbeeld, wijzigen `/apps/ws/locales/en-US/translation.json` voor Engels naar het volgende.

   * Voor taken die in het beginproces worden gestart, gebruikt u het volgende fragment uit het dialoogvenster `"startprocess" : {}` blokkeren.

   ```
   "tabname" : {
               "form" : "Application",
               "details" : "Overview",
               "attachments" : "Attachments",
               "notes" : "Helper Notes"
           }
   ```

   * Voor taken in Te-doen, gebruik het volgende fragment van `"todo" : {}` blokkeren.

   ```
   "tabname" : {
               "summary" : "Bird's-eye view",
               "history" : "Past",
               "form" : "Form",
               "details" : "Overview",
               "attachments" : "Attachments",
               "notes" : "Notes"
   }
   ```

   >[!NOTE]
   >
   >Voeg het corresponderende sleutel-waardepaar voor alle ondersteunde talen toe.
