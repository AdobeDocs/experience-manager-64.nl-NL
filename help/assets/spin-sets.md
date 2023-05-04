---
title: Spin Sets
description: Leer hoe u met centrifuges werkt in Dynamic Media. Een centrifugeerset simuleert de echte handeling waarbij een object vanuit elke hoek wordt gedraaid om het te bekijken.
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
exl-id: 47cb6d40-a5c4-4f6a-9794-bd2eddfaa7d0
feature: Spin Sets
role: User
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1876'
ht-degree: 6%

---

# Spin Sets {#spin-sets}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Een centrifugeerset simuleert de echte handeling waarbij een object wordt omgedraaid om het te onderzoeken. Met centrifuges kunt u items vanuit elke hoek bekijken en de belangrijkste visuele details vanuit elke hoek ophalen.

Een centrifugeerset simuleert een kijkervaring van 360 graden. Dynamic Media biedt centrifugesets met één as waarin gebruikers een item kunnen roteren. Bovendien kunnen gebruikers met een paar eenvoudige muisklikken in- en uitzoomen op een vrije vorm en een willekeurige weergave pannen. Op deze manier kunnen gebruikers een item vanuit een bepaald gezichtspunt nader onderzoeken.

De Reeksen van de draaien worden aangewezen door een banner met het woord **[!UICONTROL SPINSET]**. Als de Spin-set wordt gepubliceerd, wordt bovendien de publicatiedatum vermeld door de **[!UICONTROL World]** het pictogram bevindt zich op de banner samen met de laatste wijzigingsdatum die wordt aangegeven door de **[!UICONTROL Pencil]** wordt weergegeven.

![chlimage_1-380](assets/chlimage_1-380.png)

>[!NOTE]
>
>Voor informatie over de gebruikersinterface van Middelen raadpleegt u [Elementen beheren met de Touch UI](managing-assets-touch-ui.md).

Wanneer u een reeks van de Rotatie creeert, adviseert Adobe de volgende beste praktijken en handhaaft de volgende grens:

| Type limiet | Beste praktijken | Oplegde limiet |
| --- | --- | --- |
| Maximumaantal rijen/kolommen per 2D-set | 12-18 afbeeldingen per set | 1000 |

Zie ook [Dynamic Media-beperkingen](/help/assets/limitations.md).

## Snel starten: Sets draaien {#quick-start-spin-sets}

Volg deze workflow om snel weer aan de slag te gaan met centrifuges:

1. [Upload uw afbeeldingen voor meerdere weergaven.](#uploading-assets-for-spin-sets)

   U hebt minstens 8-12 opnamen van een item nodig voor een eendimensionale centrifugeset en 16-24 voor een tweedimensionale centrifugeset. De opnamen moeten regelmatig worden gemaakt om de indruk te wekken dat het item draait en wordt gespiegeld. Als een eendimensionale centrifugeset bijvoorbeeld 12 opnamen bevat, roteert u het item 30 graden (360/12) voor elke opname.

1. [Spin-sets maken.](#creating-spin-sets)

   Selecteer **[!UICONTROL Create > Spin Set]** en geef de set vervolgens een naam, kies de elementen en sorteer de afbeeldingen in de volgorde waarin ze worden weergegeven.

   Zie [Werken met kiezers](working-with-selectors.md).

   >[!NOTE]
   >
   >U kunt ook automatisch centrifuges maken [voorinstellingen voor batchsets](/help/assets/config-dms7.md#creating-batch-set-presets-to-auto-generate-image-sets-and-spin-sets).
   >
   >*Batchsets worden gemaakt door het IPS (Image Production System) als onderdeel van het opnemen van bedrijfsmiddelen en zijn alleen beschikbaar in de modus Dynamic Media - Scene7*.

1. Instellen [Voorinstellingen van viewer voor centrifugeren instellen](managing-viewer-presets.md), indien nodig.

   Beheerders kunnen voorinstellingen voor de voorinstelling Spin Set Viewer maken of wijzigen. Als u de centrifugeset wilt weergeven met een viewervoorinstelling, selecteert u de centrifugeset en selecteert u in de vervolgkeuzelijst voor de linkertrack de optie **[!UICONTROL Viewers]**.

   Zie **[!UICONTROL Tools > Assets > Viewer Presets]** om viewervoorinstellingen te maken of te bewerken.

   Zie [Voorinstellingen voor viewers toevoegen en bewerken.](managing-viewer-presets.md)

1. [Spin-sets weergeven](#viewing-spin-sets).

   U kunt sets die zijn gemaakt met voorinstellingen voor batchsets op drie verschillende manieren weergeven en openen. (Sets die zijn gemaakt met voorinstellingen voor batchsets, doen *niet* worden weergegeven in de gebruikersinterface.)

1. [Voorvertoning van centrifuges.](previewing-assets.md)

   Selecteer de centrifugeset en u kunt er een voorvertoning van weergeven. Roteer de centrifugeset. U kunt verschillende viewers kiezen in het menu **[!UICONTROL Viewers]** beschikbaar via het keuzemenu voor de linkertrack.

1. [Spin-sets publiceren.](publishing-dynamicmedia-assets.md)

   Als u een centrifugeset publiceert, wordt de volgorde geactiveerd waarin afbeeldingen in een centrifugeset worden weergegeven. Zorg ervoor dat u ze zo bestelt dat de centrifuge een vloeiende weergave van 360 graden biedt.**[!UICONTROL URL]** en **[!UICONTROL Embed]** tekenreeks. Bovendien moet u [De viewervoorinstelling publiceren](managing-viewer-presets.md).

1. [URL&#39;s koppelen aan uw webtoepassing](linking-urls-to-yourwebapplication.md) of [De video- of afbeeldingsviewer insluiten](embed-code.md).

   AEM Assets maakt URL-aanroepen voor centrifuges en activeert deze nadat u de centrifuges hebt gepubliceerd. U kunt deze URL&#39;s kopiëren wanneer u elementen voorvertoont. U kunt ze ook insluiten op uw website.

   Selecteer eerst de spinset en selecteer vervolgens **[!UICONTROL Viewers]** in het vervolgkeuzemenu voor het linkerspoor.

   Zie [Een spinset koppelen aan een webpagina](linking-urls-to-yourwebapplication.md) en [De video- of afbeeldingsviewer insluiten](embed-code.md).

Indien nodig kunt u [Draaiensets bewerken](#editing-spin-sets). Bovendien kunt u [Eigenschappen van Spin-set](managing-assets-touch-ui.md#editing-properties).

## Elementen uploaden voor centrifuges {#uploading-assets-for-spin-sets}

U hebt minstens 8-12 opnamen van een item nodig voor een eendimensionale centrifugeset en 16-24 voor een tweedimensionale centrifugeset. De opnamen moeten regelmatig worden gemaakt om de indruk te wekken dat het item draait en wordt gespiegeld. Als een eendimensionale centrifugeset bijvoorbeeld 12 opnamen bevat, roteert u het item 30 graden (360/12) voor elke opname.

U kunt afbeeldingen voor de centrifuges uploaden zoals u dat zou doen [andere middelen uploaden naar AEM Assets](managing-assets-touch-ui.md).

### Richtlijnen voor het maken van centrifuge-afbeeldingen {#guidelines-for-shooting-spin-set-images}

Hieronder vindt u een aantal aanbevolen procedures voor het uitvoeren van gecentreerde afbeeldingen. Over het algemeen geldt dat hoe meer afbeeldingen u in een centrifugeset hebt, hoe beter het effect van het draaien van de afbeelding is. Als u echter veel afbeeldingen in de set opneemt, neemt de laadtijd van de afbeeldingen toe. AEM raadt deze richtlijnen aan voor het maken van foto&#39;s voor gebruik in centrifuges:

* Gebruik minimaal 8-12 afbeeldingen in een eendimensionale centrifuge en 16-24 afbeeldingen in een tweedimensionale centrifugeset. U hebt minimaal 8 afbeeldingen nodig om 360 graden te kunnen draaien. Eendimensionale centrifuges komen vaker voor omdat het maken van tweedimensionale centrifuges arbeidsintensief is.
* Gebruik een indeling zonder verlies. TIFF en PNG worden aanbevolen.
* Masker alle afbeeldingen zodat het item op een zuiver witte of andere achtergrond met veel contrast wordt weergegeven. Voeg desgewenst schaduwen toe.
* Zorg ervoor dat de productdetails goed verlicht en in nadruk zijn.
* Neem spin beelden voor modekleding met een mannequin of een model. Vaak wordt de mannequin volledig gemaskeerd (met behulp van een glazen mannequin) of wordt in de afbeelding een gestileerde mannequin/dressform weergegeven. U kunt een op-model spin-reeks tot stand brengen door het aantal hoeken te bepalen. Markeer elke hoek met band op de vloer om het model te begeleiden en in de richting van elke opname te kijken.

## Spin-sets maken {#creating-spin-sets}

De volgorde waarin afbeeldingen worden weergegeven in een draaiset. Zorg ervoor dat u ze zo bestelt dat de centrifuge een vloeiende weergave van 360 graden biedt.

>[!NOTE]
>
>U kunt ook automatisch spinsets maken via [voorinstellingen voor batchsets](/help/assets/config-dms7.md#creating-batch-set-presets-to-auto-generate-image-sets-and-spin-sets).
>
>Batchsets worden gemaakt door het IPS (Image Production System) als onderdeel van het opnemen van elementen en zijn alleen beschikbaar in de Dynamic Media-Scene7-modus.
>
>Zie &quot;Voorinstellingen voor batchsets maken om automatisch afbeeldingssets en centrifuges te genereren&quot; in [Dynamic Media configureren - Scene7-modus](/help/assets/config-dms7.md#creating-batch-set-presets-to-auto-generate-image-sets-and-spin-sets).

Wanneer u een reeks van de Rotatie creeert, adviseert Adobe de volgende beste praktijken en handhaaft de volgende grens:

| Type limiet | Beste praktijken | Oplegde limiet |
| --- | --- | --- |
| Maximumaantal rijen/kolommen per 2D-set | 12-18 afbeeldingen per set | 1000 |

Zie ook [Dynamic Media-beperkingen](/help/assets/limitations.md).

**Om centrifuges te maken:**

1. Navigeer in Elementen naar de plaats waar u een centrifugeset wilt maken en tik op **[!UICONTROL Create]** en selecteert u **[!UICONTROL Spin Set]**. U kunt de set ook maken vanuit een map die uw assets bevat.

   ![chlimage_1-381](assets/chlimage_1-381.png)

1. Op de **[!UICONTROL Spin Set Editor]** pagina, in de **[!UICONTROL Title]** voert u een naam in voor de centrifugeset. De naam wordt weergegeven in de banner over de centrifugeset. Voer eventueel een beschrijving in.

   ![chlimage_1-382](assets/chlimage_1-382.png)

   Wanneer u de centrifugeset maakt, kunt u de miniatuur van de centrifugeset wijzigen of AEM de miniatuur automatisch selecteren op basis van de elementen in de centrifugeset. Tik op een miniatuur om deze te selecteren **[!UICONTROL Change thumbnail]**. Selecteer een willekeurige afbeelding (u kunt ook naar andere mappen navigeren om afbeeldingen te zoeken). Als u een miniatuur hebt geselecteerd en vervolgens wilt bepalen dat u een miniatuur AEM genereren op basis van de centrifugeset, selecteert u **[!UICONTROL Switch to Automatic thumbnail]**.

1. Voer een van de volgende handelingen uit:

   * In de linkerbovenhoek van het dialoogvenster **[!UICONTROL Spin Set Editor]** pagina, tikken **[!UICONTROL Add Asset]**.
   * In het midden van de **[!UICONTROL Spin Set Editor]** pagina, tikken **[!UICONTROL Tap to open Asset Selector]**.

   Tik om de elementen te selecteren die u in de centrifugeset wilt opnemen. Geselecteerde assets hebben een vinkje. Tik in de rechterbovenhoek van de pagina op **[!UICONTROL Select]**.

   Met de assetkiezer kunt u naar assets zoeken door een trefwoord te typen en op **[!UICONTROL Return]** te tikken. U kunt ook filters toepassen om de zoekresultaten te verfijnen. U kunt filteren op pad, verzameling, bestandstype en tag. Selecteer het filter en tik op het pictogram **[!UICONTROL Filter]** op de werkbalk. Tik op de knop **[!UICONTROL View]** tikken en vervolgens tikken **[!UICONTROL Column View]**, **[!UICONTROL Card View]**, of **[!UICONTROL List View]**.

   Zie [Werken met kiezers](working-with-selectors.md).

   ![chlimage_1-383](assets/chlimage_1-383.png)

1. Wanneer u elementen aan de set toevoegt, worden deze automatisch in alfanumerieke volgorde toegevoegd. Nadat u elementen hebt toegevoegd, kunt u deze handmatig opnieuw ordenen of sorteren. Indien nodig, sleept u elementen **[!UICONTROL Reorder]** rechts van de bestandsnaam van het element om de volgorde van de afbeeldingen in de lijst met sets te wijzigen.

   ![spin_set_assets6-4](assets/spin_set_assets6-4.png)

1. (Optioneel) Voer een van de volgende handelingen uit:

   * Als u een afbeelding wilt verwijderen, selecteert u de afbeelding en tikt u op **[!UICONTROL Delete Asset]**.
   * Tik op **[!UICONTROL Preset]** Selecteer vervolgens een voorinstelling die u op alle elementen tegelijk wilt toepassen.

1. Tik op **[!UICONTROL Save]**. De nieuwe centrifugeset wordt weergegeven in de map waarin u deze hebt gemaakt.

## Spin-sets weergeven {#viewing-spin-sets}

U kunt spin-sets maken in de gebruikersinterface of automatisch met [voorinstellingen voor batchsets](/help/assets/config-dms7.md#creating-batch-set-presets-to-auto-generate-image-sets-and-spin-sets). sets die zijn gemaakt met voorinstellingen voor batchsets, doen *niet* worden weergegeven in de gebruikersinterface. U hebt op drie verschillende manieren toegang tot sets die zijn gemaakt met voorinstellingen voor batchsets. (Deze methoden zijn ook beschikbaar als u de centrifuges in de gebruikersinterface hebt gemaakt.)

U kunt sets ook weergeven via de gebruikersinterface zoals beschreven in [Bewerken van centrifuges](#editing-spin-sets).

**Om de reeksen van Draaien te bekijken:**

1. Bij het openen van de eigenschappen van een afzonderlijk element. Eigenschappen geven aan wat de instelling is van het geselecteerde element (onder) **[!UICONTROL Member of Sets]**). Tik op de naam van de set om de volledige set weer te geven.

   ![chlimage_1-384](assets/chlimage_1-384.png)

1. Van een lidafbeelding van om het even welke set. Selecteer **[!UICONTROL Sets]** om de sets weer te geven waarvan het element lid is.

   ![chlimage_1-385](assets/chlimage_1-385.png)

1. Van onderzoek, kunt u selecteren **[!UICONTROL Filters]** vervolgens uitvouwen **[!UICONTROL Dynamic Media]** en selecteert u **[!UICONTROL Sets]**.

   De zoekopdracht retourneert overeenkomende sets die handmatig in de gebruikersinterface zijn gemaakt of die automatisch zijn gemaakt met voorinstellingen voor batchsets. Voor automatische sets wordt de zoekquery uitgevoerd met **[!UICONTROL Starts with]** zoekcriteria die verschillen van AEM zoekopdracht op basis van het gebruik van **[!UICONTROL Contains]** zoekcriteria. Het filter instellen op **[!UICONTROL Sets]** is de enige manier om geautomatiseerde reeksen te zoeken.

   ![chlimage_1-386](assets/chlimage_1-386.png)

## Bewerken van centrifuges {#editing-spin-sets}

U kunt diverse bewerkingstaken uitvoeren op bijvoorbeeld de volgende centrifuges:

* Voeg afbeeldingen toe aan de centrifugeset.
* Wijzig de volgorde van de afbeeldingen in de centrifugeset.
* Elementen in de centrifugeset verwijderen.
* Voorinstellingen voor viewers toepassen.
* Verwijder de centrifugeset.

**Een centrifuusset bewerken:**

1. Voer een van de volgende handelingen uit:

   * Houd de muisaanwijzer boven een gecentreerd element en tik vervolgens op **[!UICONTROL Edit]** (potloodpictogram).
   * Houd de muisaanwijzer boven een gecentreerd element en tik op **[!UICONTROL Select]** (vinkje pictogram), tikt u vervolgens op **[!UICONTROL Edit]** op de werkbalk.
   * Tik op een gecentreerd element en tik vervolgens op **[!UICONTROL Edit]** (potloodpictogram) op de werkbalk.

1. Voer een van de volgende handelingen uit om de centrifugeset te bewerken:

   * Als u de volgorde van afbeeldingen wilt wijzigen, sleept u een afbeelding naar een nieuwe locatie (selecteer het pictogram voor herschikken om items te verplaatsen).
   * Tik op de kolomkop om items in oplopende of aflopende volgorde te sorteren.
   * Tik op **[!UICONTROL Add Asset]**. Navigeren naar een element, dit selecteren en vervolgens tikken **[!UICONTROL Select]** in de rechterbovenhoek.
Als u de afbeelding verwijdert die AEM gebruikt voor de miniatuur door deze te vervangen door een andere afbeelding, wordt het oorspronkelijke element nog steeds weergegeven.
   * Als u een element wilt verwijderen, selecteert u het en tikt u op **[!UICONTROL Delete Asset]**.
   * Tik op de knop **[!UICONTROL Preset]** en selecteert u een voorinstelling.
   * Als u een volledige centrifugeset wilt verwijderen, navigeert u naar de centrifugeset, selecteert u deze en selecteert u **[!UICONTROL Delete]**

      >[!NOTE]
      >* U kunt de afbeeldingen in een centrifugeset bewerken door naar de set te navigeren en te tikken **[!UICONTROL Set Members]** in de linkerspoorstaaf en tik vervolgens op de **[!UICONTROL Edit]** (potloodpictogram) op een afzonderlijk element om het bewerkingsvenster te openen.


1. Klikken **[!UICONTROL Save]** wanneer klaar met bewerken.

## Voorvertoning van centrifuges weergeven {#previewing-spin-sets}

Zie [Elementen voorvertonen](previewing-assets.md).

## Spin-sets publiceren {#publishing-spin-sets}

Zie [Middelen publiceren](publishing-dynamicmedia-assets.md).
