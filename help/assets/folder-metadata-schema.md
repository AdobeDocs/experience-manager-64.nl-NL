---
title: Metagegevensschema van map
description: In dit artikel wordt beschreven hoe u een metagegevensschema kunt maken voor mappen met elementen in [!DNL Experience Manager] Activa
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
uuid: 286a4f26-c0ad-4691-80d8-d17ba1a2dfe0
discoiquuid: 92eacea5-7511-48ce-8a72-ff4552ebb07d
feature: Metadata
role: User,Admin
exl-id: 1bc72dac-41f7-4593-aaea-d48ebd94b43e
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1041'
ht-degree: 5%

---

# Metagegevensschema van map {#folder-metadata-schema}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

In dit artikel wordt beschreven hoe u een metagegevensschema kunt maken voor mappen met elementen in [!DNL Experience Manager] Elementen.

Met Adobe Experience Manager Assets kunt u metagegevensschema&#39;s maken voor middelenmappen, waarmee de lay-out en metagegevens worden gedefinieerd die op pagina&#39;s met mapeigenschappen worden weergegeven.

>[!NOTE]
>
>Deze functionaliteit vereist [!DNL Experience Manager] 6.4 met minstens opgesteld Service Pack 2. Voor [!DNL Experience Manager] 6.4 de details van het de dienstpak, zie deze [releaseopmerkingen](/help/release-notes/sp-release-notes.md).

## Een schema voor metagegevens van een map toevoegen {#add-a-folder-metadata-schema-form}

Met de Forms-editor voor het schema Metagegevens van map kunt u metagegevensschema&#39;s voor mappen maken en bewerken.

1. Tik/klik op de knop [!DNL Experience Manager] logo en ga naar **[!UICONTROL Tools]** > **[!UICONTROL Assets]**> **[!UICONTROL Folder Metadata Schemas]**.
1. Tik/klik op de pagina Forms van het schema met metagegevens van de map **[!UICONTROL Create]**.
1. Geef een naam voor het formulier op en tik/klik op **[!UICONTROL Create]**. Het nieuwe schema formulier wordt weergegeven op de pagina Schema Forms.

## Formulieren met metagegevens van mappen bewerken {#edit-folder-metadata-schema-forms}

U kunt een nieuw toegevoegd of bestaand schema voor metagegevens bewerken, dat het volgende bevat:

* Tabs
* Formulieritems in tabbladen.

U kunt deze formulieritems toewijzen/configureren aan een veld binnen een metagegevensknooppunt in de CRX-opslagruimte. U kunt nieuwe tabbladen of formulieritems toevoegen aan het metagegevensschemaformulier.

1. Selecteer op de pagina Schema Forms het formulier dat u hebt gemaakt en tik op de knop **[!UICONTROL Edit]** op de werkbalk.
1. Tik of klik op de pagina in de Editor van het schema voor metagegevens van de map op de knop **[!UICONTROL +]** pictogram om een tabblad aan het formulier toe te voegen. Als u de naam van het tabblad wilt wijzigen, tikt u op de standaardnaam of klikt u erop en geeft u de nieuwe naam op onder **[!UICONTROL Settings]**.

   ![custom_tab](assets/custom_tab.png)

   Tik of klik op de knop **[!UICONTROL +]** pictogram. Tikken/klikken **[!UICONTROL X]** om een tabblad te verwijderen.

1. Voeg op het actieve tabblad een of meer componenten van het tabblad **[!UICONTROL Build Form]** tab.

   ![adding_components](assets/adding_components.png)

   Als u meerdere tabbladen maakt, tikt of klikt u op een bepaald tabblad om componenten toe te voegen.

1. Als u een component wilt configureren, selecteert u deze en wijzigt u de eigenschappen ervan in het dialoogvenster **[!UICONTROL Settings]** tab.

   Verwijder indien nodig een component uit het dialoogvenster **[!UICONTROL Settings]** tab.

   ![configure_properties](assets/configure_properties.png)

