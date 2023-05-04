---
title: Image Sets
seo-title: Image Sets
description: Leer hoe u met afbeeldingssets werkt in dynamische media
seo-description: Learn how to work with image sets in dynamic media
uuid: 16008278-f59f-4fa8-90e9-19c78f132439
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
discoiquuid: e00e7cc9-b777-4f9e-906d-824bcb2bbd41
exl-id: af3f95aa-a162-4212-a20a-68b5a0e72d6d
feature: Image Sets
role: User
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '2100'
ht-degree: 10%

---

# Image Sets {#image-sets}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Afbeeldingssets bieden gebruikers een geïntegreerde weergave, waarbij gebruikers verschillende weergaven van een item kunnen zien door op een miniatuurafbeelding te klikken. Met Afbeeldingssets kunt u alternatieve weergaven van een item presenteren en de viewer beschikt over zoomgereedschappen waarmee u afbeeldingen op de juiste wijze kunt bekijken.

Afbeeldingsets worden aangegeven door een banner met het woord **[!UICONTROL IMAGESET]**. Als de afbeeldingset wordt gepubliceerd, wordt bovendien de publicatiedatum, die door het pictogram **[!UICONTROL World]** wordt aangegeven, samen met de laatste wijzigingsdatum op de banner weergegeven. Dit wordt aangegeven door het pictogram **[!UICONTROL Pencil]**.

![chlimage_1-339](assets/chlimage_1-339.png)

In de afbeeldingsset kunt u ook stalen maken door een afbeeldingsset te maken en miniaturen toe te voegen.

Deze toepassing is vooral handig wanneer u een item in een andere kleur, in een ander patroon of in een ander patroon wilt weergeven. Als u een afbeeldingsset met kleurstalen wilt maken, hebt u één afbeelding nodig voor elke andere kleur, elk patroon of elke afwerking die u aan de gebruikers wilt presenteren. Voor elke kleur, elk patroon of elke afwerking hebt u ook één kleur-, patroon- of eindstaal nodig.

Stel dat u afbeeldingen van uiteinden met verschillende kleurrekeningen wilt weergeven. de rekeningen zijn rood , groen en blauw . In dit geval hebt u drie opnamen van hetzelfde kapje nodig. Je hebt een opname nodig met een rood, een met een groen en een met een blauwe rekening. U hebt ook een rood, groen en blauw kleurenstaal nodig. De kleurstalen fungeren als de miniaturen die gebruikers in de Staalset-viewer klikken om het rode, groene of blauwe kader met vulling weer te geven.

>[!NOTE]
>
>Voor informatie over de gebruikersinterface van Middelen raadpleegt u [Elementen beheren met de Touch UI](managing-assets-touch-ui.md).

Wanneer u een Reeks van het Beeld creeert, adviseert Adobe de volgende beste praktijken en handhaaft de volgende grenzen:

| Type limiet | Beste praktijken | Oplegde limiet |
| --- | --- | --- |
| Aantal dubbele elementen per set | Geen duplicaten | 20 |
| Maximumaantal afbeeldingen per set | 5-10 afbeeldingen per set | 1000 |

Zie ook [Dynamic Media-beperkingen](/help/assets/limitations.md).

## Snel starten: Afbeeldingssets {#quick-start-image-sets}

Zo kunt u snel aan de slag:

1. [Upload uw primaire afbeeldingen voor meerdere weergaven.](#uploading-assets-in-image-sets)

   Begin door de beelden voor uw Reeksen van het Beeld te uploaden. Omdat gebruikers kunnen inzoomen op afbeeldingen in de Vastgestelde Kijker van het Beeld, houd rekening met het zoemen wanneer u beelden kiest. Zorg ervoor dat de afbeeldingen ten minste 2000 pixels groot zijn voor optimale zoomdetails. Dynamic Media kan afbeeldingen renderen tot 25 megapixels per pixel. U kunt bijvoorbeeld een afbeelding van 5000 x 5000 megapixel of een andere formaatcombinatie van maximaal 25 megapixels gebruiken.

   AEM Assets ondersteunt veel bestandsindelingen voor afbeeldingen, maar TIFF-, PNG- en EPS-afbeeldingen zonder gegevensverlies worden aanbevolen.

1. [Afbeeldingssets maken.](#creating-image-sets)

   In de Reeksen van het Beeld, klikken de gebruikers duimnagelbeelden in de Vastgestelde Kijker van het Beeld.

   Tik op **[!UICONTROL Create > Image Sets]**. Voeg vervolgens afbeeldingen toe en tik op **[!UICONTROL Save]**.

   U kunt ook automatisch afbeeldingssets maken via [voorinstellingen voor batchsets](/help/assets/config-dms7.md#creating-batch-set-presets-to-auto-generate-image-sets-and-spin-sets).

   **Belangrijk** — Batchsets worden door het IPS (Image Production System) gemaakt als onderdeel van het opnemen van bedrijfsmiddelen en zijn alleen beschikbaar in de Dynamic Media-Scene7-modus.

   Zie [Afbeeldingsset-elementen voorbereiden voor het uploaden en uploaden van uw bestanden](#uploading-assets-in-image-sets).

   Zie [Werken met kiezers.](working-with-selectors.md)

1. Toevoegen [Voorinstellingen voor Afbeeldingsset viewer](managing-viewer-presets.md), indien nodig.

   Beheerders kunnen afbeeldingen maken of wijzigen **[!UICONTROL Set Viewer Presets]**. Als u de afbeeldingsset wilt weergeven met een viewervoorinstelling, selecteert u de afbeeldingsset en selecteert u in de vervolgkeuzelijst voor de linkertrack de optie **[!UICONTROL Viewers]**.

   Zie **[!UICONTROL Tools > Assets > Viewer Presets]** om viewervoorinstellingen te maken of te bewerken.

1. (Optioneel) [Afbeeldingssets weergeven](image-sets.md#viewing-image-sets) die zijn gemaakt met behulp van voorinstellingen voor batchsets.
1. [Voorvertoning van afbeeldingssets.](previewing-assets.md)

   Selecteer de Afbeeldingsset en u kunt er een voorvertoning van weergeven. Tik op de miniatuurpictogrammen om de Afbeeldingsset in de geselecteerde viewer te bekijken. U kunt verschillende viewers kiezen in het menu **[!UICONTROL Viewers]** beschikbaar via het keuzemenu voor de linkertrack.

1. [Afbeeldingssets publiceren.](publishing-dynamicmedia-assets.md)

   Als u een Afbeeldingsset publiceert, wordt de URL- en insluitreeks geactiveerd. Bovendien moet u [een aangepaste viewervoorinstelling publiceren](managing-viewer-presets.md) die u hebt gemaakt. Voorinstellingen voor viewers buiten de box zijn al gepubliceerd.

1. [URL&#39;s koppelen aan uw webtoepassing](linking-urls-to-yourwebapplication.md) of [De video- of afbeeldingsviewer insluiten](embed-code.md).

   AEM Assets maakt URL-aanroepen voor afbeeldingssets en activeert deze nadat u de afbeeldingssets hebt gepubliceerd. U kunt deze URL&#39;s kopiëren wanneer u elementen voorvertoont. U kunt ze ook insluiten op uw website.

   Selecteer de Afbeeldingset en selecteer vervolgens in de vervolgkeuzelijst voor het linkerspoor **[!UICONTROL Viewers]**.

   Zie [Een afbeeldingset koppelen aan een webpagina](linking-urls-to-yourwebapplication.md) en [De video- of afbeeldingsviewer insluiten](embed-code.md).

Als u Afbeeldingssets wilt bewerken, raadpleegt u [Beeldsets bewerken.](#editing-image-sets) Bovendien kunt u [Eigenschappen van Afbeeldingsset](managing-assets-touch-ui.md#editing-properties).

Als u problemen ondervindt bij het maken van sets, raadpleegt u Afbeeldingen en sets in [Problemen oplossen in de modus Dynamic Media - Scene7](troubleshoot-dms7.md#images-and-sets).

## Elementen uploaden in afbeeldingssets {#uploading-assets-in-image-sets}

Begin door de beelden voor uw Reeksen van het Beeld te uploaden. Omdat gebruikers kunnen inzoomen op afbeeldingen in de Vastgestelde Kijker van het Beeld, houd rekening met het zoemen wanneer u beelden kiest. Zorg ervoor dat de afbeeldingen ten minste 2000 pixels groot zijn in de grootste dimensie. Afbeeldingssets ondersteunen veel indelingen voor afbeeldingsbestanden, maar afbeeldingen zonder verlies van TIFF, PNG en EPS worden aanbevolen.

U kunt afbeeldingen voor Afbeeldingssets uploaden zoals u [andere elementen in Elementen uploaden](managing-assets-touch-ui.md#uploading-assets).

### Afbeeldingsset-elementen voorbereiden voor uploaden {#preparing-image-set-assets-for-upload}

Voordat u Afbeeldingssets maakt, moet u ervoor zorgen dat de afbeeldingen de juiste grootte en indeling hebben.

Als u een Afbeeldingsset met meerdere weergaven wilt maken, hebt u afbeeldingen nodig die een item vanuit verschillende gezichtspunten weergeven of verschillende aspecten van hetzelfde item weergeven. Het doel is om de belangrijke kenmerken van een item te benadrukken, zodat gebruikers een volledig beeld hebben van hoe het eruit ziet of werkt.

Omdat gebruikers kunnen inzoomen op afbeeldingen in Afbeeldingssets, moet u ervoor zorgen dat de afbeeldingen ten minste 2000 pixels groot zijn. Elementen bieden ondersteuning voor veel bestandsindelingen voor afbeeldingen, maar TIFF-, PNG- en EPS-afbeeldingen zonder gegevensverlies worden aanbevolen.

>[!NOTE]
>
>Als u miniaturen gebruikt om productstalen aan te geven, moet u het volgende doen:
>
>U hebt vignetten of verschillende opnamen van dezelfde afbeelding nodig die deze in verschillende kleuren, patronen of afwerkingen weergeven. U hebt ook miniatuurbestanden nodig die overeenkomen met de verschillende kleuren, patronen of afwerkingen. Als u bijvoorbeeld miniaturen wilt weergeven met een Afbeeldingsset die hetzelfde jasje in zwart, bruin en groen toont, hebt u het volgende nodig:
>
>* Een zwarte, bruine en groene opname van hetzelfde jasje.
>* Een zwarte, bruine en groene kleurminiatuur.
>


## Afbeeldingssets maken {#creating-image-sets}

U kunt Afbeeldingssets maken via de gebruikersinterface of via de API. In deze sectie wordt beschreven hoe u Afbeeldingssets maakt in de gebruikersinterface.

>[!NOTE]
>
>U kunt ook automatisch afbeeldingssets maken via [voorinstellingen voor batchsets](/help/assets/config-dms7.md#creating-batch-set-presets-to-auto-generate-image-sets-and-spin-sets).

**Belangrijk:** Batchsets worden gemaakt door het IPS (Image Production System) als onderdeel van het opnemen van elementen en zijn alleen beschikbaar in de Dynamic Media-Scene7-modus.

Wanneer u elementen aan de set toevoegt, worden deze automatisch in alfanumerieke volgorde toegevoegd. U kunt elementen handmatig opnieuw ordenen of sorteren nadat u ze hebt toegevoegd.

>[!NOTE]
>
>Afbeeldingssets worden niet ondersteund voor elementen met `,` (komma) in de bestandsnaam.

Wanneer u een Reeks van het Beeld creeert, adviseert Adobe de volgende beste praktijken en handhaaft de volgende grenzen:

| Type limiet | Beste praktijken | Oplegde limiet |
| --- | --- | --- |
| Aantal dubbele elementen per set | Geen duplicaten | 20 |
| Maximumaantal afbeeldingen per set | 5-10 afbeeldingen per set | 1000 |

Zie ook [Dynamic Media-beperkingen](/help/assets/limitations.md).

**Een afbeeldingsset maken**:

1. In **Activa** navigeer naar de plaats waar u een afbeeldingsset wilt maken en tik op **[!UICONTROL Create]** en selecteert u **[!UICONTROL Image Set]**. U kunt de set ook maken vanuit een map die uw assets bevat.

   ![chlimage_1-340](assets/chlimage_1-340.png)

1. Op de pagina van de Editor van de Afbeeldingsset, in het dialoogvenster **[!UICONTROL Title]** voert u een naam in voor de afbeeldingsset. De naam wordt weergegeven in de banner in de Afbeeldingsset. Voer eventueel een beschrijving in.

   ![chlimage_1-341](assets/chlimage_1-341.png)

   >[!NOTE]
   >
   >Wanneer u de afbeeldingset maakt, kunt u de miniatuur van de afbeeldingset wijzigen of AEM toestaan de miniatuur automatisch te selecteren op basis van de assets in de afbeeldingset. Tik op een miniatuur om deze te selecteren **[!UICONTROL Change thumbnail]** en selecteert u een willekeurige afbeelding (u kunt ook naar andere mappen navigeren om afbeeldingen te zoeken). Als u een miniatuur hebt geselecteerd en vervolgens besluit dat AEM een miniatuur moet genereren op basis van de afbeeldingset, selecteert u **[!UICONTROL Switch to Automatic thumbnail]**.

1. Voer een van de volgende handelingen uit:

   * In de linkerbovenhoek van het dialoogvenster **[!UICONTROL Image Set Editor]** pagina, tikken **[!UICONTROL Add Asset]**.
   * In het midden van de **[!UICONTROL Image Set Editor]** pagina, tikken **[!UICONTROL Tap to open Asset Selector]**.

   Tik om elementen te selecteren die u in de afbeeldingsset wilt opnemen. Geselecteerde assets hebben een vinkje. Tik in de rechterbovenhoek van de pagina op **[!UICONTROL Select]**.

   Met de assetkiezer kunt u naar assets zoeken door een trefwoord te typen en op **[!UICONTROL Return]** te tikken. U kunt ook filters toepassen om de zoekresultaten te verfijnen. U kunt filteren op pad, verzameling, bestandstype en tag. Selecteer het filter en tik op het pictogram **[!UICONTROL Filter]** op de werkbalk. Wijzig de weergave door op de knop **[!UICONTROL View]** pictogram en selecteren **[!UICONTROL Column View]**, **[!UICONTROL Card View]**, of **[!UICONTROL List View]**.

   Zie [Werken met kiezers.](working-with-selectors.md)

   ![chlimage_1-342](assets/chlimage_1-342.png)

1. Wanneer u elementen aan de set toevoegt, worden deze automatisch in alfanumerieke volgorde toegevoegd. Nadat u elementen hebt toegevoegd, kunt u deze handmatig opnieuw ordenen of sorteren.

   Indien nodig, sleept u elementen **[!UICONTROL Reorder]** rechts van de bestandsnaam van het element om de volgorde van de afbeeldingen in de lijst met sets te wijzigen.

   ![spin_set_assets](assets/spin_set_assets.png)

   Tik op de knop **[!UICONTROL Thumbnail]** naast de afbeelding en navigeer naar de gewenste miniatuur of staal. Tik, als u klaar bent, op alle afbeeldingen **[!UICONTROL Save]**.

1. (Optioneel) Voer een van de volgende handelingen uit:

   * Als u een afbeelding wilt verwijderen, selecteert u de afbeelding en tikt u op **[!UICONTROL Delete Asset]**.
   * Tik op **[!UICONTROL Preset]** Selecteer vervolgens een voorinstelling die u op alle elementen tegelijk wilt toepassen.

1. Tik op **[!UICONTROL Save]**. De nieuwe afbeeldingsset wordt weergegeven in de map waarin u deze hebt gemaakt.

## Afbeeldingssets weergeven {#viewing-image-sets}

U kunt afbeeldingssets maken in de gebruikersinterface of automatisch met [voorinstellingen voor batchsets](/help/assets/config-dms7.md#creating-batch-set-presets-to-auto-generate-image-sets-and-spin-sets).

**Belangrijk** — De reeksen van de partij worden gecreeerd door IPS [Afbeeldingsproductiesysteem] als onderdeel van het opnemen van activa en zijn alleen beschikbaar in de Dynamic Media-Scene7-modus.)

sets die zijn gemaakt met voorinstellingen voor batchsets, doen *niet* worden weergegeven in de gebruikersinterface. U kunt deze sets op drie verschillende manieren weergeven. (Deze methoden zijn ook beschikbaar als u de afbeeldingssets in de gebruikersinterface hebt gemaakt.)

* Bij het openen van de eigenschappen van een afzonderlijk element. Eigenschappen geven aan wat de instelling is van het geselecteerde element (onder) **[!UICONTROL Member of Sets]**). Tik op de naam van de set om de volledige set weer te geven.

   ![chlimage_1-343](assets/chlimage_1-343.png)

* Van een lidafbeelding van om het even welke set. Selecteer **[!UICONTROL Sets]** om de sets weer te geven waarvan het element lid is.

   ![chlimage_1-344](assets/chlimage_1-344.png)

* Van onderzoek, kunt u selecteren **[!UICONTROL Filters]** vervolgens uitvouwen **[!UICONTROL Dynamic Media]** en selecteert u **[!UICONTROL Sets]**.

   De zoekopdracht retourneert overeenkomende sets die handmatig in de gebruikersinterface zijn gemaakt of die automatisch zijn gemaakt met voorinstellingen voor batchsets. Voor geautomatiseerde reeksen, wordt de onderzoeksvraag geleid gebruikend &quot;Begint met&quot;onderzoekscriteria die van AEM onderzoek verschillend zijn dat op het gebruiken van &quot;bevat&quot;onderzoekscriteria gebaseerd is. Het filter instellen op **[!UICONTROL Sets]** is de enige manier om geautomatiseerde reeksen te zoeken.

   ![chlimage_1-345](assets/chlimage_1-345.png)

>[!NOTE]
>
>U kunt sets weergeven in de gebruikersinterface zoals beschreven in [Afbeeldingssets bewerken](#editing-image-sets).

## Afbeeldingssets bewerken {#editing-image-sets}

U kunt diverse bewerkingstaken uitvoeren op Afbeeldingssets, zoals:

* Voeg afbeeldingen toe aan de Afbeeldingsset.
* Wijzig de volgorde van de afbeeldingen in de set Afbeeldingen.
* Elementen in de afbeeldingsset verwijderen.
* Voorinstellingen voor viewers toepassen.
* Verwijder de afbeeldingsset.

**Afbeeldingssets bewerken**:

1. Voer een van de volgende handelingen uit:

   * Houd de muisaanwijzer boven een afbeeldingsset en tik vervolgens op **[!UICONTROL Edit]** (potloodpictogram).
   * Houd de muisaanwijzer boven een afbeeldingsset en tik op **[!UICONTROL Select]** (vinkje pictogram), tikt u vervolgens op **[!UICONTROL Edit]** op de werkbalk.
   * Tik op een Image Set-element en tik vervolgens op **[!UICONTROL Edit]** (potloodpictogram) op de werkbalk.

1. Voer een van de volgende handelingen uit om de afbeeldingen in de Afbeeldingsset te bewerken:

   * Als u elementen opnieuw wilt rangschikken, sleept u een afbeelding naar een nieuwe locatie (selecteer het pictogram voor opnieuw ordenen om items te verplaatsen).
   * Tik op de kolomkop om items in oplopende of aflopende volgorde te sorteren.
   * Tik op de knop **[!UICONTROL Add Asset]**. Navigeren naar een element, dit selecteren en vervolgens tikken **[!UICONTROL Select]** in de rechterbovenhoek van de pagina.

   >[!NOTE]
   >Als u de afbeelding verwijdert die AEM gebruikt voor de miniatuur door deze te vervangen door een andere afbeelding, wordt het oorspronkelijke element nog steeds weergegeven.

   * Als u een element wilt verwijderen, selecteert u het en tikt u op **[!UICONTROL Delete Asset]**.
   * Tik op **[!UICONTROL Preset]** selecteert u vervolgens een viewervoorinstelling.
   * Als u een miniatuur wilt toevoegen of wijzigen, selecteert u het miniatuurpictogram rechts van het element. Navigeer naar de nieuwe miniatuur of het nieuwe stalenelement, selecteer het en tik op **[!UICONTROL Select]**.
   * Als u een hele afbeeldingsset wilt verwijderen, navigeert u naar de afbeeldingsset, selecteert u deze en tikt u op **[!UICONTROL Delete]**.

   >[!NOTE]
   >
   >U kunt de afbeeldingen in een Afbeeldingsset bewerken door naar de set te navigeren en te tikken **[!UICONTROL Set Members]** in de linkerspoorstaaf en tik vervolgens op de **[!UICONTROL Pencil]** op een afzonderlijk element om het bewerkingsvenster te openen.

1. Tikken **[!UICONTROL Save]** wanneer u klaar bent met bewerken.

## Voorvertoning van afbeeldingssets {#previewing-image-sets}

Zie [Elementen voorvertonen](previewing-assets.md).

## Afbeeldingssets publiceren {#publishing-image-sets}

Zie [Middelen publiceren](publishing-dynamicmedia-assets.md).
