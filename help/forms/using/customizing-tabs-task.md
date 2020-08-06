---
title: Tabs aanpassen voor een taak
seo-title: Tabs aanpassen voor een taak
description: Hoe kan ik de namen van de tabbladen voor uw taken aanpassen in de werkruimte van LiveCycle AEM Forms.
seo-description: Hoe kan ik de namen van de tabbladen voor uw taken aanpassen in de werkruimte van LiveCycle AEM Forms.
uuid: 77eabb63-f8ea-4ec0-8a41-b51c65cdecc0
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: ac0a281f-f589-4a70-9bc7-1a23e054b02f
translation-type: tm+mt
source-git-commit: f13d358a6508da5813186ed61f959f7a84e6c19f
workflow-type: tm+mt
source-wordcount: '121'
ht-degree: 0%

---


# Tabs aanpassen voor een taak {#customizing-tabs-for-a-task}

U kunt tabnamen voor de `Start Process` component aanpassen in de `Start Process` Uberweergave en de `Task Details` component in de `ToDo` Uberweergave.

1. Voer de [algemene stappen uit voor aanpassing](/help/forms/using/generic-steps-html-workspace-customization.md)van de AEM Forms-werkruimte.
1. Wijzig de waarde van `tabname`in het `translation.json` bestand.

   Wijzig bijvoorbeeld `/apps/ws/locales/en-US/translation.json` voor Engels in het volgende.

   * Gebruik het volgende fragment uit het `"startprocess" : {}` blok voor taken die in het beginproces worden gestart.

   ```
   "tabname" : {
               "form" : "Application",
               "details" : "Overview",
               "attachments" : "Attachments",
               "notes" : "Helper Notes"
           }
   ```

   * Voor taken in te doen, gebruik het volgende fragment van het `"todo" : {}` blok.

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
