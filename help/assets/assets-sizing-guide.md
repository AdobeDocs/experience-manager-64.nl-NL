---
title: Hulplijn voor middelengrootte
description: Beste praktijken om efficiënte metriek voor het schatten van de infrastructuur en de middelen te bepalen die voor plaatsing worden vereist [!DNL Experience Manager] Elementen.
uuid: f847c07d-2a38-427a-9c38-8cdca3a1210c
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
discoiquuid: 82c1725e-a092-42e2-a43b-72f2af3a8e04
feature: Asset Management
role: Architect,Admin
exl-id: 6115e5e8-9cf5-417c-91b3-0c0c9c278b5b
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1876'
ht-degree: 0%

---

# Hulplijn voor middelengrootte {#assets-sizing-guide}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Wanneer het rangschikken van het milieu voor een implementatie van de Middelen van Adobe Experience Manager, is het belangrijk om ervoor te zorgen dat er voldoende middelen in termen van schijf, cpu, geheugen, IO, en netwerkproductie beschikbaar zijn. Als u veel van deze bronnen wilt vergroten, moet u weten hoeveel elementen in het systeem worden geladen. Als er geen betere maateenheid beschikbaar is, kunt u de grootte van de bestaande bibliotheek delen door de leeftijd van de bibliotheek om de snelheid te vinden waarmee elementen worden gemaakt.

## Schijf {#disk}

### DataStore {#datastore}

Een algemene fout die wordt gemaakt bij het instellen van de grootte van de vereiste schijfruimte voor een middelenimplementatie, is het baseren van de berekeningen op de grootte van de Raw-afbeeldingen die in het systeem worden opgenomen. Standaard, [!DNL Experience Manager] maakt drie uitvoeringen naast de originele afbeelding voor het renderen van de [!DNL Experience Manager] UI-elementen. In vorige implementaties, zijn deze vertoningen waargenomen tweemaal de grootte van de activa veronderstellen die worden opgenomen.

De meeste gebruikers definiëren aangepaste uitvoeringen naast de uitvoeringen buiten de box. Naast de vertoningen, laat de Activa u subactiva uit gemeenschappelijke dossiertypes, zoals InDesign en Illustrator halen.

Tot slot slaan AEM versiemogelijkheden duplicaten van de middelen in de versiegeschiedenis op. U kunt de versies vormen om vaak worden gezuiverd. Veel gebruikers kiezen er echter voor om de versies in het systeem lange tijd te behouden, wat extra opslagruimte verbruikt.

Gezien deze factoren, vereist u een methodologie om een aanvaardbare nauwkeurige opslagruimte te berekenen om gebruikersactiva op te slaan.

1. Bepaal de grootte en het aantal elementen dat in het systeem wordt geladen.
1. Hiermee ontvangt u een representatieve steekproef van de elementen die in AEM moeten worden geüpload. Als u bijvoorbeeld PSD-, JPG-, AI- en PDF-bestanden in het systeem wilt laden, hebt u meerdere voorbeeldafbeeldingen van elke bestandsindeling nodig. Bovendien moeten deze monsters representatief zijn voor de verschillende bestandsgrootten en complexiteiten van afbeeldingen.
1. Definieer de uitvoeringen die moeten worden gebruikt.
1. De uitvoeringen maken in [!DNL Experience Manager] gebruiken van de toepassingen van ImageMagick of van de Creative Cloud van Adobe. Naast de vertoningen die de gebruikers specificeren, creeer uit-van-de-doos vertoningen. Voor gebruikers die Dynamic Media Classic implementeren, kunt u het binaire IC-bestand gebruiken om de PTIFF-uitvoeringen te genereren die in AEM moeten worden opgeslagen.
1. Als u subassets wilt gebruiken, genereert u deze voor de juiste bestandstypen. Zie de onlinedocumentatie over het genereren van pagina&#39;s met subelementen op basis van InDesign-bestanden of PNG/PDF-bestanden op basis van Illustrator-lagen.
1. Vergelijk de grootte van de uitvoerafbeeldingen, uitvoeringen en subelementen met de oorspronkelijke afbeeldingen. Hiermee kunt u een verwachte groeifactor genereren wanneer het systeem wordt geladen. Als u bijvoorbeeld uitvoeringen en subelementen genereert met een gecombineerde grootte van 3 GB na het verwerken van 1 GB aan elementen, is de groeifactor van de uitvoering 3.
1. Bepaal de maximumtijd gedurende welke elementversies in het systeem moeten worden onderhouden.
1. Bepaal hoe vaak bestaande elementen in het systeem worden gewijzigd. Indien [!DNL Experience Manager] wordt gebruikt als een samenwerkingscentrum in creatieve werkschema&#39;s, zijn de hoeveelheid veranderingen hoog. Als alleen voltooide elementen naar het systeem worden geüpload, is dit aantal veel lager.
1. Bepaal hoeveel elementen elke maand in het systeem worden geladen. Als u niet zeker weet, controleert u het aantal elementen dat momenteel beschikbaar is en verdeelt u het getal door de leeftijd van het oudste element om een geschatte waarde te berekenen.

