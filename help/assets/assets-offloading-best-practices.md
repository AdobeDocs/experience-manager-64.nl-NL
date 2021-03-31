---
title: Aanbevolen werkwijzen voor het verschuiven van elementen
description: Aanbevolen gebruiksgevallen en aanbevolen procedures voor het offloaden van workflows voor het opnemen en repliceren van bedrijfsmiddelen in AEM Assets.
contentOwner: AG
feature: Beheer van bedrijfsmiddelen
role: Business Practice,Administrator
translation-type: tm+mt
source-git-commit: 29e3cd92d6c7a4917d7ee2aa8d9963aa16581633
workflow-type: tm+mt
source-wordcount: '1823'
ht-degree: 0%

---


# Aanbevolen werkwijzen {#assets-offloading-best-practices} voor het verschuiven van elementen

>[!WARNING]
>
>Deze functie is vervangen AEM 6.4 en wordt verwijderd in AEM 6.5. Plan dienovereenkomstig.

Het verwerken van grote bestanden en het uitvoeren van workflows in Adobe Experience Manager (AEM) Assets kan aanzienlijke CPU-, geheugen- en I/O-bronnen in beslag nemen. Met name de grootte van middelen, workflows, het aantal gebruikers en de frequentie waarmee activa worden ingevoerd, kunnen van invloed zijn op de algehele systeemprestaties. De meest hulpbron-intensieve verrichtingen omvatten AEM activa opnemen en replicatiewerkschema&#39;s. Een intensief gebruik van deze workflows op één AEM ontwerpinstantie kan een negatief effect hebben op de ontwerpefficiëntie.

Als u deze taken verschuift naar speciale arbeidersinstanties, kunnen de CPU-, geheugen- en IO-overheadkosten worden verminderd. Over het algemeen is het de bedoeling om taken die intensieve CPU-/geheugen-/IO-bronnen verbruiken, over te brengen naar speciale arbeidersinstanties. In de volgende secties vindt u aanbevolen gevallen voor het offloaden van middelen.

## AEM Assets-offloading {#aem-assets-offloading}

AEM Assets implementeert een native asset-specific workflowextensie voor offloading. Het bouwt op de generische werkschemauitbreiding voort die het het ontladen kader verstrekt, maar omvat extra activa-specifieke eigenschappen in de implementatie. Het doel van het offloaden van middelen is om de workflow voor DAM Update Asset op efficiënte wijze uit te voeren op een geüpload element. Bij het offloaden van elementen kunt u de innameworkflows beter beheren.

## AEM Assets-offloadcomponenten {#aem-assets-offloading-components}

In het volgende diagram worden de belangrijkste componenten in het offloadproces van bedrijfsmiddelen weergegeven:

![chlimage_1-55](assets/chlimage_1-55.png)

### Workflow voor het offloaden van bedrijfsmiddelen door DAM-update {#dam-update-asset-offloading-workflow}

De workflow voor het offloaden van middelen uit DAM-update wordt uitgevoerd op de primaire (auteur)server waarop de gebruiker de elementen uploadt. Deze workflow wordt geactiveerd door een standaardworkflow. In plaats van het geüploade element te verwerken, wordt met deze offloadworkflow een nieuwe taak gemaakt met het onderwerp *com/adobe/granite/workflow/offloading*. De offloading-workflow voegt de naam van de doelworkflow toe: in dit geval de DAM Update Asset-workflow en het pad van het element naar de payload van de taak. Nadat de offloadtaak is gemaakt, wacht de offloadworkflow in de eerste instantie totdat de offloadtaak is uitgevoerd.

### Taakbeheer {#job-manager}

De manager van de baan verdeelt nieuwe banen aan arbeidersinstanties. Wanneer het ontwerpen van het distributiemechanisme, is het belangrijk om onderwerpenablement in aanmerking te nemen. Taken kunnen alleen worden toegewezen aan gevallen waarin het taakonderwerp is ingeschakeld. Schakel het onderwerp `com/adobe/granite/workflow/offloading` in de primaire toepassing uit en schakel het onderwerp in de worker in om ervoor te zorgen dat de taak aan de worker wordt toegewezen.

### AEM ontladen {#aem-offloading}

