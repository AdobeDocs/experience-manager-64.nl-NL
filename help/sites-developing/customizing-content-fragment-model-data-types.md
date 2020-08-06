---
title: NIET PUBLICEREN, MAAR NIET DELETE aanpassen van gegevenstypen voor modellen van inhoudsfragmenten
seo-title: Gegevenstypen aanpassen voor modellen van inhoudsfragmenten
description: Gegevenstypen die worden gebruikt in Modellen van inhoudsfragment kunnen worden aangepast.
seo-description: Gegevenstypen die worden gebruikt in Modellen van inhoudsfragment kunnen worden aangepast.
page-status-flag: de-activated
uuid: d8215dbf-2dbe-43cb-a5c1-dc1cb412a204
contentOwner: aheimoz
discoiquuid: a8b8155c-852c-4d16-b59b-7e19527c2bd4
noindex: true
translation-type: tm+mt
source-git-commit: 3bdff366a0d455b405c1f9de371ced98d25ae2e2
workflow-type: tm+mt
source-wordcount: '1642'
ht-degree: 0%

---


# NIET PUBLICEREN, MAAR NIET DELETE aanpassen van gegevenstypen voor modellen van inhoudsfragmenten{#do-not-publish-but-do-not-delete-customizing-data-types-for-content-fragment-models}

