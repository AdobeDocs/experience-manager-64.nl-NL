---
title: PUBLICEREN NIET, MAAR DELETE Aanpassen van modellen van inhoudsfragmenten niet
seo-title: Customizing Content Fragment Models
description: Modellen voor inhoudsfragmenten kunnen worden aangepast en uitgebreid.
seo-description: Content Fragment Models can be customized and extended.
page-status-flag: de-activated
uuid: 5bcfb5d8-37d4-4a0e-882d-bc8a1bac6ba7
contentOwner: AEM Docs
discoiquuid: 208225ee-9052-4a45-9cfd-f8d27d4d70ed
noindex: true
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '622'
ht-degree: 0%

---


# PUBLICEREN NIET, MAAR DELETE Aanpassen van modellen van inhoudsfragmenten niet{#do-not-publish-but-do-not-delete-customizing-content-fragment-models}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

De editor van het inhoudsfragmentmodel is een wizard op basis van `Formbuilder`, overgenomen van:

`granite/ui/components/foundation/form/formbuilder`

Deze component heeft de hulpmiddelen noodzakelijk om de belemmering en dalingsinterface van de modelredacteur terug te geven, volledig met gegevenstypes en eigenschappen voor elk.

## Locaties {#locations}

Modellen worden opgeslagen en gemaakt onder `/conf`, onder een map met de [Content Fragment Models, eigenschap](/help/assets/content-fragments-models.md#enable-content-fragment-models) ingeschakeld. Deze instelling is ook zichtbaar in het dialoogvenster **Configuratieeigenschappen**, toegankelijk via de **[Configuratiebrowser](/help/sites-administering/configurations.md)**.

1. Navigeren naar de browser via **Gereedschappen**, **Algemeen**, **Configuratiebrowser**
Bijvoorbeeld: 
`http://localhost:4502/libs/granite/configurations/content/view.html/conf`

1. Selecteer in de browser de gewenste configuratie en **Eigenschappen** op de werkbalk.

   De eigenschappen voor `global`: `http://localhost:4502/libs/granite/configurations/content/edit.html/conf/global`

In de modelconsole, alle omslagen met **Modellen van inhoudsfragmenten** wordt weergegeven. Navigeren via **Gereedschappen**, **Activa**, **Modellen van inhoudsfragmenten**; bijvoorbeeld: `http://localhost:4502/libs/dam/cfm/models/console/content/models.html/conf`.

Een gebruiker kan [een inhoudsfragmentmodel maken](/help/assets/content-fragments-models.md#creating-a-content-fragment-model) met de **Model maken** wizard (gebruiken **Maken** vanaf de console).

>[!CAUTION]
>
>U ***moet*** niets wijzigen in de `/libs` pad.
>
>Dit komt omdat de inhoud van `/libs` wordt de volgende keer overschreven dat u een upgrade uitvoert van uw exemplaar (en kan worden overschreven wanneer u een hotfix- of functiepakket toepast).

## Structuur van een model {#structure-of-a-model}

De wizard maakt een bericht met deze structuur:

![cf-54](assets/cf-54.png)

* `../settings/dam/cfm/models`

   Alle modellen worden opgeslagen onder submappen van deze map.

* `jcr:content`

   Elk model bevat een `jcr:content` knooppunt dat:

   * bevat informatie-eigenschappen over het model, zoals `jcr:title`, `lastModified`, `lastModifiedBy`
   * heeft meestal de `sling:ResourceType` van `dam/cfm/models/console/components/data/entity/default`,

      met de `sling:ResourceSuperType` van `dam/cfm/models/console/components/data/entity`

* `model`

   De `model` node contains a property `dataTypesConfig`, gebruikt om de gegevenstypen te bepalen die in de modeleditor worden gebruikt.

* `items`

   Onder de `items` alle gegevenstypen die aan het model zijn toegevoegd, worden opgeslagen (zoals gesleept en neergezet in de modeleditor). Elk item krijgt een willekeurige knooppuntnaam, maar de inhoudfragmenteditor kan alleen met dit model werken als elk item een `name` eigenschap. Bovendien, op deze knoop, worden alle configuratieeigenschappen voor een bepaald gegevenstype bewaard, met inbegrip van standaardeigenschappen nodig om de componenten terug te geven.

>[!CAUTION]
>
>Alle gegevenstypen zijn gesleept en neergezet in een modeleditor en als zodanig geïnstantieerd, **moet** de `name` eigenschapsinvoer door de gebruiker.
>
>Dit wordt gezien als **Eigenschapnaam&amp;st;** in de **Eigenschappen** tabblad van modeleditor.

## Structuur van de modeleditor {#structure-of-the-model-editor}

De **Inhoudsfragmentmodeleditor** heeft twee delen:

* In het voorvertoningsvenster of de weergave aan de linkerkant kunt u items neerzetten. Dit:

   * Toont een voorproef van **Gegevenstype** dat wordt geïnstantieerd.
   * Bevoegdheden voor bestellen in de modeleditor.

* De **Gegevenstypen**/**Eigenschappen** in het deelvenster aan de rechterkant. Dit:

   * Toont een lijst van gegevenstypes die kunnen worden gesleept en worden geconcretiseerd.
   * Voor de uit-van-de-doos modelredacteur is de lijst aanwezig bij:

      `/libs/settings/dam/cfm/models/formbuilderconfig/datatypes`

      <!-- Please uncomment when file is used
      This node contains all the data types currently supported in the model editor. For more information on how to configure the data types, see [Customizing Data Types for Content Fragment Models](/help/sites-developing/customizing-content-fragment-model-data-types.md).
      -->

   * Alle gerenderde gegevenstypen hebben twee scripttags die, wanneer ze worden geïnstantieerd, de weergave (de component die aan de linkerkant wordt gerenderd) en de **Eigenschappen** , die de eigenschappen definieert die een gebruiker voor een bepaalde component kan definiëren.

>[!CAUTION]
>
>U ***moet*** niets wijzigen in de `/libs` pad.
>
>Dit komt omdat de inhoud van `/libs` wordt de volgende keer overschreven dat u een upgrade uitvoert van uw exemplaar (en kan worden overschreven wanneer u een hotfix- of functiepakket toepast).

<!-- Please uncomment when files are used
The properties on the right side define a form that is submitted directly into JCR under `/conf`; see the path in the example [Structure of a Model](/help/sites-developing/customizing-content-fragment-models.md#structure-of-a-model).
-->

Wanneer een gegevenstype wordt geconcretiseerd, worden de input van HTML gecreeerd voor elke bezit de component in een inhoudsfragment moet worden teruggegeven. Dit zijn bijvoorbeeld:

* **Eigenschapnaam&amp;st;** ( `name`) - fungeert als id voor componenten

* **Renderen als** ( `metaType`) - typ de component die moet worden gerenderd als

* **Beschrijving** ( `fieldDescription`) - beschrijving van de component in het inhoudsfragment

* en andere.

