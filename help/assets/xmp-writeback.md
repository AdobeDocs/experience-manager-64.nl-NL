---
title: Terugverwijzing naar vertoningen XMP
description: Leer hoe de functie XMP terugschrijven de metagegevenswijzigingen voor een element doorgeeft aan alle of aan specifieke uitvoeringen van het element.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 31d652ee04fe75e96f96c9ddc5a6f2c3c64bd630
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 2%

---


# Terugverwijzing naar vertoningen XMP {#xmp-writeback-to-renditions}

Met deze XMP terugdraaifunctie in Adobe Experience Manager-elementen (AEM) worden wijzigingen in de metagegevens van elementen overgenomen in de uitvoeringen van het element.

Wanneer u de metagegevens voor een element wijzigt vanuit AEM Assets of wanneer u het element uploadt, worden wijzigingen in eerste instantie opgeslagen in het knooppunt met elementen in de map Crx-De.

De functie XMP terugschrijven geeft de metagegevenswijzigingen door in alle of in specifieke uitvoeringen van het element.

Neem bijvoorbeeld een scenario waarin u de [!UICONTROL Title] eigenschap van het element `Classic Leather` met de naam wijzigt `Nylon`.

![metadata](assets/metadata.png)

In dit geval slaat de AEM Assets de wijzigingen in de **[!UICONTROL Title]** eigenschap op in de `dc:title` parameter voor de metagegevens van de elementen die zijn opgeslagen in de elementenhiërarchie.

![metadata_stored](assets/metadata_stored.png)

AEM Assets verspreidt echter niet automatisch metagegevenswijzigingen in de uitvoeringen van een element.

Met de functie XMP terugdraaien kunt u de wijzigingen in metagegevens doorgeven aan alle of specifieke uitvoeringen van het element. De wijzigingen worden echter niet opgeslagen onder het metagegevensknooppunt in de elementenhiërarchie. In plaats daarvan worden de wijzigingen in de binaire bestanden voor de uitvoeringen ingesloten.

## Terugschrijven XMP inschakelen {#enabling-xmp-writeback}

Om de meta-gegevensveranderingen toe te laten die aan de vertoningen van het middel worden verspreid wanneer het uploaden van het, wijzig de configuratie van de Maker **van de Vertoning van** Adobe CQ DAM in de Manager van de Configuratie.

1. Open Configuratiebeheer vanuit `https://[aem_server]:[port]/system/console/configMgr`.
1. Open de **[!UICONTROL Adobe CQ DAM Rendition Maker]** configuratie.
1. Selecteer de **[!UICONTROL Propagate XMP]** optie en sla de wijzigingen op.

   ![chlimage_1-346](assets/chlimage_1-346.png)

## Terugschrijven XMP inschakelen voor specifieke uitvoeringen {#enabling-xmp-writeback-for-specific-renditions}

Als u wilt dat de functie XMP terugschrijven wijzigingen in metagegevens doorgeeft aan geselecteerde uitvoeringen, geeft u deze uitvoeringen op in de werkstroomstap XMP terugschrijfproces van DAM-metagegevens terugschrijven. Deze stap is standaard geconfigureerd met de oorspronkelijke uitvoering.

Voer de volgende stappen uit voor de functie XMP terugschrijven om metagegevens door te geven aan de vertoningsminiaturen 140.100.png en 319.319.png.

1. Navigeer in Experience Manager naar **[!UICONTROL Tools > Workflow > Models]**.
1. Open vanaf de [!UICONTROL Models] pagina het **[!UICONTROL DAM Metadata Writeback]** workflowmodel.
1. Op de pagina met eigenschappen voor **[!UICONTROL DAM Metadata Writeback]** opent u de stap **[!UICONTROL XMP Writeback Process]**.
1. Tik of klik in het dialoogvenster **[!UICONTROL Step Properties]** op het tabblad **[!UICONTROL Process]**.
1. Voeg in het **[!UICONTROL Arguments]** vak toe `rendition:cq5dam.thumbnail.140.100.png,rendition:cq5dam.thumbnail.319.319.png`. Tik of klik op **[!UICONTROL OK]**.

   ![step_properties](assets/step_properties.png)

