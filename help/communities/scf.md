---
title: Framework sociale component
seo-title: Social Component Framework
description: Het kader van de sociale component (SCF) vereenvoudigt het proces om, componenten van de Gemeenschappen te vormen aan te passen en uit te breiden
seo-description: The social component framework (SCF) simplifies the process of configuring, customizing, and extending Communities components
uuid: 23b4418d-b91c-46fc-bf42-1154ef79fe5a
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: d7b5b5e3-2d84-4a6b-bcc2-d490882ff3ed
exl-id: 9264c888-a583-40eb-9178-273146f8a12b
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1524'
ht-degree: 0%

---

# Framework sociale component {#social-component-framework}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Het sociale componentenkader (SCF) vereenvoudigt het proces om, componenten van Gemeenschappen op zowel server-kant als cliënt-kant te vormen aan te passen en uit te breiden.

De voordelen van het kader:

* **Functioneel**: Eenvoudig te integreren, zonder of weinig aanpassingen voor 80% van de gebruiksgevallen
* **Skinnable**: Consistent gebruik van HTML-kenmerken voor CSS-opmaak
* **Uitbreidbaar**: De implementatie van de component is objectgeoriënteerd en licht op bedrijfslogica - gemakkelijk om stijgende bedrijfslogin op server toe te voegen
* **Flexibel**: Eenvoudige JavaScript-sjablonen zonder logica die eenvoudig kunnen worden overschreven en aangepast
* **Toegankelijk**: De HTTP-API biedt ondersteuning voor posten vanaf elke client, waaronder mobiele apps
* **Overdraagbaar**: Integreren/insluiten in elke webpagina die is gebaseerd op elke technologie

Ontdek een auteur- of publicatieexemplaar met interactieve [Community Components Guide](components-guide.md).

## Overzicht {#overview}

In SCF, wordt een component samengesteld uit een POJO SocialComponent, een Malplaatje van Handlebars JS (om de component terug te geven), en CSS (om de component te stileren).

Een JS-sjabloon Handlebars kan de JS-componenten model/weergave uitbreiden om gebruikersinteractie met de component op de client af te handelen.

Als een component wijziging van gegevens moet ondersteunen, kan de implementatie van de API voor sociale componenten worden geschreven ter ondersteuning van het bewerken/opslaan van gegevens die vergelijkbaar zijn met model- en gegevensobjecten in traditionele webtoepassingen. Daarnaast kunnen bewerkingen (controllers) en een bewerkingsservice worden toegevoegd om bewerkingsverzoeken te verwerken, bedrijfslogica uit te voeren en de API&#39;s op het model/de gegevensobjecten aan te roepen.

De API van de sociale component kan worden uitgebreid om gegevens te verstrekken die door een cliënt voor een meningslaag of een cliënt van HTTP worden vereist.

### Hoe pagina&#39;s voor de client worden gerenderd {#how-pages-are-rendered-for-client}

![chlimage_1-25](assets/chlimage_1-25.png)

### Component Customization and Extension {#component-customization-and-extension}

Als u de componenten wilt aanpassen of uitbreiden, schrijft u alleen de overlays en extensies naar de map /apps waarmee u het upgradeproces naar toekomstige releases kunt vereenvoudigen.

