---
title: Problemen oplossen in de modus Dynamic Media - Scene7
description: Problemen met Dynamic Media oplossen - Scene7-uitvoeringsmodus.
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
exl-id: d8cc94b0-eacf-4e76-bd50-7934bbc28c92
feature: Problemen oplossen
role: Administrator,Business Practitioner
translation-type: tm+mt
source-git-commit: 13eb1d64677f6940332a2eeb4d3aba2915ac7bba
workflow-type: tm+mt
source-wordcount: '1284'
ht-degree: 0%

---

# Problemen met Dynamic Media oplossen - Scene7-modus {#troubleshooting-dynamic-media-scene-mode}

In het volgende document wordt beschreven hoe u problemen kunt oplossen bij het uitvoeren van **dynamicmedia_scene7**-uitvoeringsmodus in Dynamic Media.

## {#setup-and-configuration} instellen en configureren

Zorg ervoor dat Dynamic Media op de juiste wijze is ingesteld door het volgende te doen:

* Het bevel van het begin bevat `-r dynamicmedia_scene7` runmode argument.
* Om het even welke AEM 6.4 cumulatieve fixfixpakken (GFPs) zijn eerst geïnstalleerd *vóór* om het even welke beschikbare Packs van de Eigenschap van Dynamic Media.
* Optioneel Feature Pack 18912 is geïnstalleerd.

   Dit optionele functiepakket is bedoeld voor FTP-ondersteuning of als u middelen van Dynamic Media Classic naar Dynamic Media migreert.

* Navigeer naar de gebruikersinterface van Cloud Services en bevestig dat de provisioned account onder **[!UICONTROL Available Configurations]** verschijnt.
* Zorg ervoor dat **[!UICONTROL Dynamic Media Asset Activation (scene7)]** replicatieagent wordt toegelaten.

   Deze replicatieagent wordt gevonden onder **[!UICONTROL Agents]** op Auteur.

## Algemeen (alle activa) {#general-all-assets}

Hier volgen enkele algemene tips en trucs voor alle elementen.

### Eigenschappen van de statusstatus van de elementsynchronisatie {#asset-synchronization-status-properties}

De volgende eigenschappen van elementen kunnen in CRXDE Lite worden gecontroleerd om te bevestigen dat het middel is gesynchroniseerd van AEM naar Dynamic Media:

| **Eigenschap** | **Voorbeeld** | **Beschrijving** |
|---|---|---|
| `<object_node>/jcr:content/metadata/dam:scene7ID` | `a|364266` | Algemene indicator dat de knoop met Dynamic Media wordt verbonden. |
| `<object_node>/jcr:content/metadata/dam:scene7FileStatus` | **[!UICONTROL PublishComplete]** of fouttekst | Status van het uploaden van middelen naar Dynamic Media. |
| `<object_node>/jcr:content/metadata/dam:scene7File` | `myCompany/myAssetID` | Moet worden gevuld om URL&#39;s te genereren naar externe middelen van Dynamic Media. |
| `<object_node>/jcr:content/dam:lastSyncStatus` | `success` or `failed:<error text>` | Synchronisatiestatus van sets (centrifuges, afbeeldingssets, enzovoort), voorinstellingen voor afbeeldingen, voorinstellingen voor viewers, updates van afbeeldingen met hyperlinks voor een element of afbeeldingen die zijn bewerkt. |

### Synchronisatie-logboekregistratie {#synchronization-logging}

