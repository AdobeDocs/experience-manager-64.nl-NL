---
title: Werken met logbestanden
seo-title: Werken met logbestanden
description: Leer hoe te om AEM problemen op te lossen door met logboeken te werken.
seo-description: Leer hoe te om AEM problemen op te lossen door met logboeken te werken.
uuid: b64e0b25-5228-4c2f-9cc1-dde524134026
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: operations
content-type: reference
discoiquuid: b4c1cb82-865b-48dd-b5c0-946e6610ce8e
translation-type: tm+mt
source-git-commit: 7b39a715166eeefdf20eb22a4449068ff1ed0e42
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 2%

---


# Werken met logbestanden{#working-with-logs}

Deze sectie omvat gedetailleerde informatie over logboeken beschikbaar om u te helpen problemen oplossen.

CRX registreert gedetailleerde logboeken. Nadat u QuickStart hebt uitpakken en gestart, kunt u logbestanden op de volgende locaties vinden:

* crx-quickstart/launch/logs
* crx-quickstart/server/logs
* crx-quickstart/logs

## Het FOUTOPSPORINGSlogniveau {#activating-the-debug-log-level} activeren

Het standaardlogboekniveau is INFO, dat wil zeggen, worden de DEBUG- berichten niet geregistreerd.

Als u het niveau van het DEBUG-logbestand wilt activeren, gebruikt u de CRX-verkenner om de

```xml
/libs/sling/config/org.apache.sling.commons.log.LogManager/org.apache.sling.commons.log.level
```

eigenschap voor foutopsporing. Verlaat het logboek bij het DEBUG logboekniveau niet langer dan nodig, aangezien het veel logboeken produceert.

Een lijn in zuivert dossier begint gewoonlijk met DEBUG, en verstrekt dan het logboekniveau, de installeractie en het logboekbericht. Bijvoorbeeld:

```xml
DEBUG 3 WebApp Panel: WebApp successfully deployed
```

De logniveaus zijn als volgt:

| 0 | Fatale fout | De handeling is mislukt en het installatieprogramma kan niet doorgaan. |
|---|---|---|
| 1 | Fout | De handeling is mislukt. De installatie gaat door, maar een deel van CRX is niet correct geïnstalleerd en werkt niet. |
| 2 | Waarschuwing | De actie is geslaagd maar heeft problemen ondervonden. CRX werkt mogelijk niet correct. |
| 3 | Informatie | De actie is geslaagd. |

## Uitgebreide optie gebruikt voor probleemoplossing {#verbose-option-used-for-troubleshooting}

Wanneer u CRX start, kunt u de optie -v (verbose) toevoegen aan de opdrachtregel zoals in: &quot;

` java -jar crx-<*version*>-<*edition*>.jar -v`

Gebruik de uitgebreide optie voor het oplossen van problemen aangezien deze optie sommige van de uitvoer van het snelstartlogboek op de console toont.
