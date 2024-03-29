---
title: Metagegevensschema's
description: Het metagegevensschema definieert de indeling van de pagina met eigenschappen en de eigenschappen van metagegevens die voor elementen worden weergegeven. Leer hoe u een aangepast metagegevensschema kunt maken, het schema voor metagegevens kunt bewerken en hoe u het schema voor metagegevens op elementen kunt toepassen.
contentOwner: AG
feature: Metadata
role: User,Admin
exl-id: 82f42bb3-2c01-407c-a41b-9abe7be4660e
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '2422'
ht-degree: 8%

---

# Metadataschema&#39;s {#metadata-schemas}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

In [!DNL Experience Manager Assets], definieert een metagegevensschema de lay-out van de pagina met eigenschappen en de eigenschappen van metagegevens die worden weergegeven voor elementen die het specifieke schema gebruiken. Tot de metagegevenseigenschappen behoren titel, beschrijving, MIME-typen, tags, enzovoort. U kunt de redacteur van Forms van het Schema van Meta-gegevens gebruiken om bestaande schema&#39;s te wijzigen of douanemetagegevensschema&#39;s toe te voegen.

Ga als volgt te werk om de pagina met eigenschappen voor een element weer te geven en te bewerken:

1. Klik of tik op **[!UICONTROL View Properties]** van snelle acties op de middelentegel in de weergave Kaart.

   ![chlimage_1-170](assets/chlimage_1-170.png)

   U kunt ook een element selecteren en vervolgens op het element klikken of tikken **[!UICONTROL Properties]** op de werkbalk.

   ![chlimage_1-171](assets/chlimage_1-171.png)

