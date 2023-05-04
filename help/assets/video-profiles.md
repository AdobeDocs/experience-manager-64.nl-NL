---
title: Dynamic Media-videoprofielen
description: Dynamic Media wordt geleverd met een vooraf gedefinieerd adaptief videocoderingsprofiel. De instellingen in dit out-of-the-box-profiel zijn geoptimaliseerd om uw klanten de beste videovertoning mogelijk te maken.
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: administering
content-type: reference
exl-id: 3602e1b9-624d-408f-a7f6-1598b62dbd22
feature: Video Profiles,Video
role: Admin,User
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '2885'
ht-degree: 15%

---

# Dynamic Media-videoprofielen {#video-profiles}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Dynamic Media wordt al geleverd met een vooraf gedefinieerd adaptief videocoderingsprofiel. De instellingen in dit out-of-the-box profiel zijn geoptimaliseerd om uw klanten de beste kijkervaring mogelijk te maken. Wanneer u master video&#39;s codeert met het profiel Adaptieve videocodering, past de videospeler tijdens het afspelen automatisch de kwaliteit van de videostream aan op basis van de snelheid van de internetverbinding van uw klanten. Dit wordt adaptieve streaming genoemd.

Hier volgen nog andere factoren die de kwaliteit van uw video&#39;s bepalen:

* **Resolutie van de geüploade master video**

   Als de MP4-video met een lagere resolutie, zoals 240p of 360p, is opgenomen, kan deze niet in HD worden gestreamd.

* **Grootte videospeler**

   Standaard worden de **[!UICONTROL Width]** in het profiel Adaptieve videocodering is ingesteld op **[!UICONTROL Auto]**. Ook tijdens het afspelen wordt de beste kwaliteit gebruikt op basis van de grootte van de speler.

