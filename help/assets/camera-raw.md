---
title: Camera Raw-ondersteuning
description: Leer hoe u ondersteuning voor Camera Raw inschakelt in Adobe Experience Manager-middelen.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 69976917f19a695908f1d7e5276d969587671761
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 0%

---


# Ondersteuning voor het verwerken van afbeeldingen met Camera Raw {#camera-raw-support}

U kunt Camera Raw-ondersteuning inschakelen voor het verwerken van Raw-bestandsindelingen, zoals CR2, NEF en RAF, en voor het renderen van afbeeldingen in de JPEG-indeling. De functionaliteit wordt ondersteund in Adobe Experience Manager Assets met behulp van het [Camera Raw-pakket](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/aem630/product/assets/aem-assets-cameraraw-pkg) dat beschikbaar is via Package Share of via [Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/aem630/product/assets/aem-assets-cameraraw-pkg).

>[!NOTE]
>
>De functionaliteit ondersteunt alleen JPEG-uitvoeringen. Deze functie wordt ondersteund in Windows 64-bits, Mac OS en RHEL 7.x.

Voer de volgende stappen uit om Camera Raw-ondersteuning in Adobe Experience Manager-middelen in te schakelen:

1. Download het [Camera Raw-pakket](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/aem630/product/assets/aem-assets-cameraraw-pkg) van het Delen van het pakket of van de [Softwaredistributie](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/aem630/product/assets/aem-assets-cameraraw-pkg).

1. Ga naar `https://[aem_server]:[port]/workflow`. Open de **[!UICONTROL DAM Update Asset]** workflow.

1. Open de **[!UICONTROL Process Thumbnails]** stap.

1. Geef de volgende configuratie op het **[!UICONTROL Thumbnails]** tabblad op:

   * **[!UICONTROL Thumbnails]**: `140:100:false, 48:48:false, 319:319:false`
   * **[!UICONTROL Skip Mime Types]**: `skip:image/dng, skip:image/x-raw-(.*)`
   ![schil](assets/chlimage_1-334.png)

1. Geef op het **[!UICONTROL Web Enabled Image]** tabblad in het **[!UICONTROL Skip List]** veld op `audio/mpeg, video/(.*), image/dng, image/x-raw-(.*)`.

   ![schil](assets/chlimage_1-335.png)

1. Voeg vanuit het zijpaneel de **[!UICONTROL Camera Raw/DNG Handler]** stap onder de **[!UICONTROL Thumbnail creation]** stap toe.

1. Voeg in de **[!UICONTROL Camera Raw/DNG Handler]** stap de volgende configuratie toe op het **[!UICONTROL Arguments]** tabblad:

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
>Zorg ervoor dat de bovenstaande configuratie hetzelfde is als de **[!UICONTROL Sample DAM Update Asset With Camera RAW and DNG Handling Step]** configuratie.

U kunt nu Camera Raw-bestanden importeren in AEM-elementen. Nadat u het Camera RAW-pakket hebt geïnstalleerd en de vereiste workflow hebt geconfigureerd, wordt de **[!UICONTROL Image Adjust]** optie weergegeven in de lijst met zijvensters.

![chlimage_1-337](assets/chlimage_1-337.png)

*Afbeelding: Opties in het zijvenster*

![chlimage_1-338](assets/chlimage_1-338.png)

*Afbeelding: Met deze optie kunt u lichte bewerkingen uitvoeren op uw afbeeldingen*

Nadat u de bewerkingen in een Camera Raw-afbeelding hebt opgeslagen, `AdjustedPreview.jpg` wordt een nieuwe uitvoering voor de afbeelding gegenereerd. Voor andere afbeeldingstypen, behalve Camera Raw, worden de wijzigingen in alle uitvoeringen doorgevoerd.

## Beste werkwijzen, bekende problemen en beperkingen {#best-practices}

De functionaliteit heeft de volgende beperkingen:

* De functionaliteit ondersteunt alleen JPEG-uitvoeringen. Deze functie wordt ondersteund in Windows 64-bits, Mac OS en RHEL 7.x.
* Metagegevensterugname wordt niet ondersteund voor RAW- en DNG-indelingen.
* De Camera Raw-bibliotheek heeft beperkingen ten opzichte van het totale aantal pixels dat per keer kan worden verwerkt. Op dit moment kan het maximaal 65000 pixels aan de lange zijde van een bestand of 512 MP verwerken, ongeacht de criteria die het eerst worden aangetroffen.
