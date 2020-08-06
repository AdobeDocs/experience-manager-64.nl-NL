---
title: Uw upgrade plannen
seo-title: Uw upgrade plannen
description: Dit artikel helpt duidelijke doelstellingen, fasen en te leveren te vestigen wanneer het plannen van de AEM verbetering.
seo-description: Dit artikel helpt duidelijke doelstellingen, fasen en te leveren te vestigen wanneer het plannen van de AEM verbetering.
uuid: e912e097-a042-46e5-8084-125a6d05ac8b
contentOwner: sarchiz
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: upgrading
discoiquuid: 901108a1-c0cb-4680-bc71-6266bcde2775
translation-type: tm+mt
source-git-commit: cdec5b3c57ce1c80c0ed6b5cb7650b52cf9bc340
workflow-type: tm+mt
source-wordcount: '2451'
ht-degree: 0%

---


# Uw upgrade plannen{#planning-your-upgrade}

## Overzicht van AEM project {#aem-project-overview}

AEM wordt vaak gebruikt in implementaties met een hoog effect die miljoenen gebruikers ten goede kunnen komen. In de meeste gevallen, zijn er douanetoepassingen die op de instanties worden opgesteld, die aan de ingewikkeldheid toevoegen. Om het even welke inspanning om zulk een plaatsing te bevorderen moet methodisch worden behandeld.

Deze gids helpt met het vestigen van duidelijke doelstellingen, fasen en te leveren punten wanneer het plannen van uw verbetering. Het is gericht op de algemene uitvoering van het project en de richtsnoeren. Hoewel het een overzicht van de daadwerkelijke verbeteringsstappen verstrekt, verwijst het naar beschikbare technische middelen waar geschikt. Het moet worden gebruikt in combinatie met de in het document vermelde beschikbare technische middelen.

Het proces van de Verbetering van de AEM vereist zorgvuldig behandelde planning, analyse en uitvoeringsfasen met zeer belangrijke te leveren producten die voor elke fase worden bepaald.

Merk op dat het mogelijk is rechtstreeks van AEM versies 6.0 en tot 6.4 te bevorderen. Klanten met 5.6.x en lager moeten eerst een upgrade uitvoeren naar versie 6.0 of hoger, waarbij 6.0(SP3) wordt aanbevolen. Bovendien wordt de nieuwe indeling OAK-segmentteer nu gebruikt voor de Segment Node Store sinds 6.3 en is de migratie van de opslagplaats naar deze nieuwe indeling zelfs verplicht voor 6.0, 6.1 en 6.2.

>[!CAUTION]
>
>Als u van AEM 6.2 aan 6.3 bevordert, zou u of van versies (**6.2-SP1-GFP1 - -6.2SP1-GFP12.1**) of **6.2SP1-GFP15** moeten bevorderen. Anders, als u van **6.2SP1-GVB13/6.2SP1GVB14** aan AEM 6.3 bevordert, moet u ook aan minstens versie **6.3.2.2** bevorderen. Anders zou AEM Sites na de upgrade mislukken.

## Upgrade van bereik en vereisten {#upgrade-scope-requirements}

Hieronder vindt u een lijst met gebieden die van invloed zijn op een standaard AEM upgradeproject:

