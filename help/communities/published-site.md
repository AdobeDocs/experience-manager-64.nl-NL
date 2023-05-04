---
title: Ervaar de gepubliceerde site
seo-title: Experience the Published Site
description: Naar een gepubliceerde site bladeren
seo-description: Browse to a published site
uuid: f510224c-d991-4528-864d-44672138740c
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: introduction
content-type: reference
discoiquuid: 4dc54701-68b9-49dd-a212-b0b53330c1c0
exl-id: 8f716a59-1116-4855-baeb-3997de71b55f
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1158'
ht-degree: 0%

---

# Ervaar de gepubliceerde site {#experience-the-published-site}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

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

## Anonieme toegang tot JCR voorkomen {#prevent-anonymous-access-on-jcr}

Een bekende beperking stelt de inhoud van de communautaire site aan anonieme bezoekers via jcr-inhoud en json bloot, hoewel **anonieme toegang toestaan** is uitgeschakeld voor de inhoud van de site. Nochtans, kan dit gedrag worden gecontroleerd gebruikend de Beperkingen van het Schuiven als oplossing.

Voer de volgende stappen uit om de inhoud van uw site te beschermen tegen toegang door anonieme gebruikers via jcr-inhoud en json:

1. Ga in AEM Author-instantie naar https://&lt;host>:&lt;port>/editor.html/content/site/&lt;sitename>.html.

   >[!NOTE]
   >
   >Ga niet naar de gelokaliseerde site.

1. Ga naar **[!UICONTROL Page Properties]**.

   ![plaatsverificatie](assets/site-authentication.png)

1. Ga naar **[!UICONTROL Advanced]** tab.

   ![page-eigenschappen](assets/page-properties.png)

1. Inschakelen **[!UICONTROL Authentication Requirement]**.
1. Voeg het pad van de aanmeldingspagina toe. Bijvoorbeeld, `/content/......./GetStarted`.
1. Publiceer de pagina.

## Vertrouwd lid van de Gemeenschap {#trusted-community-member}

