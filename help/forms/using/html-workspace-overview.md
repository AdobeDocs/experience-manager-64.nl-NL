---
title: Werken met de werkruimte AEM Forms
seo-title: Werken met de werkruimte AEM Forms
description: Ga aan de slag met de werkruimte AEM Forms met dit korte overzicht van de procesworkflows.
seo-description: Ga aan de slag met de werkruimte AEM Forms met dit korte overzicht van de procesworkflows.
uuid: fac103bd-142b-46cc-9db7-22d1880260f8
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: ebabecb9-91c4-4991-8f5b-d27f940d2ecb
translation-type: tm+mt
source-git-commit: 7c65752a969d9089ad61c29b0581327d32e022d1
workflow-type: tm+mt
source-wordcount: '1082'
ht-degree: 0%

---


# Werken met de werkruimte AEM Forms {#working-with-aem-forms-workspace}

## Inleiding {#introduction}

De werkruimte van AEM Forms maakt deel uit van AEM Forms. De werkruimte vergemakkelijkt de uitvoering van HTML-formulieren, naast PDF forms. Nu kunt u aan bedrijfsprocessen van mobiele interfaces en Webtoepassingen in dienst nemen.

Bovendien is de werkruimte AEM Forms in hoge mate aanpasbaar met de standaard HTML- en JavaScript™-ontwikkelingsmethoden. Het is software op basis van componenten die eenvoudig kan worden geïntegreerd met andere webtoepassingen.

Voor meer informatie, zie [Inleiding aan de werkruimte](/help/forms/using/introduction-html-workspace.md)van AEM Forms.

## Kennis krijgen {#getting-familiar}

