---
title: Opmerkingen bij de release van AEM Sites
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
source-git-commit: f8ba597c62379ba413309303c2ad066ab7afce1e
workflow-type: tm+mt
source-wordcount: '1020'
ht-degree: 0%

---


# Opmerkingen bij de release van AEM Sites {#aem-sites-release-notes}

## Sites {#sites}

Zie het volgende voor AEM Sites 6.4-verbeteringen in detail:

### Sitebeheer {#site-administration}

* Nieuwe contentstructuurrail om snel door een sitehiërarchie te navigeren. In combinatie met de lijstweergave herstelt u het klassieke UI-interactiemodel om door een site te bladeren.
* Verbeterd schuiven in kaart en lijstweergave van grote mappen.
* Verbeterde interactie met de zoekresultaten - met de knop Vorige herstelt u het vorige zoekresultaat.
* Extra sneltoetsen voor de meeste algemene handelingen, zoals het openen van een bepaalde rail, het bewerken, verplaatsen en verwijderen van pagina&#39;s of het openen van eigenschappen.
* Mogelijkheid om sneltoetsen uit te schakelen (in Voorkeuren in-/uitschakelen).
* Stop met het tonen van tijdstempels in alle UI ten opzichte van na 7 dagen (standaard ingesteld in Voorkeuren).

### Pagina-editor {#page-editor}

* Bijgewerkte apparaatlijst voor responsieve sitevoorvertoning, nu inclusief Apple iPhone 8, 8 Plus en X, en Samsung S7
* Verplaatste standaardplaats voor de informatie van het malplaatjeontwerp vanaf /etc/design om plaatsen specifieke montages in /conf te steunen. Klanten die een upgrade uitvoeren van eerdere AEM, kunnen /etc/design blijven gebruiken.

### Component- en sjabloonontwikkeling {#component-amp-template-development}

