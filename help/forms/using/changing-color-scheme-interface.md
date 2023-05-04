---
title: Het kleurenschema van de interface wijzigen
seo-title: Changing the color scheme of the interface
description: Het kleurenschema van de gebruikersinterfacegedeelten van de AEM Forms-werkruimte selectief aanpassen.
seo-description: How to modify the color scheme of AEM Forms workspace user interface portions selectively.
uuid: 32c32f7a-8271-4d2c-8a1f-ad5ab3c90b83
contentOwner: robhagat
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: 18dab82a-badf-4c32-83a2-cd5cb04cae89
exl-id: efbb9a9e-0ddf-49f2-bcb8-14cd0c6de5ee
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 0%

---

# Het kleurenschema van de interface wijzigen {#changing-the-color-scheme-of-the-interface}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

U kunt het kleurenschema van de gebruikersinterfacegedeelten van de AEM Forms-werkruimte aanpassen aan uw wensen. Hier volgen enkele voorbeelden van representatieve aanpassingen van kleurschema&#39;s. Naast de stappen die in dit artikel worden besproken, raadpleegt u [Algemene stappen voor aanpassing van de AEM Forms-werkruimte](/help/forms/using/generic-steps-html-workspace-customization.md).

## Bovenste navigatiebalk {#top-navigation-bar}

### Achtergrondafbeelding gebruiken {#using-background-image}

De navigatiebalk boven in de AEM Forms-werkruimte bijwerken.

1. Maak een achtergrondafbeelding om de kleur bij te werken. Geef het bestand een naam als newBackground.jpg.
1. Upload het bestand met de achtergrondafbeelding in de map /apps/ws/images met een WebDAV-client.

   >[!NOTE]
   >
   >Voor meer informatie over WebDAV toegang, zie [https://dev.day.com/docs/en/crx/current/how_to/webdav_access.html](https://docs.adobe.com/docs/en/crx/current/how_to/webdav_access.html).

1. Verwijs naar de nieuwe achtergrondafbeelding in /apps/ws/css/newStyle.css door de volgende stijl toe te voegen.

   ```css
   #header {
       background:#292929 url(../images/newBackground.jpg) repeat-x;
   }
   ```

### Kleureigenschap gebruiken in CSS {#using-color-property-in-css}

1. Voeg de volgende stijl toe aan newStyle.css op /apps/ws/css

   ```css
   #header {
   background : none;
   background-color: gray;
   }
   ```

## Categorieonderdeel {#category-component}

De component van de categorie toont de diverse categorieën van uw taken in het linkerpaneel. Als u de kleur wilt wijzigen, definieert u de achtergrondkleur in `.category` -element van het CSS-bestand.

## Taakcomponent {#task-component}

De taken worden getoond in het middelste paneel genoemd de Component TaskList. Als u de kleur van de stijl wilt wijzigen, wijzigt u de stijl die is gekoppeld aan de taakkiezer in de stijlpagina.
