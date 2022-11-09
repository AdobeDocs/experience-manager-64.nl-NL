---
title: NIET PUBLICEREN, MAAR NIET DELETE aanpassen van gegevenstypen voor modellen van inhoudsfragmenten
seo-title: Customizing Data Types for Content Fragment Models
description: Gegevenstypen die worden gebruikt in Modellen van inhoudsfragment kunnen worden aangepast.
seo-description: Data types used in Content Fragment Models can be customized.
page-status-flag: de-activated
uuid: d8215dbf-2dbe-43cb-a5c1-dc1cb412a204
contentOwner: AEM Docs
discoiquuid: a8b8155c-852c-4d16-b59b-7e19527c2bd4
noindex: true
source-git-commit: 3358f6b8b492ff2b5858867a1f48a57b06944b1e
workflow-type: tm+mt
source-wordcount: '1625'
ht-degree: 0%

---


# NIET PUBLICEREN, MAAR NIET DELETE aanpassen van gegevenstypen voor modellen van inhoudsfragmenten{#do-not-publish-but-do-not-delete-customizing-data-types-for-content-fragment-models}

[Inhoudsfragmenten](/help/assets/content-fragments.md) zijn gebaseerd op [inhoudsfragmentmodellen](/help/assets/content-fragments-models.md). Deze modellen zijn opgebouwd uit [elementen](/help/assets/content-fragments.md#constituent-parts-of-a-content-fragment) van verschillende gegevenstypen.

Verschillende gegevenstypen zijn offline beschikbaar, zoals tekst op één regel, RTF-tekst op meerdere regels, numerieke velden, Booleaanse kiezers, opties voor vervolgkeuzemenu, datum en tijd en andere. AEM gebruikers kunnen gegevenstypen selecteren op basis van de redactionele intentie van het (de) overeenkomstige fragment(en). Op deze manier kunt u eenvoudig met tekstmodellen werken in complexe modellen met verschillende soorten inhoud en de bijbehorende ervaring bij het ontwerpen van fragmenten.

Gegevenstypen worden gedefinieerd door een [combinatie van knooppunteigenschappen](#properties) vastgehouden [specifieke locaties in de opslagplaats](#locations-in-the-repository). U kunt ook uw eigen [gegevenstypen](#creating-your-data-type) en [fieldProperties](#creating-your-own-fieldproperties-property).

<!-- Please uncomment when files are used>
>[!NOTE]
>
>See also [Customizing Content Fragment Models](/help/sites-developing/customizing-content-fragment-models.md).
-->

## Locaties in de opslagplaats {#locations-in-the-repository}

Alle out-of-box datatypes worden gedeclareerd onder:

`/libs/settings`

U kunt nieuwe gegevenstypen toevoegen door de nodestructuur als volgt te bedekken onder `/apps`:

`/apps/settings/dam/cfm/models/formbuilderconfig/datatypes/items`

>[!CAUTION]
>
>U mag niets wijzigen in het dialoogvenster `/libs` pad.
>
>Om het even wat er kan veranderen bij de volgende verbetering, of installatie van de dienst of los verpakking op.

## Eigenschappen {#properties}

Node-eigenschappen worden gebruikt om de gegevenstypen te definiëren:

* [Eigenschappen van gegevenstypen](#data-type-properties)
* en binnen die [fieldProperties](#fieldproperties)

### Eigenschappen van gegevenstype {#data-type-properties}

Alle gegevenstypen worden in een nodestructuur vertegenwoordigd zoals onder:

`/libs/settings/dam/cfm/models/formbuilderconfig/datatypes/items`

Elk knooppunt onder `/items` heeft eigenschappen die bepalen hoe dat gegevenstype binnen de modelredacteur zou moeten worden vertegenwoordigd.

Alle volgende eigenschappen moeten aanwezig zijn opdat het gegevenstype in de modelredacteur aanwezig is:

* `fieldIcon`

   [CoralUI-pictogram](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/coral-ui/coralui3/Coral.Icon.html#availableicons) om het gegevenstype in modelredacteur UI te vertegenwoordigen.

* ` [fieldProperties](#fieldproperties)`

   Een array die de configuratie-eigenschappen voor elk gegevenstype vertegenwoordigt.

* `fieldResourceType`

   Het Sling-brontype dat wordt gebruikt om het gegevenstype in een inhoudsfragment te renderen. Voor gegevenstypen die op verschillende manieren kunnen worden gerenderd (bijvoorbeeld als eenvoudige tekstinvoer en/of tekstinvoer met meerdere regels), moet deze eigenschap worden gemaakt als een array met alle typen bronnen. De `renderasfield` eigenschap wordt automatisch toegevoegd aan `fieldProperties` om de gebruiker het middeltype te laten kiezen zij aan het model moeten toevoegen,

* `fieldPropResourceType`

   Het Sling middeltype dat wordt gebruikt om het standaardbezit voor het gegevenstype terug te geven.

   Bijvoorbeeld voor het gegevenstype:

   * Tekst met één regel `fieldPropResourceType` zou `textfield` component
   * Boolean, de `fieldPropResourceType` zou `checkbox` component

* `fieldViewResourceType`

   Het Sling-brontype dat wordt gebruikt om het gegevenstype in de voorvertoning te renderen bij het samenstellen van het model. Wanneer de gebruiker het gegevenstype aan de linkerkant van de modelredacteur sleept, `fieldViewResourceType` eigenschap vertegenwoordigt de component die daar wordt gerenderd. Dit wordt gebruikt voor gevallen waar u niet de volledige component wilt teruggeven, maar slechts een substituut willen teruggeven die de overhead aan de modelredacteur minimaliseert.

* `fieldTitle`

   Eigenschap die de titel van dit gegevenstype definieert. Bijvoorbeeld: **Tekst met één regel** voor een `textfield` component, **Tekst met meerdere regels** voor een component met meerdere velden.

* `valueType`

   Dit is het type van waarde dat het gegevenstype terugkeert wanneer het intern wordt opgeslagen. Zie [Toewijzingen](#mappings).

* `renderType`

   Dit is een interne representatie van het gegevenstype. Het verbindt `valueType` naar een UI-component. Zie [Toewijzingen](#mappings).

* `listOrder`

   Elk gegevenstype heeft een waarde nodig die de volgorde in de lijst aangeeft. Dit wordt gebruikt om de correcte orde van de diverse gebieden (toegevoegd/bewogen door belemmering en daling) te verzekeren wanneer het bewaren van de modelredacteur. Deze waarde moet een geheel getal zijn en het wordt aanbevolen het getal op oplopende, geordende wijze toe te wijzen. Wanneer u een nieuw gegevenstype maakt, kunt u het beste de waarde toewijzen op basis van het laatste gegevenstype in de lijst (de hoogste waarde van `listOrder` waarde aanwezig in de gegevenstypen).

#### Toewijzingen {#mappings}

<table> 
 <tbody> 
  <tr> 
   <td>Gegevenstype<br /> </td> 
   <td>Type waarde<br /> </td> 
   <td>Rendertype</td> 
  </tr> 
  <tr> 
   <td>Tekst met één regel</td> 
   <td>string</td> 
   <td>text-single</td> 
  </tr> 
  <tr> 
   <td>Tekst met meerdere regels</td> 
   <td>tekenreeks, met inhoudstype<br /> </td> 
   <td>text-multi</td> 
  </tr> 
  <tr> 
   <td>Getal (geheel getal/lang)<br /> </td> 
   <td>long</td> 
   <td>getal</td> 
  </tr> 
  <tr> 
   <td>Getal (dubbel/zwevend)</td> 
   <td>double</td> 
   <td>getal</td> 
  </tr> 
  <tr> 
   <td>Boolean</td> 
   <td>boolean</td> 
   <td>boolean</td> 
  </tr> 
  <tr> 
   <td>Datum en tijd</td> 
   <td>kalender</td> 
   <td>time</td> 
  </tr> 
  <tr> 
   <td>Opsomming</td> 
   <td>string/long</td> 
   <td>opsomming</td> 
  </tr> 
  <tr> 
   <td>Tags</td> 
   <td>string</td> 
   <td>tags</td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Sommige typen (bijvoorbeeld `string`, `long`, onder meer) kan worden gemultiwaardeerd. In dit geval wordt de component die wordt gebruikt voor renderen en bewerken doorgaans omwikkeld door een component met meerdere velden ( `granite/ui/components/coral/foundation/form/multifield`). De uitzondering hierop zijn codes, waarbij de bewerkingscomponent verantwoordelijk is voor de juiste rendering.

### fieldProperties {#fieldproperties}

De configuratie-eigenschappen voor elk gegevenstype. Waarden voor `fieldProperties`:

* `base`

   Dit is de basis voor alles `fieldProperties` componenten. De definitie valt onder `/libs/dam/cfm/models/editor/components/datatypeproperties/base`.

   De variabele bevat `fieldRoot`, die vervolgens `fieldProperties` kan worden gebruikt bij het maken van invoer om het juiste pad op te halen.

   Voorbeeld: om het juiste pad voor een **Veldlabel** u hebt de sleutel nodig om de component te identificeren waartoe dit behoort, de input voor dit gebied zou moeten `fieldRoot` + `<*fieldLabel*>`

* `checkboxfields`

   Deze component voegt het standaardselectievakje voor de `Boolean` gegevenstype en de parameters Sling `checked@Delete` en `checked@TypeHint`.

* `datepickerfields`

   Component die de verborgen inputs toevoegt die nodig zijn om de component van de datumkiezer te laten functioneren. Omvat het maken van de eigenschappen `defaultDateField`, `displayedFormat`, `emptyText`, `valueFormat`, `minDate` en `maxDate`.

* `datetimepickerfields`

   Hiermee wordt een veld geselecteerd voor `Date&Time` gegevenstype voor onderscheid tussen `Date` en `Date&Time` opties.

* `datevaluefield`

   Hiermee wordt een datepicker toegevoegd aan de eigenschappen, zodat een gebruiker een standaard kan selecteren voor de `Date&Time` gegevenstype.

* `descriptionfield`

   Deze component voegt een tekstveld met meerdere regels toe dat de beschrijving vertegenwoordigt van de momenteel geselecteerde component in de editor met meerdere regels. Deze wordt automatisch toegevoegd door de renderer van de modeleditor aan het einde van elke eigenschap van het gegevenstype.

* `labelfield`

   Component die een component toevoegt `textfield` invoer die het veldlabel toevoegt voor een gegevenstype dat veldlabels kan hebben.

* `maptopropertyfield`

   Deze component voegt de `Name` in de eigenschappen, die een herkenningsteken geven aan de geselecteerde component van een gegevenstype. Het zou in alle gegevenstypes aanwezig moeten zijn.

* `maxlengthfield`

   Hiermee voegt u de opdracht `maxLength` eigenschap voor gebruik met gegevenstypen die deze eigenschap accepteren. Bijvoorbeeld met **Tekst met één regel**, **Getal**, enz.

* `multieditorfield`

   Hiermee voegt u alle verborgen velden toe die de editor met meerdere regels nodig heeft om te werken. Deze wordt vertegenwoordigd door de **Tekst met meerdere regels** gegevenstype.

* `mvfields`

   Component die alle verborgen velden toevoegt die nodig zijn voor een component met meerdere velden. Bijvoorbeeld voor de tweede optie van **Tekst met één regel** gegevenstype. Dit moet worden toegevoegd voor elke component die wordt gerenderd als een multifield.

* `numbertypefield`

   Selecteer optie voor de **Getal** gegevenstype waarin wordt geselecteerd tussen **Geheel** of **Fractie** voor de **Getal** gegevenstype.

* `numbervaluefield`

   A `numberfield` standaardwaarde voor de **Getal** `type.options` Hiermee wordt de invoer van opties toegevoegd voor de **Opsomming** gegevenstype, dat wordt gebruikt om de waarden voor de component selectBox te bepalen.

* `placeholderfield`

   Dit is een tekstveld dat fungeert als invoer voor de `emptyText` eigenschap van een component. Dit zou door alle gegevenstypes moeten worden gebruikt die placeholder (dat niet zeer ingewikkeld is; bijv. **Tekst met één regel**, **Getal**, enz.).

* `renderasfield`

   Dit is de component die automatisch wordt gerenderd wanneer er meerdere `fieldResourceTypes` zijn aanwezig in het bezit van de knoop van het gegevenstype.

* `requiredfield`

   Dit is een selectievakje dat de `required` eigenschap voor een component. Omdat de meeste componenten het `required` veld, kan dit veld worden gebruikt voor de meeste gegevenstypen.

* `tagsfields`

   Componenten die de benodigde ingangen toevoegen voor een `tagfield` component die moet worden gerenderd, wordt gebruikt door de **Tags** gegevenstype.

* `tagsroot`

   Een padkiezer die door de **Tags** gegevenstype voor instellen hoofdpad `tagsfield` component.

* `textfield`

   Wordt gebruikt door de `Boolean` gegevenstype voor het instellen van het veldlabel van het selectievakje dat door dit gegevenstype wordt gedefinieerd.

* `textvaluefield`

   De eigenschap default value voor **Tekst met één regel** gegevenstype.

## Uw gegevenstype maken {#creating-your-data-type}

Als u uw eigen gegevenstype wilt maken, moet u:

* [De knooppuntstructuur maken](#creating-the-node-structure)
* [Definieer de eigenschappen voor uw gegevenstype](#defining-the-properties-for-your-data-type)

U kunt vervolgens [gebruik uw gegevenstype](#using-your-data-type).

U kunt ook [uw eigen `fieldProperties`](#creating-your-own-fieldproperties-property).

### De knooppuntstructuur maken {#creating-the-node-structure}

De knooppuntstructuur moet onder `/apps` om de gegevenstypen te bedekken. Als dit nog niet het geval is, moet u het volgende maken:

1. Als dit nog niet het geval is, moet u het volgende maken:

   ```
   + apps 
     + settings
       + dam 
         + cfm (cq:Page) 
           + models (nt:folder)
             + formbuilderconfig (sling:folder)
               + datatypes (nt:unstructured)
                 + items (nt:unstructured)
   ```

   >[!NOTE]
   >
   >`/apps/settings/dam` reeds bestaan.
   >
   >`/cfm/models/formbuilderconfig/datatypes/items` Mogelijk moet u met de opgegeven nodetypes maken.

1. Onder `/items` u kunt nieuwe knooppunten toevoegen die uw nieuwe gegevenstype(en) vertegenwoordigen:

   * Type knooppunt: `nt:unstructured`
   * &quot;Eigenschappen: zie [Eigenschappen definiëren voor uw gegevenstype](#defining-the-properties-for-your-data-type)

### Eigenschappen definiëren voor uw gegevenstype {#defining-the-properties-for-your-data-type}

1. Waarden bepalen voor het volgende [eigenschappen van gegevenstype](#data-type-properties) die vereist zijn voor het gegevenstype:

   * `fieldResourceType`
   * `fieldPropResourceType`
   * `fieldViewResourceType`

   Deze bepalen hoe de componenten voor uw gegevenstype zullen worden teruggegeven. Zij kunnen elke component zijn; inclusief uw eigen aangepaste componenten (hiervoor is een overeenkomende set van ` [fieldProperties](#fieldproperties)`).

   Definieer deze eigenschappen met de juiste waarden op het knooppunt voor het gegevenstype.

1. De ` [fieldProperties](#fieldproperties)` te gebruiken. Dit is afhankelijk van de kenmerken of eigenschappen die uw `fieldResourceType` behoeften.

   Bijvoorbeeld een `granite/ui/components/coral/foundation/form/textfield`moet **Labelnaam**, **Maximale lengte**, **Plaatsaanduidingstekst** en **Standaardwaarde** eigenschap.

   U kunt kiezen uit de [fieldProperties](#fieldproperties), of [uw eigen eigenschappen maken](#creating-your-own-fieldproperties-property).

   Definieer deze eigenschappen met de juiste waarden op het knooppunt voor het gegevenstype.

1. Waarden bepalen voor het volgende [eigenschappen van gegevenstype](#data-type-properties):

   * `fieldIcon`
   * `fieldTitle`
   * `renderType`
   * `valueType`
   * `listOrder`

   Definieer deze eigenschappen met de juiste waarden op het knooppunt voor het gegevenstype.

### Het gegevenstype gebruiken {#using-your-data-type}

Nadat u deze knoopstructuur, met alle toegepaste eigenschappen opslaat, kunt u om het even welk model met de modelredacteur openen en, uw nieuw gegevenstype zien en gebruiken.

## Uw eigen eigenschap fieldProperties maken {#creating-your-own-fieldproperties-property}

U kunt kiezen uit de [fieldProperties](#fieldproperties)of maak uw eigen versie:

1. Een component maken onder:

   `/apps/dam/cfm/models/editor/components/datatypeproperties/`

   Als het pad niet bestaat, kunt u het maken met `nt:folder` knooppunten.

   1. Om toegang tot de variabelen te hebben, zou deze component zich moeten uitbreiden:

      `/libs/dam/cfm/models/editor/components/datatypeproperties/base`* *

   1. De component moet kunnen worden opgenomen via:

      `sling:include`

   1. Deze component moet een veld renderen (als een gebruiker gegevens moet invoeren) of een verborgen invoer met de eigenschappen die nodig zijn voor het gegevenstype. Bijvoorbeeld, vereist een multifield component een kindknoop met het type van gebied het zou moeten dupliceren, daarom zou er een input moeten zijn die (door de mechanica van de POST van de sling) een kindknoop van een specifiek type kan tot stand brengen.

1. De basisnaam van deze component moet worden toegevoegd aan `fieldProperties`.
1. Herhaal dit voor alle eigenschappen die u nodig hebt.

