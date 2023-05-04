---
title: Zoeken
seo-title: Search
description: De auteursomgeving van AEM verstrekt diverse mechanismen om naar inhoud te zoeken, afhankelijk van het middeltype.
seo-description: The author environment of AEM provides various mechanisms for searching for content, dependent on the resource type.
uuid: b50c8144-1993-441d-8303-fcb6b0f24376
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: introduction
content-type: reference
discoiquuid: b20e0f78-9ae4-47ba-8e9a-452a0a78b663
exl-id: 9c1d8969-6aa6-41b9-a797-3e6431475fc6
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 0%

---

# Zoeken{#search-features}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

De auteursomgeving van AEM verstrekt diverse mechanismen om naar inhoud te zoeken, afhankelijk van het middeltype.

>[!NOTE]
>
>Buiten de auteursomgeving zijn andere mechanismen ook beschikbaar voor het zoeken, zoals [Query Builder](/help/sites-developing/querybuilder-api.md) en [CRXDE Lite](/help/sites-developing/developing-with-crxde-lite.md).

## Grondbeginselen van zoekopdrachten {#search-basics}

Als u het deelvenster Zoeken wilt openen, klikt u op de knop **Zoeken** aan de bovenkant van de linkerruit van de aangewezen console.

![chlimage_1-140](assets/chlimage_1-140.png)

Met het deelvenster Zoeken kunt u al uw websitepagina&#39;s doorzoeken. Het bevat velden en widgets voor het volgende:

* **Fulltext**: Zoeken naar de opgegeven tekst
* **Gewijzigd na/vóór**: Alleen de pagina&#39;s zoeken die zijn gewijzigd tussen de specifieke datums
* **Sjabloon**: Alleen die pagina&#39;s zoeken op basis van de opgegeven sjabloon
* **Tags**: Alleen de pagina&#39;s met de opgegeven tags doorzoeken

>[!NOTE]
>
>Wanneer uw instantie wordt gevormd voor [Lucene-zoekopdracht](/help/sites-deploying/queries-and-indexing.md) u kunt de volgende opties gebruiken in **Fulltext**:
>
>* [Jokertekens](https://lucene.apache.org/core/5_3_1/queryparser/org/apache/lucene/queryparser/classic/package-summary.html#Wildcard_Searches)
>* [Booleaanse operatoren](https://lucene.apache.org/core/5_3_1/queryparser/org/apache/lucene/queryparser/classic/package-summary.html#Boolean_operators)
>
>* [Reguliere expressies](https://lucene.apache.org/core/5_3_1/queryparser/org/apache/lucene/queryparser/classic/package-summary.html#Regexp_Searches)
>* [Veldgroepering](https://lucene.apache.org/core/5_3_1/queryparser/org/apache/lucene/queryparser/classic/package-summary.html#Field_Grouping)
>* [Verhogen](https://lucene.apache.org/core/5_3_1/queryparser/org/apache/lucene/queryparser/classic/package-summary.html#Boosting_a_Term)
>


De zoekopdracht uitvoeren door op **Zoeken** onder aan het deelvenster. Klikken **Herstellen** de zoekcriteria te wissen.

## Filter {#filter}

Op verschillende locaties kan een filter worden ingesteld (en gewist) om de weergave omlaag te doorlopen en te verfijnen:

![chlimage_1-141](assets/chlimage_1-141.png)

## Zoeken en vervangen {#find-and-replace}

In de **Websites** console a **Zoeken en vervangen** kunt u in een sectie van de website naar meerdere instanties van een tekenreeks zoeken en deze vervangen.

1. Selecteer de hoofdpagina, of map, waar de zoek- en vervangactie moet plaatsvinden.
1. Selecteren **Gereedschappen** dan **Zoeken en vervangen**:

   ![screen_shot_2012-02-15at120346pm](assets/screen_shot_2012-02-15at120346pm.png)

1. De **Zoeken en vervangen** wordt het volgende uitgevoerd:

   * bevestigt het hoofdpad waar de zoekactie moet beginnen
   * definieert de term die moet worden gevonden
   * bepaalt de termijn die het moet vervangen
   * Hiermee wordt aangegeven of de zoekopdracht hoofdlettergevoelig moet zijn
   * Hiermee wordt aangegeven of alleen hele woorden moeten worden gevonden (anders worden ook subtekenreeksen gevonden)

   Klikken **Voorvertoning** lijsten waarin de term is gevonden. U kunt specifieke te vervangen exemplaren selecteren/wissen:

   ![screen_shot_2012-02-15at120719pm](assets/screen_shot_2012-02-15at120719pm.png)

1. Klikken **Vervangen** om alle instanties daadwerkelijk te vervangen. U wordt gevraagd de actie te bevestigen.

Het standaardwerkingsgebied voor het vondst en vervangt servlet behandelt de volgende eigenschappen:

* `jcr:title`
* `jcr:description`
* `jcr:text`
* `text`

Het bereik kan worden gewijzigd met de Apache Felix Web Management Console (bijvoorbeeld bij `http://localhost:4502/system/console/configMgr`). Selecteren `CQ WCM Find Replace Servlet (com.day.cq.wcm.core.impl.servlets.FindReplaceServlet)` en configureer het bereik naar wens.

>[!NOTE]
>
>In een standaardinstallatie AEM vindt en vervangt het gebruik van Lucene voor de zoekfunctionaliteit.
>
>Lucene indexeert tekenreekseigenschappen met een lengte van maximaal 16 k. Tekenreeksen die dit overschrijden, worden niet doorzocht.
