---
title: Videoassets beheren
description: Leer hoe u video-elementen kunt uploaden, voorvertonen, annoteren en publiceren.
uuid: 56a8c221-409f-4605-97b1-a054dd2abfab
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
discoiquuid: f341fae1-dda3-4917-b6db-ad02fec63702
translation-type: tm+mt
source-git-commit: 9ced187ddc9bb2d12922fcc734b20ef9767d8fbf

---


# Videoassets beheren {#managing-video-assets}

Leer hoe u de video-elementen beheert en bewerkt in Adobe Experience Manager (AEM) Assets. Raadpleeg ook de documentatie bij [](video.md)Dynamic Media Video als u een licentie hebt voor het gebruik van Dynamic Media.

## Video-elementen uploaden en voorvertonen {#uploading-and-previewing-video-assets}

AEM Assets genereert voorvertoningen voor video-elementen met de extensie MP4. Als de indeling van het element niet MP4 is, installeert u het MPEG-pakket om een voorvertoning te genereren. MPEG maakt video-uitvoeringen van het type OGG en MP4. U kunt een voorvertoning van deze vertoningen weergeven in de gebruikersinterface van AEM Assets.

1. Navigeer in de map Digital Assets of in de submappen naar de locatie waar u digitale elementen wilt toevoegen.
1. Klik of tik op **[!UICONTROL Maken]** op de werkbalk om het element te uploaden en kies **[!UICONTROL Bestanden]**. U kunt het ook rechtstreeks in het gebied met elementen neerzetten. Zie Elementen [](managing-assets-touch-ui.md#uploading-assets) uploaden voor meer informatie over het uploaden.
1. Tik op de knop **[!UICONTROL Afspelen]** op het video-element om een voorvertoning van een video weer te geven in de kaartweergave.

   ![chlimage_1-201](assets/chlimage_1-201.png)

   U kunt video alleen pauzeren of afspelen in de weergave **[!UICONTROL Kaart]** . De knop Afspelen/Pauzeren is niet beschikbaar in de **[!UICONTROL lijstweergave]** .

1. Tik op het pictogram **[!UICONTROL Bewerken]** op de kaart om een voorvertoning van de video weer te geven in de weergave **[!UICONTROL Details]** .

   De video wordt afgespeeld in de native videospeler van de browser. U kunt de video afspelen, pauzeren, het volume bepalen en op het volledige scherm in- of uitzoomen.

   ![chlimage_1-202](assets/chlimage_1-202.png)

## Configuratie voor het uploaden van middelen die groter zijn dan 2 GB {#configuration-to-upload-video-assets-that-are-larger-than-gb}

Standaard kunt u met de AEM-middelen geen elementen uploaden die groter zijn dan 2 GB vanwege een maximale bestandsgrootte. Nochtans, kunt u deze grens overschrijven door in CRXDE Lite te gaan en een knoop onder de `/apps` folder te creëren. Het knooppunt moet dezelfde knooppuntnaam, directorystructuur en vergelijkbare knooppunteigenschappen van volgorde hebben.

Naast de configuratie van AEM-elementen kunt u de volgende configuraties wijzigen om grote elementen te uploaden:

* Verhoog de vervaltijd van het token. Zie [!UICONTROL Adobe Granite CSRF Servlet] in de Console van het Web bij `https://[aem_server]:[port]/system/console/configMgr`. Zie [CSRF-bescherming](/help/sites-developing/csrf-protection.md)voor meer informatie.
* Verhoog de `receiveTimeout` configuratie van Dispatcher. Voor meer informatie, zie de configuratie [van de Verzender van de Manager van de](https://docs.adobe.com/content/help/en/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html#renders-options)Ervaring.

>[!NOTE]
>
>De klassieke AEM-gebruikersinterface heeft geen beperking voor de bestandsgrootte van twee gigabyte. Bovendien wordt de end-to-end workflow voor grote video niet volledig ondersteund.

Voer de volgende stappen in de `/apps` map uit om een hogere maximale bestandsgrootte te configureren.

1. Tik in AEM op **[!UICONTROL Gereedschappen > Algemeen > CRXDE Lite]**.
1. Navigeer op de pagina **[!UICONTROL CRXDE Lite]** in het foldervenster op de linkerzijde aan `/libs/dam/gui/content/assets/jcr:content/actions/secondary/create/items/fileupload`. Tik op `>>` het pictogram om het directoryvenster weer te geven.
1. Tik op de werkbalk op **[!UICONTROL Overlayknooppunt]**. U kunt ook **[!UICONTROL Overlayknooppunt]** selecteren in het contextmenu.
1. Tik in het dialoogvenster **[!UICONTROL Overlayknooppunt]** op **[!UICONTROL OK]**.

   ![chlimage_1-203](assets/chlimage_1-203.png)

1. Vernieuw de browser. Het bedekkingsknooppunt `/jcr_root/apps/dam/gui/content/assets/jcr:content/actions/secondary/create/items/fileupload` is geselecteerd.
1. Voer op het tabblad **[!UICONTROL Eigenschappen]** de juiste waarde in bytes in om de maximale grootte tot de gewenste grootte te verhogen. Voer bijvoorbeeld de volgende waarde in om de maximale grootte van 30 GB te verhogen:

   `{sizeLimit : "32212254720"}`

1. Tik op de werkbalk op Alles **** opslaan.
1. Tik in AEM op **[!UICONTROL Gereedschappen > Bewerkingen > Webconsole]**.
1. Zoek en tik op de pagina Bundles **[!UICONTROL van de webconsole van]** Adobe Experience Manager onder de kolom **[!UICONTROL Naam]** van de tabel op **[!UICONTROL Adobe Granite Workflow External Process Job Handler]**.
1. Stel de seconden voor de velden **[!UICONTROL Standaardtime-out]** en **[!UICONTROL Maximale time-out]** in op **[!UICONTROL (vijf uur) op de pagina Externe taakhandler]** `18000` van de Adobe Granite-workflow.
1. Tik op **[!UICONTROL Opslaan]**.
1. Tik in AEM op **[!UICONTROL Gereedschappen > Workflow > Modellen]**.
1. Selecteer op de pagina **[!UICONTROL Workflowmodellen]** de optie **[!UICONTROL Dynamic Media Encode Video]** en tik vervolgens op **[!UICONTROL Bewerken]**.
1. Tik op de pagina **[!UICONTROL Workflow]** op de component **[!UICONTROL Dynamic Media Video Service]** .
1. Vouw **[!UICONTROL Geavanceerde instellingen]** uit onder het tabblad **[!UICONTROL Algemeen]** in het dialoogvenster Eigenschappen **[!UICONTROL voor stap]**.
1. Geef in het veld **[!UICONTROL Time-out]** een waarde op van `18000`, tik vervolgens op **[!UICONTROL OK]** om terug te keren naar de **[!UICONTROL workflowpagina Video]** coderen van dynamische media.
1. Tik boven aan de pagina onder de titel van de pagina Video **[!UICONTROL coderen van]** dynamische media op **[!UICONTROL Opslaan]**.

## Video-elementen publiceren {#publishing-video-assets}

Nadat uw video-elementen zijn gepubliceerd, kunt u ze als URL of insluiting op een webpagina opnemen in een webpagina. Zie Elementen [](publishing-dynamicmedia-assets.md)publiceren.

## Video-elementen notities aanbrengen {#annotating-video-assets}

1. Tik in de middelenconsole op het pictogram **[!UICONTROL Bewerken]** op de elementenkaart om de pagina met elementdetails weer te geven.
1. Tik op het pictogram **[!UICONTROL Voorvertoning]** om de video af te spelen.
1. Tik op de knop **[!UICONTROL Annoteren]** om de video een annotatie te geven. Er wordt een aantekening toegevoegd op het specifieke tijdpunt (frame) in de video.

   Tijdens het notiteren kunt u tekenen op het canvas en een opmerking toevoegen aan de tekening. Opmerkingen worden automatisch opgeslagen in Adobe Experience Manager-middelen.

   ![chlimage_1-204](assets/chlimage_1-204.png)

   Tik op **[!UICONTROL Sluiten om de wizard Annotatie af te sluiten]**.

1. Als u naar een specifiek punt in de video wilt gaan, geeft u de tijd op in seconden in het tekstveld en klikt u op **[!UICONTROL Springen]**. Als u bijvoorbeeld de eerste 10 seconden van de video wilt overslaan, voert u deze in `20` het tekstveld in.

   ![chlimage_1-205](assets/chlimage_1-205.png)

1. Klik op een annotatie om deze in de tijdlijn weer te geven. Tik op **[!UICONTROL Verwijderen]** om de annotatie uit de tijdlijn te verwijderen.

   ![chlimage_1-205](assets/chlimage_1-206.png)