Door stap 1-9 uit te voeren kunt u het volgende bepalen:

* Onbewerkte grootte van te laden elementen
* Aantal te laden elementen
* Vertoningsgroeifactor
* Aantal per maand aangebrachte wijzigingen in activa
* Aantal maanden om elementversies te onderhouden
* Aantal per maand geladen nieuwe elementen
* Jaar van groei waarin ruimte moet worden toegewezen

U kunt deze aantallen in het Netwerk het Rangschikken spreadsheet specificeren om de totale ruimte te bepalen die voor uw datastore wordt vereist. Het is ook een handig hulpmiddel om het effect te bepalen van het onderhoud van elementversies of het wijzigen van elementen in [!DNL Experience Manager] op schijfgroei.

De voorbeeldgegevens die in het gereedschap zijn ingevuld, tonen aan hoe belangrijk het is om de vermelde stappen uit te voeren. Als u de datastore alleen op basis van de te laden Raw-afbeeldingen (1 TB) wijzigt, hebt u de grootte van de opslagplaats mogelijk met een factor 15 onderschat.

[Bestand ophalen](assets/disk_sizing_tool.xlsx)

### Gedeelde datastores {#shared-datastores}

Voor grote datastores, kunt u gedeelde datastore of door een gedeelde dossierdatastore op een netwerk in bijlage aandrijving of door een S3 datastore uitvoeren. In dit geval hoeft in afzonderlijke gevallen geen kopie van de binaire bestanden te worden bewaard. Bovendien vergemakkelijkt een gedeelde datastore binair-geen replicatie en helpt de bandbreedte verminderen die wordt gebruikt om activa te herhalen om milieu&#39;s of het ontladen instanties te publiceren.

#### Gevallen gebruiken {#use-cases}

De datastore kan tussen een primaire en reserve auteursinstantie worden gedeeld om de hoeveelheid tijd te minimaliseren die het vergt om de reserve instantie met veranderingen bij te werken die in de primaire instantie worden aangebracht. Adobe raadt aan de datastore te delen tussen een instantie van de primaire auteur en instanties van de offload-auteur om de overhead bij het offloaden van de workflow te verminderen. U kunt datastore tussen de auteur ook delen en instanties publiceren om het verkeer tijdens replicatie te minimaliseren.

#### Nadelen {#drawbacks}

Door sommige valkuilen wordt het delen van een datastore niet in alle gevallen aanbevolen.

#### Eén foutpunt {#single-point-of-failure}

Met een gedeelde datastore introduceert u één foutpunt in een infrastructuur. Overweeg een scenario waarin uw systeem één auteur en twee publiceer instanties heeft, elk met hun eigen datastore. Als één van hen crasht, kunnen de andere twee nog lopen. Nochtans, als datastore wordt gedeeld, kan één enkele schijfmislukking de volledige infrastructuur onderdrukken. Zorg daarom dat u een back-up van de gedeelde datastore bijhoudt vanaf waar u de datastore snel kunt herstellen.

De voorkeur wordt gegeven aan de AWS S3-service voor gedeelde datastores, omdat hierdoor de kans op mislukking aanzienlijk afneemt in vergelijking met normale schijfarchitecturen.

