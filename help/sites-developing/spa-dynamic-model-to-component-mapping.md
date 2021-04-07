---
title: Dynamisch model naar componenttoewijzing voor SPA
seo-title: Dynamisch model naar componenttoewijzing voor SPA
description: In dit artikel wordt beschreven hoe het dynamische model naar componenttoewijzing wordt uitgevoerd in de Javascript SPA SDK voor AEM.
seo-description: In dit artikel wordt beschreven hoe het dynamische model naar componenttoewijzing wordt uitgevoerd in de Javascript SPA SDK voor AEM.
uuid: 337b8d90-efd7-442e-9fac-66c33cc26212
contentOwner: bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: spa
content-type: reference
discoiquuid: 8b4b0afc-8534-4010-8f34-cb10475a8e79
exl-id: 2bbbfbaa-b0a1-4f8a-9445-51325d80e368
translation-type: tm+mt
source-git-commit: bd94d3949f0117aa3e1c9f0e84f7293a5d6b03b4
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 0%

---

# Dynamisch model naar componenttoewijzing voor SPA{#dynamic-model-to-component-mapping-for-spas}

In dit document wordt beschreven hoe het dynamische model naar componenttoewijzing wordt uitgevoerd in de Javascript SPA SDK voor AEM.

>[!NOTE]
>De eigenschap van de Redacteur van de Toepassing van de enig-Pagina (SPA) vereist AEM 6.4 de dienstpak 2 of nieuwer.
>
>De SPA Redacteur is de geadviseerde oplossing voor projecten die SPA kader gebaseerde cliënt-zijteruggeven (b.v. Reageren of Angular) vereisen.

## ComponentMapping Module {#componentmapping-module}

De `ComponentMapping` module wordt verstrekt als pakket NPM aan het front-end project. Het slaat front-end componenten op en verstrekt een manier voor de Enige Toepassing van de Pagina om front-end componenten aan AEM middeltypes in kaart te brengen. Hierdoor wordt een dynamische resolutie van componenten ingeschakeld bij het parseren van het JSON-model van de toepassing.

Elke punten in het model bevatten een `:type` gebied dat een AEM middeltype blootstelt. Als de front-end component is gekoppeld, kan deze zichzelf renderen met behulp van het fragment van het model dat is ontvangen van de onderliggende bibliotheken.

Raadpleeg het document [SPA Blueprint](/help/sites-developing/spa-blueprint.md) voor meer informatie over modelparsering en de front-end componenttoegang tot het model.

Zie ook het npm-pakket: [https://www.npmjs.com/package/@adobe/aem-spa-component-mapping](https://www.npmjs.com/package/@adobe/aem-spa-component-mapping)

## Modelgestuurde toepassing voor één pagina {#model-driven-single-page-application}

Toepassingen met één pagina die gebruikmaken van de Javascript SPA SDK voor AEM, worden modelgestuurd:

1. De front-end componenten registreren zich aan [de Winkel van de Afbeelding van de Component](/help/sites-developing/spa-dynamic-model-to-component-mapping.md#componentmapping-module).
1. Vervolgens herhaalt de [Container](/help/sites-developing/spa-blueprint.md#container), zodra deze is voorzien van een model van de [Modelleverancier](/help/sites-developing/spa-blueprint.md#the-model-provider), de modelinhoud ( `:items`).

1. In het geval van een pagina, krijgen zijn kinderen ( `:children`) eerst een componentenklasse van [Component Mapping](/help/sites-developing/spa-blueprint.md#componentmapping) en dan concretiseren het.

## Initialisatie van toepassingen {#app-initialization}

Elke component wordt uitgebreid met de mogelijkheden van [ `ModelProvider`](/help/sites-developing/spa-blueprint.md#the-model-provider). Initialisatie heeft derhalve de volgende algemene vorm:

1. Elke modelleverancier initialiseert zich en luistert naar veranderingen die aan het stuk van model worden aangebracht dat aan zijn binnencomponent beantwoordt.
1. [ `PageModelManager`](/help/sites-developing/spa-blueprint.md#pagemodelmanager) moet worden geïnitialiseerd zoals vertegenwoordigd door [initialisatiestroom](/help/sites-developing/spa-blueprint.md).

1. Nadat het paginamodel is opgeslagen, retourneert de paginamodelbeheerder het volledige model van de app.
1. Dit model wordt dan overgegaan tot de front-end wortel [Container](/help/sites-developing/spa-blueprint.md#container) component van de toepassing.
1. Stukken van het model worden uiteindelijk doorgegeven aan elke afzonderlijke onderliggende component.

![app_model_initialisatie](assets/app_model_initialization.png)
