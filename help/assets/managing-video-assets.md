---
title: Videoassets beheren
description: Leer hoe u video-elementen kunt uploaden, voorvertonen, annoteren en publiceren.
uuid: 56a8c221-409f-4605-97b1-a054dd2abfab
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
discoiquuid: f341fae1-dda3-4917-b6db-ad02fec63702
translation-type: tm+mt
source-git-commit: 2a24d7b9232f39d47d79d995251a14beb0c0f666
workflow-type: tm+mt
source-wordcount: '700'
ht-degree: 5%

---


# Videoassets beheren {#managing-video-assets}

Leer hoe u de video-elementen beheert en bewerkt in Adobe Experience Manager (AEM) Assets. Raadpleeg ook de [Dynamic Media Video documentation](video.md) als u een licentie hebt om Dynamic Media te gebruiken.

## Video-elementen uploaden en voorvertonen {#uploading-and-previewing-video-assets}

AEM Assets genereert voorvertoningen voor video-elementen met de extensie MP4. Als de indeling van het element niet MP4 is, installeert u het MPEG-pakket om een voorvertoning te genereren. MPEG maakt video-uitvoeringen van het type OGG en MP4. U kunt deze uitvoeringen voorvertonen in de gebruikersinterface van AEM Assets.

1. Navigeer in de map Digital Assets of in de submappen naar de locatie waar u digitale elementen wilt toevoegen.
1. Als u het element wilt uploaden, klikt of tikt u op **[!UICONTROL Create]** op de werkbalk en kiest u **[!UICONTROL Files]**. U kunt het ook rechtstreeks in het gebied met elementen neerzetten. Zie [Elementen uploaden](managing-assets-touch-ui.md#uploading-assets) voor meer informatie over het uploaden.
1. Tik op de knop **[!UICONTROL Play]** op het video-element om een voorvertoning van een video weer te geven in de kaartweergave.

   ![chlimage_1-201](assets/chlimage_1-201.png)

   U kunt video alleen pauzeren of afspelen in de weergave **[!UICONTROL Card]**. De knop Afspelen/Pauzeren is niet beschikbaar in de weergave **[!UICONTROL List]**.

1. Tik op het pictogram **[!UICONTROL Edit]** op de kaart om een voorvertoning van de video weer te geven in de weergave **[!UICONTROL Details]**.

   De video wordt afgespeeld in de native videospeler van de browser. U kunt de video afspelen, pauzeren, het volume bepalen en op het volledige scherm in- of uitzoomen.

   ![chlimage_1-202](assets/chlimage_1-202.png)

## Configuratie voor het uploaden van middelen die groter zijn dan 2 GB {#configuration-to-upload-video-assets-that-are-larger-than-gb}

Standaard kunt u met de AEM Assets geen elementen uploaden die groter zijn dan 2 GB vanwege een maximale bestandsgrootte. Nochtans, kunt u deze grens overschrijven door in CRXDE Lite te gaan en een knoop onder de `/apps` folder te creëren. Het knooppunt moet dezelfde knooppuntnaam, directorystructuur en vergelijkbare knooppunteigenschappen van volgorde hebben.

Naast de AEM Assets-configuratie wijzigt u de volgende configuraties om grote elementen te uploaden:

* Verhoog de vervaltijd van het token. Zie [!UICONTROL Adobe Granite CSRF Servlet] in Webconsole op `https://[aem_server]:[port]/system/console/configMgr`. Zie [CSRF-beveiliging](/help/sites-developing/csrf-protection.md) voor meer informatie.
* Verhoog de `receiveTimeout` in de configuratie van de Verzender. Voor meer informatie, zie [de configuratie van de Verzender van de Experience Manager](https://docs.adobe.com/content/help/en/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html#renders-options).

>[!NOTE]
>
>De AEM Klassieke gebruikersinterface heeft geen beperking voor de bestandsgrootte van twee gigabyte. Bovendien wordt de end-to-end workflow voor grote video niet volledig ondersteund.

Als u een hogere maximale bestandsgrootte wilt configureren, voert u de volgende stappen uit in de map `/apps`.

1. Tik in AEM op **[!UICONTROL Tools > General > CRXDE Lite]**.
1. Navigeer op de pagina **[!UICONTROL CRXDE Lite]** in het mappenvenster links naar `/libs/dam/gui/content/assets/jcr:content/actions/secondary/create/items/fileupload`. Tik op `>>` pictogram om het directoryvenster weer te geven.
1. Tik op **[!UICONTROL Overlay Node]** op de werkbalk. U kunt ook **[!UICONTROL Overlay Node]** selecteren in het contextmenu.
1. Tik in het dialoogvenster **[!UICONTROL Overlay Node]** op **[!UICONTROL OK]**.

   ![chlimage_1-203](assets/chlimage_1-203.png)

1. Vernieuw de browser. Het bedekkingsknooppunt `/apps/dam/gui/content/assets/jcr:content/actions/secondary/create/items/fileupload` is geselecteerd.
1. Voer op het tabblad **[!UICONTROL Properties]** de juiste waarde in bytes in om de maximale grootte tot de gewenste grootte te verhogen. Voer bijvoorbeeld de waarde `32212254720` in om de maximale grootte tot 30 GB te verhogen.

1. Tik op **[!UICONTROL Save All]** op de werkbalk.
1. Tik in AEM op **[!UICONTROL Tools > Operations > Web Console]**.
1. Zoek op de pagina **[!UICONTROL Adobe Experience Manager Web Console Bundles]** onder de kolom **[!UICONTROL Name]** van de tabel **[!UICONTROL Adobe Granite Workflow External Process Job Handler]** en tik op.
1. Stel op de pagina **[!UICONTROL Adobe Granite Workflow External Process Job Handler]** de seconden voor zowel **[!UICONTROL Default Timeout]** als **[!UICONTROL Max Timeout]** velden in op `18000` (vijf uur).
1. Tik op **[!UICONTROL Save]**.
1. Tik in AEM op **[!UICONTROL Tools > Workflow > Models]**.
1. Selecteer **[!UICONTROL Workflow Models]** op de pagina **[!UICONTROL Dynamic Media Encode Video]** en tik **[!UICONTROL Edit]**.
1. Tik op de pagina **[!UICONTROL Workflow]** op de component **[!UICONTROL Dynamic Media Video Service Process]**.
1. Vouw **[!UICONTROL Advanced Settings]** onder het tabblad **[!UICONTROL Common]** in het dialoogvenster **[!UICONTROL Step Properties]** uit.
1. Geef in het veld **[!UICONTROL Timeout]** een waarde op van `18000` en tik vervolgens op **[!UICONTROL OK]** om terug te keren naar de workflowpagina **[!UICONTROL Dynamic Media Encode Video]**.
1. Tik boven aan de pagina onder de paginatitel **[!UICONTROL Dynamic Media Encode Video]** op **[!UICONTROL Save]**.

## Video-elementen publiceren {#publishing-video-assets}

Nadat uw video-elementen zijn gepubliceerd, kunt u ze als URL of insluiting op een webpagina opnemen in een webpagina. Zie [Elementen publiceren](publishing-dynamicmedia-assets.md).

## Video-elementen {#annotating-video-assets} notities aanbrengen

1. Tik in de middelenconsole op het pictogram **[!UICONTROL Edit]** op de elementenkaart om de pagina met elementdetails weer te geven.
1. Tik op het pictogram **[!UICONTROL Preview]** om de video af te spelen.
1. Tik op de knop **[!UICONTROL Annotate]** om de video een annotatie te geven. Er wordt een aantekening toegevoegd op het specifieke tijdpunt (frame) in de video.

   Tijdens het notiteren kunt u tekenen op het canvas en een opmerking toevoegen aan de tekening. Opmerkingen worden automatisch opgeslagen in Adobe Experience Manager Assets.

   ![chlimage_1-204](assets/chlimage_1-204.png)

   Tik op **[!UICONTROL Close]** om de wizard Annotatie af te sluiten.

1. Als u naar een specifiek punt in de video wilt gaan, geeft u de tijd op in seconden in het tekstveld en klikt u op **[!UICONTROL Jump]**. Als u bijvoorbeeld de eerste 20 seconden van de video wilt overslaan, typt u `20` in het tekstveld.

   ![chlimage_1-205](assets/chlimage_1-205.png)

1. Klik op een annotatie om deze in de tijdlijn weer te geven. Tik op **[!UICONTROL Delete]** om de annotatie uit de tijdlijn te verwijderen.

   ![chlimage_1-206](assets/chlimage_1-206.png)
