---
title: Metagegevens van uw digitale middelen beheren
description: Leer meer over de typen metagegevens en hoe u met Adobe Experience Manager de metagegevens voor elementen kunt beheren, zodat u elementen gemakkelijker kunt indelen in categorieën en ordenen. Dankzij de mogelijkheid om willekeurige metagegevens bij uw middelen te houden en te beheren, kunt u elementen automatisch ordenen en verwerken op basis van de metagegevens van de bestanden.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 5ef4c4e42165819191c6e3810c36183110f3f34a

---


# Metagegevens van uw digitale middelen beheren {#managing-metadata-for-digital-assets}

Adobe Experience Manager-middelen bewaren metagegevens voor elk element. Hierdoor kunnen elementen gemakkelijker worden gecategoriseerd en geordend en kunnen mensen die op zoek zijn naar een bepaald bedrijfsmiddel worden geholpen. Dankzij de mogelijkheid om metagegevens te extraheren uit bestanden die zijn geüpload naar Experience Manager Assets, kan het beheer van metagegevens worden geïntegreerd met de creatieve workflow. Met de mogelijkheid van Experience Manager om metagegevens bij uw middelen te houden en te beheren, kunt u elementen automatisch ordenen en verwerken op basis van de metagegevens.

* [XMP-metadata](xmp.md)
* [Metagegevens bewerken of toevoegen](meta-edit.md)
* [Referentie metagegevensschema](meta-ref.md)

## Waarom we metagegevens nodig hebben {#why-we-need-metadata}

Metagegevens zijn gegevens over gegevens. In dit verband verwijzen gegevens naar uw digitale middel, bijvoorbeeld een afbeelding. Metagegevens zijn essentieel voor efficiënt middelenbeheer.

Metagegevens zijn de verzameling van alle gegevens die beschikbaar zijn voor een element, maar die niet noodzakelijkerwijs in die afbeelding voorkomen. Voorbeelden van metagegevens zijn:

* Naam van het element.
* Tijdstip en datum van laatste wijziging.
* Grootte van het middel zoals het in de bewaarplaats werd opgeslagen.
* Naam van de map waarin deze zich bevindt.
* Gerelateerde elementen of toegepaste tags.

Dit zijn de basiseigenschappen voor metagegevens die Experience Manager kan beheren voor elementen, zodat gebruikers alle elementen kunnen zien, bijvoorbeeld geordend op de laatste wijzigingsdatum. Dit is handig wanneer ze proberen te ontdekken welke elementen onlangs aan de opslagplaats zijn toegevoegd.

U kunt meer gegevens op hoog niveau toevoegen aan digitale elementen, bijvoorbeeld:

* Type element (is het een afbeelding, video, audioclip of document?).
* Eigenaar van het actief.
* Titel van het element.
* Beschrijving van het actief.
* Tags die aan een element zijn toegewezen.

Met meer metagegevens kunt u elementen verder indelen. Dit is handig wanneer de hoeveelheid digitale informatie toeneemt. Het is mogelijk om een paar honderd bestanden te beheren op basis van alleen de bestandsnamen. Nochtans, is deze benadering niet scalable en valt snel onder wanneer het aantal betrokken personen en het aantal beheerde activa stijgt.

Wanneer metagegevens aan elementen worden toegevoegd, neemt de waarde van het element toe omdat het element

* toegankelijker - de mensen kunnen het veel gemakkelijker vinden .
* eenvoudiger te beheren - u kunt gemakkelijker middelen zoeken met dezelfde set eigenschappen en er wijzigingen op toepassen.
* complexer - hoe meer metagegevens u aan een element hebt toegevoegd, hoe belangrijker het beheer van metagegevens wordt.

Om deze redenen biedt Experience Manager Assets u de juiste middelen voor het maken, beheren en uitwisselen van metagegevens voor uw digitale elementen.

## Typen metagegevens {#types-of-metadata}

De twee basistypen metagegevens zijn technische metagegevens en beschrijvende metagegevens.

Technische metagegevens zijn handig voor softwaretoepassingen die werken met digitale elementen en mogen niet handmatig worden onderhouden. De Elementen van de Manager van de ervaring en andere software bepalen automatisch technische meta-gegevens en de meta-gegevens kunnen veranderen wanneer het element wordt gewijzigd. De beschikbare technische metagegevens van een element zijn grotendeels afhankelijk van het bestandstype van het element. Voorbeelden van technische metagegevens zijn:

* Grootte van een bestand
* Afmetingen (hoogte en breedte) van een afbeelding
* Bitsnelheid van een audio- of videobestand
* Resolutie (detailniveau) van een afbeelding