[Inhoudsfragmenten](/help/assets/content-fragments.md) zijn gebaseerd op [inhoudsfragmentmodellen](/help/assets/content-fragments-models.md). Deze modellen worden opgebouwd van [elementen](/help/assets/content-fragments.md#constituent-parts-of-a-content-fragment) van verschillende gegevenstypen.

Verschillende gegevenstypen zijn offline beschikbaar, zoals tekst op één regel, RTF-tekst op meerdere regels, numerieke velden, Booleaanse kiezers, opties voor vervolgkeuzemenu, datum en tijd en andere. AEM gebruikers kunnen gegevenstypen selecteren op basis van de redactionele intentie van het (de) overeenkomstige fragment(en). Op deze manier kunt u eenvoudig met tekstmodellen werken in complexe modellen met verschillende soorten inhoud en de bijbehorende ervaring bij het ontwerpen van fragmenten.

Gegevenstypen worden gedefinieerd door een [combinatie van knoopeigenschappen](#properties) die op [specifieke locaties in de opslagplaats](#locations-in-the-repository)worden gehouden. U kunt ook uw eigen [gegevenstypen](#creating-your-data-type) en [fieldProperties](#creating-your-own-fieldproperties-property)maken.

<!-- Please uncomment when files are used>
>[!NOTE]
>
>See also [Customizing Content Fragment Models](/help/sites-developing/customizing-content-fragment-models.md).
-->

## Locaties in de opslagplaats {#locations-in-the-repository}

Alle out-of-box datatypes worden gedeclareerd onder:

`/libs/settings`

U kunt nieuwe gegevenstypen toevoegen door de nodestructuur als volgt te bedekken `/apps`:

`/apps/settings/dam/cfm/models/formbuilderconfig/datatypes/items`

>[!CAUTION]
>
>U mag niets in het `/libs` pad wijzigen.
>
>Om het even wat er kan veranderen bij de volgende verbetering, of installatie van de dienst of los verpakking op.

## Eigenschappen {#properties}

Node-eigenschappen worden gebruikt om de gegevenstypen te definiëren:

* [Eigenschappen van gegevenstypen](#data-type-properties)
* en binnen die [fieldProperties](#fieldproperties)

### Eigenschappen van gegevenstype {#data-type-properties}

Alle gegevenstypen worden in een nodestructuur vertegenwoordigd zoals onder:

`/libs/settings/dam/cfm/models/formbuilderconfig/datatypes/items`

Elk knooppunt onder `/items` heeft eigenschappen die definiëren hoe dat gegevenstype moet worden vertegenwoordigd in de modeleditor.

Alle volgende eigenschappen moeten aanwezig zijn opdat het gegevenstype in de modelredacteur aanwezig is:

* `fieldIcon`

   [Het pictogram](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/coral-ui/coralui3/Coral.Icon.html#availableicons) CoralUI om het gegevenstype in modelredacteur UI te vertegenwoordigen.

* ` [fieldProperties](#fieldproperties)`

   Een array die de configuratie-eigenschappen voor elk gegevenstype vertegenwoordigt.

* `fieldResourceType`

   Het Sling-brontype dat wordt gebruikt om het gegevenstype in een inhoudsfragment te renderen. Voor gegevenstypen die op verschillende manieren kunnen worden gerenderd (bijvoorbeeld als eenvoudige tekstinvoer en/of tekstinvoer met meerdere regels), moet deze eigenschap worden gemaakt als een array met alle typen bronnen. Het `renderasfield` bezit zal automatisch worden toegevoegd `fieldProperties` om de gebruiker te laten het middeltype kiezen zij aan het model moeten toevoegen,

* `fieldPropResourceType`

   Het Sling middeltype dat wordt gebruikt om het standaardbezit voor het gegevenstype terug te geven.

   Bijvoorbeeld voor het gegevenstype:

   * Tekst van één regel, `fieldPropResourceType` zou een `textfield` component zijn
   * Booleaans, het `fieldPropResourceType` zou een `checkbox` component zijn

* `fieldViewResourceType`

   Het Sling-brontype dat wordt gebruikt om het gegevenstype in de voorvertoning te renderen bij het samenstellen van het model. Wanneer de gebruiker het gegevenstype aan de linkerkant van de modelredacteur sleept, vertegenwoordigt het `fieldViewResourceType` bezit de component die daar wordt teruggegeven. Dit wordt gebruikt voor gevallen waar u niet de volledige component wilt teruggeven, maar slechts een substituut willen teruggeven die de overhead aan de modelredacteur minimaliseert.

* `fieldTitle`

   Eigenschap die de titel van dit gegevenstype definieert. Bijvoorbeeld **Enkele-regeltekst** voor een `textfield` component, **Meerdere-regeltekst** voor een component met meerdere velden.

* `valueType`

   Dit is het type van waarde dat het gegevenstype terugkeert wanneer het intern wordt opgeslagen. Zie [Toewijzingen](#mappings).

* `renderType`

   Dit is een interne representatie van het gegevenstype. Het verbindt `valueType` met een component UI. Zie [Toewijzingen](#mappings).

* `listOrder`

   Elk gegevenstype heeft een waarde nodig die de volgorde in de lijst aangeeft. Dit wordt gebruikt om de correcte orde van de diverse gebieden (toegevoegd/bewogen door belemmering en daling) te verzekeren wanneer het bewaren van de modelredacteur. Deze waarde moet een geheel getal zijn en het wordt aanbevolen het getal op oplopende, geordende wijze toe te wijzen. Wanneer u een nieuw gegevenstype maakt, kunt u het beste de waarde toewijzen op basis van het laatste gegevenstype in de lijst (de hoogste waarde van de `listOrder` waarde in de gegevenstypen).

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
>Sommige typen (bijvoorbeeld `string`, `long`onder andere) kunnen worden gemultiwaardeerd. In dit geval wordt de component die wordt gebruikt voor renderen en bewerken doorgaans omwikkeld door een component met meerdere velden ( `granite/ui/components/coral/foundation/form/multifield`). De uitzondering hierop zijn codes, waarbij de bewerkingscomponent verantwoordelijk is voor de juiste rendering.

### fieldProperties {#fieldproperties}

De configuratie-eigenschappen voor elk gegevenstype. Waarden voor `fieldProperties`:

* `base`

   Dit is de basis voor alle `fieldProperties` componenten. De definitie staat onder `/libs/dam/cfm/models/editor/components/datatypeproperties/base`.

   De variabele bevat de variabele `fieldRoot`, die vervolgens `fieldProperties` kan worden gebruikt wanneer invoer wordt gemaakt om het juiste pad op te halen.

   Voorbeeld: Als u het juiste pad voor een **veldlabel** wilt ophalen, hebt u de sleutel nodig om de component te identificeren waartoe dit behoort, moet de invoer voor dit veld `fieldRoot` + `<*fieldLabel*>`

* `checkboxfields`

   Deze component voegt het standaardselectievakje voor het `Boolean` gegevenstype toe, evenals de parameters Sling `checked@Delete` en `checked@TypeHint`.

* `datepickerfields`

   Component die de verborgen inputs toevoegt die nodig zijn om de component van de datumkiezer te laten functioneren. Omvat het creëren van de eigenschappen `defaultDateField`, `displayedFormat`, `emptyText`, `valueFormat`, `minDate` en `maxDate`.

* `datetimepickerfields`

   Hiermee voegt u een selectieveld voor het `Date&Time` gegevenstype toe om onderscheid te maken tussen `Date` en `Date&Time` opties.

* `datevaluefield`

   Hiermee wordt een datepicker toegevoegd aan de eigenschappen, zodat een gebruiker een standaardwaarde voor het `Date&Time` gegevenstype kan selecteren.

* `descriptionfield`

   Deze component voegt een tekstveld met meerdere regels toe dat de beschrijving vertegenwoordigt van de momenteel geselecteerde component in de editor met meerdere regels. Deze wordt automatisch toegevoegd door de renderer van de modeleditor aan het einde van elke eigenschap van het gegevenstype.

* `labelfield`

   Component die een `textfield` invoer toevoegt die het gebiedslabel voor een gegevenstype toevoegt dat gebiedslabels kan hebben.

* `maptopropertyfield`

   Deze component voegt het `Name` veld in de eigenschappen toe en geeft een id aan de geselecteerde component van een gegevenstype. Het zou in alle gegevenstypes aanwezig moeten zijn.

* `maxlengthfield`

   Het wordt gebruikt om het `maxLength` bezit voor gebruik met gegevenstypes toe te voegen die dit bezit goedkeuren. Bijvoorbeeld met tekst **van**&#x200B;één regel, **Aantal**, enz.

* `multieditorfield`

   Hiermee voegt u alle verborgen velden toe die de editor met meerdere regels nodig heeft om te werken. Dit wordt aangegeven met het gegevenstype Tekst **met** meerdere regels.

* `mvfields`

   Component die alle verborgen velden toevoegt die nodig zijn voor een component met meerdere velden. Bijvoorbeeld voor de tweede optie van een gegevenstype **Enkele regel** . Dit moet worden toegevoegd voor elke component die wordt gerenderd als een multifield.

* `numbertypefield`

   Selecteer een optie voor het gegevenstype **Number** waarmee u tussen **Geheel** of **Breedte** voor het gegevenstype **Number** selecteert.

* `numbervaluefield`

   Een `numberfield` standaardwaardeselector voor het **Aantal** voegt dit de optiesinput voor het gegevenstype van de `type.options` Opsomming **** toe, die wordt gebruikt om de waarden voor de uitgezochte vakcomponent te bepalen.

* `placeholderfield`

   Dit is een tekstveld dat fungeert als invoer voor de `emptyText` eigenschap van een component. Dit zou door alle gegevenstypes moeten worden gebruikt die placeholder (dat niet zeer ingewikkeld is; bijv. tekst **met**&#x200B;één regel, **nummer**, enz.).

* `renderasfield`

   Dit is de component die automatisch wordt teruggegeven wanneer verscheidene in het bezit van de knoop van het gegevenstype aanwezig `fieldResourceTypes` zijn.

* `requiredfield`

   Dit is een selectievakje dat de `required` eigenschap voor een component vertegenwoordigt. Omdat de meeste componenten het `required` gebied goedkeuren, kan dit gebied voor de meeste gegevenstypes worden gebruikt.

* `tagsfields`

   Componenten die de vereiste invoer toevoegen voor een `tagfield` component die moet worden gerenderd. Deze worden gebruikt door het gegevenstype **Codes** .

* `tagsroot`

   Een padkiezer die door het gegevenstype **Tags** wordt gebruikt om het hoofdpad voor de `tagsfield` component in te stellen.

* `textfield`

   Wordt gebruikt door het `Boolean` gegevenstype om het veldlabel in te stellen van het selectievakje dat door dit gegevenstype wordt gedefinieerd.

* `textvaluefield`

   De standaardwaarde voor het gegevenstype **Single Line Text** .

## Uw gegevenstype maken {#creating-your-data-type}

Als u uw eigen gegevenstype wilt maken, moet u:

* [De knooppuntstructuur maken](#creating-the-node-structure)
* [Definieer de eigenschappen voor uw gegevenstype](#defining-the-properties-for-your-data-type)

Vervolgens kunt u het gegevenstype [](#using-your-data-type)gebruiken.

U kunt ook uw eigen [ontwerp maken `fieldProperties`](#creating-your-own-fieldproperties-property).

### De knooppuntstructuur maken {#creating-the-node-structure}

De knoopstructuur moet onder worden gecreeerd `/apps` om de gegevenstypes te bedekken. Als dit nog niet het geval is, moet u het volgende maken:

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

1. Onder `/items` kunt u nieuwe knooppunten toevoegen die uw nieuwe gegevenstype(en) vertegenwoordigen:

   * Type knooppunt: `nt:unstructured`
   * &quot;Eigenschappen: zie de Eigenschappen [bepalen voor uw Type van Gegevens](#defining-the-properties-for-your-data-type)

### Eigenschappen definiëren voor uw gegevenstype {#defining-the-properties-for-your-data-type}

1. Bepaal waarden voor de volgende [eigenschappen](#data-type-properties) van het gegevenstype die voor uw gegevenstype worden vereist:

   * `fieldResourceType`
   * `fieldPropResourceType`
   * `fieldViewResourceType`

   Deze bepalen hoe de componenten voor uw gegevenstype zullen worden teruggegeven. Zij kunnen elke component zijn; inclusief uw eigen aangepaste componenten (hiervoor is een overeenkomende set ` [fieldProperties](#fieldproperties)`nodig).

   Definieer deze eigenschappen met de juiste waarden op het knooppunt voor het gegevenstype.

1. Bepaal de ` [fieldProperties](#fieldproperties)` te gebruiken waarde. Dit is afhankelijk van de kenmerken of eigenschappen die u `fieldResourceType` nodig hebt.

   Een `granite/ui/components/coral/foundation/form/textfield`label moet bijvoorbeeld een **labelnaam**, een **maximumlengte**, een **plaatsaanduidingstekst** en een eigenschap **Standaardwaarde** hebben.

   U kunt een optie kiezen in het vak [fieldProperties](#fieldproperties)of u kunt uw eigen eigenschappen [](#creating-your-own-fieldproperties-property)maken.

   Definieer deze eigenschappen met de juiste waarden op het knooppunt voor het gegevenstype.

1. Bepaal waarden voor de volgende [eigenschappen](#data-type-properties)van het gegevenstype:

   * `fieldIcon`
   * `fieldTitle`
   * `renderType`
   * `valueType`
   * `listOrder`

   Definieer deze eigenschappen met de juiste waarden op het knooppunt voor het gegevenstype.

### Het gegevenstype gebruiken {#using-your-data-type}

Nadat u deze knoopstructuur, met alle toegepaste eigenschappen opslaat, kunt u om het even welk model met de modelredacteur openen en, uw nieuw gegevenstype zien en gebruiken.

## Uw eigen eigenschap fieldProperties maken {#creating-your-own-fieldproperties-property}

U kunt uit uit-van-de-doos [fieldProperties](#fieldproperties)kiezen, of uw creëren:

1. Een component maken onder:

   `/apps/dam/cfm/models/editor/components/datatypeproperties/`

   Als het pad niet bestaat, kunt u het maken met behulp van `nt:folder` knooppunten.

   1. Om toegang tot de variabelen te hebben, zou deze component zich moeten uitbreiden:

      `/libs/dam/cfm/models/editor/components/datatypeproperties/base`* *

   1. De component moet kunnen worden opgenomen via:

      `sling:include`

   1. Deze component moet een veld renderen (als een gebruiker gegevens moet invoeren) of een verborgen invoer met de eigenschappen die nodig zijn voor het gegevenstype. Bijvoorbeeld, vereist een multifield component een kindknoop met het type van gebied het zou moeten dupliceren, daarom zou er een input moeten zijn die (door de mechanica van de POST van de sling) een kindknoop van een specifiek type kan tot stand brengen.

1. De basisnaam van deze component moet worden toegevoegd aan `fieldProperties`.
1. Herhaal dit voor alle eigenschappen die u nodig hebt.

