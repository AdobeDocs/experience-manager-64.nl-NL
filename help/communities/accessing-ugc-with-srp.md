---
title: Toegang tot UGC met SRP
seo-title: Accessing UGC with SRP
description: Wanneer een plaats wordt gevormd om ASRP of MSRP te gebruiken, wordt daadwerkelijke UGC niet opgeslagen in AEM knoopopslag (JCR)
seo-description: When a site is configured to use ASRP or MSRP, the actual UGC is not be stored in AEM's node store (JCR)
uuid: 5f9f8c9b-4c6a-45b0-96ff-14934380eba7
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: ee786a5c-b985-4d78-9063-6c79ae5e13e6
exl-id: 3a16a771-e1c5-4ae4-9fc6-17a47064db54
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 0%

---

# Toegang tot UGC met SRP {#accessing-ugc-with-srp}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## SRP {#about-srp}

Alle AEM Communities-componenten en -functies zijn gebaseerd op de [Sociaal-componentkader (SCF)](scf.md), die de API van SocialResourceProvider aanroept om toegang te krijgen tot alle door de gebruiker gegenereerde inhoud (UGC).

Voordat een communitysite wordt gemaakt, moet u [Storage Resource Provider (SRP)](working-with-srp.md) moet worden geconfigureerd om een implementatie te selecteren die consistent is met de onderliggende [topologie](topologies.md). De implementatie SRP is gebaseerd op drie opslagopties:

1. [ASRP](asrp.md) - Adobe-opslag op aanvraag
2. [MSRP](msrp.md) - MongoDB
3. [JSRP](jsrp.md) - JCR

## Informatie over UGC-opslag {#about-ugc-storage}

Wat belangrijk is om over opslag van UGC te weten is, wanneer een plaats wordt gevormd om ASRP of MSRP te gebruiken, wordt daadwerkelijke UGC niet opgeslagen in AEM [knooppuntopslag](../../help/sites-deploying/data-store-config.md) (JCR).

Hoewel er knooppunten in JCR kunnen zijn die de UGC schaduw geven om nuttige metagegevens te verschaffen, moeten deze knooppunten niet worden verward met de werkelijke UGC.

Zie [Overzicht opslagbronprovider.](srp.md)

## Beste praktijken {#best-practice}

Wanneer het ontwikkelen van douanecomponenten, zouden de ontwikkelaars aan code onafhankelijk van de huidige gekozen topologie moeten zorgvuldig zijn, waarbij flexibiliteit behouden blijft om zich aan een nieuwe topologie in de toekomst te bewegen.

### Stel dat JCR niet beschikbaar is {#assume-jcr-not-available}

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

Verschillende SRPs kan verschillende inheemse vraagtalen hebben. Aanbevolen wordt methoden te gebruiken van de [com.adobe.cq.social.ugc.api](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/ugc/api/package-summary.html) pakket om de aangewezen vraagtaal aan te halen.

Zie voor meer informatie [Essentiële zoekopdrachten](search-implementation.md).

## Bronnen {#resources}

* [Opslag van communautaire inhoud](working-with-srp.md) - bespreekt de beschikbare keuzen SRP voor een gemeenschappelijk opslag UGC
* [Overzicht opslagbronprovider](srp.md) - overzicht van het gebruik van introducties en opslagplaatsen
* [SRP en UGC Essentials](srp-and-ugc.md) - SRP-hulpprogrammamethoden en -voorbeelden
* [Essentiële zoekopdrachten](search-implementation.md) - essentiële informatie voor het doorzoeken van UGC
* [SocialUtils Refactoring](socialutils.md) - het in kaart brengen van afgekeurde nutsmethodes aan huidige SRP nutsmethodes
