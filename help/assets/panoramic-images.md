---
title: Panoramische afbeeldingen
seo-title: Panoramische afbeeldingen
description: Leer hoe u met panoramische afbeeldingen werkt in Dynamic Media.
seo-description: Leer hoe u met panoramische afbeeldingen werkt in Dynamic Media.
uuid: dfd7a55c-7bcc-4d62-8c3a-a73726881103
contentOwner: Rick Brough
topic-tags: dynamic-media
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
content-type: reference
discoiquuid: fc285b25-2bce-493c-87bc-5f1a8a26eb42
translation-type: tm+mt
source-git-commit: b698a1348df3ec2ab455c236422784d10cbcf7c2
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 2%

---


# Panoramische afbeeldingen {#panoramic-images}

In deze sectie wordt beschreven hoe u met de Panorama-viewer werkt om bolvormige panoramische afbeeldingen te renderen voor een indrukwekkende kijkervaring van 360 graden van een kamer, eigenschap, locatie of landschap.

Zie ook Voorinstellingen [voor viewers](managing-viewer-presets.md)beheren.

![panoramic-image2](assets/panoramic-image2.png)

## Elementen uploaden voor gebruik met de Panorama-viewer {#uploading-assets-for-use-with-the-panoramic-image-viewer}

Als u een geüpload element wilt kwalificeren als een bolvormige panorama-afbeelding die u wilt gebruiken met de Panorama-viewer, moet het element een van de volgende opties of beide hebben:

* Een hoogte-breedteverhouding van 2.

   U kunt de standaardinstelling voor de hoogte-breedteverhouding van 2 inch **[!UICONTROL CRXDE Lite]** bij het volgende overschrijven:

   `/conf/global/settings/cloudconfigs/dmscene7/jcr:content`

* Gelabeld met de trefwoorden `equirectangular`, of `spherical`en `panorama`, of `spherical` en `panoramic`. Zie [Tags](/help/sites-authoring/tags.md)gebruiken.

Both the aspect ratio and keyword criteria apply to panoramic assets for the asset details page and the **[!UICONTROL Panoramic Media]** component.

Zie [Elementen](managing-assets-touch-ui.md#uploading-assets)uploaden voor gebruik met de Panorama-viewer.

## Dynamic Media Classic configureren {#configuring-dynamic-media-classic-scene}

De Panoramische beeldviewer werkt alleen correct binnen AEM als u de voorinstellingen van de Panoramische afbeeldingsviewer synchroniseert met de specifieke metagegevens voor Dynamic Media Classic en Dynamic Media Classic, zodat de voorinstellingen van de viewer worden bijgewerkt in de JCR. Om dit te verwezenlijken, vorm Dynamische Klassieke Media op de volgende manier:

1. [Meld u voor elk bedrijfsaccount aan bij Dynamic Media Classic](https://www.adobe.com/marketing-cloud/experience-manager/scene7-login.html) .

1. Klik in de rechterbovenhoek van de pagina op **[!UICONTROL Setup > Application Setup > Publish Setup > Image Server]**.
1. Selecteer op de **[!UICONTROL Image Server Publish]** pagina in het **[!UICONTROL Publish Context]** keuzemenu boven de optie **[!UICONTROL Image Serving]**.

1. Zoek op dezelfde **[!UICONTROL Image Server Publish]** pagina de kop **[!UICONTROL Request Attributes]**.
1. Onder de **[!UICONTROL Request Attributes]** kop zoekt u **[!UICONTROL Reply Image Size Limit]**. Vergroot vervolgens in de bijbehorende **[!UICONTROL Width]** en **[!UICONTROL Height]** velden de maximaal toegestane afbeeldingsgrootte voor panoramische afbeeldingen.

   Dynamic Media Classic heeft een limiet van 25.000.000 pixels. De maximaal toegestane grootte voor afbeeldingen met een hoogte-breedteverhouding van 2:1 is 7000 x 3500. Voor standaarddesktopschermen is 4096 x 2048 pixels echter voldoende.

   >[!NOTE]
   >
   >Alleen afbeeldingen die binnen de maximaal toegestane afbeeldingsgrootte vallen, worden ondersteund. Verzoeken om afbeeldingen die groter zijn dan de maximale grootte, leveren een reactie van 403 op.

1. Ga als volgt te werk onder **[Aanvraagkenmerken]** :

   * Instellen **[!UICONTROL Request Obfuscation Mode]** op **[!UICONTROL Disabled]**.
   * Instellen **[!UICONTROL Request Locking Mode]** op **[!UICONTROL Disabled]**.

   Deze instellingen zijn nodig voor het gebruik van de **[!UICONTROL Panoramic Media]** component in AEM.

1. Tik onder aan de **[!UICONTROL Image Server Publish]** pagina links op de pagina **[!UICONTROL Save]**.

1. Tik in de rechterbenedenhoek op **[!UICONTROL Close]**.

### Problemen met de component Panoramische media oplossen {#troubleshooting-the-panoramic-media-wcm-component}

Als u een beeld in de **[!UICONTROL Panoramic Media]** component in uw WCM en componentenplaceholder deed ineenstorten, kunt u het volgende willen problemen oplossen:

* Als u een fout van 403 kent waarvoor een verbod geldt, kan deze zijn veroorzaakt door het te grote formaat van de gevraagde afbeelding. Controleer de instellingen voor Limiet *afbeeldingsgrootte voor* beantwoorden in Dynamic Media Classic (Scene7) [](#configuring-dynamic-media-classic-scene)configureren.

* Voor een *Ongeldige vergrendeling* op het element of de *Parseerfout* die op de pagina wordt weergegeven, controleert **[!UICONTROL Request Obfuscation Mode]** en **[!UICONTROL Request Locking Mode]** controleert u of deze zijn uitgeschakeld.
* Voor een bekroonde canvasfout stelt u een **[!UICONTROL Rule Set Definition File Path and Invalidate CTN]** voor de vorige aanvragen voor het afbeeldingselement in.
* Als de afbeeldingskwaliteit na een afbeeldingsaanvraag met een formaat groter dan de ondersteunde limiet erg laag wordt, controleert u of de **[!UICONTROL JPEG Encoding Attributes > Quality]** instelling niet leeg is. Een standaardinstelling voor het **[!UICONTROL Quality]** veld is `95`. U vindt de instelling op de **[!UICONTROL Image Server Publish]** pagina. Zie Dynamische media Klassiek [configureren voor toegang tot de pagina](#configuring-dynamic-media-classic-scene).

## Voorvertoning panorama-afbeeldingen weergeven {#previewing-panoramic-images}

Zie [Voorvertoning van elementen](previewing-assets.md)weergeven.

## Panorama-afbeeldingen publiceren {#publishing-panoramic-images}

Zie Elementen [](publishing-dynamicmedia-assets.md)publiceren.
