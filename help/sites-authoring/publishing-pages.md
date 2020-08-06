---
title: Pagina's publiceren
seo-title: Pagina's publiceren
description: 'null'
seo-description: 'null'
uuid: 1222859d-ef8d-462e-a125-b76e6cfec26d
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: page-authoring
content-type: reference
discoiquuid: 8f2714bc-9d6c-4e6f-97a1-3b4f977348c5
translation-type: tm+mt
source-git-commit: cdec5b3c57ce1c80c0ed6b5cb7650b52cf9bc340
workflow-type: tm+mt
source-wordcount: '1630'
ht-degree: 5%

---


# Pagina&#39;s publiceren{#publishing-pages}

Nadat u de inhoud hebt gemaakt en gecontroleerd in de auteursomgeving, [stelt u deze beschikbaar op uw openbare website](/help/sites-authoring/author.md#concept-of-authoring-and-publishing) (uw publicatieomgeving).

Dit wordt bedoeld als het publiceren van een pagina. Wanneer u een pagina uit het publicatiemilieu wilt verwijderen wordt bedoeld unpublishing. Wanneer u de pagina publiceert en publiceert, blijft deze beschikbaar in de ontwerpomgeving voor verdere wijzigingen totdat u de pagina verwijdert.

U kunt een pagina ook direct of op een vooraf gedefinieerde datum/tijd publiceren of verwijderen.

>[!NOTE]
>
>Bepaalde termen met betrekking tot publicatie kunnen worden verward:
>
>* **Publiceren/Publiceren ongedaan maken**
   >  Dit zijn de belangrijkste termen voor de acties die uw inhoud openbaar maken in uw publicatieomgeving (of niet).
   >
   >
* **Activeren/deactiveren**
   >  Deze termen zijn synoniem met publiceren/verwijderen.
   >
   >
* **Replicatie/replicatie**
   >  Dit zijn de technische termen die de beweging van gegevens (bijvoorbeeld pagina-inhoud, bestanden, code, gebruikerscommentaren) van de ene omgeving naar de andere beschrijven, zoals bij het publiceren of omgekeerd repliceren van gebruikerscommentaren.
>



>[!NOTE]
>
>Als u niet over de vereiste rechten voor het publiceren van een specifieke pagina beschikt:
>
>* Er wordt een workflow gestart om de juiste persoon op de hoogte te stellen van uw verzoek om te publiceren.
>* Deze [workflow is mogelijk aangepast](/help/sites-developing/workflows-models.md) door uw ontwikkelingsteam.
>* Er wordt kort een bericht weergegeven om u te laten weten dat de workflow is geactiveerd.

>



## Pagina&#39;s publiceren {#publishing-pages-2}

Afhankelijk van uw locatie kunt u publiceren:

* [Vanuit de pagina-editor](/help/sites-authoring/publishing-pages.md#publishing-from-the-editor)
* [Van de plaatsenconsole](/help/sites-authoring/publishing-pages.md#publishing-from-the-console)

### Publiceren vanuit de Editor {#publishing-from-the-editor}

Als u een pagina bewerkt, kunt u deze rechtstreeks vanuit de editor publiceren.

1. Selecteer het pictogram **Pagina-informatie** om het menu te openen en klik vervolgens op de optie **Pagina** publiceren.

   ![screen_shot_2018-03-21at152734](assets/screen_shot_2018-03-21at152734.png)

1. Afhankelijk van het feit of de pagina verwijzingen bevat die moeten worden gepubliceerd:

   * De pagina wordt rechtstreeks gepubliceerd als er geen referenties zijn die moeten worden gepubliceerd.
   * Als de pagina verwijzingen heeft die het publiceren vereisen, zullen deze in de **Publish** tovenaar worden vermeld, waar u of kunt:

      * Geef aan welke elementen/tags/etc. Als u samen met de pagina wilt publiceren, gebruikt u **Publiceren** om het proces te voltooien.
      * Gebruik **Annuleren** om de handeling af te breken.

   ![chlimage_1-50](assets/chlimage_1-50.png)

1. Als u **Publiceren** selecteert, wordt de pagina gekopieerd naar de publicatieomgeving. In de paginaeditor wordt een informatiebanner weergegeven die de publicatieactie bevestigt.

   ![screen_shot_2018-03-21at152840](assets/screen_shot_2018-03-21at152840.png)

   Wanneer u dezelfde pagina in de console weergeeft, is de bijgewerkte publicatiestatus zichtbaar.

   ![screen_shot_2018-03-21at152951](assets/screen_shot_2018-03-21at152951.png)

>[!NOTE]
>
>Publiceren vanuit de editor is een oppervlakkige publicatie, dat wil zeggen dat alleen de geselecteerde pagina(&#39;s) wordt/worden gepubliceerd en onderliggende pagina&#39;s niet.

### Publiceren vanuit de console {#publishing-from-the-console}

In de siteconsole zijn er twee opties voor publiceren:

* [Snel publiceren](/help/sites-authoring/publishing-pages.md#quick-publish)
* [Publicatie beheren](/help/sites-authoring/publishing-pages.md#manage-publication)

#### Snel publiceren {#quick-publish}

**Snel publiceren** is voor eenvoudige gevallen en publiceert de geselecteerde pagina(&#39;s) direct zonder verdere interactie. Daarom worden niet-gepubliceerde verwijzingen ook automatisch gepubliceerd.

Een pagina publiceren met Snel publiceren:

1. Selecteer de pagina of pagina&#39;s in de siteconsole en klik op de knop **Snel publiceren** .

   ![screen_shot_2018-03-21at153115](assets/screen_shot_2018-03-21at153115.png)

1. Bevestig de publicatie in het dialoogvenster Snel publiceren door te klikken op **Publiceren** of Annuleren door te klikken op **Annuleren**. Onthoud dat niet-gepubliceerde verwijzingen automatisch ook worden gepubliceerd.

   ![chlimage_1-51](assets/chlimage_1-51.png)

1. Wanneer de pagina wordt gepubliceerd, wordt een waarschuwing getoond die de publicatie bevestigt.

>[!NOTE]
>
>Snel publiceren is een oppervlakkige publicatie, dat wil zeggen dat alleen de geselecteerde pagina(&#39;s) wordt/worden gepubliceerd en onderliggende pagina&#39;s niet.

#### Publicatie beheren {#manage-publication}

**Publicatie** beheren biedt meer opties dan Snel publiceren, waardoor onderliggende pagina&#39;s kunnen worden opgenomen, de referenties kunnen worden aangepast en toepasselijke workflows kunnen worden gestart en de optie kan worden geboden om op een latere datum te publiceren.

Een pagina publiceren of de publicatie ervan ongedaan maken met Publicatie beheren:

1. Selecteer de pagina of pagina&#39;s in de siteconsole en klik op de knop Publicatie **beheren** .

   ![screen_shot_2018-03-21at153309](assets/screen_shot_2018-03-21at153309.png)

1. De wizard **Publicatie beheren** wordt gestart. In de eerste stap, **Opties**, kunt u:

   * Kies of u de geselecteerde pagina&#39;s wilt publiceren of de publicatie ervan ongedaan wilt maken.
   * Kies of u deze handeling nu of op een latere datum wilt uitvoeren.

   Als u later publiceert, wordt een workflow gestart om de geselecteerde pagina of pagina&#39;s op het opgegeven tijdstip te publiceren. Als u de publicatie later ongedaan maakt, wordt een workflow gestart om de publicatie van de geselecteerde pagina of pagina&#39;s op een bepaald moment ongedaan te maken.

   Als u een publicatie/publicatie later wilt annuleren, gaat u naar de [workflowconsole](/help/sites-administering/workflows.md) om de bijbehorende workflow te beëindigen.

   ![chlimage_1-52](assets/chlimage_1-52.png)

   Klik op **Volgende** om door te gaan.

1. In de volgende stap van de wizard Publicatie beheren, **Bereik**, kunt u het bereik van de publicatie/publicatie definiëren, zoals het opnemen van onderliggende pagina&#39;s en/of het opnemen van referenties.

   ![screen_shot_2018-03-21at153354](assets/screen_shot_2018-03-21at153354.png)

   U kunt de knop **Inhoud toevoegen** gebruiken om extra pagina&#39;s toe te voegen aan de lijst met pagina&#39;s die moeten worden gepubliceerd voor het geval u deze niet hebt geselecteerd voordat u de wizard Publicatie beheren start.

   Klik op de knop Inhoud toevoegen om de [padbrowser](/help/sites-authoring/author-environment-tools.md#path-browser) te starten en de inhoud te selecteren.

   Selecteer de vereiste pagina&#39;s en klik vervolgens op **Selecteren** om de inhoud aan de wizard toe te voegen of op **Annuleren **om de selectie te annuleren en terug te keren naar de wizard.

   Terug in de tovenaar, kunt u een punt in de lijst selecteren om zijn verdere opties zoals te vormen:

   * Inclusief de onderliggende elementen.
   * Verwijder het uit de selectie.
   * De gepubliceerde referenties beheren.

   ![screen_shot_2018-03-21at153450](assets/screen_shot_2018-03-21at153450.png)

   Klik op **Inclusief onderliggende items** om een dialoogvenster te openen waarin u:

   * Alleen directe kinderen opnemen.
   * Alleen gewijzigde pagina&#39;s opnemen.
   * Alleen al gepubliceerde pagina&#39;s opnemen.

   Klik op **Toevoegen** om de onderliggende pagina&#39;s toe te voegen aan de lijst met pagina&#39;s die gepubliceerd of niet gepubliceerd moeten worden op basis van de selectieopties. Klik op **Annuleren** om de selectie te annuleren en terug te keren naar de wizard.

   ![chlimage_1-53](assets/chlimage_1-53.png)

   Als u terugkeert naar de wizard, ziet u de toegevoegde pagina&#39;s op basis van uw keuze voor opties in het dialoogvenster Inclusief onderliggende items.

   U kunt de te publiceren of ongepubliceerde verwijzingen voor een pagina bekijken en wijzigen door het te selecteren en dan de **Gepubliceerde knoop van Verwijzingen** te klikken.

   ![screen_shot_2018-03-21at153801](assets/screen_shot_2018-03-21at153801.png)

   In het dialoogvenster **Gepubliceerde verwijzingen** worden de referenties voor de geselecteerde inhoud weergegeven. Standaard zijn ze allemaal geselecteerd en worden ze gepubliceerd/niet gepubliceerd, maar u kunt de optie uitschakelen om ze te deselecteren zodat ze niet in de handeling worden opgenomen.

   Klik op **Gereed** om de wijzigingen op te slaan of op **Annuleren** om de selectie te annuleren en terug te keren naar de wizard.

   ![screen_shot_2018-03-21at153824](assets/screen_shot_2018-03-21at153824.png)

   In de wizard wordt de kolom **Verwijzingen** bijgewerkt met de verwijzingen die u hebt geselecteerd om te publiceren of ongepubliceerd.

   ![screen_shot_2018-03-21at153925](assets/screen_shot_2018-03-21at153925.png)

1. Klik op **Publiceren** om te voltooien.

   Terug in de plaatsenconsole zal een berichtbericht de publicatie bevestigen.

   ![screen_shot_2018-03-21at153951](assets/screen_shot_2018-03-21at153951.png)

1. Als de gepubliceerde pagina&#39;s aan werkschema&#39;s worden geassocieerd, kunnen zij in een definitieve stap van de **Werkschema** van de publicatietovenaar worden getoond.

   >[!NOTE]
   >
   >De stap **Workflows** wordt weergegeven op basis van de rechten die de gebruiker heeft of niet. Zie de [vorige opmerking op deze pagina](/help/sites-authoring/publishing-pages.md) over publicatiebevoegdheden en het [beheren van de toegang tot workflows](/help/sites-administering/workflows-managing.md) en het [toepassen van workflows op pagina](/help/sites-authoring/workflows-applying.md) &#39;s voor meer informatie.

   De bronnen worden gegroepeerd op basis van de workflows die worden geactiveerd en elke optie heeft de volgende opties:

   * Definieer de titel van de workflow.
   * Behoud het workflowpakket, op voorwaarde dat de workflow ondersteuning biedt voor [meerdere cursussen](/help/sites-developing/workflows-models.md#configuring-a-workflow-for-multi-resource-support).
   * Definieer een titel van het workflowpakket als de optie om het workflowpakket te behouden is gekozen.

   Click **Publish** or **Publish Later **to complete the publication.

   ![chlimage_1-54](assets/chlimage_1-54.png)

## Publicatie van pagina&#39;s ongedaan maken {#unpublishing-pages}

Als u de publicatie van een pagina ongedaan maakt, wordt deze verwijderd uit uw publicatieomgeving, zodat deze niet langer beschikbaar is voor uw lezers.

Op een [manier die vergelijkbaar is met publiceren](/help/sites-authoring/publishing-pages.md#publishing-pages), kunnen een of meer pagina&#39;s niet worden gepubliceerd:

* [Vanuit de pagina-editor](/help/sites-authoring/publishing-pages.md#unpublishing-from-the-editor)
* [Van de plaatsenconsole](/help/sites-authoring/publishing-pages.md#unpublishing-from-the-console)

### Publicatie ongedaan maken vanuit de Editor {#unpublishing-from-the-editor}

Als u een pagina bewerkt en de publicatie van die pagina ongedaan wilt maken, selecteert u **Publicatie van pagina** ongedaan maken in het menu **Pagina-informatie** , net zoals u de pagina [zou](/help/sites-authoring/publishing-pages.md#publishing-from-the-editor)publiceren.

### Publicatie ongedaan maken vanuit de console {#unpublishing-from-the-console}

Net zoals u de optie Publicatie beheren [gebruikt om te publiceren](/help/sites-authoring/publishing-pages.md#manage-publication), kunt u deze ook gebruiken om de publicatie ongedaan te maken.

1. Selecteer de pagina of pagina&#39;s in de siteconsole en klik op de knop Publicatie **beheren** .
1. De wizard **Publicatie beheren** wordt gestart. In de eerste stap, bij **Opties**, selecteert u **Publicatie ongedaan maken** in plaats van de standaardoptie **Publiceren**.

   ![chlimage_1-55](assets/chlimage_1-55.png)

   Net zoals later met publiceren een workflow wordt gestart om deze versie van de pagina op het opgegeven tijdstip te publiceren, wordt later met deactiveren een workflow gestart om de publicatie van de geselecteerde pagina of pagina&#39;s op een bepaald tijdstip ongedaan te maken.

   Als u een publicatie/publicatie later wilt annuleren, gaat u naar de [workflowconsole](/help/sites-administering/workflows.md) om de bijbehorende workflow te beëindigen.

1. Als u de publicatie wilt voltooien, gaat u door met de wizard zoals u de pagina [wilt](/help/sites-authoring/publishing-pages.md#manage-publication)publiceren.

## Een boomstructuur publiceren en de publicatie ervan opheffen {#publishing-and-unpublishing-a-tree}

Wanneer u een aanzienlijk aantal inhoudspagina&#39;s hebt ingevoerd of bijgewerkt - die allen onder de zelfde wortelpagina ingezeten zijn - kan het gemakkelijker zijn om de volledige boom in één actie te publiceren.

Hiervoor kunt u de optie Publicatie [](/help/sites-authoring/publishing-pages.md#manage-publication) beheren op de siteconsole gebruiken.

1. Selecteer in de siteconsole de hoofdpagina van de boomstructuur die u wilt publiceren of waarvan u de publicatie ongedaan wilt maken, en selecteer Publicatie **beheren**.
1. De wizard **Publicatie beheren** wordt gestart. Kies of u wilt publiceren of de publicatie ongedaan wilt maken en wanneer dit moet gebeuren en selecteer **Volgende** om door te gaan.
1. Selecteer in de stap **Bereik** de basispagina en selecteer **Onderliggende** elementen opnemen.

   ![chlimage_1-56](assets/chlimage_1-56.png)

1. Schakel in het dialoogvenster Onderliggende **items** opnemen de opties uit:

   * Alleen directe kinderen opnemen
   * Alleen reeds gepubliceerde pagina&#39;s opnemen

   Deze opties zijn standaard geselecteerd, dus u moet niet vergeten deze te deselecteren. Klik op **Toevoegen** om de inhoud te bevestigen en toe te voegen aan de publicatie/publicatie.

   ![chlimage_1-57](assets/chlimage_1-57.png)

1. De wizard **Publicatie** beheren geeft een overzicht van de inhoud van de structuur die u wilt controleren. U kunt de selectie verder aanpassen door extra pagina&#39;s toe te voegen of geselecteerde pagina&#39;s te verwijderen.

   ![screen_shot_2018-03-21at154237](assets/screen_shot_2018-03-21at154237.png)

   U kunt ook de verwijzingen controleren die via de optie **Gepubliceerde verwijzingen** moeten worden gepubliceerd.

1. [Ga naar de normale](#manage-publication) wizard Publicatie beheren om de publicatie of publicatie van de boomstructuur te voltooien.

## Publicatiestatus bepalen {#determining-publication-status}

U kunt de publicatiestatus van een pagina bepalen:

* In de informatie van het [middeloverzicht over de plaatsenconsole](/help/sites-authoring/basic-handling.md#viewing-and-selecting-resources)

   ![screen_shot_2018-03-21at154336](assets/screen_shot_2018-03-21at154336.png)

   De publicatiestatus wordt weergegeven in [kaart](/help/sites-authoring/basic-handling.md#card-view)-, [kolom](/help/sites-authoring/basic-handling.md#column-view)- en [lijstweergaven](/help/sites-authoring/basic-handling.md#list-view) in de Sites-console.

* In de [tijdlijn](/help/sites-authoring/basic-handling.md#timeline)

   ![screen_shot_2018-03-21at154420](assets/screen_shot_2018-03-21at154420.png)

* In het menu [](/help/sites-authoring/author-environment-tools.md#page-information) Pagina-informatie wanneer u een pagina bewerkt

   ![screen_shot_2018-03-21at154456](assets/screen_shot_2018-03-21at154456.png)

