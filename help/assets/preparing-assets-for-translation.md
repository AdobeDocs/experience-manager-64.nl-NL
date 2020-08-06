---
title: Middelen voorbereiden voor vertaling
description: Maak hoofdmappen voor talen om het vertalen van meertalige middelen voor te bereiden.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 77c62a8f2ca50f8aaff556a6848fabaee71017ce
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 2%

---


# Middelen voorbereiden voor vertaling {#preparing-assets-for-translation}

Meertalige elementen zijn elementen met binaire getallen, metagegevens en tags in meerdere talen. Over het algemeen bestaan binaire bestanden, metagegevens en tags voor elementen in één taal, die vervolgens naar andere talen worden vertaald voor gebruik in meertalige projecten.

In Adobe Experience Manager (AEM) Assets worden meertalige middelen opgenomen in mappen, waarbij elke map de middelen in een andere taal bevat.

Elke taalmap wordt een taalkopie genoemd. De hoofdmap van een taalkopie, de hoofdtaal genoemd, identificeert de taal van de inhoud in de taalkopie. Bijvoorbeeld: */content/dam/it* is de Italiaanse taalbasis voor de Italiaanse taalkopie. De exemplaren van de taal moeten een [correct-gevormde taalwortel](preparing-assets-for-translation.md#creating-a-language-root) gebruiken zodat de correcte taal wordt gericht wanneer de vertalingen van bronactiva worden uitgevoerd.

De taalkopie waarvoor u oorspronkelijk elementen toevoegt, is de primaire taal. De primaire taal is de bron die in andere talen wordt vertaald.

De hiërarchie van voorbeeldmappen bevat verschillende taalwortels:

```java
/content
    /- dam
             |- en
             |- fr
             |- de
             |- es
             |- it
             |- ja
             |- zh
```

Voer de volgende stappen uit om uw middelen voor vertaling voor te bereiden:

1. Maak de hoofdtaalhoofdmap van uw primaire taal. De hoofdmap voor de Engelse taal in de voorbeeldmaphiërarchie is bijvoorbeeld `/content/dam/en`. Zorg ervoor dat de hoofdmap van de taal correct is geconfigureerd op basis van de informatie in [Taalhoofdmap](preparing-assets-for-translation.md#creating-a-language-root)maken.

1. Voeg middelen toe aan uw primaire taal.
1. Creeer de taalwortel van elke doeltaal waarvoor u een taalexemplaar vereist.

## Een hoofdmap voor talen maken {#creating-a-language-root}

Als u de hoofdmap van de taal wilt maken, maakt u een map en gebruikt u een ISO-taalcode als waarde voor de eigenschap Naam. Nadat u de hoofdtaal hebt gemaakt, kunt u op elk niveau in de hoofdmap van de taal een kopie van de taal maken.

De hoofdpagina van de Italiaanse taalkopie van de voorbeeldhiërarchie heeft bijvoorbeeld de eigenschap Naam `it` . Het bezit van de Naam wordt gebruikt als naam van de activaknoop in de bewaarplaats, en bepaalt daarom de weg van de activa. (`https://[AEM_server]:[port]/assets.html/content/dam/it/*`)

1. Klik of tik op de assetconsole op **[!UICONTROL Create]** en kies **[!UICONTROL Folder]** in het menu.

   ![chlimage_1-120](assets/chlimage_1-120.png)

1. Typ in het veld Naam de landcode in de notatie `<language-code>`.

   ![chlimage_1-121](assets/chlimage_1-121.png)

1. Klik of tik **[!UICONTROL Create]**. De taalwortel wordt gecreeerd in de console van Activa.

## Taalwortels weergeven {#viewing-language-roots}

De interface met geoptimaliseerde aanrakingen biedt een paneel Referenties met een lijst met taalwortels die in AEM Assets zijn gemaakt.

1. Selecteer in de middelenconsole de primaire taal waarvoor u taalkopieën wilt maken.
1. Klik of tik op het pictogram GlobalNav en kies **[!UICONTROL References]** om het paneel Referentie te openen.

   ![chlimage_1-122](assets/chlimage_1-122.png)

1. Klik of tik op het venster Referenties **[!UICONTROL Language Copies]**. In het deelvenster Taalkopieën worden de taalkopieën van de elementen weergegeven.

   ![chlimage_1-123](assets/chlimage_1-123.png)

