---
title: Sociale grafiek gebruiken
seo-title: Sociale grafiek gebruiken
description: Een volgende component aan een pagina toevoegen
seo-description: Een volgende component aan een pagina toevoegen
uuid: 8be6334b-e6c9-40bc-90a8-750b98419470
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: 0ce57ab1-e4c6-4c38-963d-556eef8757f2
translation-type: tm+mt
source-git-commit: 8f169bb9b015ae94b9160d3ebbbd1abf85610465
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 0%

---


# Sociale grafiek {#using-social-graph} gebruiken

## Inleiding {#introduction}

Het vermogen voor een lid van de gemeenschap om [activiteiten](activities.md) te volgen evenals te worden gevolgd wordt gevestigd door twee componenten: `Follow`en `Following`.

De `Follow`component moet met een andere middel worden geassocieerd, en deze vereniging is reeds gevestigd voor communautaire leden en eigenschappen.

De `Following`component maakt een lijst eenvoudig van de leden die of het huidige lid volgen of door het huidige lid worden gevolgd. Deze sociale grafiek van de verhoudingen tussen leden is inbegrepen in het gebruikersprofiel dat voor een [communityplaats](overview.md#communitiessites) wordt gevestigd.

## Volgende toevoegen aan een pagina {#adding-following-to-a-page}

Als u een `Following`component aan een pagina in auteurswijze wilt toevoegen, bepaal de plaats van de component `Communities / Following` en sleep het in plaats op een pagina waar de sociale grafiek zou moeten verschijnen.

Voor noodzakelijke informatie, bezoek [de Grondbeginselen van Componenten van Gemeenschappen](basics.md).

Wanneer de [vereiste client-side bibliotheken](essentials-socialgraph.md#essentials-for-client-side) worden opgenomen, wordt de `Following`-component op deze manier weergegeven:

![chlimage_1-447](assets/chlimage_1-447.png)

## Het vormen volgend {#configuring-following}

Momenteel, is het noodzakelijk om het bezit te plaatsen om te bepalen of de component `follows`verhouding, of `following`verhouding toont.

## Aanvullende informatie {#additional-information}

Meer informatie vindt u op de pagina [Social Graph Essentials](essentials-socialgraph.md) voor ontwikkelaars.
