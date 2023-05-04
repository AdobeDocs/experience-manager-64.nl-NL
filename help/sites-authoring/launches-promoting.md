---
title: Lanceringen promoten
seo-title: Promoting Launches
description: U moet opstartiepagina's promoten om de inhoud vóór publicatie weer naar de bron (productie) te verplaatsen.
seo-description: You need to promote launch pages to move the content back into the source (production) before publishing.
uuid: 56483f8f-d66e-4677-a7bd-3b1425625b2b
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: site-features
discoiquuid: 977a3dda-4292-4bd2-bfa5-af4d789d9ef9
legacypath: /content/docs/en/aem/6-0/author/site-page-features/launches
exl-id: 2a790f7d-03a1-4f60-a59e-0a5f15c44fa5
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '759'
ht-degree: 1%

---

# Lanceringen promoten{#promoting-launches}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

U moet opstartiepagina&#39;s promoten om de inhoud vóór publicatie weer naar de bron (productie) te verplaatsen. Wanneer een startpagina wordt bevorderd, wordt de bijbehorende pagina van de bronpagina&#39;s vervangen door de inhoud van de gepromoveerde pagina. De volgende opties zijn beschikbaar bij het promoten van een startpagina:

* Of alleen de huidige pagina of de volledige lancering wordt bevorderd.
* Of de onderliggende pagina&#39;s van de huidige pagina worden bevorderd.
* Of de volledige lancering of slechts pagina&#39;s wordt bevorderd die zijn veranderd.

>[!NOTE]
>
>Nadat u de startpagina&#39;s naar het doel hebt opgewaardeerd (**Productie**), kunt u de **Productie** pagina&#39;s als een entiteit (om het proces sneller te maken). Voeg de pagina&#39;s toe aan een workflowpakket en gebruik dit als de payload voor een workflow die een pakket met pagina&#39;s activeert. U moet het workflowpakket maken voordat u de introductie kunt promoten. Zie [Promotiepagina&#39;s verwerken met AEM workflow](#processing-promoted-pages-using-aem-workflow).

>[!CAUTION]
>
>Een enkele lancering kan niet tegelijkertijd worden bevorderd. Dit betekent dat twee promotieacties tegelijk op dezelfde start kunnen leiden tot een fout - `Launch could not be promoted` (samen met conflictfouten in het logbestand).

>[!CAUTION]
>
>Bij het promoten van introducties voor *gewijzigd* pagina&#39;s, wordt rekening gehouden met wijzigingen in zowel de bron- als startvertakkingen.

## Startpagina&#39;s promoten {#promoting-launch-pages}

