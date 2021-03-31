---
title: Middelen voorbereiden voor vertaling
description: Maak hoofdmappen voor talen om het vertalen van meertalige middelen voor te bereiden.
contentOwner: AG
feature: Projecten,vertalen
role: Business Practice,Administrator
translation-type: tm+mt
source-git-commit: 29e3cd92d6c7a4917d7ee2aa8d9963aa16581633
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 2%

---


# Elementen voorbereiden voor vertaling {#preparing-assets-for-translation}

Meertalige elementen zijn elementen met binaire getallen, metagegevens en tags in meerdere talen. Over het algemeen bestaan binaire bestanden, metagegevens en tags voor elementen in één taal, die vervolgens naar andere talen worden vertaald voor gebruik in meertalige projecten.

In Adobe Experience Manager (AEM) Assets worden meertalige middelen opgenomen in mappen, waarbij elke map de middelen in een andere taal bevat.

Elke taalmap wordt een taalkopie genoemd. De hoofdmap van een taalkopie, de hoofdmap van de taal genoemd, identificeert de taal van de inhoud in de taalkopie. */content/dam/it* is bijvoorbeeld de Italiaanse taalhoofdmap voor de Italiaanse taalkopie. De exemplaren van de taal moeten [correct-gevormde taalwortel](preparing-assets-for-translation.md#creating-a-language-root) gebruiken zodat de correcte taal wordt gericht wanneer de vertalingen van bronactiva worden uitgevoerd.

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

1. Maak de hoofdtaalhoofdmap van uw primaire taal. De hoofdmap van de Engelse taalkopie in de hiërarchie van de voorbeeldmap is bijvoorbeeld `/content/dam/en`. Zorg ervoor dat de taalwortel correct volgens de informatie in [Creërend een Wortel van de Taal](preparing-assets-for-translation.md#creating-a-language-root) wordt gevormd.

1. Voeg middelen toe aan uw primaire taal.
1. Creeer de taalwortel van elke doeltaal waarvoor u een taalexemplaar vereist.

## Een taalbasis maken {#creating-a-language-root}

Als u de hoofdmap van de taal wilt maken, maakt u een map en gebruikt u een ISO-taalcode als waarde voor de eigenschap Naam. Nadat u de hoofdtaal hebt gemaakt, kunt u op elk niveau in de hoofdmap van de taal een kopie van de taal maken.

De basispagina van de Italiaanse taalkopie van de voorbeeldhiërarchie heeft bijvoorbeeld `it` als eigenschap Name. Het bezit van de Naam wordt gebruikt als naam van de activaknoop in de bewaarplaats, en bepaalt daarom de weg van de activa. (`https://[AEM_server]:[port]/assets.html/content/dam/it/*`)

1. Klik of tik op de assetconsole op **[!UICONTROL Create]** en kies **[!UICONTROL Folder]** in het menu.

   ![chlimage_1-120](assets/chlimage_1-120.png)

1. Typ in het veld Naam de landcode in de notatie `<language-code>`.

   ![chlimage_1-121](assets/chlimage_1-121.png)

1. Klik of tik **[!UICONTROL Create]**. De taalwortel wordt gecreeerd in de console van Activa.

## Taalwortels {#viewing-language-roots} weergeven

De interface met geoptimaliseerde aanrakingen biedt een paneel Referenties met een lijst met taalwortels die in AEM Assets zijn gemaakt.

1. Selecteer in de middelenconsole de primaire taal waarvoor u taalkopieën wilt maken.
1. Klik of tik op het pictogram GlobalNav en kies **[!UICONTROL References]** om het paneel Referentie te openen.

   ![chlimage_1-122](assets/chlimage_1-122.png)

1. Klik of tik op **[!UICONTROL Language Copies]** in het venster Referenties. In het deelvenster Taalkopieën worden de taalkopieën van de elementen weergegeven.

   ![chlimage_1-123](assets/chlimage_1-123.png)

