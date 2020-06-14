---
title: XMP-terugverwijzing naar uitvoeringen
description: Leer hoe de functie XMP-schrijfback de metagegevenswijzigingen voor een element doorgeeft aan alle of aan specifieke uitvoeringen van het element.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 77c62a8f2ca50f8aaff556a6848fabaee71017ce
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 2%

---


# XMP-terugverwijzing naar uitvoeringen {#xmp-writeback-to-renditions}

Met deze functie voor terugschrijven van XMP-gegevens in AEM-elementen (Adobe Experience Manager) worden wijzigingen in de metagegevens van elementen in de uitvoeringen van het element gerepliceerd.

Wanneer u de metagegevens van een element wijzigt vanuit AEM Assets of tijdens het uploaden van het element, worden de wijzigingen in eerste instantie opgeslagen in het knooppunt met elementen in de Crx-De.

De functie Terugschrijven XMP verspreidt de metagegevenswijzigingen in alle of specifieke uitvoeringen van het element.

Neem bijvoorbeeld een scenario waarin u de [!UICONTROL Title] eigenschap van het element `Classic Leather` met de naam wijzigt `Nylon`.

![metadata](assets/metadata.png)

In dit geval slaan de AEM Assets de wijzigingen in de **[!UICONTROL Title]** eigenschap op in de `dc:title` parameter voor de metagegevens van de elementen die in de elementenhiërarchie zijn opgeslagen.

![metadata_stored](assets/metadata_stored.png)

AEM Assets geven echter niet automatisch metagegevenswijzigingen door aan de uitvoeringen van een element.

Met de functie Terugschrijven XMP kunt u de wijzigingen in metagegevens doorgeven aan alle of specifieke uitvoeringen van het element. De wijzigingen worden echter niet opgeslagen onder het metagegevensknooppunt in de elementenhiërarchie. In plaats daarvan worden de wijzigingen in de binaire bestanden voor de uitvoeringen ingesloten.

## XMP-schrijfback inschakelen {#enabling-xmp-writeback}

Om de meta-gegevensveranderingen toe te laten om aan de vertoningen van de activa worden verspreid wanneer het uploaden van het, wijzig de configuratie van de Maker **van de Vertoning van** Adobe CQ DAM in de Manager van de Configuratie.

1. Open Configuratiebeheer vanuit `https://[aem_server]:[port]/system/console/configMgr`.
1. Open de **[!UICONTROL Adobe CQ DAM Rendition Maker]** configuratie.
1. Selecteer de **[!UICONTROL Propagate XMP]** optie en sla de wijzigingen op.

   ![chlimage_1-346](assets/chlimage_1-346.png)

## XMP-schrijfback inschakelen voor specifieke uitvoeringen {#enabling-xmp-writeback-for-specific-renditions}

Als u wilt dat de XMP-terugdraaifunctie metagegevenswijzigingen doorgeeft aan geselecteerde uitvoeringen, geeft u deze uitvoeringen op in de werkstroomstap voor het XMP-terugschrijfproces van de DAM-workflow voor metagegevens terugschrijven. Deze stap is standaard geconfigureerd met de oorspronkelijke uitvoering.

Voer de volgende stappen uit voor de functie Terugschrijven XMP om metagegevens door te geven aan de vertoningsminiaturen 140.100.png en 319.319.png.

1. Navigeer in Experience Manager naar **[!UICONTROL Tools > Workflow > Models]**.
1. Open vanaf de [!UICONTROL Models] pagina het **[!UICONTROL DAM Metadata Writeback]** workflowmodel.
1. Op de pagina met eigenschappen voor **[!UICONTROL DAM Metadata Writeback]** opent u de stap **[!UICONTROL XMP Writeback Process]**.
1. Tik of klik in het dialoogvenster **[!UICONTROL Step Properties]** op het tabblad **[!UICONTROL Process]**.
1. Voeg in het **[!UICONTROL Arguments]** vak toe `rendition:cq5dam.thumbnail.140.100.png,rendition:cq5dam.thumbnail.319.319.png`. Tik of klik op **[!UICONTROL OK]**.

   ![step_properties](assets/step_properties.png)

1. To regenerate the pyramid TIFF renditions for Dynamic Media images with the new attributes, add the **[!UICONTROL Dynamic Media Process Image Assets]** step to the DAM Metadata Writeback workflow.
PTIFF-uitvoeringen worden alleen lokaal gemaakt en opgeslagen in de hybride modus Dynamic Media. Sla de workflow op.

De wijzigingen in de metagegevens worden doorgegeven aan de uitvoeringen `thumbnail.140.100.png` en `thumbnail.319.319.png` het element, en niet aan de andere.

