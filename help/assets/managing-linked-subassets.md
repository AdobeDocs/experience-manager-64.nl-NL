---
title: Samengestelde elementen beheren en subelementen genereren.
description: Leer hoe u verwijzingen naar AEM middelen maakt vanuit InDesign-, Adobe Illustrator- en Photoshop-bestanden. Leer ook hoe u de functie Paginaviewer gebruikt om afzonderlijke pagina's van bestanden met meerdere pagina's weer te geven, zoals PDF-, INDD-, PPT-, PPTX- en AI-bestanden.
contentOwner: AG
translation-type: tm+mt
source-git-commit: dc9ba70161f81578899416064bd03fdabe0bed5a
workflow-type: tm+mt
source-wordcount: '1351'
ht-degree: 0%

---


# Samengestelde elementen beheren met subelementen {#managing-compound-assets}

Adobe Experience Manager (AEM) Assets kunnen bepalen of een geüpload bestand verwijzingen bevat naar elementen die al in de repository bestaan. Deze functie is alleen beschikbaar voor ondersteunde bestandsindelingen. Als het geüploade element verwijzingen naar AEM elementen bevat, wordt een bidirectionele koppeling gemaakt tussen de geüploade en de gerefereerde elementen.

Naast het elimineren van overtolligheid, het van verwijzingen voorzien van AEM activa in de toepassingen van Adobe Creative Cloud verbetert samenwerking en verhoogt de efficiency en de productiviteit van gebruikers.

AEM Assets ondersteunt het **bidirectioneel verwijzen**. U vindt de middelen waarnaar wordt verwezen op de elementdetailpagina van het geüploade bestand. Daarnaast kunt u de bestanden waarnaar wordt verwezen voor AEM elementen bekijken op de pagina met elementdetails van het element waarnaar wordt verwezen.

Verwijzingen worden opgelost op basis van pad, document-id en instantie-id van de middelen waarnaar wordt verwezen.

## Adobe Illustrator: Elementen toevoegen als verwijzingen {#refai}

U kunt verwijzen naar bestaande AEM elementen vanuit een Adobe Illustrator-bestand.

