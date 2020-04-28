---
title: XMP-terugverwijzing naar uitvoeringen
description: Leer hoe de functie XMP-schrijfback de metagegevenswijzigingen voor een element doorgeeft aan alle of aan specifieke uitvoeringen van het element.
contentOwner: AG
translation-type: tm+mt
source-git-commit: eb135e5898fe521498eecae7109b39f54d274cce

---


# XMP-terugverwijzing naar uitvoeringen {#xmp-writeback-to-renditions}

Met deze functie voor terugschrijven van XMP-gegevens in Adobe Experience Manager (AEM) Elementen worden wijzigingen in de metagegevens van elementen overgenomen in de uitvoeringen van het element.

Wanneer u de metagegevens voor een element wijzigt vanuit AEM-elementen of wanneer u het element uploadt, worden de wijzigingen in eerste instantie opgeslagen in het knooppunt met elementen in Crx-De.

De functie Terugschrijven XMP verspreidt de metagegevenswijzigingen in alle of specifieke uitvoeringen van het element.

Overweeg een scenario waar u het bezit van de [!UICONTROL Titel] van het element `Classic Leather` aan `Nylon`. wijzigt.

![metadata](assets/metadata.png)

In dit geval slaat AEM Assets de veranderingen in het bezit van de **[!UICONTROL Titel]** in de `dc:title` parameter voor de activa op die meta-gegevens in de activahiërarchie worden opgeslagen.

![metadata_stored](assets/metadata_stored.png)

AEM-elementen geven echter niet automatisch metagegevenswijzigingen door in de uitvoeringen van een element.

Met de functie Terugschrijven XMP kunt u de wijzigingen in metagegevens doorgeven aan alle of specifieke uitvoeringen van het element. De wijzigingen worden echter niet opgeslagen onder het metagegevensknooppunt in de elementenhiërarchie. In plaats daarvan worden de wijzigingen in de binaire bestanden voor de uitvoeringen ingesloten.

## XMP-schrijfback inschakelen {#enabling-xmp-writeback}

Om de meta-gegevensveranderingen toe te laten om aan de vertoningen van de activa worden verspreid wanneer het uploaden van het, wijzig de configuratie van de Maker **van de Vertoning van** Adobe CQ DAM in de Manager van de Configuratie.

1. Open Configuratiebeheer vanuit `https://[aem_server]:[port]/system/console/configMgr`.
1. Open de configuratie van **[!UICONTROL Adobe CQ DAM Rendition Maker]** .
1. Selecteer de optie **[!UICONTROL XMP]** doorgeven en sla de wijzigingen op.

   ![chlimage_1-346](assets/chlimage_1-346.png)

## XMP-schrijfback inschakelen voor specifieke uitvoeringen {#enabling-xmp-writeback-for-specific-renditions}

Als u wilt dat de XMP-terugdraaifunctie metagegevenswijzigingen doorgeeft aan geselecteerde uitvoeringen, geeft u deze uitvoeringen op in de werkstroomstap voor het XMP-terugschrijfproces van de DAM-workflow voor metagegevens terugschrijven. Deze stap is standaard geconfigureerd met de oorspronkelijke uitvoering.

Voer de volgende stappen uit voor de functie Terugschrijven XMP om metagegevens door te geven aan de vertoningsminiaturen 140.100.png en 319.319.png.

1. Navigeer in Experience Manager naar **[!UICONTROL Extra > Workflow > Modellen]**.
1. Open vanaf de pagina [!UICONTROL Modellen] het workflowmodel voor terugschrijven van **[!UICONTROL DAM-metagegevens]** .
1. Open de stap **[!UICONTROL XMP-terugschrijfproces]** op de pagina met eigenschappen voor terugschrijven van metagegevens van **[!UICONTROL DAM]** .
1. Tik in het dialoogvenster **[!UICONTROL Step Properties]** op het tabblad **[!UICONTROL Process]** of klik op dit tabblad.
1. In het **[!UICONTROL vakje van Argumenten]** , voeg toe `rendition:cq5dam.thumbnail.140.100.png,rendition:cq5dam.thumbnail.319.319.png`. Tik/klik op **[!UICONTROL OK]**.

   ![step_properties](assets/step_properties.png)