Zie ook [Aanbevolen procedures voor videocodering](video.md#best-practices-for-encoding-videos).

>[!NOTE]
>
>Als u de metadata van een video en de bijbehorende miniaturen van videoafbeeldingen wilt genereren, moet de video zelf het coderingsproces doorlopen in Dynamische media. In AEM codeert de workflow **[!UICONTROL Dynamic Media Encode Video]** video als u dynamische media hebt ingeschakeld en videocloudservices hebt ingesteld. In deze workflow worden de historie en informatie over fouten van het workflowproces vastgelegd.
>
>Zie [De voortgang van videocodering en YouTube-publicatie controleren](video.md#monitoring-video-encoding-and-youtube-publishing-progress). Als u Dynamic Media hebt ingeschakeld en videocloudservices hebt ingesteld, **[!UICONTROL Dynamic Media Encode Video]** de workflow wordt automatisch van kracht wanneer u een video uploadt. (Als u geen dynamische media gebruikt, wordt de workflow **[!UICONTROL DAM Update Asset]** van kracht.)
>
>Metagegevens zijn handig wanneer u naar elementen zoekt. De miniaturen zijn statische videobeelden die tijdens het coderen worden gegenereerd. Deze worden door het AEM-systeem vereist en in de gebruikersinterface gebruikt om u te helpen video&#39;s visueel te identificeren in de **[!UICONTROL Cards View]**, **[!UICONTROL Search Results]** en de **[!UICONTROL Asset List]** weergeven. U kunt de gegenereerde miniaturen zien wanneer u op de knop **[!UICONTROL Renditions]** pictogram (palet van een schilder) van een gecodeerde video.

Wanneer u klaar bent met het maken van het videoprofiel, past u het toe op een map of meerdere mappen. Zie [Een videoprofiel toepassen op mappen.](#applying-a-video-profile-to-folders)

Zie voor meer informatie over het definiëren van geavanceerde verwerkingsparameters voor andere elementtypen [Elementverwerking configureren](config-dms7.md#configuring-asset-processing).

## Voorinstellingen voor adaptieve videocodering {#adaptive-video-encoding-presets}

In de volgende tabel vindt u de beste praktijken voor het coderen van profielen voor adaptieve videostreaming naar mobiele apparaten en tabletapparaten en bureaubladcomputers. U kunt deze voorinstellingen gebruiken voor elke video met de hoogte-breedteverhouding.

<table> 
 <tbody> 
  <tr> 
   <td><strong>Video-indelingscodec</strong></td> 
   <td><strong>Videogrootte - Breedte (px)</strong></td> 
   <td><strong>Videogrootte - Hoogte (px)</strong></td> 
   <td><strong>Hoogte-breedteverhouding behouden?</strong></td> 
   <td><strong>Videobitsnelheid (Kbps)</strong></td> 
   <td><strong>Videoframesnelheid (FPS)</strong></td> 
   <td><strong>Audiocodec</strong></td> 
   <td><strong>Audiobitsnelheid (Kbps)</strong></td> 
  </tr> 
  <tr> 
   <td><p>MP4 H.264 (mp4)</p> </td> 
   <td>auto</td> 
   <td>360</td> 
   <td>Ja</td> 
   <td>730</td> 
   <td>30</td> 
   <td>Dolby HE-AAC</td> 
   <td>128</td> 
  </tr> 
  <tr> 
   <td><p>MP4 H.264 (mp4)</p> </td> 
   <td>auto</td> 
   <td>540</td> 
   <td>Ja</td> 
   <td>2000<br /> </td> 
   <td>30</td> 
   <td>Dolby HE-AAC</td> 
   <td>128</td> 
  </tr> 
  <tr> 
   <td><p>MP4 H.264 (mp4)</p> </td> 
   <td>auto</td> 
   <td>720<br /> </td> 
   <td>Ja</td> 
   <td>3000<br /> </td> 
   <td>30</td> 
   <td>Dolby HE-AAC</td> 
   <td>128</td> 
  </tr> 
 </tbody> 
</table>

## Een Dynamic Media-videocoderingsprofiel voor adaptieve streaming maken {#creating-a-video-encoding-profile-for-adaptive-streaming}

Dynamic Media wordt al geleverd met een vooraf gedefinieerd adaptief videocoderingsprofiel - een groep video-uploadinstellingen voor MP4 H.264-systeem dat is geoptimaliseerd voor de beste kijkervaring. U kunt dit profiel gebruiken wanneer u uw video&#39;s uploadt.

Als dit vooraf gedefinieerde profiel echter niet aan uw behoeften voldoet, kunt u zelf een adaptief videocoderingsprofiel maken. Wanneer u de instelling gebruikt **[!UICONTROL Encode for adaptive streaming]**-*beste praktijken*- alle coderingsvoorinstellingen die u aan het profiel toevoegt, worden gevalideerd om ervoor te zorgen dat alle video&#39;s dezelfde hoogte-breedteverhouding hebben. Bovendien worden de gecodeerde video&#39;s beschouwd als een set met multibitsnelheden voor streaming.

Wanneer u het videocoderingsprofiel maakt, ziet u dat de meeste coderingsopties vooraf zijn gevuld met de aanbevolen standaardinstellingen. Als u echter een andere waarde dan de aanbevolen standaardwaarde selecteert, moet u er rekening mee houden dat dit kan leiden tot een slechte videokwaliteit tijdens het afspelen en andere prestatieproblemen.

Voor alle MP4 H.264-videocoderingsvoorinstellingen in het profiel worden dus de volgende waarden gevalideerd om ervoor te zorgen dat deze voor afzonderlijke coderingsvoorinstellingen in het profiel hetzelfde zijn, zodat adaptief streamen mogelijk wordt:

* Video-indelingscodec - MP4 H.264 (.mp4)
* Audiocodec
* Audiobitsnelheid
* Hoogte-breedteverhouding behouden
* Codering met twee controles
* Constante bitsnelheid
* H264-profiel
* Samplingfrequentie audio

Als de waarden niet gelijk zijn, kunt u doorgaan met het maken van het profiel. Let er echter op dat adaptieve streaming niet mogelijk is. In plaats daarvan krijgen gebruikers last van streaming met één bitsnelheid. Het wordt aanbevolen de coderingsinstellingen te bewerken om dezelfde waarden te gebruiken voor afzonderlijke coderingsvoorinstellingen in het profiel. (Let op: de editor voor videoprofielen en voorinstellingen moet de pariteit van de aangepaste instellingen voor videocodering afdwingen als **[!UICONTROL Encode for adaptive streaming]** is ingeschakeld.)

Zie ook [Een videocoderingsprofiel voor progressieve streaming maken](#creating-a-video-encoding-profile-for-progressive-streaming).

Zie ook [Aanbevolen procedures voor videocodering](video.md#best-practices-for-encoding-videos).

Zie voor meer informatie over het definiëren van geavanceerde verwerkingsparameters voor andere elementtypen [Elementverwerking configureren](config-dms7.md#configuring-asset-processing).

Wanneer u klaar bent met het maken van het videoprofiel, past u het toe op een of meerdere mappen.

**Een Dynamic Media-videocoderingsprofiel voor adaptieve streaming maken**:

1. Tik op het AEM of klik op het logo en navigeer naar **[!UICONTROL Tools > Assets > Video Profiles]**.
1. Tikken **[!UICONTROL Create]** om een nieuw videoprofiel toe te voegen.

1. Voer een naam en beschrijving in voor het profiel.
1. Zorg ervoor dat **[!UICONTROL Encode for adaptive streaming]** is ingeschakeld (standaard).
1. Tik op **[!UICONTROL Add Video Encoding Preset]**.
1. Op de **[!UICONTROL Basic]** de video- en audio-opties instellen.

   Tik op het informatiepictogram naast elke optie voor extra beschrijvingen of aanbevolen instellingen op basis van de geselecteerde video-indelingscodec.

1. Controleer onder de kop Videogrootte of **[!UICONTROL Keep aspect ratio]** is ingeschakeld.
1. Stel de resolutie van de videoframegrootte in pixels in. Gebruik de **[!UICONTROL Auto]** waarde die automatisch moet worden geschaald om overeen te komen met de bronverhouding (breedte/hoogte-verhouding). Bijvoorbeeld Auto x 480 of 640 x Auto.

   Voer een van de volgende handelingen uit:

   * In de **[!UICONTROL Width]** veld, Enter **[!UICONTROL auto]**. In de **[!UICONTROL Height]** Voer een waarde in pixels in.
   * Tik op de knop **[!UICONTROL Information]** pictogram i) rechts van **[!UICONTROL Height]** om de **[!UICONTROL Size Calculator]** pagina. Gebruiken **[!UICONTROL Size Calculator]** om de gewenste videoafmetingen in te stellen (weergegeven door het blauwe vak). Tikken **[!UICONTROL X]** in de rechterbovenhoek als u klaar bent.

1. (Optioneel) Tik op de knop **[!UICONTROL Advanced]** en zorg ervoor dat de **[!UICONTROL Use Default Values]** is geselecteerd (aanbevolen). U kunt ook geavanceerde video- en audio-instellingen wijzigen.
1. Tik in de rechterbovenhoek van de pagina op **[!UICONTROL Save]** om de voorinstelling op te slaan.
1. Voer een van de volgende handelingen uit:

   * Herhaal stap 5-10 om extra coderingsvoorinstellingen te maken. (Voor adaptieve videostreaming zijn meerdere videovoorinstellingen vereist.)
   * Tik in de rechterbovenhoek van de pagina op **[!UICONTROL Save]** opnieuw om het profiel op te slaan.

## De voortgang van een coderingstaak controleren {#monitoring-the-progress-of-an-encoding-job}

Er wordt een verwerkingsindicator (of voortgangsbalk) weergegeven waarmee u de voortgang van een videocoderingstaak visueel kunt controleren.

U kunt ook de `error.log` bestand om de voortgang van een coderingstaak te controleren, te controleren of de codering is voltooid of om taakfouten te zien. De `error.log` is gevonden in het dialoogvenster `logs` map waarin het exemplaar van AEM is geïnstalleerd.

## Dynamic Media-videocoderingsprofielen voor progressieve streaming maken {#creating-a-video-encoding-profile-for-progressive-streaming}

Als u de optie **[!UICONTROL Encode for adaptive streaming]** niet wilt gebruiken, moet u er rekening mee houden dat alle coderingsvoorinstellingen die u aan het profiel toevoegt, worden behandeld als afzonderlijke videoweergaven voor streaming met één bitsnelheid of progressieve videobezorging. Er is ook geen validatie om ervoor te zorgen dat alle video-uitvoeringen dezelfde hoogte-breedteverhouding hebben.

Afhankelijk van de modus waarin u werkt, zijn de ondersteunde codecs voor video-indeling als volgt:

* Dynamic Media-Scene7-modus: H.264 (.mp4)
* Dynamic Media-Hybride modus: H.264 (.mp4), WebM

Zie ook [Een videocoderingsprofiel maken voor adaptieve streaming](#creating-a-video-encoding-profile-for-adaptive-streaming).

Zie ook [Aanbevolen procedures voor videocodering](video.md#best-practices-for-encoding-videos).

Zie voor meer informatie over het definiëren van geavanceerde verwerkingsparameters voor andere elementtypen [Elementverwerking configureren](config-dms7.md#configuring-asset-processing).

Wanneer u klaar bent met het maken van het videoprofiel, past u het toe op een of meerdere mappen.

**Een Dynamic Media-videocoderingsprofiel voor progressieve streaming maken:**

1. Tik op het AEM-logo en ga naar **[!UICONTROL Tools > Assets > Video Profiles]**.
1. Tikken **[!UICONTROL Create]** om een nieuw videoprofiel toe te voegen.
1. Voer een naam en beschrijving in voor het profiel.
1. Wis de **[!UICONTROL Encode for adaptive streaming]** selectievakje.
1. Tik op **[!UICONTROL Add Video Encoding Preset]**.
1. Op de **[!UICONTROL Basic]** de video- en audio-opties instellen.

   Tik op de knop **[!UICONTROL Information]** naast elke optie voor extra beschrijvingen of aanbevolen instellingen die zijn gebaseerd op de codec voor de geselecteerde video-indeling.

1. (Optioneel) Onder de **Videogrootte** kop, uitschakelen **[!UICONTROL Keep aspect ratio]**.
1. In de **[!UICONTROL Width]** veld, Enter **[!UICONTROL auto]**; rechts van de **[!UICONTROL Height]** tikken op het veld **[!UICONTROL Information]** pictogram. Gebruik de **[!UICONTROL Size Calculator]** pagina om de videodimensie (blauwe doos) verder in te stellen hoe u wilt. Tikken **[!UICONTROL X]** als u klaar bent.
1. (Optioneel) Voer een van de volgende handelingen uit:

   * Tik op de knop **[!UICONTROL Advanced]** en zorg ervoor **[!UICONTROL Use Default Values]** is geselecteerd (aanbevolen).
   * Wis de **[!UICONTROL Use Default Values]** en geeft u de gewenste video-instellingen en audio-instellingen op.

      Tik op de knop **[!UICONTROL Information]** naast elke optie voor extra beschrijvingen of aanbevolen instellingen die zijn gebaseerd op de codec voor de geselecteerde video-indeling.

1. Tik in de rechterbovenhoek van de pagina op **[!UICONTROL Save]** om de voorinstelling op te slaan.
1. Voer een van de volgende handelingen uit:

   * Herhaal stap 5-10 om extra coderingsvoorinstellingen te maken.
   * Tik in de rechterbovenhoek van de pagina op **[!UICONTROL Save]** om het profiel op te slaan.

## Parameters voor videocodering met aangepaste toevoeging gebruiken {#using-custom-added-video-encoding-parameters}

U kunt een bestaand videocoderingsprofiel bewerken om te profiteren van de geavanceerde parameters voor videocodering die niet in de gebruikersinterface worden gevonden wanneer u een videoprofiel maakt of bewerkt in AEM. U kunt een of meer geavanceerde parameters toevoegen, zoals **[!UICONTROL minBitrate]** en **[!UICONTROL maxBitrate]**—naar uw bestaande profiel.

**Parameters voor aangepaste videocodering gebruiken**:

1. Tik op het AEM-logo en ga naar **[!UICONTROL Tools > General > CRXDE Lite]**.
1. Van de **[!UICONTROL CRXDE Lite]** pagina, in de **[!UICONTROL Explorer]** aan de linkerkant, navigeer naar het volgende:

   `/conf/global/settings/dam/dm/presets/video/*name_of_video_encoding_profile_to_edit*`

1. In het deelvenster rechtsonder op de pagina, vanaf de knop **[!UICONTROL Properties]** tabblad, geeft u de **[!UICONTROL Name]**, **[!UICONTROL Type]**, en **[!UICONTROL Value]** van de parameter die u wilt gebruiken.

   U kunt de volgende geavanceerde parameters gebruiken:

   <table> 
    <tbody> 
    <tr> 
    <td><strong>Naam</strong></td> 
    <td><strong>Beschrijving</strong><br /> </td> 
    <td><strong>Type</strong><br /> </td> 
    <td><strong>Waarde</strong></td> 
    </tr> 
    <tr> 
    <td><code>h264Level</code></td> 
    <td>H.264-niveau voor codering. Normaal wordt dit automatisch bepaald op basis van de coderingsinstellingen die u gebruikt.</td> 
    <td><code>String</code></td> 
    <td><p>10 * h264 niveau</p> <p>3,0 = 30, 1,3 = 13)</p> <p>Geen standaardwaarde.</p> </td> 
    </tr> 
    <tr> 
    <td><code>keyframe</code></td> 
    <td>Het doelaantal frames tussen hoofdframes. Bereken deze waarde om een hoofdframe te genereren na elke 2-10 seconden. Bijvoorbeeld, bij 30 kaders per seconde, zou het keyframe interval 60-300 moeten zijn.<br /> <br /> De lagere keyframe intervallen verbeteren stroom het zoeken en stroom omschakelingsgedrag voor adaptieve videocoderingen en kunnen de kwaliteit voor video's ook verbeteren die veel motie hebben. Omdat hoofdframes de grootte van een bestand echter vergroten, resulteert een lager hoofdframe-interval meestal in een lagere algemene videokwaliteit bij een bepaalde bitsnelheid.</td> 
    <td><code>String</code></td> 
    <td><p>Positief getal.</p> <p>De standaardwaarde is 300.</p> <p>De aanbevolen waarde voor HLS (Live HTTP-streaming) is 60-90.</p> </td> 
    </tr> 
    <tr> 
    <td><code>minBitrate</code></td> 
    <td><p>Minimale bitsnelheid voor coderingen met variabele bitsnelheid, in Kbps (kilobits per seconde).</p> <p>Deze parameter is alleen van toepassing wanneer<strong> Constante bitsnelheid gebruiken</strong> is uitgeschakeld op het tabblad Geavanceerd wanneer u een videocoderingsprofiel maakt of bewerkt.</p> <p>Zie ook <a href="/help/assets/video.md#bitrate">Bitsnelheid</a>.</p> </td> 
    <td><code>String</code></td> 
    <td><p>Positief getal, in Kbps.</p> <p>Geen standaardwaarde.</p> </td> 
    </tr> 
    <tr> 
    <td><code>maxBitrate</code></td> 
    <td><p>Maximale bitsnelheid voor codering van variabele bitsnelheid, in Kbps.</p> <p>Deze parameter is alleen van toepassing wanneer<strong> Constante bitsnelheid gebruiken</strong> is uitgeschakeld op het tabblad Geavanceerd wanneer u een videocoderingsprofiel maakt of bewerkt.</p> <p>Zie ook <a href="/help/assets/video.md#bitrate">Bitsnelheid</a>.</p> </td> 
    <td><code>String</code></td> 
    <td><p>Positief getal, in Kbps.</p> <p>Geen standaardwaarde. De aanbevolen waarde bedraagt echter maximaal twee keer de coderingsbitsnelheid.</p> </td> 
    </tr> 
    <tr> 
    <td><code>audioBitrateCustom</code></td> 
    <td>Waarde instellen op <code>true</code> om een constante bitsnelheid voor de audiostream te forceren, indien ondersteund door audiocodec.</td> 
    <td><code>String</code></td> 
    <td><p><code>true</code>/<code>false</code></p> <p>Standaard is <code>false</code>.</p> <p>Aanbevolen waarde voor HLS (Live HTTP-streaming) is <code>false</code>.</p> <p> </p> </td> 
    </tr> 
    </tbody> 
   </table>

   ![chlimage_1-516](assets/chlimage_1-516.png)

1. Tik in de rechterbenedenhoek van de pagina op **[!UICONTROL Add]**.
1. Voer een van de volgende handelingen uit:

   * Herhaal stap 3 en 4 om een andere parameter toe te voegen aan uw videocoderingsprofiel.
   * Tik in de linkerbovenhoek van de pagina op **[!UICONTROL Save All]**.

1. In de linkerbovenhoek van het dialoogvenster **[!UICONTROL CRXDE Lite]** pagina, tikt u op de **[!UICONTROL Back Home]** pictogram om terug te keren naar AEM.

### Een Dynamic Media-videocoderingsprofiel bewerken {#editing-a-video-encoding-profile}

U kunt elk videocoderingsprofiel bewerken dat u hebt gemaakt om videovoorinstellingen in dat profiel toe te voegen, te bewerken of te verwijderen.

Standaard kunt u de vooraf gedefinieerde uit-van-de-doos niet bewerken **[!UICONTROL Adaptive Video Encoding]** profiel dat bij Dynamic Media werd geleverd. In plaats daarvan kunt u het profiel gemakkelijk kopiëren en opslaan met een nieuwe naam. Vervolgens kunt u de gewenste voorinstellingen bewerken in het gekopieerde profiel.

Zie ook [Aanbevolen procedures voor videocodering](video.md#best-practices-for-encoding-videos).

Zie voor meer informatie over het definiëren van geavanceerde verwerkingsparameters voor andere elementtypen [Elementverwerking configureren](config-dms7.md#configuring-asset-processing).

**Een Dynamic Media-videocoderingsprofiel bewerken**:

1. Tik op het AEM-logo en ga naar **[!UICONTROL Tools > Assets > Video Profiles]**.
1. Op de **[!UICONTROL Video Profiles]** te controleren.
1. Tik op de werkbalk op **[!UICONTROL Edit]**.
1. Op de **[!UICONTROL Video Encoding Profile]** en bewerkt u de naam en beschrijving naar wens.
1. U kunt het beste het selectievakje **[!UICONTROL Encode for adaptive streaming]** inschakelen.

   Tik op het informatiepictogram voor een beschrijving van adaptieve streaming. (Schakel dit selectievakje niet in als u een progressief videoprofiel bewerkt.)

1. Onder de **[!UICONTROL Video Encoding Presets]** voorinstellingen voor videocodering waaruit het profiel bestaat, toevoegen, bewerken of verwijderen.

   Tik op de knop **[!UICONTROL Information]** pictogram naast elke optie op het tabblad **[!UICONTROL Basic]** en **[!UICONTROL Advanced]** tabbladen voor extra beschrijvingen of aanbevolen instellingen op basis van de geselecteerde codec voor video-indelingen.

1. Tik in de rechterbovenhoek van de pagina op **[!UICONTROL Save]**.

### Een Dynamic Media-videocoderingsprofiel kopiëren {#copying-a-video-encoding-profile}

1. Tik op het AEM-logo en ga naar **[!UICONTROL Tools > Assets > Video Profiles]**.
1. Op de **[!UICONTROL Video Profiles]** te controleren.
1. Tik op de werkbalk op **[!UICONTROL Copy]**.
1. Op de **[!UICONTROL Video Encoding Profile]** voert u een nieuwe naam in voor het profiel.
1. U kunt het beste het selectievakje **[!UICONTROL Encode for adaptive streaming]** inschakelen. Tik op het informatiepictogram voor een beschrijving van adaptieve streaming. (Schakel het selectievakje niet in als u een progressief videoprofiel kopieert.)

   Als in de modus Dynamic Media - hybride een WebM-videovoorinstelling deel uitmaakt van het videoprofiel, **[!UICONTROL Encode for adaptive streaming]** is niet mogelijk omdat alle voorinstellingen MP4 moeten zijn.
1. Onder de **[!UICONTROL Video Encoding Presets]** voorinstellingen voor videocodering waaruit het profiel bestaat, toevoegen, bewerken of verwijderen.

   Tik op de knop **[!UICONTROL Information]** pictogram naast elke optie op het tabblad **[!UICONTROL Basic]** en **[!UICONTROL Advanced]** tabbladen voor aanbevolen instellingen en beschrijvingen.

1. Tik in de rechterbovenhoek van de pagina op **[!UICONTROL Save]**.

### Een Dynamic Media-videocoderingsprofiel verwijderen {#deleting-a-video-encoding-profile}

1. Tik op het AEM-logo en ga naar **[!UICONTROL Tools > Assets > Video Profiles]**.
1. Op de **[!UICONTROL Video Profiles]** pagina, controleert u een of meer namen van videoprofielen.
1. Tik op de werkbalk op **[!UICONTROL Delete]**.
1. Tik op **[!UICONTROL OK]**.

## Een Dynamic Media-videoprofiel toepassen op mappen {#applying-a-video-profile-to-folders}

Wanneer u een videoprofiel aan een omslag toewijst, erven om het even welke subfolders automatisch het profiel van zijn ouderomslag. Dit betekent dat u slechts één videoprofiel aan een map kunt toewijzen. Denk daarom zorgvuldig na over de mapstructuur van de locatie waar u middelen uploadt, opslaat, gebruikt en archiveert.

Als u een ander videoprofiel aan een omslag toewees, treedt het nieuwe profiel het vorige profiel met voeten. De vorige bestaande mapelementen blijven ongewijzigd. Het nieuwe profiel wordt toegepast op de elementen die later aan de map worden toegevoegd.

Mappen waaraan een profiel is toegewezen, worden in de gebruikersinterface aangeduid met de naam van het profiel dat in de kaartnaam wordt weergegeven.

![chlimage_1-517](assets/chlimage_1-517.png)

U kunt videoprofielen toepassen op specifieke mappen of op alle elementen.

### Videoprofielen toepassen op specifieke mappen {#applying-video-profiles-to-specific-folders}

U kunt een videoprofiel toepassen op een map vanuit het menu **[!UICONTROL Tools]**, of vanuit **[!UICONTROL Properties]** als u zich in een map bevindt. In deze sectie wordt beschreven hoe u videoprofielen op beide manieren op mappen kunt toepassen.

Mappen waaraan al een profiel is toegewezen, worden aangegeven door de naam van het profiel direct onder de mapnaam weer te geven.

#### Dynamic Media-videoprofielen toepassen op mappen vanuit de gebruikersinterface van Profielen {#applying-video-profiles-to-folders-from-profiles-user-interface}

1. Tik op het AEM-logo en ga naar **[!UICONTROL Tools > Assets > Video Profiles]**.
1. Selecteer het videoprofiel dat u wilt toepassen op een of meerdere mappen.
1. Tik op **[!UICONTROL Apply Profile to Folder(s)]** en selecteer de map of meerdere mappen die u wilt gebruiken om de nieuw geüploade assets te ontvangen en tik op **[!UICONTROL Apply]**. Mappen waaraan al een profiel is toegewezen, worden aangegeven door de naam van het profiel direct onder de mapnaam weer te geven.

#### Dynamic Media-videoprofielen toepassen op mappen vanuit Eigenschappen {#applying-video-profiles-to-folders-from-properties}

1. Tik op het AEM en navigeer naar **[!UICONTROL Assets]** en vervolgens naar de map waarop u een videoprofiel wilt toepassen.
1. Tik in de map op het vinkje om het te selecteren en tik vervolgens op **[!UICONTROL Properties]**.
1. Selecteer **[!UICONTROL Video Profiles]** en selecteert u het profiel in de vervolgkeuzelijst en tikt u op **[!UICONTROL Save & Close]**. Mappen waaraan al een profiel is toegewezen, worden aangegeven door de naam van het profiel direct onder de mapnaam weer te geven.

   ![chlimage_1-518](assets/chlimage_1-518.png)

### Een Dynamic Media-videoprofiel wereldwijd toepassen {#applying-a-video-profile-globally}

Naast het toepassen van een profiel op een map, kunt u er ook een globaal toepassen, zodat het geselecteerde profiel wordt toegepast op inhoud die is geüpload naar AEM elementen in een map.

**Een Dynamic Media-videoprofiel wereldwijd toepassen**:

1. Navigeer naar CRXDE Lite naar het volgende knooppunt: `/content/dam/jcr:content`.
1. De eigenschap toevoegen **[!UICONTROL videoProfile]**: `/etc/dam/video/dynamicmedia/<name_of_video_encoding_profile>`
1. Tik op **[!UICONTROL Save All]**.

![chlimage_1-519](assets/chlimage_1-519.png)

## Dynamic Media-videoprofielen uit mappen verwijderen {#removing-a-video-profile-from-folders}

Wanneer u een videoprofiel uit een map verwijdert, nemen eventuele submappen automatisch de verwijdering van het profiel uit de bovenliggende map over. Alle verwerking van bestanden die in de mappen zijn opgetreden, blijft echter intact.

U kunt een videoprofiel uit een map verwijderen vanuit het menu **[!UICONTROL Tools]**, of vanuit **[!UICONTROL Folder Settings]** als u zich in een map bevindt. In deze sectie wordt beschreven hoe u videoprofielen op beide manieren uit mappen kunt verwijderen.

### Dynamic Media-videoprofielen uit mappen verwijderen via de gebruikersinterface Profielen {#removing-video-profiles-from-folders-via-profiles-user-interface}

1. Tik op het AEM-logo en ga naar **[!UICONTROL Tools > Assets > Video Profiles]**.
1. Selecteer het videoprofiel dat u uit een of meerdere mappen wilt verwijderen.
1. Tik op **[!UICONTROL Remove Profile from Folder(s)]** en selecteer de map of meerdere mappen die u wilt gebruiken om het profiel te verwijderen en tik op **[!UICONTROL Remove]**.

   U kunt bevestigen dat het videoprofiel niet meer wordt toegepast op een map omdat de naam niet meer onder de mapnaam wordt weergegeven.

### Dynamic Media-videoprofielen uit mappen verwijderen door eigenschappen {#removing-video-profiles-from-folders-via-properties}

1. Tik op het AEM en navigeer naar **[!UICONTROL Assets]** en vervolgens naar de map waarvan u een videoprofiel wilt verwijderen.
1. Tik in de map op het vinkje om het te selecteren en tik vervolgens op **[!UICONTROL Properties]**.
1. Selecteer **[!UICONTROL Video Profiles]** en selecteert u **[!UICONTROL None]** in het keuzemenu en tikt u op **[!UICONTROL Save & Close]**. Mappen waaraan al een profiel is toegewezen, worden aangegeven door de naam van het profiel direct onder de mapnaam weer te geven.
