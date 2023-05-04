---
title: AEM Forms Workspace Architecture
seo-title: AEM Forms Workspace Architecture
description: Conceptuele informatie en overzicht van de architectuur van de werkruimte van LiveCycle AEM Forms.
seo-description: Conceptual information and overview of the architecture of LiveCycle AEM Forms workspace.
uuid: e1a48452-ed44-4ea7-ba38-d961c8faafa5
contentOwner: robhagat
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: c3a312fb-f684-477d-916d-2d3c99aa7607
exl-id: 30bde8d6-7959-4e4b-a6f4-faf52444e67a
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 0%

---

# AEM Forms Workspace Architecture {#aem-forms-workspace-architecture}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

De AEM Forms-werkruimte is een webtoepassing die wordt gehost op CRX™. Wanneer de werkruimte in browser wordt geopend, wordt een middel CRX betreden, en de toepassing wordt teruggegeven als pagina van de HTML in browser.

De toepassing benadert de AEM Forms-server op REST-eindpunten voor het volgende:

* Gebruikerstaken ophalen, beginpunten van processen, procesgeschiedenis en gebruikersgegevens
* Handeling uitvoeren op taken
* Query uitvoeren in database
* Gebruikersvoorkeuren en meer bijwerken

De AEM Forms-server heeft via JDBC toegang tot de AEM Forms-database. De database bestaat uit taken, processen en instanties, gebruikers en gerelateerde informatie.

De AEM Forms-werkruimte is ontworpen voor modulaire JavaScript™-componenten die afzonderlijk kunnen worden aangepast en opnieuw kunnen worden gebruikt in andere webtoepassingen. De componenten zijn gebaseerd op BackBone, een JavaScript-bibliotheek die structuur geeft aan webtoepassingen. Een gedetailleerd artikel waarin de interactie van componenten met BackBone wordt beschreven is [hier](/help/forms/using/backbone-interaction.md). De organisatie van componenten in de CRX omslagstructuur wordt besproken in [dit](/help/forms/using/folder-structure.md) artikel.

Pakketten geleverd voor de AEM Forms-werkruimte:

* `adobe-lc-workspace-pkg-<version>.zip`: Het is CRX pakket, dat wil zeggen, het kan in CRX worden opgesteld gebruikend de Manager van het Pakket.
* `adobe-lc-workspace-<version>-src.zip`: Het is een archief dat volledige code van de werkruimte en de manuscripten van AEM Forms bevat om opstellen pakketten-verschepen, zuivert, en Dev pakketten.
