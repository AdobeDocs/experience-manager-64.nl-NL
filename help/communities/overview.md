---
title: AEM Communities - Overzicht
seo-title: AEM Communities - Overzicht
description: Een overzicht van AEM Communities-functies en -instellingen
seo-description: Een overzicht van AEM Communities-functies en -instellingen
uuid: 6e3ac9d2-ca31-40ea-8cab-b8451074c498
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 418cc919-0ae3-4c6c-8566-7e9a206f02a8
translation-type: tm+mt
source-git-commit: 1375282df15b1a1a1ab5ed760190af8d6288970e
workflow-type: tm+mt
source-wordcount: '1407'
ht-degree: 0%

---


# AEM Communities-overzicht {#aem-communities-overview}

Adobe Experience Manager (AEM) Communities biedt de mogelijkheid om snel een lokale community-site te maken die de prestaties verbetert, het sitebeheer verbetert en de conversie van sitebezoekers naar waardevolle leden van de community aanmoedigt.

<!--
Contact your account representative for information regarding licensing of AEM Communities as well as additional licensing for enablement features and Adobe Analytics.
-->

## Functies {#communities-features} van Gemeenschappen

AEM Communities maakt het mogelijk om een relatie te ontwikkelen met sitebezoekers die informatie geven via blogs, vragen en antwoorden en gebeurtenissencalenders, terwijl ze inzichten krijgen via forums, opmerkingen en andere community-inhoud, die vaak UGC (door gebruikers gegenereerde inhoud) wordt genoemd.

Verder maakt AEM Communities moderatie door vertrouwde leden in de publicatieomgeving mogelijk, sociale aanmelding bij Twitter en Facebook, inlinevertaling van community-inhoud, het maken van communitygroepen vanaf de gepubliceerde communitysite, het scoren naar onderscheidingstempels, het delen van bestanden, meldingen en activiteitenstreams.

De eigenschappen van gemeenschappen kunnen worden aangetoond gebruikend [AEM demovermachine](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki) openbaar op GitHub.com of met de nieuwe Wij.Retail verwijzingsimplementatie beschikbaar.

## Community-sites {#community-sites}

Een communitysite is een AEM site die is gemaakt met een eenvoudige wizard die resulteert in een website met veel algemene functies die vooraf zijn getelegrafeerd naar de site.

De wizard [Site maken](sites-console.md):

