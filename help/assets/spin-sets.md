---
title: Spin Sets
seo-title: Spin Sets
description: Leer hoe u met centrifuges in dynamische media werkt
seo-description: Leer hoe u met centrifuges in dynamische media werkt
uuid: a80a0491-6500-463a-83c4-ff4b90a88182
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
discoiquuid: afacb3ad-e4ad-4d06-a898-f3f2da8bbb64
translation-type: tm+mt
source-git-commit: 1ebe1e871767605dd4295429c3d0b4de4dd66939

---


# Spin Sets {#spin-sets}

Een centrifugeerset simuleert de echte handeling waarbij een object wordt omgedraaid om het te onderzoeken. Met centrifuges kunt u items vanuit elke hoek bekijken en de belangrijkste visuele details vanuit elke hoek verkrijgen.

Een centrifugeerset simuleert een kijkervaring van 360 graden. Dynamische media biedt centrifugesets met één as waarin gebruikers een item kunnen roteren. Bovendien kunnen gebruikers met een paar eenvoudige muisklikken in- en uitzoomen op een vrije vorm en een willekeurige weergave pannen. Op deze manier kunnen gebruikers een item vanuit een bepaald gezichtspunt nader onderzoeken.

De Reeksen van de draaien worden aangewezen door een banner met het woord **[!UICONTROL SPINSET]**. Als de Spin-set wordt gepubliceerd, staat bovendien de publicatiedatum, die wordt aangegeven door het pictogram **[!UICONTROL Wereld]** , op de banner samen met de laatste wijzigingsdatum, die wordt aangegeven door het pictogram **[!UICONTROL Potlood]** .

![chlimage_1-380](assets/chlimage_1-380.png)

>[!NOTE]
>
>Zie Elementen [beheren met de aanraakinterface](managing-assets-touch-ui.md)voor informatie over de gebruikersinterface van Elementen.

## Snel starten: Sets draaien {#quick-start-spin-sets}

Volg deze workflow om snel weer aan de slag te gaan met centrifuges:

