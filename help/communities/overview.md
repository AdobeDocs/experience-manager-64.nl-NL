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
source-git-commit: 63001012f0d865c2548703ea387c780679128ee7
workflow-type: tm+mt
source-wordcount: '1429'
ht-degree: 0%

---


# AEM Communities - Overzicht {#aem-communities-overview}

Adobe Experience Manager (AEM) Communities biedt de mogelijkheid om snel een lokale community-site te maken die de prestaties verbetert, het sitebeheer verbetert en de conversie van sitebezoekers naar waardevolle leden van de community aanmoedigt.

Neem contact op met uw accountvertegenwoordiger voor informatie over licenties voor AEM Communities en aanvullende licenties voor functies voor activering en Adobe Analytics.

## Functies van Gemeenschappen {#communities-features}

AEM Communities maakt het mogelijk om een relatie te ontwikkelen met sitebezoekers die informatie geven via blogs, vragen en antwoorden en gebeurtenissencalenders, terwijl ze inzichten krijgen via forums, opmerkingen en andere community-inhoud, die vaak UGC (door gebruikers gegenereerde inhoud) wordt genoemd.

Verder maakt AEM Communities moderatie door vertrouwde leden in de publicatieomgeving mogelijk, sociale aanmelding bij Twitter en Facebook, inlinevertaling van community-inhoud, het maken van communitygroepen vanaf de gepubliceerde communitysite, het scoren naar onderscheidingstempels, het delen van bestanden, meldingen en activiteitenstreams.

De eigenschappen van gemeenschappen kunnen worden aangetoond gebruikend de [AEM Machine](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki) van de Demo openbaar op GitHub.com of met de nieuwe Web.Retail verwijzingsimplementatie beschikbaar.

## Communitysites {#community-sites}

Een communitysite is een AEM site die is gemaakt met een eenvoudige wizard die resulteert in een website met veel algemene functies die vooraf zijn getelegrafeerd naar de site.

De wizard [Site maken](sites-console.md):

