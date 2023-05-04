---
title: Grondbeginselen van Tally
seo-title: Tally Essentials
description: Overzicht van de klasse Tally
seo-description: Tally class overview
uuid: c369c6a1-9ced-4b5c-af43-8c03236eaa52
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 9941ba90-3d40-4c90-bca8-5db49603cbfa
exl-id: f04ec253-08b8-4ee2-9873-4a51549daeba
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 0%

---

# Grondbeginselen van Tally {#tally-essentials}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Tally is een abstracte klasse die een standaardmethode verstrekt om terugkoppelen van leden te verzamelen over hoe zij specifieke producten en de diensten waarderen. Anonieme feedback wordt niet ondersteund. De bezoeker van de site moet zich registreren en aanmelden om deel te nemen en zich aan te melden om zijn feedback te wijzigen. De verplichting om zich aan te melden vergemakkelijkt de matiging en verhoogt de waarde van de feedback door meerdere posten te voorkomen.

Een aangepaste telcomponent kan worden gecreeerd door de abstracte tellingsklasse uit te breiden.

[Vergelijken](essentials-liking.md) is een uitvoering van de overeenkomst die een eenvoudige vorm is om een positief oordeel uit te spreken.

[Stemming](essentials-voting.md) is een uitvoering van een overeenkomst die een eenvoudige vorm van positief of negatief advies is.

[Classificatie](rating-basics.md) is een uitvoering van tally die een sterrenstelsel gebruikt om een reeks meningen van positief tot negatief uit te drukken.

Vanaf AEM 6.1 *opiniepeiling* is niet meer beschikbaar.

[Revisies](reviews-basics.md) is een SCF-component die een hybride van [opmerkingen](essentials-comments.md) en [beoordeling](rating-basics.md).

## Essentiële elementen voor client-kant {#essentials-for-client-side}

* [Aanpassingen aan de clientzijde](client-customize.md)

## Essentiële elementen voor server-side {#essentials-for-server-side}

* [Tally API&#39;s](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/tally/client/api/package-summary.html)

* [Eindpunten tellen](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/tally/client/endpoints/package-summary.html)

* [Aanpassingen op de server](server-customize.md)

### Toegang tot Geposte Tallies (UGC) {#accessing-posted-tallies-ugc}

UGC moet worden gemoderniseerd met behulp van een van de standaardmethoden voor gematigdheid.\
Zie [Door gebruiker gegenereerde inhoud modereren](moderate-ugc.md).

Met ingang van AEM 6.1. [gemeenschappelijk archief](working-with-srp.md) voor UGC omvat programmatische toegang tot UGC ongeacht de gekozen opslagoptie (zoals ASRP, MSRP of JSRP).

**De locatie en de indeling van de UGC in de opslagplaats kunnen zonder waarschuwing worden gewijzigd**.

Zie:

* [Overzicht opslagbronprovider](srp.md) - overzicht van het gebruik van introducties en opslagplaatsen
* [SRP en UGC Essentials](srp-and-ugc.md) - SRP-hulpprogrammamethoden en -voorbeelden
* [Toegang tot UGC met SRP](accessing-ugc-with-srp.md) - coderingsrichtlijnen
* [SocialUtils Refactoring](socialutils.md) - het in kaart brengen van afgekeurde nutsmethodes aan huidige SRP nutsmethodes