1. U kunt de verschillende bewerkbare eigenschappen van metagegevens bewerken onder de beschikbare tabbladen. U kunt het element echter niet wijzigen [!UICONTROL Type] in de [!UICONTROL Basic] tabblad met eigenschappen.

   ![chlimage_1-172](assets/chlimage_1-172.png)

   Als u het MIME-type voor een element wilt wijzigen, gebruikt u een aangepast schema voor metagegevens of wijzigt u een bestaand formulier. Zie [Metagegevensschema Forms bewerken](metadata-schemas.md#editing-metadata-schema-forms) voor meer informatie . Als u het metagegevensschema voor een bepaald MIME-type wijzigt, worden de pagina-indeling van de eigenschappen voor elementen met het huidige MIME-type en alle elementsubtypen gewijzigd. Als u bijvoorbeeld een `jpeg` schema onder `default/image` wijzigt alleen de indeling van metagegevens (eigenschappen van elementen) voor elementen met het MIME-type `IMAGE/JPEG`. Als u echter het standaardschema bewerkt, worden de wijzigingen doorgevoerd in de indeling van de metagegevens voor alle typen elementen.

## Metagegevensschema Forms {#default-metadata-schema-forms}

Als u een lijst met formulieren/sjablonen wilt weergeven, gaat u naar [!DNL Experience Manager] interface navigeert naar **[!UICONTROL Tools]** > **[!UICONTROL Assets]** > **[!UICONTROL Metadata Schemas]**.

[!DNL Experience Manager] Hier vindt u de volgende sjablonen voor het schema van metagegevens:

| Sjablonen |  | Beschrijving |
|---|---|---|
| [!UICONTROL default] |  | Het basisschema voor metagegevens voor elementen. |
|  | De volgende onderliggende formulieren nemen de eigenschappen over van [!UICONTROL default] formulier: |  |
|  | <ul><li> [!UICONTROL dm_video]</li></ul> | Schema voor Dynamic Media-video&#39;s. |
|  | <ul><li> [!UICONTROL image]</li></ul> | Schema-formulier voor elementen met het MIME-type &quot;image&quot;, bijvoorbeeld afbeelding/jpeg, afbeelding/png, enzovoort. <br> De [!UICONTROL image] formulier heeft de volgende onderliggende formuliersjablonen: <ul><li> [!UICONTROL jpeg]: Schema-formulier voor activa met subtype [!UICONTROL jpeg].</li> <li>[!UICONTROL tiff]: Schema voor de activa met subtype [!UICONTROL tiff].</li></ul> |
|  | <ul><li> [!UICONTROL application]</li></ul> | Schema-formulier voor elementen met het MIME-type &quot;application&quot;, bijvoorbeeld application/ pdf, application/ zip enzovoort. <br>[!UICONTROL pdf]: Schemaformulier voor activa met subtype pdf. |
|  | <ul><li>[!UICONTROL video]</li></ul> | Schema-formulier voor elementen met het MIME-type &quot;video&quot;, zoals video/avi, video/mp4, enzovoort. |
| [!UICONTROL collection] |  | Schemaformulier voor verzamelingen. |
| [!UICONTROL contentfragment] |  | Schemaformulier voor inhoudsfragmenten. |
| [!UICONTROL forms] |  | Dit schema-formulier heeft betrekking op [Adobe Experience Manager Forms](/help/forms/home.md). |

>[!NOTE]
>
>Als u de onderliggende formulieren van een schema wilt weergeven, klikt of tikt u op de naam van het schema.

## Een metagegevensschema toevoegen {#adding-a-metadata-schema-form}

1. Als u een aangepaste sjabloon aan de lijst wilt toevoegen, klikt u op **[!UICONTROL Create]** op de werkbalk.

   >[!NOTE]
   >
   >Onbewerkte sjablonen geven vóór de sjablonen een vergrendelingspictogram weer. Als u een van de sjablonen aanpast, verdwijnt het vergrendelingspictogram voordat de sjabloon verdwijnt.

1. Voer in het dialoogvenster de titel van het schema in en klik op **[!UICONTROL Create]** om het maken van het formulier te voltooien.

   ![chlimage_1-174](assets/chlimage_1-174.png)

## Formulieren met metagegevensschema bewerken {#editing-metadata-schema-forms}

U kunt een nieuw of bestaand schema voor metagegevens bewerken. Het metagegevensschema bevat het volgende:

* Tabs
* Formulieritems in tabbladen.

U kunt deze formulieritems toewijzen/configureren aan een veld binnen een metagegevensknooppunt in de CRX-opslagruimte.

U kunt nieuwe tabbladen of formulieritems toevoegen aan het metagegevensschemaformulier. De tabbladen en formulieritems die van het bovenliggende element zijn afgeleid, bevinden zich in de vergrendelde status. U kunt deze niet wijzigen op het niveau van het kind.

1. In de **[!UICONTROL Schema Forms]** pagina, selecteert u het selectievakje voor een formulier en klikt u op **[!UICONTROL Edit]** op de werkbalk.

   ![chlimage_1-175](assets/chlimage_1-175.png)

1. Pas op de pagina **[!UICONTROL Metadata Schema Editor]** de eigenschappenpagina van de asset aan door een of meer componenten uit de lijst met componenttypen op het tabblad **[!UICONTROL Build Form]** naar het tabblad **[!UICONTROL Basic]** te slepen.

   ![chlimage_1-176](assets/chlimage_1-176.png)

1. Als u een component wilt configureren, selecteert u deze en wijzigt u de eigenschappen ervan in het dialoogvenster **[!UICONTROL Settings]** tab.

### Componenten op het tabblad Formulier samenstellen {#components-within-the-build-form-tab}

De **[!UICONTROL Build Form]** wordt een overzicht gegeven van de formulieritems die u in het schemaformulier gebruikt. De **[!UICONTROL Settings]** bevat de kenmerken van elk item dat u selecteert in het dialoogvenster **[!UICONTROL Build Form]** tab. In de volgende tabel worden de formulieritems weergegeven die beschikbaar zijn in het dialoogvenster **[!UICONTROL Build Form]** tab:

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

Als u de eigenschappen van een metagegevenscomponent in het formulier wilt bewerken, klikt u op de component en bewerkt u alle eigenschappen of een subset van de volgende eigenschappen in het dialoogvenster **[!UICONTROL Settings]** tab.

**Veldlabel**: De naam van de eigenschap metadata die wordt weergegeven op de eigenschappenpagina voor het element.

**Toewijzen aan eigenschap**: This property specifies the relative path/name to the asset node where it is saved in the CRX repository. Het begint met `./` omdat dit aangeeft dat het pad zich onder het knooppunt van het element bevindt.

Hier volgen de geldige waarden voor deze eigenschap:

* `./jcr:content/metadata/dc:title`: Hiermee wordt de waarde in het metadataknooppunt van de asset opgeslagen als de eigenschap `dc:title`.

* `./jcr:created`: Geeft de JCR-eigenschap weer op het knooppunt van het element. Als u deze eigenschappen configureert op weergave-eigenschappen, raden wij aan deze te markeren als Bewerken uitschakelen, omdat deze beveiligd zijn. Anders wordt de fout [!UICONTROL Asset(s) failed to modify] resultaten wanneer u de eigenschappen van het element opslaat.

Om ervoor te zorgen dat de component correct in de vorm van het meta-gegevensschema wordt getoond, zou de bezitspad geen ruimten moeten omvatten.

**Plaatsaanduiding**: Gebruik deze eigenschap om relevante plaatsaanduidingstekst met betrekking tot de eigenschap metadata op te geven.

**Vereist**: Gebruik deze eigenschap om een eigenschap metadata als verplicht op de eigenschappenpagina te markeren.

**Bewerken uitschakelen**: Gebruik deze eigenschap om een eigenschap metadata onbewerkbaar te maken op de eigenschappenpagina.

**Leeg veld alleen-lezen tonen**: Mark this property to display a metadata property on the properties page even if it has no value. Wanneer een eigenschap metadata geen waarde heeft, wordt deze standaard niet vermeld op de eigenschappenpagina.

**Genummerde lijst tonen**: Gebruik deze eigenschap om een geordende keuzelijst weer te geven

**Keuzen**: Gebruik deze eigenschap om keuzen in een lijst op te geven

**Beschrijving** : Gebruik deze eigenschap om een korte beschrijving toe te voegen voor de metagegevenscomponent.

**Klasse**: Objectklasse waaraan de eigenschap is gekoppeld.

**Pictogram Verwijderen** Klik op dit pictogram om een component uit het schema te verwijderen.

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

Klikken `+` om een nieuw tabblad toe te voegen aan een schemaformulier. Standaard heeft het nieuwe tabblad de naam `Unnamed-1`. U kunt de naam wijzigen in het menu **[!UICONTROL Settings]** tab. Klikken `X` om een tabblad te verwijderen.

![chlimage_1-182](assets/chlimage_1-182.png)

## Formulieren met metagegevens verwijderen {#deleting-metadata-schema-forms}

[!DNL Experience Manager] Hiermee kunt u alleen aangepaste schema-formulieren verwijderen. U kunt hiermee de standaardschema-formulieren/sjablonen niet verwijderen. U kunt echter alle aangepaste wijzigingen in deze formulieren verwijderen.

Als u een formulier wilt verwijderen, selecteert u een formulier en klikt u op de knop **[!UICONTROL Delete]** pictogram.

>[!NOTE]
>
>Nadat u aangepaste wijzigingen in een standaardformulier hebt verwijderd, wordt het vergrendelingspictogram opnieuw weergegeven in de interface Metagegevensschema om aan te geven dat de standaardstatus van het formulier is hersteld.

>[!NOTE]
>
>U kunt de metagegevensformulieren uit het vak niet verwijderen in [!DNL Experience Manager] Elementen.

## Schema-formulieren voor MIME-typen {#schema-forms-for-mime-types}

[!DNL Experience Manager] Elementen bieden standaardformulieren voor verschillende MIME-typen uit het vak. U kunt echter aangepaste formulieren toevoegen voor elementen van verschillende MIME-typen.

### Nieuwe formulieren toevoegen voor MIME-typen {#adding-new-forms-for-mime-types}

Maak een nieuw formulier onder het juiste formuliertype. Als u bijvoorbeeld een nieuwe sjabloon wilt toevoegen voor de `image/png` subtype maken, het formulier maken onder de `image` formulieren. De titel voor het schemaformulier is de naam van het subtype. In dit geval is de titel `png`.

### Een bestaande schemasjabloon gebruiken voor verschillende MIME-typen {#using-an-existing-schema-template-for-various-mime-types}

U kunt een bestaande sjabloon voor een ander MIME-type gebruiken. Gebruik bijvoorbeeld de `image/jpeg` formulier voor activa van het MIME-type `image/png`.

In dit geval maakt u een nieuw knooppunt op `/etc/dam/metadataeditor/mimetypemappings` in de CRX-opslagplaats. Geef een naam voor het knooppunt op en definieer de volgende eigenschappen:

| Naam | Beschrijving | Type | Waarde |
|---|---|---|---|
| `exposedmimetype` | Naam van het bestaande formulier dat moet worden toegewezen | `String` | `image/jpeg` |
| `mimetypes` | Lijst met MIME-typen die het formulier gebruiken dat is gedefinieerd in het dialoogvenster `exposedmimetype` attribute | `String` | `image/png` |

[!DNL Experience Manager] Elementen wijzen de volgende MIME-typen en schema-formulieren toe:

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

De functie voor het metagegevensschema is alleen beschikbaar voor beheerders. Beheerders kunnen echter toegang verlenen aan gebruikers die geen beheerder zijn, door **[!UICONTROL Create]**, **[!UICONTROL Modify]**, en **[!UICONTROL Delete]** machtigingen voor de `/conf` map.

## Mapspecifieke metagegevens toepassen {#applying-folder-specific-metadata}

[!DNL Experience Manager] Met elementen kunt u een variant van een metagegevensschema definiëren en dit toepassen op een specifieke map.

U kunt bijvoorbeeld een variant van het standaardmetagegevensschema definiëren en deze toepassen op een map. Wanneer u het gewijzigde schema toepast, wordt het oorspronkelijke standaardmetagegevensschema genegeerd dat op elementen in de map is toegepast.

Alleen elementen die zijn geüpload naar de map waarop dit schema is toegepast, voldoen aan de gewijzigde metagegevens die zijn gedefinieerd in het metagegevensschema voor de variant.

Elementen in andere mappen waarop het oorspronkelijke schema is toegepast, voldoen nog steeds aan de metagegevens die in het oorspronkelijke schema zijn gedefinieerd.

Metagegevensovererving door elementen is gebaseerd op het schema dat wordt toegepast op de map op het eerste niveau in de hiërarchie. Met andere woorden, als een map geen submappen bevat, nemen de elementen in de map de metagegevens over van het schema dat op de map is toegepast.

Als de map een submap heeft, nemen de elementen in de submap de metagegevens over van het schema dat op submapniveau wordt toegepast als een ander schema op submapniveau wordt toegepast. Als echter geen schema of hetzelfde schema wordt toegepast op submapniveau, overerven de submapelementen de metagegevens van het schema dat is toegepast op het niveau van de bovenliggende map.

1. Klik op de knop [!DNL Experience Manager] logo en navigeer naar **[!UICONTROL Tools > Assets > Metadata Schemas]**. De pagina **[!UICONTROL Metadata Schema Forms]** wordt weergegeven.
1. Schakel het selectievakje in vóór een formulier, bijvoorbeeld het standaardmetagegevensformulier, en klik op het veld of tik op het **[!UICONTROL Copy]** gebruiken en opslaan als een aangepast formulier. Een aangepaste naam voor het formulier opgeven, bijvoorbeeld `my_default`. U kunt ook een aangepast formulier maken.

   ![chlimage_1-184](assets/chlimage_1-184.png)

1. In de **[!UICONTROL Metadata Schema Forms]** pagina, selecteert u de `my_default` formulier en klik vervolgens op **[!UICONTROL Edit]**.

1. In de **[!UICONTROL Metadata Schema Editor]** , voegt u een tekstveld toe aan het schema. Voeg bijvoorbeeld een veld met het label toe **[!UICONTROL Category]**.

   ![chlimage_1-186](assets/chlimage_1-186.png)

1. Klik op **[!UICONTROL Save]**. Het gewijzigde formulier wordt weergegeven in het dialoogvenster **[!UICONTROL Metadata Schema Forms]** pagina.
1. Klikken/tikken **[!UICONTROL Apply to Folder(s)]** van de werkbalk om de aangepaste metagegevens toe te passen op een map.

   ![chlimage_1-187](assets/chlimage_1-187.png)

1. Selecteer de map waarop u het gewijzigde schema wilt toepassen en klik/tik op **[!UICONTROL Apply]**.

   ![chlimage_1-188](assets/chlimage_1-188.png)

1. Als op de map het andere metagegevensschema is toegepast, verschijnt er een waarschuwing dat u op het punt staat het bestaande metagegevensschema te overschrijven. Klik op **[!UICONTROL Overwrite]**.
1. Klikken **[!UICONTROL OK]** om het succesbericht te sluiten.
1. Navigeer naar de map waarop u het gewijzigde metagegevensschema hebt toegepast.

## Verplichte metagegevens definiëren {#defining-mandatory-metadata}

U kunt verplichte velden definiëren op mapniveau. Deze worden afgedwongen voor elementen die naar de map worden geüpload. Als u elementen uploadt met ontbrekende metagegevens voor de verplichte velden die u eerder hebt gedefinieerd, wordt een visuele indicatie voor ontbrekende metagegevens weergegeven in de weergave Kaart.

>[!NOTE]
>
>Een metagegevensveld kan op basis van de waarde van een ander veld als verplicht worden gedefinieerd. In de weergave Kaarten [!DNL Experience Manager] geeft het waarschuwingsbericht over ontbrekende metagegevens voor dergelijke verplichte metagegevensvelden niet weer.

1. Klik op de knop [!DNL Experience Manager] logo en navigeer naar **[!UICONTROL Tools > Assets > Metadata Schemas]**. De pagina **[!UICONTROL Metadata Schema Forms]** wordt weergegeven.
1. Sla het standaardmetagegevensformulier op als een aangepast formulier. Sla het bestand bijvoorbeeld op als `my_default`.

   ![chlimage_1-189](assets/chlimage_1-189.png)

1. Bewerk het aangepaste formulier. Voeg een verplicht veld toe. Voeg bijvoorbeeld een **Categorie** en verplicht te stellen.

   ![chlimage_1-190](assets/chlimage_1-190.png)

1. Klik op **[!UICONTROL Save]**. Het gewijzigde formulier wordt weergegeven in het dialoogvenster **[!UICONTROL Metadata Schema Forms]** pagina. Als u de aangepaste metagegevens wilt toepassen op een map, selecteert u het formulier en klikt of tikt u op **[!UICONTROL Apply to Folder(s)]** op de werkbalk.

1. Navigeer naar de map en upload elementen met ontbrekende metagegevens voor het verplichte veld dat u aan het aangepaste formulier hebt toegevoegd. In de weergave Kaart voor de elementen wordt een bericht weergegeven voor de ontbrekende metagegevens voor het verplichte veld.

   ![chlimage_1-192](assets/chlimage_1-192.png)

1. (Optioneel) Toegang `http://[server]:[port]/system/console/components/`. Configureren en inschakelen `com.day.cq.dam.core.impl.MissingMetadataNotificationJob` component die standaard is uitgeschakeld. Een frequentie instellen waarbij [!DNL Experience Manager] controleert of de metagegevens van de elementen geldig zijn.
Deze configuratie voegt een eigenschap toe `hasValidMetadata` to jcr:inhoud van elementen. Met deze eigenschap, [!DNL Experience Manager] kan resultaten in een onderzoek filtreren.

>[!NOTE]
>
>Als een element wordt toegevoegd na de geplande controle, wordt het element niet gemarkeerd met `hasValidMetadata` tot de volgende geplande controle. De elementen worden niet weergegeven in tussenliggende zoekresultaten.

>[!CAUTION]
>
>De controles van de meta-gegevensbevestiging zijn middelintensief en kunnen de prestaties van uw systeem beïnvloeden. Plan de controles dienovereenkomstig. Als de [!DNL Experience Manager] de implementatie heeft prestatieproblemen. Probeer deze taak uit te schakelen.
