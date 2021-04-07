---
title: Aanbevolen werkwijzen voor bestandsindelingen voor elementen
description: Aanbevolen procedures voor bestandsondersteuning in AEM Assets.
contentOwner: AG
feature: Asset Management, ontwikkelprogramma's
role: Administrator
exl-id: ff739a17-188e-4779-8820-9e4d9b7031d0
translation-type: tm+mt
source-git-commit: bd94d3949f0117aa3e1c9f0e84f7293a5d6b03b4
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 0%

---

# Best practices voor bestandsindeling van middelen {#assets-file-format-best-practices}

AEM Assets biedt ondersteuning voor een groot aantal bibliotheken met bedrijfseigen bestandsindelingen en bestandsindelingen van derden, zodat gebruikers aan verschillende vereisten voor bestandsondersteuning kunnen voldoen. Tot de ondersteunde Adobe-bibliotheken behoren Adobe Camera Raw, Gibson, Adobe PDF Rasterizer en Adobe InDesign Server. Bovendien biedt AEM Assets ondersteuning voor bibliotheken van derden, zoals ImageMagick, TwelveMonkeys, enzovoort.

Zie [Ondersteunde indelingen voor elementen](assets-formats.md) voor de ondersteunde bestandsindelingen.

## Adobe Camera Raw-bibliotheek {#adobe-camera-raw-library}

Voor optimale prestaties raadt Adobe u aan een Adobe Camera Raw-bibliotheek te gebruiken voor:

* RAW
* DNG

De Adobe Camera Raw-bibliotheek ondersteunt CMYK-kleurprofiel als invoer. De uitvoer wordt echter gegenereerd in RGB-kleurruimte en alleen uitvoer in JPEG-indeling wordt ondersteund. De kleurruimte van het bronbestand (bijvoorbeeld CMYK) blijft niet behouden in de miniaturen.

Zie [Camera Raw ondersteuning](camera-raw.md) in AEM Assets voor meer informatie.

## Adobe PDF Rasterizer-bibliotheek {#adobe-pdf-rasterizer-library}

Voor de beste resultaten raadt Adobe u aan de Adobe PDF Rasterizer-bibliotheek te gebruiken voor de volgende bestanden:

* Zware, inhoudintensieve PDF-bestanden
* AI-bestanden met miniaturen die niet uit het vak zijn gegenereerd
* Voor AI-bestanden met SPOT-kleuren (PMS)

Miniaturen en voorvertoningen die worden gegenereerd met PDF Rasterizer, zijn beter van kwaliteit dan rasteruitvoer die niet in de doos wordt weergegeven. De Adobe PDF Rasterizer-bibliotheek ondersteunt geen kleurruimteconversie. Ongeacht de kleurruimte van het PDF-bronbestand genereert Adobe PDF Rasterizer alleen RGB-uitvoer.

## Adobe InDesign-server {#adobe-indesign-cc-server}

Adobe raadt u aan Adobe InDesign-server te gebruiken voor het extraheren van Adobe InDesign-specifieke uitvoeringen, zoals IDML en HTML. Zie [AEM elementen toevoegen als verwijzingen in Adobe InDesign](managing-linked-subassets.md#add-aem-assets-as-references-in-adobe-indesign) voor meer informatie.

##  Dynamic Media {#dynamic-media}

Dynamic Media genereert en levert meerdere variaties van rijke inhoud in real-time via het wereldwijde, schaalbare en voor prestaties geoptimaliseerde netwerk. Het dient voor interactieve kijkervaringen en stroomlijnt het beheerproces voor digitale campagnes. Zie [Dynamic Media configureren](config-dynamic.md) voor meer informatie over het inschakelen van Dynamic Media.

Dynamic Media biedt momenteel ondersteuning voor video&#39;s met maximaal 15 GB aan inhoud per bestand.

## ImageMagick-bibliotheek {#imagemagick-library}

Adobe raadt u aan de ImageMagick-bibliotheek in de volgende scenario&#39;s te gebruiken:

* Miniatuurweergaven genereren voor EPS-bestanden
* Profielgegevens behouden
* Transparantie behouden
* PSD- en PSB-bestanden verwerken

Om te weten hoe te opstelling de bibliotheek ImageMagic in AEM, zie [Gebruikend ImageMagick](media-handlers.md#an-example-using-imagemagick). Voor optimaal gebruik, zie [Beste praktijken voor het Vormen ImageMagick](best-practices-for-imagemagick.md).

## Bibliotheek {#image-transcoding-library} voor transformatie van afbeeldingen

De Adobe Imaging Transcoding Library is een oplossing voor beeldverwerking die kernfuncties voor beeldverwerking uitvoert, zoals beeldcodering, transcodering, resampling, formaatwijziging, enzovoort.

De bibliotheek Imaging Transcoding ondersteunt de volgende MIME-typen:

* JPG/JPEG
* PNG (8 bits en 16 bits)
* GIF
* BMP
* TIFF/gecomprimeerde TIFF (behalve 32 bits TIFF en PTiff).
* ICO
* ICN

Zie [Bibliotheek van transformatie van afbeeldingen](imaging-transcoding-library.md) voor meer informatie.