1. To regenerate the pyramid TIFF renditions for Dynamic Media images with the new attributes, add the **[!UICONTROL Dynamic Media Process Image Assets]** step to the DAM Metadata Writeback workflow.
PTIFF-uitvoeringen worden alleen lokaal gemaakt en opgeslagen in de hybride modus Dynamische media. Sla de workflow op.

De wijzigingen in de metagegevens worden doorgegeven aan de uitvoeringen `thumbnail.140.100.png` en `thumbnail.319.319.png` het element, en niet aan de andere.

>[!NOTE]
>
>Voor XMP-terugschrijvingsproblemen in 64-bits Linux, zie [How to enable XMP write-back on 64-bit RedHat Linux](https://helpx.adobe.com/experience-manager/kb/enable-xmp-write-back-64-bit-redhat.html).
>
>Zie Voorwaarden voor het schrijven van [XMP-metagegevens voor meer informatie over ondersteunde platforms](/help/sites-deploying/technical-requirements.md#requirements-for-aem-assets-xmp-metadata-write-back).

## XMP-metagegevens filteren {#filtering-xmp-metadata}

AEM-elementen ondersteunen zowel blacklist- als whitelist-filtering van eigenschappen/knooppunten voor XMP-metagegevens die worden gelezen van binaire elementen die in JCR worden opgeslagen wanneer elementen worden opgenomen.

Met filtering van zwarte lijsten kunt u alle XMP-metagegevenseigenschappen importeren, behalve de eigenschappen die zijn opgegeven voor uitsluiting. Voor elementtypen zoals INDD-bestanden met grote hoeveelheden XMP-metagegevens (bijvoorbeeld 1000 knooppunten met 10.000 eigenschappen) zijn de namen van te filteren knooppunten echter niet altijd van tevoren bekend. Als door filtering op zwarte lijsten een groot aantal elementen met een groot aantal XMP-metagegevens kan worden geïmporteerd, kunnen bij de AEM-instantie/cluster stabiliteitsproblemen optreden, bijvoorbeeld verstopte wachtrijen voor waarneming.

Door het filteren met whitelist van XMP-metagegevens wordt dit probleem opgelost door de XMP-eigenschappen te definiëren die moeten worden geïmporteerd. Op deze manier worden andere/onbekende XMP-eigenschappen genegeerd. U kunt enkele van deze eigenschappen toevoegen aan het filter voor zwarte lijsten voor achterwaartse compatibiliteit.

>[!NOTE]
>
>Filteren werkt alleen voor de eigenschappen die zijn afgeleid van XMP-bronnen in binaire elementen. Voor de eigenschappen die van niet-XMP bronnen, zoals formaten EXIF en IPTC worden afgeleid, werkt het filtreren niet. De aanmaakdatum van elementen wordt bijvoorbeeld opgeslagen in een eigenschap met de naam EXIF TIFF. `CreateDate` Deze waarde wordt opgeslagen in het metagegevensveld genaamd `exif:DateTimeOriginal`. Aangezien de bron een niet-XMP-bron is, werkt het filteren niet op deze eigenschap.

1. Open Configuratiebeheer vanuit `https://[aem_server]:[port]/system/console/configMgr`.
1. Open de **[!UICONTROL configuratie van Adobe CQ DAM XmpFilter]** .
1. Als u witfilters wilt toepassen, selecteert u Whitelist **[!UICONTROL toepassen op XMP-eigenschappen]** en geeft u de eigenschappen op die moeten worden geïmporteerd in het vak **[!UICONTROL Whitelisted XML Names for XMP filtering]** .

   ![chlimage_1-347](assets/chlimage_1-347.png)

1. Als u de op de zwarte lijst geplaatste XMP-eigenschappen wilt uitfilteren nadat u een whitelist-filter hebt toegepast, geeft u deze op in het vak XML-namen op de zwarte lijst voor het filteren **** van XMP. Sla de wijzigingen op.

   >[!NOTE]
   >
   >De optie Blacklist **[!UICONTROL toepassen op XMP-eigenschappen]** is standaard geselecteerd. Met andere woorden, filtering op zwarte lijsten is standaard ingeschakeld. Schakel Zwarte lijst **[!UICONTROL toepassen op XMP-eigenschappen]** uit om filteren op zwarte lijsten uit te schakelen.
