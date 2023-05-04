---
title: Communautaire functies
seo-title: Community Functions
description: Leer hoe u toegang krijgt tot de Community Function Console
seo-description: Learn how to access the Community Functions console
uuid: 5cce05f5-1dd7-496d-94c2-8fccc0177d13
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: cc993b71-e2f2-48e7-ad4e-469cb5ce2dc1
role: Admin
exl-id: 2007336d-d75c-4e01-af81-181751c04cfe
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '2457'
ht-degree: 0%

---

# Communautaire functies {#community-functions}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Het type functies dat wordt verwacht van een community-ervaring is bekend. De communautaire eigenschappen zijn beschikbaar als communautaire functies. In wezen zijn ze een of meer pagina&#39;s die vooraf zijn bekabeld om een community-functie te implementeren. Hiervoor is meer nodig dan alleen het toevoegen van een component aan een pagina in de modus Schrijven. Zij zijn de bouwstenen die worden gebruikt om de structuur van een [sjabloon voor community-site](sites.md) waarvan sites uit de gemeenschap [gemaakt](sites-console.md).

Nadat een communitysite is gemaakt, kan inhoud aan de resulterende pagina&#39;s worden toegevoegd met de standaard [AEM ontwerpmodus](../../help/sites-authoring/editing-content.md).

Een aantal communautaire functies zijn onmiddellijk beschikbaar zoals die in de console van communautaire functies worden gezien. In toekomstige versies worden meer communityfuncties geleverd en er kunnen ook aangepaste functies worden gemaakt.

>[!NOTE]
>
>De consoles voor het creëren van [communitysites](sites-console.md), [communitysjablonen](sites.md), [communitygroepsjablonen](tools-groups.md) en [communautaire functies](functions.md) zijn alleen bestemd voor gebruik in de ontwerpomgeving.

## Community-functieconsole {#community-functions-console}

In de auteursomgeving, om de console van communautaire functies te bereiken

* Vanuit globale navigatie: **[!UICONTROL Tools > Communities > Community Functions]**

![chlimage_1-379](assets/chlimage_1-379.png)

## Vooraf gebouwde functies {#pre-built-functions}

Hieronder volgt een korte beschrijving van de functies die bij AEM Communities worden geleverd. Elke functie bestaat uit een of meer AEM pagina&#39;s die onderdelen van een Gemeenschappen bevatten die zijn samengevoegd tot een functie die eenvoudig in een [sjabloon voor community-site](sites.md).

Een communitysitesjabloon biedt de structuur voor een communitysite, zoals aanmeldingsgegevens, gebruikersprofielen, meldingen, berichten, berichten, het menu van de site, zoeken, thema&#39;s en brandingfuncties.

### Instellingen voor Titel en URL {#title-and-url-settings}

**Titel** en **URL** zijn eigenschappen die alle functies van de gemeenschap gemeen hebben.