* Verzamelt kenmerken van de site op basis van de geselecteerde [communitysjabloon](sites.md) die is
   * Gemaakt op basis van [communityfuncties](#community-functions)
   * Optionele [community groups](#communitygroups)-functie
* Gebruikt te configureren instellingen:
   * Moderatie
   * Aanmelden
   * Vertaling
* Biedt essentiële functies:
   * Responsief ontwerp: Gebruikt [Twitter-Bootstrap-thema&#39;s](https://getbootstrap.com)
   * Aanmelden: Zelfregistratie, [sociale aanmelding](social-login.md), gebruikersprofielen
   * Meldingen: De leden zien gebeurtenissen die voor hen van belang zijn
   * Berichten: Leden kunnen berichten verzenden of ontvangen op de site van de community
   * Zoeken: Mogelijkheid om te zoeken op de site van de community
   * Taalomschakeling: Mogelijkheid om een taal te selecteren voor een [meertalige site](../../help/sites-administering/translation.md)
   * Beheer: Toegang voor geautoriseerde leden om gebruikers binnen de community te matigen en te beheren
* Hiermee verwijdert u veel ontwerpstappen op paginaniveau:
   * Branding: Optionele upload van een bannerafbeelding voor weergave op alle pagina&#39;s van de communitysite
   * Navigatiemenu: Navigatiekoppelingen zijn beschikbaar voor de functies die zijn opgenomen in het sjabloon voor de communautaire site

Als u snel een nieuwe communitysite wilt maken, gaat u naar [Aan de slag met AEM Communities](getting-started.md).

## Persistentie voor communautaire inhoud {#community-content-persistence}

Om de prestaties en synchronisatie van inhoud van de gebruikersgemeenschap te verbeteren, vereist AEM Communities een gemeenschappelijke opslag specifiek voor gebruiker geproduceerde inhoud (UGC) die tussen alle AEM (auteur en publiceer) instanties wordt gedeeld.

De communautaire inhoud wordt gemakkelijk betreden door de leverancier van het opslagmiddel (SRP), die een laag verstrekt om toegang van de onderliggende topologie te scheiden en een gemeenschappelijke opslag voor UGC steunt.

Ga voor meer informatie over de persistentie en aanbevolen implementaties van community-inhoud naar:

* [Opslag](working-with-srp.md) voor community-inhoud: bespreekt de beschikbare opslagopties SRP voor UGC
* [Aanbevolen technologieën](topologies.md): bespreekt topologieën die op gebruiksgeval en keus SRP worden gebaseerd
* [Opwaarderen naar AEM 6.3 Gemeenschappen](upgrade.md): biedt nuttige informatie over UGC bij de overgang naar AEM 6.3.

## Communityconsoles {#communities-consoles}

In de auteursomgeving, verleent de globale navigatieconsole toegang tot [Communities console](consoles.md), die bevat:

* [](sites-console.md) Sitesconsole

   * Site maken
   * Site bewerken
   * Sitebeheer
   * [Community ](groups.md) Groupsconsole

* [](moderation.md) Moderationconsole

   * Gemeenschappelijke bulkmoderatie UI voor auteur en publicatiemilieu&#39;s
   * Nieuwe filtercriteria

* [Leden en ](members.md) groepsbeheerconsoles

   * Biedt de mogelijkheid om gebruikers aan de serverzijde (leden) te maken en te beheren vanuit de ontwerpomgeving
   * Biedt de mogelijkheid om leden te verbieden
   * Verstrekt de capaciteit om te creëren en te leiden publiceer zijgebruikersgroepen (lidgroepen) van het auteursmilieu

* [](reports.md) Rapportenconsole

   * Biedt de mogelijkheid rapporten te genereren over toewijzingen, posten en weergaven

* [](resources.md) ResourceConsole

   * Verstrekt de capaciteit om enablement middelen en het leren wegen tot stand te brengen
   * Verleent toegang tot rapporten over enablement middelen en het leren wegen

De globale hulpmiddelenconsole verleent toegang tot de volgende hulpmiddelen van Gemeenschappen:

* [Site ](tools.md#sitetemplatesconsole) Templatesconsole

   * Sjablonen voor communitysites maken en beheren

* [Group ](tools.md#grouptemplatesconsole) Templatesconsole

   * Gebruikersgroepssjablonen maken en beheren

* [Community ](tools.md#communityfunctionsconsole) Functionsconsole

   * Community-functies maken en beheren

* [Storage ](tools.md#storageconfiguratonconsole) Configuration-console

   * Selecteer en vorm [common store](working-with-srp.md) voor de plaats

* [Component Guide](components-guide.md)

   * Een voorbeeldsite, [Community Components](http://localhost:4502/editor.html/content/community-components/en.html), die een voorbeeld biedt van alle onderdelen van de Gemeenschappen met hun standaardconfiguratie en de mogelijkheid ermee te experimenteren

## Sjablonen voor communautaire sites {#community-site-templates}

De creatie van de communautaire plaats is gebaseerd op selectie van een malplaatje van de communautaire plaats om een communautaire plaats snel te vestigen die van om het even welke steekproefplaats onafhankelijk is.

Een communitysitesjabloon, dat bestaat uit communityfuncties en communitygroepssjablonen, biedt de structuur voor een communitysite, zoals aanmeldingsgegevens, gebruikersprofielen, berichten, berichten, het menu van de site, zoeken, thema&#39;s en brandingfuncties.

Zie de [Sitesjabloonconsole](sites.md).

## Community-functies {#community-functions}

De kenmerken die van een gemeenschapservaring worden verwacht, zijn bekend. In AEM Communities zijn deze functies beschikbaar als bouwstenen, ook wel bekend als gemeenschapsfuncties.

Community-functies zijn normale AEM pagina&#39;s die bestaan uit componenten die zijn samengevoegd tot een functie die eenvoudig kan worden opgenomen in een sjabloon voor een communautaire site.

Zie [Community Functions console](functions.md).

## Communautaire groepen en groepssjablonen {#community-groups-and-group-templates}

De functie voor groepen van gemeenschappen is de mogelijkheid voor een subcommunity om dynamisch binnen een community-site te worden gemaakt door geautoriseerde gebruikers en leden van de gemeenschap uit zowel de auteur- als de publicatieomgeving.

Vanuit de auteursomgeving kunnen communitygroepen (subgemeenschappen) worden gemaakt binnen een bestaande communitysite of worden genest binnen een bestaande groep, als de structuur van de sjabloon de functie [Groepen](functions.md#groups-function) bevat.

Voor het maken van een community-groep moet een communitygroepsjabloon worden geselecteerd die het ontwerp van de pagina(&#39;s) van de community-groep bevat. Wanneer een functie van Groepen aan een malplaatjestructuur wordt toegevoegd, wordt het gevormd om of één groepsmalplaatje te specificeren of een keus van malplaatjes te verstrekken op het tijdstip dat een nieuwe communautaire groep wordt gecreeerd.

Zie ook:

* [Sitegroepen console](groups.md) : subgemeenschappen maken in de ontwerpomgeving
* [Groep sjablonen console](tools-groups.md)  - sitestructuur maken voor groepen
* [Aan de slag met AEM Communities](getting-started.md)  - zelfstudie voor het snel maken van een gemeenschapssite met geneste groepen

## Community-componenten {#community-components}

De [community-componenten](author-communities.md) waaruit een community-site is gemaakt, kunnen worden gebruikt om communautaire functies toe te voegen aan elke AEM site.

De [communitycomponentengids](components-guide.md) is beschikbaar voor interactieve exploratie van de componenten.

## Soorten gemeenschappen {#types-of-communities}

### Betrokkenheidsgemeenschap {#engagement-community}

Een betrokkenheidsgemeenschap is een community-site die klanten aanmoedigt om te informeren, feedback te vragen en klanten in staat te stellen als leden van de community te communiceren.

Functies van een betrokkenheidsgemeenschap kunnen het volgende omvatten:

* Aanmelden
* Berichten
* Forums
* Opmerkingen
* Revisies
* Waarderingen
* Stemming
* Blogs
* Groepen
* Kalenders
* Vertaling
* Moderatie
* Meldingen
* Scores en badges
* Analyserapportage

Als u het gemak wilt ervaren om snel een nieuwe betrokkenheidscommunity te maken, gaat u naar [Aan de slag met AEM Communities](getting-started.md).

### Community {#enablement-community} inschakelen

Een enablement-gemeenschap is een community-site met functies voor online leren.

Functies van een machtigingsgemeenschap kunnen zijn:

* Alle functies van een [betrokkenheidscommunity](#engagement-community)
* Mogelijkheid om inhoud en leermiddelen toe te wijzen aan leden en lidgroepen
* Ondersteunt SCORM-inhoud, zoals quizzen en tests
* Tekstspatiëring van toewijzingsgegevens
* Toegang tot rapportage en analyses
* De capaciteit om een gesprek over een het leren middel door forums, overseinen, commentaren en classificaties te hebben

Een enablement gemeenschap kan worden gecreeerd wanneer [add-on van Enablement wordt gevormd](enablement.md), die extra vergunning voor gebruik in een productiemilieu vereist. Een plaats van de enablgemeenschap zal [toewijzingsfunctie](#community-functions) omvatten.

Als u wilt ervaren hoe eenvoudig het maken van een nieuwe enablement-community is, gaat u naar [Aan de slag met AEM Communities for Enablement](getting-started-enablement.md).

## AEM demomodus {#aem-demo-machine}

De [AEM demomachine](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine) beheert en voert demo&#39;s uit voor AEM [Sites](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki/Scenario%20Sites), [Assets](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki/Scenario%20Assets), [Communities](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki/Scenario%20Communities), [Apps](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki/Scenario%20Apps) en [Forms](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki/Scenario%20Forms), die vaak meer opstelling dan eenvoudig vereisen QuickStart-instantie. De AEM demomachine zal extra [infrastructuur](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki/Infrastructure) zoals MongoDB, Solr, MySQL, MPEG en e-mailservers installeren.

De AEM Demo-machine bestaat uit:

* A [grafische gebruikersinterface](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki/User%20Interface)
* Apache ANT-scripts met configureerbare [eigenschappen](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki/Properties) en [doelen](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki/Command%20Line)
* Te installeren pakketten
De AEM Demo-machine is getest met succes met CQ 5.5, CQ 5.6.1, AEM 6.0, AEM 6.1, AEM 6.2 en AEM 6.3 op Windows, Mac OS en Linux.

Voor AEM demo-machine is een geldige AEM vereist.

>[!NOTE]
>
>Bekijk een [video inleiding](https://www.youtube.com/watch?v=zEE_zkR9fVQ&amp;feature=youtu.be) aan de AEM machine van de Demo (13:26).

## AEM Communities-documentatie {#aem-communities-documentation}

* Bezoek [Gemeenschappen implementeren](deploy-communities.md) voor meer informatie over aanbevolen implementaties.

* Bezoek [Communitysites beheren](administer-landing.md) voor meer informatie over het maken van een communitysite, het toevoegen van communitygroepen, het configureren van sjablonen voor communitysites, het modereren van community-inhoud, het beheren van leden, het labelen, meldingen, scoring en badges.

* Bezoek [Developing Communities](communities.md) voor meer informatie over het SCF (Social Component Framework) en het aanpassen van onderdelen en functies van Gemeenschappen.

* Bezoek [Authoring Communities Components](author-communities.md) voor meer informatie over het schrijven en configureren van Community-componenten.

