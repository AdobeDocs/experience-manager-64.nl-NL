---
title: PDF-rasterizer gebruiken
description: U kunt miniaturen en uitvoeringen van hoge kwaliteit genereren met de Adobe PDF Rasterizer-bibliotheek.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 0d70a672a2944e2c03b54beb3b5f734136792ab1

---


# PDF Rasterizer gebruiken {#using-pdf-rasterizer}

Wanneer u grote, inhoudintensieve PDF- of AI-bestanden uploadt naar Adobe Experience Manager (AEM) Assets, genereert de standaardbibliotheek mogelijk geen nauwkeurige uitvoer. In dergelijke gevallen kan de Adobe PDF Rasterizer-bibliotheek betrouwbaardere en nauwkeurigere uitvoer genereren dan de uitvoer uit een standaardbibliotheek.

Adobe raadt u aan de PDF Rasterizer-bibliotheek te gebruiken voor het volgende:

* AI- of PDF-bestanden met veel inhoud.
* AI- of PDF-bestanden met miniaturen die niet uit het vak zijn gegenereerd.
* AI-bestanden met Pantone Matching System (PMS)-kleuren.

Miniaturen en voorvertoningen die worden gegenereerd met PDF Rasterizer, zijn beter in kwaliteit dan uitvoer in de buitenverpakking en bieden daarom een consistente kijkervaring op verschillende apparaten. De Adobe PDF Rasterizer-bibliotheek ondersteunt geen kleurruimteconversies. De uitvoer wordt altijd naar RGB uitgevoerd, ongeacht de kleurruimte van het bronbestand.

1. Installeer het PDF-rasterpakket op uw AEM-exemplaar vanuit [Package Share](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/product/assets/aem-assets-pdf-rasterizer-pkg).

   >[!NOTE]
   >
   >De PDF Rasterizer-bibliotheek is alleen beschikbaar voor Windows en Linux.

1. Open de AEM Assets workflowconsole vanaf `https://[AEM_server]:[port]/workflow`.
1. Open de pagina **[!UICONTROL met de workflow voor DAM Update Asset]** .
1. Configureer de volgende opties om de standaardminiatuur en het genereren van webvertoningen voor PDF- en AI-bestanden over te slaan:

   * Open de stap **[!UICONTROL Miniatuurproces]** en voeg MIME-typen `application/pdf` toe `application/postscript` of **[!UICONTROL in het veld MIME-typen]** overslaan.
   ![skip_mime_types-2](assets/skip_mime_types-2.png)

   * Voeg op het tabblad Afbeelding **[!UICONTROL voor]** web `application/pdf` of `application/postscript` onder Lijst **[!UICONTROL met]** overslaan toe, afhankelijk van uw vereisten.
   ![web_enabled_imageskiplist](assets/web_enabled_imageskiplist.png)

1. Open de stap **[!UICONTROL PDF/AI-voorvertoning]** van afbeelding omzetten in pixels en verwijder het MIME-type waarvoor u de standaardgeneratie van voorvertoningen van afbeeldingen wilt overslaan. Verwijder bijvoorbeeld het MIME-type *application/pdf*, ** application/postscript of *application/illustrator* uit de lijst **[!UICONTROL MIME-typen]** .

   ![process_arguments](assets/process_arguments.png)

