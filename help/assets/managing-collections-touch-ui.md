---
title: Elementverzamelingen beheren
description: Leer taken om verzamelingen met middelen te beheren, zoals verzamelingen maken, weergeven, verwijderen, bewerken en downloaden.
contentOwner: AG
mini-toc-levels: 1
feature: Verzamelingen
role: Business Practitioner
exl-id: cadfc569-5725-4012-9f73-864243ba7743
translation-type: tm+mt
source-git-commit: bd94d3949f0117aa3e1c9f0e84f7293a5d6b03b4
workflow-type: tm+mt
source-wordcount: '2178'
ht-degree: 13%

---

# Verzamelingen beheren {#managing-collections}

Een verzameling is een set elementen binnen Adobe Experience Manager Assets. Gebruik verzamelingen om elementen tussen gebruikers te delen. De set kan een statische verzameling of een dynamische verzameling zijn die is gebaseerd op zoekresultaten.

In tegenstelling tot mappen kan een verzameling elementen van verschillende locaties bevatten. U kunt verzamelingen delen met verschillende gebruikers waaraan verschillende niveaus van bevoegdheden zijn toegewezen, zoals weergeven, bewerken, enzovoort.

U kunt meerdere verzamelingen delen met een gebruiker. Elke verzameling bevat verwijzingen naar elementen. De referentiële integriteit van activa wordt gehandhaafd over inzamelingen.

De inzamelingen zijn van de volgende types, die op de manier worden gebaseerd zij activa sorteren:

* Een verzameling die een statische referentielijst met elementen, mappen en andere verzamelingen bevat.
* Een slimme verzameling die dynamisch elementen bevat op basis van zoekcriteria.

## Toegang tot de verzamelingsconsole {#navigating-the-collections-console}

Tik of klik op het logo van de Experience Manager om het **[!UICONTROL Collections]** te openen. Ga vanaf de navigatiepagina naar **[!UICONTROL Assets]** > **[!UICONTROL Collections]**.

## Een verzameling maken {#creating-a-collection}

