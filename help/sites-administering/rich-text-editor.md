---
title: De Rich Text Editor configureren
seo-title: De Rich Text Editor configureren
description: Leer om de Rich Text Editor van AEM te vormen.
seo-description: Leer om de Rich Text Editor van AEM te vormen.
uuid: 82d2fe41-676a-4a49-939f-13374b9d869f
contentOwner: asgupta
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: operations
content-type: reference
discoiquuid: 9248d09c-b749-4aca-9167-1707c1dd8a53
translation-type: tm+mt
source-git-commit: 01a748a6f6f92c752fc6a14005f236fee304c2eb

---


# Configure the Rich Text Editor {#configure-the-rich-text-editor}

De Rich Text Editor (RTE) biedt auteurs een groot aantal functies voor het bewerken van hun tekstinhoud. Pictogrammen, selectiekaders, werkbalk en menu&#39;s zijn beschikbaar voor een WYSIWYG-ervaring bij het bewerken van tekst.

RTE kan worden gevormd om, de eigenschappen toe te laten onbruikbaar te maken en uit te breiden beschikbaar in de auteurscomponenten. Om te weten hoe te om eigenschappen RTE voor creatie te gebruiken, zie de Redacteur van de Tekst van het [Gebruik Rich voor creatie](/help/sites-authoring/rich-text-editor.md).

Het volgende werkschema illustreert een geadviseerde orde om de de configuratietaken van RTE te voltooien.

![Normale workflow voor het configureren van Rich Text Editor](assets/rte_workflow_v1.png)

**** Afbeelding: De *typische werkstroom om de Rich Text Editor te vormen*

## Interface met aanraakbediening en klassieke gebruikersinterface {#understand-touch-enabled-ui-and-classic-ui}

De interface met aanraakbediening is de standaardinterface voor AEM. Adobe introduceerde Touch UI met [responsief ontwerp](/help/sites-authoring/responsive-layout.md) voor ontwerpomgeving, in versie 5.6.De aanraakinterface is ontworpen voor touch- en desktopapparaten. De interface verschilt aanzienlijk van de oorspronkelijke klassieke interface.

![De rijke toolbar van de Redacteur van de Tekst in Touch-Toegelaten UI](assets/chlimage_1-404.png)

**** Afbeelding: Werkbalk van de *Rich Text Editor in UI met aanraakbediening*

![De Rich Text Editor-werkbalk in de klassieke gebruikersinterface](assets/rtedefault.png)

**** Afbeelding: Werkbalk *van de Rich Text Editor in de klassieke gebruikersinterface*

**Zie ook**:

