---
title: Mobiele apps testen
seo-title: Testing Mobile Apps
description: Mobiele apps testen
seo-description: null
uuid: 3b402d34-5cab-4280-b8b9-88ad9f8fc5e4
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/MOBILE
topic-tags: developing
content-type: reference
discoiquuid: 5a98e1bd-f5c1-4f2f-ac02-dbd005dc1de7
exl-id: 2a70f322-2540-471e-8a8e-6d48889cf94a
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1061'
ht-degree: 0%

---

# Mobiele apps testen{#testing-mobile-apps}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

>[!NOTE]
>
>Adobe raadt aan de SPA Editor te gebruiken voor projecten die renderen op basis van één pagina voor toepassingsframework op de client-side vereisen (bijvoorbeeld Reageren). [Meer informatie](/help/sites-developing/spa-overview.md).

Gezien het grote aantal apparaten op de markt en de apparaten die worden vrijgegeven, is het testen van uw Apps uiterst belangrijk geworden. Dit is een gebied waarop functionaliteit en bruikbaarheid lage revisies kunnen opleveren op een App Store, maar één fout kan ertoe leiden dat uw app wordt verwijderd. In uw testplannen en kwaliteitsborging moet zorgvuldig aandacht worden besteed. De volgende koppeling heeft betrekking op veel van de onderwerpen die in het algemeen moeten worden behandeld, zoals het identificeren van uw omgeving, het definiëren van testgevallen, typen tests, veronderstellingen, betrokkenheid van klanten, enz. Ook worden de hulpmiddelen besproken om in de testende inspanning te helpen. Interne gereedschappen, zoals [Hobbes](/help/sites-developing/hobbes.md), kan u helpen bij het testen van de gebruikersinterface op internet. [Dag](/help/sites-developing/tough-day.md) kan uw instanties met een gesimuleerde lading stress geven. Als uw testomgeving al ervaring heeft met hulpmiddelen van derden, zoals Selenium, kunnen deze ook worden gebruikt.

Bij de ontwikkeling van een mobiele app zijn er veel nieuwe problemen die specifiek zijn voor apparaten die samen met de traditionele tests moeten worden aangepakt.

* Functioneel - Voldoet uw app aan alle vereisten?
* Gebruiksmogelijkheden - Is de toepassing gebruiksvriendelijk en begrijpelijk voor uw klant?
* Prestaties - Wat gebeurt er tijdens een piek in het gebruik? Zijn de app-elementen, zoals vegen en carrousels, snel en trekken ze niet uit de ervaring?
* Mislukking of Onderbreking - wat gebeurt wanneer er een inkomende vraag of bericht terwijl uw app loopt is? Wat gebeurt als er een netwerkstroomonderbreking of macht weg is?
* Installatie en updates - Hoe wordt de installatie uitgevoerd? Hoe worden updates uitgeduwd?
* Technisch - verbruikt uw app te veel stroom van een apparaat?
* Lokalisatie - Zijn alle gebieden in uw app vertaald?
* Certificering - Is uw app gecertificeerd? Kunnen klanten erop vertrouwen dat het voldoet aan alle wettelijke vereisten inzake privacy van gegevens?

Deze vragen moeten tijdens uw geautomatiseerde en handmatige tests worden beantwoord.

## Automatisch testen {#automated-testing}

Er moet enige mate van geautomatiseerde tests worden uitgevoerd om de verschillende schermgrootten, geheugenbeperkingen, invoermethoden en besturingssystemen te bestrijken. Niet alleen bestrijkt het veel testgevallen, maar het kan regressietests versnellen wanneer nieuwe eigenschappen of apparaten worden geïntroduceerd. Idealiter zouden uw automatiseringsprogramma&#39;s dubbel werk moeten verminderen of beperken. Gebruik gereedschappen of frameworks zodat uw testwerkzaamheden op alle platforms van toepassing zijn. In het volgende diagram ziet u een vereenvoudigde structuur van een testomgeving voor het testen van gebruikersinterface op internet en voor het testen van mobiele apps. Links in het diagram ziet u een reeks Selenium-knooppunten met browsers. SeleniumGrid kan gemeenschappelijke, web-based tests UI aan om het even welk van deze knopen landbouwbedrijf. De Selenium-hub kan ook verbinding maken met Appium voor het testen van apps voor verschillende platforms. Alleen weergegeven zijn simulatoren, maar u kunt adb, voor Android en Xcode-hulpprogramma&#39;s voor iOS-apparaten opnemen. De verbindingen worden verstrekt later in dit document waar u specifieke details voor de vermelde hulpmiddelen kunt vinden.