U kunt een inzameling of met [statische verwijzingen](#creating-a-collection-with-static-references) of gebaseerd op een [onderzoek op criteria-gebaseerde filter](#creating-a-smart-collection) tot stand brengen. U kunt ook een verzameling maken van een lichtbak.

### Een verzameling maken met statische verwijzingen {#creating-a-collection-with-static-references}

U kunt een verzameling maken met statische verwijzingen, bijvoorbeeld een verzameling met verwijzingen naar elementen, mappen, verzamelingen, centrifuges en afbeeldingssets.

1. Navigeer naar de **[!UICONTROL Collections]** console.
1. Tik/klik op **[!UICONTROL Create]** op de werkbalk.
1. Voer op de pagina **[!UICONTROL Create Collection]** een titel en een optionele beschrijving in voor de verzameling.
1. Voeg leden toe aan de verzameling en wijs de juiste machtigingen toe. U kunt ook **[!UICONTROL Public Collection]** selecteren om alle gebruikers toegang te geven tot de verzameling.

   >[!NOTE]
   >
   >Om de leden toe te laten om inzamelingen met andere gebruikers te delen, verstrek `dam-users` groep lees toestemmingen bij de weg `home/users`. Geef gebruikers toestemming op `/content/dam/collections` locatie om de gebruikers toe te staan de verzamelingen in pop-uplijsten weer te geven. U kunt de gebruiker ook onderdeel maken van de groep `dam-users`.

1. (Optioneel) Voeg een miniatuurafbeelding toe voor de verzameling.
1. Tik of klik op **[!UICONTROL Create]** en tik of klik vervolgens op **[!UICONTROL OK]** om het dialoogvenster te sluiten. Een verzameling met de opgegeven titel en eigenschappen wordt geopend in de console voor verzamelingen.

   >[!NOTE]
   >
   >Met Experience Manager-elementen kunt u revisietaken voor een verzameling maken, net als bij het maken van revisietaken voor een map met elementen.

   Navigeer naar de gebruikersinterface Elementen om elementen aan de verzameling toe te voegen. Zie [Elementen toevoegen aan een verzameling](/help/assets/managing-collections-touch-ui.md#adding-assets-to-a-collection) voor meer informatie.

### Verzamelingen maken met dropzone {#create-collections-using-dropzone}

U kunt elementen van de interface Elementen naar een verzameling slepen. U kunt ook een kopie van een verzameling maken en de elementen daar slepen.

1. Selecteer in de interface Elementen de elementen die u aan een verzameling wilt toevoegen.
1. Sleep de elementen naar de zone **[!UICONTROL Drop in Collection]**.

   ![drop_in_collection](assets/drop_in_collection.png)

   Laat de muisknop los wanneer de Dropzone actief wordt en het label wordt gewijzigd in **[!UICONTROL Drop to Add]**.

   ![drop_to_add](assets/drop_to_add.png)

   U kunt ook op het pictogram **[!UICONTROL To Collection]** op de werkbalk tikken of erop klikken.

   ![chlimage_1-109](assets/chlimage_1-109.png)

1. Tik of klik op de pagina **[!UICONTROL Add To Collection]** op het pictogram **[!UICONTROL Create Collection]** op de werkbalk.

   Als u de assets aan een bestaande verzameling wilt toevoegen, selecteert u deze op de pagina en tikt of klikt u op **[!UICONTROL Add]**. Standaard wordt de laatst bijgewerkte verzameling geselecteerd.

1. Geef in het dialoogvenster **[!UICONTROL Create New Collection]** een naam op voor de verzameling. Selecteer **[!UICONTROL Public Collection]** als u de verzameling toegankelijk wilt maken voor alle gebruikers.
1. Tik/klik **[!UICONTROL Continue]** om de verzameling te maken.

### Een slimme verzameling maken {#creating-a-smart-collection}

Een slimme verzameling gebruikt zoekcriteria om elementen dynamisch te vullen. U kunt een slimme verzameling alleen maken met behulp van bestanden en niet met behulp van mappen of bestanden en mappen.

Voer de volgende stappen uit om een slimme verzameling te maken:

1. Navigeer naar de gebruikersinterface Middelen en tik op het zoekpictogram of klik erop.

1. Typ het trefwoord in het vak Zoeken en druk op Enter. Open het deelvenster Filters en pas een zoekfilter toe.

1. Selecteer **[!UICONTROL Files]** in de lijst **[!UICONTROL Files & Folders]**.

   ![files_option](assets/files_option.png)

1. Tik of klik op **[!UICONTROL Save Smart Collection]**.
1. Geef een naam op voor de verzameling. Selecteer **[!UICONTROL Public]** om de groep van Gebruikers DAM met de rol van de Kijker aan de slimme inzameling toe te voegen.

   ![save_collection](assets/save_collection.png)

   >[!NOTE]
   >
   >Als u **[!UICONTROL Public]** selecteert, wordt de slimme inzameling beschikbaar aan iedereen met de eigenaarrol nadat u het creeert. Als u de optie **[!UICONTROL Public]** uitschakelt, wordt de DAM-gebruikersgroep niet meer gekoppeld aan de slimme verzameling.

1. Tik of klik op **[!UICONTROL Save]** om de slimme verzameling te maken en sluit vervolgens het berichtvenster om het proces te voltooien.

   De nieuwe slimme verzameling wordt ook toegevoegd aan de lijst **[!UICONTROL Saved Searches]**.

   ![collection_list](assets/collection_listing.png)

   Het label van de knop **[!UICONTROL Create Smart Selection]** verandert in **[!UICONTROL Edit Smart Selection]**. Als u de instellingen van de slimme verzameling wilt bewerken, selecteert u **[!UICONTROL Files]** in de lijst **[!UICONTROL Files & Folders]**. Tik of klik vervolgens op de knop **[!UICONTROL Edit Smart Selection]**.

   ![chlimage_1-112](assets/chlimage_1-112.png)

## Elementen toevoegen aan een verzameling {#adding-assets-to-a-collection}

U kunt elementen toevoegen aan een verzameling die een lijst met bestanden of mappen waarnaar wordt verwezen, bevat. Slimme verzamelingen gebruiken een zoekquery om elementen te vullen. Daarom zijn statische verwijzingen naar elementen en mappen niet op hen van toepassing.

1. Selecteer het element in de gebruikersinterface Elementen en tik op het pictogram **[!UICONTROL To Collection]** op de werkbalk.

   ![chlimage_1-113](assets/chlimage_1-113.png)

   U kunt het element ook naar het **[!UICONTROL Drop in Collection]**-gebied op de interface slepen. Voeg de elementen toe wanneer het label van het gebied verandert in **[!UICONTROL Drop to Add]**.

1. Selecteer op de pagina **[!UICONTROL Add To Collection]** de verzameling waaraan u het element wilt toevoegen.

1. Tik/klik op **[!UICONTROL Add]** en sluit vervolgens het bevestigingsbericht. Het element wordt toegevoegd aan de collectie.

## Een slimme verzameling bewerken {#editing-a-smart-collection}

Slimme verzamelingen worden gemaakt door een zoekopdracht op te slaan, zodat u de inhoud kunt wijzigen door de zoekparameters van de [opgeslagen zoekopdracht](#editing-saved-searches) te wijzigen.

1. Tik in de gebruikersinterface Middelen op het zoekpictogram op de werkbalk of klik erop.

   ![chlimage_1-114](assets/chlimage_1-114.png)

1. Met de curseur in het vakje van het Onderzoek, duw op de sleutel van de Terugkeer.

1. Tik/klik op het pictogram GlobalNav om het deelvenster Filters weer te geven.

1. Selecteer in de lijst met **[!UICONTROL Saved Searches]** de slimme verzameling die u wilt wijzigen. In het deelvenster Zoeken worden de filters weergegeven die zijn geconfigureerd voor de opgeslagen zoekopdracht.

   ![select_smart_collection](assets/select_smart_collection.png)

1. Selecteer **[!UICONTROL Files]** in de lijst **[!UICONTROL Files & Folders]**.

1. Wijzig desgewenst een of meer filters. Tik of klik op **[!UICONTROL Edit Smart Collection]**.

   U kunt ook de naam van de slimme verzameling bewerken.

   ![edit_smart_collectiondialog](assets/edit_smart_collectiondialog.png)

1. Tik of klik op **[!UICONTROL Save]**. Het dialoogvenster **[!UICONTROL Edit Smart Collection]** wordt weergegeven.

1. Tik/klik **[!UICONTROL Overwrite]** om de originele slimme verzameling te vervangen door de bewerkte verzameling. U kunt ook **[!UICONTROL Save As]** selecteren om de bewerkte verzameling afzonderlijk op te slaan.

1. Tik in het bevestigingsdialoogvenster op **[!UICONTROL Save]** om het proces te voltooien.

## Metagegevens van verzamelingen weergeven en bewerken {#viewing-and-editing-collection-metadata}

De meta-gegevens van de inzameling omvat gegevens over de inzameling, met inbegrip van om het even welke markeringen die worden toegevoegd.

1. Selecteer een verzameling in de verzamelingsconsole en tik op het pictogram **[!UICONTROL Properties]** op de werkbalk.
1. Op de **[!UICONTROL Collection Metadata]** pagina, bekijk de inzamelingsmeta-gegevens van **[!UICONTROL Basic]** en **[!UICONTROL Advanced]** lusjes.
1. Wijzig desgewenst de metagegevens en tik op **[!UICONTROL Save & Close]** op de werkbalk om de wijzigingen op te slaan.

### Metagegevens van meerdere verzamelingen bulksgewijs {#editing-collection-metadata-in-bulk} bewerken

U kunt de metagegevens van meerdere verzamelingen tegelijk bewerken. Deze functionaliteit helpt u snel gemeenschappelijke meta-gegevens in veelvoudige inzamelingen te herhalen.

1. Selecteer twee of meer verzamelingen waarvoor u metagegevens wilt bewerken in de console Verzamelingen.
1. Tik/klik op **[!UICONTROL Properties]** op de werkbalk.
1. Bewerk desgewenst de metadata op de pagina **[!UICONTROL Collection Metadata]** onder de tabbladen **[!UICONTROL Basic]** en **[!UICONTROL Advanced]**.
1. Als u de eigenschappen van metagegevens voor een specifieke verzameling wilt weergeven, schakelt u de overige verzamelingen in de lijst met verzamelingen uit. De gebieden van de meta-gegevensredacteur zijn bevolkt met de meta-gegevens voor de bepaalde inzameling.

   >[!NOTE]
   >
   >* Op de pagina met eigenschappen van verzamelingen kunt u verzamelingen verwijderen uit de lijst met verzamelingen door ze te deselecteren. Alle verzamelingen zijn standaard geselecteerd in de lijst met verzamelingen. De metagegevens voor verzamelingen die u verwijdert, worden niet bijgewerkt.
   >* Selecteer boven aan de lijst het selectievakje bij **[!UICONTROL Title]** om te schakelen tussen het selecteren van de verzamelingen en het wissen van de lijst.


1. Tik/klik op **[!UICONTROL Save & Close]** op de werkbalk en sluit vervolgens het bevestigingsvenster om het proces te voltooien.
1. Selecteer **[!UICONTROL Append mode]** om de nieuwe metadata toe te voegen aan de bestaande metadata. Als u deze optie niet selecteert, worden de bestaande metadata in de velden vervangen door de nieuwe metadata. Tik of klik op **[!UICONTROL Submit]**.

   >[!NOTE]
   >
   >De metagegevens die u voor de geselecteerde verzamelingen toevoegt, overschrijven de vorige metagegevens voor deze verzamelingen. Gebruik [!UICONTROL Append mode] om nieuwe waarden aan de bestaande meta-gegevens op de gebieden toe te voegen die veelvoudige waarden kunnen bevatten. Velden met één waarde worden altijd overschreven. Alle tags die u in het veld [!UICONTROL Tags] toevoegt, worden toegevoegd aan de bestaande lijst met tags in de metagegevens.

Als u de pagina met metagegevens [!UICONTROL Properties] wilt aanpassen, inclusief het toevoegen, wijzigen of verwijderen van eigenschappen van metagegevens, gebruikt u de Schema-editor.

>[!TIP]
>
>De bulkbewerkingsmethode werkt voor elementen die beschikbaar zijn in een verzameling. Voor de elementen die beschikbaar zijn in verschillende mappen of die voldoen aan een algemeen criterium, is het mogelijk om de metagegevens bulksgewijs bij te werken nadat u deze elementen hebt doorzocht.

## Verzamelingen zoeken {#searching-collections}

U kunt inzamelingen van de console van Inzamelingen zoeken. Wanneer u met trefwoorden in het vak Zoeken zoekt, zoekt AEM Assets naar namen van verzamelingen, metagegevens en de tags die aan de verzamelingen zijn toegevoegd.

Als u zoekt naar verzamelingen op het hoogste niveau, worden alleen afzonderlijke verzamelingen geretourneerd in zoekresultaten. Elementen of mappen in de verzamelingen zijn uitgesloten. In alle andere gevallen (bijvoorbeeld in een afzonderlijke verzameling of in een mappenhiërarchie) worden alle relevante elementen, mappen en verzamelingen geretourneerd.

## Zoeken in verzamelingen {#searching-within-collections}

Tik of klik op een verzameling in de verzamelingsconsole om deze te openen.

Binnen een verzameling AEM het zoeken naar middelen beperkt tot elementen (en de bijbehorende tags en metagegevens) in de verzameling die u bekijkt. Wanneer u in een map zoekt, worden alle overeenkomende elementen en onderliggende mappen in de huidige map geretourneerd. Wanneer u in een verzameling zoekt, worden alleen overeenkomende elementen, mappen en andere verzamelingen geretourneerd die directe leden van de verzameling zijn.

## Verzamelingsinstellingen bewerken {#editing-collection-settings}

U kunt verzamelingsinstellingen bewerken, zoals titel en beschrijving, of leden toevoegen aan een verzameling.

1. Selecteer een verzameling en tik op het pictogram **[!UICONTROL Settings]** op de werkbalk. U kunt ook de snelle actie **[!UICONTROL Settings]** van de verzamelingsminiatuur gebruiken.
1. Wijzig de verzamelingsinstellingen op de pagina **[!UICONTROL Collection Settings]**. Wijzig bijvoorbeeld de titel van de verzameling, beschrijvingen, leden en machtigingen zoals beschreven in [Verzamelingen toevoegen](#creating-a-collection).

1. Tik op **[!UICONTROL Save]** om de wijzigingen op te slaan.

## Een verzameling {#deleting-a-collection} verwijderen

1. Selecteer een of meer verzamelingen in de console Verzamelingen en tik op het pictogram Verwijderen op de werkbalk.

1. Tik/klik in het dialoogvenster op **[!UICONTROL Delete]** om de verwijderactie te bevestigen.

   >[!NOTE]
   >
   >U kunt slimme verzamelingen ook verwijderen door opgeslagen zoekopdrachten ](#deleting-saved-searches) te verwijderen.[

## Een verzameling {#downloading-a-collection} downloaden

Wanneer u een verzameling downloadt, wordt de volledige hiërarchie van elementen in de verzameling gedownload, inclusief mappen en onderliggende verzamelingen.

1. Selecteer een of meer verzamelingen die u wilt downloaden in de console Verzamelingen.
1. Tik op of klik op het downloadpictogram op de werkbalk.
1. Tik/klik in het dialoogvenster **[!UICONTROL Download]** op **[!UICONTROL Download]**. Selecteer **[!UICONTROL Renditions]** als u de uitvoeringen van de elementen in de verzameling wilt downloaden. Selecteer de optie **[!UICONTROL Email]** om een e-mailbericht naar de eigenaar van de verzameling te verzenden.

   Wanneer u een verzameling selecteert die u wilt downloaden, wordt de volledige maphiërarchie onder de verzameling gedownload. Selecteer **[!UICONTROL Create separate folder for each asset]** als u elke verzameling die u downloadt, wilt opnemen (inclusief elementen in onderliggende verzamelingen die onder de bovenliggende verzameling zijn genest) in een afzonderlijke map.

## Geneste verzamelingen maken {#creating-nested-collections}

U kunt een verzameling toevoegen aan een andere verzameling en zo een geneste verzameling maken.

1. Selecteer in de verzamelingsconsole de gewenste verzameling of groep verzamelingen en tik of klik op het pictogram **[!UICONTROL To Collection]** op de werkbalk.

   ![chlimage_1-117](assets/chlimage_1-117.png)

1. Selecteer op de pagina **[!UICONTROL Add To Collection]** de verzameling waarin u de verzameling wilt toevoegen.

   >[!NOTE]
   >
   >De laatst bijgewerkte verzameling wordt standaard geselecteerd op de pagina **[!UICONTROL Add To Collection]**.

1. Tik of klik op **[!UICONTROL Add]**. Een bericht bevestigt dat de inzameling aan de doelinzameling in **[!UICONTROL Select Destination]** pagina wordt toegevoegd. Sluit het bericht om het proces te voltooien.

>[!NOTE]
>
>Slimme verzamelingen kunnen niet worden genest. Met andere woorden, slimme verzamelingen kunnen geen andere verzameling bevatten.

## Opgeslagen zoekopdrachten {#saved-searches}

In de gebruikersinterface Assets kunt u op basis van bepaalde regels, zoekcriteria of aangepaste zoekfacetten zoeken of filteren. Als u deze opslaat als **[!UICONTROL Saved Searches]**, kunt u ze later openen vanuit de lijst **[!UICONTROL Saved Searches]** in het deelvenster Filteren. Als u een opgeslagen zoekopdracht maakt, wordt ook een slimme verzameling gemaakt.

![saved_search_list](assets/saved_searches_list.png)

### Opgeslagen zoekopdrachten maken {#creating-saved-searches}

Opgeslagen zoekopdrachten worden gemaakt wanneer u een slimme verzameling maakt. Slimme verzamelingen worden automatisch toegevoegd aan de lijst met **[!UICONTROL Saved Searches]**. De opgeslagen vraag van Zoekopdrachten voor de inzameling wordt bewaard in `dam:query` bezit in crxde bij de relatieve plaats `/content/dam/collections/`. Er gelden geen limieten voor de zoekopdrachten die u kunt opslaan en voor de opgeslagen zoekopdrachten die in de lijst worden weergegeven.

>[!NOTE]
>
>U kunt slimme verzamelingen op dezelfde manier delen als statische verzamelingen.

### Opgeslagen zoekopdrachten bewerken {#editing-saved-searches}

Opgeslagen zoekopdrachten bewerken is hetzelfde als slimme verzamelingen bewerken. Zie [Een slimme verzameling bewerken](/help/assets/managing-collections-touch-ui.md#editing-a-smart-collection) voor meer informatie.

### Opgeslagen zoekopdrachten verwijderen {#deleting-saved-searches}

1. Tik in de gebruikersinterface Middelen op het zoekpictogram op de werkbalk of klik erop.

   ![chlimage_1-118](assets/chlimage_1-118.png)

1. Met de curseur op het gebied van Onderzoek, duw op de Enter sleutel.

1. Klik of tik op het GlobalNav-pictogram om het deelvenster Filters weer te geven.

1. Tik in de lijst **[!UICONTROL Saved Searches]** op het verwijderpictogram naast de slimme verzameling die u wilt verwijderen.

   ![select_smart_collection-1](assets/select_smart_collection-1.png)

1. Tik/klik in het dialoogvenster op **[!UICONTROL Delete]** om de opgeslagen zoekopdracht te verwijderen.

## Een workflow uitvoeren op een verzameling {#running-a-workflow-on-a-collection}

U kunt een workflow voor de elementen in een verzameling uitvoeren. Als de verzameling geneste verzamelingen bevat, wordt de workflow ook uitgevoerd op de elementen in de geneste verzamelingen. Als de verzameling en de geneste verzameling echter dubbele elementen bevatten, wordt de workflow slechts eenmaal uitgevoerd voor dergelijke elementen.

1. Selecteer in de console Verzamelingen een verzameling waarop u een workflow wilt uitvoeren.
1. Tik/klik op het pictogram GlobalNav en kies **[!UICONTROL Timeline]** in de lijst.
1. Klik of tik vanaf de tijdlijn op het pictogram Caret onderaan en tik op **[!UICONTROL Start Workflow]**.

   ![chlimage_1-119](assets/chlimage_1-119.png)

1. Selecteer in de sectie **[!UICONTROL Start Workflow]** een workflowmodel in de lijst. Selecteer bijvoorbeeld het model **[!UICONTROL DAM Update Asset]**.
1. Voer een titel in voor de workflow en tik/klik op **[!UICONTROL Start]**.
1. Tik/klik op **[!UICONTROL Proceed]** in het dialoogvenster. De workflow wordt uitgevoerd op alle elementen in de verzameling.

>[!MORELIKETHIS]
>
>* [E-mailberichten voor Experience Manager Assets configureren](/help/sites-administering/notification.md#assetsconfig)
>* [Een revisietaak maken voor verzamelingen](bulk-approval.md)

