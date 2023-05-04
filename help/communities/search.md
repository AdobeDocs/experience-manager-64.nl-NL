---
title: Zoekfunctie
seo-title: Search Feature
description: Zoeken toevoegen en configureren aan een Community-site
seo-description: Adding and configuring Search to a Communities site
uuid: ca633456-911f-447f-881e-653533125d5f
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: 3acac082-efbe-4995-b374-851cb9aaf62d
exl-id: 15d8bd59-397e-4bd3-b0a2-b6893c015798
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 0%

---

# Zoekfunctie {#search-feature}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

De zoekfunctie werkt met verschillende andere functies, zoals forums, om inhoud te kunnen zoeken.

Wanneer het toevoegen van de capaciteit aan onderzoeksposten ingegaan door communautaire leden, die als gebruiker geproduceerde inhoud (UGC) worden bedoeld, zijn er twee componenten: [ `Search`](#search-features) en [ `Search Results`](#search-results).

De pagina die de `Search Results` ondersteunt zowel het zoeken als de weergave van resultaten.

De pagina die de `Search`biedt een plaats om een zoekopdracht te starten met de resultaten die worden weergegeven op het tabblad `Search Results` pagina.

De zoekfunctie kan worden gebruikt met elke andere functie waarmee bezoekers en leden van de site inhoud kunnen bekijken.

## Zoeken {#search-features}

### Zoeken toevoegen aan een pagina {#add-search-to-a-page}

Als u een `Search` van een component aan een pagina op auteurswijze, gebruik componentenbrowser om van `Communities / Search` en sleep het naar de juiste plaats op een pagina. Gebruik van `Search` vereist een tweede pagina voor de `Search Results.`

Voor de nodige informatie gaat u naar [Grondbeginselen van Community-componenten](basics.md).

Wanneer de vereiste clientbibliotheek `cq.social.hbs.search`, wordt opgenomen, is dit hoe `Search` wordt weergegeven.

![chlimage_1-373](assets/chlimage_1-373.png)

### De toegevoegde zoekopdracht configureren {#configure-the-added-search}

Selecteer de geplaatste `Search` te openen en de component te selecteren `Configure` wordt het dialoogvenster Bewerken geopend.

![chlimage_1-374](assets/chlimage_1-374.png)

Onder de **[!UICONTROL Search Settings]** , geeft u op hoe wordt gezocht in welke paden een query wordt ingevoerd door een bezoeker.

![chlimage_1-375](assets/chlimage_1-375.png)

* **[!UICONTROL Search Paths]**
Door zoekpaden toe te voegen met de knop Item toevoegen, is de zoekopdracht naar inhoud beperkt. Als voorbeeld, om het onderzoek tot een specifiek forum te beperken, selecteer een forumcomponent die binnen een pagina wordt geplaatst:

   * `/content/community-components/en/forum/jcr:content/content/forum`

* **[!UICONTROL Result Page]**
De resultaten worden weergegeven op een aparte pagina die u in de browser hebt opgegeven om een pagina met de 
`Search Results` component.

## Zoekresultaten {#search-results}

### Zoekresultaten toevoegen aan een pagina {#add-search-results-to-a-page}

Als u een `Search Results` van een component aan een pagina op auteurswijze, gebruik componentenbrowser om van

* `Communities / Search Results`

en sleep het naar de juiste plaats op een pagina. In tegenstelling tot de zoekcomponent is geen tweede pagina nodig omdat de resultaten op dezelfde pagina worden weergegeven.

Als u Zoeken elders in de website gebruikt, wordt deze pagina geleverd met `Search Results` kan worden geconfigureerd als `Result Page` voor een of alle gevallen van `Search`.

Voor de nodige informatie gaat u naar [Grondbeginselen van Community-componenten](basics.md).

Wanneer de vereiste clientbibliotheek `cq.social.hbs.search`, wordt opgenomen, is dit hoe `Search Result` wordt weergegeven:

![chlimage_1-376](assets/chlimage_1-376.png)

### Het toegevoegde zoekresultaat configureren {#configure-the-added-search-result}

Selecteer de geplaatste `Search Results` te openen en de component te selecteren `Configure` wordt het dialoogvenster Bewerken geopend.

![chlimage_1-377](assets/chlimage_1-377.png)

Onder de **[!UICONTROL Search Result Settings]** kunt u opgeven welke paden in de zoekopdracht moeten worden opgenomen wanneer een bezoeker een query invoert.

![chlimage_1-378](assets/chlimage_1-378.png)

* **[!UICONTROL Search Results Per Page]**
Bepaal het aantal onderwerpen/posten dat per pagina wordt getoond. De standaardwaarde is 10.

* **[!UICONTROL Search Paths]**
Door zoekpaden toe te voegen met de knop Item toevoegen, is de zoekopdracht naar inhoud beperkt.

## Aanvullende informatie {#additional-information}

Meer informatie is te vinden op de [Essentiële zoekopdrachten](search-implementation.md) pagina voor ontwikkelaars.
