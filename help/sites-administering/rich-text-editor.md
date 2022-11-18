---
title: De Rich Text Editor configureren
description: Leer om de AEM Rich Text Editor te vormen.
contentOwner: AG
exl-id: 2d5e9ada-1567-43dc-ab19-6891e20e1d0b
source-git-commit: 0f4f8c2640629f751337e8611a2c8f32f21bcb6d
workflow-type: tm+mt
source-wordcount: '2659'
ht-degree: 0%

---

# De Rich Text Editor configureren {#configure-the-rich-text-editor}

De Rich Text Editor (RTE) biedt auteurs een groot aantal functies voor het bewerken van hun tekstinhoud. Pictogrammen, selectiekaders, werkbalk en menu&#39;s zijn beschikbaar voor een WYSIWYG-ervaring bij het bewerken van tekst.

Om te weten hoe te om eigenschappen RTE voor creatie te gebruiken, zie [Rich Text Editor gebruiken voor ontwerpen](/help/sites-authoring/rich-text-editor.md). RTE kan worden gevormd om, de eigenschappen toe te laten onbruikbaar te maken en uit te breiden beschikbaar in de auteurscomponenten. Het volgende werkschema illustreert een geadviseerde orde om de de configuratietaken van RTE in Experience Manager te voltooien.

![Normale workflow voor het configureren van Rich Text Editor](assets/rte_workflow_v1.png)

*Afbeelding: Normale workflow voor het configureren van Rich Text Editor*

## Interface met aanraakbediening en klassieke gebruikersinterface {#understand-touch-enabled-ui-and-classic-ui}

De interface met aanraakbediening is de standaardinterface voor AEM. Adobe introduceerde Touch UI met [responsief ontwerp](/help/sites-authoring/responsive-layout.md) voor de ontwerpomgeving, in versie 5.6. De aanraakinterface is ontworpen voor touch- en desktopapparaten. De interface verschilt aanzienlijk van de oorspronkelijke klassieke interface.

![De rijke toolbar van de Redacteur van de Tekst in Touch-Toegelaten UI](assets/chlimage_1-404.png)

*Afbeelding: De rijke toolbar van de Redacteur van de Tekst in Touch-Toegelaten UI*

![De Rich Text Editor-werkbalk in de klassieke gebruikersinterface](assets/rtedefault.png)

*Afbeelding: De Rich Text Editor-werkbalk in de klassieke gebruikersinterface*

