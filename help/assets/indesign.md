---
title: AEM Assets integreren met Adobe InDesign Server
description: Leer hoe u AEM Assets kunt integreren met InDesign Server.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 77c62a8f2ca50f8aaff556a6848fabaee71017ce
workflow-type: tm+mt
source-wordcount: '1658'
ht-degree: 1%

---


# AEM Assets integreren met Adobe InDesign Server {#integrating-aem-assets-with-indesign-server}

Adobe Experience Manager (AEM) Assets gebruikt:

* Een proxy om het laden van bepaalde verwerkingstaken te verdelen. Een volmacht is een instantie AEM die met een volmachtsarbeider communiceert om een specifieke taak te vervullen, en andere instanties AEM om de resultaten te leveren.
* Een proxyworker om een specifieke taak te definiëren en te beheren.

Deze kunnen betrekking hebben op een groot aantal verschillende taken; bijvoorbeeld met een Adobe InDesign Server bestanden verwerken.

Voor het volledig uploaden van bestanden naar AEM Assets die u met Adobe InDesign hebt gemaakt, wordt een proxy gebruikt. Dit gebruikt een volmachtsarbeider om met de Server van Adobe InDesign te communiceren, waar de [manuscripten](https://www.adobe.com/devnet/indesign/documentation.html#idscripting) worden in werking gesteld om meta-gegevens te halen en diverse vertoningen voor AEM Assets te produceren. De proxyworker maakt de tweewegscommunicatie mogelijk tussen de InDesign-server en de AEM-instantie(s) in een cloudconfiguratie.

>[!NOTE]
>
>Adobe InDesign wordt geleverd als twee producten:
>
>* [InDesign](https://www.adobe.com/products/indesign.html)\
   >  Zo kunt u paginalay-outs ontwerpen voor afdrukken en/of digitale distributie.
   >
   >
* [InDesign Server](https://www.adobe.com/products/indesignserver.html)\
   >  Met deze engine kunt u programmatisch geautomatiseerde documenten maken op basis van wat u met InDesign hebt gemaakt. Het werkt als dienst die een interface aan zijn motor [ExtendScript](https://www.adobe.com/devnet/scripting.html) aanbiedt.\
   >  De scripts worden geschreven in ExtendScript, wat vergelijkbaar is met javascript. Zie [https://www.adobe.com/devnet/indesign/documentation.html#idscripting](https://www.adobe.com/devnet/indesign/documentation.html#idscripting)voor meer informatie over InDesign-scripts.
>



## Hoe de extractie werkt {#how-the-extraction-works}

De InDesign-server kan worden geïntegreerd met AEM Assets, zodat bestanden die zijn gemaakt met InDesign ( `.indd`) kunnen worden geüpload, vertoningen kunnen worden gegenereerd, *alle* media kunnen worden uitgepakt (bijvoorbeeld video) en opgeslagen als elementen:

>[!NOTE]
>
>In eerdere versies van AEM konden XMP en de miniatuur worden geëxtraheerd. Nu kunnen alle media worden geëxtraheerd.

1. Upload uw `.indd` bestand naar AEM Assets.
1. Een framework verzendt opdrachtscripts naar de InDesign-server via SOAP (Simple Object Access Protocol).

   Dit opdrachtscript:

   * Haal het `.indd` bestand op.
   * InDesign Server-opdrachten uitvoeren:

      * De structuur, de tekst en alle mediabestanden worden geëxtraheerd.
      * Er worden PDF- en JPG-uitvoeringen gegenereerd.
      * HTML- en IDML-uitvoeringen worden gegenereerd.
   * Plaats de resulterende bestanden terug naar AEM Assets.
   >[!NOTE]
   >
   >IDML is een op XML gebaseerde indeling die *alles* in het InDesign-bestand rendert. Het wordt opgeslagen als gecomprimeerd pakket gebruikend [compressie Zip](https://www.techterms.com/definition/zip) .
   >
   >Zie [Adobe InDesign Interchange Formats INX en IDML](http://www.peachpit.com/articles/article.aspx?p=1381880&amp;seqNum=8) voor meer informatie.

   >[!CAUTION]
   >
   >Als InDesign Server niet is geïnstalleerd of niet is geconfigureerd, kunt u nog steeds een `.indd` bestand uploaden naar AEM. De gegenereerde uitvoeringen zijn echter beperkt tot `png` en `jpeg`, u kunt geen paginauitvoeringen genereren `html`, `idml` of de pagina-uitvoeringen.

1. Na de extractie en uitvoering:

   * De structuur wordt gerepliceerd naar een `cq:Page` (type vertoning).
   * De geëxtraheerde tekst en bestanden worden opgeslagen in AEM Assets.
   * Alle uitvoeringen worden opgeslagen in AEM Assets, in het element zelf.

## De InDesign-server integreren met AEM {#integrating-the-indesign-server-with-aem}

Als u de InDesign-server wilt integreren voor gebruik met AEM Assets en nadat u de proxy hebt geconfigureerd, moet u:

1. [Installeer de InDesign-server](#installing-the-indesign-server).
1. Indien nodig, [vorm het Werkschema](#configuring-the-aem-assets-workflow)van AEM Assets.

   Dit is alleen nodig als de standaardwaarden niet geschikt zijn voor uw instantie.

1. Configureer een [proxyworker voor de InDesign-server](#configuring-the-proxy-worker-for-indesign-server).

### De InDesign-server installeren {#installing-the-indesign-server}

U installeert en start de InDesign-server voor gebruik met AEM:

1. Download en installeer Adobe InDesign Server.

   >[!NOTE]
   >
   >InDesign Server (CS6 en hoger).

1. Indien nodig kunt u de configuratie van uw InDesign Server-instantie aanpassen.

1. Start de server vanaf de opdrachtregel:

   `<*ids-installation-dir*>/InDesignServer.com -port 8080`

   Hierdoor start u de server met de SOAP-insteekmodule die luistert op poort 8080. Alle logboekberichten en output worden geschreven direct aan het bevelvenster.

   >[!NOTE]
   >
   >Als u de outputberichten aan een dossier wilt bewaren dan gebruik redirection; bijvoorbeeld onder Windows:
   >
   >`<ids-installation-dir>/InDesignServer.com -port 8080 > ~/temp/INDD-logfile.txt 2>&1`

### De AEM Assets-workflow configureren {#configuring-the-aem-assets-workflow}

AEM Assets has a pre-configured workflow **DAM Update Asset**, that has several process steps specifically for InDesign:

* [Media extraheren](#media-extraction)
* [Pagina uitnemen](#page-extraction)

Dit werkschema is opstelling met standaardwaarden die voor uw opstelling op de diverse auteursinstanties (dit is een standaardwerkschema, zodat is de verdere informatie beschikbaar onder het [Uitgeven van een Werkschema](/help/sites-developing/workflows-models.md#configuring-a-workflow-step)) kunnen worden aangepast. Als u de standaardwaarden (met inbegrip van de haven van de ZEEP) gebruikt, dan is geen configuratie nodig.

Na de installatie wordt door het uploaden van InDesign-bestanden naar AEM Assets (op een van de gebruikelijke manieren) de workflow geactiveerd die nodig is om het element te verwerken en de verschillende uitvoeringen voor te bereiden. Test uw configuratie door een `.indd` bestand te uploaden naar AEM Assets om te bevestigen dat de verschillende uitvoeringen die onder IDS zijn gemaakt, worden weergegeven `<*your_asset*>.indd/Renditions`

#### Media extraheren {#media-extraction}

Deze stap bepaalt de extractie van media uit het `.indd` bestand.

U kunt het **[!UICONTROL Arguments]** tabblad van de **[!UICONTROL Media Extraction]** stap aanpassen.

![Argumenten voor het uitnemen van media en scriptpaden](assets/media_extraction_arguments_scripts.png)

Argumenten voor het uitnemen van media en scriptpaden

* **ExtendScript-bibliotheek**: Dit is een eenvoudige http-methodebibliotheek, vereist door de andere scripts.

* **Scripts** uitbreiden: Hier kunt u verschillende scriptcombinaties opgeven. Als u uw eigen scripts op de InDesign-server wilt uitvoeren, slaat u de scripts op `/apps/settings/dam/indesign/scripts`.

   Zie [https://www.adobe.com/devnet/indesign/documentation.html#idscripting](https://www.adobe.com/devnet/indesign/documentation.html#idscripting)voor meer informatie over InDesign-scripts.

>[!CAUTION]
>
>Wijzig de ExtendScript-bibliotheek niet. De bibliotheek biedt de HTTP-functionaliteit die nodig is voor communicatie met Sling. Met deze instelling geeft u de bibliotheek op die naar de Adobe InDesign-server moet worden verzonden voor gebruik.

Het `ThumbnailExport.jsx` script dat wordt uitgevoerd door de workflowstap Media Extraction, genereert een miniatuuruitvoering in de JPG-indeling. Deze vertoning wordt gebruikt door de werkstroomstap Miniaturen verwerken om de statische uitvoeringen te genereren die door AEM worden vereist.

U kunt de workflowstap Miniaturen verwerken zodanig configureren dat statische uitvoeringen van verschillende grootten worden gegenereerd. Zorg ervoor dat u de standaardinstellingen niet verwijdert, omdat deze vereist zijn door de gebruikersinterface van de AEM Assets. Tot slot verwijdert de workflowstap Voorvertoning afbeelding verwijderen de miniatuuruitvoering .jpg, omdat deze niet langer nodig is.

#### Pagina uitnemen {#page-extraction}

Hiermee maakt u een AEM-pagina van de geëxtraheerde elementen. Een extractiemanager wordt gebruikt om gegevens uit een vertoning (momenteel HTML of IDML) te halen. Deze gegevens worden vervolgens gebruikt om een pagina te maken met de PageBuilder.

To customize, you can edit the **[!UICONTROL Arguments]** tab of the **Page Extraction** step.

![chlimage_1-289](assets/chlimage_1-289.png)

* **Handler voor** uitpakken van pagina: Selecteer in de vervolgkeuzelijst de handler die u wilt gebruiken. Een extractiehandler werkt op een specifieke uitvoering, die door een verwante `RenditionPicker` (zie de `ExtractionHandler`-API) wordt gekozen.
Standaard is de IDML-exporthandler beschikbaar. Het werkt op de vertoning die in de stap MediaExtract wordt geproduceerd. `IDML`

* **Paginanaam**: Geef de naam op die u aan de resulterende pagina wilt toewijzen. Als deze optie leeg blijft, is de naam &quot;page&quot; (of een derivaat als &quot;page&quot; al bestaat).

* **Paginatitel**: Geef de titel op die u aan de resulterende pagina wilt toewijzen.

* **Basispad** pagina: Het pad naar de hoofdlocatie van de resulterende pagina. Indien leeg gelaten, wordt het knooppunt gebruikt dat de uitvoeringen van het element bevat.

* **Paginasjabloon**: De sjabloon die moet worden gebruikt bij het genereren van de resulterende pagina.

* **Paginaontwerp**: Het paginaontwerp dat moet worden gebruikt bij het genereren van de resulterende pagina.

### De proxyworker voor InDesign Server configureren {#configuring-the-proxy-worker-for-indesign-server}

>[!NOTE]
>
>De worker bevindt zich op de proxyinstantie.

1. Vouw in het linkerdeelvenster van de gereedschapsconsole **[!UICONTROL Cloud Services Configurations]** uit. Vouw vervolgens uit **[!UICONTROL Cloud Proxy Configuration]**.

1. Dubbelklik op het bestand **[!UICONTROL IDS worker]** dat u wilt openen voor configuratie.

1. Klik **[!UICONTROL Edit]** om het configuratiedialoogvenster te openen en de vereiste instellingen te definiëren:

   ![proxy_disworkerconfig](assets/proxy_idsworkerconfig.png)

   * **IDS-pool**: Het (de) eindpunt(en) van de ZEEP die voor het communiceren met de Server InDesign moeten worden gebruikt. U kunt items toevoegen, verwijderen en bestellen.

1. Klik **[!UICONTROL OK]** om op te slaan.

### Het vormen van Dag CQ Verbinding Externalzer  {#configuring-day-cq-link-externalizer}

Als de InDesign-server en AEM op verschillende hosts worden uitgevoerd of als deze toepassingen niet op de standaardpoorten worden uitgevoerd, configureert u **Day CQ Link External** om de hostnaam, poort en inhoudsweg voor de InDesign-server in te stellen.

1. Open Configuration Manager via de URL `https://[AEM_server]:[port]/system/console/configMgr`.
1. Locate the configuration **[!UICONTROL Day CQ Link Externalizer]**, and click the **[!UICONTROL Edit]** icon to open it.
1. Geef de hostnaam en het contextpad voor de InDesign-server op en klik op **[!UICONTROL Save]**.

   ![chlimage_1-290](assets/chlimage_1-290.png)

### Parallelle taakverwerking inschakelen voor InDesign Server(s) {#enabling-parallel-job-processing-for-indesign-server-s}

U kunt nu parallelle taakverwerking inschakelen voor IDS.

Eerst moet u bepalen hoeveel parallelle taken ( `x`) een InDesign-server maximaal kan verwerken:

* Op één multiprocessorcomputer is het maximumaantal parallelle taken (x) dat een InDesign-server kan verwerken één minder dan het aantal processors met IDS.
* Wanneer u IDS op veelvoudige machines in werking stelt moet u het totale aantal beschikbare bewerkers (dat wil zeggen op alle machines) tellen dan het totale aantal machines aftrekken.

Om het aantal parallelle banen te vormen IDS:

1. Open het **[!UICONTROL Configurations]** tabblad van de Felix-console; bijvoorbeeld:

   `http://localhost:4502/system/console/configMgr`

1. Selecteer de IDS verwerkingsrij onder:

   `Apache Sling Job Queue Configuration`

1. Set:

   * **[!UICONTROL Type]** - `Parallel`
   * **[!UICONTROL Maximum Parallel Jobs]** - `<*x*>` (zoals hierboven berekend)

1. Sla deze wijzigingen op.
1. Schakel het `enable.multisession.name` selectievakje onder `com.day.cq.dam.ids.impl.IDSJobProcessor.name configuration`in als u ondersteuning voor meerdere sessies wilt inschakelen voor Adobe CS6 en hoger.
1. Creeer een [pool van de arbeiders van &lt; `*x*>` IDS door de eindpunten van de ZEEP aan de configuratie](#configuring-the-proxy-worker-for-indesign-server)van de Arbeider toe te voegen IDS.

   Als er meerdere computers zijn waarop InDesign-servers worden uitgevoerd, voegt u SOAP-eindpunten (aantal processors per computer -1) toe voor elke computer.

   >[!NOTE]
   >
   >Wanneer u werkt met een pool met workers, kunt u een geblokkeerde lijst met IDS-workers inschakelen.
   >
   >Om dit te doen, laat checkbox &quot;enable.retry.name&quot;, onder de `com.day.cq.dam.ids.impl.IDSJobProcessor.name` configuratie toe, die IDS baanterugwinning toelaat.
   >
   >Ook, onder de `com.day.cq.dam.ids.impl.IDSPoolImpl.name` configuratie, plaats een positieve waarde voor `max.errors.to.blacklist` parameter die aantal baanterugwinnen alvorens IDS van de lijst van baanmanagers bepaalt
   >
   >De IDS-worker wordt standaard opnieuw gevalideerd nadat de configureerbare (`retry.interval.to.whitelist.name`) tijd in minuten is verstreken. Als de worker online wordt gevonden, wordt deze verwijderd uit de geblokkeerde lijst.

<!-- TBD: Make updates to configurations for allow and block list after product updates are done.
-->

## Ondersteuning inschakelen voor Adobe InDesign-server 10.0 of hoger {#enabling-support-for-indesign-server-or-higher}

Voer voor InDesign Server 10.0 of hoger de volgende stappen uit om ondersteuning voor meerdere sessies in te schakelen.

1. Open de Manager van de Configuratie van uw [!DNL Assets] instantie `https://[aem_server]:[port]/system/console/configMgr`.
1. Bewerk de configuratie `com.day.cq.dam.ids.impl.IDSJobProcessor.name`.
1. Select **[!UICONTROL ids.cc.enable]** option, and click **[!UICONTROL Save]**.

>[!NOTE]
>
>Voor [!DNL InDesign Server] integratie met [!DNL Assets], gebruik een multi-core bewerker omdat de zittingssteuneigenschap noodzakelijk voor de integratie niet op single-core systemen wordt gesteund.

## Inloggegevens van Experience Manager configureren {#configure-aem-credentials}

U kunt de standaardbeheerdersreferenties (gebruikersnaam en wachtwoord) wijzigen voor toegang tot de InDesign-server vanuit uw AEM-instantie zonder de integratie met de Adobe InDesign-server te verbreken.

1. Ga naar `/etc/cloudservices/proxy.html`.
1. Geef in het dialoogvenster de nieuwe gebruikersnaam en het nieuwe wachtwoord op.
1. Sla de referenties op.
