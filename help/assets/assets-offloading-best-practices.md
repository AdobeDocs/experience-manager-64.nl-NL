---
title: Aanbevolen werkwijzen voor het verschuiven van elementen
description: Aanbevolen gebruiksscenario's en aanbevolen procedures voor het offloaden van asset-opname- en replicatieworkflows in AEM Assets.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 77c62a8f2ca50f8aaff556a6848fabaee71017ce
workflow-type: tm+mt
source-wordcount: '1818'
ht-degree: 0%

---


# Aanbevolen werkwijzen voor het verschuiven van elementen {#assets-offloading-best-practices}

>[!WARNING]
>
>Deze functie is verouderd vanaf AEM 6.4 en wordt verwijderd uit AEM 6.5. Plan dienovereenkomstig.

Het verwerken van grote bestanden en het uitvoeren van workflows in Adobe Experience Manager (AEM)-middelen kan aanzienlijke CPU-, geheugen- en I/O-bronnen in beslag nemen. Met name de grootte van middelen, workflows, het aantal gebruikers en de frequentie waarmee activa worden ingevoerd, kunnen van invloed zijn op de algehele systeemprestaties. Tot de meest hulpbronnenintensieve bewerkingen behoren het opnemen en replicatieworkflows van AEM-middelen. Een intensief gebruik van deze workflows op één AEM-ontwerpinstantie kan een negatief effect hebben op de efficiëntie van het schrijven.

Als u deze taken verschuift naar speciale arbeidersinstanties, kunnen de CPU-, geheugen- en IO-overheadkosten worden verminderd. Over het algemeen is het de bedoeling om taken die intensieve CPU-/geheugen-/IO-bronnen verbruiken, over te brengen naar speciale arbeidersinstanties. In de volgende secties vindt u aanbevolen gevallen voor het offloaden van middelen.

## AEM Assets verschuiven {#aem-assets-offloading}

AEM Assets implementeert een native asset-specific workflowextensie voor offloading. Het bouwt op de generische werkschemauitbreiding voort die het het ontladen kader verstrekt, maar omvat extra activa-specifieke eigenschappen in de implementatie. Het doel van het offloaden van middelen is om de workflow voor DAM Update Asset op efficiënte wijze uit te voeren op een geüpload element. Bij het offloaden van elementen kunt u de innameworkflows beter beheren.

## AEM Assets onderdelen verschuiven {#aem-assets-offloading-components}

In het volgende diagram worden de belangrijkste componenten in het offloadproces van bedrijfsmiddelen weergegeven:

![chlimage_1-55](assets/chlimage_1-55.png)

### Workflow voor het offloaden van middelen door DAM-update {#dam-update-asset-offloading-workflow}

De workflow voor het offloaden van middelen uit DAM-update wordt uitgevoerd op de primaire (auteur)server waarop de gebruiker de elementen uploadt. Deze workflow wordt geactiveerd door een standaardworkflow. In plaats van het geüploade element te verwerken, maakt deze offloadworkflow een nieuwe taak met het onderwerp *com/adobe/granite/workflow/offloading*. De offloading-workflow voegt de naam van de doelworkflow toe: in dit geval de DAM Update Asset-workflow en het pad van het element naar de payload van de taak. Nadat de offloadtaak is gemaakt, wacht de offloadworkflow in de eerste instantie totdat de offloadtaak is uitgevoerd.

### Taakbeheer {#job-manager}

De manager van de baan verdeelt nieuwe banen aan arbeidersinstanties. Wanneer het ontwerpen van het distributiemechanisme, is het belangrijk om onderwerpenablement in aanmerking te nemen. Taken kunnen alleen worden toegewezen aan gevallen waarin het taakonderwerp is ingeschakeld. Maak het onderwerp `com/adobe/granite/workflow/offloading` op primair onbruikbaar, en laat het op de worker toe om ervoor te zorgen dat de baan aan de worker wordt toegewezen.

### AEM-offloading {#aem-offloading}

Het offloading-framework identificeert de workflow voor het offloaden van taken die zijn toegewezen aan arbeidersinstanties en gebruikt replicatie om deze fysiek te vervoeren, inclusief hun nuttige last (bijvoorbeeld afbeeldingen die moeten worden ingeslikt) naar workers.

### Werkstroom van taakgebruiker {#workflow-offloading-job-consumer}

