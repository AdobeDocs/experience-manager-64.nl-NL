---
title: AEM 6.4 Opmerkingen bij de release Service Pack
seo-title: AEM 6.4 Opmerkingen bij de release Service Pack
description: Opmerkingen bij de release specifiek voor Adobe Experience Manager 6.4 Service Packs.
seo-description: Opmerkingen bij de release specifiek voor Adobe Experience Manager 6.4 Service Packs.
uuid: 49a710a8-7cd5-47de-9a96-7af7f3c00dfc
contentOwner: dekalra
products: SG_EXPERIENCEMANAGER/6.4
topic-tags: release-notes
discoiquuid: 93067308-e275-490f-8d78-ae79e046059c
translation-type: tm+mt
source-git-commit: b9dffdda37992f3a9f34953b8dd391d6f6361ceb
workflow-type: tm+mt
source-wordcount: '21617'
ht-degree: 0%

---


# AEM 6.4 Opmerkingen bij de release Service Pack {#aem-service-pack-release-notes}

## Informatie opheffen {#release-information}

| Producten | **Adobe Experience Manager (AEM) 6.4** |
|---|---|
| Versie | 6.4.8.0. |
| Type | Service Pack-release |
| Date | 5 maart 2020 |
| URL downloaden | AEM 6.4.8.0 op [Softwaredistributie](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq640/servicepack/aem-service-pkg-6.4.8.zip) |

## Wat is inbegrepen in AEM 6.4.8.0 {#what-s-included-in-aem}

AEM 6.4.8.0 is een belangrijke update die nieuwe eigenschappen omvat, de belangrijkste klant verzocht om verbeteringen en prestaties, stabiliteit, veiligheidsverbeteringen, die sinds de algemene beschikbaarheid van AEM 6.4 in **April 2018 worden vrijgegeven.**

Het is ook cumulatief, wat betekent dat 6.4.8.0 alle AEM 6.4 de dienstpakken omvat die vóór het worden vrijgegeven.

Enkele belangrijke hoogtepunten van deze service pack-release zijn:

* De ingebouwde opslagplaats (Apache Jackrabbit Oak) wordt bijgewerkt naar versie 1.8.20.

* De functionaliteit voor tekstomloop wordt ondersteund voor Japanse websites in WCM-RTE.

* Verwerking van Word-einden en regeleinden wordt ondersteund voor Japanse websites.

* Extra ondersteuning voor het gebruik van de BUNSETSU-methode voor het afbreken van de Japanse taalzin en -regels op de juiste posities.

* CCR UI voor brievenbeheer steunt nu decimale waarden voor Duitse scène.

* Integratie van formuliergegevensmodellen met SOAP-webservice ondersteunt nu keuzegroepen of kenmerken voor elementen.

* AEM Assets is nu geconfigureerd met Brand Portal via [!DNL Adobe I/O].

* De jQuery-versie die in ContextHub is gebundeld, is bijgewerkt naar 3.2.1.

## Lijst met wijzigingen {#list-of-changes}

### Sites {#sites}

* Wanneer een URL van een AEM Sites-pagina een dubbele punt of percentagesymbool bevat, reageert de onderliggende browser niet meer en geven CPU-cycli een punt weer (NPR-32368, NPR-31917).
* Wanneer een AEM Sites-pagina wordt geopend voor bewerking en een component wordt gekopieerd, blijft de plakhandeling niet beschikbaar voor bepaalde plaatsaanduidingen (NPR-32328).
* Aanvraag tot activeringswerkstroom omvat geen middelen waarnaar wordt verwezen (NPR-32304).
* Wanneer een blauwdruk wordt gecreeerd, als het aantal verslagen meer dan 80 is, slechts worden de eerste 80 verslagen getoond. Blauwdruk geeft lege regels weer voor de rest van de records (NPR-32058).
* Gebruikers mogen een inhoudsfragment opslaan zonder informatie op te geven in de vereiste velden (NPR-31988).
* Automatische navigatie werkt niet voor weg die in een Component van het Fragment van de Ervaring van de Kern (NPR-31921) wordt gevormd.
* Als u het type van een tabelcel wijzigt in de Rich Text Editor (RTE), treedt de onderstaande fout op:
   `Error: No common ancestor found, cannot continue` (NPR-31916).
* Wanneer inhoud binnen dezelfde map wordt verplaatst, is de optie Pagina verplaatsen uitgeschakeld (NPR-31841).
* Toegevoegde ondersteuning voor het verdelen van Japanse taalzinnen met behulp van de BUNSETSU-methode en het afbreken van regels op de juiste positie (NPR-31836).
* Als u een hyperlink bewerkt in de Rich Text Editor (RTE), wordt het net geselecteerde pad niet opgeslagen (NPR-31659).
* Wanneer u een component met meerdere velden verwijdert en de verwijdering ongedaan maakt, wordt de component hersteld, maar worden de gegevens niet hersteld (NPR-31617).

### Assets {#assets}

* Een map zonder naam wordt gemaakt in SPS (Scene7 Publishing System) en een element van de ene map naar de andere verplaatst in Experience Manager met de Dynamic Media Scene7-configuratie (NPR-32440).

* Op de pagina met middelendetails van PDF-bestanden worden geen actieknoppen weergegeven in Experience Manager die wordt uitgevoerd in de Dynamic Media Scene7-modus (NPR-32316).

* Elementen en video-uitvoeringen kunnen niet worden verwijderd (NPR-32213).

* Het kalenderpictogram voor activering dat is gepland, wordt niet weergegeven in de kolom Status (in de klassieke gebruikersinterface van de DAM-lijst met activa) voor elementen waarvan de activering voor een latere datum en tijd is gepland (NPR-32198).

* De relatie tussen activa wordt overschreven wanneer activa verband houden met meer dan één activa die gebruikmaken van Overige (NPR-32196).

* Met de knop Opslaan wordt de Remote Set niet geïmporteerd als de gebruiker geen wijzigingen heeft aangebracht in de Set Editor in Dynamic Media Client (NPR-32178).

* Het opnemen van PSD-elementen leidt tot CPU-spike en tot een niet-responsieve Experience Manager Author-instantie (NPR-32165).

* Er is een uitzondering van het type Out of Memory waargenomen wanneer een groot ZIP-bestand wordt geüpload in Experience Manager DAM (NPR-32155).

* URL&#39;s met versiegeschiedenis worden weergegeven onder Veld Verwijzing naar op de eigenschappenpagina voor elementen (NPR-31889).

* Unpublish from Brand Portal, on Manage Publication page, mislukt voor submappen van een gepubliceerde map (NPR-31835).

* Dynamic Media-videocodering kan niet worden geüpload wanneer de Scene7 Cloud Configuration in een privémap `/conf` wordt geplaatst in plaats van `/conf/global` (NPR-31779).

* Afbeelding wordt niet weergegeven op de tijdlijn nadat annotaties zijn toegevoegd, bij Experience Manager die wordt uitgevoerd in de Dynamic Media Scene7-uitvoeringsmodus (NPR-31754).

* ZIP-bestand dat is gedownload van DAM, kan niet worden geopend met WinZip (NPR-31745).

### Integrations {#integrations-6480}

* De **Company** en **Reporting** vervolgkeuzemenu&#39;s van de Reeks worden verborgen zodra **Rapporterende Bron** wordt geselecteerd terwijl het vormen Adobe Analytics in de clouddiensten van de Experience Manager (NPR-31729).

* Adobe Campaign-eigenschappen worden niet opgeschoond wanneer een taalkopie van een nieuwsbrief die aan een Adobe Campaign is gekoppeld, wordt gemaakt, terwijl opruimen plaatsvindt wanneer een nieuwsbrief die aan een Adobe Campaign is gekoppeld, wordt gekopieerd of geplakt (NPR-32540).

* ReportSuitesServlet is kwetsbaar voor SSRF (NPR-32161).

### Verschuiven {#sling-6480}

* Niet-deterministische schaduweffecten van bronobservatie werken niet (CQ-4286466).

### Projecten {#projects-6480}

* De knop Maken is niet zichtbaar voor de gebruiker, zelfs niet als de gebruiker toestemming heeft om een project te maken in de submap (NPR-31831).

* De functionaliteit om tussen de Mening van de Kaart, de Mening van de Lijst en de Mening van de Kalender te schakelen werkt niet na het selecteren van de mening van de Kalender in Projecten (NPR-31829).

### Vertaling {#translation-6480}

* Bij het ontwerpen van vertaalprojecten voor meerdere talen wordt het project alleen voor sommige talen gegenereerd in plaats van voor alle en er wordt een fout (de resourceresolver is al gesloten) waargenomen in het logbestand (NPR-32212).

### WCM-MSM {#wcm-msm-6480}

* Machtigingsproblemen leiden tot het weergeven van fouten tijdens het verplaatsen van pagina&#39;s binnen een blauwdruk (NPR-32610).

### WCM-pagina-editor {#wcm-page-editor-6480}

* De browser reageert niet meer terwijl wordt geprobeerd een component toe te voegen aan een pagina met een specifieke URL-indeling (NPR-32368, NPR-31917).

### WCM-Admin UI {#wcm-admin-ui-6480}

* Publicatie beheren omvat geen middelen waarnaar wordt verwezen in de activeringswerkstroom (NPR-32304).

### Gemeenschappen {#communities}

* Kan de groepminiatuurafbeelding voor groepen niet bijwerken (NPR-32603).

### Merk-portal {#brand-portal}

* Het schema voor metagegevens van Unpublish in AEM Assets vult een foutbericht, hoewel het schema op de achtergrond wordt verwijderd (CQ-4286871).

### Foundation-UI {#foundations-ui-6480}

* Ongeldige tekens worden weergegeven in de URL die is toegevoegd aan een component Button (NPR-32684).

### Forms {#forms}

