---
title: Lanceringen promoten
seo-title: Lanceringen promoten
description: 'U moet opstartiepagina''s promoten om de inhoud vóór publicatie weer naar de bron (productie) te verplaatsen. '
seo-description: 'U moet opstartiepagina''s promoten om de inhoud vóór publicatie weer naar de bron (productie) te verplaatsen. '
uuid: 56483f8f-d66e-4677-a7bd-3b1425625b2b
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: site-features
discoiquuid: 977a3dda-4292-4bd2-bfa5-af4d789d9ef9
legacypath: /content/docs/en/aem/6-0/author/site-page-features/launches
translation-type: tm+mt
source-git-commit: cdec5b3c57ce1c80c0ed6b5cb7650b52cf9bc340
workflow-type: tm+mt
source-wordcount: '742'
ht-degree: 1%

---


# Lanceringen promoten{#promoting-launches}

U moet opstartiepagina&#39;s promoten om de inhoud vóór publicatie weer naar de bron (productie) te verplaatsen. Wanneer een startpagina wordt bevorderd, wordt de bijbehorende pagina van de bronpagina&#39;s vervangen door de inhoud van de gepromoveerde pagina. De volgende opties zijn beschikbaar bij het promoten van een startpagina:

* Of alleen de huidige pagina of de volledige lancering wordt bevorderd.
* Of de onderliggende pagina&#39;s van de huidige pagina worden bevorderd.
* Of de volledige lancering of slechts pagina&#39;s wordt bevorderd die zijn veranderd.

>[!NOTE]
>
>Nadat u de startpagina&#39;s naar het doel hebt opgewaardeerd (**Productie**), kunt u de **Productiepagina** &#39;s activeren als een entiteit (om het proces sneller te maken). Voeg de pagina&#39;s toe aan een workflowpakket en gebruik dit als de payload voor een workflow die een pakket met pagina&#39;s activeert. U moet het workflowpakket maken voordat u de introductie kunt promoten. See [Processing Promoted Pages Using AEM Workflow](#processing-promoted-pages-using-aem-workflow).

>[!CAUTION]
>
>Een enkele lancering kan niet tegelijkertijd worden bevorderd. Dit betekent dat twee promotieacties bij dezelfde introductie tegelijkertijd kunnen resulteren in een fout - `Launch could not be promoted` (samen met conflictfouten in het logbestand).

>[!CAUTION]
>
>Bij het promoten van startpagina&#39;s voor *gewijzigde* pagina&#39;s wordt rekening gehouden met wijzigingen in zowel de bron- als startvertakkingen.

## Startpagina&#39;s promoten {#promoting-launch-pages}

