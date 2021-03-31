---
title: Bulkmetagegevens importeren en exporteren
description: In dit artikel wordt beschreven hoe u metagegevens bulksgewijs kunt importeren en exporteren.
contentOwner: AG
feature: Metagegevens
role: Business Practice,Administrator
translation-type: tm+mt
source-git-commit: 29e3cd92d6c7a4917d7ee2aa8d9963aa16581633
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 8%

---


# Onduidelijke metagegevens importeren en exporteren {#bulk-metadata-import-and-export}

Met AEM Assets kunt u metagegevens van elementen in bulk importeren met behulp van een CSV-bestand. U kunt bulkupdates uitvoeren voor de onlangs geüploade elementen of de bestaande elementen door een CSV-bestand te importeren. U kunt ook metagegevens van elementen bulksgewijs invoeren vanuit een systeem van derden in de CSV-indeling.

## Metagegevens {#import-metadata} importeren

De import van metagegevens is asynchroon en belemmert de systeemprestaties niet. Gelijktijdige update van de metagegevens voor meerdere elementen kan bronintensief zijn vanwege XMP schrijfactiviteit als de werkstroommarkering wordt gecontroleerd. Plan zo&#39;n import tijdens het gebruik van een slanke server om te voorkomen dat de prestaties voor andere gebruikers worden beïnvloed.

>[!NOTE]
>
>Registreer de naamruimten eerst om metagegevens in aangepaste naamruimten te importeren.

Voer de volgende stappen uit om metagegevens in bulk te importeren:

1. Navigeer naar de gebruikersinterface Middelen en tik/klik op **[!UICONTROL Create]** op de werkbalk.
1. Selecteer **[!UICONTROL Metadata]** in het menu.
1. Tik op de pagina **[!UICONTROL Metadata Import]** of klik op **[!UICONTROL Select File]**.  Selecteer het CSV-bestand met de metadata.
1. Controleer of het CSV-bestand de volgende parameters bevat:

   | Parameters voor het importeren van metagegevens | Beschrijving |
   |:---|:---|
   | [!UICONTROL Batch Size] | Aantal elementen in een batch waarvoor metagegevens moeten worden geïmporteerd. De standaardwaarde is 50. Maximumwaarde is 100. |
   | [!UICONTROL Field Separator] | De standaardwaarde is `,` - een komma. U kunt elk ander teken opgeven. |
   | [!UICONTROL Multi Value Delimiter] | Scheidingsteken voor metagegevenswaarden. De standaardwaarde is `|` - een pipe. |
   | [!UICONTROL Launch Workflows] | Standaard false. Wanneer ingesteld op true en de standaardinstellingen voor Launcher zijn van kracht voor `DAM Metadata WriteBack Workflow` (die metagegevens naar de binaire XMP schrijft). Het inschakelen van opstartworkflows heeft gevolgen voor de prestaties van het systeem. |
   | [!UICONTROL Asset Path Column Name] | Hiermee definieert u de kolomnaam voor het CSV-bestand met elementen. |

1. Tik/klik op **[!UICONTROL Import]** op de werkbalk. Nadat de metagegevens zijn geïmporteerd, wordt een melding verzonden naar het Postvak Melding. Navigeer naar de eigenschappenpagina voor elementen en controleer of de metagegevenswaarden correct zijn geïmporteerd voor elementen.

Als u datum en tijdstempel wilt toevoegen tijdens het importeren van metagegevens, gebruikt u de `YYYY-MM-DDThh:mm:ss.fff-00:00`-indeling voor datum en tijd. Datum en tijd worden gescheiden door `T`, `hh` is uren in 24-uurformaat, `fff` is nanoseconden, en `-00:00` is timezone offset. `2020-03-26T11:26:00.000-07:00` is bijvoorbeeld 26 maart 2020 om 11:26:00.000 AM PST tijd.

>[!CAUTION]
>
>Als de datumnotatie niet overeenkomt met `YYYY-MM-DDThh:mm:ss.fff-00:00`, worden de datumwaarden niet ingesteld. De datumnotaties van het geëxporteerde CSV-bestand met metagegevens hebben de notatie `YYYY-MM-DDThh:mm:ss-00:00`. Als u het wilt invoeren, zet het in het aanvaardbare formaat door de nanosecondenwaarde toe te voegen die door `fff` wordt vermeld.

## Metagegevens exporteren {#export-metadata}

Hier volgen enkele voorbeelden van het gebruik van metagegevens voor bulksgewijs exporteren:

* Importeer de metagegevens in een systeem van derden wanneer u elementen migreert.
* Metagegevens over elementen delen met een groter projectteam.
* Test of controleer de metagegevens op conformiteit.
* De metagegevens extern maken voor afzonderlijke lokalisatie.

U kunt metagegevens voor meerdere elementen in CSV-indeling exporteren. De metagegevens worden asynchroon geëxporteerd en hebben geen invloed op de prestaties van het systeem. Als u metagegevens wilt exporteren, doorloopt AEM de eigenschappen van het elementknooppunt `jcr:content/metadata` en de onderliggende knooppunten en exporteert u de eigenschappen van de metagegevens in een CSV-bestand.

Voer de volgende stappen uit als u metagegevens van meerdere elementen bulksgewijs wilt exporteren:

1. Selecteer de elementenmap die elementen bevat waarvoor u metagegevens wilt exporteren. Selecteer **[!UICONTROL Export metadata]** in de werkbalk.

1. Geef in het dialoogvenster [!UICONTROL Metadata Export] een naam op voor het CSV-bestand. Selecteer **[!UICONTROL Include assets in sub-folders]** als u metagegevens voor elementen in submappen wilt exporteren.

   ![export_metadata_page](assets/export_metadata_page.png)

1. Selecteer de gewenste opties. Geef een bestandsnaam en zo nodig een datum op.
1. Geef in **[!UICONTROL Properties to be exported]** op of u alle of specifieke eigenschappen wilt exporteren. Als u **[!UICONTROL Selective]** eigenschappen kiest die u wilt exporteren, voegt u de gewenste eigenschappen toe.

1. Tik/klik op **[!UICONTROL Export]** op de werkbalk. Een bericht bevestigt dat de metagegevens worden geëxporteerd. Sluit het bericht.

1. Open het bericht in het Postvak IN voor de exporttaak. Selecteer de taak en klik op **[!UICONTROL Open]** op de werkbalk. Tik of klik op **[!UICONTROL CSV Download]** op de werkbalk om het CSV-bestand met de metadata te downloaden. Klik op **[!UICONTROL Close]**.

   ![csv_download](assets/csv_download.png)
