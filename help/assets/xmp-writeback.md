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

Overweeg een scenario waarbij u de [!UICONTROL Title] eigenschap van het element `Classic Leather` aan `Nylon` wijzigt.

![metadata](assets/metadata.png)

In dit geval slaat de AEM Assets de wijzigingen in de eigenschap **[!UICONTROL Title]** op in de parameter `dc:title` voor de metagegevens van de elementen die zijn opgeslagen in de elementenhiërarchie.

![metadata_stored](assets/metadata_stored.png)

AEM Assets verspreidt echter niet automatisch metagegevenswijzigingen in de uitvoeringen van een element.

Met de functie XMP terugdraaien kunt u de wijzigingen in metagegevens doorgeven aan alle of specifieke uitvoeringen van het element. De wijzigingen worden echter niet opgeslagen onder het metagegevensknooppunt in de elementenhiërarchie. In plaats daarvan worden de wijzigingen in de binaire bestanden voor de uitvoeringen ingesloten.

## Terugschrijven XMP {#enabling-xmp-writeback} inschakelen

Om de meta-gegevensveranderingen toe te laten die aan de vertoningen van het element worden verspreid wanneer het uploaden van het, wijzig **Adobe CQ DAM de configuratie van de Vertoningsmaker** in de Manager van de Configuratie.

1. Open Configuration Manager van `https://[aem_server]:[port]/system/console/configMgr`.
1. Open de **[!UICONTROL Adobe CQ DAM Rendition Maker]** configuratie.
1. Selecteer de optie **[!UICONTROL Propagate XMP]** en sla de wijzigingen op.

   ![chlimage_1-346](assets/chlimage_1-346.png)

## Terugschrijven XMP inschakelen voor specifieke uitvoeringen {#enabling-xmp-writeback-for-specific-renditions}

Als u wilt dat de functie XMP terugschrijven wijzigingen in metagegevens doorgeeft aan geselecteerde uitvoeringen, geeft u deze uitvoeringen op in de werkstroomstap XMP terugschrijfproces van DAM-metagegevens terugschrijven. Deze stap is standaard geconfigureerd met de oorspronkelijke uitvoering.

Voer de volgende stappen uit voor de functie XMP terugschrijven om metagegevens door te geven aan de vertoningsminiaturen 140.100.png en 319.319.png.

1. Navigeer in Experience Manager naar **[!UICONTROL Tools > Workflow > Models]**.
1. Open op de pagina [!UICONTROL Models] het workflowmodel **[!UICONTROL DAM Metadata Writeback]**.
1. Op de pagina met eigenschappen voor **[!UICONTROL DAM Metadata Writeback]** opent u de stap **[!UICONTROL XMP Writeback Process]**.
1. Tik of klik in het dialoogvenster **[!UICONTROL Step Properties]** op het tabblad **[!UICONTROL Process]**.
1. Voeg `rendition:cq5dam.thumbnail.140.100.png,rendition:cq5dam.thumbnail.319.319.png` toe in het tekstvak **[!UICONTROL Arguments]**. Tik of klik op **[!UICONTROL OK]**.

   ![step_properties](assets/step_properties.png)

1. Als u de piramide TIFF-uitvoeringen voor Dynamic Media-afbeeldingen met de nieuwe kenmerken opnieuw wilt genereren, voegt u de stap **[!UICONTROL Dynamic Media Process Image Assets]** toe aan de terugdraaiworkflow voor DAM-metagegevens.
PTIFF-uitvoeringen worden alleen lokaal gemaakt en opgeslagen in een Dynamic Media Hybrid-modus. Sla de workflow op.

De meta-gegevensveranderingen worden verspreid aan de vertoningen `thumbnail.140.100.png` en `thumbnail.319.319.png` van het middel, en niet de anderen.

>[!NOTE]
>
>Zie [Hoe kan ik XMP terugschrijven inschakelen bij 64-bits RedHat Linux](https://helpx.adobe.com/experience-manager/kb/enable-xmp-write-back-64-bit-redhat.html) voor XMP terugschrijvingsproblemen in Linux met 64 bits.
>
>Zie [XMP voorwaarden voor het terugschrijven van metagegevens](/help/sites-deploying/technical-requirements.md#requirements-for-aem-assets-xmp-metadata-write-back) voor meer informatie over ondersteunde platforms.

## XMP metagegevens filteren {#filtering-xmp-metadata}

[!DNL Experience Manager Assets] ondersteunt zowel het filteren van lijsten van afgewezen personen als lijsten van gewenste personen van eigenschappen/knooppunten voor XMP metagegevens die worden gelezen van binaire elementen en worden opgeslagen in JCR wanneer elementen worden ingeslikt.

Als u filtert met een lijst van afgewezen personen, kunt u alle eigenschappen van XMP metagegevens importeren, behalve de eigenschappen die voor uitsluiting zijn opgegeven. Voor elementtypen zoals INDD-bestanden met grote hoeveelheden XMP metagegevens (bijvoorbeeld 1000 knooppunten met 10.000 eigenschappen) zijn de namen van knooppunten die moeten worden gefilterd niet altijd van tevoren bekend. Als het filtreren gebruikend een lijst van afgewezen personen een groot aantal activa met talrijke XMP meta-gegevens om toelaat worden ingevoerd, kan de AEM instantie of de cluster stabiliteitskwesties, bijvoorbeeld verstopte observatierijen ontmoeten.

Door het filteren van XMP metagegevens via lijst van gewenste personen verhelpt u dit probleem door de XMP te definiëren die moeten worden geïmporteerd. Op deze manier worden andere of onbekende XMP eigenschappen genegeerd. Voor achterwaartse compatibiliteit kunt u enkele van deze eigenschappen toevoegen aan het filter dat een lijst van afgewezen personen gebruikt.

>[!NOTE]
>
>Filteren werkt alleen voor de eigenschappen die zijn afgeleid van XMP bronnen in binaire elementen. Voor de eigenschappen die van niet-XMP bronnen, zoals formaten EXIF en IPTC worden afgeleid, werkt het filtreren niet. De aanmaakdatum van elementen wordt bijvoorbeeld opgeslagen in de eigenschap `CreateDate` in EXIF TIFF. AEM slaat deze waarde op in het metagegevensveld `exif:DateTimeOriginal`. Aangezien de bron een niet-XMP bron is, werkt het filtreren niet aan dit bezit.

1. Open Configuration Manager van `https://[aem_server]:[port]/system/console/configMgr`.
1. Open de **[!UICONTROL Adobe CQ DAM XmpFilter]** configuratie.
1. Als u filteren via een lijst van gewenste personen wilt toepassen, selecteert u **[!UICONTROL Apply Allowlist to XMP Properties]** en geeft u in het vak **[!UICONTROL Allowed XML Names for XMP filtering]** de eigenschappen op die u wilt importeren.

   ![chlimage_1-347](assets/chlimage_1-347.png)

1. Om geblokkeerde XMP eigenschappen na het toepassen van filter via lijst van gewenste personen uit te filtreren, specificeer die in **[!UICONTROL Blocked XML Names for XMP filtering]** doos. Sla de wijzigingen op.

   >[!NOTE]
   >
   >De optie **[!UICONTROL Apply Blocklist to XMP Properties]** is standaard geselecteerd. Met andere woorden, filteren met een lijst van afgewezen personen wordt standaard ingeschakeld. Als u dergelijke filters wilt uitschakelen, schakelt u de optie **[!UICONTROL Apply Blocklist to XMP Properties]** uit.