>[!NOTE]
>
>AEM Service Pack bevat geen oplossingen voor AEM Forms. Ze worden geleverd met een apart Forms-add-onpakket. Daarnaast wordt een cumulatief installatieprogramma uitgebracht dat oplossingen voor AEM Forms op JEE bevat. Zie [AEM Forms-invoegtoepassing installeren](#install-aem-forms-add-on-package) en [AEM Forms JEE-installatieprogramma installeren](#install-aem-forms-jee-installer) voor meer informatie.

* Designer: Als de coderingsoptie is ingeschakeld, verdwijnt de subformulierrand in de gegenereerde PDF-uitvoer (NPR-32546, NPR-32322).

* Designer: Als een tabel samengevoegde cellen bevat, mislukt de toegankelijkheidstest voor het PDF-uitvoerbestand dat is geconverteerd van een XDP-formulier met de uitvoerservice (NPR-32079).

* Documentbeveiliging: Een beveiligd PDF-bestand kan niet offline worden geopend met de optie DisableGlobalOfflineSynchronizationData ingesteld op True (NPR-32080).

* Documentbeveiliging: Problemen bij het openen van een beveiligd PDF-bestand na een upgrade van ES4 naar AEM 6.3 (NPR-32170).

* Documentservices: Er wordt een foutbericht weergegeven wanneer u probeert een PDF-bestand te converteren naar een PDF/A-document met de methode voor conversie naar PDF/A (NPR-32663).

* Documentservices: Er wordt een uitzondering weergegeven bij het toepassen van de service Reader-extensies op een PDF-bestand (NPR-32639).

* Documentservices: Er wordt een foutbericht weergegeven tijdens het samenstellen en converteren van XDP-bestanden naar PDF-bestanden (NPR-31821).

* Analyses geven geen geschikte resultaten weer bij het verzenden of verlaten van formulieren op een sitepagina (NPR-31359).

### Hotfixes en de Pakken van de Eigenschap inbegrepen in vorige Packs {#hotfixes-and-feature-packs-included-in-previous-service-packs}

#### AEM 6.4.7.0 {#experience-manager-6470}

AEM 6.4.7.0 is een belangrijke update die prestaties, stabiliteit, veiligheid en belangrijkste klantenfixes en verhogingen omvat die sinds de algemene beschikbaarheid van AEM 6.4 in **April 2018 worden vrijgegeven.**

Het is ook cumulatief, wat betekent dat 6.4.7.0 alle AEM 6.4 de dienstpakken voorafgaand aan de versie omvat.

Enkele belangrijke hooglichten van AEM 6.4.7.0 zijn:

* De ingebouwde opslagplaats (Apache Jackrabbit Oak) wordt bijgewerkt naar versie 1.8.17.
* Toegevoegde ondersteuning voor het instellen van een versie van een sitepagina terwijl deze werd verwijderd.
* De nieuwe kolom voor gecreeerde datum, die sorteerbaar is, is toegevoegd in **DAM lijst** mening en op activa onderzoeksresultaten in **Lijst** mening (NPR-31311).
* Asset sorting based on **Name** column has been allowed in **List** view.
* Time-out voor batchgrootte en workflowstap voor opnieuw verwerken en batchuploaden zijn nu configureerbaar vanuit de gebruikersinterface in Dynamic Media.
* `pdfBrochure` is geplaatst aan vals in Scene 7 wolkenconfiguratie, om geheugen bij IPS te bewaren.

##### Elementen {#assets-6470}

**Verbeteringen voor producten**

* De exportversie van het API-pakket `package com.day.cq.dam.handler.standard.msoffice` wordt ondersteund door `dam-handler`-bundel wordt bijgewerkt naar 6.0.0 (CQ-4279059).
Als u het pakket `com.day.cq.dam.handler.standard.msoffice` in uw douanetoepassing gebruikt, dan wordt het geadviseerd dat u uw `dam-handler` bundel met de recentste uber jar compileert.

* Er is een nieuwe kolom voor de aanmaakdatum toegevoegd, die sorteerbaar is, in de DAM-lijstweergave en in de resultaten voor het zoeken naar middelen in de lijstweergave (NPR-31311).

* Asset sorting based on Name column is allowed in List view (NPR-31299).

**Oplossingen**

* Metagegevens voor sommige PDF-documenten worden niet bijgewerkt en naar de PDF opgeslagen bij het wijzigen van de titel (NPR-31575).

* Elementen met het plusteken (+) in de bestandsnaam kunnen niet worden verwijderd (NPR-30588).

* De DAM-mapeigenschappen geven de toegevoegde gebruikers of groepen (gemaakt door LDAP-synchronisatie) in Gesloten gebruikersgroepen niet aan (NPR-30555).

* Speciale tekens die voorkomen in de onderwerpregel van e-mailsjablonen worden niet correct weergegeven (NPR-30547).

* De namen van de activa worden veranderd in kleine letters wanneer het bewegen van activa van één omslag aan een andere in AEM die op runmode Dynamic Media Scene 7 (NPR-31631) lopen.

* De namen van de imageset worden in scène 7 gewijzigd in kleine letters wanneer imageset (of mediaset) wordt gemaakt en benoemd met de juiste naamgevingsconventie in DAM (NPR-31576).

* De Dynamic Media Encode-videoworkflow genereert geen miniatuur voor de video die van scène 7 naar Dynamic Media-uitvoeringsmodus Scene 7 is gemigreerd (NPR-31523).

* Interne serverfout wordt waargenomen tijdens het gebruik van een filter om te zoeken naar sets, AEM uitgevoerd op Dynamic Media - Scene 7 runmode (NPR-31388).

* Er is een fout opgetreden tijdens het bewerken van een externe imageset voor de afbeelding die zich in de map met dezelfde naam bevindt als de bedrijfsnaam van Scene 7 (NPR-31347).

* De activa die verwijzingen bevatten worden niet gepubliceerd (DM) (NPR-31179).

* De vervalwaarde (de tijd van het cliëntgeheime voorgeheugen aan levende) die voor de Hybride wijze van Dynamic Media wordt gevormd wordt niet herhaald aan de leveringsmilieu van Dynamic Media (NPR-31126).

* Het uploaden van AEM Dynamic Media - Scene 7 runmode naar Scene 7 duurt te lang om te voltooien (NPR-30926).

* Na het creëren van een pagina die de component van Dynamic Media terwijl het publiceren van het zelfde heeft, van auteurinstantie die op Dynamic Media loopt - Scene 7 runmode, wordt de gebruiker ertoe aangezet om de configuratie dmscene7 (NPR-30880) te publiceren.

* De waarde van de parameter &quot;asset&quot; in de insluitcode van de viewer blijft ongewijzigd nadat de waarden in het veld &quot;Title after move&quot; en &quot;Name after move&quot; in Dynamic Media zijn gewijzigd (NPR-30745).

* De resultatenpagina Touch UI-zoekopdracht (uitgevoerd via Omnissearch) wordt automatisch naar boven geschoven en verliest de schuifpositie van de gebruiker (NPR-31306).

* DAM Event Purge verwijdert de meest recente (maxSavedActivity) gebeurtenisgegevens en bevat de gegevens die eerder zijn gemaakt (NPR-30870).

* De titel en de naam van het element zijn niet blijvend na verplaatsing naar een doelmap die oneindig schuiven activeert tijdens het selecteren van de map (NPR-30647).

* Verzamelingen worden uit de weergave verwijderd wanneer een filter in AEM Assets wordt toegepast dat via Adobe Asset Link kan worden benaderd (CQ-4280534).

* Time-out voor batchgrootte en workflowstap voor opnieuw verwerken en batchuploaden kan niet worden geconfigureerd vanuit de gebruikersinterface en moet worden ingesteld in CRXDE en de workflow moet tweemaal worden gesynchroniseerd (CQ-4281254).

* De naam van workflowstappen voor batchupload en eenvoudige upload stap is hetzelfde in scène 7, wat tot verwarring leidt (CQ-4281176).

* De werkstroom voor opnieuw verwerken in Scene 7 blijft vast als een element een metagegevensknooppunt mist (CQ-4281170).

* De stap BatchUpload in de workflow voor opnieuw verwerken werkt niet voor de map met video-elementen (CQ-4280630).

* Voor PDF-opties die naar DM worden verzonden, is extractietrefwoorden standaard ingesteld op true (CQ-4280101).

* De Uitzondering van het Punt van het Null wordt waargenomen bij het runnen van Scène 7 die werkschema opnieuw verwerkt op een omslag die niet-DM activa (CQ-4279555) bevat.

* Hernoemen van element in AEM synchroniseert niet met scène 7, wanneer een element met een dubbele naam al bestaat op scène 7 (CQ-4276763).

* Het Zip-bestand dat per e-mail wordt verzonden voor het downloaden van middelen kan niet worden uitgepakt wanneer een gebruiker met Leesmachtigingen het probeert te openen (CQ-4277925).

* De PPT-renderingworkflow genereert geen uitvoeringen van de geüploade PPT-bestanden, aangezien AEM 6.4 geen update naar com.adobe.granite.poi versie 2.0.28 (CQ-4279059) uitvoert.

* PDF-bestanden zijn niet geïndexeerd en de inhoud in deze bestanden kan niet worden doorzocht (CQ-4278916).

##### Sites {#sites-6470}

* Wanneer de lanceringen met Bevorderen slechts Gewijzigde pagina&#39;s worden bevorderd en de lanceringen van de Bevordering met gewijzigde pagina&#39;s worden gedaan, slechts verschijnen de gewijzigde pagina&#39;s om worden bevorderd. Wanneer de lijst die moet worden bevorderd juist is, worden de niet-gewijzigde pagina&#39;s bovendien nog steeds onder aan de lijst weergegeven (NPR-31314).

* Wanneer een AEM Sites-pagina naar een andere locatie wordt verplaatst, worden de eigenschappen niet overeenkomstig bijgewerkt om de nieuwe locatie weer te geven (NPR-31265).

* Voor een nieuwe blauwdruk, als het aantal verslagen meer dan 40 is, slechts worden de eerste 40 verslagen getoond. Blauwdruk geeft lege regels weer voor de rest van de records (NPR-31182).

* Wanneer het aantal LiveCopy-exemplaren groot is, duurt het lang voordat de voorvertoning wordt weergegeven in het LiveCopy-overzicht (NPR-30945).

* Extra ondersteuning om een versie van een pagina in te stellen terwijl u deze verwijdert. Als versioning is uitgeschakeld voor de verwijderde pagina, kan AEM Sites dergelijke pagina&#39;s niet herstellen (NPR-30891).

* Wanneer een gebruiker Japanse of Koreaanse karakters in het beschrijvingsbezit van een menu toevoegt, toont het menu vervormde karakters voor Japans en Koreaans taaltekst (NPR-31331).

* Wanneer een gebruiker de linkerspoorgebieden concentreert en een toetsenbordkortere weg gebruikt om inhoud te kleven, kleeft het de inhoud van het paginageditor klembord in plaats van de inhoud die van de linkerspoorgebieden wordt gekopieerd (NPR-31169).

* Wanneer een gebruiker een inhoudsfragment bewerkt, wordt de reeds verwijderde variatie van het inhoudsfragment hersteld (NPR-31178).

* De query voor Content Fragment Models is inefficiënt. Het is erg langzaam als de instantie veel pagina&#39;s heeft en in een fout resulteert (NPR-30666).

* Wanneer u het model van het inhoudsfragment opslaat, wordt de tijd in het datum- en tijdveld ingesteld op 00:00 (NPR-30540).

##### Integratie {#integrations-6470}

* Bij het configureren van Adobe Launch wordt een slash (/) toegevoegd aan de URL van de bibliotheek (NPR-30700).

* De prestaties van ContextHub degraderen na het publiceren (NPR-30884).

##### Verschuiven {#sling-6470}

* Werk de versie van de bundel van de leverancier van de webconsolesecurityprovider bij naar versie 1.2.4 om de afhankelijkheid van startAPI voor het startscherm van de webconsolesecurityprovider (NPR-30885) te verwijderen.

##### Platform {#platform-6470}

* Updates in de configuratie van de buffergrootte voor de op Jetty-Gebaseerde dienst van HTTP worden niet bewaard (NPR-30925).

* QueryBuilder ondersteunt nu order by fn:name() in xpath query&#39;s (NPR-31322).

* Bijgewerkte Sling Distributed Event admin aan versie 1.1.4 die de kwaliteit van logboeken in een gegroepeerde milieu (NPR-29256) verbetert.

##### Foundation-UI {#foundation-6470}

* Wanneer u met een groot aantal zoekresultaten naar het einde van de resultatenpagina schuift, loopt de browser vast (NPR-31332).

* Wanneer u op een pagina met zoekresultaten overschakelt van de weergave Kaart naar de weergave Lijst, is er een vertraging voordat de pagina kan worden geschoven (NPR-31280).

##### {#oak-6470}

* MS Office-bestanden met .docx- en .xlsx-bestandsextensies die JPEG-afbeeldingen bevatten, kunnen niet worden geparseerd met Tika-parser (NPR-31693).

##### Livefyre {#livefyre-6470}

* De integratie van het leven met AEM 6.4 verbetering geeft de Uitzondering van het Punt Null, wanneer de integratie gebruikend stop DITA voor synthetische middelen wordt gedaan. De integratie werkt echter wanneer componenten handmatig worden toegevoegd (FYR-11066).

##### Vertaling {#translation-6470}

* Het pad naar het doelervaringsfragment wordt niet bijgewerkt tijdens het promoten van een startpagina (NPR-30830).

##### Gemeenschappen {#communities-6470}

* De e-mailfunctionaliteit werkt in sommige gevallen niet correct, zelfs niet wanneer het e-mailbericht in berichtmontages wordt toegelaten, werpt het systeem een uitzondering in NotificationsActivityStreamProvider (NPR-31521).
* Er kunnen geen nieuwe leden worden gemaakt. Er verschijnt een leeg scherm op het scherm Create Member in AEM auteurinstantie (NPR-30951).
* Gebruiker kan geen commentaar op een blog plaatsen in Internet Explorer 11 (NPR-30927).
* De beheerder van een Beperkte Groep kan niet de Kaart van de Groep bekijken, kan om het even welke Snelle verrichtingen van de Verbinding (Edit/Publish/Delete groepen) in AEM auteursinstantie (NPR-30810) uitvoeren.
* Informatie over lidgroepen/groepen is niet zichtbaar bij het maken van een nieuwe Site in AEM auteurinstantie (NPR-28840).

##### Forms {#forms-6470}

>[!NOTE]
>
>AEM Service Pack bevat geen oplossingen voor AEM Forms. Ze worden geleverd met een apart Forms-add-onpakket. Daarnaast wordt een cumulatief installatieprogramma uitgebracht dat oplossingen voor AEM Forms op JEE bevat. Zie [AEM Forms-invoegtoepassing installeren](#install-aem-forms-add-on-package) en [AEM Forms JEE-installatieprogramma installeren](#install-aem-forms-jee-installer) voor meer informatie.

**Forms-invoegtoepassing**

**Adaptieve Forms**

* Tekenreeksen bevatten de woordenboeksleutel bij het lokaliseren van adaptieve formulieren (NPR-31109).

* De selectievakjes en vervolgkeuzelijsten in Forms mislukken toegankelijkheidscontroles (NPR-31282).

**HTML5 Forms**

* Als u HTML5-voorbeeld van een XDP-formulier genereert, wordt een flikkering weergegeven terwijl exemplaren van een subformulier worden toegevoegd (NPR-30907).

**Documentservices voor OSGi**

* Als u meerdere gelijktijdige thread uitvoert voor het samenstellen van de formulieren met de methode com.adobe.fd.assembler.service.AssemblerService.invoke(), wordt een foutbericht weergegeven (NPR-31164).

* De tijdelijke bestanden die door de Assembler Service worden gemaakt, worden niet automatisch verwijderd en moeten AEM opnieuw worden opgestart (NPR-30846).

* Als u ReaderExtension-rechten toepast op PDF, wordt een foutbericht weergegeven (NPR-30930).

**Workflow**

* OSGi-workflow mislukt als gevolg van 100% CPU-gebruik (NPR-31234).

**Forms JEE-installatieprogramma**

**Document Services**

* De Convert PDF Service kan PDF-documenten niet converteren naar PostScript en er wordt een foutbericht weergegeven (NPR-31267).

* De configuratie van het eindpunt van de ZEEP stelt na het toepassen van een flard terug om HTML aan mislukking te bevestigen PDF (NPR-31309).

**PDFG-service**

* Kan het Adobe PDF-instellingenbestand dat u hebt gedownload niet uploaden via de interface voor beheerders (NPR-31273).

#### AEM 6.4.6.0 {#experience-manager-6460}

AEM 6.4.6.0 is een belangrijke update die prestaties, stabiliteit, veiligheid en belangrijkste klantenfixes en verhogingen omvat die sinds de algemene beschikbaarheid van AEM 6.4 in **April 2018 worden vrijgegeven.**

Het is ook cumulatief, wat betekent dat 6.4.6.0 alle AEM 6.4 de dienstpakken voorafgaand aan de versie omvat.

Enkele belangrijke hooglichten van AEM 6.4.6.0 zijn:

* De ingebouwde opslagplaats (Apache Jackrabbit Oak) wordt bijgewerkt naar versie 1.8.15.
* Toegevoegde ondersteuning voor het bijhouden van dynamische UI-statussen in het bijhouden van gebeurtenissen in de basis-API.
* Ondersteuning voor renditie toegevoegd aan de kerncomponent van de afbeelding.

**Assets**

* Koppeling voor het delen van elementen van een map met spatie en `&`-teken in de naam geeft lege grijze kaarten voor bepaalde elementen weer. NPR-29934: Hotfix voor CQ-4270187
* De DAM-workflow loopt vast tijdens het maken van MP4-middelen voor AEM. NPR-30031: Hotfix voor CQ-4271352
* Verbindingsprobleem met Adobe Smart Tag via Datapower. NPR-30026: Hotfix voor CQ-4269457
* PDF kan niet worden gevonden met OmniSearch. NPR-30046: Hotfix voor GRANITE-26290
* Elementpaden in URL&#39;s en mapmetagegevens die door de ACS-API worden gegenereerd, worden niet via URL gecodeerd.  GRANITE-26198: Hotfix voor CQ-4271814
* Functionaliteit voor het maken van een revisietaak werkt niet als gevolg van een ongedefinieerde lading. NPR-30469: Hotfix CQ-4274263
* De mogelijkheid om van de weergave van de kaart over te schakelen op de lijstweergave en vice versa verdwijnt na een OmniSearch-bewerking op de elementenkiezer. NPR-29852: Hotfix voor CQ-4269369
* (Tik op UI) Tijdens de wizard Publicatie beheren worden elementen toegevoegd aan de replicatiewachtrij nadat de pagina&#39;s zijn toegevoegd, waardoor enkele elementen na een paar seconden worden weergegeven. NPR-29985: Hotfix voor CQ-4270724
* Het sorteren van onderzoeksvraag door relevantie keert InDesign documenten samen met de malplaatjes van InDesign terug. Hotfix voor CQ-4273864
* Als de gebruiker een e-mailadres in hoofdletters heeft, kunnen gebruikers niet inchecken voor de elementen die eerder zijn uitgecheckt. Hotfix voor CQ-4276575
* Als u Dynamic Media-Cloud Services configureert in de modus `DMHybrid`, ontstaan er meerdere lege rapportsuites die zijn gemaakt in Analytics zonder dat deze zijn opgeslagen op AEM, waardoor de rapportsuite wordt gedupliceerd. Hotfix voor CQ-4276855
* Het waarschuwingsvenster wordt niet weergegeven tijdens het promoten op de pagina &quot;Beheerde tag&quot;. Hotfix voor CQ-4252851
* Wanneer u de carrousel gebruikt voor het beheer van tags, werkt de navigatieknop niet. Hotfix voor CQ-4275499
* De functionaliteit voor het verplaatsen van elementen in bulk wordt verbroken, waardoor elementen niet worden verplaatst. Hotfix voor CQ-4272987

**Sites**

* `pageinfo.json` de verzoeken zijn bijzonder traag en het duurt te lang om te laden . NPR-29709: Hotfix voor CQ-4269560
* `onTime` of  `offTime` metagegevenseigenschappen die op elementen zijn opgeslagen, worden niet teruggeroepen als de AEM server opnieuw wordt gestart. NPR-30413: Hotfix voor CQ-4272784
* Door onjuist gedrag van de klasse ConfigPostProcessor verwijdert het opschorten van de bovenliggende pagina de volgende cq: Het mengen van LiveRelationship type van de kindpagina. NPR-30536, NPR-30510: Hotfix voor CQ-4254113
* XSS (Cross-site scripting) in het werkstroomdialoogvenster Start op de pagina Campagne bewerken. NPR-29747: Hotfix voor CQ-4271067
* (Klassieke UI) Het werkstroomvergrendelingsstadium schakelt het werkstroomtabblad uit totdat de vergrendeling wordt losgelaten. NPR-30356: Hotfix voor CQ-4237557
* (IE11) Wanneer HTML-inhoud in een RTF-component met defaultPasteMode = plaintext wordt geplakt, wordt de HTML geplakt met de opmaak, zodat defaultPasteMode geen effect heeft. NPR-30045: Hotfix voor GRANITE-26094
* (Klassieke UI) Wanneer de pagina voor sitebeheer opnieuw wordt geladen, worden alle dropdown-items in het menu &quot;Nieuw&quot; uitgeschakeld. NPR-29980: Hotfix voor CQ-4272044
* Kan geen stijlen aan de tekst toevoegen of bestaande stijlen bewerken die voor de inhoud zijn gemaakt. NPR-29712: Hotfix voor CQ-4266249
* (Klassieke UI) Middelen zonder dc: titelwaarde wordt zonder titel weergegeven in de dialoogbrowser van het padveld. NPR-30166: Verzoek om ondersteuning voor CQ-88858
* De vraag: listener werkt niet met geneste componenten, zelfs niet nadat de component parsys is toegevoegd. NPR-30422: Hotfix voor CQ-4274863
* De fout van ContextHub tijdens AEM en de integratie van de Campagne. NPR-30625: Hotfix voor CQ-4250790
* De waarde van de requestType-parameter wordt gekopieerd naar de waarde van een HTML-tagkenmerk dat is ingekapseld in dubbele aanhalingstekens. NPR-29832: Hotfix voor CQ-4255365
* De pagina moet worden vernieuwd nadat componenten zijn gekopieerd en van de ene pagina naar de andere zijn geplakt. NPR-29982: Hotfix voor CQ-4256019
* Publiceren/verwijderen van een alias op een pagina wordt niet ondersteund en moet worden verwijderd. NPR-30062: Hotfix voor CQ-4271249
* Unclosed ResourceResolver waarschuwing in ExperienceFragmentsReplicationListener die tot stabiliteitskwesties in tijd leidt, dwingend om AEM instanties opnieuw te beginnen. NPR-30416: Hotfix voor CQ-4257521
* Als u ervaringsfragmenten verplaatst waarnaar wordt verwezen in meer dan 150 pagina&#39;s, wijzigt u het fragmentPath niet op de pagina&#39;s waarnaar wordt verwezen. NPR-30556: Hotfix voor CQ-4274900
* Parseerfout bij het openen van een inhoudsfragment met de tekens dollar (`$`) en accolade openen (`{`) achter elkaar. Hotfix voor CQ-4270266
* VersionPreviewServlet mislukt in NullPointerException wanneer het proberen om een versie van een Fragment van de Ervaring in de chronologie te tonen. NPR-30074: Hotfix voor CQ-4271881
* Kan inhoudsfragmenten niet vergrendelen met de functie Inchecken. NPR-29923: Hotfix voor CQ-4258785
* Fout bij verificatie van handtekening in SAML-verificatiehandler. NPR-30379: Verzoek om steun voor GRANITE-26567

**Replicatie**

* De Zitting JCR/Resolver van het Middel wordt gelekt tijdens implementatie OAuth op elke replicatie aan MAC/het Portaal van het Merk. NPR-30000: Hotfix voor graniet-26196

**Sling**

* De orde van kinderen beïnvloedde het gebruiken van overlapping en orde vóór veroorzaakt IndexOutOfBoundException. NPR-30408: Hotfix voor Sling-8296 &amp; Sling-7375
* InactiveBundlesHealthCheck leest de configuratie MissingPackagesHealthCheck als de configuraties InactiveBundlesHealthCheck zijn opgeslagen. NPR-30084: Hotfix voor CQ-4272644

**Handel**

* Kan de catalogusblauwdruk niet uitvoeren vanaf de Sites-console. NPR-29829: Hotfix voor CQ-4271461
* Het in het product gebruikte element bevat geen enkele verwijzing naar het product in de sectie &quot;References&quot; van het element. Het middelenpad wordt ook niet bijgewerkt als het element wordt verplaatst. NPR-30542: Hotfix voor CQ-4270247

**Platform**

* AEM Default Mail Sender kan geen e-mail verzenden naar een externe SMTP-server via TLS v1.2. NPR-30476: Hotfix voor GRANITE-26605

**Gemeenschappen**

* Groepen die op de auteur zijn verwijderd, zijn niet synchroon met alle uitgevers. NPR-29987: Hotfix voor CQ-4268738
* Verwijderde gebruikers die zijn verwijderd uit het veld Gemeenschapsbeheerders, zijn niet synchroon met de groep Lidmaatschap. NPR-30389: Hotfix voor CQ-4274339
* Gebruikers die deel uitmaken van de groep met beheerders, hebben geen snelle koppelingen naar de groep. NPR-30546: Hotfix voor CQ-4275579
* Wanneer u een nieuwe en bestaande communautaire groep bijwerkt, wordt de eigenschap in jcr overschreven: inhoudsknooppunt en wijzigt de naam ervan in de titel van de eerste pagina. NPR-30109: Hotfix voor CQ-4273719
* Quicksearch en onderzoek door plaats en adres werkt niet wanneer de gemeenschap wordt geplaatst om met de Leverancier van het Middel van de Opslag van het Gegevensbestand (DSRP) te werken. NPR-26737: Hotfix voor CQ-4258493

**Vertaling**

* Automatisch uitvoeren van translatie werkt niet. NPR-30499: Hotfix voor CQ-4276288
* De gebruiker kan taalkopie maken op het inhoudspad dat is beperkt tot alleen-lezen. NPR-29937: Hotfix voor CQ-4270708
* Probleem met vertaling - Slechts een paar componenten worden omgezet met behulp van Machine Translation. NPR-30079: Hotfix voor CQ-4273764

**Integratie**

* De aangepaste inhoud wordt pas correct weergegeven op de publicatieversie als de instantie opnieuw is gestart. NPR-30421: Hotfix voor CQ-4273706

**Projecten**

* dam: folderThumbnailPaths de waarden worden niet vernieuwd en tonen oude duimnagels zelfs na het schrappen van de activa binnen de omslag. NPR-30424: Hotfix voor CQ-4273667

**UI-consoles**

* XSS (Cross-site scripting) op Sites page properties op thumbnail tab. NPR-30048: Hotfix voor graniet-26200

**UI-Foundation**

* Toegevoegde ondersteuning voor het bijhouden van dynamische UI-statussen in het bijhouden van gebeurtenissen in de basis-API. NPR-30742, GRANITE-26322: Hotfix voor GRANITE-26036

**Forms**

>[!NOTE]
>
>AEM Service Pack bevat geen oplossingen voor AEM Forms. Ze worden geleverd met een apart Forms-add-onpakket. Daarnaast wordt een cumulatief installatieprogramma uitgebracht dat oplossingen voor AEM Forms op JEE bevat. Zie [AEM Forms-invoegtoepassing installeren](#install-aem-forms-add-on-package) en [AEM Forms JEE-installatieprogramma installeren](#install-aem-forms-jee-installer) voor meer informatie.

**Forms-invoegtoepassing**

**Adaptieve Forms**

* Het ophalen van een leeg CSS-bestand bij de uitgever duurt langer, waardoor prestatieproblemen ontstaan. NPR-30558: Hotfix voor CQ-4274399
* Forms die na publicatie is gewijzigd, wordt niet meer gepost bij het publiceren van de site. NPR-30411: Hotfix voor CQ-4236566

**Forms - Ondersteunende integratie**

* Er wordt een fout gegenereerd bij het maken van het formuliergegevensmodel met de Web Service Definition Language (WSDL). NPR-30388: Hotfix voor CQ-4272921

**Forms - Correspondentenbeheer**

* Speciale tekens zoals kleiner dan (&lt;), groter dan (>) en en en-teken (&amp;) worden gecodeerd in de gebruikersinterface van de agent. NPR-30410: Hotfix voor CQ-4273887
* Wanneer het teweegbrengen van tekstfragment dat de waarden van het Woordenboek van Gegevens bevat, wordt de Agent UI unresponsive. NPR-30098, NPR-30083: Hotfix voor CQ-4272204
* CCR UI (Correspondence UI) maken mislukt soms met foutvariabele (object Object). NPR-29983: Hotfix voor CQ-4273874
* Herladen van letteromtrekken mislukt, met een uitzondering als de beschrijving van documentfragmenten speciale tekens bevat zoals kleiner dan (&lt;), groter dan (>) en en en-teken (&amp;) in eigenschappen. NPR-29930: Hotfix voor CQ-4252762

**HTML5 Forms**

* Wanneer u in de modus Bladeren een HTML5-formulier leest met toegang tot niet-visuele desktops, wordt in de Chrome-browser vóór elke SVG (Scalable Vector Graphic) in het formulierontwerp &quot;graphic&quot; gelezen. NPR-30450: Hotfix voor CQ-4274732

**Forms JEE-installatieprogramma**

**Forms - Foundation JEE**

* Als u een verbinding met een webservice toevoegt of bewerkt door webservices aan te roepen vanuit AEM Forms Workbench, treedt er een fout op: ClassNotFoundException org.apache.axis.message.SOAPBodyElement. NPR-30116: Hotfix voor CQ-4273217

**Forms - Document Services**

* Fout bij PDF/A-label in Acrobat-preflight. NPR-30594: Hotfix voor CQ-4276032
* Gegevensbindingen van één teken in PDF zorgen ervoor dat Reader-extensies mislukken met de fout &quot;java.lang.StringIndexOutOfBoundsException: Tekenreeksindex buiten bereik: 1&quot;. NPR-30128: Hotfix voor CQ-4273878
* Wanneer een laadtest wordt uitgevoerd op HTML naar PDF-service, mislukt dit met een fout en worden instellingen voor bestandstypen verwijderd van AEM formulierserver. NPR-30085: Hotfix voor CQ-4272631
* Als u een PDF afvlakt met Adobe Acrobat 9.1 (XFA versie 3.0), wordt de PDF-formulierstatus niet behouden: Onzichtbare elementen op het formulier worden weer ingesteld op een zichtbare status. NPR-29978: Hotfix voor CQ-427088

**Forms - Documentbeveiliging**

* Het toepassen van een handtekening met tijdstempel mislukt vanwege een fout: ALC-DSC-003-000: com.adobe.idp.dsc.DSCInvocationException: Inroepfout. NPR-30696, NPR-30537: Hotfix voor CQ-4273778
* De Manager van de configuratie neemt geen Japanse koorden voor gelokaliseerde lijstkolommen op. NPR-30496: Hotfix voor CQ-4274868

**PDFG-service**

* Verbindingsfout tijdens het converteren van Word-document naar PDF op Windows Server 2016. NPR-30597: Hotfix voor CQ-4275652
* De toestemming ontkende uitzondering wanneer het proberen om de HTML aan de achtergronddienst van PDF via de bibliotheek &quot;phantomjs&quot;te gebruiken. NPR-30456: Hotfix voor CQ-4258077
* maxReuseCount voor HTML naar PDF-service wordt niet weergegeven met JBoss Management Console. NPR-30303, NPR-30135: Hotfix voor CQ-4273763

#### AEM 6.4.5.0 {#experience-manager-6450}

AEM 6.4.5.0 is een belangrijke update die prestaties, stabiliteit, veiligheid en belangrijkste klantenfixes en verhogingen omvat die sinds de algemene beschikbaarheid van AEM 6.4 in **April 2018 worden vrijgegeven.**

Het is ook cumulatief, wat betekent dat 6.4.5.0 alle AEM 6.4 de dienstpakken voorafgaand aan de versie omvat.

Enkele belangrijke hooglichten van AEM 6.4.5.0 zijn:

* De ingebouwde opslagplaats (Apache Jackrabbit Oak) wordt bijgewerkt naar versie 1.8.13.
* Time-out voor socket en verbinding toegevoegd in Merk Portal-replicatieagents.
* Verbeteringen in het uitgebreide onderzoek - De paginatielimiet van het zoekresultaat is verhoogd tot 100 pagina&#39;s.
* Uitgeschakeld `AssetDownloadServlet` component OSGi door gebrek op AEM publiceer instanties. Zie [Elementen downloaden van AEM](/help/assets/download-assets-from-aem.md) voor meer informatie.
* Ondersteuning voor beheer van meerdere sites ingeschakeld voor middelen. Zie [Elementen opnieuw gebruiken met MSM voor elementen](/help/assets/reuse-assets-using-msm.md) voor meer informatie.

**Activa**

* Elementen met een apostrof in de bestandsnaam worden niet gesynchroniseerd met Dynamic Media. NPR-29538: Hotfix voor CQ-4270592
* Bijgewerkte interface DAM DMGateway voor S3 multipart steun. NPR-29740: Hotfix voor CQ-4226303
* In het dialoogvenster voor het downloaden van middelen wordt een onjuiste bestandsgrootte weergegeven wanneer uitvoeringen voor een video in Dynamic Media worden gedownload. NPR-29642: Hotfix voor CQ-4246202
* Middelen worden onbruikbaar nadat de DAM DAM Mime Type Service van Dag CQ tekst voor m3u8 toepast. NPR-29276: Hotfix voor CQ-4264052
* De aanpassing van de verwijzing van het element kan de sessie niet opslaan als een van de verplaatste/hernoemde elementen deel uitmaakt van de verzamelingen van Sling Resource. NPR-29143: Hotfix voor /CQ-4252605
* Kan elementen niet bijhouden of vinden door de waarden van metagegevens te zoeken. NPR-29141: Hotfix voor CQ-4260215
* Wanneer u het zoekfilter gebruikt om een slimme verzameling op te slaan, blijft de klikactie in het deelvenster niet actief. NPR-29000:  Hotfix voor CQ-4240323
* Als u een map verplaatst, kunt u een map met hoofdletters of kleine letters maken. NPR-28945: Hotfix voor CQ-4265234
* Lege resultaten die worden weergegeven in Omnsearch als de naam van de verzameling ruimte bevat. NPR-29001: Hotfix voor CQ-4236729
* Als de naam van een bestand wordt gewijzigd met enkele niet-ondersteunde speciale tekens, zoals en-teken (&amp;), wordt een ongeldige map gemaakt. NPR-29196: Hotfix voor CQ-4265037
* DAM Extract Archive for zip file functionaliteit is broken. NPR-29187: Hotfix voor CQ-4254421
* Metagegevens importeren moet het importeren van metagegevens toestaan zonder naamruimten te registreren. NPR-29425, NPR-28132: Hotfix voor CQ-4269445
* Wijzigingen in metagegevens worden niet opgeslagen voor elementen waarvan de naam een aanhalingsteken bevat. NPR-29395: Hotfix voor CQ-4254305
* Kan een DAM-element niet verplaatsen als de bestandsnaam witruimte bevat. NPR-29270: Hotfix voor CQ-4266403
* Kan ZIP-archieven die zijn gecomprimeerd met Deflate64-algoritme niet downloaden. NPR-29225: Hotfix voor CQ-4253995
* Miniaturen van middelen worden langzaam weergegeven wanneer u een map opent die elementen bevat met veel versies. NPR-29833: Hotfix voor CQ-4271629
* Kan de gemarkeerde verzameling niet invoeren als de Enter-toets wordt ingedrukt nadat u de verzameling hebt geselecteerd. NPR-29723: Hotfix voor CQ-4261607
* XSS (Cross-site scripting) valt aan via het beperkte waarschuwingsvenster. NPR-29671: Hotfix voor CQ-4270133
* Het toevoegen van relaties aan elementen mislukt voor gebruikers zonder verwijdermachtigingen. NPR-29640: Hotfix voor CQ-4269196
* Nadat de elementtitel is toegevoegd aan de eigenschappenpagina, wordt de eigenschappenpagina opnieuw geopend wanneer de gebruiker de pagina probeert te sluiten AEM. NPR-29628: Hotfix voor CQ-4264929
* Als u een groot aantal relaties op elementen maakt, treedt er een fout op. NPR-28779: Hotfix voor CQ-4250708
* Het opnemen van middelen gaat langzaam in de Scene7 Connect-uitvoeringsmodus. NPR-28658: Hotfix voor CQ-4263007
* Een fout Uncaught TypeError: Kan de eigenschap &#39;split&#39; van undefined niet lezen. Deze wordt weergegeven wanneer u de zoekresultaten probeert weer te geven. NPR-28803: Hotfix voor CQ-4248371
* De replicatie van AEM naar Brand Portal blijft voor lange perioden vastzitten. NPR-28914: Hotfix voor CQ-4254932
* Het verplaatsen van activa in DAM leidt niet tot een vergelijkbare verplaatsing in Scene7. NPR-28957: Hotfix voor CQ-4264974
* De updates van meta-gegevens worden niet overgegaan tot IPS als het meta-gegevensgebied in AEM wordt bijgewerkt. NPR-28961: Hotfix voor CQ-4255393
* VersioningTimelineEventProvider moet de hoofdversie en de versieopmerking bevatten. Hotfix voor GRANITE-26063
* Het injecteren van gegevens leidt tot code-uitvoering aan de serverzijde. Hotfix voor CQ-4270246
* Ondersteuning voor beheer van meerdere sites ingeschakeld voor middelen. Hotfix voor CQ-4271453, CQ-4268621, CQ-4257491
* AEM interface zou een extra ingang voor de huidige versie van de activa in de chronologiegeschiedenis moeten tonen, tonend de recentste controle-in commentaar van de Verbinding van de Activa van Adobe. Hotfix voor CQ-4262864
* De voorbeeldvideo wordt niet geladen wanneer u een gemengdeMediaSet maakt of bewerkt. Hotfix voor CQ-4244889
* Als u de machtigingen voor het verwijderen van inhoud aan de AEM uitschakelt, kan de gebruiker niet publiceren naar Brand Portal. Hotfix voor CQ-4270426
* Vragen beperken gerelateerde problemen met rapporten over bedrijfsmiddelen na upgrade naar AEM 6.4.3. NPR-28588: Hotfix voor CQ-4262022, CQ-4260697
* De downloadfunctionaliteit gebruikt AEM Assets via assetdownload servlet, zodat anonieme gebruikers alle middelen kunnen downloaden. NPR-27315, hotfix voor CQ-4254732

**Sites**

* De naam van de JCR-klachtentag moet automatisch worden ingevuld op basis van de titel van de tag. NPR-28990: Hotfix voor CQ-4199411
* De knop Overerving annuleren is niet zichtbaar in sommige velden die zijn toegevoegd aan de pagina-eigenschappen. NPR-29079: Hotfix voor CQ-4265686
* De actie van de rollout voorproef zou niet moeten proberen om het levende exemplaar opnieuw te creëren of het te tonen in de lijst van rollout pagina&#39;s. NPR-29151: Hotfix voor CQ-4266213
* (Sjablooneditor) Stijlbeleidsregressie in de structuurmodus. NPR-28981: Hotfix voor CQ-4264400
* Geneste live kopieën tonen dubbele vermeldingen tijdens de rollout. NPR-29300: Hotfix voor CQ-4268664
* Het publiceren van een live kopie van een live kopie die een component Design Importer bevat, mislukt. Kan de referenties voor de geselecteerde pagina niet ophalen. NPR-28944: Hotfix voor CQ-4265014
* CoralUI, wanneer gebruikt met Multifield, slaat fileReferenceParameter op componentenniveau in plaats van multifield niveau op. NPR-29536: Hotfix voor CQ-4266129
* De ontwerpverwijzing wordt niet herhaald bij publicatie nadat overerving bij Design Importer is geannuleerd. NPR-29648, NPR-29721: Hotfix voor CQ-4269270, CQ-4271087
* Het padveld in de Rich Text Editor wordt geopend op het hoofdpad, ongeacht het pad dat u wilt zoeken. NPR-29483: Hotfix voor CQ-4268997
* (IE11) Met kopiëren van HTML-inhoud plakken in een RTE-component met defaultPasteMode = plaintext wordt de inhoud niet als onbewerkte tekst geplakt. NPR-29432, NPR-29171: Hotfix voor GRANITE-24941
* De spellingcontrole van de Rich Text Editor werkt niet meer in andere talen. NPR-29506: Hotfix voor CQ-4264990
* XSS (Cross-site scripting) op de pagina Campagne. NPR-29614: Hotfix voor CQ-4269322
* Het minimaliseren van Rich Text Editor van volledig scherm in de bronbewerkingsmodus leidt tot verlies van inhoud. NPR-29574: Hotfix voor CQ-4260584
* (Klassieke UI) het navigeren aan het laatste lusje is niet altijd mogelijk wanneer een groot aantal markeringen bestaat. NPR-29544: Hotfix voor CQ-4264548
* (Klassieke UI) Het navigatiemenu van de Admin Console verdwijnt, en de pagina wordt niet volledig geladen. NPR-29571: Hotfix voor CQ-4264585
* Er wordt een foutmelding gegenereerd wanneer componenten aan de WCM-pagina worden toegevoegd wanneer minificatie op de instantie is ingeschakeld. NPR-29396: Hotfix voor CQ-4266196
* An issue with the inheritance of Style System nodes from the parent. NPR-29296: Hotfix voor CQ-4266041
* De pagina die wordt teruggezet met Timewarp, moet naar het correcte beeld op het tijdstip van versioning verwijzen.  NPR-29431: Hotfix voor CQ-4262638
* Lege pagina met Javascript-fouten in de editor na installatie van de nieuwste momentopnameversie 6.4.5. NPR-29475: Hotfix voor CQ-4266196
* Terwijl het toevoegen van een component aan parsys, wordt het bezit van de ontwerpcomponentenlijst niet gerespecteerd en aan een verschillende naam van de malplaatjeknoop met een gelijkaardige parsys structuur opgelost. NPR-29509: Hotfix voor CQ-4269044
* cq:dropTarget-zone bedekt de volledige component in plaats van de grootte van de afbeelding, waardoor het lastig is om deze te richten op ingesloten componenten. NPR-29738: Hotfix voor CQ-4268912
* De afbeeldingscomponent roept de listener &quot;afteredit&quot; niet aan nadat de lokale afbeeldingseditor is gebruikt. NPR-29616 Hotfix voor CQ-4268065
* Een probleem bij het instellen van de sociale post op Facebook. NPR-29212: Hotfix voor CQ-4266630
* Bij het promoten van startpagina&#39;s voor gewijzigde pagina&#39;s wordt rekening gehouden met wijzigingen in zowel de bron- als startvertakkingen. NPR-29308: Hotfix voor CQ-4266746
* De weergegeven miniatuur op Inhoudsfragment toont de interne kalenderrepresentatie voor het veld Datum en tijd. NPR-29531: Hotfix voor CQ-4269362
* Kan geen code in bulk toevoegen aan pagina&#39;s met bestaande verschillende markeringen. NPR-28729: Hotfix voor CQ-4262922
* Het pictogram Geplande activering wordt niet weergegeven in de sitebeheerder. NPR-28725: Hotfix voor CQ-4263917

**Replicatie**

* De gevoelige kwetsbaarheid van de informatieonthulling in de component van de Agent van de Replicatie. NPR-29612, NPR-24951: Hotfix voor GRANITE-25070
* Door de gebruiker opgegeven gegevens worden niet beschermd bij uitvoer in de component cq/replication/components/agent, wat resulteert in een opgeslagen XSS-kwetsbaarheid (Cross-site scripting). Hotfix voor CQ-4266263

**Ervaringsfragmenten**

* Kan ervaringsfragmenten niet exporteren naar doel wanneer een slimme afbeelding wordt gebruikt. Hotfix voor CQ-4269606

**Sociale rapportage**

* AEM Community-rapporten worden niet weergegeven in AEM auteur-exemplaar. Hotfix voor CQ-4266294

**Platform**

* XSS (Cross-site scripting) in pakketbeheer tijdens de installatie van een pakket. NPR-29734, NPR-29713, NPR-29630: Hotfix voor GRANITE-26161, GRANITE-
* Meerdere opgeslagen en gereflecteerde XSS-scripts (Cross-site scripting) in CRXDE Lite. NPR-29634: Hotfix voor GRANITE-26049
* De aanmeldingsfunctionaliteit voor het Delen van pakketten gebruikt GET eerder dan POST verzoek, waardoor het wachtwoord onder het netwerktabblad zichtbaar wordt. NPR-29631: Hotfix voor GRANITE-26048

**Felix**

* Cross-site scripting (XSS) waargenomen in systeemconsole. De pagina wordt geladen en pop-up komt over wanneer de muis over het tekstveld wordt bewogen. NPR-29853, NPR-29633: Hotfix voor GRANITE-26188, GRANITE-26050

**Graniet**

* Apache Sling Logging Logger Configuration filtert het geïnjecteerde script niet.  NPR-29775: Hotfix voor GRANITE-26051

**Gemeenschappen**

* Groepen die bij de auteur zijn verwijderd, moeten uit de publicatie-instanties worden verwijderd. NPR-28933: Hotfix voor CQ-4264645
* Toepassingsgeheim moet zijn beveiligd met een wachtwoordveld en mag niet worden weergegeven in normale tekst voor sociale-verbindingsprogramma&#39;s. NPR-29728: Hotfix voor CQ-4270480
* Bezoekers en leden zonder moderatorrechten kunnen niet-goedgekeurde/hangende berichten zien door de URL te plakken. NPR-29726: Hotfix voor CQ-4271124, CQ-4271441
* Hoge responstijd tot 40-50 seconden wordt waargenomen bij het aanmelden bij de gebruiker voor de Gemeenschap. NPR-29678: Hotfix voor CQ-4269444

**Vertaling**

* Gebruikers zonder vertaalfunctietoegang op navigatie zouden hun subpagina&#39;s niet mogen openen. NPR-29644: Hotfix voor CQ-4269979
* Gebruikersmachtigingen die niet worden ondersteund als wizard, maken de vertaalkopie op een alleen-lezen locatie. NPR-29375: Hotfix voor CQ-4265877

**UI - Foundation**

* De paginatielimiet van het zoekresultaat is verhoogd tot 100 pagina&#39;s voor de kaartweergave en tot 200 voor de lijstweergave. NPR-2932: Hotfix voor GRANITE-24644
* Als tags lui worden geladen, wordt er niets weergegeven op de verzamelingspagina. NPR-29267: Hotfix voor GRANITE-24902
* Als u de paginatielimiet wijzigt in 100 in plaats van 40, wordt een extra uitgestelde belasting geactiveerd zonder een verzoek om paginering. NPR-29246: Hotfix voor GRANITE-25027
* AEM veld voor granietwachtwoord wordt niet ingevuld na versleuteling. NPR-29245: Hotfix voor GRANITE-24908

**Integratie**

* Een uitzonderingsbericht wordt getoond wanneer het proberen om de AEM lanceringsconfiguratie uit te geven en te bewaren. NPR-29086: Hotfix voor CQ-4266153
* BrightEdge-referenties zijn mislukt vanwege een verbindingsfout.  NPR-29167: Hotfix voor CQ-4265872
* De geërfte van checkbox die op het wortelniveau in Cloud Service vormt verschijnt zou moeten worden verwijderd. NPR-27856:  Hotfix voor CQ-4259676

**Sling**

* Time-out HTTP-verbinding wordt niet gelezen van de configuraties. NPR-29264: Hotfix voor SLING-7902
* De JCR installateurssteun veroorzaakt de configuratie OSGi om ongeldig formaat te gebruiken en herplaatsing te blokkeren. NPR-29027: Hotfix voor CQ-4264694

**Projecten**

* Gebruikers kunnen de projectworkflow niet voltooien. NPR-29621: Hotfix voor CQ-4258791
* De lijst van het Werkschema van het project toont lege rijen voorbij 40 werkschema&#39;s. NPR-28739: Hotfix voor CQ-4264005
* Als u de optie Dynamische vertoning kiest in Brand Portal, wordt een leeg ZIP-bestand gedownload. NPR-29420: Hotfix voor CQ-4268826
* Publiceer middelen van AEM Auteur /content/dam/mac folder aan het Portaal van het Merk werkt niet. NPR-29820: Hotfix voor CQ-4271118
* Leestekens in de naam veroorzaken problemen met de publicatieknop. NPR-29573: Hotfix voor CQ-4269317
* Kan de taalkopie van het element niet maken via het verwijzingspaneel. Hotfix voor CQ-4269535

**Workflow**

* Als u een upgrade uitvoert van 6.4.2 naar 6.4.4, wordt het kalenderkiezerveld van de dialoogdeelnemer verbroken. NPR-29727: Hotfix voor CQ-4270423

**WCM - Admin UI**

* De knoppen worden niet weergegeven wanneer u het tabblad met machtigingen opent in de implementatie van Coral2. Hotfix voor CQ-4269419

**WCM - MSM**

* Wanneer u een onderliggende node in de live kopie verwijdert, moet de liveRelationship worden losgekoppeld. Hotfix voor CQ-4270395
* Als u een upgrade uitvoert naar AEM 6.4.3, duurt het lang voordat u de functie voor beheer van meerdere sites kunt uitvoeren. Hotfix voor CQ-4271410

**Kwetsbaarheid**

* Het CSRF-beschermingskader werkt niet met AEM stichtingsvormen. NPR-28612: Hotfix voor GRANITE-22231

**WCM - Pagina-editor**

* Gespiegeld XSS (Cross-site scripting) bij gebruik van een ongeldige kiezer. Hotfix voor CQ-4270397

**Forms**

De belangrijkste markeringen voor AEM 6.4.5.0 vormen zijn:

**Forms-invoegtoepassing**

**Adaptieve Forms**

* (Touch UI) De optie van het werkschema van het Begin pop up niet de dialoogdoos voor configuratie. NPR-29521: Hotfix voor CQ-4269050

**Forms - Ondersteunende integratie**

* Toegelaten steun voor de Actieve Diensten van de Federatie van de Folder (ADFS) v3.0 voor de Integratie van de Dynamiek van Microsoft op-gebouw. NPR-30003, NPR-29484: Hotfix voor CQ-4270586
* Prefill-service mislukt als gevolg van een langdurige doorlooptijd van de AEM Forms Data Integration-module. NPR-28997: Hotfix voor CQ-4265988
* SOAP Webservice request is malformed within AEM Forms. NPR-29013: Hotfix voor CQ-4265443
* Er wordt geen foutbericht weergegeven tijdens het testen van de SOAP-service in het geval van een onjuiste datumwaarde. Hotfix voor CQ-4265445

**Forms - Interactieve communicatie en Forms - Correspondentenbeheer**

* CCR UI (Correspondence UI) maken kan een zwevend getal niet verwerken.  NPR-29210: Hotfix voor CQ-4254201
* De tooltip die op een variabele wordt geplaatst is niet zichtbaar op Create Correspondence UI (CCR UI). NPR-29739: Hotfix voor CQ-4250533
* Kan niet kopiëren of plakken uit Omnsearch binnen letters. NPR-29808: Hotfix voor CQ-4270783

**HTML5 Forms**

* Wanneer we een spatie in de tekst toevoegen, staat het tekstveld het einde niet toe. NPR-28844: Hotfix voor CQ-4260239

**Forms JEE-installatieprogramma**

**Forms - Foundation JEE**

* Webservicecomponent in AEM Forms Workbench kan geen webservice aanroepen. Hiervoor is tweewegs-SSL-verificatie vereist. NPR-29485: Hotfix voor CQ-4246794
* AEM Forms JEE-configuratiemanager werkt niet met meerdere NIC-kaarten. NPR-29236: Hotfix voor CQ-4268598
* AEM startfout van GemFire: java.lang.IllegalStateException: Er kan slechts één AdminDistributedSystem-verbinding tegelijk worden gemaakt. NPR-29524: Hotfix voor CQ-4266295
* NoClassDefFoundError omdat de jar-versie niet overeenkomt. NPR-28834: Hotfix voor NPR-28834

**Forms - Document Services**

* Ongeldig PDF/A-bestand wordt gerapporteerd als geldig PDF/A met de bewerking isPDFA. NPR-29076: Hotfix voor CQ-4261541
* PDF kan niet worden geconverteerd naar PDF/A-1b met formulierveld heeft geen weergavewoordenboek. NPR-29534: Hotfix voor CQ-4269618
* PDF/A-conversie van een PDF die is gemaakt met de Output Service, gaat niet over tot validatie bij Acrobat DC. NPR-29647: Hotfix voor CQ-4270448
* Apache POI-bundel mislukt, met een uitzondering. NPR-27861, NPR-28048: Hotfix voor CQ-4245898, CQ-4244778

**Forms - Designer**

* Toegevoegde PDF/UA-ondersteuning voor XFA-formulieren (XML Forms Architecture) die zijn gegenereerd met Designer en Output Service. NPR-23022

**Forms - Workflow**

* Verzending vanuit werkruimte mislukt vanwege Umlaut-teken. NPR-29087: Hotfix voor CQ-4263172

**Inclusief functiepakketten**

**Activa**

* Ondersteuning voor beheer van meerdere sites ingeschakeld voor middelen. Zie [Elementen opnieuw gebruiken met MSM voor elementen](/help/assets/reuse-assets-using-msm.md) voor meer informatie. NPR-26450: Hotfix voor CQ-4259922

**SDAB-pakketten en -inhoudspakketten**

In de volgende tekst wordt de lijst met OSGI-bundels en -inhoudspakketten in het GVB opgenomen.

Lijst van OSGi-bundels opgenomen in AEM 6.4.5.0

[Bestand ophalen](assets/6.4.5.0_bundles.txt)

Lijst van inhoudspakketten opgenomen in AEM 6.4.5.0

[Bestand ophalen](assets/6.4.5.0_OSGI.txt)

#### AEM 6.4.4.0 {#experience-manager-6440}

AEM 6.4.4.0 is een belangrijke update die prestaties, stabiliteit, veiligheid en belangrijkste klantenfixes en verhogingen omvat die sinds de algemene beschikbaarheid van AEM 6.4 in **April 2018 worden vrijgegeven.**

Het is ook cumulatief, wat betekent dat 6.4.4.0 alle AEM 6.4 de dienstpakken voorafgaand aan de versie omvat.

Enkele belangrijke hooglichten van AEM 6.4.4.0 zijn:

* De ingebouwde opslagplaats (Apache Jackrabbit Oak) wordt bijgewerkt naar versie 1.8.11.
* Toegevoegde steun voor caching de dienstversie om de frequente verzoeken van HTTP van de de dienstversie te vermijden.
* Extra ondersteuning voor het verwijderen van automatische tags.
* Er is eindeloos schuiven geïmplementeerd voor de wizard Catalogus.
* De gesteunde capaciteit om toestemmingen volgens communautaire plaatsen te beperken.
* Prestatieoplossingen (in cache plaatsen, asynchrone uitvoering, uitsluitingslijst) voor Sling Granite Content Health Check.
* De knop voor de kiezer is toegevoegd aan het dialoogvenster Paginaminiatuur.
* Nieuwe eigenschap toegevoegd om de positie van knopinfo in velden mogelijk te maken.
* Verbeterde ondersteuning voor ColorPicker in het veld Multifield.
* Er is een controle toegevoegd om lege waarden voor numerieke invoervelden in de clientlibs van Content Fragment te negeren.
* Ondersteuning ingeschakeld voor Microsoft Translator Text API v3.

**Activa**

* Migratie van ACS- en voorraadintegratie naar AEM 6.4.4.0 NPR-27632
* Publiceer later lege middelomslag met subfolders maakt de subomslagen verdwijnen. NPR-27558: Hotfix voor CQ-4254701
* Toevoeging van de eigenschap Eén tekenreeks zonder naamruimte\[\] leidt tot een onvolledige XMP. NPR-26805: Hotfix voor CQ-4254142
* Nadat de invoer-PDF is gerasterd, bevat de uitgevoerde uitvoer ontbrekende afbeeldingen. NPR-27929: Hotfix voor CTG-4150481
* De wizard Element verplaatsen geeft een onjuist aantal pagina&#39;s met verwijzingen naar gepubliceerde pagina&#39;s weer. NPR-27833: Hotfix voor CQ-4258014
* AssetPicker zoekt alleen in de eerste tag om het resultaat te filteren bij het filteren met tags. NPR-27778: Hotfix voor CQ-4257705
* AEM OTB PDF-handler blijft vastzitten bij het verwerken van PDF met externe tekens. NPR-28778: Hotfix voor CQ-4254234
* Wanneer een CSV-bestand een waarde heeft die door komma&#39;s in één kolom wordt gescheiden, ontspant AEM CSV-editor de komma niet en behandelt deze als een aparte kolom. NPR-28801: Hotfix voor CQ-4261694
* Probleem met de editor voor metagegevensschema wanneer u de padbrowser gebruikt om gegevens te selecteren. NPR-28674: Hotfix voor CQ-4263005
* Te veel elementen worden verwerkt naar de service Slimme inhoud, waardoor het periodiek labelen veel tijd in beslag neemt. NPR-28640: Hotfix voor CQ-4262661, CQ-4262644, CQ-4263234
* Bureaubladhandelingen werken niet voor de resultaten van het zoeken op de pagina `aem/start.html`. NPR-27242: Hotfix voor CQ-4248176
* De API voor middelen staat het uploaden van bestanden > 2 GB niet toe, waardoor het uploaden mislukt. NPR-27629: Hotfix voor graniet-23590
* Metagegevens worden niet opgeslagen in gedownload element in de eerste poging als Dynamic Media op de instantie is ingeschakeld. NPR-28233: Hotfix voor CQ-4260759
* Service resolver is niet gesloten in SiteCatalyst-configuratie. NPR-28015: Hotfix voor CQ-4259397
* Het verplaatsen van middelen in DAM leidt niet tot een vergelijkbare verplaatsing in Scene7 (p2p config). NPR-28313: Hotfix voor CQ-4261091

**Sites**

* (Klassieke UI) Een fractie levende exemplaren verschijnen in rollout lijst. NPR-28598, NPR-28574: Hotfix voor CQ-4263410
* LiveRelationshipManagerImpl genereert uitzonderingen wanneer cq:master leeg of ongeldig is. NPR-28590: Hotfix voor CQ-4263115
* De pagina&#39;s worden niet correct verwijderd door de optie uit het vak &#39;Verzoek tot verwijderen&#39;. NPR-28668: Hotfix voor CQ-4263195
* De gebruikersinterface voor de relatiestatus geeft geen juiste jaar- of tijdstempelwaarden weer voor verwante koraal-datepickervelden. NPR-28666: Hotfix voor CQ-4263661
* XSS (Cross-site scripting) in SuggestieHandler voor 6.4. NPR-28693: Hotfix voor CQ-4253821
* Map verplaatsen van sitebeheerder eindigt buiten geheugen en maakt AEM niet beschikbaar. NPR-28346: Hotfix voor CQ-4261398
* MSM LiveCopy-rollout-configuraties gaan na de update verloren. NPR-28311: Hotfix voor CQ-4258705
* Kan niet verder schuiven dan 40 blauwdrukconfiguraties. NPR-27640: Hotfix voor CQ-4239166
* Het gebruik van SyntheticResource als verwijzing genereert een Null-aanwijzeruitzondering en blokkeert de verplaatsing van de pagina&#39;s.  NPR-27576: Hotfix voor CQ-4258262
* PushOnModify werkt niet bij schrapping op 6.1 tot 6.4 promotieinstantie. NPR-28108: Hotfix voor CQ-4259833
* (Klassieke UI) Cancel overervingsknoop ontbreekt en de component is editable op een levende exemplaarpagina. NPR-28256: Hotfix voor CQ-4260161
* OakState0001: Onopgeloste conflicten bij rollout. NPR-27982: Hotfix voor CQ-4259548
* Wanneer het kopiëren/het kleven van een structuur die verwijzingen SyntheticResource bevat, eindigt het proces met een fout 500. NPR-27709: Hotfix voor CQ-4259179
* Kan actieve workflows niet beëindigen wanneer de taakbelasting wordt geactiveerd. NPR-27672: Hotfix voor CQ-4258520
* Bij rollout worden dubbele rollout-paden weergegeven na een upgrade van 6.1 naar 6.4. NPR-27845: Hotfix voor CQ-4259487
* Integreer de dam assetpicker modaal in de component van de paginaminiatuur. NPR-28131: Hotfix voor CQ-108042
* (Klassieke UI) Kan dialoogvensters met de widget Tags niet openen. NPR-28575: Hotfix voor CQ-4262680
* Bij het uploaden van bestanden met meerdere velden wordt de neerzetzone niet weergegeven. NPR-28676: Hotfix voor CQ-4263516
* Fout bij &#39;Ongeldige waarde van recursieselectiekader&#39; tijdens het migreren van een component van AEM 6.0 naar AEM 6.2. NPR-28609: Hotfix voor CQ-4241258
* De rijke Redacteur van de Tekst in dialoog is flikkerend wanneer het popover van een stop hoger is dan tekstgebied, vandaar, blokkerend om het even welk verder schrijven. NPR-27579: Hotfix voor CQ-4257440
* (Klassieke UI) cq:action editannotate werkt niet. NPR-28232: Hotfix voor CQ-4257703
* Als u tags verwijdert uit het deelvenster met tagfilterelementen van de pagina-editor, wordt de lijst niet correct vernieuwd. NPR-27983: Hotfix voor CQ-4245567
* Als de waarden voor getallen met meerdere velden leeg zijn en u op Opslaan klikt, wordt een oneindige laadvraag weergegeven zonder dat dit ooit gebeurt.  NPR-28400, NPR-28393: Hotfix voor CQ-4244058, CQ-4244349
* Met de machtiging Alleen lezen kunnen gebruikers/groepen geen XF selecteren en hebben ze geen optie om de XF en de pagina-eigenschappen ervan weer te geven. NPR-28341: Hotfix voor CQ-4260412
* De JSON-gegevens die van Target worden ontvangen, hebben een aantal escape-tekens waardoor de toepassingspagina wordt afgebroken. NPR-28318: Hotfix voor CQ-4252043
* Kan geen component bewerken na installatie AEM 6.4.3. NPR-28125: Hotfix voor CQ-4261216
* Het verwijderen van alle tags voor een tagveld blijft niet bestaan voor een gestructureerd inhoudsfragment. NPR-28133: Hotfix voor CQ-4247241
* Wanneer u een inhoudsfragment &quot;jcr:lastModified by&quot;- en &quot;jcr:lastModified&quot;-eigenschap bewerkt, worden waarden bijgewerkt zonder dat de gebruiker wijzigingen aanbrengt. NPR-27847: Hotfix voor CQ-4257138
* Content Fragments versioning compare diff improvements for AEM 6.4. NPR-27764
* Als er geen cq:allowedTemplates op /content/experience-fragments wordt bepaald en allowedPaths wordt gebruikt op het malplaatje van het Fragment van de Ervaring, wordt een fout geworpen wanneer het Fragment van de Ervaring wordt bewogen/gekopieerd. NPR-27487: Hotfix voor CQ-4257489
* De knop Maken wordt weergegeven wanneer u de nieuwe gebruiker vernieuwt. NPR-27335: Hotfix voor CQ-4255360
* Wanneer u een gepubliceerde pagina probeert te verplaatsen, is het aantal Pagina&#39;s waarnaar wordt verwezen op de eerste pagina van de wizard Pagina verplaatsen onjuist. NPR-28111: Hotfix voor CQ-4259663
* (Touch UI) References Rail geeft geen binnenkomende koppelingen weer. NPR-28529: Hotfix voor CQ-4262306
* Kan geen component- en pagina-eigenschappen bewerken nadat AEM 6.4.3 is geïnstalleerd. NPR-27998: Hotfix voor CQ-4261216, CQ-4260441
* Contextthub migreren naar jquery 3. NPR-28397: Hotfix voor GRANITE-19902

**Handel**

* Kan de catalogus niet selecteren als er zich meer dan 20 catalogi in een map bevinden. NPR-27649: Hotfix voor CQ-4258119
* De wizards van de handel &amp; eigenschapsmeningen worden gebroken wegens header.referer ontbrekend. Hotfix voor CQ-4261122

**Campagne - gericht**

* com.day.cq.personalization.impl.TeaserResourceEventHandler gaat in een oneindige lijn en veroorzaakt updates aan knopen op publicatieinstanties. Hotfix voor CQ-4263096

**Replicatie**

* Fout bij het samenstellen van replicatie-inhoud com.day.cq.replication.AccessDeniedException. NPR-28314: Hotfix voor CQ-4261401
* Het lek van de zitting wanneer identiteitskaart van de Agent van de Gebruiker aan admin in replicatieagent wordt geplaatst. NPR-28220: Hotfix voor CQ-4255517

**DAM - Creative Cloud**

* Ondersteuning voor HTTP API om vergelijkbare afbeeldingen te zoeken vanuit AEM Assets. Hotfix voor CQ-4254091
* Verbeter ACS API om de resultaten van een vraag toe te staan om tot de leden van een inzameling worden beperkt. Hotfix voor CQ-4258708

**DAM - Indelingen**

* Nadat het exporteren van metagegevens is geactiveerd, wordt de pagina omgeleid naar een pagina van 404. Hotfix voor CQ-4262447

**DAM - Algemeen**

* (Adobe Stock Integration) Server error modal wordt weergegeven met een Oauth-fout in het bestand error.log. Hotfix voor CQ-4260406
* Adobe Stock-integratie werkt niet als 6.4.4 wordt toegepast op 6.4.3. Hotfix voor CQ-4266009
* De verbinding aan het Model van CF ontbreekt zelfs na het toepassen van het flard van SP3. Hotfix voor CQ-4259029

**Platform**

* (Klassieke UI) Edit knoop is niet beschikbaar in de component van het Rapport van de Basis na bevordering aan 6.4.2. NPR-28560: Hotfix voor CQ-4262825
* Wanneer het gebruiken van een vraag die property.operation=like en property.depth combineert, eindigt het omhoog in een InvalidQueryException. NPR-28570: Hotfix voor CQ-4262652
* Interne serverfout wanneer het toegevoegde taalknooppunt van het overlaytaalknooppunt wordt verwijderd. NPR-28661: Hotfix voor CQ-4239194
* Null-aanwijzeruitzondering in sling-oak-1-thread van stderr.log bij willekeurig starten. NPR-28665: Hotfix voor CQ-4237845

**Felix**

* webconsole.plugins.memoryusage veroorzaakt een impasse bij verfrissen. NPR-27895:  Hotfix voor GRANITE-20715

**Graniet**

* Met de Sling Content Access Health Check wordt een lange overmatige /libs-validatie uitgevoerd voor het zoekpad naar de aangepaste resourceoplosser. NPR-28113: Hotfix voor GRANITE-23529

**Beheer van inhoudsfragmenten**

* Verbeteringen op gebied van bruikbaarheid en pariteit van functies met middelen voor inhoudsfragmenten. Hotfix voor CQ-4253883

**Gemeenschappen**

* Voer een upgrade uit van kwetsbare bootstrap naar 3.4 en ckeditor-bibliotheken naar 4.5.11. NPR-28490: Hotfix voor CQ-4257511
* Als u de bewerkingsmodi annuleert, wordt de verwijderde bijlage niet hersteld. NPR-27902: Hotfix voor CQ-4255150
* Samenstellen namens doos zou slechts aan de bevoorrechte leden zichtbaar moeten zijn. NPR-27900: Hotfix voor CQ-4251235
* Voeg rep:cache toe aan Genegeerde knooppunten bij AEM Communities User Sync Listener op publicatieinstanties. NPR-27842: Hotfix voor CQ-4247234
* Het zoekvak toont escape-teken op UI-niveau. NPR-27838: Hotfix voor CQ-4259757
* Er wordt een fout gegenereerd bij het zoeken naar speciale tekens zoals ( , +,? in quicksearch. NPR-28213: Hotfix voor CQ-4260969
* Maak een groep &#39;gemeenschapsspecifieke beheerders&#39; zodat de gebruikers de relevante communitysite kunnen bewerken en ontwerpen. NPR-27731
* Toegevoegde logica voor toetsenbordgebeurtenis om video te openen. NPR-27726: Hotfix voor CQ-4254026
* Toetsenbordnavigatie ingeschakeld voor AEM Communities Enablement-componenten bij Publiceren. NPR-27728: Hotfix voor CQ-4254028
* Label toegevoegd voor lijst- en kaartweergaveknop. NPR-27727: Hotfix voor CQ-4254027
* Behandeling van open resource resolver sessies in Social-Communities. NPR-27721: Hotfix voor CQ-4258714

**Vertaling**

* Ondersteuning bieden voor Microsoft Translator Text API v3. NPR-28366: Hotfix voor CQ-4249755
* jcr:language &amp; cq:language worden niet automatisch bijgewerkt in de vertaalde taal. NPR-28338: Hotfix voor CQ-4256046
* Cyclische verwijzingen veroorzaken StackOverflowError wanneer het creëren van taalexemplaar. NPR-27596: Hotfix voor CQ-4255621
* In een meertalig vertaalproject leidt het klikken sparen en het sluiten resultaten in verdere pagina&#39;s toevoegen aan het project tot nieuwe projecten in plaats van nieuwe vertaalbanen die in bestaand project worden gecreeerd. NPR-28219, NPR-28236: Hotfix voor CQ-4261276, CQ-4260731
* Fouttekenreeks is te lang wanneer inhoudsfragment met bulkgegevens wordt toegevoegd vanwege beperking van het aantal toegestane tekens. NPR-28722: Hotfix voor CQ-4262362

**Sociaal**

* Commentaar op de volgende pagina wordt elke keer dat een nieuwe opmerking wordt geplaatst, met geel gemarkeerd. Hotfix voor CQ-4261359
* Kan opmerkingen in door de gebruiker gegenereerde inhoud niet verwijderen met behulp van API. NPR-28075: Hotfix voor CQ-4261135
* AbstractNotificationOperationService cause ClassCastException. Hotfix voor CQ-4260456
* Verwijzing naar SCORM-cloud (Shareable Content Object Reference Model) in de speler verwijderen. Hotfix voor CQ-4260779

**UI - Foundation**

* De functie &quot;Filesystem output cache&quot; die in de HTML Client Library Manager is geïntegreerd, verbreekt de functie &quot;debugClientLibs&quot; voor gecompileerde scripts zoals LESS-bestanden. NPR-27249: Hotfix voor graniet-23313
* Het aantal elementen dat wordt weergegeven wanneer de foutopsporingsmodus is geactiveerd, is altijd 1 en er worden veel JS-fouten gegenereerd in de console van de browser.  NPR-27575: Hotfix voor GRANITE-23750
* Opslaan en sluiten op pagina-eigenschappen gaat niet terug naar de juiste pagina in AEM WAR met Tomcat. NPR-27566: Hotfix voor GRANITE-23671

**Integratie**

* `com.day.cq.personalization.impl.TeaserResourceEventHandler` gaat in een oneindige lijn en veroorzaakt updates aan knopen bij publicatie instanties. NPR-28561: Hotfix voor CQ-4263096
* De cq:acties worden niet in overweging genomen voor een doelcomponent. NPR-27616: Hotfix voor CQ-4257497
* LiveCopy-overervingsannulering werkt niet goed bij doelcontainers. NPR-28129: Hotfix voor CQ-4259813
* (Cloud Service Configs) Het selectievakje &quot;geërfd van&quot; dat op het hoofdniveau wordt weergegeven, moet worden verwijderd. NPR-27856:  Hotfix voor CQ-4259676

**Sling**

* Update to Sling Models API 1.3.8, Impl 1.4.10. NPR-27636: Hotfix voor GRANITE-23537

**OAK - Persistentie segment**

* SegmentBufferWriter wordt niet verwijderd na OnRC. NPR-27464

**Projecten**

* Het meertalige vertaalproject leidt niet tot veelvoudige taalbanen voor de gebruikers die geen deel van de beheerdersgroep uitmaken. NPR-28508: Hotfix voor CQ-4262023
* ProjectTaskListServlet lekt een ResourceResolver wanneer getTaskRenderers tijdens opstarten van de dienst wordt geroepen. NPR-27590: Hotfix voor CQ-4258011
* Als een map meer submappen bevat dan het paginaformaat en de volgorde op datum of grootte is, kan een fout niet meer dan de eerste pagina overschrijden. NPR-28867: Hotfix voor CQ-4265039
* XSS (Backport Cross-site scripting) is opgelost in DAM Viewers. NPR-28106:  Hotfix voor CQ-4253215
* Kan geen pagina&#39;s aan vertaalproject door project-beheerders toevoegen aangezien de verbinding om nieuwe pagina&#39;s aan het vertaalproject toe te voegen niet zichtbaar is. Hotfix voor CQ-4266334

**Workflow**

* Als we het dialoogvenster met volledige werkitems openen in het workflowbericht met een tagveld, wordt er een tag-eigenschap toegevoegd wanneer u op een kruismarkering klikt. NPR-28304: Hotfix voor CQ-4261321
* Knop Selectie van gebruiker in dialoogvenster Taak opnieuw toewijzen werkt niet. NPR-28963: Hotfix voor CQ-4264206

**Forms**

De belangrijkste markeringen voor AEM 6.4.4.0 vormen zijn:

* Toegevoegde ondersteuning voor het opnemen van API&#39;s voor documentbeveiliging voor ondertekening en certificering als transacties.

**Forms-invoegtoepassing**

**Adobe Sign-integratie**

* AEM 6.4 Forms Client SDK bevat geen pakket van adobesign-recipent. NPR-27735: Hotfix voor CQ-4259372

**Adaptieve Forms**

* Als het Wan-adaptieve formulier wordt gemaakt met een lege sjabloon, kunnen klanten geen onderliggende deelvensters maken in het hoofdvenster van het formulier. NPR-28758: Hotfix voor CQ-4264157
* Wanneer de waarde van het jaarveld van de datumcomponent 999 is, ontbreekt het bevestigingsmanuscript. NPR-28580: Hotfix voor CQ-4262620
* Wanneer een adaptief formulier wordt gemaakt met een lege sjabloon, kunnen klanten geen onderliggende deelvensters toevoegen aan het hoofdvenster van het formulier. NPR-28758: Hotfix voor CQ-4264157
* Kan geen waarde instellen tussen de velden van lazy geladen fragmenten van een adaptief formulier. NPR-27758: Hotfix voor CQ-4259703
* Het adaptieve formulier maakt geen gebruik van de Rich Text Editor, maar laadt de bibliotheken ervan.  NPR-27759:  Hotfix voor CQ-4259193
* Omleiden naar URL werkt niet voor adaptieve formulieren die zijn ingesloten in een AEM Sites-pagina. NPR-27620: Hotfix voor CQ-4239287
* Kan geen waarde instellen tussen de velden van lazy geladen fragmenten van een adaptief formulier. NPR-28320: Hotfix voor CQ-4262345
* Het adaptieve formulier maakt geen gebruik van de Rich Text Editor, maar laadt de bibliotheken ervan.  NPR-28001: Hotfix voor CQ-4259703, CQ-4259193
* Krabbelhandtekening werkt niet voor AEM Forms App die wordt uitgevoerd op Apple iOS 12.1. NPR-28497: Hotfix voor CQ-4261765
* Verzend Actie met gebruik van &#39;Forms Workflow&#39; Classic authoring issues in 6.4. Hotfix voor CQ-4252740
* Fout bij het verwerken van blok- en tmp-opslag. NPR-28806: Hotfix voor CQ-4264441

**Forms - Correspondentenbeheer**

* De interface van de agent kan de oorspronkelijke grootte van de afbeelding niet behouden. NPR-28800: Hotfix voor CQ-4259767
* CCR/Agent UI: Labels met datumvelden verschoven op het tabblad Gegevens. Hotfix voor CQ-4255499

**Forms - Transactierapport**

* Extra ondersteuning voor het tellen met digitale handtekeningen of voor het certificeren van een document als factureerbare transacties. NPR-28495: Hotfix voor CQ-4260236
* Digitale handtekening toegevoegd en certificeren aan Billable API. Hotfix voor CQ-4260236

**Forms Management**

Extra ondersteuning voor het vervangen van het gebruik van de client-bibliotheek met handgrepen door onderstrepingsteken in de wizard Forms Manager voor het controleren van het begin en het verplaatsen van elementen. NPR-27643: Hotfix voor CQ-4246536.
Eén bundel blijft geïnstalleerd na installatie van het Forms Management-pakket bij de release/640-tak. Hotfix voor CQ-4265410
Forms dat met bijlagen is verzonden, wordt niet weergegeven in de workflow met de verzendactie &quot;Invoke AEM Forms Workflow&quot; en het inschakelen van het portaal voor verzenden ingeschakeld. Hotfix voor CQ-4263110

**Forms - Ondersteunende integratie**

* Kan preprocessor en aangepaste verzending niet testen met Client SDK, hotfix voor CQ-4238469

**Forms JEE-installatieprogramma**

**Forms - Documentbeveiliging**

* Als u de updatebeleidsservice gebruikt, treedt er geen fout met het omsluitende object op. NPR-28751: Hotfix voor CQ-4252287
* Handtekening bouwt mislukt met oudere versie van commons-pkg. Hotfix voor CQ-4265535

**Forms - Foundation JEE**

* Wanneer AEM Forms is geïnstalleerd op IBM WebSphere, mislukt het maken van een formuliergegevensmodel op basis van SOAP. NPR-27923: Hotfix voor CQ-4251134
* SRT-hulpprogramma van PDF Generator kan geïnstalleerde versie van Adobe Acrobat niet detecteren. NPR-27971

**Forms - Designer**

* Sommige JPEG-afbeeldingen in een XDP-sjabloon worden niet correct gerenderd.  NPR-26702: Hotfix voor LC-3917457

**Forms - Workflow**

* HTML5 Forms met standaard verzendproces in an.lca werkt niet op JBoss 7. NPR-28675: Hotfix voor CQ-4243928
* Kan geen PDF forms verzenden in HTML-werkruimte. NPR-28058: Hotfix voor CQ-4260373
* De gegevens van de klant worden afgedrukt in informatielogboeken gebruikend de Forms Workflow van de Dienst van Invoke FDM. Hotfix voor CQ-4260385

**Inclusief functiepakketten**

**Sites**

* Content Fragments versioning compare difference improvements for AEM 6.4.  NPR-26760: FP voor CQ-4248839
* Verschillende verbeteringen in de variatieverschillen tussen inhoudsfragmenten voor AEM 6.4.  NPR-27866: FP voor CQ-4248839
* Ingeschakelde functie in OSGI-configuratie **AEM Workflow Intrekfunctie Flag**. De actie intrekken moet de werkstroominstantie beëindigen nadat de markering is ingesteld. NPR-26451: Hotfix voor CQ-4259090

**Platform**

* Uitgebreide Query Builder Facet Extraction hefboomwerking Oak API voor 6.4. NPR-26674: KP voor CQ-4230337

**SDAB-pakketten en -inhoudspakketten**

In de volgende tekst wordt de lijst met OSGI-bundels en -inhoudspakketten in het GVB opgenomen.

Lijst van OSGi-bundels opgenomen in AEM 6.4.4.0

[Bestand ophalen](assets/bundles_6_4_4_0.txt)

Lijst van inhoudspakketten opgenomen in AEM 6.4.4.0

[Bestand ophalen](assets/osgi_package_6_440.txt)

#### AEM 6.4.3.0 {#experience-manager-6430}

AEM 6.4.3.0 is een belangrijke update die prestaties, stabiliteit, veiligheid en belangrijkste klantenfixes en verhogingen omvat die sinds de algemene beschikbaarheid van AEM 6.4 in April 2018 worden vrijgegeven.

Het is ook cumulatief, wat betekent dat 6.4.3.0 alle AEM 6.4 de dienstpakken vóór het vrijgeven omvat.

Enkele belangrijke hooglichten van AEM 6.4.3.0 zijn:

* De ingebouwde opslagplaats (Apache Jackrabbit Oak) wordt bijgewerkt naar versie 1.8.9.
* Toegevoegde ondersteuning voor de eigenschap allowedPaths op sjablonen voor adaptieve formulieren.
* Uitgebreide, op het deelvenster gebaseerde zoekopdracht naar middelen in AEM
* XSS-oplossingen (Cross-site scripting) op de aanmeldingspagina.
* Verbeterde UI-instrumentatie.
* Verbeteringen in de verwerking van FormData.
* Verbeterde verwerking van itemnaamgeving in een multiveld.
* Verbeterde verwerking van plaatsaanduidingsitems (Kaartweergave en Lijstweergave) tijdens de selectie.
* Toegevoegde Adobe IMS-verificatie en ondersteuning voor Admin Consoles voor Managed Services.

**Activa**

* De workflow voor DAM-updatebronnen haalt geen verwijzingen uit INDD-bestanden als de optie IDS-decouple is ingeschakeld. NPR-26243; Hotfix voor CQ-4250933
* Het succesbericht wordt niet weergegeven wanneer elementen worden gepubliceerd met de Redacteur van het Bulk van de Activa. NPR-26252; Hotfix voor CQ-4251688.
* Nadat u een element uit een zoekresultaat hebt bekeken en op de knop Terug in de browser hebt geklikt, verschijnt het foutbericht &#39;Onjuist verzoek&#39; met 400 foutcode. NPR 26578; Hotfix voor CQ-4253741
* De activa meta-gegevens tonen ongeldige namespace fout na het installeren van een de dienstpak. NPR-22341; Quickfix voor CQ-4237202
* De optie om mappen en inhoudsfragmenten opnieuw te ordenen in de lijstweergave wordt niet weergegeven voor de toepasselijke mappen. NPR-27153; Hotfix voor CQ-4255873
* Gebruikers kunnen geen elementen toevoegen aan een nieuwe verzameling, omdat dit resulteert in een foutbericht met een verbroken afbeelding in het dialoogvenster met het pop-upvenster met fouten. NPR-22431; Hotfix voor CQ-4237086
* Cascading dropdown wordt niet ondersteund op dynamische vervolgkeuzelijsten. NPR-27043; Hotfix voor CQ-4252564
* Als gebruikers een niet-standaardwaarde voor de &quot;Omslag van de Wortel van het Bedrijf&quot;in de DMS7 wolkenconfiguratie plaatsen, werkt de Kijker Vooraf ingesteld niet zoals verwacht. NPR-26360; Hotfix voor CQ-4249505
* De rapportage van activa mislukt voor gevallen met een zeer groot aantal activa. NPR-27278; Hotfix voor CQ-4256748
* Submappen nemen het SmartCrop-afbeeldingsprofiel van de bovenliggende map niet over. NPR-27197; Hotfix voor CQ-4256273
* Wanneer Dynamic Media-integratie is ingeschakeld, worden sommige eigenschappen van metagegevens van Elementen gewijzigd. De breedte, de hoogte en de locatiekenmerken worden niet weergegeven. NPR-27203; Hotfix voor CQ-4256258
* Dynamic Media gebruikt de geconfigureerde proxy niet voor bepaalde typen elementen. NPR-25211; Hotfix voor CQ-4244871
* De pagina van de Editor van metagegevens bevat Null-aanwijzeruitzondering voor een ongeldige itemparameter. NPR-26169; Hotfix voor CQ-4241368.
* Als een drop-down een keuzeregel heeft en een vereiste die regel op het wordt toegepast, kan de vereiste regel niet in de meta-gegevensredacteur worden voldaan. NPR-27479; Hotfix van CQ-4251428

**Sites**

* Een gebruiker kan de rijke eigenschappen van de tekstredacteur op het volledig scherm in lijn controleren het gebruiken van inhoudsbeleid, maar kan niet de Edit Dialog rijke tekstreddereigenschappen met inhoudsbeleid controleren. NPR-26750: Hotfix voor CQ-4241130
* De rijke tekstredacteur wordt onbruikbaar wanneer geschakeld van volledig scherm aan het drijven dialoog. De zwevende weergave bevat twee teksteditors met opmaak. NPR-25589: Hotfix voor CQ-4206008
* Wanneer op een tekstveld op de Enter-toets wordt gedrukt, schakelt de Rich Text Editor over naar de modus Volledig scherm. NPR-26204: Hotfix voor CQ-4245893
* De plug-in List van de RTF-editor wordt automatisch uitgeschakeld en wijzigingen worden niet toegestaan. NPR-26507: Hotfix voor CQ-4239387
* Wanneer een speciaal teken aan het venster van de RTF-editor wordt toegevoegd, schuift het venster naar de bovenkant. NPR-26435: Hotfix voor CQ-4249869
* Clientcontextsegment.js in cache plaatsen tegenover vragen die niet in cache zijn geplaatst. NPR-26622: Hotfix voor CQ-4253486
* Wanneer een kindregel van de auteursinstantie aan de publicatieinstantie wordt geactiveerd, houdt het publiceren instantie op werkend. NPR-26601: Hotfix voor CQ-4253588
* Wanneer de rijke tekstredacteur met veelvoudige gebieden wordt gecombineerd, Uncaught TypeError: fieldAPI.getName is geen functie bij foundation.js fout komt voor. NPR-27146: Hotfix voor CQ-4253155
* De integratie van Salesforce kan niet de volmachtsconfiguratie gebruiken. NPR-27244: Hotfix voor CQ-4245300
* Wanneer u een pagina voor activering plant met de optie Publicatie beheren voor een latere datum en overschakelt naar de lijstweergave, ontbreekt het kalenderpictogram. NPR-26974: Hotfix voor CQ-4239206
* Gebruikers kunnen machtigingen voor gesloten gebruikersgroepen niet bewerken in de pagina-eigenschappen. NPR-27138: Hotfix voor CQ-4256089
Kan codes niet bewerken via labelen. NPR-26957: Hotfix voor CQ-4254858
* Wanneer een tag waarnaar wordt verwezen vanuit een gestructureerd inhoudsfragmentmodel wordt verplaatst, worden de bestaande verwijzingen naar de tag in een inhoudsfragment niet bijgewerkt. Dit gebeurt in het bewerkingsscherm van het inhoudsfragmentmodel. NPR-26776: Hotfix voor CQ-4251805
* Wanneer u een opstart met meerdere pagina&#39;s maakt en promoot, worden er meerdere versies voor elke pagina gemaakt. NPR-26917: Hotfix voor CQ-4254663
* AEM sitebeheerder verwerkt geen paden die in de adresbalk van de browser worden getypt. NPR-26780: Hotfix voor CQ-4254097
* Wanneer een pagina naar een nieuwe locatie wordt verplaatst zonder de naam ervan te wijzigen, gaat de versiegeschiedenis van de pagina verloren. NPR-26706: Hotfix voor CQ-4254025
* URL&#39;s in de ervaren fragmentbeheereditor staan geen overlays toe. NPR-26319: Hotfix voor CQ-4252156
* Wanneer een pagina wordt gemaakt met een sjabloon die een leeg ervaringsfragment bevat en wordt gepubliceerd, kan de pagina niet worden geopend en treedt een DefaultSlingScript-fout op. NPR-26305: Hotfix voor CQ-4252460
* Wanneer data-smart-use met klassen met identieke naam wordt gebruikt, wordt niet-compatibele code geproduceerd. NPR-27282: Hotfix voor Sling-7581
* Na de installatie van verbeteringsSP, hebben de plaatsen lege configuratie van de blauwdruk rollout. NPR-27609: Hotfix voor CQ-4257078

**DAM - Brand Portal**

* De predikaten van de markering worden niet gepubliceerd wanneer de vorm van het meta-gegevensschema aan het Portaal van het Merk wordt gepubliceerd. Hotfix voor CQ-4256218
* Wanneer een map op het derde niveau van AEM naar Brand Portal wordt gepubliceerd zonder dat de bovenliggende mappen worden gepubliceerd, verandert de mapnaam. Hotfix voor CQ-4255423
* De voorspellingen van de padbrowser worden gepubliceerd van AEM Assets naar Brand Portal, zoals u had verwacht. Het gepubliceerde pad bij BP blijft echter /content/dam, die moet worden bijgewerkt. Hotfix voor CQ-4256240

**DAM - Creative Cloud**

* Het pictogram Zoekmiddelen Adobe ontbreekt in de AEM hoofdnavigatie. Hotfix voor CQ-4254343

**DAM - DM-client**

* Nadat u video&#39;s hebt ingevoerd in een map die is gekoppeld aan het AVS Video Processing Profile, wordt het browservenster telkens vernieuwd. Hotfix voor CQ-4253563
* Publiceren op YouTube mislukt wanneer u een ad-hoctag gebruikt die hoofdletters bevat. Hotfix voor CQ-4252477
* Wanneer een annotatie wordt gemaakt in een element zoals PDF, wordt een oneindige pagina vernieuwd. NPR-27052: Hotfix voor CQ-4255396

**DAM - DM Services**

* Dynamic Media gebruikt de geconfigureerde proxy niet voor bepaalde typen elementen. NPR-10727; Hotfix voor CQ-4244871

**Platform**

* Prestatieproblemen met org.apache.sling.i18n. NPR-26812: Hotfix voor SLING-7543
* Kan de knoopeigenschappen niet zien wanneer de invoer-XML is opgemaakt en geïmplementeerd. NPR-26198: Hotfix voor CQ-4250448
* IndexOutOfBoundsException in ResourceProviderTracker. NPR-26968: Hotfix voor GRANITE-23310
* De JMX-console accumuleert een groot aantal beheersessies en elke 5 minuten wordt een nieuwe sessie geopend. NPR-26958: Hotfix voor CQ-4251090
* Na een upgrade van 6.2 naar 6.4 geeft het logbestand stacktracering weer voor niet-gesloten bronnenoplosser com.adobe.granite.repository.hc.impl.content.sling.SlingContentHealthCheck. NPR-26176: Hotfix voor graniet-21734
* Wanneer een uit-van-de-doos afstotingsagent van de verzender wordt gevormd om aliassen bij te werken, ontbreekt de verrichting met een StackOverflowError. NPR-26373: Hotfix voor CQ-4242928
* De replicatie gebruikt verlopen Token OAuth tot het ontbreekt. NPR-25894
* Beperkte pagina (pagina voor gesloten gebruikersgroep) met sling: alias leidt de gebruiker niet naar de aanmeldingspagina. NPR-25715: Hotfix voor graniet=22263
* Bij het publiceren van tags wordt geen activiteit weergegeven in de gebruikersinterface. Hotfix voor CQ-4255961
* Kan codes niet bewerken in klassieke UI. Hotfix voor CQ-4258697
* Bijgewerkt org.apache.felix.http.bridge naar versie 4.0.4. NPR-27038: Steun voor graniet - 2334
* Activiteitenlogbestanden voor pakketbeheer moeten worden uitgepakt in een afzonderlijk logbestand. NPR-27323: Hotfix voor graniet-14866
* De validator van het pakket rapporteert geen overlays in GVB. NPR-27119: Hotfix voor GRANITE-22825

**Projecten**

* ACS API verwerkt paginering met alleen onderliggende submappen. NPR-27617: Hotfix voor CQ-4258639

**OAK**

* Kan niet aanmelden bij de repository na installatie van AEM 6.4 Service Pack 2. NPR-27171: Hotfix voor graniet-23317

**Replicatie**

* Het controlelogboek blijft open met actieve sessies die voortdurend toenemen met ~750 per dag. NPR-27062: Hotfix voor CQ-4241350

**Gemeenschappen**

* Boven op de tweede pagina worden forumberichten en reacties toegevoegd en als het bericht wordt vernieuwd, wordt het naar de juiste locatie vóór de eerste pagina geplaatst. NPR-27342: Hotfix voor CQ-4247338
* Koppelingen naar alle bronnen zetten het contextpad (/aempublish) na het schuiven neer. NPR-26982: Hotfix voor CQ-4254345
* Toegevoegde groepen zijn niet zichtbaar in de Communautaire Managers, de Moderatoren van de Gemeenschap en het Privileged drop-down Lid bij het uitgeven van een gepubliceerde plaats. NPR-27190: Hotfix voor CQ-4258574
* Er worden slechts 10 groepen vermeld op de pagina met bronnen voor activering, zelfs als paginering is ingeschakeld voor een groepslijst. NPR-26934: Hotfix voor CQ-4252985
* De optie om onderzoek naar Geplande Post in dagboekcomponent toe te laten/onbruikbaar te maken wordt verstrekt in ConfigMgr, en de baan SearchScheduledPosts wordt geoptimaliseerd. NPR-26923: Hotfix voor CQ-4250463
* Zoeken op trefwoorden in adres werkt niet op de pagina met agendacomponenten wanneer AEM gemeenschap is ingesteld op werken met DSRP. NPR-26737: Hotfix voor CQ-4258493
* Geïmplementeerde directe verbinding met de commentaar in plaats van de belangrijkste post in de detail van een commentaar, voor moderatie UI &amp; enablement middelen. NPR-26704: Hotfix voor CQ-4251381
* Inhoud die via multiselection op moderatieconsole wordt gemodereerd, wordt niet weergegeven bij Activiteitenstroom. NPR-26695: Hotfix voor CQ-4253244
* Als u met Voornaam en Achternaam zoekt in het veld Aan van Communityberichten, wordt het verwachte resultaat niet geretourneerd. NPR-26385: Hotfix voor CQ-4248673
* Er is een fout opgetreden tijdens het uploaden van een bijlage buiten de afbeelding (bijvoorbeeld .pdf) in het forum. NPR-27360: Hotfix voor CQ-4257753
* Een forumpost vrijmaken of de functie hiervan ongedaan maken werkt niet als Auteur-Publiceren is ingesteld met MySQL DSRP. NPR-26125; Hotfix voor CQ-4251520
* De componenten van de inzameling (forums, blogs, kalender, ideatie, QnA) hebben nu een bezit in de componentendialoog om &quot;Blokkeren UGC in Auteur uit te laten - geef wijze uit&quot;, om UGC toe te staan/te ontkennen lading in WCM geeft wijze uit. NPR-26978: Hotfix voor CQ-4248161
* Zoekopdracht voor tags werkt niet voor gelokaliseerde zoektermen. NPR-26171: Hotfix voor CQ-4249926
* Met de knop Terug slaat u een pagina in de forumzoekopdracht over. NPR-26950: Hotfix voor CQ-4254804
* AEM instantie die op standaardHttp-poort (80) wordt uitgevoerd, kan imsmanifest.xml niet bereiken. NPR-27173: Hotfix voor CQ-4252211
* Opmerking verwijderen als antwoord voor QnA werkt niet als AEM Communities is ingesteld met DSRP. NPR-26247: Hotfix voor CQ-4252232
* Kan Adobe-opslag niet aanroepen: 414 fout - Lange GET-URI waargenomen wanneer gebruikers zoeken in /content/community-components/en/search.html en auteurveld selecteren als een van de filters voor die zoekterm. NPR-26643: Hotfix voor CQ-4251303
* De neerzetwaarde voor DataCenterURL in de configuratie van ASRP wordt veranderd van Dallas in Virginia (voor VA6). NPR-26936: Hotfix voor CQ-4254434
* Speciale tekens in forumzoekfouten of geen resultaten. NPR-26930: Hotfix voor CQ-4247744
* Het aantal dat voor &quot;Aantal resultaten&quot;in forumonderzoek wordt getoond gebruikt onjuiste afbakening voor Engelse en Duitse scènes. NPR-27050: Hotfix voor CQ-4248939
* Ongelezen meldingen nemen niet toe na 21. NPR-26946, NPR-27480: Hotfix voor CQ-4252829, CQ-4256939
* Met paginering in de opmerkingensectie van een component kunnen gebruikers omhoog schuiven om de pagina-inhoud te zien, waarbij ze een pagina bereiken via paginering. NPR-27032: Hotfix voor CQ-4251228
* U kunt niet op een miniatuurafbeelding klikken in de map Community Site wanneer u deze weergeeft vanuit de beheerconsole op een AEM-auteur-exemplaar. NPR-26986: Hotfix voor CQ-4254036
* Met de optie Alle gelezen tekens markeren worden alleen de eerste 10 berichten als gelezen gemarkeerd en blijven andere ongelezen totdat een pagina wordt vernieuwd. NPR-27037: Hotfix voor CQ-4254058
* Paginering wordt niet geactiveerd voor Ideatie en de lijst met onderwerpen (of antwoorden) wordt langer, tenzij deze opnieuw wordt geladen. NPR-26193: Hotfix voor CQ-4252104
* De activiteiten van andere gebruikers en schrapte UGC zichtbaar bij het aanmelden met moderatorgeloofsbrieven en het toevoegen &quot;#social-activities&quot;of &quot;#tabs-2&quot;aan het eind van het profiel van de moderator URL. Hotfix voor CQ-4251355
* Niet alle toegewezen tags kunnen uit een blogartikel worden verwijderd. NPR-26851: Hotfix voor CQ-4253359
* Relaties met UGC worden niet verwijderd bij UGC-verwijdering. NPR-27630: Hotfix voor CQ-4258706
* De koppeling naar reacties werkt niet bij een klik op de antwoorden van het forum. NPR-27623: Hotfix voor CQ-4256138
* De limiet voor gebruikersabonnementen is beperkt tot 1000. NPR-27614: Hotfix voor CQ-4254689
* Als u een site bewerkt en rollen bewerkt in de rolinstellingen, wordt er een Null-aanwijzeruitzondering gegenereerd. NPR-27377; Hotfix voor CQ-4255909

**Vertaling**

* De voorvertoning van de vertaling werkt niet met de voorbeeldinhoud &#39;we.Retail&#39;. NPR-26727: Hotfix voor CQ-4241179

**UI - Foundation**

* Een NullPointerException is teruggekeerd wanneer het proberen om configuraties na bevordering aan AEM 6.4 te downloaden. NPR-27310: Hotfix voor graniet-23573
* De pro-actieve Steun voor granite.platform.login moeilijke situaties. NPR-26941
* Proactieve back-up voor granite.ui.content-oplossingen. NPR-26294
* De component van het gebied van het aantal bevestigt negatieve aantallen niet op Internet Explorer 11. NPR-26701
* Proactieve back-up voor granite.ui.coralui3-oplossingen. NPR-26662
* Proactieve back-up voor granite.ui.coralui3-eon-oplossingen. NPR-26666
* Proactieve back-up voor oplossingen van granite.ui.foundation.components. NPR-27313
* Proactieve back-up voor granite.ui.commons-oplossingen. NPR-26753
* De pro-actieve Steun UI van de Stichting steunt. NPR-26248

**Integratie**

* Wijzigingen in AEM ervaringen die met de doelengine zijn gemaakt, worden niet gepubliceerd. NPR-24869: Hotfix voor CQ-4247832
* Kan geen veelvoudige activiteiten en ervaringen tot stand brengen als hun namen Japanse karakters omvatten. NPR-27271: Hotfix voor CQ-4256857
* Start-API-eindpunt bijwerken. NPR-26790: Hotfix voor CQ-4254380
* (Personalisatie) BrandsRetriever loopt de volledige boom. NPR-27060: Hotfix voor CQ-4255790

**WCM - Admin UI**

* Er is een HTTP-test toegevoegd voor het publiceren/verwijderen van een pagina met referenties en een UI-test voor Live Copy. Hotfix voor CQ-4256894

**WCM - Pagina-editor**

* De werkbalk Bewerken wordt uitgeschakeld voor de onderdelen die u het eerst bewerkt. Hotfix voor CQ-4253270

**Forms**

De belangrijkste markeringen voor AEM 6.4.3.0 vormen zijn:

* Ingeschakelde ondersteuning voor een array/lijst met objecten met dynamische entiteitsvervanging.
* FIPS-compatibiliteit is ingeschakeld voor Reader Extended-workflow in Digital Signature, Reader Extensions, CryptoProvider en TrustStore.
* PDF/UA-ondersteuning toegevoegd aan XFA-formulieren die zijn gegenereerd met Designer of Output Service.
* Ondersteuning ingeschakeld voor de eigenschap allowedPaths op sjablonen voor adaptieve formulieren.
* Toegevoegde JBoss 7.1.4-ondersteuning voor AEM Forms 6.4.

**Forms-invoegtoepassing**

**Backend-integratie**

* Kan modeltoewijzingen van formuliergegevens niet invullen op basis van dynamische entiteiten in SOAP-reactie. NPR-26428: Hotfix voor CQ-4250639
* De waarde voor _elementNamespace in formuliergegevensmodel met aanvullende gegevens die zijn ingevoerd met de testinterface, wordt niet correct weergegeven in de SOAP-aanvraag. Hotfix voor CQ-4255373
* Een nullable bezitsbeperking wordt geïnitialiseerd met een standaardwaarde en kan niet met FDM worden gesynchroniseerd. Hotfix voor CQ-4253873
* De standaardwaarde voor het nullable bezit wordt niet geplaatst aan Waar voor OData gegevensbron. Hotfix voor CQ-4253870

**Adaptieve Forms**

* Kan sites en formuliereditor niet laden. NPR-26977; Hotfix voor CQ-4249170
* Problemen tijdens het toevoegen van een bijlage aan een adaptief formulier met het toetsenbord. NPR-25913; Hotfix voor CQ-4249456

**Forms - Interactieve communicatie**

* Kan een deelvenster dat is toegevoegd met de optie Onderliggend deelvenster toevoegen niet verplaatsen naar de inhoudsstructuur in het webkanaal voor interactieve communicatie en in adaptieve formulieren. Hotfix voor CQ-4253915
* De namen van de lijst worden getoond in plaats van de titel van de vereniging FDM in de sectie van Gegevensbronnen van het kanaal van de Druk. Hotfix voor CQ-4253669
* De functie isUseXFABullets() is niet uitgeschakeld in de klasse PrintChannelRenderOptions en is beschikbaar in de client-SDK. Hotfix voor CQ-4246583, CQ-4252700

**Correspondentenbeheer**

* Javadocs voor 6.4 bevatten niet com.adobe.dbforms.* en de bijbehorende klassen. Hotfix voor CQ-4253200
* CCR UI toont een standaard junkwaarde voor het datumgebied voor het geval dat er geen input van de XML van testgegevens is. Hotfix voor CQ-4252041
* Als een letter een lijstmodule bevat, gaat de ruimte tussen opsommingstekens en tekst verloren tijdens het genereren van een PDF van de letter. Hotfix voor CQ-4250588

**Forms Manager**

* Ondersteuning ingeschakeld voor de eigenschap allowedPaths op sjablonen voor adaptieve formulieren. NPR-26598: Hotfix voor CQ-4255892

**Forms - Workflow**

* Als accolades zijn opgenomen in de taaknaam terwijl de Forms-workflow wordt uitgevoerd, wordt een uitzondering weergegeven in de logboeken. Hotfix voor CQ-4256626
* Kan een zoeksjabloon niet openen in de AEM Forms-werkruimte. Hotfix voor CQ-4255651

**Mobile Forms**

* Het afsluitingsbericht wordt niet weergegeven wanneer het datumveld wordt verlaten in AEM Forms dat in Internet Explorer of Chrome als HTML is weergegeven. NPR-26483: Hotfix voor CQ-4239352
* Datums in de XML wanneer de verwerking begint, geven de formulieren een validatiefout weer wanneer de gebruiker het formulier probeert te verlaten. NPR-26787: Hotfix voor CQ-4251211

**Forms JEE-installatieprogramma**

**PDF Generator-service**

* Kan instellingen voor rapportage over standaarden en compatibiliteit voor PDF Generator niet weergeven. NPR-26715: Hotfix voor CQ-4253384
* Convertpdf binair dossier ontbreekt in het toe:voegen-on pakket van AIX Forms, dat mislukking veroorzaakt terwijl het aanhalen van de dienst PDFA. Hotfix voor CQ-4257873
* De service voor het vastleggen van papier loopt vast tijdens het verwerken van TIFF-bestanden. NPR-28079:  Hotfix voor CQ-4240649

**Document Services**

* Voeg FIPS-compatibiliteit toe voor de RE-workflow in Digital Signature, Reader Extensions, CryptoProvider en TrustStore. NPR-27495: Hotfix voor CQ-4257572
* De omzetting ontbreekt terwijl het runnen van de dienst AssemblerService.toPDFA in een lijn. NPR-26354: Hotfix voor CQ-4248656
* Kan de compatibiliteit met PDF&#39;s niet correct valideren op basis van PDF/A-1b-standaarden. NPR-26286: Hotfix voor CQ-4227539
* Onvoldoende geheugen tijdens het upgraden van AEM Forms van 6.1 SP2 GVB5 naar GVB13. NPR-26285: Hotfix voor CQ-4244379
* Kan de compatibiliteit met PDF&#39;s niet op de juiste wijze valideren op basis van PDF/A-standaarden. NPR-26272: Hotfix voor CQ-4248823

**Forms - Foundation JEE**

* Toegevoegde JBoss 7.1.4-ondersteuning voor AEM Forms 6.4. NPR-27331; Hotfix voor CQ-4255601

**Functiepakketten inbegrepen**

* Ingeschakelde ondersteuning voor een array/lijst met objecten met dynamische entiteitsvervanging. NPR-26590: Hotfix voor CQ-4254655

**SDAB-bundels en inhoudspakketten inbegrepen**

Lijst van OSGi-bundels opgenomen in AEM 6.4.3.0

[Bestand ophalen](assets/6.4.3.0_bundles.txt)

Lijst van inhoudspakketten opgenomen in AEM 6.4.3.0

[Bestand ophalen](assets/6.4.3.0_OSGI.txt)

#### AEM 6.4.2.0 {#experience-manager-6420}

AEM 6.4.2.0 is een belangrijke update die prestaties, stabiliteit, veiligheid en belangrijkste klantenfixes en verhogingen omvat die sinds de algemene beschikbaarheid van AEM 6.4 in **April 2018 worden vrijgegeven.**
Het is ook cumulatief, wat betekent dat 6.4.2.0 alle AEM 6.4 de dienstpakken voorafgaand aan de versie omvat.

Enkele belangrijke hooglichten van AEM 6.4.2.0 zijn:

* De ingebouwde opslagplaats (Apache Jackrabbit Oak) wordt bijgewerkt naar versie 1.8.7.
* Toegevoegde ondersteuning voor HTML Template Language (HTL) Specification 1.4-functies
* Toegevoegde ondersteuning voor MongoDB Enterprise 3.6.
* De redacteur van de Pagina van Plaatsen voegt steun voor in-context het uitgeven en samenstelling met cliënt-zijcomponenten toe bouwt in React of Hoekig in combinatie met <a href="../sites-developing/spa-walkthrough.md">AEM Redacteur JS SDK</a>.
* Verbeteringen voor inhoudsfragmenten: heeft de mogelijkheid toegevoegd om notities aan te brengen in tekstvelden en versies naast elkaar te vergelijken.
* Toegevoegde [integratie met Adobe Stock](/help/assets/aem-assets-adobe-stock.md) zodat de gebruikers Adobe Stock-middelen rechtstreeks vanuit AEM gebruikersinterface kunnen zoeken, voorvertonen, opslaan en in licentie geven. Zie [Adobe Stock-elementen gebruiken met AEM Assets](https://docs.adobe.com/content/help/en/experience-manager-learn/assets/creative-workflows/adobe-stock.html) voor meer informatie.
* De activa toegevoegde steun voor dynamische voorwaardelijke metaschema en de capaciteit om een meta-gegevensschema voor activaomslagen te plaatsen.
* Toegevoegde configuratie in elke component om de functionaliteit voor het maken/bijwerken van de mapminiatuur in of uit te schakelen.
* Verbeteringen in de afbeeldingseditor bij het ontwerpen van pagina&#39;s.
* Regressiereparatie in Communities voor scoring-gebeurtenis die niet goed wordt afgehandeld in het geval dat een geselecteerd antwoord wordt verwijderd.
* De maximale zoekresultaatlimiet voor solr is gewijzigd in MAX_INT-10000.
* De baan van de Flush van de transactie is begonnen slechts op de eerste vraag to storeTransaction.
* De knop Alles selecteren is nu beschikbaar in de Kaart- en kolomweergave.
* Verbeterde toegankelijkheid in CoralUI.
* Verbeterde verwerking van Coral.Keys.
* Bijgewerkt moment.js tot 2.22.2
* Bijgewerkte jQuery naar 1.12.1
* Introductie van de stichting-werkstroomstatuscomponent.
* Bijgewerkte GCC naar de nieuwste versie.
* SAML naar nieuwe externe IDP-synchronisatie verplaatsen.

**Activa**

* Het genereren van subelementen voor het pptx-bestand bevat geen afbeeldingen en miniaturen. NPR-24286: Hotfix voor CQ-4217986
* migrateAllAssets - Voeg ondersteuning toe voor batchverwerking en verbeter AEM methode die UUID toevoegt aan oude elementen. NPR-24861: Hotfix voor CQ-4242863 en CQ-4247874
* Prestatieprobleem bij het genereren van miniaturen. NPR-24693: Hotfix voor CQ-4246960
* (Touch UI) De component &quot;options preate&quot; blijft leeg wanneer deze wordt toegevoegd aan de uitgeverspagina voor het delen van bedrijfsmiddelen. NPR-24643: Hotfix voor CQ-4245295
* (Workflow) Slimme tagelementen worden niet verwerkt door de proxyconfiguratie. NPR-25840: Hotfix voor CQ-4248202
* (Openbaar zoeken) Als u bestandstype:afbeelding verwijdert uit zoekcriteria, wordt het afbeeldingstype niet verwijderd. NPR-25232: Hotfix voor CQ-4248280
* Wanneer u een bestand naar een andere map probeert te verplaatsen, worden mappen met een apostrof in de naam niet weergegeven. NPR-25125: Hotfix voor CQ-4248660
* De schuifregelaar op de pagina Subelement werkt niet correct als de taalvoorkeur is ingesteld op anders dan Engels. NPR-25274: Hotfix voor CQ-4248489
* Probleem met csv-bestand voor het exporteren van metagegevens wanneer het wordt geopend op computers met een Europese getalnotatie. NPR-26009: Hotfix voor CQ-4250677
* De knop Maken is niet beschikbaar in de selectie van de elementmap zonder de machtiging Verwijderen. NPR-25788: Hotfix voor CQ-4250140
* (Backport) Verbeterde toegankelijkheid: Duplicaat-id: ID-kenmerkwaarde moet uniek zijn, Label: Formulierelementen moeten labels en koppelingsnaam hebben: Koppelingen moeten duidelijke tekst hebben. NPR-24252: Hotfix voor CQ-4250905, CQ-4250906, CQ-4250907
* Het uploaden van een CSV met velden gescheiden met &quot;,&quot; mislukt voor Europese landen. NPR-25549: Hotfix voor CQ-4249931
* (Brand Portal) Subassets van een PDF-bestand met meerdere pagina&#39;s worden niet gepubliceerd wanneer een element wordt gepubliceerd. NPR-25991: Hotfix voor CQ-4245162
* Publiceer recentere functionaliteit voor AEM aan het Portaal replicatie van het Merk. NPR-25911: Hotfix voor CQ-109139
* Het publiceren van en unpublishing van de privé inzameling door niet-admin gebruikers resulteert in een NPE. NPR-25906: Hotfix voor CQ-4250594
* Publiceren van inhoudsfragment en formulierschema&#39;s naar Brand Portal uitschakelen. NPR-24176, NPR-26004: Hotfix voor CQ-4251592, CQ-4252026
* (Dynamic Media) Bijgewerkte DM-viewers naar versie 5.10.1 waarmee u kunt controleren op dubbele namen op de pagina met voorinstellingen voor afbeeldingen. Raadpleeg Dynamic Media Viewers bijwerken (5.10.1). NPR-24403: Hotfix voor CQ-4247554
* Javascript-fout in de browserconsole in de kolomweergave bij het selecteren van een element of map. NPR-25939: Hotfix voor CQ-4250228
* (Kolomweergave) Kan taken niet identificeren omdat het sleutelbestand wordt weergegeven als een leeg wit item. NPR-25903: Hotfix voor CQ-4246307

**Sites**

* De vraag van datasource.jsp op AEM 6.2 is verschillend van AEM 6.4. NPR-24968: Hotfix voor CQ-4244235
* (Klassieke interface) Kan geen codes toevoegen aan pagina&#39;s. NPR-25255, NPR-25612: Hotfix voor CQ-4249615
* HTML Template Language Specification 1.4-functies die zijn teruggezet naar AEM 6.4.2.0 NPR-24585
* Onjuiste overerving op lokale component na kopiëren van een pagina voor live kopiëren. NPR-25920: Hotfix voor CQ-4236737, CQ-4248957
* De ON/OFF-tijd wordt opgeslagen in crx/de maar haalt niet het zelfde in de console UI van de paginaeigenschappen. NPR-25154: Hotfix voor CQ-4243431
* Stijlen - Systeem breekt de beginwaarden van eigenschappen van het dialoogvenster. NPR-25648: Hotfix voor CQ-4250073
* Wanneer u een eigenschap cq:tagName definieert in een knooppunt cq:htmlTag, wordt de tagnaam niet meegenomen via JSP. NPR-24154: Hotfix voor CQ-4244120
* Voor genestelde componenten parsys, altijd eerste (met minst genestelde weg) bevredigend ontwerp wordt toegepast van veelvoudige beschikbare componenten. Zie [Resolutie ontwerppad](https://docs.adobe.com/content/help/en/experience-manager-64/developing/platform/templates/page-templates-static.html) voor meer informatie. NPR-24973: Hotfix voor CQ-4246276
* Wanneer het kleven van tekst in een component RTE, wordt een pop-up dialoog getoond, maar niet behoorlijk teruggegeven. NPR-24895: Hotfix voor CQ-4245901
* (RTE) Prestatieproblemen met verplichte veldindicator. NPR-24894: Hotfix voor CQ-4241895
* (De component van de Pagina) het toevoegen van een component aan Parsys wordt bebouwd van recht en komt uit de breedte van het apparatenkader. NPR-25536: Hotfix voor CQ-4238224
* De redacteur Plaintext verzendt niet-bijgesneden gegevens en voegt extra ruimten toe. NPR-25312: Hotfix voor CQ-4249006
* Wanneer u de component opent met de inline-modus, zijn eerder geladen insteekmodules de tweede keer niet zichtbaar. NPR-24610: Hotfix voor CQ-4236850
* Het laden van een XF in redacteursmening door exemplaar/deeg laadt niet automatisch de master variatie. NPR-24841: Hotfix voor CQ-4248037
* Verkeerde HTML-structuur in siteadmin/damadmin breekt IE11. NPR-24686: Hotfix voor CQ-4246363, CQ-4248402
* (Publicatiewizard beheren) De kalender voor de activeringsdatum in de stap Opties wordt niet geopend na een aantal handelingen in de stap Bereik. NPR-25681: Hotfix voor CQ-4250205
* Klassieke interface werkt niet om CUG te bewerken vanwege veroudering. NPR-25075: Hotfix voor 4241823
* Optie maken is niet beschikbaar om ervaringsfragmenten te maken. NPR-26053: Hotfix voor CQ-4249923
* XF de variatie wordt geactiveerd tweemaal vandaar, producerend dubbele IDs voor het zelfde punt. NPR-24179: Hotfix voor CQ-4245093
* De lijst van de stichting is kwetsbaar aan Opgeslagen Scripting over de hele site. NPR-25185: Hotfix voor CQ-4240760
* Fout bij &#39;Ongeldige waarde van recursieselectiekader&#39; tijdens het migreren van een component van AEM 6.2.1.13 naar AEM 6.4. NPR-24146

**WCM - Pagina-editor**

* De veelvoudige gestapelde Parsys toe te schrijven aan langlopende vragen (meer dan 6) maakt AEM langzaam. Hotfix voor CQ-4240247
* JS-fout bij het toevoegen van een lege cq:tagName in cq:htmlTag-knooppunt. Hotfix voor CQ-4251852
* Werk EditableActions bij die op columnClassNames relocation wordt gebaseerd. Hotfix voor CQ-4250781
* Stel middel en modelwegen bloot gebruikend één enkel bezit en attribuut. Hotfix voor CQ-4251255
* Wijzigingen voor het afbreken van de API voor export.json herstellen. Hotfix voor CQ-4251854
* (Bewerkbare SPA) Laat de kandidaat los voor 1.0.0. Hotfix voor CQ-4251991
* De werkbalk Bewerken wordt uitgeschakeld voor andere componenten wanneer u één component bewerkt. Hotfix voor CQ-4253270

**Integratie**

* De velden Bibliotheek en Download URL moeten bewerkbaar zijn. NPR-24804: Hotfix voor CQ-4246864
* Probleem met meerdere DTM-configuraties. NPR-24685: Hotfix voor CQ-4247293
* Toegevoegde ondersteuning voor asynchrone implementatie voor gehoste clientbibliotheken. NPR-25716: Hotfix voor CQ-4245745
* Doelcomponent met ontbrekende overeenkomende aanbieding geeft de hele pagina weer en in plaats van een leeg doelcomponent wordt een andere volledige vertoning van de pagina toegevoegd. NPR-25273: Hotfix voor CQ-4248003
* De doelengine (mbox.js, at.js) gebruikt geen beheerde URL&#39;s en gebruikt URL&#39;s die dubbele punten bevatten die mogelijk mislukken bij bepaalde implementaties. NPR-25339: Hotfix voor CQ-4237854
* (Launch)LibraryDownloadProcess slaat onjuiste libraryUri-waarde op. NPR-25330: Hotfix voor CQ-4250006

**Platform**

* Lus opnieuw indexeren | NPE terwijl het uitvoeren van BinaryTextExtraction tijdens op plaats verbetering van 6.3 tot 6.4. Hotfix voor graniet - 21677
* Grensoverschrijdende overschrijving van intern gemarkeerd pad /libs/cq/cloudserviceconfigs/templates/configpage/jcr:content - Probleem tijdens het uitvoeren van patroondetector. NPR-25036: Hotfix voor CQ-4248597
* Logboekvermeldingen die niet zijn geschreven vanwege NPE in LogEntryImpl. NPR-25627: Hotfix voor graniet-22383
* Replicatie van gebeurtenis delete controleert niet op rechten. NPR-25679: Hotfix voor CQ-4241234
* Toegevoegde STARTTLS-ondersteuning in &quot;Day CQ Mail Service&quot;. NPR-25611: Hotfix voor CQ-4249924
* De pro-actieve steun voor granite.platform.login moeilijke situaties om toegankelijkheid te verbeteren. NPR-25176: Hotfix voor graniet 21746 en graniet-21309
* (AEM 6.4) Fout bij het opnieuw samenstellen en opnieuw installeren van het pakket. NPR-25173: Hotfix voor CQ-4247939
* Standaard MERGE_PRESERVE aclHandling verwijderd. NPR-24593: Hotfix voor graniet-21889
* Het inhoudstype wordt niet voorgesteld en ontbreekt in het antwoord nadat ContentDispositionFilter tweemaal is toegepast. NPR-24175: Hotfix voor Sling-7525
* De status van de Manager van het pakket is onjuist na verbetering aan AEM 6.4 tak. NPR-24551: Hotfix voor graniet-21750
* AMS-instantie - analyse van foutlogbestanden. Hotfix voor CQ-4249567

**Beveiliging**

* SAML richt opnieuw login aan logout pagina gebruikend Okta IDP. NPR-25523: Hotfix voor GRANITE-22364
* IMS-verificatie via externe IDP OAuth Provider configureert de in AEM gemaakte gebruiker. NPR-25301: Hotfix voor graniet-22363

**MAC- Test &amp; Target-integratie**

* (Doel) Tekstcomponentfout tijdens het toewijzen van doelen. Hotfix voor CQ-4233343

**Gemeenschappen**

* (Bestandsbibliotheek) Elementen downloaden met lege spaties als gevolg van indelingsproblemen. NPR-24260: Hotfix voor CQ-4245159
* Hiermee verhelpt u verschillende Adobe Social-problemen. NPR-24247: Hotfix voor CQ-4245054, CQ-4245120, CQ-4245296
* Het oneindige schuiven voor leden en groepenconsole mislukt voor het geval dat de auteur op verschillende contextpaden publiceert. NPR-24437: Hotfix voor CQ-4246013
* De post keert niet aan de onbeantwoorde staat terug zelfs bij het verwijderen uit de beantwoorde staat en de score daalt niet. NPR-24419: Hotfix voor CQ-4245797, CQ-4245932
* Gebeurtenissen die zijn toegevoegd met gebruik van kalenderfunctionaliteit in gemeenschappen leveren onjuiste waarden op. NPR-24883: Hotfix voor CQ-4244056
* (Forum van Gemeenschappen) Problemen met paginering klikken en gedrag bij laden van pagina. NPR-24880: Hotfix voor CQ-4246109
* (Chrome) Tijdzoneomzettingen ontbreken op gemeentegebeurtenissen. NPR-24881: Hotfix voor CQ-4247115
* Kan ingesloten object niet renderen in e-mail. NPR-24999: Hotfix voor CQ-4248022
* Automatiseringsreeks moet worden uitgevoerd bij UGC-update naast het maken van UGC. NPR-25892: Hotfix voor CQ-4251399
* Responssnelheid van het dialoogvenster Modal voor groepen. NPR-25623: Hotfix voor CQ-4248805
* Een enkele uitzondering wordt gegenereerd bij het verwijderen van inhoud. NPR-25869: Hotfix voor CQ-4248908
* Gepagineerde koppelingen naar threads met veel berichten werken niet bij Meldingen. NPR-25678: Hotfix voor CQ-4243038
* De tijdwaarden in het onderzoeksresultaat tonen servertijd in plaats van de tijdzone van de cliënt. NPR-25594: Hotfix voor CQ-4248986
* (Opmerkingen van het Forum) De knop Terug in de browser werkt niet zoals verwacht. NPR-25205: Hotfix voor CQ-4248573
* (Zoekresultaten) De knop Terug in de browser werkt niet zoals verwacht. NPR-25214: Hotfix voor CQ-4248574
* Null wordt geretourneerd wanneer de component communitygroupmemberList wordt bedekt. NPR-25228: Hotfix voor CQ-4248523
* (Communities Calendar) ClassCastException wordt geproduceerd terwijl het bewaren van de gebeurtenis met het nieuwe beeld van de Omslag. NPR-25167: Hotfix voor CQ-4248662
* (Communities) Berichten die worden afgekapt. NPR-25326
* (AEM-publicatie) Het Scoremiddel werkt niet bij het contextpad en geeft een leeg scherm weer. NPR-26155: Hotfix voor CQ-4251942
* (MSRP) De nieuw gecreëerde kalender wordt bewaard gedeeltelijk het werpen NPE in het foutenlogboek. NPR-26071: Hotfix voor CQ-4250531
* De paginering van het forum/van het Onderwerp wordt slechts bijgewerkt wanneer de pagina wordt verfrist. NPR-26070, NPR-25965: Hotfix voor CQ-4249509
* (Forum Vragen en antwoorden) Kan niet naar de vorige pagina navigeren bij het openen van een directe koppeling naar een opmerking. NPR-26069: Hotfix voor CQ-4251699
* Upload image in Create group werkt niet op mobile. NPR-26172: Hotfix voor CQ-4251703
* (Overseinen) wanneer het gebruiken van DSRP, wordt de naam van berichtontvanger altijd getoond als &quot;Onbekend&quot;. NPR-26056: Hotfix voor CQ-4251397
* Label voor de voltooiingsstatus van Scoreschema inschakelen is leeg in de gebruikersinterface. NPR-26034: Hotfix voor CQ-4249994
* Terwijl het creëren van een nieuwe communautaire groep, wordt een dubbele communautaire groep gecreeerd op een actief/actief cluster mongoMK. NPR-26032: Hotfix voor CQ-4245884
* (Auteur) Het duurt te lang om een groep in de wizard te laden of te maken. NPR-26031: Hotfix voor CQ-4244966
* Parsys verdwijnt bij het toevoegen van een include verklaring in het hbs manuscript. NPR-25908: Hotfix voor CQ-4250489
* Bij het toelaten van &quot;sta bevoorrecht&quot;toe, zouden de bevoorrechte leden slechts voor gebruikers moeten kunnen samenstellen die lid van de gemeenschap zijn. NPR-25877: Hotfix voor CQ-4248450
* Deeplinks geblokkeerd voor activering. NPR-25966: Hotfix voor CQ-4251478
* De paginering van het forum wordt niet dynamisch bijgewerkt na verwijdering van reacties. NPR-25970: Hotfix voor CQ-4248975, CQ-4252843
* Automatisch schuiven en markeren werkt niet bij agenda- en filelib-gebeurtenissen in het geval van geneste opmerkingen. NPR-25958: Hotfix voor CQ-4251471
* (DSRP) Direct/Deep de prestaties van de Verbinding degraderend met hoge hoeveelheden Gebruiker Gegenereerde Inhoud. NPR-25957: Hotfix voor CQ-4251470
* Kan de eigenschappen van Geprivilegieerde leden en Geprivilegieerde leden toestaan niet wijzigen. NPR-26014: Hotfix voor CQ-4244592
* Markeer alles zoals gelezen stelt de berichttellers voor alle communautaire pagina&#39;s terug. NPR-25931: Hotfix voor CQ-4248612
* Bewerk IT&#39;s die mislukken voor DSRP. NPR-25929: Hotfix voor CQ-4251382
* E-mailberichten mislukken vanwege NPE tijdens het maken van e-mailsjablonen. NPR-26039: Hotfix voor CQ-4250962
* Problemen met forumverbindingen bij het insluiten van afbeeldingen met een zeer hoge resolutie. NPR-26037: Hotfix voor CQ-4244453, CQ-4253099
* De vertoningen van de tijd schakelaars wanneer de tijdzone van de server van de gebruikerstijdzone verschilt. NPR-26036: Hotfix voor CQ-4248751
* Als u een bestand tweemaal met dezelfde naam koppelt aan een forumbericht, treedt een serverfout op. NPR-24172: Hotfix voor CQ-4244367
* Oplossingen voor achtergrondprestaties: paginering groeperen bij auteur en publiceren, zoeken in groep op auteur, serienummering van antwoorden voor dagboek, kalender en ideatie vermijden en lui laden voor het ophalen van de knop groepslidmaatschap (uitnodigen/uitnodigen) voor elke groep terwijl de pagina met groepslijsten wordt weergegeven. NPR-24538: Hotfix voor CQ-4246515
* De Middelen van Enablement zijn niet zichtbaar bij auteur. Hotfix voor CQ-4252618
* Meldingen worden niet gegenereerd voor verbinding van een onbekende gebruiker. Hotfix voor CQ-4245132
* Groepzoekactie wordt niet weergegeven op linkerspoor. Hotfix voor CQ-4252621
* (Auteur) Paginering werkt niet voor Groepenconsole. Hotfix voor CQ-4242786
* jQuery UI-upgrade. Hotfix voor CQ-4248894
* Voer een upgrade uit naar de nieuwste versie van SCORM 2017.1. NPR-25675: Hotfix voor CQ-4240671
* De velden &quot;Samenstellen namens&quot; zijn zichtbaar voor gebruikers buiten de gebruikersgemeenschap. NPR-25331: Hotfix voor CQ-4247858
* Post is nog zichtbaar op UI zelfs na schrapping en geeft fout op console. NPR-26290: Hotfix voor CQ-4252803
* (Site-instellingen) Kan de wijzigingen in Rollen niet opslaan. NPR-26274: Hotfix voor CQ-4252187
* (Vulnerability van de Veiligheid) Accountovername toe te schrijven aan het Symbolische Misconfiguration van JSON Web. NPR-26458: Hotfix voor CQ-4253314
* Paginering wordt niet opnieuw ingesteld wanneer reacties worden verwijderd. NPR-26326: Hotfix voor CQ-4252997
* Bijlageafbeelding wordt tijdens het bewerken niet weergegeven in Concepten. Hotfix voor CQ-4253360
* De pagina wordt niet vernieuwd terwijl het vastmaken van gehechtheid in Relationele Gegevensbestand (DSRP). Hotfix voor CQ-4253084
* De groepen werken niet binnen de plaatsmiddel van Enablement. Hotfix voor CQ-4252975
* Vereisten voor leerpaden blijven niet bestaan in Inschakelen. Hotfix voor CQ-4252948

**Workflow**

* Workflow-startinterface geeft geen vorige 41 startconfiguraties weer en activeert een javascript-fout in de console. NPR-25028: Hotfix voor CQ-4247604
* Als u een oudere workflow bewerkt zonder de startfunctie te bewerken, worden er meerdere workflows gemaakt voor elke workflow die een stap Pagina/element activeren bevat. NPR-25870: Hotfix voor CQ-4250896
* Onjuiste koppeling in werkstroomlading als de pagina een metagegevensknooppunt heeft. NPR-25916: Hotfix voor CQ-4250733

**Vertaling**

* Probleem verholpen waarbij bij het importeren van vertaalde projecten twee gelijktijdige aanvragen voor POSTEN worden ingediend, waardoor er een fout optreedt. NPR-24889: Hotfix voor CQ-4247638
* Probleem verholpen dat bij het maken van een vertaalproject voor meerdere talen alle pagina&#39;s voor dezelfde taal aan dezelfde taak worden toegevoegd. NPR-25091: Hotfix voor CQ-4246112
* Probleem verholpen waarbij in sommige gevallen alleen de bovenste 40 pagina&#39;s in de vertaaltaak worden vermeld. NPR-25974: Hotfix voor CQ-4248661
* component DataPicker (Coral2) verandert het jaar niet. NPR-24466: Hotfix voor graniet-21893

**UI - Foundation**

* De pro-actieve Steun UI van de Stichting steunt. NPR-24344, NPR-24345, NPR-25176, NPR-25095, NPR-24332, NPR-25653, NPR-25932, NPR-259 35, 25976
* (Design Importer) Als u een pagina importeert, worden de JS,css niet geïmporteerd. NPR-25205: Hotfix voor graniet-22236
* De pro-actieve Steun UI van de Stichting steunt om de stabiliteit van het product te verbeteren. NPR-24334

**MAC- Test &amp; Target-integratie**

* De tweede pagina van de Tovenaar Personalization ( die door &quot;Begin het richten&quot;wordt gelanceerd) is leeg en werpt consolefouten. Hotfix voor CQ-4253277

**Ervaringsfragmenten**

* De samengevoegde Fragments van de Ervaring/de Integratie van het Doel aan AEM 6.4.2.0. Hotfix voor CQ-4248653

**Beheer van inhoudsfragmenten**

* Inhoudsfragmenten, annotaties en vergelijking van versies van inhoudsfragmenten naast elkaar. Hotfix voor CQ-4247148

**DAM - Algemeen**

* Het filter Uitgecheckt door werkt niet correct in de zoekopdracht. Hotfix voor CQ-4247070
* Bij het uitvoeren van de workflow voor het bijwerken van elementen worden de kopie van de taal van het element en de bijbehorende miniatuur leeg. Hotfix voor CQ-4250641
* Duplicaat-id: id-kenmerkwaarde moet uniek zijn. Hotfix voor CQ-4250905
* Label: Formulierelementen moeten labels hebben. Hotfix voor CQ-4250906
* Koppelingsnaam: Koppelingen moeten duidelijke tekst hebben. Hotfix voor CQ-4250907
* Sjabloonmigratie JMX- en ServiceUserMapping voor poortmapmetagegevens. Hotfix voor CQ-4252947
* WebdriverIO-tests worden niet uitgevoerd in de vertakking release/640 van CQ/dam. Hotfix voor CQ-4252749
* Koppelingen naar verplaatste elementen worden niet vernieuwd als de koppeling wordt gepubliceerd. Hotfix voor CQ-4245756

**DAM - Viewers**

* Periodieke fout bij het laden van video met nieuwe viewers 5.10.1. Hotfix voor CQ-4250562

**DAM-Brand Portal**

* De publicatie van de verzameling via Brand Portal mislukt vanwege een fout. Hotfix voor CQ-4245990
* Kan de publicatie van voorinstellingen voor afbeeldingen op Brand Portal niet ongedaan maken. Hotfix voor CQ-4246140
* Subelementen van een PDF-bestand met meerdere pagina&#39;s worden niet gepubliceerd wanneer een element wordt gepubliceerd. Hotfix voor CQ-4245162

**DAM - DMClient**

* Wanneer u een video-element naar YouTube publiceert, bevatten de tags die resulteren in YouTube het volledige pad van de tag. Hotfix voor CQ-4245549
* (Opt-out en Opt-In upgrades) Probleem met CSS-omleiding van viewer. Hotfix voor CQ-4247854
* Kan geen viewervoorinstelling maken/bewerken die geen lid is van de groep &#39;beheerders&#39;. Hotfix voor CQ-4247618
* (6.4.1.0) Het toevoegen van veelvoudige video&#39;s in veelvoudige parsys breekt de videospeler. Hotfix voor CQ-4248517
* Door de naam van elementen te wijzigen en elementen binnen een afbeeldingsset te verplaatsen, kunt u deze niet bewerken. Hotfix voor CQ-4248434
* Wanneer u grote video&#39;s naar YouTube publiceert, worden er time-outberichten weergegeven. Hotfix voor CQ-4237831
* (Lijstweergave) De gebruikersinterface van de elementkiezer/de kiezer verandert in alle grijstinten en is voor de gebruiker uitgeschakeld. Hotfix voor CQ-4237817
* (Verticaal zoomen) CSS kan niet worden geladen met een fout van 404. Hotfix voor CQ-4236508
* Wanneer u een element met een percentageteken (%) in de naam van het element probeert te downloaden, resulteert dit in een leeg archief. Hotfix voor CQ-4250558
* (Kaartweergave) Er wordt geen verwerkingsindicator weergegeven wanneer u Kopiëren en Plakken in een Video-element gebruikt. Hotfix voor CQ-4249037
* (Upgrade van 6.3.2 naar 6.4) Voorinstellingen voor afbeeldingen vóór upgrade worden op de pagina Uitvoeringen weergegeven als &quot;Niet gepubliceerd&quot;, maar als deze optie is geselecteerd, levert dit geen URL-knop op. Hotfix voor CQ-4240406
* Technische schulden/kleine verbeteringen. Hotfix voor CQ-4240648
* In de Asset Selector (of de Asset Picker) worden niet alle middelen uit de beschikbare mappen weergegeven. Hotfix voor CQ-4218414
* Voorinstelling afbeelding zonder hoogte geeft afbeeldingen met een onjuiste grootte weer. Hotfix voor CQ-4246546
* (Elementen van meerdere pagina&#39;s) De gebruikersinterface wordt onderbroken wanneer op annotaties wordt geklikt. Hotfix voor CQ-4251434
* Als u de voorinstelling Analytics upgradet van 6.3 naar 6.4 en hoger, wordt een nieuwe rapportsuite en voorinstelling Analytics gemaakt, waardoor de oudere rapportgegevens van de gebruiker verloren gaan. Hotfix voor CQ-4244529
* (De wizard Publicatie beheren) Lijst met elementen lijkt leeg te zijn wanneer u probeert te publiceren of publicatie ongedaan wilt maken. Hotfix voor CQ-4251881
* Wanneer u Viewers kiest nadat u de leden hebt ingesteld, kunnen AVS-video&#39;s niet worden afgespeeld. Hotfix voor CQ-4205308
* Voorinstellingen voor videoverwerking die al zijn bijgewerkt, kunnen geen nieuwe voorinstelling voor videocodering bevatten en de bestaande coderingsvoorinstelling(en) niet bewerken. Hotfix voor CQ-4240407
* Voorinstellingen voor afbeeldingen worden niet toegepast op gedownloade dynamische uitvoeringen. Hotfix voor CQ-4249862
* De knop Alles selecteren werkt niet correct op de pagina met lijsten met voorinstellingen voor viewers. Hotfix voor CQ-4252462
* Videoprofielen: De knop Alles selecteren werkt niet. Hotfix voor CQ-4253076, CQ-4251447
* SP2-validatiecontrole - Rookcontrole. Hotfix voor CQ-4251639

**DAM - DMServices**

* Dynamic Media-uitvoeringen konden niet worden gegenereerd voor EPS-bestand. Hotfix voor CQ-4243688

**Graniet**

* Typo in bundle SymbolicName leidt tot dubbele bundel. Hotfix voor graniet - 22155
* CUGConfiguration kan CugExclude niet ophalen. Hotfix voor graniet - 21109
* Door de Adobe Granite Workflow Core opnieuw te starten, worden de workflowstappen opnieuw uitgevoerd vanaf het midden, waardoor onnodige workflows ontstaan. NPR-25057: Hotfix voor graniet-22218
* JcrResourceBundle biedt geen correcte ondersteuning voor meerdere basisnamen. NPR-25245: Hotfix voor graniet-22317
* Bij installatie van inhoudspakketten, worden ACLs gegroepeerd door hoofd, daarom, die het toestemmingsmodel breken. NPR-24583: Hotfix voor graniet-21591
* Werk de inhoud bij naar 9.4.11 om kwetsbaarheden te verhelpen. NPR-25030: Hotfix voor graniet-22120

**Forms**

De belangrijkste markeringen voor AEM 6.4.2.0 vormen zijn:

* Nieuwe eigenschap voor wachtrijen toegevoegd die moet worden bijgewerkt zonder de browser te vernieuwen.
* Toegevoegde mogelijkheid voor de gebruiker om hetzelfde WSDL-bestand te gebruiken voor meerdere services.
* Het niet-ondersteunde tijdstempelpatroon is verwijderd uit het vervolgkeuzemenu van de datumkiezer.
* Extra ondersteuning voor onderstreping van xfaf en pdf in OSGI.
* Toegevoegde ondersteuning voor het gebruik van de [mogelijkheid voor transactierapporten](https://docs.adobe.com/content/help/en/experience-manager-64/forms/transaction-reports/transaction-reports-overview.html) bij on-premise implementaties.
* Toegevoegde code om kind var in de redacteur van de voorwaardenregel niet te tonen.

**Forms-invoegtoepassing**

**Transactiemelding**

* Update de Configuratie van de Rapportering van de Transactie met het belang van omgekeerde replicatie die op een Publish server wordt gevormd. NPR-26050: Hotfix voor CQ-4246650
* Vertraagde initialisatie van Periodic Flush Job. NPR-25968: Hotfix voor CQ-4245024
* Transactieopname mislukt met uitzondering van null-aanwijzer. Hotfix voor CQ-4247302

**Forms - Workflow**

* (HTML Workspace) Wanneer een gebruiker een taak aanvraagt, wordt het aantal wachtrijen voor die bepaalde gebruiker vernieuwd, maar niet voor andere gebruikers, tenzij de pagina wordt vernieuwd. Dit probleem is opgelost door een nieuwe eigenschap. Om dit nieuwe bezit aan uw AEM instantie te vormen, verwijs naar zijn Montages van de Configuratie. NPR-24536: Hotfix voor CQ-4233665
* Kan geen groot formulier laden in de AEM Forms App op 6.4. NPR-24463: Hotfix voor CQ-4245091
* Probleem in de app voor de mobiele werkruimte tijdens het weergeven van de gedeelde taak. NPR-25177: Hotfix voor CQ-4248733
* Inconsistent validatiegedrag tussen Web en APK. NPR-25670: Hotfix voor CQ-4248178
* Wanneer een aanroep naar een webservice wordt gemaakt van een HTML5-formulier dat in de client wordt geopend, mislukt het en wordt een foutbericht geretourneerd. NPR-26048: Hotfix voor CQ-4244716
* Probleem tijdens het aanroepen van de service in AEM formulieren Windows app 6.3. NPR-26468: Hotfix voor CQ-4252341

**Mobile Forms**

* (Formset) Probleem met SSN- en mobiele veldvalidatie bij voorvertonen. NPR-24458: Hotfix voor CQ-4244983
* Gegevens worden niet weergegeven bij het vooraf invullen van velden met meerdere regels in de HTML-voorvertoning. NPR-24549: Hotfix voor CQ-4244212
* Gegevens gaan verloren wanneer het script op een veld met meerdere regels wordt geëvalueerd. NPR-25333, Hotfix voor CQ-4249610

**Forms - Interactieve communicatie en correspondentiebeheer**

* Synchronisatie mislukt op IC met Basic Template en Reference IC Print Template. NPR-24912
* (CCR) Validators werken niet voor velden/variabelen. Hotfix voor CQ-4245047
* Het pictogram Object gegevensmodel verdwijnt periodiek op de werkbalk Tekst bewerken. Hotfix voor CQ-4245122
* De logboeken van de uitzondering verschijnen op gekopieerde IC als originele IC wordt geschrapt. Hotfix voor CQ-4249378
* In de uitvoering van de letter wordt de waarde niet geëvalueerd op true, zelfs niet als de gegevens juist zijn. Hotfix voor CQ-4245944
* Automatisch gegenereerde componenten worden niet gemarkeerd bij het selecteren in de inhoudsstructuur. Hotfix voor CQ-4246178
* Problemen bij het openen van de webkanaalsjablooneditor. Hotfix voor CQ-4248182
* Kan de volgorde van toegevoegde elementen niet wijzigen omdat de pijlen omhoog en omlaag uitgeschakeld blijven. Hotfix voor CQ-4252042
* Kan eigenschappen van de Condition-module niet bijwerken. Hotfix voor CQ-4247909
* UX van het dialoogvenster Overerving annuleren wanneer de gebruiker een object opnieuw rangschikt in webkanaal, moet worden verbeterd. Hotfix voor CQ-4241076
* Gegevens in de letter die overeenkomen met bindingen die zijn gedefinieerd in XDP, worden niet gevuld bij het gebruik van een directe letter-URL. Hotfix voor CQ-4245833
* (Caching issue) De synchronisatie van Webkanaal weerspiegelt geen veranderingen die aan lay-outfragmenten, het fragment van de Tekst van drukkanaal worden aangebracht. Hotfix voor CQ-4251460
* Kan het fragment Layout en de eigenschappen DD niet bijwerken. Hotfix voor CQ-4247830
* (CCR) Het opnieuw laden van het concept mislukt als gevolg van XML-parsering. Hotfix voor CQ-4250950
* (IC Editor) De knop Fragment bewerken moet beter te ontdekken zijn. Hotfix voor CQ-4244694
* (XDP) Er wordt een leeg scherm weergegeven wanneer u een indelingsfragment toevoegt aan het nieuwe subformulier. Hotfix voor CQ-4248810
* Testfout DocumentFragment-master-DeployWithServerSideTests. Hotfix voor CQ-4245496
* Variabele van de module van de tekst Instantie die in de module van de Voorwaarde wordt gedupliceerd. Hotfix voor CQ-4252128
* In de PDF-voorbeeld-URL wordt geen transactierapportage weergegeven bij publicatie. Hotfix voor CQ-4246158
* IC synchroniseer gerelateerde problemen met Afdrukkanaal naar webkanaal synchroniseren. Hotfix voor CQ-4251505
* EXM Code opschonen: Remove LocalFunctionMapper. Hotfix voor CQ-4243265
* Om het middeltype van TableHeader van IC&#39;s webChannel lijstcomponent te verbeteren. Hotfix voor CQ-4251821
* (IC Editor) Gebruiksproblemen. Hotfix voor CQ-4241081
* Het subformulier voor kanalen afdrukken geeft geen functionaliteit voor invoegen weer. Hotfix voor CQ-4252994
* Bij het synchroniseren van wijzigingen blijven mislukt nadat FDM-knooppunt of tijdelijke aanduiding voor variabele is verwijderd. Hotfix voor CQ-4253178
* (Sjablooneditor) De standaardsjabloon toont extra gebieden voor slepen en neerzetten in de kop-/voettekst en de schermflikkeringen bij het openen van het webkanaal. Hotfix voor CQ-4253323
* Automatisch gegenereerde componenten worden niet gemarkeerd wanneer u ze selecteert in de Inhoudsstructuur. Hotfix voor CQ-4246178

**Document Services**

* (Formulierservice) OSGI biedt geen ondersteuning voor XFAF. NPR-25181, hotfix voor CQ-4251313
* De tekens in de kop van het geassembleerde PDF-bestand worden niet correct weergegeven. NPR-25113: Hotfix voor CQ-4244682

**Adaptieve Forms**

* Als Actie verzenden als E-mail verzenden, wordt een uitzondering gegenereerd met velden voor CC/BC leeg. NPR-25019: Hotfix voor CQ-4243039
* Kan de OOTB AEM Form-component niet gebruiken vanwege inefficiënte query. NPR-25065: Hotfix voor CQ-4247256
* Schuine streep verwijderen:orderBefore uit dialoogknooppunten van guideImageChoiceComponent. Hotfix voor CQ-4245013
* (Datumkiezer) Bewerkingspatroon ondersteunt geen twee typen tijdstempelpatronen. Hotfix voor CQ-4237982
* Handeling verzenden met gebruik van &#39;Forms Workflow&#39; Classic authoring issues. Hotfix voor CQ-4236981
* (Het Kanaal van het Web) de Grafiek van IC zou colspan bezit van AF grafiek moeten erven. Hotfix voor CQ-4252143

**Backend-integratie**

* (SOAP-aanvragen) Grote decimalen (meer dan 6 cijfers) worden weergegeven in exponentiële notatie, wat resulteert in een validatiefout. NPR-25283: Hotfix voor CQ-4248100
* Onjuiste validatie van optionele parameters die in complexe typen zijn gedefinieerd. NPR-25070: Hotfix voor CQ-4247107
* Toegevoegde mogelijkheid voor de gebruiker om hetzelfde WSDL-bestand te gebruiken voor meerdere services. NPR-24604, Hotfix voor CQ-4247756
* FDM rangschikt orde van parameters in zijn vraag van de ZEEP. NPR-25069, hotfix voor CQ-4247180
* FDM voegt entiteiten (in Lijst/Serie) in het verzoek van de ZEEP samen. NPR-25284: Hotfix voor CQ-4248375

**Forms JEE Installer**

**PDFG-service**

* De functie voor het maken/wijzigen van beveiligingsinstellingen werkt niet. NPR-24769: Hotfix voor CQ-4246927
* Optimize PDF door het insluiten van lettertypen selectief ongedaan te maken via één API-aanroep. NPR-23287

**Document Services**

* Uitvoerservice bevat niet de juiste codes voor toegankelijkheidstaak. NPR-24438, NPR-24439, NPR-24440, NPR-24441: Hotfix voor CQ-4243849, CQ-4243845, CQ-4243852, CQ-4243853

**Documentbeveiliging**

* Probleem met het maken van beleid met behulp van documentbeveiliging. NPR-25586, NPR-25547: Hotfix voor CQ-4247086

**Forms - Foundation JEE**

* Processen die periodiek als de Rekening van de Context van het Systeem lopen. NPR-25289, NPR-25313: Hotfix voor CQ-4249331
* AEM Forms JEE had invloed op Apache Struts en Jackson data binding security alert. NPR-25628: Hotfix voor CQ-4242891
* E-mailbeginpuntproces werkt niet. NPR-25253: Hotfix voor CQ-4248518

**Inclusief functiepakketten**

**Activa**

* Toegevoegde [integratie met Adobe Stock](/help/assets/aem-assets-adobe-stock.md) zodat gebruikers Adobe Stock-elementen rechtstreeks vanuit AEM gebruikersinterface kunnen zoeken, voorvertonen, opslaan en in licentie geven. Zie [Adobe Stock-elementen gebruiken met AEM.](https://docs.adobe.com/content/help/en/experience-manager-learn/assets/creative-workflows/adobe-stock.html) voor meer informatie. NPR-15779: Hotfix voor CQ-30857
* Toegevoegde ondersteuning voor dynamische voorwaardelijke metaschema. Zie [Trapsgewijze metagegevens](/help/assets/cascading-metadata.md) voor meer informatie. NPR-25189: Hotfix voor CQ-4237413
* De optie Asset Download is ingeschakeld voor Inhoudsfragmenten. Zie [Elementrapporten](/help/assets/asset-reports.md) voor meer informatie. NPR-25186: Hotfix voor CQ-4237410
* Mogelijkheid om een metagegevensschema voor elementmappen in te stellen. Voor meer informatie, zie [Het Schema van Meta-gegevens van de omslag ](/help/assets/folder-metadata-schema.md) en verwijs naar zijn [Montages van de Configuratie](#configuration-settings-required-for-npr) post AEM 6.4.2.0 installatie. NPR-21268: Hotfix voor CQ-4221574

**Sites**

* U kunt een inhoudsfragment bewerken zonder machtigingen voor verwijderen. Zie [Inhoudsfragmenten aanpassen en uitbreiden](https://docs.adobe.com/content/help/en/experience-manager-64/assets/fragments/content-fragments-delete.html) voor meer informatie. NPR-25793: Hotfix voor CQ-4248750
* Er is een functie toegevoegd voor het annoteren van inhoudsfragmenten. Voor meer informatie, zie [Variaties-Authoring Fragments](https://docs.adobe.com/content/help/en/experience-manager-64/assets/fragments/content-fragments-variations.html#annotating-a-content-fragment). NPR-25188: Hotfix voor CQ-4235336
* Versioning: Vergelijk inhoudsfragmenten naast elkaar. Zie [Inhoudsfragmenten beheren](https://docs.adobe.com/content/help/en/experience-manager-64/assets/fragments/content-fragments-managing.html#comparing-fragment-versions) voor meer informatie. NPR-25187: Hotfix voor CQ-4237412
* Verbeteringen in de afbeeldingseditor zijn terug te voeren op AEM 6.4.2.0. Zie [Afbeeldingseditor](https://docs.adobe.com/content/help/en/experience-manager-64/developing/components/image-editor.html) voor meer informatie. NPR-24467

**SDAB-bundels en inhoudspakketten inbegrepen**

Lijst van OSGi-bundels opgenomen in AEM 6.4.2.0

[Bestand ophalen](assets/6.4.2.0_bundle-list.txt)

Lijst van inhoudspakketten opgenomen in AEM 6.4.2.0

[Bestand ophalen](assets/6_4_2_0content-package-list.txt)

#### AEM 6.4.1.0 {#experience-manager-6410}

AEM 6.4.1.0 is een belangrijke update die prestaties, stabiliteit, veiligheid en belangrijkste klantenfixes en verhogingen omvat die sinds de algemene beschikbaarheid van AEM 6.4 in April 2018 worden vrijgegeven.

AEM 6.4.1.0 kan op AEM 6.4 GA worden geïnstalleerd. Enkele belangrijke hoogtepunten van het de dienstpak zijn:

* De ingebouwde opslagplaats (Apache Jackrabbit Oak) wordt bijgewerkt naar versie 1.8.3.
* Verbeterde slimme tags geïntroduceerd.
* Oplossingen in Ontwerpkiezer, Tagkiezer (wijzig de bron-VM en doel-VM in auto.)
* Toegevoegde ondersteuning voor typeHint om waarden als tekenreeks op te slaan.
* Toegevoegde steun voor SMTP over TLS in de Dienst van de Post.
* Proxy handling fix for HTTP forward in DMS7.
* Bijwerken naar /etc/clientlibs/social/thirdparty/handlebars/source/handlebars.js versie 1.3.
* Oplossingen in DMHybrid Opt-OUT en Opt-IN pakketten.
* Oplossingen in slim uitsnijden.
* Gemigreerde OOTB configuratiewaarden aan de nieuwe plaats ( van /etc aan /conf).
* Kleurprofielen toegevoegd aan de klantinstellingen op leveringsservers.
* Migratie van de montages van de Server van het Beeld van /etc. — amp;gt; /conf.
* Fragment met broninhoud toegevoegd voor vertaling.
* Extra ondersteuning voor ARIA voor Print en PrintDialog.
* ARIA-ondersteuning voor e-mailvalidatie toegevoegd.
* Proactieve back-up voor platform.clientlibs-oplossingen.
* Preventie van automatische uitvoering van scripts wanneer er geen invoer is naar het expliciete dataType (verhelpt CVE-2015-9251).

**Activa**

* Bij het opnieuw openen van de eigenschappenpagina voor elementen wordt de trapsgewijze vervolgkeuzelijst leeg weergegeven. NPR-23042: Hotfix voor CQ-4238761
* Gedeelde koppelingen op mylinkshare-pagina en koppelingen naar de pagina zijn niet beschikbaar voor niet-admin-gebruiker NPR-23044: Hotfix voor CQ-4239004
* Om een Null-aanwijzeruitzondering in de DAM Asset Update-workflow in 6.4.0 te voorkomen. NPR-24134: Hotfix voor CQ-4244972
* De gepubliceerde WCM-pagina bevat plaatsaanduidingspictogrammen voor hotspot, ontbrekende CSS-bestanden met een fout van 403 voor OTB-viewers. NPR-23041: Hotfix voor CQ-4233716
* (Gedetailleerde weergave) Met de navigatiefunctie Volgende/Vorige blijft een div-bedekking in het voorvertoningsgebied van Dynamische vertoning beschikbaar, waardoor de toegang tot de viewer wordt geblokkeerd. NPR-23043: Hotfix voor CQ-4238499
* CMYK-afbeeldingsuitvoering heeft een onjuiste verzadiging. NPR-23048: Hotfix voor CQ-4235470
* XMP de extractie van metagegevens door Scene7ListInfoProvider is bronintensief. NPR-23754
* (dam-levering) De expediteur van HTTP eerbiedigt de volmachtsmontages van HTTP niet. NPR-24002: Hotfix voor CQ-4244140

**Sites**

* Wanneer de naam van de pagina wordt gewijzigd terwijl de pagina wordt verplaatst, is het verplaatsen van de pagina geslaagd, maar de functie Naam wijzigen werkt niet. NPR-22923: Hotfix voor CQ-4235907
* Fout bij het publiceren van een pagina van Actieve kopie die naar een pagina van de Importeur in de Campagnes van Adobe wijst. NPR-23053: Hotfix voor CQ-4237164
* Verplaatsen/Naam wijzigen in klassieke gebruikersinterface mislukt met fout &quot;Er is een fout opgetreden tijdens het verplaatsen van de pagina&quot; en de naam is niet gewijzigd. NPR-23051: Hotfix voor CQ-4235907
* Als u inhoud overschakelt van de kolomweergave naar de lijstweergave, wordt een lege pagina weergegeven en wordt een Null-aanwijzeruitzondering geactiveerd voor pagina&#39;s waarvoor OffTime is ingesteld en OnTime leeg is. NPR-22968, NPR-23052: Hotfix voor CQ-4238940

**Handel**

* Fix Failing Core Hobbes Testcase (CQ/Commerce Module). Hotfix voor CQ-4253494

**Kwetsbaarheid**

* De integratie van Salesforce is kwetsbaar aan de Smederij van het Verzoek van de Server (SSRF). NPR-24289: Hotfix voor CQ-4245277
* Server Side Request Smederij (SSRF) en het Scripting van de dwars-Plaats (XSS) in ReportingServicesProxyServlet. NPR-24657: Hotfix voor CQ-4246880
* XSS (cross-site scripting): Gereflecteerd in commerce createcataloguswizard.html/content. NPR-24642: Hotfix voor CQ-4237017
* XSS (cross-site scripting) in Admin UI-projectkoppelingen. NPR-23272: Hotfix voor CQ-4241795

**WCM - Elementen van de Stichting**

* Als u de ontwerpkiezer opent, wordt een null-aanwijzeruitzondering gegenereerd. NPR-23047: Hotfix voor CQ-4238736

**Gebruikersinterface**

* (Coral3 Datepicker) Voeg steun voor typeHint toe om waarden als &quot;Koord te bewaren.&quot; NPR-23398: Hotfix voor graniet-21194
* Internationalisatie werkt niet op taalniveau. NPR-22967, NPR-23046: Hotfix voor graniet-21111
* Proactieve back-up voor granite.ui.commons-oplossingen. NPR-23537
* Proactieve back-up voor granite.ui.content-oplossingen. NPR-23535
* Proactieve back-up voor granite.ui.coralui-oplossingen. NPR-23538
* Kan niet meerdere gebruikers tegelijk uit de groep verwijderen. NPR-23846
* (OMEGA) Rapporteer &quot;Functie&quot; alleen in het Engels. NPR-23989: Hotfix voor graniet-21231
* (Design Importer) Als u een pagina importeert, worden de JS, css niet geïmporteerd. NPR-25203: Hotfix voor graniet-22236

**Integratie**

* Unclosed ResourceResolver in com.day.cq.analytics.sitecatalyst. NPR-22340: Hotfix voor CQ-4236515
* TargetContentImpl maakt AEM traag tijdens lange lopende vragen. NPR-22359: Hotfix voor CQ-4236907
* De doelengine (mbox.js, at.js) gebruikt geen beheerde URL&#39;s en gebruikt URL&#39;s die dubbele punten bevatten die mogelijk mislukken bij bepaalde implementaties. NPR-22434: Hotfix voor CQ-4237854
* In de modus Doel kunnen auteurs een component die van de blauwdruk is overerfd, wijzigen zonder de overerving te annuleren. NPR-22865: Hotfix voor CQ-4237907
* (Personalisatie) De pictogrammen worden vervormd wanneer het schakelen naar de mening van de Kaart. NPR-23373, NPR-23374: Hotfix voor CQ-4240018, CQ-4240019
* (Personalisatie) De console van het publiek toont niet:omslagtypes. NPR-23375: Hotfix voor CQ-4242293
* Als een component is ingesteld op een publicatie-instantie, wordt de standaardervaring vóór de beoogde toepassing weergegeven als flikkering. NPR-23415: Hotfix voor CQ-4242038
* (Adobe IMS Console) De de dienstconfiguratie van AccessTokenProvider OSGi verschijnt na schrapping opnieuw. NPR-23520: Hotfix voor CQ-4208250
* De de verwijzingsreplicatie van de configuratie ontbreekt met middenomslagstructuur. NPR-23485: Hotfix voor CQ-4242751
* (Personalisatie) clientlib geblokkeerd door proxyservlet. NPR-23521: Hotfix voor CQ-4240995
* (Adobe IMS-console) Geregistreerde Cloud-oplossingen worden niet opgenomen in de configuratietovenaar. NPR-23977: Hotfix voor CQ-4244549
* Oneindige lus bij het laden van doelinhoud op pagina&#39;s zonder HTML-extensie. NPR-23522: Hotfix voor CQ-4223600
* Activering mislukt voor een pagina met overgeërfde dynamische de configuratieverwijzingen van het Beheer van de Markering. NPR-23485: Hotfix voor CQ-4242751

**Platform**

* (Klassieke UI) (Aanraakinterface) De tagkiezer geeft geen uitzondering weer en genereert een uitzondering wanneer wordt geprobeerd naar tags te bladeren via een tagvoorspelling in het schema voor het zoeken naar middelen. NPR-23049: Hotfix voor CQ-4239371
* (Klassieke UI) Componenten die xtype=tags gebruiken keren null terug en kunnen niet worden geselecteerd uit de 0e lijst met tags. NPR-23050: Hotfix voor CQ-4239937
* (Branding) In het dialoogvenster Opt-in wordt Adobe Marketing Cloud genoemd in plaats van Adobe Experience Cloud. NPR-23210: Hotfix voor CQ-4237799
* De filteroptie zorgt ervoor dat AEM na de upgrade van 6.3 naar 6.4 traag verloopt. NPR-23260: Hotfix voor CQ-4239847 (te controleren)
* Proactieve Backport voor granite.omnissearch.core fixes. NPR-23536
* Proactieve back-up voor platform.clientlibs-oplossingen. NPR-23569
* De overerving Cloud Service Config is verbroken tijdens het bewerken van andere pagina-eigenschappen. NPR-23216: Hotfix voor CQ-4239782
* STARTTLS-ondersteuning ingeschakeld in Day CQ Mail Service. NPR-23941: Hotfix voor CQ-4240397

**Projecten**

* (Inhoudsfragment) Er wordt geen taalkopie voor ingesloten element gemaakt terwijl het Engelse element aan de vertaling wordt toegevoegd. Hotfix voor CQ-4243477
* Het msft config dropdown toont config van /libs (6.4 vormen) in plaats van van /etc(6.3 vormen) op erfeniswijze. Hotfix voor CQ-4243475
* Vertaalintroducties in vertaalprojecten automatisch bevorderen en verwijderen. Hotfix voor CQ-4243474
* Inhoudsfragment in sites die niet worden vertaald. Hotfix voor CQ-4243482, CQ-4243483, CQ-4245687
* Serverfout bij het openen van het zoekfilter voor vertaaltaken. Hotfix voor CQ-4236813
* De referentie config dropdown is leeg zelfs nadat tif binnen /conf/wij-retail aanwezig is. Hotfix voor CQ-4236315
* Project-KPI openen: prestatievermindering wanneer meer projecten worden gemaakt. NPR-23840: Hotfix voor CQ-4238392
* De Starter van het werkschema kan geen waarde TypeHint van Koord goedkeuren. NPR-23863: Hotfix voor CQ-4238356

**Gemeenschappen**

* Beveiligingskwetsbaarheden in versie 1.0 van Handlebars. NPR-23636: Hotfix voor CQ-4243055
* Bulk Allow of flagged messages werkt niet. NPR-23867: Hotfix voor CQ-4243962
* De standaardwaarde wordt niet weergegeven op de sorteerknop in de forumcomponent. NPR-23882: Hotfix voor CQ-4243375
* Problemen met het verzenden van berichten van communautaire sites naar groepen. NPR-23935

**Workflow**

* De Day CQ Workflow Email Notification Service leidt tot één e-mail per Mongo-knooppunt voor WorkflowCompleted- en WorkflowAborted-meldingen. NPR-22515: Hotfix voor CQ-4238172
* Wanneer de DAM-update-elementwerkstroom wordt uitgevoerd, wordt een NullPointerException gegenereerd. NPR-23010: Hotfix voor graniet-21096
* De stap Werkstroomproces geeft geen scripts van /etc/workflow/scripts weer. NPR-23263: Hotfix voor graniet-20775
* De dynamische Stap van de Deelnemer van het werkschema toont geen manuscripten van /apps/workflow/manuscripten. NPR-23464: Hotfix voor graniet-21276
* Kan geen enkele workflow bewerken nadat deze eenmaal is bewerkt. NPR-23742: Hotfix voor CQ-4238526
* (Klassieke UI) Wanneer het uitgeven van de werkschemalanceringen, verdwijnen de voorwaarden veroorzakend de werkschema&#39;s om zonder enige voorwaarden te lanceren. NPR-23835: Hotfix voor CQ-4239153
* Project inbox: als u overschakelt naar de kalenderweergave, wordt de hoofdinhoud in het Postvak IN weergegeven. NPR-23947: Hotfix voor CQ-4241236
* Moet de ladingsdetails in de bundel blootstellen zodat kan de component HTML de waarde in de lijstmening tonen. NPR-23948: Hotfix voor CQ-4240953
* Kan dialooggegevens niet opslaan in de stap Deelnemer dialoogvenster. NPR-23965: Hotfix voor CQ-4234123
* (Touch UI) Wanneer u een workflowmodel opslaat, verandert de knop Sync in &#39;Gesynchroniseerd&#39;, wat resulteert in een spelfout. Hotfix voor CQ-4244843
* Project inbox: als u overschakelt naar de kalenderweergave, wordt de hoofdinhoud in het Postvak IN weergegeven. Hotfix voor CQ-4244436
* Kan Dialoogvensters niet selecteren in de stap Deelnemer dialoogvenster. Hotfix voor CQ-4244532
* Proactieve Backport voor granite.omnissearch.core fixes. NPR-23536
* Probleem in Mobile Workspace App 6.4 met gedeelde taak. NPR-26383

**WCM - Vertaling**

* (Deelvenster Referentie) Vertaal-taken worden niet uitgevoerd tijdens het maken van projecten. Hotfix voor CQ-4245327

**WCM - MSM**

* (MSM) Verbeterde uitvoerprestaties. Hotfix voor CQ-4231488
* (MSM) Timing gap in Event Listening tussen gebeurtenis die daadwerkelijk plaatsvindt en gebeurtenisafhandeling. Hotfix voor CQ-4227766

**Schermen**

* Schermpagina mislukt vanwege een fout vanwege ontbrekende afhankelijkheden voor schermen-core-pkg:1.4.42. Hotfix voor CQ-4245918

**Projecten - Vertaling**

* (Inhoudsfragment) Er wordt geen taalkopie voor ingesloten element gemaakt terwijl het Engelse element aan de vertaling wordt toegevoegd. Hotfix voor CQ-4243477
* Het msft config dropdown toont config van /libs (6.4 vormen) in plaats van van /etc(6.3 vormen) op erfeniswijze. Hotfix voor CQ-4243475
* Vertaalintroducties in vertaalprojecten automatisch bevorderen en verwijderen. Hotfix voor CQ-4243474
* Inhoudsfragment in sites die niet worden vertaald. Hotfix voor CQ-4243482, CQ-4243483, CQ-4245687
* Serverfout bij het openen van het zoekfilter voor vertaaltaken. Hotfix voor CQ-4236813
* De referentie config dropdown is leeg zelfs nadat tif binnen /conf/wij-retail aanwezig is. Hotfix voor CQ-4236315

**Beheer van inhoudsfragmenten**

* Als u een component verwijdert, worden logs met stacksporen gevuld. Hotfix voor CQ-4242315

**DAM - Algemeen**

* Als u de detailweergave van een element sluit, wordt de pagina met het zoekresultaat onjuist. Hotfix voor CQ-4240960
* (Camera Raw) de optie Afbeelding aanpassen ontbreekt. Hotfix voor CQ-4246121
* IndexOutOfBoundsException: Rapport OOTB Asset Modification. Hotfix voor CQ-4239744
* Vertrouwensscore verwijderen uit rapport csv. Hotfix voor CQ-4241491
* E-maillevering voor delen van koppeling is verbroken voor niet-beheerder afzender. Hotfix voor CQ-4240357
* IT-fouten verhelpen. Hotfix voor CQ-4249891

**DAM - Brand Portal**

* De eigenschappen van activa maken slechts 3 eigenschappen op eerste lusje van lijst, rest alle lusjes kijken leeg. Hotfix voor CQ-4242503
* Voorspelden voor bestandstypen en bestandsgrootten zijn niet beschikbaar in het gepubliceerde zoekformulier. Hotfix voor CQ-4242026
* Zoeken in mapvoorspelling moet worden uitgefilterd of niet in zoekfilters worden weergegeven. Hotfix voor CQ-4241386
* De standaardzoekopdracht van moet bestaan nadat de publicatie ongedaan is gemaakt. Hotfix voor CQ-4241383, CQ-4241113
* Publiceren naar een gebaar met een merkportal werkt niet bij voorinstellingen voor afbeeldingen. Hotfix voor CQ-4241074
* Publiceren op Brand Portal werkt niet voor verzamelingen. Hotfix voor CQ-4241122, CQ-4246558

**DAM - DM-client**

* Als u een upgrade uitvoert naar 6.4, worden eerder gemaakte videocoderingsprofielen verwijderd. Hotfix voor CQ-4244067
* Het kenmerk Alt-tekst is verbroken in de Dynamic Media-component. Hotfix voor CQ-4244081
* (DMS7) Het bewerken van externe sets in AEM wordt niet overschreven in Scene7. Hotfix voor CQ-4243430
* De controle van 6.4 SP1 bouwt op DM Hybrid voort. Hotfix voor CQ-4244623
* (DMS7-UA) Als u op de knop Insluiten voor een gepubliceerd video-element klikt, lijkt er niets te gebeuren. Het dialoogvenster Insluiten wordt weergegeven met HTML-code. Hotfix voor CQ-4245237
* (DM Hybrid) Kopieer URL voor gepubliceerde VideoMiddelen of Gemengde Plaatsen van Media krijgt &quot;`[object Object]`&quot;in de dialoog URL. Hotfix voor CQ-4245236, CQ-4245451
* (DMHybrid) De pagina van de Mening van de Details van Video bevat niet de voorproef van VideoActiva tonen en output een foutenmelding aan de console. Hotfix voor CQ-4244320
* Automatische S7-codering van ons.Retail-inhoud. Hotfix voor CQ-4242253
* Er kan geen nieuwe voorinstelling voor videocodering worden toegevoegd of de bestaande coderingsvoorinstellingen worden bewerkt voordat u een upgrade van de videoverwerkingsvoorinstellingen uitvoert. Hotfix voor CQ-4240407
* Voorinstellingen voor afbeeldingen vóór de upgrade worden weergegeven als Niet gepubliceerd op de pagina Uitvoeringen en geven geen URL. Hotfix voor CQ-4240406
* (CSS) Elementen worden weergegeven, maar de gebruikte viewers zijn standaard en niet de OTB-viewers. Hotfix voor CQ-4239839
* Uitgeschakelde opschoonstap handig uitvoeren en gebruik van particuliere koraalklassen. Hotfix voor CQ-4239729
* De afbeeldingsviewer genereert een fout en geeft de juiste slimme uitsnijding niet weer. Hotfix voor CQ-4237564
* Verouderde voorinstelling onder /etc lijkt te zijn verbroken en niet te zijn gemigreerd naar een locatie onder /conf tijdens het opslaan. Hotfix voor CQ-4237416
* Regressie in OOB VideoViewer 5.8.x - de viewer breidt iframe naar rechts uit en verbreedt daardoor de paginalay-out. Hotfix voor CQ-4235465
* (DMS7) De URL van de uitvoering voor SmartCrop en de knoppen Embed zijn actief voor afbeeldingen die niet zijn gepubliceerd. Hotfix voor CQ-4233696
* (DMHybrid) Vorige uitsnijd/rotatiefunctie herstellen. Hotfix voor CQ-4239489
* Wanneer u een video voorvertoont in de kaartweergave, schakelt u de afspeelknop niet in of uit om te pauzeren. Hotfix voor CQ-4238592
* Bij het uitvoeren van een Opt-In-upgrade wordt de YouTube-configuratie niet verplaatst of gekopieerd van de oude locatie naar de nieuwe locatie. Hotfix voor CQ-4238590
* DropTwee OTB AVS-videoverwerkingsprofielen worden weergegeven onder Mapeigenschappen en slechts één bevat gedefinieerde coderingen. Hotfix voor CQ-4238096
* (DMS7) Slim uitsnijden: Gedetailleerde weergave: De knop URL heeft het label Knop Kopiëren voor uitvoeringen. Hotfix voor CQ-4237804
* Pagina met voorinstellingen voor viewer blijft leeg, zelfs nadat u de krullopdrachten hebt uitgevoerd. Hotfix voor CQ-4243246
* Uitgeschakelde opschoonstap handig uitvoeren en gebruik van particuliere koraalklassen. Hotfix voor CQ-4239729
* Video Report Details page does not show video asset. Hotfix voor CQ-4246208

**DAM - DMServices**

* (DMS7) Cloud Configuration: Kan nieuwe inhoud niet synchroniseren met Scene7 na het bijwerken naar SP1. Hotfix voor CQ-4244437
* (DMHybrid) Kleurprofielen en catalogusinstellingen worden niet geregistreerd in een aanroep van debug_info=catalog. Hotfix voor CQ-4242346
* Voeg kleurprofielen toe aan de klantinstellingen op de leveringsservers. Hotfix voor CQ-4241818, CQ-4241819
* (DMHybrid) Na 6.3 &amp;gt; 6.4-upgrade, worden catalogusinstellingen verplaatst naar het onjuiste knooppunt. Hotfix voor CQ-4239974, CQ-4239975
* (DMHybrid) het buggy-viewervoorinstellingenscript maakt niet de knooppunten die nodig zijn om de catalogusinstellingen te wijzigen. Hotfix voor CQ-4240076
* Wanneer u de vervolgkeuzelijst &quot;Indeling&quot; gebruikt en PNG- of JPG-indelingen selecteert, wordt het gedownloade bestand weergegeven als oververzadigd en donkerder dan het oorspronkelijke element. Hotfix voor CQ-4240073
* (DMS7) Verwijder de MIME Type-toewijzing: image_x-eps. Hotfix voor CQ-4240394
* (DMS7) Uploadparameters voor afdekachtergrond gaan niet naar ipsApiService.log en werken dus niet. Hotfix voor CQ-4240686
* Als u een upgrade uitvoert van de afbeeldingsverwerkingsprofielen die in een 6.3- tot 6.4-instantie zijn gemaakt, wordt de eigenschap Uitsnijden verbroken. Hotfix voor CQ-4237739
* (Dynamic Media) Het regelmatig uploaden van middelen buiten de map smartcrop mislukt. Hotfix voor CQ-4237670
* Pas de fallbackcode voor profielen Adaptive Video Encoding aan in Adaptive_Video_Encoding. Hotfix voor CQ-4237666
* De EmbedXMP-gegevens worden altijd ingesteld op &quot;actief&quot; voor het genereren van profielen. Hotfix voor CQ-4234498
* CMYK-afbeeldingsuitvoering heeft een onjuiste verzadiging. Hotfix voor CQ-4235470
* De montages van de Server van het beeld worden niet herhaald aan levering terwijl de replicatielogboeken hen succesvol merken. Hotfix voor CQ-4239480, CQ-4239046
* (DMS7) Kan geen sets maken met oude/nieuwe verwijzingen naar Cloud Configuration. Hotfix voor CQ-4238078
* In de workflowstap Scene7 wordt Scene7 alleen in de naam en in de beschrijving gelezen, maar wordt de workflowstap in de DAM Update-workflow niet verduidelijkt. Hotfix voor CQ-4237865

**DAM - Slimme tags**

* Introductie [Verbeterde slimme tags](https://docs.adobe.com/content/help/en/experience-manager-64/assets/administer/enhanced-smart-tags.html). NPR-21951

**Forms**

AEM Forms-oplossingen worden geleverd via invoegpakketten en andere patchinstallatieprogramma&#39;s die bij de release worden geleverd. Zie AEM Forms-releases voor meer informatie.

De belangrijkste markeringen voor AEM Forms zijn:

* AEM Forms introduceert de [mogelijkheid voor transactierapporten](https://docs.adobe.com/content/help/en/experience-manager-64/forms/transaction-reports/transaction-reports-overview.html) om transacties zoals verzonden formulieren, verwerkte documenten en gerenderde documenten bij uw AEM Forms-implementatie bij te houden en te tellen. Het biedt inzicht in productgebruik en helpt zakelijke gebruikers de volumes van digitale verwerking te begrijpen.
* PDF/UA-ondersteuning voor XML-formulieren ingeschakeld.
* Toegevoegde allowProxy = true voor Clientlib **aemfd.ccm.channel.contentPage**
* Bijgewerkte code om geavanceerde zoekopdrachten naar titels te maken zoals ze bevatten in plaats van gelijk.
* Update aan nieuwe versie van de Manager van het Pakket van de Knoop (NPM) op de Ononderbroken Machine van de Integratie.

**Forms-invoegtoepassing**

**Backend-integratie**

* Er wordt een fout gegenereerd wanneer een optioneel veld de waarde null krijgt. NPR-24397
* Het aanroepen van WSDL mislukt wanneer het element een andere naamruimte heeft dan een algemene naamruimte. NPR-24281
* (FDM WSDL) Getting DermisException: Uitzonderlijke lijstgegevens in het geval van een array van het type eigenschap. NPR-24265
* (FDM WSDL) Getting DermisException: java.lang.Exception: createSOAPParam: Ongeldige parameters. NPR-24264
* (FDM Client SDK) Kan het testen van de voorprocessor en de aangepaste verzendactie niet uitvoeren. Hotfix voor CQ-4238469
* Oplossingen voor Javadoc-problemen in Dermis. Hotfix voor CQ-4244250
* Verbeterde invoer in WSDL (Web Services Description Language). Hotfix voor CQ-4244133
* Het basis authentificatietesten voor WSDL resulteert in verschillende fout voor de zelfde configuratie in AEM 6.3 en AEM 6.4. Hotfix voor CQ-4244132
* Verzoek om ValueUtil op te nemen in client-sdk en javadocs. Hotfix voor CQ-4242803
* (FDM Cloud Config) Kan SOAP-gebaseerde verificatie niet configureren vanuit de cloudconfiguratie. Hotfix voor CQ-4238462
* Dermis - Voeg ontbrekende pakketten toe in JavaDocs. Hotfix voor CQ-4242815
* WSDLInvokerParams die moeten worden opgenomen in de Forms Add-On client-SDK. NPR-23381: Hotfix voor CQ-4240233

**Adaptieve Forms**

* De vertoning van het document (IC) zou als transactie moeten worden geregistreerd gebruikend de Dienst van de Opname van de Transactie. Hotfix voor CQ-4245333
* Tijdens het uitvoeren van UAT5 ontbreekt een item in pdf die in het werkgebied wordt gegenereerd. Hotfix voor CQ-4243184
* Test case voor deep copy van guideContext. Hotfix voor CQ-4242924
* Het proeftypegebied ontbreekt bij het uitvoeren van UAT3 op recentste promotieserver. Hotfix voor CQ-4243120
* Op de geüpgrade server ontbreekt het ingediende formulier de waarden voor Staat/provincie/regio en Land die aanwezig waren op de pre-upgrademeserver. Hotfix voor CQ-4241444
* (ExpressionEditor) Fout tijdens het navigeren om het werkgebied te verifiëren tijdens het verzenden van het formulier. Hotfix voor CQ-4241384
* Waarden ontbreken in het controlestadium op de pre-upgrade- en upgradeserver voor het ingediende formulier. Hotfix voor CQ-4241896
* De knop Afsluiten en opslaan onder aan de pagina werkt niet. Hotfix voor CQ-4240112
* Contactnummer ontbreekt in de bijgewerkte installatie. Hotfix voor CQ-4239870
* Onder `ACTION TAKEN` sectie in het lusje van het Type van Geschil, &quot;de Extra documenten om mijn eis te steunen&quot;heeft extra gebied het Type van Bewijs dat &quot;in het wordt bewaard. Hotfix voor CQ-4239873
* Fout in getDataAPI-fout aangetroffen in het werkgebied verifyPDF. Hotfix voor CQ-4239865
* Fouten in migratielogboeken voor auteur en publicatieinstantie. Hotfix voor CQ-4239365
* Fouten in migratielogboeken voor auteur en publicatieinstantie. Hotfix voor CQ-4239635
* Deserialisatiefout zoals &quot;Deserialization not allowed for class sun.util.agenda.ZoneInfo&quot; in foutlogboeken na verzending van een adaptief formulier. Hotfix voor CQ-4240419
* Het statusveld wordt niet ingevuld in de uitvoering van een mobiel formulier. Hotfix voor CQ-4240597
* Referentiegebruik van componenten in sjablonen verwijderen uit de lijst met patronen. Hotfix voor CQ-4239217
* Numerieke vakken voor HTML5 die zijn ingesteld als zwevend of decimaal, geven verschillende validatieresultaten in verschillende browsers. NPR-23528: Hotfix voor CQ-4244097
* (Afbeelding uploaden) Afbeelding wordt niet weergegeven in DOR-voorvertoning. Hotfix voor CQ-4243178
* De JEE-server geeft een foutmelding weer bij het verzenden van het adaptieve formulier met &quot;E-mail-PDF&quot; en &quot;Include-bijlagen&quot;. Hotfix voor CQ-4239894
* Diagram wordt tijdens runtime niet getekend met een tabel/deelvenster. Hotfix voor CQ-4240010
* Aangepast verzenden van formulieren werkt niet en het aantal transacties verandert niet omdat verzending is mislukt. Hotfix voor CQ-4246125
* (Afbeeldingskeuze) Documenten met recordopties zijn niet zichtbaar. Hotfix voor CQ-4236976
* De interface van de sjablooneditor is niet stabiel. Hotfix voor CQ-4241497
* AF&#39;s worden niet weergegeven met het tabblad Elementen van het zijpaneel, maar worden wel weergegeven met de bladeroptie voor AEM eigenschappendialoogvenster van formuliercomponenten. Hotfix voor CQ-4236751
* De workflow-id die voor formulierconversie wordt gegenereerd, moet beschikbaar zijn in het gegenereerde adaptieve formulier. Hotfix voor CQ-4240014
* Kan geen sjabloon selecteren om een pagina in sites te maken bij Direct upgraden: Livecycle naar 6.4-server. Hotfix voor CQ-4241300

**Assembler-service**

* Aanmelden van transacties bij Assembler Services. Hotfix voor CQ-4245018, CQ-4245017, CQ-4245016.
* Transactie wordt niet gerapporteerd wanneer PDF/A-conversie wordt uitgevoerd met DDX. Hotfix voor CQ-4246039

**Forms Manager**

* FM CREATE-knoplijst die alfabetisch moet worden gesorteerd. Hotfix voor CQ-4242307

**Formulierportal**

* Concepten die zijn opgeslagen op de pre-upgradeserver, worden niet correct geopend op de geüpgrade server. Hotfix voor CQ-4243303
* Versie-update naar 7.1 voor adobe-formsmanager-core-module. Hotfix voor CQ-4245753
* Concepten die zijn opgeslagen op de pre-upgradeserver, worden niet correct geopend op de geüpgrade server. Hotfix voor CQ-4243303
* Bijlagescenario&#39;s breken bij het vervangen/toevoegen/verwijderen van bijlagen in nieuwe instantie/zelfde geval van ontwerp. Hotfix voor CQ-4243165
* Het aantal concepten dat is opgehaald uit het opvragen van de database, is groter dan het aantal concepten dat aanwezig is in het portaal. Hotfix voor CQ-4241489
* Forms die wordt verzonden op een pre-upgradeserver, is niet aanwezig op de geüpgrade server. Hotfix voor CQ-4241490
* Het formulier dat in de gebruikersinterface op het tabblad Verzending wordt weergegeven, bevindt zich in de status Niet verzonden, ondanks een succesvol verzonden bericht. Hotfix voor CQ-4241487
* De guideContext moet worden gevormd door de velden grondig te kopiëren, aangezien guideContext customPropertyMap bevat die zelf een object is. Hotfix voor CQ-4240126
* Fout bij het opslaan van een formulier. Hotfix voor CQ-4240763
* De ingang voor bewaarde en voorgelegde vormen wordt bevolkt in crx/de ondanks wij de configuratie van OB die in het Ontwerp van het Portaal van Forms wordt gegeven en de Configuratie van de Verzending. Hotfix voor CQ-4240726
* (Zoeken en register) De vaste waarde van een geavanceerde zoektitel moet werken als bevat in plaats van gelijk. Hotfix voor CQ-4245499

**Mobile Forms**

* Datumveld overlapt in Mobile Forms. Hotfix voor CQ-4242256
* Formulierverzending voor Mobile Forms moet worden geregistreerd als een transactie met de Transactie Recording Service. Hotfix voor CQ-4246166
* De voorlegging van het formulier in Formset zou als transactie moeten worden geregistreerd gebruikend de Dienst van de Opname van de Transactie. Hotfix voor CQ-4246165

**AEM Forms App**

* (Windows App) Kan het formulier niet genereren. Hotfix voor CQ-4238005

**Workflow OSGI**

* Transactielogboekregistratie in Workflowtoewijzing Taak. Hotfix voor CQ-4244440
* (FDM Stap) Kan geen waarden van werkschemagegevens gebruiken wanneer een Assign stap van de Taak tussen de processtap en fdm stap wordt opgenomen. Hotfix voor CQ-4241472
* Het delegeren van een taak werkt niet in Forms Integration in OSGI Workflows. NPR-23709: Hotfix voor CQ-4243700
* (Workflow Model Editor) Sommige workflowmodellen kunnen niet worden bewerkt via de ClassicUI WF model editor. Hotfix voor CQ-4241151

**MultiChannel-document**

* Het datumveld in Sjabloon overlapt het subformulier in de IC-ontwerpomgeving. Hotfix voor CQ-4240110
* Koptekst mag niet worden verwijderd of omhoog en omlaag worden verplaatst in IC-webkanaalontwerpfuncties. Hotfix voor CQ-4243358
* (IC Editor) Standaardrijen die moeten worden ingesteld op 1 voor tabelcomponenten. Hotfix voor CQ-4244848
* Doelgebied blijft zichtbaar, zelfs nadat de inhoud is gesleept en erop is neergezet. Hotfix voor CQ-4244534
* Webkanaal herkent geen tabruimte in tekstdocumentfragmenten. Hotfix voor CQ-4244481
* (Kanaal van de Druk) de vertoning van het Document (IC) zou als transactie moeten worden geregistreerd gebruikend de Dienst van de Opname van de Transactie. Hotfix voor CQ-4245335
* (Het kanaal van het Web) de vertoning van het Document (IC) zou als transactie moeten worden geregistreerd gebruikend de Dienst van de Opname van de Transactie. Hotfix voor CQ-4245334
* Zoeken in documentcontainers of de zoekopdracht in de gegevensmodelstructuur moet gelijk zijn aan de zoekopdracht in het middelenfilter. Hotfix voor CQ-4242305
* (Documentfragment) Met de eigenschap inspringing wordt de tekst ingesprongen met de hoeveelheid eenheden die niet kan worden geïnterpreteerd. Hotfix voor CQ-4241082, CQ-4240643
* (IC Editor) Het pictogram Fragment bewerken op de tegel van het documentfragment dat op het tabblad Elementen wordt weergegeven, is niet erg gemakkelijk te vinden en te begrijpen. Hotfix voor CQ-4241047
* Anonieme toegang tot de anonieme ontoegankelijke clientbibliotheek van IC toestaan. Hotfix voor CQ-4245588
* (Webkanaal) Gegevens worden in geen van de tabellen in de webvoorvertoning omgezet en worden als leeg weergegeven. Hotfix voor CQ-4244476
* Tabelkoppen worden als variabelen weergegeven in het webkanaal bij automatisch genereren. Hotfix voor CQ-4244242
* (IC Editor) De inhoud van een documentfragment dat in een IC wordt gebruikt, moet automatisch worden aangepast aan de breedte van het doelgebied. Hotfix voor CQ-4244094
* De kanaalnaam die in de middelste bovenkant wordt weergegeven, moet consistent zijn met de IC-titel voor WEB/PRINT. Hotfix voor CQ-4242498
* In het deelvenster Gegevens van teksteditor mogen alleen entiteiten op hoofdniveau worden vermeld, hotfix voor CQ-4244121
* De standaardnaam wordt niet toegewezen wanneer het toevoegen van een nieuwe component in redacteur. Hotfix voor CQ-4244691
* De Colspan-configuratie toevoegen in alle webkanaalcomponenten. Hotfix voor CQ-4244946
* De eigenschap Breedte van layoutfragmenttabel wordt niet opnieuw ingesteld en wordt niet ondersteund in het afdrukkanaal voor Letter- of Klantcommunicatie. Hotfix voor CQ-4241574

**Correspondentenbeheer**

* Bijschriften die uit een lettertypesjabloon zijn verwijderd nadat een tekstelement met plaatsaanduidingen is bewerkt. NPR-24196
* Als het XDP-bestand wordt geüpload en wordt gebruikt als lay-out voor lettertypesjablonen, kunt u de sjablonen niet voorvertonen of bewerken. NPR-24143: Hotfix voor CQ-4244407
* Selectie van toewijzing is standaard geselecteerd in lijstfragment. Hotfix voor CQ-4240097
* De redacteur van de voorwaarde - de veelvoudige resultaatevaluatie zou door gebrek moeten worden toegelaten. Hotfix voor CQ-4240096
* Afbeelding die uit lijst wordt verwijderd, toont nog steeds de voorvertoning van de afbeelding. Hotfix voor CQ-4239909
* De regel die op de voorwaardemodule wordt geplaatst wordt geplaatst als &quot;Gebrek&quot;voor alle module(s). Hotfix voor CQ-4239878
* Maken gegevenswoordenboek mislukt vanwege fout Onbekende JCR. Hotfix voor CQ-4244122
* Tussenruimten in JavaDocs voor 6.3-inhoud. Hotfix voor CQ-4213586

**Forms JEE-installatieprogramma**

**Kern**

* (HTML Workspace) Er ontbreken gegevens voor het bijhouden van de gegevens voor toepassingen met een haakjessymbool in de naam. NPR-23402

**PDFG-service**

* Transactielogboekregistratie in PDFG-services. Hotfix voor CQ-4244951, CQ-4244586
* PDF&#39;s reduceren door lettertypen selectief te verwijderen via één API-aanroep. NPR-23287
* Update-probleem met PDFG-configuraties bij AEM upgrade. Hotfix voor CQ-4241176
* Transactielogboekregistratie in PDFUtility Service. Hotfix voor CQ-4245014

**Procesbeheer**

* (HTML-werkruimte) Beginpunten van processen worden niet in alfanumerieke volgorde gesorteerd. Hotfix voor CQ-4239629
* (HTML-werkruimte) Bereid de gegevensaanroep voor die tweemaal verschijnt wanneer het concept de eerste keer wordt geopend. Hotfix voor CQ-4243280
* (HTML-werkruimte) Gegevensproces voorbereiden wordt geactiveerd wanneer een formulier wordt gesloten. Hotfix voor CQ-4239456
* De werkruimte loopt vast wanneer deze wordt verplaatst tussen twee taken. Hotfix voor CQ-4237125

**Workbench**

* Het gegevensproces voor het voorbereiden van een Action Profile-bewerking kan worden beheerd als de standaardconfiguratie voor het renderproces is ingesteld op HTML. Hotfix voor CQ-4244292

**Forms Designer**

* Voeg PDF/UA-ondersteuning toe aan XML-formulieren die zijn gegenereerd via Designer en Output Service. NPR-23022
* inline-hyperlinks die zijn gedefinieerd in Designer, krijgen geen label en hebben geen alternatieve tekst wanneer deze worden opgeslagen als PDF in Designer. NPR-23023

**Inclusief functiepakketten**

**Activa**

* De functie voor verbeterde slimme tags is toegevoegd. Zie [Verbeterde slimme tags](https://docs.adobe.com/content/help/en/experience-manager-64/assets/administer/enhanced-smart-tags.html) voor meer informatie. NPR-21951: Hotfix voor CQ-4234883
* Introductie AEM Assets References in InDesign. Zie [AEM Assets-verwijzingen in InDesign](/help/assets/managing-linked-subassets.md) voor meer informatie. NPR-23386

**Sites**

* (Paginaontwerp) Verbeteringen in de afbeeldingseditor. Zie [Afbeeldingseditor](https://docs.adobe.com/content/help/en/experience-manager-64/developing/components/image-editor.html) voor meer informatie. NPR-24267: Hotfix voor CQ-4245502

**SDAB-pakketten en -inhoudspakketten**

In de volgende tekst wordt de lijst met OSGI-bundels en -inhoudspakketten in het GVB opgenomen.

Lijst van OSGi-bundels opgenomen in AEM 6.4.1.0

[Bestand ophalen](assets/6_4_1_0_bundle-list.txt)

Lijst van inhoudspakketten opgenomen in AEM 6.4.1.0

[Bestand ophalen](assets/6_4_1_0_content-package-list.txt)

### Installatie 6.4.8.0 {#install}

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
>Voor klanten met op AEM 6.4 geïnstalleerde de Pakken van de Eigenschap. De facultatieve die Packs van de Eigenschap door Adobe worden verstrekt hebben gebiedsdelen op de versieversie en de dienstpak. Als u een Feature Pack hebt geïnstalleerd, neemt u contact op met het AEM Customer Care-team om de compatibiliteit van deze functiepakketten met dit servicepakket voor AEM 6.4 te valideren.

* AEM 6.4.8.0 vereist AEM 6.4. Zie [upgrade documentation](../sites-deploying/upgrade.md) voor meer informatie.
* De download van Service Pack is beschikbaar op [Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) voor download.
* Voor een plaatsing met MongoDB en veelvoudige instanties, installeer AEM 6.4.8.0 op één van de instanties van de Auteur gebruikend de Manager van het Pakket.
* Voordat u het servicepack installeert, moet u zorgen voor een momentopname of een nieuwe back-up van uw AEM.
* Start de instantie opnieuw voor de installatie. Hoewel dat alleen nodig is wanneer de instantie zich nog in de updatemodus bevindt (en dit is het geval wanneer de instantie zojuist is bijgewerkt vanaf een eerdere versie), wordt het doorgaans aanbevolen als de instantie langer actief was.

>[!NOTE]
>
>Adobe raadt u niet aan het pakket AEM 6.4.8.0 te verwijderen of te verwijderen.

### Installeer het Service Pack via Package Manager {#install-the-service-pack-via-package-share}

Voer de volgende stappen uit om het Service Pack op een bestaande AEM 6.4 instantie te installeren:

1. Download het pakket van de Distributie van de Software.

1. Meld u AEM aan bij Package Manager en voeg het gedownloade AEM 6.4.8.0-pakket toe. Selecteer het geüploade pakket en klik op **[!UICONTROL Install]**.

>[!NOTE]
>
>**Dialoogvenster over de UI van de Manager van het Pakket sluit soms ongeschikt tijdens installatie van 6.4.8.0**
>
>Daarom wordt aangeraden te wachten totdat de foutenlogboeken zich stabiliseren voordat u de instantie opent. De gebruiker moet op specifieke logboeken met betrekking tot het verwijderen van updaterbundel wachten alvorens wordt gewaarborgd dat de installaties succesvol zijn. Het gebeurt meestal in Safari, maar kan af en toe in elke browser gebeuren.

### Automatische installatie {#auto-installation}

Er zijn twee manieren om AEM 6.4.8.0 in een lopende instantie automatisch te installeren:

A. Plaats de verpakking in ...*/crx-quickstart/* installfolder terwijl de server loopt. Het pakket wordt automatisch geïnstalleerd.

B. Gebruik [HTTP API van de Manager van het Pakket](https://docs.adobe.com/content/docs/en/crx/2-3/how_to/package_manager.html) - zorg ervoor u `cmd=install&recursive=true` gebruikt - zodat wordt het genestelde pakket geïnstalleerd.

>[!NOTE]
>
>AEM 6.4.8.0 ondersteunt geen Bootstrap-installatie.

### Installatie {#validate-install} valideren

1. Op de pagina Productinformatie (*/system/console/productinfo *) moet nu de bijgewerkte versietekenreeks &quot;Adobe Experience Manager, Version 6.4.8.0&quot; onder Geïnstalleerde Producten worden weergegeven.
1. Alle OSGI-bundels zijn actief of FRAGMENT in de OSGI Console (Webconsole gebruiken: /systeem/console/bundels).
1. De OSGI-bundel org.apache.jackrabbit.oak-core bevindt zich op versie 1.8.17 of hoger (gebruik webconsole: /systeem/console/bundels).

Zie [Technische vereisten](../sites-deploying/technical-requirements.md) voor informatie over het gecertificeerde platform voor deze versie van AEM Sites en Middelen.

>[!NOTE]
>Na een geslaagde installatie van het pakket wordt een >informatief bericht weergegeven dat de inhoud >package is geïnstalleerd, zoals **&quot;Content Package AEM-6.4-Service-Pack-7 is geïnstalleerd.&quot;**

### Dynamic Media Viewers bijwerken (5.10.1) {#update-dynamic-media-viewers}

<p id="Dynamic">AEM 6.4.8.0 bevat een nieuwe versie van Dynamic Media-viewers (5.10.1), waarmee u kunt controleren op dubbele namen op de pagina met voorinstellingen voor afbeeldingen. Dynamic Media-klanten wordt aangeraden de volgende opdracht uit te voeren om de voorinstellingen van de viewer uit de box te halen.

`curl -u admin:admin http://localhost:4502/libs/settings/dam/dm/presets/viewer.pushviewerpresets`

Hiermee worden nieuwe voorinstellingen van de viewer naar de locatie /conf gekopieerd.

### Invoegpakket voor AEM formulieren installeren {#install-aem-forms-add-on-package}

#### Invoegtoepassing AEM formulieren installeren {#installaemformsaddon}

>[!NOTE]
>
>Sla dit over als u AEM Forms niet gebruikt. Correcties in AEM Forms worden geleverd via een afzonderlijk invoegpakket.

>[!NOTE]
>
>AEM 6.4.8.0 bevat een nieuwe versie van [AEM Forms-compatibiliteitspakket](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/compatpack/AEM-FORMS-6.4.7.0-COMPAT). Als u een oudere versie van het AEM Forms Compatibility Package gebruikt en een update naar AEM 6.4.8.0 uitvoert, installeert u de nieuwste versie van het AEM Forms-compatibiliteitspakket na de installatie van het Forms Add-on Package.

1. Controleer of u het AEM Service Pack hebt geïnstalleerd.
1. Download het overeenkomstige formulierinvoegpakket dat u vindt op [AEM Forms-releases](https://helpx.adobe.com/aem-forms/kb/aem-forms-releases.html) voor uw besturingssysteem.
1. Installeer het formulierinvoegpakket zoals beschreven in [AEM formulierinvoegpakketten installeren](https://docs.adobe.com/content/help/en/experience-manager-64/forms/install-aem-forms/osgi-installation/installing-configuring-aem-forms-osgi.html#install-aem-forms-add-on-package).

### AEM Forms JEE-installatieprogramma {#install-aem-forms-jee-installer} installeren

>[!NOTE]
>
>Sla dit over als u AEM Forms niet gebruikt op JEE. Correcties in AEM Forms JEE worden geleverd via een afzonderlijk installatieprogramma.

Zie [AEM Forms JEE Patch Installer 0015](https://helpx.adobe.com/aem-forms/quick-fixes/6-4/jee-patch-0015.html) voor informatie over de installatie van het cumulatieve installatieprogramma voor AEM Forms JEE en de configuratie na de implementatie.

#### Voor NPR-21268 {#configuration-settings-required-for-npr} vereiste configuratie-instellingen

Als u de klassieke (oude) UI gebruikt en meta-gegevensmalplaatjes gebruikend het hebt gecreeerd, volg de stappen om het manuscript in werking te stellen JMX om hen te bewaren -

1. Ga naar /system/console/jmx.
1. Klik op &#39;Metagegevenssjablonen migreren&#39;.
1. Klik op &quot;migrateMetadataTemplatesAtPath&quot; en geef het mappad op waarin u de sjablonen voor metagegevens wilt behouden.

#### Voor NPR-24536 vereiste configuratie-instellingen {#configuration-settings-required-for-npr-1}

De telling voor gedeelde Rij verfrist zich, door gebrek, niet voor andere gebruikers wanneer een gebruiker een taak eist. Hiervoor hebben we een nieuwe eigenschap ingevoerd. Voer de onderstaande stappen uit om deze eigenschap op uw AEM-instantie te configureren:

1. Ga naar Admin UI -> Services -> Werkruimte -> Globaal beheer.
1. Algemene instellingen exporteren.
1. Voeg in het gedownloade XML-bestand de tag &lt;client_tasksPollingInterval>10&lt;/client_tasksPollingInterval> hier toe. De voorbeeldwaarde in seconden is 10. U kunt het dienovereenkomstig wijzigen.
1. Sla het bestand op.
1. Ga terug naar de interface van Admin -> Services -> Werkruimte -> Globaal beheer.
1. Importeer het XML-bestand in het gedeelte Algemene instellingen importeren.
1. U kunt zich nu afmelden bij het systeem en u opnieuw aanmelden.
1. De telling voor gedeelde rij begint voor andere gebruikers in de werkruimte te verfrissen.
1. Als u de opiniepeiling wilt uitschakelen, wijzigt u de waarde in 0 en importeert u het XML-bestand opnieuw.

### Uber Jar {#uber-jar}

De Uber Jar voor AEM 6.4.8.0 is beschikbaar in [Adobe Public Maven repository](https://repo.adobe.com/nexus/content/groups/public/com/adobe/aem/uber-jar/6.4.8/).

Om Uber Jar in een Geweven project te gebruiken, verwijs naar het artikel, [Hoe te om Uber jar](../sites-developing/ht-projects-maven.md) te gebruiken en de volgende gebiedsdeel in uw projectPOM te omvatten:

```shell
<dependency>
      <code>com.adobe.aem</groupId>
      <artifactId>uber-jar</artifactId>
      <version>6.4.8</version>
      <classifier>apis</classifier>
      <scope>provided</scope>
</dependency>
```

### Verwijderde/vervangen functies {#removed-deprecated-features}

Deze sectie bevat een lijst met functies en mogelijkheden die zijn verwijderd of verouderd uit AEM 6.4.

| Gebied | Functie | Vervanging | Versie |
|---|---|---|---|
| Assets | Tagactie beheren voor submiddelen | Geen vervanging | AEM 6.4.2.0 |
| Integratie van middelen en Adobe Creative Cloud | [AEM naar het ](https://docs.adobe.com/content/help/en/experience-manager-64/assets/administer/aem-cc-folder-sharing-best-practices.html) delen van mappen in Creative Cloud is in AEM 6.2 geïntroduceerd als een manier om creatieve gebruikers toegang te geven tot middelen van AEM. Een nieuwe mogelijkheid die wordt vrijgegeven in de Creative Cloud-toepassing, de Adobe Asset Link, biedt een veel betere gebruikerservaring en een krachtigere toegang tot middelen van AEM rechtstreeks vanuit Photoshop, InDesign en Illustrator. Adobe zal geen verdere verhogingen aan de omslag het delen capaciteit maken. Hoewel de functie in AEM is opgenomen, wordt het klanten sterk aangeraden de vervangende functie te gebruiken. | Adobe Asset Link of desktop app. Zie [AEM Creative Cloud integratie](/help/assets/aem-cc-integration-best-practices.md) artikel voor meer informatie. | AEM 6.4.4.0 |

### Bekende problemen {#known-issues}

* De volgende fouten en waarschuwingen kunnen tijdens de installatie worden weergegeven:

   * Fouten bij het maken van een componentinstantie en de geretourneerde waarde null in de servicefabriek treden op als gevolg van het opnieuw opstarten van de opslagplaats:

      * com.day.cq.cq-personalization \[com.day.cq.personalization.impl.DefaultProfileProvider(938)\] Kan componentinstantie niet maken omdat de profielmanager van de referentie niet kan worden gebonden
      * org.apache.sling.commons.planner FrameworkEvent ERROR (org.osgi.framework.ServiceException: Service factory heeft null geretourneerd. (Component: com.day.cq.tagging.impl.TagGarbageCollector (1687)
   * `com.adobe.cq.social.cq-social-jcr-provider bundle com.adobe.cq.social.cq-social-jcr-provider:1.3.5 (395)[com.adobe.cq.social.provider.jcr.impl.SpiSocialJcrResourceProviderImpl(2302)]` : Time-out bij wachten op wijziging van reg om niet-geregistreerd te voltooien.
   * `com.adobe.granite.maintenance.impl.TaskScheduler` Geen onderhoudsvensters gevonden bij graniet/bediening/onderhoud
   * `com.adobe.cq.com.adobe.cq.ui.commons bundle com.adobe.cq.com.adobe.cq.ui.commons:1.2.28 (204)[com.adobe.cq.ui.wcm.commons.internal.servlets.rte.RTEFilterServletFactory(573)]`: De methode unbindAmendement heeft een uitzondering gegenereerd (java.lang.IllegalStateException: Service is al niet geregistreerd).
Deze fouten vereisen geen actie omdat ze geen invloed hebben op uw AEM.


### Opgeloste problemen {#resolved-issues}

**AEM 6.4.4.0**

* Er is geen fout met betrekking tot de bron gevonden bij het importeren/exporteren van metagegevens. CQ-4253263
* Kan geen afbeeldingscomponent en pagina-eigenschappen bewerken nadat 6.4.3.0 is toegepast boven op 6.4.2.0. CQ-4260316 &amp; CQ-4260441
U kunt dit probleem als volgt oplossen:
   * Ga naar Pakketbeheer
   * Pakket &quot;cq-ui-wcm-admin-content-1.0.1004.zip&quot; opnieuw installeren
   * Compileer alle JSPs `(http://<AEM HOST>:<AEM PORT/system/console/slingjsp)` OF begin de instantie opnieuw.

### OSGi-bundels en inhoudspakketten inbegrepen {#osgi-bundles-and-content-packages-included}

De volgende tekstdocumenten maken een lijst van de bundels OSGi en de Pakketten van de Inhoud inbegrepen in AEM 6.4.8.0.

Lijst van OSGi-bundels opgenomen in AEM 6.4.8.0

[Bestand ophalen](assets/6.4.8.0_osgi_bundles.txt)

Lijst van inhoudspakketten opgenomen in AEM 6.4.8.0

[Bestand ophalen](assets/6.4.8.0_content_packages.txt)

### Nuttige bronnen {#helpful-resources}

* [Opmerkingen bij de release AEM 6.4](../release-notes/release-notes.md)
* [AEM productpagina](https://www.adobe.com/solutions/web-experience-management.html)
* [AEM 6.4-documentatie](https://helpx.adobe.com/nl/support/experience-manager/6-4.html)
* Abonneren op [Adobe prioritaire productupdates](https://www.adobe.com/subscription/priority-product-update.html)

### Beperkte sites {#restricted-sites-new}

Deze sites zijn alleen beschikbaar voor klanten. Neem contact op met uw Adobe-accountmanager als u een klant bent en toegang nodig hebt.

* [Product downloaden op licensing.adobe.com](https://licensing.adobe.com/).
* Productupdates, patches en pakketten voor extra functionaliteit op [Softwaredistributie](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
* [Klantenondersteuning via Admin Console](https://adminconsole.adobe.com/). Zie [Nieuwe ervaring voor klantenondersteuning van Adobe](https://docs.adobe.com/content/help/en/customer-one/using/home.html) voor meer informatie.
