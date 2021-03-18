---
title: Communautaire functies
seo-title: Communautaire functies
description: Leer hoe u toegang krijgt tot de Community Function Console
seo-description: Leer hoe u toegang krijgt tot de Community Function Console
uuid: 5cce05f5-1dd7-496d-94c2-8fccc0177d13
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: cc993b71-e2f2-48e7-ad4e-469cb5ce2dc1
role: Beheerder
translation-type: tm+mt
source-git-commit: 75312539136bb53cf1db1de03fc0f9a1dca49791
workflow-type: tm+mt
source-wordcount: '2432'
ht-degree: 0%

---


# Community-functies {#community-functions}

Het type functies dat wordt verwacht van een community-ervaring is bekend. De communautaire eigenschappen zijn beschikbaar als communautaire functies. In wezen zijn ze een of meer pagina&#39;s die vooraf zijn bekabeld om een community-functie te implementeren. Hiervoor is meer nodig dan alleen het toevoegen van een component aan een pagina in de modus Schrijven. Zij zijn de bouwstenen die worden gebruikt om de structuur van een [communityplaatsjabloon](sites.md) te bepalen waarvan de communautaire plaatsen [gecreeerd](sites-console.md) zijn.

Nadat een communitysite is gemaakt, kan inhoud aan de resulterende pagina&#39;s worden toegevoegd met de standaard [AEM ontwerpmodus](../../help/sites-authoring/editing-content.md).

Een aantal communautaire functies zijn onmiddellijk beschikbaar zoals die in de console van communautaire functies worden gezien. In toekomstige versies worden meer communityfuncties geleverd en er kunnen ook aangepaste functies worden gemaakt.

>[!NOTE]
>
>De consoles voor het maken van [communitysites](sites-console.md), [communitysitesjablonen](sites.md), [communitygroepssjablonen](tools-groups.md) en [communityfuncties](functions.md) zijn alleen bedoeld voor gebruik in de auteursomgeving.

## Community-functieconsole {#community-functions-console}

In de auteursomgeving, om de console van communautaire functies te bereiken

* Vanuit globale navigatie: **[!UICONTROL Tools > Communities > Community Functions]**

![chlimage_1-379](assets/chlimage_1-379.png)

## Vooraf gebouwde functies {#pre-built-functions}

Hieronder volgt een korte beschrijving van de functies die bij AEM Communities worden geleverd. Elke functie bestaat uit een of meer AEM pagina&#39;s die onderdelen van een Community bevatten die zijn samengevoegd tot een functie die eenvoudig kan worden opgenomen in een [communitysjabloon](sites.md).

Een communitysitesjabloon biedt de structuur voor een communitysite, zoals aanmeldingsgegevens, gebruikersprofielen, meldingen, berichten, berichten, het menu van de site, zoeken, thema&#39;s en brandingfuncties.

### Instellingen voor Titel en URL {#title-and-url-settings}

**Eigenschappen** van  **** titel en URL zijn algemeen voor alle functies van de gemeenschap.