1. Tikken/klikken **[!UICONTROL Save]** op de werkbalk om de wijzigingen op te slaan.

### Componenten om formulieren te maken {#components-to-build-forms}

De **[!UICONTROL Build Form]** wordt een lijst weergegeven met formulieritems die u in het metagegevensschema van uw map gebruikt. De **[!UICONTROL Settings]** worden de kenmerken weergegeven van elk item dat u selecteert in het dialoogvenster **[!UICONTROL Build Form]** tab. Hier volgt een lijst met formulieritems die beschikbaar zijn in het dialoogvenster **[!UICONTROL Build Form]** tab:

| Componentnaam | Beschrijving |
|---|---|
| [!UICONTROL Section Header] | Voeg een sectiekopje toe voor een lijst met gangbare componenten. |
| [!UICONTROL Single Line Text] | Voeg een teksteigenschap voor één regel toe. De eigenschap wordt opgeslagen als een tekenreeks. |
| [!UICONTROL Multi Value Text] | Voeg een teksteigenschap voor meerdere waarden toe. Deze wordt opgeslagen als een tekenreeks-array. |
| [!UICONTROL Number] | Voeg een getalcomponent toe. |
| [!UICONTROL Date] | Voeg een datumcomponent toe. |
| [!UICONTROL Dropdown] | Voeg een vervolgkeuzelijst toe. |
| [!UICONTROL Standard Tags] | Voeg een tag toe. |
| [!UICONTROL Hidden Field] | Voeg een verborgen veld toe. Deze wordt als een POST-parameter verzonden wanneer het element wordt opgeslagen. |

### Formulieritems bewerken {#editing-form-items}

Als u de eigenschappen van formulieritems wilt bewerken, tikt u op de component of klikt u op de component en bewerkt u alle eigenschappen of een subset van de volgende eigenschappen in het dialoogvenster **[!UICONTROL Settings]** tab.

**[!UICONTROL Field Label]**: De naam van de eigenschap metadata die wordt weergegeven op de eigenschappenpagina voor de map.

**[!UICONTROL Map to Property]**: This property specifies the relative path of the folder node in the CRX repository where it is saved. Het begint met &quot;**./**&quot;, hetgeen aangeeft dat het pad zich onder het knooppunt van de map bevindt.

Hier volgen de geldige waarden voor deze eigenschap:

* `./jcr:content/metadata/dc:title`: Hiermee wordt de waarde in het metagegevensknooppunt van de map opgeslagen als de eigenschap `dc:title`.

* `./jcr:created`: Geeft de JCR-eigenschap op het knooppunt van de map weer. Als u deze eigenschappen in CRXDE vormt, adviseert Adobe dat u hen als onbruikbaar maakt uitgeeft markeert, omdat zij beschermd zijn. Anders wordt de fout &#39; `Asset(s) failed to modify`&#39; vindt plaats wanneer u de eigenschappen van het element opslaat.

Neem geen spatie op in het eigenschapspad om ervoor te zorgen dat de component correct wordt weergegeven in het schema voor metagegevens.

**[!UICONTROL JSON Path]**: Gebruik deze optie om het pad van het JSON-bestand op te geven waarin u sleutelwaardeparen voor opties opgeeft.

**[!UICONTROL Placeholder]**: Gebruik deze eigenschap om relevante plaatsaanduidingstekst met betrekking tot de eigenschap metadata op te geven.

**[!UICONTROL Choices]**: Gebruik deze eigenschap om keuzen in een lijst op te geven.

**[!UICONTROL Description]**: Gebruik deze eigenschap om een korte beschrijving toe te voegen voor de metagegevenscomponent.

**[!UICONTROL Class]**: Objectklasse waaraan de eigenschap is gekoppeld.

## Formulieren met metagegevens van mappen verwijderen {#delete-folder-metadata-schema-forms}

U kunt de schemaformulieren van de omslagmeta-gegevens van het Schema Forms van de Meta-gegevens van de Omslag schrappen pagina. Als u een formulier wilt verwijderen, selecteert u het en tikt of klikt u op het pictogram Verwijderen op de werkbalk.

![delete_form](assets/delete_form.png)

## Een schema voor metagegevens van mappen toewijzen {#assign-a-folder-metadata-schema}

U kunt een schema van omslagmeta-gegevens aan een omslag of van de pagina van Forms van het Schema van Meta-gegevens van de Omslag toewijzen of wanneer het creëren van een omslag.

Als u een metagegevensschema voor een map configureert, wordt het pad naar het schema opgeslagen in het dialoogvenster `folderMetadataSchema` eigenschap van het mapknooppunt onder .*/jcr:content*.

