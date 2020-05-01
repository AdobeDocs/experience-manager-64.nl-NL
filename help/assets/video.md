---
title: Video
seo-title: Video
description: Leer hoe u met video werkt in Dynamic Media
seo-description: Leer hoe u met video werkt in Dynamic Media
uuid: 15e89f88-2787-472d-bbb6-d370bbab9228
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: Dynamic-Media
content-type: reference
discoiquuid: b721dc7c-b056-47f5-9489-9f4db45b68a0
translation-type: tm+mt
source-git-commit: a892ef7ab018aca715693125808d7ade540c8242

---


# Video {#video}

In deze sectie wordt het werken met video in Dynamic Media beschreven.

## Snel starten: Video&#39;s {#quick-start-videos}

De volgende stapsgewijze workflowbeschrijving is ontworpen om u te helpen snel aan de slag te gaan met adaptieve videosets in Dynamic Media. Nadat elke stap verwijzingen naar onderwerprubrieken zijn waar u meer informatie kunt vinden.

>[!NOTE]
>
>Voordat u met video werkt in Dynamic Media, moet u ervoor zorgen dat uw AEM-beheerder de Dynamic Media Cloud Services al heeft ingeschakeld en geconfigureerd.
>
>* Zie Dynamische Media Cloud Services [configureren in Dynamische media configureren - hybride modus.](/help/assets/config-dynamic.md)
>* Zie het [Vormen Dynamische Media - wijze](config-dms7.md) Scene7 en het [Oplossen van problemen Dynamische Media - wijze Scene7](troubleshoot-dms7.md)
>



