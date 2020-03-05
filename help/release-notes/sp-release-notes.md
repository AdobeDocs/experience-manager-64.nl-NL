---
title: AEM 6.4 de Nota's van de Versie van het Service Pack
seo-title: AEM 6.4 de Nota's van de Versie van het Service Pack
description: De nota's van de versie specifiek voor Manager 6.4 van de Ervaring van Adobe de Pakken van de Dienst.
seo-description: De nota's van de versie specifiek voor Manager 6.4 van de Ervaring van Adobe de Pakken van de Dienst.
uuid: 49a710a8-7cd5-47de-9a96-7af7f3c00dfc
contentOwner: dekalra
products: SG_EXPERIENCEMANAGER/6.4
topic-tags: release-notes
discoiquuid: 93067308-e275-490f-8d78-ae79e046059c
translation-type: tm+mt
source-git-commit: 3037d1e5c9f97778c55ee2734ded3c9ef668df4d

---


# AEM 6.4 de Nota&#39;s van de Versie van het Service Pack {#aem-service-pack-release-notes}

## Gegevens vrijgeven {#release-information}

| Producten | **Adobe Experience Manager (AEM) 6.4** |
|---|---|
| Versie | 6.4.8.0 |
| Type | Service Pack Release |
| Date | 05 maart 2020 |
| URL downloaden | AEM 6.4.8.0 op [PackageShare](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/servicepack/AEM-6.4.8.0) |

## Wat is inbegrepen in AEM 6.4.8.0 {#what-s-included-in-aem}

AEM 6.4.8.0 is een belangrijke update die nieuwe eigenschappen omvat, de zeer belangrijke klant vroeg om verhogingen en prestaties, stabiliteit, veiligheidsverbeteringen, die sinds de algemene beschikbaarheid van AEM 6.4 in **april 2018 worden vrijgegeven.**

Het is ook cumulatief wat betekent dat 6.4.8.0 alle AEM 6.4 de dienstpakken omvat die vóór het worden vrijgegeven.

Enkele zeer belangrijke hoogtepunten van deze versie van het de dienstpak zijn:

* De ingebouwde opslagplaats (Apache Jackrabbit Oak) wordt bijgewerkt naar versie 1.8.20.

* De de omloopfunctionaliteit van Word wordt gesteund voor Japanse websites in WCM-RTE.

* Word de onderbreking en de verwerking van de lijnonderbreking worden gesteund voor Japanse websites.

* Toegevoegde steun om methode te gebruiken BUNSETSU om Japanse taalzin en lijnen op aangewezen posities te breken.

* CCR UI voor brievenbeheer steunt nu decimale waarden voor Duitse scène.

* De modelintegratie van de gegevens van de vorm die de het Webdienst van de ZEEP gebruikt steunt nu keuzegroepen of attributen op elementen.

* AEM de Activa wordt nu gevormd met het Portaal van het Merk door Adobe I/O.

## Lijst van wijzigingen {#list-of-changes}

### Sites {#sites}

* Wanneer een Blauwdruk wordt gecreeerd, als het aantal verslagen meer dan 80 is, slechts worden de eerste 80 verslagen getoond. De blauwdruk toont lege lijnen voor de rest van de verslagen (NPR-32058).
* De gebruikers worden toegestaan om een Fragment van de Inhoud te bewaren zonder om het even welke informatie op de vereiste gebieden (NPR-31988) te verstrekken.
* De automatische navigatie werkt niet voor weg die in een Component van het Fragment van de Ervaring van de Kern (NPR-31921) wordt gevormd.
* Wanneer u het type van een lijstcel in de Rijke Redacteur van de Tekst (RTE) verandert, komt de hieronder fout voor:
   `Error: No common ancestor found, cannot continue` (NPR-31916).
* Wanneer de inhoud binnen de zelfde omslag wordt bewogen, is de optie van de paginabeweging gehandicapt (NPR-31841).
* Toegevoegde ondersteuning voor het verdelen van Japanse taalzinnen volgens de BUNSETSU-methode en breuklijnen op de juiste positie (NPR-31836).
* Wanneer URLs eindigt met `/_jcr_content/.html` of `/jcr:content/.html` wordt betreden, de pieken van cpu en AEM ophoudt antwoordend (NPR-31755).
* Wanneer u een hyperlink in de Rijke Redacteur van de Tekst (RTE) uitgeeft, wordt de onlangs geselecteerde weg niet bewaard (NPR-31659).
* Wanneer u een component met meerdere velden verwijdert en de verwijdering ongedaan maakt, wordt de component teruggezet, maar de gegevens worden niet teruggezet (NPR-31617).

### Assets {#assets}

* Een omslag zonder naam wordt gecreeerd in SPS (het Publiceren Scene7 Systeem) terwijl het bewegen van activa van één omslag aan een andere in de Manager van de Ervaring met de Dynamische configuratie van Media Scene7 (NPR-32440).

* De het detailpagina van activa van Pdf- dossiers toont actieknopen in de Manager van de Ervaring die op Dynamische wijze van Media Scene7 loopt (NPR-32316) niet.

* Activa- en videoleveringen kunnen niet worden verwijderd (NPR-32213).

* Het agendapictogram voor activering die gepland is, wordt niet weergegeven in de kolom Status (in de Klassieke UI van de DAM-lijst van activa) voor activa waarvan de activering gepland is voor een latere datum en tijd (NPR-32198).

* Verband tussen activa wordt overschreven wanneer activa verband houden met meer dan één activa die gebruikmaken van Overige (NPR-32196).

* Sparen de knoop voert geen Verre Reeks in wanneer de gebruiker geen veranderingen in Vastgestelde Redacteur in de Dynamische Cliënt van Media (NPR-32178) heeft aangebracht.

* PSD-assetopname veroorzaakt CPU-pieken en een niet-reagerende versie van de Author van de Manager van de Ervaring (NPR-32165).

* Uit de uitzondering van het Geheugen die wordt waargenomen wanneer een groot dossier van het PIT in de Manager DAM van de Ervaring (NPR-32155) wordt geupload.

* De geschiedenis URLs van de versie wordt getoond onder Verwezen door gebied op de pagina van het activaBezit (NPR-31889).

* Unpublished van het Merkortaal, op Manage de pagina van de Publicatie, ontbreekt voor sub-omslagen van een gepubliceerde omslag (NPR-31835).

* De dynamische de videocodes van Media slagen er niet in om te uploaden wanneer de Configuratie van de Wolk Scene7 in een privé omslag `/conf` in plaats van `/conf/global` (NPR-31779) wordt geplaatst.

* Het beeld wordt niet gezien op de chronologie nadat de annotaties worden toegevoegd, op de Manager die van de Ervaring op de Dynamische de looppaswijze van Media Scene7 loopt (NPR-31754).

* Het dossier van het PIT dat van DAM wordt gedownload kan niet worden geopend gebruikend WinZip (NPR-31745).

### Integratie {#integrations-6480}

* De drop-down menu&#39;s van de Reeks van het **Bedrijf** en van de **Rapportering** worden verborgen zodra de **Rapporterende Bron** terwijl het vormen van de Analyse van Adobe in de clouddiensten van de Manager van de Ervaring (NPR-31729) wordt geselecteerd.

* De eigenschappen van de Campagne van Adobe worden niet schoongemaakt wanneer het taalexemplaar van een bulletin verbonden aan een Campagne van Adobe wordt gemaakt, terwijl schoonmaken gebeurt wanneer een bulletin verbonden aan een Campagne van Adobe wordt gekopieerd of gekleefd (NPR-32540).

### Sling {#sling-6480}

* Niet-deterministische schaduwen van waarneming van middelen werken niet (CQ-4286466).

### Projecten {#projects-6480}

* De Create knoop is niet zichtbaar aan de gebruiker zelfs als de gebruiker toestemming heeft om project in de subfolder (NPR-31831) tot stand te brengen.

* De functionaliteit om tussen de Mening van de Kaart, de Mening van de Lijst en de Mening van de Kalender te schakelen werkt niet na het selecteren van de mening van de Kalender in Projecten (NPR-31829).

### Vertaling {#translation-6480}

* De verwezenlijking van het vertaalproject voor veelvoudige talen produceert het project slechts voor enkele talen in plaats van allen en een fout (de redacteur van het middel is reeds gesloten) wordt waargenomen in het logboek (NPR-32212).

### WCM-sjablooneditor {#wcm-template-editor-6480}

* De pieken van cpu en de Manager van de Ervaring worden niet ontvankelijk wanneer URLs die met eindigt `/_jcr_content/.html` of `/jcr:content/.html` wordt betreden (CQ-4280770).

### WCM-MSM {#wcm-msm-6480}

* De kwesties van de toestemming leiden tot vertoning van fouten terwijl het bewegen van pagina&#39;s binnen een blauwdruk (NPR-32610).

### WCM-paginaeditor {#wcm-page-editor-6480}

* Browser houdt op antwoordend terwijl het proberen om een component aan een pagina met een specifiek formaat toe te voegen URL (NPR-32368, NPR-31917).

### WCM-beheer-UI {#wcm-admin-ui-6480}

* Beheer publicatie omvat geen items waarnaar verwezen wordt in het verzoek om de activeringsworkflow (NPR-32304).

### Gemeenschappen {#communities}

* Kan de groependuimnagelafbeelding voor groepen (NPR-32603) niet bijwerken.

### Merk Portal {#brand-portal}

* Unpublished het meta-gegevensschema in de Activa van AEM bevolkt een foutenmelding hoewel het schema bij achtereind (CQ-4286871) wordt verwijderd.

### Foundation-UI {#foundations-ui-6480}

* Ongeldige die karaktervertoning in URL aan een component van de Knoop wordt toegevoegd (NPR-32684).

### Formulieren {#forms}

