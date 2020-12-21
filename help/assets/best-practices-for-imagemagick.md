---
title: ImageMagick installeren en configureren om met AEM Assets te werken
description: Leer over de software ImageMagick, hoe te om het te installeren, opstelling de het processtap van de bevellijn, en gebruik het om, duimnagels van beelden uit te geven samen te stellen en te produceren.
contentOwner: AG
translation-type: tm+mt
source-git-commit: af5f8a24db589ecdbe28d603ab9583f11d29212c
workflow-type: tm+mt
source-wordcount: '741'
ht-degree: 1%

---


# ImageMagick installeren en configureren om te werken met AEM Assets {#install-and-configure-imagemagick-to-work-with-aem-assets}

ImageMagick is een softwareplug-in voor het maken, bewerken, samenstellen of omzetten van bitmapafbeeldingen. Afbeeldingen kunnen in verschillende indelingen (meer dan 200) worden gelezen en geschreven, waaronder PNG, JPEG, JPEG-2000, GIF, TIFF, DPX, EXR, WebP, Postscript, PDF en SVG. Met ImageMagick kunt u afbeeldingen vergroten, verkleinen, spiegelen, roteren, vervormen, schuintrekken en transformeren. U kunt ook afbeeldingskleuren aanpassen, verschillende speciale effecten toepassen of tekst, lijnen, veelhoeken, ellipsen en curven tekenen met ImageMagick.

Gebruik de Adobe Experience Manager (AEM) media-handler van de opdrachtregel om afbeeldingen te verwerken via ImageMagick. Zie [Beste werkwijzen voor bestandsindelingen Middelen](assets-file-format-best-practices.md) voor informatie over het werken met verschillende bestandsindelingen die ImageMagick gebruiken. Zie [Middelen ondersteunde indelingen](assets-formats.md) voor informatie over alle ondersteunde bestandsindelingen.

Als u grote bestanden wilt verwerken met ImageMagick, moet u rekening houden met hogere geheugenvereisten dan gebruikelijk, mogelijke wijzigingen die vereist zijn voor IM-beleid en de algemene invloed op de prestaties. De geheugenvereisten zijn afhankelijk van verschillende factoren zoals resolutie, bitdiepte, kleurprofiel en bestandsindeling. Als u van plan bent om zeer grote dossiers te verwerken gebruikend ImageMagick, behoorlijk benchmark de AEM server. Aan het eind zijn er enkele nuttige bronnen beschikbaar.

>[!NOTE]
>
>Als u AEM gebruikt op Adobe Managed Services (AMS), neemt u contact op met de klantenservice van de Adobe als u van plan bent een groot aantal grote PSD- of PSB-bestanden te verwerken. Experience Manager verwerkt PSB-bestanden met zeer hoge resolutie die groter zijn dan 30000 x 23000 pixels mogelijk niet.

## ImageMagick {#installing-imagemagick} installeren

Er zijn meerdere versies van ImageMagic-installatiebestanden beschikbaar voor verschillende besturingssystemen. Gebruik de juiste versie voor uw besturingssysteem.

