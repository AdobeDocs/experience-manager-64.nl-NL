---
title: PUBLICEREN NIET, MAAR DELETE Aanpassen van modellen van inhoudsfragmenten niet
seo-title: Modellen voor inhoudsfragmenten aanpassen
description: Modellen voor inhoudsfragmenten kunnen worden aangepast en uitgebreid.
seo-description: Modellen voor inhoudsfragmenten kunnen worden aangepast en uitgebreid.
page-status-flag: de-activated
uuid: 5bcfb5d8-37d4-4a0e-882d-bc8a1bac6ba7
contentOwner: aheimoz
discoiquuid: 208225ee-9052-4a45-9cfd-f8d27d4d70ed
noindex: true
translation-type: tm+mt
source-git-commit: b61c20c65ceade0153f5cd04fbedfd02e919d483
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 0%

---


# PUBLICEREN NIET, MAAR DELETE Aanpassen van modellen van inhoudsfragmenten{#do-not-publish-but-do-not-delete-customizing-content-fragment-models} NIET

De redacteur van het Model van het Fragment van de Inhoud is een tovenaar die op `Formbuilder` wordt gebaseerd, van wordt geërft:

`granite/ui/components/foundation/form/formbuilder`

Deze component heeft de hulpmiddelen noodzakelijk om de belemmering en dalingsinterface van de modelredacteur terug te geven, volledig met gegevenstypes en eigenschappen voor elk.

## Locaties {#locations}

Modellen worden opgeslagen en gemaakt onder `/conf`, in een map waarin de eigenschap [Content Fragment Models property](/help/assets/content-fragments-models.md#enable-content-fragment-models) is ingeschakeld. Deze instelling kan ook worden weergegeven in de **Configuration Properties**, die toegankelijk is via de **[Configuration Browser](/help/sites-administering/configurations.md)**.

1. Navigeer naar de browser via **Tools**, **General**, **Configuration Browser**
Bijvoorbeeld: 
`http://localhost:4502/libs/granite/configurations/content/view.html/conf`

1. Selecteer in de browser de juiste configuratie en **Eigenschappen** in de werkbalk.

   Bijvoorbeeld de eigenschappen voor `global`: `http://localhost:4502/libs/granite/configurations/content/edit.html/conf/global`

In de modelconsole, zullen alle omslagen met het **bezit van Modellen van het Fragment** verschijnen. Navigeer via **Tools**, **Assets**, **Content Fragment Models**; bijvoorbeeld `http://localhost:4502/libs/dam/cfm/models/console/content/models.html/conf`.

Een gebruiker kan een model van het inhoudsfragment [tot stand brengen ](/help/assets/content-fragments-models.md#creating-a-content-fragment-model) gebruikend **Model** tovenaar creëren (gebruikend **Create** van de console).

>[!CAUTION]
>
>U ***must*** verandert niets in `/libs` weg.
>
>Dit komt doordat de inhoud van `/libs` de volgende keer wordt overschreven dat u uw exemplaar bijwerkt (en kan worden overschreven wanneer u een hotfix of functiepakket toepast).

## Structuur van een model {#structure-of-a-model}

De wizard maakt een bericht met deze structuur:

![cf-54](assets/cf-54.png)

* `../settings/dam/cfm/models`

   Alle modellen worden opgeslagen onder submappen van deze map.

* `jcr:content`

   Elk model bevat een `jcr:content` knoop die:

   * bevat informatie-eigenschappen over het model, zoals `jcr:title`, `lastModified`, `lastModifiedBy`
   * heeft gewoonlijk de `sling:ResourceType` van `dam/cfm/models/console/components/data/entity/default`,

      met de `sling:ResourceSuperType` van `dam/cfm/models/console/components/data/entity`

* `model`

   De `model` knoop bevat een bezit `dataTypesConfig`, die wordt gebruikt om de gegevenstypes te bepalen die in de modelredacteur worden gebruikt.

* `items`

   Onder de `items` knoop, worden alle gegevenstypes die aan het model worden toegevoegd bewaard (zoals gesleept en in de modelredacteur gelaten vallen). Elk punt wordt gegeven een willekeurige knoopnaam, maar opdat de redacteur van het inhoudsfragment met dit model kan werken, moet elk punt een `name` bezit hebben. Bovendien, op deze knoop, worden alle configuratieeigenschappen voor een bepaald gegevenstype bewaard, met inbegrip van standaardeigenschappen nodig om de componenten terug te geven.

>[!CAUTION]
>
>Alle gegevenstypes werden gesleept en in een modelredacteur gelaten vallen, en als dusdanig geconcretiseerd, **must** hebben de `name` bezitsinput door de gebruiker.
>
>Dit wordt gezien als **Naam van eigenschap &amp;ast;** in **Eigenschappen** lusje van modelredacteur.

## Structuur van de modeleditor {#structure-of-the-model-editor}

De **Inhoudsfragmentmodeleditor** bestaat uit twee delen:

* In het voorvertoningsvenster of de weergave aan de linkerkant kunt u items neerzetten. Dit:

   * Toont een voorproef van **Gegevenstype** dat wordt geconcretiseerd.
   * Bevoegdheden voor bestellen in de modeleditor.

* De tabbladen **Gegevenstypen**/**Eigenschappen** in het deelvenster aan de rechterkant. Dit:

   * Toont een lijst van gegevenstypes die kunnen worden gesleept en worden geconcretiseerd.
   * Voor de uit-van-de-doos modelredacteur is de lijst aanwezig bij:

      `/libs/settings/dam/cfm/models/formbuilderconfig/datatypes`

      <!-- Please uncomment when file is used
      This node contains all the data types currently supported in the model editor. For more information on how to configure the data types, see [Customizing Data Types for Content Fragment Models](/help/sites-developing/customizing-content-fragment-model-data-types.md).
      -->

   * Alle teruggegeven gegevenstypes hebben twee manuscriptmarkeringen die, wanneer geconcretiseerd, de mening (de component die op de linkerkant wordt teruggegeven) en **Eigenschappen** tabel zullen vormen, die de eigenschappen bepaalt die een gebruiker voor een bepaalde component kan bepalen.

>[!CAUTION]
>
>U ***must*** verandert niets in `/libs` weg.
>
>Dit komt doordat de inhoud van `/libs` de volgende keer wordt overschreven dat u uw exemplaar bijwerkt (en kan worden overschreven wanneer u een hotfix of functiepakket toepast).

<!-- Please uncomment when files are used
The properties on the right side define a form that is submitted directly into JCR under `/conf`; see the path in the example [Structure of a Model](/help/sites-developing/customizing-content-fragment-models.md#structure-of-a-model).
-->

Wanneer een gegevenstype wordt geconcretiseerd, worden de input van HTML gecreeerd voor elke bezit de component in een inhoudsfragment moet worden teruggegeven. Dit zijn bijvoorbeeld:

* **Eigenschapnaam &amp;index;** (  `name`) - fungeert als id voor componenten

* **Renderen als** (  `metaType`) - typ de component als moet worden gerenderd

* **Beschrijving** (  `fieldDescription`) - beschrijving van de component in het inhoudsfragment

* en andere.

