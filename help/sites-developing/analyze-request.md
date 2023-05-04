---
title: Analyse aanvragen
seo-title: Request Analysis Script
description: Het manuscript van de verzoekanalyse wordt gemaakt om de analyse van de access.log dossiers te verlichten die een leesbaar rapport voor recentere verwerking produceren
seo-description: The request analysis script is made to ease the analysis of the access.log files producing a readable report for later processing
uuid: 24eff3c6-5748-46f3-a30c-4a3a6427ce1d
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: testing
content-type: reference
discoiquuid: 1b5e0ccf-4157-45e3-8caf-1d6739d7d9d2
exl-id: 8582bbca-c11a-4880-88ba-da22e0301dba
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 0%

---

# Analyse aanvragen{#request-analysis-script}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Downloaden {#download}

Dit script is gemaakt om de analyse van de `access.log` bestanden die een leesbaar rapport produceren voor latere verwerking.

[Bestand ophalen](assets/analyse-access.sh)

## Beschrijving {#description}

Dit script is gemaakt om de analyse van de `access.log` bestanden die een leesbaar rapport produceren voor latere verwerking.

Het produceert het algemene verzoekaantal, GET versus POST, Verzoek verdeling over tijd en meer.

De uitvoer wordt uitgedrukt in de syntaxis Markdown. Het is daarom gemakkelijker om de uitvoer om te zetten in PDF met gereedschappen zoals een pandoc of om de uitvoer weer te geven in een browser met plug-ins zoals een Markdown-viewer.

Een aangepast pad op de opdrachtregel kan worden geanalyseerd.

Maak kennis met de opmerking in het bestand die u vertelt hoe u de opmerking moet uitvoeren:

CQ analyseren `access.log` het extrapoleren van diverse informatie en het produceren van een output van de Prijsverlaging op `stdout`.

## Gebruik {#usage}

`./analyse-access.sh access.log.2013-&ast;`

u kunt aanvullende aangepaste paden opgeven die u wilt analyseren op de opdrachtregel

`/analyse-access.sh access.log.2013-&ast; /my/custom/path/1 /my/custom/path/2`

u kunt de output bewaren door eenvoudige pijpleiding

`./analyse-access.sh access.log.2013-&ast; | tee yr2013.md`