#### Meer complexiteit {#increased-complexity}

Gedeelde datastores verhogen ook de ingewikkeldheid van verrichtingen, zoals huisvuilinzameling. Normaal, kan de huisvuilinzameling voor een standalone datastore met één enkele klik in werking worden gesteld. Nochtans, vereisen de gedeelde datastores de verrichtingen van de marktopening op elk lid dat datastore gebruikt, naast het runnen van de daadwerkelijke inzameling op één enkele knoop.

Voor AWS-bewerkingen kan het implementeren van één centrale locatie (via S3) in plaats van een RAID-array van EBS-volumes te maken, de complexiteit en operationele risico&#39;s op het systeem aanzienlijk compenseren.

#### Prestatieproblemen {#performance-concerns}

Een gedeelde datastore vereist dat de binaire getallen op een netwerk-opgezette aandrijving worden opgeslagen die tussen alle instanties wordt gedeeld. Omdat deze binaire getallen over een netwerk worden betreden, worden de systeemprestaties nadelig beïnvloed. U kunt het effect gedeeltelijk verlichten door een snelle netwerkverbinding aan een snelle serie van schijven te gebruiken. Dit is echter een kostbaar voorstel. In het geval van AWS-bewerkingen zijn alle schijven extern en vereisen ze netwerkconnectiviteit. Ephemeral-volumes verliezen gegevens wanneer de instantie start of stopt.

#### Latentie {#latency}

De latentie in S3 implementaties wordt geïntroduceerd door de achtergrond schrijvend draden. Bij de back-upprocedures moet rekening worden gehouden met deze latentie en eventuele ontlaadprocedures. Het S3-element mag niet aanwezig zijn in S3 wanneer een offloadtaak begint. Bovendien kunnen de indexen van Lucene onvolledig blijven wanneer het maken van een steun. Het is van toepassing op elk tijdgevoelig dossier dat aan S3 datastore wordt geschreven en van een andere instantie wordt betreden.

### Node Store/Document Store {#node-store-document-store}

Het is moeilijk om exacte cijfers voor de grootte van een NodeStore of DocumentStore te bepalen vanwege de middelen die door het volgende worden verbruikt:

* Metagegevens van element
* Elementen
* Controlelogboeken
* Gearchiveerde en actieve workflows

Omdat de binaire getallen in de datastore worden opgeslagen, neemt elk binair getal wat ruimte in. De meeste opslagruimten zijn kleiner dan 100 GB. Er kunnen echter grotere opslagruimten zijn tot 1 TB groot. Bovendien hebt u voldoende vrije ruimte op het volume nodig om de gecomprimeerde opslagplaats naast de vooraf gecomprimeerde versie te herschrijven om offline compacte compressie uit te voeren. Een goede regel-van-duim is de grootte van de schijf aan 1.5 keer de grootte die voor de bewaarplaats wordt verwacht.

Voor de opslagplaats, gebruik SSDs of schijven met een IOPS niveau groter dan 3000. Om de kans te elimineren dat IOPS prestatiesknelpunten introduceert, controleert cpu IO wachttijden niveaus op vroege tekenen van kwesties.

[Bestand ophalen](assets/aem_environment_sizingtool.xlsx)

## Netwerk {#network}

[!DNL Assets] heeft een aantal gebruiksgevallen die netwerkprestaties belangrijker maken dan op veel van onze [!DNL Experience Manager] projecten. Een klant kan een snelle server hebben, maar als de netwerkverbinding niet groot genoeg is om de lading van de gebruikers te steunen die activa van het systeem uploaden en downloaden, dan zal het nog langzaam lijken. Er is een goede methode om het knooppunt in de netwerkverbinding van een gebruiker te bepalen met [!DNL Experience Manager] om [[!DNL Experience Manager]  De overwegingen van activa voor gebruikerservaring, instantie het rangschikken, werkschemaevaluatie, en netwerktopologie](assets-network-considerations.md).

## WebDAV {#webdav}

Als u de [!DNL Experience Manager] desktop app aan de mix, worden de netwerkproblemen ernstiger als gevolg van inefficiënties in het WebDAV-protocol.

