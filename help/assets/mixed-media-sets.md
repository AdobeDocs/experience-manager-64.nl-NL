---
title: Mixed Media Sets
description: Leer hoe u in Dynamic Media werkt met gemengde mediasets (afbeeldingen, afbeeldingssets, centrifuges en video's).
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
exl-id: 252c1a50-17ac-4412-88d6-49bb6850658d
feature: Mediasets mixen
role: Business Practitioner
translation-type: tm+mt
source-git-commit: f9faa357f8de92d205f1a297767ba4176cfd1e10
workflow-type: tm+mt
source-wordcount: '1391'
ht-degree: 17%

---

# Mixed Media Sets {#mixed-media-sets}

Met gemengde mediasets kunt u in één presentatie een combinatie van afbeeldingen, afbeeldingssets, centrifuges en video&#39;s aanbieden.

Gemengde mediasets worden aangegeven door een banner met het woord **[!UICONTROL MixedMediaSet]**. Als de gemengde mediaset wordt gepubliceerd, wordt bovendien de publicatiedatum, die door het pictogram **[!UICONTROL World]** wordt aangegeven, samen met de laatste wijzigingsdatum op de banner weergegeven. Dit wordt aangegeven door het pictogram **[!UICONTROL Pencil]**.

![chlimage_1-348](assets/chlimage_1-348.png)

>[!NOTE]
>
>Zie [Elementen beheren met de aanraakinterface](managing-assets-touch-ui.md) voor informatie over de gebruikersinterface van Elementen.

## Snel starten: Gemengde mediasets {#quick-start-mixed-media-sets}

Ga als volgt te werk om snel aan de slag te gaan met gemengde mediasets:

1. [Upload uw elementen](#uploading-assets).

   Begin door de afbeeldingen en video&#39;s voor uw gemengde mediasets te uploaden. Maak indien nodig uw eigen [afbeeldingsets](image-sets.md) en [spinsets](spin-sets.md). Omdat gebruikers kunnen inzoomen op afbeeldingen in de viewer voor gemengde mediasets, moet u rekening houden met zoomen wanneer u afbeeldingen kiest. Zorg ervoor dat de afbeeldingen ten minste 2000 pixels groot zijn in de grootste dimensie.

1. [Gemengde mediasets maken.](#creating-mixed-media-sets)

   Tik op **[!UICONTROL Create > Mixed Media Set]** op de pagina **[!UICONTROL Assets]** om een gemengde mediaset te maken en geef vervolgens een naam op voor de set. Kies de elementen en kies de volgorde waarin de afbeeldingen worden weergegeven.

   Zie [Werken met kiezers.](working-with-selectors.md)

1. Stel [Voorinstellingen voor gemengde media-viewer](managing-viewer-presets.md) naar wens in.

   Beheerders kunnen viewervoorinstellingen voor gemengde mediasets maken of wijzigen. Als u de gemengde media met een viewervoorinstelling wilt weergeven, selecteert u de gemengde mediaset en selecteert u **[!UICONTROL Viewers]** in de vervolgkeuzelijst van het linkerspoor.

   Zie **[!UICONTROL Tools > Assets > Viewer Presets]** om voorinstellingen voor viewers te maken of te bewerken.

   Zie [Voorinstellingen voor viewers toevoegen en bewerken.](managing-viewer-presets.md)

1. [Voorvertoning gemengde mediasets.](#previewing-mixed-media-sets)

   Selecteer de gemengde Mediaset en u kunt er een voorvertoning van weergeven. Klik op de miniatuurpictogrammen om de gemengde mediaset in de geselecteerde viewer te bekijken. U kunt verschillende Viewers van **[!UICONTROL Viewers]** menu kiezen, beschikbaar van het linkerspoordrop-down menu.

1. [Gemengde mediasets publiceren.](#publishing-mixed-media-sets)

   Wanneer u een gemengde mediaset publiceert, worden de URL en de insluitreeks geactiveerd. Daarnaast moet u [de viewervoorinstelling](managing-viewer-presets.md#publishing-viewer-presets) publiceren.

1. [Koppel URL&#39;s aan uw webtoepassing ](linking-urls-to-yourwebapplication.md) of  [sluit de video- of afbeeldingsviewer](embed-code.md) in.

   AEM Assets maakt URL-aanroepen voor gemengde mediasets en activeert deze nadat u de gemengde mediasets hebt gepubliceerd. U kunt deze URL&#39;s kopiëren wanneer u elementen voorvertoont. U kunt ze ook insluiten op uw website.

   Selecteer de Gemengde Reeks van Media, dan in de linkerspoordrop-down menu, uitgezocht **[!UICONTROL Viewers]**.

   Zie [Een gemengde mediaset koppelen aan een webpagina](linking-urls-to-yourwebapplication.md) en [De video- of afbeeldingsviewer insluiten](embed-code.md).

Indien nodig kunt u [Gemengde Mediasets](#editing-mixed-media-sets) bewerken. Daarnaast kunt u [Eigenschappen van gemengde mediaset](managing-assets-touch-ui.md#editing-properties) weergeven en wijzigen.

>[!NOTE]
>
>Zie [Problemen met Dynamic Media oplossen - Scene7-modus](troubleshoot-dms7.md) als u problemen ondervindt bij het maken van sets.

## Elementen {#uploading-assets} uploaden

Begin door de afbeeldingen en video&#39;s voor uw gemengde mediasets te uploaden. Omdat gebruikers kunnen inzoomen op afbeeldingen in de gemengde Media Set Viewer, dient u rekening te houden met zoomen wanneer u afbeeldingen kiest. Zorg ervoor dat de afbeeldingen ten minste 2000 pixels groot zijn in de grootste dimensie.

Als u bovendien centrifuges of afbeeldingssets wilt toevoegen aan de gemengde mediaset, maakt u deze ook.

## Gemengde mediasets maken {#creating-mixed-media-sets}

U kunt afbeeldingen, afbeeldingssets, centrifuges en video&#39;s toevoegen aan de gemengde mediaset. Zorg ervoor dat de bestanden, afbeeldingssets en centrifuges klaar zijn om te worden gepubliceerd voordat u ze aan de gemengde mediaset toevoegt.

Wanneer u elementen aan de set toevoegt, worden deze automatisch in alfanumerieke volgorde toegevoegd. U kunt elementen handmatig opnieuw ordenen of sorteren nadat u ze hebt toegevoegd.

**Een gemengde mediaset** maken:

1. Navigeer in Elementen naar de plaats waar u een gemengde mediaset wilt maken en klik op **Maken** en selecteer **[!UICONTROL Mixed Media Set]**. U kunt de set ook maken vanuit een map die uw assets bevat.

   ![chlimage_1-349](assets/chlimage_1-349.png)

1. Voer op de pagina **[!UICONTROL Mixed Media Set Editor]** in **[!UICONTROL Title]** een naam in voor de gemengde mediaset. De naam wordt in de banner weergegeven in de gemengde mediaset. Voer eventueel een beschrijving in.

   ![chlimage_1-350](assets/chlimage_1-350.png)

   >[!NOTE]
   >
   >Wanneer u de gemengde mediaset maakt, kunt u de miniatuur van de gemengde mediaset wijzigen of AEM de miniatuur automatisch selecteren op basis van de elementen in de gemengde mediaset. Als u een miniatuur wilt selecteren, klikt u op **[!UICONTROL Change thumbnail]** en selecteert u een willekeurige afbeelding (u kunt ook naar andere mappen navigeren om afbeeldingen te zoeken). Selecteer **[!UICONTROL Switch to Automatic thumbnail]** als u een miniatuur hebt geselecteerd en vervolgens wilt bepalen dat u AEM een miniatuur wilt genereren op basis van de gemengde mediaset.

1. Tik op **[!UICONTROL Asset Selector]** om elementen te selecteren die u wilt opnemen in de gemengde mediaset. Selecteer deze en tik **[!UICONTROL Select]**.

   Met **[!UICONTROL Asset Selector]**, kunt u naar activa zoeken door in een sleutelwoord te typen en **[!UICONTROL Return]** te tikken. U kunt ook filters toepassen om de zoekresultaten te verfijnen. U kunt filteren op pad, verzameling, bestandstype en tag. Selecteer het filter en tik op het pictogram **[!UICONTROL Filter]** op de werkbalk. Wijzig de weergave door het pictogram Weergave te selecteren en de weergave **[!UICONTROL List]**, **[!UICONTROL Column]** of **[!UICONTROL Card]** te selecteren.

   Zie [Werken met kiezers](working-with-selectors.md).

   ![chlimage_1-351](assets/chlimage_1-351.png)

1. Wijzig de volgorde van de elementen door deze omhoog of omlaag in de lijst te slepen (selecteer het pictogram voor opnieuw ordenen).

   ![chlimage_1-352](assets/chlimage_1-352.png)

   Als u miniaturen wilt toevoegen, klikt u op het pictogram **[!UICONTROL +]** naast de afbeelding en navigeert u naar de gewenste miniatuur. Tik **[!UICONTROL Save]** wanneer u alle miniatuurafbeeldingen hebt geselecteerd.

   >[!NOTE]
   >
   >Tik op **[!UICONTROL Add Asset]** als u elementen wilt toevoegen.

1. Als u een element wilt verwijderen, schakelt u het desbetreffende selectievakje in en tikt u op **[!UICONTROL Delete Asset]**.
1. Tik op **[!UICONTROL Preset]** in de rechterbovenhoek om een voorinstelling toe te passen en selecteer een voorinstelling die u op de elementen wilt toepassen.
1. Klik op **[!UICONTROL Save]**. De nieuwe gemengde mediaset wordt weergegeven in de map waarin u deze hebt gemaakt.

## Gemengde mediasets bewerken {#editing-mixed-media-sets}

U kunt een verscheidenheid van het uitgeven taken aan activa in Gemengde Reeksen van Media direct in het gebruikersinterface [uitvoeren aangezien u om het even welke activa in Activa](managing-assets-touch-ui.md). U kunt ook de volgende handelingen uitvoeren in Gemengde Mediasets:

* Voeg elementen toe aan de gemengde mediaset.
* Wijzig de volgorde van elementen in de gemengde mediaset.
* Elementen verwijderen uit de gemengde mediaset.
* Voorinstellingen voor viewers toepassen.
* Wijzig de standaardminiatuur.

**Gemengde mediasets** bewerken:

1. Voer een van de volgende handelingen uit:

   * Houd de muisaanwijzer boven een element uit een gemengde mediaset en tik op **[!UICONTROL Edit]** (potloodpictogram).
   * Tik met de muis over een element uit een gemengde mediaset op **[!UICONTROL Select]** (vinkpictogram) en tik **[!UICONTROL Edit]** op de werkbalk.
   * Tik op een element uit een gemengde mediaset en tik op **[!UICONTROL Edit]** (potloodpictogram) op de werkbalk.

1. Voer in de Editor gemengde mediaset een van de volgende handelingen uit:

   * Tik op **[!UICONTROL Assets]** (afbeeldingspictogram) om elementen opnieuw te rangschikken. Sleep een element naar een nieuwe locatie.
   * Tik op **[!UICONTROL Add Asset]** om elementen toe te voegen. Navigeer naar de elementen. Tik op het pictogram van het vinkje voor elk element dat u wilt toevoegen. Houd de muisaanwijzer boven de afbeelding van het element (niet de naam van het element). Tik in de rechterbovenhoek op **[!UICONTROL Select]**.
   * Tik op **[!UICONTROL Assets]** (afbeeldingspictogram) in het linkerdeelvenster en selecteer vervolgens het element om een element te verwijderen. Tik **[!UICONTROL Delete Asset]** op de werkbalk.
   * Tik in het linkerdeelvenster op **[!UICONTROL Assets]** (afbeeldingspictogram) om elementen op naam in oplopende of aflopende volgorde te sorteren. Tik rechts van de **[!UICONTROL Assets]**-kop op de pictogrammen voor de invoegpunt.

   >[!NOTE]
   >
   >* Als u een volledige gemengde mediaset wilt verwijderen, navigeert u vanuit elke weergavemodus (zoals de weergave **[!UICONTROL Card]** of **[!UICONTROL Column]**) naar de gemengde mediaset. Wijs de asset aan en tik op het vinkje om deze te selecteren. Druk op **[!UICONTROL Backspace]** op het toetsenbord of tik **[!UICONTROL More]** (drie punten) op de werkbalk en tik vervolgens op **[!UICONTROL Delete]**.
   >* U kunt de elementen in een gemengde mediaset bewerken door naar de set te navigeren, op **[!UICONTROL Set Members]** in de linkertrack te tikken en vervolgens op het pictogram **[!UICONTROL Pencil]** op een afzonderlijk element te tikken om het bewerkingsvenster te openen.


1. Tik **[!UICONTROL Save]** wanneer u klaar bent met bewerken.

   >[!NOTE]
   >
   >* Als u de assets in een gemengde mediaset wilt bewerken, gaat u naar de gemengde mediaset. Tik (niet selecteren) op de set om deze te openen op de pagina AEM **[!UICONTROL Set Preview]**. Tik in het linkerspoor op het inlasteken om de vervolgkeuzelijst te openen en tik vervolgens op **[!UICONTROL Set Members]**. Houd de cursor op een element op de pagina **[!UICONTROL Set Members]** en tik op **[!UICONTROL Edit]** (potloodpictogram) om de bewerkingspagina te openen.
   >* Als u een volledige gemengde mediaset wilt verwijderen, navigeert u vanuit elke weergavemodus (zoals de weergave **[!UICONTROL Card]** of **[!UICONTROL Column]**) naar de gemengde mediaset. Tik op **[!UICONTROL Select]** (vinkpictogram). Druk op **[!UICONTROL Backspace]** op het toetsenbord of tik **[!UICONTROL More]** (rij met drie punten) en tik vervolgens op **[!UICONTROL Delete]**.


## Voorvertoning van gemengde mediasets {#previewing-mixed-media-sets}

Zie [Elementen voorvertonen](previewing-assets.md) voor meer informatie over het voorvertonen van gemengde mediasets.

## Gemengde mediasets {#publishing-mixed-media-sets} publiceren

Zie [Elementen publiceren](publishing-dynamicmedia-assets.md) voor meer informatie over het publiceren van gemengde Mediasets.

>[!NOTE]
>
>Als de gemengde Det van Media niet volledig in de leveringsdienst belandt de eerste keer u het publiceert, kunt u de gemengde media reeks een tweede keer moeten publiceren.
