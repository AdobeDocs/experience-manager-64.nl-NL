---
title: Metagegevensschema's
description: 'Het metagegevensschema definieert de indeling van de pagina met eigenschappen en de eigenschappen van metagegevens die voor elementen worden weergegeven. Leer hoe u een aangepast metagegevensschema kunt maken, het schema voor metagegevens kunt bewerken en hoe u het schema voor metagegevens op elementen kunt toepassen.  '
contentOwner: AG
translation-type: tm+mt
source-git-commit: b698a1348df3ec2ab455c236422784d10cbcf7c2
workflow-type: tm+mt
source-wordcount: '2397'
ht-degree: 8%

---


# Metadataschema&#39;s {#metadata-schemas}

In [!DNL Experience Manager Assets], bepaalt een meta-gegevensschema de lay-out van de eigenschappen pagina en de meta-gegevenseigenschappen die voor activa worden getoond die het bepaalde schema gebruiken. Tot de metagegevenseigenschappen behoren titel, beschrijving, MIME-typen, tags, enzovoort. U kunt de redacteur van Forms van het Schema van Meta-gegevens gebruiken om bestaande schema&#39;s te wijzigen of douanemetagegevensschema&#39;s toe te voegen.

Ga als volgt te werk om de pagina met eigenschappen voor een element weer te geven en te bewerken:

1. Klik of tik **[!UICONTROL View Properties]** van snelle acties op de middelentegel in de mening van de Kaart.

   ![chlimage_1-170](assets/chlimage_1-170.png)

   U kunt ook een element selecteren en vervolgens op het **[!UICONTROL Properties]** pictogram op de werkbalk klikken of tikken.

   ![chlimage_1-171](assets/chlimage_1-171.png)

