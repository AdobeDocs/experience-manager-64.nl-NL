---
title: Overzicht van componenten
seo-title: Components
description: Componenten zijn modulaire eenheden die specifieke functionaliteit realiseren om uw inhoud op uw website weer te geven
seo-description: Components are modular units which realize specific functionality to present your content on your website
uuid: fb39aeb8-8f43-4091-8083-ebfab89e6e63
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: components
content-type: reference
discoiquuid: 45efff93-2fe5-4313-83a0-0e23a540da93
exl-id: 3444d7df-fc43-4383-87b0-0f00fef116bc
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '616'
ht-degree: 0%

---

# Overzicht van componenten{#components-overview}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Deze pagina biedt een overzicht van Adobe Experience Manager (AEM)-componenten, zoals [gebruikt voor het ontwerpen van pagina&#39;s](/help/sites-authoring/default-components-foundation.md).

## Wat zijn componenten? {#what-exactly-is-a-component}

* Modulaire eenheden die specifieke functionaliteit realiseren om uw inhoud op uw website te presenteren.
* Herbruikbaar.
* Ontwikkeld als zelfstandige eenheden in één map van de opslagplaats.
* Geen verborgen configuratiebestanden hebben.
* Kan andere componenten bevatten.
* Kan overal binnen om het even welk AEM systeem lopen. Ze kunnen ook beperkt zijn tot bepaalde onderdelen.
* Een gestandaardiseerde gebruikersinterface hebben.
* Heb bewerkingsgedrag dat kan worden gevormd.
* Dialoogvensters gebruiken die zijn gebouwd met subelementen op basis van graniet UI-componenten
* worden ontwikkeld met [HTL](https://helpx.adobe.com/experience-manager/htl/user-guide.html) (aanbevolen) of JSP.
* Kan worden ontwikkeld om aangepaste componenten te maken die de standaardfunctionaliteit uitbreiden.

Omdat componenten modulair zijn, kunt u:

* Ontwikkel een nieuwe component op uw lokale instantie.
* Implementeer deze in de testomgeving.
* Implementeer deze in uw live ontwerpomgeving, waar auteurs en/of beheerders inhoud kunnen toevoegen en configureren.
* Implementeer deze in uw live publicatieomgeving(en), waar ze worden gebruikt om inhoud te renderen voor bezoekers van uw website. Bepaalde componenten, bijvoorbeeld voor Communities, accepteren ook invoer van uw gebruikers.

Elke AEM component:

* Is een middeltype.
* Is een inzameling van manuscripten die een specifieke functie volledig realiseren.
* Kan werken in *isolatie*, ofwel in AEM of een portaal.

## Buiten-de-box Componenten binnen AEM {#out-of-the-box-components-within-aem}

AEM wordt geleverd met verschillende [out-of-the-box componenten](/help/sites-authoring/default-components.md) die uitgebreide functionaliteit bieden, waaronder:

* Alineasysteem ( `parsys`)
* Pagina ( `responsivegrid` - alleen interface met aanraakbediening)
* Tekst
* Afbeelding, met bijbehorende tekst
* Werkbalk

De geleverde onderdelen en het gebruik ervan binnen de [voorbeeld weergeven.Handelswebsites](/help/sites-developing/we-retail.md) Hieronder ziet u hoe u componenten kunt implementeren en gebruiken. De componenten worden voorzien van al broncode en kunnen als zijn of als uitgangspunt voor gewijzigde of uitgebreide componenten worden gebruikt.

### Basiscomponenten en basiscomponenten {#core-components-and-foundation-components}

Er zijn twee reeksen van Adobe-Geleverde AEM beschikbare componenten:

* [Kernonderdelen](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html)
* [Elementaire componenten](/help/sites-authoring/default-components-foundation.md)

**Kernonderdelen** werden geïntroduceerd met AEM 6.3 en bieden flexibele en functies-rijke ontwerpfunctionaliteit. De [We.Retail-referentiesite](/help/sites-developing/we-retail.md) illustreert hoe de kerncomponenten kunnen worden gebruikt en de huidige beste praktijken van componentenontwikkeling vertegenwoordigen.

**Elementaire componenten** zijn beschikbaar met AEM voor vele versies en zijn beschikbaar uit-van-de-doos in een standaard AEM installatie. Hoewel nog steeds ondersteund, zijn de meeste vervangen, worden ze niet meer uitgebreid en zijn ze gebaseerd op oudere technologieën.

>[!NOTE]
>
>[Kernonderdelen](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html) de huidige beste praktijken voor componentenontwerp en ontwikkeling vertegenwoordigen en als verwijzingsimplementaties dienen.
>
>[AEM moderniseringsinstrumenten](modernization-tools.md) kan helpen bij de migratie naar Core Components.

### Beschikbare componenten weergeven {#viewing-available-components}

Voor een overzicht van alle beschikbare componenten in uw AEM instantie, gebruik [Componentenconsole](/help/sites-authoring/default-components-console.md).

U kunt ook CRXDE Lite gebruiken om een lijst met alle componenten in de opslagplaats op te halen.

1. In **[!UICONTROL CRXDE Lite]**, selecteert u **[!UICONTROL Tools]** vanaf de werkbalk, dan **[!UICONTROL Query]**, die de **[!UICONTROL Query]** tab.

1. In de **[!UICONTROL Query]** tab, selecteert u `XPath` als **[!UICONTROL Type]**.

1. In de **[!UICONTROL Query]** invoerveld, voer de volgende tekenreeks in:

   `//element(*, cq:Component)`

1. Klikken **[!UICONTROL Execute]** en de componenten worden vermeld.

## Aanvullende bronnen {#further-reading}

De volgende pagina&#39;s verstrekken meer gedetailleerde informatie over het ontwikkelen van deze-en ander-componenten:

* [Componenten AEM - De basisbeginselen](/help/sites-developing/components-basics.md)
* [AEM ontwikkelen](/help/sites-developing/developing-components.md)
* [Ontwikkelen AEM componenten - Codevoorbeelden](/help/sites-developing/developing-components-samples.md)
* [Meerdere lokale editors configureren](/help/sites-developing/multiple-inplace-editors.md)
* [Ontwerpmodus](/help/sites-developing/developer-mode.md)
* [Uw gebruikersinterface testen](/help/sites-developing/hobbes.md)
* [Componenten voor inhoudsfragmenten](/help/sites-developing/components-content-fragments.md)
* [Pagina-informatie ophalen in JSON-indeling](/help/sites-developing/pageinfo.md)
* [Internationaliserende componenten](/help/sites-developing/i18n.md)
* [Kernonderdelen](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html)
* [Voorwaarden verbergen gebruiken](/help/sites-developing/hide-conditions.md)
* Klassieke interface

   * [AEM (klassieke gebruikersinterface)](/help/sites-developing/developing-components-classic.md)
   * [Widgets gebruiken en uitbreiden (klassieke UI)](/help/sites-developing/widgets.md)
   * [xtypes gebruiken (klassieke UI)](/help/sites-developing/xtypes.md)
   * [Forms ontwikkelen (klassieke gebruikersinterface)](/help/sites-developing/developing-forms.md)
