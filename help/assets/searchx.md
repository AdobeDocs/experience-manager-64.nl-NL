---
title: Zoeken naar elementen uitbreiden
description: De zoekmogelijkheden van [!DNL Experience Manager] Middelen buiten de box zoeken naar elementen op tekenreeksen.
contentOwner: AG
feature: Search
role: Developer
exl-id: d68c735f-2699-4923-a7e7-4d1356eae335
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 7%

---

# Zoeken naar elementen uitbreiden {#extending-assets-search}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

U kunt zoekmogelijkheden voor Adobe Experience Manager-middelen uitbreiden. Uit de doos, [!DNL Experience Manager] Elementen zoeken naar elementen op tekenreeksen.

Het zoeken wordt gedaan via de interface QueryBuilder zodat kan het onderzoek met verscheidene predikaten worden aangepast. U kunt de standaardset voorspelden in de volgende map bedekken: `/apps/dam/content/search/searchpanel/facets`.

U kunt ook extra tabbladen toevoegen aan de [!DNL Experience Manager] Deelvenster Middelen beheren.

>[!CAUTION]
>
>Vanaf [!DNL Experience Manager] 6.4, is de klassieke gebruikersinterface afgekeurd. Zie voor aankondiging [Verouderde en verwijderde functies](../release-notes/deprecated-removed-features.md). U wordt aangeraden de interface met aanraakbediening te gebruiken. Voor aanpassingen raadpleegt u [Zoeken in gezichten](search-facets.md).

## Bedekken {#overlaying}

Om preconfigured preconfigured te bedekken, kopieer `facets` knooppunt van `/libs/dam/content/search/searchpanel` tot `/apps/dam/content/search/searchpanel/` of een andere `facetURL` eigenschap in de configuratie van het deelvenster Zoeken (de standaardinstelling is `/libs/dam/content/search/searchpanel/facets.overlay.infinity.json`).

![screen_shot_2012-06-05at113619am](assets/screen_shot_2012-06-05at113619am.png)

>[!NOTE]
>
>Standaard is de mapstructuur onder / `apps` bestaat niet en moet worden gecreëerd. Zorg ervoor dat de knooppunttypen overeenkomen met de knooppunttypen onder / `libs`.

## Tabs toevoegen {#adding-tabs}

U kunt extra tabbladen van zoekopdrachten toevoegen door deze te configureren in het dialoogvenster [!DNL Experience Manager] Middelen-beheerder. Extra tabbladen maken:

1. De mapstructuur maken `/apps/wcm/core/content/damadmin/tabs,`als deze nog niet bestaat, en kopieert u de `tabs` knooppunt van `/libs/wcm/core/content/damadmin` plakken.
1. Maak en configureer het tweede tabblad naar wens.

   >[!NOTE]
   >
   >Wanneer u een tweede deelvenster voor sitebeheer maakt, moet u een `id` gebruiken om formulierconflicten te voorkomen.

## Aangepaste voorvertoningen maken {#creating-custom-predicates}

