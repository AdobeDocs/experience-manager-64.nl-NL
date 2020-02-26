---
title: Overstappen van ContentSync naar SmartSync
seo-title: Overstappen van ContentSync naar SmartSync
description: Volg deze pagina voor meer informatie over de functie SmartSync en over de overgang van ContentSync naar SmartSync.
seo-description: Volg deze pagina voor meer informatie over de functie SmartSync en over de overgang van ContentSync naar SmartSync.
page-status-flag: never-activated
uuid: f2097a23-f21b-45e0-8ce2-7faa3cf0ed86
contentOwner: jsyal
discoiquuid: 4e502b86-bdf5-44eb-8e04-ba8062e12fa0
translation-type: tm+mt
source-git-commit: cdec5b3c57ce1c80c0ed6b5cb7650b52cf9bc340

---


# Overstappen van ContentSync naar SmartSync{#transitioning-from-contentsync-to-smartsync}

Deze sectie verstrekt een overzicht aan eigenschap SmartSync en hoe het serverlading/opslag en netwerkverkeer minimaliseert om kosten te drukken.

## Overzicht {#overview}

SmartSync is het meest recente mechanisme dat wordt gebruikt door AEM-schermen. Het dient als vervanging van de huidige methode die wordt gebruikt om offlinekanalen in de cache op te slaan en aan de speler te leveren.

Deze wordt zowel op de server als op de client uitgevoerd.

**Aan serverzijde**:

* De inhoud van de kanalen, inclusief elementen, wordt in de cache opgeslagen in */var/contentsync*.
* Cache wordt aan de spelers blootgesteld via een manifest dat de beschikbare inhoud voor een vertoning beschrijft.

**Aan de clientzijde**:

* De speler werkt zijn inhoud bij die op hierboven geproduceerd manifest wordt gebaseerd.

### Voordelen van het gebruik van SmartSync {#benefits-of-using-smartsync}

De functie SmartSync biedt een aantal voordelen voor uw AEM Screens-project. Het staat

* Dramatische vermindering van het netwerkverkeer en de vereisten van de serveropslag
* De speler downloadt intelligent activa slechts als het middel ontbreekt of verandert
* Optimalisatie van server- en clientopslag

>[!NOTE]
>
>Adobe raadt u ten zeerste aan SmartSync te gebruiken voor AEM-schermprojecten.

## Migreren van ContentSync naar SmartSync {#migrating-from-contentsync-to-smartsync}

>[!NOTE]
>
>Als u al AEM 6.3 Feature Pack 5 en AEM 6.4 Feature Pack 3 hebt geïnstalleerd, kunt u SmartSync voor activa inschakelen om het gebruik van schijfruimte te verbeteren. Als u SmartSync wilt inschakelen, volgt u de onderstaande sectie voor de overgang van ContentSync naar SmartSync en schakelt u SmartSync dus in.
>
>SmartSync is beschikbaar voor schermPlayer met ondersteunde servers AEM 6.4.3 FP3. Raadpleeg de [AEM Screens Player Downloads](https://download.macromedia.com/screens/) om de nieuwste speler te downloaden.

Voer de onderstaande stappen uit om van ContentSync over te schakelen op SmartSync als u het nieuwste Feature Pack en Players (AEM 6.4 Feature Pack 3) niet hebt geïnstalleerd:

1. Voor het migreren van ContentSync naar SmartSync moet de ContentSync-cache worden gewist voordat SmartSync wordt geactiveerd.

   Navigeer naar de console ContentSync van uw instantie gebruikend de verbinding ***http://localhost:4502/libs/cq/contentsync/content/console.html*** en klik **Duidelijke Geheime voorgeheugen**, zoals aangetoond in het hieronder cijfer:

   ![clear_contesync_cache](assets/clear_contesync_cache.png)

   >[!CAUTION]
   >
   >Alle inhoudcache moet worden gewist voordat u SmartSync voor het eerst kunt gebruiken.

1. Ga naar **Adobe Experience Manager Web Console Configuration **via AEM instance —> hammer icon —> **Operations** —> **Web Console**.

   ![screen_shot_2019-02-11at15339pm](assets/screen_shot_2019-02-11at15339pm.png)

1. **Adobe Experience Manager Webconsole Configuration **wordt geopend. Zoeken naar *services* voor offline inhoud.

   Voor het zoeken van het bezit van de Dienst **van de Inhoud van de** Schermen Off-line, druk **Command+F** voor **MAC** en **Control+F** voor **Vensters**.

   ![screen_shot_2019-02-19at22643pm](assets/screen_shot_2019-02-19at22643pm.png)

1. Klik op **Opslaan** om de eigenschap **Screens Offline Content Services* ***in te schakelen en gebruik daarom SmartSync voor AEM-schermen.
1. Nadat u SmartSync hebt ingeschakeld, navigeert u naar uw project en klikt u op Offlineinhoud **** bijwerken *(vanuit de actiebalk),* zoals in de onderstaande afbeelding wordt getoond.

   ![screen_shot_2019-02-25at102605am](assets/screen_shot_2019-02-25at102605am.png)

