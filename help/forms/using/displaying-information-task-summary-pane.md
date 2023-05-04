---
title: Informatie weergeven in het deelvenster Taakoverzicht
seo-title: Displaying information in the Task Summary pane
description: In de werkruimte van AEM Forms, kan een ruit van het Overzicht van de Taak worden gevormd om de taak samen te vatten of een andere Web-pagina te tonen.
seo-description: In AEM Forms workspace, a Task Summary pane can be configured to summarize the task or display any other web page.
uuid: 2fcc3d9f-0ec2-4250-8dc1-9746fd72ea60
contentOwner: robhagat
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: 90d0f584-b598-4b21-85d7-31da5f13d404
exl-id: cb9de2d7-04ad-4221-8db7-403464c9888b
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 0%

---

# Informatie weergeven in het deelvenster Taakoverzicht {#displaying-information-in-the-task-summary-pane}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Als u een taak opent in de AEM Forms-werkruimte, wordt in het deelvenster Taakoverzicht een overzicht van de taak weergegeven. Deze aanvullende en relevante informatie voor een taak voegt meer waarde toe aan de eindgebruiker van de AEM Forms-werkruimte.

In de werkruimte van AEM Forms kunt u een webpagina van uw keuze weergeven in het deelvenster Taakoverzicht. Een proces kan worden gecreeerd om een ruit van het Overzicht van de Taak te tonen gebruikend Workbench.

1. Maak een taakproces toewijzen in Workbench. Voor meer details over de verrichting van de Taak toewijzen, zie het onderwerp van de Verwijzing van de Dienst in [Workbench Help](https://help.adobe.com/en_US/AEMForms/6.1/WorkbenchHelp/).

   >[!NOTE]
   >
   >Als er een TaskSummary-URL bestaat, wordt de weergave Taakoverzicht standaard geopend in plaats van de formulierweergave. In dit geval wordt het formulier niet geopend in de gemaximaliseerde modus, zelfs niet als een gebruiker de optie &quot;Het formulier openen in de gemaximaliseerde modus&quot; in Taak toewijzen inschakelt.

1. Configureer het veld Taakoverzicht-URL. U kunt een letterlijke waarde, een sjabloon, een variabele of een XPath-expressie opgeven.
1. Hieronder ziet u een voorbeeld van het weergeven van de informatie op de pagina Taakoverzicht.

   * Aanmelden bij CRXDE Lite-omgeving bij `https://[server]:[port]/lc/crx/de`.
   * `Create a node`**SampleSummary** ` under `/content` with type `nt:ongestructureerd`. In the properties of this node, add `sling:resourceType` of type String and value `SampleSummary`. In the Access Control List of this node, add an entry for `PERM_WORKSPACE_USER` allowing `jcr:lezen` privileges.`
   * `Create a folder`**SampleSummary** krachtens `/apps`. In de lijst Toegangsbeheer van `/apps/SampleSummary`, een item toevoegen voor `PERM_WORKSPACE_USER` toestaan `jcr:readprivileges`.
   * `Create a file `html.esp` at `/apps/SampleSummary`. For example, add the following lines in `html.esp`.`

   ```
   <html>
       <body>
           <h1>Sample Summary</h1>
           <br/>
           <p>Hello Sir!
               <br/>
               This is sample summary page for this task.
           </p>
       </body>
   </html>
   ```

   * Stel de waarde van de taaksummiere URL in op `/lc/content/SampleSummary.html` in de stap Taak toewijzen.
   * Wanneer de taak die bij deze stap Taak toewijzen hoort, wordt geopend in de AEM Forms-werkruimte, wordt `html.esp` om `/apps/SampleSummary` wordt weergegeven in het taakoverzichtsvenster.