Adobe heeft de systeemprestaties getest met WebDAV op OS X om deze inefficiënties te illustreren. Er is een InDesign-bestand van 3,5 MB geopend, bewerkt en opgeslagen. De volgende opmerkingen werden gemaakt:

* Er zijn in totaal ongeveer 100 HTTP-aanvragen gegenereerd om de bewerking te voltooien
* Het bestand is vier keer geüpload via HTTP
* Het bestand is eenmaal gedownload via HTTP
* De volledige bewerking duurde 42 seconden om te voltooien
* In totaal zijn 18 MB gegevens overgedragen

Tijdens het analyseren van de gemiddelde opslagtijd voor bestanden via WebDAV werd vastgesteld dat de prestaties aanzienlijk toenemen naarmate de bandbreedte toeneemt tot het niveau van 5-10 Mbps. Daarom adviseert Adobe dat elke gebruiker die tot het systeem gelijktijdig toegang heeft minstens 10Mbps van uploadsnelheid en 5-10Mbps van bandbreedte zou moeten hebben.

Zie voor meer informatie [Problemen oplossen [!DNL Experience Manager] bureaubladtoepassing](https://helpx.adobe.com/experience-manager/kb/troubleshooting-companion-app.html).

## Beperkingen {#limitations}

Wanneer het rangschikken van een implementatie, is het belangrijk om systeembeperkingen in mening te houden. Als de voorgestelde implementatie deze beperkingen overschrijdt, maakt u gebruik van creatieve strategieën, zoals het verdelen van de elementen over meerdere implementaties van Elementen.

Bestandsgrootte is niet de enige factor die bijdraagt aan problemen met onvoldoende geheugen (OOM). Het hangt ook van afmetingen van het beeld af. U kunt OOM-problemen voorkomen door een hogere heapgrootte op te geven wanneer u AEM.

Bovendien kunt u de eigenschap voor drempelgrootte van het dialoogvenster `com.day.cq.dam.commons.handler.StandardImageHandler` in de Manager van de Configuratie aan gebruik tijdelijk tussendossier groter dan nul.

## Maximum aantal activa {#maximum-number-of-assets}

<!-- Currently, Adobe has not tested the system for loading greater than 8 million assets. There are limitations both on the number of documents that can exist in an Oak repository and the number of files that can exist in a datastore.

While the limit for the number of nodes in a repository has not been determined, assuming each asset generates roughly 30 nodes, putting the 8 million asset test at 240 million nodes from the assets alone. This does not include audit logs, archived workflows, or versions. -->

De limiet voor het aantal bestanden dat in een datastore kan bestaan, kan 2,1 miljard zijn vanwege bestandssysteembeperkingen. Het is waarschijnlijk dat de opslagplaats problemen door groot aantal knopen lang alvorens de datastore grens te bereiken ontmoet.

Gebruik de Camera Raw bibliotheek als de uitvoeringen onjuist zijn gegenereerd. In dit geval mag de langste zijde van de afbeelding echter niet groter zijn dan 65000 pixels. Bovendien mag de afbeelding niet meer dan 512 MP (512 &amp;oost) bevatten. 1024 &amp;Laatste; 1024 pixels)&quot;. *De omvang van het actief heeft geen gevolgen*.

Het is moeilijk nauwkeurig de grootte te schatten van het TIFF dossier dat uit-van-de-doos (OTB) met een specifieke hoop voor [!DNL Experience Manager] omdat extra factoren, zoals pixelgrootte, de verwerking beïnvloeden. Het is mogelijk dat [!DNL Experience Manager] kan een bestand verwerken van 255 MB OOTB, maar kan geen bestandsgrootte van 18 MB verwerken omdat het laatste bestand een ongewoon groter aantal pixels bevat dan het eerste.

## Grootte van activa {#size-of-assets}

Standaard, [!DNL Experience Manager] kunt u bestanden van maximaal 2 GB uploaden. Als u zeer grote elementen in AEM wilt uploaden, raadpleegt u [Configuratie om zeer grote elementen te uploaden](managing-video-assets.md#configuration-to-upload-video-assets-that-are-larger-than-gb).
