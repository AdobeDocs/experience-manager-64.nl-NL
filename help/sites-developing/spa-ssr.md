---
title: SPA en rendering op de server
seo-title: SPA en rendering op de server
description: 'null'
seo-description: 'null'
uuid: fbf7d0d1-865d-45d2-aeec-a7e3caf3fcb2
contentOwner: bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: spa
content-type: reference
discoiquuid: 30d25772-0df7-468e-bcbd-c6fb2e962662
translation-type: tm+mt
source-git-commit: 2abf448e0231eb6fcd9295f498a24e81e1ead11a

---


# SPA en rendering op de server{#spa-and-server-side-rendering}

>[!NOTE]
>De eigenschap van de Redacteur van de Toepassing van de Enige-Pagina (SPA) vereist [AEM 6.4 de dienstpak 2](https://helpx.adobe.com/experience-manager/6-4/release-notes/sp-release-notes.html) of nieuwer.
>
>De redacteur van het KUUROORD is de geadviseerde oplossing voor projecten die het kader van het KUUROORD gebaseerde cliënt-kant teruggeven (b.v. Reageren of Hoekig) vereisen.

>[!NOTE]
>
>AEM 6.4.5.0 of recenter wordt vereist om de server van het KUUROORD te gebruiken teruggevende eigenschappen zoals die in dit document worden beschreven.

## Overzicht {#overview}

De enige paginatoepassingen (SPAs) kunnen de gebruiker een rijke, dynamische ervaringen aanbieden die op vertrouwde manieren reageren en zich gedragen, vaak enkel als inheemse toepassingen. [Dit wordt bereikt door op de client te vertrouwen om de inhoud op voorgrond te laden en vervolgens de verwerking van gebruikersinteractie](/help/sites-developing/spa-walkthrough.md#how-does-a-spa-work) zwaar op te heffen, zodat de benodigde hoeveelheid communicatie tussen de client en de server tot een minimum wordt beperkt, waardoor de app reactiever wordt.

Nochtans kan dit tot langere aanvankelijke ladingstijden leiden, vooral als SPA groot en rijk in zijn inhoud is. Om de laadtijden te optimaliseren, kan een deel van de inhoud op de server worden gerenderd. Met SSR (serverside rendering) kunt u de eerste belasting van de pagina versnellen en vervolgens verdere rendering doorgeven aan de client.

## Wanneer gebruikt u SSR {#when-to-use-ssr}

SSR is niet vereist voor alle projecten. Alhoewel AEM volledig JS SSR voor SPA steunt, adviseert Adobe niet het systematisch voor elk project uit te voeren.

Wanneer u besluit SSR te implementeren, moet u eerst inschatten welke extra complexiteit, inspanning en kosten het toevoegen van SSR realistisch vertegenwoordigt voor het project, inclusief het langetermijnonderhoud. Een SSR-architectuur mag alleen worden gekozen wanneer de toegevoegde waarde duidelijk hoger is dan de geraamde kosten.

SSR verstrekt gewoonlijk één of andere waarde wanneer er duidelijk &quot;ja&quot;aan één van beiden van de volgende vragen is:

* **** SEO: Is SSR eigenlijk nog vereist voor uw plaats om behoorlijk door de onderzoeksmotoren worden geïndexeerd die verkeer brengen? Vergeet niet dat de zoekmachine die als hoofdopzoekprogramma wordt gebruikt nu JS evalueert.
* **** Paginasnelheid: Biedt SSR een meetbare snelheidsverbetering in levensechte omgevingen en vergroot de algehele gebruikerservaring?

Slechts wanneer één van minstens één van deze twee vragen met duidelijk &quot;ja&quot;voor uw project wordt beantwoord adviseert Adobe het uitvoeren van SSR. In de volgende secties wordt beschreven hoe u dit kunt doen met Adobe I/O Runtime.

## Adobe I/O-runtime {#adobe-io-runtime}

Als u [zeker weet dat voor uw project de implementatie van SSR](#when-to-use-ssr)is vereist, kunt u het beste Adobe I/O-runtime gebruiken.

Ga voor meer informatie over Adobe I/O Runtime naar

* [https://www.adobe.io/apis/experienceplatform/runtime.html](https://www.adobe.io/apis/experienceplatform/runtime.html) - voor een overzicht van de dienst
* [https://www.adobe.io/apis/experienceplatform/runtime/docs.html](https://www.adobe.io/apis/experienceplatform/runtime/docs.html) - voor gedetailleerde documentatie op het platform

In de volgende secties wordt gedetailleerd beschreven hoe Adobe I/O Runtime kan worden gebruikt om SSR voor uw SPA in twee verschillende modellen uit te voeren:

* [AEM-gestuurde communicatiestroom](#aem-driven-communication-flow)
* [Door Adobe I/O-runtime gestuurde communicatiestroom](#adobe-io-driven-communication-flow)

>[!NOTE]
>
>Adobe raadt een aparte Adobe I/O Runtime-instantie aan voor elke AEM-omgeving (auteur, publicatie, werkgebied, enz.).

## Configuratie renderfunctie voor externe inhoud {#remote-content-renderer-configuration}

AEM moet weten waar de op afstand gerenderde inhoud kan worden opgehaald. Ongeacht [welk model u verkiest om voor SSR](#adobe-io-runtime)uit te voeren, zult u aan AEM moeten specificeren hoe te om tot deze verre het teruggeven dienst toegang te hebben.

Dit wordt gedaan via de **dienst RemoteContentRenderer - van de Fabriek** van de Configuratie OSGi. Zoek naar het koord &quot;RemoteContentRenderer&quot;in de console van de Configuratie van de Console van het Web bij `http://<host>:<port>/system/console/configMgr`.

![](assets/rendererconfig.png)

De volgende velden zijn beschikbaar voor de configuratie:

* **Inhoudspatroon** - Reguliere expressie voor afstemming van een deel van de inhoud, indien nodig
* **Het verre eindpunt URL** - URL van het eindpunt dat voor het produceren van de inhoud verantwoordelijk is
   * Gebruik het beveiligde HTTPS-protocol als dit zich niet in het lokale netwerk bevindt.
* **Extra verzoekkopballen** - de Extra kopballen die aan het verzoek moeten worden toegevoegd dat naar het verre eindpunt wordt verzonden
   * Patroon: `key=value`
* **Time-out** aanvragen - Time-out externe hostaanvraag in milliseconden

>[!NOTE]
>
>Ongeacht of u ervoor kiest om de [AEM-gestuurde communicatiestroom](#aem-driven-communication-flow) of de door [Adobe I/O-runtime gestuurde flow](#adobe-io-driven-communication-flow)te implementeren, moet u een configuratie voor een externe inhoudrenderer definiëren.
>
>Deze configuratie moet ook worden bepaald als u verkiest om een server [van Node.js te](#using-node-js)gebruiken.

>[!NOTE]
>
>Deze configuratie gebruikt de renderer voor [externe inhoud](#remote-content-renderer), die over extra opties voor extensie en aanpassing beschikt.

## AEM-gestuurde communicatiestroom {#aem-driven-communication-flow}

Wanneer u SSR gebruikt, bevat de workflow [voor](/help/sites-developing/spa-overview.md#workflow) componentinteractie van SPA&#39;s in AEM een fase waarin de initiële inhoud van de app wordt gegenereerd door Adobe I/O-runtime.

1. De browser vraagt de SSR-inhoud op van AEM.
1. AEM publiceert het model naar Adobe I/O Runtime.
1. De Adobe I/O-runtime retourneert de gegenereerde inhoud
1. AEM dient de HTML die door Adobe I/O Runtime via het malplaatje van HTML van de achterste paginacomponent is teruggekeerd.

![server-side rendering-cms-drivenaemnode](assets/server-side-rendering-cms-drivenaemnode-adobeio.png)

### Adobe I/O Runtime-gestuurde communicatiestroom {#adobe-io-driven-communication-flow}

De sectie [AEM-Gedreven Communicatie Stroom](#aem-driven-communication-flow) beschrijft de standaard en geadviseerde implementatie van server zijteruggeven met betrekking tot SPAs in AEM, waar AEM het bootstrapping en het dienen van inhoud uitvoert.

Alternatief, kan SSR worden uitgevoerd zodat de Runtime van Adobe I/O van Adobe voor bootstrapping verantwoordelijk is, effectief omkeerend de communicatie stroom.

Beide modellen zijn geldig en worden ondersteund door AEM. Men moet echter eerst de voor- en nadelen van elk model in overweging nemen voordat men een bepaald model toepast.

| Bootstrapping | Voordelen | Nadelen |
|---|---|---|
| via AEM | AEM beheert injectiebibliotheken waar dat<br>nodig isBronnen hoeven alleen op AEM te worden onderhouden | Mogelijk onbekend aan ontwikkelaar van SPA |
| via Adobe I/O Runtime | Vertrouwelijker aan ontwikkelaars van het KUUROORD | Clientlib-bronnen die door de toepassing worden vereist, zoals CSS en JavaScript, moeten door de AEM-ontwikkelaar beschikbaar worden gesteld via de [`allowProxy` eigenschap](/help/sites-developing/clientlibs.md#locating-a-client-library-folder-and-using-the-proxy-client-libraries-servlet)<br>Resources moeten worden gesynchroniseerd tussen AEM en Adobe I/O<br>RuntimeVoor het maken van de SPA is mogelijk een proxyserver voor Adobe I/O Runtime nodig. |

## Planning voor SSR {#planning-for-ssr}

Over het algemeen hoeft slechts een deel van een toepassing aan serverzijde te worden gerenderd. Het algemene voorbeeld is de inhoud die boven de voud wordt weergegeven wanneer de pagina voor het eerst wordt geladen en op de server moet worden weergegeven. Dit bespaart tijd door aan de cliënt, reeds teruggegeven inhoud te leveren. Aangezien de gebruiker met het KUUROORD in wisselwerking staat, wordt de extra inhoud teruggegeven door de cliënt.

Aangezien u overweegt het uitvoeren van server het zijteruggeven voor uw SPA, moet u herzien welke delen van app het SSR zal vereisen.

## Het ontwikkelen van een SPA die SSR gebruikt {#developing-an-spa-using-ssr}

De componenten van het KUUROORD zouden door de cliënt (in browser) of serverkant kunnen worden teruggegeven. Bij rendering op de server zijn browsereigenschappen zoals venstergrootte en -locatie niet aanwezig. Daarom zouden de componenten van het KUUROORD isomorf moeten zijn, die geen veronderstelling maken over waar zij zullen worden teruggegeven.

Als u SSR wilt gebruiken, moet u uw code zowel in AEM als in Adobe I/O Runtime implementeren, die verantwoordelijk is voor de rendering aan de serverzijde. De meeste code zijn hetzelfde, maar serverspecifieke taken verschillen.

## SSR voor SPA’s in AEM {#ssr-for-spas-in-aem}

SSR voor SPA&#39;s in AEM vereist Adobe I/O-runtime, die wordt aangeroepen voor het renderen van de zijde van de toepassingsinhoudsserver. Binnen de HTML van de app wordt een resource in Adobe I/O Runtime aangeroepen om de inhoud te renderen.

Net zoals AEM de Hoekse en Reacte kaders van het KUUROORD buiten de doos steunt, wordt de server zijrendering ook gesteund voor Hoekige en Reacte apps. Zie de NPM documentatie voor beide kaders voor verdere details.

* Reageren: [https://github.com/adobe/aem-sample-we-retail-journal/blob/master/react-app/DEVELOPMENT.md#enabling-the-server-side-rendering-using-the-aem-page-component](https://github.com/adobe/aem-sample-we-retail-journal/blob/master/react-app/DEVELOPMENT.md#enabling-the-server-side-rendering-using-the-aem-page-component)
* Hoek: [https://github.com/adobe/aem-sample-we-retail-journal/blob/master/react-app/DEVELOPMENT.md#enabling-the-server-side-rendering-using-the-aem-page-component](https://github.com/adobe/aem-sample-we-retail-journal/blob/master/react-app/DEVELOPMENT.md#enabling-the-server-side-rendering-using-the-aem-page-component)

Voor een simplistisch voorbeeld raadpleegt u de app [](https://github.com/Adobe-Marketing-Cloud/aem-sample-we-retail-journal)We.Retail Journal. Het rendert de volledige kant van de toepassingsserver. Hoewel dit geen echt voorbeeld is, toont het wel wat nodig is om SSR uit te voeren.

>[!CAUTION]
>De app [](https://github.com/Adobe-Marketing-Cloud/aem-sample-we-retail-journal) We.Retail Journal is alleen bedoeld als demonstratie en gebruikt daarom Node.js als eenvoudig voorbeeld in plaats van de aanbevolen Adobe I/O-runtime. Dit voorbeeld zou niet voor om het even welk projectwerk moeten worden gebruikt.

>[!NOTE]
>Alle projecten van het KUUROORD op AEM zouden op [Maven Archetype voor Kit](https://github.com/adobe/aem-spa-project-archetype)van de Aanzet van het KUUROORD moeten worden gebaseerd.

## Node.js gebruiken {#using-node-js}

Adobe I/O Runtime is de geadviseerde oplossing voor het uitvoeren SSR voor SPAs in AEM.

Voor AEM-instanties ter plaatse is het ook mogelijk SSR te implementeren met een aangepaste Node.js-instantie op dezelfde manier als hierboven beschreven. Hoewel dit wordt ondersteund door Adobe, wordt dit niet aanbevolen.

Node.js wordt niet ondersteund voor door Adobe gehoste AEM-instanties.

>[!NOTE]
>
>Als SSR via Node.js moet worden geïmplementeerd, raadt Adobe een aparte instantie Node.js aan voor elke AEM-omgeving (auteur, publicatie, werkgebied, enz.).

## Renderer voor externe inhoud {#remote-content-renderer}

De [Verre Configuratie](#remote-content-renderer-configuration) van Renderer van de Inhoud die wordt vereist om SSR met uw KUUROORD in AEM te gebruiken staps in een meer algemene het teruggeven dienst die kan worden uitgebreid en worden aangepast om aan uw behoeften te voldoen.

### RemoteContentRenderingService {#remotecontentrenderingservice}

`RemoteContentRenderingService` is een OSGi-service voor het ophalen van inhoud die op een externe server wordt gerenderd, zoals van Adobe I/O. De inhoud die naar de externe server wordt verzonden, is gebaseerd op de doorgegeven parameter request.

`RemoteContentRenderingService` kan door gebiedsinversie in of een douaneSling model of servlet worden geïnjecteerd wanneer de extra inhoudsmanipulatie wordt vereist.

Deze service wordt intern gebruikt door de [RemoteContentRendererRequestHandlerServlet](#remotecontentrendererrequesthandlerservlet).

### RemoteContentRendererRequestHandlerServlet {#remotecontentrendererrequesthandlerservlet}

Het `RemoteContentRendererRequestHandlerServlet` kan worden gebruikt om de verzoekconfiguratie programmatically te plaatsen. `DefaultRemoteContentRendererRequestHandlerImpl`, staat de verstrekte implementatie van de standaardverzoekmanager, u toe om veelvoudige configuraties tot stand te brengen OSGi om een plaats in de inhoudsstructuur aan een ver eindpunt in kaart te brengen.

Om een manager van het douaneverzoek toe te voegen, voer de `RemoteContentRendererRequestHandler` interface uit. Ben zeker om het `Constants.SERVICE_RANKING` componentenbezit aan een geheel te plaatsen hoger dan 100, dat de rangschikking van `DefaultRemoteContentRendererRequestHandlerImpl`is.

```
@Component(immediate = true,
        service = RemoteContentRendererRequestHandler.class,
        property={
            Constants.SERVICE_RANKING +":Integer=1000"
        })
public class CustomRemoteContentRendererRequestHandlerImpl implements RemoteContentRendererRequestHandler {}
```

### Vorm de Configuratie OSGi van de Standaardmanager {#configure-default-handler}

De configuratie van de standaardmanager moet worden gevormd zoals die in de sectie [Verre Configuratie](#remote-content-renderer-configuration)van Renderer van Inhoud wordt beschreven.

###  Renderergebruik van externe inhoud {#usage}

Om een servlet te hebben halen en wat inhoud terug te keren die in de pagina kan worden ingespoten:

1. Controleer of uw externe server toegankelijk is.
1. Voeg een van de volgende fragmenten toe aan de HTML-sjabloon van een AEM-component.
1. Naar keuze, creeer of wijzig de configuraties OSGi.
1. Door de inhoud van uw site bladeren

Gewoonlijk is de HTML-sjabloon van een paginacomponent de belangrijkste ontvanger van een dergelijke functie.

```
<sly data-sly-resource="${resource @ resourceType='cq/remote/content/renderer/request/handler'}" />
```

### Vereisten {#requirements}

De servers maken gebruik van de Sling Model Exporter om de componentgegevens te serialiseren. Standaard worden zowel de `com.adobe.cq.export.json.ContainerExporter` `com.adobe.cq.export.json.ComponentExporter` als de Sling Model-adapters ondersteund. Indien nodig, kunt u klassen toevoegen die het verzoek zou moeten worden aangepast aan het gebruiken van `RemoteContentRendererServlet` en het uitvoeren van `RemoteContentRendererRequestHandler#getSlingModelAdapterClasses`. De extra klassen moeten het `ComponentExporter`uitbreiden.