De beschrijvende meta-gegevens zijn meta-gegevens betrokken bij het toepassingsdomein, bijvoorbeeld, de zaken die een activa uit komt. Metagegevens met een beschrijving kunnen niet automatisch worden bepaald. Deze wordt handmatig of halfautomatisch gemaakt. Een camera met GPS-functionaliteit kan bijvoorbeeld automatisch de breedte en lengte bijhouden en geotaggen aan de afbeelding toevoegen.

Vanwege de hoge kosten van de handmatige inspanningen die nodig zijn om beschrijvende metagegevens te maken, zijn er normen opgesteld om de uitwisseling van metagegevens tussen softwaresystemen en organisaties te vergemakkelijken.

De Elementen van de Manager van de ervaring steunen alle relevante normen voor meta-gegevensbeheer.

Vanwege het belang van metagegevens en de grote handmatige betrokkenheid die nodig is om metagegevens te maken, zijn er normen opgesteld die het uitwisselen van gegevens vergemakkelijken.

## Coderingsnormen {#encoding-standards}

Er zijn verschillende manieren om metagegevens in bestanden in te sluiten. Een selectie coderingsstandaarden wordt ondersteund:

* XMP: gebruikt door Experience Manager Assets om de opgehaalde metagegevens in de opslagplaats op te slaan.
* ID3: voor audio- en videobestanden.
* EXIF: voor afbeeldingsbestanden.
* Overige/Verouderd: van Microsoft Word, PowerPoint, Excel, etc.

### XMP {#xmp}