<table> 
 <tbody>
  <tr>
   <td><strong>Component</strong></td> 
   <td><strong>Gevolgen</strong></td> 
   <td><strong>Beschrijving</strong></td> 
  </tr>
  <tr>
   <td>Besturingssysteem</td> 
   <td>Onduidelijke, maar subtiele effecten</td> 
   <td>Op het moment van de AEM upgrade kan het tijd zijn om ook het besturingssysteem te upgraden en dit kan enige invloed hebben.</td> 
  </tr>
  <tr>
   <td>Java Runtime</td> 
   <td>Matige impact</td> 
   <td>AEM 6.3 vereist JRE 1.7.x (64 bits) of later. JRE 1.8 is de enige versie die momenteel door Oracle wordt ondersteund.</td> 
  </tr>
  <tr>
   <td>Hardware</td> 
   <td>Matige impact</td> 
   <td>Voor online revisie-opschoning is vrije<br /> schijfruimte vereist die gelijk is aan 25% van de grootte van de opslagplaats en 15% vrije heapruimte<br /> om te kunnen worden voltooid. Mogelijk moet u een upgrade van uw hardware uitvoeren om ervoor te zorgen dat<br /> voldoende bronnen beschikbaar zijn voor het volledig<br /> uitvoeren van Online revisie-opschoning. Als u een upgrade uitvoert van een versie die ouder is dan AEM 6, zijn er mogelijk aanvullende opslagvereisten<br /> .</td> 
  </tr>
  <tr>
   <td>Inhoudsopslagplaats (CRX of eikel)</td> 
   <td>Hoge impact</td> 
   <td>Vanaf versie 6.1 biedt AEM geen ondersteuning voor CRX2, dus is een migratie naar<br /> Eak (CRX3) vereist als een upgrade van een oudere versie wordt uitgevoerd. AEM 6.3 heeft<br /> een nieuwe Opslag van de Knoop van het Segment uitgevoerd die ook een migratie vereist. Hiervoor wordt het<br /> gereedschap crx2oak gebruikt.</td> 
  </tr>
  <tr>
   <td>Componenten/inhoud AEM</td> 
   <td>Matige impact</td> 
   <td><code>/libs</code> en <code>/apps</code> worden gemakkelijk behandeld door de verbetering, maar <code>/etc</code> vereist gewoonlijk één of andere handhertoepassing van aanpassingen.</td> 
  </tr>
  <tr>
   <td>AEM</td> 
   <td>Lage impact</td> 
   <td>De meeste AEM kerndiensten worden getest voor verbetering. Dit is een gebied met een lage impact.</td> 
  </tr>
  <tr>
   <td>Aangepaste toepassingsservices</td> 
   <td>Laag tot hoog effect</td> 
   <td>Afhankelijk van de toepassing en de aanpassing, kunnen er gebiedsdelen op JVM, werkend systeemversies en sommige indexerende verwante<br /><br /> veranderingen zijn, aangezien de indexen niet automatisch in Eak worden geproduceerd.</td> 
  </tr>
  <tr>
   <td>Aangepaste toepassingsinhoud</td> 
   <td>Laag tot hoog effect</td> 
   <td>Inhoud die niet via de upgrade wordt afgehandeld, kan vóór de upgrade worden opgeslagen<br /> en vervolgens weer in de opslagplaats worden geplaatst.<br /> De meeste inhoud kan worden verwerkt met het migratiehulpprogramma.</td> 
  </tr>
 </tbody>
</table>

Het is belangrijk om ervoor te zorgen dat u een ondersteund besturingssysteem gebruikt, Java-runtime, httpd en Dispatcher-versie. Zie de pagina [Technische vereisten van](/help/sites-deploying/technical-requirements.md)AEM 6.4 voor meer informatie. De bevordering van deze componenten zal rekenschap moeten geven in uw projectplan en zou moeten plaatsvinden alvorens AEM te bevorderen.

## Projectfasen {#project-phases}

Veel werk gaat in planning en het uitvoeren van een AEM verbetering. Om de verschillende inspanningen die in dit proces worden geleverd te verduidelijken, hebben we de plannings- en uitvoeringsoefeningen in afzonderlijke fasen opgesplitst. In de onderstaande secties resulteert elke fase in een leverbaar dat vaak wordt gebruikt door een toekomstige fase van het project.

### Planning voor training van auteurs {#planning-for-author-training}