Om vertrouwd met het proces van begin tot eind te zijn om een vormtoepassing te creëren om een bedrijfsproces te automatiseren, volg de analyse. U kunt een toepassing maken, beheren en testen met Workbench, Designer en AEM Forms nadat u de stappen hebt uitgevoerd. Voor implementatiedetails, zie het [Creëren van Uw Eerste Toepassing](https://help.adobe.com/en_US/livecycle/11.0/CreateFirstApp/index.html)van AEM Forms.

## Functioneel overzicht {#functional-overview}

U kunt de werkruimte AEM Forms gebruiken om de volgende taken uit te voeren:

**Een bedrijfsproces starten:** De werkruimte van AEM Forms categoriseert uw processen zoals ontworpen en opstelling door uw organisatie. U kunt de veelgebruikte categorieën als favoriet gebruiken om snel tot de categorieën toegang te hebben. Wanneer u een proces start, vult u doorgaans een formulier in om een bedrijfsproces te starten dat de werkstroom van formulieren beheert. Zie Processen [starten voor meer informatie](/help/forms/using/starting-processes.md).

**Taken weergeven en uitvoeren:** Wanneer u uw lijst te doen bekijkt, ziet u taken van een bedrijfsproces die aan u, of aan om het even welke groepen worden toegewezen die u tot behoort, of zijn de gedeelde taken van andere gebruikers. U kunt de taken naar wens openen, bewerken en voltooien. Het uitvoeren van een taak omvat meestal het verstrekken van informatie, het goedkeuren van een formulier of het afwijzen van een formulier. Voor meer informatie, zie het [Werken met te doen lijsten](/help/forms/using/todo-lists.md).

**Taken** bijhouden: Als u uw taken wilt bijhouden, gebruikt u het tabblad Bijhouden van de werkruimte AEM Forms. U kunt zoeken naar actieve of voltooide processen waaraan u bent begonnen of deelgenomen. U kunt de taken, toewijzingen en formulieren weergeven die deel uitmaakten van het proces. U kunt ook nieuwe processen starten met formuliergegevens uit een proces dat u eerder hebt gestart. Zie [Trackingprocessen](/help/forms/using/tracking-processes.md)voor meer informatie.

## Nieuwe aanbieding van de werkruimte van AEM Forms {#new-offering-of-aem-forms-workspace}

**Steun voor bulkgoedkeuring van taken**:

U kunt meerdere taken van hetzelfde type goedkeuren. Zodra u één taak voor goedkeuring selecteert, slechts blijven de taken met het zelfde proces, met de zelfde taaknamen, en de zelfde routeopties toegelaten. Zie [Werken met lijsten](/help/forms/using/todo-lists.md) van taken voor details van de implementatie.

## Migreren van Flex-werkruimte naar AEM Forms-werkruimte {#migrating-from-flex-workspace-to-aem-forms-workspace}

**Wat blijft werken**

AEM Forms op JEE implementeren standaard ook Flex Workspace. Het blijft werken zoals vroeger en al uw bestaande processen en aanpassingen blijven werken.

**Bestaande processen migreren naar de werkruimte AEM Forms:**

In de werkruimte AEM Forms zijn de standaardservices voor renderen en verzenden in het standaardactieprofiel gewijzigd en zijn nieuwe services geïntroduceerd. Voor details, zie [Nieuw teruggeven en de dienst](/help/forms/using/new-render-submit-service.md)voorleggen. Als u bestaande processen die werken met XDP-formulieren wilt migreren en gebruik wilt maken van deze services, kunt u [deze stappen](/help/forms/using/new-render-submit-service.md)volgen.

**Aanpassingen van Flex-werkruimten toewijzen aan de werkruimte AEM Forms:**

De toewijzing tussen diverse soorten aanpassingen in beide werkruimten is als volgt.

<table> 
 <tbody>
  <tr>
   <td><strong>Type aanpassing </strong></td> 
   <td><strong>Bedekte aanpassingen </strong></td> 
   <td><strong>Overeenkomende aanpassingsscenario voor werkruimte van AEM Forms</strong></td> 
  </tr>
  <tr>
   <td>Lokalisatie aanpassen</td> 
   <td>
    <ol> 
     <li>Landinstelling van werkruimte wijzigen</li> 
    </ol> </td> 
   <td>
    <ol> 
     <li><a href="/help/forms/using/changing-locale-user-interface.md">Landinstelling werkruimte AEM Forms wijzigen</a></li> 
    </ol> </td> 
  </tr>
  <tr>
   <td>Aanpassing thema</td> 
   <td>
    <ol> 
     <li>Afbeeldingen vervangen</li> 
     <li>Kleuren wijzigen</li> 
    </ol> </td> 
   <td>
    <ol> 
     <li><a href="/help/forms/using/changing-organization-logo-branding.md">Organisatie-logo wijzigen</a> </li> 
     <li><a href="/help/forms/using/changing-color-scheme-interface.md">Kleurenschema wijzigen</a></li> 
    </ol> </td> 
  </tr>
  <tr>
   <td>Layout aanpassen</td> 
   <td>
    <ol> 
     <li>De gebruikersinterface van de werkruimte vereenvoudigen<br /> </li> 
     <li>Een nieuw aanmeldingsscherm maken</li> 
     <li>Een aangepaste goedkeuringscontainer maken</li> 
    </ol> </td> 
   <td>
    <ol> 
     <li><a href="/help/forms/using/description-reusable-components.md">Werken met herbruikbare componenten</a></li> 
     <li><a href="/help/forms/using/creating-new-login-screen.md">Een nieuw aanmeldingsscherm maken</a></li> 
     <li>Goedkeuringscontainer is afgekeurd.</li> 
    </ol> </td> 
  </tr>
 </tbody>
</table>

### Beperkingen van de werkruimte van AEM Forms {#limitations-of-aem-forms-workspace}

Enkele functies van de Flex-werkruimte die niet beschikbaar zijn in de werkruimte AEM Forms, zijn onder andere: berichten en meldingen, welkomstpagina, goedkeuringscontainer en optie voor het beheren van kolomkoppen. Zie [Functies van de Flex-werkruimte niet beschikbaar in de werkruimte](/help/forms/using/features-flex-workspace-available-html.md)AEM Forms voor een volledige lijst.

## Ontwikkelen met de werkruimte AEM Forms {#developing-with-aem-forms-workspace}

### Architectuur {#architecture}

De werkruimte van AEM Forms is een HTML- en JavaScript™-webtoepassing die wordt gehost op CRX™. Wanneer de werkruimte-URL wordt geopend in een browser, wordt een CRX™-bron benaderd en wordt de toepassing weergegeven als een HTML-pagina in de browser. De JavaScript-bibliotheken en de aangepaste JavaScript-code beheren het interne en externe gedrag van de toepassing, zoals gebruikersinterface, gebruikersinteractie en communicatie met de AEM Forms-server. Voor meer details, zie de [architectuur](/help/forms/using/html-workspace-architecture.md)van de werkruimte van AEM Forms.

### Aanpassing werkruimte AEM Forms {#aem-forms-workspace-customization}

De werkruimte van AEM Forms ondersteunt een groot aantal aanpassingen om de lay-out van de gebruikersinterface, de weergave, functionaliteit en nog veel meer bij te werken. Bij de aanpassingen moet u een of meer van de volgende handelingen bijwerken:

* Weergaven van de gebruikersinterface
* Functionaliteit met semantische aanpassingen
* HTML-componenten opnieuw gebruiken in andere webtoepassingen

In het [aanpassingsartikel](introduction-customizing-html-workspace.md) worden de typen van dergelijke aanpassingen uitgelegd.

### Set up the developer environment {#set-up-the-developer-environment}

Tot de te leveren werkruimten van AEM Forms behoren een CRX-pakket dat op CRX wordt geïmplementeerd, een SDK-archief dat de volledige broncode, JavaScript-bibliotheken van derden bevat en scripts van de werkruimte AEM Forms maakt. Gebruik deze opties om de ontwikkelomgeving in te stellen voor het uitvoeren van de hierboven vermelde aanpassingen. Zie [Werkruimtecode](introduction-customizing-html-workspace.md#building-html-workspace-code)AEM Forms samenstellen voor meer informatie.

U kunt een groot deel van de interface en kernfunctionaliteit aanpassen, zoals lettertypen, kleurenschema, logo, aanmeldingsscherm, foutmeldingen, integratie met toepassingen van derden en hergebruik van componenten in toepassingen van derden. U kunt de inhoud ook verbeteren die op de overzichtspagina van de Taak wordt getoond, beelden voor de acties van de taakroute tonen, en zelfs de laag-vlakke Modellen en Weergaven wijzigen van de Backbone die tot de de werkruimtetoepassing van AEM Forms leiden.

### HTML-rendering van XDP-formulieren {#html-rendering-of-xdp-forms}

Voor een nieuw proces wordt een XDP-formulier standaard weergegeven in PDF-indeling op een bureaublad en in HTML-indeling op een tablet. Het is mogelijk om een XDP-formulier altijd in HTML-indeling te genereren. Voor details, zie [Nieuw teruggeven en de Diensten](/help/forms/using/new-render-submit-service.md)voorleggen.

[Met de functie voor mobiele formulieren](https://helpx.adobe.com/livecycle/help/mobile-forms/introduction.html) , die werkt met [profielen](https://helpx.adobe.com/livecycle/help/mobile-forms/creating-profile.html), wordt HTML-uitvoering van XDP-formulieren ingeschakeld. Standaard gebruikt het bestand &#39;Nieuw HTML-formulier renderen&#39; een `default.html` profiel dat u kunt wijzigen. U kunt ook aangepaste wijzigingen toevoegen die plaatsvinden voordat een XDP-formulier in HTML-indeling wordt weergegeven.

## App voor werkruimte AEM Forms {#aem-forms-workspace-app}

Om aan uw bedrijfsprocessen op een mobiel apparaat te werken, kunt u de AEM Forms werkruimte gebruiken app van AEM Forms aanbiedt. Zie het app-overzicht [van de werkruimte](https://helpx.adobe.com/livecycle/help/mobile-workspace/mobile-workspace-overview.html)AEM Forms voor meer informatie.
