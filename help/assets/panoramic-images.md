---
title: Panoramische afbeeldingen
description: Leer hoe u in Dynamic Media met panoramische afbeeldingen werkt.
contentOwner: Rick Brough
topic-tags: dynamic-media
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
content-type: reference
exl-id: 51150d51-865e-4b8e-9990-ca755e4c7778
feature: Panoramic Images
role: User
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 2%

---

# Panoramische afbeeldingen {#panoramic-images}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

In deze sectie wordt beschreven hoe u met de Panorama-viewer werkt om bolvormige panoramische afbeeldingen te renderen voor een indrukwekkende kijkervaring van 360 graden van een kamer, eigenschap, locatie of landschap.

Zie ook [Viewer-voorinstellingen beheren](managing-viewer-presets.md).

![panoramic-image2](assets/panoramic-image2.png)

## Elementen uploaden voor gebruik met de Panorama-viewer {#uploading-assets-for-use-with-the-panoramic-image-viewer}

Als u een geüpload element wilt kwalificeren als een bolvormige panorama-afbeelding die u wilt gebruiken met de Panorama-viewer, moet het element een van de volgende opties of beide hebben:

* Een hoogte-breedteverhouding van 2.

   U kunt de instelling voor de standaardverhouding van 2 inch overschrijven **[!UICONTROL CRXDE Lite]** op het volgende adres:

   `/conf/global/settings/cloudconfigs/dmscene7/jcr:content`

* Gecodeerd met de trefwoorden `equirectangular`, of `spherical`en `panorama`, of `spherical` en `panoramic`. Zie [Tags gebruiken](/help/sites-authoring/tags.md).

Zowel de hoogte-breedteverhouding als de trefwoordcriteria gelden voor panoramische elementen voor de pagina met de elementdetails als voor de **[!UICONTROL Panoramic Media]** component.

Als u elementen wilt uploaden voor gebruik met de Panorama-viewer, raadpleegt u [Elementen uploaden](managing-assets-touch-ui.md#uploading-assets).

## Dynamic Media Classic configureren {#configuring-dynamic-media-classic-scene}

De Panorama-viewer werkt alleen correct binnen AEM als u de voorinstellingen voor de Panoramische afbeeldingsviewer synchroniseert met specifieke metagegevens voor Dynamic Media Classic en Dynamic Media Classic, zodat de voorinstellingen van de viewer worden bijgewerkt in het JCR. Hiertoe configureert u Dynamic Media Classic op de volgende manier:

1. [Aanmelden bij uw Dynamic Media Classic-bureaubladtoepassing](https://experienceleague.adobe.com/docs/dynamic-media-classic/using/intro/dynamic-media-classic-desktop-app.html#system-requirements-dmc-app) voor elke bedrijfsrekening.

1. Klik in de rechterbovenhoek van de pagina op **[!UICONTROL Setup > Application Setup > Publish Setup > Image Server]**.
1. Op de **[!UICONTROL Image Server Publish]** pagina, van de **[!UICONTROL Publish Context]** vervolgkeuzemenu boven, selecteert u **[!UICONTROL Image Serving]**.

1. Op dezelfde **[!UICONTROL Image Server Publish]** pagina, de kop zoeken **[!UICONTROL Request Attributes]**.
1. Onder de **[!UICONTROL Request Attributes]** kop, zoeken **[!UICONTROL Reply Image Size Limit]**. Vervolgens, in de bijbehorende **[!UICONTROL Width]** en **[!UICONTROL Height]** vergroot de maximaal toegestane afbeeldingsgrootte voor panoramische afbeeldingen.

   Dynamic Media Classic heeft een limiet van 25.000.000 pixels. De maximaal toegestane grootte voor afbeeldingen met een hoogte-breedteverhouding van 2:1 is 7000 x 3500. Voor standaarddesktopschermen is 4096 x 2048 pixels echter voldoende.

   >[!NOTE]
   >
   >Alleen afbeeldingen die binnen de maximaal toegestane afbeeldingsgrootte vallen, worden ondersteund. Verzoeken om afbeeldingen die groter zijn dan de maximale grootte, leveren een reactie van 403 op.

1. Onder de **[Aanvraagkenmerken]** Ga als volgt te werk:

   * Set **[!UICONTROL Request Obfuscation Mode]** tot **[!UICONTROL Disabled]**.
   * Set **[!UICONTROL Request Locking Mode]** tot **[!UICONTROL Disabled]**.

   Deze instellingen zijn nodig voor het gebruik van de **[!UICONTROL Panoramic Media]** in AEM.

1. Onder aan het dialoogvenster **[!UICONTROL Image Server Publish]** pagina, aan de linkerkant tikken **[!UICONTROL Save]**.

1. Tik in de rechterbenedenhoek op **[!UICONTROL Close]**.

### Problemen met de component Panoramische media oplossen {#troubleshooting-the-panoramic-media-wcm-component}

Als u een afbeelding in de **[!UICONTROL Panoramic Media]** in uw WCM en samengevouwen componentenplaceholder, kunt u het volgende willen problemen oplossen:

* Als u een fout van 403 kent waarvoor een verbod geldt, kan deze zijn veroorzaakt door het te grote formaat van de gevraagde afbeelding. Controleer de *Limiet voor afbeeldingsgrootte beantwoorden* instellingen in [Dynamic Media Classic configureren](#configuring-dynamic-media-classic-scene).

* Voor een *Ongeldige vergrendeling* op het actief of *Parseringsfout* weergegeven op de pagina, controle **[!UICONTROL Request Obfuscation Mode]** en **[!UICONTROL Request Locking Mode]** om ervoor te zorgen dat ze uitgeschakeld zijn.
* Voor een bekronde canvasfout stelt u een **[!UICONTROL Rule Set Definition File Path and Invalidate CTN]** voor de vorige aanvragen voor het afbeeldingselement.
* Als de afbeeldingskwaliteit zeer laag wordt nadat een afbeeldingsaanvraag is ingediend en de afbeelding groter is dan de ondersteunde limiet, controleert u of de **[!UICONTROL JPEG Encoding Attributes > Quality]** instelling is niet leeg. Een standaardinstelling voor de **[!UICONTROL Quality]** field is `95`. U kunt de instelling vinden op het tabblad **[!UICONTROL Image Server Publish]** pagina. Ga voor toegang tot de pagina naar [Dynamic Media Classic configureren](#configuring-dynamic-media-classic-scene).

## Voorvertoning panorama-afbeeldingen weergeven {#previewing-panoramic-images}

Zie [Elementen voorvertonen](previewing-assets.md).

## Panorama-afbeeldingen publiceren {#publishing-panoramic-images}

Zie [Middelen publiceren](publishing-dynamicmedia-assets.md).
