---
title: Clientlibs voor Community-componenten
seo-title: Clientlibs voor Community-componenten
description: Clientbibliotheken voor gemeenschappen
seo-description: Clientbibliotheken voor gemeenschappen
uuid: 0a62f629-e6af-4269-862e-0595824c329f
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 7d423dff-8710-4f43-ad55-8863169946e2
translation-type: tm+mt
source-git-commit: 59d40b5bddc42a4ac057ef600243f396aefc926b
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 0%

---


# Clientlibs voor Community-componenten {#clientlibs-for-communities-components}

## Inleiding {#introduction}

In deze sectie van de documentatie wordt beschreven hoe u clientbibliotheken (clientlibs) aan een pagina voor Community-componenten kunt toevoegen.

Voor basisinformatie gaat u naar:

* [Clientzijbibliotheken](../../help/sites-developing/clientlibs.md) gebruiken die zowel gebruiksdetails als foutopsporingsgereedschappen bieden
* [Clientlibs voor SCF](client-customize.md#clientlibs) die nuttige informatie wanneer het aanpassen van componenten SCF verstrekt
* [Blog: AEM Clientbibliotheken, zoals wordt uitgelegd in het voorbeeld](https://blogs.adobe.com/experiencedelivers/experience-management/clientlibs-explained-example/)

## Waarom Clientlibs vereist zijn {#why-clientlibs-are-required}

Clientlibs zijn vereist voor het correct functioneren (JavaScript) en opmaken (CSS) van een component.

Wanneer er een [communautaire functie](functions.md) voor een eigenschap bestaat, zullen alle noodzakelijke componenten en configuraties, met inbegrip van de vereiste clientlibs, in de communautaire plaats aanwezig zijn. Alleen als de auteurs extra componenten ter beschikking moeten hebben, moeten er extra clientlibs worden toegevoegd.

Wanneer de vereiste clientlibs ontbreken, kan het [toevoegen van een Community-component aan een pagina](author-communities.md) leiden tot JavaScript-fouten en een onverwachte weergave.

### Voorbeeld: Geplaatste revisies zonder Clientlibs {#example-placed-reviews-without-clientlibs}

![chlimage_1-244](assets/chlimage_1-244.png)

### Voorbeeld: Geplaatste revisies met clips {#example-placed-reviews-with-clientlibs}

![chlimage_1-245](assets/chlimage_1-245.png)

## Vereiste clients identificeren {#identifying-required-clientlibs}

De essentiële eigenschapinformatie voor ontwikkelaars identificeert de vereiste clientlibs.

Daarnaast kunt u vanuit een AEM naar de [Community Components Guide](components-guide.md) bladeren om een lijst met clientlib-categorieën weer te geven die voor een component zijn vereist.

Bijvoorbeeld helemaal boven aan de pagina [](http://localhost:4502/content/community-components/en/reviews.html) Revisies worden de vereiste clientlibs weergegeven

* cq.ckeditor
* cq.social.hbs.reviews

![chlimage_1-246](assets/chlimage_1-246.png)

## Vereiste clips toevoegen {#adding-required-clientlibs}

Wanneer u een Gemeenschapscomponent aan een pagina wilt toevoegen, moet u de vereiste clientlibs voor de component toevoegen als deze nog niet aanwezig is.

Gebruik [CRXDE|Lite](#using-crxde-lite) om een bestaande cliëntlibslist voor een communautaire plaatspagina te wijzigen.

Om een clientlib voor een communautaire plaats toe te voegen gebruikend [CRXDE Lite](../../help/sites-developing/developing-with-crxde-lite.md):

* Ga naar [https://&lt;server>:&lt;port>/crx/de](http://localhost:4502/crx/de)
* Zoek het `clientlibslist` knooppunt voor de pagina waaraan u de component wilt toevoegen

   * `/content/sites/sample/en/page/jcr:content/clientlibslist`

* Met geselecteerde `clientlibslist` node

   * De eigenschap String[] zoeken `scg:requiredClientLibs`
   * Selecteer de instantie `Value` voor toegang tot het dialoogvenster String-array

      * Indien nodig omlaag schuiven
      * Selecteren `+` om een nieuwe clientbibliotheek in te voeren

         * Herhalen om meer clientbibliotheken toe te voegen
      * Selecteer **[!UICONTROL OK]**
   * Selecteer **[!UICONTROL Save All]**



>[!NOTE]
>
>Als de site geen gemeenschapssite is, moet het bestaan of de locatie van de clientbibliotheken die voor de site worden gebruikt, worden gedetecteerd.

Gebruikend het [Beginnen met het voorbeeld van AEM Communities](getting-started.md) , waar `site-name` is *geëngageerd*, is dit hoe de cliëntliblist zou verschijnen als het toevoegen van de revisiecomponent:

![chlimage_1-247](assets/chlimage_1-247.png)