XMP (Extensible Metadata Platform) is een open standaard die wordt gebruikt door Experience Manager-middelen voor al het metagegevensbeheer. De standaard biedt universele metagegevenscodering die in alle bestandsindelingen kan worden ingesloten. Adobe en andere bedrijven ondersteunen de XMP-standaard omdat deze een Rich Content Model biedt. Gebruikers van de XMP-standaard en van Experience Manager-middelen hebben een krachtig platform waarop ze kunnen bouwen. For more information, see [XMP](https://www.adobe.com/products/xmp.html).

### ID3 {#id}

Gegevens die in deze ID3-tags zijn opgeslagen, worden weergegeven wanneer u een digitaal audiobestand afspeelt op uw computer of op een draagbare MP3-speler.

ID3-tags zijn ontworpen voor de MP3-bestandsindeling. Aanvullende informatie over indelingen:

* ID3-tags werken in MP3- en MP3PRO-bestanden.
* WAV heeft geen tags.
* WMA heeft merkgebonden markeringen die open-bronimplementatie niet toestaan.
* Ogg Vorbis gebruikt Xiph-opmerkingen die zijn ingesloten in de Ogg-container.
* AAC gebruikt een merkgebonden etiketteringsformaat.

### Exif {#exif}

Exchangeable image file format (Exif) is de meest gebruikte metagegevensindeling voor digitale fotografie. Hiermee kunt u een vaste woordenlijst met metagegevenseigenschappen insluiten in vele bestandsindelingen, zoals JPEG, TIFF, RIFF en WAV. In Exif worden metagegevens opgeslagen als paren van een metagegevensnaam en een metagegevenswaarde. Deze naam-waarde-paren voor metagegevens worden ook wel tags genoemd en mogen niet worden verward met de codering in Experience Manager. Aangezien Exif automatisch door moderne digitale camera&#39;s wordt gecreeerd en door moderne grafieksoftware wordt gesteund, kan het als laagste gemeenschappelijke noemer voor meta-gegevensbeheer worden gezien.

Een belangrijke beperking van Exif is dat een aantal populaire indelingen voor afbeeldingsbestanden, zoals BMP, GIF of PNG, dit niet ondersteunen.

Metagegevensvelden die gewoonlijk door EXIF worden gedefinieerd, zijn van technische aard en zijn van beperkte toepassing voor beschrijvend metagegevensbeheer. Daarom biedt Experience Manager Assets het toewijzen van EXIF-eigenschappen aan [algemene metagegevensschema](metadata-schemas.md) en aan [XMP](xmp-writeback.md).

### Overige metagegevens {#other-metadata}

Andere meta-gegevens die van dossiers kunnen worden ingebed omvatten Microsoft Word, PowerPoint, Excel, etc.

## Metagegevensschema {#metadata-schemata}

Metagegevensschema&#39;s zijn vooraf gedefinieerde sets definities van metagegevenseigenschappen die in verschillende toepassingen kunnen worden gebruikt. Eigenschappen zijn altijd gekoppeld aan een element. Dit houdt in dat de eigenschappen &quot;over&quot; de bron zijn.

U kunt ook uw eigen metagegevensschema&#39;s ontwerpen als er geen schema&#39;s zijn die aan uw behoeften voldoen. Dupliceer bestaande informatie niet. Binnen een organisatie, maakt het scheiden van schema&#39;s het gemakkelijker om meta-gegevens te delen. De Manager van de ervaring voorziet u van een standaardlijst van de populairste meta-gegevensschema&#39;s. De lijst helpt u om uw meta-gegevensstrategie te springen en snel de meta-gegevenseigenschappen te kiezen die u nodig hebt.

De ondersteunde metagegevensschema&#39;s worden hieronder weergegeven.

### Standaardmetagegevens {#standard-metadata}

* dc - Dublin Core - de belangrijkste en meest gebruikte reeks metagegevens.
* DICOM - Digital Imaging and Communications in Medicine.
* Iptc4xmpCore &amp; iptc4xmpExt - International Press Communications Standard - veel onderwerpspecifieke metagegevens.
* rdf - Resource Description Framework - voor algemene semantische webmetagegevens.
* xmp - Extensible Metadata Platform.
* xmpBJ - Basic Job Ticketing.

### Toepassingsspecifieke metagegevens {#application-specific-metadata}

De toepassingsspecifieke metagegevens bevatten technische en beschrijvende metagegevens. Als u deze gebruikt, kunnen andere toepassingen mogelijk de meta-gegevens niet gebruiken. Als u bijvoorbeeld een element hebt met Adobe Photoshop-metagegevens en een andere toepassing voor het renderen van afbeeldingen probeert toegang te krijgen tot de metagegevens, heeft deze mogelijk geen toegang tot de metagegevens. Als u ontdekt dat u veel toepassing-specifieke meta-gegevens in uw activa hebt, kunt u een werkschemagestap tot stand brengen die een toepassing-specifieke bezit in een standaardbezit verandert.

* acdsee - metagegevens beheerd door het ACDSee-programma [www.acdsee.com/](https://www.acdsee.com/).
* album - Adobe Photoshop Album.
* cq - wordt gebruikt door Experience Manager Assets.
* dam - gebruikt door Experience Manager Assets.
* Index - Optima SC Description Explorer.
* crs - Adobe Photoshop Camera Raw.
* lr - Adobe Lightroom.
* mediapro - IView MediaPro.
* MicrosoftPhoto &amp; MP - Microsoft Photo.
* pdf en pdfx
* Photoshop &amp; psAux - Adobe Photoshop

### Metagegevens van Digital Rights Management {#digital-rights-management-metadata}

* cc - creative commons
* xmpRights
* plus - Picture Licensing Universal System - https://www.useplus.com/
* prism - https://www.idealliance.org/prism-metadata Publishing Requirements for Industry Standard Metadata
* prl - Prism Rights Language
* pur - Rechten van riskgebruik
* xmpPlus - integratie van PLUS met XMP

### Specifieke metagegevens voor fotografie {#photography-specific-metadata}

* exif - veel technische informatie van de camera, waaronder de GPS-positie
* crs - photoshop camera raw
* Iptc4xmpCore en iptc4xmpExt
* TIFF - metagegevens van afbeeldingen (niet alleen voor TIFF-afbeeldingen)

### Afdrukspecifieke metagegevens {#print-specific-metadata}

* pdf en pdfx - Adobe PDF en toepassingen van derden
* prism - [www.prismstandard.org](https://www.prismstandard.org) Publicatie-vereisten voor industriestandaard metagegevens
* xmp
* xmpPG - xmp voor gepagineerde tekst

### Multimediaspecifieke metagegevens {#multimedia-specific-metadata}

* xmpDM - Dynamische media
* xmpMM - Mediabeheer

## Workflows met metagegevens {#metadata-driven-workflows}

Door workflows te maken die op metagegevens zijn gebaseerd, kunt u bepaalde processen automatiseren, wat de efficiëntie ten goede komt. In een workflow met metagegevens leest het workflowbeheersysteem de workflow en wordt er dus een vooraf gedefinieerde actie uitgevoerd. U kunt bijvoorbeeld op een aantal manieren werkstromen gebruiken die zijn gebaseerd op metagegevens:

* Met de workflow kunt u controleren of een afbeelding een titel heeft. Als dit niet het geval is, wordt een bepaalde gebruiker door het systeem op de hoogte gesteld van het toevoegen van een titel.
* De workflow kan controleren of een copyrightkennisgeving op een middel distributie mogelijk maakt. Als dit het geval is, verzendt het systeem het middel naar één server. Als dit niet het geval is, verzendt het systeem het element naar een andere server.
* Een workflow kan controleren op elementen zonder vooraf gedefinieerde, verplichte metagegevens of met *ongeldige* metagegevens.
