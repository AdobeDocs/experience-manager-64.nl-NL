---
title: Moderatieconsole
seo-title: Moderation Console
description: Hoe te om tot de console van de Moderatie toegang te hebben
seo-description: How to access the Moderation console
uuid: 920124b9-af6f-4622-adb6-b8e294c5607d
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 6c405543-e339-4916-aa0f-b61d0b798cf3
role: Admin
exl-id: ded38cee-fbce-46cc-974f-38d3a293a55d
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1879'
ht-degree: 0%

---

# Moderatieconsole {#moderation-console}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

In AEM Communities, bulkgoederen [modernisering van de communautaire inhoud](moderate-ugc.md) is mogelijk van zowel auteur als publiceer milieu&#39;s door beheerders en communautaire moderatoren (vertrouwde op communautaire leden die als moderators worden toegewezen).

Beheerders en moderatoren van de gemeenschap kunnen ook [contextmatiging](in-context.md) in de publicatieomgeving.

Een kenmerk van alles [communitysites](sites-console.md) is een `Administration`menu-item beschikbaar voor gebruikers die zich aanmelden met beheerdersrechten. De `Administration`de verbinding verleent toegang tot de console van de Moderatie.

Van de console van de Moderatie, zullen de beheerders en de communautaire moderatoren toegang tot al gebruiker geproduceerde inhoud (UGC) hebben waarvoor zij toestemming hebben te matigen. Als u meerdere sites wilt gematigd, is het mogelijk om posten op alle sites weer te geven of door geselecteerde communitysites te filteren.

Voor meer informatie gaat u naar [Gebruikers en gebruikersgroepen beheren](users.md).

De console van de Moderatie steunt:
* Het uitvoeren van matigingstaken in bulk
* UGC zoeken
* UGC-details weergeven
* UGC-auteurdetails weergeven

Alleen bij aanmelding als beheerder of lid met ` [moderator permissions](in-context.md#identifyingtrustedmembers)`kan worden uitgevoerd.

## Toegang tot omgeving publiceren {#publish-environment-access}

De toegang tot de console van de Moderatie van een gepubliceerde communautaire plaats is door een verbinding van het Beleid die verschijnt wanneer een communautaire moderator binnen wordt ondertekend.

![uitgeverij](assets/publishweretail.png)

Door de verbinding van het Beleid te selecteren, verschijnt de console van de Moderatie:

![moderationconsole-publish](assets/moderationconsole-publish.png)

## Toegang tot ontwerpomgeving {#author-environment-access}

In het auteursmilieu, om de console van de Moderatie te bereiken

* Vanuit globale navigatie: **[!UICONTROL Navigation > Communities > Moderation]**

Alleen bij aanmelding als beheerder of als lid met ` [moderator permissions](in-context.md#identifyingtrustedmembers)`kan worden uitgevoerd. De enige inhoud van de gemeenschap die wordt weergegeven, is de inhoud die de ondertekenaar mag verkleinen.

>[!NOTE]
>
>UGC van het publicatiemilieu zal slechts op auteur zichtbaar zijn als gekozen SRP een gemeenschappelijke opslag uitvoert. De opslag is standaard bijvoorbeeld JSRP, wat geen algemene opslag is voor auteur en publiceren. Zie [Opslag van communautaire inhoud](working-with-srp.md).

![moderationconsoletoewijzing](assets/moderationconsoleauthor.png)

## Gebruikersinterface van aanpassingsconsole {#moderation-console-ui}

Afgezien van de linkse navigatiespoor (die bij auteur, maar niet bij publicatie verschijnt), heeft de moderatie UI de volgende belangrijkste gebieden:

* **[Bovenste navigatiebalk](#top-navigation-bar)**
* **[Werkbalk](#toolbar)**
* **[Inhoudsgebied](#content-area)**

### Bovenste navigatiebalk {#top-navigation-bar}

De bovenste navigatiebalk is voor alle consoles constant. Zie voor meer informatie [Basisverwerking](../../help/sites-authoring/basic-handling.md).

### Werkbalk {#toolbar}

De werkbalk, die zich onder de bovenste navigatiebalk bevindt, biedt de volgende schakeloptie aan de linkerkant:

* [Filterrail](moderation.md#filter-rail) opent een rails waarin u de eigenschappen kunt kiezen waarop u de inhoud wilt filteren.

De werkbalk, die zich onder de bovenste navigatiebalk bevindt, biedt de volgende schakeloptie aan de linkerkant:

![toggleswitch](assets/toggleswitch.png)

[Filterrail](moderation.md#filter-rail)\
Hiermee opent u een rails waarin u de inhoud kunt filteren op de gewenste eigenschappen.

![filterrail](assets/filterrail.png)

### Inhoudsgebied {#content-area}

Het inhoudsgebied bevat informatie voor gepost UGC:

* De UGC heeft gepost
* Lidnaam
* Member avatar
* Plaats van de post
* Wanneer het is geplaatst
* Aantal reacties op de post
* [Sentiment](moderate-ugc.md#sentiment) in verband met het bericht
* Indien goedgekeurd, wordt een vinkje weergegeven
* Als er een bijlage is, wordt een paperclip weergegeven

>[!NOTE]
>
>Het inhoudsgebied bevat een *oneindig schuiven*, wat betekent dat u kunt blijven schuiven totdat u het einde van de inhoud hebt bereikt. De werkbalk blijft tijdens het schuiven op een vaste, zichtbare positie boven het inhoudsgebied staan.

### Rail filteren {#filter-rail}

![chlimage_1-472](assets/chlimage_1-472.png)

Met het pictogram van het zijpaneel wordt de filterrail geopend. De filterrail, die links van het inhoudsgebied verschijnt, verstrekt verschillende filters, elk die een onmiddellijk effect op referenced UGC hebben die in het inhoudsgebied verschijnt.

De filters binnen elke categorie zijn **OF** worden samengevoegd en de filters in verschillende categorieën zijn **EN** rd samen.

Als u bijvoorbeeld beide incheckt **Vraag** en **Antwoord**, ziet u inhoud die een van de **Vraag** *of* een **Antwoord**.

Als u echter **Vraag** en **In behandeling**, ziet u alleen inhoud die een **Vraag** en is **In behandeling**.

>[!NOTE]
>
>De moderatoren van de Gemeenschap kunnen referentie de vooraf bepaalde filters op moderatieconsole UI. Aangezien deze filters aan het eind van URL (als parameters van het vraagkoord) worden toegevoegd, kunnen de moderatoren aan de bookmarked filters later terugkomen en deze verbindingen ook delen.

![zoekpictogram](assets/searchicon.png)

Wanneer de filterrail is geopend, schakelt het zoekpictogram de zijpaneel gesloten. Als u echter de filterrail wilt sluiten en alleen de door de gebruiker gegenereerde inhoud wilt weergeven, klikt u op het pictogram Zoeken en selecteert u de optie Alleen inhoud.

#### Inhoudspad {#content-path}

Met Inhoudspad wordt de referentie-UGC beperkt tot de posten die in de opgegeven opslagplaats voor inhoud zijn geplaatst.

![inhoudspad](assets/content-path.png)

#### Tekst zoeken {#text-search}

Bij zoeken naar tekst wordt de UGC waarnaar wordt verwezen, beperkt tot advertenties waarin de ingevoerde tekst voorkomt.

![chlimage_1-473](assets/chlimage_1-473.png)

#### Site {#site}

De site beperkt de UGC waarnaar wordt verwezen, tot advertenties aan geselecteerde communitysites. Als geen plaatsen worden gecontroleerd, dan worden alle verwijzingen naar UGC getoond.

![chlimage_1-474](assets/chlimage_1-474.png)

>[!NOTE]
>
>Wanneer de bulkmoderatieconsole door een beheerder wordt betreden, worden alle verwijzingen naar UGC getoond, met inbegrip van plaatsen niet gecreeerd met [wizard voor het maken van sites](sites-console.md), zoals de Geometrixx monsters.
>
>Wanneer de bulkmoderatieconsole bij publiceren door een vertrouwd communautair lid wordt betreden, dan slechts worden de verwijzingen naar UGC die voor communautaire plaatsen worden gecreeerd het lid aan gematigd wordt toegelaten getoond, en met de filter van de Plaats kunnen worden gefiltreerd.

#### Inhoudstype {#content-type}

Het Type van inhoud beperkt referenced UGC getoond aan posten van het geselecteerde middeltype. Een of meer van de volgende typen kunnen worden geselecteerd. Alle typen worden weergegeven als er geen is geselecteerd.

* **Opmerking**
* **Forum-onderwerp**
* **Forum Reageren**
* **Vraag QnA**
* **Antwoord vragen**
* **Blogartikel**
* **Blogopmerking**
* **Kalendergebeurtenis**
* **Opmerking kalender**
* **Map bestandsbibliotheek**
* **Document bestandsbibliotheek**
* **Idea**
* **Commentaar bij idee**

![inhoudstypen](assets/content-types.png)

#### Aanvullende inhoudstypen {#additional-content-types}

Aanvullende bronnen toevoegen waarop moet worden gefilterd:

* Op een instantie van een auteur
* Aanmelden als beheerder
* Openen [Webconsole](http://localhost:4502/system/console/configMgr)
* Zoeken `AEM Communities Moderation Dashboard Filters`
* Selecteer de configuratie die u wilt openen in de bewerkingsmodus
* Ga het ResourceType van een component in waarop te filtreren
   * Als u bijvoorbeeld wilt filteren op opgenomen stemcomponenten, voert u het volgende in:\
      `Voting=social/tally/components/hbs/voting`

![chlimage_1-475](assets/chlimage_1-475.png)

* Selecteer Opslaan
* Vernieuw de Gemeenschappen - Moderniseringsconsole

Het resultaat is een nieuw selecteerbaar filter voor `Voting`onder de `Content Type` filtergroep.

Wanneer dat filter wordt geselecteerd zal de inhoud van het dashboard UGC tonen die om het even welke ingevoerde ResourceTypes aanpast.

#### Status {#status}

De status beperkt de UGC waarnaar wordt verwezen, tot posten van de geselecteerde status, die één of meer van In behandeling, Goedgekeurd, Afgewezen of Gesloten, evenals Ontwerp of Gepland voor Blogartikelen, en Beantwoord of niet Beantwoord voor Vragen QnA kan zijn. Als geen wordt geselecteerd, dan worden allen getoond.

>[!NOTE]
>
>Als slechts de niet Beantwoorde status wordt geselecteerd, dan zal de moderator al inhoud (voor alle inhoudstypes) behalve de beantwoorde vragen zien. Dit komt omdat de eigenschap die verantwoordelijk is voor de beantwoorde vraag niet bestaat in het geval van niet-beantwoorde vragen en andere inhoud zoals het onderwerp van het forum, het blogartikel of opmerkingen.

![statussen](assets/statuses.png)

#### Markering {#flagging}

Als u een vlag voert, wordt de UGC waarnaar wordt verwezen, beperkt tot publicaties die zijn gemarkeerd of verborgen.

Wanneer een stuk inhoud is gemarkeerd, blijft het gemarkeerd totdat u de markering van dat stuk inhoud ongedaan maakt door de optie **[!UICONTROL Flag]** nogmaals. Er zijn geen markeringsniveaus, zoals belangrijk of opgevolgd.

![chlimage_1-476](assets/chlimage_1-476.png)

#### Leden {#members}

Leden beperken de UGC waarnaar wordt verwezen, die aan UGC wordt weergegeven en die door de ingevoerde lidnaam is gepost.

![chlimage_1-477](assets/chlimage_1-477.png)

#### Gepost in de laatste {#posted-in-the-last}

Gepost in de Laatste grenzen UGC van verwijzingen aan posten die in het laatste uur, de dag, de week, de maand, of het jaar worden getoond.

![chlimage_1-478](assets/chlimage_1-478.png)

#### Sentiment {#sentiment}

[Sentiment](moderate-ugc.md#sentiment) beperkt de UGC waarnaar wordt verwezen, tot posten met een sentiment-waarde die positief, negatief of neutraal is.

![chlimage_1-479](assets/chlimage_1-479.png)

## Moderatiehandelingen {#moderation-actions}

[Moderniseringsacties](moderate-ugc.md#moderation-actions) kan worden uitgevoerd op een of meer selecties die in het inhoudsgebied zijn gemaakt of wanneer u de details van de inhoud weergeeft.

Klik in het inhoudsgebied op Selecteren ( ![selecticon](assets/selecticon.png)) op een post, die verschijnt als u de muisaanwijzer (bureaublad) op het desbetreffende artikel plaatst of met een vinger op het betreffende artikel (mobiel) drukt. Op deze manier opent u de multiselectiemodus en kunt u nu de volgende posts selecteren die bulksgewijs moeten worden gemodereerd door er gewoon op te klikken. Gebruik de knoppen op de werkbalk om moderatiehandelingen uit te voeren op de geselecteerde posten. Alle acties worden ter bevestiging voorgelegd.

Als u één artikel in het inhoudsgebied wilt gematigd, houdt u de muisaanwijzer (bureaublad) of drukt u met een vinger op de post (mobiel), zodat er knoppen op de post verschijnen. Als u op één inhoudsgegeven werkt, wordt alleen een verwijderactie ter bevestiging verzonden.

### Meerdere posts modereren {#moderating-multiple-posts}

U opent de modus voor bulkselectie door op de knop `Select` pictogram op een bericht:

![select-icon](assets/select-icon.png)

Als u de modus voor bulkselectie wilt afsluiten, selecteert u het pictogram voor annuleren (x) op de werkbalk:

De moderniseringsacties die op meerdere posten kunnen worden uitgevoerd zijn:

* Weigeren
* Verwijderen
* De berichten sluiten/opnieuw openen

De pictogrammen voor deze handelingen worden alleen op de werkbalk weergegeven als er meerdere posts zijn geselecteerd.

![paars](assets/bulkmoderate.png)

### Eén artikel moderniseren {#moderating-a-single-post}

In de enkelvoudige selectiemodus is het mogelijk om

* Gebruikersgegevens weergeven door de gebruikersnaam te selecteren
* Klik op de link naar het bericht in de context bekijken
* [Reageren](#reply)
* [Toestaan](#allow)
* [Weigeren](#deny)
* [Verwijderen](#delete)
* [Sluiten](#close)
* Weergave [Moderatiegeschiedenis](#moderation-history)
* [Details weergeven](#viewdetails)

De tekst van de post op de kaartweergave boven de mageractiepictogrammen is de tekst van de post en hieronder staan de gegevens die aangeven

* Zo ja, voorafgegaan door het aantal antwoorden
* Indien gemarkeerd
* Indien goedgekeurd
* Wanneer de UGC is geplaatst

![singleElectmode](assets/singleselectmode.png)

#### Reageren {#reply}

![chlimage_1-480](assets/chlimage_1-480.png)

Wanneer het werken met één enkele post, zal een pictogram van het Antwoord verschijnen als het type UGC antwoorden steunt en wordt gevormd om antwoorden toe te staan.

#### Toestaan {#allow}

![chlimage_1-481](assets/chlimage_1-481.png)

Wanneer u met één bericht werkt, wordt het pictogram Toestaan weergegeven wanneer de advertentie is gemarkeerd of geweigerd. Als deze optie is gemarkeerd, worden alle markeringen gewist als u Toestaan selecteert.

#### Weigeren {#deny}

![chlimage_1-482](assets/chlimage_1-482.png)

De **Weigeren** matigheidsactie is slechts beschikbaar voor inhoud die wordt gematigd, en niet op ongematigde inhoud behalve in multi-selectiemodus verschijnt.

Inhoud die niet wordt gematigd, wordt altijd goedgekeurd.

De inhoud die aanvankelijk wordt gematigd gaat een Hangende staat in, en kan later worden gewijzigd om worden goedgekeurd of worden ontkend.

Inhoud die de status in behandeling verlaat, kan nooit terugkeren naar een status in behandeling. Inhoud die is gemarkeerd als goedgekeurd of geweigerd, kan op elk gewenst moment worden gewijzigd in een andere status.

#### Verwijderen {#delete}

![chlimage_1-483](assets/chlimage_1-483.png)

In de modus Enkel selecteren of Samenvoegen kunt u items selecteren en verwijderen. De verwijderactie leidt tot een bevestigingsvenster. Als deze items eenmaal zijn verwijderd, verdwijnen ze direct uit het inhoudsgebied. **Zodra UGC wordt geschrapt, wordt het permanent verwijderd uit de bewaarplaats en kan later niet worden teruggewonnen.**

#### Sluiten {#close}

![chlimage_1-484](assets/chlimage_1-484.png)

Wanneer u met één artikel werkt, wordt een pictogram Sluiten weergegeven als het type UGC de mogelijkheid ondersteunt om verdere posten voor die bron te voorkomen.

#### Moderatiegeschiedenis {#moderation-history}

![chlimage_1-485](assets/chlimage_1-485.png)

Wanneer u met één bericht werkt, wordt een pictogram Moderatiegeschiedenis weergegeven wanneer u de muisaanwijzer op de desbetreffende post plaatst. Als u het pictogram selecteert, wordt een deelvenster weergegeven met een overzicht van de acties die met betrekking tot de UGC-post zijn uitgevoerd.

Als u wilt terugkeren naar de weergave van het inhoudsgebied van meerdere UGC-posten, selecteert u de X in de rechterbovenhoek van het deelvenster met weergavedetails.

Bijvoorbeeld:

![chlimage_1-486](assets/chlimage_1-486.png)

#### Details weergeven {#view-detail}

![chlimage_1-487](assets/chlimage_1-487.png)

Als u met één artikel werkt, kunt u meer details bekijken door de UGC in de detailmodus te openen.

Houd hiertoe de muisaanwijzer boven de post om de `View Detail` en selecteert u deze om een deelvenster weer te geven met meer details over de advertentie.

Als u wilt terugkeren naar de weergave van het inhoudsgebied van meerdere UGC-posten, selecteert u de X in de rechterbovenhoek van het deelvenster met weergavedetails.

Bijvoorbeeld:

![chlimage_1-488](assets/chlimage_1-488.png)
