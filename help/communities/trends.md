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

Met de component `Community Activity List` kunt u trending-informatie over posts en weergaven door leden en posts en weergaven van inhoud toevoegen.

In deze sectie van de documentatie wordt beschreven

* De `Community Activity List`-component toevoegen aan een [communitysite](overview.md#community-sites)

* Configuratie-instellingen voor de `Community Activity List`-component

## Vereiste {#requirement}

Gegevens voor de `Community Activity List` zijn alleen beschikbaar wanneer Adobe Analytics een licentie heeft en is geconfigureerd voor de communitysite.

Zie [Analyseconfiguratie voor Gemeenschappen-functies](analytics.md).

## Een communautaire activiteitenlijst toevoegen aan een pagina {#adding-a-community-activity-list-to-a-page}

Als u een component `Community Activity List` in de modus Schrijver aan een pagina wilt toevoegen, zoekt u de component `Communities / Community Activity List` en sleept u deze naar de gewenste plaats op een pagina.

Voor noodzakelijke informatie, bezoek [de Grondbeginselen van Componenten van Gemeenschappen](basics.md).

Wanneer de component voor het eerst op een pagina van een communitysite wordt geplaatst, ziet deze er zo uit:

![chlimage_1-227](assets/chlimage_1-227.png)

## Lijst met communautaire activiteiten configureren {#configuring-community-activity-list}

Selecteer de geplaatste `Community Activity List` component en selecteer `Configure` pictogram dat het Edit dialoog opent.

![chlimage_1-228](assets/chlimage_1-228.png)

Geef op het tabblad **[!UICONTROL Comments]** op of en hoe opmerkingen voor geüploade bestanden worden weergegeven:

![chlimage_1-229](assets/chlimage_1-229.png)

* **[!UICONTROL Type]**

   Geef op of gegevens met betrekking tot leden van de gebruikersgemeenschap of door de gebruiker gegenereerde inhoud (UGC) moeten worden weergegeven.

   Selecteer  vanuit
   * `Members`
   * `Content`

   De standaardwaarde is `Members`.

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

   De standaardwaarde is `Total`.

* **[!UICONTROL Context path]**

   Verstrekt de capaciteit om de activiteit tot een ondergroep van de plaats, zoals een specifieke Blog uit te breiden.

   Standaard is dit de hele community-site.

* **[!UICONTROL Member count aggregation]**

   Als deze optie uitgeschakeld is, worden alleen berichten op het hoogste niveau geteld. Als de context bijvoorbeeld de hoofdpagina is (de standaardinstelling), wordt bij een `Activity Type`van `Posts`geen activiteit weergegeven omdat er geen inhoud naar de hoofdpagina kan worden gepost. Wanneer deze optie is ingeschakeld, worden de tellingen op alle afstammende pagina&#39;s opgenomen.

   Standaard is ingeschakeld.

## Voorbeeld van pagina met 4 componenten {#example-page-with-components}

**Top** Visitorsconfig: Type = Leden, Type activiteit = Weergaven

**Top** Contributorsconfig: Type = Leden, Type activiteit = Posten

**Top** Contentconfig: Type = Inhoud, Type activiteit = Weergaven

**Trending** Contentconfig: Type = Inhoud, Type activiteit = Post

![chlimage_1-230](assets/chlimage_1-230.png)
