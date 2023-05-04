---
title: Bulkmetagegevens importeren en exporteren
description: In dit artikel wordt beschreven hoe u metagegevens bulksgewijs kunt importeren en exporteren.
contentOwner: AG
feature: Metadata
role: User,Admin
exl-id: 956cdec4-2ba8-43c9-9122-564d764f4681
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 7%

---

# Bulkmetagegevens importeren en exporteren {#bulk-metadata-import-and-export}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

[!DNL Experience Manager] Met middelen kunt u metagegevens van elementen in bulk importeren met een CSV-bestand. U kunt bulkupdates uitvoeren voor de onlangs geüploade elementen of de bestaande elementen door een CSV-bestand te importeren. U kunt ook metagegevens van elementen bulksgewijs invoeren vanuit een systeem van derden in de CSV-indeling.

## Metagegevens importeren {#import-metadata}

De import van metagegevens is asynchroon en belemmert de systeemprestaties niet. Gelijktijdige update van de metagegevens voor meerdere elementen kan bronintensief zijn vanwege XMP schrijfactiviteit als de werkstroommarkering wordt gecontroleerd. Plan zo&#39;n import tijdens het gebruik van een slanke server om te voorkomen dat de prestaties voor andere gebruikers worden beïnvloed.

>[!NOTE]
>
>Registreer de naamruimten eerst om metagegevens in aangepaste naamruimten te importeren.

Voer de volgende stappen uit om metagegevens in bulk te importeren:

1. Navigeer naar de gebruikersinterface Middelen en tik/klik **[!UICONTROL Create]** op de werkbalk.
1. Selecteer **[!UICONTROL Metadata]** in het menu.
1. Op de **[!UICONTROL Metadata Import]** pagina, tik of klik op de knop **[!UICONTROL Select File]**.  Selecteer het CSV-bestand met de metadata.
1. Controleer of het CSV-bestand de volgende parameters bevat:

   | Parameters voor het importeren van metagegevens | Beschrijving |
   |:---|:---|
   | [!UICONTROL Batch Size] | Aantal elementen in een batch waarvoor metagegevens moeten worden geïmporteerd. De standaardwaarde is 50. Maximumwaarde is 100. |
   | [!UICONTROL Field Separator] | Standaardwaarde is `,` - een komma. U kunt elk ander teken opgeven. |
   | [!UICONTROL Multi Value Delimiter] | Scheidingsteken voor metagegevenswaarden. Standaardwaarde is `|` - een pijp. |
   | [!UICONTROL Launch Workflows] | Standaard false. Als deze waarde is ingesteld op true en als de standaardinstellingen van kracht zijn voor de `DAM Metadata WriteBack Workflow` (dat meta-gegevens naar de binaire XMP gegevens schrijft). Het inschakelen van de workflows heeft gevolgen voor de prestaties van het systeem. |
   | [!UICONTROL Asset Path Column Name] | Hiermee definieert u de kolomnaam voor het CSV-bestand met elementen. |

1. Tikken/klikken **[!UICONTROL Import]** op de werkbalk. Nadat de metagegevens zijn geïmporteerd, wordt een melding verzonden naar het Postvak Melding. Navigeer naar de eigenschappenpagina voor elementen en controleer of de metagegevenswaarden correct zijn geïmporteerd voor elementen.

Als u datum en tijdstempel wilt toevoegen tijdens het importeren van metagegevens, gebruikt u `YYYY-MM-DDThh:mm:ss.fff-00:00` notatie voor datum en tijd. Datum en tijd worden gescheiden door `T`, `hh` is uren in 24-uursnotatie, `fff` nanoseconden is, en `-00:00` is timezone offset. Bijvoorbeeld: `2020-03-26T11:26:00.000-07:00` is 26 maart 2020 om 11:26:00.000 AM PST-tijd.

>[!CAUTION]
>
>Als de datumnotatie niet overeenkomt `YYYY-MM-DDThh:mm:ss.fff-00:00`, worden de datumwaarden niet ingesteld. De datumnotaties van het geëxporteerde CSV-bestand met metagegevens hebben de indeling `YYYY-MM-DDThh:mm:ss-00:00`. Als u het wilt invoeren, zet het in het aanvaardbare formaat door de nanosecondenwaarde toe te voegen die door wordt aangegeven `fff`.

## Metagegevens exporteren {#export-metadata}

Hier volgen enkele voorbeelden van het gebruik van metagegevens voor bulksgewijs exporteren:

* Importeer de metagegevens in een systeem van derden wanneer u elementen migreert.
* Metagegevens over elementen delen met een groter projectteam.
* Test of controleer de metagegevens op conformiteit.
* De metagegevens extern maken voor afzonderlijke lokalisatie.

U kunt metagegevens voor meerdere elementen in CSV-indeling exporteren. De metagegevens worden asynchroon geëxporteerd en hebben geen invloed op de prestaties van het systeem. Als u metagegevens wilt exporteren, [!DNL Experience Manager] doorloopt de eigenschappen van het knooppunt asset `jcr:content/metadata` en de onderliggende knooppunten en exporteert de eigenschappen van de metagegevens in een CSV-bestand.

Voer de volgende stappen uit als u metagegevens van meerdere elementen bulksgewijs wilt exporteren:

1. Selecteer de elementenmap die elementen bevat waarvoor u metagegevens wilt exporteren. Selecteer **[!UICONTROL Export metadata]** in de werkbalk.

1. In de [!UICONTROL Metadata Export] een naam voor het CSV-bestand op. Selecteer **[!UICONTROL Include assets in sub-folders]**.

   ![export_metadata_page](assets/export_metadata_page.png)

1. Selecteer de gewenste opties. Geef een bestandsnaam en zo nodig een datum op.
1. In de **[!UICONTROL Properties to be exported]** geeft u op of u alle of specifieke eigenschappen wilt exporteren. Als u **[!UICONTROL Selective]** voegt u de gewenste eigenschappen toe die u wilt exporteren.

1. Tik/klik op de werkbalk **[!UICONTROL Export]**. Een bericht bevestigt dat de metagegevens worden geëxporteerd. Sluit het bericht.

1. Open het bericht in het Postvak IN voor de exporttaak. Selecteer de taak en klik op **[!UICONTROL Open]** op de werkbalk. Tik of klik op **[!UICONTROL CSV Download]** op de werkbalk om het CSV-bestand met de metadata te downloaden. Klik op **[!UICONTROL Close]**.

   ![csv_download](assets/csv_download.png)