>[!NOTE]
>
>Dit omvat de handmatige actie van het bevorderen van lanceringspagina&#39;s wanneer er slechts één lanceringsniveau is. Zie:
>
>* [Een geneste start](#promoting-a-nested-launch) bevorderen wanneer de structuur meerdere keren is gestart.
>* [Launches - De Orde van Gebeurtenissen](/help/sites-authoring/launches.md#launches-the-order-of-events) voor meer informatie over automatische bevordering en publicatie.

>



U kunt lanceringen van of de console van **Plaatsen** of de console van **Lanceringen** bevorderen:

1. Open:

   * de **Sites** -console:

      1. Open de [referentieslegel](/help/sites-authoring/author-environment-tools.md#references) en selecteer de vereiste bronpagina in de [selectiemodus](/help/sites-authoring/basic-handling.md) (of selecteer en open de referentieslegel, de volgorde is niet belangrijk). Alle verwijzingen worden weergegeven.

      1. Selecteer **Starten** (bijvoorbeeld Starten (1)) om een lijst van de specifieke lanceringen te tonen.
      1. Selecteer de specifieke lancering om de beschikbare acties te tonen.
      1. Selecteer Starten **bevorderen** om de wizard te openen.
   * de **Startconsole** :

      1. Selecteer de start (tik op de miniatuur of klik erop).
      1. Selecteer **Promoten**.


1. In de eerste stap kunt u het volgende opgeven:

   * **Volledige introductie bevorderen**
   * **Gewijzigde pagina&#39;s promoten**
   * **Huidige pagina promoten**
   * **Huidige pagina en subpagina&#39;s promoten**

   Als u bijvoorbeeld alleen gewijzigde pagina&#39;s wilt promoten:

   ![chlimage_1](assets/chlimage_1.png)

   >[!NOTE]
   >
   >Dit geldt voor één keer starten. Zie Een geneste [start](#promoting-a-nested-launch)bevorderen als u geneste introducties hebt.

1. Selecteer **Volgende** om door te gaan.
1. U kunt de pagina&#39;s bekijken die u wilt promoten. Deze zijn afhankelijk van het gekozen paginabereik:

   ![chlimage_1-1](assets/chlimage_1-1.png)

1. Selecteer **Promoten**.

## Starten van pagina&#39;s tijdens bewerken bevorderen {#promoting-launch-pages-when-editing}

Wanneer u een startpagina bewerkt, is de actie **Starten** bevorderen ook beschikbaar bij **Pagina-informatie**. Hierdoor wordt de wizard geopend die de benodigde informatie verzamelt.

![chlimage_1-2](assets/chlimage_1-2.png)

>[!NOTE]
>
>Deze optie is beschikbaar voor enkelvoudige en [geneste opstarts](#promoting-a-nested-launch).

## Een geneste start bevorderen {#promoting-a-nested-launch}

Nadat u een geneste start hebt gemaakt, kunt u deze herstellen naar een van de bronnen, inclusief de hoofdbron (productie).

![chlimage_1-3](assets/chlimage_1-3.png)

1. Net als bij het [maken van een geneste opstart](/help/sites-authoring/launches-creating.md#creating-a-nested-launch)navigeert u naar de vereiste opstart in de **Launches** -console of de **References** -rail en selecteert u deze.
1. Selecteer Starten **bevorderen** om de wizard te openen.

1. Voer de vereiste gegevens in:

   * **Promotiedoel**

      U kunt een van de bronnen promoten.

   * **Bereik** Hier kunt u kiezen of u de volledige opstart wilt promoten of alleen pagina&#39;s die daadwerkelijk zijn bewerkt. In het laatste geval kunt u opgeven of u subpagina&#39;s wilt opnemen of uitsluiten. De standaardconfiguratie is dat alleen paginawijzigingen voor de huidige pagina worden bevorderd:

      * **Volledige introductie bevorderen**
      * **Gewijzigde pagina&#39;s promoten**
      * **Huidige pagina promoten**
      * **Huidige pagina en subpagina&#39;s promoten**

   ![chlimage_1-4](assets/chlimage_1-4.png)

1. Selecteer **Volgende**.
1. Bekijk de details van de aanbieding voordat je **Promoten** selecteert:

   ![chlimage_1-5](assets/chlimage_1-5.png)

   >[!NOTE]
   >
   >De weergegeven pagina&#39;s zijn afhankelijk van het gedefinieerde **bereik** en mogelijk van de pagina&#39;s die daadwerkelijk zijn bewerkt.

1. Uw wijzigingen worden bevorderd en weerspiegeld in de **Launches** -console:

   ![chlimage_1-6](assets/chlimage_1-6.png)

## Promotiepagina&#39;s verwerken met AEM-workflow {#processing-promoted-pages-using-aem-workflow}

Gebruik workflowmodellen voor bulkverwerking van geconverteerde startpagina&#39;s:

1. Maak een workflowpakket.
1. Wanneer auteurs startpagina&#39;s promoten, slaan ze deze op in het workflowpakket.
1. Start een workflowmodel met het pakket als de payload.

Als u een workflow automatisch wilt starten wanneer pagina&#39;s worden geconverteerd, [configureert u een werkstroomstartprogramma](/help/sites-administering/workflows-starting.md#workflows-launchers) voor het pakketknooppunt.

U kunt bijvoorbeeld automatisch aanvragen voor paginanactivering genereren wanneer auteurs pagina&#39;s starten promoten. Configureer een werkstroomstartprogramma om de workflow voor activering van aanvragen te starten wanneer het pakketknooppunt wordt gewijzigd.

![chlimage_1-7](assets/chlimage_1-7.png)

