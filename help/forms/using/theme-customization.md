---
title: Aanpassing thema
seo-title: Theme Customization
description: Het thema van uw AEM Forms-app aanpassen.
seo-description: How to customize the theme of your AEM Forms app.
uuid: 36632e67-1cc6-416d-ae80-d84bbabab4bd
contentOwner: robhagat
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-app
discoiquuid: c72f608e-052a-4bf9-b7bc-ddf57483af35
exl-id: fb1e0bec-c943-4468-920d-8ef360a01365
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 0%

---

# Aanpassing thema {#theme-customization}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

U kunt de HTML-code en het CSS-bestand aanpassen en zo een aparte organisatie-specifieke vormgeving geven voor de AEM Forms-app. U kunt bijvoorbeeld de achtergrondkleur en -hoogte van taken of Startpunten wijzigen. In het volgende voorbeeld worden instructies gegeven om te wijzigen:

* aanwijzingen weergeven in plaats van de beschrijving
* aantal weergaveroutes
* kleur achtergrondverloop

## Stappen {#steps}

1. Open uw project.

   * Voor iOS: open `Capture.xcodeproj` in Xcode
   * Voor Android opent u het Android-project in Eclipse.
   * Voor Windows: open `MWSWindows.sln` in Visual Studio.

1. Navigeer naar de map templates.

   * Navigeer in Xcode naar de **Vastleggen > www > wsmobile > js > runtime > templates** map.
   * Navigeer in Eclipse naar de **assets > www > wsmobile > js > runtime > templates** map.
   * In Visual Studio, navigeer aan **MWSWindows > www > wsmobile > js > runtime > templates** map.

1. Open de `template.html` bestand voor bewerking.
1. Zoek de volgende tekenreeks:

   ```
   <%if ( (task.description !== "") && (task.description !== null) && (typeof task.description !== null) && (typeof task.description !== 'undefined') ) {%>
                  <div class="description_details">
                    <%= task.description %>
                  </div>
                 <%} else 
   ```

   Vervangen door `<%`.

1. Zoek de volgende code in het dialoogvenster `template.html` bestand:

   ```
   <ul id="task_menu_list">
                                   <li class="approve" title="<%= task.availableCommands.directCommands[0]%>" data-routename="<%= task.availableCommands.directCommands[0]%>">
                                       <%= task.availableCommands.directCommands[0]%>
                                   </li>
                                   <li class="reject last" title="<%= task.availableCommands.directCommands[1]%>" data-routename="<%= task.availableCommands.directCommands[1]%>">
                                       <%= task.availableCommands.directCommands[1]%>
                                   </li>
   ```

1. Neem een opmerking op in de volgende regel en sla het bestand op.

   ```
   task.availableCommands.directCommands[1]%>">
   <%= task.availableCommands.directCommands[1]%>
   </li>
   ```

1. Navigeer naar de css-map.

   * Navigeer in Xcode naar **Vastleggen > www > wsmobile > css**.
   * Navigeer in Eclipse naar **middelen > www > wsmobile > css**.
   * In Visual Studio, navigeer aan **MWSWindows > www > wsmobile > css**.

1. Open de `_style.css` bestand voor bewerking.
1. Voor achtergrondafbeelding wijzigt u `#323232` tot `#fff`.
1. Wijzigingen opslaan en sluiten `_style.css` bestand.
1. Open de AEM Forms-app.

   De AEM Forms-app geeft nu instructies weer in plaats van een beschrijving.
