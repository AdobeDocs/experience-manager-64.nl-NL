---
title: Opmerkingen bij de release AEM Assets
seo-title: AEM Assets
description: Opmerkingen bij de release specifiek voor Adobe Experience Manager 6.4 Activa.
seo-description: Opmerkingen bij de release specifiek voor Adobe Experience Manager 6.4 Activa.
uuid: f5e7608d-f906-4a35-b442-899703de3587
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4
topic-tags: release-notes
content-type: reference
discoiquuid: 397b3267-1437-4263-963c-9d68ccc928ab
translation-type: tm+mt
source-git-commit: f8ba597c62379ba413309303c2ad066ab7afce1e
workflow-type: tm+mt
source-wordcount: '1689'
ht-degree: 0%

---


# Opmerkingen bij de release AEM Assets {#aem-assets-release-notes}

De belangrijkste functies, hooglichten en verbeteringen die zijn uitgevoerd in AEM 6.4 Elementen worden behandeld in deze releaseopmerkingen. Voor gedetailleerde informatie, volg de verstrekte verbindingen.

## Adobe-itemkoppeling {#adobe-asset-link}

Adobe Asset Link in Creative Cloud for Enterprise stroomlijnt de samenwerking tussen ontwerpers en marketers bij het maken van content. Het is een nieuwe inheemse capaciteit in Creative Cloud voor onderneming, die een verbinding aan AEM Assets direct van Adobe Photoshop, Adobe Illustrator, of Adobe InDesign verstrekt — zonder deze hulpmiddelen te verlaten.

