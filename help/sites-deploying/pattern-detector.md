---
title: De complexiteit van upgrades beoordelen met de patroondetector
seo-title: De complexiteit van upgrades beoordelen met de patroondetector
description: Leer hoe u de patroondetector gebruikt om de complexiteit van de upgrade te beoordelen.
seo-description: Leer hoe u de patroondetector gebruikt om de complexiteit van de upgrade te beoordelen.
uuid: 4fcfdb16-3183-442a-aa5b-5f9c4fb7e091
contentOwner: sarchiz
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: upgrading
content-type: reference
discoiquuid: 8cdcfd3a-7003-4cce-97f4-da7a1a887d1b
feature: Bijwerken
exl-id: 375e202c-21d4-41f1-a2d5-592ac95c8f25
translation-type: tm+mt
source-git-commit: bd94d3949f0117aa3e1c9f0e84f7293a5d6b03b4
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 1%

---

# De complexiteit van upgrades beoordelen met de patroondetector{#assessing-the-upgrade-complexity-with-the-pattern-detector}

## Overzicht {#overview}

Met deze functie kunt u bestaande AEM controleren op hun upgradbaarheid door patronen in gebruik te detecteren die:

1. Overtreed bepaalde regels en wordt uitgevoerd op gebieden die door de upgrade worden beïnvloed of overschreven
1. Gebruik een AEM 6.x-functie of een API die niet achterwaarts compatibel is met AEM 6.4 en die na de upgrade mogelijk kan worden onderbroken.

Dit zou kunnen dienen als een beoordeling van de ontwikkelingsinspanningen die gepaard gaan met de opwaardering tot AEM 6.4.

## Instellen {#how-to-set-up}

De patroondetector wordt afzonderlijk vrijgegeven als een [één pakket](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq650/compatpack/pd-all-aem65) die werkt aan een bron AEM versies van 6.1 tot 6.5 die AEM 6.5 bevorderen. Het kan worden geïnstalleerd gebruikend [de Manager van het Pakket](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/package-manager.html).

## Het gebruik {#how-to-use}

>[!NOTE]
>
>Patroondetector kan worden uitgevoerd in elke omgeving, inclusief lokale ontwikkelingsinstanties. Om:
>
>* de detectiesnelheid verhogen
>* vertraging van bedrijfskritieke instanties vermijden\
   >tegelijkertijd wordt aangeraden het **op testomgevingen** uit te voeren die zo dicht mogelijk bij productieomgevingen liggen op het gebied van gebruikerstoepassingen, inhoud en configuraties.


U kunt verschillende methoden gebruiken om de uitvoer van de patroondetector te controleren:

* **Via de Felix Inventory Console:**

1. Ga naar de AEM webconsole door naar: https://<i></i>serveradres:serverpoort/systeem/console/configMgr
1. Selecteer **Status - Patroondetector** zoals in de onderstaande afbeelding wordt getoond:

   ![screenshot-2018-2-5pattern-detector](assets/screenshot-2018-2-5pattern-detector.png)

* **Via een reactieve, op tekst gebaseerde of reguliere JSON-interface**

* **Via een reactieve JSON-lijninterface**, wordt in elke regel een afzonderlijk JSON-document gegenereerd.

Beide methoden worden hieronder beschreven:

## Reactive Interface {#reactive-interface}

De reactieve interface maakt het mogelijk het rapport van de schending te verwerken zodra een vermoeden wordt vastgesteld.

De uitvoer is momenteel beschikbaar onder twee URL&#39;s:

1. Onbewerkte tekstinterface
1. JSON-interface

## Afhandeling van de interface Onbewerkte tekst {#handling-the-plain-text-interface}

De informatie in de uitvoer wordt opgemaakt als een reeks gebeurtenisitems. Er zijn twee kanalen - één voor het publiceren van schendingen en de tweede voor het publiceren van de huidige vooruitgang.

U kunt ze verkrijgen met de volgende opdrachten:

```shell
curl -Nsu 'admin:admin' http://localhost:4502/system/console/status-pattern-detector.txt | tee patterns-report.log | grep SUSPICION
```

De uitvoer ziet er als volgt uit:

```
2018-02-13T14:18:32.071+01:00 [SUSPICION] The pattern=ECU/extraneous.content.usage was found by detector=ContentAccessDetector with id=a07fd94318f12312c165e06d890cbd3c2c8b8dad0c030663db8b4c800dd7c33f message="Cross-boundary overlay of internal marked path /libs/granite/operations/components/commons/commons.jsp/jcr:content referenced at /apps/granite/operations/components/commons/commons.jsp/jcr:content with properties redefined: jcr:lastModifiedBy, jcr:mimeType, jcr:data, jcr:lastModified, jcr:uuid". More info at=https://www.adobe.com/go/aem6_EC
```

De voortgang kan worden gefilterd met de opdracht `grep`:

```shell
curl -Nsu 'admin:admin' http://localhost:4502/system/console/status-pattern-detector.txt | tee patterns-report.log | grep PROGRESS
```