Zodra een baan op de arbeider wordt geschreven, roept de baanmanager de baanconsument verantwoordelijk voor het *com/adobe/granite/workflow/offloading* onderwerp. De taakgebruiker voert vervolgens de DAM Update Asset-workflow uit op het element.

## Sling Topology {#sling-topology}

De het Verdelen topologiegroepen AEM instanties en laat hen toe om zich van elkaar bewust te zijn, onafhankelijk van de onderliggende persistentie. Dit kenmerk van de het Verdelen topologie laat u topologieën voor niet-gegroepeerde, gegroepeerde, en gemengde scenario&#39;s tot stand brengen. Een instantie kan eigenschappen aan de volledige topologie blootstellen. Het kader verstrekt callbacks voor het luisteren aan veranderingen in de topologie (instanties en eigenschappen). De het verkopen topologie verstrekt de stichting voor het Verdelen van verdeelde banen.

### Verspreide banen verkopen {#sling-distributed-jobs}

Het verkopen van verdeelde banen vergemakkelijkt de distributie van banen onder een reeks instanties die lid van de topologie zijn. Sling-banen zijn gebaseerd op het idee van mogelijkheden. Een baan wordt bepaald door zijn baanonderwerp. Om een baan in werking te stellen, moet een geval een baanconsument voor een specifiek baanonderwerp verstrekken. Het taakonderwerp is de belangrijkste drijfveer voor het distributiemechanisme.

Taken worden alleen verdeeld over instanties die een professionele consument voor het onderwerp bieden. Door baanconsumenten op een geval toe te laten/onbruikbaar te maken, kunt u de mogelijkheden van een geval bepalen en het distributiemechanisme beïnvloeden. De beschikbare baanconsumenten van een instantie worden uitgezonden aan de volledige topologie.

In dit verband betekent de term distributie het toewijzen van een baan aan een specifiek geval dat een baanconsument voorziet. De toewijzing aan een instantie wordt opgeslagen in de repository. Met andere woorden, het Verdelen van verdeelde banen kan aan om het even welke instantie in de topologie door gebrek worden toegewezen. Andere taken kunnen echter alleen worden uitgevoerd door instanties die dezelfde opslagplaats delen. Dit betekent dat deze taken alleen kunnen worden uitgevoerd door instanties die deel uitmaken van hetzelfde cluster. Taken die zijn toegewezen aan instanties van een andere cluster, worden niet uitgevoerd.

### Kader voor Graniet offloading {#granite-offloading-framework}

Het Granite offloading-framework is een aanvulling op Sling job distribution om taken uit te voeren die zijn toegewezen aan niet-geclusterde instanties. Er wordt geen distributie uitgevoerd (instantie-toewijzing). Nochtans, identificeert het Verschuivende banen die aan niet-gegroepeerde instanties werden verdeeld, en vervoert hen naar de doelinstantie voor uitvoering. Momenteel, gebruikt het ontladen replicatie om dit baanvervoer uit te voeren. Als u een taak wilt uitvoeren, definieert offloaden de invoer en de uitvoer, die vervolgens worden gecombineerd met de taak om de taaklading te genereren.

Het verkopen van gedistribueerde banen biedt het kader voor werk en verdeling. Bij granietoffloading wordt alleen het vervoer verzorgd voor het speciale geval waarin banen worden verdeeld over niet-geclusterde gevallen.

Naast vervoer biedt het offloading-kader een uitbreiding voor de workflow-engine. Hierdoor kan het framework gedistribueerde taken maken als onderdeel van een workflow en wachten tot de workflow is voltooid, voordat de workflow verder gaat. Het wordt geïmplementeerd met de externe stap-API van de workflow vanuit de workflow-engine. Een van de extensies vergemakkelijkt de algemene distributie van workflows. Stappen met één workflow worden niet ondersteund.

Het het ontladen kader komt ook met een gebruikersinterface (UI) om baanonderwerpenablement over de volledige topologie te visualiseren en te controleren. UI laat u gemakkelijk het onderwerp toelaten om verdeelde banen te verdelen. U kunt offloading ook instellen zonder de interface.

## Algemene richtsnoeren en beste praktijken voor het ontladen van activa {#general-guidance-and-best-practices-for-asset-offloading}

