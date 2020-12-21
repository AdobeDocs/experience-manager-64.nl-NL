---
title: Het lettertype in de interface wijzigen
seo-title: Het lettertype in de interface wijzigen
description: Hoe u de lettertypen in de gebruikersinterface selectief kunt wijzigen.
seo-description: Hoe u de lettertypen in de gebruikersinterface selectief kunt wijzigen.
uuid: d079f656-76f8-4908-9989-dde79e215eb2
contentOwner: robhagat
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: 487e3966-443a-408e-b5af-899fcba6fca6
translation-type: tm+mt
source-git-commit: f13d358a6508da5813186ed61f959f7a84e6c19f
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 1%

---


# Het lettertype wijzigen op de interface {#changing-the-font-on-the-interface}

U kunt het lettertype wijzigen dat in de AEM Forms-werkruimte wordt weergegeven. Lettertypen die in een specifieke sectie van de gebruikersinterface worden gebruikt, worden gedefinieerd in de bijbehorende sectie van het stijlblad. U kunt de lettertypen in de gebruikersinterface selectief wijzigen.

Volg de [Algemene stappen voor de aanpassing van de AEM Forms-werkruimte](/help/forms/using/generic-steps-html-workspace-customization.md) en volg, afhankelijk van uw vereisten, de stappen voor het aanpassen van CSS, HTML, of allebei.

1. Wijzig of voeg de lettertypefamilie toe aan een bestaande stijl.
1. Wijzig of voeg de lettertypefamilie inline voor het HTML-element toe.
1. Voeg een stijl toe en gebruik deze voor het HTML-element.

Voer bijvoorbeeld de volgende stappen uit als u het font van het ankerpunt op de bovenste navigatiebalk wilt wijzigen in Courier New:

1. Meld u aan bij CRXDE Lite door `https://[server]:[port]/lc/crx/de/index.jsp` te openen.
1. Voer een van de volgende handelingen uit:

   1. Als u de lettertypefamilie wilt wijzigen in een bestaande stijl, voegt u het volgende toe in het bestand newStyle.css op /apps/ws/css.

      ```css
      #topnav a {
         font-family: "Courier New";
      }
      ```

   1. Als u de lettertype-familie inline voor het HTML-element wilt toevoegen, kopieert u het bestand `/libs/ws/js/runtime/templates/appnavigation.html` naar `/apps/ws/js/runtime/templates/appnavigation.html`.

      Werk het bestand /apps/ws/js/runtime/templates/appnavigation.html als volgt bij:

      ```
      <li class="process"><a href="#" title="<%= $.t('index.header.topnav.startprocess.detail')%>" style="font-family:Courier New;" ><%= $.t('index.header.topnav.startprocess.name')%></a></li>
      <li class="todo"><a href="#/todo" title="<%= $.t('index.header.topnav.todo.detail')%>" style="font-family:Courier New;" ><%= $.t('index.header.topnav.todo.name')%></a></li>
      <li class="track"><a href="#/tracking" title="<%= $.t('index.header.topnav.tracking.detail')%>" style="font-family:Courier New;" ><%= $.t('index.header.topnav.tracking.name')%></a></li>
      <li class="preference"><a href="#/preferences" title="<%= $.t('index.header.topnav.preferences.detail')%>" style="font-family:Courier New;" ><%= $.t('index.header.topnav.preferences.name')%></a></li>
      ```

      Open het bestand /apps/ws/js/registry.js voor bewerking en vervang `text!/lc/libs/ws/js/runtime/templates/appnavigation.html` door `text!/lc/apps/ws/js/runtime/templates/appnavigation.html`.

   1. Als u een stijl wilt toevoegen die de lettertypefamilie definieert, voegt u het volgende toe in het bestand newStyle.css op /apps/ws/css.

      ```css
      .myNewFontStyle a {
         font-family: "Courier New";
      }
      ```

      Als u de lettertypefamilie inline voor het HTML-element wilt toevoegen, voegt u het volgende toe in het bestand appnavigation.html op /apps/ws/js/runtime/templates.

      ```css
      <div id="topnav" class="myNewFontStyle">
          <ul>
              <li class="process"><a href="#" title="<%= $.t('index.header.topnav.startprocess.detail')%>" ><%= $.t('index.header.topnav.startprocess.name')%></a></li>
              <li class="todo"><a href="#/todo" title="<%= $.t('index.header.topnav.todo.detail')%>"><%= $.t('index.header.topnav.todo.name')%></a></li>
              <li class="track"><a href="#/tracking" title="<%= $.t('index.header.topnav.tracking.detail')%>" ><%= $.t('index.header.topnav.tracking.name')%></a></li>
              <li class="preference"><a href="#/preferences" title="<%= $.t('index.header.topnav.preferences.detail')%>" ><%= $.t('index.header.topnav.preferences.name')%></a></li>
          </ul>
      </div>
      ```

1. Start de werkruimte opnieuw en wis de browsercache zodat de wijzigingen zichtbaar zijn.

![change_font_](assets/change_font_before.png)
**beforeFigure:** *Top navigation bar before font customation*

![change_font_](assets/change_font_after.png)
**afterFigure:** *Top navigation bar after font customization of first tab*
