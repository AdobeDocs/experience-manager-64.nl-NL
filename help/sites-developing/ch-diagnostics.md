---
title: ContextHub Diagnostics
seo-title: ContextHub Diagnostics
description: ContextHub verstrekt een diagnostische pagina waar u een overzicht van het kader ContextHub kunt zien
seo-description: ContextHub verstrekt een diagnostische pagina waar u een overzicht van het kader ContextHub kunt zien
uuid: 94ef0696-3977-4781-ad32-9f4f117eb096
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: personalization
content-type: reference
discoiquuid: 6aa88583-5d34-4f77-a932-d47d84785eca
translation-type: tm+mt
source-git-commit: 39b6af8ee815e8f6fa6e0b4a0a6dc80f29165243
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 0%

---


# ContextHub Diagnostics {#contexthub-diagnostics}

ContextHub verstrekt een diagnostische pagina waar u een overzicht van het kader kunt zien ContextHub. Als u de pagina wilt openen, gaat u bijvoorbeeld naar de pagina `contexthub.diagnostics.html` van de AEM auteur-instantie:

`http://<host>:<port>/conf/<tenant>/settings/cloudsettings/default/contexthub.diagnostics.html`

De pagina van de Diagnostiek ContextHub verstrekt informatie over de opslag en modules UI die zijn gecreeerd, de omslagen van de cliëntbibliotheek die, en verbindingen aan nuttige pagina&#39;s worden geladen.

>[!NOTE]
>
>De foutopsporingsmodus moet zijn ingeschakeld om diagnostische gegevens te kunnen retourneren. Als dit niet het geval is, is de pagina Diagnostics leeg. Zie [dit document](/help/sites-administering/contexthub-config.md#debugging-contexthub) voor meer informatie over het inschakelen van de foutopsporingsmodus.

>[!NOTE]
>
>Voor configuraties ContextHub die nog onder hun erfeniswegen worden gevestigd, is de plaats van de diagnostische pagina `http://<host>:<port>/libs/settings/cloudsettings/legacy/contexthub.diagnostics.html`.

## Opslagruimten {#stores}

De sectie van Sporen maakt een lijst van alle opslag ContextHub die zijn gevormd. Elk item in de lijst bestaat uit de volgende informatie:

* **Titel:** Het  [opslagtype ](/help/sites-developing/ch-samplestores.md) waarop de winkel is gebaseerd.
* **pad:** het pad naar het knooppunt in de opslagplaats dat de configuratie bevat.
* **resourceType:** Het pad van het opslagknooppunt waar het opslagtype is gedefinieerd.
* **clientlibs:** De categorieën van de cliëntbibliotheken die worden geladen die het archieftype uitvoeren.

## Modules {#modules}

De sectie van Modules maakt een lijst van alle modules ContextHub UI die zijn gevormd. Elk item in de lijst bestaat uit de volgende informatie:

* **Titel:** Het  [UI ](/help/sites-developing/ch-samplemodules.md) type van de Module dat de module UI gebaseerd is op.
* **pad:** het pad naar het knooppunt in de opslagplaats dat de configuratie bevat.
* **resourceType:** De weg van de gegevensopslaggegevensopslagknoop waar het UI moduletype wordt bepaald.
* **clientlibs:** De categorieën van de cliëntbibliotheken die worden geladen die het UI moduletype uitvoeren.

## Clientlibs {#clientlibs}

De sectie Clientlibs maakt een lijst van alle omslagen van de cliëntbibliotheek die ContextHub heeft geladen. De clientbibliotheken zijn gecategoriseerd:

* **kernel.js:De bibliotheken van de** cliënt die het kader ContextHub, de segmentmotor, en opslagtypes uitvoeren.
* **ui.js:De bibliotheken van de** cliënt die de ContextHub UI en UI moduletypes uitvoeren.
* **style.css:** CSS-bestanden die worden geladen uit clientbibliotheken.

## URL&#39;s {#urls}

De sectie URLs bevat verbindingen aan eigenschappen ContextHub:

* **De redacteur van de configuratie:** opent de  [Configuratie ](/help/sites-administering/contexthub-config.md) ContextHubpagina waar u opslag, wijzen UI, en modules kunt vormen UI.

* **Configuratie van modules ContextHub:** opent het bestand /etc/cloudsettings/default/contexthub.config.kernel.js, dat de Javascript-objectrepresentatie van de ContextHub-opslagconfiguraties bevat.
* **Configuratie van ContextHub UI:** Opent het bestand /etc/cloudsettings/default/contexthub.config.ui.js, dat de Javascript objecten vertegenwoordiging van de ContextHub UI wijzeconfiguraties bevat.
* **kernel.js:** Opent het bestand /etc/cloudsettings/default/contexthub.kernel.js, dat de broncode van de cliëntbibliotheken bevat die het kader ContextHub, de segmentmotor, en opslagtypes uitvoeren.
* **ui.js:** Opent het bestand /etc/cloudsettings/default/contexthub.ui.js, dat de broncode van de cliëntbibliotheken bevat die de ContextHub UI en UI moduletypes uitvoeren.
* **style.css:** Opent het bestand /etc/cloudsettings/default/contexthub.styles.css, dat de CSS stijlen voor de modules ContextHub UI en UI bevat.
