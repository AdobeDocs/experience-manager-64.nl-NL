---
title: Dynamic Media configureren - hybride modus
seo-title: Configuring Dynamic Media - Hybrid mode
description: Leer hoe u Dynamic Media - Hybride modus configureert.
seo-description: Learn how to configure Dynamic Media - Hybrid mode.
uuid: de88f68f-4697-4ff0-8008-3ae6a4684a84
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
discoiquuid: 821eb27e-67c9-4589-9196-30dacb84fa59
exl-id: 1e122f97-ac37-44f5-a1cd-bf53ffda6f5b
feature: Configuration,Hybrid Mode
role: Admin,User,Developer
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '7441'
ht-degree: 1%

---

# Dynamic Media configureren - hybride modus {#configuring-dynamic-media-hybrid-mode}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Dynamic Media - Hybride moet voor gebruik worden toegelaten en worden gevormd. Afhankelijk van je gebruikscase heeft Dynamic Media verschillende [ondersteunde configuraties](#supported-dynamic-media-configurations).

>[!NOTE]
>
>Als u Dynamic Media wilt configureren en uitvoeren in de Scene7-uitvoeringsmodus, raadpleegt u [Dynamic Media configureren - Scene7-modus](config-dms7.md).
>
>Als u Dynamic Media wilt configureren en uitvoeren in de hybride uitvoeringsmodus, volgt u de instructies op deze pagina.

Meer informatie over werken met [video](video.md) in Dynamic Media.

Als u Adobe Experience Manager-configuratie gebruikt voor verschillende omgevingen, zoals een omgeving voor ontwikkeling, een omgeving voor staging en een omgeving voor live productie, moet u Dynamic Media-Cloud Services configureren voor elk van deze omgevingen.

Als u problemen hebt met uw Dynamic Media-configuratie, is het belangrijk dat u de logbestanden bekijkt die specifiek zijn voor dynamische media. Deze worden automatisch geïnstalleerd wanneer u dynamische media inschakelt:

* `s7access.log`
* `ImageServing.log`

Deze worden beschreven in [Uw AEM controleren en onderhouden](/help/sites-deploying/monitoring-and-maintaining.md).

Hybride uitgeverij en levering vormen een kernelement van de toevoeging van Dynamic Media aan Adobe Experience Manager. Met hybride publicaties kunt u Dynamic Media-elementen, zoals afbeeldingen, sets en video, uit de cloud leveren in plaats van uit de AEM publicatieknooppunten.

Andere inhoud, zoals Dynamic Media-viewers, sitepagina&#39;s en statische inhoud, blijft beschikbaar via de AEM publicatieknooppunten.

Als u een klant van Dynamic Media bent, moet u hybride levering als leveringsmechanisme voor alle Dynamic Media-inhoud gebruiken.

## Hybride publicatiearchitectuur voor video&#39;s {#hybrid-publishing-architecture-for-videos}

![chlimage_1-506](assets/chlimage_1-506.png)

## Hybride publicatiearchitectuur voor afbeeldingen {#hybrid-publishing-architecture-for-images}

![chlimage_1-507](assets/chlimage_1-507.png)

## Ondersteunde Dynamic Media-configuraties {#supported-dynamic-media-configurations}

De configuratietaken die volgen verwijzen naar de volgende termen:

| **Term** | **Dynamic Media ingeschakeld** | **Beschrijving** |
|---|---|---|
| AEM auteurknooppunt | Wit vinkje in een groene cirkel | Het auteurknooppunt dat u op locatie of via Managed Services implementeert. |
| AEM publicatieknooppunt | Wit &quot;X&quot; in een rood vierkant. | Het publicatieknooppunt dat u op locatie of via Managed Services implementeert. |
| Publicatieknooppunt voor Image Service | Witte vinkje in een groene cirkel. | Het publicatieknooppunt dat u op de Centra van Gegevens in werking stelt die door Adobe worden beheerd. Verwijst naar de URL van de afbeeldingsservice. |

U kunt ervoor kiezen om Dynamic Media alleen te implementeren voor beeldbewerking, alleen voor video of voor zowel beeldbewerking als video. Verwijs naar de volgende tabel om de stappen te bepalen voor het configureren van Dynamic Media voor uw specifieke scenario.

<table> 
 <tbody> 
  <tr> 
   <td><strong>Scenario</strong></td> 
   <td><strong>Hoe het werkt</strong></td> 
   <td><strong>Configuratiestappen</strong></td> 
  </tr> 
  <tr> 
   <td>ALLEEN images in productie leveren</td> 
   <td>De beelden worden geleverd door servers in de wereldwijde gegevenscentra van Adobe en dan in het voorgeheugen ondergebracht door CDN voor scalable prestaties en globaal bereik.</td> 
   <td> 
    <ol> 
     <li>Op de AEM <strong>auteur</strong> knooppunt, <a href="#enabling-dynamic-media">dynamische media inschakelen</a>.</li> 
     <li>Afbeeldingen configureren in <a href="#configuring-dynamic-media-cloud-services">Dynamic Media Cloud Services</a>.</li> 
     <li><a href="#configuring-image-replication">Afbeeldingsreplicatie configureren</a>.</li> 
     <li><a href="#replicating-catalog-settings">Catalogusinstellingen repliceren</a>.</li> 
     <li><a href="#replicating-viewer-presets">Viewervoorinstellingen repliceren</a>.</li> 
     <li><a href="#using-default-asset-filters-for-replication">Standaardelementfilters gebruiken voor replicatie</a>.</li> 
     <li><a href="#configuring-dynamic-media-image-server-settings">Dynamic Media Image Server-instellingen configureren</a>.</li> 
     <li><a href="#delivering-assets">Elementen leveren</a>.</li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td>Alleen afbeeldingen leveren in pre-productie (Dev, QE, Stage, enzovoort.)</td> 
   <td>Afbeeldingen worden geleverd via het AEM publicatieknooppunt. In dit scenario, aangezien het verkeer minimaal is, is er geen behoefte om beelden aan het gegevenscentrum van Adobe te leveren. Een extra voordeel is dat u hiermee een beveiligde voorvertoning van inhoud kunt bekijken voordat de productie wordt gestart</td> 
   <td> 
    <ol> 
     <li>Op de AEM <strong>auteur</strong> knooppunt, <a href="#enabling-dynamic-media">dynamische media inschakelen</a>.</li> 
     <li>Op AEM <strong>publish</strong> knooppunt, <a href="#enabling-dynamic-media">dynamische media inschakelen</a>.</li> 
     <li><a href="#replicating-viewer-presets">Viewervoorinstellingen repliceren</a>.</li> 
     <li>Instellen <a href="#setting-up-asset-filters-for-imaging-in-non-production-deployments">middelenfilter voor niet-productieafbeeldingen</a>.</li> 
     <li><a href="#configuring-dynamic-media-image-server-settings">Dynamic Media Image Server-instellingen configureren.</a></li> 
     <li><a href="#delivering-assets">Elementen leveren.</a></li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td>ALLEEN video leveren in elke omgeving (Productie, Dev, QE, Stage, enzovoort)</td> 
   <td>De video's worden geleverd en in het voorgeheugen ondergebracht door CDN voor scalable prestaties en globaal bereik. De video-posterafbeelding (miniatuur van video die wordt weergegeven voordat het afspelen wordt gestart) wordt door de AEM-publicatie-instantie geleverd.</td> 
   <td> 
    <ol> 
     <li>Op de AEM <strong>auteur</strong> knooppunt, <a href="#enabling-dynamic-media">dynamische media inschakelen</a>.</li> 
     <li>Op de AEM <strong>publish</strong> knooppunt, <a href="#enabling-dynamic-media">dynamische media inschakelen</a> (De publicatie-instantie dient voor de video-posterafbeelding en biedt metagegevens voor het afspelen van video.)</li> 
     <li>Video configureren in <a href="#configuring-dynamic-media-cloud-services">Dynamic Media Cloud Services.</a></li> 
     <li><a href="#replicating-viewer-presets">Viewervoorinstellingen repliceren</a>.</li> 
     <li>Instellen <a href="#setting-up-asset-filters-for-video-only-deployments">middelenfilter voor alleen video</a>.</li> 
     <li><a href="#delivering-assets">Elementen leveren.</a></li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td>Lever ZOWEL beelden als video in productie</td> 
   <td><p>De video's worden geleverd en in het voorgeheugen ondergebracht door CDN voor scalable prestaties en globaal bereik. Afbeeldingen en videoposterafbeeldingen worden via servers in wereldwijde datacenters van Adobe geleverd en worden vervolgens in cache geplaatst door een CDN voor schaalbare prestaties en een wereldwijd bereik.</p> <p>Raadpleeg de vorige secties voor het instellen van het beeld of de video in de preproductie. </p> </td> 
   <td> 
    <ol> 
     <li>Op de AEM <strong>auteur</strong> knooppunt, <a href="#enabling-dynamic-media">dynamische media inschakelen</a>.</li> 
     <li>Video configureren in <a href="#configuring-dynamic-media-cloud-services">Dynamic Media Cloud Services.</a></li> 
     <li>Afbeeldingen configureren in <a href="#configuring-dynamic-media-cloud-services">Dynamic Media Cloud Services.</a></li> 
     <li><a href="#configuring-image-replication">Afbeeldingsreplicatie configureren</a>.</li> 
     <li><a href="#replicating-catalog-settings">Catalogusinstellingen repliceren</a>.</li> 
     <li><a href="#replicating-viewer-presets">Viewervoorinstellingen repliceren</a>.</li> 
     <li><a href="#using-default-asset-filters-for-replication">Gebruik standaardelementfilters voor replicatie.</a></li> 
     <li><a href="#configuring-dynamic-media-image-server-settings">Dynamic Media Image Server-instellingen configureren.</a></li> 
     <li><a href="#delivering-assets">Elementen leveren.</a></li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

## Dynamic Media inschakelen {#enabling-dynamic-media}

