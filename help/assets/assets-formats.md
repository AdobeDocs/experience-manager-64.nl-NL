---
title: Ondersteunde bestandsindelingen in AEM Assets
description: Lijst met bestandsindelingen en MIME-typen die door AEM Assets worden ondersteund en de functies die voor elke indeling worden ondersteund.
contentOwner: AG
feature: Middelenbeheer, uitvoeringen
role: Business Practice,Administrator
translation-type: tm+mt
source-git-commit: 29e3cd92d6c7a4917d7ee2aa8d9963aa16581633
workflow-type: tm+mt
source-wordcount: '1644'
ht-degree: 2%

---


# Ondersteunde bestandsindelingen in AEM Assets {#assets-supported-formats}

AEM Assets ondersteunt een groot aantal bestandsindelingen en elke functie biedt verschillende ondersteuning voor verschillende MIME-typen.

Om AEM Assets te integreren met andere standaarden compatibele oplossingen voor digitaal assetmanagement (DAM) en desktopsoftware, gebruikt u Extensible Metadata Platform (XMP).

Gebruik de legenda om het steunniveau te begrijpen.

| Ondersteuningsniveau | Beschrijving |
|:---:|---|
| ✓ | Ondersteund |
| * | Ondersteund met add-onfuncties |
| - | Niet van toepassing |

## Rasterafbeeldingsindelingen {#supported-raster-image-formats}

Rasterindelingen voor afbeeldingen die worden ondersteund voor functies voor middelenbeheer zijn als volgt:

| Format | Opslag | Metagegevensbeheer | Metagegevensextractie | Miniaturen genereren | Interactief bewerken | Metagegevens terugschrijven | Inzichten |
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

**‡** De samengevoegde afbeelding wordt uit het PSD-bestand geëxtraheerd. Het is een afbeelding die door Adobe Photoshop wordt gegenereerd en in het PSD-bestand wordt opgenomen. Afhankelijk van de instellingen kan de samengevoegde afbeelding wel of niet de werkelijke afbeelding zijn.

Rasterindelingen voor afbeeldingen die worden ondersteund voor Dynamic Media-functies zijn:

| Indeling | Uploaden<br> (Invoerindeling) | Afbeelding<br> maken<br> voorinstelling<br> (uitvoerindeling) | Voorvertoning<br> dynamische uitvoering<br> | Leveren<br> dynamische<br> uitvoering | Download<br> dynamic<br> uitvoering |
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

**‡** De samengevoegde afbeelding wordt uit het PSD-bestand geëxtraheerd. Het is een afbeelding die door Adobe Photoshop wordt gegenereerd en in het PSD-bestand wordt opgenomen. Afhankelijk van de instellingen kan de samengevoegde afbeelding wel of niet de werkelijke afbeelding zijn.

Naast bovenstaande informatie, moet u rekening houden met het volgende:

* De ondersteuning voor EPS-bestanden is alleen van toepassing op rasterafbeeldingen. Miniatuurgeneratie voor EPS-vectorafbeeldingen wordt bijvoorbeeld niet standaard ondersteund. Om steun toe te voegen, [vorm ImageMagick](best-practices-for-imagemagick.md). Om derdehulpmiddelen te integreren om extra mogelijkheden toe te laten, zie [Op de lijn gebaseerde de manager van Media](media-handlers.md#command-line-based-media-handler).

* Metagegevensterugschrijving werkt voor PSB- dossierformaat wanneer het aan `NComm` manager wordt toegevoegd.

* Als u Dynamic Media wilt gebruiken om dynamische uitvoeringen voor EPS-bestanden voor te vertonen en te genereren, raadpleegt u [Adobe Illustrator (AI), Postscript (EPS) en PDF-bestandsindelingen.](../assets/managing-image-presets.md#adobe-illustrator-ai-postscript-eps-and-pdf-file-formats)

* Voor EPS-bestanden wordt terugschrijven van metagegevens ondersteund in versie 3.0 of hoger van de PostScript Document Structuring Convention (PS-Adobe).

## Niet-ondersteunde rasterafbeeldingsindelingen in Dynamic Media {#unsupported-image-formats-dynamic-media}

In de volgende lijst worden de subtypen van rasterafbeeldingsbestandsindelingen beschreven die *niet* worden ondersteund in Dynamic Media.

Zie ook [Niet-ondersteunde bestandsindelingen detecteren voor Dynamic Media](https://helpx.adobe.com/experience-manager/kb/detect-unsupported-assets-for-dynamic-media.html).

* PNG-bestanden met een IDAT-segmentgrootte groter dan 100 MB.
* PSB-bestanden.
* PSD-bestanden met een andere kleurruimte dan CMYK, RGB, Grijswaarden of Bitmap worden niet ondersteund. DuoTone-, Lab- en Geïndexeerde kleurruimten worden niet ondersteund.
* PSD-bestanden met een bitdiepte groter dan 16.
* TIFF-bestanden met zwevende-kommagegevens.
* TIFF-bestanden met LAB-kleurruimte.

## Bibliotheek van PDF Rasterizer {#supported-pdf-rasterizer-library}

De Adobe PDF Rasterizer-bibliotheek genereert miniaturen en voorvertoningen van hoge kwaliteit voor grote en inhoudintensieve Adobe Illustrator- en PDF-bestanden. Adobe raadt u aan de PDF Rasterizer-bibliotheek te gebruiken voor het volgende:

* Inhoudsintensieve AI/PDF-bestanden die bronintensief zijn voor verwerking.
* AI/PDF-bestanden waarvoor standaard geen miniaturen worden gegenereerd.
* AI-bestanden met Pantone Matching System (PMS)-kleuren.

Zie [Werken met PDF Rasterizer](aem-pdf-rasterizer.md).

## Bibliotheek {#supported-image-transcoding-library} voor transformatie van afbeeldingen

De Adobe Imaging Transcoding Library is een oplossing voor beeldverwerking die kernfuncties voor beeldverwerking uitvoert, zoals coderen, transcoderen, resampling en vergroten/verkleinen.

De bibliotheek voor grafische transformatie ondersteunt de volgende MIME-typen: JPG/JPEG, PNG (8-bits en 16-bits), GIF, BMP, TIFF/Gecomprimeerde TIFF (behalve 32-bits TIFF-bestanden en PTIFF-bestanden), ICO en ICN.

Zie [Bibliotheek voor beeldtransformatie](imaging-transcoding-library.md).

## Camera Raw {#supported-camera-raw}

Met de Adobe Camera Raw-bibliotheek kan AEM Assets onbewerkte afbeeldingen opnemen. Zie [Camera Raw ondersteuning](camera-raw.md).

## Documentindelingen {#supported-document-formats}

Documentindelingen die worden ondersteund voor functies voor middelenbeheer zijn als volgt:

| Indeling | Opslag | Beheer van metagegevens<br> | Fulltext<br> extractie | Metagegevens<br> extractie | Miniatuur<br> genereren | Subelement<br> extractie | Metagegevens<br> terugschrijven |
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
| EPUB | ✓ | ✓ |  | ✓ | ✓ |  |  |

Documentindelingen die worden ondersteund voor Dynamic Media-functies zijn:

| Indeling | Uploaden<br> (Invoerindeling) | Afbeelding<br> maken<br> voorinstelling<br> (uitvoerindeling) | Voorvertoning<br> dynamische uitvoering<br> | Leveren<br> dynamische<br> uitvoering | Download<br> dynamic<br> uitvoering |
|---|:---:|:---:|:---:|:---:|:---:|
| [AI](managing-image-presets.md#adobe-illustrator-ai-postscript-eps-and-pdf-file-formats) | ✓ |  |  |  |  |
| DOC |  |  |  |  |  |
| DOCX |  |  |  |  |  |
| ODT |  |  |  |  |  |
| [PDF](managing-image-presets.md#adobe-illustrator-ai-postscript-eps-and-pdf-file-formats) | ✓ | ✓ | ✓ | ✓ | ✓ |
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
| EPUB |  |  |  |  |  |

Overweeg het volgende naast de bovenstaande functionaliteit:

* Als u Dynamic Media wilt gebruiken om dynamische uitvoeringen voor PDF-bestanden te genereren, raadpleegt u [Adobe Illustrator (AI), Postscript (EPS) en PDF-bestandsindelingen.](../assets/managing-image-presets.md#adobe-illustrator-ai-postscript-eps-and-pdf-file-formats)

* Als u Dynamic Media wilt gebruiken om dynamische uitvoeringen voor AI-bestanden voor te vertonen en te genereren, raadpleegt u [Adobe Illustrator (AI), Postscript (EPS) en PDF-bestandsindelingen.](../assets/managing-image-presets.md#adobe-illustrator-ai-postscript-eps-and-pdf-file-formats)

* Als u Dynamic Media wilt gebruiken om dynamische uitvoeringen voor INDD-bestanden te genereren, raadpleegt u [InDesign (INDD)-bestandsindeling](../assets/managing-image-presets.md#indesign-indd-file-format).

## Multimedia-indelingen {#supported-multimedia-formats}

| Indeling | Opslag | Metagegevensbeheer | Metagegevensextractie | Miniaturen genereren | FFMPEG-transcodering |
|:---|:---:|:---:|:---:|:---:|:---:|
| AAC | ✓ | ✓ |  | - | * |
| MIDI | ✓ | ✓ |  | - | * |
| 3GP | ✓ | ✓ |  | - | * |
| MP3 | ✓ | ✓ | ✓ | - | * |
| MPG | ✓ | ✓ |  | - | * |
| OGA | ✓ | ✓ |  | - | * |
| OGG | ✓ | ✓ |  | - | * |
| RA | ✓ | ✓ |  | - | * |
| WAV | ✓ | ✓ |  | - | * |
| WMA | ✓ | ✓ |  | - | * |
| DVI | ✓ | ✓ |  | * | * |
| FLV | ✓ | ✓ |  | * | * |
| M4V | ✓ | ✓ |  | * | * |
| MPEG | ✓ | ✓ |  | * | * |
| OGV | ✓ | ✓ |  | * | * |
| MOV | ✓ | ✓ |  | * | * |
| WMV | ✓ | ✓ |  | * | * |
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

**†** De samengevoegde afbeelding wordt uit het PSD-bestand geëxtraheerd. Het is een afbeelding die door Adobe Photoshop wordt gegenereerd en in het PSD-bestand wordt opgenomen. Afhankelijk van de instellingen kan de samengevoegde afbeelding wel of niet de werkelijke afbeelding zijn. De ZIP-archieven die zijn gemaakt met het algoritme `Deflate64` bieden beperkte AEM ondersteuning. Archiveer- en niet-archiefbewerkingen worden niet ondersteund. Bewerkingen zoals uploaden, bladeren en downloaden worden echter ondersteund.

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

**#** De andere formaten worden gesteund in DAM voor opslag, versioning, ACL, werkschema, het publiceren, en meta-gegevensbeheer.

## Ondersteunde MIME-typen {#supported-mime-types}

Standaard wordt het bestandstype AEM de bestandsextensie gebruikt. AEM kan het van de inhoud van de dossiers ontdekken. Voor laatstgenoemde, selecteer [!UICONTROL Detect MIME from content] optie in [!UICONTROL Day CQ DAM Mime Type Service] in de Console van het AEM Web.

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
| RTF | application/x-font-ttf |  |  |
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
>* [Schakel op MIME-type gebaseerde assets/Dynamic Media Classic upload job parameterondersteuning](/help/sites-administering/scene7.md#enabling-mime-type-based-assets-scene-upload-job-parameter-support) in.
>* [Configureer MIME op type gebaseerd voor ondersteuning](config-dynamic.md) voor uploadtaakparameters.