* Project Archetype 13+, zie [Github voor versienota&#39;s](https://github.com/Adobe-Marketing-Cloud/aem-project-archetype/releases).
* HTL versie 1.3.1, zie [Github voor versienota&#39;s](https://github.com/Adobe-Marketing-Cloud/htl-spec/releases/tag/1.3.1).
* Core Components 2.0.4+, zie [Github voor versienota&#39;s](https://github.com/Adobe-Marketing-Cloud/aem-core-wcm-components/releases).
* Stijlsysteem

   * Een geheel nieuw concept toegevoegd om CSS-klassen toe te wijzen aan componenten en gebruikers in de Pagina-editor toe te staan uit een subset stijlen te kiezen via de gebruikersinterface
   * Mogelijkheid toegevoegd om de HTML-elementnaam te definiëren die rondom de component wordt gerenderd, bijvoorbeeld &lt;main>, &lt;reserve>

* Het Systeem van het net voor de Container van de Lay-out, zie [Github](https://github.com/Adobe-Marketing-Cloud/aem-responsivegrid).
* Sjablooneditor en beleidsregels

   * Het beleid steunt nu de configuraties van het Systeem van de Stijl per component, per container, per malplaatje.
   * Verbeterde ondersteuning voor het definiëren van lay-out in sjablonen op bewerkbare componenten

* Referentiesite We.Retail 3.0, zie [Github voor releaseopmerkingen](https://github.com/Adobe-Marketing-Cloud/aem-sample-we-retail/releases).

>[!CAUTION]
>
>AEM bevat versie 1.12.4 van de jQuery-bibliotheek voor maximale compatibiliteit met bestaande aangepaste code. Adobe heeft wijzigingen aangebracht om bekende beveiligingsproblemen aan te pakken.

### Inhoudsfragmenten en -editor {#content-fragments-amp-editor}

* Inleiding tot gestructureerde inhoudsmodellen als basis voor inhoudsfragmenten

   * Gebruikersinterface modeleditor
   * Vooraf geconfigureerde gegevenselementen voor modellen van inhoudsfragmenten (single-line tekst, multi-line tekst, getal, boolean, date&amp;time, opsomming, inhoudsverwijzing, tags)

* De bruikbaarheid van de AEM Content Fragment-editor is verbeterd

   * Overzicht van alle elementen weergeven
   * Volledig scherm bewerken voor enkele elementen
   * Verbeterde mogelijkheden voor tekstbewerking (lijsten met opsommingstekens, genummerde lijsten, inspringing, hyperlinks, tabellen, zoeken en vervangen, spellingcontrole)

* Verbeterde uitvoeropties toegevoegd voor AEM inhoudsfragmenten

   * Nieuwe component Inhoudsfragment, als onderdeel van Core Components. [Zie code op GitHub.](https://github.com/Adobe-Marketing-Cloud/aem-core-wcm-components/tree/master/extension/contentfragment/content/src/content/jcr_root/apps/core/wcm/extension/components/contentfragment/v1/contentfragment)
   * Ondersteuning voor Content Services met JSON-uitvoer via Sling Model Exporter

### Ervaringsfragmenten {#experience-fragments}

* Introduceerde de Blokken van de Bouw van het Fragment van de Ervaring, om het hergebruiken van inhoud tussen de veranderingen van de Fragmenten van de Ervaring te vergemakkelijken door componenten te groeperen en door gemakkelijke verwijzing binnen variaties toe te staan.
* De mogelijkheid toegevoegd om ervaringsfragmenten toe te voegen aan vertaalprojecten via de referentierail
* De mogelijkheid toegevoegd om workflows te starten met Experience Fragments via de tijdlijntrack
* Referentiespoor toont nu waar een Fragment van de Ervaring in AEM wordt gebruikt
* De configuratie van malplaatjeplaatsen staat nu auteurs toe om op een globaal of omslagniveau te bepalen welke malplaatjes van het Fragment van de Ervaring worden toegestaan te gebruiken
* Geavanceerd zoeken ondersteunt nu geavanceerde filters, zoals gepubliceerd/niet-gepubliceerd, die naar sociale media en Adobe Target worden geëxporteerd
* Enkele aanmelding voor sociale media toegevoegd bij het exporteren van Experience Fragments naar Pinterest of Facebook
* Geïntegreerde AEM Ervaring Fragments met Adobe Target. Het synchroniseren van de Fragmenten van de Ervaring aan Doel zal aanbiedingen in Adobe Target tot stand brengen die met Composer van de Ervaring van het Doel kunnen worden gebruikt om het in om het even welk Doel toegelaten ervaring in te bedden.

### Vertaling {#translation}

* Verbeterde bruikbaarheid van AEM vertaalprojecten:

   * Ondersteuning voor meerdere doeltalen in één project
   * Optie om het starten van vertalingen automatisch te bevorderen en te verwijderen
   * Optie om de uitvoering van vertaalprojecten (dagelijks, wekelijks, maandelijks, jaarlijks) te plannen
   * Verbeterde tegels voor vertaalprojecten met meer gedetailleerde statusinformatie

* Introductie van Omgekeerd vertaalgeheugen bijwerken, om vertaalgeheugen in een systeem voor vertaalbeheer van derden bij te werken na lokale inhoudbewerkingen in AEM
* Workflows voor vertaling ondersteunen nu gegroepeerde taalwortels
* Mogelijkheid toegevoegd om willekeurige namen toe te wijzen aan taalwortels en JCR-eigenschap te gebruiken voor toewijzing aan ISO-code
* De updates voor slimme vertaling herkennen nu nieuwe pagina&#39;s die zijn toegevoegd aan een master taalvertakking
* Introductie van de rapportage over de vertaalstatus in de lijstweergave Sites Admin

### Meersitebeheer (MSM) {#multi-site-management-msm}

* Verbeterde MSM-schaalbaarheid met een op eik gebaseerde index versus in-geheugen (LiveCopyIndex)

### Lanceringen {#launches}

* Verbeterde prestaties van lanceringen die grote plaatsboom bevatten en als er vele Lanceringen actief zijn
* Verbeterde automatische promotie en publicatie van lanceringen met meerdere basispagina&#39;s.
* Probleem verholpen waardoor de voorvertoning van het responsieve apparaat niet kon werken met pagina&#39;s die werden bewerkt in de context van een opstart.

### Inhoud richten en simuleren {#content-targeting-simulation}

* Ondersteuningsmappen voor het organiseren van segmenten op basis van site/context (CQ-94620)
* Verplaatst standaardplaats voor segmenten in /conf om plaats/context specifieke lijsten van het Segment te hebben.

### AEM en Adobe Target  {#aem-amp-adobe-target-nbsp}

* Geïntegreerde AEM Ervaring Fragments met Adobe Target. Het synchroniseren van de Fragmenten van de Ervaring aan Doel zal aanbiedingen in Adobe Target tot stand brengen die met Composer van de Ervaring van het Doel kunnen worden gebruikt om het in om het even welk Doel toegelaten ervaring in te bedden.
* Adobe Target mbox.js versie 63 is nu inbegrepen. Adobe raadt aan om de implementatie over te schakelen naar at.js.
* at.js versie 1.2.2 is nu inbegrepen. Adobe raadt u aan om Dynamic Tag Management (DTM) of [Adobe Experience Platform Launch](https://www.adobe.com/enterprise/cloud-platform/launch.html) te gebruiken om in het bestand .js naar de site te gaan.

### AEM en Adobe Analytics {#aem-amp-adobe-analytics}

* s_code.js H.27.5 is nu opgenomen. Adobe raadt aan om de implementatie over te schakelen naar AppMeasurement.js
* AppMeasurement.js 1.8.0 is nu inbegrepen. Adobe raadt u aan om Dynamic Tag Management (DTM) of [Adobe Experience Platform Launch](https://www.adobe.com/enterprise/cloud-platform/launch.html) te gebruiken om AppMeasurement.js op de site te plaatsen.

## Invoegtoepassing Gemeenschappen {#communities-add-on}

Zie [pagina Opmerkingen bij de release van Gemeenschappen](/help/release-notes/communities-release-notes.md)

## Scherminvoegtoepassing {#screens-add-on}

* Toegevoegde ondersteuning voor schermspelers die verbinding moeten maken met AEM publicatieservers voor opdrachtbeheer en besturing en kanaaldownloads (in plaats van rechtstreeks naar AEM auteur).
* Toegevoegde mogelijkheid om kanaaltoewijzingen te groeperen in Planningen
* Kanaaltoewijzingen hebben nu de begin- en einddatum
* Het dashboard van het apparaat toont nu speler shell en ingebouwde programmatuurversie
* Apparaatdashboardlijst bevat verbindingsstatus van speler
* Extra ondersteuning voor Google Chrome OS voor AEM Screens Player
* Microsoft Windows 10 voor AEM Screens Player toegevoegd