Met om het even welke nieuwe versie, zijn er potentiële veranderingen in UI en gebruikerswerkschema&#39;s die kunnen worden geïntroduceerd. Daarnaast introduceren nieuwe releases nieuwe functies die de onderneming kunnen helpen bij het maken van een hefboomeffect. We raden u aan de geïntroduceerde functionele wijzigingen te evalueren en een plan te organiseren om uw gebruikers te trainen op een effectieve manier gebruik te maken van deze wijzigingen.

![screen_shot_2018-04-04at121206](assets/screen_shot_2018-04-04at121206.png)

De nieuwe functies in AEM 6.4 vindt u in [het AEM gedeelte van adobe.com](/help/release-notes/release-notes.md). Zorg ervoor om op om het even welke veranderingen in UIs of producteigenschappen nota te nemen die algemeen in uw organisatie worden gebruikt. Wanneer u de nieuwe functies doorloopt, moet u ook rekening houden met alle functies die van belang kunnen zijn voor uw organisatie. Na het bekijken van wat in AEM 6.4 is veranderd, ontwikkelt een opleidingsplan voor uw auteurs. Dit kan het gebruik van vrij beschikbare bronnen omvatten, zoals video&#39;s met Help-functies of formele training die via [Adobe Digital Learning Services](https://www.adobe.com/training.html)wordt aangeboden.

### Een testplan maken {#creating-a-test-plan}

De implementatie van AEM door elke klant is uniek en is aangepast om aan hun bedrijfsvereisten te voldoen. Daarom is het belangrijk om alle aanpassingen te bepalen die in het systeem zijn aangebracht zodat deze in een testplan kunnen worden opgenomen. Dit testplan zal het proces van QA aandrijven dat wij op de promotieinstantie uitvoeren.

![testplan](assets/test-plan.png)

De exacte productieomgeving moet worden gedupliceerd en na de upgrade moeten er tests op worden uitgevoerd om te controleren of alle toepassingen en aangepaste code nog steeds naar wens worden uitgevoerd. U moet al uw aanpassingen terugbrengen en prestaties, lading en veiligheidstests uitvoeren. Wanneer het organiseren van uw testplan, zorg ervoor om alle aanpassingen te behandelen die aan het systeem naast uit de doos UIs en werkschema&#39;s zijn gemaakt die in uw dagelijkse verrichtingen worden gebruikt. Deze kunnen de diensten en de diensten van douaneOSGI, integraties aan de Adobe Marketing Cloud, integraties met derde partijen door AEM schakelaars, de integratie van de douanederde, douanecomponenten en malplaatjes, de overlays van de douane UI in AEM, en douanewerkschema&#39;s omvatten. Voor klanten die van een versie voorafgaand aan AEM 6 migreren, zouden om het even welke douanevragen moeten worden geanalyseerd aangezien deze kunnen moeten worden geïndexeerd. Voor klanten die reeds op een versie van AEM 6.x zijn, zouden deze vragen nog moeten worden getest om ervoor te zorgen dat hun indexen effectief na bevordering blijven werken.

### Vaststellen welke wijzigingen in architectuur en infrastructuur nodig zijn {#determining-architectural-and-infrastructure-changes-needed}

Wanneer u een upgrade uitvoert, is het mogelijk dat u ook andere onderdelen in uw technische stapel moet bijwerken, zoals het besturingssysteem of JVM. Bovendien is het mogelijk dat als gevolg van wijzigingen in de samenstelling van de opslagplaats extra hardware nodig kan zijn. Dit komt gewoonlijk slechts voor klanten die van pre 6.x instanties migreren maar is belangrijk om te overwegen. Tot slot kunnen er wijzigingen nodig zijn in uw operationele praktijken met inbegrip van controle, onderhoud, en steun en rampenterugwinningsprocessen.

![screen_shot_2018-04-04at120223](assets/screen_shot_2018-04-04at120223.png)

Controleer de technische vereisten voor AEM 6.4 en zorg ervoor dat uw huidige hardware en software voldoende zijn. Raadpleeg de volgende documenten voor mogelijke wijzigingen in uw operationele processen:

**Controle en onderhoud:**

[Operations-dashboard](/help/sites-administering/operations-dashboard.md)

[Aanbevolen werkwijzen voor middelenbewaking](/help/assets/assets-monitoring-best-practices.md)

[Serverbronnen controleren met de JMX-console](/help/sites-administering/jmx-console.md)

[Revisie opschonen](/help/sites-deploying/revision-cleanup.md)

**Back-up/herstel en noodherstel:**

[Back-up en herstel](/help/sites-administering/backup-and-restore.md)

[Prestaties en schaalbaarheid](/help/sites-deploying/performance.md)

[Hoe te om AEM met TarMK Koude Reserve in werking te stellen](/help/sites-deploying/tarmk-cold-standby.md)

#### Overwegingen bij de herstructurering van inhoud {#content-restructuring-considerations}

AEM 6.4 heeft wijzigingen aangebracht in de structuur van de opslagplaats die zullen helpen om upgrades naadloos te maken. De veranderingen impliceren het bewegen van inhoud uit de /etc omslag naar omslagen met inbegrip van /libs, /apps, en /content, die op worden gebaseerd of Adobe of een klant de inhoud bezit, zo het beperken van de kansen om inhoud tijdens versies te beschrijven. De reorganisatie van de opslagplaats is zodanig uitgevoerd dat er geen wijzigingen in de code nodig zijn op het moment van de upgrade van 6.4, hoewel het raadzaam is de details bij de herstructurering van de [opslagplaats in AEM 6.4](/help/sites-deploying/repository-restructuring.md) te herzien terwijl een upgrade wordt gepland.

### Complexiteit van upgrade beoordelen {#assessing-upgrade-complexity}

Gezien de grote verscheidenheid in de hoeveelheid en de aard van aanpassingen die onze klanten op hun AEM milieu&#39;s toepassen, is het belangrijk om wat tijd vooruit door te brengen om het algemene niveau van inspanning te bepalen dat in uw verbetering zou moeten worden verwacht.

Er zijn twee benaderingen u kunt nemen om de ingewikkeldheid van de verbetering te beoordelen, kan een inleidende fase enkel de onlangs geïntroduceerde Detector van het Patroon gebruiken die beschikbaar is om op uw AEM 6.1, 6.2 en 6.3 instanties te lopen. De patroondetector is de eenvoudigste manier om de algemene complexiteit van de upgrade te beoordelen die met behulp van gerapporteerde patronen kan worden verwacht. Het patroondetectorrapport bevat patronen voor het identificeren van niet-beschikbare API&#39;s die worden gebruikt door de aangepaste codebase (dit is gebeurd met compatibiliteitscontroles vóór de upgrade in 6.3).

Na de eerste beoordeling zou een uitgebreidere volgende stap kunnen bestaan uit het uitvoeren van een upgrade op een testinstantie en het uitvoeren van een aantal basistests voor rook. Adobe biedt ook enkele . Bovendien, zou de lijst van [Afgekeurde en Verwijderde Eigenschappen](/help/release-notes/deprecated-removed-features.md) niet alleen voor de versie moeten worden herzien die u, maar ook voor om het even welke versies tussen uw bron en doelversies bevordert. Als u bijvoorbeeld een upgrade uitvoert van AEM 6.2 naar 6.4, is het belangrijk om naast de functies voor AEM 6.4 ook de vervangen en verwijderde AEM 6.3 te bekijken.

![screen_shot_2018-04-04at120912](assets/screen_shot_2018-04-04at120912.png)

