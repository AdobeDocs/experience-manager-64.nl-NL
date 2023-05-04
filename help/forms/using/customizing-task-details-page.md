---
title: De pagina met taakdetails aanpassen
seo-title: Customizing the task details page
description: Hoe te om de pagina van taakdetails in de werkruimte van AEM Forms aan te passen om de standaardinformatie te wijzigen die over een taak wordt getoond.
seo-description: How-to customize the task details page in AEM Forms workspace to modify the default information displayed about a task.
uuid: d85fae55-8e66-4595-8560-5485622b6841
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: 16e57cf6-aaa1-406d-a6ad-71ec60b15386
exl-id: de97e6f7-25bf-462b-b67d-0d3fbd86a321
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 0%

---

# De pagina met taakdetails aanpassen {#customizing-the-task-details-page}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

De pagina met taakdetails bevat informatie over een taak en de bijbehorende processen. U kunt de pagina met taakdetails echter aanpassen om informatie toe te voegen of te verwijderen.

U kunt de volgende informatie toevoegen aan de pagina met taakdetails:

* Informatie beschikbaar in het JSON-object van een taak (taaksectie in [JSON-objectbeschrijving in de AEM Forms-werkruimte](/help/forms/using/html-workspace-json-object-description.md))
* Informatie beschikbaar in het JSON-object van een procesinstantie (sectie Procesinstantie in [JSON-objectbeschrijving in de AEM Forms-werkruimte](/help/forms/using/html-workspace-json-object-description.md))

De pagina met taakdetails aanpassen:

1. Volg [Algemene stappen voor aanpassing van de AEM Forms-werkruimte.](/help/forms/using/generic-steps-html-workspace-customization.md)
1. Als u aanvullende informatie wilt weergeven, voegt u de corresponderende sleutel-waardeparen toe aan de `translation.json` bestand bij `todo`blok > `details`blok > `app`blok > [ `required`blok].

   De [ `required`blok] verwijst naar beschikbare blokken, zoals het taakblok voor taakinformatie, procesblok voor procesinformatie, en het huidige het taakblok voor lopende taakinformatie.

   Bijvoorbeeld, om informatie over de Selectie van de Route toe te voegen Vereist in de pagina van taakdetails, kunt u het volgende zeer belangrijk-waardepaar in het taakblok toevoegen:

   ```
   "todo" : {
       .
       .
       .
       "details" : {
           .
           .
           "task" : {
               .
               .
               "RouteSelectionRequired" : "Route Selection Required"
           }
       }
   }
   ```

   >[!NOTE]
   >
   >Voeg overeenkomstige sleutel-waardeparen voor alle gesteunde talen toe.

1. Kopiëren `/libs/ws/js/runtime/templates/taskdetails.html` tot `/apps/ws/js/runtime/templates/taskdetails.html`.

   Nieuwe informatie toevoegen aan `/apps/ws/js/runtime/templates/taskdetails.html`. Bijvoorbeeld:

   ```css
   <div class="detailsContainer">
       .
       .
       <ul>
           .
           .
           <li>
               <label for="routeSelectionRequired" title="<%= $.t('todo.details.task.RouteSelectionRequired')%>"><%= $.t('todo.details.task.RouteSelectionRequired')%></label>
               <div>
                   <span id="routeSelectionRequired"><%= isRouteSelectionRequired != null ? isRouteSelectionRequired : ''%></span>
               </div>
           </li>
           .
           .
       </ul>
   </div>
   ```

1. Open /apps/ws/js/registry.js voor bewerking.

   Zoeken en vervangen `text!/lc/libs/ws/js/runtime/templates/taskdetails.html` with `text!/lc/apps/ws/js/runtime/templates/taskdetails.html`.

>[!NOTE]
>
>Als u de pagina met taakdetails wilt aanpassen met taken die zijn gemaakt op het tabblad **Proces starten **van de AEM Forms-werkruimte, voegt u de nieuwe informatie toe aan `/apps/ws/js/runtime/templates/startprocess.html`.
>
>Als u nieuwe stijlen wilt toevoegen voor de informatie die op de detailpagina is toegevoegd, wijzigt u het CSS-bestand met de opdracht *Wijzigingen in gebruikersinterface* sectie in [Aanpassing werkruimte](/help/forms/using/changing-locale-user-interface.md).
