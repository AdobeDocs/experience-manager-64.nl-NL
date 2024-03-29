---
title: De testcase definiëren
seo-title: Defining your Test Cases
description: Uw testgevallen moeten gebaseerd zijn op de gebruiksgevallen en de gedetailleerde specificaties van de eisen
seo-description: Your test cases should be based upon the use cases and the detailed requirements specification
uuid: 82dff825-da58-49a2-bf35-f5bb905e523d
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: testing
content-type: reference
discoiquuid: 87a1f27a-765e-4882-9c06-5909e1610e1d
exl-id: ad529be3-9d31-492f-943f-ef3e99e13586
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 0%

---

# De testcase definiëren{#defining-your-test-cases}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Uw testgevallen moeten gebaseerd zijn op:

**Gevallen gebruiken**

* Deze definiëren de vereiste functionaliteit in termen van de interactie tussen de actoren (rollen die bepaalde handelingen initiëren) en het systeem.
* De gebruiksscenario&#39;s moeten door de klant worden gedefinieerd.

**Gedetailleerde specificaties voor vereisten**

* Alle functionele en prestatie-eisen moeten worden getest.

De tests moeten duidelijk omschrijven:

* vereisten; deze kunnen betrekking hebben op specifieke systemen , configuraties of testervaring .
* te volgen stappen; op een passend niveau van gedetailleerdheid.
* Verwachte resultaten.
* Duidelijke criteria voor slagen of zakken.

Het vooruitzicht om testgevallen te automatiseren is duidelijk aantrekkelijk, aangezien het herhalende taken kan elimineren.

## Handmatige en geautomatiseerde tests {#manual-versus-automated-tests}

Het automatiseren van testgevallen is echter een belangrijke investering, dus moeten bepaalde aspecten in overweging worden genomen:

* Vereis tijd, inspanning en ervaring aan opstelling en vorm.
* Als browser wordt gebaseerd, is er een verhoogd risico op problemen wanneer browser updates worden geïnstalleerd; meer tijd nodig hebben om te corrigeren.
* Alleen echt haalbaar voor grote projecten.
* Goed als er meerdere releases worden gegenereerd voor tests of in het langetermijnreleaseplan.

## Specifieke aspecten testen {#testing-specific-aspects}

Bij het testen AEM zijn enkele specifieke details van bijzonder belang:

Auteur- en publicatie-omgevingen

Hoewel, [Omgevingen](/help/sites-developing/the-basics.md#environments) er moet worden gewezen op een doorslaggevende factor van AEM met betrekking tot tests .

U moet AEM als twee toepassingen beschouwen:

* de **Auteur** omgeving Met deze instantie kunnen auteurs inhoud invoeren en publiceren.
Dit heeft een kleine (er), voorspelbare reeks gebruikers, voor wie specifieke functionaliteit en prestaties cruciaal zijn.
* de **Publiceren** omgeving Deze instantie presenteert de website in de gepubliceerde vorm voor toegang door bezoekers.
Dit heeft gewoonlijk een grotere reeks gebruikers, waar het volume van verkeer niet altijd 100% voorspelbaar is. Prestaties zijn nog steeds van cruciaal belang - bij het beantwoorden van verzoeken. Er moet ook rekening worden gehouden met caching en taakverdeling.

Alhoewel dezelfde software als dusdanig:

* verschillende doeleinden dienen
* verschillende eisen hebben met betrekking tot functionaliteit en prestaties
* zijn verschillend gevormd
* afzonderlijk worden afgebeeld
* zullen elk hun eigen reeks goedkeuringstests hebben

Met andere woorden, zij moeten afzonderlijk en met verschillende testgevallen worden getest.

**Personalisatie**

Wanneer het testen van verpersoonlijking elk individueel gebruiksgeval zou moeten worden herhaald gebruikend veelvoudige gebruikersrekeningen om gedrag te bewijzen.

Het cachegeheugen moet ook op correct gedrag worden gecontroleerd.

**De verzender**

De meeste projecten zullen Dispatcher voor caching en lading het in evenwicht brengen installeren.

Testen is moeilijk (caching vindt plaats op verschillende niveaus en op verschillende locaties) en moet gebeuren op basis van een zwarte doos. De belangrijkste aspecten waarop u wilt testen zijn:

* **Nauwkeurigheid**; zorgt ervoor dat de websitebezoeker de inhoud kan bijwerken.
* **Continuïteit**; zorgt u ervoor dat de website beschikbaar blijft wanneer één server wordt afgesloten.
* **Clusters** Clusters worden gebruikt voor:
   * **Failover**
Als één server uitvalt, nemen andere servers in de cluster de verwerking over.
   * **Prestaties**
Het in evenwicht brengen van de lading met volledige failover verhoogt de prestaties van een cluster.

Wanneer gebruikt voor een klantenproject moet de cluster worden getest om correcte verrichting van de configuratie te bevestigen.

## Software van derden testen {#testing-third-party-software}

Eventuele software van derden die aan AEM is gekoppeld, wordt vermeld in de gedetailleerde specificaties voor de vereisten.

Eventuele vereiste tests (afhankelijk van het vastgestelde bereik) moeten worden geanalyseerd en er moet een schone test worden uitgevoerd.
