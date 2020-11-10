---
title: Samengestelde elementen beheren en subelementen genereren.
description: Leer hoe u verwijzingen naar AEM middelen maakt vanuit InDesign-, Adobe Illustrator- en Photoshop-bestanden. Leer ook hoe u de functie Paginaviewer gebruikt om afzonderlijke pagina's van bestanden met meerdere pagina's weer te geven, zoals PDF-, INDD-, PPT-, PPTX- en AI-bestanden.
contentOwner: AG
translation-type: tm+mt
source-git-commit: ddfcb74451f41cea911700a64abceaaf47e7af49
workflow-type: tm+mt
source-wordcount: '1327'
ht-degree: 0%

---


# Samengestelde elementen beheren met subelementen {#managing-compound-assets}

Adobe Experience Manager (AEM) Assets kunnen bepalen of een geüpload bestand verwijzingen bevat naar elementen die al in de repository bestaan. Deze functie is alleen beschikbaar voor ondersteunde bestandsindelingen. Als het geüploade element verwijzingen naar AEM elementen bevat, wordt een bidirectionele koppeling gemaakt tussen de geüploade en de gerefereerde elementen.

Naast het elimineren van overtolligheid, het van verwijzingen voorzien van AEM activa in de toepassingen van Adobe Creative Cloud verbetert samenwerking en verhoogt de efficiency en de productiviteit van gebruikers.

AEM Assets ondersteunt **bidirectionele referentie**. U vindt de middelen waarnaar wordt verwezen op de elementdetailpagina van het geüploade bestand. Daarnaast kunt u de bestanden waarnaar wordt verwezen voor AEM elementen bekijken op de pagina met elementdetails van het element waarnaar wordt verwezen.

Verwijzingen worden opgelost op basis van pad, document-id en instantie-id van de middelen waarnaar wordt verwezen.

## AEM Assets toevoegen als verwijzingen in Adobe Illustrator {#refai}

U kunt verwijzen naar bestaande AEM elementen vanuit een Adobe Illustrator-bestand.