Het offloading-framework identificeert de workflow voor het offloaden van taken die zijn toegewezen aan arbeidersinstanties en gebruikt replicatie om deze fysiek te vervoeren, inclusief hun nuttige last (bijvoorbeeld afbeeldingen die moeten worden ingeslikt) naar workers.

### Workflow voor het ontladen van taken voor consumenten {#workflow-offloading-job-consumer}

Zodra een baan op de arbeider wordt geschreven, roept de baanmanager de baanconsument verantwoordelijk voor *com/adobe/granite/workflow/offloading* onderwerp. De taakgebruiker voert vervolgens de DAM Update Asset-workflow uit op het element.

## Onderwerptopologie {#sling-topology}

De het Verdelen topologiegroepen AEM instanties en laten hen toe om zich van elkaar bewust te zijn, onafhankelijk van de onderliggende persistentie. Dit kenmerk van de het Verdelen topologie laat u topologieën voor niet-gegroepeerde, gegroepeerde, en gemengde scenario&#39;s tot stand brengen. Een instantie kan eigenschappen aan de volledige topologie blootstellen. Het kader verstrekt callbacks voor het luisteren aan veranderingen in de topologie (instanties en eigenschappen). De het verkopen topologie verstrekt de stichting voor het Verdelen van verdeelde banen.

### Verdeelde taken verkopen {#sling-distributed-jobs}

Het verkopen van verdeelde banen vergemakkelijkt de distributie van banen onder een reeks instanties die lid van de topologie zijn. Sling-banen zijn gebaseerd op het idee van mogelijkheden. Een baan wordt bepaald door zijn baanonderwerp. Om een baan in werking te stellen, moet een geval een baanconsument voor een specifiek baanonderwerp verstrekken. Het taakonderwerp is de belangrijkste drijfveer voor het distributiemechanisme.

Taken worden alleen verdeeld over instanties die een professionele consument voor het onderwerp bieden. Door baanconsumenten op een geval toe te laten/onbruikbaar te maken, kunt u de mogelijkheden van een geval bepalen en het distributiemechanisme beïnvloeden. De beschikbare baanconsumenten van een instantie worden uitgezonden aan de volledige topologie.

In dit verband betekent de term distributie het toewijzen van een baan aan een specifiek geval dat een baanconsument voorziet. De toewijzing aan een instantie wordt opgeslagen in de repository. Met andere woorden, het Verdelen van verdeelde banen kan aan om het even welke instantie in de topologie door gebrek worden toegewezen. Andere taken kunnen echter alleen worden uitgevoerd door instanties die dezelfde opslagplaats delen. Dit betekent dat deze taken alleen kunnen worden uitgevoerd door instanties die deel uitmaken van hetzelfde cluster. Taken die zijn toegewezen aan instanties van een andere cluster, worden niet uitgevoerd.

### Graniet offloading framework {#granite-offloading-framework}

Het Granite offloading-framework is een aanvulling op Sling job distribution om taken uit te voeren die zijn toegewezen aan niet-geclusterde instanties. Er wordt geen distributie uitgevoerd (instantie-toewijzing). Nochtans, identificeert het Verschuivende banen die aan niet-gegroepeerde instanties werden verdeeld, en vervoert hen naar de doelinstantie voor uitvoering. Momenteel, gebruikt het ontladen replicatie om dit baanvervoer uit te voeren. Als u een taak wilt uitvoeren, definieert offloaden de invoer en de uitvoer, die vervolgens worden gecombineerd met de taak om de taaklading te genereren.

Het verkopen van gedistribueerde banen biedt het kader voor werk en verdeling. Bij granietoffloading wordt alleen het vervoer verzorgd voor het speciale geval waarin banen worden verdeeld over niet-geclusterde gevallen.

Naast vervoer biedt het offloading-kader een uitbreiding voor de workflow-engine. Hierdoor kan het framework gedistribueerde taken maken als onderdeel van een workflow en wachten tot de workflow is voltooid, voordat de workflow verder gaat. Het wordt geïmplementeerd met de externe stap-API van de workflow vanuit de workflow-engine. Een van de extensies vergemakkelijkt de algemene distributie van workflows. Stappen met één workflow worden niet ondersteund.