* Voor skin
   * Alleen de [CSS moet worden bewerkt](client-customize.md#skinning-css)
* Voor uiterlijk
   * De JS-sjabloon en CSS wijzigen
* Voor look, Voel en UX
   * De JS-sjabloon, CSS en [JavaScript uitbreiden/overschrijven](client-customize.md#extending-javascript)
* Om de informatie beschikbaar aan het Malplaatje JS of aan het eindpunt van GET te wijzigen
   * Breid uit [SocialComponent](server-customize.md#socialcomponent-interface)
* Aangepaste verwerking toevoegen tijdens bewerkingen
   * Schrijf een [OperationExtension](server-customize.md#operationextension-class)
* Een nieuwe aangepaste bewerking toevoegen
   * Een nieuwe [Verschuiving na bewerking](server-customize.md#postoperation-class)
   * Bestaande gebruiken [OperationServices](server-customize.md#operationservice-class) indien nodig
   * Voeg JavaScript-code toe om uw bewerking zo nodig vanaf de client aan te roepen

## Server-Side Framework {#server-side-framework}

Het framework biedt API&#39;s voor toegang tot functionaliteit op de server en voor ondersteuning van interactie tussen de client en de server.

### Java API&#39;s {#java-apis}

De Java API&#39;s bieden abstracte klassen en interfaces die gemakkelijk kunnen worden overgeërfd of gesubclassificeerd.

De hoofdklassen worden beschreven op het tabblad [Aanpassing op de server](server-customize.md) pagina.

Bezoek [Overzicht opslagbronprovider](srp.md) voor meer informatie over het werken met UGC.

### HTTP-API {#http-api}

De HTTP-API ondersteunt eenvoudige aanpassingen en keuzemogelijkheden van clientplatforms voor PhoneGap-apps, native apps en andere integraties en mashups. Bovendien staat HTTP API een communautaire plaats toe om als dienst zonder een cliënt te lopen, zodat de kadercomponenten in om het even welke webpage kunnen worden geïntegreerd die op om het even welke technologie wordt voortgebouwd.

### HTTP API - GET {#http-api-get-requests}

Voor elke SocialComponent, verstrekt het kader een op HTTP-Gebaseerd API eindpunt. Het eindpunt wordt betreden door een verzoek van de GET naar het middel met &quot;.social.json&quot;selecteur + uitbreiding te verzenden. Met Sling wordt het verzoek aan de `DefaultSocialGetServlet`.

De `DefaultSocialGetServlet`

1. Geeft de resource (resourceType) door aan de `SocialComponentFactoryManager`en ontvangt een SocialComponentFactory die een `SocialComponent`die de bron vertegenwoordigt.

1. Roept de fabriek aan en ontvangt een `SocialComponent`in staat om de bron en het verzoek af te handelen.
1. Roept de `SocialComponent`, die de aanvraag verwerkt en een JSON-weergave van de resultaten retourneert.
1. Retourneert de JSON-reactie op de client.

**`GET Request`**

Een standaard GET servlet luistert naar .social.json verzoeken waaraan de SocialComponent met klantgerichte JSON antwoordt.

![chlimage_1-26](assets/chlimage_1-26.png)

### HTTP API - POST-aanvragen {#http-api-post-requests}

Naast de (Gelezen) verrichtingen van de GET, bepaalt het kader een eindpuntpatroon om andere verrichtingen op een component toe te laten, met inbegrip van Create, Update en Schrapping. Deze eindpunten zijn HTTP-API&#39;s die invoer accepteren en reageren met HTTP-statuscodes of met een JSON-reactieobject.

Met dit eindpuntpatroon van het framework worden CUD-bewerkingen uitbreidbaar, herbruikbaar en getest.

**`POST Request`**

Er is een Sling POST:verrichting voor elke verrichting SocialComponent. De bedrijfslogica en onderhoudscode voor elke verrichting zijn verpakt in een OperationService die door HTTP API of van elders als dienst OSGi toegankelijk is. Hooks wordt geleverd ter ondersteuning van instelbare bewerkingsextensies voor acties voor en na acties.

![chlimage_1-27](assets/chlimage_1-27.png)

### Storage Resource Provider (SRP) {#storage-resource-provider-srp}

Meer informatie over de verwerking van UGC die is opgeslagen in het dialoogvenster [community content store](working-with-srp.md), zie

* [Overzicht opslagbronprovider](srp.md) - Inleiding en overzicht van het gebruik van opslagruimten
* [SRP en UGC Essentials](srp-and-ugc.md) - Hulpprogrammamethoden en -voorbeelden van SRP API
* [Toegang tot UGC met SRP](accessing-ugc-with-srp.md) - Codeerrichtsnoeren

### Aanpassingen op de server {#server-side-customizations}

Bezoek [Aanpassingen op de server](server-customize.md) voor informatie over het aanpassen van de bedrijfslogica en het gedrag van een onderdeel van de Gemeenschappen aan de serverzijde.

## Handlebars JS Templating Language {#handlebars-js-templating-language}

Een van de meest opvallende wijzigingen in het nieuwe kader is het gebruik van de [Handlebars JS](https://handlebarsjs.com/) Sjabloontaal (HBS), een populaire open-source technologie voor server-client rendering.

HBS-scripts zijn eenvoudig, zonder logica, kunnen op zowel de server als de client worden gecompileerd, zijn eenvoudig te bedekken en aan te passen en zijn op natuurlijke wijze gebonden aan de client-UX, omdat HBS renderen aan de clientzijde ondersteunt.

Het kader biedt verschillende [Handbalkhelpers](handlebars-helpers.md) die nuttig zijn bij het ontwikkelen van sociale componenten.

Op de server, wanneer het Sling een verzoek van de GET verhelpt, identificeert het het manuscript dat zal worden gebruikt om op het verzoek te antwoorden. Als het manuscript een malplaatje HBS (.hbs) is, zal het Sling het verzoek aan de Motor van Handlebars delegeren. De Motor Handlebars zal dan de SocialComponent van aangewezen SocialComponentFactory krijgen, een context bouwen, en de HTML teruggeven.

### Geen toegangsbeperking {#no-access-restriction}

Handlebars (HBS) malplaatjedossiers (.hbs) zijn analoog aan .jsp en .html malplaatjedossiers, behalve zij kunnen voor het teruggeven zowel in cliëntbrowser als op de server worden gebruikt. Daarom zal een cliëntbrowser die om een cliënt-zijmalplaatje verzoekt een .hbs dossier van de server ontvangen.

Dit vereist dat alle malplaatjes van HBS in de sling onderzoekspad (om het even welke .hbs dossiers onder /libs/ of /apps) door om het even welke gebruiker van auteur kunnen worden gehaald of publiceren.

De toegang van HTTP tot .hbs dossiers kan niet worden verboden.

### Een onderdeel van een Gemeenschappen toevoegen of opnemen {#add-or-include-a-communities-component}

De meeste onderdelen van een Gemeenschappen moeten *added* als Verlenen adresseerbare bron. Een aantal communautaire componenten kan *inbegrepen* in een sjabloon als een niet-bestaande bron, zodat de locatie waar door de gebruiker gegenereerde inhoud (UGC) moet worden geschreven, dynamisch kan worden opgenomen en aangepast.

In beide gevallen geldt dat de component [vereiste clientbibliotheken](clientlibs.md) moet ook aanwezig zijn.

**Een component toevoegen**

Het toevoegen van een component verwijst naar het proces om een geval van een middel (component) toe te voegen, zoals wanneer gesleept van componentenbrowser (sidekick) op een pagina in auteur uitgeeft wijze.

Het resultaat is een JCR-onderliggend knooppunt onder een pari-knooppunt, dat adresseerbaar is.

**Een component opnemen**

Het opnemen van een component verwijst naar het proces waarbij een verwijzing naar een component wordt toegevoegd [&quot;niet-bestaande&quot; resource](srp.md#for-non-existing-resources-ners) (geen JCR-knooppunt) in de sjabloon, zoals het gebruik van een scripttaal.

Vanaf AEM 6.1, wanneer een component dynamisch in plaats van toegevoegd wordt omvat, is het mogelijk om de eigenschappen van de component in auteur *design *mode uit te geven.

Slechts een paar AEM Communities-componenten kunnen dynamisch worden opgenomen. Het zijn:

* [Opmerkingen](essentials-comments.md)
* [Classificatie](rating-basics.md)
* [Revisies](reviews-basics.md)
* [Stemming](essentials-voting.md)

De [Community Components Guide](components-guide.md) staat toe inbegrepen componenten om van worden een knevel te schakelen van worden toegevoegd aan worden omvat.

**Bij gebruik van handgrepen** sjabloontaal, de niet-bestaande bron wordt opgenomen met de [inclusief helper](handlebars-helpers.md#include) door zijn resourceType te specificeren:

`{{include this.id path="comments" resourceType="social/commons/components/hbs/comments"}}`

**Bij gebruik van JSP**, wordt een bron opgenomen met de tag [cq:include](../../help/sites-developing/taglib.md#lt-cq-include):

```
<cq:include path="votes" 
 resourceType="social/tally/components/voting" />
```

>[!NOTE]
>
>Als u een component dynamisch aan een pagina wilt toevoegen in plaats van deze toe te voegen aan of op te nemen in een sjabloon, raadpleegt u [Component Sideloading](sideloading.md).

### Handlebars Helpers {#handlebars-helpers}

Zie [SCF Handlebars Helpers](handlebars-helpers.md) voor een lijst en beschrijving van aangepaste hulplijnen die beschikbaar zijn in het SCF.

## Client-Side Framework {#client-side-framework}

### JavaScript-framework voor modelweergave {#model-view-javascript-framework}

Het kader omvat een verlenging van [Backbone.js](https://www.backbonejs.org/), een model-weergave JavaScript-framework, om de ontwikkeling van rijke, interactieve componenten te vergemakkelijken. De objectgeoriënteerde aard ondersteunt een uitbreidbaar/herbruikbaar framework. De communicatie tussen client en server wordt vereenvoudigd door middel van de HTTP API.

Het framework maakt gebruik van Handlebars-sjablonen aan de serverzijde om de componenten voor de client te renderen. De modellen zijn gebaseerd op de JSON-reacties die door de HTTP-API zijn gegenereerd. De meningen binden zich aan HTML die door de malplaatjes Handlebars wordt geproduceerd en verstrekken interactiviteit.

### CSS-conventies {#css-conventions}

Hieronder vindt u aanbevolen conventies voor het definiëren en gebruiken van CSS-klassen:

* Gebruik duidelijk benoemde CSS-klassenselectienamen en vermijd generieke namen zoals &#39;kop&#39;, &#39;afbeelding&#39;, enzovoort.
* Definieer specifieke klassenselectorstijlen, zodat de CSS-opmaakmodellen goed werken met andere elementen en stijlen op de pagina. Bijvoorbeeld: `.social-forum .topic-list .li { color: blue; }`
* CSS-klassen voor opmaak gescheiden houden van CSS-klassen voor UX aangestuurd door JavaScript

### Aanpassingen op de client {#client-side-customizations}

Voor het aanpassen van de weergave en het gedrag van een onderdeel van een Community op de client-side, verwijst u naar [Aanpassingen op de client](client-customize.md), met informatie over:

* [Bedekkingen](client-customize.md#overlays)
* [Extensies](client-customize.md#extensions)
* [HTML Markup](client-customize.md#htmlmarkup)
* [CSS schuintrekken](client-customize.md#skinning-css)
* [JavaScript uitbreiden](client-customize.md#extending-javascript)
* [Clientlibs voor SCF](client-customize.md#clientlibs-for-scf)

## Essentiële functies en componenten {#feature-and-component-essentials}

De essentiële informatie voor ontwikkelaars wordt beschreven in de [Essentiële functies en componenten](essentials.md) sectie.

Aanvullende informatie over ontwikkelaars vindt u in het gedeelte [Codeerrichtlijnen](code-guide.md) sectie.

## Problemen oplossen {#troubleshooting}

Gemeenschappelijke punten van zorg en bekende punten worden beschreven in de [Problemen oplossen](troubleshooting.md) sectie.
