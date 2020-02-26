---
title: Opmerkingen bij de release AEM-sites
seo-title: AEM Sites
description: Opmerkingen bij de release die specifiek zijn voor Adobe Experience Manager 6.4 Sites.
seo-description: Opmerkingen bij de release die specifiek zijn voor Adobe Experience Manager 6.4 Sites.
uuid: 593928ec-5d1a-4a88-bd73-897421c5984a
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4
topic-tags: release-notes
content-type: reference
discoiquuid: 40225441-7cfe-4395-ac71-60504b42e764
translation-type: tm+mt
source-git-commit: 901a923b6ab2b6bee1738d2b8f1928571c8019cb

---


# Opmerkingen bij de release AEM-sites {#aem-sites-release-notes}

## Sites {#sites}

Zie het volgende voor de verbeteringen van AEM-sites 6.4:

### Sitebeheer {#site-administration}

* Nieuwe contentstructuurrail om snel door een sitehiërarchie te navigeren. In combinatie met de lijstweergave herstelt u het klassieke UI-interactiemodel om door een site te bladeren.
* Verbeterd schuiven in kaart en lijstweergave van grote mappen.
* Verbeterde interactie met de zoekresultaten - met de knop Vorige herstelt u het vorige zoekresultaat.
* Extra sneltoetsen voor de meeste algemene handelingen, zoals het openen van een bepaalde rail, het bewerken, verplaatsen en verwijderen van pagina&#39;s of het openen van eigenschappen.
* Mogelijkheid om sneltoetsen uit te schakelen (in Voorkeuren in-/uitschakelen).
* Stop met het tonen van tijdstempels in alle UI relatief na 7 dagen (standaard ingesteld in Voorkeuren).

###  Pagina-editor {#page-editor}

* Bijgewerkte apparaatlijst voor responsieve sitevoorvertoning, nu inclusief Apple iPhone 8, 8 Plus en X, en Samsung S7
* Verplaatste standaardplaats voor de informatie van het malplaatjeontwerp vanaf /etc/design om plaatsen specifieke montages in /conf te steunen. Klanten die een upgrade uitvoeren van eerdere AEM-versies, kunnen het gebruik van /etc/design blijven gebruiken.

### Component- en sjabloonontwikkeling {#component-amp-template-development}

