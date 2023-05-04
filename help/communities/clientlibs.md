---
title: Clientlibs voor Community-componenten
seo-title: Clientlibs for Communities Components
description: Clientbibliotheken voor gemeenschappen
seo-description: Client-side libraries for Communities
uuid: 0a62f629-e6af-4269-862e-0595824c329f
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 7d423dff-8710-4f43-ad55-8863169946e2
exl-id: 9b4ed16f-3c7c-478a-a897-9b4be086988b
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '415'
ht-degree: 0%

---

# Clientlibs voor Community-componenten {#clientlibs-for-communities-components}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Inleiding {#introduction}

In deze sectie van de documentatie wordt beschreven hoe u clientbibliotheken (clientlibs) aan een pagina voor Community-componenten kunt toevoegen.

Voor basisinformatie gaat u naar:

* [Client-Side bibliotheken gebruiken](../../help/sites-developing/clientlibs.md) die zowel gebruiksdetails als foutopsporingsgereedschappen biedt
* [Clientlibs voor SCF](client-customize.md#clientlibs) die nuttige informatie verstrekt wanneer het aanpassen van componenten SCF

## Waarom Clientlibs vereist zijn {#why-clientlibs-are-required}

Clientlibs zijn vereist voor het correct functioneren (JavaScript) en opmaken (CSS) van een component.

Wanneer er een [gemeenschapsfunctie](functions.md) voor een eigenschap , zullen alle noodzakelijke componenten en configuraties, met inbegrip van de vereiste clientlibs, in de communautaire plaats aanwezig zijn. Alleen als de auteurs extra componenten ter beschikking moeten hebben, moeten er extra clientlibs worden toegevoegd.

Wanneer de vereiste clientlibs ontbreken, [een onderdeel van een Gemeenschappen aan een pagina toevoegen](author-communities.md) kan resulteren in JavaScript-fouten en een onverwachte weergave.

### Voorbeeld: Geplaatste revisies zonder Clientlibs {#example-placed-reviews-without-clientlibs}

![chlimage_1-244](assets/chlimage_1-244.png)

### Voorbeeld: Geplaatste revisies met clips {#example-placed-reviews-with-clientlibs}

![chlimage_1-245](assets/chlimage_1-245.png)

## Vereiste clients identificeren {#identifying-required-clientlibs}

De essentiële eigenschapinformatie voor ontwikkelaars identificeert de vereiste clientlibs.

Bovendien kunt u vanuit een AEM naar de [Community Components Guide](components-guide.md) biedt toegang tot een lijst met clientlib-categorieën die vereist zijn voor een component.

Bijvoorbeeld helemaal boven aan de [Pagina Revisies](http://localhost:4502/content/community-components/en/reviews.html) de vereiste clientlibs worden vermeld

* cq.ckeditor
* cq.social.hbs.reviews

![chlimage_1-246](assets/chlimage_1-246.png)

## Vereiste clips toevoegen {#adding-required-clientlibs}

Wanneer u een Gemeenschapscomponent aan een pagina wilt toevoegen, moet u de vereiste clientlibs voor de component toevoegen als deze nog niet aanwezig is.

Gebruiken [CRXDE|Lite](#using-crxde-lite) om een bestaande clientlibslist voor een communautaire plaatspagina te wijzigen.

Om een clientlib voor een communautaire plaats toe te voegen gebruikend [CRXDE Lite](../../help/sites-developing/developing-with-crxde-lite.md):

* Bladeren naar [https://&lt;server>:&lt;port>/crx/de](http://localhost:4502/crx/de)
* Zoek de `clientlibslist` knooppunt voor de pagina waarop u de component wilt toevoegen

   * `/content/sites/sample/en/page/jcr:content/clientlibslist`

* Met `clientlibslist` knooppunt geselecteerd

   * De tekenreeks zoeken[] eigenschap `scg:requiredClientLibs`
   * Selecteer zijn `Value` om toegang te krijgen tot het dialoogvenster String-array

      * Indien nodig omlaag schuiven
      * Selecteren `+` om een nieuwe clientbibliotheek in te voeren

         * Herhalen om meer clientbibliotheken toe te voegen
      * Selecteer **[!UICONTROL OK]**
   * Selecteer **[!UICONTROL Save All]**



>[!NOTE]
>
>Als de site geen gemeenschapssite is, moet het bestaan of de locatie van de clientbibliotheken die voor de site worden gebruikt, worden gedetecteerd.

Met de [Aan de slag met AEM Communities](getting-started.md) voorbeeld, waarbij `site-name` is *aangaan*, is dit hoe de clientliblist zou verschijnen als het toevoegen van de revisiecomponent:

![chlimage_1-247](assets/chlimage_1-247.png)
