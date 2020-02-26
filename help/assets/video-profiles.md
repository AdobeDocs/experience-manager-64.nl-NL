---
title: Dynamische mediavideoprofielen
seo-title: Dynamische mediavideoprofielen
description: 'Dynamische media wordt al geleverd met een vooraf gedefinieerd adaptief videocoderingsprofiel. De instellingen in dit out-of-the-box profiel zijn geoptimaliseerd om uw klanten de beste kijkervaring mogelijk te maken. '
seo-description: 'Dynamische media wordt al geleverd met een vooraf gedefinieerd adaptief videocoderingsprofiel. De instellingen in dit out-of-the-box profiel zijn geoptimaliseerd om uw klanten de beste kijkervaring mogelijk te maken. '
uuid: cfb498f8-44a0-4d94-99b0-fed7c27f575b
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: administering
content-type: reference
discoiquuid: b893f366-279a-4872-9413-77626d3387ea
translation-type: tm+mt
source-git-commit: 1ebe1e871767605dd4295429c3d0b4de4dd66939

---


# Dynamic Media video profiles {#video-profiles}

Dynamische media wordt al geleverd met een vooraf gedefinieerd adaptief videocoderingsprofiel. De instellingen in dit out-of-the-box profiel zijn geoptimaliseerd om uw klanten de beste kijkervaring mogelijk te maken. Wanneer u uw stramienvideo&#39;s codeert met het profiel Adaptieve videocodering, past de videospeler tijdens het afspelen automatisch de kwaliteit van de videostream aan op basis van de snelheid van de internetverbinding van uw klanten. Dit wordt adaptieve streaming genoemd.

Hier volgen nog andere factoren die de kwaliteit van uw video&#39;s bepalen:

* **Resolutie van de geüploade hoofdvideo**

   Als de MP4-video met een lagere resolutie, zoals 240p of 360p, is opgenomen, kan deze niet in HD worden gestreamd.

* **Grootte videospeler**

   Standaard is de **[!UICONTROL breedte]** in het profiel Adaptieve videocodering ingesteld op **[!UICONTROL Automatisch]**. Ook tijdens het afspelen wordt de beste kwaliteit gebruikt op basis van de grootte van de speler.