>[!MORELIKETHIS]
>
>* [UI-aanbevelingen](/help/sites-deploying/ui-recommendations.md)
>* Informatie over het vervangen van de klassieke gebruikersinterface vindt u in [AEM 6.4 Opmerkingen bij de release](/help/release-notes/deprecated-removed-features.md)
>* Voor verschil tussen UIs, zie [Aanraakinterface en klassieke gebruikersinterface](https://aemcq5pedia.wordpress.com/2018/01/05/touch-enabled-ui-aem6-3/)
>* Als u de interface met aanraakbediening gedetailleerd wilt begrijpen, raadpleegt u [Concepten van AEM Touch UI](/help/sites-developing/touch-ui-concepts.md)


## Verschillende bewerkingsmodi {#editingmodes}

Auteurs kunnen tekstinhoud in AEM maken en bewerken met de verschillende modi van componenten. De toolbaropties voor het ontwerpen en het formatteren van inhoud en de gebruikerservaring van rte-toegelaten componenten op verschillende het uitgeven wijze variëren gebaseerd op configuraties RTE.

| Bewerkmodus | Bewerkingsgebied | Aanbevolen functies om te worden ingeschakeld | Aanraakinterface | Klassieke interface |
|--- |--- |--- |--- |--- |
| Inline | Op locatie bewerken voor snelle, kleine bewerkingen; Opmaken zonder dialoogvenster te openen | Minimale RTE-functies | J | J |
| RTE volledig scherm | Behandelt gehele pagina | Alle vereiste eigenschappen van RTE | J | N |
| Dialoog | Dialoogvenster boven op de pagina-inhoud, maar heeft geen betrekking op de gehele pagina | Alle vereiste eigenschappen van RTE in Klassieke UI; Functies op oordeelkundige wijze inschakelen in Touch UI | J | J |
| Dialoogvenster volledig scherm | Hetzelfde als de modus Volledig scherm; bevat gebieden van de dialoog naast RTE | Alle vereiste eigenschappen van RTE | J | N |

>[!NOTE]
>
>De functie voor het bewerken van bronnen is niet beschikbaar in de inline bewerkingsmodus van de interface met aanraakbediening. U kunt afbeeldingen niet slepen in de modus Volledig scherm. Alle andere functies werken in alle modi.

### Inline bewerken {#inline-editing}

Als u de inhoud opent (met een langzaam dubbeltikken/klikken), kan deze op de pagina worden bewerkt. Er wordt een compacte werkbalk met basisopties weergegeven.

![Inline bewerken met de standaardwerkbalk in Touch-gebruikersinterface](assets/chlimage_1-405.png)

*Afbeelding: Inline bewerken met de standaardwerkbalk in Touch-gebruikersinterface*

In de klassieke gebruikersinterface kunt u met een trage dubbelklik op de component inline bewerken en met een oranje omtrek de inhoud markeren. Als de Inhoudszoeker is geopend, wordt boven in het venster een werkbalk weergegeven met de beschikbare RTE-opmaakopties. Als de Inhoudszoeker niet is geopend, worden de opmaakopties niet weergegeven en kunt u alleen standaardtekstbewerkingen uitvoeren.

### Volledig scherm bewerken {#full-screen-editing}

AEM componenten kunnen worden geopend in de weergave Volledig scherm, waarin de pagina-inhoud wordt verborgen en het beschikbare scherm wordt ingenomen. U kunt overwegen om een gedetailleerde versie van de inlinebewerking op volledig scherm te bewerken, aangezien deze de meeste bewerkingsopties biedt. U kunt het openen door op ![rte_fullscreen](assets/rte_fullscreen.png)op de compacte werkbalk als u de inline bewerkingsmodus gebruikt.

De modus Volledig scherm van het dialoogvenster bevat een gedetailleerde RTE-werkbalk en de opties en componenten die beschikbaar zijn in de dialoogmodus. Het is alleen van toepassing voor een dialoog die naast andere componenten RTE bevat.

![De gedetailleerde RTE-werkbalk wanneer u bewerkingen uitvoert in de modus Volledig scherm in de gebruikersinterface met aanraakbediening](assets/chlimage_1-406.png)

*Afbeelding: De gedetailleerde RTE-werkbalk wanneer u bewerkingen uitvoert in de modus Volledig scherm in de gebruikersinterface met aanraakbediening*

### Dialoogbewerkingen {#dialog-editing}

Wanneer dubbelgeklikt wordt op een component in de klassieke gebruikersinterface, wordt een dialoogvenster geopend voor het bewerken van de inhoud. Het dialoogvenster wordt boven op de bestaande pagina geopend. In sommige specifieke scenario&#39;s, opent de dialoog als pop-up venster. Wanneer een tekstcomponent bijvoorbeeld deel uitmaakt van een kolom in een paginalay-out met meerdere kolommen en het gebied dat beschikbaar is voor het dialoogvenster kleiner is.

![Dialoogbewerkingsmodus in interface met aanraakbediening](assets/dialog_editing_modetouchui.png)

*Afbeelding: Dialoogbewerkingsmodus in interface met aanraakbediening*

![Dialoogvenster in klassieke gebruikersinterface met gedetailleerde werkbalk voor bewerken](assets/chlimage_1-407.png)

*Afbeelding: Dialoogvenster in klassieke gebruikersinterface met gedetailleerde werkbalk voor bewerken*

## Informatie over RTE-plug-ins en de bijbehorende functies {#aboutplugins}

De functionaliteit wordt beschikbaar gesteld via een reeks plug-ins, elk met:

* A `features` eigenschap:

   * Hiermee wordt de basisfunctionaliteit voor die plug-in geactiveerd of gedeactiveerd.
   * Dat kan worden gevormd gebruikend een gestandaardiseerde procedure.

* Indien van toepassing, meer eigenschappen en opties die gespecialiseerde configuratie vereisen.

De basisfuncties van de RTE worden geactiveerd of gedeactiveerd door de waarde van de `features` eigenschap op een knooppunt dat specifiek is voor de juiste insteekmodule.

In de volgende tabel worden de huidige plug-ins weergegeven:

* Plug-in-id&#39;s met een koppeling naar de API-documentatie. ID wordt gebruikt als knooppuntnaam wanneer [een plug-in activeren](/help/sites-administering/configure-rich-text-editor-plug-ins.md#activateplugin).
* Toegestane waarden voor de `features` eigenschap.
* Een beschrijving van de functionaliteit die door de plug-in wordt geboden.

| Plug-in-id | functies | Beschrijving |
|--- |--- |--- |
| bewerken | cut copy paste-default paste-plaintext paste-wordhtml | [De drie plakmodi knippen, kopiëren en plakken](/help/sites-administering/configure-rich-text-editor-plug-ins.md#text-styles). |
| [findreplace](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/widgets-api/index.html?class=CQ.form.rte.plugins.FindReplacePlugin) | zoeken, vervangen | Zoeken en vervangen. |
| [format](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/widgets-api/index.html?class=CQ.form.rte.plugins.FormatPlugin) | vet cursief onderstrepen | [Basistekstopmaak](/help/sites-administering/configure-rich-text-editor-plug-ins.md#text-styles). |
| [afbeelding](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/widgets-api/index.html?class=CQ.form.rte.plugins.ImagePlugin) | afbeelding | Basisondersteuning voor afbeeldingen (slepen vanuit de inhoud of de Inhoudszoeker). Afhankelijk van de browser heeft de ondersteuning verschillende gedragingen voor auteurs |
| [toetsen](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/widgets-api/index.html?class=CQ.form.rte.plugins.KeyPlugin) |  | Zie voor het definiëren van deze waarde [tabgrootte](/help/sites-administering/configure-rich-text-editor-plug-ins.md#tab-size). |
| [justify](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/widgets-api/index.html?class=CQ.form.rte.plugins.JustifyPlugin) | uitvullen, links uitvullen, rechts uitvullen | Alinea-uitlijning. |
| [koppelingen](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/widgets-api/index.html?class=CQ.form.rte.plugins.LinkPlugin) | ontkoppelingsanker wijzigen | [Hyperlinks en ankers](/help/sites-administering/configure-rich-text-editor-plug-ins.md#link-styles). |
| [lijsten](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/widgets-api/index.html?class=CQ.form.rte.plugins.ListPlugin) | geordende ongeordende inspringing uitspringen | Deze insteekmodule bestuurt beide [inspringing en lijsten](/help/sites-administering/configure-rich-text-editor-plug-ins.md#indent-margin); inclusief geneste lijsten. |
| [misverstanden](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/widgets-api/index.html?class=CQ.form.rte.plugins.MiscToolsPlugin) | specialchars-bronbewerking | Met diverse gereedschappen kunnen auteurs toegang krijgen tot [speciale tekens](/help/sites-administering/configure-rich-text-editor-plug-ins.md#special-char) of bewerk de HTML-bron. U kunt ook een geheel toevoegen [bereik van speciale tekens](/help/sites-administering/configure-rich-text-editor-plug-ins.md#define-range-char) als u uw eigen lijst wilt bepalen. |
| Paraformat | paraformat | De standaardindelingen voor alinea&#39;s zijn Alinea, Kop 1, Kop 2 en Kop 3 (`<p>`, `<h1>`, `<h2>`, en `<h3>`). U kunt [meer alineaopmaak toevoegen](/help/sites-administering/configure-rich-text-editor-plug-ins.md#para-formats) of breid de lijst uit. |
| spellingcontrole | checktext | [Spellingcontrole taalbewust](/help/sites-administering/configure-rich-text-editor-plug-ins.md#add-dict). |
| stijlen | stijlen | Ondersteuning voor opmaak met behulp van een CSS-klasse. [Nieuwe tekststijlen toevoegen](/help/sites-administering/configure-rich-text-editor-plug-ins.md#text-styles) als u uw eigen reeks stijlen wilt toevoegen (of uitbreiden) voor gebruik met tekst. |
| subsuperscript | subscript, superscript | Extensies voor de basisindelingen, subscript en superscript toevoegen. |
| table | verwijderbaar inzetbare verwijderbare insteekmodule removerow insert column removecolumn cellprops mergecells splitcell selectrow selected columns | Zie [tabelstijlen configureren](/help/sites-administering/configure-rich-text-editor-plug-ins.md#table-styles), als u uw eigen stijlen voor of volledige lijsten of individuele cellen wilt toevoegen. |
| ongedaan maken | ongedaan maken, opnieuw uitvoeren | Grootte historie van [ongedaan maken en opnieuw uitvoeren](/help/sites-administering/configure-rich-text-editor-plug-ins.md#undo-history) bewerkingen. |

>[!NOTE]
>
>De plug-in Volledig scherm wordt niet ondersteund in de dialoogmodus. Gebruik van de `dialogFullScreen` instellen om de werkbalk voor de modus Volledig scherm te configureren.

## Begrijp de configuratiewegen en plaatsen {#understand-the-configuration-paths-and-locations}

De [wijze van het uitgeven van RTE (en UI)](#editingmodes) die u voor uw auteurs verstrekt bepaalt de plaats voor de configuratiedetails wanneer u [het activeren van de stop-ins van RTE](/help/sites-administering/configure-rich-text-editor-plug-ins.md#activateplugin):

| Bewerkmodus | Locatie voor aanraakinterface | Locatie voor klassieke gebruikersinterface |
|---|---|---|
| Inline | `cq:editConfig/cq:inplaceEditing` | `cq:editConfig/cq:inplaceEditing` |
| Volledig scherm | `cq:editConfig/cq:inplaceEditing` | Niet van toepassing |
| Dialoog | `cq:dialog` | `dialog` |
| Dialoogvenster Volledig scherm | `cq:dialog` | Niet van toepassing |

>[!NOTE]
>
>Geef het knooppunt onder geen naam `cq:inplaceEditing` als `config`. Aan `cq:inplaceEditing` node, definieert u de volgende eigenschappen:
>
>* **Naam**: `configPath`
>* **Type**: `String`
>* **Waarde**: pad van het knooppunt met de feitelijke configuratie
>
>Noem niet de knoop van de configuratie RTE als `config`. Anders, worden de configuraties RTE van kracht voor slechts de beheerders en niet voor de gebruikers in de groep `content-author`.

Configureer de volgende eigenschappen die alleen van toepassing zijn in de bewerkingsmodus Dialoogvenster in Touch UI:

* `useFixedInlineToolbar`: Stel deze Booleaanse eigenschap in die op de RTE-node is gedefinieerd (één met sling:resourceType= `cq/gui/components/authoring/dialog/richtext`) naar `True`om de RTE-werkbalk vast te maken in plaats van zwevend.

   Wanneer deze eigenschap true is, wordt het bewerken van Richtingstekst standaard gestart op de gebeurtenis &quot;foundation-contentloaded&quot;.

   Als u dit wilt voorkomen, stelt u de eigenschap in `customStart` tot `True`en activeer de gebeurtenis &#39;rte-start&#39; om RTE-bewerking te starten. Wanneer deze eigenschap &#39;true&#39; is, werkt het standaardgedrag, het starten bij klikken.

* `customStart`: Stel deze Booleaanse eigenschap die is gedefinieerd op het RTE-knooppunt in op `True`, om te controleren wanneer om RTE te beginnen door de gebeurtenis in werking te stellen `rte-start`.

* `rte-start`: Deze gebeurtenis activeren op het tabblad `contenteditable-div` van RTE, wanneer beginnen RTE uit te geven. Dit werkt alleen als `customStart` is ingesteld op true.

Wanneer RTE wordt gebruikt in de aanraking-toegelaten dialoog, plaatsend het bezit `useFixedInlineToolbar` naar waar is verplicht om problemen te voorkomen .

## Op plaats bewerken aanpassen {#customizing-in-place-editing}

U kunt definiëren op welke HTML-kiezer de teksteditor begint door de volgende eigenschappen te configureren:

* **`editElementQuery`** - Gedefinieerd op `cq:InplaceEditingConfig`, wordt deze eigenschap gebruikt om een kiezer op te geven van het element HTML waarop de inline-bewerking voor de tekstcomponent wordt gestart. Als u deze optie niet opgeeft, wordt het inline bewerken direct gestart op de HTML van de tekstcomponent.
* **`textPropertyName`** - Gedefinieerd op `cq:InplaceEditingConfig`, wordt deze eigenschap gebruikt om de naam op te geven van de eigenschap die wordt opgeslagen op het inhoudsknooppunt waar de HTML-waarde van de tekstcomponent na inline-bewerking wordt voortgezet.

De overeenkomende eigenschap voor de dialoogmodus is `name`.

## RTE-functies inschakelen door plug-ins te activeren {#enable-rte-functionalities-by-activating-plug-ins}

De functionaliteit van RTE wordt beschikbaar gemaakt via een reeks stop-ins, elk met eigenschappen bezit. U kunt de eigenschap features configureren om de verschillende functies van elke insteekmodule in of uit te schakelen.

Voor gedetailleerde configuraties van de stop-ins van RTE, zie [hoe te om de stop-ins van RTE te activeren en te vormen](/help/sites-administering/configure-rich-text-editor-plug-ins.md).

Download deze steekproefconfiguratie om te begrijpen hoe te om RTE te vormen. In dit pakket zijn alle functies ingeschakeld.

[Bestand ophalen](/help/assets/assets/rte-sample-all-features-enabled-10.zip)

>[!NOTE]
>
>De [Tekstcomponent Core Components](https://helpx.adobe.com/experience-manager/core-components/using/text.html) staat malplaatjeredacteurs toe om vele stop-ins van RTE in het gebruikersinterface als inhoudsbeleid te vormen, die de behoefte aan technische configuratie elimineren. Het beleid van de inhoud kan met RTE gebruikersinterfaceconfiguraties werken zoals beschreven. Zie voor meer informatie de [De montages van het gebruikersinterface van RTE en inhoudsbeleid](/help/sites-administering/rich-text-editor.md#rtecontentpolicies), [Paginasjablonen maken](/help/sites-authoring/templates.md)en de [Documentatie voor ontwikkelaars van kerncomponenten](https://helpx.adobe.com/experience-manager/core-components/using/developing.html).

>[!NOTE]
>
>Ter referentie kunt u de standaardtekstcomponenten (geleverd als onderdeel van een standaardinstallatie) vinden op:
>
>* `/libs/wcm/foundation/components/text`
>* `/libs/foundation/components/text`
>
>Als u uw eigen tekstcomponent wilt maken, kopieert u de bovenstaande component in plaats van deze componenten te bewerken.

## RTE-werkbalk configureren {#dialogfullscreen}

AEM staat u toe om UI voor de Redacteur RichText voor de verschillende het uitgeven wijzen verschillend te vormen. De standaardinstellingen worden hieronder gegeven. U kunt deze standaardinstellingen op basis van uw vereisten overschrijven.

Voor de beste ontwerpervaring:

* Schakel in een zwevend dialoogvenster alleen de plug-ins in die geen pop-up hebben, omdat het zwevende dialoogvenster een kleiner formaat heeft.
* Schakel in het dialoogvenster Volledig scherm alle vereiste plug-ins in, zelfs de plug-ins met grotere pop-ups, zoals de `Paste` insteekmodule. Gebruik de `dialogFullScreen` hieronder beschreven configuratie.

```java
<uiSettings jcr:primaryType="nt:unstructured">
  <cui jcr:primaryType="nt:unstructured">
    <inline
      jcr:primaryType="nt:unstructured"
      toolbar="[format#bold,format#italic,format#underline,#justify,#lists,links#modifylink,links#unlink,#paraformat]">
      <popovers jcr:primaryType="nt:unstructured">
        <justify
          jcr:primaryType="nt:unstructured"
          items="[justify#justifyleft,justify#justifycenter,justify#justifyright]"
          ref="justify"/>
        <lists
          jcr:primaryType="nt:unstructured"
          items="[lists#unordered,lists#ordered,lists#outdent,lists#indent]"
          ref="lists"/>
        <paraformat
          jcr:primaryType="nt:unstructured"
          items="paraformat:getFormats:paraformat-pulldown"
          ref="paraformat"/>
      </popovers>
    </inline>
    <dialogFullScreen
      jcr:primaryType="nt:unstructured"
      toolbar="[format#bold,format#italic,format#underline,justify#justifyleft,justify#justifycenter,justify#justifyright,lists#unordered,lists#ordered,lists#outdent,lists#indent,links#modifylink,links#unlink,table#createoredit,#paraformat,image#imageProps]">
      <popovers jcr:primaryType="nt:unstructured">
        <paraformat
          jcr:primaryType="nt:unstructured"
          items="paraformat:getFormats:paraformat-pulldown"
          ref="paraformat"/>
      </popovers>
    </dialogFullScreen>
    <tableEditOptions
      jcr:primaryType="nt:unstructured"
      toolbar="[table#insertcolumn-before,table#insertcolumn-after,table#removecolumn,-,table#insertrow-before,table#insertrow-after,table#removerow,-,table#mergecells-right,table#mergecells-down,table#mergecells,table#splitcell-horizontal,table#splitcell-vertical,-,table#selectrow,table#selectcolumn,-,table#ensureparagraph,-,table#modifytableandcell,table#removetable,-,undo#undo,undo#redo,-,table#exitTableEditing,-]">
    </tableEditOptions>
  </cui>
</uiSettings>
```

Er worden verschillende UI-instellingen gebruikt voor de inlinemodus en de modus Volledig scherm. De eigenschap toolbar wordt gebruikt om de knoppen van de werkbalk op te geven. Als de knop zelf bijvoorbeeld een functie is (bijvoorbeeld `Bold`), wordt het opgegeven als `PluginName#FeatureName` (bijvoorbeeld `links#modifylink`). Als de knop een pop-up is (met enkele functies van een plug-in), wordt deze opgegeven als `#PluginName` (bijvoorbeeld `#format`). Scheidingstekens ( | ) tussen een groep knoppen kan worden opgegeven met &#39;-&#39;.

Het pop-upknooppunt onder de modus Inline of Volledig scherm bevat een lijst met de popovers die worden gebruikt. Elke onderliggende node onder de `popovers` node wordt benoemd naar de plug-in (bijvoorbeeld `format`). Het heeft een eigenschap `items` met een lijst met functies van de plug-in (bijvoorbeeld `format#bold`).

## RTE-gebruikersinterface-instellingen en inhoudsbeleid {#rtecontentpolicies}

De beheerders kunnen de opties controleren RTE gebruikend inhoudsbeleid, zeggen in plaats van de configuratie zoals hierboven beschreven. In het inhoudsbeleid worden de ontwerpeigenschappen van een component gedefinieerd wanneer deze als onderdeel van een component worden gebruikt [bewerkbare sjabloon](../sites-authoring/templates.md). Als bijvoorbeeld een tekstcomponent die de RTE gebruikt wordt gebruikt met een bewerkbare sjabloon, kan het inhoudsbeleid definiëren dat de optie Vet beschikbaar is en zijn enkele opties voor alineaopmaak beschikbaar. Het inhoudsbeleid is herbruikbaar en kan op meerdere sjablonen worden toegepast.

AEM 6.4 Service Pack 3 en daarna, de beschikbare opties in RTE stroom stroomafwaarts van de configuraties van het gebruikersinterface aan het inhoudsbeleid.

* De de configuratiemontages van de gebruikersinterface bepalen welke opties aan het inhoudsbeleid beschikbaar zijn.
* Als de gebruikersinterfaceconfiguratie van RTE verwijderde of geen punt toelaat, kan het inhoudsbeleid niet het vormen.
* Een auteur heeft toegang tot slechts dergelijke functionaliteit die door de gebruikersinterfaceconfiguraties en het inhoudsbeleid ter beschikking wordt gesteld.

Als voorbeeld kunt u de [Documentatie van de component Text Core](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/components/text.html#the-text-component-and-the-rich-text-editor).

## Toewijzing aanpassen tussen werkbalkpictogrammen en -opdrachten {#iconstoolbar}

U kunt de afbeelding aanpassen tussen de koraalpictogrammen die worden weergegeven op de RTE-werkbalk en de beschikbare opdrachten. U kunt geen andere pictogrammen gebruiken behalve Koraalpictogrammen.

1. Een knooppunt maken met de naam `icons` krachtens `uiSettings/cui`.

1. Maak knooppunten voor afzonderlijke pictogrammen eronder.
1. Geef voor elk van de afzonderlijke pictogramknooppunten een koraalpictogram en een opdracht op om aan het pictogram toe te wijzen.

Hieronder ziet u een voorbeeldfragment waarmee u de opdracht Vet maken toewijst aan het pictogram Koraal met de naam `textItalic`.

```java
<text jcr:primaryType="nt:unstructured" sling:resourceType="cq/gui/components/authoring/dialog/richtext" name="./text" useFixedInlineToolbar="{Boolean}true"> 
    <rtePlugins jcr:primaryType="nt:unstructured"> 
        <format jcr:primaryType="nt:unstructured" features="bold,italic"/> 
    </rtePlugins> 
    <uiSettings jcr:primaryType="nt:unstructured"> 
        <cui jcr:primaryType="nt:unstructured"> 
            <inline jcr:primaryType="nt:unstructured" 
                toolbar="[format#bold,format#italic,format#underline,links#modifylink,links#unlink]"> 
            </inline> 
            <icons jcr:primaryType="nt:unstructured"> 
                <bold jcr:primaryType="nt:unstructured" 
                    command="format#bold" 
                    icon="textItalic"/> 
            </icons> 
        </cui> 
    </uiSettings> 
</text>
```

## Overschakelen naar de KoralUI 2 Rich Text Editor {#switch-to-coralui-rich-text-editor}

Voor een pagina, kunt u of CoralUI 2 KTE clientlib of CoralUI 3 KTE clientlib omvatten. Standaard bevat de Rich Text Editor de CoralUI 3 RTE clientlib. Ga als volgt te werk om over te schakelen op CoralUI 2 RTE.

>[!NOTE]
>
>Adobe adviseert niet de omschakeling als beste praktijken. Schakel als laatste redmiddel over naar CoralUI 2 RTE. De stop-ins van de douane voor CoralUI 2 RTE werkt met CoralUI 3 RTE als stop-ins niet van internals RTE, zoals klassen afhangt. Als u aangepaste plug-ins voor CoralUI 3 RTE gebruikt, gebruikt u `rte.coralui3` bibliotheek.

1. Het knooppunt bedekken `/libs/cq/gui/components/authoring/editors/clientlibs/core` krachtens `/apps`en voer de volgende handelingen uit:

   * Vervangen `rte.coralui3` with `rte.coralui2` voor het gebiedsdeelbezit.
   * Vervangen `cq.authoring.editor.core.inlineediting.rte.coralui3` with `cq.authoring.editor.core.inlineediting.rte.coralui2` voor de eigenschap embed.
   * Vervangen `cq.authoring.rte.coralui3` with `cq.authoring.rte.coralui2` voor de eigenschap embed.

1. De knooppunten bedekken `/libs/cq/gui/components/authoring/dialog/richtext/clientlibs/rte/coralui3` en `/libs/cq/gui/components/authoring/dialog/richtext/clientlibs/rte/coralui2` krachtens `/apps`.

   Categorie verwijderen `cq.authoring.dialog` van `/apps/cq/gui/components/authoring/dialog/richtext/clientlibs/rte/coralui3` en voeg deze toe aan `/apps/cq/gui/components/authoring/dialog/richtext/clientlibs/rte/coralui2`.

1. Wijzig een andere afhankelijkheid die op de pagina wordt opgenomen vanuit `rte.coralui3` tot `rte.coralui2`. Bijvoorbeeld na het bedekken van het knooppunt `/libs/mcm/campaign/components/touch-ui/clientlibs/rte` krachtens `/apps`, wijzigt u de afhankelijkheid ervan `rte.coralui3` tot `rte.coralui2`.

1. Het knooppunt bedekken `cq/ui/widgets` krachtens `/apps`. De afhankelijkheid vervangen `cq.rte` op het knooppunt `/apps/cq/ui/widgets` with `cq.coralui2.rte`.

>[!NOTE]
>
>CoralUI 2 RTE gebruikt handlebars malplaatjes voor stop-in dialogen. Daarom had CoralUI 2 RTE clientlib een afhankelijkheid van handlebars clientlib. CoralUI 3 RTE gebruikt geen zakbalkmalplaatjes en heeft geen bijbehorende gebiedsdeel. Als uw aangepaste plug-ins handbalksjablonen gebruiken, neemt u de client lib-handler op uw webpagina op.

## Aanvullende informatie {#further-information}

Voor meer informatie over het vormen van RTE, zie [Widget-API AEM](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/widgets-api/index.html) referentie.

Met name om de beschikbare plug-ins en bijbehorende opties te zien:

* De [CQ.form.RichText](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/widgets-api/index.html?class=CQ.form.RichText) biedt een formulierveld voor het bewerken van opgemaakte tekstgegevens (opgemaakte tekst). Zie Configuratieopties voor meer informatie over alle parameters die beschikbaar zijn voor het RTF-formulier.
* De component RichText verstrekt een brede waaier van functionaliteit gebruikend stop-ins die onder worden vermeld [CQ.form.rate.plugins.Plugin](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/widgets-api/index.html?class=CQ.form.rte.plugins.Plugin). Voor elke insteekmodule:

   * Zie de Functies voor meer informatie over functionaliteit die kan worden ingeschakeld (of uitgeschakeld).
   * Zie de Opties Config voor alle parameters beschikbaar voor gedetailleerde configuratie van de aangewezen stop-binnen.

* Meer informatie over de Regels van de HTML voor verbindingen is ook beschikbaar.

Met de bovenstaande opties kunt u uw eigen RTE uitbreiden en aanpassen. Als u bijvoorbeeld de ankers wilt weergeven die beschikbaar zijn op de pagina wanneer u een koppeling maakt, kunt u uw eigen implementatie van de `LinkPlugin`.

## Bekende beperkingen {#known-limitations}

AEM het vermogen van RTE heeft de volgende beperkingen:

* De mogelijkheden van RTE worden gesteund slechts in AEM componentendialogen. RTE wordt niet gesteund op wizards of Stichting-vormen als [Pagina-eigenschappen](/help/sites-developing/page-properties-views.md) en [Basisstructuur](/help/sites-authoring/scaffolding.md) op interface met aanraakbediening.

* AEM werkt niet aan [Hybride apparaten](/help/release-notes/known-issues.md).

* Noem niet de knoop van de configuratie RTE `config`. Anders, treedt de configuratie RTE voor slechts de beheerders en niet voor de gebruikers in de groep van kracht `content-author`.

* RTE biedt geen ondersteuning voor inlineframe of iframe voor het insluiten van inhoud.

>[!MORELIKETHIS]
>
>* [RTE-plug-ins configureren](configure-rich-text-editor-plug-ins.md)
>* [Rich Text Editor gebruiken voor ontwerpen](../sites-authoring/rich-text-editor.md)
>* [RTE voor toegankelijke sites configureren](rte-accessible-content.md)
>* [Aanraakinterface en Klassieke UI-functiepariteit](../release-notes/touch-ui-features-status.md)
>* [Zelfstudie als voorbeeld voor het maken van een samengestelde component met meerdere velden](https://experience-aem.blogspot.com/2019/05/aem-65-touchui-composite-multifield-with-coral3-rte-rich-text.html)

