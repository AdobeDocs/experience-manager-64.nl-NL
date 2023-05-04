---
title: Videoassets beheren
description: Leer hoe u video-elementen kunt uploaden, voorvertonen, annoteren en publiceren.
uuid: 56a8c221-409f-4605-97b1-a054dd2abfab
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
discoiquuid: f341fae1-dda3-4917-b6db-ad02fec63702
feature: Asset Management,Video
role: User
exl-id: eb652414-5b10-45af-a8b6-f1de649994c5
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '728'
ht-degree: 5%

---

# Videoassets beheren {#managing-video-assets}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Leer hoe u de video-elementen beheert en bewerkt in Adobe Experience Manager Assets. Als u een licentie hebt voor het gebruik van Dynamic Media, raadpleegt u de [Dynamic Media Video-documentatie](video.md).

## Video-elementen uploaden en voorvertonen {#uploading-and-previewing-video-assets}

[!DNL Experience Manager] Elementen genereren voorvertoningen voor video-elementen met de extensie MP4. Als de indeling van het element niet MP4 is, installeert u het MPEG-pakket om een voorvertoning te genereren. MPEG maakt video-uitvoeringen van het type OGG en MP4. U kunt deze vertoningen voorvertonen in het dialoogvenster [!DNL Experience Manager] Elementengebruikersinterface.