Het het ontladen kader komt ook met een gebruikersinterface (UI) om baanonderwerpenablement over de volledige topologie te visualiseren en te controleren. UI laat u gemakkelijk het onderwerp toelaten om verdeelde banen te verdelen. U kunt offloading ook instellen zonder de interface.

## Algemene richtlijnen en beste praktijken voor het ontladen van activa {#general-guidance-and-best-practices-for-asset-offloading}

Elke implementatie is uniek en er is dus geen standaardconfiguratie voor alle offloading. In de volgende secties vindt u richtlijnen en tips en tips voor het oplossen van problemen bij het offloaden van bedrijfsmiddelen.

Het ontladen van activa brengt ook algemene kosten met zich mee voor het systeem, waaronder bedrijfsoverheadkosten. Als u problemen ondervindt met het laden van elementen, raadt Adobe u aan eerst de configuratie te verbeteren zonder dat u dit hoeft te offloaden. Overweeg de volgende opties voordat u overschakelt op het offloaden van elementen:

* Hardware schalen
* Workflows optimaliseren
* Tijdelijke workflows gebruiken
* Het aantal cores beperken dat wordt gebruikt voor workflows

Als u tot de conclusie komt dat het offloaden van middelen een geschikte aanpak voor u is, biedt Adobe de volgende richtlijnen:

* Een op TarMK gebaseerde implementatie wordt aanbevolen
* Op TarMK gebaseerde elementen offloading is niet ontworpen voor uitgebreide horizontale schaling
* Zorg ervoor dat de netwerkprestaties tussen auteur en arbeiders bevredigend zijn

### Aanbevolen middelen voor offloading van implementatie {#recommended-assets-offloading-deployment}

Met AEM en eikel, zijn er verscheidene plaatsingsscenario&#39;s mogelijk. Voor het offloaden van middelen, wordt een op TarMK gebaseerde plaatsing met gedeelde datastore geadviseerd. Het volgende diagram schetst de geadviseerde plaatsing:

![chlimage_1-56](assets/chlimage_1-56.png)

Voor details rond het vormen van een datastore, zie [Het vormen knoopopslag en gegevensopslag in AEM](../sites-deploying/data-store-config.md).

### Automatisch agentbeheer uitschakelen {#turning-off-automatic-agent-management}

Adobe adviseert dat u automatisch agentenbeheer uitzet omdat het binair-geen replicatie steunt en verwarring kan veroorzaken wanneer vestiging een nieuwe het ontladen topologie. Bovendien steunt het niet automatisch de voorwaartse replicatiestroom die door binair-minder replicatie wordt vereist.

1. Open de Manager van de Configuratie van URL `http://localhost:4502/system/console/configMgr`.
1. Open de configuratie voor `OffloadingAgentManager` (`http://localhost:4502/system/console/configMgr/com.adobe.granite.offloading.impl.transporter.OffloadingAgentManager`).
1. Automatisch agentbeheer uitschakelen.

### Voorwaartse replicatie {#using-forward-replication} gebruiken

Door gebrek, gebruikt het ontladen van vervoer omgekeerde replicatie om de ontladen activa van de worker aan primaire terug te trekken. De omgekeerde replicatieagenten steunen binair-geen replicatie. U zou het ontladen moeten vormen om door:sturen replicatie te gebruiken om de ontladen activa terug van worker aan primair te duwen.