>[!NOTE]
>
>AEM Service Pack omvat geen moeilijke situaties voor Vormen AEM. Zij worden geleverd gebruikend een afzonderlijk toe:voegen-op pakket van Vormen. Bovendien wordt een cumulatieve installateur vrijgegeven die moeilijke situaties voor Vormen AEM op JEE omvat. Voor meer informatie, zie [installeer toe:voegen-op pakket](#install-aem-forms-add-on-package) van Vormen AEM en [installeer de installateur](#install-aem-forms-jee-installer)van JEE van Vormen AEM.

* Ontwerper: Als de etiketteringsoptie wordt toegelaten, verdwijnt de subform grens in de geproduceerde output PDF (NPR-32546, NPR-32322).

* Ontwerper: Als er samengevoegde cellen in een lijst zijn, ontbreekt de toegankelijkheidstest voor het outputPdf- dossier dat van een vorm wordt omgezet XDP gebruikend de outputdienst (NPR-32079).

* Documentbeveiliging: Een beschermd Pdf- dossier slaagt er niet in om off-line met de optie te openen DisableGlobalOfflineSynchronizationData die aan Waar (NPR-32080) wordt geplaatst.

* Documentbeveiliging: Kwesties terwijl het openen van een beschermd Pdf- dossier na bevordering van ES4 aan AEM 6.3 (NPR-32170).

* Documentservices: Een foutenmelding toont terwijl het proberen om een Pdf- dossier in een document om te zetten PDF/A gebruikend de methode van de toPDFA omzetting (NPR-32663).

* Documentservices: Een uitzonderingsvertoningen terwijl het toepassen van de dienst van de Uitbreidingen van de Lezer op een Pdf- dossier (NPR-32639).

* Documentservices: Een foutenmelding toont terwijl het assembleren van en het omzetten van XDP dossiers in Pdf- dossiers (NPR-31821).

* De analyses tonen geen aangewezen resultaten bij het voorleggen van of het verlaten van vormen op een pagina van Plaatsen (NPR-31359).

### Hotfixes en de Pakken van de Eigenschap inbegrepen in vorige Pakken van de Dienst {#hotfixes-and-feature-packs-included-in-previous-service-packs}

#### AEM 6.4.7.0 {#experience-manager-6470}

AEM 6.4.7.0 is een belangrijke update die prestaties, stabiliteit, veiligheid en zeer belangrijke klantenmoeilijke situaties en verhogingen omvat die sinds de algemene beschikbaarheid van AEM 6.4 in **april 2018 worden vrijgegeven.**

Het is ook cumulatief, wat betekent dat 6.4.7.0 al AEM 6.4 de dienstpakken versie vóór het omvat.

Enkele zeer belangrijke hoogtepunten van AEM 6.4.7.0 zijn:

* De ingebouwde opslagplaats (Apache Jackrabbit Oak) wordt bijgewerkt naar versie 1.8.17.
* Toegevoegde steun om versie van een pagina van Plaatsen te plaatsen terwijl het schrappen van het.
* De nieuwe kolom voor gecreeerde datum, die sorteerbaar is, is toegevoegd in de **DAM lijstmening** en op de resultaten van het activaonderzoek in de mening van de **Lijst** (NPR-31311).
* Het sorteren van activa op de kolom van de **Naam** wordt gebaseerd is toegestaan in de mening die van de **Lijst** .
* De grootte van de partij en de onderbrekingen van de werkschema voor het Herproces en de Upload van de Partij zijn nu configureerbaar van UI in Dynamische Media.
* De `pdfBrochure` is geplaatst aan vals in Scene 7 wolkenconfiguratie, om geheugen bij IPS te bewaren.

##### Assets {#assets-6470}

**Productverbeteringen**

* De de uitvoerversie van API pakket dat door `package com.day.cq.dam.handler.standard.msoffice` `dam-handler` bundel wordt gesteund wordt bevorderd tot 6.0.0 (CQ-4279059).
Als u het pakket `com.day.cq.dam.handler.standard.msoffice` in uw douaneimplementatie gebruikt, dan wordt het geadviseerd dat u uw `dam-handler` bundel met de recentste uberpot compileert.

**Fixes**

* De meta-gegevens voor sommige Pdf- documenten worden niet bijgewerkt en aan PDF bewaard bij het wijzigen van zijn titel (NPR-31575).

* Activa met het &quot;+&quot;-symbool in de bestandsnaam kunnen niet worden verwijderd (NPR-30588).

* De de omslageigenschappen van DAM tonen niet de toegevoegde gebruikers of de groepen (die door synchronisatie LDAP worden gecreeerd) in Gesloten Gebruikersgroepen (NPR-30555).

* Speciale tekens die voorkomen in de onderwerpregel van e-mailtemplates worden niet goed weergegeven (NPR-30547).

* De namen van activa worden veranderd in lager geval wanneer het bewegen van activa van één omslag aan een andere in AEM die op Dynamische runmode van Media Scene 7 (NPR-31631) lopen.

* De namen van imageset worden veranderd in lager geval in Scene 7, wanneer imageset (of mediaset) wordt gecreeerd en met aangewezen noemende overeenkomst in DAM (NPR-31576) genoemd.

* De dynamische Media Encodeert het Videowerkschema slaagt er niet in om duimnagel voor de video te produceren die van Scene 7 aan Dynamische Media - Scene 7 looppaswijze (NPR-31523) wordt gemigreerd.

* De interne Fout van de Server wordt waargenomen terwijl het gebruiken van filter aan onderzoek naar Reeksen, in AEM die op Dynamische Media loopt - Scene 7 runmode (NPR-31388).

* De fout wordt waargenomen terwijl het uitgeven van een verre imageset, voor het beeld dat in de omslag verblijft genoemd het zelfde als Scene 7 bedrijfnaam (NPR-31347).

* De activa die verwijzingen bevatten worden niet gepubliceerd (DM) (NPR-31179).

* De afloop (de tijd van het cliëntgeheime voorgeheugen om te leven) waarde die voor Dynamische Hybride wijze wordt gevormd van Media wordt niet herhaald aan de Dynamische de leveringsmilieu van Media (NPR-31126).

* Uploads van Dynamische Media AEM - Scene 7 runmode aan Scene 7 duurt te lang om te voltooien (NPR-30926).

* Na het creëren van een pagina die de Dynamische component van Media heeft terwijl het publiceren van het zelfde, van auteursinstantie die op Dynamische Media loopt - Scene 7 runmode, wordt de gebruiker ertoe aangezet om de configuratie dmscène7 (NPR-30880) te publiceren.

* De waarde van de &quot;activa&quot;parameter in kijker inbedde code blijft onveranderd na het veranderen van de waarden in &quot;Titel na beweging&quot;en &quot;Naam na beweging&quot;gebied op Dynamische Media - Scene 7 (NPR-30745).

* De het onderzoek van de aanraking UI (die door Omnissearch wordt gedaan) resultatenpagina scrolt automatisch omhoog en verliest de rolpositie van de gebruiker (NPR-31306).

* De Zuivering van de Gebeurtenis van DAM schrapt de recentste (maxSavedActivities) gebeurtenisgegevens en houdt de gegevens die vroeger (NPR-30870) worden gecreeerd.

* De de titel en naamverandering van activa voortduurden niet na beweging aan een bestemmingsomslag die het oneindige scrollen teweegbrengt terwijl het selecteren van het (NPR-30647).

* De inzamelingen worden verwijderd uit de mening bij het toepassen van om het even welke filter in activa AEM die van de Verbinding van de Activa van Adobe worden betreden (CQ-4280534).

* De grootte van de partij en werkschemastap onderbreking voor het Herproces en de Upload van de Partij zijn niet configureerbaar van UI, en moeten in CRXDE worden geplaatst en werkschema moet tweemaal worden gesynchroniseerd (CQ-4281254).

* De de stapnaam van het werkschema voor partij upload en eenvoudig upload stap is het zelfde in Scene 7, die tot verwarring (CQ-4281176) leidt.

* Het werkschema van het herproces in Scene 7 wordt geplakt als een activa meta-gegevensknoop (CQ-4281170) missen.

* BatchUpload stap in het herproceswerkschema werkt niet voor de omslag die videoactiva (CQ-4280630) heeft.

* De opties PDF die naar DM worden verzonden hebben extractKeywords die aan waar door gebrek (CQ-4280101) wordt geplaatst.

* De ongeldige Uitzondering van het Punt wordt waargenomen op lopende Scene 7 het werkschema van het Herproces op een omslag die activa niet-DM (CQ-4279555) bevat.

* De activa die in AEM anders noemen kunnen niet aan scène 7 synchroniseren, wanneer een activa met een dubbele naam reeds bij Scene 7 (CQ-4276763) bestaat.

* Het postdossier dat per e-mail voor activadownload wordt verzonden slaagt er niet in unzip wanneer een gebruiker met Gelezen toestemmingen probeert om het te openen (CQ-4277925).

* PPT Rendition Workflow levert geen rendities op van de geüploade PPT-bestanden, aangezien AEM 6.4 niet kan worden bijgewerkt naar com.adobe.granite.poi versie 2.0.28 (CQ-4279059).

* PDF-bestanden zijn niet geïndexeerd en inhoud binnen kan niet worden doorzocht (CQ-4278916).

##### Sites {#sites-6470}

* Wanneer de lanceringen met Bevorderen slechts Gewijzigde pagina&#39;s worden bevorderd en de lanceringen met gewijzigde pagina&#39;s bevorderen worden gedaan, slechts verschijnen de gewijzigde pagina&#39;s om worden bevorderd. Bovendien worden, wanneer de lijst die moet worden bevorderd juist is, de niet-gewijzigde pagina&#39;s nog steeds onderaan de lijst (NPR-31314) weergegeven.

* Wanneer een pagina van de Plaatsen AEM naar een verschillende plaats wordt verplaatst, worden zijn eigenschappen niet dienovereenkomstig bijgewerkt om op zijn nieuwe plaats (NPR-31265) te wijzen.

* Voor een nieuwe blauwdruk, als het aantal verslagen meer dan 40 is, slechts worden de eerste 40 verslagen getoond. De blauwdruk toont lege lijnen voor de rest van de verslagen (NPR-31182).

* Wanneer het aantal LiveCopies groot is, duurt het overzicht LiveCopy lang om de voorproef (NPR-30945) terug te geven.

* Toegevoegde steun om een versie van een pagina te plaatsen terwijl het schrappen van het. Als versioning voor de geschrapte pagina onbruikbaar wordt gemaakt, kunnen de Plaatsen AEM dergelijke pagina&#39;s niet herstellen (NPR-30891).

* Wanneer een gebruiker Japanse of Koreaanse karakters in het beschrijvingsbezit van een menu toevoegt, toont het menu vervormde karakters voor Japanse en Koreaanse taaltekst (NPR-31331).

* Wanneer een gebruiker zich op linker spoorgebieden concentreert en een toetsenbordkortere weg gebruikt om inhoud te kleven, kleeft het de inhoud van het klembord van de paginaredacteur in plaats van de inhoud die van de linkerspoorgebieden (NPR-31169) wordt gekopieerd.

* Wanneer een gebruiker een inhoudsfragment uitgeeft, wordt de reeds geschrapte variatie van het inhoudsfragment hersteld (NPR-31178).

* De vraag van de Modellen van het Fragment van de inhoud is inefficiënt. Het is zeer langzaam als de instantie heel wat pagina&#39;s heeft en in een fout (NPR-30666) resulteert.

* Bij het bewaren van het model van het inhoudsfragment, wordt de tijd op het datum en tijdgebied geplaatst aan 00:00 (NPR-30540).

##### Integratie {#integrations-6470}

* Wanneer het vormen van de Lancering van Adobe, wordt een voorwaartse schuine streep (/) prepended in de bibliotheek URL (NPR-30700).

* De prestaties van ContextHub degraderen na het publiceren (NPR-30884).

##### Sling {#sling-6470}

* Werk de webconsoleleveranciersbundelversie bij naar 1.2.4 om de afhankelijkheid van de startpagina van het lanceerplatform te verwijderen van de webconsolesecurityprovider (NPR-30885).

##### Platform {#platform-6470}

* De updates in de configuratie van de buffergrootte voor de op Jetty-Gebaseerde dienst van HTTP worden niet bewaard (NPR-30925).

* QueryBuilder steunt nu orderby fn:name () in xpath queries (NPR-31322).

* Bijgewerkt het Ruilen verdeelde gebeurtenisadmin aan versie 1.1.4 verbeterend de kwaliteit van logboeken in een gegroepeerde milieu (NPR-29256).

##### Foundation-UI {#foundation-6470}

* Het scrollen aan het eind van de resultatenpagina met een groot aantal onderzoeksresultaten veroorzaakt browser om te botsen (NPR-31332).

* Wanneer het schakelen van de mening van de Kaart aan de mening van de Lijst op een pagina van onderzoeksresultaten, is er een vertraging vóór de pagina kan worden gescrold (NPR-31280).

##### Oak {#oak-6470}

* De dossiers van MS Office met .docx en .xlsx- dossieruitbreidingen die beelden JPEG bevatten ontleden niet gebruikend Tika parser (NPR-31693).

##### Livefyre {#livefyre-6470}

* De levensintegratie met AEM 6.4 verbetering geeft de Volledige Uitzondering van het Punt, wanneer de integratie gebruikend DITA plugin voor synthetische middelen wordt gedaan. De integratie, echter, werkt wanneer de componenten manueel worden toegevoegd (FYR-11066).

##### Vertaling {#translation-6470}

* De weg aan het fragment van de bestemmingservaring wordt niet bijgewerkt wanneer het bevorderen van een lanceringspagina (NPR-30830).

##### Gemeenschappen {#communities-6470}

* De e-mailfunctionaliteit werkt in sommige gevallen niet behoorlijk zelfs wanneer het e-mailoverseinen in berichtmontages wordt toegelaten, werpt het systeem een uitzondering in NomissionsActivityStreamProvider (NPR-31521).
* Niet in staat om nieuwe leden te creëren, verschijnt het lege scherm op het Create scherm van het Lid in AEM auteursinstantie (NPR-30951).
* De gebruiker kan geen commentaar op een blog in Internet Explorer 11 (NPR-30927) plaatsen.
* De beheerder van een Beperkte Groep kan niet de Kaart van de Groep bekijken, kan om het even welke Snelle verrichtingen van de Verbinding (geef uit/publiceer/schrap groepen) in AEM auteursinstantie (NPR-30810) niet uitvoeren.
* De informatie van de lidgroepen/van de Groep is niet zichtbaar bij het creëren van een nieuwe Plaats in de auteur van AEM instantie (NPR-28840).

##### Formulieren {#forms-6470}

>[!NOTE]
>
>AEM Service Pack omvat geen moeilijke situaties voor Vormen AEM. Zij worden geleverd gebruikend een afzonderlijk toe:voegen-op pakket van Vormen. Bovendien wordt een cumulatieve installateur vrijgegeven die moeilijke situaties voor Vormen AEM op JEE omvat. Voor meer informatie, zie [installeer toe:voegen-op pakket](#install-aem-forms-add-on-package) van Vormen AEM en [installeer de installateur](#install-aem-forms-jee-installer)van JEE van Vormen AEM.

**Formulierinvoegpakket**

**Aanpassingsvormen**

* De koorden bevatten de woordenboeksleutel terwijl het lokaliseren van adaptieve vormen (NPR-31109).

* De checkboxes en drop-down lijsten in Vormen ontbreken de controles van de Toegankelijkheid (NPR-31282).

**HTML5-formulieren**

* Het produceren van HTML5 voorproef van een vorm XDP toont een flikkering terwijl het toevoegen van instanties van subform (NPR-30907).

**Documentservices voor OSGi**

* De lopende veelvoudige gelijktijdige draad voor het assembleren van de vormen gebruikend de methode com.adobe.fd.assembler.service.AssemblerService.invoke () toont een foutenmelding (NPR-31164).

* De tijdelijke dossiers die door de Dienst van de Assembler worden gecreeerd worden niet automatisch geschrapt en vereist nieuw begin AEM (NPR-30846).

* Het toepassen van ReaderExtension Rechten op PDF resulteert in een foutenmelding (NPR-30930).

**Werkstroom**

* De OSGi-workflow is mislukt als gevolg van 100% CPU-gebruik (NPR-31234).

**Forms JEE-installateur**

**Documentservices**

* De convert PDF-service kan PDF-documenten niet converteren naar PostScript en geeft een foutbericht weer (NPR-31267).

* De het eindpuntconfiguratie van de ZEEP stelt na het toepassen van een flard terug om HTML op mislukking te bevestigen PDF (NPR-31309).

**PDFG-service**

* Kan het gedownloade Adobe PDF-instellingenbestand niet uploaden met de admin UI (NPR-31273).

#### AEM 6.4.6.0 {#experience-manager-6460}

AEM 6.4.6.0 is een belangrijke update die prestaties, stabiliteit, veiligheid en zeer belangrijke klantenmoeilijke situaties en verhogingen omvat die sinds de algemene beschikbaarheid van AEM 6.4 in **april 2018 worden vrijgegeven.**

Het is ook cumulatief, wat betekent dat 6.4.6.0 al AEM 6.4 de dienstpakken versie vóór het omvat.

Enkele zeer belangrijke hoogtepunten van AEM 6.4.6.0 zijn:

* De ingebouwde opslagplaats (Apache Jackrabbit Oak) wordt bijgewerkt naar versie 1.8.15.
* Toegevoegde steun voor het volgen van dynamische-UI-staten in het volgen van gebeurtenis in de stichting API.
* Ondersteuning voor renditie toevoegen aan de component van de afbeeldingskern.

**Assets**

* De het aandeelverbinding van activa van een omslag met ruimte en `&` karakter in de naam toont lege grijze kaarten voor sommige activa. NPR-29934: Hotfix voor CQ-4270187
* DAM-workflow crasht terwijl MP4-elementen voor AEM worden gemaakt. NPR-30031: Hotfix voor CQ-4271352
* De de connectiviteitskwestie van de Markering van Adobe Slimme door Datapower. NPR-30026: Hotfix voor CQ-4269457
* PDF kan niet worden gevonden gebruikend OmniSearch. NPR-30046: Hotfix voor GRANITE-26290
* De wegen van activa in URLs en omslagmeta-gegevens die door de ACS API worden geproduceerd zijn geen URL gecodeerd.  GRANITE-26198: Hotfix voor CQ-4271814
* Creeer de taakfunctionaliteit van het Overzicht werkt niet toe te schrijven aan niet gedefiniëerde lading. NPR-30469: Hotfix CQ-4274263
* De capaciteit om de mening van kaartmening aan lijstmening te schakelen en vice versa verdwijnt na het doen van een OmniSearch op de activaplukker. NPR-29852: Hotfix voor CQ-4269369
* (Tik op UI) Tijdens het beheren van de publicatietovenaar, worden de activa toegevoegd aan de replicatierij nadat de pagina&#39;s worden toegevoegd, vandaar veroorzakend enkele activa om na een paar seconden te verschijnen. NPR-29985: Hotfix voor CQ-4270724
* Het sorteren van onderzoeksvraag door relevantie keert documenten InDesign samen met malplaatjes InDesign terug. Hotfix voor CQ-4273864
* Als de gebruiker een e-mailid in hoofdletters heeft, kunnen de gebruikers niet inchecken voor de activa die eerder zijn uitgecheckt. Hotfix voor CQ-4276575
* Het vormen van de Dynamische Diensten van de Wolk van Media op `DMHybrid` wijze resulteert in veelvoudige lege rapportreeksen die in Analytics worden gecreeerd zonder die rapportreeks identiteitskaart op AEM wordt opgeslagen resulterend in de verdubbeling van de rapportreeks. Hotfix voor CQ-4276855
* De dialoog van de waarschuwing verschijnt niet terwijl het bevorderen in &quot;Beheerde Markering&quot;pagina. Hotfix voor CQ-4252851
* Wanneer het gebruiken van de carrousel voor het beheren van markeringen, werkt de navigatieknoop niet. Hotfix voor CQ-4275499
* De functionaliteit van de Bulk-verplaatsingsactiva wordt gebroken resulterend in het niet bewegen van activa. Hotfix voor CQ-4272987

**Sites**

* `pageinfo.json` de verzoeken zijn uiterst traag en duren te lang om te laden . NPR-29709: Hotfix voor CQ-4269560
* `onTime` of de `offTime` meta-gegevenseigenschappen bewaard op activa worden niet herinnerd als de server AEM opnieuw wordt begonnen. NPR-30413: Hotfix voor CQ-4272784
* Wegens onjuist gedrag van klasse ConfigPostProcessor, verwijdert het opschorten van ouderpagina cq: Het mengen van LiveRelatie type van de kindpagina. NPR-30536, NPR-30510: Hotfix voor CQ-4254113
* Het scripting van de dwars-plaats (XSS) op bij het werkschemadialoog van het Begin in het uitgeven van de Campagne pagina. NPR-29747: Hotfix voor CQ-4271067
* (Klassieke UI) Het de slotstadium van het Werkschema maakt het werkschemabblad onbruikbaar tot het slot wordt vrijgegeven. NPR-30356: Hotfix voor CQ-4237557
* (IE11) Wanneer het kleven van de inhoud van HTML in een Rijke component van de Redacteur van de Tekst met defaultPasteMode = plaintext, wordt HTML gekleefd met het formatteren, vandaar, heeft defaultPasteMode geen effect. NPR-30045: Hotfix voor GRANITE-26094
* (Klassieke UI) Wanneer de pagina van plaatsadmin wordt herladen, zijn alle dropdown punten in het &quot;Nieuwe&quot;menu gehandicapt. NPR-29980: Hotfix voor CQ-4272044
* Kan geen stijlen aan de tekst toevoegen of bestaande stijlen bewerken die op de inhoud zijn geschreven. NPR-29712: Hotfix voor CQ-4266249
* (Klassieke UI) Activa zonder DC: de titelwaarde is vermeld zonder titel in browser van de de dialoogdoos van het weggebied. NPR-30166: Ondersteunend verzoek voor CQ-88858
* De vraag: de luisteraar werkt niet met genestelde componenten zelfs na het toevoegen van de component parsys. NPR-30422: Hotfix voor CQ-4274863
* De fout van ContextHub tijdens integratie van AEM en van de Campagne. NPR-30625: Hotfix voor CQ-4250790
* De waarde van de resourceType verzoekparameter wordt gekopieerd in de waarde van een de markeringsattribuut van HTML dat in dubbele aanhalingstekens ingekapseld is. NPR-29832: Hotfix voor CQ-4255365
* Een pagina verfrist zich is nodig nadat de componenten van één pagina aan een andere worden gekopieerd en worden gekleefd. NPR-29982: Hotfix voor CQ-4256019
* Publiceer/maak van een pagina alias ongedaan wordt niet gesteund en zou moeten worden verwijderd. NPR-30062: Hotfix voor CQ-4271249
* De niet gesloten waarschuwing ResourceResolver in ExperienceFragmentReplicationListener die tot stabiliteitskwesties in tijd leidt, dwingend om AEM instanties opnieuw te beginnen. NPR-30416: Hotfix voor CQ-4257521
* De bewegende Fragmenten van de Ervaring die in meer dan 150 pagina&#39;s van verwijzingen worden voorzien wijzigen niet fragmentPath in de pagina&#39;s waar zij van verwijzingen worden voorzien. NPR-30556: Hotfix voor CQ-4274900
* Het ontleden fout wanneer het openen van een Fragment van de Inhoud dat karakters dollar ($) en open steun ({) heeft na elkaar. Hotfix voor CQ-4270266
* VersionPreviewServlet ontbreekt in NullPointerException wanneer het proberen om een versie van een Fragment van de Ervaring in de chronologie te tonen. NPR-30074: Hotfix voor CQ-4271881
* Onbekwaam om inhoudsfragmenten via de controleeigenschap te sluiten. NPR-29923: Hotfix voor CQ-4258785

**Replicatie**

* De Zitting van JCR/Resolver van het Middel wordt gelekt tijdens de implementatie van OAuth op elke replicatie aan MAC/het Portaal van het Merk. NPR-30000: Hotfix voor Graniet-26196

**Sling**

* De orde van kinderen beïnvloedde het gebruiken van overlapping en orde alvorens veroorzaakt IndexOutOfBoundException. NPR-30408: Hotfix voor Sling-8296 &amp; Sling-7375
* InactiveBundlesHealthCheck leest MissingPackagesHealthCheck configuratie af zodra de configuraties InactiveBundlesHealthCheck zijn opgeslagen. NPR-30084: Hotfix voor CQ-4272644

**Handel**

* Onbekwaam om catalogusblauwdruk van de console van Plaatsen in werking te stellen. NPR-29829: Hotfix voor CQ-4271461
* Het in het product gebruikte activum bevat geen verwijzing naar het product in de sectie &quot;Referenties&quot; van het activum, noch wordt het activapad bijgewerkt als het actief wordt verplaatst. NPR-30542: Hotfix voor CQ-4270247

**Platform**

* AEM de StandaardAfzender van de Post kan post naar een verre server SMTP over TLS v1.2 verzenden niet. NPR-30476: Hotfix voor GRANITE-26605

**Gemeenschappen**

* De groepen die op de auteur worden geschrapt zijn niet in synchronisatie met alle uitgevers. NPR-29987: Hotfix voor CQ-4268738
* De geschrapte gebruikers die uit het Gebied van de Beheerders worden verwijderd Communautaire zijn niet in synchronisatie met de groep van het Lidmaatschap. NPR-30389: Hotfix voor CQ-4274339
* Het gedeelte van gebruikers van de groep van beheerders heeft geen snelle verbindingen voor de groep. NPR-30546: Hotfix voor CQ-4275579
* Het bijwerken van om het even welke pas gecreëerde en bestaande communautaire groep beschrijft het bezit op jcr: de inhoudsknoop en verandert hun naam in de titel van de eerste pagina. NPR-30109: Hotfix voor CQ-4273719
* Het quicksearch en het onderzoek door plaats en adres werken niet wanneer de gemeenschap aan het werk met de Leverancier van het Middel van de Opslag van het Gegevensbestand (DSRP) wordt geplaatst. NPR-26737: Hotfix voor CQ-4258493

**Vertaling**

* Auto-uitvoering van Vertaling werkt niet. NPR-30499: Hotfix voor CQ-4276288
* De gebruiker kan taalexemplaar op de inhoudsweg tot stand brengen die tot read-only wordt beperkt. NPR-29937: Hotfix voor CQ-4270708
* Vertaalprobleem - Slechts enkele onderdelen worden vertaald met behulp van Machine Translation. NPR-30079: Hotfix voor CQ-4273764

**Integratie**

* De aangepaste inhoud wordt niet correct getoond op publiceren instantie tot het nieuwe begin van de instantie. NPR-30421: Hotfix voor CQ-4273706

**Projecten**

* dam: folderThumbnailPaths de waarden worden niet vernieuwd en tonen oude duimnagels zelfs na het schrappen van de activa binnen de omslag. NPR-30424: Hotfix voor CQ-4273667

**UI-consoles**

* Het scripting van de dwars-plaats (XSS) op de paginaeigenschappen van Plaatsen op duimnagel tabel. NPR-30048: Hotfix voor Graniet-26200

**UI-Foundation**

* Toegevoegde steun voor het volgen van dynamische-UI-staten in het volgen van gebeurtenis in de stichting API. NPR-30742, GRANITE-26322: Hotfix voor GRANITE-26036

**Formulieren**

>[!NOTE]
>
>AEM Service Pack omvat geen moeilijke situaties voor Vormen AEM. Zij worden geleverd gebruikend een afzonderlijk toe:voegen-op pakket van Vormen. Bovendien wordt een cumulatieve installateur vrijgegeven die moeilijke situaties voor Vormen AEM op JEE omvat. Voor meer informatie, zie [installeer toe:voegen-op pakket](#install-aem-forms-add-on-package) van Vormen AEM en [installeer de installateur](#install-aem-forms-jee-installer)van JEE van Vormen AEM.

**Formulierinvoegpakket**

**Aanpassingsvormen**

* Het lege .css dossier vergt langere tijd om van de uitgever te halen, veroorzakend prestatieskwestie. NPR-30558: Hotfix voor CQ-4274399
* De vormen die na het publiceren worden gewijzigd worden niet opnieuw gepost op het publiceren van de plaats. NPR-30411: Hotfix voor CQ-4236566

**Formulieren - Backend Integration**

* Een fout wordt geworpen terwijl het creëren van het Model van de Gegevens van de Vorm met de Taal van de Definitie van de Dienst van het Web (WSDL). NPR-30388: Hotfix voor CQ-4272921

**Formulieren - Correspondentiebeheer**

* De speciale karakters zoals minder-dan (&lt;), groter-dan (>) en ampersand (&amp;) worden gecodeerd in de Agent UI. NPR-30410: Hotfix voor CQ-4273887
* Wanneer het teweegbrengen van tekstfragment dat de waarden van het Woordenboek van Gegevens bevat, wordt de Agent UI unresponsief. NPR-30098, NPR-30083: Hotfix voor CQ-4272204
* Creeer Correspondentie UI (CCR UI) ontbreekt periodiek met foutenvariabele (objecten Voorwerp). NPR-29983: Hotfix voor CQ-4273874
* Het ontwerp van de brief herlaadt ontbreekt met een uitzondering wanneer de beschrijving van de Fragmenten van het Document speciale karakters zoals minder-dan (&lt;), groter-dan (>) en ampersand (&amp;) in eigenschappen bevat. NPR-29930: Hotfix voor CQ-4252762

**HTML5-formulieren**

* Wanneer het gebruiken van de Toegang van de Desktop nietVisual op Browse wijze om een vorm te lezen HTML5, browser van het Chroom leest &quot;grafisch&quot;vóór elke Scalable Vector Grafisch (SVG) in het vormontwerp. NPR-30450: Hotfix voor CQ-4274732

**Forms JEE-installateur**

**Formulieren - Foundation JEE**

* Het toevoegen van of het uitgeven van een verbinding van de Dienst van het Web door de Webdiensten van de Werkbank van de Vormen aan te halen AEM werpt een fout: ClassNotFoundException org.apache.as.message.SOAPBodyElement. NPR-30116: Hotfix voor CQ-4273217

**Formulieren - Documentservices**

* Het etiket PDF/A mist fout in de preflight van de Acrobaat. NPR-30594: Hotfix voor CQ-4276032
* De Bindingen van de Gegevens van enig karakter in PDF veroorzaken de Uitbreidingen van de Lezer om met een fout &quot;java.lang.StringIndexOutOfBoundsException te ontbreken: De index van het koord uit waaier: 1&quot;. NPR-30128: Hotfix voor CQ-4273878
* Wanneer een ladingstest op de dienst van HTML aan PDF wordt uitgevoerd, ontbreekt het met een fout en de dossiertype montages worden verwijderd uit AEM vormenserver. NPR-30085: Hotfix voor CQ-4272631
* Het afvlakken van een PDF met Acrobaat 9.1 van Adobe (XFA versie 3.0) behoudt niet de PDF vormstaat: De onzichtbare elementen op de vorm worden terug geplaatst naar een zichtbare staat. NPR-29978: Hotfix voor CQ-4270888

**Formulieren - Documentbeveiliging**

* Het toepassen van een handtekening met timestamp ontbreekt met fout: ALC-DSC-003-000: com.adobe.idp.dsc.DSCInvocationException: Inroepfout. NPR-30696, NPR-30537: Hotfix voor CQ-4273778
* De Manager van de configuratie neemt geen Japanse koorden voor gelokaliseerde lijstkolommen op. NPR-30496: Hotfix voor CQ-4274868

**PDFG-service**

* De fout van de verbinding terwijl het proberen om het document van Word in PDF op de Server 2016 van Vensters om te zetten. NPR-30597: Hotfix voor CQ-4275652
* De toestemming ontkende uitzondering wanneer het proberen om de dienst van HTML te gebruiken aan PDF achterste deelgenoot via de &quot;fantomjs&quot;bibliotheek. NPR-30456: Hotfix voor CQ-4258077
* maxReuseCount voor de dienst van HTML aan PDF wordt niet getoond met de Console van het Beheer JBoss. NPR-30303, NPR-30135: Hotfix voor CQ-4273763

#### AEM 6.4.5.0 {#experience-manager-6450}

AEM 6.4.5.0 is een belangrijke update die prestaties, stabiliteit, veiligheid en zeer belangrijke klantenmoeilijke situaties en verhogingen omvat die sinds de algemene beschikbaarheid van AEM 6.4 in **april 2018 worden vrijgegeven.**

Het is ook cumulatief, wat betekent dat 6.4.5.0 al AEM 6.4 de dienstpakken versie vóór het omvat.

Enkele zeer belangrijke hoogtepunten van AEM 6.4.5.0 zijn:

* De ingebouwde opslagplaats (Apache Jackrabbit Oak) wordt bijgewerkt naar versie 1.8.13.
* Toegevoegde contactdoosonderbreking en verbindingsonderbreking in de agenten van de Portaal van het Merk.
* De verhogingen van het onderzoek - verhoogde de paginatielimiet van het onderzoeksresultaat tot 100 pagina&#39;s.
* De gehandicapte `AssetDownloadServlet` component OSGi door gebrek op AEM publiceert instanties. Voor meer informatie, zie de activa van de [Download van AEM](/help/assets/download-assets-from-aem.md).
* Ondersteuning voor beheer op meerdere sites voor bedrijfsmiddelen. Voor meer informatie, zie [Hergebruik activa gebruikend MSM voor Activa](/help/assets/reuse-assets-using-msm.md).

**Assets**

* De activa met een weglatingsteken in filename synchroniseren niet aan Dynamische Media. NPR-29538: Hotfix voor CQ-4270592
* De bijgewerkte interface van DAM DMGGateway voor S3 multipart steun. NPR-29740: Hotfix voor CQ-4226303
* De dialoog van de activadownload toont een onjuiste dossiergrootte wanneer het downloaden van vertolkingen voor een video in Dynamische Media. NPR-29642: Hotfix voor CQ-4246202
* De activa worden onbruikbaar na Dag CQ DAM Mime Type Service past tekst voor m3u8 toe. NPR-29276: Hotfix voor CQ-4264052
* De de verwijzingsaanpassing van activa slaagt er niet in om de zitting te bewaren als om het even welke bewogen/anders genoemd activa deel van het Verdelen van de inzamelingen van het Middel uitmaken. NPR-29143: Hotfix voor /CQ-4252605
* Kan activa volgen of vinden niet door de meta-gegevenswaarden te zoeken. NPR-29141: Hotfix voor CQ-4260215
* Wanneer het gebruiken van de onderzoeksfilter om een Slimme Inzameling te bewaren, handhaaft de klikactie op het paneel geen nadruk. NPR-29000:  Hotfix voor CQ-4240323
* Het bewegen van een omslag staat de verwezenlijking van een omslag met gemengde of hoofdletters namen toe. NPR-28945: Hotfix voor CQ-4265234
* De lege resultaten die in Onderzoek worden getoond als de inzamelingsnaam ruimte heeft. NPR-29001: Hotfix voor CQ-4236729
* Het anders noemen van een dossier gebruikend sommige niet gestaafde speciale karakters zoals ampersand (&amp;) leidt tot een ongeldige omslag. NPR-29196: Hotfix voor CQ-4265037
* DAM Extract Archive for zip file functionaliteit is kapot. NPR-29187: Hotfix voor CQ-4254421
* De invoer van meta-gegevens zou het invoeren van meta-gegevens moeten toestaan zonder namespaces te registreren. NPR-29425, NPR-28132: Hotfix voor CQ-4269445
* De de meta-gegevensveranderingen van de besparing werken niet voor activa de waarvan naam een citaatkarakter bevat. NPR-29395: Hotfix voor CQ-4254305
* Kan een activa van DAM bewegen niet als filename whitespace bevat. NPR-29270: Hotfix voor CQ-4266403
* Kan de archieven van het PIT downloaden die met het algoritme Deflate64 worden samengeperst niet. NPR-29225: Hotfix voor CQ-4253995
* De duimnagels van activa worden getoond langzaam wanneer het openen van een omslag die activa met vele versies bevat. NPR-29833: Hotfix voor CQ-4271629
* Onbekwaam om de benadrukte inzameling in te gaan als de Enter sleutel na het selecteren van de inzameling wordt gedrukt. NPR-29723: Hotfix voor CQ-4261607
* De dwars-plaats scripting (XSS) aanval door het beperkte waakzame venster. NPR-29671: Hotfix voor CQ-4270133
* Het toevoegen van verhoudingen aan activa ontbreekt voor gebruikers zonder schrappingstoestemmingen. NPR-29640: Hotfix voor CQ-4269196
* Na het toevoegen van activatitel in de eigenschappen pagina, wanneer de gebruiker probeert om de pagina te sluiten, opent AEM opnieuw de eigenschappen pagina. NPR-29628: Hotfix voor CQ-4264929
* Het creëren van een groot aantal verhoudingen op activa resulteert in een fout. NPR-28779: Hotfix voor CQ-4250708
* De opname van activa is langzaam op Scene7 verbindt looppaswijze. NPR-28658: Hotfix voor CQ-4263007
* Een fout UncaughtTypeError: Kan bezit &quot;delen&quot;van niet lezen niet wordt getoond wanneer het proberen om de onderzoeksresultaten te bekijken. NPR-28803: Hotfix voor CQ-4248371
* De replicatie van AEM aan het Portaal van het Merk is geplakt voor lange periodes. NPR-28914: Hotfix voor CQ-4254932
* Het bewegen van activa in DAM resulteert niet in een gelijkaardige beweging op Scene7. NPR-28957: Hotfix voor CQ-4264974
* De updates van meta-gegevens worden niet overgegaan tot IPS als het meta-gegevensgebied in AEM wordt bijgewerkt. NPR-28961: Hotfix voor CQ-4255393
* VersioningChronologieEventProvider zou wortelversie samen met de versiecommentaar moeten verstrekken. Hotfix voor GRANITE-26063
* Het injecteren van gegevens leidt tot codeuitvoering bij de serverkant. Hotfix voor CQ-4270246
* Ondersteuning voor beheer op meerdere sites voor bedrijfsmiddelen. Hotfix voor CQ-4271453, CQ-4268621, CQ-4257491
* De interface AEM zou een extra ingang voor de huidige versie van de activa in de chronologiegeschiedenis moeten tonen, tonend de recentste controlecommentaar van de Verbinding van de Activa van Adobe. Hotfix voor CQ-4262864
* De steekproefvideo laadt niet bij het creëren van of het uitgeven van een MixedMediaSet. Hotfix voor CQ-4244889
* Het onbruikbaar maken van de toestemmingen om inhoud op de kant te schrappen AEM verhindert de gebruiker om aan het Portaal van het Merk te publiceren. Hotfix voor CQ-4270426
* Vragenlimieten voor problemen met Asset-rapporten na upgrade naar AEM 6.4.3. NPR-28588: Hotfix voor CQ-4262022, CQ-4260697
* De downloadfunctionaliteit maakt gebruik van AEM Assets via assetdownload serlet, zodat anonieme gebruikers alle bedrijfsmiddelen kunnen downloaden. NPR-27315, Hotfix voor CQ-4254732

**Sites**

* De naam van de JCR- klachtenmarkering zou auto-bevolkt moeten zijn gebaseerd op markeringstitel. NPR-28990: Hotfix voor CQ-4199411
* Annuleer overervingsknoop is niet zichtbaar op sommige gebieden die in de paginaeigenschappen worden toegevoegd. NPR-29079: Hotfix voor CQ-4265686
* De het uitloopvoorproefactie zou niet moeten proberen om het levende exemplaar te ontspannen of het te tonen in de lijst van uitrolpagina&#39;s. NPR-29151: Hotfix voor CQ-4266213
* (De Redacteur van het Malplaatje) regressie van het Beleid van de Stijl op structuurwijze. NPR-28981: Hotfix voor CQ-4264400
* De genestelde levende exemplaren tonen dubbele ingangen tijdens uitlooptraject. NPR-29300: Hotfix voor CQ-4268664
* Het publiceren van een Levend Exemplaar van een Levend Exemplaar dat een component van de Importeur van het Ontwerp bevat ontbreekt met Slaagde er niet in om verwijzingen voor de geselecteerde pagina terug te winnen. NPR-28944: Hotfix voor CQ-4265014
* CoralUI, wanneer gebruikt met Multifield, slaat fileReferenceParameter op het componentenniveau in plaats van op multifield niveau op. NPR-29536: Hotfix voor CQ-4266129
* De ontwerpverwijzing wordt niet herhaald op publiceert na het annuleren van overerving op de Importeur van het Ontwerp. NPR-29648, NPR-29721: Hotfix voor CQ-4269270, CQ-4271087
* Het weggebied in de Rijke Redacteur van de Tekst opent bij de wortelweg ongeacht de weg die aan onderzoek wordt gespecificeerd. NPR-29483: Hotfix voor CQ-4268997
* (IE11) De inhoud van HTML van het deeg van het exemplaar in een component van RTE met defaultPasteMode = plaintext kleeft niet de inhoud als gewone tekst. NPR-29432, NPR-29171: Hotfix voor GRANITE-24941
* De rijke spellcheck van de Redacteur van de Tekst werkt niet meer in andere talen. NPR-29506: Hotfix voor CQ-4264990
* Het scripting van de dwars-plaats (XSS) op de pagina van de Campagne. NPR-29614: Hotfix voor CQ-4269322
* Het minimaliseren van de Rijke Redacteur van de Tekst van fullscreen terwijl in bron uitgeeft wijze leidt tot verlies van inhoud. NPR-29574: Hotfix voor CQ-4260584
* (Klassieke UI) het navigeren aan het laatste lusje is niet altijd mogelijk wanneer een groot aantal markeringen bestaan. NPR-29544: Hotfix voor CQ-4264548
* (Klassieke UI) het navigatiemenu van de Console Admin verdwijnt, en de pagina laadt niet volledig. NPR-29571: Hotfix voor CQ-4264585
* De waakzaamheid van de fout wordt geproduceerd wanneer het toevoegen van componenten aan WCM pagina wanneer de minificatie op de instantie wordt toegelaten. NPR-29396: Hotfix voor CQ-4266196
* Een kwestie met de overerving van de knopen van het Systeem van de Stijl van de ouder. NPR-29296: Hotfix voor CQ-4266041
* De pagina die met Timewarp wordt teruggezet zou naar het correcte beeld op het tijdstip van versioning moeten verwijzen.  NPR-29431: Hotfix voor CQ-4262638
* Lege pagina met fouten Javascript op redacteur na het installeren van recentste 6.4.5 momentopnameversie. NPR-29475: Hotfix voor CQ-4266196
* Terwijl het toevoegen van een component aan een parsys, wordt het bezit van de ontwerpcomponentenlijst niet geëerbiedigd en aan een verschillende naam van de malplaatjeknoop met een gelijkaardige parsys structuur opgelost. NPR-29509: Hotfix voor CQ-4269044
* cq:dropTargets de streek behandelt de gehele component in plaats van de grootte van het beeld, die het richten met ingebedde componenten moeilijk maakt. NPR-29738: Hotfix voor CQ-4268912
* De beeldcomponent roept niet de &quot;achteraf uitgeven&quot;luisteraar nadat de beeld redacteur op zijn plaats wordt gebruikt. NPR-29616 Hotfix voor CQ-4268065
* Een probleem bij het opzetten van het sociale bericht op Facebook. NPR-29212: Hotfix voor CQ-4266630
* Wanneer het bevorderen van lanceringen voor gewijzigde pagina&#39;s, worden de wijzigingen in zowel de bron als lanceringstakken overwogen. NPR-29308: Hotfix voor CQ-4266746
* De teruggegeven duimnagel op het Fragment van de Inhoud toont interne kalendervertegenwoordiging voor het gebied van de Datum en van de Tijd. NPR-29531: Hotfix voor CQ-4269362
* Kan geen markering aan pagina&#39;s met bestaande verschillende markeringen bulken toevoegen. NPR-28729: Hotfix voor CQ-4262922
* Het geplande activeringspictogram wordt niet weergegeven in de site-admin. NPR-28725: Hotfix voor CQ-4263917

**Replicatie**

* De gevoelige kwetsbaarheid van de informatieonthulling in de component van de Agent van de Replicatie. NPR-29612, NPR-24951: Hotfix voor GRANITE-25070
* De gebruiker-verstrekte gegevens zijn niet ontsnapt aan output in de cq/de replicatie/de componenten/de agentencomponent, resulterend in opgeslagen dwars-plaats scripting (XSS) kwetsbaarheid. Hotfix voor CQ-4266263

**Ervaringsfragmenten**

* Kan de Fragmenten van de Ervaring naar doel uitvoeren niet wanneer het slimme beeld wordt gebruikt. Hotfix voor CQ-4269606

**Sociale rapportage**

* De communautaire verslagen van AEM tonen niet in de auteur van AEM. Hotfix voor CQ-4266294

**Platform**

* Het scripting van de dwars-plaats (XSS) in pakketmanager terwijl het installeren van een pakket. NPR-29734, NPR-29713, NPR-29630: Hotfix voor GRANITE-26161, GRANITE-
* Veelvoud opgeslagen en weerspiegelde dwars-plaats scripting (XSS) in CRXDE Lite. NPR-29534: Hotfix voor GRANITE-26049
* De login functionaliteit voor het gebruik van het Aandeel van het Pakket KRIJGT verzoek eerder dan POST verzoek, veroorzakend dat het wachtwoord onder het netwerk tabel zichtbaar is. NPR-29631: Hotfix voor GRANITE-26048

**Felix**

* Het scripting van de dwars-plaats (XSS) dat in systeemconsole wordt waargenomen. De pagina wordt geladen en omhoog komt over wanneer de muis over tekstgebied wordt gehakt. NPR-29853, NPR-29633: Hotfix voor GRANITE-26188, GRANITE-26050

**Graniet**

* De Configuratie van de Registratie van de Registratie van de Sling van Apache registreert niet het geïnjecteerde manuscript filtreert.  NPR-29775: Hotfix voor GRANITE-26051

**Gemeenschappen**

* De groepen die op auteur worden geschrapt zouden uit moeten worden verwijderd publiceren instanties. NPR-28933: Hotfix voor CQ-4264645
* Het toepassingsgeheim zou met een wachtwoordgebied moeten worden beschermd, dat niet in gewone teksten voor sociale verbindings hulpmiddelen moet worden getoond. NPR-29728: Hotfix voor CQ-4270480
* De bezoekers en de leden, zonder moderatorvoorrechten, kunnen niet goedgekeurde/hangende posten zien door URL te kleven. NPR-29726: Hotfix voor CQ-4271124, CQ-4271441
* De hoge reactietijd tot 40-50 seconden wordt waargenomen op gebruikerslogin voor Gemeenschap. NPR-29678: Hotfix voor CQ-4269444

**Vertaling**

* De gebruikers zonder de toegang van de vertaaleigenschap op navigatie zouden niet tot zijn subpagina&#39;s moeten kunnen toegang hebben. NPR-29644: Hotfix voor CQ-4269979
* De toestemmingen van de gebruiker niet die als tovenaar worden gehandhaafd staan de verwezenlijking van het vertaalexemplaar in een read-only plaats toe. NPR-29375: Hotfix voor CQ-4265877

**UI - Foundation**

* Verhoogde de paginatielimiet van het onderzoeksresultaat tot 100 pagina&#39;s voor kaartmening en 200 voor de lijstmening. NPR-29332: Hotfix voor GRANITE-24644
* Wegens luie lading van markeringen, wordt niets getoond op de inzamelingspagina. NPR-29267: Hotfix voor GRANITE-24902
* Het veranderen van de paginatielimiet in 100 in plaats van 40 brengt een extra luie lading zonder pagineringsverzoek teweeg. NPR-29246: Hotfix voor GRANITE-25027
* AEM granite het wachtwoordgebied wordt niet bevolkt na encryptie. NPR-29245: Hotfix voor GRANITE-24908

**Integratie**

* Een uitzonderingsbericht wordt getoond wanneer het proberen om de AEM lanceringsconfiguratie uit te geven en te bewaren. NPR-29086: Hotfix voor CQ-4266153
* BrightEdge-referenties ontbreken bij verbindingsfout.  NPR-29167: Hotfix voor CQ-4265872
* De geërfte van checkbox die op het wortelniveau in de Dienst van de Wolk verschijnt zou moeten worden verwijderd. NPR-27856:  Hotfix voor CQ-4259676

**Sling**

* De de verbindingsonderbreking van HTTP wordt niet gelezen van de configuraties. NPR-29264: Hotfix voor SLING-7902
* De installateurswriteback van JCR veroorzaakt de configuratie OSGi om ongeldig formaat te gebruiken en de herplaatsing te blokkeren. NPR-29027: Hotfix voor CQ-4264694

**Projecten**

* De gebruikers kunnen niet het projectwerkschema voltooien. NPR-29621: Hotfix voor CQ-4258791
* De lijst van het Werkschema van het project toont lege rijen voorbij 40 werkschema&#39;s. NPR-28739: Hotfix voor CQ-4264005
* Het kiezen van de Dynamische optie van de Vertoning in het Portaal van het Merk downloadt een leeg .zip dossier. NPR-29420: Hotfix voor CQ-4268826
* Publiceer Activa van de omslag van de Auteur AEM /content/dam/mac aan het Portaal van het Merk werkt niet. NPR-29820: Hotfix voor CQ-4271118
* De beknotting in de naam veroorzaakt kwesties met publiceren knoop. NPR-29573: Hotfix voor CQ-4269317
* Onbekwaam om het exemplaar van de activataal door verwijzingspaneel te creëren. Hotfix voor CQ-4269535

**Werkstroom**

* De verbetering van 6.4.2 aan 6.4.4 breekt het de kalender gebied van de dialoogdeelnemer. NPR-29727: Hotfix voor CQ-4270423

**WCM - Admin UI**

* Het openen van het toestemmingenlusje in implementatie Coral2 toont niet de knopen. Hotfix voor CQ-4269419

**WCM - MSM**

* Het schrappen van een kindknoop in het levende exemplaar zou liveRelationship moeten losmaken. Hotfix voor CQ-4270395
* De verbetering aan AEM 6.4.3 maakt de Manager van de Multi-Plaats lang om uit te rollen. Hotfix voor CQ-4271410

**Kwetsbaarheid**

* CSRF-beschermingskader werkt niet met AEM-stichtingsvormen. NPR-28612: Hotfix voor GRANITE-22231

**WCM - Pagina-editor**

* Het weerspiegelde dwars-plaats scripting (XSS) wanneer het gebruiken van een ongeldige selecteur. Hotfix voor CQ-4270397

**Formulieren**

De belangrijkste hoogtepunten voor vormen AEM 6.4.5.0 zijn:

**Formulierinvoegpakket**

**Aanpassingsvormen**

* (Aanraking UI) De het werkschemaoptie van het Begin verschijnt niet de dialoogdoos voor configuratie. NPR-29521: Hotfix voor CQ-4269050

**Formulieren - Backend Integration**

* Toegelaten steun voor de Actieve Diensten van de Federatie van de Folder (ADFS) v3.0 voor de Dynamica op-gebouwintegratie van Microsoft. NPR-30003, NPR-29484: Hotfix voor CQ-4270586
* De dienst van de prefill ontbreekt toe te schrijven aan lange doorlooptijd van de module van de Integratie van de Gegevens van Vormen AEM. NPR-28997: Hotfix voor CQ-4265988
* Het verzoek van het Web van de ZEEP is misvormd binnen Vormen AEM. NPR-29013: Hotfix voor CQ-4265443
* Er wordt geen foutbericht weergegeven tijdens het testen van de SOAP-service, in het geval van een onjuiste datumwaarde. Hotfix voor CQ-4265445

**Formulieren - Interactieve communicatie en formulieren - Correspondentiebeheer**

* Creeer de Overeenstemming UI (CCR UI) er niet in slaagt om een vlotteraantal te behandelen.  NPR-29210: Hotfix voor CQ-4254201
* Tooltip die op een variabele wordt geplaatst is niet zichtbaar op Create Correspondentie UI (CCR UI). NPR-29739: Hotfix voor CQ-4250533
* Onbekwaam om van Onderzoek binnen brieven te kopiëren of te kleven. NPR-29808: Hotfix voor CQ-4270783

**HTML5-formulieren**

* Wanneer wij een ruimte binnen de tekst toevoegen, staat het tekstgebied niet toe om aan het eind te vullen. NPR-28844: Hotfix voor CQ-4260239

**Forms JEE-installateur**

**Formulieren - Foundation JEE**

* De component van Webservice in de Werkbank van de Vormen AEM kan de Webdienst aanhalen niet, die bidirectionele SSL authentificatie vereist. NPR-29485: Hotfix voor CQ-4246794
* De de configuratiemanager van JEE van Vormen AEM werkt niet met veelvoudige NIC kaarten. NPR-29236: Hotfix voor CQ-4268598
* AEM-opstartfout afkomstig van GemFire: java.lang.IllegalStateException: Slechts één verbinding AdminDistributedSystem kan allen in één keer worden gemaakt. NPR-29524: Hotfix voor CQ-4266295
* NoClassDefFoundError wegens fout van de jar versie. NPR-28834: Hotfix voor NPR-28834

**Formulieren - Documentservices**

* Het ongeldige Pdf/A- dossier wordt gemeld als geldig PDF/A gebruikend isPDFA verrichting. NPR-29076: Hotfix voor CQ-4261541
* PDF kan niet worden geconverteerd naar PDF/A-1b met het veld Formulier zonder weergavekaart. NPR-29534: Hotfix voor CQ-4269618
* De omzetting van PDF/A van PDF die met de Dienst van de Output wordt geproduceerd gaat geen bevestiging met Acrobaat gelijkstroom over. NPR-29647: Hotfix voor CQ-4270448
* Apache POI-bundel faalt, met een uitzondering. NPR-27861, NPR-28048: Hotfix voor CQ-4245898, CQ-4244778

**Formulieren - Ontwerper**

* De toegevoegde steun PDF/UA aan de vormen van de Architectuur van de Vormen van XML (XFA) die gebruikend de Dienst van de Ontwerper en van de Output worden geproduceerd. NPR-23022

**Formulieren - Werkstroom**

* De verklaringen van werkruimte ontbreken met karakter Umlaut. NPR-29087: Hotfix voor CQ-4263172

**Inclusief functiepakketten**

**Assets**

* Ondersteuning voor beheer op meerdere sites voor bedrijfsmiddelen. Voor meer informatie, zie [Hergebruik activa gebruikend MSM voor Activa](/help/assets/reuse-assets-using-msm.md). NPR-26450: Hotfix voor CQ-4259922

**SGA-bundels en -inhoud**

In de volgende tekst wordt de lijst van OSGI-bundels en -inhoudspakketten in het GVB opgenomen.

Lijst van OSGi-bundels opgenomen in AEM 6.4.5.0

[Bestand ophalen](assets/6.4.5.0_bundles.txt)

Lijst van de Inhoud Pakketten inbegrepen in AEM 6.4.5.0

[Bestand ophalen](assets/6.4.5.0_OSGI.txt)

#### AEM 6.4.4.0 {#experience-manager-6440}

AEM 6.4.4.0 is een belangrijke update die prestaties, stabiliteit, veiligheid en zeer belangrijke klantenmoeilijke situaties en verhogingen omvat die sinds de algemene beschikbaarheid van AEM 6.4 in **april 2018 worden vrijgegeven.**

Het is ook cumulatief, wat betekent dat 6.4.4.0 al AEM 6.4 de dienstpakken versie vóór het omvat.

Enkele zeer belangrijke hoogtepunten van AEM 6.4.4.0 zijn:

* De ingebouwde opslagplaats (Apache Jackrabbit Oak) wordt bijgewerkt naar versie 1.8.11.
* Toegevoegde steun voor caching de dienstversie om de frequente verzoeken van HTTP van de de dienstversie te vermijden.
* Extra ondersteuning voor het verwijderen van automatische tags.
* Geïmplementeerd eindeloos scrollen voor catalogustovenaar.
* De gesteunde capaciteit om toestemmingen volgens communautaire plaatsen te beperken.
* De moeilijke situaties van prestaties (caching, async uitvoering, uitsluitingslijst) voor het Verdelen van de Gezondheidscontrole van de Inhoud van de Graniet.
* Toegevoegde assetpicker knoop aan de dialoog van de paginaduimnagel.
* Toegevoegd nieuw bezit om tooltip het plaatsen op gebieden toe te staan.
* Verbeterde ondersteuning van ColorPicker binnen het Multifield.
* Toegevoegd een controle om lege waarden voor aantalinput multifields in de cliënten van het Fragment van de Inhoud te negeren.
* Ondersteuning voor Microsoft Translator Text API v3 is ingeschakeld.

**Assets**

* Migratie van ACS- en voorraadintegratie naar AEM 6.4.4.0 NPR-27632
* Publiceer recentere lege activaomslag met sub-omslagen maakt de sub-omslagen verdwijnen. NPR-27558: Hotfix voor CQ-4254701
* De toevoeging van Enige niet-namespaced bezit van het Koord \ [\] veroorzaakt onvolledige writeback XMP. NPR-26805: Hotfix voor CQ-4254142
* Na het rasterizing van de input pdf, heeft de geproduceerde output ontbrekende beelden. NPR-27929: Hotfix voor CTG-4150481
* De Tovenaar van de Activa van de beweging toont een onjuiste telling van het Verwijzing van pagina&#39;s voor gepubliceerde pagina&#39;s. NPR-27833: Hotfix voor CQ-4258014
* AssetPicker zoekt slechts de eerste markering om het resultaat te filtreren wanneer het filtreren met markeringen. NPR-27778: Hotfix voor CQ-4257705
* De manager van AEM OOTB PDF wordt geplakt bij het verwerken van PDF met buitenlandse karakters. NPR-28778: Hotfix voor CQ-4254234
* Wanneer een Csv- dossier waarde heeft die door komma in één enkele kolom wordt gescheiden, ontsnapt de redacteur AEM CSV niet de komma en behandelt het als afzonderlijke kolom. NPR-28801: Hotfix voor CQ-4261694
* Kwestie met de Redacteur van het Schema van Meta-gegevens terwijl het gebruiken van wegBrowser om gegevens te selecteren. NPR-28674: Hotfix voor CQ-4263005
* Teveel activa worden verwerkt aan de Slimme Dienst van de Inhoud resulterend in een enorme hoeveelheid tijd om het periodieke etiketteringsproces te voltooien. NPR-28640: Hotfix voor CQ-4262661, CQ-4262644, CQ-4263234
* De acties van de Desktop werken niet voor de resultaten van het Onderzoek van `aem/start.html` pagina. NPR-27242: Hotfix voor CQ-4248176
* De activa API staat niet toe uploadt van dossier > 2 GB veroorzakend uploadt mislukking. NPR-27629: Hotfix voor Graniet-23590
* De meta-gegevens bewaren niet in gedownloade activa in de eerste poging in het geval van de Dynamische Media op de instantie wordt toegelaten. NPR-28233: Hotfix voor CQ-4260759
* De dienst resolver is niet gesloten in configuratie SiteCatalyst. NPR-28015: Hotfix voor CQ-4259397
* Het bewegen van activa in DAM resulteert niet in een gelijkaardige beweging op Scene7 (p2p config). NPR-28313: Hotfix voor CQ-4261091

**Sites**

* (Klassieke UI) Een fractie levende exemplaren verschijnen in uitrollijst. NPR-28598, NPR-28574: Hotfix voor CQ-4263410
* LiveRelationshipManagerImpl werpt uitzonderingen wanneer cq:de meester is leeg of ongeldig. NPR-28590: Hotfix voor CQ-4263115
* De pagina&#39;s worden niet goed verwijderd door het werkschema &quot;Verzoek tot verwijdering&quot;. NPR-28668: Hotfix voor CQ-4263195
* De Status UI van de relatie toont geen juiste jaar of timestamp waarden voor verwante koraal-datepicker gebieden. NPR-28666: Hotfix voor CQ-4263661
* Het scripting van de dwars-plaats (XSS) in SuggestieHandler voor 6.4. NPR-28693: Hotfix voor CQ-4253821
* De omslag van de beweging van sitadmin beëindigt binnen uit geheugen en maakt AEM niet beschikbaar. NPR-28346: Hotfix voor CQ-4261398
* De configuraties van de Uitvoer van MSM LiveCopy worden verloren na update. NPR-28311: Hotfix voor CQ-4258705
* Onbekwaam om voorbij 40 blauwdrukconfiguraties te scrollen. NPR-27640: Hotfix voor CQ-4239166
* Het gebruik van SyntheticResource als verwijzing werpt een Volledige Uitzondering van de Wijzer en blokkeert de beweging van de pagina&#39;s.  NPR-27576: Hotfix voor CQ-4258262
* PushOnModify werkt niet aan schrapping op 6.1 tot 6.4 promotieinstantie. NPR-28108: Hotfix voor CQ-4259833
* (Klassieke UI) annuleert overervingsknoop mist en de component is editable op een levende exemplaarpagina. NPR-28256: Hotfix voor CQ-4260161
* OakState0001: Onopgeloste conflicten bij het Uitrollen. NPR-27982: Hotfix voor CQ-4259548
* Wanneer het exemplaar/het kleven van een structuur die verwijzingen SyntheticResource bevat, beëindigt het proces met een fout 500. NPR-27709: Hotfix voor CQ-4259179
* De werkstromen kunnen niet worden beëindigd wanneer de nuttige lading wordt geactiveerd. NPR-27672: Hotfix voor CQ-4258520
* De implementatie toont dubbele uitloopwegen na verbetering van 6.1 aan 6.4. NPR-27845: Hotfix voor CQ-4259487
* Integreer damassetpicker modal in de component van de paginaduimnagel. NPR-28131: Hotfix voor CQ-108042
* (Klassieke UI) Kan Dialogen met tags widget niet openen. NPR-28575: Hotfix voor CQ-4262680
* Multifield dossier uploadt toont dalingsstreek niet. NPR-28676: Hotfix voor CQ-4263516
* &#39;Ongeldige waarde voor terugkeringskiezer&#39;-fout tijdens het migreren van een onderdeel van AEM 6.0 naar AEM 6.2. NPR-28609: Hotfix voor CQ-4241258
* De rijke Redacteur van de Tekst in dialoog flikkert wanneer popover van een plugin hoger is dan tekstgebied, vandaar, blokkerend om het even welke verdere creatie. NPR-27579: Hotfix voor CQ-4257440
* (Klassieke UI) cq:actiedacannotaat werkt niet. NPR-28232: Hotfix voor CQ-4257703
* Het verwijderen van markeringen uit het paneel van het de activaonderzoek van de markeringsfilter van de paginaredacteur verfrist niet behoorlijk de lijst. NPR-27983: Hotfix voor CQ-4245567
* Als de waarden voor meerdere velden leeg zijn, zal het klikken sparen in oneindige ladingsherinnering resulteren zonder eigenlijk ooit te voltooien.  NPR-28400, NPR-28393: Hotfix voor CQ-4244058, CQ-4244349
* Met enkel gelezen toestemming, kunnen de gebruikers/de groepen geen XF selecteren en geen optie hebben om XF en zijn paginaeigenschappen te bekijken. NPR-28341: Hotfix voor CQ-4260412
* De gegevens JSON die van Doel worden ontvangen hebben een aantal vluchtkarakters die de toepassingspagina veroorzaken om te breken. NPR-28318: Hotfix voor CQ-4252043
* Kan geen onderdeel bewerken nadat AEM 6.4.3 is geïnstalleerd. NPR-28125: Hotfix voor CQ-4261216
* De schrapping van alle markeringen voor een markeringsgebied wordt niet voortgeduurd voor een gestructureerd inhoudsfragment. NPR-28133: Hotfix voor CQ-4247241
* Wanneer het uitgeven van een Tevreden Fragment &quot;jcr:last gewijzigd door&quot;en &quot;jcr:last modified&quot;bezit, worden de waarden bijgewerkt zonder gebruiker die om het even welke veranderingen aanbrengt. NPR-27847: Hotfix voor CQ-4257138
* De Fragmenten van de inhoud die diff verbeteringen voor AEM 6.4 versioning vergelijken. NPR-27764
* Als er geen cq is:allowTemplates die op /content/experience-fragments wordt bepaald en allowPaths wordt gebruikt op het malplaatje van het Kader van de Ervaring, wordt een fout geworpen wanneer het Kader van de Ervaring wordt bewogen/gekopieerd. NPR-27487: Hotfix voor CQ-4257489
* De knop Maken verschijnt op vernieuwen voor de nieuwe gebruiker. NPR-27335: Hotfix voor CQ-4255360
* Terwijl het proberen om een gepubliceerde pagina te bewegen, is de telling van de Pagina&#39;s van het Verwijzing die op de eerste pagina van de tovenaar van de &quot;Pagina van de Beweging&quot;verschijnt onjuist. NPR-28111: Hotfix voor CQ-4259663
* (Aanrails voor aanraakinterface) Referenties geven geen inkomende links weer. NPR-28529: Hotfix voor CQ-4262306
* Kan geen component- en paginaeigenschappen bewerken nadat u AEM 6.4.3 hebt geïnstalleerd. NPR-27998: Hotfix voor CQ-4261216, CQ-4260441
* Migreer contexthub aan jquery 3. NPR-28397: Hotfix voor GRANITE-19902

**Handel**

* Kan catalogus niet selecteren als er meer dan 20 catalogi in een map zijn. NPR-27649: Hotfix voor CQ-4258119
* De tovenaars van de handel &amp; de eigenschappen meningen worden gebroken toe te schrijven aan header.referer het missen. Hotfix voor CQ-4261122

**Campagne - gericht werken**

* com.day.cq.personalization.impl.TeaserResourceEventHandler gaat in een oneindige lijn en veroorzaakt updates aan knopen op openbare instanties. Hotfix voor CQ-4263096

**Replicatie**

* Fout terwijl de bouw van replicatieinhoud com.day.cq.replication.AccessDeniedException. NPR-28314: Hotfix voor CQ-4261401
* Het lek van de zitting wanneer identiteitskaart van de Agent van de Gebruiker aan admin in replicatieagent wordt geplaatst. NPR-28220: Hotfix voor CQ-4255517

**DAM - Creative Cloud**

* De steunHTTP API om gelijkaardige beelden van binnen Activa te vinden AEM. Hotfix voor CQ-4254091
* Verbeter ACS API om de resultaten van een vraag toe te staan om tot de leden van een inzameling worden beperkt. Hotfix voor CQ-4258708

**DAM - Formaten**

* Nadat de meta-gegevensuitvoer wordt teweeggebracht, wordt de pagina opnieuw gericht aan een pagina 404. Hotfix voor CQ-4262447

**DAM - Algemeen**

* (Adobe Stock Integration) de foutenmodaal van de Server wordt getoond met een Oauth fout in het error.log- dossier. Hotfix voor CQ-4260406
* De integratie van de Voorraad van Adobe functioneert niet als 6.4.4 op 6.4.3 wordt toegepast. Hotfix voor CQ-4266009
* De verbinding aan het Model van het CF mist zelfs na het toepassen van SP3 flard. Hotfix voor CQ-4259029

**Platform**

* (Klassieke UI) uitgeven knoop is niet beschikbaar in de component van het Rapport van de Basis na bevordering aan 6.4.2. NPR-28560: Hotfix voor CQ-4262825
* Wanneer het gebruiken van een vraag die property.operation=like en property.depth combineert, beëindigt het omhoog in een OngeldigeQueryException. NPR-28570: Hotfix voor CQ-4262652
* Interne fout van de Server wanneer de onlangs toegevoegde taalknoop wordt verwijderd uit overbelaste taalknoop. NPR-28661: Hotfix voor CQ-4239194
* De Uitzondering van de Wijzer in stderr.log in sling-oak-1 draad op willekeurige begin. NPR-28665: Hotfix voor CQ-4237845

**Felix**

* webconsole.plugins.memoryusage veroorzaakt een impasse op verfrissing. NPR-27895:  Hotfix voor GRANITE-20715

**Graniet**

* Het verkopen van de Gezondheidscontrole van de Toegang van de Inhoud voert lange bovenmatige /libs bevestiging voor het onderzoekspad van de mantogembron resolver uit. NPR-28113: Hotfix voor GRANITE-23529

**Beheer van contentfragmentatie**

* De verbeteringen van de bruikbaarheid en eigenschappariteit met Activa voor de Fragmenten van de Inhoud. Hotfix voor CQ-4253883

**Gemeenschappen**

* Bevorder kwetsbare laarzentrekker aan 3.4 en ckredacteursbibliotheken aan 4.5.11. NPR-28490: Hotfix voor CQ-4257511
* De annulering van de het uitgeven wijzen herstelt niet de geschrapte gehechtheid. NPR-27902: Hotfix voor CQ-4255150
* De samenstelling namens doos zou slechts aan de bevoorrechte leden zichtbaar moeten zijn. NPR-27900: Hotfix voor CQ-4251235
* Voeg toe rep:geheim voorgeheugen in Onwettige Knooppunten bij de Luisteraar van de Synchronisatie van de Gebruiker van AEM Gemeenschappen op publiceer instanties. NPR-27842: Hotfix voor CQ-4247234
* Het onderzoeksvakje toont vluchtkarakter op niveau UI. NPR-27838: Hotfix voor CQ-4259757
* Fout bij zoeken naar speciale tekens zoals ( , +,? in snel zoeken. NPR-28213: Hotfix voor CQ-4260969
* Creeer een groep van &quot;gemeenschap-specifieke beheerders&quot;voor de gebruikers om de relevante communautaire plaats uit te geven en te schrijven. NPR-27731
* Toegevoegde logica voor toetsenbordgebeurtenis om video te openen. NPR-27726: Hotfix voor CQ-4254026
* Toegelaten toetsenbordnavigatie voor de componenten van Enablement van AEM van Gemeenschappen op Publish. NPR-27728: Hotfix voor CQ-4254028
* Toegevoegd aria-etiket voor lijst en de knoop van de kaartmening. NPR-27727: Hotfix voor CQ-4254027
* Behandeling van open resource resolver zittingen in Sociale Gemeenschappen. NPR-27721: Hotfix voor CQ-4258714

**Vertaling**

* Ondersteuning bieden voor Microsoft Translator Text API v3. NPR-28366: Hotfix voor CQ-4249755
* jcr:taal &amp; cq:taal wordt niet automatisch bijgewerkt in de vertaalde taal. NPR-28338: Hotfix voor CQ-4256046
* De cyclische verwijzingen veroorzaken StackOverflowError wanneer het creëren van taalexemplaar. NPR-27596: Hotfix voor CQ-4255621
* In een vertaalproject in meerdere talen leidt het klikken sparen en dicht resultaten in verdere pagina&#39;s die aan het project worden toegevoegd tot het creëren van nieuwe projecten in plaats van nieuwe vertaalbanen die in bestaand project worden gecreeerd. NPR-28219, NPR-28236: Hotfix voor CQ-4261276, CQ-4260731
* Het Koord van de fout te lang wanneer het toevoegen van inhoudsfragment met bulkgegevens toe te schrijven aan beperking op het aantal toegestane karakters. NPR-28722: Hotfix voor CQ-4262362

**sociaal**

* Commentaar op de volgende pagina wordt gemarkeerd met geel telkens als een nieuwe opmerking wordt geplaatst. Hotfix voor CQ-4261359
* Onbekwaam om commentaren in de Gebruiker te schrappen produceerde Inhoud gebruikend API. NPR-28075: Hotfix voor CQ-4261135
* AbstractNotificationOperationService veroorzaakt ClassCastException. Hotfix voor CQ-4260456
* Verwijder verwijzing naar de Aandeelbare Wolk van de Verwijzing van Objecten van de Inhoud (SCORM) in de speler. Hotfix voor CQ-4260779

**UI - Foundation**

* De &quot;de outputgeheim voorgeheugeneigenschap van het Filesystem&quot;die in de Manager van de Bibliotheek van de Cliënt van HTML wordt geïntegreerd breekt de &quot;debugClientLibs&quot;eigenschap voor gecompileerde manuscripten zoals MINDER dossiers. NPR-27249: Hotfix voor graniet-23313
* Het aantal getoonde activa wanneer zuivert wijze wordt geactiveerd is altijd 1 en veel JS fouten worden geworpen in de console van browser.  NPR-27575: Hotfix voor GRANITE-23750
* Opslaan en sluiten op pagina-eigenschappen keert niet terug naar de juiste pagina in AEM WAR met Tomcat. NPR-27566: Hotfix voor GRANITE-23671

**Integratie**

* `com.day.cq.personalization.impl.TeaserResourceEventHandler` gaat in een oneindige lijn en veroorzaakt updates aan knopen op publiceren instanties. NPR-28561: Hotfix voor CQ-4263096
* Het hoofdkwartier: acties worden niet in aanmerking genomen voor een specifiek onderdeel. NPR-27616: Hotfix voor CQ-4257497
* De overervingsannulering van LiveCopy werkt niet behoorlijk aan gerichte containers. NPR-28129: Hotfix voor CQ-4259813
* (De Dienst van de Wolk vormt) &quot;geërft van&quot;checkbox die op het wortelniveau verschijnt zou moeten worden verwijderd. NPR-27856:  Hotfix voor CQ-4259676

**Sling**

* Update aan de Modellen van het Sling API 1.3.8, Impl 1.4.10. NPR-27636: Hotfix voor GRANITE-23537

**OAK - Persistentie segment**

* SegmentBufferWriter niet gespoeld na OnRC. NPR-27464

**Projecten**

* Het meertalige vertaalproject leidt niet tot veelvoudige taalbanen voor de gebruikers die geen deel van de beheerdersgroep uitmaken. NPR-28508: Hotfix voor CQ-4262023
* ProjectTaskListServlet lekt een ResourceResolver wanneer getTaskRenderers tijdens opstarten van de dienst wordt geroepen. NPR-27590: Hotfix voor CQ-4258011
* Als een folder meer subdirectories dan de paginagrootte heeft en het opdracht geven tot is door datum of grootte, dan verhindert een fout zich voorbij de eerste pagina te bewegen. NPR-28867: Hotfix voor CQ-4265039
* De steun van de dwars-plaats scripting (XSS) moeilijke situaties in de Kijkers van DAM. NPR-28106:  Hotfix voor CQ-4253215
* Onbekwaam om pagina&#39;s aan vertaalproject door project-beheerders toe te voegen aangezien de verbinding om nieuwe pagina&#39;s aan het vertaalproject toe te voegen niet zichtbaar is. Hotfix voor CQ-4266334

**Werkstroom**

* Wanneer wij de volledige dialoog van het het werkpunt in het werkschemabericht openen dat een gebied van de Markering heeft, voegt het klikken op kruis een bezit van de Markering aan het toe. NPR-28304: Hotfix voor CQ-4261321
* De Knoop van de Knevel van de Selectie van de gebruiker in de Dialoog van de Taak opnieuw toewijzen werkt niet. NPR-28963: Hotfix voor CQ-4264206

**Formulieren**

De belangrijkste hoogtepunten voor vormen AEM 6.4.4.0 zijn:

* Toegevoegde steun om documentveiligheid APIs te registreren voor het ondertekenen van en het certificeren als transacties.

**Formulierinvoegpakket**

**Integratie van Adobe-teken**

* AEM 6.4 de Cliënt SDK van Vormen bevat adobesign-recepent pakket niet. NPR-27735: Hotfix voor CQ-4259372

**Aanpassingsvormen**

* Wanneer Wan adaptive vorm met een leeg malplaatje wordt gecreeerd, kunnen de klanten niet panelen aan het wortelpaneel van de vorm kind maken. NPR-28758: Hotfix voor CQ-4264157
* Wanneer de waarde van het jaargebied van datumcomponent 9999 is, ontbreekt het bevestigingsmanuscript. NPR-28580: Hotfix voor CQ-4262620
* Wanneer een adaptieve vorm met een leeg malplaatje wordt gecreeerd, kunnen de klanten niet panelen aan het wortelpaneel van de vorm kind maken. NPR-28758: Hotfix voor CQ-4264157
* Onbekwaam om waarde tussen de gebieden van luie geladen fragmenten van een adaptieve vorm te plaatsen. NPR-27758: Hotfix voor CQ-4259703
* De adaptieve vorm gebruikt geen Rijke tekstredacteur maar laadt zijn bibliotheken.  NPR-27759:  Hotfix voor CQ-4259193
* Omleiden naar URL werkt niet voor adaptieve vormen ingebed in een pagina van Plaatsen AEM. NPR-27620: Hotfix voor CQ-4239287
* Onbekwaam om waarde tussen de gebieden van luie geladen fragmenten van een adaptieve vorm te plaatsen. NPR-28320: Hotfix voor CQ-4262345
* De adaptieve vorm gebruikt geen Rijke tekstredacteur maar laadt zijn bibliotheken.  NPR-28001: Hotfix voor CQ-4259703, CQ-4259193
* De Handtekening van de kribble werkt niet voor de App die van Vormen AEM op Apple iOS 12.1 loopt. NPR-28497: Hotfix voor CQ-4261765
* Leg Actie voor gebruikend de Klassieke auteurskwesties van het Werkschema van Vormen&quot;in 6.4. Hotfix voor CQ-4252740
* Fout bij het verwerken van blok en tmp-opslag. NPR-28806: Hotfix voor CQ-4264441

**Formulieren - Correspondentiebeheer**

* De agent UI slaagt er niet in om originele grootte van het beeld te behouden. NPR-28800: Hotfix voor CQ-4259767
* CCR/Agent UI: De etiketten van de gebieden van de Datum verschoven in Gegevens tabel. Hotfix voor CQ-4255499

**Formulieren - Transactierapportering**

* Toegevoegde steun om te tellen gebruikend digitale handtekeningen of het verklaren van een document als factureerbare transacties. NPR-28495: Hotfix voor CQ-4260236
* Toegevoegde Digitale handtekening en Certificeer aan Billable API. Hotfix voor CQ-4260236

**Formulierbeheer**

Toegevoegde steun om gebruik van de bibliotheek van de handlebalkcliënt met onderstreepteken in de tovenaar van het het beginoverzicht van de Manager van Vormen te vervangen en activatovenaar te bewegen. NPR-27643: Hotfix voor CQ-4246536.
Één bundel blijft in geïnstalleerde staat na het installeren van het pakket van het Beheer van Vormen op versie/640 tak. Hotfix voor CQ-4265410Forms die met gehechtheid in hen worden voorgelegd verschijnen niet in werkschema met voorlegging van actie &quot;haalt het Werkschema van Vormen AEM&quot;in &amp; laat portaal toe voorleggen gecontroleerd. Hotfix voor CQ-4263110

**Formulieren - Backend Integration**

* Kan het testen van pre/post preprocessor en douane verzenden niet doen met Client SDK, Hotfix voor CQ-4238469

**Forms JEE-installateur**

**Formulieren - Documentbeveiliging**

* Bij het gebruiken van de updatebeleidsdienst, kan de objecten geen fout overschrijven voorkomt. NPR-28751: Hotfix voor CQ-4252287
* De handtekening bouwt het ontbreken met oudere versie van kommons-pkg. Hotfix voor CQ-4265535

**Formulieren - Foundation JEE**

* Wanneer de Vormen van AEM op IBM WebSphere wordt geïmpliceerd, ontbreekt het creëren van een Model van de Gegevens van de Vorm dat op ZEEP wordt gebaseerd. NPR-27923: Hotfix voor CQ-4251134
* Het SRT hulpmiddel van de Generator PDF slaagt er niet in om geïnstalleerde versie van de Acrobaat van Adobe te ontdekken. NPR-27971

**Formulieren - Ontwerper**

* Sommige beelden JPEG in een malplaatje XDP geven niet behoorlijk terug.  NPR-26702: Hotfix voor LC-3917457

**Formulieren - OBSOLETE**

* Het document vangt de dienstcrasht terwijl het verwerken van TIF- dossiers. NPR-28079:  Hotfix voor CQ-4240649

**Formulieren - Werkstroom**

* De Vormen van HTML5 met gebrek voorleggen proces in an.lca niet aan JBoss 7 voor. NPR-28675: Hotfix voor CQ-4243928
* Onbekwaam om Vormen PDF in de Werkruimte van HTML voor te leggen. NPR-28058: Hotfix voor CQ-4260373
* De gegevens van de klant worden gedrukt in info logboeken gebruikend het Invoke Werkschema van de Vormen van de Dienst FDM van de Dienst. Hotfix voor CQ-4260385

**Inclusief functiepakketten**

**Sites**

* De Fragmenten van de inhoud die verschil verbeteringen voor AEM 6.4 versioning vergelijken.  NPR-26760: FP voor CQ-4248839
* De de verschillen van de de Fragmenten van de inhoud verschillen verbeteringen voor AEM 6.4.  NPR-27866: FP voor CQ-4248839
* Toegelaten eigenschap in de configuratieAEM- **Werkschema die van de Configuratie van SmGI de Vlag** van de Eigenschap terugtrekt. De terugtrekkende actie zou de werkschemainstantie na het plaatsen van de vlag moeten eindigen. NPR-26451: Hotfix voor CQ-4259090

**Platform**

* De verbeterde hefboomwerkingsOak API van de Opleiding van het Facet van de Bouwer van de Vraag voor 6.4. NPR-26674: FP voor CQ-4230337

**SGA-bundels en -inhoud**

In de volgende tekst wordt de lijst van OSGI-bundels en -inhoudspakketten in het GVB opgenomen.

Lijst van OSGi-bundels opgenomen in AEM 6.4.4.0

[Bestand ophalen](assets/bundles_6_4_4_0.txt)

Lijst van de Inhoud Pakketten inbegrepen in AEM 6.4.4.0

[Bestand ophalen](assets/osgi_package_6_440.txt)

#### AEM 6.4.3.0 {#experience-manager-6430}

AEM 6.4.3.0 is een belangrijke update die prestaties, stabiliteit, veiligheid en zeer belangrijke klantenmoeilijke situaties en verhogingen omvat die sinds de algemene beschikbaarheid van AEM 6.4 in april 2018 worden vrijgegeven.

Het is ook cumulatief, wat betekent dat 6.4.3.0 al AEM 6.4 de dienstpakken versie vóór het omvat.

Enkele zeer belangrijke hoogtepunten van AEM 6.4.3.0 zijn:

* De ingebouwde opslagplaats (Apache Jackrabbit Oak) wordt bijgewerkt naar versie 1.8.9.
* Toegevoegde steun voor allowPaths bezit op Aanpassingsvormenmalplaatjes.
* Verbeterde, op het scherm gebaseerde zoekopdracht naar bedrijfsmiddelen in AEM
* Het scripting van de dwars-plaats (XSS) moeilijke situaties in de Login pagina.
* Verbeterde instrumentatie UI.
* Verbeteringen in de verwerking FormData.
* Verbeterde verwerking van punt noemend binnen een Multifield.
* Verbeterde behandeling van placeholder punten (de Mening van de Kaart en de Mening van de Lijst) tijdens selectie.
* Toegevoegde de Authentificatie van Adobe IMS en de Steun van de Console van Admin voor de Beheerde Diensten.

**Assets**

* Het werkschema van de Activa van de Update DAM haalt geen verwijzingen uit dossiers INDD als IDS de Ontkoppelde optie wordt toegelaten. NPR-26243; Hotfix voor CQ-4250933
* Het succesbericht wordt niet getoond wanneer de activa met de Redacteur van het Bulk van Activa worden gepubliceerd. NPR-26252; Hotfix voor CQ-4251688.
* Na het bekijken van activa van een onderzoeksresultaat, als u de Achterknoop in browser klikt, leidt het tot een foutenmelding van het &quot;Slechte Verzoek&quot;met 400 foutencode. NPR 26578; Hotfix voor CQ-4253741
* De activameta-gegevens toont ongeldige namespace fout na het installeren van een de dienstpak. NPR-22341; Quickfix voor CQ-4237202
* De optie om omslagen en inhoudsfragmenten in lijstmening opnieuw in orde te brengen wordt niet getoond voor de toepasselijke omslagen. NPR-27153; Hotfix voor CQ-4255873
* De gebruikers kunnen geen activa aan een nieuwe inzameling toevoegen, aangezien het in een foutenmelding met een gebroken beeld in de fout popup dialoog resulteert. NPR-22431; Hotfix voor CQ-4237086
* Cascading dropdown wordt niet gesteund op dynamische dropdown lijsten. NPR-27043; Hotfix voor CQ-4252564
* Als de gebruikers een niet-standaardwaarde voor de &quot;Omslag van de Wortel van het Bedrijf&quot;in DMS7 wolk config plaatsen, werkt de Vooraf ingestelde Kijker niet zoals verwacht. NPR-26360; Hotfix voor CQ-4249505
* De rapportage van activa faalt voor gevallen met een zeer groot aantal activa. NPR-27278; Hotfix voor CQ-4256748
* Subfolders erven niet het het beeldprofiel van SmartCrop van de ouderomslag. NPR-27197; Hotfix voor CQ-4256273
* Wanneer de Dynamische integratie van Media wordt toegelaten, worden sommige meta-gegevenseigenschappen van Activa gewijzigd. De breedte, de hoogte, en de plaatsattributen worden niet getoond. NPR-27203; Hotfix voor CQ-4256258
* De dynamische Media gebruiken niet de gevormde volmacht voor sommige types van activa. NPR-25211; Hotfix voor CQ-4244871
* De pagina van de Redacteur van meta-gegevens bevat de Volledige Uitzondering van de Wijzer voor ongeldige puntparameter. NPR-26169; Hotfix voor CQ-4241368.
* Als een drop-down een keuzeregel en een vereiste regel heeft die op het wordt toegepast, kan de vereiste regel niet in de meta-gegevensredacteur worden tevredengesteld. NPR-27479; Hotfix van CQ-4251428

**Sites**

* Een gebruiker kan de rijke eigenschappen van de tekstredacteur op de in-lijn volledige het schermwijze controleren gebruikend inhoudsbeleid, maar kan niet de Edit rijke eigenschappen van de tekstredacteur van de Dialoog met inhoudsbeleid controleren. NPR-26750: Hotfix voor CQ-4241130
* De rijke tekstredacteur wordt onbruikbaar wanneer geschakeld van het volledige scherm aan het drijven dialoog. De drijvende mening bevat twee rijke tekstredacteurs. NPR-25589: Hotfix voor CQ-4206008
* Wanneer de terugkeersleutel (ga sleutel in) op een tekstgebied wordt geduwd op, schakelt de rijke tekstredacteur op het volledig-schermwijze. NPR-26204: Hotfix voor CQ-4245893
* De stop van de lijst van rijke tekstredacteur is gehandicapt automatisch en staat geen wijzigingen toe. NPR-26507: Hotfix voor CQ-4239387
* Wanneer een speciaal karakter aan het rijke venster van de tekstredacteur wordt toegevoegd, scrolt het venster aan de bovenkant. NPR-26435: Hotfix voor CQ-4249869
* Client Context segment.js caching vs. niet-caching vragen. NPR-26622: Hotfix voor CQ-4253486
* Wanneer een kindregel van de auteursinstantie aan wordt geactiveerd publiceert instantie, publiceert instantie ophoudt werkend. NPR-26601: Hotfix voor CQ-4253588
* Wanneer de rijke tekstredacteur met veelvoudige gebieden wordt gecombineerd, UncaughtTypeError: fieldAPI.getName is geen functie bij foundation.js de fout komt voor. NPR-27146: Hotfix voor CQ-4253155
* De integratie van de Salesforce kan niet de volmachtsconfiguratie gebruiken. NPR-27244: Hotfix voor CQ-4245300
* Wanneer u een pagina voor activering plant die de Manage optie van de Publicatie voor een recentere datum gebruikt en op de lijstmening overschakelt, mist het kalenderpictogram. NPR-26974: Hotfix voor CQ-4239206
* De gebruikers kunnen niet de gesloten toestemmingen van de gebruikersgroep in de paginaeigenschappen uitgeven. NPR-27138: Hotfix voor CQ-4256089Kan tags niet bewerken via tagging. NPR-26957: Hotfix voor CQ-4254858
* Wanneer een markering van een gestructureerd model van het inhoudsfragment van verwijzingen wordt voorzien wordt bewogen, worden de bestaande verwijzingen naar de markering binnen een inhoudsfragment niet bijgewerkt. Dit gebeurt in uitgeven het scherm van het model van het inhoudsfragment. NPR-26776: Hotfix voor CQ-4251805
* Wanneer u een lancering met verscheidene pagina&#39;s creeert en bevordert, wordt de veelvoudige versie voor elke pagina gecreeerd. NPR-26917: Hotfix voor CQ-4254663
* AEM-sitadmin behandelt geen paden die in de browser-adresbalk zijn getypt. NPR-26780: Hotfix voor CQ-4254097
* Wanneer een pagina naar een nieuwe plaats wordt bewogen zonder het anders te noemen, wordt de versiegeschiedenis van de pagina verloren. NPR-26706: Hotfix voor CQ-4254025
* URLs in de redacteur van het ervaringsfragment admin staat geen bekledingen toe. NPR-26319: Hotfix voor CQ-4252156
* Wanneer een pagina met een malplaatje wordt gecreeerd dat lege ervaringsfragment bevat en gepubliceerd, ontbreekt de pagina om te openen en een fout DefaultSlingScript komt voor. NPR-26305: Hotfix voor CQ-4252460
* Wanneer het gegeven-slim-gebruik met klassen met identieke naam wordt gebruikt, wordt de niet-nalevbare code geproduceerd. NPR-27282: Hotfix voor Sling-7581
* Na de installatie van verbeteringsSP, hebben de plaatsen de lege configuratie van de blauwdruk van de uitlooptraject. NPR-27609: Hotfix voor CQ-4257078

**DAM - Merk Portal**

* De predikaten van de markering worden niet gepubliceerd wanneer de vorm van het meta-gegevensschema aan het Portaal van het Merk wordt gepubliceerd. Hotfix voor CQ-4256218
* Wanneer een derdeniveauomslag van AEM aan het Portaal van het Merk wordt gepubliceerd, zonder de ouderomslagen te publiceren, verandert de omslagnaam. Hotfix voor CQ-4255423
* Het wegbrowser predikaat wordt gepubliceerd van de Activa van AEM aan het Portaal van het Merk zoals verwacht. Nochtans, blijft de gepubliceerde weg bij BP /content/dam, die moet worden bijgewerkt. Hotfix voor CQ-4256240

**DAM - Creative Cloud**

* Het pictogram van de &quot;Activa van Adobe van het Onderzoek&quot;mist van de belangrijkste navigatie AEM. Hotfix voor CQ-4254343

**DAM - DM-client**

* Nadat u video&#39;s hebt ingevoerd in een map die is gekoppeld aan het AVS Video Processing Profile, wordt het browservenster steeds opnieuw vernieuwd. Hotfix voor CQ-4253563
* YouTube-publicatievorm mislukt wanneer u een ad-hoctag gebruikt met hoofdletters. Hotfix voor CQ-4252477
* Wanneer een annotatie in activa zoals PDF wordt gecreeerd, begint UI een oneindige pagina verfrist lijn. NPR-27052: Hotfix voor CQ-4255396

**DAM - DM Services**

* De dynamische Media gebruiken niet de gevormde volmacht voor sommige types van activa. NPR-10727; Hotfix voor CQ-4244871

**Platform**

* Prestatieproblemen met org.apache.sling.i18n. NPR-26812: Hotfix voor SLING-7543
* Onbekwaam om de knoopeigenschappen te zien wanneer inputXML wordt geformatteerd en opgesteld. NPR-26198: Hotfix voor CQ-4250448
* IndexOutOfBoundsException in ResourceProviderTracker. NPR-26968: Hotfix voor GRANITE-23310
* De console JMX accumuleert talrijke admin zittingen en een nieuwe zitting wordt geopend om de 5 minuten. NPR-26958: Hotfix voor CQ-4251090
* Na bevordering van 6.2 aan 6.4, toont het logboekdossier stapelspoor voor unclosed middelresolver com.adobe.granite.repository.hc.impl.content.sling.SlingContentHealthCheck. NPR-26176: Hotfix voor graniet-21734
* Wanneer een uit-van-de-doos de spoelagent van de verzender wordt gevormd om aliassen bij te werken, ontbreekt de verrichting met een StackOverflowError. NPR-26373: Hotfix voor CQ-4242928
* Het gebruik van de replicatie verliep het teken OAuth tot het ontbreekt. NPR-25894
* Beperkte pagina (Gesloten pagina van de Groep van de Gebruiker) met het slingeren: alias richt de gebruiker niet aan de login pagina opnieuw. NPR-25715: Hotfix voor Graniet=22263
* Bij het publiceren van markeringen, wordt geen activiteit getoond op UI. Hotfix voor CQ-4255961
* Kan geen tags bewerken in klassieke UI. Hotfix voor CQ-4258697
* Bijgewerkt org.apache.felix.http.bridge aan versie 4.0.4. NPR-27038: Steun voor graniet - 23334
* De activiteitenlogboeken van de manager van het pakket zouden in een afzonderlijk logboekdossier moeten worden gehaald. NPR-27323: Hotfix voor Graniet-14866
* De validator van het pakket meldt geen bekledingen in GFP. NPR-27119: Hotfix voor GRANITE-22825

**Projecten**

* ACS API misbehandelt het pagineren met slechts subdirectory kinderen. NPR-27617: Hotfix voor CQ-4258639

**OAK**

* Kan zich niet aanmelden bij de repository nadat AEM 6.4 Service Pack 2 is geïnstalleerd. NPR-27171: Hotfix voor Graniet-23317

**Replicatie**

* Het Logboek van de controle blijft open met actieve zittingen die constant blijven stijgen met ~750 elke dag. NPR-27062: Hotfix voor CQ-4241350

**Gemeenschappen**

* De posten en de antwoorden van het forum worden toegevoegd bovenop de tweede pagina en wanneer verfrist, beweegt de post zich aan de correcte plaats bovenop de eerste pagina. NPR-27342: Hotfix voor CQ-4247338
* De verbindingen met alle middelen laten vallen de contextweg (/aempublish) na het scrollen. NPR-26982: Hotfix voor CQ-4254345
* De toegevoegde groepen zijn niet zichtbaar in de Managers van de Gemeenschap, Communautaire Moderators en de Bevoorrechte drop-down van het Lid bij het uitgeven van een gepubliceerde plaats. NPR-27190: Hotfix voor CQ-4258574
* Slechts 10 groepen zijn vermeld in enablement middelen pagina zelfs als de paginering voor groeplijst wordt toegelaten. NPR-26934: Hotfix voor CQ-4252985
* De optie om onderzoek naar Geplande Post in dagboekcomponent toe te laten/onbruikbaar te maken wordt verstrekt in ConfigMgr, en de baan SearchScheduledPosts wordt geoptimaliseerd. NPR-26923: Hotfix voor CQ-4250463
* Het onderzoek door sleutelwoorden in adres werkt niet in kalendercomponentenpagina wanneer de gemeenschap AEM aan het werk met DSRP wordt geplaatst. NPR-26737: Hotfix voor CQ-4258493
* Geïmplementeerde directe verbinding aan de commentaar in plaats van de belangrijkste post in het detail van een commentaar, voor matiging UI &amp; enablement middelen. NPR-26704: Hotfix voor CQ-4251381
* De inhoud die door multi-selectie op moderatieconsole wordt gemodereerd verschijnt niet op de Stroom van de Activiteit. NPR-26695: Hotfix voor CQ-4253244
* Het onderzoek met Voornaam en Familienaam op aan gebied van het Overseinen van Gemeenschappen keert niet het verwachte resultaat terug. NPR-26385: Hotfix voor CQ-4248673
* Fout waargenomen wanneer het uploaden van een gehechtheid buiten beeld (bijvoorbeeld .pdf) in Forum. NPR-27360: Hotfix voor CQ-4257753
* Unpin of unfeature werkt een forumpost niet als Auteur-Publish met MySQL DSRP wordt geplaatst. NPR-26125; Hotfix voor CQ-4251520
* De componenten van de inzameling (forums, blogs, kalender, ideatie, QnA) hebben nu een bezit in de componentendialoog om &quot;het Blok UGC op Auteur toe te laten/onbruikbaar te maken geeft Wijze&quot;uit, om lading UGC op WCM toe te staan/te ontkennen geef wijze uit. NPR-26978: Hotfix voor CQ-4248161
* Het Onderzoek van markeringen werkt niet voor gelokaliseerde onderzoekstermijnen. NPR-26171: Hotfix voor CQ-4249926
* De achterknoop slaat een pagina in het forumonderzoek over. NPR-26950: Hotfix voor CQ-4254804
* De instantie AEM die op de haven van standaardHttp loopt (80) kan niet imsmanifest.xml bereiken. NPR-27173: Hotfix voor CQ-4252211
* Unmark commentaar als antwoord voor QnA werkt niet als de Gemeenschappen AEM met DSRP wordt geplaatst. NPR-26247: Hotfix voor CQ-4252232
* Kan de Opslag van Adobe roepen niet: 414 fout - Lange GET URI waargenomen wanneer de gebruikers /content/community-components/en/search.html zoeken en auteursgebied als één van de filters voor die onderzoekstermijn selecteren. NPR-26643: Hotfix voor CQ-4251303
* De waarde van Dropdown voor DataCenterURL in configuratie ASRP wordt veranderd van Dallas in Virginia (voor VA6). NPR-26936: Hotfix voor CQ-4254434
* De speciale karakters in de fouten van de forumterugkeer of geen resultaten. NPR-26930: Hotfix voor CQ-4247744
* Het aantal dat voor &quot;Aantal resultaten&quot;in forumonderzoek wordt getoond gebruikt onjuiste afbakening voor Engelse en Duitse scènes. NPR-27050: Hotfix voor CQ-4248939
* Ongelezen berichten stijgen niet meer dan 21. NPR-26946, NPR-27480: Hotfix voor CQ-4252829, CQ-4256939
* De paginering in de commentaarsectie van om het even welke component maakt tot gebruikers scrollen omhoog om de paginainhoud te zien, bij het bereiken van een pagina door paginering. NPR-27032: Hotfix voor CQ-4251228
* De communautaire omslag van de Plaats is niet klikbaar op duimnagelbeeld wanneer het bekijken van adminconsole op de instantie van de Auteur AEM. NPR-26986: Hotfix voor CQ-4254036
* De optie &quot;markeren alle gelezen&quot;markeert slechts eerste 10 berichten zoals gelezen en anderen blijven ongelezen tot een pagina zich verfrist. NPR-27037: Hotfix voor CQ-4254058
* De paginering wordt niet teweeggebracht voor Ideatie en de lijst van onderwerpen (of antwoorden) wordt langer tenzij het wordt herladen. NPR-26193: Hotfix voor CQ-4252104
* De activiteiten van andere gebruikers en geschrapte UGC zichtbaar bij het het programma openen met moderatorgeloofsbrieven en het toevoegen van &quot;#social-activiteiten&quot;of &quot;#tabs-2&quot;aan het eind van het profiel URL van de moderator. Hotfix voor CQ-4251355
* Alle toegewezen markeringen kunnen niet uit een blogartikel worden verwijderd. NPR-26851: Hotfix voor CQ-4253359
* Verhoudingen met UGC worden niet verwijderd op UGC-verwijdering. NPR-27630: Hotfix voor CQ-4258706
* De verbinding voor antwoorden werkt niet aan rij klikt op de antwoorden van het Forum. NPR-27623: Hotfix voor CQ-4256138
* De limiet voor gebruikersabonnementen is beperkt tot 1000. NPR-27614: Hotfix voor CQ-4254689
* Het uitgeven van een plaats en het uitgeven rollen in de rolmontages werpen de Volledige Uitzondering van de Wijzer. NPR-27377; Hotfix voor CQ-4255909

**Vertaling**

* De voorproef van de vertaling werkt niet met de wij.retail steekproefinhoud. NPR-26727: Hotfix voor CQ-4241179

**UI - Foundation**

* Een NullPointerException is teruggekeerd wanneer het proberen om configuraties na bevordering aan AEM 6.4 te downloaden. NPR-27310: Hotfix voor Graniet-23573
* Proactieve Backport voor granite.platform.login moeilijke situaties. NPR-26941
* Pro-actieve Backport voor granite.ui.coentmoeilijke situaties. NPR-26294
* De het gebiedscomponent van het aantal bevestigt geen negatieve aantallen op Internet Explorer 11. NPR-26701
* Pro-actieve Backport voor granite.ui.coralui3 moeilijke situaties. NPR-26662
* Pro-actieve Backport voor granite.ui.coralui3-eon moeilijke situaties. NPR-26666
* De pro-actieve Steun voor granite.ui.foundation.components bevestigt. NPR-27313
* Pro-actieve Backport voor granite.ui.commons moeilijke situaties. NPR-26753
* Pro-actieve de Backports van de Stichting UI. NPR-26248

**Integratie**

* Wijzigingen in de AEM-ervaringen die met de doelengine zijn gemaakt, worden niet gepubliceerd. NPR-24869: Hotfix voor CQ-4247832
* Kan veelvoudige activiteiten en ervaringen tot stand brengen niet als hun namen Japanse karakters omvatten. NPR-27271: Hotfix voor CQ-4256857
* Start API-eindpunt bijwerken NPR-26790: Hotfix voor CQ-4254380
* (Personalisatie) BrandsRetriever loopt de volledige boom. NPR-27060: Hotfix voor CQ-4255790

**WCM - Admin UI**

* De toegevoegde test van HTTP voor het publiceren/unpublishing van een pagina met verwijzingen en een test UI voor Levend Exemplaar. Hotfix voor CQ-4256894

**WCM - Pagina-editor**

* Geef toolbar uit wordt gehandicapt voor componenten op eerste uitgeeft. Hotfix voor CQ-4253270

**Formulieren**

De belangrijkste hoogtepunten voor vormen AEM 6.4.3.0 zijn:

* Toegelaten steun voor een serie/lijst van voorwerpen met de Dynamische Vervanging van de Entiteit.
* Toegelaten naleving FIPS voor Reader Uitgebreide werkschema in Digitale Handtekening, de Uitbreidingen van de Lezer, CryptoProvider, en TrustStore.
* De toegevoegde steun PDF/UA aan XFA vormen die gebruikend de Dienst van de Ontwerper of van de Output worden geproduceerd.
* Toegelaten steun voor allowPaths bezit op Aanpassings vormenmalplaatjes.
* Toegevoegde JBoss 7.1.4 steun voor de Vormen 6.4 van AEM.

**Formulierinvoegpakket**

**Backend-integratie**

* Onbekwaam om modelafbeeldingen van vormgegevens te bevolken die op dynamische entiteiten in de reactie van de ZEEP worden gebaseerd. NPR-26428: Hotfix voor CQ-4250639
* De waarde voor _elementNamespace in het model van vormgegevens extra gegevens, ingegaan gebruikend Test UI, wordt niet correct weerspiegeld in het verzoek van de ZEEP. Hotfix voor CQ-4255373
* Een nullable bezitsbeperking wordt geïnitialiseerd met een standaardwaarde en kan niet met FDM worden gesynchroniseerd. Hotfix voor CQ-4253873
* De standaardwaarde voor het nullable bezit wordt niet geplaatst aan Waar voor OData gegevensbron. Hotfix voor CQ-4253870

**Aanpassingsvormen**

* Onbekwaam om plaatsen en vormenredacteur te laden. NPR-26977; Hotfix voor CQ-4249170
* Problemen bij het toevoegen van een bijlage aan een adaptief formulier met het toetsenbord. NPR-25913; Hotfix voor CQ-4249456

**Formulieren - Interactieve communicatie**

* Onbekwaam om een paneel te bewegen dat gebruikend de Add optie van het kindpaneel in de inhoudsboom in het kanaal van het Web van Interactieve Mededeling en in adaptieve vormen is toegevoegd. Hotfix voor CQ-4253915
* De namen van de lijst worden getoond in plaats van de titel van de vereniging FDM in de sectie van Gegevensbronnen van het kanaal van de Druk. Hotfix voor CQ-4253669
* De functie isUseXFABullets () is niet gehandicapt in klasse PrintChannelRenderOptions en is beschikbaar in cliëntSDK. Hotfix voor CQ-4246583, CQ-4252700

**Correspondentiebeheer**

* JavaDocs voor 6.4 bevat niet com.adobe.dbforms.* verpakking en de overeenkomstige klassen. Hotfix voor CQ-4253200
* CCR UI toont een standaard troepenwaarde voor het datumgebied voor het geval dat er geen input van de testgegevens XML is. Hotfix voor CQ-4252041
* Als een brief een lijstmodule bevat, wordt de ruimte tussen kogel en tekst verloren terwijl het produceren van PDF van de brief. Hotfix voor CQ-4250588

**Formulierbeheer**

* Toegelaten steun voor allowPaths bezit op Aanpassings vormenmalplaatjes. NPR-26598: Hotfix voor CQ-4255892

**Formulieren - Werkstroom**

* Als de steunen in de taaknaam terwijl het uitvoeren van het werkschema van Vormen inbegrepen zijn, wordt een uitzondering getoond in de logboeken. Hotfix voor CQ-4256626
* Onbekwaam om een malplaatje van het Onderzoek in AEM te openen vormt werkruimte. Hotfix voor CQ-4255651

**Mobiele formulieren**

* Het uitgangsbericht toont niet terwijl het weggaan van het datumgebied in Vormen AEM die als HTML in Internet Explorer of Chroom worden teruggegeven. NPR-26483: Hotfix voor CQ-4239352
* De data in XML wanneer de verwerking begint veroorzaakt de vormen om een bevestigingsfout op te werpen wanneer de gebruiker probeert om de vorm te verlaten. NPR-26787: Hotfix voor CQ-4251211

**Forms JEE-installateur**

**PDF-generatorservice**

* Kan standaardinstellingen voor rapportage en naleving voor PDF-Generator niet weergeven. NPR-26715: Hotfix voor CQ-4253384
* het omgekeerde pdf binaire dossier mist in het toe:voegen-op pakket van de Vormen van AIX, dat mislukking terwijl het aanhalen van de dienst PDFA veroorzaakt. Hotfix voor CQ-4257873

**Documentservices**

* Voeg FIPS naleving voor het werkschema van RE in Digitale Handtekening, de Uitbreidingen van de Lezer, CryptoProvider, en TrustStore toe. NPR-27495: Hotfix voor CQ-4257572
* De omzetting ontbreekt terwijl het runnen van de dienst AssemblerService.toPDFA in een lijn. NPR-26354: Hotfix voor CQ-4248656
* Kan de naleving van PDF&#39;s niet correct valideren op basis van PDF/A-1b-standaarden. NPR-26286: Hotfix voor CQ-4227539
* Uit geheugenkwesties terwijl het bevorderen van de Vormen van AEM van 6.1 SP2 GVB5 aan GVB13. NPR-26285: Hotfix voor CQ-4244379
* Kan de naleving van PDF&#39;s niet correct valideren op basis van PDF/A-standaarden. NPR-26272: Hotfix voor CQ-4248823

**Formulieren - Foundation JEE**

* Toegevoegde JBoss 7.1.4 steun voor de Vormen 6.4 van AEM. NPR-27331; Hotfix voor CQ-4255601

**Functiepakketten inbegrepen**

* Toegelaten steun voor een serie/lijst van voorwerpen met de Dynamische Vervanging van de Entiteit. NPR-26590: Hotfix voor CQ-4254655

**SGA-bundels en inhoud**

Lijst van OSGi-bundels opgenomen in AEM 6.4.3.0

[Bestand ophalen](assets/6.4.3.0_bundles.txt)

Lijst van inhoud Pakketten in AEM 6.4.3.0

[Bestand ophalen](assets/6.4.3.0_OSGI.txt)

#### AEM 6.4.2.0 {#experience-manager-6420}

AEM 6.4.2.0 is een belangrijke update die prestaties, stabiliteit, veiligheid en zeer belangrijke klantenmoeilijke situaties en verhogingen omvat die sinds de algemene beschikbaarheid van AEM 6.4 in **april 2018 worden vrijgegeven.**
Het is ook cumulatief, wat betekent dat 6.4.2.0 al AEM 6.4 de dienstpakken versie vóór het omvat.

Enkele zeer belangrijke hoogtepunten van AEM 6.4.2.0 zijn:

* De ingebouwde opslagplaats (Apache Jackrabbit Oak) wordt bijgewerkt naar versie 1.8.7.
* Toegevoegde steun voor de Specificatie 1.4 van de Taal van het Malplaatje van HTML (HTL) eigenschappen
* Extra ondersteuning voor MongoDB Enterprise 3.6.
* De redacteur van de Pagina van Plaatsen voegt steun voor in-context het uitgeven en samenstelling met cliënt-zijcomponenten toe bouwen in React of Angular in combinatie met de Redacteur van het KUUROORD JS SDK <a href="../sites-developing/spa-walkthrough.md">van</a>AEM.
* De verhogingen van de Fragmenten van de inhoud: voegde het vermogen toe om op tekstgebieden te annoteren, en zij aan zij vergelijking van versies.
* Toegevoegde [integratie met de Voorraad](/help/assets/aem-assets-adobe-stock.md) van Adobe zodat de gebruikers, voorproef, sparen en vergunning de activa van de Voorraad van Adobe direct van het gebruikersinterface van AEM kunnen zoeken. Voor meer gedetailleerde informatie, zie het [Gebruiken van de activa van de Voorraad van Adobe met activa](https://helpx.adobe.com/experience-manager/kt/assets/stock-assets-feature-video-use.md)AEM.
* De activa toegevoegde steun voor dynamische voorwaardelijke metaschema en de capaciteit om een meta-gegevensschema voor activaomslagen te plaatsen.
* Toegevoegde configuratie in elke component om de verwezenlijking/updatefunctionaliteit van de omslagduimnagel toe te laten onbruikbaar te maken.
* De verhogingen van de Redacteur van het beeld op paginacreatie.
* De moeilijke situatie van de regressie in Gemeenschappen voor het noteren van gebeurtenis die niet behoorlijk wordt behandeld in het geval van geselecteerd antwoord die wordt geschrapt.
* Herziene de maximumgrens van onderzoeksresultaten voor solr aan MAX_INT-10000.
* De baan van de Duw van de transactie is begonnen slechts op de eerste vraag aan storeTransaction.
* De knop Alles selecteren is nu beschikbaar in Kaartweergave en kolomweergave.
* De verbeteringen van de toegankelijkheid in CoralUI.
* Verbeterde verwerking van Coral.Keys.
* Bijgewerkt moment.js aan 2.22.2
* Bijgewerkte jquery aan 1.12.1
* Introduceerde stichting-werkstroom statuscomponent.
* Bijgewerkte GCC aan recentste versie.
* SAML van de beweging aan nieuwe externe synchronisatie IDP.

**Assets**

* De generatie van subassets voor pptx- dossier bevat geen beelden en duimnagels. NPR-24286: Hotfix voor CQ-4217986
* migrateAllAssets - voeg steun voor partijverwerking toe en verbeter AEM methode die UUID aan oude activa toevoegt. NPR-24861: Hotfix voor CQ-4242863 en CQ-4247874
* Het probleem van prestaties met duimnagelgeneratie. NPR-24693: Hotfix voor CQ-4246960
* (Tik op UI) De component &quot;options voorspellen&quot; blijft leeg wanneer toegevoegd aan de pagina van de uitgeverij van het Aandeel van Activa. NPR-24643: Hotfix voor CQ-4245295
* (Werkschema) de Slimme Activa van de Markering verwerken niet door de volmachtsconfiguratie. NPR-25840: Hotfix voor CQ-4248202
* (Omnissearch) het verwijderen van filetype:het beeld uit zoekcriteria verwijdert niet het beeldtype. NPR-25232: Hotfix voor CQ-4248280
* Wanneer het proberen om een dossier naar een verschillende omslag te verplaatsen, worden de omslagen met weglatingsteken in hun naam niet getoond. NPR-25125: Hotfix voor CQ-4248660
* De schuif in Subasset pagina werkt niet correct wanneer de taalvoorkeur aan andere dan het Engels wordt geplaatst. NPR-25274: Hotfix voor CQ-4248489
* Probleem met csv-bestand met metagegevens exporteren wanneer het wordt geopend op machines met een Europees nummerformaat. NPR-26009: Hotfix voor CQ-4250677
* De knop Maken is niet beschikbaar op de selectie van de activamap zonder toestemming om deze te verwijderen. NPR-25788: Hotfix voor CQ-4250140
* (Backport) Verbeteringen van de toegankelijkheid: Duplicaat-id: De waarde van de attributen van identiteitskaart moet uniek zijn, Etiket: De elementen van de vorm moeten etiketten en verbinding-naam hebben: De verbindingen moeten duidelijke teksten hebben. NPR-24252: Hotfix voor CQ-4250905, CQ-4250906, CQ-4250907
* Het uploaden van een csv met velden gescheiden met &quot;,&quot; mislukt voor Europese landen. NPR-25549: Hotfix voor CQ-4249931
* (Merk Portal) Subassets van een pdf-bestand met meerdere pagina&#39;s publiceren niet wanneer een actief wordt gepubliceerd. NPR-25991: Hotfix voor CQ-4245162
* Publiceer recentere functionaliteit voor AEM aan de replicatie van het Portaal van het Merk. NPR-25911: Hotfix voor CQ-109139
* Het publiceren en unpublishing de privé inzameling door gebruikers niet-admin resulteert in een NPE. NPR-25906: Hotfix voor CQ-4250594
* Maak publiceren van inhoudsfragment en vormenschema&#39;s aan het Portaal van het Merk onbruikbaar. NPR-24176, NPR-26004: Hotfix voor CQ-4251592, CQ-4252026
* (Dynamische Media) werkte de kijkers van DM aan versie 5.10.1 bij die controle voor dubbele namen op de Vooraf ingestelde pagina van het Beeld toelaat. Raadpleeg Dynamische mediumweergaven bijwerken (5.10.1). NPR-24403: Hotfix voor CQ-4247554
* De fout van Javascript in browser console in kolommening bij het selecteren van een activa of een omslag. NPR-25939: Hotfix voor CQ-4250228
* (De mening van de Kolom) kan geen taken identificeren aangezien het belangrijkste dossier omhoog als lege witte ingang verschijnt. NPR-25903: Hotfix voor CQ-4246307

**Sites**

* De vraag van datasource.jsp op AEM 6.2 is verschillend van AEM 6.4. NPR-24968: Hotfix voor CQ-4244235
* (Klassieke UI) Kan geen tags aan pagina&#39;s toevoegen. NPR-25255, NPR-25612: Hotfix voor CQ-4249615
* De Specificatie 1.4 van de Taal van het Malplaatje van HTML eigenschappen die aan AEM 6.4.2.0 NPR-24585 worden gesteund
* De verkeerde overerving op lokale component na het kopiëren van een levende exemplaarpagina. NPR-25920: Hotfix voor CQ-4236737, CQ-4248957
* De tijd wordt ON/OFF opgeslagen in crx/de maar haalt niet het zelfde in de console van paginaeigenschappen UI. NPR-25154: Hotfix voor CQ-4243431
* Het Systeem van stijlen breekt de aanvankelijke de eigenschappen van de dialoog waarden. NPR-25648: Hotfix voor CQ-4250073
* Wanneer het bepalen van cq:tagName bezit in een cq:htmlTag knoop, wordt de markeringsnaam niet overwogen als de component via JSP inbegrepen is. NPR-24154: Hotfix voor CQ-4244120
* Voor een genestelde parsys componenten, altijd wordt het eerste (met de minste genestelde weg) bevredigende ontwerp toegepast van veelvoudige beschikbare componenten. Voor meer informatie, zie de Resolutie [van de Weg van het](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/page-templates-static.html)Ontwerp. NPR-24973: Hotfix voor CQ-4246276
* Wanneer het kleven van tekst in een component van RTE, wordt een pop-up dialoog getoond, maar niet behoorlijk teruggegeven. NPR-24895: Hotfix voor CQ-4245901
* (RTE) Prestatiekwesties met verplichte veldindicator. NPR-24894: Hotfix voor CQ-4241895
* (De component van de Pagina) het Toevoegen van een component aan Parsys wordt bebouwd van recht en komt uit de breedte van het apparatenkader. NPR-25536: Hotfix voor CQ-4238224
* De redacteur van Plaintext verzendt niet in orde gemaakte gegevens en voegt extra ruimten toe. NPR-25312: Hotfix voor CQ-4249006
* Terwijl het openen van de component die inlide wijze gebruikt, eerder geladen plugins zijn niet zichtbaar de tweede keer. NPR-24610: Hotfix voor CQ-4236850
* Het laden van een XF in redacteursmening door exemplaar/deeg laadt automatisch niet de hoofdvariatie. NPR-24841: Hotfix voor CQ-4248037
* De verkeerde structuur van HTML in site admin/damadmin breekt IE11. NPR-24686: Hotfix voor CQ-4246363, CQ-4248402
* (Beheer de Tovenaar van de Publicatie) Kalender voor activeringsdatum in de stap van Opties opent niet na sommige acties bij de stap van het Bereik. NPR-25681: Hotfix voor CQ-4250205
* Klassieke UI werkt niet om CUG uit te geven toe te schrijven aan afleiding. NPR-25075: Hotfix voor 4241823
* Creeer optie niet beschikbaar om ervaringsfragmenten tot stand te brengen. NPR-26053: Hotfix voor CQ-4249923
* De variatie XF wordt geactiveerd tweemaal vandaar, producerend dubbele IDs voor het zelfde punt. NPR-24179: Hotfix voor CQ-4245093
* De lijst van de stichting is kwetsbaar aan Opgeslagen dwars-Plaats Scripting. NPR-25185: Hotfix voor CQ-4240760
* &#39;Ongeldige waarde van de recursieselector&#39;-fout tijdens het migreren van een onderdeel van AEM 6.2.1.13 naar AEM 6.4. NPR-24146

**WCM - Pagina-editor**

* Veelvoudige gestapelde Parsys toe te schrijven aan long-running vragen (meer dan 6) maakt AEM traag. Hotfix voor CQ-4240247
* JS-fout bij het toevoegen van lege cq:tagName in cq:htmlTag-node. Hotfix voor CQ-4251852
* Update EditableActions die op de verhuizing columnClassNames wordt gebaseerd. Hotfix voor CQ-4250781
* Stel middel en modelwegen bloot gebruikend één enkel bezit en attribuut. Hotfix voor CQ-4251255
* Keer export.json API terug die veranderingen doorbreekt. Hotfix voor CQ-4251854
* (Editable SPA) de kandidaat van de Versie voor 1.0.0. Hotfix voor CQ-4251991
* Geef toolbar uit wordt gehandicapt voor andere componenten bij het uitgeven van om het even welke component. Hotfix voor CQ-4253270

**Integratie**

* De bibliotheek en de Download URL- gebieden zouden editable moeten zijn. NPR-24804: Hotfix voor CQ-4246864
* Probleem met meerdere DTM-configuraties. NPR-24685: Hotfix voor CQ-4247293
* Toegevoegde steun voor asynchrone plaatsing voor ontvangen cliëntbibliotheken. NPR-25716: Hotfix voor CQ-4245745
* De gerichte component met het missen van overeenkomstige aanbieding geeft de gehele pagina terug en in plaats van een lege gerichte component, wordt een andere volledige vertolking van de pagina toegevoegd. NPR-25273: Hotfix voor CQ-4248003
* De motor van het doel (mbox.js, at.js) gebruikt geen beheerde URLs en gebruikt URLs die dubbelpunten bevatten die met bepaalde plaatsingen zouden kunnen ontbreken. NPR-25339: Hotfix voor CQ-4237854
* (Lancering)LibraryDownloadProcess slaat verkeerde libraryUri waarde op. NPR-25330: Hotfix voor CQ-4250006

**Platform**

* Reindexeringslus| NPE terwijl het uitvoeren van BinaryTextExtraction tijdens plaatsverbetering van 6.3 tot 6.4. Hotfix voor Graniet - 21677
* Grensoverschrijdende opheffing van interne duidelijke weg /libs/cq/cloudserviceconfigs/sjablonen/configurepage/jcr:content - Probleem tijdens het uitvoeren van patroondetector. NPR-25036: Hotfix voor CQ-4248597
* De ingangen van het logboek niet geschreven toe te schrijven aan NPE in LogEntryImpl. NPR-25627: Hotfix voor Graniet-22383
* De replicatie van schrappingsgebeurtenis controleert geen rechten. NPR-25679: Hotfix voor CQ-4241234
* De toegevoegde steun STARTTLS in de &quot;Dienst van de Post van de Dag CQ.&quot; NPR-25611: Hotfix voor CQ-4249924
* De pro-actieve steun voor granite.platform.login moeilijke situaties om toegankelijkheid te verbeteren. NPR-25176: Hotfix voor Graniet 21746 en Graniet-21309
* (AEM 6.4) Fout tijdens het opnieuw samenstellen van pakket en het opnieuw installeren van het pakket. NPR-25173: Hotfix voor CQ-4247939
* Verwijderde standaardMERGE_PRESERVE aclHandling. NPR-24593: Hotfix voor Graniet-21889
* Het tevreden-Type wordt niet voorgesteld en mist in de reactie na tweemaal het toepassen van ContentDispositionFilter. NPR-24175: Hotfix voor Sling-7525
* De status van de Manager van het pakket verkeerd na verbetering aan AEM 6.4 tak. NPR-24551: Hotfix voor graniet-21750
* De instantie van AMS - de logboekanalyse van de Fout. Hotfix voor CQ-4249567

**Beveiliging**

* SAML richt opnieuw login aan logout pagina gebruikend Okta IDP opnieuw. NPR-25523: Hotfix voor GRANITE-22364
* IMS-verificatie via OAK externe IDP OAuth Provider-configuraties schakelt de gebruiker die in AEM is gemaakt, uit. NPR-25301: Hotfix voor graniet-22363

**MAC - Test &amp; de Integratie van het Doel**

* (Het richten) de componentenfout van de Tekst tijdens het Targeting. Hotfix voor CQ-4233343

**Gemeenschappen**

* (De Bibliotheek van het Dossier) Downloadend activa met lege ruimten van de kwesties van het oorzaken formaat. NPR-24260: Hotfix voor CQ-4245159
* Vast aan verscheidene Sociale kwesties van Adobe. NPR-24247: Hotfix voor CQ-4245054, CQ-4245120, CQ-4245296
* De info- rol voor leden en groepenconsole ontbreekt in het geval dat de auteur looppas op verschillende contextwegen publiceert. NPR-24437: Hotfix voor CQ-4246013
* De post keert niet aan de onbeantwoorde staat terug zelfs bij het verwijderen uit de beantwoorde staat en de score niet decrement. NPR-24419: Hotfix voor CQ-4245797, CQ-4245932
* De gebeurtenissen die gebruikend kalenderfunctionaliteit in de output van gemeenschappen worden toegevoegd verkeerde waarden. NPR-24883: Hotfix voor CQ-4244056
* (het Forum van Gemeenschappen) Kwesties met Paginering klikken en het ladingsgedrag van de Pagina. NPR-24880: Hotfix voor CQ-4246109
* (Chrome) de omzettingen van de tijdzone ontbreken op gemeenschappen gebeurtenissen. NPR-24881: Hotfix voor CQ-4247115
* Onbekwaam om ingebed voorwerp in E-mail terug te geven. NPR-24999: Hotfix voor CQ-4248022
* De opeenvolging van de automatisering zou op update UGC naast verwezenlijking UGC moeten worden uitgevoerd. NPR-25892: Hotfix voor CQ-4251399
* De modulaire dialoogontvankelijkheid op Groepen. NPR-25623: Hotfix voor CQ-4248805
* Solr wordt de uitzondering geworpen op inhoudsschrapping. NPR-25869: Hotfix voor CQ-4248908
* De gepagineerde verbindingen met draden met heel wat posten werken niet aan Berichten. NPR-25678: Hotfix voor CQ-4243038
* De waarden van de tijd in de tijd van de de vertoningsserver van het onderzoeksresultaat in plaats van de de tijdzone van de cliënt. NPR-25594: Hotfix voor CQ-4248986
* (De commentaren van het Forum) Browser de achterknoop werkt niet zoals verwacht. NPR-25205: Hotfix voor CQ-4248573
* (De resultaten van het Onderzoek) Browser de achterknoop werkt niet zoals verwacht. NPR-25214: Hotfix voor CQ-4248574
* Null is teruggekeerd wanneer het overbelen van de component van het communautaire groepslidmaatschap. NPR-25228: Hotfix voor CQ-4248523
* (De Kalender van Gemeenschappen) ClassCastException wordt geproduceerd terwijl het bewaren van de gebeurtenis met het nieuwe beeld van de Bedekking. NPR-25167: Hotfix voor CQ-4248662
* (Communities) Berichten worden afgekapt. NPR-25326
* (AEM publiceert) het Middel van het Scorebord ontbreekt met contextweg en toont het lege scherm. NPR-26155: Hotfix voor CQ-4251942
* (MSRP) de pas gecreëerde kalender wordt bewaard gedeeltelijk werpend NPE in het foutenlogboek. NPR-26071: Hotfix voor CQ-4250531
* De paginering van het forum/van het Onderwerp wordt slechts bijgewerkt wanneer de pagina wordt verfrist. NPR-26070, NPR-25965: Hotfix voor CQ-4249509
* (Q&amp;A Forum) Onbekwaam om aan vorige pagina te navigeren bij het openen van een directe verbinding aan een commentaar. NPR-26069: Hotfix voor CQ-4251699
* Upload beeld in Create groep werkt niet aan mobiel. NPR-26172: Hotfix voor CQ-4251703
* (Overseinen) wanneer het gebruiken van DSRP, wordt de naam van berichtontvanger altijd getoond als &quot;Onbekend&quot;. NPR-26056: Hotfix voor CQ-4251397
* Het de voltooiingsstatusetiket van het Middel van het Scorebord van Enablement verschijnt leeg in UI. NPR-26034: Hotfix voor CQ-4249994
* Terwijl het creëren van een nieuwe communautaire groep, wordt een dubbele communautaire groep gecreeerd op een actieve/actieve cluster mongoMK. NPR-26032: Hotfix voor CQ-4245884
* (Auteur) de aanmaaktovenaar van de Groep duurt te lang om een groep binnen de tovenaar te laden/tot stand te brengen. NPR-26031: Hotfix voor CQ-4244966
* Parsys verdwijnt bij het toevoegen van omvat verklaring in het hbs manuscript. NPR-25908: Hotfix voor CQ-4250489
* Bij het toelaten van &quot;sta bevoorrecht&quot;toe, zouden de bevoorrechte leden slechts voor gebruikers moeten kunnen samenstellen die lid van de gemeenschap zijn. NPR-25877: Hotfix voor CQ-4248450
* Deeplinks geblokkeerd voor inschakeling. NPR-25966: Hotfix voor CQ-4251478
* De paginering van het forum wordt niet dynamisch bijgewerkt op verwijdering van antwoorden. NPR-25970: Hotfix voor CQ-4248975, CQ-4252843
* De auto scrollen en het benadrukken werken niet aan kalender en filelibgebeurtenissen in het geval van genestelde commentaren. NPR-25958: Hotfix voor CQ-4251471
* (DSRP) de Direct/Deep prestaties van de Verbinding die met hoge hoeveelheden Gebruiker degraderen - geproduceerde Inhoud. NPR-25957: Hotfix voor CQ-4251470
* Onbekwaam om de eigenschappen van Allow bevoorrechte Leden en Bevoorrechte leden te wijzigen. NPR-26014: Hotfix voor CQ-4244592
* Merk allen zoals gelezen stelt de berichttellers voor alle communautaire pagina&#39;s terug. NPR-25931: Hotfix voor CQ-4248612
* Geef ITs uit ontbreekt voor DSRP. NPR-25929: Hotfix voor CQ-4251382
* E-mail ITs die wegens NPE ontbreken terwijl het bouwen van e-mailmalplaatjes. NPR-26039: Hotfix voor CQ-4250962
* De draadkwesties van het forum wanneer het inbedden van beelden met zeer hoge resolutie. NPR-26037: Hotfix voor CQ-4244453, CQ-4253099
* De vertoningenschakelaars van de tijd wanneer de streek van de servertijd van de gebruikerstijdzone verschilt. NPR-26036: Hotfix voor CQ-4248751
* Het vastmaken van een dossier tweemaal met de zelfde naam aan een forumpost leidt tot serverfout. NPR-24172: Hotfix voor CQ-4244367
* De de prestatiesmoeilijke situaties van de steun - de paginering van de Groep op auteur en publiceert, het onderzoek van de Groep op auteur, vermijdend rangschikking van antwoorden voor dagboek, kalender en ideatie en luie lading voor het krijgen van de knoop van het groepslidmaatschap (nodig/unnodig) voor elke groep terwijl het bekijken van de pagina van de groepslijst. NPR-24538: Hotfix voor CQ-4246515
* De Middelen van Enablement zijn niet zichtbaar op auteur. Hotfix voor CQ-4252618
* De berichten worden niet geproduceerd voor draad van onbekende gebruiker. Hotfix voor CQ-4245132
* Het onderzoek van de groep verschijnt niet op linkerspoor. Hotfix voor CQ-4252621
* (Auteur) Paginering werkt niet voor de Console van Groepen. Hotfix voor CQ-4242786
* jQuery UI-upgrade. Hotfix voor CQ-4248894
* Upgrade naar de nieuwste versie van SCORM 2017.1. NPR-25675: Hotfix voor CQ-4240671
* De velden &quot;Compose on Behalve&quot; zijn zichtbaar voor gebruikers buiten de gemeenschap. NPR-25331: Hotfix voor CQ-4247858
* De post is nog zichtbaar op UI zelfs na schrapping en geeft fout op console. NPR-26290: Hotfix voor CQ-4252803
* (De montages van de Plaats) Onbruikbaar om veranderingen te bewaren die aan Rollen worden gedaan. NPR-26274: Hotfix voor CQ-4252187
* (De Kwetsbaarheid van de Veiligheid) de Overname van de Rekening toe te schrijven aan de Symbolische Misconfiguration van het Web JSON. NPR-26458: Hotfix voor CQ-4253314
* De paginering wordt niet teruggesteld na verwijdering van antwoorden. NPR-26326: Hotfix voor CQ-4252997
* Het beeld van de gehechtheid wordt niet getoond in Tekeningen terwijl het uitgeven. Hotfix voor CQ-4253360
* De pagina verfrist zich niet terwijl het vastmaken van gehechtheid in Relational Database (DSRP). Hotfix voor CQ-4253084
* De groepen werken niet binnen het de plaatsmiddel van Enablement. Hotfix voor CQ-4252975
* De vereisten die Wegen leren worden niet voortgeduurd in Enablement. Hotfix voor CQ-4252948

**Werkstroom**

* De lancerer UI van het werkschema toont niet voorbij 41 lanceringsconfiguraties en brengt een fout javascript in de console teweeg. NPR-25028: Hotfix voor CQ-4247604
* Het uitgeven van een erfeniswerkschema zonder zijn lancerer uit te geven veroorzaakt veelvoudige werkschema&#39;s om op om het even welk werkschema tot stand te brengen dat een Activate stap van de Pagina/van Activa bevat. NPR-25870: Hotfix voor CQ-4250896
* Onjuiste verbinding in werkschemalading als de pagina een meta-gegevensknoop heeft. NPR-25916: Hotfix voor CQ-4250733

**Vertaling**

* Vast dat het invoeren van vertaald project twee gezamenlijke POST- verzoeken maakt, vandaar, veroorzakend fout. NPR-24889: Hotfix voor CQ-4247638
* Vast dat wanneer het creëren van vertaalproject voor veelvoudige talen, alle pagina&#39;s voor de zelfde taal aan de zelfde baan worden toegevoegd. NPR-25091: Hotfix voor CQ-4246112
* Vast dat in sommige gevallen, de vertaalbaan slechts van de hoogste 40 pagina&#39;s een lijst maakt. NPR-25974: Hotfix voor CQ-4248661
* De component van DataPicker (Coral2) die niet het jaar verandert. NPR-24466: Hotfix voor Graniet-21893

**UI - Foundation**

* Pro-actieve de Backports van de Stichting UI. NPR-24344, NPR-24345, NPR-25176, NPR-25095, NPR-24332, NPR-25653, NPR-25932, NPR-259 35 NPR-25976
* (De Importeur van het Ontwerp) het Invoeren van een pagina voert js niet in, css. NPR-25203: Hotfix voor Graniet-22236
* De pro-actieve Steun van de Stichting UI Backports om de stabiliteit van het product te verbeteren. NPR-24334

**MAC - Test &amp; de Integratie van het Doel**

* Tweede pagina van Persoonlijke instellingenWizard ( gestart door &quot;Start Targeting&quot; ) is leeg en werpt consolefouten. Hotfix voor CQ-4253277

**Ervaringsfragmenten**

* Samengevoegde de Fragmenten van de Ervaring/Integratie van het Doel aan AEM 6.4.2.0. Hotfix voor CQ-4248653

**Beheer van contentfragmentatie**

* De annotaties van de Fragmenten van de inhoud, en zij-aan-zij vergelijking van de versies van het Fragment van de Inhoud. Hotfix voor CQ-4247148

**DAM - Algemeen**

* &quot;Uitcheckt door&quot; filter werkt niet correct binnen zoekopdracht. Hotfix voor CQ-4247070
* Bij het uitvoeren van het werkschema van de activaupdate, worden het exemplaar van de activataal en zijn duimnagel leeg. Hotfix voor CQ-4250641
* Duplicaat-id: de waarde van de attributen van identiteitskaart moet uniek zijn. Hotfix voor CQ-4250905
* Etiket: De elementen van de vorm moeten etiketten hebben. Hotfix voor CQ-4250906
* Naam link: De verbindingen moeten duidelijke teksten hebben. Hotfix voor CQ-4250907
* De Meta-gegevens van de Omslag van de haven JMX en ServiceUserMapping van het Malplaatje van de Migratie JMX en ServiceUserMapping. Hotfix voor CQ-4252947
* WebdriverIO-tests niet uitgevoerd in release/640 branch of CQ/dam. Hotfix voor CQ-4252749
* De verbindingen aan bewogen activa zijn niet refactored als de verbinding wordt gepubliceerd. Hotfix voor CQ-4245756

**DAM - Kijkers**

* Intermitterende fout bij het laden van video met nieuwe kijkers 5.10.1. Hotfix voor CQ-4250562

**DAM-Merk-portaal**

* Unpublished inzameling van het Portaal van het Merk ontbreekt met fout. Hotfix voor CQ-4245990
* Onbekwaam om beeld ongedaan te maken stelt van het Portaal van het Merk vooraf in. Hotfix voor CQ-4246140
* Subassets van een pdf-bestand met meerdere pagina&#39;s worden niet gepubliceerd wanneer een actief wordt gepubliceerd. Hotfix voor CQ-4245162

**DAM - DMClient**

* Bij het publiceren van een videoelement naar YouTube, zijn de tags die resulteren in YouTube inclusief het volledige pad van de tag. Hotfix voor CQ-4245549
* (Opt-uit en Opt-in verbeteringen) Kwestie met CSS van de Kijker richt opnieuw. Hotfix voor CQ-4247854
* Onbekwaam om kijker te creëren/uit te geven die als niet lid van &quot;beheerders&quot;groep wordt vooraf ingesteld. Hotfix voor CQ-4247618
* (6.4.1.0) Het toevoegen van veelvoudige video&#39;s in veelvoudige parsys breekt de videospeler. Hotfix voor CQ-4248517
* Het anders noemen van &amp; het bewegen van activa binnen een Reeks van het Beeld maakt het uitgeven onmogelijk. Hotfix voor CQ-4248434
* Publiceer grote video&#39;s naar YouTube en gooi tijdberichten uit. Hotfix voor CQ-4237831
* (Lijstweergave) De gebruikersinterface van de Asset Picker/Selector verandert in alle grijs en is uitgeschakeld voor de gebruiker. Hotfix voor CQ-4237817
* (Verticaal zoomen) Css kan niet laden met een fout van 404. Hotfix voor CQ-4236508
* Het proberen om activa met percenten (%) karakter in de activanaam te downloaden resulteert in een leeg archief. Hotfix voor CQ-4250558
* (Kaartweergave) Er wordt geen verwerkingsindicator weergegeven bij het gebruik van Kopiëren en Plakken op een videoelement. Hotfix voor CQ-4249037
* (Upgrade van 6.3.2 naar 6.4) Voorinstellingen voor een upgrade-image worden op de pagina Rendities weergegeven als &quot;Niet gepubliceerd&quot;, maar geven geen URL-knop op wanneer deze is geselecteerd. Hotfix voor CQ-4240406
* Technische schulden/kleine verbeteringen. Hotfix voor CQ-4240648
* De Asset Selector (of Asset Picker) geeft niet alle bedrijfsmiddelen uit de beschikbare mappen weer. Hotfix voor CQ-4218414
* Het beeld dat zonder hoogtevertoningenbeelden met onjuiste grootte wordt vooraf ingesteld. Hotfix voor CQ-4246546
* (Activa van meerdere pagina&#39;s) UI breekt op het klikken op annotaties. Hotfix voor CQ-4251434
* De bevordering van 6.3 aan 6.4 en later vooraf ingestelde Analytics, een nieuwe rapportreeks en vooraf ingestelde analytics wordt gecreeerd die de oudere rapporteringsgegevens van de gebruiker verliezen. Hotfix voor CQ-4244529
* (Beheer de Tovenaar van de Publicatie) de Lijst van Activa schijnen leeg te zijn wanneer het proberen om te publiceren of unpublished. Hotfix voor CQ-4251881
* Wanneer het kiezen van Kijkers na het bekijken van de Vastgestelde Leden, ontbreken de video&#39;s AVS aan playback. Hotfix voor CQ-4205308
* De videoverwerking van de pre-Verbetering stelt kan geen nieuwe Video het Coderen vooraf in wordt toegevoegd hebben noch de bestaande het Coderen Vooraf ingestelde die(n) uitgeven. Hotfix voor CQ-4240407
* Het beeld stelt wordt niet toegepast op gedownloade dynamische vertolkingen vooraf in. Hotfix voor CQ-4249862
* Selecteer al knoop werkt niet correct op de Vooraf ingestelde de lijstpagina van de Kijker. Hotfix voor CQ-4252462
* Videoprofielen: Selecteer Alle knoop is niet-functioneel. Hotfix voor CQ-4253076, CQ-4251447
* SP2 Validatiepas - Rookpas. Hotfix voor CQ-4251639

**DAM - DMServices**

* De dynamische Rendities van Media slaagden er niet in om voor EPS dossier te produceren. Hotfix voor CQ-4243688

**Graniet**

* Het type in bundel SymbolicName leidt tot dubbele bundel. Hotfix voor Graniet - 22155
* CUGConfiguration kan CugExclude niet opnemen. Hotfix voor Graniet - 21109
* Het opnieuw beginnen van de Kern van het Werkschema van Adobe Granite stelt de werkschemastappen van het midden opnieuw in werking creërend onnodige werkschema&#39;s. NPR-25057: Hotfix voor Graniet-22218
* JcrResourceBundle steunt correct geen veelvoudige basisnamen. NPR-25245: Hotfix voor Graniet-22317
* Voor installatie van inhoudspakketten, wordt ACLs gegroepeerd door hoofd, daarom, die het toestemmingsmodel breken. NPR-24583: Hotfix voor Graniet-21591
* Update Jetty aan 9.4.11 om kwetsbaarheid te bevestigen. NPR-25030: Hotfix voor graniet-22120

**Formulieren**

De belangrijkste hoogtepunten voor vormen AEM 6.4.2.0 zijn:

* Toegevoegd nieuw bezit voor Rijen die moeten worden bijgewerkt zonder browser te verfrissen.
* Toegevoegd vermogen voor de gebruiker om het zelfde dossier van WSDL voor de veelvoudige dienst te gebruiken.
* Verwijderde het niet gestaafde timestamp patroon uit datepicker dropdown.
* Toegevoegde ondersteuning voor underwriting xfaf en pdf in OSGI.
* Toegevoegde steun om het vermogen van de [transactierapporten](https://helpx.adobe.com/experience-manager/6-4/forms/using/transaction-reports-overview.html) bij plaatsingen op-gebouw te gebruiken.
* Toegevoegde code om kind var in de redacteur van de voorwaardenregel niet te tonen.

**Formulierinvoegpakket**

**Transactiemelding**

* De Rapporterende configuratie van de Transactie van de update met het belang van omgekeerde-replicatie die op een Publish server wordt gevormd. NPR-26050: Hotfix voor CQ-4246650
* Vertraagde initialisatie van Periodic Flush Job. NPR-25968: Hotfix voor CQ-4245024
* De Opname van de transactie ontbreekt met de Volledige Uitzondering van de Wijzer. Hotfix voor CQ-4247302

**Formulieren - Werkstroom**

* (De Werkruimte van HTML) wanneer een gebruiker een taak eist, wordt de telling van rij verfrist voor die bepaalde gebruiker maar niet voor andere gebruikers tenzij de pagina wordt verfrist. Deze kwestie is door een nieuw bezit bevestigd. Om dit nieuwe bezit aan uw instantie te vormen AEM, verwijs naar zijn Montages van de Configuratie. NPR-24536: Hotfix voor CQ-4233665
* Onbekwaam om grote vorm in de App van Vormen te laden AEM op 6.4. NPR-24463: Hotfix voor CQ-4245091
* Kwestie in de Mobiele App van de Werkruimte wanneer het proberen om de gedeelde taak te bekijken. NPR-25177: Hotfix voor CQ-4248733
* Het inconsistente bevestigingsgedrag tussen Web en APK. NPR-25670: Hotfix voor CQ-4248178
* Wanneer een vraag aan de Webdienst een HTML5 vorm wordt gemaakt die binnen de cliënt wordt geopend, ontbreekt het en een foutenmelding is teruggekeerd. NPR-26048: Hotfix voor CQ-4244716
* Probleem terwijl het roepen van de dienst in AEM vormt Windows app 6.3. NPR-26468: Hotfix voor CQ-4252341

**Mobiele formulieren**

* (Formet) SSN en de Mobiele kwestie van de gebiedsbevestiging wanneer previewed. NPR-24458: Hotfix voor CQ-4244983
* Het gegeven wordt niet getoond met het prefilling van multi-line gebieden in de voorproef van HTML. NPR-24549: Hotfix voor CQ-4244212
* De gegevens worden verloren wanneer het manuscript op een multi-line gebied wordt geëvalueerd. NPR-25333, Hotfix voor CQ-4249610

**Formulieren - Interactieve communicatie en correspondentiebeheer**

* De synchronisatie ontbreekt op IC met BasisMalplaatje en het Malplaatje van de Druk van IC van de Verwijzing. NPR-24912
* (CCR) Validators werken niet voor gebieden/variabelen. Hotfix voor CQ-4245047
* Het pictogram van de Objecten van het Model van gegevens verdwijnt op de toolbar van de Teksten uitgeef met tussenpozen. Hotfix voor CQ-4245122
* De logboeken van de uitzondering verschijnen op gekopieerde IC als originele IC wordt geschrapt. Hotfix voor CQ-4249378
* In de brievenvertolking, evalueert de voorwaarde niet aan waar zelfs wanneer de gegevens correct zijn. Hotfix voor CQ-4245944
* De auto-geproduceerde componenten worden niet benadrukt bij het selecteren van de boom van de Inhoud. Hotfix voor CQ-4246178
* Kwesties terwijl het openen van de redacteur van het Malplaatje van het Kanaal van het Web. Hotfix voor CQ-4248182
* Kan de volgorde van de toegevoegde activa niet wijzigen omdat de pijlen omhoog/omlaag uitgeschakeld blijven. Hotfix voor CQ-4252042
* Onbekwaam om eigenschappen van de module van de Voorwaarde bij te werken. Hotfix voor CQ-4247909
* UX van de dialoog van de &quot;Cancel Overerving&quot;wanneer de gebruiker een Voorwerp in het Kanaal van het Web re-schikt moet worden verbeterd. Hotfix voor CQ-4241076
* De gegevens in de brief die aan banden beantwoordt die in XDP worden bepaald zijn niet bevolkt bij het gebruiken van directe brief URL. Hotfix voor CQ-4245833
* (De kwestie van Caching) de Synchronisatie van Webkanaal wijst niet op veranderingen die aan lay-outfragmenten, het fragment van de Tekst van drukkanaal worden aangebracht. Hotfix voor CQ-4251460
* Onbekwaam om het fragment van de Lay-out en de eigenschappen van DD bij te werken. Hotfix voor CQ-4247830
* (CCR) Het opnieuw laden van het ontwerp ontbreekt wegens het ontleden van XML. Hotfix voor CQ-4250950
* (De Redacteur van IC) &quot;geef Fragment&quot;knoop uit zou meer te ontdekken moeten zijn. Hotfix voor CQ-4244694
* (XDP) het lege scherm wordt getoond bij het toevoegen van een lay-outfragment in nieuwe gecreeerde subform. Hotfix voor CQ-4248810
* De testmislukking van documentFragment-meester-DeployWithServerSideTests. Hotfix voor CQ-4245496
* De module van de tekst veranderlijke Instantie die in de module van de Voorwaarde wordt gedupliceerd. Hotfix voor CQ-4252128
* De voorproefURL PDF toont transactie geen rapportering op publiceert. Hotfix voor CQ-4246158
* IC Sync verwante kwesties met het Kanaal van de Druk aan het Syncen van het Kanaal van het Web. Hotfix voor CQ-4251505
* EXM-code opschonen: Verwijder LocalFunctionMapper. Hotfix voor CQ-4243265
* Om het middeltype van TableHeader van de de lijstcomponent van IC te verbeteren WebChannel. Hotfix voor CQ-4251821
* (Redacteur van IC) de kwesties van de Bruikbaarheid. Hotfix voor CQ-4241081
* Het kanaalsubform van de druk toont tussenvoegselfunctionaliteit niet. Hotfix voor CQ-4252994
* Houd veranderingssynchronisatie ontbreekt post verwijderend FDM knoop of Veranderlijke placeholder. Hotfix voor CQ-4253178
* (De Redacteur van het Malplaatje) het Basismalplaatje toont kopbal/footer extra gebieden van de belemmeringsdaling en het scherm flikkert bij het openen van het Kanaal van het Web. Hotfix voor CQ-4253323
* De auto-geproduceerde componenten worden niet benadrukt bij het selecteren van de boom van de Inhoud. Hotfix voor CQ-4246178

**Documentservices**

* (Form Service) OSGI heeft geen ondersteuning voor XFAF. NPR-25181, Hotfix voor CQ-4251313
* De karakters in de rubriek van het geassembleerde Pdf- dossier komen worden verminkt. NPR-25113: Hotfix voor CQ-4244682

**Aanpassingsvormen**

* Verzend Actie aangezien Send Post een uitzondering met CC/BC- gebiedsspatie werpt. NPR-25019: Hotfix voor CQ-4243039
* Kan de OOTB AEM-component niet gebruiken vanwege inefficiënte query. NPR-25065: Hotfix voor CQ-4247256
* Verwijderen: bestellingVoordat u de dialoognodes van guideImageChoiceComponent selecteert. Hotfix voor CQ-4245013
* (De Plukker van de Datum) geef Patroon uit steunt twee types van timestamp patroon niet. Hotfix voor CQ-4237982
* Leg Actie voor gebruikend de Klassieke auteurskwesties van het &quot;Werkschema van Vormen&quot;creatie. Hotfix voor CQ-4236981
* (Het Kanaal van het Web) de Grafiek van IC zou colspan bezit van AF grafiek moeten erven. Hotfix voor CQ-4252143

**Backend-integratie**

* (De verzoeken van de ZEEP) Grote decimalen (meer dan 6 cijfers) worden vertegenwoordigd in exponentiële aantekening die in bevestigingsfout resulteert. NPR-25283: Hotfix voor CQ-4248100
* Onjuiste validatie van facultatieve parameters die in complexe types worden bepaald. NPR-25070: Hotfix voor CQ-4247107
* Toegevoegd vermogen voor de gebruiker om het zelfde dossier van WSDL voor de veelvoudige dienst te gebruiken. NPR-24604, Hotfix voor CQ-4247756
* FDM rangschikt orde van parameters in zijn vraag van de ZEEP. NPR-25069, Hotfix voor CQ-4247180
* FDM voegt entiteiten (in Lijst/Serie) in het verzoek van de ZEEP samen. NPR-25284: Hotfix voor CQ-4248375

**Forms JEE Installer**

**PDFG-service**

* Het maken/wijzigen van functie van veiligheidsmontages werkt niet. NPR-24769: Hotfix voor CQ-4246927
* Optimaliseer PDFs door doopvonten via enige API vraag selectief open te bedden. NPR-23287

**Documentservices**

* De Dienst van de output verstrekt niet de correcte markeringen voor toegankelijkheidslezer. NPR-24438, NPR-24439, NPR-24440, NPR-24441: Hotfix voor CQ-4243849, CQ-4243845, CQ-4243852, CQ-4243853

**Documentbeveiliging**

* Kwestie met de verwezenlijking van het Beleid gebruikend de Veiligheid van het Document. NPR-25586, NPR-25547: Hotfix voor CQ-4247086

**Formulieren - Foundation JEE**

* Processen die periodiek als Rekening van de Context van het Systeem lopen. NPR-25289, NPR-25313: Hotfix voor CQ-4249331
* AEM vormt JEE die door Apache Struts en Jackson gegevens wordt beïnvloed bindende veiligheidsalarm. NPR-25628: Hotfix voor CQ-4242891
* Het proces van het e-mailbeginpunt werkt niet. NPR-25253: Hotfix voor CQ-4248518

**Inclusief functiepakketten**

**Assets**

* Toegevoegde [integratie met de Voorraad](/help/assets/aem-assets-adobe-stock.md) van Adobe zodat de gebruikers, voorproef, sparen en vergunning de activa van de Voorraad van Adobe van het gebruikersinterface van AEM direct kunnen zoeken. Voor meer gedetailleerde informatie, zie het [Gebruiken van de activa van de Voorraad van Adobe met activa]AEM (https://helpx.adobe.com/experience-manager/kt/assets/using/stock-assets-feature-video-use.html). NPR-15779: Hotfix voor CQ-30857
* Toegevoegde steun voor dynamische voorwaardelijke metaschema. Voor meer informatie, zie het [Draperen Meta-gegevens](/help/assets/cascading-metadata.md). NPR-25189: Hotfix voor CQ-4237413
* De toegelaten optie van de &quot;Download van Activa&quot;op de Fragmenten van de Inhoud. Voor meer informatie, zie de Rapporten van [Activa](/help/assets/asset-reports.md). NPR-25186: Hotfix voor CQ-4237410
* Capaciteit om een meta-gegevensschema voor activaomslagen te plaatsen. Voor meer informatie, zie het Schema van de Meta-gegevens van de [Omslag](/help/assets/folder-metadata-schema.md) en verwijs naar zijn [Montages](#configuration-settings-required-for-npr) van de Configuratie post AEM 6.4.2.0 installatie. NPR-21268: Hotfix voor CQ-4221574

**Sites**

* Sta het uitgeven van een inhoudsfragment toe zonder toestemmingen te schrappen. Voor meer informatie, zie het [Aanpassen en het Uitbreiden van de Fragmenten](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/customizing-content-fragments.html#AssetPermissions)van de Inhoud. NPR-25793: Hotfix voor CQ-4248750
* Toegevoegd de capaciteit om de Fragmenten van de Inhoud te annoteren. For more information, see [Variations-Authoring Fragments](https://helpx.adobe.com/experience-manager/6-4/assets/using/content-fragments-variations.html#AnnotatingaContentFragment). NPR-25188: Hotfix voor CQ-4235336
* Versioning: Vergelijk de Fragmenten van de Inhoud zij aan zij. Voor meer informatie, zie het [Leiden de Fragmenten](https://helpx.adobe.com/experience-manager/6-4/assets/using/content-fragments-managing.html#ComparingFragmentVersions)van de Inhoud. NPR-25187: Hotfix voor CQ-4237412
* De verhogingen van de Redacteur van het beeld die aan AEM 6.4.2.0 worden gesteund. Voor meer informatie, zie de Redacteur [van het](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/image-editor.html)Beeld. NPR-24467

**SGA-bundels en inhoud**

Lijst van OSGi-bundels opgenomen in AEM 6.4.2.0

[Bestand ophalen](assets/6.4.2.0_bundle-list.txt)

Lijst van inhoud Pakketten in AEM 6.4.2.0

[Bestand ophalen](assets/6_4_2_0content-package-list.txt)

#### AEM 6.4.1.0 {#experience-manager-6410}

AEM 6.4.1.0 is een belangrijke update die prestaties, stabiliteit, veiligheid en zeer belangrijke klantenmoeilijke situaties en verhogingen omvat die sinds de algemene beschikbaarheid van AEM 6.4 in april 2018 worden vrijgegeven.

AEM 6.4.1.0 kan worden geïnstalleerd op AEM 6.4 GA. Enkele zeer belangrijke hoogtepunten van het de dienstpak zijn:

* De ingebouwde opslagplaats (Apache Jackrabbit Oak) wordt bijgewerkt naar versie 1.8.3.
* Introduceerde Verbeterde Slimme Markeringen.
* Vestigingen in ontwerpkiezer, tagkiezer (de bron-VM wijzigen en VM richten op auto.)
* Toegevoegde steun voor typeHint om waarden als koord te bewaren.
* Toegevoegde steun voor SMTP over TLS in de Dienst van de Post.
* De behandeling van de volmacht moeilijke situatie voor de expediteur van HTTP in DMS7.
* Update naar /etc/clientlibs/social/thirdparty/handlebars/source/handlebars.js versie 1.3.
* Vast in DMHybrid Opt-OUT en Opt-IN pakketten.
* Vast in Slim Gewas.
* De migreerde OOTB configuratiewaarden aan de nieuwe plaats (van /etc. aan /conf).
* De toegevoegde kleurenprofielen aan de klantenmontages op leveringsservers.
* Migratie van de montages van de Server van het Beeld van /etc —&amp;gt; /conf.
* Toegevoegd Bron-contentfragment voor vertaling.
* De toegevoegde steun ARIA aan Druk en PrintDialog.
* ARIA-ondersteuning voor extra e-mailvalidatie.
* Pro-actieve Backport voor platform.clientlibs moeilijke situaties.

**Assets**

* De draperende dropdown waarde toont leeg bij het heropenen van de pagina van activaeigenschappen. NPR-23042: Hotfix voor CQ-4238761
* De gedeelde verbindingen op mylinkshare pagina en de verbindingen aan de pagina zijn niet beschikbaar voor niet-admin gebruiker NPR-23044: Hotfix voor CQ-4239004
* Om een Volledige Uitzondering van de Wijzer in het werkschema van de Update van Activa van DAM in 6.4.0 te verhinderen. NPR-24134: Hotfix voor CQ-4244972
* De gepubliceerde WCM pagina toont placeholder pictogrammen voor hotspot, ontbrekende CSS dossiers met 403 fout voor Kijkers OTB. NPR-23041: Hotfix voor CQ-4233716
* (De Mening van het Detail) de eigenschap van de Navigatie Next/Back verlaat een bekleding afd in het Dynamische de voorproefgebied die van de Renditie toegang tot de kijker blokkeert. NPR-23043: Hotfix voor CQ-4238499
* De CMYK-afbeeldingsrenditie heeft een onjuiste verzadiging. NPR-23048: Hotfix voor CQ-4235470
* De meta-gegevensextractie XMP door Scene7ListInfoProvider is middel intensief. NPR-23754
* (dam-levering) de expediteur van Http respecteert de volmachtsmontages van HTTP niet. NPR-24002: Hotfix voor CQ-4244140

**Sites**

* Wanneer wij de pagina anders noemen terwijl wij bewegen, is de beweging van pagina succesvol maar noem functionaliteit anders niet werkt. NPR-22923: Hotfix voor CQ-4235907
* Fout wanneer het publiceren van een Levende pagina van het Exemplaar die aan een Pagina van de Importeur in de Campagnes van Adobe richt. NPR-23053: Hotfix voor CQ-4237164
* De beweging/noemt in Klassieke UI ontbreekt met fout anders, &quot;een fout kwam terwijl het bewegen van pagina&quot;voor en anders noemde niet. NPR-23051: Hotfix voor CQ-4235907
* Het schakelen van inhoud van de mening van de Kolom aan lijstmening geeft een lege pagina terug en brengt een Volledige Uitzondering van de Wijzer voor pagina&#39;s met Geplaatste OffTime en OnTime als spatie teweeg. NPR-22968, NPR-23052: Hotfix voor CQ-4238940

**Handel**

* Fix Failing Core Hobbes Testcase (CQ/Commerce Module). Hotfix voor CQ-4253494

**Kwetsbaarheid**

* De integratie van Salesforce is kwetsbaar aan de Smeeuw van het Verzoek van de Server van de Zijkant (SSRF). NPR-24289: Hotfix voor CQ-4245277
* Server Side Request Forgery (SSRF) en Cross-Site Scripting (XSS) in ReportingServicesProxyServlet. NPR-24657: Hotfix voor CQ-4246880
* Scripting op verschillende locaties (XSS): Gereflecteerd in commerciële createcatalogwizard.html/content. NPR-24642: Hotfix voor CQ-4237017
* Het scripting van de dwars-plaats (XSS) in de verbindingen van het Project Admin UI. NPR-23272: Hotfix voor CQ-4241795

**WCM - Elementen van de Stichting**

* Het openen van de plukker van het Ontwerp resulteert in een ongeldige wijzeruitzondering. NPR-23047: Hotfix voor CQ-4238736

**Gebruikersinterface**

* (Coral3 Datepicker) voeg steun voor typeHint toe om waarden als &quot;Koord te bewaren.&quot; NPR-23398: Hotfix voor Graniet-21194
* Internationalisatie-vertalingen werken niet op taalniveau. NPR-22967, NPR-23046: Hotfix voor Graniet-21111
* Pro-actieve Backport voor granite.ui.commons moeilijke situaties. NPR-23537
* Pro-actieve Backport voor granite.ui.coentmoeilijke situaties. NPR-23535
* De pro-actieve Backport voor granite.ui.coralui moeilijke situaties. NPR-23538
* Kan meerdere gebruikers niet tegelijk uit de groep verwijderen. NPR-23846
* (OMEGA) Rapport &quot;Functie&quot; alleen in het Engels. NPR-23989: Hotfix voor graniet-21231
* (De Importeur van het Ontwerp) het Invoeren van een pagina voert geen Js, css in. NPR-25203: Hotfix voor Graniet-22236

**Integratie**

* Unclosed ResourceResolver in com.day.cq.analytics.sitecatalysator. NPR-22340: Hotfix voor CQ-4236515
* TargetContentImpl maakt AEM langzaam tijdens lange lopende vragen. NPR-22359: Hotfix voor CQ-4236907
* De motor van het doel (mbox.js, at.js) gebruikt geen beheerde URLs en gebruikt URLs die dubbelpunten bevatten die met bepaalde plaatsingen zouden kunnen ontbreken. NPR-22434: Hotfix voor CQ-4237854
* Op de wijze van het Doel, kunnen de Auteurs een component wijzigen die van de blauwdruk wordt geërft zonder de overerving te annuleren. NPR-22865: Hotfix voor CQ-4237907
* (Personalisatie) de pictogrammen worden vervormd wanneer het overschakelen op de mening van de Kaart. NPR-23373, NPR-23374: Hotfix voor CQ-4240018, CQ-4240019
* (Personalisatie) de console van het publiek toont niet:omslagtypes. NPR-23375: Hotfix voor CQ-4242293
* Wanneer een component wordt gericht op publiceer instantie, lijkt het flikkeren tonend de standaardervaring vóór gerichte. NPR-23415: Hotfix voor CQ-4242038
* (De Console van Adobe IMS) de de dienstconfiguratie van AccessTokenProvider OSGi verschijnt na schrapping opnieuw. NPR-23520: Hotfix voor CQ-4208250
* De de verwijzingsreplicatie van de configuratie ontbreekt met middenomslagstructuur. NPR-23485: Hotfix voor CQ-4242751
* (Personalisatie) clientlib die door volmachtsservlet wordt geblokkeerd. NPR-23521: Hotfix voor CQ-4240995
* (De Console van Adobe IMS) de Geregistreerde Oplossingen van de Wolk worden niet opgenomen in configuratietovenaar. NPR-23977: Hotfix voor CQ-4244549
* De oneindige lijn wanneer het laden van gerichte inhoud op pagina&#39;s zonder een uitbreiding van HTML. NPR-23522: Hotfix voor CQ-4223600
* De activering ontbreekt voor een pagina met geërfte Dynamische de configuratieverwijzingen van het Beheer van de Markering. NPR-23485: Hotfix voor CQ-4242751

**Platform**

* (Klassieke UI) (Aanraking UI) De markeringsplukker toont en werpt geen uitzondering wanneer het proberen om voor markeringen via een markeringen te doorbladeren voorspelt in het schema van het Onderzoek van Activa. NPR-23049: Hotfix voor CQ-4239371
* (Klassieke UI) Componenten die xtype=tags gebruiken keren ongeldig terug en kunnen niet uit de lijst van eth van markeringen worden geselecteerd. NPR-23050: Hotfix voor CQ-4239937
* (het Brandmerken) de Opt-in dialoog noemt de Wolk van de Marketing van Adobe in plaats van de Wolk van de Ervaring van Adobe. NPR-23210: Hotfix voor CQ-4237799
* De optie van de filter maakt AEM na bevordering van 6.3 tot 6.4 langzaam. NPR-23260: Hotfix voor CQ-4239847 (te controleren)
* Proactieve Backport voor granite.omnissearch.core fixes. NPR-23536
* Pro-actieve Backport voor platform.clientlibs moeilijke situaties. NPR-23569
* De overerving van Config van de Dienst van de Wolk gebroken wanneer het uitgeven van andere paginaeigenschappen. NPR-23216: Hotfix voor CQ-4239782
* De toegelaten steun STARTTLS in de Dienst van de Post van de Dag CQ. NPR-23941: Hotfix voor CQ-4240397

**Projecten**

* (Content Fragment) Taalkopieën voor ingesloten bedrijfsmiddelen worden niet gemaakt terwijl Engelse bedrijfsmiddelen worden toegevoegd aan vertalingen. Hotfix voor CQ-4243477
* De msft config dropdown toont config van /libs (6.4 configuraties) in plaats van /etc(6.3 configuraties) op erfeniswijze. Hotfix voor CQ-4243475
* Vertaalintroducties in vertaalprojecten automatisch promoten en verwijderen. Hotfix voor CQ-4243474
* Het fragment van de inhoud binnen plaatsen die niet worden vertaald. Hotfix voor CQ-4243482, CQ-4243483, CQ-4245687
* Serverfout bij het openen van het zoekfilter voor vertaalwerk. Hotfix voor CQ-4236813
* De geloofwaardige config dropdown is leeg zelfs nadat tif binnen /conf/wij-kleinhandels aanwezig is. Hotfix voor CQ-4236315
* Open Project KPI: de prestatievermindering aangezien meer projecten worden gecreeerd. NPR-23840: Hotfix voor CQ-4238392
* De Starter van het werkschema kan niet waarde TypeHint van Koord goedkeuren. NPR-23863: Hotfix voor CQ-4238356

**Gemeenschappen**

* De kwetsbaarheid van de veiligheid in Versie 1.0 van Handlebars. NPR-23636: Hotfix voor CQ-4243055
* De bulk staat van gemarkeerde berichten toe werkt niet. NPR-23867: Hotfix voor CQ-4243962
* De standaardwaarde toont niet op het sorteren knoop in forumcomponent. NPR-23882: Hotfix voor CQ-4243375
* Kwesties met berichtlevering van communautaire plaatsen aan groepen. NPR-23935

**Werkstroom**

* De dag-CQ Service voor het melden van werkstroom-e-mail van het Werkschema E-mail van de Dag brengt één e-mail per knoop van het Mongo voor WerkstroomCompleted en WerkstroomAborted berichten teweeg. NPR-22515: Hotfix voor CQ-4238172
* Het runnen van het werkschema van de de updateactiva van DAM werpt een NullPointerException. NPR-23010: Hotfix voor Graniet-21096
* De stap van het Proces van het werkschema toont geen manuscripten van /etc/werkschema/manuscripten. NPR-23263: Hotfix voor Graniet-20775
* De Dynamische Stap van de Deelnemer van het werkschema toont geen manuscripten van /apps/werkschema/manuscripten. NPR-23464: Hotfix voor Graniet-21276
* Kan geen workflow bewerken nadat deze eenmaal is bewerkt. NPR-23742: Hotfix voor CQ-4238526
* (Klassieke UI) Op het uitgeven van de werkschemalanceerders, verdwijnen de voorwaarden veroorzakend de werkschema&#39;s om zonder enige voorwaarden te lanceren. NPR-23835: Hotfix voor CQ-4239153
* Project inbox: de omschakeling naar kalendermening toont belangrijkste inhoud inbox. NPR-23947: Hotfix voor CQ-4241236
* Behoefte om ladingsdetails in de bundel bloot te stellen zodat kan de component HTL de waarde in de lijstmening tonen. NPR-23948: Hotfix voor CQ-4240953
* Onbekwaam om dialooggegevens in de stap van de Deelnemer van de Dialoog op te slaan. NPR-23965: Hotfix voor CQ-4234123
* (Tik op UI) Wanneer u een workflowmodel opslaat, verandert de knop &#39;Synchroniseren&#39; in &#39;Synched&#39; als gevolg van een spellingsfout. Hotfix voor CQ-4244843
* Project inbox: de omschakeling naar kalendermening toont belangrijkste inhoud inbox. Hotfix voor CQ-4244436
* Onbekwaam om Dialogen in de stap van de Deelnemer van de Dialoog te selecteren. Hotfix voor CQ-4244532
* Proactieve Backport voor granite.omnissearch.core fixes. NPR-23536
* Kwestie in Mobiele Werkruimte App 6.4 met Gedeelde Taak. NPR-26383

**WCM - Vertalen**

* (Referentiepanel) Vertaaltaken worden niet uitgevoerd tijdens het maken van projecten. Hotfix voor CQ-4245327

**WCM - MSM**

* (MSM) de prestatiesverbetering van de Uitvoer. Hotfix voor CQ-4231488
* (MSM) het hiaat van de Timing in de Luisteren van de Gebeurtenis tussen gebeurtenis die eigenlijk en gebeurtenis behandeling gebeurt. Hotfix voor CQ-4227766

**Schermen**

* De pagina van het scherm ontbreekt met fout toe te schrijven aan ontbrekende gebiedsdelen voor scherm-kern-kg:1.4.42. Hotfix voor CQ-4245918

**Projecten - Vertaling**

* (Content Fragment) Taalkopieën voor ingesloten bedrijfsmiddelen worden niet gemaakt terwijl Engelse bedrijfsmiddelen worden toegevoegd aan vertalingen. Hotfix voor CQ-4243477
* De msft config dropdown toont config van /libs (6.4 configuraties) in plaats van /etc(6.3 configuraties) op erfeniswijze. Hotfix voor CQ-4243475
* Vertaalintroducties in vertaalprojecten automatisch promoten en verwijderen. Hotfix voor CQ-4243474
* Het fragment van de inhoud binnen plaatsen die niet worden vertaald. Hotfix voor CQ-4243482, CQ-4243483, CQ-4245687
* Serverfout bij het openen van het zoekfilter voor vertaalwerk. Hotfix voor CQ-4236813
* De geloofwaardige config dropdown is leeg zelfs nadat tif binnen /conf/wij-kleinhandels aanwezig is. Hotfix voor CQ-4236315

**Beheer van contentfragmentatie**

* Het schrappen van component vult logboeken met stapelsporen. Hotfix voor CQ-4242315

**DAM - Algemeen**

* Het sluiten van de detailmening van activa keert aan onjuiste pagina van het onderzoeksresultaat terug. Hotfix voor CQ-4240960
* (Ruwe Camera) de optie van het Beeld past optie aan mist. Hotfix voor CQ-4246121
* IndexOutOfBoundsException: Rapport van OOTB Asset Modification. Hotfix voor CQ-4239744
* Verwijder betrouwbaarheidsscore uit rapport csv. Hotfix voor CQ-4241491
* E-maillevering voor delen van verbinding verbroken voor niet-admin-afzender. Hotfix voor CQ-4240357
* IT-storingen oplossen. Hotfix voor CQ-4249891

**DAM - Merk Portal**

* De eigenschappen van activa maken een lijst van slechts 3 eigenschappen op eerste lusje, rest alle lusjes leeg kijken. Hotfix voor CQ-4242503
* Het type van dossier en de grootte van het dossier voorspellen zijn niet beschikbaar in gepubliceerde onderzoeksvorm. Hotfix voor CQ-4242026
* Het onderzoek in folderpredikaat zou moeten worden gefiltreerd uit/niet getoond in onderzoeksfilters. Hotfix voor CQ-4241386
* Standaard onderzoek van zou moeten bestaan na unpublished. Hotfix voor CQ-4241383, CQ-4241113
* Publiceer aan merk poortgebaar werkt niet voor beeld vooraf instelt. Hotfix voor CQ-4241074
* Publiceer aan het Portaal van het Merk werkt niet voor inzamelingen. Hotfix voor CQ-4241122, CQ-4246558

**DAM - DM-client**

* De bevordering aan 6.4 verwijdert eerder gecreeerde video het coderen profielen. Hotfix voor CQ-4244067
* Het attribuut van de Tekst van Alt wordt gebroken in de Dynamische component van Media. Hotfix voor CQ-4244081
* (DMS7) het uitgeven verre reeksen in AEM wordt niet beschreven in Scene7. Hotfix voor CQ-4243430
* De controle van 6.4 SP1 bouwt op DM Hybrid voort. Hotfix voor CQ-4244623
* (DMS7-UA) Wanneer het klikken van de Embed knoop voor een gepubliceerd VideoActivum, schijnt niets te gebeuren. De Embed dialoog wordt verwacht om met de code van HTML te tonen. Hotfix voor CQ-4245237
* (DM Hybrid) het Exemplaar URL voor gepubliceerde VideoActiva of de Gemengde Reeksen van Media krijgt &quot;[[objecten Voorwerp]&quot;in de dialoog URL. Hotfix voor CQ-4245236, CQ-4245451
* (DMHybrid) De pagina van de Mening van de Details van de Video bevat niet de voorproef van de VideoActiva toont en output een foutenmelding aan de console. Hotfix voor CQ-4244320
* Automatische S7 Codering van wij.retail inhoud. Hotfix voor CQ-4242253
* De video-verwerking van de verbetering stelt kan geen nieuwe Video vooraf ingestelde Codering hebben vooraf in wordt toegevoegd of het bestaande Coderen uitgeven stelt vooraf in. Hotfix voor CQ-4240407
* De pre-Verbetering Beeld stelt wordt getoond als Niet gepubliceerd op de pagina van Rendities vooraf in en brengt geen URL op. Hotfix voor CQ-4240406
* (CSS) de activa worden getoond - maar de kijkers die worden gebruikt zijn gebrek en niet de Kijkers OTB. Hotfix voor CQ-4239839
* Uitgeschakelde opruimingsstap wordt handmatig uitgevoerd en wordt gebruikt in particuliere koraalklassen. Hotfix voor CQ-4239729
* De kijker van het beeld produceert een fout en slaagt er niet in om het correcte slimme gewas te tonen. Hotfix voor CQ-4237564
* De legaliteit die onder /etc is ingesteld, lijkt te zijn gebroken en niet te zijn gemigreerd naar locatie onder /conf bij het opslaan. Hotfix voor CQ-4237416
* Regressie in OOB VideoViewer 5.8.x - de kijker breidt iframe aan het recht uit, vandaar het breken van paginalay-out. Hotfix voor CQ-4235465
* (DMS7) de Slimme vertolking URL van het Gewas en bedt knopen in zijn actief voor beelden die niet zijn gepubliceerd. Hotfix voor CQ-4233696
* (DMHybrid) Herstel vorige gewas/roteer eigenschap. Hotfix voor CQ-4239489
* Wanneer het previewing van een video in kaartmening, knevel de spelknoop niet om te pauzeren. Hotfix voor CQ-4238592
* Wanneer het uitvoeren van een Opt-in verbetering, wordt de configuratie YouTube niet bewogen/gekopieerd van zijn oude plaats aan de nieuwe plaats. Hotfix voor CQ-4238590
* DropTwo de Profielen van de Videoverwerking van OOTB AVS zijn vermeld onder de eigenschappen van de Omslag en slechts één bevat bepaalde het coderen. Hotfix voor CQ-4238096
* (DMS7) Slim gewas: Detailweergave: De knoop URL wordt geëtiketteerd de knoop van het Exemplaar voor rendementen. Hotfix voor CQ-4237804
* De kijker stelt de lijstpagina voor blijft leeg zelfs na het uitvoeren van de curl bevelen. Hotfix voor CQ-4243246
* Uitgeschakelde opruimingsstap hanteert handmatige uitvoering en gebruik van privékoraalklassen. Hotfix voor CQ-4239729
* De video pagina van de Details van het Rapport toont geen videoactiva. Hotfix voor CQ-4246208

**DAM - DMServices**

* (DMS7) Cloudconfiguratie: Onbekwaam om nieuwe inhoud met Scene7 na het bijwerken aan SP1 te synchroniseren. Hotfix voor CQ-4244437
* (DMHybrid) de profielen van de Kleur en de catalogusmontages registreren niet in een debug_info=catalogusvraag. Hotfix voor CQ-4242346
* Voeg kleurenprofielen aan de klantenmontages op leveringsservers toe. Hotfix voor CQ-4241818, CQ-4241819
* (DMHybrid) na 6.3&amp;gt; 6.4 verbetering, catalogusmontages worden bewogen aan de onjuiste knoop. Hotfix voor CQ-4239974, CQ-4239975
* (DMHybrid) buggusviewerpresets het manuscript creeert niet de knopen nodig om catalogusmontages te wijzigen. Hotfix voor CQ-4240076
* Wanneer het gebruiken van de drop-down selectie van het &quot;Formaat&quot;en het selecteren van of de formaten van PNG of van JPG, wordt het gedownloade dossier getoond als oververzadigd en donkerder dan de originele activa. Hotfix voor CQ-4240073
* (DMS7) verwijder de MIME afbeelding van het Type: image_x-eps. Hotfix voor CQ-4240394
* (DMS7) Upload parameters voor knockoutachtergrond niet de ipsApiService.log overgaan en zo, werk niet. Hotfix voor CQ-4240686
* Het bevorderen van de Profielen van de Verwerking van het Beeld die in een 6.3 tot 6.4 instantie worden gecreeerd breekt het &quot;Gewas-type&quot;bezit. Hotfix voor CQ-4237739
* (Dynamic Media) Het regelmatig uploaden van bedrijfsmiddelen buiten de map voor het slimme gewas is mislukt. Hotfix voor CQ-4237670
* Pas de profielreservecode voor &quot;Adaptive Video Encoding&quot; profielnaam aan &quot;Adaptive_Video_Encoding&quot; aan. Hotfix voor CQ-4237666
* EmbedXMP het gegeven wordt altijd geplaatst aan &quot;actief&quot;voor de generatieproces van het Ptiff. Hotfix voor CQ-4234498
* De CMYK-afbeeldingsrenditie heeft een onjuiste verzadiging. Hotfix voor CQ-4235470
* De montages van de Server van het beeld worden niet herhaald aan levering terwijl de replicatielogboeken hen succesvol markeren. Hotfix voor CQ-4239480, CQ-4239046
* (DMS7) Kan geen sets maken met oude/nieuwe verwijzingen naar Cloud Configuration. Hotfix voor CQ-4238078
* Scene7 de werkschemastap leest slechts Scene7 in de naam en de beschrijving maar verduidelijkt niet de werkschemastap in het werkschema van de Update DAM. Hotfix voor CQ-4237865

**DAM - Slimme tags**

* Introduceerde Verbeterde Slimme Markeringen. NPR-21951

**Formulieren**

De moeilijke situaties van de Vormen AEM worden geleverd door toe:voegen-op pakketten en andere flardinstallateurs die van de versie worden voorzien. Voor details, zie de Versies van Vormen AEM.

De belangrijkste hoogtepunten voor Vormen AEM zijn:

* De Vormen van AEM introduceert het vermogen [van](https://helpx.adobe.com/experience-manager/6-4/forms/using/transaction-reports-overview.html) transactierapporten om telling van transacties zoals voorgelegde vormen, verwerkte documenten, en teruggegeven documenten op uw plaatsing van Vormen te volgen en te houden AEM. Het verstrekt inzicht in productgebruik en helpt bedrijfsgebruikers digitale verwerkingsvolumes begrijpen.
* Toegelaten steun PDF/UA aan de vormen van XML.
* Toegevoegde allowProxy = waar voor Clientlib **aemfd.ccm.channel.contentpage**
* Bijgewerkte code om gevorderd titelonderzoek te maken zoals bevat eerder dan gelijk.
* Update aan nieuwe versie van de Manager van het Pakket van de Knoop (NPM) op de Ononderbroken Machine van de Integratie.

**Formulierinvoegpakket**

**Backend-integratie**

* Een fout wordt geproduceerd wanneer het verstrekken van ongeldig als waarde aan een facultatief gebied. NPR-24397
* Het aanhalen van WSDL ontbreekt wanneer het element verschillende namespace buiten globale namespace heeft. NPR-24281
* (FDM WSDL) het Krijgen DermisException: Uitzonderde lijstgegevens in het geval van bezitstype serie. NPR-24265
* (FDM WSDL) het Krijgen DermisException: java.lang.Exception: createSOAPParam: Ongeldige Params. NPR-24264
* (FDM Client SDK) Er kunnen geen tests worden uitgevoerd voor pre-/post-processor en aangepaste verzending van acties. Hotfix voor CQ-4238469
* Vast voor kwesties Javadoc in Dermis. Hotfix voor CQ-4244250
* Verbeterde input in de Taal van de Beschrijving van de Diensten van het Web (WSDL). Hotfix voor CQ-4244133
* Het basis authentificatie testen voor WSDL resulteert in verschillende fout voor zelfde configuratie in AEM 6.3 en AEM 6.4. Hotfix voor CQ-4244132
* Verzoek om ValueUtil in cliënt-sdk en javadocs te omvatten. Hotfix voor CQ-4242803
* (FDM Cloud Config) Kan op ZEEP gebaseerde verificatie niet configureren vanuit de cloudconfiguratie. Hotfix voor CQ-4238462
* Dermis - voeg ontbrekende pakketten in JavaDocs toe. Hotfix voor CQ-4242815
* WSDLInvokerParams die in de toe:voegen-op cliëntsdk van Vormen moet worden omvat. NPR-23381: Hotfix voor CQ-4240233

**Aanpassingsvormen**

* De vertolking van het document (IC) zou als transactie moeten worden geregistreerd gebruikend de Dienst van de Opname van de Transactie. Hotfix voor CQ-4245333
* Terwijl het uitvoeren van UAT5, pdf die in verifieert stadium wordt geproduceerd mist een ingang. Hotfix voor CQ-4243184
* Het geval van de test voor diep exemplaar van guideContext. Hotfix voor CQ-4242924
* Het het typegebied van het bewijs mist bij het uitvoeren van UAT3 op recentste promotieserver. Hotfix voor CQ-4243120
* Op geüpgraded server, mist het voorgelegde formulier de waarden van de Staat/van de Provincie/van het Gebied en van het Land die op pre-verbeteringsserver aanwezig waren. Hotfix voor CQ-4241444
* (ExpressionEditor) Fout terwijl het navigeren om stadium tijdens vormvoorlegging te verifiëren. Hotfix voor CQ-4241384
* De waarden ontbreken in verifieert stadium op pre-verbetering en promotieserver voor voorgelegde vorm. Hotfix voor CQ-4241896
* Sluiten en sparen knoop bij de bodem van de pagina werkt niet. Hotfix voor CQ-4240112
* Het aantal van het contact ontbreekt op de promotieopstelling. Hotfix voor CQ-4239870
* Onder `ACTION TAKEN` sectie in het lusje van het Type van Geschil, heeft de &quot;Extra documenten om mijn eis&quot;te steunen extra gebiedType van Bewijs dat &quot;in het wordt opgeslagen. Hotfix voor CQ-4239873
* &quot;Fout in getDataAPI&quot;fout die in het stadium wordt ontmoet verifieertPdf. Hotfix voor CQ-4239865
* Fouten in migratielogboeken voor auteur en publiceren instantie. Hotfix voor CQ-4239365
* Fouten in migratielogboeken voor auteur en publiceren instantie. Hotfix voor CQ-4239635
* Deserialization-fout zoals &quot;Deserialization not allow for class sun.util.calendar.ZoneInfo&quot; in error logt na indiening van een adaptieve vorm aan. Hotfix voor CQ-4240419
* Het gebied van de staat wordt niet bevolkt in Mobiele vormvertolking. Hotfix voor CQ-4240597
* Verwijder verwijzingsgebruik van componenten in malplaatjes uit antipatroonlijst. Hotfix voor CQ-4239217
* HTML5 de Numerieke Doos die als Vloer of Decimaal wordt geplaatst geeft verschillende bevestigingsresultaten in verschillende browsers. NPR-23528: Hotfix voor CQ-4244097
* (Het beeld uploadt) het Beeld dat niet in de voorproef van DOR wordt getoond. Hotfix voor CQ-4243178
* De server van JEE werpt een fout bij het proberen om het AanpassingsVorm met &quot;E-mailPDF&quot;en &quot;omvat gehechtheid&quot;voor te leggen. Hotfix voor CQ-4239894
* De grafiek wordt niet uitgezet bij runtime gebruikend lijst/paneel. Hotfix voor CQ-4240010
* Aanpassingsformulier werkt niet en er is geen wijziging in het aantal transacties als gevolg van het niet indienen van aanvragen. Hotfix voor CQ-4246125
* (De keus van het Beeld) Document van verslagopties is niet zichtbaar. Hotfix voor CQ-4236976
* De redacteur UI van het malplaatje is niet stabiel. Hotfix voor CQ-4241497
* AFs wordt niet getoond gebruikend activa tabel van zijpaneel terwijl getoond gebruikend doorblader optie voor de dialoog van het het bezit van de vormcomponent AEM. Hotfix voor CQ-4236751
* Werkstroom-ID die voor formulierconversie is gegenereerd, moet beschikbaar zijn in gegenereerde adaptieve vorm. Hotfix voor CQ-4240014
* Kan template niet selecteren om een pagina te maken op sites in Direct Upgrade: Levenscyclus tot 6,4-server. Hotfix voor CQ-4241300

**Assemblerservice**

* Het registreren van de transactie in de Diensten van de Assembler. Hotfix voor CQ-4245018, CQ-4245017, CQ-4245016.
* De transactie wordt niet gemeld wanneer de omzetting PDF/A gebruikend DDX wordt gedaan. Hotfix voor CQ-4246039

**Formulierbeheer**

* FM CREEER te sorteren knooplijst alfabetisch. Hotfix voor CQ-4242307

**Formulierportal**

* Tekeningen die zijn opgeslagen op de pre-upgradeserver, worden niet correct geopend op de geüpgraded server. Hotfix voor CQ-4243303
* De update van de versie aan 7.1 voor adobe-formsmanager-kern-module. Hotfix voor CQ-4245753
* Tekeningen die zijn opgeslagen op de pre-upgradeserver, worden niet correct geopend op de geüpgraded server. Hotfix voor CQ-4243303
* De scenario&#39;s van de gehechtheid breken bij het vervangen van/het toevoegen van/het verwijderen van gehechtheid in nieuwe instantie/het zelfde geval van ontwerp. Hotfix voor CQ-4243165
* De telling van ontwerp dat van het vragen van het gegevensbestand wordt teruggewonnen is meer dan de telling van ontwerpen huidig in portaal. Hotfix voor CQ-4241489
* De vormen die op pre-verbeteringsserver worden voorgelegd zijn niet aanwezig op promotieserver. Hotfix voor CQ-4241490
* De vorm die in UI in voorleggingslusje wordt getoond is in Niet voorgelegde staat ondanks succesvol voorleggingsbericht. Hotfix voor CQ-4241487
* guideContext zou moeten worden gevormd door de gebieden diep te kopiëren aangezien guideContext customPropertyMap bevat dat zelf een voorwerp is. Hotfix voor CQ-4240126
* Fout bij het opslaan van een formulier. Hotfix voor CQ-4240763
* De ingang voor bewaarde en voorgelegde vormen wordt bevolkt in crx/de ondanks wij de configuratie van OB die in de Configuratie van het Ontwerp van het Portaal van Vormen en van de Voorlegging wordt gegeven. Hotfix voor CQ-4240726
* (Zoeken en register) De vaste waarde van de geavanceerde zoektitel moet werken als bevat in plaats van gelijk. Hotfix voor CQ-4245499

**Mobiele formulieren**

* Het Gebied van de datum is overlappend in Mobiele Vormen. Hotfix voor CQ-4242256
* De voorlegging van de vorm voor Mobiele Vormen zou als transactie moeten worden geregistreerd gebruikend de Dienst van de Opname van de Transactie. Hotfix voor CQ-4246166
* De indiening van de vorm in Formet zou als transactie moeten worden geregistreerd gebruikend de Dienst van de Opname van de Transactie. Hotfix voor CQ-4246165

**AEM Forms App**

* (Windows App) Kan het formulier niet teruggeven. Hotfix voor CQ-4238005

**Workflow OSGI**

* Transactielogboek in Werkstroom Toewijzen Taak. Hotfix voor CQ-4244440
* (FDM Stap) Onbekwaam om waarden van werkschemameta-gegevens te gebruiken wanneer een Assign stap van de Taak tussen de processtap en fdm stap wordt opgenomen. Hotfix voor CQ-4241472
* De delegatie van wijst taak toe werkt niet in de Integratie van Vormen in Werkschema&#39;s OSGI. NPR-23709: Hotfix voor CQ-4243700
* (De ModelRedacteur van het Werkschema) Sommige Modellen van het Werkschema zijn niet editable via de ClassicUI modelredacteur WF. Hotfix voor CQ-4241151

**MultiChannel-document**

* Het gebied van de datum in Malplaatje overlappt subform in de creatie van IC. Hotfix voor CQ-4240110
* De kopbal zou niet moeten worden toegestaan om worden geschrapt of worden bewogen naar boven en naar onder in het Webkanaal van IC creatie. Hotfix voor CQ-4243358
* (Redacteur van IC) Standaard rijen die aan 1 voor de componenten van de Lijst moeten worden geplaatst. Hotfix voor CQ-4244848
* Het Gebied van het doel zichtbaar te blijven zelfs nadat de inhoud is gesleept en op het gelaten vallen. Hotfix voor CQ-4244534
* Het kanaal van het Web erkent lussenruimte in de Fragmenten van het Document van de Tekst niet. Hotfix voor CQ-4244481
* (Het kanaal van de Druk) de renditie van het Document (IC) zou als transactie moeten worden geregistreerd gebruikend de Dienst van de Opname van de Transactie. Hotfix voor CQ-4245335
* (Het kanaal van het Web) de renditie van het Document (IC) zou als transactie moeten worden geregistreerd gebruikend de Dienst van de Opname van de Transactie. Hotfix voor CQ-4245334
* Het Onderzoek van de Container van het document of het Onderzoek van de Boom van de Gegevens Model moet aan het de filteronderzoek van Activa worden verenigd. Hotfix voor CQ-4242305
* (Het Fragment van het Document) het inkeping bezit indent de tekst door hoeveel eenheden niet kunnen worden begrepen. Hotfix voor CQ-4241082, CQ-4240643
* (De Redacteur van IC) het Edit pictogram van het Fragment op de tegel van het documentfragment dat onder het lusje van Activa wordt vermeld is niet zeer gemakkelijk te ontdekken en te begrijpen. Hotfix voor CQ-4241047
* Sta anonieme toegang tot de Anonieme ontoegankelijke de cliëntbibliotheek van IC toe. Hotfix voor CQ-4245588
* (Het kanaal van het Web) de Gegevens lossen niet in om het even welke lijst in Webvoorproef op en getoond als leeg. Hotfix voor CQ-4244476
* De kopballen van de lijst worden getoond als variabelen in Webkanaal op auto-generatie. Hotfix voor CQ-4244242
* (De Redacteur van IC) de Inhoud van een Fragment van het Document dat in IC wordt gebruikt zou automatisch moeten worden opnieuw gerangschikt om de breedte van het Gebied van het Doel te passen. Hotfix voor CQ-4244094
* De kanaalnaam die in de centrumbovenkant wordt getoond moet of de titel van IC voor WEB/DRUKTE verenigbaar zijn. Hotfix voor CQ-4242498
* Het de objecten van de redacteur van de tekst het paneel van Gegevens zou van slechts hoogste niveauentiteiten, Hotfix voor CQ-4244121 moeten een lijst maken
* De standaard naam wordt niet toegewezen wanneer het toevoegen van een nieuwe component in redacteur. Hotfix voor CQ-4244691
* Het toevoegen van configuratie Colspan in alle componenten van het Webkanaal. Hotfix voor CQ-4244946
* Het bezit van de Breedte van de Lijst van het Fragment van de lay-out wordt teruggesteld en geëerd in het Kanaal van de Druk van de Brief of van de Communicatie van de Klant niet. Hotfix voor CQ-4241574

**Correspondentiebeheer**

* De titels die uit brievenmalplaatje worden verwijderd na het uitgeven van een tekstactiva die placeholders bevatten. NPR-24196
* Het XDP dossier, wanneer geupload en gebruikt als lay-out voor brievenmalplaatjes, ontbreekt aan voorproef of geeft de malplaatjes uit. NPR-24143: Hotfix voor CQ-4244407
* De selectie van de taak wordt geselecteerd door gebrek in lijstfragment. Hotfix voor CQ-4240097
* De redacteur van de voorwaarde - de Veelvoudige resultaatevaluatie zou door gebrek moeten worden toegelaten. Hotfix voor CQ-4240096
* Het beeld wanneer geschrapt van Lijst toont nog beeld in voorproef. Hotfix voor CQ-4239909
* De regel die op de voorwaardenmodule is ingesteld, is ingesteld als &#39;Standaard&#39; voor alle module(s). Hotfix voor CQ-4239878
* De verwezenlijking van het Woordenboek van gegevens ontbreekt met de &quot;Onbekende uitzondering JCR&quot;fout. Hotfix voor CQ-4244122
* Kranten in 6.3 Inhoud JavaDocs. Hotfix voor CQ-4213586

**Forms JEE-installateur**

**Kern**

* (De Werkruimte van HTML) het Volgen details missen voor toepassingen met haakjes symbool in de naam. NPR-23402

**PDFG-service**

* Het registreren van de transactie in diensten PDFG. Hotfix voor CQ-4244951, CQ-4244586
* Het verminderen van PDFs door doopvonten selectief unembedding via enige API vraag. NPR-23287
* PDFG de kwestie van de configuratieneupdate op verbetering AEM. Hotfix voor CQ-4241176
* Het registreren van de transactie in de Dienst PDFUtility. Hotfix voor CQ-4245014

**Procesbeheer**

* (De Werkruimte van HTML) de Startpoints van het proces worden niet gesorteerd in alfanumerieke orde. Hotfix voor CQ-4239629
* (De werkruimte van HTML) bereidt gegevensvraag voor die tweemaal komt wanneer het ontwerp de eerste keer wordt geopend. Hotfix voor CQ-4243280
* (De Werkruimte van HTML) bereidt het proces van Gegevens voor wordt teweeggebracht terwijl het sluiten van een vorm. Hotfix voor CQ-4239456
* De ruimte van het werk hangt wanneer overspannen tussen twee taken. Hotfix voor CQ-4237125

**Werkbank**

* Beheer het Profiel van de Actie voorbereidingen ontbreekt het gegevensproces wanneer het gebrek procesconfiguratie teruggeeft aan HTML wordt geplaatst. Hotfix voor CQ-4244292

**Forms Designer**

* Voeg steun PDF/UA aan de vormen van XML toe die via de Dienst van de Ontwerper en van de Output worden geproduceerd. NPR-23022
* de gealigneerde Hyperlinks die in Ontwerper worden bepaald worden niet geëtiketteerd noch hebben zij afwisselende teksten wanneer bewaard als PDF van Ontwerper. NPR-23023

**Inclusief functiepakketten**

**Assets**

* Toegevoegd de capaciteit voor Verbeterde Slimme Markeringen. Voor meer informatie, zie [Verbeterde Slimme Markeringen](https://helpx.adobe.com/experience-manager/6-4/assets/using/enhanced-smart-tags.html). NPR-21951: Hotfix voor CQ-4234883
* Introduceerde AEM-bedrijfsmiddelenverwijzingen in InDesign. Voor meer informatie, zie de Verwijzingen van de Activa [AEM in InDesign](/help/assets/managing-linked-subassets.md). NPR-23386

**Sites**

* (De Auteurs van de Pagina) de verhogingen van de Redacteur van het Beeld. Voor meer informatie, zie de Redacteur [van het](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/image-editor.html)Beeld. NPR-24267: Hotfix voor CQ-4245502

**SGA-bundels en -inhoud**

In de volgende tekst wordt de lijst van OSGI-bundels en -inhoudspakketten in het GVB opgenomen.

Lijst van OSGi-bundels opgenomen in AEM 6.4.1.0

[Bestand ophalen](assets/6_4_1_0_bundle-list.txt)

Lijst van inhoud Pakketten in AEM 6.4.1.0

[Bestand ophalen](assets/6_4_1_0_content-package-list.txt)

### Installeer 6.4.8.0 {#install}

#### Installatievereisten {#setup-requirements}

<!--

>[!NOTE]
>
>For successful installation of AEM 6.4.6.0 on the instance, it is strongly recommended to upgrade the version of com.adobe.granite.oak.s3connector to 1.8.4 for the customers who are on the older version of s3 connector.
>The process of upgrading the com.adobe.granite.oak.s3connector is available at [https://helpx.adobe.com/in/experience-manager/6-4/sites/deploying/using/data-store-config.html](https://helpx.adobe.com/in/experience-manager/6-4/sites/deploying/using/data-store-config.html).
>Download the latest version of com.adobe.granite.oak.s3connector from: [https://repo.adobe.com/nexus/content/groups/public/com/adobe/granite/com.adobe.granite.oak.s3connector/](https://repo.adobe.com/nexus/content/groups/public/com/adobe/granite/com.adobe.granite.oak.s3connector/)

-->

>[!CAUTION]
>
>Voor klanten met de Packs van de Eigenschap die op AEM 6.4 worden geïnstalleerd. De facultatieve die Pakken van de Eigenschap door Adobe worden verstrekt hebben gebiedsdelen op de versieversie en de dienstpak dat. Als u een Feature Pack hebt geïnstalleerd, neemt u contact op met het AEM-team van de klantenservice om de compatibiliteit van deze functiepakketten met dit servicepakket voor AEM 6.4 te controleren.

* AEM 6.4.8.0 vereist AEM 6.4. Ga naar de [upgradedocumentatie](../sites-deploying/upgrade.md) voor gedetailleerde instructies.
* De download van het Pak van de Dienst is beschikbaar op het Aandeel van het Pakket van Adobe, dat u tot van AEM 6.4 instantie kunt direct toegang hebben.
* Voor een plaatsing met MongoDB en veelvoudige instanties, installeer AEM 6.4.8.0 op één van de instanties van de Auteur gebruikend de Manager van het Pakket.
* Alvorens het de dienstpak te installeren, zorg ervoor om een momentopname of een verse steun van uw AEM instantie te hebben.
* Start de installatie opnieuw vóór de installatie. Terwijl dat slechts nodig is wanneer de instantie nog op updatewijze (en dit is het geval wanneer de instantie enkel van een vroegere versie werd bijgewerkt) is, wordt het over het algemeen geadviseerd als de instantie voor langere periode liep.

>[!NOTE]
>
>Adobe adviseert niet verwijderend of desinstalleert het pakket AEM 6.4.8.0.

### Installeer het Service Pack via Package Share {#install-the-service-pack-via-package-share}

Voer de volgende stappen uit om het Service Pack op een bestaande AEM 6.4 instantie te installeren:

1. Meld u aan bij het Pakket delen binnen AEM of rechtstreeks vanaf uw browser en download het AEM 6.4.8.0-pakket.

   (zoek naar &quot;AEM-6.4.8.0&quot;om het te vinden)
1. Installeer het gedownloade pakket met Package Manager.

>[!NOTE]
>
>**De dialoog op de Manager UI van het Pakket komt soms onvroeg tijdens installatie van 6.4.8.0 weg**
>
>Daarom wordt het geadviseerd om op foutenlogboeken te wachten om te stabiliseren alvorens tot de instantie toegang te hebben. De gebruiker moet op specifieke logboeken met betrekking tot de desinstallatie van updaterbundel wachten alvorens wordt verzekerd dat de installaties succesvol zijn. Het gebeurt over het algemeen op Safari maar kan met tussenpozen op om het even welke browser gebeuren.

### Automatische installatie {#auto-installation}

Er zijn twee manieren om AEM 6.4.8.0 in een lopende instantie automatisch te installeren:

A. Plaats de verpakking in ...*/crx-quickstart/install* omslag terwijl de server loopt. Het pakket wordt automatisch geïnstalleerd.

B. Gebruik [HTTP API van de Manager](https://docs.adobe.com/content/docs/en/crx/2-3/how_to/package_manager.html) van het Pakket - zorg ervoor u gebruikt `cmd=install&recursive=true` - zodat is het genestelde pakket geïnstalleerd.

>[!NOTE]
>
>AEM 6.4.8.0 steunt geen installatie Van Bootstrap.

### Installatie valideren {#validate-install}

1. De pagina van de Informatie van het Product (*/systeem/console/productinfo *) zou de bijgewerkte versiereeks &quot;de Manager van de Ervaring van Adobe, Versie 6.4.8.0&quot;onder Geïnstalleerde Producten nu moeten tonen.
1. Alle bundels OSGI zijn of ACTIEF of FRAGMENT in de Console OSGI (de Console van het Web van het Gebruik: /systeem/console/bundels).
1. De OSGI-bundel org.apache.jackrabbit.oak-core is op versie 1.8.17 of hoger (Web Console gebruiken: /systeem/console/bundels).

Zie [Technische vereisten](../sites-deploying/technical-requirements.md)voor het bepalen van het gecertificeerde platform voor het uitvoeren van deze release van AEM-sites en -bedrijfsmiddelen.

>[!Nprijsopgave]
>Bij de succesvolle installatie van het pakket wordt een >informatief bericht weergegeven dat aangeeft dat de inhoud >pakket is geïnstalleerd, zoals **&quot;Content Package AEM-6.4-Service-Pack-7 is geïnstalleerd.&quot;**

### Dynamische mediumweergaven bijwerken (5.10.1) {#update-dynamic-media-viewers}

<p id="Dynamic">AEM 6.4.8.0 bevat nieuwe versie van de Dynamische kijkers van Media (5.10.1) die controle voor dubbele namen op de Vooraf ingestelde pagina van het Beeld toelaat. De dynamische klanten van Media worden geadviseerd om het volgende bevel in werking te stellen om uit de dooskijker te brengen vooraf instelt aan een bijgewerkte staat.

`curl -u admin:admin http://localhost:4502/libs/settings/dam/dm/presets/viewer.pushviewerpresets`

die nieuwe kijker zal kopiëren vooraf instelt aan /conf plaats.

### AEM-formulieren toevoegen aan pakket installeren {#install-aem-forms-add-on-package}

#### AEM-formulieren toevoegen {#installaemformsaddon}

>[!NOTE]
>
>Sla over als u geen AEM-formulieren gebruikt. De montages in Vormen AEM worden geleverd door een afzonderlijk toe:voegen-op pakket.

>[!NOTE]
>
>AEM 6.4.8.0 omvat een nieuwe versie van het compatibiliteitspakket van de Vormen van [AEM](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/compatpack/AEM-FORMS-6.4.7.0-COMPAT). Als u een oudere versie van het Pakket van de Verenigbaarheid van Vormen AEM en het bijwerken aan AEM 6.4.8.0 gebruikt, installeer de recentste versie van het pakket van de Vormen AEM verenigbaarheidspakket na installatie van het Pakket van Vormen toe:voegen-op Pakket.

1. Zorg ervoor dat u het AEM Service Pack hebt geïnstalleerd.
1. Download het overeenkomstige vormenpakket toe:voegen-op dat bij de versies van de Vormen van [AEM voor uw werkend systeem wordt vermeld](https://helpx.adobe.com/aem-forms/kb/aem-forms-releases.html) .
1. Installeer het pakket van de vormen toe:voegen-op zoals beschreven in het [Installeren van AEM vormenpakketten](https://helpx.adobe.com/experience-manager/6-4/forms/using/installing-configuring-aem-forms-osgi.html#InstallAEMFormsaddonpackage)toe:voegen-op.

### Installeren van AEM Forms JEE-installateur {#install-aem-forms-jee-installer}

>[!NOTE]
>
>Sla over als u geen AEM-formulieren gebruikt op JEE. De montages in de Vormen JEE van AEM worden geleverd door een afzonderlijke installateur.

Voor informatie over het installeren van de cumulatieve installateur voor JEE van Vormen AEM en post-plaatsingsconfiguratie, zie Installateur 0015 van het Flard van de Vormen JEE van [AEMVormen](https://helpx.adobe.com/aem-forms/quick-fixes/6-4/jee-patch-0015.html).

#### Voor NPR-21268 vereiste configuratiemontages {#configuration-settings-required-for-npr}

Als u (oude) (klassieke) UI gebruikt en meta-gegevensmalplaatjes gebruikend het hebt gecreeerd, volg de stappen om het manuscript in werking te stellen JMX om hen te bewaren -

1. Ga naar /system/console/jmx.
1. Klik op &quot;Migreer de Malplaatjes van Meta-gegevens.&quot;
1. Klik op &quot;migrateMetadataTemplatesAtPath&quot;en lever de omslagweg waaronder u de meta-gegevensmalplaatjes wilt worden bewaard.

#### Voor NPR-24536 vereiste configuratiemontages {#configuration-settings-required-for-npr-1}

De telling voor gedeelde Rij verfrist zich niet, door gebrek, voor andere gebruikers wanneer een gebruiker een taak eist. Daarvoor hebben we een nieuw onroerend goed geïntroduceerd. Volg de stappen hieronder om dit bezit op uw instantie te vormen AEM:

1. Ga naar Beheer UI -> Services -> Werkruimte -> Wereldwijd beheer.
1. Globale instellingen exporteren.
1. In het gedownloade dossier van XML, voeg de markering &lt;client_takenPollingInterval>10&lt;/client_takenPollingInterval> hier toe, is 10 de voorbeeldwaarde in seconden. U kunt het dienovereenkomstig wijzigen.
1. Sla het bestand op.
1. Ga terug naar Beheer UI -> Services -> Werkruimte -> Wereldwijd beheer.
1. Voer het xmldossier in de Globale sectie van Montages van de Invoer in.
1. U kunt nu logout van het systeem en login opnieuw.
1. De telling voor gedeelde rij begint voor andere gebruikers in de werkruimte te verfrissen.
1. Om de opiniepeiling uit te zetten, verander de waarde in 0 en voer opnieuw het dossier van XML in.

### Uber Jar {#uber-jar}

Uber Jar voor AEM 6.4.8.0 is beschikbaar in de Openbare Geweven bewaarplaats [van](https://repo.adobe.com/nexus/content/groups/public/com/adobe/aem/uber-jar/6.4.8/)Adobe.

Om de Jar van Uber in een Maven project te gebruiken, verwijs naar het artikel, [hoe te om de jar](../sites-developing/ht-projects-maven.md) van Uber te gebruiken en het volgende gebiedsdeel in uw projectPOM te omvatten:

```shell
<dependency>
      <code>com.adobe.aem</groupId>
      <artifactId>uber-jar</artifactId>
      <version>6.4.8.0</version>
      <classifier>apis</classifier>
      <scope>provided</scope>
</dependency>
```

### Verwijderde/afgekeurde functies {#removed-deprecated-features}

Deze sectie maakt een lijst van eigenschappen en mogelijkheden die uit AEM 6.4 zijn verwijderd of afgekeurd.

| Gebied | Functie | Vervanging | Versie |
|---|---|---|---|
| Assets | Actie voor tags beheren voor submiddelen | Geen vervanging | AEM 6.4.2.0 |
| Activa en Adobe Creative Cloud-integratie | [AEM aan de omslag van de Wolk van de Creative](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/creative-cloud.html) werd geïntroduceerd in AEM 6.2 als manier om creatieve gebruikers toegang tot activa van AEM te geven. Een nieuw vermogen dat in de toepassing van de Wolk van de Creatieve, de Verbinding van de Activa van Adobe wordt vrijgegeven, verstrekt een veel betere gebruikerservaring en een krachtigere toegang tot activa van AEM direct van binnenuit Photoshop, InDesign, en Illustrator. Adobe zal geen verdere verhogingen aan de omslag maken delend vermogen. Terwijl de eigenschap in AEM inbegrepen is, worden de klanten geadviseerd om de vervanging te gebruiken. | Adobe Asset Link of desktop-app. Voor meer informatie, zie [AEM het de integratieartikel](/help/assets/aem-cc-integration-best-practices.md) van de Wolk Creative. | AEM 6.4.4.0 |

### Bekende problemen {#known-issues}

* De volgende fouten en waarschuwingen kunnen tijdens de installatie worden weergegeven:

   * Fouten als gevolg van het opnieuw opstarten van de repository komen de instantie van de component en de nietig verklaarde fabriek van de Service voor.

      * com.day.cq.cq-personalisatie \[com.day.cq.personalization.impl.DefaultProfileProvider(938)\] Kan componenteninstantie niet tot stand brengen wegens het niet binden van verwijzingsprofielManager
      * org.apache.sling.commons.planner FrameworkEvent ERROR (org.osgi.framework.ServiceException: De fabriek van de dienst is ongeldig teruggekeerd. (Onderdeel: com.day.cq.tagging.impl.TagGarbageCollector (1687))
   * `com.adobe.cq.social.cq-social-jcr-provider bundle com.adobe.cq.social.cq-social-jcr-provider:1.3.5 (395)[com.adobe.cq.social.provider.jcr.impl.SpiSocialJcrResourceProviderImpl(2302)]` : Time-out die wacht op reg-wijziging om niet-geregistreerd te voltooien.
   * `com.adobe.granite.maintenance.impl.TaskScheduler` Geen onderhoudsvensters gevonden bij graniet/exploitatie/onderhoud
   * `com.adobe.cq.com.adobe.cq.ui.commons bundle com.adobe.cq.com.adobe.cq.ui.commons:1.2.28 (204)[com.adobe.cq.ui.wcm.commons.internal.servlets.rte.RTEFilterServletFactory(573)]`: De methode unbindAm heeft een uitzondering (java.lang.IllegalStateException geworpen: Service al niet geregistreerd).
Deze fouten vereisen geen actie aangezien zij geen invloed hebben op uw instantie AEM.


### Opgeloste problemen {#resolved-issues}

**AEM 6.4.4.0**

* Geen middel gevonden fout wordt waargenomen bij het invoeren/het uitvoeren van meta-gegevens. kw-4253263
* Kan geen afbeeldingsonderdelen en pagina-eigenschappen bewerken nadat u boven 6.4.2.0 de 6.4.3.0 hebt toegepast. CQ-4260316 &amp; CQ-4260441Om dit probleem te kunnen oplossen:
   * Ga naar Package Manager
   * Installeer pakket &quot;cq-ui-wcm-admin-content-1.0.1004.zip&quot; opnieuw
   * Alle JSP&#39;s opnieuw compileren `(http://<AEM HOST>:<AEM PORT/system/console/slingjsp)` OF de instantie opnieuw opstarten.

### OSGi-bundels en Content Packages zijn inbegrepen {#osgi-bundles-and-content-packages-included}

De volgende tekstdocumenten maken een lijst van de bundels OSGi en de Pakketten van de Inhoud inbegrepen in AEM 6.4.8.0.

Lijst van OSGi-bundels opgenomen in AEM 6.4.8.0

[Bestand ophalen](assets/6.4.8.0_osgi_bundles.txt)

Lijst van de Inhoud Pakketten inbegrepen in AEM 6.4.8.0

[Bestand ophalen](assets/6.4.8.0_content_packages.txt)

### Nuttige middelen {#helpful-resources}

* [AEM 6.4 releaseaantekeningen](../release-notes/release-notes.md)
* [AEM-productpagina](https://www.adobe.com/solutions/web-experience-management.html)
* [AEM 6.4-documentatie](https://helpx.adobe.com/support/experience-manager/6-4.html)
* Abonneer u op [Adobe prioritaire productupdates](https://www.adobe.com/subscription/priority-product-update.html)

### Beperkte locaties {#restricted-sites-new}

Deze plaatsen zijn slechts beschikbaar aan klanten. Als u een klant bent en toegang nodig hebt, gelieve uw de rekeningsmanager van Adobe te contacteren.

* [Download van product op license.adobe.com](https://licensing.adobe.com/)
* [Contact opnemen met Customer Support](https://daycare.day.com/)
