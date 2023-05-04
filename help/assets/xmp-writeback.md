---
title: Terugverwijzing naar vertoningen XMP
description: Leer hoe de functie XMP terugschrijven de metagegevenswijzigingen voor een element doorgeeft aan alle of aan specifieke uitvoeringen van het element.
contentOwner: AG
feature: Metadata
role: User,Admin
exl-id: 456f8c91-aacf-4db5-a329-2d1650ff0f2f
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '748'
ht-degree: 2%

---

# Terugverwijzing naar vertoningen XMP {#xmp-writeback-to-renditions}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Deze XMP functie voor terugschrijven in [!DNL Adobe Experience Manager Assets] Hiermee worden de wijzigingen in de metagegevens van de uitvoeringen van het oorspronkelijke element gerepliceerd. Wanneer u de metagegevens van een element wijzigt vanuit Middelen of tijdens het uploaden van het element, worden de wijzigingen in eerste instantie opgeslagen in het metagegevensknooppunt in de elementenhiërarchie.

Met de functie XMP terugschrijven kunt u de wijzigingen in metagegevens doorgeven aan alle of specifieke uitvoeringen van het element. De functie schrijft alleen die metagegevenseigenschappen terug die `jcr` namespace, dat wil zeggen, een eigenschap met de naam `dc:title` is teruggeschreven maar een eigenschap met een naam `mytitle` is niet.

Overweeg een scenario waar u wijzigt [!UICONTROL Title] eigendom van het getitelde actief `Classic Leather` tot `Nylon`.

![metagegevens](assets/metadata.png)

In dit geval worden de [!DNL Experience Manager] Elementen slaan de wijzigingen in de **[!UICONTROL Title]** eigenschap in de `dc:title` parameter voor de metagegevens van elementen die zijn opgeslagen in de elementhiërarchie.

![metadata_stored](assets/metadata_stored.png)

