---
title: Richtlijnen voor afstelling van middelenprestaties
description: Hoofdfocusgebieden rondom [!DNL Experience Manager] configuratie, veranderingen in hardware, software, en netwerkcomponenten om knelpunten te verwijderen en de prestaties van te optimaliseren [!DNL Experience Manager] Elementen.
contentOwner: AG
feature: Asset Management
role: Architect,Admin
exl-id: 6c1bff46-f9e0-4638-9374-a9e820d30534
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '3164'
ht-degree: 0%

---

# Richtlijnen voor afstelling van middelenprestaties {#assets-performance-tuning-guide}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Een installatie van Adobe Experience Manager Assets bevat een aantal hardware-, software- en netwerkcomponenten. Afhankelijk van uw plaatsingsscenario, kunt u specifieke configuratieveranderingen in hardware, software, en netwerkcomponenten vereisen om prestatiesknelpunten te verwijderen.

Bovendien kunt u door bepaalde richtlijnen voor de optimalisatie van hardware en software te identificeren en aan te houden een solide basis leggen voor uw [!DNL Experience Manager] De plaatsing van activa om aan verwachtingen rond prestaties, scalability, en betrouwbaarheid te voldoen.

Slechte prestaties in [!DNL Experience Manager] Elementen kunnen van invloed zijn op de interactieve prestaties, de verwerking van bedrijfsmiddelen, de downloadsnelheid en andere aspecten.

In feite, is de prestatiesoptimalisering een fundamentele taak die u uitvoert alvorens u doelmetriek voor om het even welk project vestigt.

Hier zijn bepaalde belangrijke aandachtsgebieden waaromheen u prestatieproblemen ontdekt en verhelpt voordat deze van invloed zijn op gebruikers.

## Platform {#platform}

while [!DNL Experience Manager] Adobe wordt ondersteund op een aantal platforms. In Linux en Windows heeft de grootste ondersteuning voor native gereedschappen gevonden. Dit levert optimale prestaties en vereenvoudigt de implementatie. In het ideale geval moet u een 64-bits besturingssysteem implementeren om te voldoen aan de hoge geheugenvereisten van een [!DNL Experience Manager] Implementatie van middelen. Zoals bij alle [!DNL Experience Manager] implementatie, moet u TarMK waar mogelijk implementeren. Hoewel TarMK niet voorbij één enkele auteurinstantie kan schrapen, wordt het gevonden om beter te presteren dan MongoMK. U kunt TarMK-offloadinstanties toevoegen om de verwerkingskracht van de workflow te verhogen [!DNL Experience Manager] Implementatie van middelen.

### Temp-map {#temp-folder}

Om de uploadtijden van middelen te verbeteren, gebruik krachtige opslag voor de folder van de Temp van Java. In Linux en Windows kan een RAM-station of SSD worden gebruikt. In cloudomgevingen kan een vergelijkbaar type snelle opslag worden gebruikt. Bijvoorbeeld in Amazon EC2, en [ephalogeffect](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/InstanceStorage.html) kan voor de tijdelijke map worden gebruikt.

Ervan uitgaande dat de server over voldoende geheugen beschikt, configureert u een RAM-station. Voer in Linux de volgende opdrachten uit om een 8 GB RAM-station te maken:

```shell
mkfs -q /dev/ram1 800000
 mkdir -p /mnt/aem-tmp
 mount /dev/ram1 /mnt/aem-tmp
 df -H | grep aem-tmp
```

In Windows OS moet u een stuurprogramma van een andere fabrikant gebruiken om een RAM-station te maken of gewoon krachtige opslagruimte zoals SSD gebruiken.

Zodra het volume van de hoge prestatietemp klaar is, dan plaats de parameter JVM -Djava.io.tmpdir. U kunt bijvoorbeeld de JVM-parameter hieronder toevoegen aan de CQ_JVM_OPTS-variabele in het bin/start-script van AEM:

`-Djava.io.tmpdir=/mnt/aem-tmp`

## Java-configuratie {#java-configuration}

### Java-versie {#java-version}

Omdat Oracle de release van updates voor Java 7 sinds april 2015 heeft stopgezet, raadt Adobe aan om te implementeren [!DNL Experience Manager] Middelen in Java 8. In sommige gevallen heeft het een verbeterde prestatie aangetoond.

### JVM-parameters {#jvm-parameters}

U moet de volgende JVM-parameters instellen:

* `-XX:+UseConcMarkSweepGC`
* `-Doak.queryLimitInMemory`=500000
* `-Doak.queryLimitReads`=100000
* `-Dupdate.limit`=250000
* `-Doak.fastQuerySize`=true

