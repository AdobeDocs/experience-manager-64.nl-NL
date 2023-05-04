---
title: Ondersteunde bestandsindelingen in [!DNL Experience Manager] Activa
description: Lijst met bestandsindelingen en MIME-typen die worden ondersteund door Middelen en de functies die worden ondersteund voor elke indeling.
contentOwner: AG
feature: Asset Management,Renditions
role: User,Admin
exl-id: ee25fe8f-36fb-42b3-9f90-0ea77bc02e2f
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1671'
ht-degree: 1%

---

# Bestandsindelingen ondersteund in [!DNL Adobe Experience Manager Assets] {#assets-supported-formats}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

[!DNL Experience Manager Assets] ondersteunt een groot aantal bestandsindelingen en elke functie biedt verschillende ondersteuning voor verschillende MIME-typen.

Om te integreren [!DNL Assets] met andere DAM-oplossingen (Digital Asset Management) en desktopsoftware, gebruik Adobe Extensible Metadata Platform (XMP).

Gebruik de legenda om het steunniveau te begrijpen.

| Ondersteuningsniveau | Beschrijving |
|:---:|---|
| ✓ | Ondersteund |
| &#42; | Ondersteund met extra functies |
| − | Niet van toepassing |

## Rasterafbeeldingsindelingen {#supported-raster-image-formats}

Rasterindelingen voor afbeeldingen die worden ondersteund voor functies voor middelenbeheer zijn als volgt:

