---
title: ContextHub
seo-title: ContextHub
description: ContextHub is een kader voor het opslaan van, het manipuleren van, en het voorstellen van contextgegevens
seo-description: ContextHub is a framework for storing, manipulating, and presenting context data
uuid: 14e6ff4f-ffbe-454a-b2ec-a35333526e27
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: personalization
content-type: reference
discoiquuid: acf5c17a-95b7-43ba-9734-241e20f4f374
exl-id: 0a6b815a-5055-4c44-96d1-ff238b4285f3
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 0%

---

# ContextHub{#contexthub}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

ContextHub is een kader voor het opslaan van, het manipuleren van, en het voorstellen van contextgegevens. Met de JavaScript-API aan de clientzijde hebt u toegang tot de gegevens voor het aanpassen van de inhoud.

>[!NOTE]
>
>De [We.Retail-referentieimplementatie](/help/sites-developing/we-retail.md) Voert ContextHub uit en kan als verwijzing dienen aangezien u ContextHub in uw eigen project integreert.

>[!CAUTION]
>
>De weg die de configuratie bevat van steekproefContextHub die door wordt gebruikt [We.Retail-referentieimplementatie](/help/sites-developing/we-retail.md) ( `/libs/settings/cloudsettings/legacy`) alleen gebruiken als referentie voor het maken van uw eigen configuratie.
>
>Het zou niet in een project als uw eigen configuratie ContextHub moeten worden gebruikt.

## Persistentie {#persistence}

De opslag ContextHub handhaaft contextgegevens over de cliënt. De JavaScript API van ContextHub laat u toe om tot opslag toegang te hebben om, gegevens tot stand te brengen bij te werken en te schrappen zonodig. Als dusdanig, vertegenwoordigt ContextHub een gegevenslaag op uw pagina&#39;s.

Elke opslag ContextHub is een geval van een vooraf bepaald opslagtype:

* ContextHub biedt verschillende [voorbeeldwinkeltypen](/help/sites-developing/ch-samplestores.md).
* Consoles AEM gebruiken voor [winkels maken](/help/sites-administering/contexthub-config.md#creating-a-contexthub-store).
* Ontwikkelaars kunnen [aangepaste winkeltypen maken](/help/sites-developing/ch-extend.md#creating-custom-store-candidates).
* Ontwikkelaars kunnen [toegang opslaggegevens](/help/sites-developing/ch-adding.md#interacting-with-contexthub-stores) via Javascript.

## Segmentering {#segmentation}

ContextHub omvat een segmenteringsmotor die segmenten beheert en bepaalt welke segmenten voor de huidige context worden opgelost. Verschillende segmenten zijn gedefinieerd. U kunt de JavaScript-API gebruiken om [omgezette segmenten bepalen](/help/sites-developing/ch-adding.md#determining-resolved-contexthub-segments).

## Presentatie {#presentation}

De [ContextHub-werkbalk](/help/sites-authoring/ch-previewing.md) stelt marketers en auteurs in staat om opslaggegevens te bekijken en te manipuleren om de gebruikerservaring bij het ontwerpen van pagina&#39;s te simuleren. De toolbar bestaat uit groepen modules UI die toegang tot winkels verlenen ContextHub.

Elke module ContextHub UI is een geval van een vooraf bepaald moduletype:

* ContextHub biedt verschillende [voorbeeldmoduletypen](/help/sites-developing/ch-samplemodules.md).
* Consoles AEM gebruiken voor [UI-modules toevoegen](/help/sites-administering/contexthub-config.md#adding-a-ui-module)en [groeperen hen in wijzen UI](/help/sites-administering/contexthub-config.md#adding-a-ui-mode).

* Ontwikkelaars kunnen [aangepaste moduletypen maken](/help/sites-developing/ch-extend.md#creating-contexthub-ui-module-types).

Ontwikkelaars moeten [Voeg de component ContextHub aan de pagina toe](/help/sites-developing/ch-adding.md).