De Patroondetector die in 6.4 is geïntroduceerd, geeft u een vrij nauwkeurige schatting van wat u in de meeste gevallen tijdens een upgrade wilt verwachten. Nochtans, voor complexere aanpassingen en plaatsingen waar u onverenigbare veranderingen hebt kunt u een ontwikkelingsinstantie aan AEM 6.4 volgens de instructies in het [Uitvoeren van een Verbetering](/help/sites-deploying/in-place-upgrade.md)op zijn plaats bevorderen. Na voltooiing, voer wat hoge rooktests op dit milieu uit. Het doel van deze exercitie is niet om de inventarisatie van de testgevallen volledig te voltooien en een formele inventarisatie van de defecten op te stellen, maar om ons een ruwe schatting te geven van de hoeveelheid werk die nodig zal zijn om de code te upgraden voor compatibiliteit met punt 6.4. Wanneer gecombineerd met de Opsporing [van het](/help/sites-deploying/pattern-detector.md) Patroon en de architecturale veranderingen die in de vorige sectie werden bepaald, kan een ruwe schatting aan het team van het projectbeheer voor de planning van de verbetering worden verstrekt.

### Upgraden en rollback-runbook samenstellen {#building-the-upgrade-and-rollback-runbook}

Terwijl Adobe het proces voor de bevordering van een AEM instantie heeft gedocumenteerd, zullen de het netwerklay-out van elke klant, plaatsingsarchitectuur en aanpassingen verfijnen en het maken van deze benadering vereisen. Daarom moedigen wij u aan om alle documentatie te herzien die wij hebben verstrekt en het te gebruiken om een projectspecifieke runbook te informeren die de specifieke verbetering en terugdraaiprocedures beschrijft die u in uw milieu zult volgen. Als u een upgrade uitvoert van CRX2, dient u te evalueren hoe lang de migratie van inhoud duurt wanneer u van CRX2 naar eiken gaat. Voor grote gegevensbanken kan het aanzienlijk zijn.

![runbook-diagram](assets/runbook-diagram.png)

Wij hebben upgrade- en terugdraaiprocedures in de [upgradeprocedure](/help/sites-deploying/upgrade-procedure.md) en stapsgewijze instructies gegeven voor het toepassen van de upgrade bij het uitvoeren van een [In-Place-upgrade](/help/sites-deploying/in-place-upgrade.md). Deze instructies zouden met uw systeemarchitectuur, aanpassingen, en downtime tolerantie moeten worden herzien en in overweging genomen om de aangewezen schakelaar-over en rollback procedures te bepalen die u tijdens de verbetering zult uitvoeren. Wijzigingen in architectuur of serverformaten moeten worden opgenomen wanneer u uw aangepaste runbook gaat maken. Het is belangrijk om op te merken dat dit als een eerste ontwerp moet worden behandeld. Aangezien uw team hun QA en ontwikkelingscycli voltooit en de verbetering aan het opvoeren milieu opstelt, is het waarschijnlijk dat de behoefte aan sommige extra stappen kan worden vereist. In het ideale geval moet dit document voldoende informatie bevatten, zodat de upgrade volledig kan worden uitgevoerd op basis van de informatie die erin is opgenomen als het document aan een medewerker van uw bedrijf is overhandigd.

### Een projectplan ontwikkelen {#developing-a-project-plan}

Wij kunnen de output van de vorige oefeningen gebruiken om een projectplan te bouwen dat de verwachte termijnen voor onze test of ontwikkelingsinspanningen, opleiding, en daadwerkelijke verbeteringsuitvoering behandelt.

![ontwikkelingsplan](assets/develop-project-plan.png)

Een alomvattend projectplan moet het volgende omvatten:

* Afronding van ontwikkelings- en testplannen

* Ontwikkeling en QA-omgevingen verbeteren

* De aangepaste codebasis voor AEM 6.4 bijwerken

* Een test en reparatiecyclus van kwaliteitscontrole

* De testomgeving upgraden

* Integratie, prestaties en belasting testen

* Milieu-certificering

* Live gaan

### Ontwikkeling en kwaliteitscontrole {#performing-development-and-qa}