1. Download de geschikte [ImageMagick-installatiebestanden](https://www.imagemagick.org/script/download.php) voor uw besturingssysteem.
1. Start het installatiebestand om ImageMagick te installeren op de schijf waarop de AEM server wordt gehost.

1. Plaats de variabele van het wegmilieu aan de installatiemap ImageMagic.
1. Om te controleren of de installatie succesvol was, voer `identify -version` bevel uit.

## De processtap {#set-up-the-command-line-process-step} van de opdrachtregel instellen

U kunt de processtap van de bevellijn voor uw bepaald gebruiksgeval plaatsen. Voer de volgende stappen uit om elke keer dat u een JPEG-afbeeldingsbestand toevoegt aan `/content/dam` op de AEM een gespiegelde afbeelding en miniaturen (140x100, 48x48, 319x319 en 1280x1280) te genereren:

1. Ga op de AEM server naar de workflowconsole (`https://[aem_server]:[Port]/workflow`) en open het **[!UICONTROL DAM Update Asset]** workflowmodel.
1. Open in het workflowmodel **[!UICONTROL DAM Update Asset]** de stap **[!UICONTROL EPS thumbnails (powered by ImageMagick)]**.
1. Voeg in **[!UICONTROL Arguments tab]** `image/jpeg` toe aan de lijst **[!UICONTROL Mime Types]**.

   ![mime_types_jpeg](assets/mime_types_jpeg.png)

1. Voer in het tekstvak **[!UICONTROL Commands]** de volgende opdracht in:

   `convert ./${filename} -flip ./${basename}.flipped.jpg`

1. Selecteer de markeringen **[!UICONTROL Delete Generated Rendition]** en **[!UICONTROL Generate Web Rendition]**.

   ![select_flags](assets/select_flags.png)

1. Geef op het tabblad **[!UICONTROL Web Enabled Image]** de details voor de vertoning op met afmetingen 1280x1280 pixels. Geef bovendien i *image/jpeg* op in het tekstvak **[!UICONTROL Mimetype]**.

   ![web_enabled_image](assets/web_enabled_image.png)

1. Tik of klik op **[!UICONTROL OK]** om de wijzigingen op te slaan.

   >[!NOTE]
   >
   >Het `convert` bevel kan niet met bepaalde versies van Vensters (bijvoorbeeld Vensters SE) lopen, omdat het met het inheemse `convert` nut strijdig is dat deel van de installatie van Vensters uitmaakt. In dit geval, vermeld de volledige weg voor het nut ImageMagick. Geef bijvoorbeeld
   >
   >`"C:\Program Files\ImageMagick-6.8.9-Q16\convert.exe" -define jpeg:size=319x319 ./${filename} -thumbnail 319x319 cq5dam.thumbnail.319.319.png`

1. Open de stap **[!UICONTROL Process Thumbnails]** en voeg het MIME-type `image/jpeg` toe onder **[!UICONTROL Skip Mime Types]**.

   ![skip_mime_types](assets/skip_mime_types.png)

1. Voeg op het tabblad **[!UICONTROL Web Enabled Image]** het MIME-type `image/jpeg` toe onder **[!UICONTROL Skip List]**. Tik of klik op **[!UICONTROL OK]** om de wijzigingen op te slaan.

   ![web_enabled](assets/web_enabled.png)

1. Sla de workflow op.
1. Als u wilt controleren of ImageMagic afbeeldingen correct kan verwerken, uploadt u een JPG-afbeelding naar AEM Assets. Controleer of er een gespiegelde afbeelding en de uitvoeringen voor zijn gegenereerd.

## Beveiligingskwetsbaarheden beperken {#mitigating-security-vulnerabilities}

Er zijn meerdere beveiligingskwetsbaarheden verbonden aan het gebruik van ImageMagick voor het verwerken van afbeeldingen. Als u bijvoorbeeld door gebruikers verzonden afbeeldingen verwerkt, bestaat het risico dat de code op afstand wordt uitgevoerd (RCE).

Daarnaast zijn verschillende plug-ins voor beeldverwerking afhankelijk van de ImageMagick-bibliotheek, waaronder, maar niet uitsluitend, PHP&#39;s fantaick, Ruby&#39;s magick en paperclip en Node.js imagemagick.

Als u ImageMagick of een beïnvloede bibliotheek gebruikt, adviseert Adobe dat u de bekende kwetsbaarheid verlicht door minstens één van de volgende taken (maar bij voorkeur allebei) uit te voeren:

1. Controleer of alle afbeeldingsbestanden beginnen met de verwachte [&quot;magische bytes&quot;](https://en.wikipedia.org/wiki/List_of_file_signatures) die overeenkomen met de afbeeldingsbestandstypen die u ondersteunt, voordat u ze naar ImageMagick stuurt voor verwerking.
1. Gebruik een beleidsdossier om de kwetsbare Codeurs onbruikbaar te maken ImageMagick. Het algemene beleid voor ImageMagick vindt u op `/etc/ImageMagick`.

>[!MORELIKETHIS]
>
>* [Aanbevolen procedures voor het verwerken van verschillende bestandsindelingen met AEM Assets](assets-file-format-best-practices.md)
>* [Opdrachtregelopties voor ImageMagick](https://www.imagemagick.org/script/command-line-options.php)
>* [Eenvoudige en geavanceerde voorbeelden van het gebruik van ImageMagick](https://www.imagemagick.org/Usage/)
>* [Afstelling van prestaties van middelen voor ImageMagick](performance-tuning-guidelines.md)
>* [Volledige lijst met bestandsindelingen die door AEM Assets worden ondersteund](assets-formats.md)
>* [Begrijp bestandsindelingen en de geheugenkosten van afbeeldingen](https://www.scantips.com/basics1d.html)