1. [Upload uw afbeeldingen voor meerdere weergaven.](#uploading-assets-for-spin-sets)

   U hebt minstens 8-12 opnamen van een item nodig voor een eendimensionale centrifugeset en 16-24 voor een tweedimensionale centrifugeset. De opnamen moeten regelmatig worden gemaakt om de indruk te wekken dat het item draait en wordt gespiegeld. Als een eendimensionale centrifugeset bijvoorbeeld 12 opnamen bevat, roteert u het item 30 graden (360/12) voor elke opname.

1. [Spin-sets maken.](#creating-spin-sets)

   Als u een centrifugeset wilt maken, selecteert u **[!UICONTROL Maken > Spin-set]** en geeft u de set een naam, kiest u de elementen en sorteert u de afbeeldingen in de volgorde waarin deze worden weergegeven.

   See [Working with Selectors](working-with-selectors.md).

   >[!NOTE]
   >
   >U kunt ook automatisch centrifuges maken via voorinstellingen voor [batchsets](/help/assets/config-dms7.md#creating-batch-set-presets-to-auto-generate-image-sets-and-spin-sets).
   *De reeksen van de partij worden gecreeerd door IPS (het Systeem van de Productie van het Beeld) als deel van activa opnemen en zijn beschikbaar slechts in Dynamische Media - wijze* Scene7.

1. Stel, indien nodig, [voorinstellingen](managing-viewer-presets.md)voor de draaiende viewer in.

   Beheerders kunnen voorinstellingen voor de voorinstelling Spin Set Viewer maken of wijzigen. Als u de centrifugeset wilt weergeven met een viewervoorinstelling, selecteert u de centrifugeset en selecteert u **[!UICONTROL Viewers]** in de vervolgkeuzelijst voor de linkertrack.

   Zie **[!UICONTROL Gereedschappen > Middelen > Voorinstellingen]** viewer om voorinstellingen voor viewers te maken of te bewerken.

   Zie Voorinstellingen voor viewers [toevoegen en bewerken.](managing-viewer-presets.md)

1. [Spin-sets](#viewing-spin-sets)weergeven.

   U kunt sets die zijn gemaakt met voorinstellingen voor batchsets op drie verschillende manieren weergeven en openen. (Sets die zijn gemaakt met behulp van voorinstellingen voor batchsets, worden *niet* weergegeven in de gebruikersinterface.)

1. [Voorvertoning van centrifuges.](previewing-assets.md)

   Selecteer de centrifugeset en u kunt er een voorvertoning van weergeven. Roteer de centrifugeset. U kunt verschillende viewers kiezen in het menu **[!UICONTROL Viewers]** , beschikbaar in het keuzemenu voor de linkertrack.

1. [Spin-sets publiceren.](publishing-dynamicmedia-assets.md)

   Als u een centrifugeset publiceert, wordt de volgorde geactiveerd waarin afbeeldingen in een centrifugeset worden weergegeven. Zorg ervoor dat u ze zo bestelt dat de centrifuge een vloeiende weergave van 360 graden biedt.**[!UICONTROL URL]** en **[!UICONTROL Embed]** string. Bovendien moet u de voorinstelling [van de viewer](managing-viewer-presets.md)publiceren.

1. [Koppel URL&#39;s aan uw webtoepassing](linking-urls-to-yourwebapplication.md) of [sluit de video- of afbeeldingsviewer](embed-code.md)in.

   Met AEM-elementen worden URL-aanroepen voor centrifuges gemaakt en geactiveerd nadat u de centrifuges hebt gepubliceerd. U kunt deze URL&#39;s kopiëren wanneer u elementen voorvertoont. U kunt ze ook insluiten op uw website.

   Selecteer eerst de centrifugeset en vervolgens **[!UICONTROL Viewers]** in het vervolgkeuzemenu voor de linkertrack.

   Zie Een centrifugeerset [koppelen aan een webpagina](linking-urls-to-yourwebapplication.md) en de video- of afbeeldingsviewer [](embed-code.md)insluiten.

Indien nodig kunt u [centrifuges](#editing-spin-sets)bewerken. Bovendien kunt u de eigenschappen [van de](managing-assets-touch-ui.md#editing-properties)Spin-set weergeven en bewerken.

## Elementen uploaden voor centrifuges {#uploading-assets-for-spin-sets}

U hebt minstens 8-12 opnamen van een item nodig voor een eendimensionale centrifugeset en 16-24 voor een tweedimensionale centrifugeset. De opnamen moeten regelmatig worden gemaakt om de indruk te wekken dat het item draait en wordt gespiegeld. Als een eendimensionale centrifugeset bijvoorbeeld 12 opnamen bevat, roteert u het item 30 graden (360/12) voor elke opname.

U kunt afbeeldingen voor de centrifuges uploaden zoals u elk ander element in AEM-elementen [](managing-assets-touch-ui.md)uploadt.

### Richtlijnen voor het maken van centrifuges {#guidelines-for-shooting-spin-set-images}

Hieronder vindt u een aantal aanbevolen procedures voor het uitvoeren van gecentreerde afbeeldingen. Over het algemeen geldt dat hoe meer afbeeldingen u in een centrifugeset hebt, hoe beter het effect van het draaien van de afbeelding is. Als u echter veel afbeeldingen in de set opneemt, neemt de laadtijd van de afbeeldingen toe. AEM raadt de volgende richtlijnen aan voor het maken van foto&#39;s voor gebruik in centrifuges:

* Gebruik minimaal 8-12 afbeeldingen in een eendimensionale centrifuge en 16-24 afbeeldingen in een tweedimensionale centrifugeset. U hebt minimaal 8 afbeeldingen nodig om 360 graden te kunnen draaien. Eendimensionale centrifuges komen vaker voor omdat het maken van tweedimensionale centrifuges arbeidsintensief is.
* Gebruik een indeling zonder verlies. TIFF en PNG worden aanbevolen.
* Masker alle afbeeldingen zodat het item op een zuiver witte of andere achtergrond met veel contrast wordt weergegeven. Voeg desgewenst schaduwen toe.
* Zorg ervoor dat de productdetails goed verlicht en in nadruk zijn.
* Neem spin beelden voor modekleding met een mannequin of een model. Vaak wordt de mannequin volledig gemaskeerd (met behulp van een glazen mannequin) of wordt in de afbeelding een gestileerde mannequin/dressform weergegeven. U kunt een op-model spin-reeks tot stand brengen door het aantal hoeken te bepalen. Markeer elke hoek met band op de vloer om het model te begeleiden en in de richting van elke opname te kijken.

## Spin-sets maken {#creating-spin-sets}

De volgorde waarin afbeeldingen worden weergegeven in een draaiset. Zorg ervoor dat u ze zo bestelt dat de centrifuge een vloeiende weergave van 360 graden biedt.

>[!NOTE]
>
>U kunt ook automatisch spin-sets maken via voorinstellingen voor [batchsets](/help/assets/config-dms7.md#creating-batch-set-presets-to-auto-generate-image-sets-and-spin-sets).
 De reeksen van de partij worden gecreeerd door IPS (het Systeem van de Productie van het Beeld) als deel van activa opnemen en zijn beschikbaar slechts op Dynamische Media - wijze Scene7.
>
>Zie &quot;het Creëren van partijreeks vooraf instelt om de Reeksen van het Beeld en Reeksen van de Draai&quot;in het [Vormen Dynamische Media - wijze](/help/assets/config-dms7.md#creating-batch-set-presets-to-auto-generate-image-sets-and-spin-sets)Scene7 automatisch te produceren.

**Om centrifuges te maken:**

1. Navigeer in Elementen naar de plaats waar u een centrifugeset wilt maken, tik op **[!UICONTROL Maken]** en selecteer **[!UICONTROL-centrifugeset**. U kunt de set ook maken vanuit een map die uw elementen bevat.

   ![chlimage_1-381](assets/chlimage_1-381.png)

1. Voer in het veld **[!UICONTROL Titel]** op de pagina Editor **[!UICONTROL van]** centrifugeset een naam in voor de centrifugeset. De naam wordt weergegeven in de banner over de centrifugeset. Voer eventueel een beschrijving in.

   ![chlimage_1-382](assets/chlimage_1-382.png)

   Wanneer u de centrifugeset maakt, kunt u de miniatuur van de centrifugeset wijzigen of AEM toestaan de miniatuur automatisch te selecteren op basis van de elementen in de centrifugeset. Tik op **[!UICONTROL Wijzigen om een miniatuur]** te selecteren. Selecteer een willekeurige afbeelding (u kunt ook naar andere mappen navigeren om afbeeldingen te zoeken). Als u een miniatuur hebt geselecteerd en vervolgens besluit dat u een miniatuur van de centrifugeset wilt genereren, selecteert u **[!UICONTROL Schakelen naar automatische miniatuur]**.

1. Voer een van de volgende handelingen uit:

   * Tik in de linkerbovenhoek van de pagina **[!UICONTROL Spin Set Editor]** op Element **[!UICONTROL toevoegen]**.
   * Tik in het midden van de pagina **[!UICONTROL Spin Set Editor]** op **[!UICONTROL Tikken om de Asset Selector]** te openen.
   Tik om de elementen te selecteren die u in de centrifugeset wilt opnemen. Geselecteerde elementen hebben een vinkje erboven. Tik op **[!UICONTROL Selecteren]** in de rechterbovenhoek van de pagina als u klaar bent.

   Met de Kiezer van Activa, kunt u naar activa zoeken door in een sleutelwoord te typen en **[!UICONTROL Terugkeer]** te tikken. U kunt ook filters toepassen om de zoekresultaten te verfijnen. U kunt filteren op pad, verzameling, bestandstype en tag. Selecteer het filter en tik op het pictogram **[!UICONTROL Filter]** op de werkbalk. Tik op het pictogram **[!UICONTROL Weergave]** en tik vervolgens op **[!UICONTROL Kolomweergave]**, **[!UICONTROL Kaartweergave]** of **[!UICONTROL Lijstweergave]** om de weergave in de rechterbovenhoek van de pagina te wijzigen.

   See [Working with Selectors](working-with-selectors.md).

   ![chlimage_1-383](assets/chlimage_1-383.png)

1. Wanneer u elementen aan de set toevoegt, worden deze automatisch in alfanumerieke volgorde toegevoegd. Nadat u elementen hebt toegevoegd, kunt u deze handmatig opnieuw ordenen of sorteren. Indien nodig sleept u het pictogram **[!UICONTROL Opnieuw ordenen]** van een element naar rechts naast de bestandsnaam van het element om de volgorde van de afbeeldingen in de lijst met sets te wijzigen.

   ![spin_set_assets6-4](assets/spin_set_assets6-4.png)

1. (Optioneel) Voer een van de volgende handelingen uit:

   * Als u een afbeelding wilt verwijderen, selecteert u de afbeelding en tikt u op Element **** verwijderen.
   * Tik op **[!UICONTROL Voorinstelling]** en selecteer vervolgens een voorinstelling die u op alle elementen tegelijk wilt toepassen om een voorinstelling toe te passen in de rechterbovenhoek van de pagina.

1. Tik op **[!UICONTROL Opslaan]**. De nieuwe centrifugeset wordt weergegeven in de map waarin u deze hebt gemaakt.

## Spin-sets weergeven {#viewing-spin-sets}

U kunt spin-sets maken in de gebruikersinterface of automatisch met behulp van voorinstellingen voor [batchsets](/help/assets/config-dms7.md#creating-batch-set-presets-to-auto-generate-image-sets-and-spin-sets). Set die is gemaakt met voorinstellingen voor batchsets, wordt echter *niet* weergegeven in de gebruikersinterface. U hebt op drie verschillende manieren toegang tot sets die zijn gemaakt met voorinstellingen voor batchsets. (Deze methoden zijn ook beschikbaar als u de centrifuges in de gebruikersinterface hebt gemaakt.)

U kunt sets ook weergeven in de gebruikersinterface, zoals wordt beschreven in [Spin-sets](#editing-spin-sets)bewerken.

**Om de reeksen van Draaien te bekijken:**

1. Bij het openen van de eigenschappen van een afzonderlijk element. Eigenschappen geven aan welke sets het geselecteerde element is ingesteld als lid van (onder **[!UICONTROL Lid van Sets]**). Tik op de naam van de set om de volledige set weer te geven.

   ![chlimage_1-384](assets/chlimage_1-384.png)

1. Van een lidafbeelding van om het even welke reeks. Selecteer het menu **[!UICONTROL Sets]** om de sets weer te geven waarvan het element lid is.

   ![chlimage_1-385](assets/chlimage_1-385.png)

1. U kunt vanuit de zoekopdracht **[!UICONTROL Filters]** selecteren, vervolgens **[!UICONTROL Dynamische media]** uitvouwen en **[!UICONTROL Sets]** selecteren.

   De zoekopdracht retourneert overeenkomende sets die handmatig in de gebruikersinterface zijn gemaakt of die automatisch zijn gemaakt met voorinstellingen voor batchsets. Voor geautomatiseerde reeksen, wordt de onderzoeksvraag geleid gebruikend **[!UICONTROL Begint met]** onderzoekscriteria die verschillend van AEM onderzoek zijn dat op het gebruiken van **[!UICONTROL Bevat]** onderzoekscriteria gebaseerd is. Het instellen van het filter op **[!UICONTROL Sets]** is de enige manier om geautomatiseerde sets te doorzoeken.

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

   * Houd de muisaanwijzer boven een gecentreerd element en tik op **[!UICONTROL Bewerken]** (potloodpictogram).
   * Houd de muisaanwijzer boven een gecentreerd element, tik op **[!UICONTROL Selecteren]** (vinkpictogram) en tik vervolgens op **[!UICONTROL Bewerken]** op de werkbalk.
   * Tik op een gecentreerd element en tik vervolgens op **[!UICONTROL Bewerken]** (potloodpictogram) op de werkbalk.

1. Voer een van de volgende handelingen uit om de centrifugeset te bewerken:

   * Als u de volgorde van afbeeldingen wilt wijzigen, sleept u een afbeelding naar een nieuwe locatie (selecteer het pictogram voor herschikken om items te verplaatsen).
   * Tik op de kolomkop om items in oplopende of aflopende volgorde te sorteren.
   * Tik op Element **** toevoegen om een element toe te voegen of een bestaand element bij te werken. Navigeer naar een element, selecteer het en tik op **[!UICONTROL Selecteren]** in de rechterbovenhoek.
Als u de afbeelding verwijdert die AEM voor de miniatuur gebruikt door deze te vervangen door een andere afbeelding, wordt het oorspronkelijke element nog steeds weergegeven.
   * Als u een element wilt verwijderen, selecteert u het en tikt u op Element **** verwijderen.
   * Tik op het pictogram **[!UICONTROL Voorinstelling]** en selecteer een voorinstelling om een voorinstelling toe te passen.
   * Als u een volledige centrifugeset wilt verwijderen, navigeert u naar de centrifugeset, selecteert u deze en selecteert u **[!UICONTROL Verwijderen]**

      >[!NOTE]
      >* U kunt de afbeeldingen in een centrifugeset bewerken door naar de set te navigeren, op Leden **** instellen in de linkertrack te tikken en vervolgens op het pictogram **[!UICONTROL Bewerken]** (potlood) op een afzonderlijk element te tikken om het bewerkingsvenster te openen.


1. Klik op **[!UICONTROL Opslaan]** wanneer u klaar bent met bewerken.

## Voorvertoning van centrifuges weergeven {#previewing-spin-sets}

Zie [Voorvertoning van elementen](previewing-assets.md)weergeven.

## Spin-sets publiceren {#publishing-spin-sets}

Zie Elementen [](publishing-dynamicmedia-assets.md)publiceren.