Zie ook [Aanbevolen werkwijzen voor videocodering](video.md#best-practices-for-encoding-videos).

>[!NOTE]
>
>Als u de metagegevens van een video en de bijbehorende miniaturen van videoafbeeldingen wilt genereren, moet de video zelf het coderingsproces doorlopen in Dynamische media. In AEM codeert de workflow **[!UICONTROL Dynamische media coderen video]** als u dynamische media hebt ingeschakeld en videocloudservices hebt ingesteld. In deze workflow worden de historie en informatie over mislukkingen van het workflowproces vastgelegd.
>
>Zie [De videocodering controleren en de voortgang](video.md#monitoring-video-encoding-and-youtube-publishing-progress)van het publiceren op YouTube. Als u Dynamic Media hebt ingeschakeld en videocloudservices hebt ingesteld, wordt de workflow Video **[!UICONTROL via]** dynamische media coderen automatisch van kracht wanneer u een video uploadt. (Als u geen dynamische media gebruikt, wordt de workflow voor **[!UICONTROL DAM-updatemiddelen]** van kracht.)
>
>Metagegevens zijn handig wanneer u naar elementen zoekt. De miniaturen zijn statische videobeelden die tijdens het coderen worden gegenereerd. Ze zijn vereist door het AEM-systeem en worden gebruikt in de gebruikersinterface om u te helpen video&#39;s visueel te identificeren in de weergave **** Kaarten, de weergave **[!UICONTROL Zoekresultaten]** en de weergave **[!UICONTROL Lijst]** met middelen. De gegenereerde miniaturen worden weergegeven wanneer u op het pictogram **[!UICONTROL Uitvoeringen]** (een palet van een schilder) van een gecodeerde video tikt.

Wanneer u klaar bent met het maken van het videoprofiel, past u het toe op een map of meerdere mappen. Zie Een videoprofiel [toepassen op mappen.](#applying-a-video-profile-to-folders)

Zie [Elementverwerking](config-dms7.md#configuring-asset-processing)configureren voor het definiëren van geavanceerde verwerkingsparameters voor andere elementtypen.

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

## Een profiel voor dynamische mediacodering voor adaptieve streaming maken {#creating-a-video-encoding-profile-for-adaptive-streaming}

Dynamische media wordt al geleverd met een vooraf gedefinieerd adaptief videocoderingsprofiel - een groep video-uploadinstellingen voor MP4 H.264-systeem dat is geoptimaliseerd voor de beste kijkervaring. U kunt dit profiel gebruiken wanneer u uw video&#39;s uploadt.

Als dit vooraf gedefinieerde profiel echter niet aan uw behoeften voldoet, kunt u zelf een adaptief videocoderingsprofiel maken. Als u de instelling **[!UICONTROL Coderen gebruikt voor adaptieve streaming]**, is *een goede werkwijze*: alle coderingsvoorinstellingen die u toevoegt aan het profiel worden gevalideerd om ervoor te zorgen dat alle video&#39;s dezelfde hoogte-breedteverhouding hebben. Bovendien worden de gecodeerde video&#39;s beschouwd als een set met multibitsnelheden voor streaming.

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

Als de waarden niet gelijk zijn, kunt u doorgaan met het maken van het profiel. Let er echter op dat adaptieve streaming niet mogelijk is. In plaats daarvan krijgen gebruikers last van streaming met één bitsnelheid. Het wordt aanbevolen de coderingsinstellingen te bewerken om dezelfde waarden te gebruiken voor afzonderlijke coderingsvoorinstellingen in het profiel. (De videoprofiel/voorinstellingseditor moet de pariteit van de adaptieve instellingen voor videocodering afdwingen als **[!UICONTROL Coderen voor adaptieve streaming]** is ingeschakeld.)

Zie ook Een videocoderingsprofiel [maken voor progressieve streaming](#creating-a-video-encoding-profile-for-progressive-streaming).

Zie ook [Aanbevolen werkwijzen voor videocodering](video.md#best-practices-for-encoding-videos).

Zie [Elementverwerking](config-dms7.md#configuring-asset-processing)configureren voor het definiëren van geavanceerde verwerkingsparameters voor andere elementtypen.

Wanneer u klaar bent met het maken van het videoprofiel, past u het toe op een of meerdere mappen.

**Een profiel voor videocodering van dynamische media maken voor adaptieve streaming**:

1. Tik op het AEM-logo of klik op dit logo en navigeer naar **[!UICONTROL Gereedschappen > Elementen > Videoprofielen]**.
1. Tik op **[!UICONTROL Maken]** om een nieuw videoprofiel toe te voegen.

1. Voer een naam en beschrijving in voor het profiel.
1. Controleer of **[!UICONTROL Coderen voor adaptieve streaming]** is ingeschakeld (standaard).
1. Tik op Voorinstelling voor videocodering **[!UICONTROL toevoegen]**.
1. Stel op het tabblad **[!UICONTROL Standaard]** de video- en audio-opties in.

   Tik op het informatiepictogram naast elke optie voor extra beschrijvingen of aanbevolen instellingen op basis van de geselecteerde video-indelingscodec.

1. Controleer of onder de kop Videogrootte de hoogte-breedteverhouding **** behouden is ingeschakeld.
1. Stel de resolutie van de videoframegrootte in pixels in. Gebruik de waarde **[!UICONTROL Automatisch]** om automatisch te schalen zodat deze overeenkomt met de hoogte-breedteverhouding van de bron (breedte-hoogteverhouding). Bijvoorbeeld Auto x 480 of 640 x Auto.

   Voer een van de volgende handelingen uit:

   * Voer in het veld **[!UICONTROL Breedte]** **[!UICONTROL automatisch]** in. Voer in het veld **[!UICONTROL Hoogte]** een waarde in pixels in.
   * Tik op het pictogram **[!UICONTROL Informatie]** (i) rechts van **[!UICONTROL Hoogte]** om de pagina **[!UICONTROL Grootte berekenen]** te openen, zodat u de grootte van de video kunt visualiseren. Met de **[!UICONTROL maatcalculator]** kunt u de gewenste videoafmetingen instellen (weergegeven door het blauwe vak). Tik op **[!UICONTROL X]** in de rechterbovenhoek als u klaar bent.

1. (Optioneel) Tik op het tabblad **[!UICONTROL Geavanceerd]** en schakel het selectievakje Standaardwaarden **** gebruiken in (aanbevolen). U kunt ook geavanceerde video- en audio-instellingen wijzigen.
1. Tik in de rechterbovenhoek van de pagina op **[!UICONTROL Opslaan]** om de voorinstelling op te slaan.
1. Voer een van de volgende handelingen uit:

   * Herhaal stap 5-10 om extra coderingsvoorinstellingen te maken. (Voor adaptieve videostreaming zijn meerdere videovoorinstellingen vereist.)
   * Tik in de rechterbovenhoek van de pagina nogmaals op **[!UICONTROL Opslaan]** om het profiel op te slaan.

## De voortgang van een coderingstaak controleren {#monitoring-the-progress-of-an-encoding-job}

Er wordt een verwerkingsindicator (of voortgangsbalk) weergegeven waarmee u de voortgang van een videocoderingstaak visueel kunt controleren.

U kunt het `error.log` bestand ook weergeven om de voortgang van een coderingstaak te controleren, te zien of de codering is voltooid of om taakfouten te zien. De `error.log` map staat in de `logs` map waarin uw exemplaar van AEM is geïnstalleerd.

## Een profiel voor dynamische mediacodering voor progressieve streaming maken {#creating-a-video-encoding-profile-for-progressive-streaming}

Als u ervoor kiest de optie **[!UICONTROL Coderen voor adaptieve streaming]** niet te gebruiken, moet u er rekening mee houden dat alle coderingsvoorinstellingen die u aan het profiel toevoegt, worden beschouwd als afzonderlijke video-uitvoeringen voor streaming met één bitsnelheid of progressieve videoverzending. Er is ook geen validatie om ervoor te zorgen dat alle video-uitvoeringen dezelfde hoogte-breedteverhouding hebben.

Afhankelijk van de modus waarin u werkt, zijn de ondersteunde codecs voor video-indeling als volgt:

* Dynamische media-Scene7 wijze: H.264 (.mp4)
* Dynamische media-hybride modus: H.264 (.mp4), WebM

Zie ook Een videocoderingsprofiel [maken voor adaptieve streaming](#creating-a-video-encoding-profile-for-adaptive-streaming).

Zie ook [Aanbevolen werkwijzen voor videocodering](video.md#best-practices-for-encoding-videos).

Zie [Elementverwerking](config-dms7.md#configuring-asset-processing)configureren voor het definiëren van geavanceerde verwerkingsparameters voor andere elementtypen.

Wanneer u klaar bent met het maken van het videoprofiel, past u het toe op een of meerdere mappen.

**Een profiel voor dynamische mediacodering voor progressieve streaming maken:**

1. Tik op het AEM-logo en navigeer naar **[!UICONTROL Gereedschappen > Middelen > Videoprofielen]**.
1. Tik op **[!UICONTROL Maken]** om een nieuw videoprofiel toe te voegen.
1. Voer een naam en beschrijving in voor het profiel.
1. Schakel het selectievakje **[!UICONTROL Coderen voor adaptieve streaming]** uit.
1. Tik op Voorinstelling voor videocodering **[!UICONTROL toevoegen]**.
1. Stel op het tabblad **[!UICONTROL Standaard]** de video- en audio-opties in.

   Tik op het pictogram **[!UICONTROL Informatie]** naast elke optie voor extra beschrijvingen of aanbevolen instellingen op basis van de geselecteerde codec voor video-indelingen.

1. (Optioneel) Schakel onder de kop **Videogrootte** de optie **[!UICONTROL Hoogte-breedteverhouding]** behouden uit.
1. Voer in het veld **[!UICONTROL Breedte]** **[!UICONTROL auto]** in; Tik rechts van het veld **[!UICONTROL Hoogte]** op het pictogram **[!UICONTROL Informatie]** . Gebruik de pagina **[!UICONTROL Groottecalculator]** om de videodimensie (blauw vakje) verder te plaatsen hoe u wilt. Tik op **[!UICONTROL X]** als u klaar bent.
1. (Optioneel) Voer een van de volgende handelingen uit:

   * Tik op het tabblad **[!UICONTROL Geavanceerd]** en schakel het selectievakje Standaardwaarden **** gebruiken in (aanbevolen).
   * Schakel het selectievakje Standaardwaarden **** gebruiken uit en geef de gewenste video-instellingen en audio-instellingen op.

      Tik op het pictogram **[!UICONTROL Informatie]** naast elke optie voor extra beschrijvingen of aanbevolen instellingen op basis van de geselecteerde codec voor video-indelingen.

1. Tik in de rechterbovenhoek van de pagina op **[!UICONTROL Opslaan]** om de voorinstelling op te slaan.
1. Voer een van de volgende handelingen uit:

   * Herhaal stap 5-10 om extra coderingsvoorinstellingen te maken.
   * Tik in de rechterbovenhoek van de pagina op **[!UICONTROL Opslaan]** om het profiel op te slaan.

## Parameters voor videocodering met aangepaste toevoeging gebruiken {#using-custom-added-video-encoding-parameters}

U kunt een bestaand videocoderingsprofiel bewerken om te profiteren van geavanceerde parameters voor videocodering die niet in de gebruikersinterface worden gevonden wanneer u een videoprofiel maakt of bewerkt in AEM. Aangepast voegt u een of meer geavanceerde parameters, zoals **[!UICONTROL minBitrate]** en **[!UICONTROL maxBitrate]**, toe aan uw bestaande profiel.

**U kunt als volgt parameters** voor videocodering met aangepaste toevoeging gebruiken:

1. Tik op het AEM-logo en navigeer naar **[!UICONTROL Gereedschappen > Algemeen > CRXDE Lite]**.
1. Navigeer van de pagina **[!UICONTROL CRXDE Lite]** in het paneel van de **[!UICONTROL Ontdekkingsreiziger]** op de linkerzijde aan het volgende:

   `/conf/global/settings/dam/dm/presets/video/*name_of_video_encoding_profile_to_edit*`

1. In het paneel op de laag-juiste kant van de pagina, van het lusje van **[!UICONTROL Eigenschappen]** , specificeer de **[!UICONTROL Naam]**, het **[!UICONTROL Type]**, en de **[!UICONTROL Waarde]** van de parameter u wilt gebruiken.

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
    <td>H.264-niveau voor codering. Normaal gesproken wordt dit automatisch bepaald op basis van de coderingsinstellingen die u gebruikt.</td> 
    <td><code>String</code></td> 
    <td><p>10 * h264 niveau</p> <p>3,0 = 30, 1,3 = 13)</p> <p>Geen standaardwaarde.</p> </td> 
    </tr> 
    <tr> 
    <td><code>keyframe</code></td> 
    <td>Het doelaantal frames tussen hoofdframes. Bereken deze waarde om een hoofdframe te genereren na elke 2-10 seconden. Bijvoorbeeld, bij 30 kaders per seconde, zou het keyframe interval 60-300 moeten zijn.<br /> Met <br /> lagere keyframe-intervallen verbetert u het zoeken naar streams en het schakelen tussen streams voor adaptieve videocoderingen. De kwaliteit van video's met veel beweging kan ook verbeteren. Omdat hoofdframes de grootte van een bestand echter vergroten, resulteert een lager hoofdframe-interval meestal in een lagere algemene videokwaliteit bij een bepaalde bitsnelheid.</td> 
    <td><code>String</code></td> 
    <td><p>Positief getal.</p> <p>De standaardwaarde is 300.</p> <p>De aanbevolen waarde voor HLS (Live HTTP-streaming) is 60-90.</p> </td> 
    </tr> 
    <tr> 
    <td><code>minBitrate</code></td> 
    <td><p>Minimale bitsnelheid voor coderingen met variabele bitsnelheid, in Kbps (kilobits per seconde).</p> <p>Deze parameter is alleen van toepassing wanneer<strong> Constante bitsnelheid</strong> gebruiken op het tabblad Geavanceerd is uitgeschakeld wanneer u een videocoderingsprofiel maakt of bewerkt.</p> <p>Zie ook <a href="/help/assets/video.md#bitrate">Bitsnelheid</a>.</p> </td> 
    <td><code>String</code></td> 
    <td><p>Positief getal, in Kbps.</p> <p>Geen standaardwaarde.</p> </td> 
    </tr> 
    <tr> 
    <td><code>maxBitrate</code></td> 
    <td><p>Maximale bitsnelheid voor codering van variabele bitsnelheid, in Kbps.</p> <p>Deze parameter is alleen van toepassing wanneer<strong> Constante bitsnelheid</strong> gebruiken op het tabblad Geavanceerd is uitgeschakeld wanneer u een videocoderingsprofiel maakt of bewerkt.</p> <p>Zie ook <a href="/help/assets/video.md#bitrate">Bitsnelheid</a>.</p> </td> 
    <td><code>String</code></td> 
    <td><p>Positief getal, in Kbps.</p> <p>Geen standaardwaarde. De aanbevolen waarde bedraagt echter maximaal twee keer de coderingsbitsnelheid.</p> </td> 
    </tr> 
    <tr> 
    <td><code>audioBitrateCustom</code></td> 
    <td>Stel de waarde in om een constante bitsnelheid voor de audiostream <code>true</code> te forceren, indien ondersteund door de audiocodec.</td> 
    <td><code>String</code></td> 
    <td><p><code>true</code>/<code>false</code></p> <p>Standaard is dit <code>false</code>.</p> <p>De aanbevolen waarde voor HLS (Live HTTP-streaming) is <code>false</code>.</p> <p> </p> </td> 
    </tr> 
    </tbody> 
   </table>

   ![chlimage_1-516](assets/chlimage_1-516.png)

1. Tik in de rechterbenedenhoek van de pagina op **[!UICONTROL Toevoegen]**.
1. Voer een van de volgende handelingen uit:

   * Herhaal stap 3 en 4 om een andere parameter toe te voegen aan uw videocoderingsprofiel.
   * Tik in de linkerbovenhoek van de pagina op Alles **[!UICONTROL opslaan]**.

1. Tik in de linkerbovenhoek van de **[!UICONTROL CRXDE Lite]** -pagina op het **[!UICONTROL pictogram Home]** Terug om terug te keren naar AEM.

### Een profiel voor videocodering van dynamische media bewerken {#editing-a-video-encoding-profile}

U kunt elk videocoderingsprofiel bewerken dat u hebt gemaakt om videovoorinstellingen in dat profiel toe te voegen, te bewerken of te verwijderen.

Standaard kunt u het vooraf gedefinieerde, kant-en-klare **[!UICONTROL adaptieve videocoderingsprofiel]** dat bij Dynamische media is geleverd, niet bewerken. In plaats daarvan kunt u het profiel gemakkelijk kopiëren en opslaan met een nieuwe naam. Vervolgens kunt u de gewenste voorinstellingen bewerken in het gekopieerde profiel.

Zie ook [Aanbevolen werkwijzen voor videocodering](video.md#best-practices-for-encoding-videos).

Zie [Elementverwerking](config-dms7.md#configuring-asset-processing)configureren voor het definiëren van geavanceerde verwerkingsparameters voor andere elementtypen.

**Een profiel** voor videocodering van dynamische media bewerken:

1. Tik op het AEM-logo en navigeer naar **[!UICONTROL Gereedschappen > Middelen > Videoprofielen]**.
1. Controleer op de pagina **[!UICONTROL Videoprofielen]** één videoprofielnaam.
1. Tik op **[!UICONTROL Bewerken]** op de werkbalk.
1. Bewerk de naam en beschrijving op de pagina Profiel **[!UICONTROL voor]** videocodering.
1. U kunt het beste het selectievakje **[!UICONTROL Coderen voor adaptieve streaming]** inschakelen.

   Tik op het informatiepictogram voor een beschrijving van adaptieve streaming. (Schakel dit selectievakje niet in als u een progressief videoprofiel bewerkt.)

1. Onder de kop Voorinstellingen **[!UICONTROL voor]** videocodering kunt u voorinstellingen voor videocodering die het profiel vormen, toevoegen, bewerken of verwijderen.

   Tik op het pictogram **[!UICONTROL Informatie]** naast elke optie op de tabbladen **[!UICONTROL Standaard]** en **[!UICONTROL Geavanceerd]** voor extra beschrijvingen of aanbevolen instellingen die zijn gebaseerd op de codec voor de geselecteerde video-indeling.

1. Tik in de rechterbovenhoek van de pagina op **[!UICONTROL Opslaan]**.

### Een profiel voor videocodering van dynamische media kopiëren {#copying-a-video-encoding-profile}

1. Tik op het AEM-logo en navigeer naar **[!UICONTROL Gereedschappen > Middelen > Videoprofielen]**.
1. Controleer op de pagina **[!UICONTROL Videoprofielen]** één videoprofielnaam.
1. Tik op **[!UICONTROL Kopiëren]** op de werkbalk.
1. Voer op de pagina Profiel **[!UICONTROL voor]** videocodering een nieuwe naam in voor het profiel.
1. U kunt het beste het selectievakje **[!UICONTROL Coderen voor adaptieve streaming]** inschakelen. Tik op het informatiepictogram voor een beschrijving van adaptieve streaming. (Schakel het selectievakje niet in als u een progressief videoprofiel kopieert.)

   Als in de modus Dynamische media - hybride een WebM-videovoorinstelling deel uitmaakt van het videoprofiel, is **[!UICONTROL Coderen voor adaptieve streaming]** niet mogelijk omdat alle voorinstellingen MP4 moeten zijn.
1. Onder de kop Voorinstellingen **[!UICONTROL voor]** videocodering kunt u voorinstellingen voor videocodering die het profiel vormen, toevoegen, bewerken of verwijderen.

   Tik op het pictogram **[!UICONTROL Informatie]** naast elke optie op de tabbladen **[!UICONTROL Standaard]** en **[!UICONTROL Geavanceerd]** voor aanbevolen instellingen en beschrijvingen.

1. Tik in de rechterbovenhoek van de pagina op **[!UICONTROL Opslaan]**.

### Een profiel voor videocodering van dynamische media verwijderen {#deleting-a-video-encoding-profile}

1. Tik op het AEM-logo en navigeer naar **[!UICONTROL Gereedschappen > Middelen > Videoprofielen]**.
1. Controleer een of meer namen van videoprofielen op de pagina **[!UICONTROL Videoprofielen]** .
1. Tik op de werkbalk op **[!UICONTROL Verwijderen]**.
1. Tik op **[!UICONTROL OK]**.

## Een dynamisch mediavideoprofiel toepassen op mappen {#applying-a-video-profile-to-folders}

Wanneer u een videoprofiel aan een omslag toewijst, erven om het even welke subfolders automatisch het profiel van zijn ouderomslag. Dit betekent dat u slechts één videoprofiel aan een map kunt toewijzen. Denk daarom zorgvuldig na over de mapstructuur van de locatie waar u middelen uploadt, opslaat, gebruikt en archiveert.

Als u een ander videoprofiel aan een omslag toewees, treedt het nieuwe profiel het vorige profiel met voeten. De vorige bestaande mapelementen blijven ongewijzigd. Het nieuwe profiel wordt toegepast op de elementen die later aan de map worden toegevoegd.

Mappen waaraan een profiel is toegewezen, worden in de gebruikersinterface aangeduid met de naam van het profiel dat in de kaartnaam wordt weergegeven.

![chlimage_1-517](assets/chlimage_1-517.png)

U kunt videoprofielen toepassen op specifieke mappen of op alle elementen.

### Videoprofielen toepassen op specifieke mappen {#applying-video-profiles-to-specific-folders}

U kunt een videoprofiel toepassen op een map vanuit het menu **[!UICONTROL Gereedschappen]** of vanuit de map **[!UICONTROL Eigenschappen]**. In deze sectie wordt beschreven hoe u videoprofielen op beide manieren op mappen kunt toepassen.

Mappen waaraan al een profiel is toegewezen, worden aangegeven door de naam van het profiel direct onder de mapnaam weer te geven.

#### Dynamische mediavideoprofielen toepassen op mappen vanuit de gebruikersinterface van Profielen {#applying-video-profiles-to-folders-from-profiles-user-interface}

1. Tik op het AEM-logo en navigeer naar **[!UICONTROL Gereedschappen > Middelen > Videoprofielen]**.
1. Selecteer het videoprofiel dat u wilt toepassen op een of meerdere mappen.
1. Tik op Profiel **[!UICONTROL toepassen op map(pen)]** en selecteer de map of meerdere mappen die u wilt gebruiken om de nieuw geüploade elementen te ontvangen en tik op **[!UICONTROL Toepassen]**. Mappen waaraan al een profiel is toegewezen, worden aangegeven door de naam van het profiel direct onder de mapnaam weer te geven.

#### Dynamische mediavideoprofielen toepassen op mappen vanuit Eigenschappen {#applying-video-profiles-to-folders-from-properties}

1. Tik op het AEM-logo en navigeer naar **[!UICONTROL Middelen]** en vervolgens naar de map waarop u een videoprofiel wilt toepassen.
1. Tik in de map op het vinkje om het te selecteren en tik vervolgens op **[!UICONTROL Eigenschappen]**.
1. Selecteer het tabblad **[!UICONTROL Videoprofielen]** en selecteer het profiel in de vervolgkeuzelijst en tik op **[!UICONTROL Opslaan en sluiten]**. Mappen waaraan al een profiel is toegewezen, worden aangegeven door de naam van het profiel direct onder de mapnaam weer te geven.

   ![chlimage_1-518](assets/chlimage_1-518.png)

### Een dynamisch mediavideoprofiel wereldwijd toepassen {#applying-a-video-profile-globally}

Naast het toepassen van een profiel op een map, kunt u er ook een globaal toepassen, zodat het geselecteerde profiel wordt toegepast op inhoud die in AEM-elementen in een map is geüpload.

**Een dynamisch mediavideoprofiel algemeen** toepassen:

1. Navigeer naar CRXDE Lite naar het volgende knooppunt: `/content/dam/jcr:content`.
1. Voeg de eigenschap **[!UICONTROL videoProfile]** toe: `/etc/dam/video/dynamicmedia/<name_of_video_encoding_profile>`
1. Tik op Alles **** opslaan.

![chlimage_1-519](assets/chlimage_1-519.png)

## Een dynamisch mediavideoprofiel uit mappen verwijderen {#removing-a-video-profile-from-folders}

Wanneer u een videoprofiel uit een map verwijdert, nemen eventuele submappen automatisch de verwijdering van het profiel uit de bovenliggende map over. Alle verwerking van bestanden die in de mappen zijn opgetreden, blijft echter intact.

U kunt een videoprofiel uit een map verwijderen vanuit het menu **[!UICONTROL Gereedschappen]** of vanuit de map Instellingen **** map. In deze sectie wordt beschreven hoe u videoprofielen op beide manieren uit mappen kunt verwijderen.

### Dynamische mediavideoprofielen uit mappen verwijderen via de gebruikersinterface Profielen {#removing-video-profiles-from-folders-via-profiles-user-interface}

1. Tik op het AEM-logo en navigeer naar **[!UICONTROL Gereedschappen > Middelen > Videoprofielen]**.
1. Selecteer het videoprofiel dat u uit een of meerdere mappen wilt verwijderen.
1. Tik op Profiel **[!UICONTROL verwijderen uit map(pen)]** en selecteer de map of meerdere mappen waaruit u het profiel wilt verwijderen en tik op **[!UICONTROL Verwijderen]**.

   U kunt bevestigen dat het videoprofiel niet meer wordt toegepast op een map omdat de naam niet meer onder de mapnaam wordt weergegeven.

### Dynamische mediavideoprofielen uit mappen verwijderen met eigenschappen {#removing-video-profiles-from-folders-via-properties}

1. Tik op het AEM-logo en navigeer naar **[!UICONTROL Middelen]** en vervolgens naar de map waaruit u een videoprofiel wilt verwijderen.
1. Tik in de map op het vinkje om het te selecteren en tik vervolgens op **[!UICONTROL Eigenschappen]**.
1. Selecteer het tabblad **[!UICONTROL Videoprofielen]** en selecteer **[!UICONTROL Geen]** in de vervolgkeuzelijst en tik op **[!UICONTROL Opslaan en sluiten]**. Mappen waaraan al een profiel is toegewezen, worden aangegeven door de naam van het profiel direct onder de mapnaam weer te geven.

