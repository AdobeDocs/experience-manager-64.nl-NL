---
title: Leaderboard-functie
seo-title: Leaderboard Feature
description: Een Leaderboard-component aan een pagina toevoegen
seo-description: Adding a Leaderboard component to a page
uuid: 2a766b63-3ab4-44cd-8a26-629a71b837ea
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: 1e96d388-8517-4a84-bb0a-d49567eb4bdf
exl-id: 1ebe0cbb-33be-4101-92e3-64253a7f7f31
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 0%

---

# Leaderboard-functie {#leaderboard-feature}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Inleiding {#introduction}

De `Leaderboard` de component biedt de mogelijkheid om een idee te krijgen van de manier waarop leden binnen de gemeenschap met elkaar communiceren door leden te rangschikken op basis van verdiende punten (basisscore) of hun deskundigheid (geavanceerde scoring).

Voordat u de leaderboard-component op een pagina plaatst, moet u [Scores en badges van gemeenschappen](implementing-scoring.md).

In deze sectie van de documentatie wordt beschreven

* Het toevoegen van `Leaderboard` component aan een [community-site](overview.md#community-sites)

* De montages van de configuratie voor de `Leaderboard` component

## Een Leaderboard toevoegen aan een pagina {#adding-a-leaderboard-to-a-page}

Als u een `Leaderboard` naar een pagina in de modus Schrijver, zoek de component

* `Communities / Leaderboard`

en sleep het naar de juiste plaats op een pagina.

Voor de nodige informatie gaat u naar [Grondbeginselen van Community-componenten](basics.md).

Wanneer de component voor het eerst op een pagina van een communitysite wordt geplaatst, ziet deze er zo uit:

![chlimage_1-8](assets/chlimage_1-8.png)

## Leaderboard configureren {#configuring-leaderboard}

Selecteer de geplaatste `Leaderboard` te openen en de component te selecteren `Configure` wordt het dialoogvenster Bewerken geopend.

![chlimage_1-9](assets/chlimage_1-9.png) ![chlimage_1-10](assets/chlimage_1-10.png)

### Het tabblad Instellingen {#settings-tab}

Onder de **[!UICONTROL Settings]** tabblad geeft u op welke informatie over het lid wordt weergegeven:

* **[!UICONTROL Display Name]**
Een beschrijvende naam die voor het bord moet worden weergegeven en die de regels weergeeft die zijn geselecteerd voor het weergeven van badges en scores.

   Standaard is `Leaderboard`, als er niets is ingevoerd.

* **[!UICONTROL Badge]**
Als deze optie is ingeschakeld, wordt een kolom voor badge-pictogrammen opgenomen in het leaderboard.

   De optie Standaard is uitgeschakeld.

* **[!UICONTROL Badge Name]**
Als deze optie is ingeschakeld, wordt een kolom met de naam van de badge opgenomen in het leaderboard.

   De optie Standaard is uitgeschakeld.

* **[!UICONTROL Use Avatar]**
Als deze optie is ingeschakeld, wordt de avatarafbeelding van het lid opgenomen in het leaderboard, naast de naamkoppeling naar het profiel van het lid.

   De optie Standaard is uitgeschakeld.

### Regels, tabblad {#rules-tab}

Onder de **[!UICONTROL Rules]** tab, de site van de community en de bijbehorende regels voor scoring en badging

* **[!UICONTROL Rule Location]**
(Vereist) Plaats waar de het Scoren/het Bedragen regel wordt gevormd.

* **[!UICONTROL Scoring Rule]**
(Vereist) Specifieke regel die de scores genereert die moeten worden weergegeven.

* **[!UICONTROL Badging Rule]**
(Vereist) Specifieke regel die de badge aan vertoning produceert.

* **[!UICONTROL Display Limit]**
Aantal leden dat per pagina moet worden weergegeven.

   De standaardwaarde is 10.

## Voorbeeld: Lederboard van deelnemers {#example-participants-leaderboard}

Deze lederbordrapporten zijn het resultaat van het toepassen van elementaire scoringregels.

Configuratie van de component Leaderboard:

* **[!UICONTROL Settings]** tab:

   * Weergavenaam = `Participation Board`
   * `checked`:

      * Badge
      * Naam badge
      * Avatar gebruiken

* **[!UICONTROL Rules]** tab:

   * Locatie van regel = `/content/sites/communities/jcr:content`
   * Scoreregel = `/etc/community/scoring/rules/forums-scoring`
   * Badgingregel = `/etc/community/badging/rules/reference-badging`
   * Weergavelimiet = `10`

![chlimage_1-11](assets/chlimage_1-11.png)

## Voorbeeld: Expert Leaderboard {#example-experts-leaderboard}

Dit leaderboard-rapport is het resultaat van het toepassen van geavanceerde scoreregels.

Configuratie van de component Leaderboard:

* **[!UICONTROL Settings]** tab:

   * Weergavenaam = `Expertise Board`
   * `checked`:

      * Badge
      * Avatar gebruiken

* **[!UICONTROL Rules]** tab:

   * Locatie van regel = `/content/sites/communities/jcr:content`
   * Scoreregel = `/etc/community/scoring/rules/adv-forums-scoring`
   * Badgingregel = `/etc/community/badging/rules/adv-forums-badging`
   * Weergavelimiet = `10`

![chlimage_1-12](assets/chlimage_1-12.png)

## Aanvullende informatie {#additional-information}

Meer informatie is te vinden op de [Essentiële elementen op Leaderboard](leaderboard.md) pagina voor ontwikkelaars.

De instructies voor het creëren van regels worden verstrekt op [Scores en badges van gemeenschappen](implementing-scoring.md) pagina voor beheerders.