* [UI-aanbevelingen](/help/sites-deploying/ui-recommendations.md)
* Informatie over het vervangen van de klassieke gebruikersinterface vindt u in [AEM 6.4 Release-notities](/help/release-notes/deprecated-removed-features.md)
* Zie [Aanraakinterface en Klassieke UI voor het verschil tussen de gebruikersinterface](https://aemcq5pedia.wordpress.com/2018/01/05/touch-enabled-ui-aem6-3/)
* Zie [Concepten van AEM Touch-interface voor meer informatie over de interface met aanraakbediening](/help/sites-developing/touch-ui-concepts.md)

## Verschillende bewerkingsmodi {#editingmodes}

Auteurs kunnen tekstinhoud in AEM maken en bewerken met de verschillende modi van componenten. De toolbaropties voor het ontwerpen en het formatteren van inhoud en de gebruikerservaring van rte-toegelaten componenten op verschillende het uitgeven wijze variëren gebaseerd op configuraties RTE.

<table> 
 <tbody> 
  <tr> 
   <th>Bewerkmodus</th> 
   <th>Bewerkingsgebied</th> 
   <th>Aanbevolen functies om te worden ingeschakeld<br /> </th> 
   <th>Aanraakinterface</th> 
   <th>Klassieke interface</th> 
  </tr> 
  <tr> 
   <td>Inline</td> 
   <td>Op locatie bewerken voor snelle, kleine bewerkingen; Opmaken zonder dialoogvenster te openen</td> 
   <td>Minimale RTE-functies</td> 
   <td>J</td> 
   <td>J</td> 
  </tr> 
  <tr> 
   <td>RTE volledig scherm</td> 
   <td>Behandelt gehele pagina<br /> </td> 
   <td>Alle vereiste eigenschappen van RTE<br /> </td> 
   <td>J</td> 
   <td>N<br /> </td> 
  </tr> 
  <tr> 
   <td>Dialoog</td> 
   <td>Dialoogvenster boven op de pagina-inhoud, maar heeft geen betrekking op de gehele pagina</td> 
   <td>Alle vereiste eigenschappen van RTE in Klassieke UI; Functies op oordeelkundige wijze inschakelen in Touch UI<br /> </td> 
   <td>J</td> 
   <td>J</td> 
  </tr> 
  <tr> 
   <td>Dialoogvenster volledig scherm<br /> </td> 
   <td>Hetzelfde als de modus Volledig scherm; bevat gebieden van de dialoog naast RTE<br /> </td> 
   <td>Alle vereiste eigenschappen van RTE</td> 
   <td>J</td> 
   <td>N</td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>De functie voor het bewerken van bronnen is niet beschikbaar in de inline bewerkingsmodus van de interface met aanraakbediening. U kunt afbeeldingen niet slepen in de modus Volledig scherm. Alle andere functies werken in alle modi.

### Inline bewerken {#inline-editing}

Als u de inhoud opent (met een langzaam dubbeltikken/klikken), kan deze op de pagina worden bewerkt. Er wordt een compacte werkbalk met basisopties weergegeven.

![Inline bewerken met de standaardwerkbalk in Touch-gebruikersinterface](assets/chlimage_1-405.png)

**** Afbeelding: Inline bewerken met de standaardwerkbalk in de gebruikersinterface voor *aanraakbediening*

In de klassieke gebruikersinterface kunt u met een trage dubbelklik op de component inline bewerken en met een oranje omtrek de inhoud markeren. Als de Inhoudszoeker is geopend, wordt boven in het venster een werkbalk weergegeven met de beschikbare RTE-opmaakopties. Als de Inhoudszoeker niet is geopend, worden de opmaakopties niet weergegeven en kunt u alleen standaardtekstbewerkingen uitvoeren.

### Volledig scherm bewerken {#full-screen-editing}

AEM-componenten kunnen worden geopend in de weergave Volledig scherm, waarin de pagina-inhoud wordt verborgen en het beschikbare scherm wordt ingenomen. U kunt overwegen om een gedetailleerde versie van de inlinebewerking op volledig scherm te bewerken, aangezien deze de meeste bewerkingsopties biedt. Het kan worden geopend door ![rte_fullscreen](assets/rte_fullscreen.png), van de compacte toolbar te klikken wanneer het gebruiken van de gealigneerde het uitgeven wijze.

De modus Volledig scherm van het dialoogvenster bevat een gedetailleerde RTE-werkbalk en de opties en componenten die beschikbaar zijn in de dialoogmodus. Het is alleen van toepassing voor een dialoog die naast andere componenten RTE bevat.

![De gedetailleerde RTE-werkbalk wanneer u bewerkingen uitvoert in de modus Volledig scherm in de gebruikersinterface met aanraakbediening](assets/chlimage_1-406.png)

**** Afbeelding: De gedetailleerde RTE-werkbalk wanneer u bewerkingen uitvoert in de modus Volledig scherm in de interface met aanraakbediening **

### Dialoogbewerkingen {#dialog-editing}

Wanneer dubbelgeklikt wordt op een component in de klassieke gebruikersinterface, wordt een dialoogvenster geopend voor het bewerken van de inhoud. Het dialoogvenster wordt boven op de bestaande pagina geopend. In sommige specifieke scenario&#39;s, opent de dialoog als pop-up venster. Wanneer een tekstcomponent bijvoorbeeld deel uitmaakt van een kolom in een paginalay-out met meerdere kolommen en het gebied dat beschikbaar is voor het dialoogvenster kleiner is.

![Dialoogbewerkingsmodus in interface met aanraakbediening](assets/dialog_editing_modetouchui.png)

**** Afbeelding: Bewerkingsmodus van *dialoogvenster in interface met aanraakbediening*

![Dialoogvenster in klassieke gebruikersinterface met gedetailleerde werkbalk voor bewerken](assets/chlimage_1-407.png)

**** Afbeelding: Dialoogvenster in *klassieke gebruikersinterface met gedetailleerde werkbalk voor bewerken*

## Informatie over RTE-plug-ins en de bijbehorende functies {#aboutplugins}

De functionaliteit wordt beschikbaar gesteld via een reeks plug-ins, elk met:

* Een `features` eigenschap:

   * Hiermee wordt de basisfunctionaliteit voor die plug-in geactiveerd of gedeactiveerd.
   * Dat kan worden gevormd gebruikend een gestandaardiseerde procedure.

* Indien van toepassing, meer eigenschappen en opties die gespecialiseerde configuratie vereisen.

De basiseigenschappen van RTE worden geactiveerd, of worden gedeactiveerd, door de waarde van het `features` bezit op een knoop specifiek voor de aangewezen stop-in.

In de volgende tabel worden de huidige plug-ins weergegeven:

* Plug-in-id&#39;s met een koppeling naar de API-documentatie. ID wordt gebruikt als de knooppuntnaam wanneer het [activeren van een stop-in](/help/sites-administering/configure-rich-text-editor-plug-ins.md#activateplugin).
* Toegestane waarden voor de `features` eigenschap.
* Een beschrijving van de functionaliteit die door de plug-in wordt geboden.

<table> 
 <tbody> 
  <tr> 
   <td><p>Plug-in-id<br /><br /> </p> </td> 
   <td><p>functies<br /><br /> </p> </td> 
   <td><p>Beschrijving<br /> <br /> </p> </td> 
  </tr> 
  <tr> 
   <td><p>bewerken</p> </td> 
   <td><p>cut<br /> copy<br /> paste-default<br /> paste-plaintext<br /> paste-wordhtml</p> </td> 
   <td><p><a href="/help/sites-administering/configure-rich-text-editor-plug-ins.md#textstyles" target="_blank">Knip, kopieer en kopieer de drie plakmodi</a>.</p> </td> 
  </tr> 
  <tr> 
   <td><p><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/widgets-api/index.html?class=CQ.form.rte.plugins.FindReplacePlugin">findreplace</a></p> </td> 
   <td><p>zoeken<br /> vervangen</p> </td> 
   <td><p>Zoeken en vervangen.</p> </td> 
  </tr> 
  <tr> 
   <td><p><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/widgets-api/index.html?class=CQ.form.rte.plugins.FormatPlugin">format</a></p> </td> 
   <td><p>vet<br /> cursief<br /> onderstrepen</p> </td> 
   <td><p><a href="/help/sites-administering/configure-rich-text-editor-plug-ins.md#textstyles" target="_blank">Basistekstopmaak</a>.</p> </td> 
  </tr> 
  <tr> 
   <td><p><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/widgets-api/index.html?class=CQ.form.rte.plugins.ImagePlugin">image</a></p> </td> 
   <td><p>image</p> </td> 
   <td><p>Stel bepaalde afbeeldingseigenschappen in, zoals uitlijning en alt-tekst. Basisondersteuning voor het slepen en neerzetten van afbeeldingen vanuit de Inhoudszoeker werkt zonder deze plug-in.</p> <p><em>Opmerking</em>: Het ontwerpgedrag kan per browser verschillen. Mozilla Firefox biedt bijvoorbeeld mogelijkheden om het formaat te wijzigen, maar Google Chrome niet.</p> </td> 
  </tr> 
  <tr> 
   <td><p><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/widgets-api/index.html?class=CQ.form.rte.plugins.KeyPlugin">toetsen</a></p> </td> 
   <td><p> </p> </td> 
   <td><p>Zie de <a href="/help/sites-administering/configure-rich-text-editor-plug-ins.md#tabsize" target="_blank">tabgrootte</a>om deze waarde te definiëren.</p> </td> 
  </tr> 
  <tr> 
   <td><p><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/widgets-api/index.html?class=CQ.form.rte.plugins.JustifyPlugin">justify</a></p> </td> 
   <td><p>uitvullen, links<br /> uitvullen, midden<br /> rechts uitvullen</p> </td> 
   <td><p>Alinea-uitlijning.</p> </td> 
  </tr> 
  <tr> 
   <td><p><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/widgets-api/index.html?class=CQ.form.rte.plugins.LinkPlugin">koppelingen</a></p> </td> 
   <td><p>modifylink<br /> unlink<br /> anchor</p> </td> 
   <td><p><a href="/help/sites-administering/configure-rich-text-editor-plug-ins.md#linkstyles" target="_blank">Hyperlinks en ankers</a>.</p> </td> 
  </tr> 
  <tr> 
   <td><p><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/widgets-api/index.html?class=CQ.form.rte.plugins.ListPlugin">lijsten</a></p> </td> 
   <td><p>geordende<br /> ongeordende<br /> inspringing<br /> uitspringen</p> </td> 
   <td><p>Deze insteekmodule bestuurt zowel de <a href="/help/sites-administering/configure-rich-text-editor-plug-ins.md#indentmargin" target="_blank">inspringing als de lijsten</a>; inclusief geneste lijsten.</p> </td> 
  </tr> 
  <tr> 
   <td><p><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/widgets-api/index.html?class=CQ.form.rte.plugins.MiscToolsPlugin">misverstanden</a></p> </td> 
   <td><p>specialchars<br /> -bronbewerking</p> </td> 
   <td>Met diverse gereedschappen kunnen auteurs <a href="/help/sites-administering/configure-rich-text-editor-plug-ins.md#spchar" target="_blank">speciale tekens</a> invoeren of de HTML-bron bewerken. U kunt ook een heel <a href="/help/sites-administering/configure-rich-text-editor-plug-ins.md#definerangechar" target="_blank">scala aan speciale tekens</a> toevoegen als u uw eigen lijst wilt definiëren.</td> 
  </tr> 
  <tr> 
   <td><p>Paraformat</p> </td> 
   <td><p>paraformat</p> </td> 
   <td>De standaardindexdelingen zijn Alinea, Kop 1, Kop 2 en Kop 3 (&lt;p&gt;, &lt;h1&gt;, &lt;h2&gt; en &lt;h3&gt;). U kunt meer alinea-indelingen <a href="/help/sites-administering/configure-rich-text-editor-plug-ins.md#paraformats" target="_blank"></a> toevoegen of de lijst uitbreiden.</td> 
  </tr> 
  <tr> 
   <td><p>spellingcontrole</p> </td> 
   <td><p>checktext</p> </td> 
   <td><p><a href="/help/sites-administering/configure-rich-text-editor-plug-ins.md#adddict" target="_blank">Spellingcontrole</a>met behoud van taal.</p> </td> 
  </tr> 
  <tr> 
   <td><p>stijlen</p> </td> 
   <td><p>stijlen</p> </td> 
   <td>Ondersteuning voor opmaak met behulp van een CSS-klasse. <a href="/help/sites-administering/configure-rich-text-editor-plug-ins.md#textstyles" target="-blank">Voeg nieuwe tekststijlen</a> toe als u uw eigen reeks stijlen voor gebruik met tekst wilt toevoegen (of uitbreiden).</td> 
  </tr> 
  <tr> 
   <td><p>subsuperscript</p> </td> 
   <td><p>subscript<br /> superscript</p> </td> 
   <td><p>Extensies voor de basisindelingen, subscript en superscript toevoegen.</p> </td> 
  </tr> 
  <tr> 
   <td><p>table</p> </td> 
   <td><p>table<br /> removetable<br /> insert<br /> removerow<br /> insert column<br /> removecolumn<br /> cellprops<br /> mergecells<br /> splitcell<br /> selectrow<br /> selected columns</p> </td> 
   <td>Zie tabelstijlen <a href="/help/sites-administering/configure-rich-text-editor-plug-ins.md#tablestyles" target="_blank"></a>configureren als u uw eigen stijlen voor gehele tabellen of afzonderlijke cellen wilt toevoegen.</td> 
  </tr> 
  <tr> 
   <td><p>ongedaan maken</p> </td> 
   <td><p>ongedaan maken<br /> opnieuw uitvoeren</p> </td> 
   <td>Grootte historie van bewerkingen voor <a href="/help/sites-administering/configure-rich-text-editor-plug-ins.md#undohistory" target="_blank">ongedaan maken en opnieuw uitvoeren</a> .</td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>De plug-in Volledig scherm wordt niet ondersteund in de dialoogmodus. Gebruik de `dialogFullScreen` instelling om de werkbalk voor de modus Volledig scherm te configureren.

## Begrijp de configuratiewegen en plaatsen {#understand-the-configuration-paths-and-locations}

De [wijze van het uitgeven van RTE (en UI)](#editingmodes) die u voor uw auteurs verstrekt beslist de plaats voor de configuratiedetails wanneer u de stop-ins [van RTE](/help/sites-administering/configure-rich-text-editor-plug-ins.md#activateplugin)activeert:

| Bewerkmodus | Locatie voor aanraakinterface | Locatie voor klassieke gebruikersinterface |
|---|---|---|
| Inline | `cq:editConfig/cq:inplaceEditing` | `cq:editConfig/cq:inplaceEditing` |
| Volledig scherm | `cq:editConfig/cq:inplaceEditing` | Niet van toepassing |
| Dialoog | `cq:dialog` | `dialog` |
| Dialoogvenster Volledig scherm | `cq:dialog` | Niet van toepassing |

>[!NOTE]
>
>Geef het knooppunt onder niet de naam `cq:inplaceEditing` als `config`. Definieer bij `cq:inplaceEditing` knooppunt de volgende eigenschappen:
>
>* **Naam**: `configPath`
   >
   >
* **Type**: `String`
   >
   >
* **Waarde**: pad van het knooppunt met de feitelijke configuratie
>
>
Noem niet de de configuratieknoop van RTE zoals `config`. Anders, worden de configuraties RTE van kracht voor slechts de beheerders en niet voor de gebruikers in de groep `content-author`.

Configureer de volgende eigenschappen die alleen van toepassing zijn in de bewerkingsmodus Dialoogvenster in Touch UI:

* `useFixedInlineToolbar`: Plaats dit bezit Van Boole dat op de knoop RTE (met het verbinden:resourceType= `cq/gui/components/authoring/dialog/richtext`) wordt bepaald aan `True`, om de toolbar van RTE te maken vast in plaats van het drijven.

   Wanneer deze eigenschap true is, wordt het bewerken van Richtingstekst standaard gestart op de gebeurtenis &quot;foundation-contentloaded&quot;.

   Om dit te verhinderen, plaats het bezit aan `customStart` `True`en teweegbrengt de gebeurtenis &quot;rte-start&quot;om RTE het uitgeven te beginnen. Wanneer deze eigenschap &#39;true&#39; is, werkt het standaardgedrag, het starten bij klikken.

* `customStart`: Plaats dit bezit Van Boole dat op de knoop RTE aan wordt bepaald, om te controleren wanneer om RTE te beginnen door de gebeurtenis te teweegbrengen `True``rte-start`.

* `rte-start`: Trigger deze gebeurtenis op de `contenteditable-div` van RTE, wanneer beginnen RTE uit te geven. Dit werkt alleen als true `customStart` is ingesteld.

Als RTE wordt gebruikt in het dialoogvenster met aanraakbediening, is het verplicht de eigenschap in te stellen op true `useFixedInlineToolbar` om problemen te voorkomen.

## RTE-functies inschakelen door plug-ins te activeren {#enable-rte-functionalities-by-activating-plug-ins}

De functionaliteit van RTE wordt beschikbaar gemaakt via een reeks stop-ins, elk met eigenschappen bezit. U kunt de eigenschap features configureren om de verschillende functies van elke insteekmodule in of uit te schakelen.

Voor gedetailleerde configuraties van de stop-ins van RTE, zie [hoe te om de stop-ins](/help/sites-administering/configure-rich-text-editor-plug-ins.md)van RTE te activeren en te vormen.


Download deze steekproefconfiguratie om te begrijpen hoe te om RTE te vormen. In dit pakket zijn alle functies ingeschakeld.

[Bestand ophalen](/help/assets/assets/rte-sample-all-features-enabled-10.zip)

>[!NOTE]
>
>De de tekstcomponent [van Componenten van de](https://helpx.adobe.com/experience-manager/core-components/using/text.html) Kern staat malplaatjeredacteurs toe om vele stop-ins van RTE in het gebruikersinterface als inhoudsbeleid te vormen, die de behoefte aan technische configuratie elimineren. Het beleid van de inhoud kan met RTE gebruikersinterfaceconfiguraties werken zoals beschreven. Voor meer informatie, zie de de [gebruikersinterfacemontages van RTE en inhoudsbeleid](/help/sites-administering/rich-text-editor.md#rtecontentpolicies), [creeer paginasjablonen](/help/sites-authoring/templates.md), en de de ontwikkelaarsdocumentatie [van de Componenten van de](https://helpx.adobe.com/experience-manager/core-components/using/developing.html)Kern.

>[!NOTE]
>
>Ter referentie kunt u de standaardtekstcomponenten (geleverd als onderdeel van een standaardinstallatie) vinden op:
>
>* `/libs/wcm/foundation/components/text`
>* `/libs/foundation/components/text`
>
>
Als u uw eigen tekstcomponent wilt maken, kopieert u de bovenstaande component in plaats van deze componenten te bewerken.

## RTE-werkbalk configureren {#dialogfullscreen}

AEM staat u toe om UI voor de Redacteur RichText voor de verschillende het uitgeven wijzen verschillend te vormen. De standaardinstellingen worden hieronder gegeven. U kunt deze standaardinstellingen op basis van uw vereisten overschrijven.

Voor de beste ontwerpervaring:

* Schakel in een zwevend dialoogvenster alleen de plug-ins in die geen pop-up hebben, omdat het zwevende dialoogvenster een kleiner formaat heeft.
* In het dialoogvenster Volledig scherm schakelt u alle vereiste plug-ins in, zelfs de plug-ins met grotere pop-ups, zoals de `Paste` plug-in. Gebruik de hieronder beschreven `dialogFullScreen` configuratie.

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

Er worden verschillende UI-instellingen gebruikt voor de inlinemodus en de modus Volledig scherm. De eigenschap toolbar wordt gebruikt om de knoppen van de werkbalk op te geven. Als de knop zelf bijvoorbeeld een functie is (bijvoorbeeld `Bold`), wordt deze opgegeven als `PluginName#FeatureName` (bijvoorbeeld `links#modifylink`). Als de knop een pop-up is (met enkele functies van een plug-in), wordt deze opgegeven als `#PluginName` (bijvoorbeeld `#format`). Scheidingstekens (| ) tussen een groep knoppen kan worden opgegeven met &#39;-&#39;.

Het pop-upknooppunt onder de modus Inline of Volledig scherm bevat een lijst met de popovers die worden gebruikt. Elk onderliggend knooppunt onder het `popovers` knooppunt krijgt een naam na de insteekmodule (bijvoorbeeld `format`). Deze bevat een eigenschap `items` die een lijst bevat met functies van de plug-in (bijvoorbeeld `format#bold`).

## RTE-gebruikersinterface-instellingen en inhoudsbeleid {#rtecontentpolicies}

De beheerders kunnen de opties controleren RTE gebruikend inhoudsbeleid, zeggen in plaats van de configuratie zoals hierboven beschreven. In het inhoudsbeleid worden de ontwerpeigenschappen van een component gedefinieerd wanneer deze worden gebruikt als onderdeel van een [bewerkbare sjabloon](../sites-authoring/templates.md). Als bijvoorbeeld een tekstcomponent die de RTE gebruikt wordt gebruikt met een bewerkbare sjabloon, kan het inhoudsbeleid definiëren dat de optie Vet beschikbaar is en zijn enkele opties voor alineaopmaak beschikbaar. Het inhoudsbeleid is herbruikbaar en kan op meerdere sjablonen worden toegepast.

Vanaf AEM 6.4 Service Pack 3, de beschikbare opties in RTE stroom stroomafwaarts van de configuraties van het gebruikersinterface aan het inhoudsbeleid.

* De de configuratiemontages van de gebruikersinterface bepalen welke opties aan het inhoudsbeleid beschikbaar zijn.
* Als de gebruikersinterfaceconfiguratie van RTE verwijderde of geen punt toelaat, kan het inhoudsbeleid niet het vormen.
* Een auteur heeft toegang tot slechts dergelijke functionaliteit die door de gebruikersinterfaceconfiguraties en het inhoudsbeleid ter beschikking wordt gesteld.

Als voorbeeld kunt u de documentatie [van de Component van de](https://docs.adobe.com/content/help/en/experience-manager-core-components/using/components/text.html#the-text-component-and-the-rich-text-editor)Kern van de Tekst zien.

## Toewijzing aanpassen tussen werkbalkpictogrammen en -opdrachten {#iconstoolbar}

U kunt de afbeelding aanpassen tussen de koraalpictogrammen die worden weergegeven op de RTE-werkbalk en de beschikbare opdrachten. U kunt geen andere pictogrammen gebruiken behalve Koraalpictogrammen.

1. Maak een knooppunt met de naam `icons` under `uiSettings/cui`.

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
>Adobe raadt het overschakelen niet aan als aanbevolen werkwijze. Schakel als laatste redmiddel over naar CoralUI 2 RTE. De stop-ins van de douane voor CoralUI 2 RTE werkt met CoralUI 3 RTE als stop-ins niet van internals RTE, zoals klassen afhangt. Gebruik de `rte.coralui3` bibliotheek als u aangepaste plug-ins voor CoralUI 3 RTE gebruikt.

1. Bedek het knooppunt `/libs/cq/gui/components/authoring/editors/clientlibs/core` onder `/apps`en voer de volgende handelingen uit:

   * Vervangen `rte.coralui3` door `rte.coralui2` voor het gebiedsdeelbezit.
   * Vervangen door `cq.authoring.editor.core.inlineediting.rte.coralui3` voor `cq.authoring.editor.core.inlineediting.rte.coralui2` de eigenschap embed.
   * Vervangen door `cq.authoring.rte.coralui3` voor `cq.authoring.rte.coralui2` de eigenschap embed.

1. Bedek de knooppunten `/libs/cq/gui/components/authoring/dialog/richtext/clientlibs/rte/coralui3` en `/libs/cq/gui/components/authoring/dialog/richtext/clientlibs/rte/coralui2` onder `/apps`.

   Categorie verwijderen `cq.authoring.dialog` uit `/apps/cq/gui/components/authoring/dialog/richtext/clientlibs/rte/coralui3` en toevoegen aan `/apps/cq/gui/components/authoring/dialog/richtext/clientlibs/rte/coralui2`.

1. Wijzig een andere afhankelijkheid die op de pagina wordt opgenomen van `rte.coralui3` naar `rte.coralui2`. Wijzig bijvoorbeeld, na het bedekken van het knooppunt `/libs/mcm/campaign/components/touch-ui/clientlibs/rte` onder `/apps`, de afhankelijkheid van het knooppunt van `rte.coralui3` naar `rte.coralui2`.

1. Bedek het knooppunt `cq/ui/widgets` onder `/apps`. Vervang de afhankelijkheid `cq.rte` bij de knoop `/apps/cq/ui/widgets` met `cq.coralui2.rte`.

>[!NOTE]
>
>CoralUI 2 RTE gebruikt handlebars malplaatjes voor stop-in dialogen. Daarom had CoralUI 2 RTE clientlib een afhankelijkheid van handlebars clientlib. CoralUI 3 RTE gebruikt geen zakbalkmalplaatjes en heeft geen bijbehorende gebiedsdeel. Als uw aangepaste plug-ins handbalksjablonen gebruiken, neemt u de client lib-handler op uw webpagina op.

## Aanvullende informatie {#further-information}

Zie de [AEM Widget API](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/widgets-api/index.html) -naslaggids voor meer informatie over het configureren van de RTE.

Met name om de beschikbare plug-ins en bijbehorende opties te zien:

* De [component CQ.form.RichText](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/widgets-api/index.html?class=CQ.form.RichText) biedt een formulierveld voor het bewerken van opgemaakte tekstgegevens (RTF-gegevens). Zie Configuratieopties voor meer informatie over alle parameters die beschikbaar zijn voor het RTF-formulier.
* De component RichText biedt een groot aantal functies met plug-ins die worden vermeld onder [CQ.form.rte.plugins.Plugin](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/widgets-api/index.html?class=CQ.form.rte.plugins.Plugin). Voor elke insteekmodule:

   * zie de Eigenschappen voor details van functionaliteit die kan worden toegelaten (of worden onbruikbaar gemaakt)
   * Zie de Opties Config voor alle parameters beschikbaar voor gedetailleerde configuratie van de aangewezen stop - binnen

* Meer informatie over HTML-regels voor koppelingen is ook beschikbaar.

Met de bovenstaande opties kunt u uw eigen RTE uitbreiden en aanpassen. Als u bijvoorbeeld de ankers wilt weergeven die beschikbaar zijn op de pagina wanneer u een koppeling maakt, kunt u uw eigen implementatie van de koppeling opgeven `LinkPlugin`.

## Bekende beperkingen {#known-limitations}

AEM RTE-mogelijkheden hebben de volgende beperkingen:

* RTE-mogelijkheden worden alleen ondersteund in dialoogvensters van AEM-componenten. RTE wordt niet gesteund op tovenaars of stichting-vormen zoals de Eigenschappen [van de](../sites-developing/page-properties-views.md) Pagina en het [Opslaan](../sites-authoring/scaffolding.md) op touch-Toegelaten UI.

* AEM werkt niet op [hybride apparaten](../release-notes/known-issues.md).

* Geef het RTE-configuratieknooppunt geen naam `config`. Anders, treedt de configuratie RTE voor slechts de beheerders en niet voor de gebruikers in de groep van kracht `content-author`.

* RTE biedt geen ondersteuning voor inlineframe of iframe voor het insluiten van inhoud.

>[!MORELIKETHIS]
>
>* [RTE-plug-ins configureren](configure-rich-text-editor-plug-ins.md)
>* [Rich Text Editor gebruiken voor ontwerpen](../sites-authoring/rich-text-editor.md)
>* [RTE voor toegankelijke sites configureren](rte-accessible-content.md)
>* [Aanraakinterface en Klassieke UI-functiepariteit](../release-notes/touch-ui-features-status.md)
>* [Zelfstudie als voorbeeld voor het maken van een samengestelde component met meerdere velden](https://experience-aem.blogspot.com/2019/05/aem-65-touchui-composite-multifield-with-coral3-rte-rich-text.html)

