---
title: AEM Communities - Overzicht
seo-title: AEM Communities Overview
description: Een overzicht van AEM Communities-functies en -instellingen
seo-description: An overview of AEM Communities features and setup
uuid: 6e3ac9d2-ca31-40ea-8cab-b8451074c498
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 418cc919-0ae3-4c6c-8566-7e9a206f02a8
exl-id: 3a8b21f8-75da-4867-9a8a-80fddf7946ed
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1432'
ht-degree: 0%

---

# AEM Communities - Overzicht {#aem-communities-overview}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Adobe Experience Manager (AEM) Communities biedt de mogelijkheid om snel een lokale community-site te maken die de prestaties verbetert, het sitebeheer verbetert en de conversie van sitebezoekers naar waardevolle leden van de community aanmoedigt.

<!--
Contact your account representative for information regarding licensing of AEM Communities as well as additional licensing for enablement features and Adobe Analytics.
-->

## Functies van Gemeenschappen {#communities-features}

AEM Communities maakt het mogelijk om een relatie te ontwikkelen met sitebezoekers die informatie geven via blogs, vragen en antwoorden en gebeurtenissencalenders, terwijl ze inzichten krijgen via forums, opmerkingen en andere community-inhoud, die vaak UGC (door gebruikers gegenereerde inhoud) wordt genoemd.

Verder maakt AEM Communities het mogelijk dat vertrouwde leden zich modereren in de publicatieomgeving, zich aanmelden bij Twitter en Facebook, inlinevertaling van community-inhoud, het maken van groepen uit de gemeenschap vanaf de gepubliceerde website, het scoren naar onderscheidingstempels, het delen van bestanden, meldingen en activiteitenstreams.

De kenmerken van de Gemeenschappen kunnen worden aangetoond met behulp van de [AEM demo-machine](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki) beschikbaar openbaar op GitHub.com of met de nieuwe Wij.Retail verwijzingsimplementatie.

## Communitysites {#community-sites}

Een communitysite is een AEM site die is gemaakt met een eenvoudige wizard die resulteert in een website met veel algemene functies die vooraf zijn getelegrafeerd naar de site.

De [wizard voor het maken van sites](sites-console.md):