1. To regenerate the pyramid TIFF renditions for Dynamic Media images with the new attributes, add the **[!UICONTROL Dynamic Media Process Image Assets]** step to the DAM Metadata Writeback workflow.
PTIFF-uitvoeringen worden alleen lokaal gemaakt en opgeslagen in de hybride modus Dynamische media. Sla de workflow op.

De wijzigingen in de metagegevens worden doorgegeven aan de uitvoeringen `thumbnail.140.100.png` en `thumbnail.319.319.png` het element, en niet aan de andere.

>[!NOTE]
>
>Voor XMP terugzetproblemen in Linux met 64 bits, zie [hoe te XMP terugschrijven op Linux](https://helpx.adobe.com/experience-manager/kb/enable-xmp-write-back-64-bit-redhat.html)met 64 bits toe te laten.
>
>Zie [XMP voorwaarden voor het terugschrijven van metagegevens voor meer informatie over ondersteunde platforms](/help/sites-deploying/technical-requirements.md#requirements-for-aem-assets-xmp-metadata-write-back).

## XMP {#filtering-xmp-metadata}

[!DNL Experience Manager Assets] ondersteunt zowel het filteren van lijsten van afgewezen personen als lijsten van gewenste personen van eigenschappen/knooppunten voor XMP metagegevens die worden gelezen van binaire elementen en worden opgeslagen in JCR wanneer elementen worden ingeslikt.

Als u filtert met een lijst van afgewezen personen, kunt u alle eigenschappen van XMP metagegevens importeren, behalve de eigenschappen die voor uitsluiting zijn opgegeven. Voor elementtypen zoals INDD-bestanden met grote hoeveelheden XMP metagegevens (bijvoorbeeld 1000 knooppunten met 10.000 eigenschappen) zijn de namen van knooppunten die moeten worden gefilterd niet altijd van tevoren bekend. Als het filtreren gebruikend een lijst van afgewezen personen een groot aantal activa met talrijke XMP meta-gegevens om toelaat worden ingevoerd, kan de AEM instantie of de cluster stabiliteitskwesties, bijvoorbeeld verstopte observatierijen ontmoeten.

Door het filteren van XMP metagegevens via lijst van gewenste personen wordt dit probleem opgelost doordat u de XMP eigenschappen kunt definiëren die moeten worden geïmporteerd. Op deze manier worden andere of onbekende XMP eigenschappen genegeerd. Voor achterwaartse compatibiliteit kunt u enkele van deze eigenschappen toevoegen aan het filter dat een lijst van afgewezen personen gebruikt.

>[!NOTE]
>
>Filteren werkt alleen voor de eigenschappen die zijn afgeleid van XMP bronnen in binaire elementen. Voor de eigenschappen die van niet-XMP bronnen, zoals formaten EXIF en IPTC worden afgeleid, werkt het filtreren niet. De aanmaakdatum van elementen wordt bijvoorbeeld opgeslagen in een eigenschap met de naam EXIF TIFF. `CreateDate` AEM slaat deze waarde op in het genoemde metagegevensveld `exif:DateTimeOriginal`. Aangezien de bron een niet-XMP bron is, werkt het filtreren niet aan dit bezit.

1. Open Configuratiebeheer vanuit `https://[aem_server]:[port]/system/console/configMgr`.
1. Open de **[!UICONTROL Adobe CQ DAM XmpFilter]** configuratie.
1. Als u filters wilt toepassen via een lijst van gewenste personen, selecteert u de eigenschappen die u wilt importeren in het **[!UICONTROL Apply Allowlist to XMP Properties]****[!UICONTROL Allowed XML Names for XMP filtering]** vak en geeft u deze op.

   ![chlimage_1-347](assets/chlimage_1-347.png)

1. Als u geblokkeerde XMP wilt uitfilteren nadat u filtert via lijst van gewenste personen hebt toegepast, geeft u de eigenschappen in het **[!UICONTROL Blocked XML Names for XMP filtering]** vak op. Sla de wijzigingen op.

   >[!NOTE]
   >
   >The **[!UICONTROL Apply Blocklist to XMP Properties]** option is selected by default. Met andere woorden, filteren met een lijst van afgewezen personen wordt standaard ingeschakeld. Als u dergelijke filters wilt uitschakelen, schakelt u de **[!UICONTROL Apply Blocklist to XMP Properties]** optie uit.
