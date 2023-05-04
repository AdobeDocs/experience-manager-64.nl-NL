---
title: Samengestelde elementen beheren en subelementen genereren.
description: Leer hoe u verwijzingen maakt naar [!DNL Experience Manager] elementen uit InDesign-, Adobe Illustrator- en Photoshop-bestanden. Leer ook hoe u de functie Paginaviewer kunt gebruiken om afzonderlijke pagina's met bestanden van meerdere pagina's weer te geven.
contentOwner: AG
feature: Asset Management
role: User,Admin
exl-id: 9fa44b26-76f7-48e2-a9df-4fd1c0074158
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1354'
ht-degree: 0%

---

# Samengestelde elementen beheren met subelementen {#managing-compound-assets}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Adobe Experience Manager Assets kan bepalen of een geüpload bestand verwijzingen bevat naar elementen die al in de repository bestaan. Deze functie is alleen beschikbaar voor ondersteunde bestandsindelingen. Als het geüploade element verwijzingen bevat naar [!DNL Experience Manager] elementen, wordt een bidirectionele koppeling gemaakt tussen de geüploade en de bestanden waarnaar wordt verwezen.

Naast het elimineren van overtolligheid, verwijzend naar [!DNL Experience Manager] elementen in Adobe Creative Cloud-toepassingen verbeteren de samenwerking en verhogen de efficiëntie en productiviteit van gebruikers.

[!DNL Experience Manager] Elementen worden ondersteund **bidirectionele verwijzing**. U vindt de middelen waarnaar wordt verwezen op de elementdetailpagina van het geüploade bestand. Daarnaast kunt u de bestanden met verwijzingen weergeven voor [!DNL Experience Manager] elementen op de pagina met elementdetails van het element waarnaar wordt verwezen.

Verwijzingen worden opgelost op basis van pad, document-id en instantie-id van de middelen waarnaar wordt verwezen.

## Adobe Illustrator: Elementen toevoegen als verwijzingen {#refai}

U kunt verwijzen naar bestaande [!DNL Experience Manager] elementen uit een Adobe Illustrator-bestand.