>[!NOTE]
>
>Dit omvat de handmatige actie van het bevorderen van lanceringspagina&#39;s wanneer er slechts één lanceringsniveau is. Zie:
>
>* [Een geneste start bevorderen](#promoting-a-nested-launch) wanneer de structuur meer dan één keer wordt gestart.
>* [Starten - de volgorde van gebeurtenissen](/help/sites-authoring/launches.md#launches-the-order-of-events) voor meer informatie over automatische promotie en publicatie.
>


U kunt lanceringen van één van beide bevorderen **Sites** of de **Starten** console:

1. Open:

   * de **Sites** console:

      1. Open de [referentie-rail](/help/sites-authoring/author-environment-tools.md#references) en selecteert u de gewenste bronpagina met [selectiemodus](/help/sites-authoring/basic-handling.md) (of selecteer en open de referentie-rail, de volgorde is niet belangrijk). Alle verwijzingen worden weergegeven.

      1. Selecteren **Starten** (bv. Startpagina&#39;s (1)) om een lijst weer te geven met de specifieke lanceringen.
      1. Selecteer de specifieke lancering om de beschikbare acties te tonen.
      1. Selecteren **Starten bevorderen** om de wizard te openen.
   * de **Starten** console:

      1. Selecteer de start (tik op de miniatuur of klik erop).
      1. Selecteren **Bevorderen**.


1. In de eerste stap kunt u het volgende opgeven:

   * **Volledige introductie bevorderen**
   * **Gewijzigde pagina&#39;s promoten**
   * **Huidige pagina promoten**
   * **Huidige pagina en subpagina&#39;s promoten**

   Als u bijvoorbeeld alleen gewijzigde pagina&#39;s wilt promoten:

   ![chlimage_1](assets/chlimage_1.png)

   >[!NOTE]
   >
   >Dit geldt voor één keer starten, als u geneste lanceringen hebt, zie [Een geneste start bevorderen](#promoting-a-nested-launch).

1. Selecteren **Volgende** om verder te gaan.
1. U kunt de pagina&#39;s bekijken die u wilt promoten. Deze zijn afhankelijk van het gekozen paginabereik:

   ![chlimage_1-1](assets/chlimage_1-1.png)

1. Selecteren **Bevorderen**.

## Starten van pagina&#39;s tijdens bewerken bevorderen {#promoting-launch-pages-when-editing}

Wanneer u een startpagina bewerkt, wordt **Starten bevorderen** actie is ook beschikbaar via **Pagina-informatie**. Hierdoor wordt de wizard geopend die de benodigde informatie verzamelt.

![chlimage_1-2](assets/chlimage_1-2.png)

>[!NOTE]
>
>Dit is beschikbaar voor enkelvoudig en [geneste lanceringen](#promoting-a-nested-launch).

## Een geneste start bevorderen {#promoting-a-nested-launch}

Nadat u een geneste start hebt gemaakt, kunt u deze herstellen naar een van de bronnen, inclusief de hoofdbron (productie).

![chlimage_1-3](assets/chlimage_1-3.png)

1. Zoals met [Een geneste start maken](/help/sites-authoring/launches-creating.md#creating-a-nested-launch), navigeer naar en selecteer de vereiste start in een van de **Starten** of de **Verwijzingen** spoorwegen.
1. Selecteren **Starten bevorderen** om de wizard te openen.

1. Voer de vereiste gegevens in:

   * **Promotiedoel**

      U kunt een van de bronnen promoten.

   * **Toepassingsgebied**
Hier kunt u kiezen of u de volledige opstart wilt bevorderen of alleen pagina&#39;s die daadwerkelijk zijn bewerkt. In het laatste geval kunt u opgeven of u subpagina&#39;s wilt opnemen of uitsluiten. De standaardconfiguratie is dat alleen paginawijzigingen voor de huidige pagina worden bevorderd:

      * **Volledige introductie bevorderen**
      * **Gewijzigde pagina&#39;s promoten**
      * **Huidige pagina promoten**
      * **Huidige pagina en subpagina&#39;s promoten**

   ![chlimage_1-4](assets/chlimage_1-4.png)

1. Selecteren **Volgende**.
1. De details van de aanbieding bekijken voordat je de selectie maakt **Bevorderen**:

   ![chlimage_1-5](assets/chlimage_1-5.png)

   >[!NOTE]
   >
   >De weergegeven pagina&#39;s zijn afhankelijk van de **Toepassingsgebied** gedefinieerde en mogelijk de pagina&#39;s die daadwerkelijk zijn bewerkt.

1. Uw wijzigingen worden bevorderd en weerspiegeld in de **Starten** console:

   ![chlimage_1-6](assets/chlimage_1-6.png)

## Promotiepagina&#39;s verwerken met AEM-workflow {#processing-promoted-pages-using-aem-workflow}

Gebruik workflowmodellen voor bulkverwerking van geconverteerde startpagina&#39;s:

1. Maak een workflowpakket.
1. Wanneer auteurs startpagina&#39;s promoten, slaan ze deze op in het workflowpakket.
1. Start een workflowmodel met het pakket als de payload.

Als u automatisch een workflow wilt starten wanneer pagina&#39;s worden geconverteerd, [configureren van een workflow](/help/sites-administering/workflows-starting.md#workflows-launchers) voor het pakketknooppunt.

U kunt bijvoorbeeld automatisch aanvragen voor paginanactivering genereren wanneer auteurs pagina&#39;s starten promoten. Configureer een werkstroomstartprogramma om de workflow voor activering van aanvragen te starten wanneer het pakketknooppunt wordt gewijzigd.

![chlimage_1-7](assets/chlimage_1-7.png)