Synchronisatiefouten en -problemen worden aangemeld `error.log` (AEM servermap `/crx-quickstart/logs/`). Er is voldoende logboekregistratie beschikbaar om de hoofdoorzaak van de meeste problemen te bepalen. U kunt echter het logbestand voor DEBUG verhogen in het `com.adobe.cq.dam.ips`-pakket via de Sling Console ([http://localhost:4502/system/console/slinglog](http://localhost:4502/system/console/slinglog)) om meer informatie te verzamelen.

### {#move-copy-delete} verplaatsen, kopiëren of verwijderen

Voer de volgende handelingen uit voordat u een bewerking Verplaatsen, Kopiëren of Verwijderen uitvoert:

* Bevestig voor afbeeldingen en video&#39;s dat er een `<object_node>/jcr:content/metadata/dam:scene7ID`-waarde bestaat voordat u bewerkingen voor verplaatsen, kopiëren of verwijderen uitvoert.
* Bevestig voor voorinstellingen voor afbeeldingen en viewers dat er een `https://<server>/crx/de/index.jsp#/etc/dam/presets/viewer/testpreset/jcr%3Acontent/metadata`-waarde bestaat voordat u bewerkingen voor verplaatsen, kopiëren of verwijderen uitvoert.
* Als de bovenstaande metagegevenswaarde ontbreekt, moet u elementen opnieuw uploaden voordat u bewerkingen verplaatst, kopieert of verwijdert.

### Versiebeheer {#version-control}

Bij het vervangen van een bestaand Dynamic Media-element (dezelfde naam en locatie) kunt u beide elementen behouden of een versie vervangen of maken:

* Als u beide behoudt, wordt een nieuw element gemaakt met een unieke naam voor het gepubliceerde element-URL. **[!UICONTROL image.jpg]** is bijvoorbeeld het oorspronkelijke element en **[!UICONTROL image1.jpg]** is het net geüploade element.

* Het maken van een versie wordt niet ondersteund in de Dynamic Media- Scene7-modus. De nieuwe versie vervangt het bestaande element in levering.

## Afbeeldingen en sets {#images-and-sets}

Raadpleeg de volgende richtlijnen voor het oplossen van problemen als u problemen hebt met afbeeldingen en sets.

<table> 
 <tbody> 
  <tr> 
   <td><strong>Probleem</strong></td> 
   <td><strong>Foutopsporing</strong></td> 
   <td><strong>Oplossing</strong></td> 
  </tr> 
  <tr> 
   <td>Kan de knop Kopie-URL/Insluiten niet openen in de weergave met elementdetails</td> 
   <td> 
    <ol> 
     <li><p>Ga naar CRX/DE:</p> 
      <ul> 
       <li>Controleer of de voorinstelling in het JCR <code>/etc/dam/presets/viewer/&lt;preset&gt; has lastReplicationAction</code> is gedefinieerd. Deze locatie is van toepassing als u een upgrade hebt uitgevoerd van AEM 6.x naar 6.4 en de migratie hebt uitgeschakeld. Anders is de locatie <code>/conf/global/settings/dam/dm/presets/viewer</code>.</li> 
       <li>Controleer of het element in de JCR <code>dam:scene7FileStatus</code><strong> </strong>onder Metagegevens wordt weergegeven als <code>PublishComplete</code>.</li> 
      </ul> </li> 
    </ol> </td> 
   <td><p>Pagina vernieuwen/naar een andere pagina navigeren en terugkeren (JSP voor side rail moet opnieuw worden gecompileerd)</p> <p>Als dat niet werkt:</p> 
    <ul> 
     <li>Middelen publiceren.</li> 
     <li>Elementen opnieuw uploaden en publiceren.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>De kiezer van het element in de seteditor is vastgelopen tijdens ononderbroken laden</td> 
   <td><p>Bekend probleem dat in 6.4 moet worden opgelost</p> </td> 
   <td><p>Sluit de kiezer en open deze opnieuw.</p> </td> 
  </tr> 
  <tr> 
   <td><strong>De </strong> selectieknop is niet actief nadat u een element hebt geselecteerd als onderdeel van het bewerken van een set</td> 
   <td><p> </p> <p>Bekend probleem dat in 6.4 moet worden opgelost</p> <p> </p> </td> 
   <td><p>Klik eerst op een andere map in de Asset Selector en ga terug om het element te selecteren.</p> </td> 
  </tr> 
  <tr> 
   <td>De carrouselhotspot beweegt zich rond na het schakelen tussen dia's</td> 
   <td><p>Controleer of alle dia's even groot zijn.</p> </td> 
   <td><p>Gebruik voor de carrousel alleen afbeeldingen met dezelfde grootte.</p> </td> 
  </tr> 
  <tr> 
   <td>De afbeelding wordt niet voorvertoond met de Dynamic Media-viewer</td> 
   <td><p>Controleer of het element <code>dam:scene7File</code> bevat in de metagegevenseigenschappen (CRXDE Lite)</p> </td> 
   <td><p>Controleer of alle elementen zijn verwerkt.</p> </td> 
  </tr> 
  <tr> 
   <td>Geüpload element wordt niet weergegeven in elementkiezer</td> 
   <td><p>Element controleren heeft eigenschap <code>jcr:content</code> &gt; <strong><code>dam:assetState</code></strong> = <code>processed</code> (CRXDE Lite)</p> </td> 
   <td><p>Controleer of alle elementen zijn verwerkt.</p> </td> 
  </tr> 
  <tr> 
   <td>Banner op kaartweergave toont <strong>Nieuw</strong> wanneer het element nog niet is verwerkt</td> 
   <td>Activeer <code>jcr:content</code> &gt; <code>dam:assetState</code> = als <code>unprocessed</code> niet door de workflow is opgepikt.</td> 
   <td>Wacht tot asset is opgehaald via workflow.</td> 
  </tr> 
  <tr> 
   <td>In afbeeldingen of sets wordt de URL van de viewer of de insluitcode niet weergegeven</td> 
   <td>Controleer of de viewervoorinstelling is gepubliceerd.</td> 
   <td><p>Ga naar <strong>Gereedschappen</strong> &gt; <strong>Middelen</strong> &gt; <strong>Viewer-voorinstellingen</strong> en publiceer de viewervoorinstelling.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Video {#video}

Raadpleeg de volgende richtlijnen voor het oplossen van problemen als u problemen hebt met video.

<table> 
 <tbody> 
  <tr> 
   <td><strong>Probleem</strong></td> 
   <td><strong>Foutopsporing</strong></td> 
   <td><strong>Oplossing</strong></td> 
  </tr> 
  <tr> 
   <td>Video kan niet worden voorvertoond</td> 
   <td> 
    <ul> 
     <li>Controleer of aan de map een videoprofiel is toegewezen (als de bestandsindeling niet wordt ondersteund). Als deze optie niet wordt ondersteund, wordt alleen een afbeelding weergegeven.</li> 
     <li>Het videoprofiel moet meer dan één coderingsvoorinstelling bevatten om een AVS-set te genereren (enkele coderingen worden behandeld als video-inhoud voor MP4-bestanden). voor niet-ondersteunde bestanden, op dezelfde manier behandeld als niet-verwerkte bestanden).</li> 
     <li>Controleer of de video is verwerkt door <code>dam:scene7FileAvs</code> van <code>dam:scene7File</code> in metagegevens te bevestigen.</li> 
    </ul> </td> 
   <td> 
    <ol> 
     <li>Wijs een videoprofiel toe aan de map.</li> 
     <li>Bewerk het videoprofiel om meerdere coderingsvoorinstellingen op te nemen.</li> 
     <li>Wacht tot de video is verwerkt.</li> 
     <li>Als u de video opnieuw laadt, moet u ervoor zorgen dat de Dynamic Media Encode Video-workflow niet wordt uitgevoerd.<br /> </li> 
     <li>Upload de video opnieuw.</li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td>Video is niet gecodeerd</td> 
   <td> 
    <ul> 
     <li>Controleer of de runmode <span class="kbd">dynamicmedia_scene7</span> is.</li> 
     <li>Controleer of Dynamic Media-cloudservice is geconfigureerd.</li> 
     <li>Controleer of een videoprofiel is gekoppeld aan de uploadmap.</li> 
    </ul> </td> 
   <td> 
    <ol> 
     <li>Controleer uw AEM met <span class="kbd">-r dynamicmedia_scene7</span></li> 
     <li>Controleer of de Dynamic Media-configuratie onder Cloud Services correct is ingesteld.</li> 
     <li>Controleer of de map een videoprofiel heeft. Controleer ook het videoprofiel.</li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td>Videoverwerking duurt te lang</td> 
   <td><p>U kunt als volgt bepalen of videocodering nog wordt uitgevoerd of dat er een foutstatus is ingevoerd:</p> 
    <ul> 
     <li>Controleer de videostatus <code>http://localhost:4502/crx/de/index.jsp#/content/dam/folder/videomp4/jcr%3Acontent</code> &gt; <span class="kbd">dam:assetState</span></li> 
     <li>Controleer de video vanaf de workflowconsole <code>http://localhost:4502/libs/cq/workflow/content/console.html</code> &gt; Instanties, Archiveren, tabbladen met foutmeldingen.</li> 
    </ul> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Video-uitvoering ontbreekt</td> 
   <td><p>Wanneer video wordt geüpload, maar er geen gecodeerde vertoningen zijn:</p> 
    <ul> 
     <li>Controleer of aan de map een videoprofiel is toegewezen.</li> 
     <li>Controleer of de video is verwerkt door <code>dam:scene7FileAvs</code> in metagegevens te bevestigen.</li> 
    </ul> </td> 
   <td> 
    <ol> 
     <li>Wijs een videoprofiel toe aan de map.</li> 
     <li>Wacht tot de video is verwerkt.<br /> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

## Viewers {#viewers}

Raadpleeg de volgende richtlijnen voor het oplossen van problemen als u problemen hebt met viewers.

<table> 
 <tbody> 
  <tr> 
   <td><strong>Probleem</strong></td> 
   <td><strong>Foutopsporing</strong></td> 
   <td><strong>Oplossing</strong></td> 
  </tr> 
  <tr> 
   <td>Voorinstellingen van viewer worden niet gepubliceerd</td> 
   <td><p>Ga door naar de diagnostische pagina van de voorbeeldmanager: <code>http://localhost:4502/libs/dam/gui/content/s7dam/samplemanager/samplemanager.html</code></p> <p>Berekende waarden observeren. Als u correct werkt, ziet u het volgende:</p> <p><code class="code">_DMSAMPLE status: 0 unsyced assets - activation not necessary
       _OOTB status: 0 unsyced assets - 0 unactivated assets</code></p> <p><strong>Opmerking</strong>: Het kan ongeveer 10 minuten duren nadat de Dynamic Media-cloudinstellingen zijn geconfigureerd voor synchronisatie van de viewerelementen.</p> <p>Als er niet-geactiveerde elementen overblijven, klikt u op een van de <strong>Alle niet-geactiveerde elementen weergeven</strong> knoppen om details weer te geven.</p> </td> 
   <td> 
    <ol> 
     <li>Navigeer naar de lijst met voorinstellingen voor viewers in de beheerprogramma's: <code>http://localhost:4502/libs/dam/gui/content/s7dam/samplemanager/samplemanager.html</code></li> 
     <li>Selecteer alle viewervoorinstellingen en klik op <strong>Publiceren</strong>.</li> 
     <li>Navigeer terug naar voorbeeldbeheer en controleer of het aantal niet-geactiveerde elementen nu nul is.</li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td>Vooraf ingestelde illustraties van de viewer retourneren 404 vanaf de voorvertoning in elementdetails of kopiëren, URL- en insluitcode</td> 
   <td><p>Ga als volgt te werk bij CRXDE Lite:</p> 
    <ol> 
     <li>Navigeer naar de map <code>&lt;sync-folder&gt;/_CSS/_OOTB</code> in de Dynamic Media-synchronisatiemap (bijvoorbeeld <code>/content/dam/_CSS/_OOTB</code>),</li> 
     <li>Zoek het metagegevensknooppunt van het problematische element (bijvoorbeeld <code>&lt;sync-folder&gt;/_CSS/_OOTB/CarouselDotsLeftButton_dark_sprite.png/jcr:content/metadata/</code>).</li> 
     <li>Controleer of <code>dam:scene7*</code>-eigenschappen aanwezig zijn. Als het element is gesynchroniseerd en gepubliceerd, ziet u dat de <code>dam:scene7FileStatus</code>-set is ingesteld op <strong>PublishComplete</strong>.</li> 
     <li>Poging om de illustratie rechtstreeks vanuit Dynamic Media aan te vragen door de waarden van de volgende eigenschappen en letterlijke tekenreeksen samen te voegen 
      <ul> 
       <li><code>dam:scene7Domain</code></li> 
       <li><code>"is/content"</code></li> 
       <li><code>dam:scene7Folder</code></li> 
       <li><code>&lt;asset-name&gt;</code></li> 
       <li>Voorbeeld: <code>https://&lt;server&gt;/is/content/myfolder/_CSS/_OOTB/CarouselDotsLeftButton_dark_sprite.png</code></li> 
      </ul> </li> 
    </ol> </td> 
   <td><p>Als de voorbeeldbestanden of voorinstellingsillustraties van de viewer niet zijn gesynchroniseerd of gepubliceerd, start u het gehele kopiëren/synchronisatieproces opnieuw:</p> 
    <ol> 
     <li>Navigeer naar CRXDE Lite. 
      <ul> 
       <li>Verwijderen <code>&lt;sync-folder&gt;/_CSS/_OOTB</code>.</li> 
      </ul> </li> 
     <li>Ga naar het CRX-pakketbeheer: <code>http://localhost:4502/crx/packmgr/</code><a href="http://localhost:4502/crx/packmgr/"></a> 
      <ol> 
       <li>Zoeken naar viewerpakket in lijst (begint met <span class="kbd">cq-dam-scene7-viewers-content</span>)</li> 
       <li>Klik <strong>Opnieuw installeren</strong>.</li> 
      </ol> </li> 
     <li>Onder Cloud Services, navigeer aan de pagina van de Configuratie van Dynamic Media, dan open de doos van de configuratiedialoog voor uw configuratie Dynamic Media - S7. 
      <ul> 
       <li>Breng geen veranderingen aan, klik <strong>sparen</strong>. Hierdoor wordt de logica opnieuw geactiveerd voor het maken en synchroniseren van de voorbeeldelementen, de CSS voor viewervoorinstellingen en illustraties.<br /> <br /> </li> 
      </ul> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>
