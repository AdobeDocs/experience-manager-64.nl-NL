---
title: Bewegingsaanpassing
seo-title: Gesture customization
description: De bewegingen in uw AEM Forms-app aanpassen
seo-description: Customize the gestures on your AEM Forms app
uuid: 117e0e21-66bd-42f1-879c-6c1443991974
contentOwner: robhagat
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-app
discoiquuid: 747d13d3-e7cc-4aa1-bcc8-4b57157e71ed
exl-id: 238410e0-1623-49dc-b2fc-b5b2d5fb362b
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 0%

---

# Bewegingsaanpassing {#gesture-customization}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

U kunt de gebaren van de AEM Forms-app aanpassen om een aparte methode voor het werken met de app te bieden. U kunt bijvoorbeeld nieuwe bewegingen toevoegen om een taak of beginpunt te openen of te sluiten.

## Bewegingen aanpassen in de AEM Forms-app {#to-customize-gestures-in-aem-forms-app}

In de AEM Forms-app wordt met de veegbeweging links een nieuwe taak of beginpunt geopend en met de veegbeweging rechts niets. In het volgende voorbeeld worden stappen beschreven voor het openen van een nieuwe taak of beginpunt voor het uitvoeren van de rechterveegbeweging in de AEM Forms-app.

1. Open uw project.

   * Voor iOS: open `Capture.xcodeproj` in Xcode
   * Voor Android opent u het Android-project in Eclipse.
   * Voor Windows: open `MWSWindows.sln` in Visual Studio.

1. Navigeer naar de map views en open het dialoogvenster `task.js` bestand voor bewerking.

   * Navigeer in Xcode naar de **Vastleggen > www > wsmobile > js > runtime > views** map.
   * Navigeer in Eclipse naar de **assets > www > wsmobile > js > runtime > views** map.
   * In Visual Studio, navigeer aan **MWSWindows > www > wsmobile > js > runtime > views** map.

   >[!NOTE]
   >
   >Het bestand task.js bevat de backboneweergave die is gekoppeld aan elke taak of elk beginpunt dat in de lijst met taken of beginpunten wordt vermeld.

1. In de `task.js` bestand, zoekt u naar de eigenschap events van de weergave.

   De eigenschap events is een kaart met elke vermelding in de indeling:

   `"EventName Selector": "Function"`

   Wanneer u een JavaScript-gebeurtenis activeert met de naam `EventName`op een HTML-element dat is opgegeven door `Selector`de `Function`wordt aangeroepen.

1. Zoeken

   * &quot;tap.taskContentArea&quot;: &quot;onTaskClick&quot;,

      &quot;tap.taskOpenArea&quot;: &quot;onTaskClick&quot;,

      &quot;tik.task-content&quot;: &quot;onTaskClick&quot;,

      &quot;tap.last_empty_div&quot;: &quot;onTaskClick&quot;,
   en vervangen door

   * &quot;swipe.taskContentArea&quot; : &quot;onTaskClick&quot;,

      &quot;swipe.taskOpenArea&quot; : &quot;onTaskClick&quot;,

      &quot;veeggebaar.task-content&quot;: &quot;onTaskClick&quot;,

      &quot;veeggebaar.last_empty_div&quot;: &quot;onTaskClick&quot;,


1. Sla het bestand op en sluit het `task.js` bestand.
1. De AEM Forms-app ontwikkelen en uitvoeren. Nu kunt u een toepassing openen met een veegbeweging naar links en een veegbeweging naar rechts.

Op dezelfde manier kunt u ook wijzigingen aanbrengen in andere weergaven voor verschillende combinaties van bewegingen, HTML-elementen en functies.