1. **Voer de volgende handelingen uit om uw video** &#39;s met dynamische media te uploaden:

   * Maak uw eigen videocoderingsprofiel. U kunt ook gewoon het vooraf gedefinieerde profiel Adaptieve videocodering gebruiken dat bij Dynamische media wordt geleverd.

      * [Een videocoderingsprofiel](video-profiles.md)maken.
      * Meer informatie over de [aanbevolen procedures voor videocodering](#best-practices-for-encoding-videos).
   * Koppel het videoverwerkingsprofiel aan een of meer mappen waar u de hoofdvideo&#39;s gaat uploaden.

      * [Een videoprofiel toepassen op mappen](video-profiles.md#applying-a-video-profile-to-folders).
      * Meer informatie over de [aanbevolen procedures voor het ordenen van uw digitale middelen voor het gebruik van verwerkingsprofielen](organize-assets.md#organize-using-folders).
      * Meer informatie over het [ordenen van digitale middelen](organize-assets.md).
   * Upload uw stramienvideo&#39;s naar de mappen. U kunt videobestanden uploaden van maximaal 15 GB elk. Wanneer u video&#39;s aan de map toevoegt, worden deze gecodeerd volgens het videoverwerkingsprofiel dat u aan de map hebt toegewezen.

      * [Upload uw video](managing-video-assets.md#uploading-and-previewing-video-assets)&#39;s.
      * Meer informatie over [ondersteunde invoerbestandsindelingen](assets-formats.md#supported-multimedia-formats).
   * Controleer hoe de [videocodering vordert](#monitoring-video-encoding-and-youtube-publishing-progress) vanuit de asset- of workflowweergave.




1. **Voer een van de volgende handelingen uit om uw dynamische media-video** &#39;s te beheren:

   * Video-elementen organiseren, doorbladeren en zoeken

      * [Digitale elementen ordenen](organize-assets.md)

         Meer informatie over de [aanbevolen procedures voor het ordenen van uw digitale middelen voor het gebruik van verwerkingsprofielen](organize-assets.md#organize-using-folders)

      * [Video-elementen](search-video-assets.md) zoeken of elementen [zoeken](managing-assets-touch-ui.md#searching-assets)
   * Video-elementen voorvertonen en publiceren

      * Bekijk de bronvideo en de gecodeerde vertoningen van de video samen met de bijbehorende miniaturen:

         [Een voorvertoning weergeven van video](managing-video-assets.md#uploading-and-previewing-video-assets) &#39;s of elementen [voorvertonen](previewing-assets.md)

         [Video-uitvoeringen weergeven](video-renditions.md)

         [Video-uitvoeringen beheren](managing-assets-touch-ui.md#managing-renditions)

      * [Viewervoorinstellingen beheren](managing-viewer-presets.md)
      * [Elementen publiceren](publishing-dynamicmedia-assets.md)
   * Werken met videometagegevens

      * Bekijk de eigenschappen van een gecodeerde video-uitvoering, zoals framesnelheid, audio- en videobitsnelheid en codec:

         [Eigenschappen van video-uitvoeringen weergeven](video-renditions.md)

      * Bewerk de eigenschappen van video, zoals de titel, beschrijving en tags, aangepaste metagegevensvelden:

         [Video-eigenschappen bewerken](managing-assets-touch-ui.md#editing-properties)

      * [Metagegevens voor digitale elementen beheren](metadata.md)
      * [Metagegevensschema&#39;s](metadata-schemas.md)
   * Video&#39;s bekijken, goedkeuren en notities aanbrengen

      * [Video&#39;s](managing-video-assets.md#annotating-video-assets) annoteren of elementen [annoteren](managing-assets-touch-ui.md#annotating)
      * [Workflows toepassen op elementen](assets-workflow.md) of een workflow [starten voor een element](managing-assets-touch-ui.md#starting-a-workflow-on-an-asset)
      * [Mapmiddelen controleren](bulk-approval.md)
      * [Projecten](/help/sites-authoring/projects.md)




1. **Publiceer uw dynamische Media video** door één van het volgende te doen:

   * Als u Adobe Experience Manager gebruikt als uw webcontentbeheersysteem, kunt u video&#39;s rechtstreeks toevoegen aan uw webpagina&#39;s.

      * [Video&#39;s toevoegen aan uw webpagina](adding-dynamic-media-assets-to-pages.md)&#39;s.
   * Als u een systeem voor webcontentbeheer van derden gebruikt, kunt u video&#39;s koppelen aan of insluiten in uw webpagina&#39;s.

      * Video integreren met URL:

         [URL&#39;s koppelen aan uw webapplicatie](linking-urls-to-yourwebapplication.md).
      * Video integreren met gebruik van ingesloten code op webpagina:

         [De videoviewer insluiten op een webpagina](embed-code.md).
   * [Video&#39;s publiceren naar YouTube](#publishing-videos-to-youtube).
   * [Videorapporten](#viewing-video-reports)genereren.
   * [Bijschriften toevoegen aan video](#adding-captions-to-video).



## Werken met video in dynamische media {#working-with-video-in-dynamic-media}

Video in Dynamic Media is een end-to-end oplossing die het gemakkelijk maakt om adaptieve video van hoge kwaliteit te publiceren voor het streamen op meerdere schermen, waaronder desktopcomputers, iOS, Android, Blackberry en mobiele Windows-apparaten. Een adaptieve videoreeks groepeert versies van de zelfde video die bij verschillende beetjetarieven en formaten zoals 400 kbps, 800 kbps, en 1000 kbps worden gecodeerd. De desktopcomputer of het mobiele apparaat detecteert de beschikbare bandbreedte.

Op een mobiel iOS-apparaat detecteert het bijvoorbeeld een bandbreedte zoals 3G, 4G of Wi-Fi. Vervolgens wordt automatisch de naar rechts gecodeerde video geselecteerd bij de verschillende bitsnelheden van de video in de adaptieve videoset. De video wordt gestreamd naar desktops, mobiele apparaten of tablets.

Bovendien wordt de videokwaliteit automatisch dynamisch geschakeld als de netwerkomstandigheden veranderen op het bureaublad of op het mobiele apparaat. Ook, als een klant volledig-schermwijze op een Desktop ingaat, antwoordt de Adaptieve VideoReeks door een betere resolutie te gebruiken, daardoor verbeterend de het bekijken van de klant ervaring. Het gebruik van Adaptieve videosets biedt u de best mogelijke weergave voor klanten die Dynamic Media-video afspelen op meerdere schermen en apparaten.

De logica die een videospeler gebruikt om te bepalen welke gecodeerde video moet worden afgespeeld of tijdens het afspelen moet worden geselecteerd, is gebaseerd op het volgende algoritme:

1. Videospeler laadt het eerste videofragment op basis van de bitsnelheid die het dichtst bij de waarde ligt die is ingesteld voor de &#39;initiële bitsnelheid&#39; in de speler zelf.
1. De videospelerschakelaars die op veranderingen in de bandbreedtesnelheid worden gebaseerd die de volgende criteria gebruiken:

   1. De speler kiest de hoogste bandbreedtestroom onder of gelijk aan de geschatte bandbreedte.
   1. De speler overweegt slechts 80% van de beschikbare bandbreedte. Als er echter een overstap wordt gemaakt, is het conservatiever bij slechts 70% om overschatting te voorkomen en onmiddellijk terug te keren.

Voor gedetailleerde technische informatie over het algoritme, zie [https://android.googlesource.com/platform/frameworks/av/+/master/media/libstagefright/httplive/LiveSession.cpp](https://android.googlesource.com/platform/frameworks/av/+/master/media/libstagefright/httplive/LiveSession.cpp)

Voor het beheren van afzonderlijke video- en adaptieve videosets wordt het volgende ondersteund:

* Video uploaden van diverse ondersteunde video-indelingen en audio-indelingen en video coderen naar MP4 H.264-indeling, zodat deze op meerdere schermen kan worden afgespeeld. U kunt vooraf gedefinieerde adaptieve videovoorinstellingen gebruiken, voorinstellingen voor één videocodering gebruiken of uw eigen codering aanpassen om de kwaliteit en de grootte van de video te bepalen.

   * Wanneer een adaptieve videoset wordt gegenereerd, bevat deze MP4-video&#39;s.
   * **Opmerking**: Stramien-/bronvideo&#39;s worden niet toegevoegd aan een adaptieve videoset.

* ondertiteling in alle HTML5-videoviewers.
* Video organiseren, doorbladeren en doorzoeken met volledige metagegevensondersteuning voor een efficiënt beheer van video-elementen.
* Lever Adaptieve videosets naar het web, naar desktops en mobiele apparaten, waaronder de iPhone, iPad, Android, Blackberry en Windows-telefoon.

Adaptieve videostreaming wordt ondersteund op verschillende iOS-platforms. Zie de naslaggids voor [Adobe Viewers](https://marketing.adobe.com/resources/help/en_US/s7/viewers_ref/c_about.html).

Dynamische media ondersteunt het afspelen van mobiele video voor MP4 H.264-video. U vindt Blackberry-apparaten die deze video-indeling ondersteunen op de volgende locatie: [Ondersteunde video-indelingen op Blackberry](https://support.blackberry.com/kb/articleDetail?ArticleNumber=000005482).

U kunt de apparaten van Vensters vinden die dit videoformaat bij het volgende steunen: [Ondersteunde video-indelingen op Windows Phone](https://msdn.microsoft.com/library/windows/apps/ff462087%28v=vs.105%29.aspx)

* Speel de video terug gebruikend Dynamische Media VideoKijker vooraf instelt, met inbegrip van het volgende:

   * Afzonderlijke videoviewers.
   * Gemengde Media-viewers die zowel video- als afbeeldingsinhoud combineren.

* Configureer videospelers om aan uw brandingbehoeften te voldoen.
* Video met een eenvoudige URL of insluitcode integreren in uw website, mobiele site of mobiele toepassing.

Zie [Dynamische videoweergave](https://s7d9.scene7.com/s7/uvideo.jsp?asset=GeoRetail/Mop_AVS&amp;config=GeoRetail/Universal_Video1&amp;stageSize=640,480).

Zie ook [Informatie over HTML5 Viewers](https://marketing.adobe.com/resources/help/en_US/s7/viewers_ref/c_html5_viewers_about.html) in de Adobe Scene7 Viewer Reference Guide.

## Beste praktijken: De HTML5-videoviewer gebruiken {#best-practice-using-the-html-video-viewer}

De voorinstellingen van de dynamische media HTML5-videoviewer zijn robuuste videospelers. U kunt ze gebruiken om veel voorkomende problemen te voorkomen die samenhangen met het afspelen van HTML5-video en met problemen die samenhangen met mobiele apparaten, zoals een gebrek aan adaptieve streaminglevering en een beperkt bereik voor de desktopbrowser.

Aan de ontwerpkant van de speler, kunt u alle functionaliteit van de videospeler ontwerpen gebruikend standaardhulpmiddelen van de Webontwikkeling. U kunt bijvoorbeeld de knoppen, besturingselementen en de achtergrond van een aangepaste posterafbeelding ontwerpen met HTML5 en CSS, zodat u uw klanten kunt bereiken met een aangepaste weergave.

Aan de afspeelzijde van de viewer wordt automatisch de videocapaciteit van de browser gedetecteerd. Vervolgens wordt de video afgespeeld met behulp van HLS-streaming (adaptieve videostreaming). Als deze leveringsmethoden niet aanwezig zijn, wordt in plaats daarvan HTML5 progressief gebruikt.

Door de combinatie in één speler van de capaciteit om de playbackcomponenten te ontwerpen gebruikend HTML5 en CSS, ingebedde playback te hebben, en adaptieve en progressieve het stromen te gebruiken afhankelijk van het vermogen van browser, breidt u het bereik van uw rijke media inhoud tot zowel Desktop als mobiele gebruikers uit en verzekert een gestroomlijnde videoervaring.

Zie ook [Informatie over HTML5 Viewers](https://marketing.adobe.com/resources/help/en_US/s7/viewers_ref/c_html5_viewers_about.html) in de Adobe Viewers Reference Guide.

### Video afspelen op bureaubladcomputers en mobiele apparaten met de HTML5-videoviewer {#playback-of-video-on-desktop-computers-and-mobile-devices-using-the-html-video-viewer}

Voor adaptieve videostreaming op het bureaublad en mobiele apparaten zijn de video&#39;s die worden gebruikt voor het schakelen naar een andere bitsnelheid, gebaseerd op alle MP4-video&#39;s in de adaptieve videoset.

Het afspelen van video vindt plaats met behulp van HLS-videostreaming (HTTP Live Streaming) of progressieve videodownload. In eerdere versies van AEM, zoals 6.0, 6.1 en 6.2, werden video&#39;s gestreamd via HTTP.

In AEM 6.3 en hoger worden video&#39;s nu echter gestreamd via HTTPS (dat wil zeggen, HLS-videostreaming) omdat de URL van de DM-gatewayservice altijd HTTPS gebruikt. Merk op dat er geen klanteninvloed in dit standaardgedrag is. Videostreaming vindt altijd plaats via HTTPS, tenzij dit niet door de browser wordt ondersteund. (zie de volgende tabel). Op grond daarvan wordt met

* Als u een HTTPS-website met HTTPS-videostreaming hebt, is streaming prima.
* Als u een HTTP-website met HTTPS-videostreaming hebt, is streaming prima en zijn er geen problemen met gemengde inhoud in de webbrowser.

HLS (HTTP Live Streaming) is een Apple-standaard voor adaptieve videostreaming die het afspelen automatisch aanpast op basis van de capaciteit van de netwerkbandbreedte. Ook kan de klant naar elk punt in de video zoeken zonder dat de rest van de video hoeft te worden gedownload (zie ook Live HTTP-streaming).

Progressieve video wordt geleverd door de video lokaal te downloaden en op het desktopscherm of mobiele apparaat van de gebruiker op te slaan.

De volgende lijst beschrijft het apparaat, browser, en playbackmethode van video&#39;s op Desktopcomputers en mobiele apparaten gebruikend de VideoKijker Scene7.

<table> 
 <tbody> 
  <tr> 
   <td><strong>Apparaat</strong></td> 
   <td><strong>Browser</strong></td> 
   <td><strong>Video-afspeelmodus</strong></td> 
  </tr> 
  <tr> 
   <td>Desktop</td> 
   <td>Internet Explorer 9 en 10</td> 
   <td>Progressieve download.</td> 
  </tr> 
  <tr> 
   <td>Desktop</td> 
   <td>Internet Explorer 11+</td> 
   <td>In Windows 8 en Windows 10 - Gebruik van HTTPS forceren wanneer om HLS wordt gevraagd. Bekende beperking: HTTP op HLS werkt niet in deze browser/werkend systeemcombinatie<br /> <br /> op Vensters 7 - Progressieve download. Gebruikt de standaardlogica voor het selecteren van het protocol HTTP versus HTTPS.</td> 
  </tr> 
  <tr> 
   <td>Desktop</td> 
   <td>Firefox 23-44</td> 
   <td>Progressieve download.</td> 
  </tr> 
  <tr> 
   <td>Desktop</td> 
   <td>Firefox 45 of hoger</td> 
   <td>HLS-videostreaming.</td> 
  </tr> 
  <tr> 
   <td>Desktop</td> 
   <td>Chroom</td> 
   <td>HLS-videostreaming.</td> 
  </tr> 
  <tr> 
   <td>Desktop</td> 
   <td>Safari (Mac)</td> 
   <td>HLS-videostreaming.</td> 
  </tr> 
  <tr> 
   <td>Mobiel</td> 
   <td>Chrome (Android 6 of eerder)</td> 
   <td>Progressieve download.</td> 
  </tr> 
  <tr> 
   <td>Mobiel</td> 
   <td>Chrome (Android 7 of hoger)</td> 
   <td>HLS-videostreaming.</td> 
  </tr> 
  <tr> 
   <td>Mobiel</td> 
   <td>Android (standaardbrowser)</td> 
   <td>Progressieve download.</td> 
  </tr> 
  <tr> 
   <td>Mobiel</td> 
   <td>Safari (iOS)</td> 
   <td>HLS-videostreaming.</td> 
  </tr> 
  <tr> 
   <td>Mobiel</td> 
   <td>Chrome (iOS)</td> 
   <td>HLS-videostreaming.</td> 
  </tr> 
  <tr> 
   <td>Mobiel</td> 
   <td>Blackberry</td> 
   <td>HLS-videostreaming.</td> 
  </tr> 
 </tbody> 
</table>

## Architectuur van Dynamic Media-video-oplossing {#architecture-of-dynamic-media-video-solution}

De volgende afbeelding toont de algemene ontwerpworkflow voor video&#39;s die via DMGateway worden geüpload en gecodeerd en voor openbare consumptie beschikbaar worden gesteld.

![chlimage_1-427](assets/chlimage_1-427.png)

## Hybride publicatiearchitectuur voor video&#39;s {#hybrid-publishing-architecture-for-videos}

![chlimage_1-428](assets/chlimage_1-428.png)

## Aanbevolen werkwijzen voor het coderen van video&#39;s {#best-practices-for-encoding-videos}

De workflow **[!UICONTROL Video coderen met Dynamische media]** codeert video als u dynamische media hebt ingeschakeld en videocloudservices hebt ingesteld. In deze workflow worden de historie en informatie over fouten van het workflowproces vastgelegd. Zie [De voortgang van videocodering en YouTube-publicatie controleren](#monitoring-video-encoding-and-youtube-publishing-progress). If you have enabled Dynamic Media and set up Video Cloud services, the **[!UICONTROL Dynamic Media Encode Video]** workflow automatically takes effect when you upload a video. (If you are not using Dynamic Media, the **[!UICONTROL DAM Update Asset]** workflow takes effect.)

Hier volgt een overzicht van tips voor het coderen van bronvideobestanden.

Raadpleeg het volgende voor advies over videocodering:

* Artikel: *Streaming 101: De basisbeginselen — Codecs, Bandbreedte, Gegevenssnelheid en Resolutie:* [www.adobe.com/go/learn_s7_streaming101_en](https://www.adobe.com/go/learn_s7_streaming101_en).
* Video: *Basisbeginselen van videocodering:* [www.adobe.com/go/learn_s7_encoding_en](https://www.adobe.com/go/learn_s7_encoding_en).

### Bronvideobestanden {#source-video-files}

Wanneer u een videobestand codeert, gebruikt u een videobronbestand van de hoogst mogelijke kwaliteit. Gebruik geen eerder gecodeerde videobestanden omdat deze bestanden al zijn gecomprimeerd en als u verder codeert, wordt een video van subparkwaliteit gemaakt.

In de volgende tabel worden de aanbevolen grootte, de hoogte-breedteverhouding en de minimale bitsnelheid beschreven die uw bronvideobestanden moeten hebben voordat u ze codeert:

| Grootte | Hoogte-breedteverhouding | Minimale bitsnelheid |
|--- |--- |--- |
| 1024 x 768 | 4:3 | 4500 kbps voor de meeste video&#39;s. |
| 1280 x 720 | 16:9 | 3000 - 6000 kbps, afhankelijk van de hoeveelheid beweging in de video. |
| 1920 x 1080 | 16:9 | 6000 - 8000 kbps, afhankelijk van de mate van beweging in de video. |

### De metagegevens van een bestand ophalen {#obtaining-a-file-s-metadata}

U kunt de metagegevens van een bestand verkrijgen door de metagegevens van het bestand te bekijken met een gereedschap voor videobewerking of met een toepassing die is ontworpen voor het verkrijgen van metagegevens. Hieronder vindt u instructies voor het gebruik van MediaInfo, een toepassing van derden, voor het verkrijgen van de metagegevens van een videobestand:

1. Ga naar deze webpagina: [https://mediaarea.net/en/MediaInfo](https://mediaarea.net/en/MediaInfo).
1. Selecteer en download het installatieprogramma voor de GUI-versie die u gebruikt en volg de installatie-instructies.
1. Klik na de installatie met de rechtermuisknop op het videobestand (alleen Windows) en selecteer **[!UICONTROL MediaInfo]**, of open **[!UICONTROL MediaInfo]** en sleep het videobestand naar de toepassing. U ziet alle metagegevens die aan het videobestand zijn gekoppeld, inclusief de breedte, hoogte en fps.

### Hoogte-breedteverhouding {#aspect-ratio}

Wanneer u een voorinstelling voor videocodering kiest of maakt voor het hoofdvideobestand, moet u ervoor zorgen dat de voorinstelling dezelfde hoogte-breedteverhouding heeft als het hoofdvideobestand. De hoogte-breedteverhouding is de verhouding tussen de breedte en de hoogte van de video.

Als u de hoogte-breedteverhouding van een videobestand wilt bepalen, vraagt u de metagegevens van het bestand op en noteert u de breedte en hoogte van het bestand (zie De metagegevens van het bestand hierboven verkrijgen). Gebruik vervolgens deze formule om de hoogte-breedteverhouding te bepalen:

*width/height = hoogte-breedteverhouding*

In de volgende tabel wordt beschreven hoe de resultaten van de formule worden omgezet in algemene opties voor de hoogte-breedteverhouding:

| Resultaat van formule | Hoogte-breedteverhouding |
|--- |--- |
| 1.33 | 4:3 |
| 0.75 | 3:4 |
| 1.78 | 16:9 |
| 0.56 | 9:16 |

Een video van 1440 x 1080 hoogte heeft bijvoorbeeld een hoogte-breedteverhouding van 1440/1080 of 1,33. In dit geval kiest u een voorinstelling voor videocodering met een hoogte-breedteverhouding van 4:3 om het videobestand te coderen.

### Bitsnelheid {#bitrate}

Bitsnelheid is de hoeveelheid gegevens die wordt gecodeerd om één seconde video af te spelen. De bitsnelheid wordt gemeten in kilobits per seconde (Kbps).

Omdat in alle codecs compressie met verlies wordt gebruikt, is bitsnelheid de belangrijkste factor voor de videokwaliteit. Bij compressie met verlies neemt de kwaliteit af naarmate u een videobestand comprimeert. Daarom zijn alle andere eigenschappen gelijk (de resolutie, framesnelheid en codec), hoe lager de bitsnelheid, hoe lager de kwaliteit van het gecomprimeerde bestand.

Wanneer u een codering voor bitsnelheden selecteert, kunt u kiezen uit twee typen:

* **Codering** met constante bitsnelheid (CBR) - Tijdens CBR-codering blijft de bitsnelheid of het aantal bits per seconde tijdens het coderingsproces ongewijzigd. Bij CBR-codering blijft de gegevenssnelheid van de set behouden voor de instelling van de gehele video. Bij CBR-codering worden mediabestanden niet geoptimaliseerd voor kwaliteit, maar wordt opslagruimte bespaard.

   Gebruik CBR als uw video een vergelijkbaar bewegingsniveau in de gehele video bevat. CBR wordt meestal gebruikt voor het streamen van video-inhoud. Zie ook Video-coderingsparameters [op aangepaste basis](video-profiles.md#using-custom-added-video-encoding-parameters)gebruiken.

* **VBR-codering** (Variable Bitrate Encoding) - VBR-codering past de gegevenssnelheid naar beneden en naar de bovenste limiet die u instelt, aan op basis van de gegevens die de compressor nodig heeft. Dit betekent dat de bitsnelheid van het mediabestand tijdens een VBR-coderingsproces dynamisch wordt verhoogd of verlaagd, afhankelijk van de bitsnelheidbehoeften van mediabestanden.

   VBR duurt langer om te coderen maar produceert de gunstigste resultaten; de kwaliteit van het mediabestand is superieur. VBR wordt het meest meestal gebruikt voor http progressieve levering van video-inhoud.

**Wanneer moet u VBR versus CRB gebruiken?**
Als het gaat om het selecteren van VBR tegenover CBR, wordt het bijna altijd geadviseerd dat u VBR voor uw media dossiers gebruikt. VBR biedt bestanden van hogere kwaliteit tegen concurrerende bitsnelheden. Wanneer u VBR gebruikt, moet u ervoor zorgen dat u met codering met twee controles gebruikt en de maximale bitsnelheid instellen op 1,5x de bitsnelheid van de doelvideo.

Wanneer u een voorinstelling voor videocodering kiest, moet u rekening houden met de verbindingssnelheid van de eindgebruiker. Kies een voorinstelling met een gegevenssnelheid van 80 procent van die snelheid. Als de verbindingssnelheid van de eindgebruiker van het doel bijvoorbeeld 1000 Kbps is, is de beste voorinstelling een snelheid met een videogegevenssnelheid van 800 Kbps.

In deze tabel wordt de gegevenssnelheid beschreven van standaardverbindingssnelheden.

| Snelheid (Kbps) | Verbindingstype |
|--- |--- |
| 256 | Inbelverbinding. |
| 800 | Normale mobiele verbinding. Kies hiervoor een gegevenssnelheid tussen 400 en maximaal 800 voor 3G-ervaringen. |
| 2000 | Standaardbreedbandverbinding voor desktops. Voor deze verbinding, richt een gegevenstarief in de waaier 800-2000 Kbps, met de meeste doelstellingen gemiddeld 1200-1500 Kbps. |
| 5000 | Typische breedbandverbinding. Codering in dit bovenste bereik wordt niet aanbevolen, omdat de video bij deze snelheid niet beschikbaar is voor de meeste consumenten. |

### Resolutie {#resolution}

**Met Resolutie** worden de hoogte en breedte van een videobestand in pixels beschreven. De meeste bronvideo wordt opgeslagen met een hoge resolutie (bijvoorbeeld 1920 x 1080). Voor streamingdoeleinden wordt bronvideo gecomprimeerd tot een lagere resolutie (640 x 480 of lager).

Resolutie en gegevenssnelheid zijn twee geïntegreerde gekoppelde factoren die de videokwaliteit bepalen. Als u dezelfde videokwaliteit wilt behouden, geldt dat hoe hoger het aantal pixels in een videobestand (hoe hoger de resolutie), hoe hoger de gegevenssnelheid. Neem bijvoorbeeld het aantal pixels per frame in een videobestand met een resolutie van 320 x 240 en een resolutie van 640 x 480:

| Resolutie | Pixels per frame |
|--- |--- |
| 320 x 240 | 76,800 |
| 640 x 480 | 307,200 |

Het bestand van 640 x 480 heeft vier keer zoveel pixels per frame. Als u voor deze twee voorbeeldresoluties dezelfde gegevenssnelheid wilt bereiken, past u viermaal de compressie toe op het bestand van 640 x 480, waardoor de kwaliteit van de video kan afnemen. Daarom levert een videogegevenssnelheid van 250 Kbps beelden van hoge kwaliteit bij een resolutie van 320 x 240, maar niet bij een resolutie van 640 x 480.

Over het algemeen geldt dat hoe hoger de gegevenssnelheid, hoe beter uw video er uitziet en hoe hoger de resolutie die u gebruikt, hoe hoger de gegevenssnelheid die u nodig hebt om de weergavekwaliteit te behouden (in vergelijking met lagere resoluties).

Omdat de resolutie en de gegevenssnelheid zijn gekoppeld, hebt u twee opties bij het coderen van video:

* Kies een gegevenssnelheid en codeer vervolgens met de hoogste resolutie die er goed uitziet in de gekozen gegevenssnelheid.
* Kies een resolutie en codeer met de gegevenssnelheid die nodig is voor video van hoge kwaliteit met de gekozen resolutie.

Wanneer u een voorinstelling voor videocodering kiest (of maakt) voor het hoofdvideobestand, gebruikt u deze tabel om de juiste resolutie in te stellen:

| Resolutie | Hoogte (pixels) | Schermgrootte |
|--- |--- |--- |
| 240p | 240 | Glanzend scherm |
| 300p | 300 | Klein scherm, meestal voor mobiele apparaten |
| 360p | 360 | Klein scherm |
| 480p | 480 | Standaardscherm |
| 720p | 720 | Groot scherm |
| 1080p | 1080 | High-definition groot scherm |

### FPS (frames per seconde) {#fps-frames-per-second}

In de Verenigde Staten en Japan wordt de meeste video opgenomen met een snelheid van 29,97 frames per seconde (fps); in Europa wordt de meeste video opgenomen met 25 fps. Film wordt opgenomen bij 24 fps.

Kies een voorinstelling voor videocodering die overeenkomt met de fps-snelheid van het hoofdvideobestand. Als de hoofdvideo bijvoorbeeld 25 fps is, kiest u een coderingsvoorinstelling met 25 fps. Standaard wordt voor alle aangepaste codering de fps van het hoofdvideobestand gebruikt. Daarom hoeft u de fps-instelling niet expliciet op te geven wanneer u een voorinstelling voor videocodering maakt.

### Afmetingen videocodering {#video-encoding-dimensions}

Voor optimale resultaten selecteert u de coderingsafmetingen, zodat de bronvideo een volledig veelvoud van alle gecodeerde video&#39;s is.

Als u deze verhouding wilt berekenen, deelt u de bronbreedte door de gecodeerde breedte om de breedteverhouding op te halen. Vervolgens deelt u de bronhoogte door de gecodeerde hoogte om de hoogte-breedteverhouding te bepalen.

Als de resulterende verhouding een geheel geheel getal is, betekent dit dat de video optimaal wordt geschaald. Als de resulterende verhouding geen geheel geheel getal is, is dit van invloed op de videokwaliteit doordat pixelartefacten overblijven op het scherm. Dit effect is vooral opvallend wanneer de video tekst heeft.

Stel dat uw bronvideo bijvoorbeeld 1920 x 1080 is. In de volgende tabel bieden de drie gecodeerde video&#39;s de optimale coderingsinstellingen.

<table> 
 <tbody> 
  <tr> 
   <th><p>Videotype</p> </th> 
   <th><p>Breedte x hoogte</p> </th> 
   <th><p>Breedteverhouding</p> </th> 
   <th><p>Hoogteverhouding</p> </th> 
  </tr>
  <tr> 
   <td><p>Bron</p> </td> 
   <td><p>1920 x 1080</p> </td> 
   <td><p>1</p> </td> 
   <td><p>1</p> </td> 
  </tr> 
  <tr> 
   <td><p>Gecodeerd</p> </td> 
   <td><p>960 x 540</p> </td> 
   <td><p>2</p> </td> 
   <td><p>2</p> </td> 
  </tr> 
  <tr> 
   <td><p>Gecodeerd</p> </td> 
   <td><p>640 x 360</p> </td> 
   <td><p>3</p> </td> 
   <td><p>3</p> </td> 
  </tr> 
  <tr> 
   <td><p>Gecodeerd</p> </td> 
   <td><p>480 x 270</p> </td> 
   <td><p>4</p> </td> 
   <td><p>4</p> </td> 
  </tr> 
 </tbody> 
</table>

### Gecodeerde videobestandsindeling {#encoded-video-file-format}

Dynamische media raadt u aan voorinstellingen voor MP4 H.264-videocodering te gebruiken. Omdat MP4-bestanden de H.264-videocodec gebruiken, biedt deze video van hoge kwaliteit, maar met een gecomprimeerde bestandsgrootte.

## Video&#39;s publiceren naar YouTube {#publishing-videos-to-youtube}

U kunt AEM-video-elementen op locatie rechtstreeks publiceren naar een YouTube-kanaal dat u eerder hebt gemaakt.

Als u video-elementen naar YouTube wilt publiceren, stelt u AEM-elementen in met tags. U koppelt deze tags aan een YouTube-kanaal. Als de tag van een video-element overeenkomt met de tag van een YouTube-kanaal, wordt de video gepubliceerd naar YouTube. Als het video-element geen tag heeft, wordt het niet gepubliceerd naar YouTube.

Wanneer u naar YouTube publiceert, wordt het verwerkingsprofielsysteem in AEM en dus ook het videocoderingsprofiel overgeslagen. Deze bypass treedt op omdat YouTube een eigen codering heeft, zodat een videoverwerkingsprofiel niet nodig is. In de meeste gevallen wordt echter verwacht dat uw video-elementen al via een videoverwerkingsprofiel zijn afgespeeld. Wanneer u het videoverwerkingsprofiel overslaat en rechtstreeks naar YouTube publiceert, betekent dit gewoon dat uw video-element in AEM Asset geen zichtbare miniatuur krijgt. Dit betekent ook dat als u in de dynamische-mediarijmodus werkt, video&#39;s die niet zijn gecodeerd, niet werken met de dynamische-mediatypen.

Wanneer u video-elementen publiceert naar YouTube-servers, voert u de volgende taken uit om een veilige en beveiligde server-naar-server verificatie met YouTube te garanderen:

1. [Google Cloud-instellingen configureren](#configuring-google-cloud-settings)
1. [Een YouTube-kanaal maken](#creating-a-youtube-channel)
1. [Codes toevoegen voor publicatie](#adding-tags-for-publishing)
1. [De YouTube-agent voor publicatiereplicatie inschakelen](#enabling-the-youtube-publish-replication-agent)
1. [YouTube instellen in AEM](#setting-up-youtube-in-aem)
1. [(Optioneel) De standaardeigenschappen van YouTube voor uw geüploade video&#39;s automatisch instellen](#optional-automating-the-setting-of-default-youtube-properties-for-your-uploaded-videos)
1. [Video&#39;s publiceren naar uw YouTube-kanaal](#publishing-videos-to-your-youtube-channel)
1. [(Optioneel) De gepubliceerde video op YouTube controleren](video.md#optional-verifying-the-published-video-on-youtube)
1. [YouTube-URL&#39;s koppelen aan uw webtoepassing](#linking-youtube-urls-to-your-web-application)

U kunt de publicatie van video&#39;s ook [ongedaan maken om deze van YouTube](#unpublishing-videos-to-remove-them-from-youtube)te verwijderen.

### Google Cloud-instellingen configureren {#configuring-google-cloud-settings}

Als u op YouTube wilt publiceren, hebt u een Google-account nodig. Als u een GMAIL-account hebt, hebt u al een Google-account. Als u geen Google-account hebt, kunt u er eenvoudig een maken. U hebt het account nodig omdat u referenties nodig hebt om video-elementen naar YouTube te publiceren. Als u al een account hebt gemaakt, slaat u deze taak over en gaat u verder met het [maken van een YouTube-kanaal](#creating-a-youtube-channel).

>[!NOTE]
>
>De volgende stappen waren correct op het moment van schrijven. Google werkt zijn websites echter regelmatig en zonder kennisgeving bij. Daarom kunnen deze stappen iets anders zijn.

**Google Cloud-instellingen** configureren:

1. Maak een nieuw Google-account.

   [https://accounts.google.com/SignUp?service=mail](https://accounts.google.com/SignUp?service=mail)

   Als u al een Google-account hebt, gaat u verder met de volgende stap.

1. Ga naar [https://cloud.google.com/](https://cloud.google.com/).
1. Tik op de pagina Google Cloud Platform bovenaan op **[!UICONTROL Console]**. U moet zich mogelijk **aanmelden** met uw aanmeldingsgegevens van uw Google-account.
1. Tik op de pagina **[!UICONTROL Dashboard]** op **[!UICONTROL Project]** maken.
1. In het **[!UICONTROL Nieuwe de dialoogvakje van het Project]** , ga in een projectnaam in.

   Merk op dat uw project identiteitskaart op uw projectnaam wordt gebaseerd. Kies daarom de projectnaam zorgvuldig; het kan na het creëren niet worden veranderd. U moet dezelfde project-id opnieuw invoeren wanneer u YouTube later instelt in Adobe Experience Manager. U kunt identiteitskaart van het project willen neer schrijven.
1. Tik op **[!UICONTROL Maken]**.

1. Tik op het **[!UICONTROL dashboard]** van uw project in de **[!UICONTROL Aan de slag]** -kaart op API&#39;s **[!UICONTROL inschakelen en krijg referenties als sleutels]**.
1. Tik boven aan de **[!UICONTROL dashboardpagina]** op **[!UICONTROL Enable API]**.
1. Tik op de pagina **[!UICONTROL Bibliotheek]** onder YouTube-API&#39;s op de **[!UICONTROL YouTube-API]**.
1. Tik boven aan de pagina **YouTube Data API v3]** op **[!UICONTROL Enable]** om deze in te schakelen.
1. Mogelijk hebt u referenties nodig om de API te gebruiken. Tik zo nodig op **[!UICONTROL Credentials]** maken.
1. Van **[!UICONTROL waar zult u API van roepen?]** vervolgkeuzelijst: selecteer **[!UICONTROL Webserver (bijvoorbeeld node.js, Tomcat)]**.
1. Onder **[!UICONTROL welke gegevens gaat u toegang krijgen?]** Selecteer **[!UICONTROL Gebruikersgegevens]**.
1. Tik op **[!UICONTROL Welke referenties heb ik nodig?]**.
1. Voer onder de kop **[!UICONTROL Create an OAuth 2.0 client ID]** een unieke naam in.
1. Voer in het tekstveld onder de kop **[!UICONTROL Geautoriseerde JavaScript-oorsprong]** het volgende pad in, waarbij u uw eigen domein- en poortnummer in het pad vervangt, en druk vervolgens op **[!UICONTROL Enter]** om het pad naar de lijst toe te voegen:

   `https://<servername.domain>:<port_number>`

   Bijvoorbeeld, `https://1a2b3c.mycompany.com:4321`

   **Opmerking**: Het bovenstaande padvoorbeeld is alleen bedoeld ter illustratie.

1. Voer in het tekstveld onder de kop **[!UICONTROL Toegestane omleiding van URI&#39;s]** het volgende in, vervang uw eigen domein- en poortnummer in het pad en druk vervolgens op Enter om het pad aan de lijst toe te voegen:

   `https://<servername.domain>:<port#>/etc/cloudservices/youtube.youtubecredentialcallback.json`

   Bijvoorbeeld, `https://1a2b3c.mycompany.com:4321/etc/cloudservices/youtube.youtubecredentialcallback.json`

   **Opmerking**: Het bovenstaande padvoorbeeld is alleen bedoeld ter illustratie.

1. Tik op Client-id **[!UICONTROL maken]**.
1. Selecteer op de pagina Referenties onder de kop **[!UICONTROL Instellen van het bevestigingsscherm]** OAuth 2.0 het Gmail-adres dat u momenteel gebruikt.
1. Voer in het tekstveld onder de kop **[!UICONTROL Productnaam die aan de gebruikers]** wordt weergegeven, de tekst in die u wilt weergeven op het instemmingsscherm.

   Het toestemmingsscherm wordt getoond aan de beheerder AEM wanneer zij voor YouTube voor authentiek verklaren; AEM neemt contact op met YouTube voor toestemming.

1. Tik op **[!UICONTROL Doorgaan]**.
1. Tik op **[!UICONTROL Downloaden]** onder de kop **[!UICONTROL Referenties]** downloaden.
1. Sla het `client_id.json` bestand op.

   U hebt dit gedownloade json-bestand nodig wanneer u YouTube later instelt in Adobe Experience Manager.

1. Tik **[!UICONTROL op Gereed]**.

   Nu maakt u een YouTube-kanaal.

### Een YouTube-kanaal maken {#creating-a-youtube-channel}

Als u video&#39;s naar YouTube wilt publiceren, hebt u een of meer kanalen nodig. Als u al een YouTube-kanaal hebt gemaakt, kunt u deze taak overslaan en naar Codes **toevoegen voor publicatie** gaan.

>[!CAUTION]
>
>Zorg ervoor dat u al een of meer kanalen hebt ingesteld in YouTube &amp;ast;before&amp;ast; Voeg kanalen toe onder YouTube-instellingen in AEM (zie [YouTube instellen in AEM](#setting-up-youtube-in-aem) hieronder). Als u dit niet doet, krijgt u geen enkele waarschuwing voor bestaande kanalen. Google-verificatie vindt echter nog steeds plaats wanneer u een kanaal toevoegt, maar er is geen optie om te kiezen welk kanaal de video wordt verzonden.

**Een YouTube-kanaal** maken:

1. Ga naar [https://www.youtube.com](https://www.youtube.com/) en meld u aan met de referenties van uw Google-account.
1. Tik in de rechterbovenhoek van de YouTube-pagina op uw profielfoto (kan ook als een letter in een cirkel met effen kleuren worden weergegeven) en tik vervolgens op **[!UICONTROL YouTube-instellingen]** (pictogram met ronde versnelling).
1. Tik op de pagina **[!UICONTROL Overzicht]** onder de kop **[!UICONTROL Extra functies]** op Alle kanalen **[!UICONTROL bekijken of maak een nieuw kanaal]**.
1. Tik op de pagina **[!UICONTROL Kanalen]** op **[!UICONTROL Nieuw kanaal]**.
1. Voer op de pagina **[!UICONTROL Merkaccount]** in het veld Naam **** merkaccount een bedrijfsnaam of een andere kanaalnaam in die u kiest waar u uw video-elementen wilt publiceren en tik vervolgens op **[!UICONTROL Maken]**.

   Onthoud de naam die u hier invoert, omdat u deze opnieuw moet invoeren wanneer u YouTube instelt in AEM.

1. (Optioneel) Voeg desgewenst meer kanalen toe.

   Nu gaat u labels toevoegen voor publicatie.

### Codes toevoegen voor publicatie {#adding-tags-for-publishing}

Als u video&#39;s naar YouTube wilt publiceren, koppelt AEM tags aan een of meer YouTube-kanalen. Zie [Codes](/help/sites-administering/tags.md)beheren als u codes voor publicatie wilt toevoegen.

Of als u de standaardlabels wilt gebruiken in AEM, kunt u deze taak overslaan en naar de [Enable YouTube Publish Replication-agent](#enabling-the-youtube-publish-replication-agent)gaan.

### De YouTube-publicatiereplicatieagent inschakelen {#enabling-the-youtube-publish-replication-agent}

1. Tik in de linkerbovenhoek van AEM op het AEM-logo en tik vervolgens in de linkertrack op **[!UICONTROL Extra > Implementatie > Replicatie > Agents op auteur]**.
1. Tik op de pagina **[!UICONTROL Agenten van auteur]** op **[!UICONTROL YouTube Publish (youtube)]**.
1. Tik op de werkbalk rechts van Instellingen op **[!UICONTROL Bewerken]**.
1. Selecteer **[!UICONTROL Toegelaten]** checkbox om de replicatieagent aan te zetten.
1. Tik op **[!UICONTROL OK]**.

   U gaat nu YouTube instellen in AEM.

### YouTube instellen in AEM {#setting-up-youtube-in-aem}

1. In the upper-left corner of AEM, tap the AEM logo, then in the left rail, tap **[!UICONTROL Tools > Deployment > Cloud Services]**.
1. Tik onder de kop Services **[!UICONTROL van]** derden onder YouTube op **[!UICONTROL Configureren nu]**.
1. Voer in het dialoogvenster **Configuratie maken]** een titel (verplicht) en naam (optioneel) in de desbetreffende velden in.
1. Tik op **[!UICONTROL Maken]**.
1. In the **[!UICONTROL YouTube Account Settings]** dialog box, in the **[!UICONTROL Application Name]** field, enter the Google Project ID.

   U hebt de project-id opgegeven toen u aanvankelijk eerder Google Cloud-instellingen had geconfigureerd.

   Laat het dialoogvenster **[!UICONTROL YouTube-accountinstellingen]** geopend. daar kom je zo op terug .

1. Open met een teksteditor zonder opmaak het JSON-bestand dat u eerder hebt gedownload en opgeslagen in de taak Google Cloud-instellingen configureren.
1. Selecteer en kopieer de volledige JSON-tekst.
1. Return to the **[!UICONTROL YouTube Account Settings]** dialog box. In the **[!UICONTROL JSON Config]** field, paste the JSON text.
1. Tik op **[!UICONTROL OK]**.

   U stelt nu YouTube-kanalen in AEM in.

1. To the right of **[!UICONTROL Available Channels]**, tap **[!UICONTROL +]** (plus sign icon).
1. In the **[!UICONTROL YouTube Channel Settings]** dialog box, in the **[!UICONTROL Title]** field, enter the name of the channel that you created in the task **C[!UICONTROL reating a YouTube channel ]**earlier.

   U kunt desgewenst een beschrijving toevoegen.

1. Tik op **[!UICONTROL OK]**.
1. YouTube/Google-verificatie wordt weergegeven. Als u zich nog niet hebt aangemeld bij het Google Cloud-account, slaat u deze stap over.

   * Voer de Google-gebruikersnaam en het wachtwoord in die aan de Google Project-id en de JSON-tekst hierboven zijn gekoppeld.
   * Afhankelijk van hoeveel kanalen uw account twee of meer items bevat. Selecteer een kanaal. Selecteer het e-mailadres niet.
   * Tik op de volgende pagina op **[!UICONTROL Accepteren]** om toegang tot dit kanaal toe te staan.

1. Tik **[!UICONTROL toestaan**.

   U stelt nu labels in voor publiceren.

1. **Tags instellen voor publicatie** - Tik op de pagina **[!UICONTROL Cloud Services > YouTube]** op het pictogram **[!UICONTROL Potlood]** om de lijst met tags te bewerken die u wilt gebruiken.
1. Tik op het pictogram van de vervolgkeuzelijst (ondersteboven) om de lijst met beschikbare labels in AEM weer te geven.
1. Tik op een of meer tags om deze toe te voegen.

   Als u een toegevoegde tag wilt verwijderen, selecteert u de tag en tikt u op **[!UICONTROL X]**.

1. Tik op **[!UICONTROL OK]** als u alle gewenste tags hebt toegevoegd.

   Nu publiceert u video&#39;s naar uw YouTube-kanaal.

### (Optioneel) De standaardeigenschappen van YouTube voor uw geüploade video&#39;s automatisch instellen {#optional-automating-the-setting-of-default-youtube-properties-for-your-uploaded-videos}

U kunt de instelling van YouTube-eigenschappen automatiseren bij het uploaden van uw video&#39;s. U doet dit door een verwerkingsprofiel voor metagegevens te maken in AEM.

To create the metadata processing profile, you are first going to copy values from the **[!UICONTROL Field Label]**, **[!UICONTROL Map to property]**, and **[!UICONTROL Choices]** fields, all found in Metadata Schemas for video. Vervolgens kunt u het verwerkingsprofiel voor YouTube-videometadata opbouwen door die waarden eraan toe te voegen.

**U kunt als volgt de standaardeigenschappen van YouTube voor uw geüploade video** desgewenst automatiseren:

1. In the upper-left corner of AEM, tap the AEM logo, then in the left rail, tap **[!UICONTROL Tools > Assets > Metadata Schemas]**.
1. Tik **[!UICONTROL standaard]**. (Voeg geen vinkje toe aan het selectievak links van &quot;standaard&quot;.)
1. On the **[!UICONTROL default]** page, check the box to the left of **[!UICONTROL video]**, then tap **[!UICONTROL Edit]**.
1. Tik op het tabblad **[!UICONTROL Geavanceerd]** op de pagina **[!UICONTROL Metagegevensschema-editor]** .
1. Tik op **[!UICONTROL YouTube-categorie]** onder de kop YouTube Publishing. (Tik niet op de vervolgkeuzelijst YouTube-categorie.)
1. Ga als volgt te werk aan de rechterkant van de pagina, onder het tabblad **[!UICONTROL Instellingen]** :

   * Selecteer en kopieer de waarde in het tekstveld **[!UICONTROL Veldlabel]** .

      Plak de gekopieerde waarde in een open teksteditor. Deze waarde hebt u later nodig wanneer u uw verwerkingsprofiel voor metagegevens maakt. Laat de teksteditor geopend.

   * Selecteer en kopieer de waarde in het tekstveld **[!UICONTROL Toewijzen aan eigenschap]** .

      Plak de gekopieerde waarde in de geopende teksteditor. Deze waarde hebt u later nodig wanneer u uw verwerkingsprofiel voor metagegevens maakt. Laat de teksteditor geopend.

   * Selecteer en kopieer onder **[!UICONTROL Keuzen]** de standaardwaarde die u wilt gebruiken (zoals Personen en blogs of Wetenschap en Technologie).

      Plak de gekopieerde waarde in de geopende teksteditor. Deze waarde hebt u later nodig wanneer u uw verwerkingsprofiel voor metagegevens maakt. Laat de teksteditor geopend.

1. Tik onder de kop YouTube Publishing op **[!UICONTROL YouTube Privacy]**. (Tik niet op de vervolgkeuzelijst YouTube Privacy.)
1. Ga als volgt te werk aan de rechterkant van de pagina, onder het tabblad **[!UICONTROL Instellingen]** :

   * Selecteer en kopieer de waarde in het tekstveld **[!UICONTROL Veldlabel]** .

      Plak de gekopieerde waarde in een open teksteditor. Deze waarde hebt u later nodig wanneer u uw verwerkingsprofiel voor metagegevens maakt. Laat de teksteditor geopend.

   * Selecteer en kopieer de waarde in het tekstveld **[!UICONTROL Toewijzen aan eigenschap]** .

      Plak de gekopieerde waarde in de geopende teksteditor. Deze waarde hebt u later nodig wanneer u uw verwerkingsprofiel voor metagegevens maakt. Laat de teksteditor geopend.

   * Selecteer onder **[!UICONTROL Keuzen]** de standaardwaarde die u wilt gebruiken en kopieer deze. De keuzen zijn gegroepeerd in twee. Het onderste veld in het paar is de standaardwaarde die u wilt kopiëren, bijvoorbeeld public, unlist of private.

      Plak de gekopieerde waarde in de geopende teksteditor. Deze waarde hebt u later nodig wanneer u uw verwerkingsprofiel voor metagegevens maakt. Laat de teksteditor geopend.

1. Tik in de rechterbovenhoek van de pagina **[!UICONTROL Metadata Schema Editor]** op **[!UICONTROL Annuleren]**.
1. In the upper-left corner of AEM, tap the AEM logo, then in the left rail, tap **[!UICONTROL Tools > Assets > Metadata Profiles]**.

1. Tik op de pagina **[!UICONTROL Metadata Profiles** , in de rechterbovenhoek van de pagina, op **[!UICONTROL maken**. Voer in het dialoogvenster **[!UICONTROL Metagegevensprofiel** toevoegen in het tekstveld Titel **** profiel de naam in `YouTube Video`.
1. Tik op het tabblad **[!UICONTROL Geavanceerd]** op de pagina **** Metagegevensprofiel-editor.
1. Voeg de gekopieerde Publishing-waarden voor YouTube als volgt toe aan het profiel:

   * Tik rechts van de pagina op het tabblad **[!UICONTROL Formulier]** samenstellen.
   * Sleep de component met het label **[!UICONTROL Sectiekoptekst]** naar links en zet deze neer in het formuliergebied.
   * Tik op **[!UICONTROL Veldlabel]** om de component te selecteren.
   * Typ rechts op de pagina onder het tabblad **[!UICONTROL Instellingen]** in het tekstveld **[!UICONTROL Veldlabel]** `YouTube Publishing`.
   * Tap the **[!UICONTROL Build Form]** tab, then drag the component labeled **[!UICONTROL Single Line Text]** and drop it below the **[!UICONTROL YouTube Publishing]** heading that you just created.
   * Tik op **[!UICONTROL Veldlabel]** om de component te selecteren.
   * Plak rechts van de pagina, onder het tabblad **[!UICONTROL Instellingen]** , de waarden voor **[!UICONTROL YouTube Publishing]** (waarde van **[!UICONTROL veldlabel]** en **[!UICONTROL Toewijzen aan eigenschapwaarde]** ) die u eerder hebt gekopieerd, in hun respectievelijke velden op het formulier. Plak de waarde **[!UICONTROL Keuzen]** in het veld **[!UICONTROL Standaardwaarde]** .

1. Voeg de gekopieerde YouTube-privacywaarden als volgt toe aan het profiel:

   * Tik rechts van de pagina op het tabblad **[!UICONTROL Formulier]** samenstellen.
   * Sleep de component met het label **[!UICONTROL Sectiekoptekst]** naar links en zet deze neer in het formuliergebied.
   * Tik op **[!UICONTROL Veldlabel]** om de component te selecteren.
   * Voer rechts op de pagina onder het tabblad Instellingen in het tekstveld Veld Label `YouTube Privacy`.
   * Tap the **[!UICONTROL Build Form]** tab, then drag the component labeled **[!UICONTROL Single Line Text]** and drop it below the **[!UICONTROL YouTube Privacy]** heading you just created.
   * Tik op **[!UICONTROL Veldlabel]** om de component te selecteren.
   * Plak rechts van de pagina, onder het tabblad **[!UICONTROL Instellingen]** , de waarden voor **[!UICONTROL YouTube Publishing]** (waarde van **[!UICONTROL veldlabel]** en **[!UICONTROL Toewijzen aan eigenschapwaarde]** ) die u eerder hebt gekopieerd, in hun respectievelijke velden op het formulier. Plak de waarde **[!UICONTROL-keuzen** in het veld **[!UICONTROL Standaardwaarde]** .

1. Near the upper-right corner of the page, tap **[!UICONTROL Save]**.
1. Pas het metagegevensprofiel voor YouTube Publishing toe op de mappen waarin u video&#39;s gaat uploaden. U moet zowel het metagegevensprofiel als het videoprofiel hebben ingesteld.

   Zie [Metadataprofielen](metadata-profiles.md) en [Videoprofielen](video-profiles.md).

### Video&#39;s publiceren naar uw YouTube-kanaal {#publishing-videos-to-your-youtube-channel}

Nu associeert u de markeringen die u eerder aan videoactiva toevoegde. Dit proces laat AEM weten welke middelen naar uw YouTube-kanaal moeten worden gepubliceerd.

Voor het publiceren van inhoud van YouTube gebruikt AEM de workflow **[!UICONTROL Publiceren naar YouTube]** , waarmee u de voortgang kunt controleren en eventuele foutgegevens kunt bekijken.
Zie [De voortgang van videocodering en YouTube-publicatie controleren](#monitoring-video-encoding-and-youtube-publishing-progress).

**Video&#39;s publiceren naar uw YouTube-kanaal**:

1. Navigeer in AEM naar een video-element dat u naar uw YouTube-kanaal wilt publiceren.
1. Selecteer het video-element.

   De oorspronkelijke bronvideo wordt altijd geüpload, ongeacht het geselecteerde video-element, zoals de oorspronkelijke bronvideo of een gecodeerde uitvoering ervan.

1. Tik op **[!UICONTROL Eigenschappen]** op de werkbalk.
1. Tik op het tabblad **[!UICONTROL Standaard]** onder de kop Metagegevens op **[!UICONTROL Bladeren]** rechts van het veld **[!UICONTROL Codes]** .
1. Navigeer op de pagina **[!UICONTROL Codes]** selecteren naar de gewenste codes en selecteer een of meer codes.
1. Tik in de rechterbovenhoek van de pagina op het pictogram **[!UICONTROL Bevestigen]** .
1. Tik in de rechterbovenhoek van de eigenschappenpagina van de video op **[!UICONTROL Opslaan]**.
1. Tik op de werkbalk op **[!UICONTROL Publiceren > Publiceren]**.

   U kunt desgewenst de gepubliceerde video op uw YouTube-kanaal verifiëren.

### (Optioneel) De gepubliceerde video op YouTube controleren {#optional-verifying-the-published-video-on-youtube}

U kunt de voortgang van uw publicatie op YouTube (of het ongedaan maken van de publicatie) volgen.

Zie [De voortgang van videocodering en YouTube-publicatie controleren](#monitoring-video-encoding-and-youtube-publishing-progress).

De het publiceren tijden kunnen zeer afhankelijk van talrijke factoren variëren die het formaat van uw hoofdvideo, dossiergrootte, en uploadverkeer omvatten. Het publicatieproces kan een paar minuten tot enkele uren duren. Houd er ook rekening mee dat opmaak met een hogere resolutie veel langzamer wordt gerenderd. Het duurt bijvoorbeeld aanzienlijk langer om 720p en 1080p weer te geven dan 480p.

Als u na acht uur nog steeds een statusbericht ziet met de melding **[!UICONTROL Geüpload (bewerking, een ogenblik geduld)]**, verwijdert u de video van onze site en uploadt u deze opnieuw.

### Linking YouTube URLs to your Web Application {#linking-youtube-urls-to-your-web-application}

U kunt een URL-tekenreeks van YouTube verkrijgen die wordt gegenereerd door Dynamic Media nadat u de video hebt gepubliceerd. Wanneer u de URL van YouTube kopieert, wordt deze op het Klembord gedownload, zodat u deze indien nodig kunt plakken naar pagina&#39;s in uw website of toepassing.

De URL van YouTube kan pas worden gekopieerd nadat u het video-element naar YouTube hebt gepubliceerd.

**U kunt als volgt YouTube-URL&#39;s koppelen aan uw webtoepassing**:

1. Navigeer naar het *gepubliceerde* video-element van YouTube waarvan u de URL wilt kopiëren en selecteer het.

   Remember that YouTube URLs are only available to copy *after* you have first *published* the video assets to YouTube.

1. Tik op **[!UICONTROL Eigenschappen]** op de werkbalk.
1. Tap the **[!UICONTROL Advanced]** tab.
1. Selecteer onder de kop **[!UICONTROL YouTube Publishing]** in de **[!UICONTROL YouTube URL]** -lijst de URL-tekst en kopieer deze naar uw webbrowser om een voorvertoning van het element weer te geven of om deze toe te voegen aan uw webinhoudspagina.

### Publiceren van video&#39;s ongedaan maken om deze van YouTube te verwijderen {#unpublishing-videos-to-remove-them-from-youtube}

Wanneer u de publicatie van een video-element in AEM ongedaan maakt, wordt de video verwijderd van YouTube.

>[!CAUTION]
>
>Als u een video rechtstreeks van YouTube verwijdert, is AEM zich hiervan niet bewust en gedraagt het zich alsof de video nog steeds op YouTube wordt gepubliceerd. Publiceer altijd een video-element van YouTube via AEM.

Om inhoud van YouTube te verwijderen, gebruikt AEM **[!UICONTROL Unpublish van het werkschema YouTube]** , dat u vooruitgang en om het even welke mislukkingsinformatie laat controleren en bekijken.
Zie [De voortgang van videocodering en YouTube-publicatie controleren](#monitoring-video-encoding-and-youtube-publishing-progress).

**U kunt als volgt de publicatie van video&#39;s ongedaan maken om deze van YouTube** te verwijderen:

1. In the upper-left corner of AEM, tap the AEM logo, then in the left rail, tap **[!UICONTROL Tools > Assets]**.
1. Navigeer naar de video-elementen waarvan u de publicatie ongedaan wilt maken via uw YouTube-kanaal.
1. Selecteer in de modus voor middelenselectie een of meer gepubliceerde video-elementen.
1. Tik op **[!UICONTROL Unpublish > Unpublish]** op de werkbalk.

## Monitoring video encoding and YouTube publishing progress {#monitoring-video-encoding-and-youtube-publishing-progress}

Wanneer u een nieuwe video uploadt naar een map waarop videocodering is toegepast of wanneer u de video publiceert naar YouTube, kunt u op verschillende manieren controleren hoe de videocodering/het publiceren via youtube vordert (of mislukt). De daadwerkelijke voortgang van het publiceren op YouTube is alleen beschikbaar via de logboeken, maar of het programma mislukt of slaagt, wordt op een andere manier vermeld die in de volgende procedure wordt beschreven. Bovendien kunt u e-mailmeldingen ontvangen wanneer een publicatieworkflow of videocodering op YouTube is voltooid of is afgebroken.

### Voortgang van toezicht {#monitoring-progress}

De voortgang controleren (inclusief mislukte codering/YouTube-publicatie):

1. Voortgang videocodering weergeven in map met elementen:

   * In de **[!UICONTROL Kaartweergave]** wordt de voortgang van de videocodering met een percentage weergegeven op het element. Als er een fout optreedt, wordt deze informatie ook weergegeven op het element.

      ![chlimage_1-429](assets/chlimage_1-429.png)

   * In **[!UICONTROL List View]**, video encoding progress displays in the **[!UICONTROL Processing Status]** column. Als er een fout is, wordt dit bericht in dezelfde kolom weergegeven.

      ![chlimage_1-430](assets/chlimage_1-430.png)

      Deze kolom wordt niet standaard weergegeven. Als u de kolom wilt inschakelen, selecteert u Instellingen **** weergeven in het vervolgkeuzemenu **[!UICONTROL Weergaven]** , voegt u de kolom **[!UICONTROL Verwerkingsstatus]** toe en tikt u op **[!UICONTROL Bijwerken]**.

      ![chlimage_1-431](assets/chlimage_1-431.png)

1. De voortgang van de elementen weergeven. Wanneer u op een element tikt, opent u het vervolgkeuzemenu en selecteert u **[!UICONTROL Tijdlijn]**. Selecteer **[!UICONTROL Workflows]** om deze te beperken tot workflowactiviteiten zoals coderen of YouTube-publicatie.

   ![chlimage_1-432](assets/chlimage_1-432.png)

   Workflowinformatie zoals codering wordt weergegeven in de tijdlijn. Voor YouTube-publicaties bevat de tijdlijn van de **[!UICONTROL workflow]** ook de naam van het YouTube-kanaal en de URL van de YouTube-video. Bovendien ziet u foutmeldingen in de tijdlijn van de **[!UICONTROL workflow]** .

   >[!NOTE]
   >
   >It may take a long time for failure/error messages to finally be recorded due to multiple workflow configurations on **[!UICONTROL retries]**, **[!UICONTROL retry delay]**, and **[!UICONTROL timeout]** from [http://localhost:4502/system/console/configMgr](http://localhost:4502/system/console/configMgr), for example:
   >
   >* Configuratie Apache Sling-taakwachtrij
   >* Adobe Granite Workflow External Process Job Handler
   >* Tijdelijke wachtrij voor Granite Workflow
   > 
   >U kunt de eigenschappen **[!UICONTROL retry]**, **[!UICONTROL retry delay]**, en **[!UICONTROL timeout]** in deze configuraties aanpassen.

1. Zie **Workflowinstanties** beschikbaar via **[!UICONTROL Extra > Workflow > Instanties]** voor actieve workflows.

   >[!NOTE]
   >
   >Mogelijk hebt u beheerdersrechten nodig om het menu **[!UICONTROL Gereedschappen]** te openen.

   ![chlimage_1-433](assets/chlimage_1-433.png)

   Selecteer het exemplaar en tik **[!UICONTROL Open Geschiedenis]**.

   ![chlimage_1-434](assets/chlimage_1-434.png)

   Vanuit het gebied **[!UICONTROL Workflowinstanties]** kunt u workflows ook opschorten, beëindigen of hernoemen. Zie [Workflows](/help/sites-administering/workflows-administering.md) beheren voor meer informatie.

1. Voor mislukte taken, zie de **Werkstroommislukkingen** beschikbaar bij **[!UICONTROL Hulpmiddelen > Werkschema > Gebreken]**. The **[!UICONTROL Workflow Failure]** lists all failed workflow activities.

   >[!NOTE]
   >
   >Mogelijk hebt u beheerdersrechten nodig om het menu **[!UICONTROL Gereedschappen]** te openen.

   ![chlimage_1-435](assets/chlimage_1-435.png)

   >[!NOTE]
   >
   >It may take a long time for the error message to finally be recorded due to multiple workflow configurations on **[!UICONTROL retries]**, **[!UICONTROL retry delay]**, and **[!UICONTROL timeout]** from [http://localhost:4502/system/console/configMgr](http://localhost:4502/system/console/configMgr), for example:
   >
   >* Configuratie Apache Sling-taakwachtrij
   >* Adobe Granite Workflow External Process Job Handler
   >* Tijdelijke wachtrij voor Granite Workflow
   >
   >U kunt de eigenschappen **[!UICONTROL retry]**, **[!UICONTROL retry delay]**, en **[!UICONTROL timeout]** in deze configuraties aanpassen.

1. Zie **[!UICONTROL Workflowarchief]** beschikbaar via **[!UICONTROL Extra > Workflow > Archiveren]** voor voltooide workflows. The **[!UICONTROL Workflow Archive]** lists all completed workflow activities.

   Mogelijk hebt u beheerdersrechten nodig om het menu **[!UICONTROL Gereedschappen]** te openen.

   ![chlimage_1-436](assets/chlimage_1-436.png)

1. U kunt e-mailmeldingen ontvangen over afgebroken of mislukte workflowtaken. Deze e-mailberichten kunnen door een beheerder worden geconfigureerd.
Zie E-mailmeldingen [](#configuring-e-mail-notifications)configureren.

#### E-mailmeldingen configureren {#configuring-e-mail-notifications}

Mogelijk hebt u beheerdersrechten nodig om het menu **[!UICONTROL Gereedschappen]** te openen.

Hoe u een melding configureert, hangt af van het feit of u meldingen voor coderingstaken of publicatietaken op YouTube wilt:

* Voor coderingstaken kunt u de configuratiepagina openen voor alle e-mailmeldingen in de AEM-workflow via **[!UICONTROL Opties > Bewerkingen > Webconsole]** en door te zoeken naar **[!UICONTROL Day CQ Workflow Email Notification Service]**. Zie E-mailmelding [configureren in AEM](/help/sites-administering/notification.md). U kunt de selectievakjes voor **[!UICONTROL Waarschuwen bij afbreken]** of **[!UICONTROL Waarschuwen bij voltooien]** selecteren of wissen.

* Ga als volgt te werk voor publicatietaken op YouTube:

1. Selecteer in AEM **[!UICONTROL Opties > Workflow > Modellen]**.
1. Selecteer de workflow **[!UICONTROL Publiceren naar YouTube]** en tik op **[!UICONTROL Bewerken]**.
1. Klik met de rechtermuisknop op de **[!UICONTROL workflowstap Uploaden]** naar YouTube en tik vervolgens op **[!UICONTROL Bewerken]**.
1. Tik op het tabblad **Argumenten **.
1. U kunt de volgende selectievakjes in- of uitschakelen:

   * **[!UICONTROL Start publiceren]**
   * **[!UICONTROL Publicatiefout]**
   * **[!UICONTROL Voltooiing]** publiceren, inclusief informatie over kanalen en URL&#39;s
   Als u een selectievakje wist, ontvangt u geen e-mailbericht van de publicatieworkflow van YouTube.

   >[!NOTE]
   >
   >Deze e-mailberichten zijn specifiek voor YouTube en vormen een aanvulling op de algemene e-mailmeldingen over de workflow. Het gevolg is dat u twee sets e-mailmeldingen ontvangt: het algemene bericht dat beschikbaar is in de **Day CQ Workflow Email Notification Service** en een specifiek bericht voor YouTube, afhankelijk van uw configuratie-instellingen.

## Video-rapporten weergeven {#viewing-video-reports}

De videorapporten zijn beschikbaar wanneer u Dynamische Media - Hybride wijze in werking stelt; de rapporten zijn niet beschikbaar wanneer u Dynamische Media - wijze Scene7 in werking stelt.

De videoRapporten tonen verscheidene gezamenlijke metriek over een gespecificeerde periode om u te helpen controleren dat *published *individual en gezamenlijke video&#39;s zoals verwacht presteren. De volgende statistische gegevens worden geaggregeerd voor alle gepubliceerde video&#39;s op uw gehele website:

* Video start
* Voltooiingssnelheid
* Gemiddelde tijd op video
* Totale tijd op video
* Video&#39;s per bezoek

Er wordt ook een tabel met alle *gepubliceerde* video&#39;s weergegeven, zodat u de bovenste weergegeven video&#39;s op uw website kunt bijhouden op basis van het totale aantal video&#39;s dat wordt gestart.

Wanneer u een videonaam in de lijst tikt, ziet u het rapport voor het behoud van het publiek van de video (drop-off) in de vorm van een lijndiagram. Het diagram toont het aantal weergaven voor een bepaald tijdstip tijdens het afspelen van video. Wanneer u de video afspeelt, wordt de verticale balk gesynchroniseerd met de tijdindicator in de speler. De vallen in de gegevens van het lijndiagram wijzen op waar uw publiek van oninteresse wegvalt.

Als de video buiten Adobe Experience Manager Dynamic Media is gecodeerd, zijn het diagram voor het vasthouden van het publiek (drop-off) en de gegevens voor het afspeelpercentage in de tabel niet beschikbaar.

Zie ook Dynamische Media Cloud Services [configureren](/help/assets/config-dynamic.md).

>[!NOTE]
>
>Het bijhouden en rapporteren van gegevens is uitsluitend gebaseerd op het gebruik van de eigen videospeler van Dynamic Media en de bijbehorende voorinstelling van de videospeler. U kunt dus geen video&#39;s bijhouden en rapporteren die door andere videospelers worden afgespeeld.

Door gebrek, de eerste keer u VideoRapporten ingaat, toont het rapport videogegevens die bij de eerste van de huidige maand beginnen en met de datum van de huidige maand beëindigen. U kunt het standaarddatumbereik echter overschrijven door uw eigen datumbereik op te geven. De volgende keer dat u Video-rapporten invoert, wordt het opgegeven datumbereik gebruikt.

Videorapporten werken alleen correct als er automatisch een rapportsuite-id wordt gemaakt wanneer Dynamic Media Cloud Services is geconfigureerd. Tegelijkertijd wordt de rapportsuite-id doorgegeven aan de publicatieserver, zodat deze beschikbaar is voor de functie URL kopiëren wanneer u een voorvertoning van elementen weergeeft. Hiervoor moet de publicatieserver echter al zijn ingesteld. Als de publicatieserver niet is ingesteld, kunt u nog steeds publiceren om het videoverslag te bekijken. U moet echter wel terugkeren naar de Dynamic Media Cloud Configuration en op **OK** tikken.

**Videorapporten** weergeven:

1. In the upper-left corner of AEM, tap the AEM logo, then in the left rail, tap **[!UICONTROL Tools > Assets > Video Reports]**.
1. Voer een van de volgende handelingen uit op de pagina Videorapporten:

   * Tik in de rechterbovenhoek op het pictogram **[!UICONTROL Videorapport]** vernieuwen.

      U hoeft alleen Vernieuwen te gebruiken als de einddatum van het rapport de huidige dag is. Dit zorgt ervoor dat u video het volgen ziet die sinds de laatste tijd is voorgekomen u het rapport in werking stelde.

   * Tik in de rechterbovenhoek op het pictogram **[!UICONTROL Datumkiezer]** .

      Geef het begin- en einddatumbereik op waarvoor u videogegevens wilt en tik op Rapport **** uitvoeren.
   In het groepsvak **[!UICONTROL Metriek]** bovenaan ziet u verschillende statistische metingen voor alle *gepubliceerde* video&#39;s op uw site.

1. Tik in de tabel met de bovenste gepubliceerde video&#39;s op een videonaam om de video af te spelen en zie ook het rapport voor het vasthouden van het publiek van de video (drop-off).

### Het bekijken van videorapporten die op een videokijker worden gebaseerd die u gebruikend Scene7 HMTL5 Kijker SDK creeerde {#viewing-video-reports-based-on-a-video-viewer-that-you-created-using-the-scene-hmtl-viewer-sdk}

Als u een uit-van-doos videoviewer gebruikt die door Dynamische Media wordt verstrekt, of als u een vooraf ingestelde douaneviewer creeerde die van een uit-van-doos videokijker wordt gebaseerd, dan worden geen extra stappen vereist om videorapporten te bekijken. Als u echter uw eigen videoviewer hebt gemaakt die is gebaseerd op de SDK van de Scene7 HTML5 Viewer, voert u de volgende stappen uit om ervoor te zorgen dat de videoviewer traceergebeurtenissen verzendt naar Dynamic Media Video Reports.

Gebruik de Verwijzing van Kijkers Scene7 en Scene7 HTML5 Viewers SDK om uw eigen videokijkers tot stand te brengen.

Zie de Gids [van de Verwijzing van](https://marketing.adobe.com/resources/help/en_US/s7/viewers_ref/index.html)Kijkers Scene7.

Download Scene7 HTML Viewer SDK van de Verbinding van de Ontwikkelaar van Adobe.

Zie [Adobe Developer Connection](https://help.adobe.com/en_US/scene7/using/WSef8d5860223939e2-43dedf7012b792fc1d5-8000.html).

Om VideoRapporten te bekijken die op een videokijker worden gebaseerd die u gebruikend Scene7 HTML5 Viewer SDK creeerde:

1. Navigeer naar een gepubliceerd video-element.
1. Near the upper-left corner of the asset&#39;s page, from the drop-down list, select **[!UICONTROL Viewers]**.
1. Selecteer een voorinstelling voor een videoviewer en kopieer de insluitcode.
1. Zoek in de insluitcode de regel met het volgende:

   `videoViewer.setParam("config2", "<value>");`

   De `config2` parameter schakelt tracering in HTML5 Viewers in. Het is ook een bedrijfsspecifieke voorinstelling die de configuratiegegevens bevat voor Video Reporting en voor klantspecifieke configuraties van Adobe Analytics.

   The correct value for the config2 parameter is found in both the **[!UICONTROL Embed Code]** and in the copy **[!UICONTROL URL]** function. In de URL van de opdracht voor het kopiëren van de **[!UICONTROL URL]**, zoekt u naar de parameter `&config2=<value>`. De waarde is bijna altijd `companypreset`, maar in sommige gevallen ook `companypreset-1`, `companypreset-2`, enz.

1. Voeg in uw aangepaste videoviewercode AppMeasurementBridge .jsp als volgt toe aan de viewerpagina:

   * Bepaal eerst of u de `&preset` parameter nodig hebt.

      Als de `config2` parameter `companypreset`is, hebt u *niet* nodig `&preset=parameter`.

      Als er iets anders `config2` is, stelt u de parameter preset op dezelfde manier in als de `config2` parameter. Voeg bijvoorbeeld, als `config2=companypreset-2`, `&param2=companypreset-2` aan AppMeturmentBridge.jsp URL toe.

   * Voeg vervolgens het script AppMeasurementBridge.jsp toe:

      `<script language="javascript" type="text/javascript" src="https://s7d1.scene7.com/s7viewers/AppMeasurementBridge.jsp?company=robindallas&preset=companypreset-2"></script>`

1. Maak als volgt de component TrackingManager:

   * Na het roepen `s7sdk.Utils.init();` creeer een instantie TrackingManager om gebeurtenissen te volgen door het volgende toe te voegen:

      `var trackingManager = new s7sdk.TrackingManager();`

   * Verbind componenten met TrackingManager door het volgende te doen:

      Verbind in de `s7sdk.Event.SDK_READY` gebeurtenismanager, de component u aan TrackingManager wilt volgen.

      Als de component bijvoorbeeld `videoPlayer`is, voegt u

      `trackingManager.attach(videoPlayer);`

      om de component aan trackingManager vast te maken. Als u meerdere viewers op een pagina wilt bijhouden, gebruikt u meerdere beheercomponenten voor tekstspatiëring.

   * Maak het object AppMeasurementBridge door het volgende toe te voegen:

      ```
      var appMeasurementBridge = new AppMeasurementBridge(); appMeasurementBridge.setVideoPlayer(videoPlayer);
      ```

   * Voeg de functie voor bijhouden toe door het volgende toe te voegen:

      ```
      trackingManager.setCallback(appMeasurementBridge.track, 
       appMeasurementBridge);
      ```
   Het object appMeturementBridge heeft een ingebouwde trackfunctie. U kunt echter uw eigen systeem beschikbaar stellen voor de ondersteuning van meerdere trackingsystemen of andere functies.

   Voor meer informatie, zie het *Gebruiken van de Component* TrackingManager in *Scene7 HTML5 Viewer SDK Handboek* beschikbaar voor download van de Verbinding [van de Ontwikkelaar van](https://help.adobe.com/en_US/scene7/using/WSef8d5860223939e2-43dedf7012b792fc1d5-8000.html)Adobe.

## Bijschriften toevoegen aan video {#adding-captions-to-video}

U kunt het bereik van uw video&#39;s uitbreiden naar wereldwijde markten door ondertiteling toe te voegen aan enkele video&#39;s of aan Adaptive Video Sets. Door ondertiteling toe te voegen vermijdt u de noodzaak om de audio te dupliceren, of de behoefte om inheemse sprekers te gebruiken om de audio voor elke verschillende taal opnieuw op te nemen. De video wordt afgespeeld in de taal waarin deze is opgenomen. Er verschijnen ondertitels in vreemde talen, zodat mensen in verschillende talen het audiogedeelte nog steeds kunnen begrijpen.

Ondertiteling maakt ook een betere toegankelijkheid mogelijk door ondertiteling te gebruiken voor doven of slechthorenden.

>[!NOTE]
>
>De videospeler die u gebruikt moet de vertoning van titels steunen.

Dynamische media kan bijschriftbestanden omzetten in de indeling JSON (JavaScript Object Notation). Met deze conversie kunt u de JSON-tekst insluiten in een webpagina als een verborgen, maar volledige transcriptie van de video. Zoekprogramma&#39;s kunnen de inhoud vervolgens verkennen en indexeren, zodat de video&#39;s gemakkelijker te vinden zijn en klanten meer informatie krijgen over de video-inhoud.

Zie [Het dienen van statische (niet-beeld) inhoud](https://marketing.adobe.com/resources/help/en_US/s7/is_ir_api/is_api/c_serving_static_nonimage_contents.html) in het Beeld *Scene7 die API Hulp* voor meer informatie over het gebruiken van de functie JSON in een URL dienen.

**Bijschriften of ondertitels toevoegen aan video**:

1. U kunt een toepassing of service van derden gebruiken om een ondertitelingsbestand of ondertitelingsbestand voor video te maken.

   Zorg ervoor dat het bestand dat u maakt, voldoet aan de WebVTT-standaard (Web Video Text Tracks). De bestandsnaamextensie voor ondertiteling is .vtt. U kunt meer informatie over de WebVTT ondertitelingsnorm leren.

   Zie [WebVTT: De indeling](https://dev.w3.org/html5/webvtt/)Webvideoteksttracks.

   Er zijn zowel gratis als premiumtools en -services die u kunt gebruiken voor het schrijven van bijschriften/ondertitelingsbestanden buiten Dynamische media. Als u bijvoorbeeld een eenvoudig videobijschriftbestand zonder opmaak wilt maken, kunt u de volgende gratis gereedschappen voor het maken en bewerken van bijschriften gebruiken:

   [WebVTT Caption Maker](https://testdrive-archive.azurewebsites.net/Graphics/CaptionMaker/Default.html)

   U bereikt de beste resultaten met het programma in Internet Explorer 9 of hoger, Google Chrome of Safari.

   Plak in het veld URL van videobestand **** invoeren in het gereedschap de gekopieerde URL van het videobestand en tik vervolgens op **[!UICONTROL Laden]**. See [Obtaining a URL for an Asset](linking-urls-to-yourwebapplication.md#obtaining-a-url-for-an-asset) to get the URL to the video file itself which you can then paste into the **[!UICONTROL Enter URL of video file field]**. Internet Explorer, Chrome of Safari kunnen de video vervolgens op een native manier afspelen.

   Volg nu de aanwijzingen op het scherm van de site om het WebVTT-bestand te ontwerpen en op te slaan. Wanneer u klaar bent, kopieert u de inhoud van het bijschriftbestand en plakt u deze in een teksteditor zonder opmaak en slaat u het bestand op met de bestandsnaamextensie .vtt.

   >[!NOTE]
   >
   >Houd er rekening mee dat de WebVTT-standaard vereist dat u afzonderlijke .vtt-bestanden maakt en dat u elke taal die u wilt ondersteunen, aanroept voor algemene ondersteuning van videoondertitels in meerdere talen.

   Over het algemeen wilt u het VTT-bestand van het bijschrift dezelfde naam geven als het videobestand en dit bestand toevoegen met de landinstelling van de taal, zoals -EN, of -FR of -DE, enzovoort. Hierdoor kunt u het genereren van video-URL&#39;s automatiseren met behulp van uw bestaande systeem voor webcontentbeheer.

1. Upload in AEM uw WebVTT-bijschriftbestand naar DAM.
1. Navigeer naar het *gepubliceerde* video-element dat u wilt koppelen aan het bijschriftbestand dat u hebt geüpload.

   Houd er rekening mee dat URL&#39;s alleen beschikbaar zijn om te kopiëren *nadat* u de assets eerst hebt *gepubliceerd*.

   Zie Elementen [publiceren.](publishing-dynamicmedia-assets.md)

1. Voer een van de volgende handelingen uit:

   * Tik op **[!UICONTROL URL]** voor een pop-upvideo. Selecteer in het dialoogvenster URL de URL en kopieer deze naar het Klembord en passeer de URL naar een eenvoudige teksteditor. Voeg de gekopieerde URL van de video toe met de volgende syntaxis:

      `&caption=<server_path>/is/content/<path_to_caption.vtt_file,1>`

      Noteer de tekst aan het `,1` einde van het bijschriftpad. Direct na de bestandsnaamextensie .vtt in het pad kunt u de knop voor een gesloten bijschrift op de videospelerbalk in- of uitschakelen (uitschakelen) door deze in te stellen op respectievelijk `,1` of `,0`.

   * Tik op Code **** insluiten voor een ingesloten videoviewerervaring. Selecteer in het dialoogvenster Code insluiten de insluitcode en kopieer deze naar het klembord en plak de code in een eenvoudige teksteditor. Voeg de gekopieerde insluitcode toe met de volgende syntaxis:

      `videoViewer.setParam("caption","<path_to_caption.vtt_file,1>");`

      Noteer de tekst aan het `,1` einde van het bijschriftpad. Direct na de bestandsnaamextensie .vtt in het pad kunt u de knop voor een gesloten bijschrift op de videospelerbalk in- of uitschakelen (uitschakelen) door deze in te stellen op respectievelijk `,1` of `,0`.

## Hoofdstukmarkeringen aan video toevoegen {#adding-chapter-markers-to-video}

U kunt uw lange formuliervideo&#39;s beter weergeven en navigeren door hoofdstukmarkeringen toe te voegen aan enkele video&#39;s of aan Adaptieve videosets. Wanneer een gebruiker de video afspeelt, kunnen ze op de hoofdstukmarkeringen op de videotijdlijn tikken (ook wel de videoscrubber genoemd) om gemakkelijk naar het betreffende punt te navigeren, of direct naar nieuwe inhoud, demonstraties, zelfstudies, enzovoort te gaan.

>[!NOTE]
>
>De videospeler die wordt gebruikt moet het gebruik van hoofdstukmarkeringen steunen. Dynamische media-videospelers ondersteunen wel hoofdstukmarkeringen, maar het gebruik van videospelers van derden is mogelijk niet mogelijk.

Desgewenst kunt u uw eigen aangepaste videoviewer maken en markeren met hoofdstukken in plaats van een voorinstelling voor de videoviewer te gebruiken. Voor instructies voor het maken van uw eigen HTML5-viewer met hoofdstuknavigatie verwijst u in de Adobe Scene7 Viewer SDK voor HTML5-handleiding naar de kop &quot;Gedrag aanpassen met behulp van wijzigingstoetsen&quot; onder de klassen `s7sdk.video.VideoPlayer` en `s7sdk.video.VideoScrubber`. De SDK van de Adobe Scene7 Viewer is beschikbaar als download via [Adobe Developer Connection](https://help.adobe.com/en_US/scene7/using/WSef8d5860223939e2-43dedf7012b792fc1d5-8000.html).

U maakt een hoofdstuklijst voor uw video op ongeveer dezelfde manier als u bijschriften maakt. U maakt dus een WebVTT-bestand. Merk op, echter, dat dit dossier van om het even welk WebVTT titeldossier moet gescheiden zijn dat u ook kunt gebruiken; u kunt geen titels en hoofdstukken in één dossier combineren WebVTT.

U kunt het volgende voorbeeld als voorbeeld van het formaat gebruiken u gebruikt om een dossier WebVTT met hoofdstuknavigatie tot stand te brengen:

### WebVTT-bestand met navigatie in videohoofdstukken {#webvtt-file-with-video-chapter-navigation}

```xml
WEBVTT 
Chapter 1 
00:00.000 --> 01:04.364 
The bicycle store behind it all. 
Chapter 2 
01:04.364 --> 02:00.944 
Creative Cloud. 
Chapter 3 
02:00.944 --> 03:02.937 
Ease of management for a working solution. 
Chapter 4 
03:02.937 --> 03:35.000 
Cost-efficient access to rapidly evolving technology.
```

In het bovenstaande voorbeeld `Chapter 1` is dit de actidentificator en is deze optioneel. De actieduur van `00:00:000 --> 01:04:364` geeft de begin- en eindtijd van het hoofdstuk op in `00:00:000` indeling. Deze laatste drie cijfers zijn milliseconden en kunnen desgewenst worden gelaten. `000` De hoofdstuktitel van `The bicycle store behind it all` is de daadwerkelijke beschrijving van de inhoud van het hoofdstuk. De actidentificator, de begintijd en de hoofdstuktitel worden allemaal weergegeven in een pop-up in de videospeler wanneer een gebruiker de muisaanwijzer boven een visueel actiepunt in de tijdlijn van de video houdt.

Omdat u een HTML5-videoviewer gebruikt, moet u ervoor zorgen dat het hoofdstukbestand dat u maakt, voldoet aan de WebVTT-standaard (Web Video Text Tracks). De bestandsextensie van het hoofdstuk is .vtt. U kunt meer informatie over de WebVTT ondertitelingsnorm leren.

Zie [WebVTT: De indeling Webvideoteksttracks](https://dev.w3.org/html5/webvtt/)

**Hoofdstukmarkeringen aan video toevoegen:**

1. Maak met een eenvoudige teksteditor buiten AEM een hoofdbestand voor de video.

   Voor wereldwijde ondersteuning van videohoofdstukken in andere talen dan het Engels, dient u er rekening mee te houden dat de WebVTT-standaard vereist dat u afzonderlijke .vtt-bestanden maakt en dat u elke taal die u wilt ondersteunen, aanroept.

1. Sla het `.vtt` bestand op in UTF8-codering om problemen met tekenuitvoering in de hoofdstuktiteltekst te voorkomen.

   Over het algemeen wilt u het hoofdstuk VTT-bestand dezelfde naam geven als het videobestand en het toevoegen met hoofdstukken. Hierdoor kunt u het genereren van video-URL&#39;s automatiseren met behulp van uw bestaande systeem voor webcontentbeheer.
1. Upload uw WebVTT-hoofdstukbestand in AEM.

   Zie Elementen [uploaden](managing-assets-touch-ui.md#uploading-assets).

1. Voer een van de volgende handelingen uit:

   <table> 
     <tbody> 
      <tr> 
       <td>Voor een ervaring met een pop-upvideoviewer</td> 
       <td> 
       <ol> 
       <li>Navigeer naar de <i>gepubliceerde </i>video-elementen die u wilt koppelen aan het hoofdstukbestand dat u hebt geüpload. Houd er rekening mee dat URL's alleen beschikbaar zijn om te kopiëren <i>nadat</i> u de assets eerst hebt <i>gepubliceerd</i>. Zie Elementen <a href="/help/assets/publishing-dynamicmedia-assets.md">publiceren.</a></li> 
       <li>Tik vervolgens in het keuzemenu op <strong>Viewers</strong>.</li> 
       <li>Tik in de linkertrack op de naam van de voorinstelling voor de videoviewer. Er wordt een voorvertoning van de video geopend op een aparte pagina.</li> 
       <li>Tik in de linkerrail onderaan op <strong>URL</strong>.</li> 
       <li>Selecteer in het dialoogvenster URL de URL en kopieer deze naar het Klembord. Plak vervolgens de URL in een eenvoudige teksteditor.</li> 
       <li>Voeg de gekopieerde URL van de video toe aan de volgende syntaxis om deze te koppelen aan de gekopieerde URL naar het hoofdstukbestand:<br /> <br /> <code>&amp;navigation=&lt;<i>full_copied_URL_path_to_chapter_file</i>.vtt&gt;</code><br /> </li> 
      </ol> </td> 
      </tr> 
      <tr> 
       <td>Voor een ingesloten videoviewerervaring<br /> </td> 
       <td> 
       <ol> 
       <li>Navigeer naar de <i>gepubliceerde </i>video-elementen die u wilt koppelen aan het hoofdstukbestand dat u hebt geüpload. Houd er rekening mee dat URL's alleen beschikbaar zijn om te kopiëren <i>nadat</i> u de assets eerst hebt <i>gepubliceerd</i>. Zie Elementen <a href="/help/assets/publishing-dynamicmedia-assets.md">publiceren.</a></li> 
       <li>Tik vervolgens in het keuzemenu op <strong>Viewers</strong>.</li> 
       <li>Tik in de linkertrack op de naam van de voorinstelling voor de videoviewer. Er wordt een voorvertoning van de video geopend op een aparte pagina.</li> 
       <li>Tik in de linkerspoorstaaf onderaan op <strong>Insluiten</strong>.</li> 
       <li>Selecteer in het dialoogvenster Code insluiten de gehele code en kopieer deze naar het klembord. Plak de code vervolgens in een eenvoudige teksteditor.</li> 
       <li>Voeg de insluitcode van de video toe aan de volgende syntaxis om deze te koppelen aan de gekopieerde URL naar het hoofdstukbestand:<br /> <br /> <code>videoViewer.setParam("navigation","&lt;<i>full_copied_URL_path_to_chapter_file</i>.vtt&gt;"</code></li> 
      </ol> </td> 
      </tr> 
     </tbody> 
    </table>

## Informatie over videominiaturen {#about-video-thumbnails}

U kunt kiezen uit een van de tien miniatuurafbeeldingen die automatisch door Dynamic Media worden gegenereerd om aan uw video toe te voegen. De videospeler geeft de geselecteerde miniatuur weer wanneer een video-element wordt gebruikt met de component Dynamic Media in de ontwerpomgeving van AEM-sites, AEM Mobile of AEM-schermen. De miniatuur fungeert als een statisch beeld dat de inhoud van de gehele video het beste vertegenwoordigt en dat gebruikers verder aanmoedigt op de knop Afspelen te tikken.

Op basis van de totale tijd van de video worden in Dynamic Media tien (standaard) miniatuurafbeeldingen vastgelegd met 1%, 11%, 21%, 31%, 41%, 51%, 61%, 71%, 81% en 91% in de video. De tien miniaturen blijven bestaan. Dit betekent dat als u een andere miniatuur kiest, u de reeks niet opnieuw hoeft te genereren. U bekijkt een voorvertoning van de tien miniatuurafbeeldingen en selecteert vervolgens de miniatuurafbeelding die u voor de video wilt gebruiken. Als u wilt veranderen in gebrek, kunt u CRXDE Lite gebruiken om het tijdinterval te vormen dat duimnagelbeelden worden geproduceerd. Als u bijvoorbeeld alleen een reeks van vier miniatuurafbeeldingen met gelijkmatige tussenruimte uit uw video wilt genereren, kunt u de intervaltijd instellen op 24%, 49%, 74% en 99%.

In het ideale geval kunt u een videominiatuur toevoegen nadat u de video hebt geüpload, maar voordat u de video op uw website publiceert.

Desgewenst kunt u een aangepaste miniatuur uploaden om uw video te vertegenwoordigen in plaats van een miniatuur te gebruiken die is gegenereerd door Dynamic Media. U kunt bijvoorbeeld een aangepaste miniatuurafbeelding maken met de titel van uw video, een opvallende openingsafbeelding of een zeer specifieke afbeelding die uit uw video is vastgelegd. De aangepaste videominiatuurafbeelding die u uploadt, moet een maximale resolutie van 1280 x 720 pixels (minimale breedte van 640 pixels) en niet groter zijn dan 2 MB.

>[!NOTE]
>
>Aangepaste videominiaturen zijn alleen beschikbaar wanneer u de modus Dynamische media - hybride uitvoert.

### Een videominiatuur toevoegen {#adding-a-video-thumbnail}

1. Navigeer naar een geüpload video-element waaraan u een videominiatuur wilt toevoegen.
1. Tik in de modus voor middelenselectie in de **[!UICONTROL lijstweergave]** of de **[!UICONTROL kaartweergave]** op het video-element.
1. Tik op de werkbalk op het pictogram **[!UICONTROL Weergave-eigenschappen]** (een cirkel met een &quot;i&quot; erin).
1. Tik op de pagina **[!UICONTROL Eigenschappen]** van de video op Miniatuur **[!UICONTROL wijzigen]**.
1. Tik op de pagina Miniatuur **[!UICONTROL wijzigen op de werkbalk op]** Frame **** selecteren.

   Dynamische media genereert een reeks miniatuurafbeeldingen van uw video op basis van het standaardtijdinterval of tijdinterval dat u hebt aangepast.

1. Geef een voorvertoning van de gegenereerde miniatuurafbeeldingen weer en selecteer de miniatuurafbeelding die u aan de video wilt toevoegen.
1. Tik op Wijzigen **[!UICONTROL opslaan]**.

   De miniatuurafbeelding van de video wordt bijgewerkt en gebruikt nu de miniatuur die u hebt geselecteerd. Als u later besluit de miniatuurafbeelding te wijzigen, gaat u terug naar de pagina Miniatuur **** wijzigen en selecteert u een nieuwe pagina.

   Als u nieuwe standaardtijdintervallen configureerde, of u uploadde een nieuwe video om de bestaande video te vervangen, zult u Dynamische Media moeten hebben de duimnagels opnieuw produceren.

   Zie Het standaardtijdinterval [configureren dat videominiaturen worden gegenereerd](#configuring-the-default-time-interval-that-video-thumbnails-are-generated).

#### Het standaardtijdinterval configureren dat videominiaturen worden gegenereerd {#configuring-the-default-time-interval-that-video-thumbnails-are-generated}

Wanneer u het nieuwe standaardtijdinterval configureert en opslaat, is uw wijziging automatisch alleen van toepassing op video&#39;s die u in de toekomst uploadt. De nieuwe standaardinstelling wordt niet automatisch toegepast op video&#39;s die u eerder hebt geüpload. Voor bestaande video&#39;s moet u de miniaturen opnieuw genereren.

Zie [Een videominiatuur](#adding-a-video-thumbnail)toevoegen.

Om het standaardtijdinterval te vormen dat videominiaturen worden geproduceerd,

1. Tik in AEM op **[!UICONTROL Gereedschappen > Algemeen > CRXDE Lite]**.

1. Navigeer op de pagina CRXDE Lite, in het folderpaneel op de linkerzijde, het `o etc/dam/imageserver/configuration/jcr:content/settings.`

   Als het mappendeelvenster niet zichtbaar is, moet u mogelijk op het pictogram >> links van het tabblad Start tikken.

1. Dubbeltik op het tabblad **[!UICONTROL Eigenschappen]** in het deelvenster rechtsonder op `thumbnailtime`.
1. Gebruik de tekstvelden in het dialoogvenster Miniatuur bewerken om intervalwaarden als percentages in te voeren.

   * Tik op het plusteken (+) om een of meer velden voor intervalwaarden toe te voegen. Mogelijk moet u naar de onderkant van het dialoogvenster bladeren om het pictogram te zien.
   * Tik op het minteken (-) rechts van een veld voor de intervalwaarde om dit uit de lijst te verwijderen.
   * Tik op het pictogram pijl-omhoog en pijl-omlaag om de intervalwaarden opnieuw te ordenen.

1. Tik op **[!UICONTROL OK]** om terug te keren naar het tabblad **[!UICONTROL Eigenschappen]** .
1. Tik in de linkerbovenhoek van de CRXDE Lite-pagina op Alles **** opslaan en tik vervolgens op het pictogram **[!UICONTROL Home]** Terug in de linkerbovenhoek om terug te keren naar AEM.

   Zie [Een videominiatuur toevoegen.](#adding-a-video-thumbnail)

### Een aangepaste videominiatuur toevoegen {#adding-a-custom-video-thumbnail}

>[!NOTE]
>
>Deze functie is alleen beschikbaar als u Dynamische media - hybride modus uitvoert.

1. Navigeer naar een geüpload video-element waaraan u een videominiatuur wilt toevoegen.
1. Tik in de modus voor middelenselectie in de **[!UICONTROL lijstweergave]** of de **[!UICONTROL kaartweergave]** op het video-element.
1. Tik op de werkbalk op het pictogram **[!UICONTROL Weergave-eigenschappen]** (een cirkel met een &quot;i&quot; erin).
1. Tik op de pagina **[!UICONTROL Eigenschappen]** van de video op Miniatuur **[!UICONTROL wijzigen]**.
1. Tik op de pagina **[!UICONTROL Miniatuur]** wijzigen op de werkbalk op Nieuwe miniatuur **** uploaden.
1. Navigeer naar een miniatuurafbeelding die u wilt gebruiken, selecteer deze en tik op **[!UICONTROL Openen]** om de afbeelding naar AEM te uploaden
1. Tik op Wijzigingen **** opslaan nadat de afbeelding is geüpload op de pagina Miniatuur **[!UICONTROL wijzigen]**.

   De aangepaste miniatuur wordt toegevoegd aan uw video.

