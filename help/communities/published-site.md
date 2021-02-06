---
title: Ervaar de gepubliceerde site
seo-title: Ervaar de gepubliceerde site
description: Naar een gepubliceerde site bladeren
seo-description: Naar een gepubliceerde site bladeren
uuid: f510224c-d991-4528-864d-44672138740c
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: introduction
content-type: reference
discoiquuid: 4dc54701-68b9-49dd-a212-b0b53330c1c0
translation-type: tm+mt
source-git-commit: 63001012f0d865c2548703ea387c780679128ee7
workflow-type: tm+mt
source-wordcount: '1131'
ht-degree: 0%

---


# Geniet van de gepubliceerde site {#experience-the-published-site}

## Bladeren naar nieuwe site bij publicatie {#browse-to-new-site-on-publish}

Nu de nieuwe site voor gemeenschappen is gepubliceerd, bladert u naar de URL die wordt weergegeven bij het maken van de site, maar naar de publicatieserver, bijvoorbeeld

* Auteur-URL = http://localhost:4502/content/sites/engage/en.html
* URL publiceren = http://localhost:4503/content/sites/engage/en.html

Om verwarring over welk lid bij auteur en publicatie is aangemeld, te minimaliseren, wordt aangeraden voor elke instantie verschillende browsers te gebruiken.

Wanneer de bezoeker van de site voor het eerst op de gepubliceerde site aankomt, is deze doorgaans nog niet aangemeld en is de site anoniem.

## http://localhost:4503/content/sites/engage/en.html {#http-localhost-content-sites-engage-en-html}

![chlimage_1-311](assets/chlimage_1-311.png)

## Anonieme sitebezoeker {#anonymous-site-visitor}

Een anonieme sitebezoeker ziet het volgende in de gebruikersinterface:

* Titel van de site. Aan de slag - zelfstudie
* Geen profielkoppeling
* Geen berichtenkoppeling
* Geen koppeling voor meldingen
* Zoekveld
* Koppeling met aanmelden
* De merkbanner
* Menukoppelingen voor de componenten die zijn opgenomen in het referentiesjabloon voor de site

Als u verschillende koppelingen selecteert, bevindt de modus Alleen-lezen zich.

## Anonieme toegang tot JCR {#prevent-anonymous-access-on-jcr} voorkomen

Een bekende beperking stelt de inhoud van de communautaire plaats aan anonieme bezoekers door jcr inhoud en json bloot, hoewel **anonieme toegang toestaan** voor de inhoud van de plaats gehandicapt is. Nochtans, kan dit gedrag worden gecontroleerd gebruikend de Beperkingen van het Schuiven als oplossing.

Voer de volgende stappen uit om de inhoud van uw site te beschermen tegen toegang door anonieme gebruikers via jcr-inhoud en json:

1. Ga naar https://&lt;host>:&lt;port>/editor.html/content/site/&lt;sitename>.html voor een AEM-auteur-exemplaar.

   >[!NOTE]
   >
   >Ga niet naar de gelokaliseerde site.

1. Ga naar **[!UICONTROL Page Properties]**.

   ![plaatsverificatie](assets/site-authentication.png)

1. Ga naar **[!UICONTROL Advanced]** tabblad.

   ![page-eigenschappen](assets/page-properties.png)

1. **[!UICONTROL Authentication Requirement]** inschakelen.
1. Voeg het pad van de aanmeldingspagina toe. Bijvoorbeeld, `/content/......./GetStarted`.
1. Publiceer de pagina.

## Vertrouwd communautair lid {#trusted-community-member}

