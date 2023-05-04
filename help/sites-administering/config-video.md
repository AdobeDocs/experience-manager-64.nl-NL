---
title: De component Video configureren
seo-title: Configure the Video component
description: Leer hoe u de videocomponent configureert.
seo-description: Learn how to configure the Video Component.
uuid: f4755a13-08ea-4096-a951-46a590f8d766
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: operations
content-type: reference
discoiquuid: a1efef3c-0e4b-4a17-bcad-e3cc17adbbf7
exl-id: 46d0765d-fb77-4332-8fbb-5bd2abcd6806
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 0%

---

# De component Video configureren {#configure-the-video-component}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

De [Video-component](/help/sites-authoring/default-components-foundation.md#video) Hiermee kunt u een vooraf gedefinieerd, OOTB-video-element (out-of-the-box) op uw pagina plaatsen.

Voor juiste transcodering moet uw beheerder [Mpeg installeren en AEM configureren](#install-ffmpeg) afzonderlijk. Zij kunnen ook [Uw videoprofielen configureren](#configure-video-profiles) voor gebruik met HTML5-elementen.

>[!CAUTION]
>
>Van deze component wordt niet meer verwacht om buiten-van-de-doos zonder uitgebreide project-vlakke aanpassing te functioneren.

## Videoprofielen configureren {#configure-video-profiles}

U kunt videoprofielen voor HTML5-elementen definiëren. De hier gekozen methoden worden op volgorde gebruikt. Voor toegang, gebruik [Ontwerpmodus](/help/sites-authoring/default-components-designmode.md) (Alleen klassieke gebruikersinterface) en selecteer de **[!UICONTROL Profiles]** tab:

![chlimage_1-317](assets/chlimage_1-317.png)

U kunt ook het ontwerp configureren van de videocomponenten en -parameters voor [!UICONTROL Playback], [!UICONTROL Flash], en [!UICONTROL Advanced].

## Mpeg installeren en AEM configureren {#install-ffmpeg}

De videocomponent is afhankelijk van open-source product Forms van derden voor een correcte transcodering van video&#39;s die kunnen worden gedownload van [https://ffmpeg.org/](https://ffmpeg.org/). Nadat u MPEG hebt geïnstalleerd, moet u AEM configureren voor het gebruik van een specifieke audiocodec en specifieke runtime-opties.

**Fmpeg voor uw platform installeren**:

* **In Windows:**

   1. Download het gecompileerde binaire bestand als `ffmpeg.zip`
   1. Pak een map uit.
   1. De systeemomgevingsvariabele instellen `PATH` tot `<*your-ffmpeg-locatio*n>\bin`
   1. Start AEM opnieuw.

* **In Mac OS X:**

   1. Xcode installeren ([https://developer.apple.com/technologies/tools/xcode.html](https://developer.apple.com/technologies/tools/xcode.html))
   1. XQuartz/X11 installeren.
   1. MacPorts installeren ([https://www.macports.org/](https://www.macports.org/))
   1. Voer in de console de volgende opdracht uit en volg de instructies:

      `sudo port install ffmpeg`

      `FFmpeg` moet zijn `PATH` AEM kan het oppakken via de opdrachtregel.

* **De vooraf gecompileerde versie voor OS X 10.6 gebruiken:**

   1. Download de vooraf gecompileerde versie.
   1. Extraheer het naar de `/usr/local` directory.
   1. Van terminal, voer uit:

      `sudo ln -s /usr/local/Cellar/ffmpeg/0.6/bin/ffmpeg /usr/bin/ffmpeg`

**AEM configureren**:

1. Openen [!UICONTROL CRXDE Lite] in uw webbrowser. ([http://localhost:4502/crx/de](http://localhost:4502/crx/de))
1. Selecteer `/libs/settings/dam/video/format_aac/jcr:content` en zorg ervoor dat de knoopeigenschappen als volgt zijn:

   * audioCodec:

      ```
       aac
      ```

   * customArgs:

      ```
       -flags +loop -me_method umh -g 250 -qcomp 0.6 -qmin 10 -qmax 51 -qdiff 4 -bf 16 -b_strategy 1 -i_qfactor 0.71 -cmp chroma -subq 8 -me_range 16 -coder 1 -sc_threshold 40 -b-pyramid normal -wpredp 2 -mixed-refs 1 -8x8dct 1 -fast-pskip 1 -keyint_min 25 -refs 4 -trellis 1 -direct-pred 3 -partitions i8x8,i4x4,p8x8,b8x8
      ```

1. Als u de configuratie wilt aanpassen, maakt u een bedekking in `/apps/settings/` knooppunt en dezelfde structuur onder `/conf/global/settings/` knooppunt. Kan het bestand niet bewerken in `/libs` knooppunt. Als u bijvoorbeeld een pad wilt bedekken `/libs/settings/dam/video/fullhd-bp`, maakt u deze op `/conf/global/settings/dam/video/fullhd-bp`.

   >[!NOTE]
   >
   >Bedek en bewerk het gehele profielknooppunt en niet alleen de eigenschap die moet worden gewijzigd. Dergelijke middelen worden niet opgelost via SlingResourceMerger.

1. Als u een van de eigenschappen hebt gewijzigd, klikt u op **[!UICONTROL Save All]**.

>[!NOTE]
>
>OTB-workflowmodellen blijven niet behouden wanneer u een upgrade uitvoert van uw AEM. Adobe raadt u aan OOTB-workflowmodellen te kopiëren voordat u ze bewerkt. Kopieer bijvoorbeeld het model OOTB DAM Update Asset voordat u de stap MPEG Transcoding in het DAM Update Asset model bewerkt om namen van videoprofielen te kiezen die vóór de upgrade bestonden. Vervolgens kunt u de `/apps` knoop om AEM de douaneveranderingen in het model te laten terugwinnen OTB.