1. Gebruiken [[!DNL Experience Manager] bureaubladtoepassing](https://helpx.adobe.com/experience-manager/desktop-app/aem-desktop-app.html), mount [!DNL Experience Manager] De opslagplaats van activa als aandrijving op uw lokale machine. Navigeer in het gekoppelde station naar de locatie van het element waarnaar u wilt verwijzen.
1. Sleep het element van het gekoppelde station naar het Illustrator-bestand.
1. Sla het Illustrator-bestand op het gekoppelde station op, of [uploaden](managing-assets-touch-ui.md#uploading-assets) aan de [!DNL Experience Manager] opslagplaats.
1. Nadat de workflow is voltooid, gaat u naar de pagina met elementdetails voor het element. De verwijzingen naar bestaande [!DNL Experience Manager] activa worden vermeld onder **[!UICONTROL Dependencies]** in de **[!UICONTROL References]** kolom.

   ![chlimage_1-258](assets/chlimage_1-258.png)

1. De middelen waarnaar wordt verwezen, die onder **[!UICONTROL Dependencies]** Er kan ook naar worden verwezen door andere bestanden dan het huidige bestand. Als u een lijst met referentiebestanden voor een element wilt weergeven, klikt u op het element onder in **[!UICONTROL Dependencies]**.

   ![chlimage_1-259](assets/chlimage_1-259.png)

1. Klik op de knop **[!UICONTROL View Properties]** op de werkbalk. Op de pagina met eigenschappen wordt de lijst met bestanden die naar het huidige element verwijzen, weergegeven onder de **[!UICONTROL References]** in de **[!UICONTROL Basic]** tab.

   ![chlimage_1-260](assets/chlimage_1-260.png)

## Adobe InDesign: Elementen toevoegen als verwijzingen {#add-aem-assets-as-references-in-adobe-indesign}

Referentie [!DNL Experience Manager] elementen vanuit een InDesign-bestand: sleep [!DNL Experience Manager] elementen naar het InDesign-bestand of exporteer het InDesign-bestand als een ZIP-bestand.

Er bestaan al elementen waarnaar wordt verwezen in [!DNL Experience Manager] Elementen. U kunt subelementen extraheren via [InDesign-server configureren](indesign.md). Ingesloten elementen in een InDesign-bestand worden geëxtraheerd als subelementen.

>[!NOTE]
>
>Als de InDesign-server proxy is, is de voorvertoning van InDesign-bestanden ingesloten in de XMP metagegevens. In dit geval is het niet expliciet vereist miniatuurextractie uit te voeren. Als de InDesign-server echter geen proxy is, moeten miniaturen expliciet worden uitgepakt voor InDesign-bestanden.

Wanneer een INDD-bestand wordt geüpload, worden de verwijzingen opgehaald door te zoeken naar elementen met `xmpMM:InstanceID` en `xmpMM:DocumentID` in de repository.

### Verwijzingen maken door elementen te slepen {#create-references-by-dragging-aem-assets}

Deze procedure lijkt op [Elementen toevoegen als verwijzingen in Adobe Illustrator](#refai).

### Verwijzingen naar elementen maken door een ZIP-bestand te exporteren {#create-references-to-aem-assets-by-exporting-a-zip-file}

1. Voer de stappen uit in [Workflowmodellen maken](/help/sites-developing/workflows-models.md) om een nieuwe workflow te maken.
1. Gebruik de [Functie voor pakket van Adobe InDesign](https://helpx.adobe.com/indesign/how-to/indesign-package-files-for-handoff.html) om het document te exporteren. Adobe InDesign kan een document en de gekoppelde elementen als een pakket exporteren. In dit geval bevat de geëxporteerde map een `Links` map die subelementen bevat in het InDesign-bestand. De `Links` is aanwezig in dezelfde map als het INDD-bestand.
1. Een ZIP-bestand maken en uploaden naar het [!DNL Experience Manager] opslagplaats.
1. Start de Unarchiver-workflow.
1. Wanneer de werkstroom is voltooid, wordt er automatisch naar de verwijzingen in de map Koppelingen verwezen als subelementen. Als u een lijst met de desbetreffende elementen wilt weergeven, navigeert u naar de pagina met de elementdetails van het element InDesign en sluit u de [Rail](/help/sites-authoring/basic-handling.md#rail-selector).

## Adobe Photoshop: Elementen toevoegen als verwijzingen {#refps}

1. Een WebDav-client gebruiken, koppelen [!DNL Experience Manager] Middelen als een station.
1. Verwijzingen maken naar [!DNL Experience Manager] In een Photoshop-bestand navigeert u met de functie Gekoppelde plaatsen in Photoshop naar de overeenkomstige elementen in het gekoppelde station.

   ![chlimage_1-261](assets/chlimage_1-261.png)

1. Opslaan in Photoshop-bestand naar het gekoppelde station of [uploaden](managing-assets-touch-ui.md#uploading-assets) aan de [!DNL Experience Manager] opslagplaats.
1. Nadat de workflow is voltooid, worden de verwijzingen naar bestaande [!DNL Experience Manager] elementen worden weergegeven op de pagina met elementdetails.

   Als u de middelen waarnaar wordt verwezen wilt weergeven, sluit u het dialoogvenster [Rail](/help/sites-authoring/basic-handling.md#rail-selector) op de pagina met elementdetails.

1. De middelen waarnaar wordt verwezen, bevatten ook de lijst met elementen waarnaar wordt verwezen. Als u een lijst met middelen waarnaar wordt verwezen wilt weergeven, navigeert u naar de pagina met elementdetails en sluit u de [spoor](/help/sites-authoring/basic-handling.md#rail-selector).

>[!NOTE]
>
>Er kan ook worden verwezen naar de elementen in samengestelde elementen op basis van hun document-id en instantie-id. Deze functionaliteit is alleen beschikbaar in Adobe Illustrator- en Adobe Photoshop-versies. Voor andere toepassingen wordt het verwijzen uitgevoerd op basis van het relatieve pad van gekoppelde elementen in het hoofdsamengestelde element, zoals dat in eerdere versies van AEM is gebeurd.

## Subelementen maken {#generate-subassets}

Voor de ondersteunde elementen met indelingen die uit meerdere pagina&#39;s bestaan — PDF-bestanden, AI-bestanden, Microsoft PowerPoint- en Apple-toetsenbordbestanden en Adobe InDesign-bestanden — [!DNL Experience Manager] U kunt subelementen genereren die overeenkomen met elke afzonderlijke pagina van het oorspronkelijke element. Deze subassets zijn gekoppeld aan de *parent* elementen toevoegen en de weergave van meerdere pagina&#39;s vergemakkelijken. Voor alle andere doeleinden worden de subactiva behandeld als normale activa in AEM.

Genereren van subelementen is standaard uitgeschakeld. Voer de volgende stappen uit om het genereren van subelementen in te schakelen:

1. Meld u aan bij Experience Manager als beheerder. Ga naar **[!UICONTROL Tools > Workflow > Models]**.
1. Selecteren **[!UICONTROL DAM Update Asset]** workflow en klik op **[!UICONTROL Edit]**.
1. Klikken **[!UICONTROL Toggle Side Panel]** en zoek de **[!UICONTROL Create Sub Asset]** stap. Voeg de stap toe aan de workflow. Klik op **[!UICONTROL Sync]**.

Voer een van de volgende handelingen uit om de subelementen te genereren:

* Nieuwe elementen: De [!UICONTROL DAM Update Assets] wordt uitgevoerd op elk nieuw element dat naar AEM wordt geüpload. Subelementen worden automatisch gegenereerd voor nieuwe elementen die uit meerdere pagina&#39;s bestaan.
* Bestaande elementen met meerdere pagina&#39;s: Handmatig het dialoogvenster [!UICONTROL DAM Update Assets] workflow volgens een van de volgende stappen:

   * Selecteer een element en klik op [!UICONTROL Timeline] om het linkerdeelvenster te openen. U kunt ook de sneltoets gebruiken `alt + 3`. Klikken [!UICONTROL Start Workflow], selecteert u [!UICONTROL DAM Update Asset], klikt u op [!UICONTROL Start]en klik op [!UICONTROL Proceed].
   * Selecteer een element en klik op [!UICONTROL Create > Workflow] op de werkbalk. Selecteer in het pop-updialoogvenster de optie [!UICONTROL DAM Update Asset] workflow, klik op [!UICONTROL Start]en klik op [!UICONTROL Proceed].

Met name voor Microsoft Word-documenten voert u de opdracht **[!UICONTROL DAM Parse Word Documents]** workflow. Het genereert een `cq:Page` uit de inhoud van het Microsoft Word-document. Er wordt verwezen naar de afbeeldingen die uit het document zijn geëxtraheerd. `cq:Page` component. Deze afbeeldingen worden geëxtraheerd, zelfs als het genereren van subelementen is uitgeschakeld.

## Subelementen weergeven {#viewing-subassets}

De subelementen worden alleen weergegeven als de subelementen zijn gegenereerd en beschikbaar zijn voor het geselecteerde element met meerdere pagina&#39;s. Open het element met meerdere pagina&#39;s om de gegenereerde subelementen weer te geven. Klik in de linkerbovenhoek van de pagina op ![Linkerspoorpictogram](assets/do-not-localize/aem_leftrail_contentonly.png) en klik op **[!UICONTROL Subassets]** in de lijst. Wanneer u **[!UICONTROL Subassets]** in de lijst. U kunt ook de sneltoets gebruiken `alt + 5`.

![Subelementen weergeven voor elementen die uit meerdere pagina&#39;s bestaan](assets/view_subassets_simulation.gif)

## Pagina&#39;s van een bestand met meerdere pagina&#39;s weergeven {#view-pages-of-a-multi-page-file}

U kunt een bestand met meerdere pagina&#39;s, zoals PDF, INDD, PPT, PPTX en AI, weergeven met de functie Paginaviewer van [!DNL Experience Manager] Elementen. Een element met meerdere pagina&#39;s openen en klikken **[!UICONTROL View Pages]** in de linkerbovenhoek van de pagina. In de Paginaviewer die wordt geopend, worden de pagina&#39;s van het element en de besturingselementen weergegeven waarmee u door elke pagina kunt bladeren en erop kunt inzoomen.

![Pagina&#39;s van elementen met meerdere pagina&#39;s weergeven en bekijken](assets/view_multipage_asset_fmr.gif)

Voor InDesign kunt u pagina&#39;s uitnemen met de InDesign-server. Als de voorvertoningen van pagina&#39;s worden opgeslagen tijdens het maken van het InDesign-bestand, is InDesign Server niet vereist voor het uitnemen van pagina&#39;s.

De volgende opties zijn beschikbaar in de werkbalk, in de linkerrails en in de besturingselementen voor de Paginaviewer:

* **[!UICONTROL Desktop Actions]** om een specifiek subelement te openen of te tonen met [!DNL Experience Manager] bureaubladtoepassing. Zie hoe te [Desktophandelingen configureren](https://experienceleague.adobe.com/docs/experience-manager-desktop-app/using/using.html#desktopactions-v2) als u [!DNL Experience Manager] bureaubladtoepassing.

* **[!UICONTROL Properties]** wordt geopend [!UICONTROL Properties] pagina van het specifieke subelement.

* **[!UICONTROL Annotate]** kunt u het specifieke subelement van een annotatie voorzien. De annotaties die u op afzonderlijke subelementen gebruikt, worden samen verzameld en weergegeven wanneer het bovenliggende element wordt geopend voor weergave.

* **[!UICONTROL Page Overview]** worden alle subelementen tegelijkertijd weergegeven.

* **[!UICONTROL Timeline]** optie van de linkerspoorstaaf na het klikken ![Linkerspoorpictogram](assets/do-not-localize/aem_leftrail_contentonly.png) geeft de activiteitsstroom voor het bestand weer.

## Beste werkwijzen en beperking {#best-practice-limitation-tips}

* Bij elke implementatie van Experience Managers kan het genereren van subelementen zeer veel resources vergen. Als u subassets genereert wanneer complexe elementen worden geüpload, voegt u de stap toe in de DAM-workflow voor het bijwerken van middelen. Als u op verzoek subassets genereert, maakt u een aparte workflow om subassets te genereren. Met een speciale workflow kunt u de andere stappen in de workflow voor DAM-update-elementen overslaan en computerbronnen opslaan.

>[!MORELIKETHIS]
>
>* [Adobe Experience Manager-bureaubladtoepassing gebruiken](https://experienceleague.adobe.com/docs/experience-manager-desktop-app/using/using.html)

