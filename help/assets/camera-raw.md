---
title: Camera Raw ondersteuning
description: Leer hoe u Camera Raw ondersteuning inschakelt in Adobe Experience Manager Assets.
contentOwner: AG
feature: Developer Tools
role: Admin
exl-id: 637c57ae-55a6-4032-9821-b55839b3e567
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 0%

---

# Camera Raw gebruiken om afbeeldingen te verwerken {#camera-raw-support}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

U kunt de Camera Raw ondersteuning inschakelen voor het verwerken van Raw-bestandsindelingen, zoals CR2, NEF en RAF, en het renderen van afbeeldingen in de JPEG-indeling. De functionaliteit wordt ondersteund in Adobe Experience Manager Assets met de [Camera Raw pakket](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/aem630/product/assets/aem-assets-cameraraw-pkg) beschikbaar bij Softwaredistributie.

>[!NOTE]
>
>De functionaliteit ondersteunt alleen JPEG-uitvoeringen. Deze functie wordt ondersteund in Windows 64-bits, Mac OS en RHEL 7.x.

Ga als volgt te werk om Camera Raw ondersteuning in Adobe Experience Manager Assets in te schakelen:

1. Download de [Camera Raw pakket](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/aem630/product/assets/aem-assets-cameraraw-pkg) van de Distributie van de Software.

1. Ga naar `https://[aem_server]:[port]/workflow`. Open de **[!UICONTROL DAM Update Asset]** workflow.

1. Open de **[!UICONTROL Process Thumbnails]** stap.

1. Geef de volgende configuratie op in de **[!UICONTROL Thumbnails]** tab:

   * **[!UICONTROL Thumbnails]**: `140:100:false, 48:48:false, 319:319:false`
   * **[!UICONTROL Skip Mime Types]**: `skip:image/dng, skip:image/x-raw-(.*)`

   ![schil](assets/chlimage_1-334.png)

1. In de **[!UICONTROL Web Enabled Image]** tabblad, in het dialoogvenster **[!UICONTROL Skip List]** veld, specificeren `audio/mpeg, video/(.*), image/dng, image/x-raw-(.*)`.

   ![schil](assets/chlimage_1-335.png)

1. Voeg vanuit het zijpaneel de **[!UICONTROL Camera Raw/DNG Handler]** stap onder de **[!UICONTROL Thumbnail creation]** stap.

1. In de **[!UICONTROL Camera Raw/DNG Handler]** stap, voeg de volgende configuratie in toe **[!UICONTROL Arguments]** tab:

   * **[!UICONTROL Mime Types]**: `image/dng` en `image/x-raw-(.*)`
   * **[!UICONTROL Command]**:

      * `DAM_Raw_Converter ${directory}/${filename} ${directory} cq5dam.web.1280.1280.jpeg 1280 1280`
      * `DAM_Raw_Converter ${directory}/${filename} ${directory} cq5dam.thumbnail.319.319.jpeg 319 319`
      * `DAM_Raw_Converter ${directory}/${filename} ${directory} cq5dam.thumbnail.140.100.jpeg 140 100`
      * `DAM_Raw_Converter ${directory}/${filename} ${directory} cq5dam.thumbnail.48.48.jpeg 48 48`

   ![chlimage_1-336](assets/chlimage_1-336.png)

1. Klik op **[!UICONTROL Save]**.

>[!NOTE]
>
>Zorg ervoor dat de bovenstaande configuratie gelijk is aan de **[!UICONTROL Sample DAM Update Asset With Camera RAW and DNG Handling Step]** configuratie.

U kunt nu Camera Raw-bestanden importeren in [!DNL Experience Manager] Elementen. Nadat u het Camera Raw pakket hebt geïnstalleerd en de vereiste workflow hebt geconfigureerd, **[!UICONTROL Image Adjust]** wordt weergegeven in de lijst met zijvensters.

![chlimage_1-337](assets/chlimage_1-337.png)

*Afbeelding: Opties in het zijvenster*

![chlimage_1-338](assets/chlimage_1-338.png)

*Afbeelding: Met deze optie kunt u lichte bewerkingen uitvoeren op uw afbeeldingen*

Nadat u de bewerkingen hebt opgeslagen in een Camera Raw afbeelding, wordt een nieuwe vertoning weergegeven `AdjustedPreview.jpg` wordt voor de afbeelding gegenereerd. Voor andere afbeeldingstypen, behalve Camera Raw, worden de wijzigingen in alle uitvoeringen doorgevoerd.

## Beste werkwijzen, bekende problemen en beperkingen {#best-practices}

De functionaliteit heeft de volgende beperkingen:

* De functionaliteit ondersteunt alleen JPEG-uitvoeringen. Deze functie wordt ondersteund in Windows 64-bits, Mac OS en RHEL 7.x.
* Metagegevensterugname wordt niet ondersteund voor RAW- en DNG-indelingen.
* De Camera Raw bibliotheek heeft beperkingen rond de totale pixel het in een tijd kan verwerken. Op dit moment kan het maximaal 65000 pixels aan de lange zijde van een bestand of 512 MP verwerken, ongeacht de criteria die het eerst worden aangetroffen.