| Indeling | Opslag | Metagegevensbeheer | Metagegevensextractie | Miniaturen genereren | Interactief bewerken | Metagegevens terugschrijven | Inzichten |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| PNG | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| GIF | ✓ | ✓ | ✓ | ✓ | ✓ |  | ✓ |
| TIFF | ✓ | ✓ | ✓ | ✓ |  | ✓ | ✓ |
| JPEG | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| BMP | ✓ | ✓ | ✓ | ✓ | ✓ |  | ✓ |
| PNM | ✓ | ✓ |  |  |  |  | ✓ |
| PGM | ✓ | ✓ |  |  |  |  | ✓ |
| PBM | ✓ | ✓ |  |  |  |  | ✓ |
| PPM | ✓ | ✓ |  |  |  |  | ✓ |
| PSD **‡** | ✓ | ✓ | ✓ | ✓ |  |  | ✓ |
| [EPS](managing-image-presets.md#adobe-illustrator-ai-postscript-eps-and-pdf-file-formats) | ✓ | ✓ | ✓ | ✓ |  | ✓ |  |
| PICT |  |  |  |  |  |  | ✓ |
| PSB | ✓ | ✓ | ✓ | ✓ |  |  |  |

**‡** De samengevoegde afbeelding wordt uit het PSD-bestand geëxtraheerd. Het is een afbeelding die door Adobe Photoshop wordt gegenereerd en die in het PSD-bestand wordt opgenomen. Afhankelijk van de instellingen kan de samengevoegde afbeelding wel of niet de werkelijke afbeelding zijn.

Rasterindelingen voor afbeeldingen die worden ondersteund voor Dynamic Media-functies zijn:

| Indeling | Uploaden<br> (Invoerindeling) | Maken<br> image<br> voorinstelling<br> (Uitvoerindeling) | Voorvertoning<br> dynamic<br> uitvoering | Leveren<br> dynamic<br> uitvoering | Downloaden<br> dynamic<br> uitvoering |
|---|:---:|:---:|:---:|:---:|:---:|
| PNG | ✓ | ✓ | ✓ | ✓ | ✓ |
| GIF | ✓ | ✓ | ✓ | ✓ | ✓ |
| TIFF | ✓ | ✓ | ✓ | ✓ | ✓ |
| JPEG | ✓ | ✓ | ✓ | ✓ | ✓ |
| BMP | ✓ |  |  |  |  |
| PNM |  |  |  |  |  |
| PGM |  |  |  |  |  |
| PBM |  |  |  |  |  |
| PPM |  |  |  |  |  |
| PSD **‡** | ✓ |  |  |  |  |
| [EPS](managing-image-presets.md#adobe-illustrator-ai-postscript-eps-and-pdf-file-formats) | ✓ | ✓ | ✓ | ✓ | ✓ |
| PICT | ✓ |  |  |  |  |
| PSB |  |  |  |  |  |

**‡** De samengevoegde afbeelding wordt uit het PSD-bestand geëxtraheerd. Het is een afbeelding die door Adobe Photoshop wordt gegenereerd en die in het PSD-bestand wordt opgenomen. Afhankelijk van de instellingen kan de samengevoegde afbeelding wel of niet de werkelijke afbeelding zijn.

Naast bovenstaande informatie, moet u rekening houden met het volgende:

* De ondersteuning voor EPS-bestanden is alleen van toepassing op rasterafbeeldingen. Miniatuurgeneratie voor vectorafbeeldingen van EPS wordt bijvoorbeeld niet standaard ondersteund. Als u ondersteuning wilt toevoegen, [ImageMagick configureren](best-practices-for-imagemagick.md). Om hulpmiddelen van derden te integreren om extra mogelijkheden toe te laten, zie [Op opdrachtregel gebaseerde Media Handler](media-handlers.md#command-line-based-media-handler).

* Metagegevensterugschrijving werkt voor PSB-bestandsindeling wanneer deze wordt toegevoegd aan de `NComm` handler.

* Als u Dynamic Media wilt gebruiken om dynamische uitvoeringen voor EPS-bestanden voor te vertonen en te genereren, raadpleegt u [Adobe Illustrator- (AI), Postscript- (EPS) en PDF-bestandsindelingen.](../assets/managing-image-presets.md#adobe-illustrator-ai-postscript-eps-and-pdf-file-formats)

* Voor EPS-bestanden wordt terugschrijven van metagegevens ondersteund in versie 3.0 of hoger van de PostScript Document Structuring Convention (PS-Adobe).

## Niet-ondersteunde rasterafbeeldingsindelingen in Dynamic Media {#unsupported-image-formats-dynamic-media}

In de volgende lijst worden de subtypen beschreven van de bestandsindelingen voor rasterafbeeldingen die *niet* ondersteund in Dynamic Media.

Zie ook [Niet-ondersteunde bestandsindelingen detecteren voor Dynamic Media](https://helpx.adobe.com/experience-manager/kb/detect-unsupported-assets-for-dynamic-media.html).

* PNG-bestanden met een IDAT-segmentgrootte groter dan 100 MB.
* PSB-bestanden.
* PSD-bestanden met een andere kleurruimte dan CMYK, RGB, Grijswaarden of Bitmap worden niet ondersteund. DuoTone-, Lab- en Geïndexeerde kleurruimten worden niet ondersteund.
* PSD-bestanden met een bitdiepte groter dan 16.
* TIFF-bestanden met zwevende-kommagegevens.
* TIFF-bestanden met Lab-kleurruimte.

## PDF Rasterizer-bibliotheek {#supported-pdf-rasterizer-library}

De Adobe PDF Rasterizer-bibliotheek genereert miniaturen en voorvertoningen van hoge kwaliteit voor grote en inhoudintensieve Adobe Illustrator- en PDF-bestanden. Adobe raadt u aan de PDF Rasterizer-bibliotheek te gebruiken voor het volgende:

* Inhoudsintensieve AI/PDF-bestanden die bronintensief zijn voor verwerking.
* AI/PDF-bestanden waarvoor standaard geen miniaturen worden gegenereerd.
* AI-bestanden met PMS-kleuren (Pantone Matching System).

Zie [PDF Rasterizer gebruiken](aem-pdf-rasterizer.md).

## Bibliotheek voor transformatie van afbeeldingen {#supported-image-transcoding-library}

De Adobe Imaging Transcoding Library is een oplossing voor beeldverwerking die kernfuncties voor beeldverwerking uitvoert, zoals coderen, transcoderen, resampling en vergroten/verkleinen.

De Bibliotheek van de Transcodering van het Beeld steunt JPG/JPEG, PNG (8 bits en 16 bits), GIF, BMP, TIFF/Gecomprimeerde TIFF (behalve 32 beetje TIFF- dossiers en PTIFF- dossiers), ICO, en ICN MIME types.

Zie [Afbeeldingstransformatiebibliotheek](imaging-transcoding-library.md).

## Camera Raw {#supported-camera-raw}

De Adobe Camera Raw-bibliotheek schakelt [!DNL Assets] om Raw-afbeeldingen in te voeren. Zie [Camera Raw ondersteuning](camera-raw.md).

## Documentindelingen {#supported-document-formats}

Documentindelingen die worden ondersteund voor functies voor middelenbeheer zijn als volgt:

| Indeling | Opslag | Metagegevens<br> management | Fulltext<br> extractie | Metagegevens<br> extractie | Miniatuur<br> opwekking | Subelement<br> extractie | Metagegevens<br> terugschrijven |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| [AI](managing-image-presets.md#adobe-illustrator-ai-postscript-eps-and-pdf-file-formats) | ✓ | ✓ |  | ✓ | ✓ | ✓ | ✓ |
| DOC | ✓ | ✓ | ✓ | ✓ |  |  |  |
| DOCX | ✓ | ✓ | ✓ | ✓ |  |  |  |
| ODT | ✓ | ✓ | ✓ |  |  |  |  |
| [PDF](managing-image-presets.md#adobe-illustrator-ai-postscript-eps-and-pdf-file-formats) | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| HTML | ✓ | ✓ | ✓ |  |  |  |  |
| RTF | ✓ | ✓ | ✓ |  |  |  |  |
| TXT | ✓ | ✓ | ✓ |  |  |  |  |
| XLS | ✓ | ✓ | ✓ |  |  |  |  |
| XLSX | ✓ | ✓ | ✓ | ✓ |  |  |  |
| ODS | ✓ | ✓ | ✓ |  |  |  |  |
| PPT | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |  |
| PPTX | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |  |
| ODP | ✓ | ✓ | ✓ |  |  |  |  |
| [INDD](managing-image-presets.md#indesign-indd-file-format) | ✓ | ✓ |  | ✓ | ✓ | ✓ | ✓ |
| PS | ✓ | ✓ |  |  |  |  |  |
| QXP | ✓ | ✓ |  |  |  |  |  |
| ePub | ✓ | ✓ |  | ✓ | ✓ |  |  |

Documentindelingen die worden ondersteund voor Dynamic Media-functies zijn:

| Indeling | Uploaden<br> (Invoerindeling) | Maken<br> image<br> voorinstelling<br> (Uitvoerindeling) | Voorvertoning<br> dynamic<br> uitvoering | Leveren<br> dynamic<br> uitvoering | Downloaden<br> dynamic<br> uitvoering |
|---|:---:|:---:|:---:|:---:|:---:|
| [AI](managing-image-presets.md#adobe-illustrator-ai-postscript-eps-and-pdf-file-formats) | ✓ |  |  |  |  |
| DOC |  |  |  |  |  |
| DOCX |  |  |  |  |  |
| ODT |  |  |  |  |  |
| [PDF](managing-image-presets.md#adobe-illustrator-ai-postscript-eps-and-pdf-file-formats) (Zie onderstaande opmerking) | ✓ | ✓ | ✓ | ✓ | ✓ |
| HTML |  |  |  |  |  |
| RTF |  |  |  |  |  |
| TXT |  |  |  |  |  |
| XLS |  |  |  |  |  |
| XLSX |  |  |  |  |  |
| ODS |  |  |  |  |  |
| PPT |  |  |  |  |  |
| PPTX |  |  |  |  |  |
| ODP |  |  |  |  |  |
| [INDD](managing-image-presets.md#indesign-indd-file-format) | ✓ |  |  |  |  |
| PS |  |  |  |  |  |
| QXP |  |  |  |  |  |
| ePub |  |  |  |  |  |

>[!NOTE]
>
>Voor beveiligde PDF wordt alleen Uploaden ondersteund.

Overweeg het volgende naast de bovenstaande functionaliteit:

* Als u Dynamic Media wilt gebruiken om dynamische uitvoeringen voor PDF-bestanden te genereren, raadpleegt u [Adobe Illustrator- (AI), Postscript- (EPS) en PDF-bestandsindelingen.](../assets/managing-image-presets.md#adobe-illustrator-ai-postscript-eps-and-pdf-file-formats)

* Als u Dynamic Media wilt gebruiken om dynamische uitvoeringen voor AI-bestanden voor te vertonen en te genereren, raadpleegt u [Adobe Illustrator- (AI), Postscript- (EPS) en PDF-bestandsindelingen.](../assets/managing-image-presets.md#adobe-illustrator-ai-postscript-eps-and-pdf-file-formats)

* Als u Dynamic Media wilt gebruiken om dynamische uitvoeringen voor INDD-bestanden te genereren, raadpleegt u [InDesign-bestandsindeling (INDD)](../assets/managing-image-presets.md#indesign-indd-file-format).

## Multimedia-indelingen {#supported-multimedia-formats}

| Indeling | Opslag | Metagegevensbeheer | Metagegevensextractie | Miniaturen genereren | FFMPEG-transcodering |
|:---|:---:|:---:|:---:|:---:|:---:|
| AAC | ✓ | ✓ |  | − | &#42; |
| MIDI | ✓ | ✓ |  | − | &#42; |
| 3GP | ✓ | ✓ |  | − | &#42; |
| MP3 | ✓ | ✓ | ✓ | − | &#42; |
| MPG | ✓ | ✓ |  | − | &#42; |
| OGA | ✓ | ✓ |  | − | &#42; |
| OGG | ✓ | ✓ |  | − | &#42; |
| RA | ✓ | ✓ |  | − | &#42; |
| WAV | ✓ | ✓ |  | − | &#42; |
| WMA | ✓ | ✓ |  | − | &#42; |
| DVI | ✓ | ✓ |  | &#42; | &#42; |
| FLV | ✓ | ✓ |  | &#42; | &#42; |
| M4V | ✓ | ✓ |  | &#42; | &#42; |
| MPEG | ✓ | ✓ |  | &#42; | &#42; |
| OGV | ✓ | ✓ |  | &#42; | &#42; |
| MOV | ✓ | ✓ |  | &#42; | &#42; |
| WMV | ✓ | ✓ |  | &#42; | &#42; |
| SWF | ✓ | ✓ |  |  |  |

## Invoervideo-indelingen voor Dynamic Media Transcoding {#supported-input-video-formats-for-dynamic-media-transcoding}

| Videobestandsextensie | Container | Aanbevolen videocodecs | Niet-ondersteunde video-codecs |
|---|---|---|---|
| MP4 | MPEG-4 | H264/AVC (alle profielen) |  |
| MOV, QT | Apple QuickTime | H264/AVC, Apple ProRes422 &amp; HQ, Sony XDCAM, Sony DVCAM, HDV, Panasonic DVCPro, Apple DV (DV25), Apple PhotoJPEG, Sorenson, Avid DNxHD, Avid AVR | Apple Intermediate, Apple Animation |
| FLV, F4V | Adobe Flash | H264/AVC, Flix VP6, H263, Sorenson | SWF (vectoranimatiebestanden) |
| WMV | Windows Media 9 | WMV3 (v9), WMV2 (v8), WMV1 (v7), GoToMeeting (G2M2, G2M3, G2M4) | Microsoft Screen (MSS2), Microsoft Photo Story (WVP2) |
| MPG, VOB, M2V, MP2 | MPEG-2 | MPEG-2 |  |
| M4V | Apple iTunes | H264/AVC |  |
| AVI | A/V Interleave | XVID, DIVX, HDV, MiniDV (DV25), Techsmith Camtasia, Huffyuv, Fraps, Panasonic DVCPro | Indeo3 (IV30), MJPEG, Microsoft Video 1 (MS-CRAM) |
| WebM | WebM | Google VP8 |  |
| OGV, OGG | Ogg | Theora, VP3, Dirac |  |
| MXF | MXF | Sony XDCAM, MPEG-2, MPEG-4, Panasonic DVCPro |  |
| MTS | AVCHD | H264/AVC |  |
| MKV | Matroska | H264/AVC |  |
| R3D, RM | Raw-video, rood | MJPEG 2000 |  |
| RAM, RM | RealVideo | Niet ondersteund | Real G2 (RV20), Real 8 (RV30), Real 10 (RV40) |
| FLAC | Native Flac | Vrije, verliesvrije audiocodec |  |
| MJ2 | Beweging JPEG 2000 | Motion JPEG 2000-codec |  |

## Archiefindelingen {#supported-archive-formats}

De ondersteunde archiefindelingen en de toepasbaarheid van de algemene DAM-workflows worden behandeld in de volgende tabel.

| Indeling | Opslag | Versioning | Workflow | Publiceren | Toegangsbeheer | Dynamic Media-levering |
|---|:---:|:---:|:---:|:---:|:---:|:---:|
| TGZ | ✓ | ✓ | ✓ | ✓ | ✓ |  |
| JAR | ✓ | ✓ | ✓ | ✓ | ✓ |  |
| RAR | ✓ | ✓ | ✓ | ✓ | ✓ |  |
| TAR | ✓ | ✓ | ✓ | ✓ | ✓ |  |
| ZIP **†** | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |

**†** De samengevoegde afbeelding wordt uit het PSD-bestand geëxtraheerd. Het is een afbeelding die door Adobe Photoshop wordt gegenereerd en die in het PSD-bestand wordt opgenomen. Afhankelijk van de instellingen kan de samengevoegde afbeelding wel of niet de werkelijke afbeelding zijn. De ZIP-archieven die zijn gemaakt met `Deflate64` algoritme heeft beperkte ondersteuning in AEM. Archiveer- en niet-archiefbewerkingen worden niet ondersteund. Bewerkingen zoals uploaden, bladeren en downloaden worden echter ondersteund.

## Overige ondersteunde indelingen {#other-supported-formats}

De toepasbaarheid van algemene DAM-workflows voor een aantal andere bestandsindelingen wordt in de onderstaande tabel beschreven.

| Indeling | Opslag | Versioning | Workflow | Publiceren | Toegangsbeheer | Dynamic Media-levering |
|---|:---:|:---:|:---:|:---:|:---:|:---:|
| **#** | ✓ | ✓ | ✓ | ✓ | ✓ |  |
| SVG | ✓ | ✓ | ✓ | ✓ | ✓ |  |
| CSS | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| VTT | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| XML | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| JavaScript (indien geconfigureerd met eigen leveringsdomein) |  |  |  |  |  | ✓ |

**Aantal** De andere indelingen worden in DAM ondersteund voor opslag-, versioning-, ACL-, workflow-, publicatie- en metagegevensbeheer.

## Ondersteunde MIME-typen {#supported-mime-types}

Standaard, [!DNL Experience Manager] detecteert het bestandstype met de bestandsextensie. [!DNL Experience Manager] kan het van de inhoud van de dossiers ontdekken. Selecteer [!UICONTROL Detect MIME from content] optie in [!UICONTROL Day CQ DAM Mime Type Service] in de [!DNL Experience Manager] Webconsole.

Een lijst met ondersteunde MIME-typen is beschikbaar in CRXDE Lite op `/conf/global/settings/cloudconfigs/dmscene7/jcr:content/mimeTypes`.

| Bestandsextensie | MIME-type/internet-mediatype | Standaardwaarde voor jobParam | Toegestane jobParam-waarde |
|---|---|---|---|
| Afbeelding | image/s7asset | `usmAmount=1.75&usmRadius=0.2`<br>`&usmThreshold=2&usmMonochrome=0&` | De standaardjobParam is van toepassing op alle mime-afbeeldingselementen.<ul><li>[knockoutBackgroundOptions](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-knockout-background-options.html)</li><li>[manualCropOptions](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-manual-crop-options.html)</li><li>[autoColorCropOptions](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-auto-color-crop-options.html)</li><li>[autoTransparentCropOptions](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-auto-transparent-crop-options.html)</li><li>[colorManagementOptions](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-color-management-options.html)</li><li>[autoSetCreationOptions](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-auto-set-creation-options.html)</li><li>[emailSetting](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/sting-constants/r-email-settings.html)</li><li>[xmpKeywords](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-xmp-keywords.html)</li><li>[unsharpMaskOptions](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-unsharp-mask-options.html)</li></ul> |
| 3G2 | video/3gpp2 |  | [ExcludeMasterVideoFromAVS](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-exclude-master-video-from-avs.html) |
| 3GP | video/3gpp |  | [ExcludeMasterVideoFromAVS](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-exclude-master-video-from-avs.html) |
| AAC | audio/x-aac |  |  |
| AFM | application/x-font-type1 |  |  |
| AI | application/postscript | `aiprocess=Rasterize&airesolution=150`<br>`&aicolorspace=Auto&aialpha=false` | <ul><li>[postScriptOptions](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-post-script-options.html)</li><li> [illustratorOptions](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-illustrator-options.html)</li></ul> |
| AIFF | audio/x-aiff |  |  |
| AVI | video/x-msvideo |  | [ExcludeMasterVideoFromAVS](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-exclude-master-video-from-avs.html) |
| BMP | image/bmp |  |  |
| CSS | text/css |  |  |
| DOC | application/msword |  |  |
| EPS | <ul><li>application/postscript</li><li>applicatie/eps</li><li>application/x-eps</li><li>afbeelding/eps</li><li>image/x-eps</li> |  |  |
| F4V | video/x-f4v |  | ExcludeMasterVideoFromAVS |
| FLA | application/x-shockwave-flash |  |  |
| FLV | video/x-flv |  | [ExcludeMasterVideoFromAVS](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-exclude-master-video-from-avs.html) |
| FPX | image/vnd.fpx |  |  |
| GIF | image/gif |  |  |
| ICC | application/vnd.iccprofile |  |  |
| ICM | application/vnd.iccprofile |  |  |
| INDD | application/x-indesign |  |  |
| JPEG | image/jpeg |  |  |
| JPG | image/jpeg |  |  |
| M2V | video/mpeg |  | [ExcludeMasterVideoFromAVS](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-exclude-master-video-from-avs.html) |
| M4V | video/x-m4v |  | [ExcludeMasterVideoFromAVS](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-exclude-master-video-from-avs.html) |
| MOV | video/quicktime |  | [ExcludeMasterVideoFromAVS](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-exclude-master-video-from-avs.html) |
| MP3 | audio/mpeg |  |  |
| MP4 | video/mp4 |  | [ExcludeMasterVideoFromAVS](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-exclude-master-video-from-avs.html) |
| MPEG | video/mpeg |  | [ExcludeMasterVideoFromAVS](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-exclude-master-video-from-avs.html) |
| MPG | video/mpeg |  | [ExcludeMasterVideoFromAVS](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-exclude-master-video-from-avs.html) |
| MTS | model/vnd.mts |  |  |
| OGV | video/ogg |  | [ExcludeMasterVideoFromAVS](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-exclude-master-video-from-avs.html) |
| OTF | application/x-font-otf |  |  |
| PDF | application/pdf | `pdfprocess=Rasterize&resolution=150`<br>`&colorspace=Auto&pdfbrochure=false`<br>`&keywords=false&links=false` | [pdfOptions](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-photoshop-options.html) |
| PFB | application/x-font-type1 |  |  |
| PFM | application/x-font-type1 |  |  |
| PICT | image/x-pict |  |  |
| PNG | image/png |  |  |
| PPT | application/vnd.ms-powerpoint |  |  |
| PS | application/postscript | `psprocess=Rasterize&psresolution=150`<br>`&pscolorspace=Auto&psalpha=false`<br>`&psextractsearchwords=false`<br>`&aiprocess=Rasterize&airesolution=150`<br>`&aicolorspace=Auto&aialpha=false` | <ul><li>[postScriptOptions](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-post-script-options.html)</li><li>[illustratorOptions](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-illustrator-options.html)</li></ul> |
| PSD | image/vnd.adobe.photoshop | `process=None&layerNaming=Layername`<br>`&anchor=Center&createTemplate=false`<br>`&extractText=false&extendLayers=false` | <ul><li>[PhotoshopOptions](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-photoshop-options.html)</li><li>[photoshopLayerOptions](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-photoshop-layer-options.html)</li></ul> |
| RTF | application/rtf |  |  |
| SVG | image/svg+xml |  |  |
| SWF | application/x-shockwave-flash |  |  |
| TAR | application/x-tar |  |  |
| TIF/TIFF | image/tiff |  |  |
| TTC | application/x-font-ttf |  |  |
| TTF | application/x-font-ttf |  |  |
| VOB | video/dvd |  | [ExcludeMasterVideoFromAVS](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-exclude-master-video-from-avs.html) |
| VTT | text/vtt |  |  |
| WAV | audio/x-wav |  |  |
| WEBM | video/web |  | [ExcludeMasterVideoFromAVS](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-exclude-master-video-from-avs.html) |
| WMA | audio/x-ms-wma |  |  |
| WMV | video/x-ms-wmv |  | [ExcludeMasterVideoFromAVS](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-exclude-master-video-from-avs.html) |
| XLS | application/vnd.ms-excel |  |  |
| ZIP | application/zip |  |  |

>[!MORELIKETHIS]
>
>* [Ondersteuning voor MIME-taakparameters op basis van type inschakelen/Dynamic Media Classic-upload](/help/sites-administering/scene7.md#enabling-mime-type-based-assets-scene-upload-job-parameter-support).
>* [MIME-type configureren voor ondersteuning van taakparameters voor uploaden](config-dynamic.md).