[!DNL Experience Manager] De activa komen met een reeks vooraf bepaalde predikaten die kunnen worden gebruikt om een pagina van het Aandeel van Activa aan te passen. Op deze manier wordt een aandeel in activa aangepast in [Een pagina voor het delen van bedrijfsmiddelen maken en configureren](assets-finder-editor.md#creating-and-configuring-an-asset-share-page).

Naast het gebruik van reeds bestaande voorspellingen, [!DNL Experience Manager] ontwikkelaars kunnen ook hun eigen voorspellingen maken met behulp van de [Query Builder-API](/help/sites-developing/querybuilder-api.md).

Voor het maken van aangepaste predikaten is basiskennis over de [Widget-framework](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/widgets-api/index.html).

De beste praktijken moeten een bestaand predikaat kopiëren en het aanpassen. Voorspelregels voor monsters bevinden zich in `/libs/cq/search/components/predicates`.

### Voorbeeld: Een eenvoudige voorspelling van eigenschappen maken {#example-build-a-simple-property-predicate}

Een voorspelling van eigenschappen maken:

1. Maak bijvoorbeeld een componentmap in de projectmap `/apps/geometrixx/components/titlepredicate`.
1. Toevoegen `content.xml`:

   ```xml
   <?xml version="1.0" encoding="UTF-8"?>
   <jcr:root xmlns:sling="https://sling.apache.org/jcr/sling/1.0"
    xmlns:cq="https://www.day.com/jcr/cq/1.0"
    xmlns:jcr="https://www.jcp.org/jcr/1.0"
       jcr:primaryType="cq:Component"
       jcr:title="Title Predicate"
       sling:resourceSuperType="foundation/components/parbase"
       allowedParents="[*/parsys]"
       componentGroup="Search"/>
   ```

1. Toevoegen `titlepredicate.jsp`.

   ```xml
   <%--
     Sample title predicate component
   
   --%><%@ page import="java.util.Calendar" %><%
   %><%@include file="/libs/foundation/global.jsp"%><%
   
       // A unique id is necessary in case this predicate is inserted multiple times on the same page
       String elemId = "cq-predicate-" +  Long.toString(Calendar.getInstance().getTimeInMillis());
   
   %><div class="predicatebox">
   
       <div class="title">Title</div>
   
       <%-- The wrapper for the form elements. All items will be append to this wrapper. --%>
       <div id="<%= elemId %>" class="content"></div>
   
   </div><script type="text/javascript">
   
       CQ.Ext.onLoad(function() {
   
           var predicateName = "property";
           var propertyName = "jcr:content/metadata/dc:title";
           var elemId = "<%= elemId %>";
   
           // Get the page wide available QueryBuilder.
           var qb = CQ.search.Util.getQueryBuilder();
   
           // createId adds a counter to the predicate name - useful in case this predicate
           // is inserted multiple times on the same page.
           var id = qb.createId(predicateName);
   
           // Hidden field that defines the property to search for; in our case this
           // is the "dc:title" metadata. The name "property" (or "1_property", "2_property" etc.)
           // indicates the server to use the property predicate
           // (com.day.cq.search.eval.JcrPropertyPredicateEvaluator).
           qb.addField({
               "xtype": "hidden",
               "renderTo": elemId,
               "name": id,
               "value": propertyName
           });
   
           // The visible text field. The name has to be like the one of the hidden field above
           // plus the ".value" suffix.
           qb.addField({
               "xtype": "textfield",
               "renderTo": elemId,
               "name": id + ".value"
           });
   
           // Depending on the predicate additional parameters allow to configure the
           // predicate. Here we add an operation parameter to create a "like" query.
           // Again note the name set to the id and a suffix.
           qb.addField({
               "xtype": "hidden",
               "renderTo": elemId,
               "name": id + ".operation",
               "value": "like"
           });
   
       });
   
   </script>
   ```

1. Als u de component beschikbaar wilt maken, moet u deze kunnen bewerken. Een component bewerkbaar maken in CRXDE: een knooppunt toevoegen `cq:editConfig` van het primaire type `cq:EditConfig`. U kunt alinea&#39;s verwijderen door een eigenschap met meerdere waarden `cq:actions` met één waarde van **DELETE** toe te voegen.
1. Navigeer naar de browser en op de voorbeeldpagina (bijvoorbeeld `press.html`) overschakelen naar de ontwerpmodus en uw nieuwe component inschakelen voor het predikaat-alineasysteem (bijvoorbeeld **left**).

1. In **Bewerken** de nieuwe component is nu beschikbaar in de sidekick (in de **Zoeken** groep). De component invoegen in het dialoogvenster **Voorspellen** kolom en typ een zoekwoord, bijvoorbeeld **Ruitje** en klik op het vergrootglas om het zoeken te starten.

   >[!NOTE]
   >
   >Zorg er bij het zoeken voor dat u de term exact typt, inclusief het juiste hoofdlettergebruik.

### Voorbeeld: Een eenvoudige groepspreiding maken {#example-build-a-simple-group-predicate}

Om een groep te bouwen predikaat:

1. Maak bijvoorbeeld een componentmap in de projectmap `/apps/geometrixx/components/picspredicate`.
1. Toevoegen `content.xml`:

   ```xml
   <?xml version="1.0" encoding="UTF-8"?>
   <jcr:root xmlns:sling="https://sling.apache.org/jcr/sling/1.0"
    xmlns:cq="https://www.day.com/jcr/cq/1.0"
    xmlns:jcr="https://www.jcp.org/jcr/1.0"
       jcr:primaryType="cq:Component"
       jcr:title="Image Formats"
       sling:resourceSuperType="foundation/components/parbase"
       allowedParents="[*/parsys]"
       componentGroup="Search"/>
   ```

1. Toevoegen `titlepredicate.jsp`:

   ```java
   <%--
   
     Sample group predicate component
   
   --%><%@ page import="java.util.Calendar" %><%
   %><%@include file="/libs/foundation/global.jsp"%><%
   
       // A unique id is necessary in case this predicate is inserted multiple times on the same page.
       String elemId = "cq-predicate-" +  Long.toString(Calendar.getInstance().getTimeInMillis());
   
   %><div class="predicatebox">
   
       <div class="title">Image Formats</div>
   
       <%-- The wrapper for the form elements. All items will be append to this wrapper. --%>
       <div id="<%= elemId %>" class="content"></div>
   
   </div><script type="text/javascript">
   
       CQ.Ext.onLoad(function() {
   
           var predicateName = "property";
           var propertyName = "jcr:content/metadata/dc:format";
           var elemId = "<%= elemId %>";
   
           // Get the page wide available QueryBuilder.
           var qb = CQ.search.Util.getQueryBuilder();
   
           // Create a unique group ID; will return e.g. "1_group".
           var groupId = qb.createGroupId();
   
           // Hidden field that defines the property to search for  - in our case "dc:format" -
           // and declares the group of predicates. "property" in the name ("1_group.property")
           // indicates to the server to use the "property predicate"
           // (com.day.cq.search.eval.JcrPropertyPredicateEvaluator).
           qb.addField({
               "xtype": "hidden",
               "renderTo": "<%= elemId %>",
               "name": groupId + "." + predicateName, // 1_group.property
               "value": propertyName
           });
   
           // Declare to combine the multiple values using OR.
           qb.add(new CQ.Ext.form.Hidden({
               "name": groupId + ".p.or",  // 1_group.p.or
               "value": "true"
           }));
   
           // The options
           var options = [
               { "label":"JPEG", "value":"image/jpeg"},
               { "label":"PNG",  "value":"image/png" },
               { "label":"GIF",  "value":"image/gif" }
           ];
   
           // Build a checkbox for each option.
           for (var i = 0; i < options.length; i++) {
               qb.addField({
                   "xtype": "checkbox",
                   "renderTo": "<%= elemId %>",
                   // 1_group.property.0_value, 1_group.property.1_value etc.
                   "name": groupId + "." +  predicateName + "." + i + "_value",
                   "inputValue": options[i].value,
                   "boxLabel": options[i].label,
                   "listeners": {
                       "check": function() {
                           // Submit the search form when checking/unchecking a checkbox.
                           qb.submit();
                       }
                   }
               });
           }
   
       });
   ```

1. Als u de component beschikbaar wilt maken, moet u deze kunnen bewerken. Een component bewerkbaar maken in CRXDE: een knooppunt toevoegen `cq:editConfig` van het primaire type `cq:EditConfig`. U kunt alinea&#39;s verwijderen door een eigenschap met meerdere waarden `cq:actions` met één waarde van `DELETE` toe te voegen.
1. Navigeer naar de browser en op de voorbeeldpagina (bijvoorbeeld `press.html`) overschakelen naar de ontwerpmodus en uw nieuwe component inschakelen voor het predikaat-alineasysteem (bijvoorbeeld **left**).
1. In **Bewerken** de nieuwe component is nu beschikbaar in de sidekick (in de **Zoeken** groep). De component invoegen in het dialoogvenster **Voorspellen** kolom.

### Vooraf geïnstalleerde widgets {#installed-predicate-widgets}

De volgende voorspelling is beschikbaar als vooraf geconfigureerde ExtJS-widgets.

### FulltextPredicate {#fulltextpredicate}

| Eigenschap | Type | Beschrijving |
|---|---|---|
| predikaatName | String | Naam van de voorspelling. Standaardwaarden: `fulltext` |
| searchCallback | -functie | Callback voor het activeren van zoeken op gebeurtenis `keyup`. Standaardwaarden: `CQ.wcm.SiteAdmin.doSearch` |

### PropertyPredicate {#propertypredicate}

| Eigenschap | Type | Beschrijving |
|---|---|---|
| predikaatName | String | Naam van de voorspelling. Standaardwaarden: `property` |
| propertyName | String | Naam van de eigenschap JCR. Standaardwaarden: `jcr:title` |
| defaultValue | String | Standaardwaarde vooraf ingevuld. |

### PathPredicate {#pathpredicate}

| Eigenschap | Type | Beschrijving |
|---|---|---|
| predikaatName | String | Naam van de voorspelling. Standaardwaarden: `path` |
| rootPath | String | Hoofdpad van de voorspelling. Standaardwaarden: `/content/dam` |
| pathFieldPredicateName | String | Standaardwaarden: `folder` |
| showFlatOption | Boolean | Markering voor selectievakje `search in subfolders`. Heeft als standaardwaarde true. |

### DatePredicate {#datepredicate}

| Eigenschap | Type | Beschrijving |
|---|---|---|
| predikaatName | String | Naam van de voorspelling. Standaardwaarden: `daterange` |
| eigenschapsnaam | String | Naam van de eigenschap JCR. Standaardwaarden: `jcr:content/jcr:lastModified` |
| defaultValue | String | Vooraf ingestelde standaardwaarde |

### OptionsPredicate {#optionspredicate}

| Eigenschap | Type | Beschrijving |
|---|---|---|
| titel | String | Hiermee wordt een extra bovenste titel toegevoegd |
| predikaatName | String | Naam van de voorspelling. Standaardwaarden: `daterange` |
| eigenschapsnaam | String | Naam van de eigenschap JCR. Standaardwaarden: `jcr:content/metadata/cq:tags` |
| samenvouwen | String | Niveau samenvouwen. Standaardwaarden: `level1` |
| triggerSearch | Boolean | Markering voor het activeren van zoekopdrachten bij controle. Standaard ingesteld op false |
| searchCallback | -functie | Callback voor het teweegbrengen van onderzoek. Standaardwaarden: `CQ.wcm.SiteAdmin.doSearch` |
| searchTimeoutTime | Getal | Time-out voordat searchCallback wordt gestart. Wordt standaard ingesteld op 800 ms |

## Zoekresultaten aanpassen {#customizing-search-results}

De presentatie van zoekresultaten op een pagina voor het delen van bedrijfsmiddelen wordt bepaald door de geselecteerde lens. [!DNL Experience Manager] Elementen worden geleverd met een set vooraf gedefinieerde lenzen die kunnen worden gebruikt om een pagina voor het delen van elementen aan te passen. Op deze manier wordt een aandeel in activa aangepast in [Een pagina voor het delen van bedrijfsmiddelen maken en configureren](assets-finder-editor.md#creating-and-configuring-an-asset-share-page).

Naast het gebruik van reeds bestaande lenzen, [!DNL Experience Manager] ontwikkelaars kunnen ook hun eigen lenzen maken .
