---
title: Activiteitendensen
seo-title: Activiteitendensen
description: Een component Community Activity List aan een pagina toevoegen
seo-description: Een component Community Activity List aan een pagina toevoegen
uuid: 6a030340-0e69-432a-98f1-3effb2b97136
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: 93a112fc-ef34-4281-89b8-a0f1b3d3aca9
translation-type: tm+mt
source-git-commit: 5ddbcb2addff2d6e3a3e9d7e100a6d9ba89fdd60
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 1%

---


# Activiteitendensen {#activity-trends}

## Inleiding {#introduction}

De `Community Activity List` component biedt de mogelijkheid om trending information betreffende posten en weergaven door leden toe te voegen, alsook publicaties en weergaven van inhoud.

In deze sectie van de documentatie wordt beschreven

* De `Community Activity List` component toevoegen aan een [communitysite](overview.md#community-sites)

* Configuratie-instellingen voor de `Community Activity List` component

## Vereiste {#requirement}

Gegevens voor de `Community Activity List` website zijn alleen beschikbaar wanneer Adobe Analytics een licentie heeft en geconfigureerd voor de communitysite.

Zie [Analytics Configuration for Communities Features](analytics.md).

## Een communautaire activiteitenlijst toevoegen aan een pagina {#adding-a-community-activity-list-to-a-page}

Als u een `Community Activity List` component aan een pagina wilt toevoegen in de ontwerpmodus, zoekt u de component `Communities / Community Activity List` en sleept u deze naar de juiste plaats op een pagina.

Ga voor de benodigde informatie naar [Community Components Basics](basics.md).

Wanneer de component voor het eerst op een pagina van een communitysite wordt geplaatst, ziet deze er zo uit:

![chlimage_1-227](assets/chlimage_1-227.png)

## Lijst met communautaire activiteiten configureren  {#configuring-community-activity-list}

Selecteer de geplaatste `Community Activity List` component die u wilt openen en selecteer het `Configure` pictogram waarmee het dialoogvenster Bewerken wordt geopend.

![chlimage_1-228](assets/chlimage_1-228.png)

Geef op het **[!UICONTROL Comments]** tabblad op of en hoe opmerkingen voor geüploade bestanden worden weergegeven:

![chlimage_1-229](assets/chlimage_1-229.png)

* **[!UICONTROL Type]**

   Geef op of gegevens met betrekking tot leden van de gebruikersgemeenschap of door de gebruiker gegenereerde inhoud (UGC) moeten worden weergegeven.

   Selecteer  vanuit
   * `Members`
   * `Content`

   Standaard is dit `Members`.

* **[!UICONTROL Display title]**

   Een beschrijvende titel die boven de gegevens wordt weergegeven, zoals `Trending Content`.

   Standaard is geen titel.

* **[!UICONTROL Display count]**

   Het aantal aan te bieden items.

   De standaardwaarde is 10.

* **[!UICONTROL Activity type]**

   Selecteer een van de volgende opties
   * `Views`(paginabezoeken)
   * `Posts`(maken van UGC)
   * `Follows`
   * `Likes`

   Standaard zijn weergaven.

* **[!UICONTROL Time period]**

   Selecteer een van de volgende opties
   * `Last 24 hours`
   * `Last 7 days`
   * `Last 30 days`
   * `Last 90 days`
   * `This year (since Jan 1st)`
   * `Total`

   Standaard is dit `Total`.

* **[!UICONTROL Context path]**

   Verstrekt de capaciteit om de activiteit tot een ondergroep van de plaats, zoals een specifieke Blog uit te breiden.

   Standaard is dit de hele community-site.

* **[!UICONTROL Member count aggregation]**

   Als deze optie uitgeschakeld is, worden alleen berichten op het hoogste niveau geteld. Als de context bijvoorbeeld de hoofdpagina is (de standaardinstelling), `Activity Type`wordt bij een `Posts`van deze pagina nooit enige activiteit weergegeven, omdat de inhoud niet op de hoofdpagina kan worden geplaatst. Wanneer deze optie is ingeschakeld, worden de tellingen op alle afstammende pagina&#39;s opgenomen.

   Standaard is ingeschakeld.

## Voorbeeldpagina met 4 componenten {#example-page-with-components}

**Configuratie van bovenste bezoekers** : Type = Leden, Type activiteit = Weergaven

**Configuratie van belangrijkste contribuanten** : Type = Leden, Type activiteit = Posten

**Configuratie van de bovenste inhoud** : Type = Inhoud, Type activiteit = Weergaven

**Trending Content** config: Type = Inhoud, Type activiteit = Post

![chlimage_1-230](assets/chlimage_1-230.png)