1. Plaats met [AEM desktop app](https://helpx.adobe.com/experience-manager/desktop-app/aem-desktop-app.html) de AEM Assets-opslagplaats als een station op uw lokale computer. Navigeer in het gekoppelde station naar de locatie van het element waarnaar u wilt verwijzen.
1. Sleep het element van het gekoppelde station naar het Illustrator-bestand.
1. Sla het Illustrator-bestand op het gekoppelde station op of [upload](managing-assets-touch-ui.md#uploading-assets) naar de AEM opslagplaats.
1. Nadat de workflow is voltooid, gaat u naar de pagina met elementdetails voor het element. De verwijzingen naar bestaande AEM zijn vermeld onder **[!UICONTROL Dependencies]** in **[!UICONTROL References]** kolom.

   ![chlimage_1-258](assets/chlimage_1-258.png)

1. De middelen waarnaar wordt verwezen die onder **[!UICONTROL Dependencies]** verschijnen kunnen ook door dossiers buiten huidige worden van verwijzingen voorzien. Als u een lijst met referentiebestanden voor een element wilt weergeven, klikt u op het element onder **[!UICONTROL Dependencies]**.

   ![chlimage_1-259](assets/chlimage_1-259.png)

1. Klik op het pictogram **[!UICONTROL View Properties]** op de werkbalk. Op de eigenschappenpagina wordt de lijst met bestanden die naar het huidige element verwijzen, weergegeven onder de kolom **[!UICONTROL References]** op het tabblad **[!UICONTROL Basic]**.

   ![chlimage_1-260](assets/chlimage_1-260.png)

## Adobe InDesign: Elementen toevoegen als verwijzingen {#add-aem-assets-as-references-in-adobe-indesign}

Als u vanuit een InDesign-bestand wilt verwijzen naar AEM elementen, sleept u AEM elementen naar het InDesign-bestand of exporteert u het InDesign-bestand als een ZIP-bestand.

De activa waarnaar wordt verwezen bestaan reeds in AEM Assets. U kunt subassets extraheren door [InDesign server](indesign.md) te configureren. Ingesloten elementen in een InDesign-bestand worden geëxtraheerd als subelementen.

>[!NOTE]
>
>Als de InDesign-server proxy is, is de voorvertoning van InDesign-bestanden ingesloten in de XMP metagegevens. In dit geval is het niet expliciet vereist miniatuurextractie uit te voeren. Als de InDesign-server echter geen proxy is, moeten miniaturen expliciet worden uitgepakt voor InDesign-bestanden.

Wanneer een INDD-bestand wordt geüpload, worden de verwijzingen opgehaald door te zoeken naar elementen met de eigenschappen `xmpMM:InstanceID` en `xmpMM:DocumentID` in de opslagplaats.

### Verwijzingen maken door elementen {#create-references-by-dragging-aem-assets} te slepen

Deze procedure is vergelijkbaar met [Elementen toevoegen als verwijzingen in Adobe Illustrator](#refai).

### Verwijzingen naar elementen maken door een ZIP-bestand {#create-references-to-aem-assets-by-exporting-a-zip-file} te exporteren

1. Voer de stappen in [Creating Workflow Models](/help/sites-developing/workflows-models.md) uit om een nieuwe werkstroom tot stand te brengen.
1. Met de functie [Pakket maken van Adobe InDesign](https://helpx.adobe.com/indesign/how-to/indesign-package-files-for-handoff.html) kunt u het document exporteren. Adobe InDesign kan een document en de gekoppelde elementen als een pakket exporteren. In dit geval bevat de geëxporteerde map een map `Links` met subelementen in het InDesign-bestand. De map `Links` bevindt zich in dezelfde map als het INDD-bestand.
1. Maak een ZIP-bestand en upload het naar de AEM-opslagplaats.
1. Start de Unarchiver-workflow.
1. Wanneer de werkstroom is voltooid, wordt er automatisch naar de verwijzingen in de map Koppelingen verwezen als subelementen. Als u een lijst met de desbetreffende elementen wilt weergeven, navigeert u naar de pagina met elementdetails van het InDesign-element en sluit u [Rail](/help/sites-authoring/basic-handling.md#rail-selector).

## Adobe Photoshop: Elementen toevoegen als verwijzingen {#refps}

1. Gebruik een WebDav-client om AEM Assets op te zetten als een station.
1. Als u verwijzingen naar AEM elementen in een Photoshop-bestand wilt maken, navigeert u naar de corresponderende elementen in het gekoppelde station met de functie Gekoppelde plaatsen in Photoshop.

   ![chlimage_1-261](assets/chlimage_1-261.png)

1. Opslaan in Photoshop-bestand op het gemonteerde station of [uploaden](managing-assets-touch-ui.md#uploading-assets) naar de AEM opslagplaats.
1. Nadat de workflow is voltooid, worden de verwijzingen naar bestaande AEM weergegeven op de pagina met elementdetails.

   Sluit [Rail](/help/sites-authoring/basic-handling.md#rail-selector) op de pagina met elementdetails om de betreffende elementen weer te geven.

1. De middelen waarnaar wordt verwezen, bevatten ook de lijst met elementen waarnaar wordt verwezen. Als u een lijst met middelen waarnaar wordt verwezen wilt weergeven, navigeert u naar de pagina met elementdetails en sluit u [rail](/help/sites-authoring/basic-handling.md#rail-selector).

>[!NOTE]
>
>Er kan ook worden verwezen naar de elementen in samengestelde elementen op basis van hun document-id en instantie-id. Deze functionaliteit is alleen beschikbaar in Adobe Illustrator- en Adobe Photoshop-versies. Voor andere toepassingen wordt het verwijzen uitgevoerd op basis van het relatieve pad van gekoppelde elementen in het hoofdsamengestelde element, zoals dat in eerdere versies van AEM is gebeurd.

## Subelementen maken {#generate-subassets}

Voor de ondersteunde elementen met indelingen die uit meerdere pagina&#39;s bestaan (PDF-bestanden, AI-bestanden, Microsoft PowerPoint- en Apple-toetsenbordbestanden en Adobe InDesign-bestanden), kunnen AEM subelementen genereren die overeenkomen met elke afzonderlijke pagina van het oorspronkelijke element. Deze subelementen zijn gekoppeld aan het *parent*-element en maken de weergave van meerdere pagina&#39;s eenvoudiger. Voor alle andere doeleinden worden de subactiva behandeld als normale activa in AEM.

Genereren van subelementen is standaard uitgeschakeld. Voer de volgende stappen uit om het genereren van subelementen in te schakelen:

1. Meld u aan bij Experience Manager als beheerder. Ga naar **[!UICONTROL Tools > Workflow > Models]**.
1. Selecteer **[!UICONTROL DAM Update Asset]** werkstroom en klik **[!UICONTROL Edit]**.
1. Klik op **[!UICONTROL Toggle Side Panel]** en zoek de stap **[!UICONTROL Create Sub Asset]**. Voeg de stap toe aan de workflow. Klik op **[!UICONTROL Sync]**.

Voer een van de volgende handelingen uit om de subelementen te genereren:

* Nieuwe elementen: De [!UICONTROL DAM Update Assets] workflow wordt uitgevoerd op elk nieuw element dat naar AEM wordt geüpload. Subelementen worden automatisch gegenereerd voor nieuwe elementen die uit meerdere pagina&#39;s bestaan.
* Bestaande elementen met meerdere pagina&#39;s: Voer handmatig de [!UICONTROL DAM Update Assets]-workflow uit volgens een van de volgende stappen:

   * Selecteer een element en klik op [!UICONTROL Timeline] om het linkerdeelvenster te openen. U kunt ook de sneltoets `alt + 3` gebruiken. Klik [!UICONTROL Start Workflow], selecteer [!UICONTROL DAM Update Asset], klik [!UICONTROL Start], en klik [!UICONTROL Proceed].
   * Selecteer een element en klik op [!UICONTROL Create > Workflow] op de werkbalk. Selecteer [!UICONTROL DAM Update Asset] workflow in het pop-updialoogvenster, klik op [!UICONTROL Start] en klik op [!UICONTROL Proceed].

Met name voor Microsoft Word-documenten voert u de **[!UICONTROL DAM Parse Word Documents]**-workflow uit. Er wordt een `cq:Page`-component gegenereerd op basis van de inhoud van het Microsoft Word-document. Er wordt verwezen naar de afbeeldingen die uit het document zijn geëxtraheerd, uit de component `cq:Page`. Deze afbeeldingen worden geëxtraheerd, zelfs als het genereren van subelementen is uitgeschakeld.

## Subelementen {#viewing-subassets} weergeven

De subelementen worden alleen weergegeven als de subelementen zijn gegenereerd en beschikbaar zijn voor het geselecteerde element met meerdere pagina&#39;s. Open het element met meerdere pagina&#39;s om de gegenereerde subelementen weer te geven. Klik in de linkerbovenhoek van de pagina op ![Pictogram Linkerspoor](assets/do-not-localize/aem_leftrail_contentonly.png) en klik op **[!UICONTROL Subassets]** in de lijst. Wanneer u **[!UICONTROL Subassets]** van de lijst selecteert. U kunt ook de sneltoets `alt + 5` gebruiken.

![Subelementen weergeven voor elementen die uit meerdere pagina&#39;s bestaan](assets/view_subassets_simulation.gif)

## Pagina&#39;s van een bestand met meerdere pagina&#39;s {#view-pages-of-a-multi-page-file} weergeven

U kunt een bestand met meerdere pagina&#39;s, zoals PDF, INDD, PPT, PPTX en AI, weergeven met de functie Paginaviewer van AEM Assets. Open een element met meerdere pagina&#39;s en klik op **[!UICONTROL View Pages]** in de linkerbovenhoek van de pagina. In de Paginaviewer die wordt geopend, worden de pagina&#39;s van het element en de besturingselementen weergegeven waarmee u door elke pagina kunt bladeren en erop kunt inzoomen.

![Pagina&#39;s van elementen met meerdere pagina&#39;s weergeven en bekijken](assets/view_multipage_asset_fmr.gif)

Voor InDesign kunt u pagina&#39;s uitnemen met de InDesign-server. Als de voorvertoningen van pagina&#39;s worden opgeslagen tijdens het maken van het InDesign-bestand, is InDesign Server niet vereist voor het uitnemen van pagina&#39;s.

De volgende opties zijn beschikbaar in de werkbalk, in de linkerrails en in de besturingselementen voor de Paginaviewer:

* **[!UICONTROL Desktop Actions]** om een specifiek submiddel te openen of weer te geven met AEM bureaubladtoepassing. Zie hoe u [Bureaubladhandelingen configureren](https://experienceleague.adobe.com/docs/experience-manager-desktop-app/using/using.html?lang=en#desktopactions-v2) als u AEM bureaubladtoepassing gebruikt.

* **[!UICONTROL Properties]** Hiermee opent u de  [!UICONTROL Properties] pagina van het specifieke subelement.

* **[!UICONTROL Annotate]** kunt u het specifieke subelement van een annotatie voorzien. De annotaties die u op afzonderlijke subelementen gebruikt, worden samen verzameld en weergegeven wanneer het bovenliggende element wordt geopend voor weergave.

* **[!UICONTROL Page Overview]** worden alle subelementen tegelijkertijd weergegeven.

* **[!UICONTROL Timeline]** Nadat u op  ![Linkerrails hebt geklikt, wordt de ](assets/do-not-localize/aem_leftrail_contentonly.png) activiteitsstroom voor het bestand weergegeven.

## Beste werkwijzen en beperking {#best-practice-limitation-tips}

* Bij elke implementatie van Experience Managers kan het genereren van subelementen zeer veel resources vergen. Als u subassets genereert wanneer complexe elementen worden geüpload, voegt u de stap toe in de DAM-workflow voor het bijwerken van middelen. Als u op verzoek subassets genereert, maakt u een aparte workflow om subassets te genereren. Met een speciale workflow kunt u de andere stappen in de workflow voor DAM-update-elementen overslaan en computerbronnen opslaan.

>[!MORELIKETHIS]
>
>* [Adobe Experience Manager-bureaubladtoepassing gebruiken](https://experienceleague.adobe.com/docs/experience-manager-desktop-app/using/using.html)