Maar [!DNL Experience Manager Assets] geeft automatisch geen metagegevenswijzigingen door aan de uitvoeringen van een element. Zie [hoe te om XMP terug te zetten](#enabling-xmp-writeback).

## Terugschrijven XMP inschakelen {#enabling-xmp-writeback}

Als u wilt dat de wijzigingen in metagegevens tijdens het uploaden naar de uitvoeringen van het element kunnen worden doorgegeven, wijzigt u de instelling **Adobe CQ DAM Rendition Maker** configuratie in de Manager van de Configuratie.

1. Configuratiebeheer openen vanuit `https://[aem_server]:[port]/system/console/configMgr`.
1. Open de **[!UICONTROL Adobe CQ DAM Rendition Maker]** configuratie.
1. Selecteer **[!UICONTROL Propagate XMP]** en slaat u de wijzigingen op.

   ![chlimage_1-346](assets/chlimage_1-346.png)

## Terugschrijven XMP inschakelen voor specifieke uitvoeringen {#enabling-xmp-writeback-for-specific-renditions}

Als u wilt dat de functie XMP terugschrijven wijzigingen in metagegevens doorgeeft aan geselecteerde uitvoeringen, geeft u deze uitvoeringen op in de werkstroomstap XMP terugschrijfproces van DAM-metagegevens terugschrijven. Deze stap is standaard geconfigureerd met de oorspronkelijke uitvoering.

Voer de volgende stappen uit voor de functie XMP terugschrijven om metagegevens door te geven aan de vertoningsminiaturen 140.100.png en 319.319.png.

1. Navigeer in Experience Manager naar **[!UICONTROL Tools > Workflow > Models]**.
1. Van de [!UICONTROL Models] pagina, opent u de **[!UICONTROL DAM Metadata Writeback]** workflowmodel.
1. Op de pagina met eigenschappen voor **[!UICONTROL DAM Metadata Writeback]** opent u de stap **[!UICONTROL XMP Writeback Process]**.
1. Tik of klik in het dialoogvenster **[!UICONTROL Step Properties]** op het tabblad **[!UICONTROL Process]**.
1. In de **[!UICONTROL Arguments]** vak, toevoegen `rendition:cq5dam.thumbnail.140.100.png,rendition:cq5dam.thumbnail.319.319.png`. Tik of klik op **[!UICONTROL OK]**.

   ![step_properties](assets/step_properties.png)

1. Als u de TIFF-piramide-uitvoeringen voor Dynamic Media-afbeeldingen opnieuw wilt genereren met de nieuwe kenmerken, voegt u de opdracht **[!UICONTROL Dynamic Media Process Image Assets]** stap naar de terugdraaiworkflow voor DAM-metagegevens.
PTIFF-uitvoeringen worden alleen lokaal gemaakt en opgeslagen in een Dynamic Media Hybrid-modus. Sla de workflow op.

De wijzigingen in de metagegevens worden doorgegeven aan de uitvoeringen `thumbnail.140.100.png` en `thumbnail.319.319.png` van het actief, en niet de andere.

>[!NOTE]
>
>Voor XMP terugzetproblemen in 64-bits Linux raadpleegt u [XMP terugschrijven inschakelen bij 64-bits RedHat Linux](https://helpx.adobe.com/experience-manager/kb/enable-xmp-write-back-64-bit-redhat.html).
>
>Voor meer informatie over ondersteunde platforms raadpleegt u [Voorwaarden voor het terugschrijven van metagegevens XMP](/help/sites-deploying/technical-requirements.md#requirements-for-aem-assets-xmp-metadata-write-back).

## XMP {#filtering-xmp-metadata}

[!DNL Experience Manager Assets] ondersteunt zowel het filteren van lijsten van gewezen personen als lijsten van gewenste personen van eigenschappen/knooppunten voor XMP metagegevens die worden gelezen van binaire elementen en worden opgeslagen in JCR wanneer elementen worden opgenomen.

Als u filtert met een lijst van gewezen personen, kunt u alle eigenschappen van XMP metagegevens importeren, behalve de eigenschappen die voor uitsluiting zijn opgegeven. Voor elementtypen zoals INDD-bestanden met grote hoeveelheden XMP metagegevens (bijvoorbeeld 1000 knooppunten met 10.000 eigenschappen) zijn de namen van knooppunten die moeten worden gefilterd niet altijd van tevoren bekend. Als door filtering met een lijst van gewezen personen een groot aantal elementen met een groot aantal XMP metagegevens kan worden geïmporteerd, [!DNL Experience Manager] instantie of cluster kan stabiliteitsproblemen ondervinden, bijvoorbeeld verstopte wachtrijen voor waarneming.

Door het filteren van XMP metagegevens via lijst van gewenste personen verhelpt u dit probleem door de XMP te definiëren die moeten worden geïmporteerd. Op deze manier worden andere of onbekende XMP eigenschappen genegeerd. Voor achterwaartse compatibiliteit kunt u enkele van deze eigenschappen toevoegen aan het filter dat een lijst van gewezen personen gebruikt.

>[!NOTE]
>
>Filteren werkt alleen voor de eigenschappen die zijn afgeleid van XMP bronnen in binaire elementen. Voor de eigenschappen die van niet-XMP bronnen, zoals formaten EXIF en IPTC worden afgeleid, werkt het filtreren niet. De aanmaakdatum van het element wordt bijvoorbeeld opgeslagen in een eigenschap met de naam `CreateDate` in EXIF TIFF. [!DNL Experience Manager] slaat deze waarde in genoemd meta-gegevensgebied op `exif:DateTimeOriginal`. Aangezien de bron een niet-XMP bron is, werkt het filtreren niet aan dit bezit.

1. Configuratiebeheer openen vanuit `https://[aem_server]:[port]/system/console/configMgr`.
1. Open de **[!UICONTROL Adobe CQ DAM XmpFilter]** configuratie.
1. Als u filteren via een lijst van gewenste personen wilt toepassen, selecteert u **[!UICONTROL Apply Allowlist to XMP Properties]** en geeft u de eigenschappen op die u wilt importeren in het dialoogvenster **[!UICONTROL Allowed XML Names for XMP filtering]** doos.

   ![chlimage_1-347](assets/chlimage_1-347.png)

1. Om geblokkeerde XMP eigenschappen na het toepassen van filter via lijst van gewenste personen uit te filteren, specificeer die in **[!UICONTROL Blocked XML Names for XMP filtering]** doos. Sla de wijzigingen op.

   >[!NOTE]
   >
   >De **[!UICONTROL Apply Blocklist to XMP Properties]** is standaard geselecteerd. Met andere woorden, filteren met een lijst van gewezen personen wordt standaard ingeschakeld. Als u dergelijke filters wilt uitschakelen, schakelt u de optie **[!UICONTROL Apply Blocklist to XMP Properties]** optie.