Wanneer een communautaire functie aan een malplaatje van de communautaire plaats wordt toegevoegd of wanneer toegevoegd [wijzigen](sites-console.md#modifying-site-properties) In de structuur van een communitysite wordt het dialoogvenster van de functie geopend, zodat de titel en de URL kunnen worden geconfigureerd.

#### Configuratiefunctie {#configuration-function-details}

![chlimage_1-380](assets/chlimage_1-380.png)

* **[!UICONTROL Title]**
(
*vereist*) De tekst die wordt weergegeven in het menu met functies voor de site

* **[!UICONTROL URL]**
(*vereist*) De naam die wordt gebruikt om de URI te genereren. De naam moet in overeenstemming zijn met de [naamconventies](../../help/sites-developing/naming-conventions.md) opgelegd door AEM en JCR.

Als u bijvoorbeeld de site gebruikt die u hebt gemaakt op basis van de [Aan de slag](getting-started.md) zelfstudie, als

* Titel = webpagina
* URL = pagina

De URL naar de pagina is http://local_host:4503/content/sites/engage/en/page.html en de menukoppeling voor de pagina ziet er als volgt uit:

![chlimage_1-381](assets/chlimage_1-381.png)

### Functie activiteitsstroom {#activity-stream-function}

De functie activity stream is een pagina met een [Activiteitsstromen](activities.md) met alle geselecteerde weergaven (alle activiteiten, gebruikersactiviteiten en volgende). Zie ook [Essentiële elementen activiteitsstroom](essentials-activities.md) voor ontwikkelaars.

Wanneer u een sjabloon toevoegt, wordt het volgende dialoogvenster geopend:

#### Configuratiefunctie {#configuration-function-details-1}

![chlimage_1-382](assets/chlimage_1-382.png)

* Zie [Instellingen voor Titel en URL](#title-and-url-settings)
* **[!UICONTROL Show "My Activities" view]**
Als deze optie is ingeschakeld, bevat de pagina Activiteiten een tabblad waarop de activiteiten worden gefilterd op basis van de activiteiten die door het huidige lid binnen de gemeenschap worden gegenereerd. Standaard is ingeschakeld.

* **[!UICONTROL Show "All Activities" view]**
Als deze optie is ingeschakeld, bevat de pagina Activiteiten een tabblad dat alle activiteiten bevat die zijn gegenereerd binnen de gemeenschap waartoe het huidige lid toegang heeft. Standaard is ingeschakeld.

* **[!UICONTROL Show "News Feed" view]**
Als deze optie is ingeschakeld, bevat de pagina Activiteiten een tabblad waarop de activiteiten worden gefilterd op basis van de activiteiten die het huidige lid volgt. Standaard is ingeschakeld.

### Toewijzingsfunctie {#assignments-function}

De toewijzingsfunctie is de basisfunctie die een [gemeenschapssite voor activering](overview.md#enablement-community). Het maakt het mogelijk middelen voor activering toe te wijzen aan leden van de gemeenschap. Zie ook [Essentiële toewijzingen](essentials-assignments.md) voor ontwikkelaars.

Deze functie is beschikbaar als een functie van de [add-on inschakelen](enablement.md). De inschakelingsadd-on vereist aanvullende licenties voor gebruik in een productieomgeving.

Wanneer toegevoegd aan een malplaatje, is de enige configuratie voor [Instellingen voor Titel en URL](#title-and-url-settings).

### Blogfunctie {#blog-function}

De blogfunctie is een pagina met een [Blogcomponent](blog-feature.md) geconfigureerd voor labelen, het uploaden van bestanden, als volgt, leden die zichzelf moeten bewerken, stemmen en moderatie. Zie ook [Grondbeginselen van blogs](blog-developer-basics.md) voor ontwikkelaars.

Wanneer u een sjabloon toevoegt, wordt het volgende dialoogvenster geopend:

![chlimage_1-383](assets/chlimage_1-383.png)

* Zie [Instellingen voor Titel en URL](#title-and-url-settings)
* **[!UICONTROL Allow Privileged Members]**
Als deze optie is ingeschakeld, staat de blog geprivilegieerde leden alleen toe artikelen te maken door de selectie van een [groep geprivilegieerde leden](users.md#privileged-members-group). Als deze optie niet is ingeschakeld, mogen alle leden van de gemeenschap het bestand maken. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow File Uploads]**
Als deze optie is ingeschakeld, bevat de blog de mogelijkheid voor leden om bestanden te uploaden. Standaard is ingeschakeld.

* **[!UICONTROL Allow Threaded Replies]**
Als deze optie niet is ingeschakeld, staat de blog reacties (opmerkingen) op een artikel toe, maar zijn reacties op opmerkingen niet toegestaan. Standaard is ingeschakeld.

* **[!UICONTROL Allow Featured Content]**
Indien deze optie is ingeschakeld, kan het idee worden geïdentificeerd als [aanbevolen inhoud](featured.md). Standaard is ingeschakeld.

### Kalenderfunctie {#calendar-function}

De kalenderfunctie is een pagina met een [Kalendercomponent](calendar.md) geconfigureerd om tags toe te staan. Zie ook [Essentiële elementen van agenda](calendar-basics-for-developers.md) voor ontwikkelaars.

Wanneer u een sjabloon toevoegt, wordt het volgende dialoogvenster geopend:

![chlimage_1-384](assets/chlimage_1-384.png)

* Zie [Instellingen voor Titel en URL](#title-and-url-settings)
* **[!UICONTROL Allow Pinning]**
Als deze optie is ingeschakeld, kunnen de reacties op onderwerpen worden vastgezet aan het begin van de lijst met opmerkingen. Standaard is ingeschakeld.

* **[!UICONTROL Allow Privileged Members]**
Als deze optie is ingeschakeld, staat de blog geprivilegieerde leden alleen toe artikelen te maken door de selectie van een [groep geprivilegieerde leden](users.md#privileged-members-group). Als deze optie niet is ingeschakeld, mogen alle leden van de gemeenschap het bestand maken. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow File Uploads]**
Als deze optie is ingeschakeld, bevat de blog de mogelijkheid voor leden om bestanden te uploaden. Standaard is ingeschakeld.

* **[!UICONTROL Allow Threaded Replies]**
Als deze optie niet is ingeschakeld, staat de blog reacties (opmerkingen) op een artikel toe, maar zijn reacties op opmerkingen niet toegestaan. Standaard is ingeschakeld.

* **[!UICONTROL Allow Featured Content]**
Indien deze optie is ingeschakeld, kan het idee worden geïdentificeerd als [aanbevolen inhoud](featured.md). Standaard is ingeschakeld.

### Catalogusfunctie {#catalog-function}

De catalogusfunctie biedt de mogelijkheid om [enablement community](overview.md#enablement-community) leden kunnen bladeren door bronnen die niet aan hen zijn toegewezen. Zie [Tags toewijzen](tag-resources.md) en [Essentiële elementen van catalogus](catalog-developer-essentials.md) voor ontwikkelaars.

Alle enablement-bronnen en leerpaden voor de communitysite worden in alle catalogi weergegeven als hun eigenschap, ` [Show in Catalog](resources.md)`, is ingesteld op true. Als u expliciet bronnen en leerpaden wilt opnemen, moet u een [voorfilter](catalog-developer-essentials.md#pre-filters) naar de catalogus.

Wanneer de configuratie aan een sjabloon is toegevoegd, kunt u met de configuratie tagnaamruimten opgeven die worden gebruikt om het tagfilter te configureren dat aan bezoekers van de site wordt aangeboden:

![catalogusfunctie](assets/catalogfunc.png)

* Zie [Instellingen voor Titel en URL](#title-and-url-settings)
* **[!UICONTROL Select All Namespaces]**

   * Met de geselecteerde tagnaamruimten wordt gedefinieerd welke tags bezoekers kunnen selecteren voor het filteren van de lijst met activeringsbronnen die in de catalogus wordt vermeld.
   * Als deze optie is ingeschakeld, zijn alle naamruimten voor tags die zijn toegestaan voor de communitysite, beschikbaar.
   * Als deze optie uitgeschakeld is, is het mogelijk een of meer naamruimten te selecteren die zijn toegestaan voor de communitysite.
   * Standaard is ingeschakeld.

### Functie aanbevolen inhoud {#featured-content-function}

De functie voor aanbevolen inhoud is een pagina met een [Aanbevolen inhoudscomponent](featured.md) geconfigureerd om opmerkingen toe te voegen en te verwijderen.

De mogelijkheid om inhoud van kenmerken te voorzien, is mogelijk toegestaan of niet toegestaan voor elk onderdeel (zie [Blogfunctie](#blog-function), [Kalenderfunctie](#calendar-function), [Functie van forum](#forum-function), [Idealisatiefunctie](#ideation-function), en [QnA-functie](#qna-function)).

Wanneer toegevoegd aan een malplaatje, is de enige configuratie voor [Instellingen voor Titel en URL](#title-and-url-settings).

### Functie bestandsbibliotheek {#file-library-function}

De bestandsbibliotheekfunctie is een pagina met een [Bestandsbibliotheek, component](file-library.md) geconfigureerd om opmerkingen toe te voegen en te verwijderen.

Wanneer toegevoegd aan een malplaatje, is de enige configuratie voor [Instellingen voor Titel en URL](#title-and-url-settings).

### Functie van forum {#forum-function}

De forumfunctie is een pagina met een [Forum-component](forum.md) geconfigureerd voor labelen, het uploaden van bestanden, als volgt, leden die zichzelf moeten bewerken, stemmen en moderatie.

Wanneer u een sjabloon toevoegt, wordt het volgende dialoogvenster geopend:

#### Configuratiefunctie {#configuration-function-details-2}

![chlimage_1-385](assets/chlimage_1-385.png)

* Zie [Instellingen voor Titel en URL](#title-and-url-settings)
* **[!UICONTROL Allow Pinning]**
Als deze optie is ingeschakeld, kunnen de reacties op onderwerpen worden vastgezet aan het begin van de lijst met opmerkingen. Standaard is ingeschakeld.

* **[!UICONTROL Allow Privileged Members]**
Indien deze optie is ingeschakeld, staat het forum geprivilegieerde leden alleen toe onderwerpen te posten door de selectie van een [groep geprivilegieerde leden](users.md#privileged-members-group). Als deze optie niet is ingeschakeld, mogen alle leden van de gemeenschap posten. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow File Uploads]**
Als deze optie is ingeschakeld, kunnen leden bestanden uploaden. Standaard is ingeschakeld.

* **[!UICONTROL Allow Threaded Replies]**
Als het forum niet wordt gecontroleerd, zal het commentaar op een onderwerp toestaan, maar antwoorden op die commentaren worden niet toegestaan. Standaard is ingeschakeld.

* **[!UICONTROL Allow Featured Content]**
Indien deze optie is ingeschakeld, kan het idee worden geïdentificeerd als [aanbevolen inhoud](featured.md). Standaard is ingeschakeld.

### Functie Groepen {#groups-function}

>[!CAUTION]
>
>De groepfunctie moet *niet* zijn *alleen* functioneren in de structuur van een site of in een sjabloon voor een community-site.
>
>Elke andere functie, zoals de [page, functie](#page-function), moet worden opgenomen en als eerste worden vermeld.

De groepsfunctie biedt leden van de gemeenschap de mogelijkheid om subgemeenschappen binnen de gemeenschapssite in de publicatieomgeving te maken.

Afhankelijk van [instellingen](sites-console.md#groupmanagement) wanneer de functie Groepen is opgenomen in een [sjabloon voor community-site](sites.md), kunnen de groepen openbaar of privé zijn en één of meerdere malplaatjes van de communautaire groep kunnen worden gevormd om een keus van malplaatjes te verstrekken wanneer de communautaire groep eigenlijk wordt gecreeerd (zoals van het publicatiemilieu). A [communitygroepsjabloon](tools-groups.md) Hiermee geeft u aan welke communautaire functies worden gemaakt voor de pagina&#39;s van de groep, zoals forums en kalenders.

Wanneer een communautaire groep wordt gecreeerd, wordt een lidgroep dynamisch gecreeerd voor de nieuwe groep, waaraan de leden kunnen worden toegewezen of zich aansluiten. Zie voor meer informatie [Gebruikers en gebruikersgroepen beheren](users.md).

Vanaf Gemeenschappen [functiepakket 1](deploy-communities.md#latestfeaturepack), worden in de ontwerpomgeving groepen gemaakt met de [Community Sites Group-console](groups.md)en kan worden gemaakt in de publicatieomgeving wanneer deze is ingeschakeld.

Wanneer u een sjabloon toevoegt, wordt het volgende dialoogvenster geopend:

![chlimage_1-386](assets/chlimage_1-386.png)

* Zie [Instellingen voor Titel en URL](#title-and-url-settings)
* **[!UICONTROL Select Group Templates]**
Een keuzemenu waarmee u een of meer ingeschakelde groepssjablonen kunt selecteren waaruit de toekomstige maker van een nieuwe communitygroep (in de publicatieomgeving) kan kiezen.

* **[!UICONTROL Allow Privileged Members]**
Indien deze optie is ingeschakeld, staat het forum geprivilegieerde leden alleen toe onderwerpen te posten door de selectie van een [veiligheidsgroep van geprivilegieerde leden](users.md#privileged-members-group). Als deze optie niet is ingeschakeld, mogen alle leden van de gemeenschap posten. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Publish Creation]**
Als deze optie is ingeschakeld, kunnen geautoriseerde leden van de gemeenschap een groep maken in de publicatieomgeving. Als deze optie niet is ingeschakeld, kunnen alleen nieuwe groepen (subgemeenschappen) worden gemaakt in de auteursomgeving via de console Groepen van de sites van de Gemeenschappen.

   Standaard is `checked`.

### Idealisatiefunctie {#ideation-function}

De videofunctie is een pagina met één [Onderdeel voor ideeën](ideation-feature.md).

Wanneer u een sjabloon toevoegt, wordt het volgende dialoogvenster geopend met de standaardnamen voor Titel en URL en de standaardweergave-instellingen voor de sjabloon:

![chlimage_1-387](assets/chlimage_1-387.png)

* Zie [Instellingen voor Titel en URL](#title-and-url-settings)
* **[!UICONTROL Allow Privileged Members]**
Indien deze optie is ingeschakeld, staat het forum geprivilegieerde leden alleen toe onderwerpen te posten door de selectie van een [veiligheidsgroep van geprivilegieerde leden](users.md#privileged-members-group). Als deze optie niet is ingeschakeld, mogen alle leden van de gemeenschap posten. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow File Uploads]**
Als deze optie is ingeschakeld, kunnen leden bestanden uploaden. Standaard is ingeschakeld.

* **[!UICONTROL Allow Threaded Replies]**
Als deze optie niet is ingeschakeld, is het mogelijk om antwoorden (opmerkingen) op een onderwerp toe te staan, maar om opmerkingen te beantwoorden is het niet toegestaan. Standaard is ingeschakeld.

* **[!UICONTROL Allow Featured Content]**
Indien deze optie is ingeschakeld, kan het idee worden geïdentificeerd als [aanbevolen inhoud](featured.md). Standaard is ingeschakeld.

### Leaderboard-functie {#leaderboard-function}

De leaderboardfunctie is een pagina met één pagina [Leaderboard-component](enabling-leaderboard.md).

**OPMERKING**: de Leaderboard-component moet verder worden geconfigureerd *na* Er wordt een community-site gemaakt op basis van een communitysjabloon die de Leaderboard-functie bevat. De component Leaderboard [regels](enabling-leaderboard.md#rules-tab) moet worden gespecificeerd, afhankelijk van de configuratie van [scoring en badges](implementing-scoring.md) voor de site van de community.

Wanneer u een sjabloon toevoegt, wordt het volgende dialoogvenster geopend met de standaardnamen voor Titel en URL en de standaardweergave-instellingen voor de sjabloon:

![chlimage_1-388](assets/chlimage_1-388.png)

* Zie [Instellingen voor Titel en URL](#title-and-url-settings)
* **[!UICONTROL Display Badge]**
Als deze optie is ingeschakeld, wordt een kolom voor badge-pictogrammen opgenomen in het leaderboard.

   De optie Standaard is uitgeschakeld.

* **[!UICONTROL Display Badge Name]**
Als deze optie is ingeschakeld, wordt een kolom met de naam van de badge opgenomen in het leaderboard.

   De optie Standaard is uitgeschakeld.

* **[!UICONTROL Display Avatar]**
Als deze optie is ingeschakeld, wordt de avatarafbeelding van het lid opgenomen in het leaderboard, naast de naamkoppeling naar het profiel van het lid.

   De optie Standaard is uitgeschakeld.

### Paginacode {#page-function}

De paginafunctie voegt een lege pagina aan de communautaire plaats toe dat het in de eigenschappen van de communautaire plaats wordt getelegrafeerd: aanmelden, menu, meldingen, berichten, berichten, thema&#39;s en branding. Inhoud kan aan de pagina worden toegevoegd met de [standaard AEM ontwerpmodus](../../help/sites-authoring/editing-content.md).

Wanneer toegevoegd aan een malplaatje, is de enige configuratie voor [Instellingen voor Titel en URL](#title-and-url-settings).

### QnA-functie {#qna-function}

De functie QnA is een pagina met een [QnA-component](working-with-qna.md) geconfigureerd voor labelen, het uploaden van bestanden, als volgt, leden die zichzelf moeten bewerken, stemmen en moderatie.

Wanneer toegevoegd aan een malplaatje, staat de configuratie beperking aan bevoorrechte leden toe:

![chlimage_1-389](assets/chlimage_1-389.png)

* Zie [Instellingen voor Titel en URL](#title-and-url-settings)
* **[!UICONTROL Allow Pinning]**
Als deze optie is ingeschakeld, kunnen de reacties op onderwerpen worden vastgezet aan het begin van de lijst met opmerkingen. Standaard is ingeschakeld.

* **[!UICONTROL Allow Privileged Members]**
Indien gecontroleerd, zal het forum QnA bevoorrechte leden slechts toestaan om vragen te posten door selectie van toe te staan [groep geprivilegieerde leden](users.md#privileged-members-group). Als deze optie niet is ingeschakeld, mogen alle leden van de gemeenschap posten. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow File Uploads]**
Als deze optie is ingeschakeld, bevat het QnA-forum de mogelijkheid voor leden om bestanden te uploaden. Standaard is ingeschakeld.

* **[!UICONTROL Allow Threaded Replies]**
Als het QnA-forum niet wordt gecontroleerd, kan er commentaar (antwoorden) worden gegeven op een geposte vraag, maar antwoorden op antwoorden zijn niet toegestaan. Standaard is ingeschakeld.

* **[!UICONTROL Allow Featured Content]**
Indien deze optie is ingeschakeld, kan het idee worden geïdentificeerd als [aanbevolen inhoud](featured.md). Standaard is ingeschakeld.

## Community-functie maken {#create-community-function}

De mogelijkheid om een gemeenschapsfunctie te maken, wordt bereikt door de `Create Community Function` pictogram boven aan de console voor communautaire functies. Er kunnen meerdere functies worden gemaakt die op dezelfde AEM blauwdruk zijn gebaseerd en vervolgens op unieke wijze worden aangepast door het openen in de bewerkingsmodus van de auteur.

![chlimage_1-390](assets/chlimage_1-390.png)

### Community-functienaam {#community-function-name}

![chlimage_1-391](assets/chlimage_1-391.png)

In het deelvenster Community Function Name worden een naam, beschrijving en of de functie is ingeschakeld of uitgeschakeld geconfigureerd:

* **[!UICONTROL Community Function Name]**
De functienaam die wordt gebruikt voor weergave en opslag

* **[!UICONTROL Community Function Description]**
De functiebeschrijving voor de weergave

* **[!UICONTROL Disabled/Enabled]**
Een schakeloptie die bepaalt of de functie waarnaar wordt verwezen

### AEM {#aem-blueprint}

![chlimage_1-392](assets/chlimage_1-392.png)

Op de `AEM Blueprint` is het mogelijk de blauwdruk te selecteren die de onderliggende uitvoering van de communautaire functie is .

De functie van de gemeenschap is een mini plaats die uit één of meerdere pagina&#39;s wordt samengesteld, die voor opneming in een communautaire plaats met inbegrip van login, gebruikersprofielen, berichten, overseinen, plaatsmenu, onderzoek, het thema, en branding eigenschappen vooraf wordt getelegrafeerd. Wanneer de functie is gemaakt, is het mogelijk om [open de functie](#open-community-function) in de bewerkingsmodus van de auteur en pas de pagina- en/of componentinstellingen aan.

Aangezien de communautaire functie als [live kopie](../../help/sites-administering/msm.md#live-copies) van [blauwdruk](../../help/sites-administering/msm-livecopy.md#creatingablueprint), is het mogelijk wijzigingen door te voeren die zijn aangebracht in een functie die van invloed is op alle pagina&#39;s van de gemeenschapssite die zijn gemaakt op basis van de [sjabloon voor community-site](sites.md) of [communitygroepsjabloon](tools-groups.md) dat de functie omvatte. Het is ook mogelijk om een pagina los te koppelen van de bovenliggende blauwdruk om wijzigingen op paginaniveau aan te brengen.

Zie ook [Beheer van meerdere sites](../../help/sites-administering/msm.md).

### Miniatuur {#thumbnail}

![chlimage_1-393](assets/chlimage_1-393.png)

In het deelvenster Miniatuur kan een afbeelding worden geüpload om te worden weergegeven in het dialoogvenster [Community Functions-console](#community-functions-console).

## Community-functie openen {#open-community-function}

![chlimage_1-394](assets/chlimage_1-394.png)

Selecteer `Open Community Function` pictogram om de bewerkingsmodus voor auteurs in te schakelen voor het ontwerpen van de pagina-inhoud en het wijzigen van de configuratie van de component(en) met functies.

### Componenten configureren {#configuring-components}

Een communautaire functie wordt uitgevoerd als Levende Kopie van een AEM Blauwdruk, die details onder wordt gedocumenteerd [Beheer van meerdere sites](../../help/sites-administering/msm.md).

Het is mogelijk om niet alleen pagina-inhoud te schrijven, maar componenten te configureren.

Als het vormen van een component op een pagina van een gecreeerde communautaire plaats, kan het noodzakelijk zijn om te annuleren [overerving](../../help/sites-administering/msm-livecopy.md#changing-live-copy-content) om de component te configureren. De overerving moet worden hersteld wanneer de configuratie is voltooid.

Voor configuratiedetails, bezoek [Community-componenten](author-communities.md) voor auteurs.

## Community-functie bewerken {#edit-community-function}

![chlimage_1-395](assets/chlimage_1-395.png)

Selecteer `Edit Community Function` pictogram om de eigenschappen van de functie te bewerken met dezelfde deelvensters als [gemeenschapsfunctie maken](#create-community-function), inclusief het inschakelen of uitschakelen van de functie.