## Gegevensopslag en geheugenconfiguratie {#data-store-and-memory-configuration}

### Configuratie bestandsgegevensopslag {#file-data-store-configuration}

Het scheiden van de gegevensopslag van de segmentopslag wordt geadviseerd voor allen [!DNL Experience Manager] Gebruikers van middelen. Bovendien vormt het vormen van `maxCachedBinarySize` en `cacheSizeInMB` parameters kunnen u helpen de prestaties te maximaliseren. Set `maxCachedBinarySize` tot de kleinste bestandsgrootte die in de cache kan worden opgeslagen. Geef de grootte op van de cache in het geheugen die moet worden gebruikt voor de datastore in `cacheSizeInMB`. Adobe raadt u aan deze waarde in te stellen tussen 2 en 10 procent van de totale heapgrootte. Het testen van de belasting/prestaties kan echter helpen de ideale instelling te bepalen.

### De maximale grootte van de cache voor gebufferde afbeeldingen configureren {#configure-the-maximum-size-of-the-buffered-image-cache}

Wanneer u grote hoeveelheden assets uploadt naar Adobe Experience Manager, om onverwachte pieken in het geheugenverbruik mogelijk te maken en om te voorkomen dat JVM uitvalt met OutOfMemoryErrors, verkleint u de geconfigureerde maximumgrootte van de cache voor gebufferde images. Neem bijvoorbeeld een voorbeeld van een systeem met een maximale heap (- `Xmx`param) van 5 GB, een Oak BlobCache ingesteld op 1 GB en een documentcache ingesteld op 2 GB. In dit geval neemt de gebufferde cache maximaal 1,25 GB en geheugen in beslag, waardoor er slechts 0,75 GB geheugen overblijft voor onverwachte pieken.

Vorm de als buffer opgetreden voor geheim voorgeheugengrootte in de Console van het Web OSGi. At `https://host:port/system/console/configMgr/com.day.cq.dam.core.impl.cache.CQBufferedImageCache`, stelt u de eigenschap in `cq.dam.image.cache.max.memory` in bytes. 1073741824 is bijvoorbeeld 1 GB (1024 x 1024 x 1024 = 1 GB).