[Dynamische media](https://www.adobe.com/solutions/web-experience-management/dynamic-media.html) is standaard uitgeschakeld. Als u wilt profiteren van Dynamic Media-functies, moet u dynamische media inschakelen met de **[!UICONTROL dynamicmedia]** de uitvoermodus zoals u bijvoorbeeld zou doen **[!UICONTROL publish]** uitvoeringsmodus. Controleer voordat u de functie inschakelt of [technische voorschriften](/help/sites-deploying/technical-requirements.md#requirements-for-aem-dynamic-media-add-on).

>[!NOTE]
>
>Als u dynamische media inschakelt via de uitvoeringsmodus, wordt de functionaliteit in AEM 6.1 en AEM 6.0 vervangen, waarbij u dynamische media hebt ingeschakeld door het instellen van de **[!UICONTROL dynamicMediaEnabled]** markeren naar **[!UICONTROL true]**. Deze markering heeft geen functionaliteit in AEM 6.2 en later. Bovendien hoeft u de snelstartprocedure niet opnieuw te starten om dynamische media in te schakelen.

Als u Dynamic Media inschakelt, zijn de dynamische mediafuncties beschikbaar in de gebruikersinterface en ontvangt elk geüploade afbeeldingselement een `cqdam.pyramid.tiff` uitvoering die wordt gebruikt voor snelle levering van dynamische afbeeldingsuitvoeringen. Deze PTIFF&#39;s hebben belangrijke voordelen, zoals (1) de mogelijkheid om slechts één master afbeelding te beheren en op elk moment oneindige uitvoeringen te genereren zonder extra opslagruimte en (2) de mogelijkheid om interactieve visualisatie te gebruiken, zoals zoomen, pannen, centrifugeren, enzovoort.

Als u Dynamic Media Classic in AEM wilt gebruiken, moet u Dynamic Media alleen inschakelen als u een [specifiek scenario](/help/sites-administering/scene7.md#aem-scene-integration-versus-dynamic-media). Dynamic Media is uitgeschakeld, tenzij u Dynamic Media inschakelt in de runmode.

Om dynamische media toe te laten, moet u de dynamische media runmode of van de bevellijn of van de naam van het quickstart dossier toelaten.

**Dynamische media inschakelen**:

1. Ga als volgt te werk op de opdrachtregel wanneer u de snelstart start:

   * Toevoegen **[!UICONTROL -r dynamicmedia]** aan het einde van de opdrachtregel wanneer het jar-bestand wordt gestart.

   ```shell
   java -Xmx4096m -Doak.queryLimitInMemory=500000 -Doak.queryLimitReads=500000 -jar cq-quickstart-6.4.0.jar -r dynamicmedia
   ```

   Als u publiceert naar s7delivery, dan moet u ook de volgende TrustStore argumenten omvatten:

   ```shell
   -Djavax.net.ssl.trustStore=<absoluteFilePath>/customerTrustStoreFileName>
   
    -Djavax.net.ssl.trustStorePassword=<passwordForTrustStoreFile>
   ```

1. Verzoek `http://localhost:4502/is/image` en zorg ervoor de Server van het Beeld nu loopt.

   >[!NOTE]
   >
   >Als u problemen met Dynamic Media wilt oplossen, raadpleegt u de volgende logboeken in het dialoogvenster **[!UICONTROL crx-quickstart/logs/]** map:
   >
   >* ImageServer-&lt;portid>-&lt;yyyy>&lt;mm>&lt;dd>.log - Het logboek ImageServer verstrekt statistieken en analytische informatie die voor het analyseren van het gedrag van het interne proces ImageServer wordt gebruikt.

      Voorbeeld van de naam van een logbestand voor een afbeeldingsserver: `ImageServer-57346-2019-07-25.log`
   * s7access-&lt;yyyy>&lt;mm>&lt;dd>.log - Het s7access logboek registreert elk verzoek dat aan Dynamic Media via `/is/image` en `/is/content`.
   Deze logboeken worden alleen gebruikt als Dynamic Media is ingeschakeld. Zij zijn niet opgenomen in de **Volledige download** pakket dat wordt gegenereerd op basis van het **[!UICONTROL system/console/status-Bundlelist]** pagina; wanneer u Customer Support belt als u een Dynamic Media-probleem hebt, voeg dan beide logbestanden aan het probleem toe.

### Als u AEM hebt geïnstalleerd op een andere poort of een ander contextpad... {#if-you-installed-aem-to-a-different-port-or-context-path}

Als u implementeert [AEM naar een toepassingsserver](/help/sites-deploying/application-server-install.md) en hebt Dynamic Media ingeschakeld, moet u de **zelfzucht** in de externalizer. Anders werkt het genereren van miniaturen voor elementen niet correct voor dynamische media-elementen.

Als u bovendien quickstart uitvoert op een andere poort of een ander contextpad, moet u ook de **zelfzucht** domein.

Als Dynamic Media is ingeschakeld, worden de statische miniatuuruitvoeringen voor afbeeldingselementen gegenereerd met Dynamic Media. Voor het correct genereren van miniaturen voor dynamische media, moet AEM een URL-aanvraag naar zichzelf uitvoeren en zowel het poortnummer als het contextpad kennen.

In AEM:

* De **zelfzucht** in het [extern](/help/sites-developing/externalizer.md) wordt gebruikt om zowel het havenaantal als contextweg terug te winnen.
* Indien niet **zelfzucht** het domein wordt gevormd, worden het havenaantal en contextweg teruggewonnen van de dienst van HTTP van Jetty.

In een AEM plaatsing van de WAR van QuickStart, kunnen het havenaantal en de contextweg niet worden afgeleid, daarom moet u een **zelfzucht** domein. Zie [documentatie van externalizer](/help/sites-developing/externalizer.md) op hoe te om te vormen **zelfzucht** domein.

>[!NOTE]
In een [Zelfstandige implementatie AEM QuickStart](/help/sites-deploying/deploy.md), **zelfzucht** domein te hoeven over het algemeen niet worden gevormd omdat het havenaantal en de contextweg auto-gevormd kunnen zijn. Nochtans, als alle netwerkinterfaces worden uitgezet, moet u vormen **zelfzucht** domein.

## Dynamic Media uitschakelen  {#disabling-dynamic-media}

Dynamische media zijn niet standaard ingeschakeld. Als u echter eerder dynamische media hebt ingeschakeld, kunt u deze later uitschakelen.

Als u dynamische media wilt uitschakelen nadat u deze hebt ingeschakeld, verwijdert u de **[!UICONTROL -r dynamicmedia]** markering voor uitvoermodus.

**Dynamic Media uitschakelen nadat deze is ingeschakeld**:

1. Op de opdrachtregel kunt u een van de volgende handelingen uitvoeren wanneer u de snelstart start:

   * Niet toevoegen `-r dynamicmedia` op de opdrachtregel wanneer het JAR-bestand wordt gestart.

   ```shell
   java -Xmx4096m -Doak.queryLimitInMemory=500000 -Doak.queryLimitReads=500000 -jar cq-quickstart-6.4.0.jar
   ```

1. Verzoek `http://localhost:4502/is/image`. Je ontvangt een bericht dat Dynamic Media is uitgeschakeld.

   >[!NOTE]
   Nadat de Dynamic Media-uitvoeringsmodus is uitgeschakeld, wordt de workflowstap die het `qdam.pyramid.tiff` uitvoering wordt automatisch overgeslagen. Hierdoor worden ook ondersteuning voor dynamische uitvoeringen en andere Dynamic Media-functies uitgeschakeld.
   Houd er ook rekening mee dat wanneer de Dynamic Media-uitvoeringsmodus wordt uitgeschakeld nadat de AEM is geconfigureerd, alle middelen die in die uitvoeringsmodus zijn geüpload, nu ongeldig zijn.

## (Optioneel) Dynamic Media-voorinstellingen en -configuraties migreren van 6.3 naar 6.4 zonder downtime {#optional-migrating-dynamic-media-presets-and-configurations-from-to-zero-downtime}

Als u AEM Dynamic Media van 6.3 aan 6.4 bevordert - die nu de capaciteit voor nul onderbreking (ook als &quot;Opt-in&quot;wordt bekend) plaatsingen omvat - moet u het volgende krullbevel in werking stellen om al uw voorinstellingen en configuraties van te migreren `/etc` tot `/conf` in CRXDE Lite.

**Opmerking**: Als u de AEM op compatibiliteitsmodus uitvoert, hebt u het compatibiliteitspakket geïnstalleerd. U hoeft deze opdrachten niet uit te voeren.

Aangepaste voorinstellingen en configuraties migreren uit `/etc` tot `/conf`, voert u de volgende Linux-curl-opdracht uit:

`curl -u admin:admin http://localhost:4502/libs/settings/dam/dm/presets.migratedmcontent.json`

Voor alle upgrades, met of zonder het compatibiliteitspakket, kunt u de voorinstellingen van de verouderde viewer kopiëren door de volgende opdracht uit te voeren:

`curl -u admin:admin http://localhost:4502/libs/settings/dam/dm/presets/viewer.pushviewerpresets`

## Afbeeldingsreplicatie configureren {#configuring-image-replication}

De levering van Dynamic Media-afbeeldingen werkt door het publiceren van afbeeldingselementen, waaronder videominiaturen, van AEM Author die deze repliceert tot Adobe op aanvraag (de Replication Service URL). De activa worden dan geleverd door de dienst van de beeldlevering op bestelling (de Dienst URL van het Beeld).

U moet het volgende doen:

1. [Verificatie instellen](#setting-up-authentication).
1. [De replicatieagent configureren](#configuring-the-replication-agent).

De Replication Agent publiceert Dynamic Media-elementen, zoals afbeeldingen, videometagegevens en stelt deze in op de door Adobe gehoste Image Service. De replicatieagent is niet standaard ingeschakeld.

Nadat u de replicatieagent hebt gevormd, moet u [valideren en testen of de installatie is gelukt](#validating-the-replication-agent-for-dynamic-media). In dit gedeelte worden deze procedures beschreven.

>[!NOTE]
De standaardgeheugenlimiet voor het maken van PTIFF is 3 GB voor alle workflows. U kunt bijvoorbeeld één afbeelding verwerken die 3 GB geheugen vereist terwijl andere workflows worden gepauzeerd, of u kunt 10 afbeeldingen parallel verwerken die elk 300 MB geheugen vereisen.
De geheugenlimiet is configureerbaar en moet passen bij de beschikbaarheid van de systeembronnen en het type afbeeldingsinhoud dat wordt verwerkt. Als u vele zeer grote activa hebt en genoeg geheugen op het systeem hebt, kunt u deze grens verhogen om ervoor te zorgen dat de beelden parallel worden verwerkt.
Een afbeelding waarvoor meer dan de maximale geheugenlimiet is vereist, wordt afgewezen.
Als u de geheugenlimiet voor het maken van PTIFF wilt wijzigen, navigeert u naar **[!UICONTROL Tools > Operations > Web Console > Adobe CQ Scene7 PTiffManager]** en wijzigt u de `maxMemory` waarde.

### Verificatie instellen {#setting-up-authentication}

U moet replicatieverificatie instellen bij de auteur om afbeeldingen te kunnen repliceren naar de Dynamic Media-service voor het leveren van images. U doet dit door een KeyStore te verkrijgen en deze vervolgens op te slaan onder de **[!UICONTROL dynamic-media-replication]** gebruiker en configureren. Uw bedrijfsbeheerder had tijdens het inrichtingsproces een welkomstbericht met het KeyStore-bestand en de benodigde gegevens moeten ontvangen. Neem contact op met Customer Support als je dit niet hebt ontvangen.

**Verificatie instellen**:

1. Neem contact op met de Klantenondersteuning voor uw KeyStore-bestand en wachtwoord als u dit nog niet hebt. Dit maakt deel uit van provisioning en de sleutels worden aan uw account gekoppeld.
1. Tik in AEM op het AEM-logo om toegang te krijgen tot de globale navigatieconsole en tik vervolgens op **[!UICONTROL Tools > Security > Users]**.
1. Navigeer op de pagina Gebruikersbeheer naar de **[!UICONTROL dynamic-media-replication]** gebruiker, tikt u vervolgens om te openen.

   ![dm-replicatie](assets/dm-replication.png)

1. Tik op de pagina Gebruikersinstellingen bewerken voor dynamische media-replicatie op de knop **[!UICONTROL Keystore]** tab, tikt u vervolgens op **[!UICONTROL Create KeyStore]**.

   ![dm-replication-keystore](assets/dm-replication-keystore.png)

1. Voer een wachtwoord in en bevestig het wachtwoord in het dialoogvenster **[!UICONTROL Set KeyStore Access Password]** in.

   >[!NOTE]
   Het wachtwoord onthouden dat u invoert. U zult het opnieuw moeten ingaan wanneer u vormt **[!UICONTROL Replication Agent]** later.

   ![chlimage_1-508](assets/chlimage_1-508.png)

1. Op de **[!UICONTROL Edit User Settings For dynamic-media-replication]** pagina, breid de **[!UICONTROL Add Private Key from KeyStore file]** en voeg het volgende toe (zie de volgende afbeeldingen):

   * In de **[!UICONTROL New Alias]** gebied, ga de naam van een alias in die u later in de replicatieconfiguratie zult gebruiken; bijvoorbeeld: **replicatie**.
   * Tik op **[!UICONTROL KeyStore File]**. Navigeer naar het KeyStore-bestand dat u via Adobe ontvangt, selecteer het en tik op **[!UICONTROL Open]**.
   * In de **[!UICONTROL KeyStore File Password]** Voer het wachtwoord voor het KeyStore-bestand in. Dit is _niet_ Het KeyStore-wachtwoord dat u in stap 5 hebt gemaakt, maar dat het KeyStore-bestandswachtwoord is Adobe, staat in het welkomstbericht dat u tijdens de provisioning ontvangt. Neem contact op met de klantenondersteuning van Adobe als u geen wachtwoord voor een KeyStore-bestand hebt ontvangen.
   * In de **[!UICONTROL Private Key Password]** Voer het wachtwoord voor de persoonlijke sleutel in (dit kan hetzelfde wachtwoord zijn als dat voor de vorige stap). Adobe geeft het wachtwoord voor de persoonlijke sleutel op in het welkomstbericht dat u tijdens de levering hebt ontvangen. Neem contact op met de klantenondersteuning van Adobe als u geen wachtwoord voor persoonlijke sleutels hebt ontvangen.
   * In de **[!UICONTROL Private Key Alias]** veld, voert u de alias van de persoonlijke sleutel in. Bijvoorbeeld, `companyname-alias`. Adobe geeft de alias voor de persoonlijke sleutel op in het welkomstbericht dat u tijdens de levering hebt ontvangen. Neem contact op met de klantenondersteuning van Adobe als u geen alias voor een persoonlijke sleutel hebt ontvangen.

   ![edit_settings_fordynamic-media-replication2](assets/edit_settings_fordynamic-media-replication2.png)

1. Tikken **[!UICONTROL Save & Close]** om uw wijzigingen in deze gebruiker op te slaan.

   Vervolgens moet u [vorm de replicatieagent.](#configuring-the-replication-agent)

### De Replication Agent configureren {#configuring-the-replication-agent}

1. Tik in AEM op het AEM-logo om toegang te krijgen tot de globale navigatieconsole en tik vervolgens op **[!UICONTROL Tools > Deployment > Replication > Agents on author]**.
1. Tik op de pagina Agents op de auteurspagina op **[!UICONTROL Dynamic Media Hybrid Image Replication (s7delivery)]**.
1. Tik op **[!UICONTROL Edit]**.
1. Tik op de knop **[!UICONTROL Settings]** en voert u het volgende in:

   * **[!UICONTROL Enabled]** - Schakel dit selectievakje in om de replicatieagent in te schakelen.
   * **[!UICONTROL Region]** - Instellen op het juiste gebied: Noord-Amerika, Europa of Azië
   * **[!UICONTROL Tenant ID]** - Deze waarde is de naam van uw bedrijf/huurder die aan de Dienst van de Replicatie publiceert. Deze waarde is de huurder-id die Adobe opgeeft in het welkomstbericht dat u tijdens de levering hebt ontvangen. Neem contact op met de klantenondersteuning van Adobe als u dit niet hebt ontvangen.
   * **[!UICONTROL Key Store Alias]** - Deze waarde is gelijk aan de waarde van** Nieuwe alias** die is ingesteld bij het genereren van de sleutel in [Verificatie instellen](#setting-up-authentication); bijvoorbeeld: `replication`. (Zie stap 7 in [Verificatie instellen](#setting-up-authentication).)
   * **[!UICONTROL Key Store Password]** - Dit is het KeyStore-wachtwoord dat is gemaakt toen u op **[!UICONTROL Create KeyStore]**. Adobe geeft dit wachtwoord niet op. Zie stap 5 van [Verificatie instellen](#setting-up-authentication).

   In de volgende afbeelding ziet u de replicatieagent met voorbeeldgegevens:

   ![chlimage_1-509](assets/chlimage_1-509.png)

1. Tik op **[!UICONTROL OK]**.

### De Replication Agent for Dynamic Media valideren {#validating-the-replication-agent-for-dynamic-media}

Ga als volgt te werk om de replicatieagent voor dynamische media te valideren:

Tik op **[!UICONTROL Test Connection]**. Voorbeeld-uitvoer is als volgt:

```shell
11.03.2016 10:57:55 - Transferring content for ReplicationAction{type=TEST, path[0]='/content/dam', time=1457722675402, userId='admin', revision='null'}
11.03.2016 10:57:55 - * Auth User: replication-receiver
11.03.2016 10:57:55 - * HTTP Version: 1.1
11.03.2016 10:57:55 - * Using OAuth 2.0 Authorization Grants
11.03.2016 10:57:55 - * OAuth 2.0 User: dynamic-media-replication
11.03.2016 10:57:55 - * OAuth 2.0 Token: '*****' initialized
11.03.2016 10:57:55 - Publishing: POST[https://replicate-na.assetsadobe.com:8580/is-publish/publish-receiver?Cmd=Test&RootId=xfpuu-6613]
11.03.2016 10:57:55 - Publish response: OK[]
11.03.2016 10:57:55 - Transfer succeeded in 141 ms for ReplicationAction{type=TEST, path[0]='/content/dam', time=1457722675402, userId='admin', revision='null'}
-------------------------------------------------------------------------------------------------------------------------------
Replication test succeeded
```

>[!NOTE]
U kunt ook op een van de volgende manieren controleren:
* Controleer de replicatielogboeken om ervoor te zorgen het middel wordt herhaald.
* Publiceer een afbeelding. Tik op de afbeelding en selecteer **[!UICONTROL Viewers]** in vervolgkeuzemenu. Selecteer een viewervoorinstelling en tik vervolgens op **[!UICONTROL URL]** en kopieer en plak de URL in de browser om te controleren of de afbeelding zichtbaar is.


### Problemen met verificatie oplossen {#troubleshooting-authentication}

Bij het instellen van verificatie zijn er enkele problemen die u kunt oplossen. Controleer voordat u deze inschakelt of u replicatie hebt ingesteld.

#### Probleem: HTTP-statuscode 401 met bericht - Autorisatie vereist {#problem-http-status-code-with-message-authorization-required}

Dit probleem kan worden veroorzaakt doordat KeyStore niet is ingesteld voor `dynamic-media-replication` gebruiker.

```shell
Replication test to s7delivery:https://s7bern.macromedia.com:8580/is-publish/
17.06.2016 18:54:43 - Transferring content for ReplicationAction{type=TEST, path[0]='/content/dam', time=1466214883309, userId='admin', revision='null'}
17.06.2016 18:54:43 - * Auth User: replication-receiver
17.06.2016 18:54:43 - * HTTP Version: 1.1
17.06.2016 18:54:43 - * Using OAuth 2.0 Authorization Grants
17.06.2016 18:54:43 - * OAuth 2.0 User: dynamic-media-replication
17.06.2016 18:54:43 - No OAuth token available. OAuth not initialized
17.06.2016 18:54:43 - * Using Client Auth SSL alias - replication-alias *
17.06.2016 18:54:43 - Publishing: POST[https://<localhost>:8580/is-publish//publish-receiver?Cmd=Test&RootId=brough]
17.06.2016 18:54:43 - Transfer failed for ReplicationAction{type=TEST, path[0]='/content/dam', time=1466214883309, userId='admin', revision='null'}. java.io.IOException: Failed to execute request
'https://<localhost>:8580/is-publish//publish-receiver?Cmd=Test&RootId=brough':
 Server returned status code 401 with message: Authorization required.
17.06.2016 18:54:43 - Error while replicating: com.day.cq.replication.ReplicationException: Transfer failed for ReplicationAction{type=TEST, path[0]='/content/dam', time=1466214883309,
 userId='admin', revision='null'}. java.io.IOException: Failed to execute request
'https://<localhost>:8580/is-publish//publish-receiver?Cmd=Test&RootId=brough':
 Server returned status code 401 with message: Authorization required.
```

**Oplossing**: Controleer of de `KeyStore` is opgeslagen naar **[!UICONTROL dynamic-media-replication]** en wordt voorzien van het juiste wachtwoord.

#### Probleem: Kan sleutel niet decoderen - kan gegevens niet decoderen {#problem-could-not-decrypt-key-could-not-decrypt-data}

```xml
Replication test to s7delivery:https://<localhost>:8580/is-publish/
17.06.2016 19:00:16 - Transferring content for ReplicationAction{type=TEST, path[0]='/content/dam', time=1466215216662, userId='admin', revision='null'}
17.06.2016 19:00:16 - * Auth User: replication-receiver
17.06.2016 19:00:16 - * HTTP Version: 1.1
17.06.2016 19:00:16 - * Using OAuth 2.0 Authorization Grants
17.06.2016 19:00:16 - * OAuth 2.0 User: dynamic-media-replication
17.06.2016 19:00:16 - No OAuth token available. OAuth not initialized
17.06.2016 19:00:16 - * Using Client Auth SSL alias - replication-alias *
17.06.2016 19:00:16 - Transfer failed for ReplicationAction{type=TEST, path[0]='/content/dam', time=1466215216662, userId='admin', revision='null'}. java.lang.SecurityException: java.security.UnrecoverableKeyException: Could not decrypt key: Could not decrypt data.
```

**Oplossing**: Controleer het wachtwoord. Het wachtwoord in de replicatieagent wordt opgeslagen is niet het zelfde wachtwoord dat werd gebruikt om keystore tot stand te brengen dat.

#### Probleem: InvalidAlgorithmParameterException {#problem-invalidalgorithmparameterexception}

Dit probleem wordt veroorzaakt door een configuratiefout in uw AEM Auteur-instantie. Het Java-proces op de auteur krijgt niet de juiste `javax.net.ssl.trustStore`. U ziet deze fout in het replicatielogboek:

```shell
14.04.2016 09:37:43 - Transfer failed for ReplicationAction{type=TEST, path[0]='/content/dam', time=1460651862089, userId='admin', revision='null'}. java.io.IOException: Failed to execute request 'https://<localhost>:8580/is-publish/publish-receiver?Cmd=Test&RootId=rbrough-osx2': java.lang.RuntimeException: Unexpected error: java.security.InvalidAlgorithmParameterException: the trustAnchors parameter must be non-empty
14.04.2016 09:37:43 - Error while replicating: com.day.cq.replication.ReplicationException: Transfer failed for ReplicationAction{type=TEST, path[0]='/content/dam', time=1460651862089, userId='admin', revision='null'}. java.io.IOException: Failed to execute request 'https://<localhost>:8580/is-publish/publish-receiver?Cmd=Test&RootId=rbrough-osx2': java.lang.RuntimeException: Unexpected error: java.security.InvalidAlgorithmParameterException: the trustAnchors parameter must be non-empty
```

Of het foutenlogboek:

```shell
07.25.2019 12:00:59.893 *ERROR* [sling-threadpool-db2763bb-bc50-4bb5-bb64-10a09f432712-(apache-sling-job-thread-pool)-90-com_day_cq_replication_job_s7delivery(com/day/cq/replication/job/s7delivery)] com.day.cq.replication.Agent.s7delivery.queue Error during processing of replication.
 
java.io.IOException: Failed to execute request 'https://replicate-na.assetsadobe.com:8580/is-publish/publish-receiver?Cmd=Test&RootId=rbrough-osx': java.lang.RuntimeException: Unexpected error: java.security.InvalidAlgorithmParameterException: the trustAnchors parameter must be non-empty
        at com.scene7.is.catalog.service.publish.atomic.PublishingServiceHttp.executePost(PublishingServiceHttp.scala:195)
```

**Oplossing**: Zorg ervoor dat het Java-proces op de AEM-auteur de eigenschap system heeft **-Djavax.net.ssl.trustStore=** ingesteld op een geldige truststore.

#### Probleem: KeyStore is niet ingesteld of is niet geïnitialiseerd {#problem-keystore-is-either-not-set-up-or-it-is-not-initialized}

Dit probleem kan worden veroorzaakt door een hotfix of een functiepakket dat het **[!UICONTROL dynamic-media-user]** of **[!UICONTROL keystore]** knooppunt.

Voorbeeld van replicatielogboek:

```shell
Replication test to s7delivery:https://replicate-na.assetsadobe.com/is-publish
02.08.2016 14:37:44 - Transferring content for ReplicationAction{type=TEST, path[0]='/content/dam', time=1470173864834, userId='admin', revision='null'}
02.08.2016 14:37:44 - * Auth User: replication-receiver
02.08.2016 14:37:44 - * HTTP Version: 1.1
02.08.2016 14:37:44 - * Using OAuth 2.0 Authorization Grants
02.08.2016 14:37:44 - * OAuth 2.0 User: dynamic-media-replication
02.08.2016 14:37:44 - Transfer failed for ReplicationAction{type=TEST, path[0]='/content/dam', time=1470173864834, userId='admin', revision='null'}. com.adobe.granite.keystore.KeyStoreNotInitialisedException: Uninitialised key store for user dynamic-media-replication
```

**Oplossing**:

1. Ga naar de **[!UICONTROL User Management]** pagina:

   `localhost:4502/libs/granite/security/content/useradmin.html`
1. Op de **[!UICONTROL User Management]** pagina, naar de **[!UICONTROL dynamic-media-replication]** gebruiker, tikt u vervolgens om te openen.
1. Tik op het tabblad **[!UICONTROL KeyStore]**. Als de **[!UICONTROL Create KeyStore]** verschijnt, moet u de stappen onder opnieuw uitvoeren [Verificatie instellen](#setting-up-authentication) eerder.
1. Als u de **[!UICONTROL KeyStore]** instellen, moet u mogelijk [De Replication Agent configureren](config-dynamic.md#configuring-the-replication-agent) ook hier weer.

   Wijzig de s7delivery Replication Agent.

   `localhost:4502/etc/replication/agents.author/s7delivery.html`

1. Tikken **[!UICONTROL Test Connection]** om te controleren of de configuratie geldig is.

#### Probleem: Publish Agent gebruikt SSL in plaats van OAuth {#problem-publish-agent-is-using-ssl-instead-of-oauth}

Dit probleem kan worden veroorzaakt door een hotfix of een functiepakket die niet correct hebben geïnstalleerd of de instellingen overschrijven.

Voorbeeld van replicatielogboek:

```shell
01.08.2016 18:42:59 - Transferring content for ReplicationAction{type=TEST, path[0]='/content/dam', time=1470073379634, userId='admin', revision='null'}
01.08.2016 18:42:59 - * Auth User: replication-receiver
01.08.2016 18:42:59 - * HTTP Version: 1.1
01.08.2016 18:42:59 - * Using Client Auth SSL alias - replication-receiver *
01.08.2016 18:42:59 - Publishing: POST[https://replicate-eu.assetsadobe2.com:443/is-publish/publish-receiver?Cmd=Test&RootId=altayerstaging]
01.08.2016 18:42:59 - Transfer failed for ReplicationAction{type=TEST, path[0]='/content/dam', time=1470073379634, userId='admin', revision='null'}. java.io.IOException: Failed to execute request 'https://replicate-eu.assetsadobe2.com:443/is-publish/publish-receiver?Cmd=Test&RootId=rbroughstaging': Server returned status code 401 with message: Authorization required.
01.08.2016 18:42:59 - Error while replicating: com.day.cq.replication.ReplicationException: Transfer failed for ReplicationAction{type=TEST, path[0]='/content/dam', time=1470073379634, userId='admin', revision='null'}. java.io.IOException: Failed to execute request 'https://replicate-eu.assetsadobe2.com:443/is-publish/publish-receiver?Cmd=Test&RootId=rbroughstaging': Server returned status code 401 with message: Authorization required.
```

**Oplossing:**

1. Tik in AEM op **[!UICONTROL Tools >  General > CRXDE Lite]**.

   `localhost:4502/crx/de/index.jsp`

1. Ga naar de **[!UICONTROL s7delivery Replication Agent]** knooppunt.

   `localhost:4502/crx/de/index.jsp#/etc/replication/agents.author/s7delivery/jcr:content`

1. Deze instelling toevoegen aan de replicatieagent (Boolean met waarde ingesteld op **[!UICONTROL True]**):

   `enableOauth=true`

1. Tik in de linkerbovenhoek van de pagina op **[!UICONTROL Save All]**.

### Uw configuratie testen {#testing-your-configuration}

Adobe adviseert dat u een test van begin tot eind van de configuratie uitvoert.

Zorg ervoor dat u het volgende al hebt gedaan voordat u met deze test begint:

* Voorinstellingen voor toegevoegde afbeelding.
* Configureren **Dynamic Media-configuratie (ouder dan 6.3)** krachtens **[!UICONTROL Cloud Services]**. De afbeeldingsservice-URL is vereist voor deze test

Om uw configuratie te testen:

1. Upload een afbeeldingselement. (Tik in Elementen op **[!UICONTROL Create > Files]** en selecteer het bestand.)
1. Wacht tot de workflow is voltooid.
1. Publiceer het afbeeldingselement. (Selecteer het element en tik op **[!UICONTROL Quick Publish]**.)
1. Navigeer naar de uitvoeringen voor die afbeelding door de afbeelding te openen en te tikken **[!UICONTROL Renditions]**.

   ![chlimage_1-510](assets/chlimage_1-510.png)

1. Selecteer een dynamische vertoning.
1. Tikken **[!UICONTROL URL]** om de URL voor dit element te verkrijgen.
1. Navigeer naar de geselecteerde URL en controleer of de afbeelding zich naar behoren gedraagt.

U kunt ook testen of uw elementen zijn geleverd door req=exists aan uw URL toe te voegen.

## Dynamic Media-Cloud Services configureren {#configuring-dynamic-media-cloud-services}

De Dynamic Media Cloud-service biedt ondersteuning voor cloudservices, zoals hybride publicatie en levering van beelden en video, videoanalyse en videocodering.

Als onderdeel van de configuratie moet u een registratie-id, een URL voor de videoservice, een URL voor de afbeeldingsservice, een URL voor de replicatieservice en een verificatieverificatie invoeren. U zou al deze informatie als deel van het proces van de rekeninglevering moeten ontvangen. Als u deze gegevens niet hebt ontvangen, neemt u contact op met de Adobe Experience Manager Administrator of Adobe Technical Support om deze gegevens te vragen.

>[!NOTE]
Voordat u Dynamic Media-Cloud Services instelt, moet u eerst uw publicatieexemplaar hebben ingesteld. U moet ook replicatie hebben opstelling alvorens de Cloud Services van Dynamic Media te vormen.

**Dynamische mediawolkenservices configureren**:

1. Tik in AEM op het AEM logo om toegang te krijgen tot de algemene navigatieconsole en tik op **[!UICONTROL Tools > Cloud Services > Dynamic Media Configuration (Pre-6.3)]**.
1. Op de **[!UICONTROL Dynamic Media Configuration Browser]** pagina, selecteert u in het linkervenster de optie **[!UICONTROL global]** tikt u vervolgens op **[!UICONTROL Create]**.
1. In de **[!UICONTROL Create Dynamic Media Configuration]** in het dialoogvenster **[!UICONTROL Title]** veld, typt u een titel.
1. Als u Dynamic Media for video configureert,

   * In de **[!UICONTROL Registration ID]** veld, typt u uw registratie-id.
   * In de **[!UICONTROL Video Service URL]** Voer de URL van de videoservice voor de Dynamic Media Gateway in.

1. Als u Dynamic Media configureert voor beeldbewerking, kunt u het volgende doen: **[!UICONTROL Image Service URL]** Voer de URL van de afbeeldingsservice voor de Dynamic Media Gateway in.
1. Tikken **[!UICONTROL Save]** om terug te keren naar de Dynamic Media Configuration Browser-pagina.
1. Tik op het AEM om de globale navigatieconsole te openen.

## Video-rapportage configureren {#configuring-video-reporting}

U kunt videoverslagen over veelvoudige installaties van AEM vormen gebruikend Dynamic Media - Hybride wijze.

**Wanneer gebruiken:** Op dat moment configureert u **[!UICONTROL Dynamic Media Configuration (Pre 6.3)]** Er zijn veel functies gestart, waaronder videoberichten. De configuratie leidt tot een rapportreeks in een regionaal bedrijf Analytics. Als u veelvoudige knopen van de Auteur vormt, creeert u een afzonderlijke rapportreeks voor elke. Dit heeft tot gevolg dat de rapportage van gegevens tussen de installaties inconsistent is. Bovendien als elke knoop van de Auteur naar de zelfde Hybride Publish server verwijst, verandert de laatste installatie van de Auteur de reeks van het bestemmingsrapport voor al videorapportering. Deze kwestie overlaadt het systeem van Analytics met teveel rapportseries.

**Aan de slag:** Configureer videomelding door de volgende drie taken uit te voeren.

1. Een [!DNL Video Analytics] vooraf ingesteld pakket nadat u hebt geconfigureerd **[!UICONTROL Dynamic Media Configuration (Pre 6.3)]** op het eerste auteurknooppunt. Deze aanvankelijke taak is belangrijk omdat het een nieuwe configuratie toestaat om het gebruiken van de zelfde rapportreeks voort te zetten.
1. Installeer de [!DNL Video Analytics] pakket met voorinstellingen ***new*** Auteur-knooppunt ***voor*** U configureert Dynamic Media Configuration (Pre 6.3).

1. Verifieer en zuivert de pakketinstallatie.

### Een [!DNL Video Analytics] vooraf ingesteld pakket na het configureren van het eerste knooppunt Auteur {#creating-a-video-analytics-preset-package-after-configuring-the-first-author-node}

Wanneer u deze taak hebt voltooid, beschikt u over een pakketbestand met de [!DNL Video Analytics] voorinstellingen. Deze voorinstellingen bevatten een rapportsuite, de trackingserver, de naamruimte voor bijhouden en de Marketing Cloud-organisatie-id, indien beschikbaar.

1. Als u dit nog niet hebt gedaan, configureert u **[!UICONTROL Dynamic Media Configuration (Pre 6.3)]**.
1. (Optioneel) U kunt de **[!UICONTROL Report Suite ID]** (u moet toegang hebben tot het JCR). Terwijl u **[!UICONTROL Report Suite ID]** is niet vereist, wordt validatie eenvoudiger.
1. Een pakket maken met **[!UICONTROL Package Manager]**.
1. Bewerk het pakket om een filter op te nemen.

   In AEM: `/conf/global/settings/dam/dm/presets/analytics/jcr:content/userdata`

1. Maak het pakket.
1. Download of deel de [!DNL Video Analytics] vooraf ingesteld pakket zodat het kan worden gedeeld met volgende nieuwe auteurknooppunten.

### De installatie van de [!DNL Video Analytics] vooraf ingesteld pakket voordat u extra Auteur-knooppunten configureert {#installing-the-video-analytics-preset-package-before-you-configure-additional-author-nodes}

Zorg ervoor dat u deze taak uitvoert _voor_ u vormt **[!UICONTROL Dynamic Media Configuration (Pre 6.3)]**. Als u dit niet doet, wordt er een andere ongebruikte rapportsuite gemaakt. Bovendien, alhoewel de video het melden correct zal blijven werken, wordt het verzamelen van gegevens niet geoptimaliseerd.

Zorg ervoor dat de [!DNL Video Analytics] Het vooraf ingestelde pakket van het eerste auteurknooppunt is toegankelijk op het nieuwe auteurknooppunt.

1. Upload de [!DNL Video Analytics] vooraf ingesteld pakket dat u eerder hebt gemaakt naar **[!UICONTROL Package Manager]**.
1. Installeer de [!DNL Video Analytics] vooraf ingesteld pakket.
1. Configureren **[!UICONTROL Dynamic Media Configuration (Pre 6.3)]**.

### De pakketinstallatie controleren en fouten opsporen {#verifying-and-debugging-the-package-installation}

1. Voer een van de volgende handelingen uit om de installatie van het pakket te controleren en, indien nodig, fouten op te sporen:

   * **Controleer de [!DNL Video Analytics] door middel van het JCR vooraf ingesteld**
Als u de opdracht [!DNL Video Analytics] via het JCR vooraf instellen, moet u toegang hebben tot **[!UICONTROL CRXDE Lite]**.

      AEM - In **[!UICONTROL CRXDE Lite]**, navigeer naar `/conf/global/settings/dam/dm/presets/analytics/jcr:content/userdata  `

      Dat is `http://localhost:4502/crx/de/index.jsp#/conf/global/settings/dam/dm/presets/analytics/jcr%3Acontent/userdata`

      Als u geen toegang hebt tot **[!UICONTROL CRXDE Lite]** in het knooppunt Auteur kunt u de voorinstelling controleren via de server Publiceren.

   * **Controleer de [!DNL Video Analytics] via de afbeeldingsserver vooraf instellen**

      U kunt de [!DNL Video Analytics] rechtstreeks vooraf instellen door een afbeeldingsserver te maken `req=userdata` verzoek.

      Als u bijvoorbeeld het dialoogvenster [!DNL Video Analytics] In het knooppunt Auteur kunt u de volgende aanvraag indienen:

      `http://localhost:4502/is/image/conf/global/settings/dam/dm/presets/analytics?req=userdata`

      Als u de voorinstelling wilt valideren op publicatieservers, kunt u een vergelijkbare directe aanvraag indienen bij de publicatieserver. De reacties zijn hetzelfde op de knooppunten Auteur en Publiceren. De reactie ziet er ongeveer als volgt uit:

      ```
      marketingCloudOrgId=0FC4E86B573F99CC7F000101
       reportSuite=aemaem6397618-2018-05-23
       trackingNamespace=aemvideodal
       trackingServer=aemvideodal.d2.sc.omtrdc.net
      ```

   * **Controleer de [!DNL Video Analytics] vooraf ingesteld via het gereedschap Video melden in AEM**

      Tik op **[!UICONTROL Tools > Assets > Video Reporting]** `http://localhost:4502/mnt/overlay/dam/gui/content/s7dam/videoreports/videoreport.html`

      Als u het volgende foutbericht ziet, is de rapportsuite beschikbaar, maar niet gevuld. Deze fout is correct-en gewenst-in een nieuwe installatie alvorens het systeem om het even welke gegevens verzamelt.

      ![screen_shot_2018-05-23at52254pm](assets/screen_shot_2018-05-23at52254pm.png)
   Als u rapportgegevens wilt genereren, uploadt en publiceert u één video. Gebruiken **[!UICONTROL Copy URL]** en voer de video minstens één keer uit.

   Houd er rekening mee dat het maximaal 12 uur kan duren voordat de rapportgegevens zijn gevuld met het gebruik van de Video Viewer.

   Als er een fout is en de rapportreeks niet correct wordt geplaatst, wordt het volgende alarm getoond.

   ![screen_shot_2018-05-23at52612pm](assets/screen_shot_2018-05-23at52612pm.png)

   Deze fout wordt ook weergegeven als Video Reporting wordt uitgevoerd voordat u configureert **[!UICONTROL Dynamic Media Configuration (Pre 6.3)]** diensten.

### Het oplossen van problemen de video rapporteringsconfiguratie {#troubleshooting-the-video-reporting-configuration}

* Tijdens de installatie zijn soms verbindingen met de Analytics API-server onderbroken. De installatie probeert de verbinding 20 keer opnieuw, maar het ontbreekt nog. Wanneer deze situatie voorkomt, registreert het logboekdossier veelvoudige fouten. Zoeken naar `SiteCatalystReportService`.
* Niet installeren [!DNL Video Analytics] Het vooraf ingestelde pakket kan eerst de verwezenlijking van een nieuwe rapportreeks veroorzaken.
* De bevordering van AEM 6.3 aan AEM 6.4 of AEM 6.4.1, dan vormend **[!UICONTROL Dynamic Media Configuration (Pre 6.3)]**, maakt nog steeds een rapportsuite. Dit probleem is bekend en moet worden opgelost voor AEM 6.4.2.

### Over het [!DNL Video Analytics] voorinstelling {#about-the-video-analytics-preset}

De [!DNL Video Analytics] De voorinstelling (ook wel analysevoorinstelling genoemd) wordt naast de voorinstellingen van de viewer in Dynamic Media opgeslagen. Het is in feite hetzelfde als een viewervoorinstelling, maar met informatie die wordt gebruikt om AppMeasurement- en Video Heartbeat-rapportage te configureren.

De eigenschappen van de voorinstelling zijn als volgt:

* **[!UICONTROL reportSuite]**
* **[!UICONTROL trackingServer]**
* **[!UICONTROL trackingNamespace]**
* **[!UICONTROL marketingCloudOrgId]** (niet aanwezig in oudere AEM versies)

AEM 6.4 en nieuwere versies opslaan deze voorinstelling op `/conf/global/settings/dam/dm/presets/analytics/jcr:content/userdata`

## Catalogusinstellingen worden gerepliceerd {#replicating-catalog-settings}

U moet uw eigen standaardinstellingen voor de catalogus publiceren als onderdeel van het installatieproces via het JCR. Catalogusinstellingen herhalen:

1. In een Eindvenster, stel het volgende in werking:

   `curl -u admin:admin localhost:4502/libs/settings/dam/dm/presets/viewer.pushviewerpresets`

1. Navigeer AEM naar de volgende locatie in **[!UICONTROL CRXDE Lite]** (vereist beheerdersrechten):

   `https://<server>:<port>/crx/de/index.jsp#/conf/global/settings/dam/dm/imageserver/`

1. Tik op het tabblad **[!UICONTROL Replication]**. 
1. Tik op **[!UICONTROL Replicate]**.

## Viewer-voorinstellingen repliceren {#replicating-viewer-presets}

Als u een element met een viewervoorinstelling wilt leveren, moet u de viewervoorinstelling repliceren of publiceren. (Alle viewervoorinstellingen moeten zijn geactiveerd _en_ gerepliceerd om de URL of insluitcode voor een element te verkrijgen.) Zie [Voorinstellingen van viewer publiceren](managing-viewer-presets.md#publishing-viewer-presets) voor meer informatie .

>[!NOTE]
Standaard worden in het systeem verschillende uitvoeringen weergegeven wanneer u **[!UICONTROL Renditions]** en diverse viewervoorinstellingen wanneer u **[!UICONTROL Viewers]** in de gedetailleerde weergave van het element. U kunt het aantal dat u ziet verhogen of verlagen. Zie [Het aantal voorinstellingen voor afbeeldingen dat wordt weergegeven verhogen](/help/assets/managing-image-presets.md#increasing-or-decreasing-the-number-of-image-presets-that-display) of [Het aantal weergavevoorinstellingen voor viewers vergroten](/help/assets/managing-viewer-presets.md#increasing-the-number-of-viewer-presets-that-display).

## Elementen filteren voor replicatie {#filtering-assets-for-replication}

Bij niet-Dynamic Media-implementaties repliceert u _alles_ elementen (zowel afbeeldingen als video) van de AEM auteur naar het AEM publicatieknooppunt. Deze workflow is nodig omdat de AEM ook de middelen levert.

Bij Dynamic Media-implementaties is het echter niet nodig om dezelfde middelen te repliceren naar publicatieknooppunten, omdat assets via de cloud worden geleverd. AEM publicatieknooppunten moeten echter niet worden gerepliceerd. Zo voorkomt u extra opslagkosten en langere verwerkingstijden om elementen te repliceren. Andere inhoud, zoals Dynamic Media-viewers, sitepagina&#39;s en statische inhoud, wordt nog steeds aangeboden vanaf de AEM publicatieknooppunten.

Naast het repliceren van de activa, worden de volgende niet-activa ook herhaald:

* Dynamic Media-leveringsconfiguratie: `/conf/global/settings/dam/dm/imageserver/configuration/jcr:content/settings`
* Voorinstellingen afbeelding: `/conf/global/settings/dam/dm/presets/macros`
* Voorinstellingen viewer: `/conf/global/settings/dam/dm/presets/viewer`

Met de filters kunt u _uitsluiten_ elementen die worden gerepliceerd naar het AEM publicatieknooppunt.

### Standaardelementfilters gebruiken voor replicatie {#using-default-asset-filters-for-replication}

Als u Dynamic Media for 1 gebruikt, kunt u afbeeldingen in productie nemen _of_ 2) beelden en video, dan kunt u de standaardfilters gebruiken die wij ongewijzigd verstrekken. De volgende filters zijn standaard actief:

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td><strong>Filter</strong></td> 
   <td><strong>Mimetype</strong></td> 
   <td><strong>Uitvoeringen</strong></td> 
  </tr> 
  <tr> 
   <td>Afbeeldingslevering Dynamic Media</td> 
   <td><p>filterafbeeldingen</p> <p>filtersets</p> <p> </p> </td> 
   <td><p>Begint met <strong>image/</strong></p> <p>Bevat <strong>application/</strong> en eindigt met <strong>set</strong>.</p> </td> 
   <td>De 'filter-images' die buiten het vak (voor afzonderlijke afbeeldingselementen, waaronder interactieve afbeeldingen) en 'filtersets' (voor centrifuges, afbeeldingssets, gemengde mediasets en Carousel-sets) worden gebruikt, zijn: 
    <ul> 
     <li>Inclusief PTIFF-afbeeldingen en metagegevens voor replicatie (elke uitvoering die begint met <strong>cqdam</strong>).</li> 
     <li>Sluit de oorspronkelijke afbeelding en statische afbeeldingsuitvoeringen uit van replicatie.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>Dynamic Media Video Delivery</td> 
   <td>filter-video</td> 
   <td>Begint met <strong>video/</strong></td> 
   <td>De uit-van-de-doos "filter-video"zal: 
    <ul> 
     <li>Inclusief proxy-video-uitvoeringen, videominiatuur/posterafbeelding, metagegevens (zowel bij bovenliggende video als bij video-uitvoeringen) voor replicatie (Willekeurige uitvoering die begint met <strong>cqdam</strong>).</li> 
     <li>Sluit de originele video en statische miniatuuruitvoeringen uit van replicatie.<br /> <br /> <strong>Opmerking:</strong> De proxy-video-uitvoeringen bevatten geen binaire elementen, maar zijn in plaats daarvan alleen knooppunteigenschappen. Er is dus geen invloed op de grootte van de uitgeversopslagplaats.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>Dynamic Media Classic-integratie</td> 
   <td><p>filterafbeeldingen</p> <p>filtersets</p> <p>filter-video</p> </td> 
   <td><p>Begint met <strong>image/</strong></p> <p>Bevat <strong>application/</strong> en eindigt met <strong>set</strong>.</p> <p>Begint met <strong>video/</strong></p> </td> 
   <td><p>U vormt het Vervoer URI om aan uw AEM te richten publiceert server in plaats van de Adobe Dynamic Media Cloud Replication Service URL. Als u dit filter instelt, kan Dynamic Media Classic elementen leveren in plaats van AEM publicatie-instantie.</p> <p>Met de 'filter-images', 'filtersets' en 'filter-video' uit de box worden:</p> 
    <ul> 
     <li>Inclusief PTIFF-afbeelding, proxyvideo-uitvoeringen en metagegevens voor replicatie. Maar omdat ze niet bestaan in het JCR-programma voor AEM - integratie in Dynamic Media Classic - doet het in feite niets.</li> 
     <li>Sluit de oorspronkelijke afbeelding, statische afbeeldingsuitvoeringen, oorspronkelijke video en statische miniatuuruitvoeringen uit van replicatie. In plaats daarvan levert Dynamic Media Classic afbeeldingen en video-elementen.</li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
Filters zijn van toepassing op MIME-typen en kunnen geen padspecifieke notatie hebben.

### Elementfilters instellen voor uitsluitend video-implementaties {#setting-up-asset-filters-for-video-only-deployments}

Als u Dynamic Media alleen voor video gebruikt, voert u de volgende stappen uit om elementfilters voor replicatie in te stellen:

1. Tik in AEM op het AEM logo om toegang te krijgen tot de algemene navigatieconsole en tik op **[!UICONTROL Tools > Deployment > Replication > Agents on author]**.
1. Tik op de pagina Agents op de auteurspagina op **[!UICONTROL Default Agent (publish)]**.
1. Tik op **[!UICONTROL Edit]**.
1. In de **[!UICONTROL Agent Settings]** in het dialoogvenster [!UICONTROL Settings] tab, check **[!UICONTROL Enabled]** om de agent in te schakelen.
1. Tik op **[!UICONTROL OK]**.
1. Tik in AEM op **[!UICONTROL Tools > General > CRXDE Lite]**.
1. Navigeer in de linkermappenstructuur naar `/etc/replication/agents.author/dynamic_media_replication/jcr:content/damRenditionFilters`
1. Zoeken [!UICONTROL filter-video], klikt u er met de rechtermuisknop op en selecteert u **[!UICONTROL Copy]**.
1. Navigeer in de linkermappenstructuur naar `/etc/replication/agents.author/publish`
1. Zoeken [!UICONTROL jcr:content], klikt u er met de rechtermuisknop op en selecteert u **[!UICONTROL Paste]**.

Hiermee wordt de AEM-publicatie-instantie zo ingesteld dat zowel de videoposterafbeelding als de videometagegevens worden geleverd die zijn vereist voor het afspelen, terwijl de video zelf wordt geleverd door de Dynamic Media-cloudservice. Het filter sluit ook de originele video en statische miniatuuruitvoeringen uit van replicatie, die niet nodig zijn voor de publicatie-instantie.

### Elementfilters instellen voor imaging bij implementaties buiten de productie {#setting-up-asset-filters-for-imaging-in-non-production-deployments}

Als u Dynamic Media gebruikt voor het maken van images in implementaties die niet voor productiedoeleinden worden gebruikt, voert u de volgende stappen uit om elementfilters voor replicatie in te stellen:

1. Tik in AEM op het AEM logo om toegang te krijgen tot de algemene navigatieconsole en tik op **[!UICONTROL Tools > Deployment > Replication > Agents on author]**.
1. Tik op de pagina Agents op de auteurspagina op **[!UICONTROL Default Agent (publish)]**.
1. Tik op **[!UICONTROL Edit]**.
1. In de **[!UICONTROL Agent Settings]** in het dialoogvenster **[!UICONTROL Settings]** tab, check **[!UICONTROL Enabled]** om de agent in te schakelen.
1. Tik op **[!UICONTROL OK]**.
1. Tik in AEM op **[!UICONTROL Tools > General > CRXDE Lite]**.
1. Navigeer in de linkermappenstructuur naar `/etc/replication/agents.author/dynamic_media_replication/jcr:content/damRenditionFilters`

   ![image-2018-01-16-10-22-40-410](assets/image-2018-01-16-10-22-40-410.png)

1. Zoeken **[!UICONTROL filter-images]**, klikt u er met de rechtermuisknop op en selecteert u **[!UICONTROL Copy]**.
1. Navigeer in de linkermappenstructuur naar `/etc/replication/agents.author/publish`
1. Zoeken **[!UICONTROL jcr:content]**, klikt u er met de rechtermuisknop op en selecteert u **[!UICONTROL Create > Create Node]**. Voer de naam in `damRenditionFilters` van het type `nt:unstructured`.
1. Zoeken [!UICONTROL `damRenditionFilters`], klikt u er met de rechtermuisknop op en selecteert u **[!UICONTROL Paste]**.

Hiermee wordt de AEM-publicatie-instantie zo ingesteld dat de afbeeldingen worden geleverd aan uw niet-productieomgeving. Het filter sluit ook de oorspronkelijke afbeelding en statische uitvoeringen uit van replicatie, die niet nodig zijn voor de publicatie-instantie.

>[!NOTE]
Als er vele verschillende filters in een auteur zijn, heeft elke agent een verschillende gebruiker nodig die aan het wordt toegewezen. De granietcode dwingt het model van één filter per gebruiker af. Voor elke filterinstelling moet er altijd een andere gebruiker zijn.
Als u meer dan één filter op een server-bijvoorbeeld gebruikt, één filter voor replicatie om te publiceren en een tweede filter voor s7delivery-dan moet u ervoor zorgen dat deze twee filters een verschillend hebben **userId** die aan hen in **[!UICONTROL jcr:content]** knooppunt. Zie de volgende afbeelding:

![image-2018-01-16-10-26-28-465](assets/image-2018-01-16-10-26-28-465.png)

### Elementfilters aanpassen voor replicatie {#customizing-asset-filters-for-replication}

Elementfilters optioneel aanpassen voor replicatie:

1. Tik in AEM op het AEM logo om toegang te krijgen tot de algemene navigatieconsole en tik op **[!UICONTROL Tools > General > CRXDE Lite]**.
1. Navigeer in de linkermappenstructuur naar `/etc/replication/agents.author/dynamic_media_replication/jcr:content/damRenditionFilters` om de filters te bekijken.

   ![chlimage_1-511](assets/chlimage_1-511.png)

1. Als u het Mime-type voor het filter wilt definiëren, gaat u als volgt naar het Mime-type:

   Vouw in de linkerspoorstaaf uit **[!UICONTROL content > dam > <`locate_your_asset`> > jcr:content > metadata]** en vervolgens in de tabel, zoekt u `dc:format`.

   De volgende afbeelding is een voorbeeld van het pad van een element naar `dc:format`.

   ![chlimage_1-512](assets/chlimage_1-512.png)

   Let erop dat de `dc:format` voor het actief `Fiji Red.jpg` is `image/jpeg`.

   Als u dit filter wilt toepassen op alle afbeeldingen, ongeacht de indeling, stelt u de waarde in op `image/*` waar `*` is een reguliere expressie die wordt toegepast op alle afbeeldingen in elke indeling.

   Als u het filter alleen wilt toepassen op afbeeldingen van het type JPEG, voert u een waarde in van `image/jpeg`.

1. Bepaal welke uitvoeringen u van replicatie wilt omvatten of uitsluiten.

   U kunt onder andere de volgende tekens gebruiken om te filteren voor replicatie:

<table> 
 <tbody> 
  <tr> 
   <td><strong>Te gebruiken teken</strong></td> 
   <td><strong>Hoe het activa voor replicatie filtreert</strong></td> 
  </tr> 
  <tr> 
   <td>*</td> 
   <td>Jokerteken<br /> </td> 
  </tr> 
  <tr> 
   <td>+</td> 
   <td>Omvat activa voor replicatie.</td> 
  </tr> 
  <tr> 
   <td>-</td> 
   <td>Sluit elementen van replicatie uit.</td> 
  </tr> 
 </tbody> 
</table>

Ga naar `content/dam/<locate_your_asset>/jcr:content/renditions`.

De volgende afbeelding is een voorbeeld van de uitvoeringen van een element.

![chlimage_1-513](assets/chlimage_1-513.png)

Als u het bovenstaande voorbeeld gebruikt en alleen de PTIFF (Pyramid TIFF) wilt repliceren, voert u `+cqdam,*` inclusief alle uitvoeringen waarmee wordt gestart `cqdam`. In het voorbeeld is die vertoning `cqdam.pyramid.tiff`.

Als u alleen het origineel wilt repliceren, voert u `+original`.

## Dynamic Media Image Server-instellingen configureren {#configuring-dynamic-media-image-server-settings}

Als u de Dynamic Media Image Server configureert, moet u de Adobe CQ Scene7 ImageServer-bundel en de Adobe CQ Scene7 PlatformServer-bundel bewerken.

>[!NOTE]
Dynamic Media werkt out-of-the-box [nadat deze is ingeschakeld](#enabling-dynamic-media). U kunt echter desgewenst de installatie verfijnen door Dynamic Media Image Server te configureren om aan bepaalde specificaties of vereisten te voldoen.

**Vereiste**: _Voor_ Als u Dynamic Media Image Server configureert, dient u ervoor te zorgen dat uw VM van Windows een installatie van de Microsoft Visual C++-bibliotheken omvat. De bibliotheken zijn nodig om Dynamic Media Image Server uit te voeren. U kunt [Download het Microsoft Visual C++ 2010 Redistributable Pakket (x64) hier](https://www.microsoft.com/en-us/download/details.aspx?id=26999).

**Dynamic Media Image Server-instellingen configureren**:

1. Tik in de linkerbovenhoek van AEM op **[!UICONTROL Adobe Experience Manager]** om toegang te krijgen tot de globale navigatieconsole, tikt u vervolgens op **[!UICONTROL Tools > Operations > Web Console]**.
1. Op de **[!UICONTROL Adobe Experience Manager Web Console Configuration]** pagina, tikken **[!UICONTROL OSGi > Configuration]** om alle bundels weer te geven die momenteel binnen AEM worden uitgevoerd.

   De Dynamic Media Delivery Servers staan onder de volgende namen in de lijst:

   * **[!UICONTROL Adobe CQ Scene7 ImageServer]**
   * **[!UICONTROL Adobe CQ Scene7 PlatformServer]**

1. In de lijst met bundels, rechts van **[!UICONTROL Adobe CQ Scene7 ImageServer]** tikt u op **[!UICONTROL Edit]** pictogram.
1. In de **[!UICONTROL Adobe CQ Scene7 ImageServer]** stelt u de volgende configuratiewaarden in:

   >[!NOTE]
   In de meeste gevallen is het niet nodig de standaardwaarden te wijzigen. Als u echter wel de standaardwaarden wijzigt, moet u de bundel opnieuw starten om de wijzigingen door te voeren.

<table> 
 <tbody> 
  <tr> 
   <td><strong>Eigenschap</strong></td> 
   <td><strong>Standaardwaarde</strong></td> 
   <td><strong>Beschrijving</strong></td> 
  </tr> 
  <tr> 
   <td>TcpPort.name</td> 
   <td><code><em>empty</em></code></td> 
   <td>Het aantal van de haven voor communicatie met het proces ImageServer te gebruiken. Standaard wordt de vrije poort automatisch gedetecteerd.</td> 
  </tr> 
  <tr> 
   <td>AllowRemoteAccess.name</td> 
   <td><code><em>empty</em></code></td> 
   <td><p>Externe toegang tot ImageServer-proces toestaan of weigeren. Als de waarde false is, luistert de afbeeldingsserver alleen op de localhost.</p> <p>Standaard externalizer-instellingen die naar de localhost verwijzen, moeten het werkelijke domein of IP-adres van de specifieke VM-instantie opgeven. De reden hiervoor is dat de localhost mogelijk naar het bovenliggende systeem van de VM wijst.</p> <p>Domeinen of IP-adressen voor de VM moeten mogelijk een vermelding van het hostbestand hebben, zodat deze zelf kan worden opgelost.</p> </td> 
  </tr> 
  <tr> 
   <td>MaxRenderRgnPixels</td> 
   <td>16 MPixels</td> 
   <td>Maximale grootte in megapixels die wordt gerenderd.</td> 
  </tr> 
  <tr> 
   <td>MaxMessageSize</td> 
   <td>16 MBytes</td> 
   <td>Maximale berichtgrootte in megabytes die wordt afgeleverd.</td> 
  </tr> 
  <tr> 
   <td>RandomAccessUrlTimeout</td> 
   <td>20</td> 
   <td>De waarde van de onderbreking voor hoe lang in seconden ImageServer op JCR zal wachten om op een gerangschikte tegelverzoek te antwoorden.</td> 
  </tr> 
  <tr> 
   <td>WorkerThreads</td> 
   <td>10</td> 
   <td>Aantal arbeidersdraden.</td> 
  </tr> 
 </tbody> 
</table>

1. Tik op **[!UICONTROL Save]**.
1. In de lijst met bundels, rechts van **[!UICONTROL Adobe CQ Scene7 PlatformServer]** tikt u op **[!UICONTROL Edit]** pictogram.
1. In de **[!UICONTROL Adobe CQ Scene7 PlatformServer]** de volgende standaardopties voor waarden instellen:

   >[!NOTE]
   Dynamic Media Image Server gebruikt een eigen schijfcache om reacties in de cache op te slaan. De AEM HTTP-cache en de Dispacher kunnen niet worden gebruikt om reacties van Dynamic Media Image Server in cache te plaatsen.

   | **Eigenschap** | **Standaardwaarde** | **Beschrijving** |
   |---|---|---|
   | **[!UICONTROL Cache enabled]** | Ingeschakeld | Of de responscache is ingeschakeld. |
   | **[!UICONTROL Cache roots]** | cachegeheugen | Een of meer paden naar de responscachemappen. Relatieve paden worden omgezet in de interne bundelmap s7imaging. |
   | **[!UICONTROL Cache Max Size]** | 200000000 | Maximale grootte van responscache in bytes. |
   | **[!UICONTROL Cache Max Entries]** | 100000 | Maximumaantal items dat is toegestaan in de cache. |

### Standaardinstellingen voor Manifest {#default-manifest-settings}

Standaard manifest laat u de gebreken vormen die worden gebruikt om de antwoorden van de Levering van Dynamic Media te produceren. U kunt de kwaliteit (kwaliteit van de JPEG, de resolutie, de modus voor het berekenen van nieuwe pixels), het in cache plaatsen (verlopen) verfijnen en voorkomen dat afbeeldingen die te groot zijn, worden gerenderd (standaardpixel, standaardminiatuur, maxpix).

De plaats van de standaard manifeste configuratie wordt genomen van **[!UICONTROL Catalog root]** standaardwaarde van **[!UICONTROL Adobe CQ Scene7 PlatformServer]** bundel. Deze waarde bevindt zich standaard op het volgende pad binnen **[!UICONTROL Tools > General > CRXDE Lite]**:

`/conf/global/settings/dam/dm/imageserver/`

![configimageservercrxdelite](assets/configimageservercrxdelite.png)

U kunt de waarden van de eigenschappen wijzigen, zoals wordt beschreven in de onderstaande tabel, door nieuwe waarden in te voeren.

Tik op **[!UICONTROL Save All]**.

Zorg ervoor dat u op de knop **[!UICONTROL Access Control]** tab (rechts van de **[!UICONTROL Properties]** tab), stelt u vervolgens de toegangsbeheerrechten in op `jcr:read` voor alle gebruikers en voor gebruikers met dynamische media-replicatie.

![configimageservercrxdeliteaccessController, tabblad](assets/configimageservercrxdeliteaccesscontroltab.png)

Instellingen voor de manifestatie en de standaardwaarden ervan:

<table> 
 <tbody> 
  <tr> 
   <td><strong>Eigenschap</strong></td> 
   <td><strong>Standaardwaarde</strong></td> 
   <td><strong>Beschrijving</strong></td> 
  </tr> 
  <tr> 
   <td>bkgcolor</td> 
   <td>FFFFFF</td> 
   <td><p>Standaardachtergrondkleur. De RGB-waarde die wordt gebruikt om elk gebied van een antwoordafbeelding dat geen werkelijke afbeeldingsgegevens bevat, in te vullen.</p> <p>Zie ook <a href="https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-serving-api/image-serving-api/attributes/r-bkgcolor.html">BkgColor</a> in de Image Serving API.</p> </td> 
  </tr> 
  <tr> 
   <td>defaultPix</td> 
   <td>300,300</td> 
   <td><p>Standaardweergavegrootte. De server beperkt antwoordafbeeldingen tot maximaal deze breedte en hoogte als in de aanvraag niet expliciet de weergavegrootte wordt opgegeven met wid=, hei= of scl=.</p> <p>Opgegeven als twee gehele getallen, 0 of groter, gescheiden door een komma. Breedte en hoogte in pixels. Een van beide of beide waarden kunnen op 0 worden ingesteld om ze onbeperkt te houden. Is niet van toepassing op geneste/ingesloten aanvragen.</p> <p>Zie ook <a href="https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-serving-api/image-serving-api/attributes/r-defaultpix.html">DefaultPix</a> in de Image Serving API.</p> <p>Gewoonlijk gebruikt u echter een viewervoorinstelling of voorinstelling voor afbeeldingen om het element te leveren. De standaardvoorinstelling is alleen van toepassing op elementen die geen viewervoorinstelling of voorinstelling voor afbeeldingen gebruiken.</p> </td> 
  </tr> 
  <tr> 
   <td>standaard miniatuur</td> 
   <td>100,100</td> 
   <td><p>Standaardminiatuurgrootte. Wordt gebruikt in plaats van kenmerk::DefaultPix voor aanvragen van miniaturen (req=tmb).</p> <p>De server beperkt antwoordafbeeldingen tot maximaal deze breedte en hoogte als een miniatuuraanvraag (req=tmb) de grootte niet expliciet opgeeft met gebruik van wid=, hei= of scl=.</p> <p>Opgegeven als twee gehele getallen, 0 of groter, gescheiden door een komma. Breedte en hoogte in pixels. Een van beide of beide waarden kunnen op 0 worden ingesteld om ze onbeperkt te houden. </p> <p>Is niet van toepassing op geneste/ingesloten aanvragen.</p> <p>Zie ook <a href="https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-serving-api/image-serving-api/attributes/r-defaultthumbpix.html">DefaultThumbPix</a> in de Image Serving API. </p> </td> 
  </tr> 
  <tr> 
   <td>vervaldatum</td> 
   <td>36000000</td> 
   <td><p>De standaardtijd voor de clientcache om te live gaan. Biedt een standaardvervalinterval voor het geval dat een bepaalde catalogusrecord geen geldige catalogus bevat::Expiration value.</p> <p>Reëel getal, 0 of hoger. Aantal milliseconden tot aan vervaldatum sinds de antwoordgegevens werden geproduceerd. Reeks aan 0 om altijd het antwoordbeeld onmiddellijk te verlopen, dat effectief cliënt caching onbruikbaar maakt. Deze waarde wordt standaard ingesteld op 10 uur. Als een nieuwe afbeelding wordt gepubliceerd, duurt het tien uur voordat de oude afbeelding de cache van de gebruiker verlaat. Neem contact op met de Klantenondersteuning als u de cache sneller moet wissen.</p> <p>Zie ook <a href="https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-serving-api/image-serving-api/attributes/r-expiration.html">Verlopen</a> in de Image Serving API.</p> </td> 
  </tr> 
  <tr> 
   <td>jpegquality</td> 
   <td>80</td> 
   <td><p>Standaardcoderingskenmerken van JPEG. Hiermee geeft u de standaardkenmerken op voor JPEG-antwoordafbeeldingen.</p> <p>Geheel getal en markering, gescheiden door een komma. De eerste waarde ligt in het bereik 1.100 en definieert de kwaliteit. De tweede waarde kan 0 zijn voor normaal gedrag of 1 voor het uitschakelen van de downsampling van de RGB-chromaticiteit die gewoonlijk door JPEG-encoders wordt gebruikt.</p> <p>Zie ook <a href="https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-serving-api/image-serving-api/attributes/r-jpegquality.html">JpegQuality</a> in de Image Serving API.</p> </td> 
  </tr> 
  <tr> 
   <td>maxpix</td> 
   <td>2000,2000</td> 
   <td><p>Limiet voor afbeeldingsgrootte beantwoorden. Maximale breedte en hoogte van antwoordafbeelding die aan de client worden geretourneerd.</p> <p>De server retourneert een fout als een aanvraag een antwoordafbeelding veroorzaakt waarvan de breedte of hoogte groter is dan kenmerk::MaxPix.</p> <p>Zie ook <a href="https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-serving-api/image-serving-api/attributes/r-maxpix.html">MaxPix</a> in de Image Serving API.</p> </td> 
  </tr> 
  <tr> 
   <td>resmode</td> 
   <td>SHARP2</td> 
   <td><p>Standaardmodus voor opnieuw berekenen van pixels. Hiermee geeft u de standaardkenmerken voor resampling en interpolatie op die moeten worden gebruikt voor het schalen van afbeeldingsgegevens.</p> <p>Wordt gebruikt wanneer resMode= niet is opgegeven in een aanvraag.</p> <p>Toegestane waarden zijn BILIN, BICUB of SHARP2.</p> <p>Enum. Stel dit in op 2 voor bilin, 3 voor bicub of 4 voor de interpolatiemodus Sharp2. Gebruik Sharp2 voor de beste resultaten.</p> <p>Zie ook <a href="https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-serving-api/image-serving-api/attributes/r-is-cat-resmode.html">ResMode</a> in de Image Serving API.</p> </td> 
  </tr> 
  <tr> 
   <td>resolutie</td> 
   <td>72</td> 
   <td><p>Standaardobjectresolutie. Biedt een standaardobjectresolutie voor het geval een bepaalde catalogusrecord geen geldige catalogus bevat::resolutiewaarde.</p> <p>Reëel getal, groter dan 0. Doorgaans uitgedrukt als pixels per inch, maar mogelijk ook in andere eenheden, zoals pixels per meter.</p> <p>Zie ook <a href="https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-serving-api/image-serving-api/attributes/r-resolution.html">Resolutie</a> in de Image Serving API.</p> </td> 
  </tr> 
  <tr> 
   <td>miniatuur</td> 
   <td>1%,11%,21%,31%,41%,51%,61%,71%,81%,91%</td> 
   <td>Deze waarden vertegenwoordigen een momentopname van de videoplaytime en worden overgegaan tot <a href="https://encoding.com/">encoding.com</a>. Zie <a href="/help/assets/video.md#about-video-thumbnails">Informatie over videominiaturen</a> voor meer informatie .</td> 
  </tr> 
 </tbody> 
</table>

## Dynamic Media-kleurbeheer configureren {#configuring-dynamic-media-color-management}

Met dynamisch kleurbeheer voor media kunt u de juiste elementen kleuren om ze voor te vertonen.

Met kleurcorrectie behouden ingesloten elementen hun kleurruimte (RGB, CMYK, Grijs) en ingesloten kleurprofiel in de gegenereerde piramide-TIFF-uitvoering. Wanneer u een dynamische uitvoering aanvraagt, wordt de afbeeldingskleur gecorrigeerd in de doelkleurruimte. U configureert het uitvoerkleurprofiel in de publicatie-instellingen voor dynamische media in de JCR.

Bij kleurbeheer voor Adobe wordt gebruikgemaakt van ICC-profielen, een indeling die is gedefinieerd door het ICC (International Color Consortium).

U kunt dynamisch kleurbeheer voor media configureren en voorinstellingen voor afbeeldingen configureren met CMYK, RGB of Grijsuitvoer. Zie [Voorinstellingen voor afbeeldingen configureren](managing-image-presets.md).

Gevallen voor geavanceerd gebruik kunnen een handmatige configuratie gebruiken **[!UICONTROL icc=]** Hiermee kunt u expliciet een uitvoerkleurprofiel selecteren:

* **[!UICONTROL icc]** - [Kleurprofiel uitvoeren.](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-serving-api/image-serving-api/http-protocol-reference/command-reference/r-icc.html)

* **[!UICONTROL iccEmbed]** - [Kleurprofiel insluiten.](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-serving-api/image-serving-api/http-protocol-reference/command-reference/r-iccembed.html)

>[!NOTE]
De standaardset Adobe-kleurprofielen is alleen beschikbaar als u [Feature Pack 12445 van de Distributie van de Software](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq630/featurepack/cq-6.3.0-featurepack-12445) geïnstalleerd. Alle eigenschapspakken en de dienstpakken zijn beschikbaar bij [Softwaredistributie](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html). Het Feature Pack 12445 verstrekt de kleurenprofielen van de Adobe.

### Functiepak 12445 installeren {#installing-feature-pack}

U moet functiepak 12445 installeren om de mogelijkheden voor dynamisch kleurbeheer voor media te kunnen gebruiken.

**Om functiepak 12445 te installeren**:

1. Navigeren naar [Softwaredistributie](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) en downloaden `cq-6.3.0-featurepack-12445`.

   Zie [Werken met pakketten](/help/sites-administering/package-manager.md) voor meer informatie over het gebruik van pakketten in [!DNL Adobe Experience Manager].

1. Installeer het functiepakket.

### De standaardkleurprofielen configureren {#configuring-the-default-color-profiles}

Nadat u het functiepakket hebt geïnstalleerd, moet u de juiste standaardkleurprofielen configureren om kleurcorrectie in te schakelen wanneer u RGB- of CMYK-afbeeldingsgegevens aanvraagt.

**De standaardkleurprofielen configureren**:

1. In **[!UICONTROL Tools > General > CRXDE Lite]**, navigeer naar `/conf/global/settings/dam/dm/imageserver/configuration/settings` die de standaard Adobe Color-profielen bevat.

   ![chlimage_1-514](assets/chlimage_1-514.png)

1. Voeg een eigenschap voor kleurcorrectie toe door naar de onderkant van het deelvenster **[!UICONTROL Properties]** en handmatig de naam, het type en de waarde van de eigenschap in te voeren, die in de volgende tabellen worden beschreven. Tik op **[!UICONTROL Add]** en vervolgens **[!UICONTROL Save All]** om uw waarden op te slaan.

   De eigenschappen voor kleurcorrectie worden beschreven in het dialoogvenster **[!UICONTROL Color Corrections Properties]** tabel. Waarden die u kunt toewijzen aan eigenschappen voor kleurcorrectie bevinden zich in de **[!UICONTROL Color Profile]** tabel.

   Bijvoorbeeld in **[!UICONTROL Name]**, toevoegen `iccprofilecmyk`, selecteert u **[!UICONTROL Type]** `String`en toevoegen `WebCoated` als **[!UICONTROL Value]**. Tikken **[!UICONTROL Add]** vervolgens **[!UICONTROL Save All]** om uw waarden op te slaan.

   ![chlimage_1-515](assets/chlimage_1-515.png)

   **Tabel met kleurcorrectie-eigenschappen**

   <table> 
    <tbody> 
      <tr> 
      <td><strong>Eigenschap</strong></td> 
      <td><strong>Type</strong></td> 
      <td><strong>Standaard</strong></td> 
      <td><strong>Beschrijving</strong></td> 
      </tr> 
      <tr> 
      <td><a href="https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-serving-api/image-serving-api/attributes/r-iccprofilergb.html">iccprofilergb</a></td> 
      <td>String</td> 
      <td>&lt;empty&gt;</td> 
      <td>Naam van het standaardkleurprofiel RGB.</td> 
      </tr> 
      <tr> 
      <td><a href="https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-serving-api/image-serving-api/attributes/r-iccprofilecmyk.html">icprofilecmyk</a></td> 
      <td>String</td> 
      <td>&lt;empty&gt;</td> 
      <td>Naam van het standaard CMYK-kleurprofiel.</td> 
      </tr> 
      <tr> 
      <td><a href="https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-serving-api/image-serving-api/attributes/r-iccprofilegray.html">icprofilegray</a></td> 
      <td>String</td> 
      <td>&lt;empty&gt;</td> 
      <td>Naam van het standaardkleurprofiel Grijs.</td> 
      </tr> 
      <tr> 
      <td><a href="https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-serving-api/image-serving-api/attributes/r-iccprofilesrcrgb.html">iccprofilesrcrgb</a></td> 
      <td>String</td> 
      <td>&lt;empty&gt;</td> 
      <td>Naam van het standaardkleurprofiel RGB dat wordt gebruikt voor RGB-afbeeldingen zonder ingesloten kleurprofiel</td> 
      </tr> 
      <tr> 
      <td><a href="https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-serving-api/image-serving-api/attributes/r-iccprofilesrccmyk.html">iccprofilesrcmyk</a></td> 
      <td>String</td> 
      <td>&lt;empty&gt;</td> 
      <td>Naam van het standaard CMYK-kleurprofiel dat wordt gebruikt voor CMYK-afbeeldingen zonder ingesloten kleurprofiel.</td> 
      </tr> 
      <tr> 
      <td><a href="https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-serving-api/image-serving-api/attributes/r-iccprofilesrcgray.html">iccprofilesrcgray</a></td> 
      <td>String</td> 
      <td>&lt;empty&gt;</td> 
      <td>Naam van het standaard grijskleurprofiel dat wordt gebruikt voor CMYK-afbeeldingen zonder ingesloten kleurprofiel.</td> 
      </tr> 
      <tr> 
      <td><a href="https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-serving-api/image-serving-api/attributes/r-iccblackpointcompensation.html">icblackpointcompensatie</a></td> 
      <td>Boolean</td> 
      <td>Waar</td> 
      <td>Hiermee geeft u aan of zwartpuntcompensatie moet worden toegepast tijdens kleurcorrectie. Adobe raadt u aan dit aan te doen.</td> 
      </tr> 
      <tr> 
      <td><a href="https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-serving-api/image-serving-api/attributes/r-iccdither.html">icdithering</a></td> 
      <td>Boolean</td> 
      <td>Onwaar</td> 
      <td>Hiermee geeft u aan of dithering moet worden toegepast tijdens kleurcorrectie.</td> 
      </tr> 
      <tr> 
      <td><a href="https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-serving-api/image-serving-api/attributes/r-iccrenderintent.html">iccrenderintent</a></td> 
      <td>String</td> 
      <td>relatief</td> 
      <td><p>Geeft de render-intentie aan. Acceptabele waarden zijn: <strong>perceptueel, relatief, verzadiging, absoluut. </strong><i></i>Adobe beveelt aan <strong>relatief </strong><i></i>als standaard.</p> </td> 
      </tr> 
    </tbody> 
    </table>

   >[!NOTE]
   Namen van eigenschappen zijn hoofdlettergevoelig en moeten allemaal kleine letters zijn.

   **Kleurprofieltabel**

   De volgende kleurprofielen zijn geïnstalleerd:

   <table> 
    <tbody> 
      <tr> 
      <th><p>Naam</p> </th> 
      <th><p>Kleurruimte</p> </th> 
      <th><p>Beschrijving</p> </th> 
      </tr> 
      <tr> 
      <td>AdobeRGB</td> 
      <td>RGB</td> 
      <td>Adobe RGB (1998)</td> 
      </tr> 
      <tr> 
      <td>AppleRGB</td> 
      <td>RGB</td> 
      <td>Apple RGB</td> 
      </tr> 
      <tr> 
      <td>CIERGB</td> 
      <td>RGB</td> 
      <td>CIE RGB</td> 
      </tr> 
      <tr> 
      <td>CoatedFogra27</td> 
      <td>CMYK</td> 
      <td>Coated FOGRA27 (ISO 12647-2:2004)</td> 
      </tr> 
      <tr> 
      <td>CoatedFogra39</td> 
      <td>CMYK</td> 
      <td>Coated FOGRA39 (ISO 12647-2:2004)</td> 
      </tr> 
      <tr> 
      <td>CoatedGraCol</td> 
      <td>CMYK</td> 
      <td>Coated GRACoL 2006 (ISO 12647-2:2004)</td> 
      </tr> 
      <tr> 
      <td>ColorMatchRGB</td> 
      <td>RGB</td> 
      <td>ColorMatch RGB</td> 
      </tr> 
      <tr> 
      <td>EuropeISOCoated</td> 
      <td>CMYK</td> 
      <td>Europe ISO Coated FOGRA27</td> 
      </tr> 
      <tr> 
      <td>EuroscaleCoated</td> 
      <td>CMYK</td> 
      <td>Euroscale Coated v2</td> 
      </tr> 
      <tr> 
      <td>EuroscaleUncoated</td> 
      <td>CMYK</td> 
      <td>Euroscale Uncoated v2</td> 
      </tr> 
      <tr> 
      <td>JapanColorCoated</td> 
      <td>CMYK</td> 
      <td>Japan Color 2001 Coated</td> 
      </tr> 
      <tr> 
      <td>JapanColorNewspaper</td> 
      <td>CMYK</td> 
      <td>Japan Color 2002 Newspaper</td> 
      </tr> 
      <tr> 
      <td>JapanColorUncoated</td> 
      <td>CMYK</td> 
      <td>Japan Color 2001 Uncoated</td> 
      </tr> 
      <tr> 
      <td>JapanColorWebCoated</td> 
      <td>CMYK</td> 
      <td>Japan Color 2003 Web Coated</td> 
      </tr> 
      <tr> 
      <td>JapanWebCoated</td> 
      <td>CMYK</td> 
      <td>Japan Web Coated (Ad)</td> 
      </tr> 
      <tr> 
      <td>NewsprintSNAP2007</td> 
      <td>CMYK</td> 
      <td>US Newsprint (SNAP 2007)</td> 
      </tr> 
      <tr> 
      <td>NTSC</td> 
      <td>RGB</td> 
      <td>NTSC (1953)</td> 
      </tr> 
      <tr> 
      <td>PAL</td> 
      <td>RGB</td> 
      <td>PAL/SECAM</td> 
      </tr> 
      <tr> 
      <td>ProPhoto</td> 
      <td>RGB</td> 
      <td>ProPhoto RGB</td> 
      </tr> 
      <tr> 
      <td>PS4Default</td> 
      <td>CMYK</td> 
      <td>Photoshop 4 standaard CMYK</td> 
      </tr> 
      <tr> 
      <td>PS5Default</td> 
      <td>CMYK</td> 
      <td>Photoshop 5 standaard CMYK</td> 
      </tr> 
      <tr> 
      <td>SheetfedCoated</td> 
      <td>CMYK</td> 
      <td>U.S. Sheetfed Coated v2</td> 
      </tr> 
      <tr> 
      <td>SheetfedUncoated</td> 
      <td>CMYK</td> 
      <td>U.S. Sheetfed Uncoated v2</td> 
      </tr> 
      <tr> 
      <td>SMPTE</td> 
      <td>RGB</td> 
      <td>SMPTE-C</td> 
      </tr> 
      <tr> 
      <td>sRGB</td> 
      <td>RGB</td> 
      <td>sRGB IEC61966-2.1</td> 
      </tr> 
      <tr> 
      <td>UncoatedFogra29</td> 
      <td>CMYK</td> 
      <td>Uncoated FOGRA29 (ISO 12647-2:2004)</td> 
      </tr> 
      <tr> 
      <td>WebCoated</td> 
      <td>CMYK</td> 
      <td>U.S. Web Coated (SWOP) v2</td> 
      </tr> 
      <tr> 
      <td>WebCoatedFogra28</td> 
      <td>CMYK</td> 
      <td>Web Coated FOGRA28 (ISO 12647-2:2004)</td> 
      </tr> 
      <tr> 
      <td>WebCoatedGrade3</td> 
      <td>CMYK</td> 
      <td>Web Coated SWOP 2006 Grade 3 Paper</td> 
      </tr> 
      <tr> 
      <td>WebCoatedGrade5</td> 
      <td>CMYK</td> 
      <td>Web Coated SWOP 2006 Grade 5 Paper</td> 
      </tr> 
      <tr> 
      <td>WebUncoated</td> 
      <td>CMYK</td> 
      <td>U.S. Web Uncoated v2</td> 
      </tr> 
      <tr> 
      <td>WideGamutRGB</td> 
      <td>RGB</td> 
      <td>Brede kleuromvang RGB</td> 
      </tr> 
    </tbody> 
    </table>

1. Tik op **[!UICONTROL Save All]**.

U kunt bijvoorbeeld instellen **[!UICONTROL iccprofilergb]** tot `sRGB`, en **[!UICONTROL iccprofilecmyk]** tot `WebCoated`. Dit doet het volgende:

* Hiermee schakelt u kleurcorrectie in voor RGB- en CMYK-afbeeldingen.
* RGB-afbeeldingen die geen kleurprofiel hebben, worden verondersteld zich in het deelvenster `sRGB` kleurruimte.
* CMYK-afbeeldingen zonder kleurprofiel worden verondersteld zich in te bevinden `WebCoated` kleurruimte.
* Dynamische uitvoeringen die RGB-uitvoer retourneren, retourneren deze in het dialoogvenster `sRGB` kleurruimte.
* Dynamische uitvoeringen die CMYK-uitvoer retourneren, retourneren deze in het dialoogvenster `WebCoated` kleurruimte.

## Elementen leveren {#delivering-assets}

Nadat u alle bovenstaande taken hebt voltooid, worden de geactiveerde Dynamic Media-middelen aangeboden via de Image- of Video-service. In AEM komt deze mogelijkheid tot uiting in een **[!UICONTROL Copy Image URL]**, **[!UICONTROL Copy Viewer URL]**, **[!UICONTROL Embed Viewer Code]** en in de WCM.

Zie [Dynamic Media-middelen leveren](delivering-dynamic-media-assets.md).

<table> 
 <tbody> 
  <tr> 
   <td><strong>Wanneer u...</strong></td> 
   <td><strong>Resultaat</strong></td> 
  </tr> 
  <tr> 
   <td>URL van afbeelding kopiëren</td> 
   <td><p>In het dialoogvenster URL kopiëren wordt een URL weergegeven die vergelijkbaar is met de volgende URL (URL is alleen bedoeld voor demonstratiedoeleinden):</p> <p><code>https://IMAGESERVICEPUBLISHNODE/is/image/content/dam/path/to/Image.jpg?$preset$</code></p> <p>Wanneer <code>IMAGESERVICEPUBLISHNODE</code> verwijst naar de URL van de afbeeldingsservice.</p> <p>Zie ook <a href="/help/assets/delivering-dynamic-media-assets.md">Dynamic Media-middelen leveren</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>Een viewer-URL kopiëren</td> 
   <td><p>In het dialoogvenster URL kopiëren wordt een URL weergegeven die vergelijkbaar is met de volgende URL (URL is alleen bedoeld voor demonstratiedoeleinden):</p> <p><code>https://PUBLISHNODE/etc/dam/viewers/s7viewers/html5/BasicZoomViewer.html?asset=/content/dam/path/to/Image.jpg&amp;config=/conf/global/settings/dam/dm/presets/viewer/Zoom_dark&amp;serverUrl=https://IMAGESERVICEPUBLISHNODE/is/image/&amp;contentRoot=%2F</code></p> <p>Wanneer <code>PUBLISHNODE</code> verwijst naar het AEM publicatieknooppunt en <code>IMAGESERVICEPUBLISHNODE</code> verwijst naar de URL van de afbeeldingsservice.</p> <p>Zie ook <a href="/help/assets/delivering-dynamic-media-assets.md">Dynamic Media-middelen leveren</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>Insluitcode van een viewer kopiëren</td> 
   <td><p>In het dialoogvenster Code insluiten kopiëren wordt een codefragment weergegeven dat lijkt op het volgende (codevoorbeeld is alleen bedoeld voor demonstratiedoeleinden):</p> <p><code class="code">&lt;style type="text/css"&gt;
       #s7basiczoom_div.s7basiczoomviewer{
       width:100%;
       height:auto;
       }
       &lt;/style&gt;
       &lt;script
       type="text/javascript" src="https://PUBLISHNODE/etc/dam/viewers/s7viewers/html5/js/BasicZoomViewer.js"&gt;&lt;/script&gt;
       &lt;div id="s7basiczoom_div"&gt;&lt;/div&gt;
       &lt;script type="text/javascript"&gt;
       var s7basiczoomviewer = new s7viewers.BasicZoomViewer({
       "containerId" : "s7basiczoom_div",
       "params" : {
       "serverurl" : "https://IMAGESERVICEPUBLISHNODE/is/image/",
       "contenturl" : "https://PUBLISHNODE/",
       "config" : "/conf/global/settings/dam/dm/presets/viewer/Zoom_dark",
       "asset" : "/content/dam/path/to/Image.jpg" }
       }).init();
       &lt;/script&gt;</code></p> <p>Wanneer <code>PUBLISHNODE</code> verwijst naar het AEM publicatieknooppunt en <code>IMAGESERVICEPUBLISHNODE</code> verwijst naar de URL van de afbeeldingsservice.</p> <p>Zie ook <a href="/help/assets/delivering-dynamic-media-assets.md">Dynamic Media-middelen leveren</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>

### WCM Dynamic Media en interactieve mediacomponenten {#wcm-dynamic-media-and-interactive-media-components}

WCM-pagina&#39;s die verwijzen naar Dynamic Media en Interactive Media-componenten verwijzen naar de leveringsservice.