Deze ervaring veronderstelt [Aaron McDonald](tutorials.md#demo-users) de rollen van [gemeenschapsmanager en moderator](create-site.md#roles) werd toegewezen. Als dat niet het geval is, gaat u terug naar de auteursomgeving om [de site-instellingen te wijzigen](sites-console.md#modifying-site-properties) en selecteert u Aaron McDonald als zowel communitymanager als moderator.

Selecteer in de rechterbovenhoek `Log in` en onderteken met gebruikersnaam &quot;aaron.mcdonald@mailinator.com&quot; en wachtwoord &quot;password&quot;. Meld u aan met de Twitter- of Facebook-referenties.

![chlimage_1-312](assets/chlimage_1-312.png)

Zodra ondertekend binnen, merk op is er een nieuw menupunt, `Administration`, dat verschijnt omdat het lid de rol van Moderator werd gegeven. Het selecteren van verschillende koppelingen is nu interessanter.

![chlimage_1-313](assets/chlimage_1-313.png)

U ziet dat de kalenderpagina de startpagina is omdat de gekozen Sjabloon Referentie-site eerst de kalenderfunctie bevatte, gevolgd door de functie Activiteitenstroom, de functie Forum, enzovoort. Deze structuur is zichtbaar vanuit de console [Sitesjabloon](sites.md#edit-site-template) of wanneer u site-eigenschappen wijzigt in de auteursomgeving:

![chlimage_1-314](assets/chlimage_1-314.png)

>[!NOTE]
>
>Ga voor meer informatie over communautaire componenten en functies naar
>
>* [Community Components](author-communities.md)  (voor auteurs)
>* [Component, Function en Feature Essentials](essentials.md)  (voor ontwikkelaars)

>



## Forum link {#forum-link}

U kunt de standaardfunctie voor forums weergeven door de koppeling Forum te selecteren.

Leden kunnen een nieuw onderwerp plaatsen of een onderwerp volgen.

Sitebezoekers kunnen artikelen weergeven en op verschillende manieren sorteren.

![chlimage_1-315](assets/chlimage_1-315.png)

## Groepskoppeling {#groups-link}

Aangezien Aaron een groepsbeheerder is, zal het selecteren van de verbinding van Groepen Aaron toestaan om een nieuwe communautaire groep tot stand te brengen door een groepsmalplaatje, beeld te selecteren, of de groep open of geheim is, en het uitnodigen van leden.

Dit is een voorbeeld waarin een groep wordt gemaakt in de publicatieomgeving.

Groepen kunnen ook in de auteursomgeving worden gecreeerd en binnen de communautaire plaats in het auteursmilieu ([Community Groepen console](groups.md)) worden beheerd. De ervaring van [het creëren van groepen op auteur](nested-groups.md) is daarna in dit leerprogramma.

![chlimage_1-316](assets/chlimage_1-316.png)

Een referentiegroep maken:

1. Selecteer **[!UICONTROL New Group]**
1. **[!UICONTROL Settings tab]**
   * Groepsnaam: `Sports`
   * Beschrijving: `A parent group for various sporting groups`
   * Groepsnaam URL: `sports`
   * Selecteer `Open Group` (een lid van de gemeenschap toestaan om deel te nemen door lid te worden van de gemeenschap)
1. **[!UICONTROL Template tab]**
   * Selecteer `Reference Group` (bevat een groepfunctie in zijn structuur om geneste groepen toe te staan)
1. Selecteer **[!UICONTROL Create Group]**

![chlimage_1-317](assets/chlimage_1-317.png)

Nadat de nieuwe groep wordt gecreeerd, **selecteer de nieuwe Groep van Sport** om twee (genestelde) binnen tot stand te brengen groepen. Aangezien een sitestructuur niet kan beginnen met de groepsfunctie, moet u na het openen van de Sportgroep de koppeling Groepen selecteren:

![chlimage_1-318](assets/chlimage_1-318.png)

De tweede set koppelingen, die begint met `Blog`, behoort tot de momenteel geselecteerde groep, de `Sports`groep. Door de verbinding `Groups` van Sport te selecteren, is het mogelijk om twee groepen binnen de groep van Sport te nesten.

Voeg bijvoorbeeld twee n `ew groups.` toe

* Een met de naam `Baseball`
   * Laat deze ingesteld staan als een `Open Group` (vereist lidmaatschap)
   * Selecteer op het tabblad Sjablonen `Conversational Group`
* Een met de naam `Gymnastics`
   * Wijzig de instelling in `Member Only Group` (beperkt lidmaatschap)
   * Selecteer op het tabblad Sjablonen `Conversational Group`

**Opmerking**:

* Mogelijk moet de pagina worden vernieuwd voordat beide groepen worden weergegeven
* This template does *not *include the groups function, so no more nesting of groups will be unable
* Bij de auteur biedt de [Groepenconsole](groups.md) een derde keuze - een `Public Group` (optioneel lidmaatschap)

Nadat beide groepen zijn gemaakt, selecteert u de Baseball-groep, een open groep en ziet u de koppelingen: `Discussions` `What's New` `Members`
De koppelingen van de groep worden weergegeven onder de koppelingen van de hoofdsite en resulteren in de volgende weergave:

![chlimage_1-319](assets/chlimage_1-319.png)

Op auteur - met administratieve voorrechten, navigeer aan [de Groepen van Gemeenschappen console](members.md) en voeg Weston McCall aan `Community Engage Gymnastics <uid> Members` groep toe.

Als u doorgaat met publiceren, meldt u zich af als Aaron McDonald en bekijkt u de groepen in de Sports Group als anonieme bezoeker van de site:

* Van homepage
* `Groups`koppeling selecteren
* `Sports`koppeling selecteren
* Selecteer de verbinding `Groups`van de Sport

Alleen de Baseball-groep is zichtbaar.

Meld u aan bij Weston McCall (weston.mccall@dodgit.com / wachtwoord) en navigeer naar dezelfde locatie. Let op: Weston kan de open `Baseball` groep `enter or Leave` en de private `Gymnastics`groep `Join` &lt;a3.

![chlimage_1-320](assets/chlimage_1-320.png)

## Koppeling naar webpagina {#web-page-link}

Selecteer de koppeling Webpagina om de basiswebpagina weer te geven die in de site is opgenomen. U kunt de standaardinstellingen AEM de ontwerpgereedschappen gebruiken om inhoud aan deze pagina toe te voegen in de ontwerpomgeving.

Ga bijvoorbeeld naar **auteur**-instantie, open de map `engage` in de [Community Sites-console](sites-console.md), selecteer het pictogram **Site openen** om de modus Schrijver bewerken te activeren. Selecteer vervolgens de voorvertoningsmodus om de koppeling `Web Page`te selecteren en selecteer vervolgens de bewerkingsmodus om de componenten Titel en Tekst toe te voegen. Ten slotte publiceert u alleen de pagina of de hele site opnieuw.

![chlimage_1-321](assets/chlimage_1-321.png)

## Koppeling {#administration-link} beheren

Wanneer het communitylid moderatievoorrechten heeft, dan zal de verbinding van het Beleid zichtbaar zijn en het selecteren zal de geposte communautaire inhoud tonen en het toestaan om [gematigd](moderate-ugc.md) op een manier gelijkend op [moderatieconsole](moderation.md) in het auteursmilieu te zijn.

Gebruik de knop Vorige van de browser om terug te keren naar de gepubliceerde site. De meeste consoles zijn niet toegankelijk via globale navigatie in de publicatieomgeving.

![chlimage_1-322](assets/chlimage_1-322.png)

## Zelfregistratie {#self-registration}

Nadat u zich hebt afgemeld, kunt u een nieuwe gebruikersregistratie maken.

* Selecteer `Log In`
* Selecteer `Sign up for a new account`

![chlimage_1-323](assets/chlimage_1-323.png) ![chlimage_1-324](assets/chlimage_1-324.png)

Standaard is het e-mailadres de aanmeldings-id. Als deze optie is uitgeschakeld, kan de bezoeker zijn of haar eigen aanmeldings-id (gebruikersnaam) invoeren. De gebruikersnaam moet uniek zijn in de publicatieomgeving.

Als u `Sign Up`de naam, het e-mailadres en het wachtwoord van de gebruiker hebt opgegeven, wordt de gebruiker gemaakt en kunnen deze worden ondertekend.

Nadat u zich hebt aangemeld, is de eerste pagina die wordt weergegeven hun `Profile`pagina, die zij kunnen aanpassen.

![chlimage_1-325](assets/chlimage_1-325.png)

Als het lid zijn aanmeldings-id vergeet, wordt het e-mailadres gebruikt.

![chlimage_1-326](assets/chlimage_1-326.png)
