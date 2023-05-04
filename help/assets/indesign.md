---
title: Integreren [!DNL Experience Manager] Middelen bij Adobe InDesign Server
description: Leer hoe u kunt integreren [!DNL Experience Manager] Activa met InDesign Server.
contentOwner: AG
feature: Publishing
role: Admin
exl-id: d80562f7-071c-460a-9c68-65f48d36fbd9
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1682'
ht-degree: 1%

---

# Middelen integreren met Adobe InDesign Server {#integrating-aem-assets-with-indesign-server}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Adobe Experience Manager Assets gebruikt:

* Een proxy om het laden van bepaalde verwerkingstaken te verdelen. Een proxy is een [!DNL Experience Manager] instantie die communiceert met een proxyworker om een specifieke taak uit te voeren, en andere [!DNL Experience Manager] instanties om de resultaten te leveren.
* Een proxyworker om een specifieke taak te definiëren en te beheren.

Deze kunnen betrekking hebben op een groot aantal verschillende taken; bijvoorbeeld met een Adobe InDesign Server bestanden verwerken.

Bestanden volledig uploaden naar [!DNL Experience Manager] Elementen die u met Adobe InDesign hebt gemaakt, worden gebruikt. Dit gebruikt een volmachtsarbeider om met Adobe InDesign Server te communiceren waar [scripts](https://www.adobe.com/devnet/indesign/documentation.html#idscripting) worden uitgevoerd om metagegevens te extraheren en verschillende uitvoeringen te genereren voor [!DNL Experience Manager] Elementen. De volmachtsarbeider laat de bidirectionele communicatie tussen de InDesign Server en toe [!DNL Experience Manager] instantie(s) in een cloudconfiguratie.

>[!NOTE]
>
>Adobe InDesign bestaat uit twee producten:
>
>* [InDesign](https://www.adobe.com/products/indesign.html)\
   >  Zo kunt u paginalay-outs ontwerpen voor afdrukken en/of digitale distributie.
>
>* [InDesign Server](https://www.adobe.com/products/indesignserver.html)\
   >  Met deze engine kunt u programmatisch geautomatiseerde documenten maken op basis van wat u met InDesign hebt gemaakt. Het werkt als dienst die een interface aan zijn aanbiedt [ExtendScript](https://www.adobe.com/devnet/scripting.html) motor.\
   >  De scripts zijn geschreven in ExtendScript en zijn vergelijkbaar met JavaScript. Voor informatie over Adobe InDesign-scripts raadpleegt u [https://www.adobe.com/devnet/indesign/documentation.html#idscripting](https://www.adobe.com/devnet/indesign/documentation.html#idscripting).
>


## Hoe de extractie werkt {#how-the-extraction-works}

De InDesign Server kan worden geïntegreerd met [!DNL Experience Manager] Elementen zodat bestanden die met InDesign zijn gemaakt ( `.indd`) kan worden geüpload, uitvoeringen worden gegenereerd, *alles* media geëxtraheerd (bijvoorbeeld video) en opgeslagen als elementen:

>[!NOTE]
>
>Eerdere versies van [!DNL Experience Manager] konden XMP en de miniatuur extraheren, nu kunnen alle media worden geëxtraheerd.

1. Upload uw `.indd` bestand naar [!DNL Experience Manager] Elementen.
1. Een framework verzendt opdrachtscripts naar de InDesign Server via SOAP (Simple Object Access Protocol).

   Dit opdrachtscript:

   * De `.indd` bestand.
   * InDesign Server-opdrachten uitvoeren:

      * De structuur, de tekst en alle mediabestanden worden geëxtraheerd.
      * PDF- en JPG-uitvoeringen worden gegenereerd.
      * HTML- en IDML-uitvoeringen worden gegenereerd.
   * De resulterende bestanden opnieuw plaatsen naar [!DNL Experience Manager] Elementen.

   >[!NOTE]
   >
   >IDML is een op XML gebaseerd formaat dat teruggeeft *alles* in het InDesign-bestand. Het wordt opgeslagen als een gecomprimeerd pakket met [Postcode](https://www.techterms.com/definition/zip) compressie.
   >
   >Zie [Adobe InDesign Interchange Formats INX en IDML](https://www.peachpit.com/articles/article.aspx?p=1381880&amp;seqNum=8) voor nadere informatie.

   >[!CAUTION]
   >
   >Als de InDesign Server niet geïnstalleerd of niet gevormd is, dan kunt u nog uploaden `.indd` bestand in [!DNL Experience Manager]. De gegenereerde uitvoeringen blijven echter beperkt tot `png` en `jpeg`, kunt u niet genereren `html`, `idml` of de pagina-uitvoeringen.

1. Na de extractie en uitvoering:

   * De structuur wordt gerepliceerd naar een `cq:Page` (type vertoning).
   * De geëxtraheerde tekst en bestanden worden opgeslagen in [!DNL Experience Manager] Elementen.
   * Alle uitvoeringen worden opgeslagen in [!DNL Experience Manager] Activa, in het actief zelf.

## De InDesign Server integreren met [!DNL Experience Manager] {#integrating-the-indesign-server-with-aem}

De InDesign Server integreren voor gebruik met [!DNL Experience Manager] Middelen en na het configureren van uw proxy moet u:

1. [De InDesign Server installeren](#installing-the-indesign-server).
1. Indien vereist, [vorm [!DNL Experience Manager] Assets Workflow](#configuring-the-aem-assets-workflow).

   Dit is alleen nodig als de standaardwaarden niet geschikt zijn voor uw instantie.

1. Een [proxyworker voor de InDesign Server](#configuring-the-proxy-worker-for-indesign-server).

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

### Het vormen van [!DNL Experience Manager] Assets Workflow {#configuring-the-aem-assets-workflow}

[!DNL Experience Manager] Elementen hebben een vooraf geconfigureerde workflow **DAM Update-element**, die verscheidene processtappen specifiek voor InDesign heeft:

* [Media extraheren](#media-extraction)
* [Pagina uitnemen](#page-extraction)

Dit werkschema is opstelling met standaardwaarden die voor uw opstelling op de diverse auteursinstanties (dit is een standaardwerkschema, zodat is de verdere informatie beschikbaar onder [Een workflow bewerken](/help/sites-developing/workflows-models.md#configuring-a-workflow-step)). Als u de standaardwaarden (met inbegrip van de haven van de ZEEP) gebruikt, dan is geen configuratie nodig.

Na de installatie worden InDesign-bestanden geüpload naar [!DNL Experience Manager] Elementen (volgens een van de gebruikelijke methoden) activeren de workflow die nodig is om het element te verwerken en de verschillende uitvoeringen voor te bereiden. Test uw configuratie door een `.indd` bestand in [!DNL Experience Manager] Middelen om te bevestigen dat u de verschillende vertoningen ziet die door IDS onder worden gecreeerd `<*your_asset*>.indd/Renditions`

#### Media extraheren {#media-extraction}

Met deze stap bepaalt u de extractie van media uit de `.indd` bestand.

Als u deze wilt aanpassen, kunt u **[!UICONTROL Arguments]** tabblad van het dialoogvenster **[!UICONTROL Media Extraction]** stap.

![Argumenten voor het uitnemen van media en scriptpaden](assets/media_extraction_arguments_scripts.png)

Argumenten voor het uitnemen van media en scriptpaden

* **ExtendScript-bibliotheek**: Dit is een eenvoudige http-methodebibliotheek, vereist door de andere scripts.

* **Scripts uitbreiden**: Hier kunt u verschillende scriptcombinaties opgeven. Als u uw eigen manuscripten op de InDesign Server wilt uitvoeren, sparen de manuscripten bij `/apps/settings/dam/indesign/scripts`.

   Zie voor informatie over InDesign-scripts [https://www.adobe.com/devnet/indesign/documentation.html#idscripting](https://www.adobe.com/devnet/indesign/documentation.html#idscripting).

>[!CAUTION]
>
>Wijzig de ExtendScript-bibliotheek niet. De bibliotheek biedt de HTTP-functionaliteit die nodig is voor communicatie met Sling. Met deze instelling geeft u de bibliotheek op die naar de Adobe InDesign Server moet worden verzonden voor gebruik.

De `ThumbnailExport.jsx` een script uitvoeren dat wordt uitgevoerd door de workflowstap Media Extraction, genereert een miniatuuruitvoering in de JPG-indeling. Deze vertoning wordt gebruikt door de workflowstap Miniaturen verwerken om de statische vertoningen te genereren die worden vereist door [!DNL Experience Manager].

U kunt de workflowstap Miniaturen verwerken zodanig configureren dat statische uitvoeringen van verschillende grootten worden gegenereerd. Zorg ervoor dat u de standaardinstellingen niet verwijdert, omdat deze vereist zijn voor de [!DNL Experience Manager] UI Middelen. Tot slot verwijdert de workflowstap Voorvertoning afbeelding verwijderen de miniatuuruitvoering .jpg, omdat deze niet langer nodig is.

#### Pagina uitnemen {#page-extraction}

Hiermee maakt u een [!DNL Experience Manager] pagina uit de geëxtraheerde elementen. Een extractiemanager wordt gebruikt om gegevens uit een vertoning (momenteel HTML of IDML) te halen. Deze gegevens worden vervolgens gebruikt om een pagina te maken met de PageBuilder.

Als u de **[!UICONTROL Arguments]** tabblad van het dialoogvenster **Pagina uitnemen** stap.

![chlimage_1-289](assets/chlimage_1-289.png)

* **Handler voor pagina-uitname**: Selecteer in de vervolgkeuzelijst de handler die u wilt gebruiken. Een extractiehandler werkt op een specifieke uitvoering, die door een verwante `RenditionPicker` (zie de `ExtractionHandler`-API) wordt gekozen.
Standaard is de IDML-exporthandler beschikbaar. Zij opereert op de `IDML` vertoning die in de stap MediaExtract wordt geproduceerd.

* **Paginanaam**: Geef de naam op die u aan de resulterende pagina wilt toewijzen. Als deze optie leeg blijft, is de naam &quot;page&quot; (of een derivaat als &quot;page&quot; al bestaat).

* **Paginatitel**: Geef de titel op die u aan de resulterende pagina wilt toewijzen.

* **Basispad pagina**: Het pad naar de hoofdlocatie van de resulterende pagina. Indien leeg gelaten, wordt het knooppunt gebruikt dat de uitvoeringen van het element bevat.

* **Paginasjabloon**: De sjabloon die moet worden gebruikt bij het genereren van de resulterende pagina.

* **Paginaontwerp**: Het paginaontwerp dat moet worden gebruikt bij het genereren van de resulterende pagina.

### De proxyworker voor InDesign Server configureren {#configuring-the-proxy-worker-for-indesign-server}

>[!NOTE]
>
>De worker bevindt zich op de proxyinstantie.

1. Vouw in de console Tools de **[!UICONTROL Cloud Services Configurations]** in het linkerdeelvenster. Vouw vervolgens uit **[!UICONTROL Cloud Proxy Configuration]**.

1. Dubbelklik op de knop **[!UICONTROL IDS worker]** om te openen voor configuratie.

1. Klikken **[!UICONTROL Edit]** om het configuratiedialoogvenster te openen en de vereiste instellingen te definiëren:

   ![proxy_disworkerconfig](assets/proxy_idsworkerconfig.png)

   * **IDS Pool**: Het (de) eindpunt(en) van de ZEEP die voor het communiceren met de InDesign Server moeten worden gebruikt. U kunt items toevoegen, verwijderen en bestellen.

1. Klikken **[!UICONTROL OK]** om op te slaan.

### Het vormen van Dag CQ Verbinding Externalzer {#configuring-day-cq-link-externalizer}

Als de InDesign Server en [!DNL Experience Manager] zijn op verschillende gastheren of één of beide toepassingen werken niet aan standaardhavens, vormen **Day CQ Link ExternalAlizer** om de hostnaam, poort en inhoudspad voor de InDesign Server in te stellen.

1. Access Configuration Manager via de URL `https://[AEM_server]:[port]/system/console/configMgr`.
1. De configuratie zoeken **[!UICONTROL Day CQ Link Externalizer]**. Klikken **[!UICONTROL Edit]** openen.
1. De montages van de Verbinding Externalzer helpen absolute URLs voor tot stand brengen [!DNL Experience Manager] en voor de [!DNL InDesign Server]. Gebruiken **[!UICONTROL Domains]** veld om de hostnaam en het contextpad voor het [!DNL Adobe InDesign Server]. Volg de aanwijzingen op het scherm. Klik op **[!UICONTROL Save]**.

   ![Externe instellingen koppelen](assets/link-externalizer-config.png)

### Parallelle taakverwerking inschakelen voor InDesign Server {#enabling-parallel-job-processing-for-indesign-server}

U kunt nu parallelle taakverwerking inschakelen voor IDS.

Eerst moet u het maximumaantal parallelle banen bepalen ( `x`) een InDesign Server kan verwerken:

* Op één multiprocessorcomputer is het maximumaantal parallelle taken (x) dat een InDesign Server kan verwerken één minder dan het aantal processors met IDS.
* Wanneer u IDS op veelvoudige machines in werking stelt moet u het totale aantal beschikbare bewerkers (dat wil zeggen op alle machines) tellen dan het totale aantal machines aftrekken.

Om het aantal parallelle banen te vormen IDS:

1. Open de **[!UICONTROL Configurations]** tabblad van de Felix-console; bijvoorbeeld:

   `http://localhost:4502/system/console/configMgr`

1. Selecteer de IDS verwerkingsrij onder:

   `Apache Sling Job Queue Configuration`

1. Instellen:

   * **[!UICONTROL Type]** - `Parallel`
   * **[!UICONTROL Maximum Parallel Jobs]** - `<*x*>` (zoals hierboven berekend)

1. Sla deze wijzigingen op.
1. Als u ondersteuning voor meerdere sessies wilt inschakelen voor Adobe CS6 en later, schakelt u het selectievakje `enable.multisession.name` selectievakje onder `com.day.cq.dam.ids.impl.IDSJobProcessor.name configuration`.
1. Een [pool van &lt; `*x*>` IDS de arbeiders door de eindpunten van de ZEEP aan de configuratie van de Arbeider IDS toe te voegen](#configuring-the-proxy-worker-for-indesign-server).

   Als er meerdere computers zijn waarop InDesign Server wordt uitgevoerd, voegt u SOAP-eindpunten (aantal processors per computer -1) toe voor elke computer.

   >[!NOTE]
   >
   >Wanneer u werkt met een groep workers, kunt u de lijst van gewezen personen van IDS-workers inschakelen.
   >
   >Om dit te doen, laat checkbox &quot;enable.retry.name&quot;, onder toe `com.day.cq.dam.ids.impl.IDSJobProcessor.name` configuratie, waardoor IDS-taken kunnen worden opgehaald.
   >
   >Onder de `com.day.cq.dam.ids.impl.IDSPoolImpl.name` configuratie, een positieve waarde instellen voor `max.errors.to.blacklist` parameter die het aantal taakterugwinnen alvorens een IDS van de lijst van baanmanagers bepaalt
   >
   >Door gebrek, na configureerbaar (`retry.interval.to.whitelist.name`) in minuten wordt de IDS-worker opnieuw gevalideerd. Als de worker online wordt gevonden, wordt deze uit de lijst van gewezen personen verwijderd.

<!-- TBD: Make updates to configurations for allow and block list after product updates are done. See CQ-4298427.
-->

## Ondersteuning inschakelen voor Adobe InDesign-server 10.0 of hoger {#enabling-support-for-indesign-server-or-higher}

Voer voor InDesign-server 10.0 of hoger de volgende stappen uit om ondersteuning voor meerdere sessies mogelijk te maken.

1. Open de Configuratie Manager van uw [!DNL Assets] instance `https://[aem_server]:[port]/system/console/configMgr`.
1. De configuratie bewerken `com.day.cq.dam.ids.impl.IDSJobProcessor.name`.
1. Selecteren **[!UICONTROL ids.cc.enable]** en klik op **[!UICONTROL Save]**.

>[!NOTE]
>
>Voor [!DNL InDesign Server] integratie met [!DNL Assets], gebruik een multicore-processor omdat de functie voor sessieondersteuning die nodig is voor de integratie niet wordt ondersteund op single core-systemen.

## Referenties van Experience Manager configureren {#configure-aem-credentials}

U kunt de standaardbeheerdersreferenties (gebruikersnaam en wachtwoord) wijzigen voor toegang tot de InDesign-server via uw [!DNL Experience Manager] -instantie zonder de integratie met de Adobe InDesign-server te verbreken.

1. Ga naar `/etc/cloudservices/proxy.html`.
1. Geef in het dialoogvenster de nieuwe gebruikersnaam en het nieuwe wachtwoord op.
1. Sla de referenties op.