Van [!DNL Experience Manager] 6.1 SP1, als u een `sling:osgiConfig` knoop voor het vormen van dit bezit, zorg ervoor om het gegevenstype aan Lang te plaatsen. Zie voor meer informatie [CQBufferedImageCache verbruikt heap tijdens het uploaden van middelen](https://helpx.adobe.com/experience-manager/kb/cqbufferedimagecache-consumes-heap-during-asset-uploads.html).

### Gedeelde gegevensopslag {#shared-data-stores}

Het uitvoeren van S3 of de Gedeelde Datastore van het Dossier kan helpen om schijfruimte te besparen en netwerkproductie in grootschalige implementaties te verhogen. Voor meer informatie over de voor- en nadelen van het gebruik van een gedeelde datastore raadpleegt u [Hulplijn voor middelengrootte](assets-sizing-guide.md).

### S3-gegevensopslag {#s-data-store}

De volgende S3 configuratie van de Opslag van Gegevens ( `org.apache.jackrabbit.oak.plugins.blob.datastore.S3DataStore.cfg`) hielp Adobe 12,8 TB binaire grote voorwerpen (BLOBs) uit een bestaande opslag van dossiergegevens in een S3 gegevensopslag bij een klantenplaats halen:

```conf
accessKey=<snip>
 secretKey=<snip>
 s3Bucket=<snip>
 s3Region=us-standard
 s3EndPoint=<a href="https://s3.amazonaws.com/">s3.amazonaws.com</a>
 connectionTimeout=120000
 socketTimeout=120000
 maxConnections=80
 writeThreads=60
 concurrentUploadsThreads=30
 asyncUploadLimit=30
 maxErrorRetry=1000
 path=/opt/author/crx-quickstart/repository/datastore
 s3RenameKeys=false
 s3Encryption=SSE_S3
 proactiveCaching=true
 uploadRetries=1000
 migrateFailuresCount=400
```

## Netwerkoptimalisatie {#network-optimization}

Adobe raadt aan HTTPS in te schakelen omdat veel bedrijven firewalls hebben die HTTP-verkeer sluizen, wat het uploaden van bestanden negatief beïnvloedt en bestanden beschadigt. Bij grote bestanden uploaden dient u ervoor te zorgen dat gebruikers een bekabelde verbinding met het netwerk hebben omdat een WiFi-netwerk snel verzadigd raakt. Voor richtsnoeren voor het identificeren van netwerkknelpunten raadpleegt u [Hulplijn voor middelengrootte](assets-sizing-guide.md). Om netwerkprestaties te beoordelen door netwerktopologie te analyseren, zie [Overwegingen voor middelennetwerken](assets-network-considerations.md).

Primair, hangt uw strategie van de netwerkoptimalisering van de hoeveelheid beschikbare bandbreedte en de lading op uw af [!DNL Experience Manager] -instantie. De gemeenschappelijke configuratieopties, met inbegrip van firewalls of volmachten kunnen helpen netwerkprestaties verbeteren. Hier volgen enkele belangrijke punten:

* Afhankelijk van uw instantietype (klein, gematigd, groot), zorg ervoor dat u voldoende netwerkbandbreedte voor uw hebt [!DNL Experience Manager] -instantie. De adequate bandbreedtetoewijzing is vooral belangrijk als [!DNL Experience Manager] wordt gehost op AWS.
* Als uw [!DNL Experience Manager] -instantie wordt gehost op AWS, kunt u profiteren van een veelzijdig schalingsbeleid. De instantie vergroten als gebruikers een hoge belasting verwachten. Downsize het voor matige/lage lading.
* HTTPS: De meeste gebruikers hebben firewalls die het verkeer van HTTP snuffelen, wat het uploaden van dossiers of zelfs corrupte dossiers tijdens het uploaden negatief kan beïnvloeden.
* Grote bestanden uploaden: Zorg ervoor dat gebruikers een bekabelde verbinding met het netwerk hebben (WiFi-verbindingen verzadigen snel).

## Workflows {#workflows}

### Tijdelijke workflows {#transient-workflows}

Stel waar mogelijk de DAM Update Asset-workflow in op Transient. De instelling verlaagt aanzienlijk de overheadkosten die nodig zijn voor het verwerken van workflows, omdat workflows in dit geval niet door de normale tracking- en archiveringsprocessen hoeven te gaan.

>[!NOTE]
>
>Standaard is de DAM Update Asset-workflow ingesteld op Overgang in [!DNL Experience Manager] 6.3. In dit geval kunt u de volgende procedure overslaan.

1. Openen `http://localhost:4502/miscadmin` op de [!DNL Experience Manager] -instantie die u wilt configureren.

1. Vouw vanuit de navigatiestructuur uit **[!UICONTROL Tools]** > **[!UICONTROL Workflow]** > **[!UICONTROL Models]** > **[!UICONTROL dam]**.
1. Dubbelklikken **[!UICONTROL DAM Update Asset]**.
1. Van het het drijven hulpmiddelpaneel, schakelaar aan **[!UICONTROL Page]** en klikt u op **[!UICONTROL Page Properties]**.
1. Selecteren **[!UICONTROL Transient Workflow]** Klikken **[!UICONTROL OK]**.

   >[!NOTE]
   >
   >Bepaalde functies ondersteunen geen tijdelijke workflows. Als uw [!DNL Experience Manager] De plaatsing van activa vereist deze eigenschappen, vormt geen voorbijgaande werkschema&#39;s.

   Als er geen tijdelijke workflows kunnen worden gebruikt, voert u de workflow regelmatig uit om gearchiveerde DAM Update Asset-workflows te verwijderen om ervoor te zorgen dat de systeemprestaties niet afnemen.

   Normaal gesproken dient u wekelijks penseelworkflows uit te voeren. Nochtans, in middel-intensieve scenario&#39;s, zoals tijdens brede activaopname, kunt u het vaker in werking stellen.

   Om werkschemazuivering te vormen, voeg een nieuwe Adobe Granite configuratie van de Wrijving van het Werkschema door de console OSGi toe. Vervolgens configureert en plant u de workflow als onderdeel van het wekelijkse onderhoudsvenster.

   Als het leegmaken te lang duurt, is het wel even. Daarom dient u ervoor te zorgen dat uw reinigingstaken zijn voltooid om situaties te voorkomen waarin het leegmaken van werkstromen mislukt vanwege het grote aantal werkstromen.

   Nadat u bijvoorbeeld een groot aantal niet-tijdelijke workflows hebt uitgevoerd (waarmee u knooppunten voor workflowinstanties maakt), kunt u [ACS AEM Comment Workflow Remover](https://adobe-consulting-services.github.io/acs-aem-commons/features/workflow-remover.html) op ad-hocbasis. Het verwijdert overtollige, voltooide werkschemainstanties onmiddellijk eerder dan het wachten op de Adobe Granite planner van de Wrijving van het Werkschema van de.

### Maximumaantal parallelle banen {#maximum-parallel-jobs}

Standaard, [!DNL Experience Manager] wordt een maximumaantal parallelle taken uitgevoerd dat gelijk is aan het aantal processors op de server. Het probleem met deze instelling is dat tijdens perioden van zware belasting alle processors worden bezet door de DAM Update Asset-workflows, waardoor de reactiesnelheid van de gebruikersinterface wordt vertraagd en het voorkomen van [!DNL Experience Manager] van het uitvoeren van andere processen die serverprestaties en stabiliteit beschermen. U kunt deze waarde als een goede praktijk instellen op de helft van de processors die beschikbaar zijn op de server door de volgende stappen uit te voeren:

1. Aan [!DNL Experience Manager] Auteur, ga naar [http://localhost:4502/system/console/slingevent](http://localhost:4702/system/console/slingevent).
1. Klik op Bewerken in elke werkstroomwachtrij die relevant is voor uw implementatie, bijvoorbeeld de Granite Transient Workflow Queue.
1. Wijzig de waarde van Maximale parallelle taken en klik op Opslaan.

Het instellen van een wachtrij op de helft van de beschikbare processors is een werkbare oplossing om mee te beginnen. Het kan echter zijn dat u dit aantal moet verhogen of verlagen om een maximale doorvoer te bereiken en dat aantal aan te passen aan de omgeving. Er zijn afzonderlijke rijen voor tijdelijke en niet-tijdelijke werkstromen evenals andere processen, zoals externe werkschema&#39;s. Als meerdere wachtrijen die zijn ingesteld op 50% van de processors tegelijkertijd actief zijn, kan het systeem snel overbelast raken. De rijen die zwaar worden gebruikt variëren zeer over gebruikersimplementaties. Daarom moet u ze mogelijk nauwkeurig configureren voor maximale efficiëntie zonder dat dit ten koste gaat van de stabiliteit van de server.

### Verschuiven {#offloading}

Voor grote workflows of workflows die veel resources vereisen, zoals videotranscodering, kunt u de DAM Update Asset-workflows verschuiven naar een tweede auteurinstantie. Vaak is het probleem met offloaden dat elke belasting die wordt bespaard door het offloaden van de workflowverwerking, wordt gecompenseerd door de kosten voor het heen en weer repliceren van de inhoud tussen instanties.

Vanaf [!DNL Experience Manager] 6.2 en met een functiepakket voor [!DNL Experience Manager] 6.1, kunt u het ontladen met binair-minder replicatie uitvoeren. In dit model, delen de auteursinstanties een gemeenschappelijke datastore en verzenden slechts de meta-gegevens heen en weer door voorwaartse replicatie. Hoewel deze aanpak goed werkt met een datastore voor gedeelde bestanden, kunnen er problemen zijn met een S3-datastore. Omdat achtergrondschrijfthreads latentie kunnen veroorzaken, is het mogelijk dat een element niet naar de datastore is geschreven voordat de offloadtaak wordt gestart.

### DAM Update Asset Configuration {#dam-update-asset-configuration}

De DAM Update Asset-workflow bevat een volledige reeks stappen die zijn geconfigureerd voor taken, zoals het genereren en integreren van Dynamic Media Classic PTIFF. Het is echter mogelijk dat de meeste gebruikers niet meerdere van deze stappen nodig hebben. Adobe raadt u aan een aangepaste kopie van het workflowmodel voor DAM Update Asset te maken en overbodige stappen te verwijderen. In dit geval werkt u de draagraketten voor DAM Update Asset bij en wijst u deze naar het nieuwe model.

>[!NOTE]
>
>Als u de DAM Update Asset-workflow intensief uitvoert, kan de bestandsdatatastore aanzienlijk groter worden. De resultaten van een door Adobe uitgevoerd experiment hebben aangetoond dat de datastore-grootte met ongeveer 400 GB kan toenemen als binnen 8 uur ongeveer 5500 workflows worden uitgevoerd.
>
>Het is een tijdelijke verhoging, en datastore wordt hersteld aan zijn originele grootte nadat u de taak van de datastore huisvuilinzameling in werking stelt.
>
>Typisch, loopt de de inzamelingstaak van de datastore wekelijks samen met andere geplande onderhoudstaken.
>
>Als u een beperkte schijfruimte hebt en de werkschema&#39;s van de Activa van de Update van DAM intensief in werking stelt, overweeg de taak van de huisvuilinzameling vaker te plannen.

#### Genereren van uitvoering bij uitvoering {#runtime-rendition-generation}

Klanten gebruiken afbeeldingen van verschillende grootten en indelingen op hun website of voor distributie aan zakelijke partners. Aangezien elke uitvoering de afdruk van het middel in de opslagplaats vergroot, raadt Adobe u aan deze functie zorgvuldig te gebruiken. Om de hoeveelheid bronnen te verminderen die nodig is om afbeeldingen te verwerken en op te slaan, kunt u deze afbeeldingen tijdens runtime genereren in plaats van als uitvoeringen tijdens het opnemen.

Vele klanten van Plaatsen voeren een beeldservlet uit die resizes en teelten beelden op het ogenblik zij worden gevraagd, wat extra lading aan de publicatieinstantie oplegt. Maar zolang deze afbeeldingen in het cachegeheugen kunnen worden opgeslagen, kan de uitdaging worden beperkt.

Een andere manier is om Dynamic Media Classic-technologie te gebruiken om beeldmanipulatie volledig uit te schakelen. Bovendien kunt u Brand Portal implementeren die niet alleen taken voor het genereren van vertoningen overneemt van de [!DNL Experience Manager] infrastructuur, maar ook de volledige publicatielaag.

#### ImageMagick {#imagemagick}

Als u de DAM Update Asset-workflow aanpast om uitvoeringen te genereren met ImageMagick, raadt Adobe u aan het bestand policy.xml aan te passen op */etc/ImageMagick/*. Standaard gebruikt ImageMagick de volledige beschikbare schijfruimte op het volume van het besturingssysteem en het beschikbare geheugen. Breng de volgende configuratiewijzigingen aan in de `policymap` sectie van policy.xml om deze middelen te beperken.

```xml
<policymap>
  <!-- <policy domain="system" name="precision" value="6"/> -->
  <policy domain="resource" name="temporary-path" value="/ephemeral0/imagemagick_tmp"/>
  <policy domain="resource" name="memory" value="1000MiB"/>
  <policy domain="resource" name="map" value="1000MiB"/>
  <!-- <policy domain="resource" name="area" value="1gb"/> -->
  <policy domain="resource" name="disk" value="10000MiB"/>
  <!-- <policy domain="resource" name="file" value="768"/> -->
  <policy domain="resource" name="thread" value="1"/>
  <policy domain="resource" name="throttle" value="50"/>
  <!-- <policy domain="resource" name="time" value="3600"/> -->
</policymap>
```

Stel bovendien het pad in naar de tijdelijke map van ImageMagick in het dialoogvenster *configure.xml* bestand (of door de omgevingsvariabele in te stellen `MAGIC_TEMPORARY_PATH`) naar een schijfpartitie met voldoende ruimte en IOPS.

>[!CAUTION]
>
>Een fout-configuratie kan uw server onstabiel maken als ImageMagick alle beschikbare schijfruimte gebruikt. De beleidswijzigingen die vereist zijn om grote bestanden te verwerken met ImageMagick kunnen van invloed zijn op de [!DNL Experience Manager] prestaties. Zie voor meer informatie [ImageMagick installeren en configureren](best-practices-for-imagemagick.md).

>[!NOTE]
>
>The ImageMagick `policy.xml` en `configure.xml` bestanden zijn te vinden onder `/usr/lib64/ImageMagick-*/config/` in plaats van `/etc/ImageMagick/`. Zie [ImageMagick-documentatie](https://www.imagemagick.org/script/resources.php) voor meer informatie over de locaties van het configuratiebestand.

Als u [!DNL Experience Manager] kunt u via Adobe Managed Services (AMS) contact opnemen met de klantenondersteuning van Adobe als u van plan bent een groot aantal grote PSD- of PSB-bestanden te verwerken. Experience Manager verwerkt PSB-bestanden met zeer hoge resolutie die groter zijn dan 30000 x 23000 pixels mogelijk niet.

<!-- 

#### Sub-asset generation and page extraction {#sub-asset-generation-and-page-extraction}

During asset uploads, AEM's workflow creates a separate asset for each page in PDF and Office documents. Each of these pages is an asset by itself, which consumes additional disk space, requires versioning and additional workflow processing. If you do not require separate pages, disable Sub Asset Generation and Page Extraction.

To disable Sub Asset generation, do the following:

1. Open the **[!UICONTROL Workflow Console]** tool by going to */libs/cq/workflow/content/console.html*

1. Select the **[!UICONTROL Models]** tab
1. Double click the **[!UICONTROL DAM Update Asset]** workflow model
1. Delete **[!UICONTROL Process Sub Asset]** step from **[!UICONTROL DAM Update Asset]** workflow model.

1. Click on **[!UICONTROL Save]**

To disable Page Extraction:

1. Open the **[!UICONTROL Workflow Console]** tool by going to */libs/cq/workflow/content/console.html*

1. Select the **[!UICONTROL Launchers]** tab
1. Select a launcher that launches **[!UICONTROL DAM Parse Word Documents]** workflow model 
1. Click **[!UICONTROL Edit]**
1. Select **[!UICONTROL Disable]**
1. Click **[!UICONTROL OK]**
1. Repeat steps 3-6 for other launcher items that use **DAM Parse Word Documents **workflow model 

-->

<!--
# Sub-asset generation and page extraction {#sub-asset-generation-and-page-extraction}

>[!CAUTION]
>
>AEM 6.4 has reached the end of extended support and this documentation is no longer updated. For further details, see our [technical support periods](https://helpx.adobe.com/support/programs/eol-matrix.html). Find the supported versions [here](https://experienceleague.adobe.com/docs/).

During asset uploads, AEM's workflow creates a separate asset for each page in PDF and Office documents. Each of these pages is an asset by itself, which consumes additional disk space, requires versioning and additional workflow processing. If you do not require separate pages, disable Sub Asset Generation and Page Extraction.

To disable Sub Asset generation, do the following:

1. Open the **[!UICONTROL Workflow Console]** tool by going to */libs/cq/workflow/content/console.html*

1. Select the **[!UICONTROL Models]** tab
1. Double click the **[!UICONTROL DAM Update Asset]** workflow model
1. Delete **[!UICONTROL Process Sub Asset]** step from **[!UICONTROL DAM Update Asset]** workflow model.

1. Click on **[!UICONTROL Save]**

To disable Page Extraction:

1. Open the **[!UICONTROL Workflow Console]** tool by going to */libs/cq/workflow/content/console.html*

1. Select the **[!UICONTROL Launchers]** tab
1. Select a launcher that launches **[!UICONTROL DAM Parse Word Documents]** workflow model.
1. Click **[!UICONTROL Edit]**
1. Select **[!UICONTROL Disable]**
1. Click **[!UICONTROL OK]**
1. Repeat steps 3-6 for other launcher items that use **DAM Parse Word Documents** workflow model.
-->

### XMP {#xmp-writeback}

XMP terugschrijven werkt het oorspronkelijke element bij wanneer metagegevens worden gewijzigd in AEM. Dit resulteert in het volgende:

* Het element zelf wordt gewijzigd
* Er wordt een versie van het element gemaakt
* DAM Update-element wordt uitgevoerd op het element

De vermelde resultaten verbruiken aanzienlijke middelen. Daarom beveelt Adobe aan [XMP terugdraaien uitschakelen](https://helpx.adobe.com/experience-manager/kb/disable-xmp-writeback.html), indien dit niet vereist is.

Het invoeren van een grote hoeveelheid meta-gegevens kan in middel-intensieve XMP terugzetactiviteit resulteren als de loopwerkstroomvlag wordt gecontroleerd. Plan zo&#39;n import tijdens het gebruik van een slanke server, zodat de prestaties voor andere gebruikers niet worden beïnvloed.

## Replicatie {#replication}

Bij het repliceren van activa aan een groot aantal publiceer instanties, bijvoorbeeld in een implementatie van Plaatsen, adviseert Adobe u kettingreplicatie te gebruiken. In dit geval dupliceert de auteurinstantie naar één enkel publicatiegeval dat beurtelings aan andere publiceert instanties herhaalt, die de auteursinstantie vrijmaken.

### Kettingreplicatie configureren {#configure-chain-replication}

1. Bepaal op welke publicatie-instantie u de replicaties wilt koppelen
1. Op die publicatieinstantie voeg replicatieagenten toe die aan andere publicatieinstanties richten
1. Op elk van die replicatieagenten, laat toe **[!UICONTROL On Receive]** op de **[!UICONTROL Triggers]** tab

>[!NOTE]
>
>Adobe beveelt geen automatische activering van elementen aan. Indien nodig raadt Adobe u echter aan dit als de laatste stap in een workflow te doen, meestal DAM Update Asset.

## Indexen zoeken {#search-indexes}

Zorg ervoor u de recentste de dienstpakken en op prestaties betrekking hebbende hotfixes uitvoert aangezien zij vaak updates aan systeemindexen omvatten. Zie [Tips voor afstemmen van prestaties | 6,x](https://helpx.adobe.com/experience-manager/kb/performance-tuning-tips.html) voor bepaalde indexoptimalisaties die kunnen worden toegepast, afhankelijk van uw versie van AEM.

Maak aangepaste indexen voor query&#39;s die u vaak uitvoert. Zie voor meer informatie [methodologie voor het analyseren van trage query&#39;s](https://aemfaq.blogspot.com/2014/08/oak-query-log-file-analyzer-tool.html) en [aangepaste indexen maken](/help/sites-deploying/queries-and-indexing.md). Voor extra inzichten rond vraag en index beste praktijken, zie [Beste praktijken voor Vragen en het Indexeren](/help/sites-deploying/best-practices-for-queries-and-indexing.md).

### Lucene-indexconfiguraties {#lucene-index-configurations}

Sommige optimalisaties kunnen worden uitgevoerd op de indexconfiguraties van de eik die kunnen helpen [!DNL Experience Manager] Prestaties van elementen:

Werk de configuratie van LuceneIndexProvider bij:

1. Ga naar /system/console/configMgrorg.apache.jackrabbit.oak.plugins.index.lucene.LuceneIndexProviderService
1. Inschakelen **[!UICONTROL CopyOnRead , CopyOnWrite , and Prefetch Index Files]** in versies ouder dan [!DNL Experience Manager] 6.2 Deze waarden zijn standaard ingeschakeld in [!DNL Experience Manager] 6.2 en latere versies.

Indexconfiguraties bijwerken om de herindexatietijd te verbeteren:

1. CRXDe /crx/de/index.jsp openen en aanmelden als beheerder
1. Bladeren naar /ak:index/lucene
1. Een tekenreeks toevoegen[] eigenschap benoemd **[!UICONTROL excludedPaths]** met waarden &quot;/var&quot;, &quot;/etc/workflow/instances&quot; en &quot;/etc/replication&quot;
1. Blader naar /oak:index/damAssetLucene
1. Een tekenreeks toevoegen[] eigenschap benoemd **[!UICONTROL includedPaths]** met één waarde &quot;/content/dam&quot;
1. Opslaan

(Alleen AEM6.1 en 6.2) Werk de index ntBaseLucene bij om de prestaties van het verwijderen en verplaatsen van elementen te verbeteren:

1. Bladeren naar */ak:index/ntBaseLucene/indexRules/nt:base/properties*
1. Twee nt:niet-gestructureerde knooppunten toevoegen **[!UICONTROL slingResource]** en **[!UICONTROL damResolvedPath]** krachtens */ak:index/ntBaseLucene/indexRules/nt:base/properties*
1. Stel de eigenschappen hieronder op de knooppunten in (waar ordered en propertyIndex-eigenschappen van het type zijn *Boolean*:

   slingResource

   name=&quot;sling:resource&quot;

   ordered=false

   propertyIndex= true

   type=&quot;String&quot;

   damResolvedPath

   name=&quot;dam:resolvedPath&quot;

   ordered=false

   propertyIndex=true

   type=&quot;String&quot;

1. Stel de eigenschap in op het knooppunt /oak:index/ntBaseLucene `reindex=true`
1. Klik op **[!UICONTROL Save All]**
1. Controleer error.log om te zien wanneer het indexeren wordt voltooid:

   Indexering voltooid voor indexen: [/oak:index/ntBaseLucene]

1. U kunt ook zien dat het indexeren door de /oak:index/ntBaseLucene knoop in CRXDe te verfrissen wordt voltooid aangezien het herindexbezit aan vals zou terugkeren
1. Als het indexeren is voltooid, gaat u terug naar CRXDe en stelt u de optie **[!UICONTROL type]** eigenschap voor uitgeschakeld op deze twee indexen

   * */oak:index/slingResource*
   * */oak:index/damResolvedPath*

1. Klik op **[!UICONTROL Save All]**

Lucene-tekstextractie uitschakelen:

Als uw gebruikers niet de inhoud van activa hoeven te kunnen zoeken, bijvoorbeeld, zoekend de tekst in de documenten van de PDF, dan kunt u indexprestaties verbeteren door deze eigenschap onbruikbaar te maken.

1. Ga naar de [!DNL Experience Manager] pakketbeheer /crx/packmgr/index.jsp
1. Upload en installeer het onderstaande pakket

[Bestand ophalen](assets/disable_indexingbinarytextextraction-10.zip)

### Totaal raden {#guess-total}

Gebruik bij het maken van query&#39;s die grote resultaatsets genereren de opdracht `guessTotal` om te voorkomen dat er veel geheugen wordt gebruikt wanneer u deze uitvoert.

## Bekende problemen {#known-issues}

### Grote bestanden {#large-files}

Er zijn twee belangrijke bekende problemen met betrekking tot grote bestanden in AEM. Wanneer de dossiers grootten groter dan 2 GB bereiken, kan de koude reserve synchronisatie in een uit-van-geheugensituatie lopen. In sommige gevallen wordt de stand-bysynchronisatie niet uitgevoerd. In andere gevallen loopt de primaire instantie vast. Dit scenario is van toepassing op alle bestanden in [!DNL Experience Manager] die groter is dan 2 GB, inclusief inhoudspakketten.

Op dezelfde manier kan het enige tijd duren voordat het bestand, wanneer bestanden een grootte van 2 GB bereiken terwijl een gedeelde S3-datastore wordt gebruikt, volledig doorloopt van de cache naar het bestandssysteem. Dientengevolge, wanneer het gebruiken van binair-minder replicatie, is het mogelijk dat de binaire gegevens niet kunnen zijn voortgeduurd alvorens de replicatie voltooit. Deze situatie kan tot problemen leiden, vooral als de beschikbaarheid van gegevens belangrijk is, bijvoorbeeld in offloadscenario&#39;s.

## Prestaties testen {#performance-testing}

Voor elke [!DNL Experience Manager] de implementatie, een prestatietestregeling opzetten die knelpunten snel kan opsporen en oplossen. Hier volgen enkele belangrijke aandachtsgebieden.

### Netwerktests {#network-testing}

Voor alle kwesties van netwerkprestaties van de klant, voer de volgende taken uit:

* De netwerkprestaties van de test van binnen het klantennetwerk
* De netwerkprestaties van de test van binnen het netwerk van Adobe. Voor klanten van AMS, werk met uw CSE om van binnen het netwerk van Adobe te testen.
* De netwerkprestaties van de test van een ander toegangspunt
* Door een hulpmiddel van de netwerkbenchmark te gebruiken
* Testen tegen de verzender

### [!DNL Experience Manager] instantie testen {#aem-instance-testing}

Om latentie te minimaliseren en een hoge doorvoer te bereiken via efficiënt CPU-gebruik en delen van de belasting, kunt u de prestaties van uw [!DNL Experience Manager] regelmatig. Met name:

* Belastingtests uitvoeren tegen de [!DNL Experience Manager] instance
* Uploadprestaties en reactiesnelheid van de gebruikersinterface bewaken

## [!DNL Experience Manager] Checklist voor prestaties van middelen {#aem-assets-performance-checklist}

* Schakel HTTPS in om rondom eventuele bedrijfs-HTTP-verkeersfragmenten te komen.
* Gebruik een bekabelde verbinding voor het uploaden van zware middelen.
* Stel optimale JVM-parameters in.
* Configureer een FileSystem DataStore of een S3 DataStore.
* Genereren van subelementen uitschakelen. Als deze optie is ingeschakeld, maakt AEM workflow een afzonderlijk element voor elke pagina in een element van meerdere pagina&#39;s. Elk van deze pagina&#39;s is een individueel middel dat extra schijfruimte verbruikt, versioning, en extra werkschemaverwerking vereist. Als u geen afzonderlijke pagina&#39;s nodig hebt, schakelt u het genereren van subelementen en het uitnemen van pagina&#39;s uit.
* Schakel tijdelijke workflows in.
* Stem de wachtrijen voor de Granite-workflow af om gelijktijdige taken te beperken.
* Vorm ImageMagick om middelconsumptie te beperken.
* Verwijder overbodige stappen uit de DAM Update Asset-workflow.
* Vorm werkschema en versie het zuiveren.
* Optimaliseer de configuratie van de index van Lucene.
* Optimaliseer indexen met de recentste de dienstpakken en hotfixes. Raadpleeg de klantenondersteuning van Adobe voor eventuele extra indexoptimalisaties die beschikbaar zijn.
* Gebruiken `guessTotal` om queryprestaties te optimaliseren.
* Als u [!DNL Experience Manager] om dossiertypes van de inhoud van de dossiers (door te vormen [!UICONTROL Day CQ DAM Mime Type Service] in de [!UICONTROL [!DNL Experience Manager] Web Console]), veel bestanden bulksgewijs uploaden tijdens niet-piekuren omdat de bewerking bronintensief is.
