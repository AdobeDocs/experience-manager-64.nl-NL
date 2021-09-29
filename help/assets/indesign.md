---
title: Integreer [!DNL Experience Manager] Middelen met Adobe InDesign Server
description: Leer hoe te om [!DNL Experience Manager] Middelen met InDesign Server te integreren.
contentOwner: AG
feature: Publishing
role: Admin
exl-id: d80562f7-071c-460a-9c68-65f48d36fbd9
source-git-commit: cc9b6d147a93688e5f96620d50f8fc8b002e2d0d
workflow-type: tm+mt
source-wordcount: '1646'
ht-degree: 1%

---

# Middelen integreren met Adobe InDesign Server {#integrating-aem-assets-with-indesign-server}

Adobe Experience Manager Assets gebruikt:

* Een proxy om het laden van bepaalde verwerkingstaken te verdelen. Een volmacht is een [!DNL Experience Manager] instantie die met een volmachtsarbeider communiceert om een specifieke taak te vervullen, en andere [!DNL Experience Manager] instanties om de resultaten te leveren.
* Een proxyworker om een specifieke taak te definiëren en te beheren.

Deze kunnen betrekking hebben op een groot aantal verschillende taken; bijvoorbeeld met een Adobe InDesign Server bestanden verwerken.

Als u bestanden volledig wilt uploaden naar [!DNL Experience Manager] elementen die u met Adobe InDesign hebt gemaakt, wordt een proxy gebruikt. Dit gebruikt een volmachtsarbeider om met Adobe InDesign Server te communiceren, waar [manuscripten](https://www.adobe.com/devnet/indesign/documentation.html#idscripting) worden in werking gesteld om meta-gegevens te halen en diverse vertoningen voor [!DNL Experience Manager] Activa te produceren. De volmachtsarbeider laat de bidirectionele communicatie tussen de InDesign Server en [!DNL Experience Manager] instantie(s) in een wolkenconfiguratie toe.

>[!NOTE]
>
>Adobe InDesign bestaat uit twee producten:
>
>* [InDesign](https://www.adobe.com/products/indesign.html)\
   >  Zo kunt u paginalay-outs ontwerpen voor afdrukken en/of digitale distributie.
>
>* [InDesign Server](https://www.adobe.com/products/indesignserver.html)\
   >  Met deze engine kunt u programmatisch geautomatiseerde documenten maken op basis van wat u met InDesign hebt gemaakt. Het werkt als dienst die een interface aan zijn [ExtendScript](https://www.adobe.com/devnet/scripting.html) motor aanbiedt.\
   >  De scripts zijn geschreven in ExtendScript en zijn vergelijkbaar met JavaScript. Zie [https://www.adobe.com/devnet/indesign/documentation.html#idscripting](https://www.adobe.com/devnet/indesign/documentation.html#idscripting) voor informatie over Adobe InDesign-scripts.

>


## Hoe de extractie werkt {#how-the-extraction-works}

De InDesign Server kan met Elementen worden geïntegreerd [!DNL Experience Manager] zodat de dossiers met InDesign ( `.indd`) worden gecreeerd kunnen worden geupload, geproduceerde vertoningen, *allen* (bijvoorbeeld, video) worden gehaald en als activa worden opgeslagen:

>[!NOTE]
>
>In eerdere versies van [!DNL Experience Manager] konden XMP en de miniatuur worden opgehaald. Alle media kunnen nu worden uitgepakt.

1. Upload uw `.indd`-bestand naar [!DNL Experience Manager]-elementen.
1. Een framework verzendt opdrachtscripts naar de InDesign Server via SOAP (Simple Object Access Protocol).

   Dit opdrachtscript:

   * Haal het `.indd` bestand op.
   * InDesign Server-opdrachten uitvoeren:

      * De structuur, de tekst en alle mediabestanden worden geëxtraheerd.
      * Er worden PDF- en JPG-uitvoeringen gegenereerd.
      * HTML- en IDML-uitvoeringen worden gegenereerd.
   * Plaats de resulterende bestanden weer op [!DNL Experience Manager] Elementen.

   >[!NOTE]
   >
   >IDML is een op XML-Gebaseerde formaat dat *alles* in het dossier van de InDesign teruggeeft. Het wordt opgeslagen als samengeperst pakket gebruikend [Zip](https://www.techterms.com/definition/zip) compressie.
   >
   >Zie [Adobe InDesign Interchange Formats INX en IDML](https://www.peachpit.com/articles/article.aspx?p=1381880&amp;seqNum=8) voor meer informatie.

   >[!CAUTION]
   >
   >Als de InDesign Server niet geïnstalleerd of niet gevormd is, dan kunt u een `.indd` dossier in [!DNL Experience Manager] nog uploaden. De gegenereerde uitvoeringen zijn echter beperkt tot `png` en `jpeg`, u kunt `html`, `idml` of de pagina-uitvoeringen niet genereren.

1. Na de extractie en uitvoering:

   * De structuur wordt gerepliceerd naar een `cq:Page` (type vertoning).
   * De geëxtraheerde tekst en bestanden worden opgeslagen in Elementen [!DNL Experience Manager].
   * Alle vertoningen worden opgeslagen in Elementen [!DNL Experience Manager], in het middel zelf.

## De InDesign Server integreren met [!DNL Experience Manager] {#integrating-the-indesign-server-with-aem}

Om de InDesign Server voor gebruik met [!DNL Experience Manager] Middelen te integreren en na het vormen van uw volmacht, moet u:

1. [Installeer de InDesign Server](#installing-the-indesign-server).
1. Indien nodig [configureer de  [!DNL Experience Manager] Assets Workflow](#configuring-the-aem-assets-workflow).

   Dit is alleen nodig als de standaardwaarden niet geschikt zijn voor uw instantie.

1. Configureer een [proxyworker voor de InDesign Server](#configuring-the-proxy-worker-for-indesign-server).

### De InDesign Server installeren {#installing-the-indesign-server}

De InDesign Server installeren en starten voor gebruik met [!DNL Experience Manager]:

1. Download en installeer de Adobe InDesign Server.

   >[!NOTE]
   >
   >InDesign Server (CS6 en hoger).

1. Indien nodig, kunt u de configuratie van uw instantie van de InDesign Server aanpassen.

1. Start de server vanaf de opdrachtregel:

   `<*ids-installation-dir*>/InDesignServer.com -port 8080`

   Hierdoor start u de server met de SOAP-insteekmodule die luistert op poort 8080. Alle logboekberichten en output worden geschreven direct aan het bevelvenster.

   >[!NOTE]
   >
   >Als u de outputberichten aan een dossier wilt bewaren dan gebruik redirection; bijvoorbeeld onder Windows:
   >
   >`<ids-installation-dir>/InDesignServer.com -port 8080 > ~/temp/INDD-logfile.txt 2>&1`

### De [!DNL Experience Manager]-middelenworkflow configureren {#configuring-the-aem-assets-workflow}

[!DNL Experience Manager] Elementen hebben een vooraf geconfigureerde workflow  **DAM Update Asset**, die verschillende processtappen bevat, met name voor InDesign:

* [Media extraheren](#media-extraction)
* [Pagina uitnemen](#page-extraction)

Dit werkschema is opstelling met standaardwaarden die voor uw opstelling op de diverse auteursinstanties (dit is een standaardwerkschema, zodat is de verdere informatie beschikbaar onder [het Uitgeven van een Werkschema](/help/sites-developing/workflows-models.md#configuring-a-workflow-step)) kunnen worden aangepast. Als u de standaardwaarden (met inbegrip van de haven van de ZEEP) gebruikt, dan is geen configuratie nodig.

Na de installatie, zal het uploaden van InDesign dossiers in [!DNL Experience Manager] Middelen (door om het even welke gebruikelijke methodes) de werkschema teweegbrengen die wordt vereist om de activa te verwerken en de diverse vertoningen voor te bereiden. Test uw configuratie door een `.indd` bestand te uploaden naar [!DNL Experience Manager] Middelen om te bevestigen dat de verschillende uitvoeringen die door IDS onder `<*your_asset*>.indd/Renditions` zijn gemaakt, worden weergegeven

#### Media extraheren {#media-extraction}

Deze stap bepaalt de extractie van media uit het `.indd`-bestand.

Als u een document wilt aanpassen, kunt u het tabblad **[!UICONTROL Arguments]** van de stap **[!UICONTROL Media Extraction]** bewerken.

![Argumenten voor het uitnemen van media en scriptpaden](assets/media_extraction_arguments_scripts.png)

Argumenten voor het uitnemen van media en scriptpaden

* **ExtendScript-bibliotheek**: Dit is een eenvoudige http-methodebibliotheek, vereist door de andere scripts.

* **Scripts** uitbreiden: Hier kunt u verschillende scriptcombinaties opgeven. Als u uw eigen manuscripten op de InDesign Server wilt worden uitgevoerd, sparen de manuscripten bij `/apps/settings/dam/indesign/scripts`.

   Zie [https://www.adobe.com/devnet/indesign/documentation.html#idscripting](https://www.adobe.com/devnet/indesign/documentation.html#idscripting) voor informatie over InDesign-scripts.

>[!CAUTION]
>
>Wijzig de ExtendScript-bibliotheek niet. De bibliotheek biedt de HTTP-functionaliteit die nodig is voor communicatie met Sling. Met deze instelling geeft u de bibliotheek op die naar de Adobe InDesign Server moet worden verzonden voor gebruik.

Met het `ThumbnailExport.jsx`-script dat wordt uitgevoerd door de workflowstap Media Extraction, wordt een miniatuuruitvoering in JPG-indeling gegenereerd. Deze vertoning wordt gebruikt door de werkstroomstap Miniaturen verwerken om de statische uitvoeringen te genereren die worden vereist door [!DNL Experience Manager].

U kunt de workflowstap Miniaturen verwerken zodanig configureren dat statische uitvoeringen van verschillende grootten worden gegenereerd. Zorg ervoor dat u de standaardinstellingen niet verwijdert, omdat deze vereist zijn door de interface [!DNL Experience Manager] Middelen. Tot slot verwijdert de workflowstap Voorvertoning afbeelding verwijderen de miniatuuruitvoering .jpg, omdat deze niet langer nodig is.

#### Pagina uitnemen {#page-extraction}

Hiermee maakt u een [!DNL Experience Manager]-pagina van de geëxtraheerde elementen. Een extractiemanager wordt gebruikt om gegevens uit een vertoning (momenteel HTML of IDML) te halen. Deze gegevens worden vervolgens gebruikt om een pagina te maken met de PageBuilder.

Als u een pagina wilt aanpassen, kunt u het tabblad **[!UICONTROL Arguments]** van de stap **Pagina-uitname** bewerken.

![chlimage_1-289](assets/chlimage_1-289.png)

* **Handler voor** uitpakken van pagina: Selecteer in de vervolgkeuzelijst de handler die u wilt gebruiken. Een extractiehandler werkt op een specifieke uitvoering, die door een verwante `RenditionPicker` (zie de `ExtractionHandler`-API) wordt gekozen.
Standaard is de IDML-exporthandler beschikbaar. Het werkt op de `IDML` vertoning die in de stap MediaExtract wordt geproduceerd.

* **Paginanaam**: Geef de naam op die u aan de resulterende pagina wilt toewijzen. Als deze optie leeg blijft, is de naam &quot;page&quot; (of een derivaat als &quot;page&quot; al bestaat).

* **Paginatitel**: Geef de titel op die u aan de resulterende pagina wilt toewijzen.

* **Basispad** pagina: Het pad naar de hoofdlocatie van de resulterende pagina. Indien leeg gelaten, wordt het knooppunt gebruikt dat de uitvoeringen van het element bevat.

* **Paginasjabloon**: De sjabloon die moet worden gebruikt bij het genereren van de resulterende pagina.

* **Paginaontwerp**: Het paginaontwerp dat moet worden gebruikt bij het genereren van de resulterende pagina.

### De proxyworker voor InDesign Server configureren {#configuring-the-proxy-worker-for-indesign-server}

>[!NOTE]
>
>De worker bevindt zich op de proxyinstantie.

1. Vouw **[!UICONTROL Cloud Services Configurations]** in het linkerdeelvenster van de gereedschapsconsole uit. Vouw vervolgens **[!UICONTROL Cloud Proxy Configuration]** uit.

1. Dubbelklik op **[!UICONTROL IDS worker]** om de configuratie te openen.

1. Klik **[!UICONTROL Edit]** om het configuratiedialoogvenster te openen en de vereiste instellingen te definiëren:

   ![proxy_disworkerconfig](assets/proxy_idsworkerconfig.png)

   * **IDS-pool**: Het (de) eindpunt(en) van de ZEEP die voor het communiceren met de InDesign Server moeten worden gebruikt. U kunt items toevoegen, verwijderen en bestellen.

1. Klik **[!UICONTROL OK]** om op te slaan.

### Het vormen van Dag CQ Verbinding Externalzer {#configuring-day-cq-link-externalizer}

Als de InDesign Server en [!DNL Experience Manager] op verschillende gastheren zijn of één of beide toepassingen niet aan standaardhavens werken, vorm **De Verbinding Externalzer van CQ van de Dag** om de gastheernaam, de haven, en de inhoudspad voor de InDesign Server te plaatsen.

1. Open Configuration Manager op de URL `https://[AEM_server]:[port]/system/console/configMgr`.
1. Zoek de configuratie **[!UICONTROL Day CQ Link Externalizer]**. Klik **[!UICONTROL Edit]** om te openen.
1. De montages van de Verbinding Externalzer helpen absolute URLs voor de [!DNL Experience Manager] plaatsing en voor [!DNL InDesign Server] tot stand brengen. Gebruik **[!UICONTROL Domains]** veld om de hostnaam en het contextpad voor [!DNL Adobe InDesign Server] op te geven. Volg de aanwijzingen op het scherm. Klik op **[!UICONTROL Save]**.

   ![Externe instellingen koppelen](assets/link-externalizer-config.png)

### Parallelle taakverwerking inschakelen voor InDesign Server {#enabling-parallel-job-processing-for-indesign-server}

U kunt nu parallelle taakverwerking inschakelen voor IDS.

Eerst moet u het maximumaantal parallelle banen ( `x`) bepalen een InDesign Server kan verwerken:

* Op één multiprocessorcomputer is het maximumaantal parallelle taken (x) dat een InDesign Server kan verwerken één minder dan het aantal processors met IDS.
* Wanneer u IDS op veelvoudige machines in werking stelt moet u het totale aantal beschikbare bewerkers (dat wil zeggen op alle machines) tellen dan het totale aantal machines aftrekken.

Om het aantal parallelle banen te vormen IDS:

1. Open het tabblad **[!UICONTROL Configurations]** van de Felix-console; bijvoorbeeld:

   `http://localhost:4502/system/console/configMgr`

1. Selecteer de IDS verwerkingsrij onder:

   `Apache Sling Job Queue Configuration`

1. Set:

   * **[!UICONTROL Type]** - `Parallel`
   * **[!UICONTROL Maximum Parallel Jobs]** -  `<*x*>` (zoals hierboven berekend)

1. Sla deze wijzigingen op.
1. Schakel het selectievakje `enable.multisession.name` onder `com.day.cq.dam.ids.impl.IDSJobProcessor.name configuration` in om de ondersteuning voor meerdere sessies voor Adobe CS6 en later in te schakelen.
1. Maak een [pool van &lt; `*x*>` IDS-workers door SOAP-eindpunten toe te voegen aan de IDS Worker-configuratie](#configuring-the-proxy-worker-for-indesign-server).

   Als er meerdere computers zijn waarop InDesign Server wordt uitgevoerd, voegt u SOAP-eindpunten (aantal processors per computer -1) toe voor elke computer.

   >[!NOTE]
   >
   >Wanneer u werkt met een groep workers, kunt u de lijst van gewezen personen van IDS-workers inschakelen.
   >
   >Om dit te doen, laat checkbox &quot;enable.retry.name&quot;, onder de `com.day.cq.dam.ids.impl.IDSJobProcessor.name` configuratie toe, die IDS baanterugwinning toelaat.
   >
   >Ook, onder de `com.day.cq.dam.ids.impl.IDSPoolImpl.name` configuratie, plaats een positieve waarde voor `max.errors.to.blacklist` parameter die aantal baanterugwinnen alvorens IDS van de lijst van baanmanagers bepaalt
   >
   >Door gebrek, na configureerbare (`retry.interval.to.whitelist.name`) tijd in notulen wordt de IDS worker opnieuw bevestigd. Als de worker online wordt gevonden, wordt deze uit de lijst van gewezen personen verwijderd.

<!-- TBD: Make updates to configurations for allow and block list after product updates are done. See CQ-4298427.
-->

## Ondersteuning inschakelen voor Adobe InDesign-server 10.0 of hoger {#enabling-support-for-indesign-server-or-higher}

Voer voor InDesign-server 10.0 of hoger de volgende stappen uit om ondersteuning voor meerdere sessies mogelijk te maken.

1. Open de Manager van de Configuratie van uw [!DNL Assets] instantie `https://[aem_server]:[port]/system/console/configMgr`.
1. Bewerk de configuratie `com.day.cq.dam.ids.impl.IDSJobProcessor.name`.
1. Selecteer **[!UICONTROL ids.cc.enable]** optie, en klik **[!UICONTROL Save]**.

>[!NOTE]
>
>Voor [!DNL InDesign Server] integratie met [!DNL Assets], gebruik een multi-core bewerker omdat de zittingssteuneigenschap noodzakelijk voor de integratie niet op single core systemen wordt gesteund.

## Referenties van Experience Manager configureren {#configure-aem-credentials}

U kunt de standaardbeheerdersreferenties (gebruikersnaam en wachtwoord) wijzigen voor toegang tot de InDesign-server vanuit uw [!DNL Experience Manager]-exemplaar zonder de integratie met de Adobe InDesign-server te verbreken.

1. Ga naar `/etc/cloudservices/proxy.html`.
1. Geef in het dialoogvenster de nieuwe gebruikersnaam en het nieuwe wachtwoord op.
1. Sla de referenties op.