* Project Archetype 13+, zie [Github voor versienota](https://github.com/Adobe-Marketing-Cloud/aem-project-archetype/releases).
* HTML versie 1.3.1, zie [Github voor versienota](https://github.com/Adobe-Marketing-Cloud/htl-spec/releases/tag/1.3.1).
* Core Components 2.0.4+, zie [Github voor versienota](https://github.com/Adobe-Marketing-Cloud/aem-core-wcm-components/releases).
* Stijlsysteem

   * Een geheel nieuw concept toegevoegd om CSS-klassen toe te wijzen aan componenten en gebruikers in de Pagina-editor toe te staan uit een subset stijlen te kiezen via de gebruikersinterface
   * Mogelijkheid toegevoegd om de HTML-elementnaam te definiëren die rondom de component wordt gerenderd, bijvoorbeeld &lt;main>, &lt;reserve>

* Het Systeem van het Net voor de Container van de Lay-out, zie [Github](https://github.com/Adobe-Marketing-Cloud/aem-responsivegrid).
* Sjablooneditor en beleidsregels

   * Het beleid steunt nu de configuraties van het Systeem van de Stijl per component, per container, per malplaatje.
   * Verbeterde ondersteuning voor het definiëren van lay-out in sjablonen op bewerkbare componenten

* Referentie Site We.Retail 3.0, zie [Github voor releaseopmerkingen](https://github.com/Adobe-Marketing-Cloud/aem-sample-we-retail/releases).

>[!CAUTION]
>
>AEM bevat versie 1.12.4 van de jQuery-bibliotheek voor maximale compatibiliteit met bestaande aangepaste code. Adobe heeft wijzigingen aangebracht om bekende beveiligingsproblemen te verhelpen.

### Inhoudsfragmenten en -editor {#content-fragments-amp-editor}

* Inleiding tot gestructureerde inhoudsmodellen als basis voor inhoudsfragmenten

   * Gebruikersinterface modeleditor
   * Vooraf geconfigureerde gegevenselementen voor modellen van inhoudsfragmenten (single-line tekst, multi-line tekst, getal, boolean, date&amp;time, opsomming, inhoudsverwijzing, tags)

* Verbeterde bruikbaarheid van de AEM Content Fragment Editor

   * Overzicht van alle elementen weergeven
   * Volledig scherm bewerken voor enkele elementen
   * Verbeterde mogelijkheden voor tekstbewerking (lijsten met opsommingstekens, genummerde lijsten, inspringing, hyperlinks, tabellen, zoeken en vervangen, spellingcontrole)

* Verbeterde uitvoeropties toegevoegd voor AEM Content Fragments

   * Nieuwe component Inhoudsfragment, als onderdeel van Core Components. [Zie code op GitHub.](https://github.com/Adobe-Marketing-Cloud/aem-core-wcm-components/tree/master/extension/contentfragment/content/src/content/jcr_root/apps/core/wcm/extension/components/contentfragment/v1/contentfragment)
   * Ondersteuning voor Content Services met JSON-uitvoer via Sling Model Exporter

### Ervaringsfragmenten {#experience-fragments}

* Introduceerde de Blokken van de Bouw van het Fragment van de Ervaring, om het hergebruiken van inhoud tussen de veranderingen van de Fragmenten van de Ervaring te vergemakkelijken door componenten te groeperen en door gemakkelijke verwijzing binnen variaties toe te staan.
* De mogelijkheid toegevoegd om ervaringsfragmenten toe te voegen aan vertaalprojecten via de referentierail
* De mogelijkheid bieden om workflows te starten met Experience Fragments via de tijdlijn
* Referentiespoor toont nu waar een Fragment van de Ervaring in AEM wordt gebruikt
* De configuratie van malplaatjeplaatsen staat nu auteurs toe om op een globaal of omslagniveau te bepalen welke malplaatjes van het Fragment van de Ervaring worden toegestaan te gebruiken
* Geavanceerd zoeken ondersteunt nu geavanceerde filters, zoals gepubliceerd/niet-gepubliceerd, geëxporteerd naar sociale media en Adobe Target
* Enkele aanmelding voor sociale media toegevoegd bij het exporteren van Experience Fragments naar Pinterest of Facebook
* Geïntegreerde AEM Ervaar Fragments met het Doel van Adobe. Als u Experience Fragments synchroniseert met Doel, worden er aanbiedingen in Adobe Target gemaakt die met Visual Experience Composer van Target kunnen worden gebruikt om deze in een voor Doel ingeschakelde ervaring in te sluiten.

### Vertaling {#translation}

* Verbeterde bruikbaarheid van AEM-vertaalprojecten:

   * Ondersteuning voor meerdere doeltalen in één project
   * Optie om het starten van vertalingen automatisch te bevorderen en te verwijderen
   * Optie om de uitvoering van vertaalprojecten (dagelijks, wekelijks, maandelijks, jaarlijks) te plannen
   * Verbeterde tegels voor vertaalprojecten met meer gedetailleerde statusinformatie

* Introductie van Omgekeerd vertaalgeheugen-update om vertaalgeheugen in een ander vertaalbeheersysteem na lokale inhoudbewerkingen in AEM bij te werken
* Workflows voor vertaling ondersteunen nu gegroepeerde taalwortels
* Mogelijkheid toegevoegd om willekeurige namen toe te wijzen aan taalwortels en JCR-eigenschap te gebruiken voor toewijzing aan ISO-code
* De updates voor slimme vertaling herkennen nu nieuwe pagina&#39;s die zijn toegevoegd aan een taalstramienvertakking
* Introductie van de rapportage over de vertaalstatus in de lijstweergave Sites Admin

### Multisite beheer (MSM) {#multi-site-management-msm}

* Verbeterde MSM-schaalbaarheid met een op eik gebaseerde index versus in-geheugen (LiveCopyIndex)

### Lanceringen {#launches}

* Verbeterde prestaties van lanceringen die grote plaatsboom bevatten en als er vele Lanceringen actief zijn
* Verbeterde automatische promotie en publicatie van lanceringen met meerdere basispagina&#39;s.
* Probleem verholpen waardoor de voorvertoning van het responsieve apparaat niet kon werken met pagina&#39;s die werden bewerkt in de context van een opstart.

### Inhoud richten en simuleren {#content-targeting-simulation}

* Ondersteuningsmappen voor het organiseren van segmenten op basis van site/context (CQ-94620)
* Verplaatst standaardplaats voor segmenten in /conf om plaats/context specifieke lijsten van het Segment te hebben.

### AEM en Adobe-doel {#aem-amp-adobe-target-nbsp}

* Geïntegreerde AEM Ervaar Fragments met het Doel van Adobe. Als u Experience Fragments synchroniseert met Doel, worden er aanbiedingen in Adobe Target gemaakt die met Visual Experience Composer van Target kunnen worden gebruikt om deze in een voor Doel ingeschakelde ervaring in te sluiten.
* Adobe Target versie 63 is nu inbegrepen. Adobe raadt u aan om van implementatie over te schakelen naar at.js.
* at.js versie 1.2.2 is nu inbegrepen. Adobe raadt u aan om Dynamic Tag Management (DTM) of [Adobe Experience Platform Launch](https://www.adobe.com/enterprise/cloud-platform/launch.html) te gebruiken voor de installatie van .js op de site.

### AEM en Adobe Analytics {#aem-amp-adobe-analytics}

* s_code.js H.27.5 is nu opgenomen. Adobe raadt u aan om de implementatie over te schakelen naar AppMeturement.js
* AppMeasurement.js 1.8.0 is nu inbegrepen. Adobe raadt u aan om Dynamic Tag Management (DTM) of [Adobe Experience Platform Launch](https://www.adobe.com/enterprise/cloud-platform/launch.html) te gebruiken om AppMeasurement.js op de site te plaatsen.

## Invoegtoepassing Gemeenschappen {#communities-add-on}

Zie pagina Opmerkingen bij de release [van Gemeenschappen](/help/release-notes/communities-release-notes.md)

## Scherminvoegtoepassing {#screens-add-on}

* Toegevoegde ondersteuning voor schermspelers die verbinding moeten maken met AEM-publicatieservers voor commando en besturing en kanaaldownloads (in plaats van rechtstreeks naar AEM-auteur).
* Toegevoegde mogelijkheid om kanaaltoewijzingen te groeperen in Planningen
* Kanaaltoewijzingen hebben nu de begin- en einddatum
* Het dashboard van het apparaat toont nu speler shell en ingebouwde programmatuurversie
* Apparaatdashboardlijst bevat verbindingsstatus van speler
* Extra ondersteuning voor Google Chrome OS voor AEM Screens Player
* Microsoft Windows 10 voor AEM Screens Player toegevoegd