Wanneer een communautaire functie aan een malplaatje van de communautaire plaats wordt toegevoegd of wanneer [modifying](sites-console.md#modifying-site-properties) de structuur van een communautaire plaats wordt toegevoegd, opent de dialoog van de functie zodat de Titel en URL kunnen worden gevormd.

#### Details configuratiefunctie {#configuration-function-details}

![chlimage_1-380](assets/chlimage_1-380.png)

* **[!UICONTROL Title]**
(
*(vereist*) De tekst die wordt weergegeven in het menu met functies voor de site

* **[!UICONTROL URL]**
(*vereist*) De naam die wordt gebruikt om URI te genereren. De naam moet voldoen aan de [naamconventies](../../help/sites-developing/naming-conventions.md) die door AEM en JCR worden opgelegd.

Als u bijvoorbeeld de site gebruikt die u hebt gemaakt op basis van de zelfstudie [Aan de slag](getting-started.md), als

* Titel = webpagina
* URL = pagina

De URL naar de pagina is http://local_host:4503/content/sites/engage/en/page.html en de menukoppeling voor de pagina ziet er als volgt uit:

![chlimage_1-381](assets/chlimage_1-381.png)

### Functie activiteitsstroom {#activity-stream-function}

De functie van de activiteitenstroom is een pagina met een [component van de Streams van de Activiteit](activities.md) met alle geselecteerde meningen (alle activiteiten, gebruikersactiviteiten, en het volgende). Zie ook [De Hoofdzaak van de Stroom van de Activiteit](essentials-activities.md) voor ontwikkelaars.

Wanneer u een sjabloon toevoegt, wordt het volgende dialoogvenster geopend:

#### Details configuratiefunctie {#configuration-function-details-1}

![chlimage_1-382](assets/chlimage_1-382.png)

* Zie [Instellingen voor titel en URL](#title-and-url-settings)
* **[!UICONTROL Show "My Activities" view]**
Als deze optie is ingeschakeld, bevat de pagina Activiteiten een tabblad waarop de activiteiten worden gefilterd op basis van de activiteiten die door het huidige lid binnen de gemeenschap worden gegenereerd. Standaard is ingeschakeld.

* **[!UICONTROL Show "All Activities" view]**
Als deze optie is ingeschakeld, bevat de pagina Activiteiten een tabblad dat alle activiteiten bevat die zijn gegenereerd binnen de gemeenschap waartoe het huidige lid toegang heeft. Standaard is ingeschakeld.

* **[!UICONTROL Show "News Feed" view]**
Als deze optie is ingeschakeld, bevat de pagina Activiteiten een tabblad waarop de activiteiten worden gefilterd op basis van de activiteiten die het huidige lid volgt. Standaard is ingeschakeld.

### Toewijzingsfunctie {#assignments-function}

De toewijzingsfunctie is de basisfunctie die een [communitysite voor enablement](overview.md#enablement-community) definieert. Het maakt het mogelijk middelen voor activering toe te wijzen aan leden van de gemeenschap. Zie ook [Essentiële toewijzingen](essentials-assignments.md) voor ontwikkelaars.

Deze functie is beschikbaar als eigenschap van [enablement toe:voegen-on](enablement.md). De inschakelingsadd-on vereist aanvullende licenties voor gebruik in een productieomgeving.

Wanneer toegevoegd aan een malplaatje, is de enige configuratie voor [Titel en Montages URL](#title-and-url-settings).

### Blogfunctie {#blog-function}

De blogfunctie is een pagina met een [Blogcomponent](blog-feature.md) die is geconfigureerd voor codering, het uploaden van bestanden, na het bewerken, stemmen en modereren van bestanden. Zie ook [Blog Essentials](blog-developer-basics.md) voor ontwikkelaars.

Wanneer u een sjabloon toevoegt, wordt het volgende dialoogvenster geopend:

![chlimage_1-383](assets/chlimage_1-383.png)

* Zie [Instellingen voor titel en URL](#title-and-url-settings)
* **[!UICONTROL Allow Privileged Members]**
Als deze optie is ingeschakeld, staat de blog alleen geprivilegieerde leden toe artikelen te maken door de selectie van een groep [ ](users.md#privileged-members-group)geprivilegieerde leden toe te staan. Als deze optie niet is ingeschakeld, mogen alle leden van de gemeenschap het bestand maken. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow File Uploads]**
Als deze optie is ingeschakeld, bevat de blog de mogelijkheid voor leden om bestanden te uploaden. Standaard is ingeschakeld.

* **[!UICONTROL Allow Threaded Replies]**
Als deze optie niet is ingeschakeld, staat de blog reacties (opmerkingen) op een artikel toe, maar zijn reacties op opmerkingen niet toegestaan. Standaard is ingeschakeld.

* **[!UICONTROL Allow Featured Content]**
Als deze optie is ingeschakeld, kan het idee worden geïdentificeerd als  [aanbevolen inhoud](featured.md). Standaard is ingeschakeld.

### Kalenderfunctie {#calendar-function}

De kalenderfunctie is een pagina met een [agendacomponent](calendar.md) die wordt gevormd om het etiketteren toe te staan. Zie ook [Kalenderelementen](calendar-basics-for-developers.md) voor ontwikkelaars.

Wanneer u een sjabloon toevoegt, wordt het volgende dialoogvenster geopend:

![chlimage_1-384](assets/chlimage_1-384.png)

* Zie [Instellingen voor titel en URL](#title-and-url-settings)
* **[!UICONTROL Allow Pinning]**
Als deze optie is ingeschakeld, kunnen de reacties op onderwerpen worden vastgezet aan het begin van de lijst met opmerkingen. Standaard is ingeschakeld.

* **[!UICONTROL Allow Privileged Members]**
Als deze optie is ingeschakeld, staat de blog alleen geprivilegieerde leden toe artikelen te maken door de selectie van een groep [ ](users.md#privileged-members-group)geprivilegieerde leden toe te staan. Als deze optie niet is ingeschakeld, mogen alle leden van de gemeenschap het bestand maken. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow File Uploads]**
Als deze optie is ingeschakeld, bevat de blog de mogelijkheid voor leden om bestanden te uploaden. Standaard is ingeschakeld.

* **[!UICONTROL Allow Threaded Replies]**
Als deze optie niet is ingeschakeld, staat de blog reacties (opmerkingen) op een artikel toe, maar zijn reacties op opmerkingen niet toegestaan. Standaard is ingeschakeld.

* **[!UICONTROL Allow Featured Content]**
Als deze optie is ingeschakeld, kan het idee worden geïdentificeerd als  [aanbevolen inhoud](featured.md). Standaard is ingeschakeld.

### Catalogusfunctie {#catalog-function}

De catalogusfunctie verstrekt de capaciteit voor [enablement community](overview.md#enablement-community) leden om enablement middelen te doorbladeren die niet aan hen worden toegewezen. Zie [Tags toewijzen Bronnen](tag-resources.md) en [Grondbeginselen van catalogi](catalog-developer-essentials.md) voor ontwikkelaars.

Alle actiemiddelen en leerpaden voor de communautaire plaats zullen in alle catalogi tonen als hun bezit, ` [Show in Catalog](resources.md)`, aan waar wordt geplaatst. Als u expliciet bronnen en leerpaden wilt opnemen, moet u een [voorfilter](catalog-developer-essentials.md#pre-filters) toepassen op de catalogus.

Wanneer de configuratie aan een sjabloon is toegevoegd, kunt u met de configuratie tagnaamruimten opgeven die worden gebruikt om het tagfilter te configureren dat aan bezoekers van de site wordt aangeboden:

![catalogusfunctie](assets/catalogfunc.png)

* Zie [Instellingen voor titel en URL](#title-and-url-settings)
* **[!UICONTROL Select All Namespaces]**

   * Met de geselecteerde tagnaamruimten wordt gedefinieerd welke tags bezoekers kunnen selecteren voor het filteren van de lijst met activeringsbronnen die in de catalogus wordt vermeld.
   * Als deze optie is ingeschakeld, zijn alle naamruimten voor tags die zijn toegestaan voor de communitysite, beschikbaar.
   * Als deze optie uitgeschakeld is, is het mogelijk een of meer naamruimten te selecteren die zijn toegestaan voor de communitysite.
   * Standaard is ingeschakeld.

### Functie {#featured-content-function} aanbevolen inhoud

De functie voor aanbevolen inhoud is een pagina met een [component Aanbevolen inhoud](featured.md) geconfigureerd om opmerkingen toe te voegen en te verwijderen.

De mogelijkheid om inhoud te voorzien kan per component worden toegestaan of niet toegestaan (zie [Blogfunctie](#blog-function), [Kalenderfunctie](#calendar-function), [Forum Function](#forum-function), [Ideatiefunctie](#ideation-function) en [QnA Functie](#qna-function)).

Wanneer toegevoegd aan een malplaatje, is de enige configuratie voor [Titel en Montages URL](#title-and-url-settings).

### Bestandsbibliotheekfunctie {#file-library-function}

De functie van de dossierbibliotheek is een pagina met een [component van de Bibliotheek van het Dossier ](file-library.md) wordt gevormd om commentaren toe te staan om worden toegevoegd en worden geschrapt.

Wanneer toegevoegd aan een malplaatje, is de enige configuratie voor [Titel en Montages URL](#title-and-url-settings).

### Functie van forum {#forum-function}

De forumfunctie is een pagina met een [Forum-component](forum.md) die is geconfigureerd voor codering, het uploaden van bestanden, volgend op, leden die zichzelf moeten bewerken, stemmen en moderatie.

Wanneer u een sjabloon toevoegt, wordt het volgende dialoogvenster geopend:

#### Details configuratiefunctie {#configuration-function-details-2}

![chlimage_1-385](assets/chlimage_1-385.png)

* Zie [Instellingen voor titel en URL](#title-and-url-settings)
* **[!UICONTROL Allow Pinning]**
Als deze optie is ingeschakeld, kunnen de reacties op onderwerpen worden vastgezet aan het begin van de lijst met opmerkingen. Standaard is ingeschakeld.

* **[!UICONTROL Allow Privileged Members]**
Indien gecontroleerd, zal het forum bevoorrechte leden slechts toestaan om onderwerpen te posten door selectie van een  [bevoorrechte ledengroep](users.md#privileged-members-group) toe te staan. Als deze optie niet is ingeschakeld, mogen alle leden van de gemeenschap posten. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow File Uploads]**
Als deze optie is ingeschakeld, kunnen leden bestanden uploaden. Standaard is ingeschakeld.

* **[!UICONTROL Allow Threaded Replies]**
Als het forum niet wordt gecontroleerd, zal het commentaar op een onderwerp toestaan, maar antwoorden op die commentaren worden niet toegestaan. Standaard is ingeschakeld.

* **[!UICONTROL Allow Featured Content]**
Als deze optie is ingeschakeld, kan het idee worden geïdentificeerd als  [aanbevolen inhoud](featured.md). Standaard is ingeschakeld.

### Groepeert functie {#groups-function}

>[!CAUTION]
>
>De groepsfunctie moet *not* eerst of de enige functie *in de structuur van een plaats of in een malplaatje van de communautaire plaats zijn.*
>
>Elke andere functie, zoals de [paginafunctie](#page-function), moet worden opgenomen en als eerste worden vermeld.

De groepsfunctie biedt leden van de gemeenschap de mogelijkheid om subgemeenschappen binnen de gemeenschapssite in de publicatieomgeving te maken.

Afhankelijk van [settings](sites-console.md#groupmanagement) wanneer de functie van Groepen in [communityplaatsjabloon](sites.md) inbegrepen is, kunnen de groepen openbaar of privé zijn en één of meerdere malplaatjes van de communautaire groep kunnen worden gevormd om een keus van malplaatjes te verstrekken wanneer de communautaire groep eigenlijk wordt gecreeerd (zoals van het publicatiemilieu). Een [communitygroepsjabloon](tools-groups.md) geeft aan welke Gemeenschappen-functies worden gemaakt voor de groepspagina&#39;s, zoals forums en kalenders.

Wanneer een communautaire groep wordt gecreeerd, wordt een lidgroep dynamisch gecreeerd voor de nieuwe groep, waaraan de leden kunnen worden toegewezen of zich aansluiten. Zie [Gebruikers en gebruikersgroepen beheren](users.md) voor meer informatie.

Vanaf Communities [feature pack 1](deploy-communities.md#latestfeaturepack), worden communitygroepen gemaakt in de auteursomgeving met behulp van de [console Groepen van Communitysites](groups.md), en kunnen deze worden gemaakt in de publicatieomgeving wanneer deze is ingeschakeld.

Wanneer u een sjabloon toevoegt, wordt het volgende dialoogvenster geopend:

![chlimage_1-386](assets/chlimage_1-386.png)

* Zie [Instellingen voor titel en URL](#title-and-url-settings)
* **[!UICONTROL Select Group Templates]**
Een keuzemenu waarmee u een of meer ingeschakelde groepssjablonen kunt selecteren waaruit de toekomstige maker van een nieuwe communitygroep (in de publicatieomgeving) kan kiezen.

* **[!UICONTROL Allow Privileged Members]**
Indien gecontroleerd, zal het forum bevoorrechte leden slechts toestaan om onderwerpen te posten door selectie van een  [bevoorrechte groep](users.md#privileged-members-group) van de ledenveiligheid toe te staan. Als deze optie niet is ingeschakeld, mogen alle leden van de gemeenschap posten. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Publish Creation]**
Als deze optie is ingeschakeld, kunnen geautoriseerde leden van de gemeenschap een groep maken in de publicatieomgeving. Als deze optie niet is ingeschakeld, kunnen alleen nieuwe groepen (subgemeenschappen) worden gemaakt in de auteursomgeving via de console Groepen van de sites van de Gemeenschappen.

   De standaardwaarde is `checked`.

### Idealisatiefunctie {#ideation-function}

De videofunctie is een pagina met één [Ideeringscomponent](ideation-feature.md).

Wanneer u een sjabloon toevoegt, wordt het volgende dialoogvenster geopend met de standaardnamen voor Titel en URL en de standaardweergave-instellingen voor de sjabloon:

![chlimage_1-387](assets/chlimage_1-387.png)

* Zie [Instellingen voor titel en URL](#title-and-url-settings)
* **[!UICONTROL Allow Privileged Members]**
Indien gecontroleerd, zal het forum bevoorrechte leden slechts toestaan om onderwerpen te posten door selectie van een  [bevoorrechte groep](users.md#privileged-members-group) van de ledenveiligheid toe te staan. Als deze optie niet is ingeschakeld, mogen alle leden van de gemeenschap posten. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow File Uploads]**
Als deze optie is ingeschakeld, kunnen leden bestanden uploaden. Standaard is ingeschakeld.

* **[!UICONTROL Allow Threaded Replies]**
Als deze optie niet is ingeschakeld, is het mogelijk om antwoorden (opmerkingen) op een onderwerp toe te staan, maar om opmerkingen te beantwoorden is het niet toegestaan. Standaard is ingeschakeld.

* **[!UICONTROL Allow Featured Content]**
Als deze optie is ingeschakeld, kan het idee worden geïdentificeerd als  [aanbevolen inhoud](featured.md). Standaard is ingeschakeld.

### Leaderboard-functie {#leaderboard-function}

De leaderboard-functie is een pagina met één [Leaderboard-component](enabling-leaderboard.md).

**OPMERKING**: De Leaderboard-component moet verder worden geconfigureerd  ** nadat een communitysite is gemaakt op basis van een communitysjabloon die de Leaderboard-functie bevat. De [regels](enabling-leaderboard.md#rules-tab) van de component Leaderboard moeten worden gespecificeerd, die van configuratie van [scoring en badges](implementing-scoring.md) voor de communautaire plaats afhangen.

Wanneer u een sjabloon toevoegt, wordt het volgende dialoogvenster geopend met de standaardnamen voor Titel en URL en de standaardweergave-instellingen voor de sjabloon:

![chlimage_1-388](assets/chlimage_1-388.png)

* Zie [Instellingen voor titel en URL](#title-and-url-settings)
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

De paginafunctie voegt een lege pagina aan de communautaire plaats toe dat het in de eigenschappen van de communautaire plaats wordt getelegrafeerd: aanmelden, menu, meldingen, berichten, berichten, thema&#39;s en branding. Inhoud kan aan de pagina worden toegevoegd met de standaardontwerpmodus [AEM](../../help/sites-authoring/editing-content.md).

Wanneer toegevoegd aan een malplaatje, is de enige configuratie voor [Titel en Montages URL](#title-and-url-settings).

### QnA-functie {#qna-function}

De functie QnA is een pagina met een [component QnA](working-with-qna.md) die voor het etiketteren wordt gevormd, dossier uploadt, volgende, leden aan zelf-uitgeven, stemmen, en matiging.

Wanneer toegevoegd aan een malplaatje, staat de configuratie beperking aan bevoorrechte leden toe:

![chlimage_1-389](assets/chlimage_1-389.png)

* Zie [Instellingen voor titel en URL](#title-and-url-settings)
* **[!UICONTROL Allow Pinning]**
Als deze optie is ingeschakeld, kunnen de reacties op onderwerpen worden vastgezet aan het begin van de lijst met opmerkingen. Standaard is ingeschakeld.

* **[!UICONTROL Allow Privileged Members]**
Indien gecontroleerd, zal het forum QnA bevoorrechte leden slechts toestaan om vragen te posten door selectie van een  [bevoorrechte ledengroep](users.md#privileged-members-group) toe te staan. Als deze optie niet is ingeschakeld, mogen alle leden van de gemeenschap posten. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow File Uploads]**
Als deze optie is ingeschakeld, bevat het QnA-forum de mogelijkheid voor leden om bestanden te uploaden. Standaard is ingeschakeld.

* **[!UICONTROL Allow Threaded Replies]**
Als het QnA-forum niet wordt gecontroleerd, kan er commentaar (antwoorden) worden gegeven op een geposte vraag, maar antwoorden op antwoorden zijn niet toegestaan. Standaard is ingeschakeld.

* **[!UICONTROL Allow Featured Content]**
Als deze optie is ingeschakeld, kan het idee worden geïdentificeerd als  [aanbevolen inhoud](featured.md). Standaard is ingeschakeld.

## Community-functie maken {#create-community-function}

De capaciteit om een communautaire functie tot stand te brengen wordt bereikt door het `Create Community Function` pictogram te selecteren dat bij de bovenkant van de console van de Functies van de Gemeenschap wordt gevestigd. Er kunnen meerdere functies worden gemaakt die op dezelfde AEM blauwdruk zijn gebaseerd en vervolgens op unieke wijze worden aangepast door het openen in de bewerkingsmodus voor auteurs.

![chlimage_1-390](assets/chlimage_1-390.png)

### Naam communautaire functie {#community-function-name}

![chlimage_1-391](assets/chlimage_1-391.png)

In het deelvenster Community Function Name worden een naam, beschrijving en of de functie is ingeschakeld of uitgeschakeld geconfigureerd:

* **[!UICONTROL Community Function Name]**
De functienaam die wordt gebruikt voor weergave en opslag

* **[!UICONTROL Community Function Description]**
De functiebeschrijving voor de weergave

* **[!UICONTROL Disabled/Enabled]**
Een schakeloptie die bepaalt of de functie waarnaar wordt verwezen

### AEM blauwdruk {#aem-blueprint}

![chlimage_1-392](assets/chlimage_1-392.png)

In het `AEM Blueprint` paneel, is het mogelijk om de blauwdruk te selecteren die de onderliggende implementatie van de communautaire functie is.

De functie van de gemeenschap is een mini plaats die uit één of meerdere pagina&#39;s wordt samengesteld, die voor opneming in een communautaire plaats met inbegrip van login, gebruikersprofielen, berichten, overseinen, plaatsmenu, onderzoek, het thema, en branding eigenschappen vooraf wordt getelegrafeerd. Als de functie eenmaal is gemaakt, is het mogelijk om de functie [te openen in de modus Bewerken door schrijver en de pagina- en/of componentinstellingen aan te passen.](#open-community-function)

Aangezien de communautaire functie als [levende exemplaar](../../help/sites-administering/msm.md#live-copies) van een [blauwdruk](../../help/sites-administering/msm-livecopy.md#creatingablueprint) wordt uitgevoerd, is het mogelijk om veranderingen uit te voeren die aan een functie worden aangebracht die alle communautaire plaatspagina&#39;s beïnvloedt die van [communitymalplaatje](sites.md) of [communitygroepmalplaatje](tools-groups.md) worden gecreeerd die de functie omvatte. Het is ook mogelijk om een pagina los te koppelen van de bovenliggende blauwdruk om wijzigingen op paginaniveau aan te brengen.

Zie ook [Beheer van meerdere sites](../../help/sites-administering/msm.md).

### Miniatuur {#thumbnail}

![chlimage_1-393](assets/chlimage_1-393.png)

In het venster Miniatuur kan een afbeelding worden geüpload om te worden weergegeven in de [Community Functions console](#community-functions-console).

## Community-functie openen {#open-community-function}

![chlimage_1-394](assets/chlimage_1-394.png)

Selecteer het pictogram `Open Community Function` om de bewerkingsmodus voor auteurs in te schakelen voor het ontwerpen van de pagina-inhoud en het wijzigen van de configuratie van de component(en) met functies.

### Componenten {#configuring-components} configureren

Een communautaire functie wordt uitgevoerd als Levende Kopie van een AEM Blauwdruk, details waarvan onder [Multisite Manager](../../help/sites-administering/msm.md) worden gedocumenteerd.

Het is mogelijk om niet alleen pagina-inhoud te schrijven, maar componenten te configureren.

Als het vormen van een component op een pagina van een gecreeerde communautaire plaats, kan het noodzakelijk zijn [overerving ](../../help/sites-administering/msm-livecopy.md#changing-live-copy-content) te annuleren om de component te vormen. De overerving moet worden hersteld wanneer de configuratie is voltooid.

Voor configuratiedetails, bezoek [Communities Components](author-communities.md) voor auteurs.

## Community-functie bewerken {#edit-community-function}

![chlimage_1-395](assets/chlimage_1-395.png)

Selecteer het pictogram `Edit Community Function` om de eigenschappen van de functie uit te geven gebruikend de zelfde panelen zoals [creërend een communautaire functie](#create-community-function), met inbegrip van het toelaten of onbruikbaar maken van de functie.
