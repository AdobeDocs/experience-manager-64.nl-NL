---
title: Best practices voor het testen van prestaties
seo-title: Best practices voor het testen van prestaties
description: In dit artikel worden de algemene strategieën en methoden beschreven die voor het testen van de prestaties worden gebruikt, alsmede enkele instrumenten die beschikbaar zijn om het proces te helpen.
seo-description: In dit artikel worden de algemene strategieën en methoden beschreven die voor het testen van de prestaties worden gebruikt, alsmede enkele instrumenten die beschikbaar zijn om het proces te helpen.
uuid: ab8720d6-b864-4d00-9e07-2e1699cfe7db
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: best-practices
discoiquuid: 669018a0-f6ef-42b2-9c6f-83d7dd5a7095
translation-type: tm+mt
source-git-commit: 1a87e927ada393524962f0ad7db93097a3cfab5b
workflow-type: tm+mt
source-wordcount: '1925'
ht-degree: 0%

---


# Best practices voor het testen van prestaties{#best-practices-for-performance-testing}

## Inleiding {#introduction}

Het testen van prestaties is een belangrijk deel van om het even welke AEM plaatsing. Afhankelijk van de vereisten van de klant kunnen de prestaties worden getest op de publicatie-instanties, de auteur-instanties of beide.

In deze documentatie worden algemene strategieën en methodologieën voor het uitvoeren van prestatietests beschreven, alsmede enkele instrumenten die door Adobe beschikbaar worden gesteld om het proces te ondersteunen. Tot slot zullen wij enkele hulpmiddelen analyseren die in AEM 6 beschikbaar zijn om met prestaties het stemmen, zowel vanuit een codeanalyse als perspectief van de systeemconfiguratie te helpen.

### Realiteit simuleren {#simulating-reality}

Wat het belangrijkst is wanneer het uitvoeren van prestatietests is ervoor te zorgen dat u een productiemilieu zo dicht mogelijk nastreeft. Hoewel dit vaak moeilijk kan zijn, is het absoluut noodzakelijk de nauwkeurigheid van deze tests te waarborgen. Wanneer het werken aan het ontwerpen van prestatietests, is het belangrijk om de volgende punten in overweging te nemen:

* Productie-achtige inhoud

Veel prestatiemetingen in AEM, zoals de tijd van de vraagreactie, kunnen door de grootte van de inhoud op het systeem worden beïnvloed. Het is belangrijk ervoor te zorgen dat de testomgeving zo dicht mogelijk een kopie van de productiegegevens heeft.

* Productiecode

De AEM versie en hotfixes die in productie worden ingezet, moeten in de testomgeving hetzelfde zijn. Het is ook belangrijk om op de versie van de code te testen die aan productie wordt opgesteld.

* Productieachtige hardware en netwerkconfiguratie

De tests zijn zinloos zonder een omgeving die zoveel mogelijk op de productie lijkt. In het ideale geval moeten de hardwarespecificaties, de netwerkinterfaces, de taakverdelingsmechanismen en de CDN identiek zijn aan de productie in de testomgeving.

* Productiebelasting

Veel prestatieproblemen worden pas zichtbaar wanneer het systeem zwaar belast is. Goede prestatietests moeten de belasting simuleren die de productiesystemen op hun hoogtepunt zullen beleven.

### Doelstellingen instellen {#setting-goals}

Voordat wordt begonnen met het testen van de prestaties, moeten niet-functionele eisen worden vastgesteld om de belasting- en responstijden te bepalen. Als u van een bestaand systeem migreert, zorg ervoor dat de reactietijd aan uw huidige productiewaarden gelijkaardig is. Voor lading, is het best om de huidige pieklading te nemen en te verdubbelen. Hierdoor kan de website goed blijven functioneren terwijl deze groeit.

### Opties {#tools}

Er zijn veel commercieel verkrijgbare hulpmiddelen voor het testen van prestaties op de markt. Wanneer het runnen van een lading die hulpmiddel produceert, is het belangrijk om ervoor te zorgen dat de computers die de tests uitvoeren voldoende netwerkbandbreedte hebben. Als de testmachine de grenzen van de verbinding bereikt, wordt geen extra belasting in de testomgeving gegenereerd.

#### Testgereedschappen {#testing-tools}

* Met het gereedschap **Dag** van de Adobe kunt u belasting genereren op AEM en prestatiegegevens verzamelen. Het AEM engineeringteam van Adobe gebruikt het gereedschap voor het testen van de belasting van het AEM product zelf. De scripts die op de Dag van de Hoek worden uitgevoerd, worden gevormd via bezitsdossiers en JMX XML- dossiers. Raadpleeg de documentatie [van](/help/sites-developing/tough-day.md)Tough Day voor meer informatie.