![chlimage_1](assets/chlimage_1.jpeg)

## Handmatig testen {#manual-testing}

Uw app moet niet alleen automatisch testen, maar ook handmatig testen. Klanten die de app op een echt apparaat uitvoeren, kunnen niet door een script worden gedupliceerd. Ook hier hebt u veel mogelijkheden. U kunt een platform, zoals HockeyApp, gebruiken om te bepalen wie toegang heeft en verzamelt terugkoppelt. Of u kunt het hele proces uitbesteden aan een service zoals UTest, ElusiveStars of Testin. Als u een groep interne testers hebt, maar geen apparaatvariatie hebt, zijn er cloudservices waarmee u handmatige tests kunt uitvoeren op hun aantal apparaten. Een van die services is SauceLabs. U kunt ook op afstand toepassingen maken op PhoneGap Enterprise en deze op lokale apparaten installeren voor acceptatietests of demoing. Zie de [PhoneGap](https://phonegap.com/) website voor de meest recente functies en documentatie. Ongeacht de aanpak moeten handmatige tests worden uitgevoerd;

* een groot doelwit van testers bereiken;
* test tegen een grote groep apparaten (idealiter echte apparaten, maar simulatoren/emulators als er geen echte apparaten beschikbaar zijn);
* Feedback geven:

   * crashrapporten;
   * analyse/tracering;
   * bruikbaarheid,
   * aandachtsgebieden,
   * prestaties,
   * gegevens/energieverbruik enz.

## Gereedschappen {#tools}

Er is een groot aantal gereedschappen beschikbaar voor het testen van mobiele apps. De keuze van degenen die u wilt gebruiken, is gebaseerd op uw specifieke situatie: kenmerken, prijs, ondersteuning, dekking, enz. Hieronder volgt slechts een kleine beschrijving van een aantal beschikbare gereedschappen en services.

**Selenium**

* Kader dat API voor testmanuscripten omvat om WebDriver te voeren en diverse browsers te controleren.
* U kunt dit in combinatie met Appium gebruiken voor tests op echte apparaten.
* SeleniumGrid leidt tests over knopen voor parallel testen.
* Met de Selenium IDE kunt u het schrijven van testcase verminderen.

Zie voor meer informatie [https://www.seleniumhq.org/](https://www.seleniumhq.org/).

**Testdroid**

* Een testservice op basis van de cloud met continue integratie en echte apparaattests.
* Omvat App Crawler die apparatenverenigbaarheid controleert, logboeken analyseert, meningen oversteekt, screenshots neemt, en prestaties controleert.

Zie voor meer informatie [https://testdroid.com/](https://testdroid.com/).

**Appium**

* Appium is een populair platformframework voor het automatiseren van mobiele tests.
* Bovendien is een inspecteur inbegrepen met verslagmogelijkheden om codetestgevallen te helpen.

Zie voor meer informatie [https://appium.io/](https://appium.io/).

**SauceLabs**

* SauceLabs biedt tests in de cloud en integreert deze met continue integratie.
* Tests worden automatisch uitgevoerd in de cloud-omgeving of u kunt een bepaald apparaat of platform starten en handmatig testen uitvoeren om problemen met foutopsporing te verhelpen.

Zie voor meer informatie [https://saucelabs.com/](https://saucelabs.com/).

**AppTestNow**

* Een outsourcingservice waarmee uw mobiele apps worden getest.
* Omvat een grote groep apparaten en biedt een breed scala aan testtypen: prestaties, kwaliteit, functionaliteit, certificering, lokalisatie, gegevensverbruik, enz.

Zie voor meer informatie [https://www.apptestnow.com](https://www.apptestnow.com/).

**HockeyApp**

* HockeyApp valt onder de handmatige tests waarbij de mobiele app naar een persoonlijke app-winkel wordt gestuurd waar de testers de app kunnen downloaden en uitproberen.

Zie voor meer informatie [https://hockeyapp.net/features/](https://hockeyapp.net/features/).

**Jenkins**

* Hoewel Jenkins geen testinstrument is, is het een doorlopend integratieframework dat de ruggengraat vormt voor geautomatiseerde tests. Er zijn talloze plug-ins van derden beschikbaar om de functionaliteit uit te breiden. De insteekmodule SeleniumGrid biedt bijvoorbeeld een UI voor het beheren van de Selenium-hub en -knooppunten.

Zie voor meer informatie [https://jenkins-ci.org/](https://jenkins-ci.org/) en [https://wiki.jenkins-ci.org/display/JENKINS/Plugins](https://wiki.jenkins-ci.org/display/JENKINS/Plugins).
