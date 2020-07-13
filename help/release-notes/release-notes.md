---
title: Algemene opmerkingen bij de release van Adobe Experience Manager 6.4
seo-title: Release-opmerkingen
description: 'Adobe Experience Manager 6.4 merkt op beschrijvend de versieinformatie, wat nieuw is, hoe te om en gedetailleerde veranderingslijsten te installeren. '
seo-description: 'Adobe Experience Manager 6.4 merkt op beschrijvend de versieinformatie, wat nieuw is, hoe te om en gedetailleerde veranderingslijsten te installeren. '
uuid: 5a220301-2727-4078-ba19-4a2dbf9657f4
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4
topic-tags: release-notes
content-type: reference
discoiquuid: 2be468e7-2b4e-4e04-881b-b9bdd1f55e57
translation-type: tm+mt
source-git-commit: f1bf1545689b977a0f5074954df224db58cbd695
workflow-type: tm+mt
source-wordcount: '2745'
ht-degree: 1%

---


# Algemene opmerkingen bij de release van Adobe Experience Manager 6.4 {#general-release-notes-for-adobe-experience-manager}

## Geen informatie {#release-information}

<table> 
 <tbody>
  <tr>
   <th>Product</th> 
   <td>Adobe Experience Manager<br /> </td> 
  </tr>
  <tr>
   <th>Versie</th> 
   <td>6.4</td> 
  </tr>
  <tr>
   <th>Type</th> 
   <td>Grote release</td> 
  </tr>
  <tr>
   <th>Algemene beschikbaarheidsdatum</th> 
   <td>4 april 2018<br /> </td> 
  </tr>
  <tr>
   <th>Aanbevolen updates</th> 
   <td>Zie <a href="https://helpx.adobe.com/experience-manager/aem-releases-updates.html">AEM-releases en updates</a></td> 
  </tr>
 </tbody>
</table>

### Trivia {#trivia}

De releasecyclus voor deze versie van Adobe Experience Manager begon op 27 april 2017, doorliep 22 versies van kwaliteitsborging en het bevestigen van fouten, en eindigde op 22 maart 2018. Het totale aantal klantgerelateerde problemen, inclusief verbeteringen en nieuwe functies die in deze release zijn opgelost, is 704.

Adobe Experience Manager 6.4 is over het algemeen beschikbaar sinds 4 april 2018.

