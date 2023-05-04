---
title: Codevalkuilen
seo-title: Code pitfalls
description: Gemeenschappelijke coderingsvalkuilen die worden vermeden bij het ontwikkelen voor AEM
seo-description: Common coding pitfalls to avoid when developing for AEM
uuid: e7413bdc-4889-45ff-bdcb-b0893d33a3b7
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: best-practices
discoiquuid: 01362026-a696-4a5d-94e9-ea784eaa6e4b
exl-id: f39910cf-1875-43fc-bfb5-259b9d8f135d
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 0%

---

# Codevalkuilen{#code-pitfalls}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Bindingen in Java-code voorkomen {#avoid-sling-bindings-in-java-code}

Het verkopen Bindingen zijn een ongepaste manier om tot de dienst in 90% van gevallen toegang te krijgen. Gebruik in plaats daarvan *@Reference* of *@Injecteren* annotaties.

## Geen thread.interrupt in Java-code {#avoid-thread-interrupt-in-java-code}

*Thread.interrupt* is gevaarlijk omdat het dossiers, met inbegrip van Lucene- dossiers en blijvende geheim voorgeheugendossiers, wanneer geroepen op het verkeerde ogenblik kan sluiten.

## Gebruik geen Java-synchronisatie met ReadWriteLocks {#avoid-mixing-java-synchronization-with-readwritelocks}

Dit kan tot een rassenvoorwaarde leiden waarin de code uiteindelijk zal blokkeren.