* Verzamelt eigenschappen van de plaats, die op het geselecteerde malplaatje [van de](sites.md) communautaire plaats wordt gebaseerd die is
   * Gebouwd op basis van [gemeenschapsfuncties](#community-functions)
   * Optionele [community groups](#communitygroups) -functie
* Gebruikt te configureren instellingen:
   * Moderatie
   * Aanmelden
   * Vertaling
* Biedt essentiële functies:
   * Responsief ontwerp: Gebruikt [thema&#39;s Twitter-Bootstrap](https://getbootstrap.com)
   * Aanmelden: Zelfregistratie, [sociale aanmelding](social-login.md), gebruikersprofielen
   * Meldingen: De leden zien gebeurtenissen die voor hen van belang zijn
   * Berichten: Leden kunnen berichten verzenden of ontvangen op de site van de community
   * Zoeken: Mogelijkheid om te zoeken op de site van de community
   * Taalomschakeling: De mogelijkheid om een taal te selecteren voor een [meertalige site](../../help/sites-administering/translation.md)
   * Beheer: Toegang voor geautoriseerde leden om gebruikers binnen de community te matigen en te beheren
* Hiermee verwijdert u veel ontwerpstappen op paginaniveau:
   * Branding: Optionele upload van een bannerafbeelding voor weergave op alle pagina&#39;s van de communitysite
   * Navigatiemenu: Navigatiekoppelingen zijn beschikbaar voor de functies die zijn opgenomen in het sjabloon voor de communautaire site

Ga naar [Aan de slag met AEM Communities](getting-started.md)om snel een nieuwe community-site te maken.

## Persistentie van communautaire inhoud {#community-content-persistence}

Om de prestaties en synchronisatie van inhoud van de gebruikersgemeenschap te verbeteren, vereist AEM Communities een gemeenschappelijke opslag specifiek voor gebruiker geproduceerde inhoud (UGC) die tussen alle AEM (auteur en publiceer) instanties wordt gedeeld.

De communautaire inhoud wordt gemakkelijk betreden door de leverancier van het opslagmiddel (SRP), die een laag verstrekt om toegang van de onderliggende topologie te scheiden en een gemeenschappelijke opslag voor UGC steunt.

Ga voor meer informatie over de persistentie en aanbevolen implementaties van community-inhoud naar:

* [Opslag](working-with-srp.md)voor community-inhoud: bespreekt de beschikbare opslagopties SRP voor UGC
* [Aanbevolen technologieën](topologies.md): bespreekt topologieën die op gebruiksgeval en keus SRP worden gebaseerd
* [Opwaarderen naar AEM 6.3 Gemeenschappen](upgrade.md): biedt nuttige informatie over UGC bij de overgang naar AEM 6.3.

## Communityconsoles {#communities-consoles}

In het auteursmilieu, verleent de globale navigatieconsole toegang tot de console [van](consoles.md)Gemeenschappen, die bevat:

* [Sites](sites-console.md) -console

   * Site maken
   * Site bewerken
   * Sitebeheer
   * [Community Group](groups.md) -console

* [Moderniseringsconsole](moderation.md)

   * Gemeenschappelijke bulkmoderatie UI voor auteur en publicatiemilieu&#39;s
   * Nieuwe filtercriteria

* [Leden en groepen](members.md) beheerconsoles

   * Biedt de mogelijkheid om gebruikers aan de serverzijde (leden) te maken en te beheren vanuit de ontwerpomgeving
   * Biedt de mogelijkheid om leden te verbieden
   * Verstrekt de capaciteit om te creëren en te leiden publiceer zijgebruikersgroepen (lidgroepen) van het auteursmilieu

* [Rapporten](reports.md) console

   * Biedt de mogelijkheid rapporten te genereren over toewijzingen, posten en weergaven

* [Bronnen](resources.md) -console

   * Verstrekt de capaciteit om enablement middelen en het leren wegen tot stand te brengen
   * Verleent toegang tot rapporten over enablement middelen en het leren wegen

De globale hulpmiddelenconsole verleent toegang tot de volgende hulpmiddelen van Gemeenschappen:

* [Sitesjabloonconsole](tools.md#sitetemplatesconsole)

   * Sjablonen voor communitysites maken en beheren

* [Groep sjablonen](tools.md#grouptemplatesconsole) , console

   * Gebruikersgroepssjablonen maken en beheren

* [Community Functions](tools.md#communityfunctionsconsole) console

   * Community-functies maken en beheren

* [Opslagconfiguratie](tools.md#storageconfiguratonconsole) -console

   * De [algemene opslag](working-with-srp.md) voor de site selecteren en configureren

* [Component Guide](components-guide.md)

   * Een voorbeeldsite, [Community Components](http://localhost:4502/editor.html/content/community-components/en.html), die een voorbeeld van alle onderdelen van de Gemeenschappen met hun standaardconfiguratie en de mogelijkheid biedt hiermee te experimenteren

## Sjablonen voor communautaire sites {#community-site-templates}

De creatie van de communautaire plaats is gebaseerd op selectie van een malplaatje van de communautaire plaats om een communautaire plaats snel te vestigen die van om het even welke steekproefplaats onafhankelijk is.

Een communitysitesjabloon, dat bestaat uit communityfuncties en communitygroepssjablonen, biedt de structuur voor een communitysite, zoals aanmeldingsgegevens, gebruikersprofielen, berichten, berichten, het menu van de site, zoeken, thema&#39;s en brandingfuncties.

Zie de console [Sjablonen](sites.md)voor sites.

## Communautaire functies {#community-functions}

De kenmerken die van een gemeenschapservaring worden verwacht, zijn bekend. In AEM Communities zijn deze functies beschikbaar als bouwstenen, ook wel bekend als gemeenschapsfuncties.

Community-functies zijn normale AEM pagina&#39;s die bestaan uit componenten die zijn samengevoegd tot een functie die eenvoudig kan worden opgenomen in een sjabloon voor een communautaire site.

Zie de [Community Functions console](functions.md).

## Communautaire groepen en groepssjablonen {#community-groups-and-group-templates}

De functie voor groepen van gemeenschappen is de mogelijkheid voor een subcommunity om dynamisch binnen een community-site te worden gemaakt door geautoriseerde gebruikers en leden van de gemeenschap uit zowel de auteur- als de publicatieomgeving.

Vanuit de auteursomgeving kunnen communitygroepen (subgemeenschappen) worden gemaakt binnen een bestaande communitysite of worden genest binnen een bestaande groep, als de structuur van de sjabloon de functie [](functions.md#groups-function)Groepen bevat.

Voor het maken van een community-groep moet een communitygroepsjabloon worden geselecteerd die het ontwerp van de pagina(&#39;s) van de community-groep bevat. Wanneer een functie van Groepen aan een malplaatjestructuur wordt toegevoegd, wordt het gevormd om of één groepsmalplaatje te specificeren of een keus van malplaatjes te verstrekken op het tijdstip dat een nieuwe communautaire groep wordt gecreeerd.

Zie ook:

* [Sitegroepen console](groups.md) - subgemeenschappen maken in de ontwerpomgeving
* [Groep sjablonen console](tools-groups.md) - sitestructuur maken voor groepen
* [Aan de slag met AEM Communities](getting-started.md) - zelfstudie voor het snel maken van een gemeenschapssite met geneste groepen

## Community-componenten {#community-components}

De [communautaire componenten](author-communities.md) waarvan een communautaire plaats wordt gebouwd kunnen worden gebruikt om de eigenschappen van Gemeenschappen aan om het even welke AEM Plaats toe te voegen.

De [Community components guide](components-guide.md) is beschikbaar voor interactieve verkenning van de componenten.

## Soorten Gemeenschappen {#types-of-communities}

### Gemeenschap voor betrokkenheid {#engagement-community}

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

Ga naar [Aan de slag met AEM Communities](getting-started.md)om snel een nieuwe betrokkenheidscommunity te maken.

### Enablement Community {#enablement-community}

Een enablement-gemeenschap is een community-site met functies voor online leren.

Functies van een machtigingsgemeenschap kunnen zijn:

* Alle functies van een [betrokkenheidsgemeenschap](#engagement-community)
* Mogelijkheid om inhoud en leermiddelen toe te wijzen aan leden en lidgroepen
* Ondersteunt SCORM-inhoud, zoals quizzen en tests
* Tekstspatiëring van toewijzingsgegevens
* Toegang tot rapportage en analyses
* De capaciteit om een gesprek over een het leren middel door forums, overseinen, commentaren en classificaties te hebben

Een enablement gemeenschap kan worden gecreeerd wanneer de toe:voegen- [functie Enablement wordt gevormd](enablement.md), die extra vergunning voor gebruik in een productiemilieu vereist. Een plaats van de enablgemeenschap zal de [toewijzingsfunctie](#community-functions)omvatten.

Ga naar [Aan de slag met AEM Communities for Enablement](getting-started-enablement.md)om te zien hoe eenvoudig het maken van een nieuwe community voor activering is.

## AEM demo-machine {#aem-demo-machine}

De [AEM Demo Machine](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine) beheert en voert demo&#39;s uit voor AEM [Plaatsen](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki/Scenario%20Sites), [Activa](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki/Scenario%20Assets), [Gemeenschappen](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki/Scenario%20Communities), [Apps](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki/Scenario%20Apps) [](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki/Scenario%20Forms)enForms, die vaak meer opstelling vereisen dan eenvoudig het lanceren van een instantie QuickStart. De AEM demo Machine zal extra [infrastructuur](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki/Infrastructure) zoals MongoDB, Solr, MySQL, MPEG en e-mailservers installeren.

De AEM Demo-machine bestaat uit:

* Een [grafische gebruikersinterface](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki/User%20Interface)
* Apache ANT-scripts met configureerbare [eigenschappen](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki/Properties) en [doelen](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki/Command%20Line)
* Te installeren pakkettenDe AEM demovernemingssysteem is getest met CQ 5.5, CQ 5.6.1, AEM 6.0, AEM 6.1, AEM 6.2 en AEM 6.3 op Windows, Mac OS en Linux.

Voor AEM demo-machine is een geldige AEM vereist.

>[!NOTE]
>
>Bekijk een [videoinleiding](https://www.youtube.com/watch?v=zEE_zkR9fVQ&amp;feature=youtu.be) op de AEM Demo-machine (13:26).

## AEM Communities-documentatie {#aem-communities-documentation}

* Bezoek [Implementerende gemeenschappen](deploy-communities.md) voor meer informatie over aanbevolen implementaties.

* Ga naar [Communitysites](administer-landing.md) beheren voor meer informatie over het maken van een communitysite, het toevoegen van communitygroepen, het configureren van sjablonen voor communitysites, het modereren van community-inhoud, het beheren van leden, het labelen, meldingen, scoring en badges.

* Bezoek [Ontwikkelingsgemeenschappen](communities.md) voor meer informatie over het sociale-componentframework (SCF) en het aanpassen van onderdelen en functies van Gemeenschappen.

* Bezoek [Authoring Communities Components](author-communities.md) voor meer informatie over het maken en configureren van Community-componenten.