Deze ervaring gaat uit van [Aaron McDonald](tutorials.md#demo-users) is toegewezen aan de rollen van [gemeenschapsbeheerder en moderator](create-site.md#roles). Zo niet, ga dan terug naar de auteursomgeving [de site-instellingen wijzigen](sites-console.md#modifying-site-properties) en selecteer Aaron McDonald als gemeenschapsleider en moderator.

Selecteer in de rechterbovenhoek de optie `Log in`en meld u aan met gebruikersnaam &quot;aaron.mcdonald@mailinator.com&quot; en wachtwoord &quot;password&quot;. Meld u aan met Twitter- of Facebook-referenties.

![chlimage_1-312](assets/chlimage_1-312.png)

Nadat u zich hebt aangemeld, ziet u een nieuw menu-item. `Administration`, hetgeen blijkt uit het feit dat het lid de rol van Moderator kreeg. Het selecteren van verschillende koppelingen is nu interessanter.

![chlimage_1-313](assets/chlimage_1-313.png)

U ziet dat de kalenderpagina de startpagina is omdat de gekozen Sjabloon Referentie-site eerst de kalenderfunctie bevatte, gevolgd door de functie Activiteitenstroom, de functie Forum, enzovoort. Deze structuur is zichtbaar vanuit de [Sitesjabloon](sites.md#edit-site-template) console of bij het wijzigen van site-eigenschappen in de ontwerpomgeving:

![chlimage_1-314](assets/chlimage_1-314.png)

>[!NOTE]
>
>Ga voor meer informatie over communautaire componenten en functies naar
>
>* [Community-componenten](author-communities.md) (voor auteurs)
>* [Component, Function en Feature Essentials](essentials.md) (voor ontwikkelaars)
>


## Forum-koppeling {#forum-link}

U kunt de standaardfunctie voor forums weergeven door de koppeling Forum te selecteren.

Leden kunnen een nieuw onderwerp plaatsen of een onderwerp volgen.

Sitebezoekers kunnen artikelen weergeven en op verschillende manieren sorteren.

![chlimage_1-315](assets/chlimage_1-315.png)

## Groepen koppelen {#groups-link}

Aangezien Aaron een groepsbeheerder is, zal het selecteren van de verbinding van Groepen Aaron toestaan om een nieuwe communautaire groep tot stand te brengen door een groepsmalplaatje, beeld te selecteren, of de groep open of geheim is, en het uitnodigen van leden.

Dit is een voorbeeld waarin een groep wordt gemaakt in de publicatieomgeving.

Groepen kunnen ook worden gemaakt in de auteursomgeving en worden beheerd binnen de communitysite in de ontwerpomgeving (de [Community Group-console](groups.md)). De ervaring van [groepen maken op auteur](nested-groups.md) is volgende in deze zelfstudie.

![chlimage_1-316](assets/chlimage_1-316.png)

Een referentiegroep maken:

1. Selecteer **[!UICONTROL New Group]**
1. **[!UICONTROL Settings tab]**
   * Groepsnaam: `Sports`
   * Beschrijving: `A parent group for various sporting groups`
   * Groepsnaam URL: `sports`
   * selecteren `Open Group` ( elk lid van de gemeenschap toestaan deel te nemen door lid te worden )
1. **[!UICONTROL Template tab]**
   * Selecteren `Reference Group` (bevat een groepfunctie in de structuur om geneste groepen toe te staan)
1. Selecteer **[!UICONTROL Create Group]**

![chlimage_1-317](assets/chlimage_1-317.png)

Nadat nieuwe groep is gemaakt, **Selecteer de nieuwe groep Sport** om er twee (geneste) groepen in te maken. Aangezien een sitestructuur niet kan beginnen met de groepsfunctie, moet u na het openen van de Sportgroep de koppeling Groepen selecteren:

![chlimage_1-318](assets/chlimage_1-318.png)

De tweede set koppelingen, te beginnen met `Blog`, behoren tot de momenteel geselecteerde groep, `Sports`groep. Door de Sport te selecteren&#39; `Groups` kunnen twee groepen in de groep Sport worden genest.

Voeg bijvoorbeeld twee n toe `ew groups.`

* Eén naam `Baseball`
   * Laat het als een `Open Group` (vereist lidmaatschap)
   * Selecteer op het tabblad Sjablonen de optie `Conversational Group`
* Eén naam `Gymnastics`
   * De instelling wijzigen in `Member Only Group` (beperkt lidmaatschap)
   * Selecteer op het tabblad Sjablonen de optie `Conversational Group`

**Kennisgeving**:

* Mogelijk moet de pagina worden vernieuwd voordat beide groepen worden weergegeven
* This template does *not *include the groups function, so no more nesting of groups will be unable
* Op auteur: [Groepsconsole](groups.md) biedt een derde keuze - a `Public Group` (optioneel lidmaatschap)

Nadat beide groepen zijn gemaakt, selecteert u de Baseball-groep, een open groep en ziet u de koppelingen: `Discussions` `What's New` `Members`
De koppelingen van de groep worden weergegeven onder de koppelingen van de hoofdsite en resulteren in de volgende weergave:

![chlimage_1-319](assets/chlimage_1-319.png)

Navigeer bij de auteur - met beheerdersrechten naar de [console Gemeenschappen-groepen](members.md) en voegt Weston McCall toe aan de `Community Engage Gymnastics <uid> Members` groep.

Als u doorgaat met publiceren, meldt u zich af als Aaron McDonald en bekijkt u de groepen in de Sports Group als anonieme bezoeker van de site:

* Van homepage
* Selecteren `Groups`link
* Selecteren `Sports`link
* Selecteer de Sport&#39; `Groups`link

Alleen de Baseball-groep is zichtbaar.

Meld u aan bij Weston McCall (weston.mccall@dodgit.com / wachtwoord) en navigeer naar dezelfde locatie. Let op: Weston kan `Join` open `Baseball` groep en `enter or Leave` particuliere `Gymnastics`groep.

![chlimage_1-320](assets/chlimage_1-320.png)

## Koppeling naar webpagina {#web-page-link}

Selecteer de koppeling Webpagina om de basiswebpagina weer te geven die in de site is opgenomen. U kunt de standaardinstellingen AEM de ontwerpgereedschappen gebruiken om inhoud aan deze pagina toe te voegen in de ontwerpomgeving.

Ga bijvoorbeeld naar **auteur** -instantie, opent u de `engage` in de [Community Sites-console](sites-console.md), selecteert u de **Site openen** pictogram om de bewerkingsmodus voor auteurs te activeren. Selecteer vervolgens de voorvertoningsmodus om de optie `Web Page`en selecteert u vervolgens de bewerkingsmodus om de componenten Titel en Tekst toe te voegen. Ten slotte publiceert u alleen de pagina of de hele site opnieuw.

![chlimage_1-321](assets/chlimage_1-321.png)

## Beheerkoppeling {#administration-link}

Wanneer het lid van de gemeenschap moderatie voorrechten heeft, dan zal de verbinding van het Beleid zichtbaar zijn en het selecteren van het zal de geposte communautaire inhoud tonen en het toestaan om te zijn [gematigd](moderate-ugc.md) op een wijze die vergelijkbaar is met die van [moderatieconsole](moderation.md) in de ontwerpomgeving.

Gebruik de knop Vorige van de browser om terug te keren naar de gepubliceerde site. De meeste consoles zijn niet toegankelijk via globale navigatie in de publicatieomgeving.

![chlimage_1-322](assets/chlimage_1-322.png)

## Zelfregistratie {#self-registration}

Nadat u zich hebt afgemeld, kunt u een nieuwe gebruikersregistratie maken.

* Selecteer `Log In`
* Selecteer `Sign up for a new account`

![chlimage_1-323](assets/chlimage_1-323.png) ![chlimage_1-324](assets/chlimage_1-324.png)

Standaard is het e-mailadres de aanmeldings-id. Als deze optie is uitgeschakeld, kan de bezoeker zijn of haar eigen aanmeldings-id (gebruikersnaam) invoeren. De gebruikersnaam moet uniek zijn in de publicatieomgeving.

Nadat u de naam, het e-mailadres en het wachtwoord van de gebruiker hebt opgegeven, selecteert u `Sign Up`wordt de gebruiker gemaakt en kan deze ondertekenen.

Na aanmelding is de eerste weergegeven pagina `Profile`pagina, die ze kunnen aanpassen.

![chlimage_1-325](assets/chlimage_1-325.png)

Als het lid zijn aanmeldings-id vergeet, wordt het e-mailadres gebruikt.

![chlimage_1-326](assets/chlimage_1-326.png)