1. Navigeer in de map Digital Assets of in de submappen naar de locatie waar u digitale elementen wilt toevoegen.
1. Als u het element wilt uploaden, klikt u of tikt u op **[!UICONTROL Create]** op de werkbalk en kies vervolgens **[!UICONTROL Files]**. U kunt het ook rechtstreeks in het gebied met elementen neerzetten. Zie [Elementen uploaden](managing-assets-touch-ui.md#uploading-assets) voor meer informatie over het uploaden.
1. Tik op de knop **[!UICONTROL Play]** op het video-element.

   ![chlimage_1-201](assets/chlimage_1-201.png)

   U kunt video pauzeren of afspelen in het dialoogvenster **[!UICONTROL Card]** alleen weergeven. De knop Afspelen/Pauzeren is niet beschikbaar in het dialoogvenster **[!UICONTROL List]** weergeven.

1. Tik op de knop **[!UICONTROL Edit]** pictogram op de kaart om een voorvertoning van de video weer te geven in het dialoogvenster **[!UICONTROL Details]** weergeven.

   De video wordt afgespeeld in de native videospeler van de browser. U kunt de video afspelen, pauzeren, het volume bepalen en op het volledige scherm in- of uitzoomen.

   ![chlimage_1-202](assets/chlimage_1-202.png)

## Configuratie voor het uploaden van middelen die groter zijn dan 2 GB {#configuration-to-upload-video-assets-that-are-larger-than-gb}

Standaard worden de [!DNL Experience Manager] Met middelen kunt u geen elementen uploaden die groter zijn dan 2 GB vanwege een maximale bestandsgrootte. Nochtans, kunt u deze grens overschrijven door in CRXDE Lite te gaan en een knoop onder te creëren `/apps` directory. Het knooppunt moet dezelfde knooppuntnaam, directorystructuur en vergelijkbare knooppunteigenschappen van volgorde hebben.

Naast [!DNL Experience Manager] Configuratie van elementen, wijzig de volgende configuraties om grote elementen te uploaden:

* Verhoog de vervaltijd van het token. Zie [!UICONTROL Adobe Granite CSRF Servlet] in webconsole op `https://[aem_server]:[port]/system/console/configMgr`. Zie voor meer informatie [CSRF-bescherming](/help/sites-developing/csrf-protection.md).
* De `receiveTimeout` in Dispatcher-configuratie. Zie voor meer informatie [Configuratie van Experience Manager Dispatcher](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html#renders-options).

>[!NOTE]
>
>De [!DNL Experience Manager] Klassieke gebruikersinterface heeft geen beperking voor de bestandsgrootte van twee gigabyte. Bovendien wordt de end-to-end workflow voor grote video niet volledig ondersteund.

Voer de volgende stappen uit in het dialoogvenster `/apps` directory.

1. Tik in AEM op **[!UICONTROL Tools > General > CRXDE Lite]**.
1. In de **[!UICONTROL CRXDE Lite]** pagina, in het foldervenster op de linkerzijde, navigeer aan `/libs/dam/gui/content/assets/jcr:content/actions/secondary/create/items/fileupload`. Tik op `>>` pictogram.
1. Tik op de werkbalk op **[!UICONTROL Overlay Node]**. U kunt ook **[!UICONTROL Overlay Node]** selecteren in het contextmenu.
1. Tik in het dialoogvenster **[!UICONTROL Overlay Node]** op **[!UICONTROL OK]**.

   ![chlimage_1-203](assets/chlimage_1-203.png)

1. Vernieuw de browser. Het overlayknooppunt `/apps/dam/gui/content/assets/jcr:content/actions/secondary/create/items/fileupload` is geselecteerd.
1. In de **[!UICONTROL Properties]** voert u de gewenste waarde in bytes in om de maximale grootte tot de gewenste grootte te verhogen. Voer bijvoorbeeld `32212254720` waarde om de groottelimiet te verhogen tot 30 GB.

1. Tik op de werkbalk op **[!UICONTROL Save All]**.
1. Tik in AEM op **[!UICONTROL Tools > Operations > Web Console]**.
1. Op de **[!UICONTROL Adobe Experience Manager Web Console Bundles]** pagina, onder de **[!UICONTROL Name]** kolom van de tabel, zoek en tik **[!UICONTROL Adobe Granite Workflow External Process Job Handler]**.
1. In de **[!UICONTROL Adobe Granite Workflow External Process Job Handler]** pagina, stel de seconden voor beide in **[!UICONTROL Default Timeout]** en **[!UICONTROL Max Timeout]** velden naar `18000` (vijf uur).
1. Tik op **[!UICONTROL Save]**.
1. Tik in AEM op **[!UICONTROL Tools > Workflow > Models]**.
1. Op de **[!UICONTROL Workflow Models]** pagina, selecteert u **[!UICONTROL Dynamic Media Encode Video]** tikt u vervolgens op **[!UICONTROL Edit]**.
1. Op de **[!UICONTROL Workflow]** pagina, dubbeltikt u op de **[!UICONTROL Dynamic Media Video Service Process]** component.
1. In de **[!UICONTROL Step Properties]** onder de **[!UICONTROL Common]** tab, uitvouwen **[!UICONTROL Advanced Settings]**.
1. Geef in het veld **[!UICONTROL Timeout]** een waarde op van `18000` en tik vervolgens op **[!UICONTROL OK]** om terug te keren naar de workflowpagina **[!UICONTROL Dynamic Media Encode Video]**.
1. Boven aan de pagina, onder de **[!UICONTROL Dynamic Media Encode Video]** paginatitel, tikken **[!UICONTROL Save]**.

## Video-elementen publiceren {#publishing-video-assets}

Nadat uw video-elementen zijn gepubliceerd, kunt u ze als URL of insluiting op een webpagina opnemen in een webpagina. Zie [Elementen publiceren](publishing-dynamicmedia-assets.md).

## Video-elementen notities aanbrengen {#annotating-video-assets}

1. Tik vanuit de middelenconsole op de knop **[!UICONTROL Edit]** op de elementenkaart om de pagina met elementdetails weer te geven.
1. Tik op de knop **[!UICONTROL Preview]** pictogram om de video af te spelen.
1. Tik op de knop **[!UICONTROL Annotate]** knop. Er wordt een aantekening toegevoegd op het specifieke tijdpunt (frame) in de video.

   Tijdens het notiteren kunt u tekenen op het canvas en een opmerking toevoegen aan de tekening. Opmerkingen worden automatisch opgeslagen in Adobe Experience Manager Assets.

   ![chlimage_1-204](assets/chlimage_1-204.png)

   Tik op **[!UICONTROL Close]**.

1. Als u naar een specifiek punt in de video wilt gaan, geeft u de tijd op in seconden in het tekstveld en klikt u op **[!UICONTROL Jump]**. Als u bijvoorbeeld de eerste 20 seconden van de video wilt overslaan, voert u `20` in het tekstveld.

   ![chlimage_1-205](assets/chlimage_1-205.png)

1. Klik op een annotatie om deze in de tijdlijn weer te geven. Tikken **[!UICONTROL Delete]** om de annotatie uit de tijdlijn te verwijderen.

   ![chlimage_1-206](assets/chlimage_1-206.png)