Elke implementatie is uniek en er is dus geen standaardconfiguratie voor alle offloading. In de volgende secties vindt u richtlijnen en tips en tips voor het oplossen van problemen bij het offloaden van bedrijfsmiddelen.

Het ontladen van activa brengt ook algemene kosten met zich mee voor het systeem, waaronder bedrijfsoverheadkosten. Als u problemen ondervindt met het laden van middelen, raadt Adobe u aan eerst de configuratie te verbeteren zonder deze te offloaden. Overweeg de volgende opties voordat u overschakelt op het offloaden van elementen:

* Hardware schalen
* Workflows optimaliseren
* Tijdelijke workflows gebruiken
* Het aantal cores beperken dat wordt gebruikt voor workflows

Als u tot de conclusie komt dat het offloaden van middelen een geschikte aanpak voor u is, geeft Adobe de volgende richtlijnen:

* Een op TarMK gebaseerde implementatie wordt aanbevolen
* Op TarMK gebaseerde elementen offloading is niet ontworpen voor uitgebreide horizontale schaling
* Zorg ervoor dat de netwerkprestaties tussen auteur en arbeiders bevredigend zijn

### Aanbevolen middelen na implementatie {#recommended-assets-offloading-deployment}

Met AEM en Oak, zijn er verscheidene plaatsingsscenario&#39;s mogelijk. Voor het offloaden van middelen, wordt een op TarMK gebaseerde plaatsing met gedeelde datastore geadviseerd. Het volgende diagram schetst de geadviseerde plaatsing:

![chlimage_1-56](assets/chlimage_1-56.png)

Voor details rond het vormen van een datastore, zie het [Vormen van knoopopslag en gegevensopslag in AEM](../sites-deploying/data-store-config.md).

### Automatisch agentenbeheer uitschakelen {#turning-off-automatic-agent-management}

Adobe raadt u aan om automatisch agentbeheer uit te schakelen omdat dit geen ondersteuning biedt voor replicatie zonder binaire getallen en omdat dit verwarring kan veroorzaken wanneer u een nieuwe offloadtopologie instelt. Bovendien steunt het niet automatisch de voorwaartse replicatiestroom die door binair-minder replicatie wordt vereist.

1. Open Configuration Manager via de URL `http://localhost:4502/system/console/configMgr`.
1. Open de configuratie voor `OffloadingAgentManager` (`http://localhost:4502/system/console/configMgr/com.adobe.granite.offloading.impl.transporter.OffloadingAgentManager`).
1. Automatisch agentbeheer uitschakelen.

### Voorwaartse replicatie gebruiken {#using-forward-replication}

Door gebrek, gebruikt het ontladen van vervoer omgekeerde replicatie om de ontladen activa van de worker aan primaire terug te trekken. De omgekeerde replicatieagenten steunen binair-geen replicatie. U zou het ontladen moeten vormen om door:sturen replicatie te gebruiken om de ontladen activa terug van worker aan primair te duwen.

