---
title: Panoramische afbeeldingen
Description: Learn how to work with panoramic images in Dynamic Media.
contentOwner: Rick Brough
topic-tags: dynamic-media
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
content-type: reference
exl-id: 51150d51-865e-4b8e-9990-ca755e4c7778
feature: Panoramische afbeeldingen
role: Business Practitioner
translation-type: tm+mt
source-git-commit: f9faa357f8de92d205f1a297767ba4176cfd1e10
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 2%

---

# Panoramische afbeeldingen {#panoramic-images}

In deze sectie wordt beschreven hoe u met de Panorama-viewer werkt om bolvormige panoramische afbeeldingen te renderen voor een indrukwekkende kijkervaring van 360 graden van een kamer, eigenschap, locatie of landschap.

Zie ook [Viewer-voorinstellingen beheren](managing-viewer-presets.md).

![panoramisch beeld2](assets/panoramic-image2.png)

## Elementen uploaden voor gebruik met de Panorama-viewer {#uploading-assets-for-use-with-the-panoramic-image-viewer}

Als u een geüpload element wilt kwalificeren als een bolvormige panorama-afbeelding die u wilt gebruiken met de Panorama-viewer, moet het element een van de volgende opties of beide hebben:

* Een hoogte-breedteverhouding van 2.

   U kunt de standaardverhouding van 2 in **[!UICONTROL CRXDE Lite]** bij het volgende met voeten treden:

   `/conf/global/settings/cloudconfigs/dmscene7/jcr:content`

* Gelabeld met de trefwoorden `equirectangular` of `spherical`en `panorama`, of `spherical` en `panoramic`. Zie [Tags gebruiken](/help/sites-authoring/tags.md).

Zowel zijn de aspectverhouding als de sleutelwoordcriteria op panoramische activa voor de pagina van elementdetails en **[!UICONTROL Panoramic Media]** component van toepassing.

Zie [Elementen uploaden](managing-assets-touch-ui.md#uploading-assets) om elementen te uploaden voor gebruik met de Panoramische Image Viewer.

## Dynamic Media Classic {#configuring-dynamic-media-classic-scene} configureren

De Panorama-viewer werkt alleen correct binnen AEM als u de voorinstellingen voor de Panoramische afbeeldingsviewer synchroniseert met klassieke metagegevens van Dynamic Media Classic en Dynamic Media, zodat de voorinstellingen van de viewer worden bijgewerkt in de JCR. Hiertoe configureert u Dynamic Media Classic als volgt:

1. [Meld u voor elk bedrijfsaccount aan bij uw Dynamic Media Classic-](https://experienceleague.adobe.com/docs/dynamic-media-classic/using/intro/dynamic-media-classic-desktop-app.html?lang=en#system-requirements-dmc-app) bureaubladtoepassing.

1. Klik in de rechterbovenhoek van de pagina op **[!UICONTROL Setup > Application Setup > Publish Setup > Image Server]**.
1. Selecteer **[!UICONTROL Image Serving]** in het vervolgkeuzemenu **[!UICONTROL Image Server Publish]** boven op de pagina **[!UICONTROL Publish Context]**.

1. Zoek op dezelfde **[!UICONTROL Image Server Publish]**-pagina de kop **[!UICONTROL Request Attributes]**.
1. Zoek onder de kop **[!UICONTROL Request Attributes]** **[!UICONTROL Reply Image Size Limit]**. Vergroot vervolgens in de bijbehorende velden **[!UICONTROL Width]** en **[!UICONTROL Height]** de maximaal toegestane afbeeldingsgrootte voor panoramische afbeeldingen.

   Dynamic Media Classic heeft een limiet van 25.000.000 pixels. De maximaal toegestane grootte voor afbeeldingen met een hoogte-breedteverhouding van 2:1 is 7000 x 3500. Voor standaarddesktopschermen is 4096 x 2048 pixels echter voldoende.

   >[!NOTE]
   >
   >Alleen afbeeldingen die binnen de maximaal toegestane afbeeldingsgrootte vallen, worden ondersteund. Verzoeken om afbeeldingen die groter zijn dan de maximale grootte, leveren een reactie van 403 op.

1. Onder **[Request Attributes]** rubriek, doe het volgende:

   * Stel **[!UICONTROL Request Obfuscation Mode]** in op **[!UICONTROL Disabled]**.
   * Stel **[!UICONTROL Request Locking Mode]** in op **[!UICONTROL Disabled]**.

   Deze instellingen zijn nodig voor het gebruik van de **[!UICONTROL Panoramic Media]**-component in AEM.

1. Tik onder aan de pagina **[!UICONTROL Image Server Publish]** links op **[!UICONTROL Save]**.

1. Tik in de rechterbenedenhoek op **[!UICONTROL Close]**.

### Problemen met de component Panoramische media {#troubleshooting-the-panoramic-media-wcm-component} oplossen

Als u een beeld in de **[!UICONTROL Panoramic Media]** component in uw WCM en componentenplaceholder samengevouwen hebt gelaten vallen, kunt u het volgende willen problemen oplossen:

* Als u een fout van 403 kent waarvoor een verbod geldt, kan deze zijn veroorzaakt door het te grote formaat van de gevraagde afbeelding. Controleer de *Limiet voor afbeeldingsgrootte beantwoorden*-instellingen in [Dynamic Media Classic configureren](#configuring-dynamic-media-classic-scene).

* Voor een *Ongeldige vergrendeling* op het element of *Parseerfout* die op de pagina wordt weergegeven, schakelt u **[!UICONTROL Request Obfuscation Mode]** en **[!UICONTROL Request Locking Mode]** in om ervoor te zorgen dat deze zijn uitgeschakeld.
* Voor een bekroonde canvasfout stelt u een **[!UICONTROL Rule Set Definition File Path and Invalidate CTN]** in voor de vorige aanvragen voor het afbeeldingselement.
* Als de afbeeldingskwaliteit na een afbeeldingsaanvraag met een formaat groter dan de ondersteunde limiet erg laag wordt, controleert u of de instelling **[!UICONTROL JPEG Encoding Attributes > Quality]** niet leeg is. Een typische instelling voor het veld **[!UICONTROL Quality]** is `95`. U kunt de instelling vinden op de pagina **[!UICONTROL Image Server Publish]**. Zie [Dynamic Media Classic configureren](#configuring-dynamic-media-classic-scene) voor toegang tot de pagina.

## Voorvertoning van panorama-afbeeldingen {#previewing-panoramic-images}

Zie [Elementen voorvertonen](previewing-assets.md).

## Panorama-afbeeldingen {#publishing-panoramic-images} publiceren

Zie [Elementen publiceren](publishing-dynamicmedia-assets.md).
