---
title: Toegang tot UGC met SRP
seo-title: Toegang tot UGC met SRP
description: Wanneer een plaats wordt gevormd om ASRP of MSRP te gebruiken, wordt daadwerkelijke UGC niet opgeslagen in AEM knoopopslag (JCR)
seo-description: Wanneer een plaats wordt gevormd om ASRP of MSRP te gebruiken, wordt daadwerkelijke UGC niet opgeslagen in AEM knoopopslag (JCR)
uuid: 5f9f8c9b-4c6a-45b0-96ff-14934380eba7
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: ee786a5c-b985-4d78-9063-6c79ae5e13e6
exl-id: 3a16a771-e1c5-4ae4-9fc6-17a47064db54
translation-type: tm+mt
source-git-commit: bd94d3949f0117aa3e1c9f0e84f7293a5d6b03b4
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 0%

---

# Toegang tot UGC met SRP {#accessing-ugc-with-srp}

## Informatie over SRP {#about-srp}

Alle AEM Communities-componenten en -functies zijn gebaseerd op het [social component framework (SCF)](scf.md), dat de SocialResourceProvider API aanroept om toegang te krijgen tot alle door de gebruiker gegenereerde inhoud (UGC).

Alvorens een communautaire plaats wordt gecreeerd, moet [de leverancier van het opslagmiddel (SRP)](working-with-srp.md) worden gevormd om een implementatie te selecteren verenigbaar met onderliggende [topologie](topologies.md). De implementatie SRP is gebaseerd op drie opslagopties:

1. [ASRP](asrp.md) - Adobe opslag op aanvraag
2. [MSRP](msrp.md) - MongoDB
3. [JSRP](jsrp.md) - JCR

## Informatie over UGC-opslag {#about-ugc-storage}

Wat belangrijk is om over opslag van UGC te weten is, wanneer een plaats wordt gevormd om ASRP of MSRP te gebruiken, wordt daadwerkelijke UGC niet opgeslagen in AEM [nodeopslag](../../help/sites-deploying/data-store-config.md) (JCR).

Hoewel er knooppunten in JCR kunnen zijn die de UGC schaduw geven om nuttige metagegevens te verschaffen, moeten deze knooppunten niet worden verward met de werkelijke UGC.

Zie [Overzicht opslagbronleverancier.](srp.md)

## Beste praktijken {#best-practice}

Wanneer het ontwikkelen van douanecomponenten, zouden de ontwikkelaars aan code onafhankelijk van de huidige gekozen topologie moeten zorgvuldig zijn, waarbij flexibiliteit behouden blijft om zich aan een nieuwe topologie in de toekomst te bewegen.

### Stel dat JCR niet beschikbaar {#assume-jcr-not-available} is

Methoden die specifiek zijn voor het JCR moeten worden vermeden.

Te gebruiken methoden:

* Sling API (Sling Resource)
   * Ga er niet van uit dat er JCR-knooppunten zijn

* OSGi Events
   * Ga er niet van uit dat er JCR-gebeurtenissen zijn

* [Hulpprogramma&#39;s voor sociale bronnen](socialutils.md#socialresourceutilities-package)
* [SCF-hulpprogramma&#39;s](socialutils.md#scfutilities-package)

Te vermijden methoden:

* Knooppunt-API
* JCR-gebeurtenissen
* Workflowstartprogramma&#39;s (die gebruikmaken van JCR-gebeurtenissen)

### Zoekverzamelingen gebruiken {#use-search-collections}

Verschillende SRPs kan verschillende inheemse vraagtalen hebben. Het wordt aanbevolen methoden uit het pakket [com.adobe.cq.social.ugc.api](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/ugc/api/package-summary.html) te gebruiken om de juiste querytaal aan te roepen.

Zie [Essentiële elementen zoeken](search-implementation.md) voor meer informatie.

## Bronnen {#resources}

* [Community Content Storage](working-with-srp.md)  - bespreekt de beschikbare SRP-keuzes voor een UGC-gemeenschappelijk archief
* [Overzicht](srp.md)  van Storage Resource Provider - inleiding en overzicht van opslaggebruik
* [SRP en de Hoofdzaak](srp-and-ugc.md)  UGC - SRP nutsmethodes en voorbeelden
* [Hoofdzaak](search-implementation.md)  zoeken - essentiële informatie voor het zoeken naar UGC
* [SocialUtils Refactoring](socialutils.md)  - in kaart gebrachte vervangen nutsmethodes aan huidige SRP hulpprogrammamethodes