Dit resulteert in de volgende uitvoer:

```
2018-02-13T14:19:26.909+01:00 [PROGRESS] emitted=127731/52 MB patterns (from=6.4), analysed=45780/16 MB items, found=0 suspicions so far in period=PT5.005S (throughput=34667 items/sec)
2018-02-13T14:19:31.904+01:00 [PROGRESS] emitted=127731/52 MB patterns (from=6.4), analysed=106050/39 MB items, found=0 suspicions so far in period=PT10S (throughput=23378 items/sec)
2018-02-13T14:19:35.685+01:00 [PROGRESS] Finished in period=PT13.782
```

## De JSON-interface {#handling-the-json-interface} verwerken

Op dezelfde manier kan JSON worden verwerkt met het [jq-gereedschap](https://stedolan.github.io/jq/) zodra het is gepubliceerd.

```shell
curl -Nsu 'admin:admin' http://localhost:4502/system/console/status-pattern-detector.json | tee patterns-report.json | jq --unbuffered -C 'select(.suspicion == true)'
```

Met de uitvoer:

```
{
  "timestamp": "2018-02-13T14:20:18.894+01:00",
  "suspicion": true,
  "pattern": {
    "code": "ECU",
    "type": "extraneous.content.usage",
    "detective": "ContentAccessDetector",
    "moreInfo": "https://www.adobe.com/go/aem6_ECU"
  },
  "item": {
    "id": "a07fd94318f12312c165e06d890cbd3c2c8b8dad0c030663db8b4c800dd7c33f",
    "message": "Cross-boundary overlay of internal marked path /libs/granite/operations/components/commons/commons.jsp/jcr:content referenced at /apps/granite/operations/components/commons/commons.jsp/jcr:content with properties redefined: jcr:lastModifiedBy, jcr:mimeType, jcr:data, jcr:lastModified, jcr:uuid"
  }
}
```

De voortgang wordt om de 5 seconden gemeld en kan worden opgehaald door andere berichten uit te sluiten dan die welke als verdenking zijn gemarkeerd:

```shell
curl -Nsu 'admin:admin' http://localhost:4502/system/console/status-pattern-detector.json | tee patterns-report.json | jq --unbuffered -C 'select(.suspicion == false)'
```

Met de uitvoer:

```
{
  "suspicion": false,
  "timestamp": "2018-02-13T14:21:17.279+01:00",
  "type": "PROGRESS",
  "database": {
    "patternsEmitted": 127731,
    "patternsEmittedSize": "52 MB",
    "databasesEmitted": [
      "6.4"
    ]
  },
  "state": {
    "itemsAnalysed": 57209,
    "itemsAnalysedSize": "26 MB",
    "suspicionsFound": 0
  },
  "progress": {
    "elapsedTime": "PT5.003S",
    "elapsedTimeMilliseconds": 5003,
    "itemsPerSecond": 36965
  }
}
{
  "suspicion": false,
  "timestamp": "2018-02-13T14:21:22.276+01:00",
  "type": "PROGRESS",
  "database": {
    "patternsEmitted": 127731,
    "patternsEmittedSize": "52 MB",
    "databasesEmitted": [
      "6.4"
    ]
  },
  "state": {
    "itemsAnalysed": 113194,
    "itemsAnalysedSize": "46 MB",
    "suspicionsFound": 0
  },
  "progress": {
    "elapsedTime": "PT10S",
    "elapsedTimeMilliseconds": 10000,
    "itemsPerSecond": 24092
  }
}
{
  "suspicion": false,
  "timestamp": "2018-02-13T14:21:25.762+01:00",
  "type": "FINISHED",
  "database": {
    "patternsEmitted": 127731,
    "patternsEmittedSize": "52 MB",
    "databasesEmitted": [
      "6.4"
    ]
  },
  "state": {
    "itemsAnalysed": 140744,
    "itemsAnalysedSize": "63 MB",
    "suspicionsFound": 1
  },
  "progress": {
    "elapsedTime": "PT13.486S",
    "elapsedTimeMilliseconds": 13486,
    "itemsPerSecond": 19907
  }
}
{
  "suspicion": false,
  "type": "SUMMARY",
  "suspicionsFound": 1,
  "totalTime": "PT13.487S"
}
```

>[!NOTE]
>
>De geadviseerde benadering is de volledige output van krulling in het dossier te bewaren en dan het via `jq` of `grep` te verwerken om informatietype te filtreren.

## Detectiebereik {#scope}

Met de huidige patroondetector kunt u controleren:

* OSGi bundelt uitvoer en invoer wanverhouding
* De het verkopen middeltypes en supertypes (met onderzoek-weg inhoudsoverlays) gebruiken
* definities van eiken-indexen (compatibiliteit)
* VLT-pakketten (overmatig gebruik)
* rep:Compatibiliteit van gebruikersknooppunten (in de context van OAuth-configuratie)