1. U kunt de verschillende bewerkbare eigenschappen van metagegevens bewerken onder de beschikbare tabbladen. U kunt het element echter niet wijzigen [!UICONTROL Type] op het [!UICONTROL Basic] tabblad Eigenschappen.

   ![chlimage_1-172](assets/chlimage_1-172.png)

   Als u het MIME-type voor een element wilt wijzigen, gebruikt u een aangepast schema voor metagegevens of wijzigt u een bestaand formulier. Zie Metagegevensschema [bewerken Forms](metadata-schemas.md#editing-metadata-schema-forms) voor meer informatie. Als u het metagegevensschema voor een bepaald MIME-type wijzigt, worden de pagina-indeling van de eigenschappen voor elementen met het huidige MIME-type en alle elementsubtypen gewijzigd. Als u bijvoorbeeld een `jpeg` schema wijzigt in `default/image` plaats daarvan, wordt alleen de metagegevensindeling (eigenschappen van elementen) gewijzigd voor elementen met het MIME-type `IMAGE/JPEG`. Als u echter het standaardschema bewerkt, worden de wijzigingen doorgevoerd in de indeling van de metagegevens voor alle typen elementen.

## Metagegevensschema Forms {#default-metadata-schema-forms}

Als u een lijst met formulieren/sjablonen wilt weergeven, navigeert u in de [!DNL Experience Manager] interface naar **[!UICONTROL Tools]** > **[!UICONTROL Assets]** > **[!UICONTROL Metadata Schemas]**.

[!DNL Experience Manager] Hier vindt u de volgende sjablonen voor het schema van metagegevens:

| Sjablonen |  | Beschrijving |
|---|---|---|
| [!UICONTROL default] |  | Het basisschema voor metagegevens voor elementen. |
|  | De volgende onderliggende formulieren nemen de eigenschappen van het [!UICONTROL default] formulier over: |  |
|  | <ul><li> [!UICONTROL dm_video]</li></ul> | Schemaformulier voor Dynamic Media-video&#39;s. |
|  | <ul><li> [!UICONTROL image]</li></ul> | Schema-formulier voor elementen met het MIME-type &quot;image&quot;, bijvoorbeeld afbeelding/jpeg, afbeelding/png, enzovoort. <br> Het [!UICONTROL image] formulier heeft de volgende onderliggende formuliersjablonen: <ul><li> [!UICONTROL jpeg]: Schema voor activa met subtype [!UICONTROL jpeg].</li> <li>[!UICONTROL tiff]: Schema voor de activa met subtype [!UICONTROL tiff].</li></ul> |
|  | <ul><li> [!UICONTROL application]</li></ul> | Schema-formulier voor elementen met het MIME-type &quot;application&quot;, bijvoorbeeld application/ pdf, application/ zip enzovoort. <br>[!UICONTROL pdf]: Schemaformulier voor activa met subtype pdf. |
|  | <ul><li>[!UICONTROL video]</li></ul> | Schema-formulier voor elementen met het MIME-type &quot;video&quot;, zoals video/avi, video/mp4, enzovoort. |
| [!UICONTROL collection] |  | Schemaformulier voor verzamelingen. |
| [!UICONTROL contentfragment] |  | Schemaformulier voor inhoudsfragmenten. |
| [!UICONTROL forms] |  | Dit schema-formulier heeft betrekking op [Adobe Experience Manager Forms](/help/forms/home.md). |

>[!NOTE]
>
>Als u de onderliggende formulieren van een schema wilt weergeven, klikt of tikt u op de naam van het schema.

## Een metagegevensschema toevoegen {#adding-a-metadata-schema-form}

1. Als u een aangepaste sjabloon aan de lijst wilt toevoegen, klikt u op **[!UICONTROL Create]** de werkbalk.

   >[!NOTE]
   >
   >Onbewerkte sjablonen geven vóór de sjablonen een vergrendelingspictogram weer. Als u een van de sjablonen aanpast, verdwijnt het vergrendelingspictogram voordat de sjabloon verdwijnt.

1. Voer in het dialoogvenster de titel van het schema in en klik **[!UICONTROL Create]** om het maken van het formulier te voltooien.

   ![chlimage_1-174](assets/chlimage_1-174.png)

## Formulieren met metagegevensschema bewerken {#editing-metadata-schema-forms}

U kunt een nieuw of bestaand schema voor metagegevens bewerken. Het metagegevensschema bevat het volgende:

* Tabs
* Formulieritems in tabbladen.

U kunt deze formulieritems toewijzen/configureren aan een veld binnen een metagegevensknooppunt in de CRX-opslagruimte.

U kunt nieuwe tabbladen of formulieritems toevoegen aan het metagegevensschemaformulier. De tabbladen en formulieritems die van het bovenliggende element zijn afgeleid, bevinden zich in de vergrendelde status. U kunt deze niet wijzigen op het niveau van het kind.

1. In the **[!UICONTROL Schema Forms]** page, select the check box before a form and then click **[!UICONTROL Edit]** on the toolbar.

   ![chlimage_1-175](assets/chlimage_1-175.png)

1. Pas op de pagina **[!UICONTROL Metadata Schema Editor]** de eigenschappenpagina van de asset aan door een of meer componenten uit de lijst met componenttypen op het tabblad **[!UICONTROL Build Form]** naar het tabblad **[!UICONTROL Basic]** te slepen.

   ![chlimage_1-176](assets/chlimage_1-176.png)

1. Als u een component wilt configureren, selecteert u deze en wijzigt u de eigenschappen ervan op het **[!UICONTROL Settings]** tabblad.

### Componenten op het tabblad Formulier samenstellen {#components-within-the-build-form-tab}

Het **[!UICONTROL Build Form]** tabblad bevat formulieritems die u in het schemaformulier gebruikt. Het **[!UICONTROL Settings]** tabblad bevat de kenmerken van elk item dat u op het **[!UICONTROL Build Form]** tabblad selecteert. De volgende tabel bevat een lijst met formulieritems die beschikbaar zijn op het **[!UICONTROL Build Form]** tabblad:

| Componentnaam | Beschrijving |
|---|---|
| [!UICONTROL Section Header] | Voeg een sectiekopje toe voor een lijst met gangbare componenten. |
| [!UICONTROL Single Line Text] | Voeg een eigenschap voor één regel tekst toe. De eigenschap wordt opgeslagen als een tekenreeks. |
| [!UICONTROL Multi Value Text] | Voeg een teksteigenschap voor meerdere waarden toe. Deze wordt opgeslagen als een tekenreeks-array. |
| [!UICONTROL Number] | Voeg een getalcomponent toe. |
| [!UICONTROL Date] | Voeg een datumcomponent toe. |
| [!UICONTROL Dropdown] | Voeg een vervolgkeuzelijst toe. |
| [!UICONTROL Standard Tags] | Voeg een tag toe. |
| [!UICONTROL Smart Tags] | U kunt zoekmogelijkheden uitbreiden door automatisch metagegevenstags toe te voegen. |
| [!UICONTROL Hidden Field] | Voeg een verborgen veld toe. Deze wordt als een POST-parameter verzonden wanneer het element wordt opgeslagen. |
| [!UICONTROL Asset Referenced By] | Voeg deze component toe om een lijst weer te geven met elementen waarnaar door het element wordt verwezen. |
| [!UICONTROL Asset Referencing] | Toevoegen om een lijst weer te geven met elementen die naar het element verwijzen. |
| [!UICONTROL Products References] | Toevoegen om de lijst weer te geven met producten die aan het element zijn gekoppeld. |
| [!UICONTROL Asset Rating] | Toevoegen aan weergaveopties voor het beoordelen van het element. |
| [!UICONTROL Contextual Metadata] | Toevoegen om de weergave van andere tabbladen met metagegevens in de eigenschappenpagina met elementen te besturen. |

### De metagegevenscomponent bewerken {#editing-the-metadata-component}

Als u de eigenschappen van een metagegevenscomponent in het formulier wilt bewerken, klikt u op de component en bewerkt u alle eigenschappen of een subset van de volgende eigenschappen op het **[!UICONTROL Settings]** tabblad.

**Veldlabel**: De naam van de eigenschap metadata die wordt weergegeven op de eigenschappenpagina voor het element.

**Toewijzen aan eigenschap**: This property specifies the relative path/name to the asset node where it is saved in the CRX repository. Het begint met `./` omdat erop wijst dat de weg onder de knoop van het element is.

Hier volgen de geldige waarden voor deze eigenschap:

* `./jcr:content/metadata/dc:title`: Hiermee wordt de waarde in het metadataknooppunt van de asset opgeslagen als de eigenschap `dc:title`.

* `./jcr:created`: Geeft de JCR-eigenschap weer op het knooppunt van het element. Als u deze eigenschappen configureert op weergave-eigenschappen, raden wij aan deze te markeren als Bewerken uitschakelen, omdat deze beveiligd zijn. Anders [!UICONTROL Asset(s) failed to modify] resulteert de fout wanneer u de eigenschappen van het element opslaat.

Om ervoor te zorgen dat de component correct in de vorm van het meta-gegevensschema wordt getoond, zou de bezitspad geen ruimten moeten omvatten.

**Tijdelijke aanduiding**: Gebruik deze eigenschap om relevante plaatsaanduidingstekst met betrekking tot de eigenschap metadata op te geven.

**Vereist**: Gebruik deze eigenschap om een eigenschap metadata als verplicht op de eigenschappenpagina te markeren.

**Bewerken** uitschakelen: Gebruik deze eigenschap om een eigenschap metadata onbewerkbaar te maken op de eigenschappenpagina.

**Leeg veld alleen**-lezen tonen: Mark this property to display a metadata property on the properties page even if it has no value. Wanneer een eigenschap metadata geen waarde heeft, wordt deze standaard niet vermeld op de eigenschappenpagina.

**Genummerde** lijst tonen: Gebruik deze eigenschap om een geordende keuzelijst weer te geven

**Keuzen**: Gebruik deze eigenschap om keuzen in een lijst op te geven

**Omschrijving** : Gebruik deze eigenschap om een korte beschrijving toe te voegen voor de metagegevenscomponent.

**Klasse**: Objectklasse waaraan de eigenschap is gekoppeld.

**Pictogram** verwijderen Klik op dit pictogram om een component uit het schema te verwijderen.

>[!NOTE]
>
>De component Verborgen veld bevat deze kenmerken niet. In plaats daarvan bevat de klasse eigenschappen, zoals Naam, Waarde, Veldlabel en Beschrijving. De waarden voor de component Verborgen veld worden als een POST-parameter verzonden wanneer het element wordt opgeslagen. Deze wordt niet opgeslagen als metagegevens voor het element.

Als u de optie **[!UICONTROL Required]** selecteert, kunt u zoeken naar assets waarvoor verplichte metadata ontbreken. Vouw in het deelvenster **[!UICONTROL Filters]** het predicaat **[!UICONTROL Metadata Validation]** uit en selecteer de optie **[!UICONTROL Invalid]**. In de zoekresultaten worden assets weergegeven waarvoor verplichte metadata ontbreken die u via het schemaformulier hebt geconfigureerd.

![chlimage_1-178](assets/chlimage_1-178.png)

Als u de component Contextuele metagegevens toevoegt aan een tabblad van een schemaformulier, wordt de component weergegeven als een lijst op de eigenschappenpagina van elementen waarop het specifieke schema wordt toegepast. De lijst bevat alle andere tabbladen, behalve het tabblad waarop u de component Contextuele metagegevens hebt toegepast. Momenteel biedt deze functie basisfunctionaliteit voor het beheren van de weergave van metagegevens op basis van de context.

![chlimage_1-179](assets/chlimage_1-179.png)

Als u een tabblad in de eigenschappenpagina wilt opnemen, naast het tabblad waarop de component Contextuele metagegevens is toegepast, selecteert u het tabblad in de lijst. Het tabblad wordt toegevoegd aan de pagina met eigenschappen.

![chlimage_1-180](assets/chlimage_1-180.png)

### Eigenschappen in JSON-bestand opgeven {#specifying-properties-in-json-file}

In plaats van eigenschappen voor de opties op het tabblad **[!UICONTROL Settings]** op te geven, kunt u de opties in een JSON-bestand definiëren door overeenkomstige sleutel-waardeparen op te geven. Geef het pad van het JSON-bestand op in het veld **[!UICONTROL JSON Path]**.

### Een tabblad toevoegen aan of verwijderen uit het schemaformulier {#adding-deleting-a-tab-in-the-schema-form}

Met de schema-editor kunt u een tabblad toevoegen of verwijderen. Het standaardschemaformulier bevat standaard de tabbladen **[!UICONTROL Basic]**, **[!UICONTROL Advanced]**, **[!UICONTROL IPTC]** en **[!UICONTROL IPTC Extension]**.

![chlimage_1-181](assets/chlimage_1-181.png)

Klik `+` om een nieuw tabblad toe te voegen aan een schemaformulier. Standaard heeft het nieuwe tabblad de naam `Unnamed-1`. U kunt de naam wijzigen van het **[!UICONTROL Settings]** tabblad. Klik `X` om een tabblad te verwijderen.

![chlimage_1-182](assets/chlimage_1-182.png)

## Formulieren met metagegevens verwijderen {#deleting-metadata-schema-forms}

Met AEM kunt u alleen aangepaste schema-formulieren verwijderen. U kunt hiermee de standaardschema-formulieren/sjablonen niet verwijderen. U kunt echter alle aangepaste wijzigingen in deze formulieren verwijderen.

Als u een formulier wilt verwijderen, selecteert u een formulier en klikt u op het **[!UICONTROL Delete]** pictogram.

>[!NOTE]
>
>Nadat u aangepaste wijzigingen in een standaardformulier hebt verwijderd, wordt het vergrendelingspictogram opnieuw weergegeven in de interface Metagegevensschema om aan te geven dat de standaardstatus van het formulier is hersteld.

>[!NOTE]
>
>In AEM Assets kunt u het schema voor metagegevens in het vak niet verwijderen.

## Schema-formulieren voor MIME-typen {#schema-forms-for-mime-types}

AEM Assets bevat standaardformulieren voor verschillende MIME-typen uit het vak. U kunt echter aangepaste formulieren toevoegen voor elementen van verschillende MIME-typen.

### Nieuwe formulieren toevoegen voor MIME-typen {#adding-new-forms-for-mime-types}

Maak een nieuw formulier onder het juiste formuliertype. For example, to add a new template for the `image/png` subtype, create the form under the `image` forms. De titel voor het schemaformulier is de naam van het subtype. In dit geval is de titel `png`.

### Een bestaande schemasjabloon gebruiken voor verschillende MIME-typen {#using-an-existing-schema-template-for-various-mime-types}

U kunt een bestaande sjabloon voor een ander MIME-type gebruiken. Gebruik het `image/jpeg` formulier bijvoorbeeld voor elementen van het type MIME `image/png`.

In dit geval maakt u een nieuw knooppunt in `/etc/dam/metadataeditor/mimetypemappings` de CRX-opslagplaats. Geef een naam voor het knooppunt op en definieer de volgende eigenschappen:

| Naam | Beschrijving | Type | Waarde |
|---|---|---|---|
| `exposedmimetype` | Naam van het bestaande formulier dat moet worden toegewezen | `String` | `image/jpeg` |
| `mimetypes` | Lijst met MIME-typen die het formulier gebruiken dat is gedefinieerd in het `exposedmimetype` kenmerk | `String` | `image/png` |

AEM Assets wijst de volgende MIME-typen en schema-formulieren toe:

| Schema-formulier | MIME-typen |
|---|---|
| image/jpeg | image/pjpeg |
| image/tiff | image/x-tiff |
| application/pdf | application/postscript |
| application/x-ImageSet | Multipart/aanverwante; type=application/x-ImageSet |
| application/x-SpinSet | Multipart/aanverwante; type=application/x-SpinSet |
| application/x-MixedMediaSet | Multipart/aanverwante; type=application/x-MixedMediaSet |
| video/quicktime | video/x-quicktime |
| video/mpeg4 | video/mp4 |
| video/avi | video/avi, video/msvideo, video/x-msvideo |
| video/wmv | video/x-ms-wmv |
| video/flv | video/x-flv |

## Toegang tot metagegevensschema&#39;s verlenen {#granting-access-to-metadata-schemas}

De functie voor het metagegevensschema is alleen beschikbaar voor beheerders. Beheerders kunnen echter toegang verlenen aan gebruikers die geen beheerder zijn door machtigingen voor **[!UICONTROL Create]**, **[!UICONTROL Modify]** en **[!UICONTROL Delete]** machtigingen voor de `/conf` map op te geven.

## Mapspecifieke metagegevens toepassen {#applying-folder-specific-metadata}

Met AEM Assets kunt u een variant van een metagegevensschema definiëren en dit toepassen op een specifieke map.

U kunt bijvoorbeeld een variant van het standaardmetagegevensschema definiëren en deze toepassen op een map. Wanneer u het gewijzigde schema toepast, wordt het oorspronkelijke standaardmetagegevensschema genegeerd dat op elementen in de map is toegepast.

Alleen elementen die zijn geüpload naar de map waarop dit schema is toegepast, voldoen aan de gewijzigde metagegevens die zijn gedefinieerd in het metagegevensschema voor de variant.

Elementen in andere mappen waarop het oorspronkelijke schema is toegepast, voldoen nog steeds aan de metagegevens die in het oorspronkelijke schema zijn gedefinieerd.

Metagegevensovererving door elementen is gebaseerd op het schema dat wordt toegepast op de map op het eerste niveau in de hiërarchie. Met andere woorden, als een map geen submappen bevat, nemen de elementen in de map de metagegevens over van het schema dat op de map is toegepast.

Als de map een submap heeft, nemen de elementen in de submap de metagegevens over van het schema dat op submapniveau wordt toegepast als een ander schema op submapniveau wordt toegepast. Als echter geen schema of hetzelfde schema wordt toegepast op submapniveau, overerven de submapelementen de metagegevens van het schema dat is toegepast op het niveau van de bovenliggende map.

1. Klik op het AEM-logo en ga naar **[!UICONTROL Tools > Assets > Metadata Schemas]**. De pagina **[!UICONTROL Metadata Schema Forms]** wordt weergegeven.
1. Schakel het selectievakje in voor een formulier, bijvoorbeeld het standaardmetagegevensformulier, en klik op het pictogram of tik op het **[!UICONTROL Copy]** pictogram en sla het op als een aangepast formulier. Geef bijvoorbeeld een aangepaste naam voor het formulier op `my_default`. U kunt ook een aangepast formulier maken.

   ![chlimage_1-184](assets/chlimage_1-184.png)

1. Selecteer het **[!UICONTROL Metadata Schema Forms]** formulier op de `my_default` pagina en klik op **[!UICONTROL Edit]**.

1. Voeg op de **[!UICONTROL Metadata Schema Editor]** pagina een tekstveld toe aan het schema. Voeg bijvoorbeeld een veld met het label toe **[!UICONTROL Category]**.

   ![chlimage_1-186](assets/chlimage_1-186.png)

1. Klik op **[!UICONTROL Save]**. Het gewijzigde formulier wordt weergegeven op de **[!UICONTROL Metadata Schema Forms]** pagina.
1. Klik/tik **[!UICONTROL Apply to Folder(s)]** van de toolbar om de douanemetagegevens op een omslag toe te passen.

   ![chlimage_1-187](assets/chlimage_1-187.png)

1. Selecteer de map waarop u het gewijzigde schema wilt toepassen en klik/tik op **[!UICONTROL Apply]**.

   ![chlimage_1-188](assets/chlimage_1-188.png)

1. Als op de map het andere metagegevensschema is toegepast, verschijnt er een waarschuwing dat u op het punt staat het bestaande metagegevensschema te overschrijven. Klik op **[!UICONTROL Overwrite]**.
1. Klik **[!UICONTROL OK]** om het succesbericht te sluiten.
1. Navigeer naar de map waarop u het gewijzigde metagegevensschema hebt toegepast.

## Verplichte metagegevens definiëren {#defining-mandatory-metadata}

U kunt verplichte velden definiëren op mapniveau. Deze worden afgedwongen voor elementen die naar de map worden geüpload. Als u elementen uploadt met ontbrekende metagegevens voor de verplichte velden die u eerder hebt gedefinieerd, wordt een visuele indicatie voor ontbrekende metagegevens weergegeven in de weergave Kaart.

>[!NOTE]
>
>Een metagegevensveld kan op basis van de waarde van een ander veld als verplicht worden gedefinieerd. In de weergave Kaarten geeft AEM het waarschuwingsbericht over ontbrekende metagegevens voor dergelijke verplichte metagegevensvelden niet weer.

1. Klik op het AEM-logo en ga naar **[!UICONTROL Tools > Assets > Metadata Schemas]**. De pagina **[!UICONTROL Metadata Schema Forms]** wordt weergegeven.
1. Sla het standaardmetagegevensformulier op als een aangepast formulier. Sla het bestand bijvoorbeeld op als `my_default`.

   ![chlimage_1-189](assets/chlimage_1-189.png)

1. Bewerk het aangepaste formulier. Voeg een verplicht veld toe. Voeg bijvoorbeeld een veld **Categorie** toe en maak het veld verplicht.

   ![chlimage_1-190](assets/chlimage_1-190.png)

1. Klik op **[!UICONTROL Save]**. Het gewijzigde formulier wordt weergegeven op de **[!UICONTROL Metadata Schema Forms]** pagina. Als u de aangepaste metagegevens wilt toepassen op een map, selecteert u het formulier en klikt of tikt u op de werkbalk op **[!UICONTROL Apply to Folder(s)]** het formulier.

1. Navigeer naar de map en upload elementen met ontbrekende metagegevens voor het verplichte veld dat u aan het aangepaste formulier hebt toegevoegd. In de weergave Kaart voor de elementen wordt een bericht weergegeven voor de ontbrekende metagegevens voor het verplichte veld.

   ![chlimage_1-192](assets/chlimage_1-192.png)

1. (Optioneel) Toegang `http://[server]:[port]/system/console/components/`. Vorm en laat `com.day.cq.dam.core.impl.MissingMetadataNotificationJob` component toe die door gebrek wordt onbruikbaar gemaakt. Stel een frequentie in waarmee AEM controleert of metagegevens over de elementen geldig zijn.
Deze configuratie voegt een eigenschap toe `hasValidMetadata` aan jcr:inhoud van elementen. Met deze eigenschap kunnen AEM resultaten in een zoekopdracht filteren.

>[!NOTE]
>
>Als een element wordt toegevoegd na de geplande controle, wordt het element pas gemarkeerd met `hasValidMetadata` de volgende geplande controle. De elementen worden niet weergegeven in tussenliggende zoekresultaten.

>[!CAUTION]
>
>De controles van de meta-gegevensbevestiging zijn middelintensief en kunnen de prestaties van uw systeem beïnvloeden. Plan de controles dienovereenkomstig. Als de AEM implementatie prestatieproblemen heeft, kunt u deze taak uitschakelen.