1. Sleep de stap **[!UICONTROL PDF Rasterizer Handler]** van het zijpaneel naar onder de stap **[!UICONTROL Miniaturen]** verwerken.
1. Configureer de volgende argumenten voor de stap **[!UICONTROL PDF Rasterizer Handler]** :

   * MIME-typen: *application/pdf* of *application/postscript*
   * Opdrachten: `PDFRasterizer -d -p 1 -s 1280 -t PNG -i ${file}`
   * Miniatuurgrootten toevoegen: 319:319, 140:100, 48:48. Voeg indien nodig aangepaste miniatuurconfiguratie toe.
   De opdrachtregelargumenten voor de `PDFRasterizer` opdracht kunnen het volgende bevatten:

   **-d**: Vlag om het vloeiend weergeven van tekst, vectorillustraties en afbeeldingen mogelijk te maken. Hiermee maakt u afbeeldingen van betere kwaliteit. Het opnemen van deze parameter zorgt er echter voor dat de opdracht langzaam wordt uitgevoerd en dat de afbeeldingen groter worden.

   `-p`: Paginanummer. De standaardwaarde is alle pagina&#39;s. &#39;*&#39; geeft alle pagina&#39;s aan.

   **-s**: Maximale afmetingen afbeelding (hoogte of breedte). Deze wordt voor elke pagina geconverteerd naar DPI. Als de pagina&#39;s van verschillende grootte zijn, kan elke pagina potentieel met verschillende hoeveelheid schalen. De standaardinstelling is het daadwerkelijke paginaformaat.

   **-t**: Type uitvoerafbeelding. Geldige typen zijn JPEG, PNG, GIF en BMP. De standaardwaarde is JPEG.

   **-i**: Pad voor invoer-PDF. Het is een verplichte parameter.

   `-h`: Help

1. Als u tussenliggende vertoningen wilt verwijderen, selecteert u Gegenereerde vertoning **[!UICONTROL verwijderen]**.
1. Als u wilt dat PDF omzetten in pixels, selecteert u **[!UICONTROL Webvertoning]** genereren.

   ![generate_web_renditions1](assets/generate_web_renditions1.png)

1. Geef de instellingen op op het tabblad Afbeelding **[!UICONTROL voor]** web ingeschakeld.

   ![web_enabled_image1](assets/web_enabled_image1.png)

1. Sla de workflow op.
1. Als u wilt dat PDF-Rasterizer PDF-pagina&#39;s kan verwerken met PDF-bibliotheken, opent u het model **[!UICONTROL DAM Process Subasset]** van de Workflowconsole.
1. Sleep vanuit het zijpaneel de stap PDF Rasterizer Handler onder de stap **[!UICONTROL Webgebaseerde afbeeldingsuitvoering]** maken.
1. Configureer de volgende argumenten voor de stap **[!UICONTROL PDF Rasterizer Handler]** :

   * MIME-typen: `application/pdf` of `application/postscript`
   * Opdrachten: `PDFRasterizer -d -p 1 -s 1280 -t PNG -i ${file}`
   * Miniatuurgrootten toevoegen: 319:319, 140:100, 48:48. Voeg indien nodig aangepaste miniatuurconfiguratie toe.
   De opdrachtregelargumenten voor de opdracht PDFRasterizer kunnen het volgende bevatten:

   **-d**: Vlag om het vloeiend weergeven van tekst, vectorillustraties en afbeeldingen mogelijk te maken. Hiermee maakt u afbeeldingen van betere kwaliteit. Het opnemen van deze parameter zorgt er echter voor dat de opdracht langzaam wordt uitgevoerd en dat de afbeeldingen groter worden.

   **-p**: Paginanummer. De standaardwaarde is alle pagina&#39;s. Met een sterretje worden alle pagina&#39;s `*` aangegeven.

   **-s**: Maximale afmetingen afbeelding (hoogte of breedte). Deze wordt voor elke pagina geconverteerd naar DPI. Als de pagina&#39;s van verschillende grootte zijn, kan elke pagina potentieel met verschillende hoeveelheid schalen. De standaardinstelling is het daadwerkelijke paginaformaat.

   **-t**: Type uitvoerafbeelding. Geldige typen zijn JPEG, PNG, GIF en BMP. De standaardwaarde is JPEG.

   **-i**: Pad voor invoer-PDF. Het is een verplichte parameter.

   **-h**:Help

1. Als u tussenliggende vertoningen wilt verwijderen, selecteert u Gegenereerde vertoning **[!UICONTROL verwijderen]**.
1. Als u wilt dat PDF omzetten in pixels, selecteert u **[!UICONTROL Webvertoning]** genereren.

   ![generate_web_renditions](assets/generate_web_renditions.png)

1. Geef de instellingen op op het tabblad **** Web Enabled Image.

   ![web_enabled_image-1](assets/web_enabled_image-1.png)

1. Sla de workflow op.
1. Upload een PDF- of AI-bestand naar AEM-elementen. PDF-rasterfunctie genereert de miniaturen en webuitvoeringen voor het bestand.
