---
title: Activiteitendensen
seo-title: Activity Trends
description: Een component Community Activity List aan een pagina toevoegen
seo-description: Adding a Community Activity List component to a page
uuid: 6a030340-0e69-432a-98f1-3effb2b97136
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: 93a112fc-ef34-4281-89b8-a0f1b3d3aca9
exl-id: a2cb9738-98a5-4ea6-8d5a-a6c0aa04cd32
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 1%

---

# Activiteitendensen {#activity-trends}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Inleiding {#introduction}

De `Community Activity List` biedt de mogelijkheid om trendinformatie toe te voegen over posten en weergaven door leden, alsmede over posten en weergaven van inhoud.

In deze sectie van de documentatie wordt beschreven

* Het toevoegen van `Community Activity List` component aan een [community-site](overview.md#community-sites)

* De montages van de configuratie voor de `Community Activity List` component

## Vereiste {#requirement}

Gegevens voor de `Community Activity List` is alleen beschikbaar als Adobe Analytics een licentie heeft en geconfigureerd voor de community-site.

Zie [Analytische configuratie voor functies van Gemeenschappen](analytics.md).

## Een communautaire activiteitenlijst toevoegen aan een pagina {#adding-a-community-activity-list-to-a-page}

Als u een `Community Activity List` naar een pagina in de modus Schrijver, zoek de component `Communities / Community Activity List` en sleep het naar de juiste plaats op een pagina.

Voor de nodige informatie gaat u naar [Grondbeginselen van Community-componenten](basics.md).

Wanneer de component voor het eerst op een pagina van een communitysite wordt geplaatst, ziet deze er zo uit:

![chlimage_1-227](assets/chlimage_1-227.png)

## Lijst met communautaire activiteiten configureren  {#configuring-community-activity-list}

Selecteer de geplaatste `Community Activity List` te openen en de component te selecteren `Configure` wordt het dialoogvenster Bewerken geopend.

![chlimage_1-228](assets/chlimage_1-228.png)

Onder de **[!UICONTROL Comments]** , geeft u op of en hoe opmerkingen voor geüploade bestanden worden weergegeven:

![chlimage_1-229](assets/chlimage_1-229.png)

* **[!UICONTROL Type]**

   Geef op of gegevens met betrekking tot leden van de gebruikersgemeenschap of door de gebruiker gegenereerde inhoud (UGC) moeten worden weergegeven.

   Selecteer  vanuit
   * `Members`
   * `Content`

   Standaard is `Members`.

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

   Standaard is `Total`.

* **[!UICONTROL Context path]**

   Verstrekt de capaciteit om de activiteit tot een ondergroep van de plaats, zoals een specifieke Blog uit te breiden.

   Standaard is dit de hele community-site.

* **[!UICONTROL Member count aggregation]**

   Als deze optie uitgeschakeld is, worden alleen berichten op het hoogste niveau geteld. Als de context bijvoorbeeld de hoofdpagina is (de standaardinstelling), `Activity Type`van `Posts`geen activiteit tonen omdat inhoud niet op de hoofdpagina kan worden geplaatst. Wanneer deze optie is ingeschakeld, worden de tellingen op alle afstammende pagina&#39;s opgenomen.

   Standaard is ingeschakeld.

## Voorbeeldpagina met 4 componenten {#example-page-with-components}

**Topbezoekers** config: Type = Leden, Type activiteit = Weergaven

**Belangrijkste bijdragers** config: Type = Leden, Type activiteit = Posten

**Bovenste inhoud** config: Type = Inhoud, Type activiteit = Weergaven

**Trend Content** config: Type = Inhoud, Type activiteit = Post

![chlimage_1-230](assets/chlimage_1-230.png)
