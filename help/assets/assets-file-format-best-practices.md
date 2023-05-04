---
title: Aanbevolen werkwijzen voor bestandsindelingen voor elementen
description: Aanbevolen procedures voor bestandsondersteuning in [!DNL Experience Manager] Elementen.
contentOwner: AG
feature: Asset Management,Developer Tools
role: Admin
exl-id: ff739a17-188e-4779-8820-9e4d9b7031d0
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 0%

---

# Aanbevolen werkwijzen voor bestandsindelingen voor elementen {#assets-file-format-best-practices}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

[!DNL Experience Manager Assets] Biedt ondersteuning voor een groot aantal bibliotheken met bedrijfseigen bestandsindelingen en bestandsindelingen van derden, zodat gebruikers aan verschillende vereisten voor bestandsondersteuning kunnen voldoen. Tot de ondersteunde Adobe-bibliotheken behoren Adobe Camera Raw, Gibson, Adobe PDF Rasterizer en Adobe InDesign Server. Daarnaast [!DNL Assets] Biedt ondersteuning voor bibliotheken van derden, zoals ImageMagick, TwelveMonkeys, enzovoort.

Voor de ondersteunde bestandsindelingen raadpleegt u [Ondersteunde indelingen voor middelen](assets-formats.md).

## Adobe Camera Raw-bibliotheek {#adobe-camera-raw-library}

Voor optimale prestaties raadt Adobe u aan een Adobe Camera Raw-bibliotheek te gebruiken voor:

* RAW
* DNG

De Adobe Camera Raw-bibliotheek ondersteunt CMYK-kleurprofiel als invoer. De uitvoer wordt echter alleen in de kleurruimte RGB gegenereerd en uitvoer in de indeling JPEG wordt alleen ondersteund. De kleurruimte van het bronbestand (bijvoorbeeld CMYK) blijft niet behouden in de miniaturen.

Zie voor meer informatie [Camera Raw ondersteuning](camera-raw.md) in [!DNL Assets].

## Adobe PDF Rasterizer-bibliotheek {#adobe-pdf-rasterizer-library}

Voor de beste resultaten raadt Adobe u aan de Adobe PDF Rasterizer-bibliotheek te gebruiken voor de volgende bestanden:

* Zware, inhoudintensieve PDF-bestanden
* AI-bestanden met miniaturen die niet uit het vak zijn gegenereerd
* Voor AI-bestanden met SPOT-kleuren (PMS)

Miniaturen en voorvertoningen die worden gegenereerd met de Rasterizer-PDF, zijn beter van kwaliteit dan rasteruitvoer die niet in de doos wordt weergegeven. De Adobe PDF Rasterizer-bibliotheek ondersteunt geen kleurruimteconversie. Ongeacht de kleurruimte van het PDF-bronbestand genereert Adobe PDF Rasterizer alleen RGB-uitvoer.

## Adobe InDesign-server {#adobe-indesign-cc-server}

Adobe raadt u aan Adobe InDesign-server te gebruiken om Adobe InDesign-specifieke uitvoeringen, zoals IDML en HTML, te extraheren. Zie voor meer informatie [Toevoegen [!DNL Experience Manager] elementen als verwijzingen in Adobe InDesign](managing-linked-subassets.md#add-aem-assets-as-references-in-adobe-indesign).

##  Dynamic Media   {#dynamic-media}

Dynamic Media genereert en levert meerdere variaties van rijke inhoud in real-time via het wereldwijde, schaalbare en voor prestaties geoptimaliseerde netwerk. Het dient voor interactieve kijkervaringen en stroomlijnt het beheerproces voor digitale campagnes. Ga voor meer informatie over het inschakelen van Dynamic Media naar [Dynamic Media configureren](config-dynamic.md).

Dynamic Media biedt momenteel ondersteuning voor video&#39;s met maximaal 15 GB aan inhoud per bestand.

## ImageMagick-bibliotheek {#imagemagick-library}

Adobe raadt u aan de ImageMagick-bibliotheek in de volgende scenario&#39;s te gebruiken:

* Miniatuurweergaven genereren voor EPS-bestanden
* Profielgegevens behouden
* Transparantie behouden
* PSD- en PSB-bestanden verwerken

Om te weten hoe te opstelling de bibliotheek ImageMagic in [!DNL Experience Manager], zie [ImageMagick gebruiken](media-handlers.md#an-example-using-imagemagick). Voor optimaal gebruik raadpleegt u [Beste praktijken voor het Vormen ImageMagick](best-practices-for-imagemagick.md).

## Bibliotheek voor transformatie van afbeeldingen {#image-transcoding-library}

De Adobe Imaging Transcoding Library is een oplossing voor beeldverwerking die kernfuncties voor beeldverwerking uitvoert, zoals beeldcodering, transcodering, resampling, formaatwijziging, enzovoort.

De bibliotheek Imaging Transcoding ondersteunt de volgende MIME-typen:

* JPG/JPEG
* PNG (8 bits en 16 bits)
* GIF
* BMP
* TIFF/Gecomprimeerde TIFF (behalve 32 bits TIFF en PTiff).
* ICO
* ICN

Zie voor meer informatie [Afbeeldingstransformatiebibliotheek](imaging-transcoding-library.md).