>[!NOTE]
>
>Adobe raadt u aan het nieuwste servicepakket te installeren, aangezien alle nieuwe functiepakketten alleen via [servicepacks](https://helpx.adobe.com/experience-manager/maintenance-releases-roadmap.html)worden geleverd.

## Wat is er nieuw {#what-s-new}

Adobe Experience Manager 6.4 is een verbeteringsversie aan Adobe Experience Manager 6.3 codebasis. Het verstrekt nieuwe en verbeterde functionaliteit, zeer belangrijke klantenmoeilijke situaties, de verhogingen van de hoge prioriteit van de klant en algemene insectenmoeilijke situaties die op productstabilisatie gericht zijn. Het omvat ook de meerderheid van alle Adobe Experience Manager 6.3 eigenschapspakken, hete moeilijke situatie, en de versies van het de dienstpak.

De onderstaande lijst biedt een overzicht, terwijl op de volgende pagina&#39;s alle details worden weergegeven.

### Experience Manager Foundation {#experience-manager-foundation}

Volledige lijst met wijzigingen in [AEM Foundation](wcm-platform.md).

Het platform van Adobe Experience Manager 6.4 bouwt voort op de bijgewerkte versies van het op OSGi gebaseerde kader (Apache Sling en Apache Felix) en de Inhoudsgegevensbank van Java: Apache Jackrabbit Oak 1.8.2.

De QuickStart gebruikt Eclipse Jetty 9.3.22 als servlet-engine.

#### User Interface {#user-interface}

Er zijn verschillende verbeteringen aangebracht in de interface om deze productiever en gebruiksvriendelijker te maken.

* [Nieuwe contentstructuurrails](/help/sites-authoring/basic-handling.md#content-tree) om snel door een hiërarchie te navigeren. In combinatie met de lijstmening, herstelt dit het Klassieke UI interactiemodel.
* Verbeterde schuifervaring in kaart- en lijstweergave van grote mappen.
* [Verbeterde interactie met de zoekresultaten](/help/sites-authoring/search.md) - met de knop Vorige herstelt u het vorige zoekresultaat.
* [Extra sneltoetsen](/help/sites-authoring/keyboard-shortcuts.md)voor de meeste algemene handelingen, zoals het openen van een bepaalde rail, het bewerken, verplaatsen en verwijderen van items of het openen van eigenschappen.
* [Mogelijkheid om sneltoetsen](/help/sites-authoring/user-properties.md) uit te schakelen (in Voorkeuren in-/uitschakelen).
* [Stop met het tonen van tijdstempels in alle UI](/help/sites-authoring/user-properties.md) -relatief na 7 dagen (standaard ingesteld in Voorkeuren).

Raadpleeg de [documentatie](/help/sites-authoring/home.md) bij het schrijven voor meer informatie over deze functies.

>[!CAUTION]
>
>Adobe is niet van plan verdere verbeteringen aan te brengen in de klassieke gebruikersinterface. AEM 6.4 heeft de Klassieke inbegrepen UI, en de klanten die van vroegere versies bevorderen kunnen het blijven gebruiken zoals is. Merk op dat Klassieke UI volledig wordt gesteund terwijl wordt afgekeurd. [Lees meer](/help/sites-deploying/ui-recommendations.md).

#### Content-repository {#content-repository}

* Snellere en efficiëntere compressie door online revisie opschonen. Interne tests tonen aan dat de nieuwe staartafwerking tot 10 keer sneller is en meer schijfruimte met minder IOPS kan terugwinnen dan AEM 6.3. Dit heeft minder invloed op de prestaties als de Online revisie Cleanup wordt uitgevoerd. Zie [de documentatiepagina](/help/sites-deploying/revision-cleanup.md#full-and-tail-compaction-modes)voor meer informatie.

* Continuous Revision Cleanup for MongoMK vervangt gepland onderhoud voor opschonen
* Verbeterde efficiëntie voor het opschonen van revisies in documentknooppunten

#### Zoeken en indexeren {#search-indexing}

* Verbeterde ondersteuning voor indexeringsbewerkingen via &#39;ak-run&#39; (CLI):

   * Indexconsistentiecontrole
   * Indexeringsstatistieken
   * Index configuratie Im/export
   * Opnieuw indexeren

* Verminderde groei van de Luceen-gerelateerde opslagplaats voor een algemene verbeterde systeemprestaties

Ga voor meer informatie naar [deze documentatiepagina](/help/sites-deploying/indexing-via-the-oak-run-jar.md).

#### Bewaking {#monitoring}

* Een nieuw [Systeemoverzicht](/help/sites-administering/operations-dashboard.md#system-overview) biedt een momentopnamergave van alle aan prestaties gerelateerde systeemstatus en -activiteiten
* Een nieuwe reeks [gezondheidscontroles](/help/sites-administering/operations-dashboard.md#health-checks) rond indexering, vragen en onderhoud

#### Projecten en workflows {#projects-and-workflows}

* Nieuwe [Workfloweditor om workflowmodellen](/help/sites-developing/workflows-models.md)te maken en te bewerken.

![screen_shot_2018-04-04at71143am](assets/screen_shot_2018-04-04at71143am.png)

#### Upgrade uitvoeren vanaf eerdere versie {#upgrade-from-earlier-version}

* [Achterwaartse compatibiliteit](/help/sites-deploying/backward-compatibility.md): De achterwaartse compatibele eigenschappen in 6.4, helpen uw douanecode in de meeste gevallen compatibel blijven en verminderen verbeteringsinspanning.
* [Complexiteitsbeoordeling](/help/sites-deploying/pattern-detector.md)van upgrade: Het nieuwe gereedschap Patroondetector om de complexiteit van upgrades te beoordelen voordat u een upgrade uitvoert.
* [Herstructurering](/help/sites-deploying/repository-restructuring.md)van de opslagplaats: aanzienlijke herstructurering ( hoofdzakelijk / enz . ) om verbeteringen te vergemakkelijken en de toepassing van beste praktijken te bevorderen ;
* Meer algemene informatie over upgrades vindt u op [deze pagina](/help/sites-deploying/upgrade.md) voor meer informatie.

### Experience Manager-sites {#experience-manager-sites}

Volledige lijst met wijzigingen in [AEM Sites en invoegtoepassingen](sites.md).

#### Vloeiende ervaringen {#fluid-experiences}

De introductie van Fluid Ervaring begin 2017, gesteund door de Fragments van de Inhoud, de Fragments van de Ervaring en de Diensten van de Inhoud waren het begin om aan een multi-kanaal-eerste inhoudsbeheer te evolueren. AEM 6.4 breidt elk van de gebieden beduidend uit:

**[Contentfragmenten](/help/assets/content-fragments.md)**

Nieuw in 6.4 is een visuele redacteur van het [inhoudsmodel](/help/assets/content-fragments-models.md) en een nieuwe [configureerbare component](https://helpx.adobe.com/experience-manager/core-components/using/content-fragment-component.html) om flexibele output van HTML en JSON te verstrekken om in de Diensten van de Inhoud te omvatten.

**Ervaringsfragmenten**

Het maken van variaties in een fragment met dezelfde inhoud maar verschillende lay-outs is nu efficiënter dankzij de mogelijkheid Bouwstenen te maken. Naast het verzenden van Experience Fragments naar Facebook en Pinterest, is het nu mogelijk om ze als aanbieding naar Adobe Target te sturen.

**Inhoudsservices**

Er zijn verschillende verbeteringen aangebracht in Sling Model Exporter en de Core Components om een robuuste JSON-uitvoer te bieden voor het insluiten van inhoud in mobiele apps en ervaringen met apps van één pagina.

#### Sites sneller samenstellen {#gettings-sites-built-quicker}

AEM 6.4 voltooit de transformatie naar het volgende generatie componentenmodel. Het concept van de Componenten van de Kern dat in AEM 6.3 wordt geïntroduceerd, en nu door het Systeem van de Stijl wordt aangesloten, verstrekt een efficiënte manier om nieuwe te bouwen en bestaande plaatsen uit te breiden.

Aanbevolen zelfstudie voor meer informatie over hoe u het nieuwe componentmodel het beste kunt gebruiken: [Aan de slag met AEM Sites - WKND-zelfstudie](https://helpx.adobe.com/experience-manager/kt/sites/using/getting-started-wknd-tutorial-develop.html)

#### Scherminvoegtoepassing {#screens-add-on}

AEM Screens staan voor een consistente boodschap via alle marketingkanalen, waaronder Digital Signage en kiosk-netwerken. AEM 6.4 biedt extra ondersteuning voor het uitvoeren van de Sigage Player op Microsoft Windows- en Google Chrome OS-hardware. Bovendien zijn verbeteringen op het gebied van extern apparaatbeheer en programma&#39;s (groepen kanalen) beschikbaar.

Raadpleeg de gebruikershandleiding voor [AEM Screens voor meer informatie over de schermupdates](https://docs.adobe.com/content/help/en/experience-manager-screens/user-guide/aem-screens-introduction.html).

### Experience Manager Communities {#experience-manager-communities}

AEM 6.4 voegt veel nieuwe functies en verbeteringen toe aan de Gemeenschappen. Volledige lijst met wijzigingen is beschikbaar in [AEM Communities](communities-release-notes.md). De belangrijkste kenmerken van deze release zijn:

#### Verbeteringen voor modernisering {#enhancements-to-moderation}

**Automatische spamdetectie**

Er is een nieuwe spamdetectieengine beschikbaar waarmee ongewenste door de gebruiker gegenereerde inhoud op sites en groepen in de gebruikersgemeenschap kan worden uitgefilterd. Zodra toegelaten van systeem/console/configMgr, merkt het een stuk van gebruiker geproduceerde inhoud als spam die op een vooraf bepaalde reeks spamwoorden wordt gebaseerd. Meer informatie over de motor van de spamopsporing, verwijs [het automatiseren van communautaire gebruiker die inhoud](/help/communities/moderate-ugc.md#spam-detection)produceert.

![spamdetectie](assets/spamdetection.png)

**Nieuwe filters voor QnA**

De nieuwe filters, genoemd Beantwoord en niet Beantwoord, zijn toegevoegd aan bulkmoderatieconsole om vragen te filtreren QnA. Om te weten hoe de Beantwoord en Onbeantwoorde statusfilters werken, verwijs [bulk het modereren gebruiker geproduceerde inhoud](/help/communities/moderation.md#main-pars-note-521961797).

**Filters voor bladwijzermodernisering**

De capaciteit om referentie de vooraf bepaalde matigingsfilters op moderatieconsole is verstrekt. Deze filters worden toegevoegd aan het einde van de URL-tekenreeks en kunnen daarom later worden gedeeld, opnieuw worden gebruikt en herzien. Zorg dat u weet hoe u bladwijzerfilters kunt gebruiken in de [bulkmoderatieconsole](/help/communities/moderation.md#main-pars-note-429176623).

#### UGC- en gebruikersprofielen verwijderen {#delete-ugc-and-user-profiles}

AEM 6.4 Communities maakt API&#39;s [en voorbeeldservlet](/help/communities/user-ugc-management-service.md) buiten de box beschikbaar [](https://github.com/Adobe-Marketing-Cloud/aem-communities-ugc-migration/tree/master/bundles/communities-ugc-management-servlet) zodat eindgebruikers controle kunnen hebben over hun gegevens. Deze API&#39;s stellen organisaties voor gegevensverwerking en gegevenscontrole ook in staat EU-aanvragen voor naleving van de GDPR-richtlijn in te dienen.

#### Verbeteringen voor site- en groepsbeheer {#enhancements-to-site-and-group-management}

**Groepen met meerdere landinstellingen maken in één stap**

Er is voorzien in de mogelijkheid om meertalige groepen te maken in één enkele bewerking. Om dergelijke groepen tot stand te brengen, kunnen de gebruikers aan de Inzameling van de Groep van de gewenste communautaire plaats van de console van Plaatsen navigeren. Maak een groep en geef de gewenste talen op op de pagina Sjabloon voor communautaire groep. Meer over deze functionaliteit, verwijs [communautaire groepenconsole](/help/communities/groups.md).

![meertalige groep](assets/multilingualgroup.png)

**[Websites en groepen van gemeenschappen met één klik verwijderen](/help/communities/groups.md)**

Het pictogram Verwijderen is nu beschikbaar op de respectievelijke sites en groepen en navigeert bij globale navigatie. Met dit pictogram worden alle items en inhoud van de site of groep verwijderd en worden alle gebruikerskoppelingen verwijderd. Meer informatie over deze functionaliteit, verwijs het [beheren van communautaire plaatsen](/help/communities/create-site.md#main-pars-text-fe17) en het [beheren van communautaire groepen](/help/communities/groups.md#main-pars-text-5e8c).

#### Verbeteringen in Enablement {#enhancements-to-enablement}

De functies Toewijzing en Catalogus zijn nu beschikbaar in groepen. Op deze manier kunt u leerinhoud maken, beheren en publiceren voor een specifieke set doelgroepsleden. Raadpleeg [Enablement-bronnen](/help/communities/resource.md)beheren voor meer informatie over het inschakelen van groepen uit de gebruikersgemeenschap.

![toewijzingscatalogus](assets/assignmentcatalog.png)

### Experience Manager Assets {#experience-manager-assets}

AEM 6.4 biedt verschillende nieuwe functies en verbeteringen aan Middelen, waaronder nieuwe, verbeterde CreativeCloud-integratie, belangrijke vernieuwingen op het gebied van kunstmatige intelligentie, verbeterd metagegevensbeheer, verbeterde rapportering en verbeterde gebruikerservaring. De volledige lijst van veranderingen beschikbaar in [AEM Assets](assets.md). De belangrijkste punten van de release zijn:

**Adobe-elementkoppeling**

Adobe Asset Link in Creative Cloud voor ondernemingen stroomlijnt de samenwerking tussen creatieve partijen en marketers bij het maken van inhoud. Het is een nieuwe native functie in Creative Cloud voor ondernemingen die Photoshop CC, Illustrator CC en InDesign CC verbindt met AEM — zonder dat creatieve gebruikers hun programma&#39;s hoeven te verlaten.

Zie [Adobe Asset Link](https://www.adobe.com/creativecloud/business/enterprise/adobe-asset-link.html)voor meer informatie over deze mogelijkheid, voorwaarden en toegang tot deze functie.

![adobe_asset_link](assets/adobe_asset_link.png)

**AEM-bureaubladtoepassing**

De AEM-bureaubladtoepassing is bijgewerkt naar versie 1.8, die compatibel is met AEM 6.4. De volledige lijst met wijzigingen voor de AEM-bureaubladtoepassing vindt u in een speciaal document met opmerkingen [over de release van de](https://helpx.adobe.com/experience-manager/desktop-app/release-notes.html) AEM-bureaubladtoepassing.

De verbeteringen die sinds de release van AEM 6.3 zijn geïntroduceerd, omvatten de mogelijkheid om hiërarchische mappen op de achtergrond te uploaden, een nieuwe interface voor het bewaken van bewerkingen op de achtergrond van elementen, verbeterde caching, netwerken en aanmelding, en algemene stabiliteitsverbeteringen. De documentatie bevat ook een handleiding voor [beste praktijken](https://helpx.adobe.com/experience-manager/desktop-app/aem-desktop-app.html).

**Adobe Sensei Services**

De nieuwe mogelijkheden omvatten Verbeterde Slimme Markeringen, met de capaciteit om klantenbedrijfsconomie te leren, automatisch etiketteren digitale activa met klant-specifieke markeringen en Slimme Vertaal Onderzoek, die ontdekkingsbaarheid in veelvoudige talen door onderzoekstermijnen te vertalen op de vlucht verbetert. Zie [Verbeterde slimme tags](/help/assets/enhanced-smart-tags.md)voor meer informatie over deze functie.

![enhanced_smart_tags2](assets/enhanced_smart_tags2.png)

**Metagegevens**

Tot de verbeteringen behoren het gelijktijdig importeren en exporteren van metagegevens voor een groot aantal elementen en geavanceerde metagegevensconstructies, zoals [trapsgewijze metagegevens](/help/assets/cascading-metadata.md).

**Rapporten**

De rapportage van activa onderging een grote revisie in AEM 6.4 met nieuw rapporteringskader, gebruikerservaring, en meer OOTB- rapporten voor klantentoepassingen. Zie [Elementrapporten](/help/assets/asset-reports.md)voor meer informatie over het genereren van verschillende rapporten.

**Gebruikerservaring**

Meerdere verbeteringen om het bladeren, zoeken en beheren van middelen voor gebruikers te verbeteren, zoals schuiven, terugzoeken, verbeterde zoekfilters en nog veel meer. De volledige lijst beschikbaar in [AEM Assets](assets.md).

**Brand Portal**

Verschillende verbeteringen op het gebied van metagegevens, rapportage, digitale rechten, aanmeldingservaring en publicatieprestaties voor middelendistributie. Om over de nieuwe verhogingen en de eigenschappen te weten te komen, zie [Nieuw in het Portaal](https://helpx.adobe.com/experience-manager/brand-portal/using/whats-new.html)van het Merk van AEM Assets.

#### Invoegtoepassing Dynamic Media {#dynamic-media-add-on}

AEM 6.4 bevat veel nieuwe functies en verbeteringen voor Dynamic Media. De volledige lijst is beschikbaar in [AEM Assets](assets.md). De belangrijkste hoogtepunten omvatten het volgende:

**Slim uitsnijden**

Smart Crop, aangedreven door Adobe Sensei, biedt automatisch niet-destructieve bijsnijdingen van afbeeldingen waarbij het interessepunt voor responsief ontwerp behouden blijft. U kunt een voorbeeld van bijgesneden afbeeldingssuggesties bekijken en deze indien nodig handmatig aanpassen. Met deze functie kunt u ook automatische stalen genereren voor productafbeeldingen.

Raadpleeg de documentatie bij [Afbeeldingsprofielen](/help/assets/image-profiles.md) voor meer informatie over het gebruik van Slim uitsnijden.

Zie Dynamic Media-elementen [toevoegen aan pagina](/help/assets/adding-dynamic-media-assets-to-pages.md) &#39;s voor meer informatie over het werken met Slim uitsnijden in de component Dynamic Media.

**Smart Imaging**

Slimme beeldverwerking maakt gebruik van de unieke kijkkenmerken van elke gebruiker, zodat deze automatisch afbeeldingen levert die zijn geoptimaliseerd voor zijn ervaring, wat resulteert in betere prestaties en betrokkenheid.

Raadpleeg de documentatie bij [Smart Imaging](/help/assets/imaging-faq.md) voor meer informatie.

![smart_crop](assets/smart_crop.png)

**Verbeteringen voor media en viewer**

Met nieuwe viewers, zoals Panorama&#39;s en VR, kunt u een indrukwekkende ervaring bieden.

Raadpleeg de documentatie bij [Panorama](/help/assets/panoramic-images.md) -afbeeldingen voor meer informatie.

**3D-middelen**

Nieuwe integratie met [Adobe Dimension CC](https://www.adobe.com/products/dimension.html), een Creative Cloud-toepassing voor het ontwerpen van 3D-ervaringen.

Zie [Werken met documentatie over 3D-middelen](/help/assets/assets-3d.md) voor meer informatie.

![do-not-localize/3d](assets/do-not-localize/3d.png)

### Experience Manager Forms {#experience-manager-forms}

AEM 6.4 Forms biedt verschillende nieuwe functies en verbeteringen. De hooglichten omvatten:

* Interactieve communicatie via meerdere kanalen
* Prefill Interactieve Mededelingen van bedrijfstoepassingen
* Workflowmodernisering en ondersteuning voor mobiele werknemers
* Lazy laadfragmenten
* Single-hop upgrade van LiveCycle naar Experience Manager Forms 6.4

Meer informatie over de pagina Opmerkingen bij de release van [AEM Forms](forms.md) . Zie ook het [overzicht van nieuwe functies en verbeteringen in AEM 6.4 Forms](/help/forms/using/whats-new.md) voor informatie over nieuwe en verbeterde functies en documentatiebronnen.

### Experience Manager Livefyre {#experience-manager-livefyre}

U kunt Livefyre integreren met uw AEM 6.4-exemplaar. Hier vindt u informatie over de integratie van Livefyre in AEM:

* [Integratie van Livefyre](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/livefyre.html)

### Gebruik klantgerichte ontwikkeling {#leverage-customer-focused-development}

Adobe gebruikt een klantgericht ontwikkelingsmodel dat klanten toestaat om aan alle stadia van het ontwikkelingsproces, tijdens specificatie, ontwikkeling en het testen bij te dragen. Onze dank gaat uit naar alle klanten en partners die een bijdrage leveren aan dit proces.

Adobe beschikt over de procedures en processen om verzameling, prioritering en tracering van de klantgerichte oplossing van problemen en ontwikkeling van verbeteringsverzoeken mogelijk te maken. Het ondersteuningsportal [voor](https://helpx.adobe.com/marketing-cloud/contact-support.html) Adobe Marketingen Cloud is geïntegreerd met het Adobe-systeem voor verbetering en foutopsporing. Vragen van de klant worden waar mogelijk met de klantenservice geïdentificeerd en opgelost. Bij doorverwijzing naar O&amp;O wordt alle klantinformatie vastgelegd en gebruikt voor prioritering en rapportage. Prioriteit wordt gegeven in ontwikkeling aan betaalde steun en garantiekwesties en betaalde klantenverhogingen.

Dit proces van prioritering heeft meer dan 500 klantgerichte veranderingen opgeleverd die in AEM 6.4 worden bevestigd.

## Lijst met bestanden die deel uitmaken van de release {#list-of-files-that-are-part-of-the-release}

**Stichting**

* Standalone QuickStart: cq-quickstart-6.4.0.jar
* Quickstart toepassingsserver: cq-quickstart-6.4.0.war
* Dispatcher 4.3.1 of hoger voor verschillende webservers en -platforms ([downloadkoppeling](https://helpx.adobe.com/experience-manager/dispatcher/release-notes.html))
* Plug-in voor Eclipse IDE (meer[lezen en downloaden](/help/sites-developing/aem-eclipse.md))

* Extension for Brackets Code Editor (meer[lezen en downloaden](/help/sites-developing/aem-brackets.md))
* Geweven/de Beelddelen van de Wieg ([downloadverbinding](https://repo.adobe.com/nexus/content/repositories/releases/com/adobe/aem/uber-jar/6.1.0/))

**Sites**

* Core Components ([GitHub-project](https://github.com/Adobe-Marketing-Cloud/aem-core-wcm-components))
* We.Retail Reference Implementation ([lees meer](/help/sites-developing/we-retail.md))
* Project Blueprint Archetype ([GitHub-project](https://github.com/Adobe-Marketing-Cloud/aem-project-archetype))
* AEM Screens voor verschillende doelplatforms ([downloaden](https://download.macromedia.com/screens/))
* Smart Content Language Models. Engels is vooraf geïnstalleerd - meer talen kunnen worden gedownload

   * [Duits](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq630/product/smartcontent-model-de)
   * [Spaans](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq630/product/smartcontent-model-es)
   * [Italiaans](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq630/product/smartcontent-model-it)
   * [Frans](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq630/product/smartcontent-model-fr)

* [Het Hulpmiddel](/help/sites-developing/dialog-conversion.md) van de Omzetting van de dialoog om Klassieke UI componenten aan Koraal 3 te migreren

**Assets**

* Adobe Experience Manager desktop app ([lees meer](https://helpx.adobe.com/experience-manager/desktop-app/aem-desktop-app.html) en [download](https://helpx.adobe.com/experience-manager/kb/download-companion-app.html))

* Pakket maken om verbeterde PDF-rasterfunctie toe te voegen ([lees meer](/help/assets/aem-pdf-rasterizer.md) en [download](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq630/product/assets/aem-assets-pdf-rasterizer-pkg))

* Pakket maken om uitgebreide ondersteuning voor RAW-afbeeldingen toe te voegen ([lees meer](/help/assets/camera-raw.md))

**Formulieren**

* Pakketten voor AEM Forms mogelijkheden:

   * [adobe-aemfd-aix-pkg](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/fd/AEM-FORMS-6.4-AIX)
   * [adobe-aemfd-linux-pkg](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/fd/AEM-FORMS-6.4-LX)
   * [adobe-aemfd-solaris-pkg](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/fd/AEM-FORMS-6.4-SOL)
   * [adobe-aemfd-win-pkg](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/fd/AEM-FORMS-6.4-WIN)
   * [adobe-aemfd-osx-pkg](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/fd/AEM-FORMS-6.4-OSX)

## Talen {#languages}

De gebruikersinterface is beschikbaar in de volgende talen:

* Engels
* Duits
* Frans
* Spaans
* Italiaans
* Braziliaans Portugees
* Japans
* Vereenvoudigd Chinees
* Traditioneel Chinees (beperkte ondersteuning)
* Koreaans

Experience Manager 6.4 is gecertificeerd voor GB18030-2005 CITS om de Chinese coderingsstandaard te gebruiken.

## Installeren en bijwerken {#install-update}

Zie [installatieinstructies](/help/sites-deploying/custom-standalone-install.md) voor installatievereisten.

Zie de [upgradedocumentatie](/help/sites-deploying/upgrade.md) voor gedetailleerde instructies.

## Ondersteunde Platforms {#supported-platforms}

Hier vindt u de volledige matrix met ondersteunde platforms, inclusief. Ondersteuning op [AEM 6.4 — Technische vereisten](/help/sites-deploying/technical-requirements.md)

>[!NOTE]
>
>Oracle is overgestapt op een LTS-model (Long Term Support) voor Oracle Java SE-producten. Java 9 en 10 zijn niet-LTS-versies van Oracle (zie [Oracle Java SE-supportroutekaart](https://www.oracle.com/technetwork/java/eol-135779.html)). Adobe biedt alleen ondersteuning voor LTS-releases van Java om AEM in productie te kunnen uitvoeren. Daarom is Java 8 de aanbevolen versie voor gebruik met AEM 6.4.

## Verouderde en verwijderde functies {#deprecated-and-removed-features}

Adobe evalueert voortdurend de mogelijkheden in het product en is van plan om in de loop der tijd de mogelijkheden te vervangen door krachtigere versies, of besluit om geselecteerde onderdelen opnieuw te implementeren om beter voorbereid te zijn op toekomstige verwachtingen of uitbreidingen.

Voor Adobe Experience Manager 6.4, [lees de lijst van afgekeurde en verwijderde mogelijkheden](deprecated-removed-features.md). De pagina bevat ook een vooraankondiging van wijzigingen in 2019 en een belangrijke kennisgeving voor klanten die een update uitvoeren van eerdere releases.

## Lijsten met gedetailleerde wijzigingen {#detailed-changes-lists}

[AEM Sites](sites.md)

[AEM Assets](assets.md)

[AEM Communities](communities-release-notes.md)

[AEM Forms](forms.md)

[AEM Foundation](wcm-platform.md)

## Bekende problemen {#known-issues}

[Lijst met bekende problemen](known-issues.md)

### Productdownload en -ondersteuning (beperkt aantal sites) {#product-download-and-support-restricted-sites}

Deze sites zijn alleen beschikbaar voor klanten. Neem contact op met uw accountmanager van Adobe als u een klant bent en toegang nodig hebt.

* [](https://daycare.day.com) [Product downloaden op licensing.adobe.com](https://licensing.adobe.com/)

* [Klantenondersteuning op de dag van de zorg.dag.com](https://daycare.day.com)

