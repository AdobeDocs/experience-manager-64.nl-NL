---
title: Mixed Media Sets
seo-title: Mixed Media Sets
description: Leer hoe u met gemengde mediasets werkt in dynamische media
seo-description: Leer hoe u met gemengde mediasets werkt in dynamische media
uuid: e37fa648-74e2-42e3-8611-8509c92ec00d
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
discoiquuid: 599c316e-b6a7-4a28-bc4b-75d48409bde0
translation-type: tm+mt
source-git-commit: b698a1348df3ec2ab455c236422784d10cbcf7c2
workflow-type: tm+mt
source-wordcount: '1395'
ht-degree: 17%

---


# Mixed Media Sets {#mixed-media-sets}

Met gemengde mediasets kunt u in één presentatie een combinatie van afbeeldingen, afbeeldingssets, centrifuges en video&#39;s aanbieden.

Gemengde mediasets worden aangegeven door een banner met het woord **[!UICONTROL MixedMediaSet]**. Als de gemengde mediaset wordt gepubliceerd, wordt bovendien de publicatiedatum, die door het pictogram **[!UICONTROL World]** wordt aangegeven, samen met de laatste wijzigingsdatum op de banner weergegeven. Dit wordt aangegeven door het pictogram **[!UICONTROL Pencil]**.

![chlimage_1-348](assets/chlimage_1-348.png)

>[!NOTE]
>
>Zie Elementen [beheren met de aanraakinterface](managing-assets-touch-ui.md)voor informatie over de gebruikersinterface van Elementen.

## Snel starten: Gemengde mediasets {#quick-start-mixed-media-sets}

Ga als volgt te werk om snel aan de slag te gaan met gemengde mediasets:

1. [Upload uw elementen](#uploading-assets).

   Begin door de afbeeldingen en video&#39;s voor uw gemengde mediasets te uploaden. Maak indien nodig uw eigen [afbeeldingsets](image-sets.md) en [spinsets](spin-sets.md). Omdat gebruikers kunnen inzoomen op afbeeldingen in de viewer voor gemengde mediasets, moet u rekening houden met zoomen wanneer u afbeeldingen kiest. Zorg ervoor dat de afbeeldingen ten minste 2000 pixels groot zijn in de grootste dimensie.

1. [Gemengde mediasets maken.](#creating-mixed-media-sets)

   Tik op de **[!UICONTROL Assets]** pagina op de set om een gemengde mediaset te maken **[!UICONTROL Create > Mixed Media Set]** en geef deze een naam. Kies de elementen en kies de volgorde waarin de afbeeldingen worden weergegeven.

   See [Working with Selectors.](working-with-selectors.md)

1. Stel indien nodig [gemengde voorinstellingen](managing-viewer-presets.md)voor de Media Viewer in.

   Beheerders kunnen viewervoorinstellingen voor gemengde mediasets maken of wijzigen. Als u de gemengde media met een viewervoorinstelling wilt weergeven, selecteert u de gemengde mediaset en selecteert u **[!UICONTROL Viewers]** in de vervolgkeuzelijst van het linkerspoor.

   Zie **[!UICONTROL Tools > Assets > Viewer Presets]** viewervoorinstellingen maken of bewerken.

   Zie Voorinstellingen voor viewers [toevoegen en bewerken.](managing-viewer-presets.md)

1. [Voorvertoning gemengde mediasets.](#previewing-mixed-media-sets)

   Selecteer de gemengde Mediaset en u kunt er een voorvertoning van weergeven. Klik op de miniatuurpictogrammen om de gemengde mediaset in de geselecteerde viewer te bekijken. U kunt verschillende Viewers van het **[!UICONTROL Viewers]** menu kiezen, beschikbaar van het linkerspoordrop-down menu.

1. [Gemengde mediasets publiceren.](#publishing-mixed-media-sets)

   Wanneer u een gemengde mediaset publiceert, worden de URL en de insluitreeks geactiveerd. Bovendien moet u de voorinstelling [van de viewer](managing-viewer-presets.md#publishing-viewer-presets)publiceren.

1. [Koppel URL&#39;s aan uw webtoepassing](linking-urls-to-yourwebapplication.md) of [sluit de video- of afbeeldingsviewer](embed-code.md)in.

   AEM Assets maakt URL-aanroepen voor gemengde mediasets en activeert deze nadat u de gemengde mediasets hebt gepubliceerd. U kunt deze URL&#39;s kopiëren wanneer u elementen voorvertoont. U kunt ze ook insluiten op uw website.

   Select the Mixed Media Set, then in the left rail drop-down menu, select **[!UICONTROL Viewers]**.

   Zie [Een gemengde mediaset koppelen aan een webpagina](linking-urls-to-yourwebapplication.md) en [De video- of afbeeldingsviewer insluiten](embed-code.md).

Indien nodig kunt u [gemengde mediasets](#editing-mixed-media-sets)bewerken. Daarnaast kunt u de eigenschappen [van](managing-assets-touch-ui.md#editing-properties)gemengde mediaset weergeven en wijzigen.

>[!NOTE]
>
>Zie [Problemen met dynamische media oplossen - Scene7-modus](troubleshoot-dms7.md)voor informatie over het maken van sets.

## Elementen uploaden {#uploading-assets}

Begin door de afbeeldingen en video&#39;s voor uw gemengde mediasets te uploaden. Omdat gebruikers kunnen inzoomen op afbeeldingen in de gemengde Media Set Viewer, dient u rekening te houden met zoomen wanneer u afbeeldingen kiest. Zorg ervoor dat de afbeeldingen ten minste 2000 pixels groot zijn in de grootste dimensie.

Als u bovendien centrifuges of afbeeldingssets wilt toevoegen aan de gemengde mediaset, maakt u deze ook.

## Gemengde mediasets maken {#creating-mixed-media-sets}

U kunt afbeeldingen, afbeeldingssets, centrifuges en video&#39;s toevoegen aan de gemengde mediaset. Zorg ervoor dat de bestanden, afbeeldingssets en centrifuges klaar zijn om te worden gepubliceerd voordat u ze aan de gemengde mediaset toevoegt.

Wanneer u elementen aan de set toevoegt, worden deze automatisch in alfanumerieke volgorde toegevoegd. U kunt elementen handmatig opnieuw ordenen of sorteren nadat u ze hebt toegevoegd.

**Een gemengde mediaset** maken:

1. In Assets, navigate to where you want to create a mixed media set, and click **Create**, and select **[!UICONTROL Mixed Media Set]**. U kunt de set ook maken vanuit een map die uw assets bevat.

   ![chlimage_1-349](assets/chlimage_1-349.png)

1. Voer op de **[!UICONTROL Mixed Media Set Editor]** pagina in **[!UICONTROL Title]** een naam in voor de gemengde mediaset. De naam wordt in de banner weergegeven in de gemengde mediaset. Voer eventueel een beschrijving in.

   ![chlimage_1-350](assets/chlimage_1-350.png)

   >[!NOTE]
   >
   >Wanneer u de gemengde mediaset maakt, kunt u de miniatuur van de gemengde mediaset wijzigen of AEM de miniatuur automatisch selecteren op basis van de elementen in de gemengde mediaset. Als u een miniatuur wilt selecteren, klikt u op een willekeurige afbeelding **[!UICONTROL Change thumbnail]** en selecteert u deze (u kunt ook naar andere mappen navigeren om afbeeldingen te zoeken). If you have selected a thumbnail and then decide that you want AEM to generate one from the mixed media set, select **[!UICONTROL Switch to Automatic thumbnail]**.

1. Tap the **[!UICONTROL Asset Selector]** to select assets that you want to include in your Mixed Media Set. Selecteer deze en tik op **[!UICONTROL Select]**.

   With the **[!UICONTROL Asset Selector]**, you can search for assets by typing in a keyword and tapping **[!UICONTROL Return]**. U kunt ook filters toepassen om de zoekresultaten te verfijnen. U kunt filteren op pad, verzameling, bestandstype en tag. Selecteer het filter en tik op het pictogram **[!UICONTROL Filter]** op de werkbalk. Change the view by selecting the View icon and selecting **[!UICONTROL List]**, **[!UICONTROL Column]**, or **[!UICONTROL Card]** view.

   See [Working with Selectors](working-with-selectors.md).

   ![chlimage_1-351](assets/chlimage_1-351.png)

1. Wijzig de volgorde van de elementen door deze omhoog of omlaag in de lijst te slepen (selecteer het pictogram voor opnieuw ordenen).

   ![chlimage_1-352](assets/chlimage_1-352.png)

   If you want to add thumbnails, click the **[!UICONTROL +]** icon next to the image and navigate to the thumbnail you want. Tik op alle miniatuurafbeeldingen wanneer u klaar bent met het selecteren **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Tik op **[!UICONTROL Add Asset]** als u elementen wilt toevoegen.

1. Als u een element wilt verwijderen, schakelt u het desbetreffende selectievakje in en tikt u op **[!UICONTROL Delete Asset]**.
1. Tik in de rechterbovenhoek op een voorinstelling om deze toe te passen. Selecteer vervolgens de voorinstelling die u op de elementen wilt toepassen. **[!UICONTROL Preset]**
1. Klik op **[!UICONTROL Save]**. De nieuwe gemengde mediaset wordt weergegeven in de map waarin u deze hebt gemaakt.

## Gemengde mediasets bewerken {#editing-mixed-media-sets}

U kunt diverse bewerkingstaken rechtstreeks in de gebruikersinterface uitvoeren op elementen in gemengde mediasets, [net als op elementen](managing-assets-touch-ui.md). U kunt ook de volgende handelingen uitvoeren in Gemengde Mediasets:

* Voeg elementen toe aan de gemengde mediaset.
* Wijzig de volgorde van elementen in de gemengde mediaset.
* Elementen verwijderen uit de gemengde mediaset.
* Voorinstellingen voor viewers toepassen.
* Wijzig de standaardminiatuur.

**Gemengde mediasets** bewerken:

1. Voer een van de volgende handelingen uit:

   * Houd de muisaanwijzer boven een element uit een gemengde mediaset en tik op **[!UICONTROL Edit]** (potloodpictogram).
   * Houd de muisaanwijzer boven een element uit een gemengde mediaset, tik op **[!UICONTROL Select]** (vinkpictogram) en tik vervolgens op **[!UICONTROL Edit]** de werkbalk.
   * Tik op een element uit een gemengde mediaset en tik vervolgens op **[!UICONTROL Edit]** (potloodpictogram) op de werkbalk.

1. Voer in de Editor gemengde mediaset een van de volgende handelingen uit:

   * Tik in het linkerdeelvenster op **[!UICONTROL Assets]** (afbeeldingspictogram) en sleep een element naar een nieuwe locatie om de volgorde van de elementen te wijzigen.
   * Tik op **[!UICONTROL Add Asset]** de werkbalk om elementen toe te voegen. Navigeer naar de elementen. Tik op het pictogram van het vinkje voor elk element dat u wilt toevoegen. Houd de muisaanwijzer boven de afbeelding van het element (niet de naam van het element). Tik in de rechterbovenhoek op **[!UICONTROL Select]**.
   * Tik op **[!UICONTROL Assets]** (afbeeldingspictogram) en selecteer het element om een element te verwijderen. Tik op de werkbalk **[!UICONTROL Delete Asset]**.
   * Tik in het linkerdeelvenster op **[!UICONTROL Assets]** (afbeeldingspictogram) om elementen op naam in oplopende of aflopende volgorde te sorteren. Tik rechts van de **[!UICONTROL Assets]** kop op of omlaag de invoegpictogrammen.

   >[!NOTE]
   >
   >* To delete an entire Mixed Media Set, from any viewing mode (such as **[!UICONTROL Card]** view or **[!UICONTROL Column]** view) navigate to the Mixed Media Set. Wijs de asset aan en tik op het vinkje om deze te selecteren. Druk op **[!UICONTROL Backspace]** het toetsenbord of tik op **[!UICONTROL More]** (drie punten) op de werkbalk en tik vervolgens op **[!UICONTROL Delete]**.
   >* You can edit the assets in a Mixed Media Set by navigating to the set, tapping **[!UICONTROL Set Members]** in the left rail, and then tapping the **[!UICONTROL Pencil]** icon on an individual asset to open the editing window.


1. Tik **[!UICONTROL Save]** wanneer u klaar bent met bewerken.

   >[!NOTE]
   >
   >* Als u de assets in een gemengde mediaset wilt bewerken, gaat u naar de gemengde mediaset. Tap (do not select) the set to open it in the AEM **[!UICONTROL Set Preview]** page. In the left rail, tap the down caret to open the drop-down list, then tap **[!UICONTROL Set Members]**. In the **[!UICONTROL Set Members]** page, hover on an asset, then tap **[!UICONTROL Edit]** (pencil icon) to open the editing page.
   >* To delete an entire Mixed Media Set - From any viewing mode (such as **[!UICONTROL Card]** view or **[!UICONTROL Column]** view), navigate to the Mixed Media Set. Hover on the set, then tap **[!UICONTROL Select]** (checkmark icon). Druk op **[!UICONTROL Backspace]** het toetsenbord of tik op **[!UICONTROL More]** (rij met drie punten) en tik vervolgens op **[!UICONTROL Delete]**.


## Voorvertoning van gemengde mediasets {#previewing-mixed-media-sets}

Zie Elementen [](previewing-assets.md) voorvertonen voor meer informatie over het voorvertonen van gemengde mediasets.

## Gemengde mediasets publiceren {#publishing-mixed-media-sets}

Zie Elementen [](publishing-dynamicmedia-assets.md) publiceren voor meer informatie over het publiceren van gemengde mediasets.

>[!NOTE]
>
>Als de gemengde Det van Media niet volledig in de leveringsdienst belandt de eerste keer u het publiceert, kunt u de gemengde media reeks een tweede keer moeten publiceren.