>[!NOTE]
>
>Voor XMP-terugschrijvingsproblemen in 64-bits Linux, zie [How to enable XMP write-back on 64-bit RedHat Linux](https://helpx.adobe.com/experience-manager/kb/enable-xmp-write-back-64-bit-redhat.html).
>
>Zie Voorwaarden voor het schrijven van [XMP-metagegevens voor meer informatie over ondersteunde platforms](/help/sites-deploying/technical-requirements.md#requirements-for-aem-assets-xmp-metadata-write-back).

## XMP-metagegevens filteren {#filtering-xmp-metadata}

[!DNL Experience Manager Assets] ondersteunt zowel geblokkeerde lijsten als toegestane catalogusfiltering van eigenschappen/knooppunten voor XMP-metagegevens die worden gelezen uit binaire elementen van elementen en die worden opgeslagen in JCR wanneer elementen worden opgenomen.

Als u filtert met een geblokkeerde lijst, kunt u alle eigenschappen van XMP-metagegevens importeren, behalve de eigenschappen die voor uitsluiting zijn opgegeven. Voor elementtypen zoals INDD-bestanden met grote hoeveelheden XMP-metagegevens (bijvoorbeeld 1000 knooppunten met 10.000 eigenschappen) zijn de namen van te filteren knooppunten echter niet altijd van tevoren bekend. Als het filtreren gebruikend een geblokkeerde lijst een groot aantal activa met talrijke meta-gegevens XMP om toelaat worden ingevoerd, kan de instantie AEM of de cluster stabiliteitskwesties, bijvoorbeeld verstopte observatierijen ontmoeten.

Door het filteren van XMP-metagegevens via de toegestane lijst verhelpt u dit probleem door de XMP-eigenschappen te definiëren die moeten worden geïmporteerd. Op deze manier worden andere of onbekende XMP-eigenschappen genegeerd. Voor achterwaartse verenigbaarheid, kunt u sommige van deze eigenschappen aan het filter toevoegen dat een geblokkeerde lijst gebruikt.

<!-- TBD: The instructions don't seem to match the UI. I see com.day.cq.dam.commons.metadata.XmpFilterBlackWhite.description
in Config Manager. And the settings are,
com.day.cq.dam.commons.metadata.XmpFilterBlackWhite.xmp.filter.apply_whitelist.name
com.day.cq.dam.commons.metadata.XmpFilterBlackWhite.xmp.filter.whitelist.name
com.day.cq.dam.commons.metadata.XmpFilterBlackWhite.xmp.filter.apply_blacklist.name
com.day.cq.dam.commons.metadata.XmpFilterBlackWhite.xmp.filter.blacklist.name
 
TBD: Make updates to configurations for allow and block list after product updates are done.
-->

>[!NOTE]
>
>Filteren werkt alleen voor de eigenschappen die zijn afgeleid van XMP-bronnen in binaire elementen. Voor de eigenschappen die van niet-XMP bronnen, zoals formaten EXIF en IPTC worden afgeleid, werkt het filtreren niet. De aanmaakdatum van elementen wordt bijvoorbeeld opgeslagen in een eigenschap met de naam EXIF TIFF. `CreateDate` Deze waarde wordt opgeslagen in het metagegevensveld genaamd `exif:DateTimeOriginal`. Aangezien de bron een niet-XMP-bron is, werkt het filteren niet op deze eigenschap.

1. Open Configuratiebeheer vanuit `https://[aem_server]:[port]/system/console/configMgr`.
1. Open de **[!UICONTROL Adobe CQ DAM XmpFilter]** configuratie.
1. Als u filtering wilt toepassen via een toegestane lijst, selecteert u de eigenschappen die u wilt importeren in het **[!UICONTROL Apply Whitelist to XMP Properties]****[!UICONTROL Whitelisted XML Names for XMP filtering]** vak en geeft u deze op.

   ![chlimage_1-347](assets/chlimage_1-347.png)

1. Als u geblokkeerde XMP-eigenschappen wilt uitfilteren nadat u filtering hebt toegepast via de lijst met toegestane waarden, geeft u de eigenschappen in het **[!UICONTROL Blacklisted XML Names for XMP filtering]** vak op. Sla de wijzigingen op.

   >[!NOTE]
   >
   >The **[!UICONTROL Apply Blacklist to XMP Properties]** option is selected by default. Met andere woorden, het filtreren gebruikend een geblokkeerde lijst wordt toegelaten door gebrek. Als u dergelijke filters wilt uitschakelen, schakelt u de **[!UICONTROL Apply Blacklist to XMP Properties]** optie uit.
