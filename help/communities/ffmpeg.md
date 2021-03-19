---
title: MPEG voor Gemeenschappen
seo-title: MPEG voor Gemeenschappen
description: Mpeg for Communities installeren en configureren
seo-description: Mpeg for Communities installeren en configureren
uuid: ef2f821c-70e9-4889-a8d7-a93b10a1d428
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 739ec991-552b-42cd-85cd-984d1c9fe8fd
role: Beheerder
translation-type: tm+mt
source-git-commit: 75312539136bb53cf1db1de03fc0f9a1dca49791
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 0%

---


# mpeg voor Gemeenschappen {#ffmpeg-for-communities}

## Overzicht {#overview}

mpeg is een oplossing voor het converteren en streamen van audio en video en wordt, indien geïnstalleerd, gebruikt voor de juiste transcodering van [video-elementen](../../help/sites-authoring/default-components-foundation.md#video) en voor de functie voor activering van AEM-gemeenschappen.

mpeg wordt gebruikt in de auteursomgeving om meta-gegevens voor geupload enablement middelen te verkrijgen evenals een duimnagel te produceren om te tonen wanneer het vermelden van het enablement middel.

## Mpeg {#installing-ffmpeg} installeren

MPEG moet worden geïnstalleerd op de server(s) die als host fungeert voor de AEM *auteur*-instantie(s).

1. Ga naar [https://www.ffmpeg.org](https://www.ffmpeg.org/)
1. Download de nieuwste versie van MPEG voor uw specifieke omgeving (Macintosh, Windows of Linux)

   * Het is belangrijk om MPEG up-to-date te houden wegens veiligheidskwetsbaarheden in oudere versies

1. Installeer de MPEG volgens de instructies voor het besturingssysteem.

1. Zorg ervoor dat het uitvoerbare bestand van de MPEG is ingesteld in het systeempad.

   U moet Mpeg vanuit elke map in uw systeem kunnen uitvoeren.

   * bijvoorbeeld `ffmpeg -version`

## MPEG Transcoding Service {#configure-ffmpeg-transcoding-service} configureren

Wanneer MPEG wordt geïnstalleerd, worden standaard meerdere uitvoeringen geconfigureerd (transcoderingen) volgens de definitie van de DAM-werkstroom voor bijwerken.

Aangezien de transcoderingen CPU-intensief zijn, wordt aangeraden de lijst met doeluitvoeringen te wijzigen. In de meeste gevallen is transcodering niet nodig.

U kunt als volgt de DAM Update Asset-workflow wijzigen en in dit voorbeeld de transcodering uitschakelen:

* Aanmelden bij de instantie van de auteur met beheerdersrechten
* Vanuit globale navigatie: **[!UICONTROL Tools > Workflow > Models]**
* **[!UICONTROL DAM Update Asset]** zoeken
* Dubbelklik om de workflow voor bewerken te openen in de klassieke gebruikersinterface

   Resulterende locatie: [http://localhost:4502/cf#/etc/workflow/models/dam/update_asset.html](http://localhost:4502/cf#/etc/workflow/models/dam/update_asset.html)

* Dubbelklik op de stap **[!UICONTROL FFmpeg transcoding]** om het dialoogvenster Step Properties te openen
* Onder het tabblad **[!UICONTROL Process]**:

   * **[!UICONTROL Arugments]**: Wis alle ingangen om transcoderende Standaardwaarden onbruikbaar te maken:  `profile:firefoxhq,profile:hq,profile:flv,profile:iehq`

![chlimage_1-372](assets/chlimage_1-372.png)

* Selecteer **[!UICONTROL OK]** om het dialoogvenster `Step Properties` te sluiten

* Selecteer **[!UICONTROL Save]** om de `DAM Update Asset`-workflow op te slaan

   (linkerbovenhoek)