Wij hebben procedures verstrekt voor de [Verbetering van Code en Aanpassingen](/help/sites-deploying/upgrading-code-and-customizations.md) om met AEM 6.4 compatibel te zijn. Aangezien dit iteratieve proces wordt uitgevoerd, zouden veranderingen in runbook moeten worden aangebracht zoals nodig. Zie ook [Achterwaartse Verenigbaarheid in AEM 6.4](/help/sites-deploying/backward-compatibility.md) op informatie over hoe uw aanpassingen achterwaarts compatibel in de meeste gevallen kunnen blijven zonder ontwikkeling onmiddellijk na verbetering te vereisen.

![screen_shot_2018-04-04at154829](assets/screen_shot_2018-04-04at154829.png)

Het ontwikkelings- en testproces is doorgaans een herhalend proces. Door aanpassingen kunnen wijzigingen die tijdens de upgrade zijn aangebracht, ertoe leiden dat een volledige sectie van het product onbruikbaar wordt. Als ontwikkelaars de hoofdoorzaak van het probleem hebben aangepakt en het testteam toegang heeft om deze functies te testen, kunnen er mogelijk extra problemen worden ontdekt. Aangezien de kwesties worden ontdekt die aanpassingen aan het verbeteringsproces vereisen, zorg ervoor om hen aan uw runtime van de douaneverbetering toe te voegen. Na verscheidene herhalingen van het testen en het bevestigen, zou de codebasis volledig moeten worden bevestigd en voor plaatsing aan het opvoeren milieu klaar zijn.

### Eindtest {#final-testing}

Wij adviseren een definitieve ronde van het testen nadat codebase door het team van QA van uw organisatie is verklaard. Deze testronde omvat het valideren van uw runbook in een testomgeving, gevolgd door gebruikersacceptatie, prestaties en beveiligingstests.

![screen_shot_2018-04-04at120435](assets/screen_shot_2018-04-04at120435.png)

Deze stap is essentieel aangezien het de enige tijd is dat u de stappen in runbook tegen een productie-als milieu kunt bevestigen. Zodra het milieu is bevorderd, is het belangrijk om eindgebruikers wat tijd toe te staan om binnen te registreren en door de activiteiten te gaan zij wanneer het gebruiken van het systeem in hun dagelijkse activiteiten doen. Het is niet ongebruikelijk dat gebruikers een deel van het systeem leveraging dat niet eerder in overweging werd genomen. Het vinden en corrigeren van problemen in deze gebieden vóór go-live kan kostbare productieonderbrekingen helpen voorkomen. Aangezien een nieuwe versie van AEM significante veranderingen in het onderliggende platform bevat, is het ook belangrijk om prestaties, lading en veiligheidstests op het systeem uit te voeren alsof wij het voor het eerst lanceerden.

### De upgrade uitvoeren {#performing-the-upgrade}

Zodra de definitieve aftekening van alle belanghebbenden is ontvangen, is het tijd om de vastgestelde runboekprocedures uit te voeren. Wij hebben stappen voor verbetering en terugschroeven van prijzen in de Procedure [van de](/help/sites-deploying/upgrade-procedure.md) Verbetering en installatiestappen in het Uitvoeren van een [Verbetering](/help/sites-deploying/in-place-upgrade.md) op zijn plaats als verwijzingspunt verstrekt.

![uitvoeren-upgrade](assets/perform-upgrade.png)

Wij hebben enkele stappen in de verbeteringsinstructies voor omgevingsbevestiging verstrekt. Deze omvatten basiscontroles zoals het aftasten van de verbeteringslogboeken en het verifiëren dat alle bundels OSGi behoorlijk zijn begonnen, maar wij adviseren ook het bevestigen met uw eigen testgevallen die op uw bedrijfsprocessen worden gebaseerd. Wij adviseren ook het controleren van het programma van AEM Online Opruiming van de Revisie en verwante routines om ervoor te zorgen dat zij tijdens een rustige tijd voor uw bedrijf zullen voorkomen. Deze routines zijn essentieel voor de prestaties op lange termijn van AEM.