### Wijs aan een schema van de pagina van het Schema van Meta-gegevens van de Omslag toe {#assign-to-a-schema-from-the-folder-metadata-schema-page}

1. Tik/klik op de knop [!DNL Experience Manager] logo en ga naar **[!UICONTROL Tools]** > **[!UICONTROL Assets]** > **[!UICONTROL Folder Metadata Schemas]**.
1. Selecteer op de pagina Forms van het schema Metagegevens map het schema dat u op een map wilt toepassen.
1. Tik/klik op de werkbalk **[!UICONTROL Apply to Folder(s)]**.

1. Selecteer de map waarop u het schema wilt toepassen en klik/tik op **[!UICONTROL Apply]**. Als er al een metagegevensschema op de map is toegepast, verschijnt er een waarschuwingsbericht dat u het bestaande metagegevensschema wilt overschrijven. Tik of klik op **[!UICONTROL Overwrite]**.
1. Open de eigenschappen van de metagegevens voor de map waarop u het metagegevensschema hebt toegepast.

   ![folder_properties](assets/folder_properties.png)

   Tik of klik op het tabblad **[!UICONTROL Folder Metadata]** om de velden met metadata van de map weer te geven.

   ![folder_metadata_properties](assets/folder_metadata_properties.png)

### Een schema toewijzen bij het maken van een map {#assign-a-schema-when-creating-a-folder}

U kunt een schema van omslagmeta-gegevens toewijzen wanneer het creëren van een omslag. Als het systeem ten minste één schema voor metagegevens van de map bevat, wordt een extra lijst weergegeven in het dialoogvenster **[!UICONTROL Create Folder]** . U kunt het gewenste schema selecteren. Standaard is geen schema geselecteerd.

1. Van de [!DNL Assets] gebruikersinterface, tikken/klikken **[!UICONTROL Create]** op de werkbalk.
1. Geef een titel en naam voor de map op.
1. Selecteer het gewenste schema in de lijst Metagegevensschema van map. Tik vervolgens/klik op **[!UICONTROL Create]**.

   ![select_schema](assets/select_schema.png)

1. Open de eigenschappen van de metagegevens voor de map waarop u het metagegevensschema hebt toegepast.
1. Tik of klik op het tabblad **[!UICONTROL Folder Metadata]** om de velden met metadata van de map weer te geven.

## Het schema voor metagegevens van de map gebruiken {#use-the-folder-metadata-schema}

Open de eigenschappen voor een map die met een mapmetadataschema is geconfigureerd. Er wordt een tabblad **[!UICONTROL Folder Metadata]** weergegeven op de pagina met mapeigenschappen. Selecteer dit tabblad om het formulier van het mapmetadataschema weer te geven.

Geef waarden voor metagegevens op in de verschillende velden en tik/klik op **[!UICONTROL Save]** om de waarden op te slaan. De waarden die u opgeeft, worden opgeslagen in het mapknooppunt in de CRX-opslagruimte.

![folder_metadata_properties-1](assets/folder_metadata_properties-1.png)
