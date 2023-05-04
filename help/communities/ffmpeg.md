---
title: MPEG voor Gemeenschappen
seo-title: FFmpeg for Communities
description: Mpeg for Communities installeren en configureren
seo-description: How to install and configure FFmpeg for Communities
uuid: ef2f821c-70e9-4889-a8d7-a93b10a1d428
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 739ec991-552b-42cd-85cd-984d1c9fe8fd
role: Admin
exl-id: 9ed54ee3-3509-4a43-a710-90f4543ccaf3
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 0%

---

# MPEG voor Gemeenschappen {#ffmpeg-for-communities}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Overzicht {#overview}

mpeg is een oplossing voor het converteren en streamen van audio en video en wordt, indien geïnstalleerd, gebruikt voor de juiste transcodering van [video-elementen](../../help/sites-authoring/default-components-foundation.md#video) en voor de activering van de AEM-gemeenschappen.

mpeg wordt gebruikt in de auteursomgeving om meta-gegevens voor geupload enablement middelen te verkrijgen evenals een duimnagel te produceren om te tonen wanneer het vermelden van het enablement middel.

## Mpeg installeren {#installing-ffmpeg}

Fmpeg moet worden geïnstalleerd op de server(s) die als host fungeert voor de AEM *auteur* instantie(s).

1. Ga naar [https://www.ffmpeg.org](https://www.ffmpeg.org/)
1. Download de nieuwste versie van MPEG voor uw specifieke omgeving (Macintosh, Windows of Linux)

   * Het is belangrijk om MPEG up-to-date te houden wegens veiligheidskwetsbaarheden in oudere versies

1. Installeer de MPEG volgens de instructies voor het besturingssysteem.

1. Zorg ervoor dat het uitvoerbare bestand van de MPEG is ingesteld in het systeempad.

   U moet Mpeg vanuit elke map in uw systeem kunnen uitvoeren.

   * bijvoorbeeld: `ffmpeg -version`

## MPEG Transcoding Service configureren {#configure-ffmpeg-transcoding-service}

Wanneer MPEG wordt geïnstalleerd, worden standaard meerdere uitvoeringen geconfigureerd (transcoderingen) volgens de definitie van de DAM-werkstroom voor bijwerken.

Aangezien de transcoderingen CPU-intensief zijn, wordt aangeraden de lijst met doeluitvoeringen te wijzigen. In de meeste gevallen is transcodering niet nodig.

U kunt als volgt de DAM Update Asset-workflow wijzigen en in dit voorbeeld de transcodering uitschakelen:

* Aanmelden bij de instantie van de auteur met beheerdersrechten
* Vanuit globale navigatie: **[!UICONTROL Tools > Workflow > Models]**
* Zoeken **[!UICONTROL DAM Update Asset]**
* Dubbelklik om de workflow voor bewerken te openen in de klassieke gebruikersinterface

   Resulterende locatie: [http://localhost:4502/cf#/etc/workflow/models/dam/update_asset.html](http://localhost:4502/cf#/etc/workflow/models/dam/update_asset.html)

* Dubbelklik op de knop **[!UICONTROL FFmpeg transcoding]** stap voor toegang tot het dialoogvenster Step Properties
* Onder de **[!UICONTROL Process]** tab:

   * **[!UICONTROL Arugments]**: Wis alle ingangen om transcoderende Standaardwaarden onbruikbaar te maken: `profile:firefoxhq,profile:hq,profile:flv,profile:iehq`

![chlimage_1-372](assets/chlimage_1-372.png)

* Selecteren **[!UICONTROL OK]** om de `Step Properties` dialoogvenster

* Selecteren **[!UICONTROL Save]** om de `DAM Update Asset` werkstroom

   (linkerbovenhoek)
