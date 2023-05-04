---
title: De Dynamic Media Video- of Image-viewer insluiten op een webpagina
seo-title: Embedding the Dynamic Media Video or Image viewer on a web page
description: Leer hoe u Dynamic Media-video of -afbeeldingen op een webpagina insluit
seo-description: Learn how to embed Dynamic media video or images on a web page
uuid: 6f786521-eb6c-4c80-8c15-9bf97b56818f
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
discoiquuid: 4ae76d8a-208f-4099-9f17-a94df424685e
exl-id: bff564a8-e982-4e1a-a9b5-05e44e3e4d46
feature: Components
role: User
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 19%

---

# De Dynamic Media Video- of Image-viewer insluiten op een webpagina {#embedding-the-video-or-image-viewer-on-a-web-page}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Gebruik de functie **[!UICONTROL Embed Code]** wanneer u de video wilt afspelen of een asset wilt bekijken die op een webpagina is ingesloten. U kopieert de insluitcode naar het klembord, zodat u deze op uw webpagina&#39;s kunt plakken. Het bewerken van de code is niet toegestaan in het dialoogvenster **[!UICONTROL Embed Code]**.

U sluit alleen URL&#39;s in als u _niet_ gebruiken [!DNL Experience Manager] als uw WCM. Als u [!DNL Experience Manager] als uw WCM, [u voegt de elementen rechtstreeks op de pagina toe.](adding-dynamic-media-assets-to-pages.md)

Zie [Het verbinden van URLs aan uw Toepassing van het Web.](linking-urls-to-yourwebapplication.md)

Zie [Geoptimaliseerde afbeeldingen voor een responsieve site leveren.](responsive-site.md)

>[!NOTE]
>
>De insluitcode kan pas worden gekopieerd nadat u het geselecteerde element hebt gepubliceerd. Daarnaast moet u ook de voorinstelling van de viewer of de voorinstelling van de afbeelding publiceren.
>
>Zie [Middelen publiceren](publishing-dynamicmedia-assets.md).
>
>Zie [Voorinstellingen van viewer publiceren](managing-viewer-presets.md#publishing-viewer-presets).
>
>Zie [Voorinstellingen voor afbeeldingen publiceren](managing-image-presets.md#publishing-image-presets).

**De Dynamic Media Video- of Image-viewer insluiten op een webpagina**:

1. Ga naar de *gepubliceerd* video of afbeeldingselement waarvan u de insluitcode wilt kopiëren.

   Onthoud dat de insluitcode alleen beschikbaar is om te kopiëren *nadat* u de assets eerst hebt *gepubliceerd*. Bovendien moet de viewervoorinstelling of afbeeldingsvoorinstelling ook worden gepubliceerd.

   Zie [Middelen publiceren.](publishing-dynamicmedia-assets.md)

   Zie [Voorinstellingen van viewer publiceren](managing-viewer-presets.md#publishing-viewer-presets).

   Zie [Voorinstellingen voor afbeeldingen publiceren](managing-image-presets.md#publishing-image-presets).

1. Selecteer het vervolgkeuzemenu in de linkertrack en tik op **[!UICONTROL Viewers]**.
1. Tik in de linkertrack op de naam van een viewervoorinstelling. De viewervoorinstelling wordt toegepast op het element.
1. Tik op **[!UICONTROL Embed]**.
1. In de **[!UICONTROL Embed Code]** , kopieert u de volledige code naar het klembord en tikt u vervolgens op **[!UICONTROL Close]**.
1. Plak de insluitcode in uw webpagina&#39;s.

## HTTP/2 gebruiken om uw Dynamic Media-middelen te leveren {#using-http-to-deliver-your-dynamic-media-assets}

HTTP/2 is het nieuwe, bijgewerkte webprotocol dat de manier verbetert waarop browsers en servers communiceren. Het zorgt voor een snellere overdracht van informatie en vermindert de hoeveelheid verwerkingskracht die nodig is. De levering van Dynamic Media-middelen kan nu plaatsvinden via HTTP/2, wat betere responstijd en laadtijden biedt.

Zie [HTTP2 Levering van inhoud](http2.md) voor volledige informatie over hoe u aan de slag gaat met HTTP/2 met uw Dynamic Media-account.
