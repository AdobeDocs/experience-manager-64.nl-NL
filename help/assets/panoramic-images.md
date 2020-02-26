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
source-git-commit: e2bb2f17035e16864b1dc54f5768a99429a3dd9f

---


# Panoramische afbeeldingen {#panoramic-images}

In deze sectie wordt beschreven hoe u met de Panorama-viewer werkt om bolvormige panoramische afbeeldingen te renderen voor een indrukwekkende kijkervaring van 360 graden van een kamer, eigenschap, locatie of landschap.

Zie ook Voorinstellingen [voor viewers](managing-viewer-presets.md)beheren.

![panoramic-image2](assets/panoramic-image2.png)

## Elementen uploaden voor gebruik met de Panorama-viewer {#uploading-assets-for-use-with-the-panoramic-image-viewer}

Als u een geüpload element wilt kwalificeren als een bolvormige panorama-afbeelding die u wilt gebruiken met de Panorama-viewer, moet het element een van de volgende opties of beide hebben:

* Een hoogte-breedteverhouding van 2.

   U kunt de standaardverhouding van 2 in **[!UICONTROL CRXDE Lite]** bij het volgende met voeten treden:

   `/conf/global/settings/cloudconfigs/dmscene7/jcr:content`

* Gelabeld met de trefwoorden `equirectangular`, of `spherical`en `panorama`, of `spherical` en `panoramic`. Zie [Tags](/help/sites-authoring/tags.md)gebruiken.

Zowel zijn de aspectverhouding als de sleutelwoordcriteria op panoramische activa voor de pagina van elementdetails en de **[!UICONTROL Panoramische Media]** component van toepassing.

Zie [Elementen](managing-assets-touch-ui.md#uploading-assets)uploaden voor gebruik met de Panorama-viewer.

## Dynamic Media Classic configureren {#configuring-dynamic-media-classic-scene}

De Panoramische beeldviewer werkt alleen correct binnen AEM als u de voorinstellingen van de Panoramische afbeeldingsviewer synchroniseert met de specifieke metagegevens voor Dynamic Media Classic en Dynamic Media Classic, zodat de voorinstellingen van de viewer worden bijgewerkt in de JCR. Om dit te verwezenlijken, vorm Dynamische Klassieke Media op de volgende manier:

1. [Meld u voor elk bedrijfsaccount aan bij Dynamic Media Classic](https://www.adobe.com/marketing-cloud/experience-manager/scene7-login.html) .

1. Klik in de rechterbovenhoek van de pagina op **[!UICONTROL Setup > Application Setup > Publish Setup > Image Server]**.
1. Op de de Publish **[!UICONTROL pagina van de Server van het]** Beeld, van het **[!UICONTROL Publish drop-down menu dichtbij de bovenkant, uitgezochte]** Beeld Serving ****.

1. Voor de zelfde pagina van de Publicatie **[!UICONTROL van de Server van het]** Beeld, bepaal de plaats van de rubriek **[!UICONTROL verzoekAttributen]**.
1. Zoek onder de kop **[!UICONTROL Kenmerken]** aanvragen de optie Limiet voor afbeeldingsgrootte **[!UICONTROL beantwoorden]**. Vergroot vervolgens in de bijbehorende velden **[!UICONTROL Breedte]** en **[!UICONTROL Hoogte]** de maximaal toegestane afbeeldingsgrootte voor panoramische afbeeldingen.

   Dynamic Media Classic heeft een limiet van 25.000.000 pixels. De maximaal toegestane grootte voor afbeeldingen met een hoogte-breedteverhouding van 2:1 is 7000 x 3500. Voor standaarddesktopschermen is 4096 x 2048 pixels echter voldoende.

   >[!NOTE]
   >
   >Alleen afbeeldingen die binnen de maximaal toegestane afbeeldingsgrootte vallen, worden ondersteund. Verzoeken om afbeeldingen die groter zijn dan de maximale grootte, leveren een reactie van 403 op.

1. Ga als volgt te werk onder **Aanvraagkenmerken]** :

   * Stel de modus **** Verzoek om oprukking in op **[!UICONTROL Uitgeschakeld]**.
   * Stel de **[!UICONTROL modus]** Verzoek vergrendelen in op **[!UICONTROL Uitgeschakeld]**.
   Deze instellingen zijn nodig voor het gebruik van de **[!UICONTROL component Panoramische media]** in AEM.

1. Tik onder aan de pagina **[!UICONTROL Afbeeldingsserver publiceren]** links op **[!UICONTROL Opslaan]**.

1. Tik in de rechterbenedenhoek op **[!UICONTROL Sluiten]**.

### Problemen met de component Panoramische media oplossen {#troubleshooting-the-panoramic-media-wcm-component}

Als u een beeld in de component **[!UICONTROL Panoramische Media]** in uw WCM liet vallen en componentenplaceholder deed ineenstorten, kunt u het volgende willen problemen oplossen:

* Als u een fout van 403 kent waarvoor een verbod geldt, kan deze zijn veroorzaakt door het te grote formaat van de gevraagde afbeelding. Herzie de montages van de Grens *van de Grootte van het Beeld van het Antwoord in het* Vormen van Dynamische Klassieke Media (Scene7) [](#configuring-dynamic-media-classic-scene).

* Voor een *Ongeldige vergrendeling* op het element of een *parseringsfout* die op de pagina wordt weergegeven, schakelt u de modus **** Obfusatie aanvragen en de modus **** Aanvraag vergrendelen in om ervoor te zorgen dat deze zijn uitgeschakeld.
* Voor een bekroonde canvasfout, opstelling een Pad van het Dossier van de Definitie van de Regel en maakt CTN **** voor de vorige verzoeken om het beeldmiddel ongeldig.
* Als de afbeeldingskwaliteit na een afbeeldingsaanvraag met een formaat groter dan de ondersteunde limiet erg laag wordt, controleert u of de instelling **[!UICONTROL JPEG-coderingskenmerken > Kwaliteit]** niet leeg is. Een standaardinstelling voor het veld **[!UICONTROL Kwaliteit]** is `95`. U kunt het plaatsen op de de Publish **[!UICONTROL pagina van de Server van het]** Beeld vinden. Zie Dynamische media Klassiek [configureren voor toegang tot de pagina](#configuring-dynamic-media-classic-scene).

## Voorvertoning panorama-afbeeldingen weergeven {#previewing-panoramic-images}

Zie [Voorvertoning van elementen](previewing-assets.md)weergeven.

## Panorama-afbeeldingen publiceren {#publishing-panoramic-images}

Zie Elementen [](publishing-dynamicmedia-assets.md)publiceren.
