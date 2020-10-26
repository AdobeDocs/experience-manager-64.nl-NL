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


# PUBLICEREN NIET, MAAR DELETE Aanpassen van modellen van inhoudsfragmenten niet{#do-not-publish-but-do-not-delete-customizing-content-fragment-models}

De redacteur van het Model van het Fragment van de Inhoud is een tovenaar die op wordt gebaseerd `Formbuilder`, van wordt geërft:

`granite/ui/components/foundation/form/formbuilder`

Deze component heeft de hulpmiddelen noodzakelijk om de belemmering en dalingsinterface van de modelredacteur terug te geven, volledig met gegevenstypes en eigenschappen voor elk.

## Locaties {#locations}

Modellen worden opgeslagen en gemaakt onder `/conf`een map waarin de eigenschap [Modellen](/help/assets/content-fragments-models.md#enable-content-fragment-models) inhoudsfragment is ingeschakeld. Dit plaatsen kan ook in de Eigenschappen **van de** Configuratie worden gezien, toegankelijk van Browser **[van de](/help/sites-administering/configurations.md)** Configuratie.

1. Navigeer naar de browser via **Hulpmiddelen**, **Algemeen**, Browser **van de** Configuratie bijvoorbeeld, 
`http://localhost:4502/libs/granite/configurations/content/view.html/conf`

1. Selecteer in de browser de gewenste configuratie en kies vervolgens **Eigenschappen** op de werkbalk.

   Bijvoorbeeld de eigenschappen voor `global`: `http://localhost:4502/libs/granite/configurations/content/edit.html/conf/global`

In de modelconsole, zullen alle omslagen met het bezit van Modellen **van het Fragment van de** Inhoud verschijnen. Navigeer via **gereedschappen**, **elementen**, **inhoudsfragmentmodellen**; bijvoorbeeld `http://localhost:4502/libs/dam/cfm/models/console/content/models.html/conf`.

Een gebruiker kan een model [van het inhoudsfragment](/help/assets/content-fragments-models.md#creating-a-content-fragment-model) tot stand brengen gebruikend **Create Model** tovenaar (gebruikend **Create** van de console).

>[!CAUTION]
>
>U ***mag*** niets in het `/libs` pad wijzigen.
>
>De reden hiervoor is dat de inhoud van `/libs` de volgende keer dat u een upgrade uitvoert van de instantie, wordt overschreven (en dat deze kan worden overschreven wanneer u een hotfix- of functiepakket toepast).

## Structuur van een model {#structure-of-a-model}

De wizard maakt een bericht met deze structuur:

![cf-54](assets/cf-54.png)

* `../settings/dam/cfm/models`

   Alle modellen worden opgeslagen onder submappen van deze map.

* `jcr:content`

   Elk model bevat een `jcr:content` knooppunt:

   * bevat informatie-eigenschappen over het model, zoals `jcr:title`, `lastModified``lastModifiedBy`
   * gewoonlijk de `sling:ResourceType` van `dam/cfm/models/console/components/data/entity/default`,

      met `sling:ResourceSuperType` de `dam/cfm/models/console/components/data/entity`

* `model`

   Het `model` knooppunt bevat een eigenschap `dataTypesConfig`die wordt gebruikt om de gegevenstypen te bepalen die in de modeleditor worden gebruikt.

* `items`

   Onder de `items` knoop, worden alle gegevenstypes die aan het model worden toegevoegd bewaard (zoals gesleept en in de modelredacteur gelaten vallen). Elk item krijgt een willekeurige knooppuntnaam, maar voor de inhoudsfragmenteditor moet elk item een `name` eigenschap hebben. Bovendien, op deze knoop, worden alle configuratieeigenschappen voor een bepaald gegevenstype bewaard, met inbegrip van standaardeigenschappen nodig om de componenten terug te geven.

>[!CAUTION]
>
>Alle gegevenstypes die in een modelredacteur worden gesleept en worden gelaten vallen, en als dergelijke geconcretiseerd, **moeten** de `name` bezitsinput door de gebruiker hebben.
>
>Dit wordt gezien als **Eigenschapnaam&amp;ast;** op het tabblad **Eigenschappen** van de modeleditor.

## Structuur van de modeleditor {#structure-of-the-model-editor}

De Editor **van het** inhoudsfragmentmodel bestaat uit twee delen:

* In het voorvertoningsvenster of de weergave aan de linkerkant kunt u items neerzetten. Dit:

   * Toont een voorproef van het Type **van** Gegevens dat wordt geconcretiseerd.
   * Bevoegdheden voor bestellen in de modeleditor.

* De tabbladen **Gegevenstypen**/**Eigenschappen** in het deelvenster aan de rechterkant. Dit:

   * Toont een lijst van gegevenstypes die kunnen worden gesleept en worden geconcretiseerd.
   * Voor de uit-van-de-doos modelredacteur is de lijst aanwezig bij:

      `/libs/settings/dam/cfm/models/formbuilderconfig/datatypes`

      <!-- Please uncomment when file is used
      This node contains all the data types currently supported in the model editor. For more information on how to configure the data types, see [Customizing Data Types for Content Fragment Models](/help/sites-developing/customizing-content-fragment-model-data-types.md).
      -->

   * Alle teruggegeven gegevenstypes hebben twee manuscriptmarkeringen die, wanneer geconcretiseerd, de mening (de component die op de linkerkant wordt teruggegeven) en het lusje van **Eigenschappen** zullen vormen, die de eigenschappen bepaalt die een gebruiker voor een bepaalde component kan bepalen.

>[!CAUTION]
>
>U ***mag*** niets in het `/libs` pad wijzigen.
>
>De reden hiervoor is dat de inhoud van `/libs` de volgende keer dat u een upgrade uitvoert van uw exemplaar, wordt overschreven (en dat deze kan worden overschreven wanneer u een hotfix- of functiepakket toepast).

<!-- Please uncomment when files are used
The properties on the right side define a form that is submitted directly into JCR under `/conf`; see the path in the example [Structure of a Model](/help/sites-developing/customizing-content-fragment-models.md#structure-of-a-model).
-->

Wanneer een gegevenstype wordt geconcretiseerd, worden de input van HTML gecreeerd voor elke bezit de component in een inhoudsfragment moet worden teruggegeven. Dit zijn bijvoorbeeld:

* **Eigenschapnaam&amp;ast;** ( `name`) - fungeert als id voor componenten

* **Renderen als** ( `metaType`) - typ de component als moet worden gerenderd

* **Beschrijving** ( `fieldDescription`) - beschrijving van de component in het inhoudsfragment

* en andere.

