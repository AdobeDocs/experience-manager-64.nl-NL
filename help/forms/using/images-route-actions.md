---
title: Afbeeldingen aanpassen die worden gebruikt in routehandelingen
seo-title: Customize images used in route actions
description: Hoe kan ik-om-de beelden aan te passen die in routeacties in de werkruimte van LiveCycle AEM Forms worden gebruikt.
seo-description: How-to customize the images used in route actions in LiveCycle AEM Forms workspace.
uuid: 42608376-587e-4b57-a9d5-8f9ebd981426
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: 10158c13-47b4-43e3-ac47-690f3cbab158
exl-id: 7b1f60e7-c8fa-43b6-bef4-88b42e7bbc36
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 0%

---

# Afbeeldingen aanpassen die worden gebruikt in routehandelingen {#customize-images-used-in-route-actions}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Voer de in [Algemene stappen voor aanpassing](/help/forms/using/generic-steps-html-workspace-customization.md) gevolgd door de stappen die in dit artikel worden beschreven.

## Afbeeldingen voor routeacties {#images-for-route-actions}

1. Voeg de stijlen die afbeeldingen in de CSS definiëren toe op de volgende locatie voor de nieuwe routeacties:

   `/apps/ws/css/newStyle.css`

   Bijvoorbeeld: Een nieuwe stijl toevoegen met de naam `myStyle1`zoals hieronder wordt getoond en uploadt het beelddossier `myStyleIcon1.png` aan de `/apps/ws/image`s met een WebDAV-client.

   >[!NOTE]
   >
   >Voor meer informatie over WebDAV toegang, zie [https://dev.day.com/docs/en/crx/current/how_to/webdav_access.html](https://docs.adobe.com/docs/en/crx/current/how_to/webdav_access.html).

   >[!NOTE]
   >
   >Voorkeur om de stijlnaam te gebruiken om het zelfde als de naam van de routeactie te zijn.

   ```css
   .myStyle1{
   
           background-image: url('../images/myStyleIcon1.png');
   
       }
   ```

## Taaklijstactie pop-up {#task-list-task-action-popup}

1. Een pop-upactie voor een taaklijst maken, zie [AEM Forms-werkruimtecode samenstellen](introduction-customizing-html-workspace.md#building-html-workspace-code). Hiervoor moet het ontwikkelingspakket worden gebruikt.

1. Kopiëren `/libs/ws/js/runtime/templates/task.html` tot `/apps/ws/js/runtime/templates/task.html`.

1. Als de naam van de CSS-stijl gelijk is aan de naam van de routeactie die van de server komt, wijzigt u de volgende code in `/apps/ws/js/runtime/templates/task.html`:

   ```
   <%if(routeList == null){%>
               <li>
                   <a href="javascript:void(0);" title="<%= $.t('taskaction.directcommand.'+availableCommands.directCommands[0])%>" value="<%= availableCommands.directCommands[0]%>" data-action="route"><%= $.t('taskaction.directcommand.'+availableCommands.directCommands[0])%></a>
               </li>
               <%}else{%>
               <%for(var i = 0; i<availableCommands.directCommands.length; i++){%>
               <li>
                   <a href="javascript:void(0);" title="<%= availableCommands.directCommands[i]%>" value="<%= availableCommands.directCommands[i]%>" data-action="route"><%= availableCommands.directCommands[i]%></a>
               </li>
               <%}%>
               <%}%>
   
   To
   
   <%if(routeList == null){%>
               <li class="<%= availableCommands.directCommands[0]%>" alt="<%= $.t('taskaction.directcommand.'+availableCommands.directCommands[0]+'.value')%>">
                   <a href="javascript:void(0);" title="<%= $.t('taskaction.directcommand.'+availableCommands.directCommands[0])%>" value="<%= availableCommands.directCommands[0]%>" data-action="route"><%= $.t('taskaction.directcommand.'+availableCommands.directCommands[0])%></a>
               </li>
               <%}else{%>
               <%for(var i = 0; i<availableCommands.directCommands.length; i++){%>
               <li class="<%= availableCommands.directCommands[i]%>" alt="<%= $.t('taskaction.directcommand.'+availableCommands.directCommands[i]+'.value')%>">
                   <a href="javascript:void(0);" title="<%= availableCommands.directCommands[i]%>" value="<%= availableCommands.directCommands[i]%>" data-action="route"><%= availableCommands.directCommands[i]%></a>
               </li>
               <%}%>
               <%}%>
   ```

1. Als de naam van de CSS-stijl verschilt van de naam van de routeactie die van de server komt, wijzigt u de volgende code in `/apps/ws/js/runtime/templates/task.html`. Er wordt een stapel toegevoegd van de `if-else` servlet voorwaarden om de stijl met de naam van de routeactie in kaart te brengen.

```
<%if(routeList == null){%>
            <li>
                <a href="javascript:void(0);" title="<%= $.t('taskaction.directcommand.'+availableCommands.directCommands[0])%>" value="<%= availableCommands.directCommands[0]%>" data-action="route"><%= $.t('taskaction.directcommand.'+availableCommands.directCommands[0])%></a>
            </li>
            <%}else{%>
            <%for(var i = 0; i<availableCommands.directCommands.length; i++){%>
            <li>
                <a href="javascript:void(0);" title="<%= availableCommands.directCommands[i]%>" value="<%= availableCommands.directCommands[i]%>" data-action="route"><%= availableCommands.directCommands[i]%></a>
            </li>
            <%}%>
            <%}%>
 
To
 
<%if(routeList == null){%>
            <li class="<%= availableCommands.directCommands[0]%>" alt="<%= $.t('taskaction.directcommand.'+availableCommands.directCommands[0]+'.value')%>">
                <a href="javascript:void(0);" title="<%= $.t('taskaction.directcommand.'+availableCommands.directCommands[0])%>" value="<%= availableCommands.directCommands[0]%>" data-action="route"><%= $.t('taskaction.directcommand.'+availableCommands.directCommands[0])%></a>
            </li>
            <%}else{%>
            <%for(var i = 0; i<availableCommands.directCommands.length; i++){%>
                <%if(availableCommands.directCommands[i].equals("myAction1")){%>
                     <li class="myStyle1" alt="<%= $.t('taskaction.directcommand.'+availableCommands.directCommands[i]+'.value')%>">
                         <a href="javascript:void(0);" title="<%= availableCommands.directCommands[i]%>" value="<%= availableCommands.directCommands[i]%>" data-action="route"><%= availableCommands.directCommands[i]%></a>
                     </li>
                <%}else if(availableCommands.directCommands[i].equals("myAction2")){%>
                     <li class="myStyle2" alt="<%= $.t('taskaction.directcommand.'+availableCommands.directCommands[i]+'.value')%>">
                         <a href="javascript:void(0);" title="<%= availableCommands.directCommands[i]%>" value="<%= availableCommands.directCommands[i]%>" data-action="route"><%= availableCommands.directCommands[i]%></a>
                     </li>
                <%}%>
            <%}%>
            <%}%>
```

## Taakdetails taakactie pop-up {#task-details-task-action-popup}

1. Kopiëren `/libs/ws/js/runtime/templates/taskdetails.html` tot `/apps/ws/js/runtime/templates/taskdetails.html`.

1. Als de naam van de CSS-stijl gelijk is aan de naam van de routeactie die van de server komt, wijzigt u de volgende code in `/apps/ws/js/runtime/templates/taskdetails.html`:

   ```
   <%for (var i = 0; i < availableCommands.directCommands.length; i++) {%>
                           <li class="routeAction">
                               <a href="javascript:void(0);" title="<%= availableCommands.directCommands[i]%>" value="<%= availableCommands.directCommands[i]%>" data-action="route"><%= availableCommands.directCommands[i]%></a>
                           </li>
                       <%}%>
   
   To
   
   <%for (var i = 0; i < availableCommands.directCommands.length; i++) {%>
                           <li class="routeAction">
                               <a href="javascript:void(0);" title="<%= availableCommands.directCommands[i]%>" value="<%= availableCommands.directCommands[i]%>" data-action="route">
                               <i class="<%= availableCommands.directCommands[i]%>" value="<%= availableCommands.directCommands[i]%>" data-action="route"/>
                               </a>
                           </li>
                       <%}%>
   ```

1. Als de naam van de CSS-stijl verschilt van de naam van de routeactie die van de server komt, wijzigt u de volgende code in `/apps/ws/js/runtime/templates/taskdetails.html`. Er wordt een stapel toegevoegd `if-else` servlet voorwaarden om de stijl met de naam van de routeactie in kaart te brengen.

   ```
   <%for (var i = 0; i < availableCommands.directCommands.length; i++) {%>
                           <li class="routeAction">
                               <a href="javascript:void(0);" title="<%= availableCommands.directCommands[i]%>" value="<%= availableCommands.directCommands[i]%>" data-action="route"><%= availableCommands.directCommands[i]%></a>
                           </li>
                       <%}%>
   
   To
   
   <%for (var i = 0; i < availableCommands.directCommands.length; i++) {%>
                   <%if(availableCommands.directCommands[i].equals("myAction1")){%>
                       <li class="routeAction">
                               <a href="javascript:void(0);" title="<%= availableCommands.directCommands[i]%>" value="<%= availableCommands.directCommands[i]%>" data-action="route">
                               <i class="myStyle1" value="<%= availableCommands.directCommands[i]%>" data-action="route"/>
                               </a>
                           </li>
                   <%}else if(availableCommands.directCommands[i].equals("myAction2")){%>
                       <li class="routeAction">
                               <a href="javascript:void(0);" title="<%= availableCommands.directCommands[i]%>" value="<%= availableCommands.directCommands[i]%>" data-action="route">
                               <i class="myStyle2" value="<%= availableCommands.directCommands[i]%>" data-action="route"/>
                               </a>
                           </li>
                   <%}%>
               <%}%>
   ```

1. Openen `/apps/ws/js/registry.js` voor het bewerken van en het zoeken naar de volgende tekst:\
   `"text!/lc/libs/ws/js/runtime/templates/taskdetails.html"`

1. Vervang de tekst door:\
   `"text!/lc/apps/ws/js/runtime/templates/taskdetails.html"`