1. Als u van de standaardconfiguratie gebruikend omgekeerde replicatie migreert, maak of schrap alle agenten genoemd &quot; `offloading_outbox`&quot; en &quot; `offloading_reverse_*`&quot; op primair en arbeider onbruikbaar, waar &amp;ast; vertegenwoordigt Sling identiteitskaart van de doelinstantie.
1. Voor elke worker maakt u nieuwe replicatieagent die naar de primaire worker verwijst. De procedure is het zelfde als het creëren van voorwaartse agenten van primair aan arbeider. Zie [Replicatieagents maken voor offloading](../sites-deploying/offloading.md#creating-replication-agents-for-offloading) voor instructies over het instellen van offloading-replicatieagents.
1. Open configuratie voor `OffloadingDefaultTransporter` (`http://localhost:4502/system/console/configMgr/com.adobe.granite.offloading.impl.transporter.OffloadingDefaultTransporter`).
1. Wijzig de waarde van de eigenschap `default.transport.agent-to-master.prefix` van `offloading_reverse` naar `offloading`.

<!-- TBD: Make updates to the configuration for allow and block list after product updates are done.
-->

### Het gebruiken van gedeelde datastore en binair-less replicatie tussen auteur en arbeiders  {#using-shared-datastore-and-binary-less-replication-between-author-and-workers}

Het gebruik van binair-minder replicatie wordt geadviseerd om de vervoeroverheadkosten voor activa het ontladen te verminderen. Om te weten hoe te opstelling binair-geen replicatie voor een gedeelde datastore, zie het [Vormen van de Opslag van Knoop en de Opslag van Gegevens in AEM](/help/sites-deploying/data-store-config.md). De procedure is niet verschillend voor Activa die, behalve dat het andere replicatieagenten impliceert. Omdat de binaire-minder replicatie slechts met voorwaartse replicatieagenten werkt, zou u voorwaartse replicatie voor alle het ontladen agenten ook moeten gebruiken.

### Vervoerspakketten uitschakelen {#turning-off-transport-packages}

Door gebrek, leidt het ontladen tot een inhoudspakket dat de het ontladen baan en baanlading (het originele element) bevat, en vervoert dit enige het ontladen pakket gebruikend één enkel replicatieverzoek. Het maken van deze offloading-pakketten is contraproductief wanneer u binair-geen replicatie gebruikt, omdat binaire bestanden bij het maken van het pakket opnieuw met serienummering in het pakket worden gecodeerd. Het gebruik van deze vervoerpakketten kan worden uitgezet, wat de het ontladen baan en lading veroorzaakt in veelvoudige replicatieverzoeken, één voor elke ladingsingang worden vervoerd. Deze manier, kan het voordeel van binair-minder replicatie worden gebruikt.

1. Open de componentconfiguratie van de *component OffloadingDefaultTransporter* op [http://localhost:4502/system/console/configMgr/com.adobe.granite.offloading.impl.transporter.OffloadingDefaultTransporter](http://localhost:4502/system/console/configMgr/com.adobe.granite.offloading.impl.transporter.OffloadingDefaultTransporter)
1. Schakel het *eigenschappenreplicatiepakket (default.transport.contentPackage)* uit.

### Het transport van het workflowmodel uitschakelen {#disabling-the-transport-of-workflow-model}

Standaard voegt de *DAM Update Asset Offloading* -offloadworkflow het workflowmodel toe om de worker aan te roepen tot de taaklading. Omdat deze workflow standaard het out-of-the-box *DAM Update Asset* -model volgt, kan deze extra lading worden verwijderd.

Als het workflowmodel is uitgeschakeld voor het laden van de taak, moet u ervoor zorgen dat u wijzigingen naar het workflowmodel waarnaar wordt verwezen, distribueert met andere gereedschappen, zoals pakketbeheer.

Om het vervoer van het werkschemamodel onbruikbaar te maken, wijzig de DAM Update Workflow van de Offload van Activa.

1. Open de workflowconsole via [http://localhost:4502/libs/cq/workflow/content/console.html](http://localhost:4502/libs/cq/workflow/content/console.html).
1. Open het tabblad Modellen.
1. Open het workflowmodel van DAM Update Asset Offloading.
1. Open stapeigenschappen voor de stap Verschuiving DAM-workflow.
1. Open het tabblad Argumenten en schakel de opties Model toevoegen aan invoer en Model toevoegen aan uitvoer uit.
1. Sla de wijzigingen in het model op.

### Het pollinterval optimaliseren {#optimizing-the-polling-interval}

Offloading van werkstroom wordt geïmplementeerd met behulp van een externe workflow op de primaire werkstroom, die opiniepeilt voor de voltooiing van de offloaded workflow op de worker. Het standaardpollinginterval voor de externe werkstroomprocessen is vijf seconden. Adobe raadt u aan het pollinginterval van de stap Middelen die wordt verwijderd, te verhogen tot ten minste 15 seconden om de overhead van de primaire items te verminderen.

1. Open de workflowconsole via [http://localhost:4502/libs/cq/workflow/content/console.html](http://localhost:4502/libs/cq/workflow/content/console.html).

1. Open het tabblad Modellen.
1. Open het workflowmodel van DAM Update Asset Offloading.
1. Open de stapeigenschappen voor de DAM-stap voor het verschuiven van de workflow.
1. Open het tabblad Commons en pas de waarde van de eigenschap Periode aan.
1. Sla de wijzigingen in het model op.

## Meer bronnen {#more-resources}

Dit document richt zich op het offloaden van bedrijfsmiddelen. Hier volgt een aantal aanvullende documentatie over offloading:

* [Taken verschuiven](/help/sites-deploying/offloading.md)
* [Offloader middelenwerkstroom](/help/sites-administering/workflow-offloader.md)