* AEM verstrekt uit de vakhulpmiddelen om problematische vragen, verzoeken en foutenmeldingen snel te zien. Zie de sectie [Diagnosetools](/help/sites-administering/operations-dashboard.md#diagnosis-tools) in de documentatie van het vluchthandboek voor meer informatie.
* Apache biedt een product met de naam **JMeter** dat kan worden gebruikt voor prestatie- en belastingtests en functioneel gedrag. Het is open-sourcesoftware en vrij te gebruiken, maar heeft een kleinere functieset dan bedrijfsproducten en een steile leercurve. JMeter is te vinden op de website van Apache op [https://jmeter.apache.org/](https://jmeter.apache.org/)

* **Load Runner** is een testproduct voor het laden van bedrijfsniveau. Er is een gratis evaluatieversie beschikbaar. Meer informatie is te vinden op [https://www.microfocus.com/en-us/products/loadrunner-load-testing/overview](https://www.microfocus.com/en-us/products/loadrunner-load-testing/overview)

* U kunt ook gereedschappen voor laadtests op basis van cloud gebruiken, zoals [Neustar](https://www.neustar.biz/services/web-performance/load-testing) .
* Wanneer het gaat om het testen van mobiele of responsieve websites, moet een aparte set hulpmiddelen worden gebruikt. They work by throttling network bandwidth, simulating slower mobile connections like 3G or EDGE. Among the more widely used tools are:

   * **[Network Link Conditioner](https://nshipster.com/network-link-conditioner/)**- it provides an easy to use UI and works at a fairly low level on the networking stack. It includes versions for OS X and iOS;[](https://nshipster.com/network-link-conditioner/)
   * [**Charles **](https://www.charlesproxy.com/)- een Web het zuiveren volmachtstoepassing die naast verscheidene andere toepassingen, netwerkthrottling verstrekt. Versies zijn beschikbaar voor Windows, OS X en Linux.[](https://www.charlesproxy.com/)

#### Optimalisatieprogramma&#39;s {#optimization-tools}

**Bewaking**

De documentatie van de Prestaties [van de](/help/sites-deploying/monitoring-and-maintaining.md#monitoring-performance) Controle is een goede middel voor hulpmiddelen en methodes die kunnen worden gebruikt om kwestie en puntgebieden voor het stemmen te diagnostiseren.

**Modus voor ontwikkelaars in Touch UI**

Een van de nieuwe functies in de aanraakinterface van AEM 6 is de Developer Mode. Net zoals ontwerpers kunnen schakelen tussen bewerkings- en voorvertoningsmodi, kunnen ontwikkelaars overschakelen naar de modus voor ontwikkelaars in de gebruikersinterface om de rendertijd voor elk van de componenten op de pagina te zien en stacksporen van eventuele fouten te zien. Zie deze [CQ Gems-presentatie](https://docs.adobe.com/content/ddc/en/gems/aem-6-0-developer-mode.html)voor meer informatie over de modus Ontwikkelaar.

**Het gebruiken van rlog.jar om de verzoeklogboeken te lezen**

Voor een uitgebreidere analyse van de aanvraag meldt u zich aan bij een AEM, `rlog.jar` kunt u de `request.log` bestanden die AEM genereert doorzoeken en sorteren. Dit jar-bestand wordt samen met een AEM in de `/crx-quickstart/opt/helpers` map geïnstalleerd. Voor meer informatie over rlog hulpmiddel en het verzoeklogboek in het algemeen, zie de [Controle en het Onderhouden](/help/sites-deploying/monitoring-and-maintaining.md) documentatie.

**Het gereedschap Uitleg query**

Het [Uitdrukkelijke hulpmiddel](/help/sites-administering/operations-dashboard.md#explain-query) van de Vraag in ACS AEM Hulpmiddelen kan worden gebruikt om de indexen te bekijken die wanneer het runnen van een vraag worden gebruikt. Dit kan zeer nuttig zijn wanneer het optimaliseren van langzaam lopende vragen.

**PageSpeed-gereedschappen**

De PageSpeed-programma&#39;s van Google bieden een siteanalyse voor het volgen van de aanbevolen procedures voor paginaprestaties en een insteekmodule die naast de dispatcher op een Apache-instantie kan worden geïnstalleerd voor extra optimalisaties. Zie de website [PageSpeed Tools voor meer informatie](https://developers.google.com/speed/pagespeed/).

## Auteursomgeving {#author-environment}

### Performing Tests {#performing-tests}

Voor het uitvoeren van prestatietests in de auteursomgeving is het nodig dat u de ervaring van productiefouteurs simuleert. Dit betekent dat de auteursinstallaties alle componenten, bundels OSGi, UI aanpassing, douaneindexes en andere toevoegingen moeten bevatten u voor de instanties van de productiesauteur op zijn plaats hebt.

There are many automation frameworks available that are designed for performance and load testing. Custom scripts can be recorded in these tools and then played back to simulate a peak number of authors performing similar content creation and activation activities simultaneously. U wordt aangeraden het gereedschap Onvoldoende dag te gebruiken om activiteiten te simuleren, zoals het uploaden van duizenden elementen of het activeren van een groot aantal pagina&#39;s.

For the types of environments that have requirements of heavy asset loading or page authoring it is imperative to use tools like Tough Day in order to ensure that the environment will operate efficiently under peak load. [WebDAV](/help/sites-administering/webdav-access.md) is een hulpmiddel dat geen scripting vereist en kan ook worden gebruikt om grote hoeveelheden activa te laden.

#### MongoDB Specific Steps {#mongodb-specific-steps}

On systems with MongoDB backends, AEM provides several [JMX](/help/sites-administering/jmx-console.md) MBeans that need to be monitored when performing load or performance tests:

* The **Consolidated Cache Statistics** MBean. Het kan direct worden betreden door te gaan:

`https://server:port/system/console/jmx/org.apache.jackrabbit.oak%3Aid%3D6%2Cname%3D%22Consolidated+Cache+statistics%22%2Ctype%3D%22ConsolidatedCacheStats%22`

For the cache named **Document-Diff**, the hit rate should be over `.90`. If the hit rate falls below 90%, it is likely that you will need to modify your `DocumentNodeStoreService` configuration. Adobe product support can recommend optimal settings for your environment.

* The **Oak Repository Statistics** Mbean. Het kan direct worden betreden door te gaan:

`https://server:port/system/console/jmx/org.apache.jackrabbit.oak%3Aid%3D16%2Cname%3D%22Oak+Repository+Statistics%22%2Ctype%3D%22RepositoryStats%22`

The **ObservationQueueMaxLength** section will show the number of events in Oak’s observation queue over the last hours, minutes, seconds and weeks. Find the largest number of events in the &quot;per hour&quot; section. This number needs to be compared to the `oak.observation.queue-length` setting which can be found in the **SlingRepositoryManager** component in the [OSGi console](/help/sites-deploying/web-console.md). If the highest number shown for the observation queue exceeds the `queue-length` setting, contact Adobe Support for assistance with raising the setting. The default setting is 1,000, but most deployments usually need to raise it to 20,000 or 50,000.

## Publicatie-omgeving {#publish-environment}

### Performing Tests {#performing-tests-1}

The most important part of a deployment that needs to be subjected to load tests is the end user facing publish or dispatcher environment.

Third party automated testing tools can be used to test the performance of the website. These tools will allow you to record steps that users will go through on the site and run many of these sessions at the same time to simulate the load that is typical of a production website.

Most production websites have optimizations in place like dispatcher caching and a content delivery network in place. When testing, you need to make sure that these optimizations are available for the test environment as well. In addition to monitoring response times for the end users, you also need to monitor system metrics on the publish servers and dispatchers to ensure that the system is not constrained by hardware resources.

On a system that does not require a high level of personalization, the dispatcher should cache most requests. As a result, the load on the publish instance should remain relatively flat. If a high level of personalization is required, it is recommended to use technologies such as iFrames or AJAX requests for the personalized content so as to allow as much dispatcher caching as possible.

For basic tests, Apache Bench can be used to measure web server response times and help to create load for measuring things like memory leaks. For more see the example in the [Monitoring documentation](/help/sites-deploying/monitoring-and-maintaining.md#apache-bench).

## Troubleshooting Performance Issues {#troubleshooting-performance-issues}

After running performance tests on the author instance, any issues will need to be investigated, diagnosed and addressed. U kunt verschillende gereedschappen en technieken gebruiken bij het uitvoeren van analyses en het aanpakken van problemen:

* U kunt het logboek [van de Prestaties van het](/help/sites-administering/operations-dashboard.md#request-performance) Verzoek in het Dashboard van Verrichtingen inspecteren. Dit gereedschap kan worden gebruikt om aanvragen voor langzame pagina&#39;s te identificeren
* Langzame vragen analyseren met het gereedschap [Query-prestaties](/help/sites-administering/operations-dashboard.md#query-performance)

* Bekijk de foutlijst voor fouten of waarschuwingen. For more information, see [Logging](/help/sites-deploying/configure-logging.md)
* De hardwarebronnen van het systeem controleren, zoals geheugen en CPU-gebruik, schijf-I/O of netwerk-I/O. Deze middelen zijn vaak de oorzaken van prestatiesknelpunten
* Optimaliseer de architectuur van de pagina&#39;s en hoe zij worden gericht om het gebruik van URL parameters te minimaliseren om voor zoveel mogelijk caching mogelijk toe te staan
* Volg de documentatie over het optimaliseren van [prestaties](/help/sites-deploying/configuring-performance.md) en het afstemmen van [prestaties](https://helpx.adobe.com/experience-manager/kb/performance-tuning-tips.html)

* If issues are present with editing certain pages or components on author instances, use the TouchUI Developer Mode to inspect the page in question. Hierdoor wordt een uitsplitsing van elk inhoudsgebied op de pagina en de laadtijd gegenereerd
* Minify all JS and CSS on the site. For more information on how to do this, see this [blog post](https://blogs.adobe.com/foxes/enable-js-and-css-minification/).
* Eliminate embedded CSS and JS from the components. They should be included and minified with the client-side libraries to minimize the number of requests required to render the page
* Use browser tools like Chrome’s Network tab to inspect the server requests and see which are taking the longest.

Once problem areas are identified, application code can be inspected for performance optimizations. Any out of the box AEM features that are not performing properly can be addressed with Adobe Support.