Meer over het vermogen, de eerste vereisten, en hoe te om tot het toegang te hebben, zie de pagina van de Verbinding [van de Activa van](https://helpx.adobe.com/enterprise/using/adobe-asset-link.html) Adobe.

## Verbeterde slimme tags (aangedreven door Adobe Sensei) {#enhanced-smart-tags-powered-by-adobe-sensei}

AEM 6.4 introduceert de mogelijkheid van kunstmatige intelligentie, verbeterde slimme tags naast slimme tags die in AEM 6.3 zijn geïntroduceerd.

* De Slimme Dienst van de Inhoud leert de bedrijfstaxonomie van de klant en gebruikt het om digitale activa met klant relevante markeringen naast generische markeringen automatisch te etiketteren. Het verbetert de ontdekkbaarheid van activa beduidend en vermindert tijd aan markt.
* Adobe Sensei is verantwoordelijk voor de Smart Content Service. Hiermee kunt u het algoritme voor imageherkenning trainen op uw bedrijfsconomie. Deze inhouds-informatie wordt vervolgens gebruikt om relevante tags toe te passen op vergelijkbare elementen.

Als u AEM Assets Enhanced Smart Tags wilt gebruiken, installeert u het [nieuwste servicepakket van AEM 6.4](https://helpx.adobe.com/experience-manager/aem-releases-updates.html).

## Smart Translation Search (Engelstalig) (aangedreven door Adobe Sensei) {#smart-translation-search-powered-by-adobe-sensei}

AEM 6.4 introduceert Smart Translation Search mogelijkheid om meertalige zoekscenario&#39;s te ondersteunen. Klanten met wereldwijd gedistribueerde teams voor meerdere landinstellingen hebben nu toegang tot het zoeken in verschillende talen zonder dat ze dure en tijdrovende vertaalworkflows moeten doorlopen.

* Zoekopdracht wordt zonder handmatige tussenkomst vertaald.
* Slimme tags worden gegenereerd in het Engels en worden automatisch vertaald naar andere talen.
* Meertalig zoeken is gebaseerd op de opensource-bibliotheek Apache Joshua die meer dan 50 talen ondersteunt.

## Gebruikerservaring {#user-experience}

AEM 6.4 biedt een aanzienlijke verbetering van de gebruikerservaring op het gebied van bladeren, zoeken, elementen van meerdere pagina&#39;s en beheertools. Details hieronder:

Verbeteringen voor bladeren

* Nieuwe contentstructuurrails om snel door de hiërarchie van elementen te navigeren. In combinatie met de lijstmening, herstelt dit het Klassieke UI interactiemodel om activa hiërarchieën te doorbladeren.
* Nieuwe sneltoetsen, zoals m, om elementen te verplaatsen, p om de eigenschappenpagina te openen, Ctrl + C om de bewerking te kopiëren en nog veel meer.
* Verbeterde schuifervaring, luie laadervaring in kaart- en lijstweergave voor het bladeren door een groot aantal elementen.
* Verbeterde kaartweergave met ondersteuning voor kaarten van verschillende formaten op basis van de weergave-instelling.
* Betere ervaring met middelendetails met de mogelijkheid om naar &quot;vorig&quot; of &quot;volgend&quot; element te navigeren, samen met het aantal elementen, het huidige element.

Verbeteringen voor zoeken

* De nieuwe knoop van het Onderzoek terug met capaciteit om aan een onderzoekspunt te navigeren en aan de zelfde positie in onderzoeksresultaten terug te komen zonder de onderzoeksvraag opnieuw in werking te stellen.
* De nieuwe resultaten van het Onderzoek tellen om aantal onderzoeksresultaten te tonen.
* Het verbeterde filter van het Onderzoek van het Type van Dossier met capaciteit om onderzoeksresultaten te filtreren die op fijnkorrelige mime types zoals JPG, PNG, en PSD worden gebaseerd, in vergelijking met vorige beeld, document, de opties van multimedia.
* Verbeterde zoekfilters met nauwkeurige tijdstempels in plaats van de vorige tijdschuifregelaar.

Verbeteringen voor elementen van meerdere pagina&#39;s

* Verbeterde bladerervaring voor elementen van meerdere pagina&#39;s met een kleiner aantal klikken.
* Verbeterde ondersteuning voor opmerkingen en annotaties waarbij alle opmerkingen zijn gesorteerd op middelenniveau in plaats van op paginaniveau.

Verbeteringen voor beheerprogramma&#39;s

* Verbeterde eigenschappenkiezer in de beheerfuncties voor metagegevens, zoeken en rapporten met Type voor en bladermogelijkheden om de beheerervaring te vereenvoudigen.

Catalogi

* Verbeterde gebruikerservaring, uitlijning met de gebruikersinterface van Sjablonen. Zie [Catalog Producer](../sites-administering/catalog-producer.md)voor meer informatie.

## Metadata {#metadata}

AEM 6.4 omvat meerdere geavanceerde mogelijkheden voor metagegevensbeheer om metagegevens op schaal te beheren en de integriteit van metagegevens via regels en validaties af te dwingen. Hier volgen de belangrijkste mogelijkheden:

* Nieuwe bulkmetagegevens kunnen worden geëxporteerd naar (alle, selectieve) metagegevens voor een groot aantal elementen in CSV-indeling voor bewerking, delen en integratie van derden.
* Nieuwe bulkmetagegevens voor het importeren van CSV-bestanden om nieuwe metagegevens toe te voegen en bestaande metagegevens voor meerdere elementen tegelijk bij te werken. Deze bewerking is asynchroon en belemmert de systeemprestaties niet. Zodra dit is voltooid, wordt de gebruiker via AEM meldingssysteem op de hoogte gesteld.
* Nieuwe trapsgewijze en contextafhankelijke metagegevens met het gereedschap Metagegevensschema. Het is nu mogelijk om ketens van afhankelijkheden en waardetoewijzingen tussen velden te definiëren. U kunt ook de context definiëren waarin formuliervelden voor metagegevens worden weergegeven/verborgen. Op deze manier kunt u op elk moment alleen relevante velden weergeven, afhankelijk van de waarden in andere velden.

## Rapporten {#reports}

AEM 6.4 biedt aanzienlijke verbeteringen op het gebied van middelenrapportage:

* De nieuwe onderneming-vlakke, scalable (voor grote bewaarplaatsen) meldt kader die het Verschuiven banen voor asynchrone verwerkingsrapportverzoeken toepast. U kunt rapport op een specifieke datum en een tijd plannen. U kunt douanekolommen aan een rapport ook toevoegen.
* Nieuwe OOTB-rapporten die het vaakst door klanten worden gevraagd, zoals schijfgebruik, bestanden, gedeelde koppelingen, publiceren naar Brand-portal en training voor slimme tags.
* De nieuwe verwezenlijking en beheer UI van Rapporten met fijne korrelige opties, capaciteit om tot gearchiveerde rapporten toegang te hebben, zie rapportloopstatus (succes, ontbroken, een rij gevormd, etc.).

## Brand Portal {#brand-portal}

* **6.3 Platform-upgrade**: Brand Portal is bijgewerkt van AEM 6.0 naar AEM 6.3 met nieuwe functies en prestatieverbeteringen.
* **Parallelle publicatie**: Er kunnen maximaal replicaties plaatsvinden tussen AEM Assets en Brand Portal (voorheen 1), wat de publicatieprestaties aanzienlijk verbetert
* **Schema en zoekfacet publiceren**: Mogelijkheid om metagegevensschema&#39;s en aangepaste zoekfacetten naar Brand Portal te publiceren, waardoor dubbel werk wordt voorkomen.
* **Bulklabels publiceren**: Mogelijkheid om taxonomie (samen met hiërarchie) te publiceren naar Brand Portal, waardoor dubbel werk wordt voorkomen.
* **Zelf aanmelden of toegang** aanvragen: Workflow voor niet-geregistreerde gebruikers naar Brand Portal.
* **Onderhoudsmelding** in de app (op het scherm): Meldingen worden ruim van tevoren weergegeven om verstoring in de bedrijfsvoering te voorkomen.
* **Verbeteringen** rapporteren: Er zijn drie OOTB-rapporten beschikbaar: downloads, publiceren en delen via koppelingen.
* **Beperkingen** op basis van DRM: Nadat een gelicentieerd element is verlopen, kan het niet meer worden gedownload van Brand Portal.

## Bureaubladapp AEM {#aem-desktop-app}

AEM bureaubladtoepassing wordt bijgewerkt naar versie 1.8, die compatibel is met AEM 6.4. De volledige lijst met wijzigingen voor AEM desktop-app vindt u in een speciaal document met opmerkingen [over de release van de](https://docs.adobe.com/content/help/en/experience-manager-desktop-app/using/release-notes.html) AEM desktop-app.\
Hier volgt een lijst met AEM belangrijke kenmerken van de bureaubladtoepassing sinds AEM 6.3 is uitgebracht:

* Mogelijkheid om hiërarchische mappen op de achtergrond te uploaden.
* UI om het uploaden van middelen op de achtergrond te controleren.
* Verbeteringen in de cache, waaronder een interface voor het beheren van cacheparameters.
* Bredere ondersteuning voor AEM verificatieconfiguraties (SAML/SSO) en netwerkproxy.
* Ondersteunbaarheid: eenvoudige toegang tot logbestanden vanuit de gebruikersinterface.
* Verbeterde stabiliteit en oplossingen voor problemen met klanten.

De volgende documentatie is beschikbaar voor een eenvoudigere toegang tot de documentatie en de aanbevolen procedures:

* [Gebruikershandleiding](https://docs.adobe.com/content/help/en/experience-manager-desktop-app/using/using.html)voor eindgebruikers die met de toepassing werken.
* [Installatiehandleiding](https://docs.adobe.com/content/help/en/experience-manager-desktop-app/using/install-upgrade.html)voor beheerders die AEM en AEM bureaubladtoepassing instellen om samen te werken

## Gelaagde opslag {#tiered-storage}

AEM 6.4 bevat een reeks functies die verschillende gelaagde opslagvoorkeuren ondersteunen en levenscyclusregels implementeren. De opslagopties ondersteunen (maar zijn niet beperkt) ook openbare wolken - AWS of Azure.

* De mogelijkheid voor gebruikers om opslagklasse te selecteren en later naar eigen inzicht te wijzigen en regels te definiëren voor de opslag van elementen van de ene klasse naar de andere of de levenscyclus van hun elementen te beheren.
* De mogelijkheid voor gebruikers om hun opslagkosten te verlagen door een ander AWS of Azure te selecteren.

Voor een overzicht van ondersteunde platforms raadpleegt u de documentatie over [technische vereisten](../sites-deploying/technical-requirements.md).

## Gesloten gebruikersgroep {#closed-user-group}

* In AEM 6.4 biedt een gesloten gebruikersgroep of CUG een manier om maptoegang te beperken bij een publicatie-instantie. Het is een aanraakinterface-optie om hoofden toe te voegen via de pagina met eigenschappen van mappen op mapniveau en worden toegepast op alle mappen en submappen/middelen in de map.
* Als in de publicatiemodus een CUG is geconfigureerd en verificatie is ingeschakeld in een map, worden gebruikers omgeleid naar een aanmeldingspagina wanneer zij toegang proberen te krijgen tot de map. Daarom hebben geautoriseerde gebruikers pas toegang tot de map en de bijbehorende middelen nadat ze zich met succes hebben aangemeld. Daarom beperkt CUG leestoegang tot een bepaalde boom in de inhoudsbewaarplaats voor iedereen behalve geselecteerde hoofden.

## Invoegtoepassing Dynamic Media {#dynamic-media-add-on}

Dynamic Media in 6.4 ondersteunen een nieuwe modus - waarbij master element wordt geüpload en beheerd met de webinterface van AEM Assets, en dynamische uitvoeringen en andere dynamische mediafuncties op de achtergrond worden afgehandeld door de service voor cloudlevering van Dynamic Media.

In deze modus (die eerst werd geïntroduceerd met de release van [AEM 6.3-functiepakketten 14410 en 18912](https://helpx.adobe.com/experience-manager/6-3/release-notes/dynamic-media-featurepack-14410.html)) profiteren gebruikers van end-to-end functies voor middelenbeheer en dynamische media met de moderne interface van het web van AEM Assets en maken ze nog steeds gebruik van de leveringsservices die achterwaarts compatibel zijn met Dynamic Media Classic (Scene7), inclusief ongewijzigde bezorgings-URL&#39;s.

Daarnaast introduceert AEM 6.4 nieuwe functies die door Adobe Sensei worden aangestuurd, verbeteringen voor opkomende media zoals VR en 3D, Dynamic Media viewers en ondersteuning voor Experience Fragments in Interactive Images en Carousel Banners.

### Smart Crop (aangedreven door Adobe Sensei) {#smart-crop-powered-by-adobe-sensei}

* Met Slim uitsnijden kunt u afbeeldingen automatisch op niet-destructieve wijze uitsnijden, zodat het interessepunt voor een responsief ontwerp behouden blijft. U kunt bijgesneden suggesties vooraf bekijken en ze indien nodig handmatig aanpassen.
* Met deze functie kunt u ook automatische stalen genereren voor productafbeeldingen. Met Automatisch stalen genereren kunt u automatisch kleurstalen, patroonstalen of beide toevoegen aan productafbeeldingen.

Raadpleeg de documentatie bij [Afbeeldingsprofielen](../assets/image-profiles.md) voor meer informatie.

Zie ook Dynamic Media-elementen [toevoegen aan de documentatie bij Pagina](../assets/adding-dynamic-media-assets-to-pages.md) &#39;s voor meer informatie over het gebruik van Slim uitsnijden met de component Dynamic Media.

### Smart Imaging {#smart-imaging}

* Slimme beeldverwerking maakt gebruik van de unieke weergavekenmerken van elke gebruiker, zodat deze automatisch afbeeldingen levert die zijn geoptimaliseerd voor zijn of haar ervaring, wat resulteert in betere prestaties en betrokkenheid.
* Afbeeldingen worden automatisch geconverteerd naar verschillende indelingen op basis van de mogelijkheden van de browser.
* De instellingen voor de afbeeldingskwaliteit worden bepaald in de browser en toegepast. Deze intelligentie zorgt ervoor dat de prestaties bij het laden van afbeeldingen acceptabel blijven voor een beperkte bandbreedte en een lage verbindingssnelheid.

Raadpleeg de documentatie bij [Smart Imaging](../assets/imaging-faq.md) voor meer informatie.

### Verbeteringen voor media en viewer {#emerging-media-amp-viewer-enhancements}

* Nieuwe viewers worden ondersteund en bieden een betere en indrukwekkende ervaring voor de gebruiker.
* De Panoramische Viewer helpt de gebruiker te betrekken en biedt de mogelijkheid om ruimteschalen, eigenschappen, locaties en landschappen beter te ervaren. Raadpleeg de documentatie bij [Panorama](../assets/panoramic-images.md) -afbeeldingen voor meer informatie.

* VR Viewer biedt een indrukwekkende ervaring voor eigenschappen, locaties en landschappen.
* Vertical Image Viewer geoptimaliseerd voor productafbeeldingen.
* Verbeterde toegankelijkheid van toetsenborden.

### 3D en integratie met Dimension CC {#d-and-integration-with-dimension-cc}

Er is integratie met [Adobe Dimension CC](https://www.adobe.com/products/dimension.html) voor een naadloze 3D-workflow geïntroduceerd. Zie [Werken met documentatie over 3D-elementen](../assets/assets-3d.md) voor meer informatie.