* Elementen van de site samenstellen op basis van de geselecteerde [sjabloon voor community-site](sites.md) die
   * Gebouwd van [communautaire functies](#community-functions)
   * Optioneel [communautaire groepen](#communitygroups) functie
* Gebruikt te configureren instellingen:
   * Moderatie
   * Aanmelden
   * Vertaling
* Biedt essentiële functies:
   * Responsief ontwerp: Gebruiksmiddelen [Twitter-thema&#39;s voor Bootstrap](https://getbootstrap.com)
   * Aanmelden: Zelfregistratie [sociale aanmelding](social-login.md), gebruikersprofielen
   * Meldingen: De leden zien gebeurtenissen die voor hen van belang zijn
   * Berichten: Leden kunnen berichten verzenden of ontvangen op de site van de community
   * Zoeken: Mogelijkheid om te zoeken op de site van de community
   * Taalomschakeling: Mogelijkheid om een taal te selecteren voor een [meertalige site](../../help/sites-administering/translation.md)
   * Beheer: Toegang voor geautoriseerde leden om gebruikers binnen de community te matigen en te beheren
* Hiermee verwijdert u veel ontwerpstappen op paginaniveau:
   * Branding: Optionele upload van een bannerafbeelding voor weergave op alle pagina&#39;s van de communitysite
   * Navigatiemenu: Navigatiekoppelingen zijn beschikbaar voor de functies die zijn opgenomen in het sjabloon voor de communautaire site

Ga naar [Aan de slag met AEM Communities](getting-started.md).

## Persistentie van communautaire inhoud {#community-content-persistence}

Om de prestaties en synchronisatie van inhoud van de gebruikersgemeenschap te verbeteren, vereist AEM Communities een gemeenschappelijke opslag specifiek voor gebruiker geproduceerde inhoud (UGC) die tussen alle AEM (auteur en publiceer) instanties wordt gedeeld.

De communautaire inhoud wordt gemakkelijk betreden door de leverancier van het opslagmiddel (SRP), die een laag verstrekt om toegang van de onderliggende topologie te scheiden en een gemeenschappelijke opslag voor UGC steunt.

Ga voor meer informatie over de persistentie en aanbevolen implementaties van community-inhoud naar:

* [Opslag van communautaire inhoud](working-with-srp.md): bespreekt de beschikbare opslagopties SRP voor UGC
* [Aanbevolen topologieën](topologies.md): bespreekt topologieën die op gebruiksgeval en keus SRP worden gebaseerd
* [Opwaarderen naar AEM 6.3 Gemeenschappen](upgrade.md): biedt nuttige informatie over UGC bij de overgang naar AEM 6.3.

## Communityconsoles {#communities-consoles}

In de auteursomgeving biedt de globale navigatieconsole toegang tot de [Communityconsole](consoles.md), die het volgende bevat:

* [Sites](sites-console.md) console

   * Site maken
   * Site bewerken
   * Sitebeheer
   * [Communautaire groepen](groups.md) console

* [Moderatie](moderation.md) console

   * Gemeenschappelijke bulkmoderatie UI voor auteur en publicatiemilieu&#39;s
   * Nieuwe filtercriteria

* [Leden en groepen](members.md) beheerconsoles

   * Biedt de mogelijkheid om gebruikers aan de serverzijde (leden) te maken en te beheren vanuit de ontwerpomgeving
   * Biedt de mogelijkheid om leden te verbieden
   * Verstrekt de capaciteit om te creëren en te leiden publiceer zijgebruikersgroepen (lidgroepen) van het auteursmilieu

* [Rapporten](reports.md) console

   * Biedt de mogelijkheid rapporten te genereren over toewijzingen, posten en weergaven

* [Bronnen](resources.md) console

   * Verstrekt de capaciteit om enablement middelen en het leren wegen tot stand te brengen
   * Verleent toegang tot rapporten over enablement middelen en het leren wegen

De globale hulpmiddelenconsole verleent toegang tot de volgende hulpmiddelen van Gemeenschappen:

* [Sitesjablonen](tools.md#sitetemplatesconsole) console

   * Sjablonen voor communitysites maken en beheren

* [Groepssjablonen](tools.md#grouptemplatesconsole) console

   * Gebruikersgroepssjablonen maken en beheren

* [Communautaire functies](tools.md#communityfunctionsconsole) console

   * Community-functies maken en beheren

* [Opslagconfiguratie](tools.md#storageconfiguratonconsole) console

   * Selecteer en vorm de [gemeenschappelijk archief](working-with-srp.md) voor de site

* [Component Guide](components-guide.md)

   * een voorbeeldsite; [Community-componenten](http://localhost:4502/editor.html/content/community-components/en.html), die een steekproef van alle communautaire componenten met hun standaardconfiguratie en de capaciteit verstrekt om met hen te experimenteren

## Sjablonen voor communautaire sites {#community-site-templates}

De creatie van de communautaire plaats is gebaseerd op selectie van een malplaatje van de communautaire plaats om een communautaire plaats snel te vestigen die van om het even welke steekproefplaats onafhankelijk is.

Een communitysitesjabloon, dat bestaat uit communityfuncties en communitygroepssjablonen, biedt de structuur voor een communitysite, zoals aanmeldingsgegevens, gebruikersprofielen, berichten, berichten, het menu van de site, zoeken, thema&#39;s en brandingfuncties.

Zie de [Sitesjabloonconsole](sites.md).

## Communautaire functies {#community-functions}

De kenmerken die van een gemeenschapservaring worden verwacht, zijn bekend. In AEM Communities zijn deze functies beschikbaar als bouwstenen, ook wel bekend als gemeenschapsfuncties.

Community-functies zijn normale AEM pagina&#39;s die bestaan uit componenten die zijn samengevoegd tot een functie die eenvoudig kan worden opgenomen in een sjabloon voor een communautaire site.

Zie de [Community Functions-console](functions.md).

## Communautaire groepen en groepssjablonen {#community-groups-and-group-templates}

De functie voor groepen van gemeenschappen is de mogelijkheid voor een subcommunity om dynamisch binnen een community-site te worden gemaakt door geautoriseerde gebruikers en leden van de gemeenschap uit zowel de auteur- als de publicatieomgeving.

Vanuit de auteursomgeving kunnen communitygroepen (subgemeenschappen) worden gemaakt binnen een bestaande communitysite of worden genest binnen een bestaande groep, als de structuur van de sjabloon de [Groepen, functie](functions.md#groups-function).

Voor het maken van een community-groep moet een communitygroepsjabloon worden geselecteerd die het ontwerp van de pagina(&#39;s) van de community-groep bevat. Wanneer een functie van Groepen aan een malplaatjestructuur wordt toegevoegd, wordt het gevormd om of één groepsmalplaatje te specificeren of een keus van malplaatjes te verstrekken op het tijdstip dat een nieuwe communautaire groep wordt gecreeerd.

Zie ook:

* [Sitegroepen, console](groups.md) - het creëren van subgemeenschappen in de auteursomgeving
* [Groep sjablonen, console](tools-groups.md) - het creëren van plaatsstructuur voor groepen
* [Aan de slag met AEM Communities](getting-started.md) - zelfstudie voor het snel maken van een community-site met geneste groepen

## Community-componenten {#community-components}

De [communautaire componenten](author-communities.md) Van waaruit een communautaire plaats wordt gebouwd kan worden gebruikt om de eigenschappen van Gemeenschappen aan om het even welke AEM Plaats toe te voegen.

De [Community-componentengids](components-guide.md) is beschikbaar voor interactieve verkenning van de componenten.

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

Ga voor het gemak om snel een nieuwe betrokkenheidsgemeenschap te maken naar [Aan de slag met AEM Communities](getting-started.md).

### Enablement Community {#enablement-community}

Een enablement-gemeenschap is een community-site met functies voor online leren.

Functies van een machtigingsgemeenschap kunnen zijn:

* Alle functies van een [betrokkenheidsgemeenschap](#engagement-community)
* Mogelijkheid om inhoud en leermiddelen toe te wijzen aan leden en lidgroepen
* Ondersteunt SCORM-inhoud, zoals quizzen en tests
* Tekstspatiëring van toewijzingsgegevens
* Toegang tot rapportage en analyses
* De capaciteit om een gesprek over een het leren middel door forums, overseinen, commentaren en classificaties te hebben

Een enablement-gemeenschap kan worden opgericht wanneer de [Invoegtoepassing inschakelen is geconfigureerd](enablement.md), waarvoor aanvullende licenties vereist zijn voor gebruik in een productieomgeving. Een site van de gemeenschap voor activering bevat de [toewijzingsfunctie](#community-functions).

Ga naar [Aan de slag met AEM Communities for Enablement](getting-started-enablement.md).

## AEM demo-machine {#aem-demo-machine}

De [AEM demo-machine](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine) beheert en voert demo&#39;s voor AEM uit [Sites](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki/Scenario%20Sites), [Activa](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki/Scenario%20Assets), [Gemeenschappen](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki/Scenario%20Communities), [Apps](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki/Scenario%20Apps) en [Forms](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki/Scenario%20Forms), waarvoor vaak meer instellingen nodig zijn dan het starten van een QuickStart-instantie. De AEM Demo-machine stelt aanvullende instellingen in [infrastructuur](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki/Infrastructure) zoals MongoDB-, Solr-, MySQL-, MPEG- en e-mailservers.

De AEM Demo-machine bestaat uit:

* A [grafische gebruikersinterface](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki/User%20Interface)
* Apache ANT-scripts met configureerbare [eigenschappen](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki/Properties) en [streefdoelen](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki/Command%20Line)
* Pakketten voor installatie van de AEM Demo-computer zijn getest met CQ 5.5, CQ 5.6.1, AEM 6.0, AEM 6.1, AEM 6.2 en AEM 6.3 op Windows, MacOS en Linux.

Voor AEM demo-machine is een geldige AEM vereist.

>[!NOTE]
>
>Een [video-introductie](https://www.youtube.com/watch?v=zEE_zkR9fVQ&amp;feature=youtu.be) naar de AEM demomachine (13:26).

## AEM Communities-documentatie {#aem-communities-documentation}

* Bezoek [Gemeenschappen inzetten](deploy-communities.md) voor meer informatie over aanbevolen implementaties.

* Bezoek [Communitysites beheren](administer-landing.md) om over het creëren van een communautaire plaats te leren, toevoegend communautaire groepen, vormend de malplaatjes van de communautaire plaats, het modereren van communautaire inhoud, het beheren van leden, het etiketteren, berichten, het scoren, en badges.

* Bezoek [Ontwikkelingsgemeenschappen](communities.md) voor meer informatie over het raamwerk voor sociale componenten (SCF) en het aanpassen van onderdelen en functies van Gemeenschappen.

* Bezoek [Componenten van Gemeenschappen ontwerpen](author-communities.md) om te leren om met te schrijven en de componenten van de Gemeenschappen te vormen.