1. Als u van de standaardconfiguratie gebruikend omgekeerde replicatie migreert, maak of schrap alle agenten genoemd &quot; `offloading_outbox`&quot;en &quot; `offloading_reverse_*`&quot;op primair en arbeider onbruikbaar, waar &amp;ast; vertegenwoordigt Sling identiteitskaart van de doelinstantie.
1. Voor elke worker maakt u nieuwe replicatieagent die naar de primaire worker verwijst. De procedure is het zelfde als het creëren van voorwaartse agenten van primair aan arbeider. Zie [Replicatieagents maken voor offloading](../sites-deploying/offloading.md#creating-replication-agents-for-offloading) voor instructies over het instellen van offloading-replicatieagents.
1. Open configuratie voor `OffloadingDefaultTransporter` (`http://localhost:4502/system/console/configMgr/com.adobe.granite.offloading.impl.transporter.OffloadingDefaultTransporter`).
1. Wijzig de waarde van de eigenschap `default.transport.agent-to-master.prefix` van `offloading_reverse` in `offloading`.

<!-- TBD: Make updates to the configuration for allow and block list after product updates are done.
TBD: Update the property in the last step when GRANITE-30586 is fixed.
-->

### Het gebruiken van gedeelde datastore en binair-less replicatie tussen auteur en arbeiders {#using-shared-datastore-and-binary-less-replication-between-author-and-workers}

Het gebruik van binair-minder replicatie wordt geadviseerd om de vervoeroverheadkosten voor activa het ontladen te verminderen. Om te weten hoe te opstelling binair-geen replicatie voor een gedeelde datastore, zie [het Vormen van de Opslag van Knoop en de Opslag van Gegevens in AEM](/help/sites-deploying/data-store-config.md). De procedure is niet verschillend voor Activa die, behalve dat het andere replicatieagenten impliceert. Omdat de binaire-minder replicatie slechts met voorwaartse replicatieagenten werkt, zou u voorwaartse replicatie voor alle het ontladen agenten ook moeten gebruiken.

### Vervoerspakketten uitschakelen {#turning-off-transport-packages}

Door gebrek, leidt het ontladen tot een inhoudspakket dat de het ontladen baan en baanlading (het originele element) bevat, en vervoert dit enige het ontladen pakket gebruikend één enkel replicatieverzoek. Het maken van deze offloading-pakketten is contraproductief wanneer u binair-geen replicatie gebruikt, omdat binaire bestanden opnieuw in het pakket worden geserialiseerd wanneer u het pakket maakt. Het gebruik van deze vervoerpakketten kan worden uitgezet, wat de het ontladen baan en lading veroorzaakt in veelvoudige replicatieverzoeken, één voor elke ladingsingang worden vervoerd. Deze manier, kan het voordeel van binair-minder replicatie worden gebruikt.

1. Open de componentconfiguratie van *OffloadingDefaultTransporter* component op [http://localhost:4502/system/console/configMgr/com.adobe.granite.offloading.impl.transporter.OffloadingDefaultTransporter](http://localhost:4502/system/console/configMgr/com.adobe.granite.offloading.impl.transporter.OffloadingDefaultTransporter)
1. Schakel de eigenschap *Replication Package (default.transport.contentPackage)* uit.

### Het vervoer van het werkschemamodel {#disabling-the-transport-of-workflow-model} onbruikbaar maken

Standaard wordt met de *DAM Update Asset Offloading* offloading-workflow het workflowmodel toegevoegd waarmee de worker wordt aangeroepen bij de taaklading. Omdat deze workflow standaard het model *DAM Update Asset* volgt, kan deze extra lading worden verwijderd.

Als het workflowmodel is uitgeschakeld voor het laden van de taak, moet u ervoor zorgen dat u wijzigingen naar het workflowmodel waarnaar wordt verwezen, distribueert met andere gereedschappen, zoals pakketbeheer.

Om het vervoer van het werkschemamodel onbruikbaar te maken, wijzig de DAM Update Workflow van de Offload van Activa.

1. Open de workflowconsole via [http://localhost:4502/libs/cq/workflow/content/console.html](http://localhost:4502/libs/cq/workflow/content/console.html).
1. Open het tabblad Modellen.
1. Open het workflowmodel van DAM Update Asset Offloading.
1. Open stapeigenschappen voor de stap Verschuiving DAM-workflow.
1. Open het tabblad Argumenten en schakel de opties Model toevoegen aan invoer en Model toevoegen aan uitvoer uit.
1. Sla de wijzigingen in het model op.

### Het opiniepeilingsinterval {#optimizing-the-polling-interval} optimaliseren

Offloading van werkstroom wordt geïmplementeerd met behulp van een externe workflow op de primaire werkstroom, die opiniepeilt voor de voltooiing van de offloaded workflow op de worker. Het standaardpollinginterval voor de externe werkstroomprocessen is vijf seconden. Adobe raadt u aan het pollinginterval van de stap Elementen die wordt verschoven naar ten minste 15 seconden te verhogen om de overhead bij offloading op de primaire server te verminderen.

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

