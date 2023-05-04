---
title: Middelen voorbereiden voor vertaling
description: Maak hoofdmappen voor talen om het vertalen van meertalige middelen voor te bereiden.
contentOwner: AG
feature: Projects,Translation
role: User,Admin
exl-id: cc6c4f9e-8e22-4622-8b24-230ae258351c
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 2%

---

# Middelen voorbereiden voor vertaling {#preparing-assets-for-translation}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Meertalige elementen zijn elementen met binaire getallen, metagegevens en tags in meerdere talen. Over het algemeen bestaan binaire bestanden, metagegevens en tags voor elementen in één taal, die vervolgens naar andere talen worden vertaald voor gebruik in meertalige projecten.

In Adobe Experience Manager Assets worden meertalige middelen opgenomen in mappen, waarbij elke map de middelen in een andere taal bevat.

Elke taalmap wordt een taalkopie genoemd. De hoofdmap van een taalkopie, de hoofdmap van de taal genoemd, identificeert de taal van de inhoud in de taalkopie. Bijvoorbeeld: */content/dam/it* is de Italiaanse taalbasis voor de Italiaanse taalkopie. Taalkopieën moeten een [correct geconfigureerde taalhoofdmap](preparing-assets-for-translation.md#creating-a-language-root) zodat de juiste taal wordt gebruikt wanneer vertalingen van bronelementen worden uitgevoerd.

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

1. Maak de hoofdtaalhoofdmap van uw primaire taal. De hoofdmap van de kopie van de Engelse taal in de voorbeeldmaphiërarchie is bijvoorbeeld `/content/dam/en`. Zorg ervoor dat de taalwortel correct volgens de informatie in wordt gevormd [Een hoofdmap voor talen maken](preparing-assets-for-translation.md#creating-a-language-root).

1. Voeg middelen toe aan uw primaire taal.
1. Creeer de taalwortel van elke doeltaal waarvoor u een taalexemplaar vereist.

## Een hoofdmap voor talen maken {#creating-a-language-root}

Als u de hoofdmap van de taal wilt maken, maakt u een map en gebruikt u een ISO-taalcode als waarde voor de eigenschap Naam. Nadat u de hoofdtaal hebt gemaakt, kunt u op elk niveau in de hoofdmap van de taal een kopie van de taal maken.

De hoofdpagina van de Italiaanse taalkopie van de voorbeeldhiërarchie heeft bijvoorbeeld `it` als de eigenschap Name. Het bezit van de Naam wordt gebruikt als naam van de activaknoop in de bewaarplaats, en bepaalt daarom de weg van de activa. (`https://[AEM_server]:[port]/assets.html/content/dam/it/*`)

1. Klik of tik op de assetconsole op **[!UICONTROL Create]** en kies **[!UICONTROL Folder]** in het menu.

   ![chlimage_1-120](assets/chlimage_1-120.png)

1. Typ in het veld Naam de landcode in de notatie `<language-code>`.

   ![chlimage_1-121](assets/chlimage_1-121.png)

1. Klikken of tikken **[!UICONTROL Create]**. De taalwortel wordt gecreeerd in de console van Activa.

## Taalwortels weergeven {#viewing-language-roots}

De interface die is geoptimaliseerd voor aanrakingen bevat een paneel Referenties met een lijst met taalbasissen die zijn gemaakt in [!DNL Experience Manager] Elementen.

1. Selecteer in de middelenconsole de primaire taal waarvoor u taalkopieën wilt maken.
1. Klik of tik op het GlobalNav-pictogram en kies **[!UICONTROL References]** om het paneel Referentie te openen.

   ![chlimage_1-122](assets/chlimage_1-122.png)

1. Klik of tik in het venster Referenties op **[!UICONTROL Language Copies]**. In het deelvenster Taalkopieën worden de taalkopieën van de elementen weergegeven.

   ![chlimage_1-123](assets/chlimage_1-123.png)
