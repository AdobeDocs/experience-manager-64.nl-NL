---
title: Mixed Media Sets
description: Leer hoe u in Dynamic Media werkt met gemengde mediasets (afbeeldingen, afbeeldingssets, centrifuges en video's).
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
exl-id: 252c1a50-17ac-4412-88d6-49bb6850658d
feature: Mixed Media Sets
role: User
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1424'
ht-degree: 17%

---

# Mixed Media Sets {#mixed-media-sets}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Met gemengde mediasets kunt u in één presentatie een combinatie van afbeeldingen, afbeeldingssets, centrifuges en video&#39;s aanbieden.

Gemengde mediasets worden aangegeven door een banner met het woord **[!UICONTROL MixedMediaSet]**. Als de gemengde mediaset wordt gepubliceerd, wordt bovendien de publicatiedatum, die door het pictogram **[!UICONTROL World]** wordt aangegeven, samen met de laatste wijzigingsdatum op de banner weergegeven. Dit wordt aangegeven door het pictogram **[!UICONTROL Pencil]**.

![chlimage_1-348](assets/chlimage_1-348.png)

>[!NOTE]
>
>Voor informatie over de gebruikersinterface van Middelen raadpleegt u [Elementen beheren met de Touch UI](managing-assets-touch-ui.md).

## Snel starten: Gemengde mediasets {#quick-start-mixed-media-sets}

Ga als volgt te werk om snel aan de slag te gaan met gemengde mediasets:

1. [Uw elementen uploaden](#uploading-assets).

   Begin door de afbeeldingen en video&#39;s voor uw gemengde mediasets te uploaden. Maak indien nodig uw eigen [afbeeldingsets](image-sets.md) en [spinsets](spin-sets.md). Omdat gebruikers kunnen inzoomen op afbeeldingen in de viewer voor gemengde mediasets, moet u rekening houden met zoomen wanneer u afbeeldingen kiest. Zorg ervoor dat de afbeeldingen ten minste 2000 pixels groot zijn in de grootste dimensie.

1. [Gemengde mediasets maken.](#creating-mixed-media-sets)

   Om een Gemengde Reeks van Media tot stand te brengen, van **[!UICONTROL Assets]** pagina, tikken **[!UICONTROL Create > Mixed Media Set]** en geef de set een naam. Kies de elementen en kies de volgorde waarin de afbeeldingen worden weergegeven.

   Zie [Werken met kiezers.](working-with-selectors.md)

1. Instellen [Voorinstellingen voor gemengde media-viewer](managing-viewer-presets.md), indien nodig.

   Beheerders kunnen viewervoorinstellingen voor gemengde mediasets maken of wijzigen. Als u de gemengde media met een viewervoorinstelling wilt weergeven, selecteert u de gemengde mediaset en selecteert u **[!UICONTROL Viewers]** in de vervolgkeuzelijst van het linkerspoor.

   Zie **[!UICONTROL Tools > Assets > Viewer Presets]** om viewervoorinstellingen te maken of te bewerken.

   Zie [Voorinstellingen voor viewers toevoegen en bewerken.](managing-viewer-presets.md)

1. [Voorvertoning gemengde mediasets.](#previewing-mixed-media-sets)

   Selecteer de gemengde Mediaset en u kunt er een voorvertoning van weergeven. Klik op de miniatuurpictogrammen om de gemengde mediaset in de geselecteerde viewer te bekijken. U kunt verschillende Viewers kiezen in het menu **[!UICONTROL Viewers]** beschikbaar via het keuzemenu voor de linkertrack.

1. [Gemengde mediasets publiceren.](#publishing-mixed-media-sets)

   Wanneer u een gemengde mediaset publiceert, worden de URL en de insluitreeks geactiveerd. Bovendien moet u [De viewervoorinstelling publiceren](managing-viewer-presets.md#publishing-viewer-presets).

1. [URL&#39;s koppelen aan uw webtoepassing](linking-urls-to-yourwebapplication.md) of [De video- of afbeeldingsviewer insluiten](embed-code.md).

   AEM Assets maakt URL-aanroepen voor gemengde mediasets en activeert deze nadat u de gemengde mediasets hebt gepubliceerd. U kunt deze URL&#39;s kopiëren wanneer u elementen voorvertoont. U kunt ze ook insluiten op uw website.

   Selecteer de Gemengde Reeks van Media, dan in het linkerspoordrop-down menu, uitgezocht **[!UICONTROL Viewers]**.

   Zie [Een gemengde mediaset koppelen aan een webpagina](linking-urls-to-yourwebapplication.md) en [De video- of afbeeldingsviewer insluiten](embed-code.md).

Indien nodig kunt u [Gemengde mediasets](#editing-mixed-media-sets). Bovendien kunt u bekijken en wijzigen [Eigenschappen van gemengde mediaset](managing-assets-touch-ui.md#editing-properties).

>[!NOTE]
>
>Als u problemen ondervindt bij het maken van sets, raadpleegt u [Problemen oplossen in de modus Dynamic Media - Scene7](troubleshoot-dms7.md).

## Elementen uploaden {#uploading-assets}

Begin door de afbeeldingen en video&#39;s voor uw gemengde mediasets te uploaden. Omdat gebruikers kunnen inzoomen op afbeeldingen in de gemengde Media Set Viewer, dient u rekening te houden met zoomen wanneer u afbeeldingen kiest. Zorg ervoor dat de afbeeldingen ten minste 2000 pixels groot zijn in de grootste dimensie.

Als u bovendien centrifuges of afbeeldingssets wilt toevoegen aan de gemengde mediaset, maakt u deze ook.

## Gemengde mediasets maken {#creating-mixed-media-sets}

U kunt afbeeldingen, afbeeldingssets, centrifuges en video&#39;s toevoegen aan de gemengde mediaset. Zorg ervoor dat de bestanden, afbeeldingssets en centrifuges klaar zijn om te worden gepubliceerd voordat u ze aan de gemengde mediaset toevoegt.

Wanneer u elementen aan de set toevoegt, worden deze automatisch in alfanumerieke volgorde toegevoegd. U kunt elementen handmatig opnieuw ordenen of sorteren nadat u ze hebt toegevoegd.

**Een gemengde mediaset maken**:

1. Navigeer in Elementen naar de plaats waar u een gemengde mediaset wilt maken en klik op **Maken** en selecteert u **[!UICONTROL Mixed Media Set]**. U kunt de set ook maken vanuit een map die uw assets bevat.

   ![chlimage_1-349](assets/chlimage_1-349.png)

1. In de **[!UICONTROL Mixed Media Set Editor]** pagina, in **[!UICONTROL Title]**, ga een naam voor de Gemengde Reeks van Media in. De naam wordt in de banner weergegeven in de gemengde mediaset. Voer eventueel een beschrijving in.

   ![chlimage_1-350](assets/chlimage_1-350.png)

   >[!NOTE]
   >
   >Wanneer u de gemengde mediaset maakt, kunt u de miniatuur van de gemengde mediaset wijzigen of AEM de miniatuur automatisch selecteren op basis van de elementen in de gemengde mediaset. Als u een miniatuur wilt selecteren, klikt u op **[!UICONTROL Change thumbnail]** en selecteert u een willekeurige afbeelding (u kunt ook naar andere mappen navigeren om afbeeldingen te zoeken). Als u een miniatuur hebt geselecteerd en vervolgens wilt bepalen dat u een miniatuur AEM genereren op basis van de gemengde mediaset, selecteert u **[!UICONTROL Switch to Automatic thumbnail]**.

1. Tik op de knop **[!UICONTROL Asset Selector]** om elementen te selecteren die u wilt opnemen in de gemengde mediaset. Selecteer ze en tik erop **[!UICONTROL Select]**.

   Met de **[!UICONTROL Asset Selector]**, kunt u naar elementen zoeken door een trefwoord in te voeren en te tikken **[!UICONTROL Return]**. U kunt ook filters toepassen om de zoekresultaten te verfijnen. U kunt filteren op pad, verzameling, bestandstype en tag. Selecteer het filter en tik op het pictogram **[!UICONTROL Filter]** op de werkbalk. De weergave wijzigen door het pictogram Weergave te selecteren en **[!UICONTROL List]**, **[!UICONTROL Column]**, of **[!UICONTROL Card]** weergeven.

   Zie [Werken met kiezers](working-with-selectors.md).

   ![chlimage_1-351](assets/chlimage_1-351.png)

1. Wijzig de volgorde van de elementen door deze omhoog of omlaag in de lijst te slepen (selecteer het pictogram voor opnieuw ordenen).

   ![chlimage_1-352](assets/chlimage_1-352.png)

   Als u miniaturen wilt toevoegen, klikt u op de knop **[!UICONTROL +]** naast de afbeelding en navigeer naar de gewenste miniatuur. Tik wanneer u klaar bent met het selecteren van alle miniatuurafbeeldingen op **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Tik op elementen als u elementen wilt toevoegen **[!UICONTROL Add Asset]**.

1. Als u een element wilt verwijderen, schakelt u het desbetreffende selectievakje in en tikt u op **[!UICONTROL Delete Asset]**.
1. Tik op een voorinstelling om deze toe te passen **[!UICONTROL Preset]** in de rechterbovenhoek en selecteert u een voorinstelling die u op de elementen wilt toepassen.
1. Klik op **[!UICONTROL Save]**. De nieuwe gemengde mediaset wordt weergegeven in de map waarin u deze hebt gemaakt.

## Gemengde mediasets bewerken {#editing-mixed-media-sets}

U kunt diverse bewerkingstaken rechtstreeks in de gebruikersinterface uitvoeren op elementen in gemengde mediasets [zoals u elk element in Elementen](managing-assets-touch-ui.md). U kunt ook de volgende handelingen uitvoeren in Gemengde Mediasets:

* Voeg elementen toe aan de gemengde mediaset.
* Wijzig de volgorde van elementen in de gemengde mediaset.
* Elementen verwijderen uit de gemengde mediaset.
* Voorinstellingen voor viewers toepassen.
* Wijzig de standaardminiatuur.

**Gemengde mediasets bewerken**:

1. Voer een van de volgende handelingen uit:

   * Houd de muisaanwijzer boven een element uit een gemengde mediaset en tik vervolgens op **[!UICONTROL Edit]** (potloodpictogram).
   * Houd de muisaanwijzer boven een element uit een gemengde mediaset en tik op **[!UICONTROL Select]** (vinkje pictogram), tikt u vervolgens op **[!UICONTROL Edit]** op de werkbalk.
   * Tik op een element uit een gemengde mediaset en tik vervolgens op **[!UICONTROL Edit]** (potloodpictogram) op de werkbalk.

1. Voer in de Editor gemengde mediaset een van de volgende handelingen uit:

   * Tik op **[!UICONTROL Assets]** (Afbeeldingspictogram), sleept u een element naar een nieuwe locatie.
   * Tik op de werkbalk om elementen toe te voegen **[!UICONTROL Add Asset]**. Navigeer naar de elementen. Tik op het pictogram van het vinkje voor elk element dat u wilt toevoegen. Houd de muisaanwijzer boven de afbeelding van het element (niet de naam van het element). Tik in de rechterbovenhoek op **[!UICONTROL Select]**.
   * Tik in het linkerdeelvenster op een element om dit te verwijderen **[!UICONTROL Assets]** (Afbeeldingspictogram) en selecteer vervolgens het element. Tik op de werkbalk **[!UICONTROL Delete Asset]**.
   * Tik in het linkerdeelvenster op **[!UICONTROL Assets]** (afbeeldingspictogram). Rechts van het **[!UICONTROL Assets]** tikt u op de pictogrammen voor het inlasteken omhoog of omlaag.

   >[!NOTE]
   >
   >* Om een volledige Gemengde Reeks van Media te schrappen, van om het even welke het bekijken wijze (zoals **[!UICONTROL Card]** of **[!UICONTROL Column]** (weergave) navigeert u naar de gemengde mediaset. Wijs de asset aan en tik op het vinkje om deze te selecteren. Druk **[!UICONTROL Backspace]** op het toetsenbord, of tik **[!UICONTROL More]** (drie punten) op de werkbalk tikken **[!UICONTROL Delete]**.
   >* U kunt de elementen in een gemengde mediaset bewerken door naar de set te navigeren en te tikken **[!UICONTROL Set Members]** in de linkerspoorstaaf, en dan het tikken van **[!UICONTROL Pencil]** op een afzonderlijk element om het bewerkingsvenster te openen.


1. Tikken **[!UICONTROL Save]** wanneer u klaar bent met bewerken.

   >[!NOTE]
   >
   >* Als u de assets in een gemengde mediaset wilt bewerken, gaat u naar de gemengde mediaset. Tik (niet selecteren) op de set om deze te openen in de AEM **[!UICONTROL Set Preview]** pagina. Tik in het linkerspoor op het inlasteken om de vervolgkeuzelijst te openen en tik vervolgens op **[!UICONTROL Set Members]**. In de **[!UICONTROL Set Members]** pagina, houd de muisaanwijzer boven een element en tik vervolgens op **[!UICONTROL Edit]** (potloodpictogram) om de bewerkingspagina te openen.
   >* Om een volledige Gemengde Reeks van Media te schrappen - van om het even welke het bekijken wijze (zoals **[!UICONTROL Card]** of **[!UICONTROL Column]** (weergave), navigeert u naar de gemengde mediaset. Druk op de set en tik vervolgens op **[!UICONTROL Select]** (vinkje). Druk **[!UICONTROL Backspace]** op uw toetsenbord, of tik **[!UICONTROL More]** (rij met drie punten), tikt u vervolgens op **[!UICONTROL Delete]**.


## Voorvertoning van gemengde mediasets {#previewing-mixed-media-sets}

Zie [Elementen voorvertonen](previewing-assets.md) voor meer informatie over hoe u een voorvertoning van gemengde mediasets kunt weergeven.

## Gemengde mediasets publiceren {#publishing-mixed-media-sets}

Zie [Middelen publiceren](publishing-dynamicmedia-assets.md) voor details over hoe te om Gemengde Reeksen van Media te publiceren.

>[!NOTE]
>
>Als de gemengde Det van Media niet volledig in de leveringsdienst belandt de eerste keer u het publiceert, kunt u de gemengde media reeks een tweede keer moeten publiceren.
