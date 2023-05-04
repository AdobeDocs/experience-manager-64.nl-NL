---
title: Tags gebruiken
seo-title: Using Tags
description: Tags zijn een snelle en eenvoudige methode om inhoud binnen een website te classificeren
seo-description: Tags are a quick and easy method of classifying content within a website
uuid: a91f8724-fc35-4f40-b21c-bee90429765b
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: site-features
discoiquuid: d0b0e47b-e68d-407d-9d06-deca2039dede
exl-id: 846a925a-673e-4051-a673-1a9236701f0a
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '711'
ht-degree: 2%

---

# Tags gebruiken {#using-tags}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Tags zijn een snelle en eenvoudige methode om inhoud binnen een website te classificeren. Tags kunnen worden beschouwd als trefwoorden of labels die aan een pagina, element of andere inhoud kunnen worden gekoppeld, zodat zoekopdrachten naar die inhoud en verwante inhoud kunnen worden uitgevoerd.

* Zie [Tags beheren](/help/sites-administering/tags.md) voor informatie over het maken en beheren van tags en over de inhoudstags die zijn toegepast.
* Zie [Tags voor ontwikkelaars](/help/sites-developing/tags.md) voor informatie over het etiketteringskader evenals het opnemen van en het uitbreiden van markeringen in douanetoepassingen.

## Tien redenen voor het gebruik van tags {#ten-reasons-to-use-tagging}

1. Inhoud ordenen: het labelen maakt het leven voor auteurs gemakkelijker aangezien zij inhoud snel en zonder moeite kunnen organiseren .

1. Tags organiseren: terwijl tags inhoud ordenen, ordenen hiërarchische taxonomieën/naamruimten tags.

1. Georganiseerde tags toepassen: met de mogelijkheid om codes en subcodes te maken, wordt het mogelijk volledige taxonomische systemen uit te drukken, met inbegrip van termen, subtermen en hun relaties. Zo kunt u een tweede (of derde) inhoudshiërarchie maken die parallel is aan de officiële inhoudshiërarchie.

1. Gecontroleerde labeling: U kunt de codering beheren door machtigingen toe te passen op tags en/of naamruimten om het maken en de toepassing van tags te beheren.

1. Flexibele tags: Tags hebben vele namen en gezichten: tags, taxonomie termen, categorieën, labels en nog veel meer. Zij zijn flexibel in hun inhoudsmodel en in de manier waarop zij kunnen worden gebruikt; bijvoorbeeld bij het schetsen van doeldemografie, het categoriseren en classificeren van inhoud of het creëren van een secundaire inhoudshiërarchie.

1. Verbeterd zoeken: de standaardzoekcomponent in AEM bevat over het algemeen gemaakte tags en toegepaste tags waarop filters kunnen worden toegepast om de resultaten te beperken tot die welke relevant zijn.

1. SEO inschakelen: tags die zijn toegepast als pagina-eigenschappen, worden automatisch weergegeven in de tags van de pagina, zodat deze zichtbaar zijn voor zoekprogramma&#39;s.

1. Eenvoudig, geavanceerd: U kunt eenvoudig tags maken op basis van een woord en een knop. Daarna kunt u een titel, beschrijving en een onbeperkt label toevoegen om meer semantiek aan de tag toe te voegen.

1. Kernconsistentie: het coderingssysteem is een kernonderdeel van AEM en wordt door alle AEM gebruikt om inhoud te categoriseren . Verder is de API voor codering beschikbaar voor ontwikkelaars die toepassingen met codering willen maken die toegang hebben tot dezelfde taxonomieën.

1. Combineert structuur en flexibiliteit: AEM is ideaal voor het werken met gestructureerde informatie, door het nesten van pagina&#39;s en paden. Het is even krachtig wanneer het werken met ongestructureerde informatie, toe te schrijven aan de ingebouwde full-text onderzoek. Tags combineren de sterke punten van structuur en flexibiliteit.

Wanneer u de inhoudsstructuur voor een site en het metagegevensschema voor elementen ontwerpt, moet u rekening houden met de lichte en toegankelijke manier waarop u tags kunt toewijzen.

## Tags toepassen {#applying-tags}

In de auteursomgeving kunnen de auteurs markeringen toepassen door tot de pagina eigenschappen toegang te hebben en één of meerdere markeringen in te gaan in **Tags/trefwoorden** veld.

Toepassen [vooraf gedefinieerde tags](/help/sites-administering/tags.md)in de **Pagina-eigenschappen** het venster gebruiken **Tags** en **Labels selecteren** venster. Het tabblad **Standaardtags** is de standaardnaamruimte, wat betekent dat er geen `namespace-string:` als voorvoegsel is voor de taxonomie.

![chlimage_1-92](assets/chlimage_1-92.png)

### Codes publiceren {#publishing-tags}

Net als bij pagina&#39;s kunt u het volgende uitvoeren op tags en naamruimten:

**Activeren**

* Afzonderlijke tags activeren.

   Net als bij pagina&#39;s moeten nieuwe tags worden geactiveerd voordat deze beschikbaar komen in de publicatieomgeving.

>[!NOTE]
>
>Wanneer u een pagina activeert, wordt automatisch een dialoogvenster geopend waarin u niet-geactiveerde tags die bij de pagina horen, kunt activeren.

**Deactiveren**

* Deactiveer de geselecteerde labels.

## Labelwolken {#tag-clouds}

Tagwolken tonen een wolk van markeringen, of voor de huidige pagina, de volledige website, of die het vaakst betreden. Labelwolken zijn een manier om de problemen te markeren die de gebruiker interesseert (geweest). De grootte van de tekst die wordt gebruikt om de tag weer te geven, is afhankelijk van het gebruik ervan.

De [Cloud labelen](/help/sites-authoring/default-components-foundation.md#tag-cloud) wordt gebruikt om een tagwolk aan een pagina toe te voegen (groep Algemeen).

## Zoeken op tags {#searching-on-tags}

U kunt tags zoeken in zowel de auteur- als de publicatieomgeving.

### Zoekcomponent gebruiken {#using-search-component}

Een [component Zoeken](/help/sites-authoring/default-components-foundation.md#search) op een pagina biedt een zoekfunctie die tags bevat en kan worden gebruikt in zowel de auteur- als de publicatieomgeving.

![chlimage_1-93](assets/chlimage_1-93.png)