1. Plaats met behulp van [AEM bureaubladtoepassing](https://helpx.adobe.com/experience-manager/desktop-app/aem-desktop-app.html)de AEM Assets-opslagplaats als een station op uw lokale computer. Navigeer in het gekoppelde station naar de locatie van het element waarnaar u wilt verwijzen.
1. Sleep het element van het gekoppelde station naar het Illustrator-bestand.
1. Sla het Illustrator-bestand op het gekoppelde station op of [upload het bestand naar](managing-assets-touch-ui.md#uploading-assets) de AEM opslagplaats.
1. Nadat de werkstroom is voltooid, gaat u naar de pagina met elementdetails voor het element. De verwijzingen naar bestaande AEM zijn vermeld onder **[!UICONTROL Dependencies]** in de **[!UICONTROL References]** kolom.

   ![chlimage_1-258](assets/chlimage_1-258.png)

1. De middelen waarnaar wordt verwezen die onder **[!UICONTROL Dependencies]** worden weergegeven, kunnen ook worden verwezen door andere bestanden dan de huidige. Als u een lijst wilt weergeven met bestanden die naar een element verwijzen, klikt u op het element onder **[!UICONTROL Dependencies]**.

   ![chlimage_1-259](assets/chlimage_1-259.png)

1. Click the **[!UICONTROL View Properties]** icon from the toolbar. Op de pagina met eigenschappen wordt de lijst met bestanden die naar het huidige element verwijzen, weergegeven onder de **[!UICONTROL References]** kolom op het **[!UICONTROL Basic]** tabblad.

   ![chlimage_1-260](assets/chlimage_1-260.png)

## AEM elementen toevoegen als verwijzingen in Adobe InDesign {#add-aem-assets-as-references-in-adobe-indesign}

Als u vanuit een InDesign-bestand wilt verwijzen naar AEM elementen, sleept u AEM elementen naar het InDesign-bestand of exporteert u het InDesign-bestand als een ZIP-bestand.

De activa waarnaar wordt verwezen bestaan reeds in AEM Assets. U kunt subassets extraheren door de InDesign-server [te](indesign.md)configureren. Ingesloten elementen in een InDesign-bestand worden geëxtraheerd als subelementen.

>[!NOTE]
>
>Als de InDesign-server proxy is, is de voorvertoning van InDesign-bestanden ingesloten in de XMP metagegevens. In dit geval is het niet expliciet vereist miniatuurextractie uit te voeren. Als de InDesign-server echter geen proxy is, moeten miniaturen expliciet worden uitgepakt voor InDesign-bestanden.

### Verwijzingen maken door AEM elementen te slepen {#create-references-by-dragging-aem-assets}

Deze procedure is vergelijkbaar met het [toevoegen van AEM elementen als verwijzingen in Adobe Illustrator](#refai).

### Verwijzingen naar AEM elementen maken door een ZIP-bestand te exporteren {#create-references-to-aem-assets-by-exporting-a-zip-file}

1. Voer de stappen in het [Creëren van de Modellen](/help/sites-developing/workflows-models.md) van het Werkschema uit om een nieuwe werkschema tot stand te brengen.
1. Gebruik de functie Pakket van Adobe InDesign om het document te exporteren.
Adobe InDesign kan een document en de gekoppelde elementen als een pakket exporteren. In dit geval bevat de geëxporteerde map een map Koppelingen met subelementen in het InDesign-bestand.
1. Maak een ZIP-bestand en upload het naar de AEM-opslagplaats.
1. Start de Unarchiver-workflow.
1. Wanneer de werkstroom is voltooid, wordt er automatisch naar de verwijzingen in de map Koppelingen verwezen als subelementen. Als u een lijst met de desbetreffende elementen wilt weergeven, navigeert u naar de pagina met elementdetails van het element InDesign en sluit u de [Rail](/help/sites-authoring/basic-handling.md#rail-selector).

## AEM elementen toevoegen als verwijzingen in Adobe Photoshop {#refps}

1. Gebruik een WebDav-client om AEM Assets op te zetten als een station.
1. Als u verwijzingen naar AEM elementen in een Photoshop-bestand wilt maken, navigeert u naar de corresponderende elementen in het gekoppelde station met de functie Gekoppelde plaatsen in Photoshop.

   ![chlimage_1-261](assets/chlimage_1-261.png)

1. Opslaan in Photoshop-bestand op het gemonteerde station of [uploaden](managing-assets-touch-ui.md#uploading-assets) naar de AEM opslagplaats.
1. Nadat de workflow is voltooid, worden de verwijzingen naar bestaande AEM weergegeven op de pagina met elementdetails.

   Als u de middelen waarnaar wordt verwezen wilt weergeven, sluit u de [Rail](/help/sites-authoring/basic-handling.md#rail-selector) op de pagina met elementdetails.

1. De middelen waarnaar wordt verwezen, bevatten ook de lijst met elementen waarnaar wordt verwezen. Als u een lijst met middelen waarnaar wordt verwezen wilt weergeven, navigeert u naar de pagina met elementdetails en sluit u de [rail](/help/sites-authoring/basic-handling.md#rail-selector).

>[!NOTE]
>
>Er kan ook worden verwezen naar de elementen in samengestelde elementen op basis van hun document-id en instantie-id. Deze functionaliteit is alleen beschikbaar in Adobe Illustrator- en Adobe Photoshop-versies. Voor andere toepassingen wordt het verwijzen uitgevoerd op basis van het relatieve pad van gekoppelde elementen in het hoofdsamengestelde element, zoals dat in eerdere versies van AEM is gebeurd.

## Subelementen maken {#generate-subassets}

Voor de ondersteunde elementen met indelingen die uit meerdere pagina&#39;s bestaan (PDF-bestanden, AI-bestanden, Microsoft PowerPoint- en Apple-toetsenbordbestanden en Adobe InDesign-bestanden), kunnen AEM subelementen genereren die overeenkomen met elke afzonderlijke pagina van het oorspronkelijke element. Deze subelementen zijn gekoppeld aan het *bovenliggende* element en maken de weergave van meerdere pagina&#39;s eenvoudiger. Voor alle andere doeleinden worden de subactiva behandeld als normale activa in AEM.

Genereren van subelementen is standaard uitgeschakeld. Voer de volgende stappen uit om het genereren van subelementen in te schakelen:

1. Meld u aan bij Experience Manager als beheerder. Ga naar **[!UICONTROL Tools > Workflow > Models]**.
1. Select **[!UICONTROL DAM Update Asset]** workflow and click **[!UICONTROL Edit]**.
1. Klik **[!UICONTROL Toggle Side Panel]** en zoek de **[!UICONTROL Create Sub Asset]** stap. Voeg de stap toe aan de workflow. Klik op **[!UICONTROL Sync]**.

Voer een van de volgende handelingen uit om de subelementen te genereren:

* Nieuwe elementen: De [!UICONTROL DAM Update Assets] workflow wordt uitgevoerd op elk nieuw element dat naar AEM wordt geüpload. Subelementen worden automatisch gegenereerd voor nieuwe elementen die uit meerdere pagina&#39;s bestaan.
* Bestaande elementen met meerdere pagina&#39;s: Voer handmatig de [!UICONTROL DAM Update Assets] workflow uit volgens een van de volgende stappen:

   * Selecteer een element en klik [!UICONTROL Timeline] om het linkerdeelvenster te openen. U kunt ook de sneltoets gebruiken `alt + 3`. Klik [!UICONTROL Start Workflow], selecteer [!UICONTROL DAM Update Asset], klik [!UICONTROL Start], en klik [!UICONTROL Proceed].
   * Select an asset and click [!UICONTROL Create > Workflow] from the toolbar. Selecteer in het pop-updialoogvenster de [!UICONTROL DAM Update Asset] workflow, klik [!UICONTROL Start]en klik op [!UICONTROL Proceed].

Met name voor Microsoft Word-documenten voert u de **[!UICONTROL DAM Parse Word Documents]** workflow uit. Er wordt een `cq:Page` component gegenereerd op basis van de inhoud van het Microsoft Word-document. De afbeeldingen die uit het document zijn geëxtraheerd, worden vanuit de `cq:Page` component gebruikt. Deze afbeeldingen worden geëxtraheerd, zelfs als het genereren van subelementen is uitgeschakeld.

## Subelementen weergeven {#viewing-subassets}

De subelementen worden alleen weergegeven als de subelementen zijn gegenereerd en beschikbaar zijn voor het geselecteerde element met meerdere pagina&#39;s. Open het element met meerdere pagina&#39;s om de gegenereerde subelementen weer te geven. Klik in de linkerbovenhoek van de pagina op het pictogram ![Linkerspoor en klik](assets/do-not-localize/aem_leftrail_contentonly.png) **[!UICONTROL Subassets]** in de lijst. Wanneer u een keuze maakt in de **[!UICONTROL Subassets]** lijst. U kunt ook de sneltoets gebruiken `alt + 5`.

![Subelementen weergeven voor elementen die uit meerdere pagina&#39;s bestaan](assets/view_subassets_simulation.gif)

## Pagina&#39;s van een bestand met meerdere pagina&#39;s weergeven {#view-pages-of-a-multi-page-file}

U kunt een bestand met meerdere pagina&#39;s, zoals PDF, INDD, PPT, PPTX en AI, weergeven met de functie Paginaviewer van AEM Assets. Open een element met meerdere pagina&#39;s en klik in de linkerbovenhoek van de pagina. **[!UICONTROL View Pages]** In de Paginaviewer die wordt geopend, worden de pagina&#39;s van het element en de besturingselementen weergegeven waarmee u door elke pagina kunt bladeren en erop kunt inzoomen.

![Pagina&#39;s van elementen met meerdere pagina&#39;s weergeven en bekijken](assets/view_multipage_asset_fmr.gif)

Voor InDesign kunt u pagina&#39;s uitnemen met de InDesign-server. Als de voorvertoningen van pagina&#39;s worden opgeslagen tijdens het maken van het InDesign-bestand, is InDesign Server niet vereist voor het uitnemen van pagina&#39;s.

De volgende opties zijn beschikbaar in de werkbalk, in de linkerrails en in de besturingselementen voor de Paginaviewer:

* **[!UICONTROL Desktop Actions]** om een specifiek submiddel te openen of weer te geven met AEM bureaubladtoepassing. Zie hoe u bureaubladhandelingen [kunt](https://experienceleague.adobe.com/docs/experience-manager-desktop-app/using/using.html?lang=en#desktopactions-v2) configureren als u AEM bureaubladtoepassing gebruikt.

* **[!UICONTROL Properties]** Hiermee opent u de [!UICONTROL Properties] pagina van het specifieke subelement.

* **[!UICONTROL Annotate]** kunt u het specifieke subelement van een annotatie voorzien. De annotaties die u op afzonderlijke subelementen gebruikt, worden samen verzameld en weergegeven wanneer het bovenliggende element wordt geopend voor weergave.

* **[!UICONTROL Page Overview]** worden alle subelementen tegelijkertijd weergegeven.

* **[!UICONTROL Timeline]** Nadat u op het pictogram ![](assets/do-not-localize/aem_leftrail_contentonly.png) Linkerspoor hebt geklikt, wordt de activiteitsstroom voor het bestand weergegeven.

## Beste werkwijzen en beperking {#best-practice-limitation-tips}

* Bij elke implementatie van Experience Managers kan het genereren van subelementen zeer veel resources vergen. Als u subassets genereert wanneer complexe elementen worden geüpload, voegt u de stap toe in de DAM-workflow voor het bijwerken van middelen. Als u op verzoek subassets genereert, maakt u een aparte workflow om subassets te genereren. Met een speciale workflow kunt u de andere stappen in de workflow voor DAM-update-elementen overslaan en computerbronnen opslaan.

>[!MORELIKETHIS]
>
>* [Adobe Experience Manager-bureaubladtoepassing gebruiken](https://experienceleague.adobe.com/docs/experience-manager-desktop-app/using/using.html)

