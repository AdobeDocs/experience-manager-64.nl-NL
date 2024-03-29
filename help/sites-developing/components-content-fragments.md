---
title: Componenten voor inhoudsfragmenten
seo-title: Components for Content Fragments
description: AEM inhoudsfragmenten worden gemaakt en beheerd als pagina-onafhankelijke elementen
seo-description: AEM content fragments are created and managed as page-independent assets
uuid: 289ed9cb-9531-43a9-b0d8-a3499e2e9ee5
contentOwner: AEM Docs
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: components
content-type: reference
discoiquuid: 76b63c7c-f7ea-46be-8d10-6c1a30af2e2b
pagetitle: Components for Content Fragments
exl-id: 516c1561-5c13-4301-8009-9b021087cec7
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '968'
ht-degree: 1%

---

# Componenten voor inhoudsfragmenten{#components-for-content-fragments}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

>[!CAUTION]
>
>Voor bepaalde functies voor inhoudsfragmenten moet de toepassing van [AEM 6.4 Service Pack 2 (6.4.2.0)](/help/release-notes/sp-release-notes.md).

## Componenten voor het ontwerpen van fragmenten {#components-for-fragment-authoring}

>[!CAUTION]
>
>Het wordt afgeraden de werkelijke componenten die in de fragmenteditor worden gebruikt, uit te breiden of te wijzigen, omdat deze nog steeds kunnen worden gewijzigd.

Zie de [Content Fragment Management API - Client-kant](/help/sites-developing/customizing-content-fragments.md#the-content-fragment-management-api-client-side).

## Componenten voor paginaontwerp {#components-for-page-authoring}

>[!CAUTION]
>
>De [Component Content Fragment Core](https://helpx.adobe.com/experience-manager/core-components/using/content-fragment-component.html) wordt nu aanbevolen. Zie [Basiscomponenten ontwikkelen](https://helpx.adobe.com/experience-manager/core-components/using/developing.html) voor meer informatie .
>
>In deze sectie wordt de oorspronkelijke component beschreven die is geleverd voor gebruik met inhoudsfragmenten (**Inhoudsfragment** in de **Algemeen** groep).

Inhoudsfragmenten van Adobe Experience Manager (AEM) worden [gemaakt en beheerd als paginaonafhankelijke assets](/help/assets/content-fragments.md). U kunt hiermee kanaalneutrale inhoud maken, samen met (mogelijk kanaalspecifieke) variaties. [Vervolgens kunt u deze fragmenten en de variaties ervan gebruiken bij het ontwerpen van de inhoudspagina&#39;s](/help/sites-authoring/content-fragments.md). U kunt ook een bestaand inhoudsfragmentelement gebruiken door [het slepen van middelenbrowser naar pagina](/help/sites-authoring/content-fragments.md#adding-a-content-fragment-to-your-page) (zoals voor andere op activa gebaseerde componenten, zoals het stichtingscomponentenbeeld). De inhoud van het inhoudsfragmentcomponent uit de doos toont slechts één [element](/help/assets/content-fragments.md#constituent-parts-of-a-content-fragment) van het inhoudsfragment waarnaar wordt verwezen. Met behulp van het componentdialoogvenster kunt u het dialoogvenster [element, variatie en bereik van fragmentalinea&#39;s](/help/assets/content-fragments.md#constituent-parts-of-a-content-fragment) die u op de pagina wilt weergeven.

>[!NOTE]
>
>Deze component Content Fragment is in AEM 6.2 geïntroduceerd als een verbeterde versie van de component Article, die is vervangen.

>[!NOTE]
>
>Inhoudsfragmenten worden niet ondersteund in de klassieke UI.

### Definitie {#definition}

De **Inhoudsfragment** wordt gebruikt om een verwijzing naar een inhoudsfragmentelement (effectief verbeterde tekstelementen) te bevatten. Het middeltype voor het inhoudsfragment is:

* `dam/cfm/components/contentfragment/contentfragment`

De verwijzing wordt gedefinieerd in de eigenschap:

* `fileReference`

Alleen de editor van de interface met aanraakbediening biedt volledige ondersteuning voor componenten van inhoudsfragmenten, waaronder de clientbibliotheek:

* `cq.authoring.editor.plugin.cfm`

Deze bibliotheek voegt eigenschappen, specifiek voor inhoudsfragmenten, aan de redacteur toe. Er is bijvoorbeeld ondersteuning beschikbaar voor het toevoegen en configureren van inhoudsfragmenten op de pagina, het zoeken naar elementen van inhoudsfragmenten in de elementenbrowser en de bijbehorende inhoud in het zijpaneel.

### Tussen inhoud {#in-between-content}

De **Inhoudskader** t component staat u toe om extra componenten tussen de verschillende getoonde paragrafen te laten vallen [element](/help/assets/content-fragments.md#constituent-parts-of-a-content-fragment). In feite bestaat het weergegeven element uit verschillende alinea&#39;s (elke alinea wordt gemarkeerd door een regelterugloop). Tussen deze alinea&#39;s kunt u inhoud invoegen met behulp van andere componenten.

Vanuit technisch gezichtspunt, leeft elke paragraaf van het getoonde element in zijn eigen parsys, en elke component die u tussen de paragrafen toevoegt zal (onder de kap) in parsys worden opgenomen.

Met andere woorden, als de instantie van de inhoudfragment component uit drie paragrafen wordt samengesteld, dan zal de component drie verschillende parsys in de bewaarplaats hebben. Alle inwendige inhoud die aan het inhoudsfragment wordt toegevoegd zal eigenlijk binnen deze parsys worden gevestigd.

In de gegevensopslagruimte wordt de tussenliggende inhoud opgeslagen ten opzichte van de positie binnen de algemene alinearichting, d.w.z. de inhoud is niet gekoppeld aan de werkelijke alinea-inhoud.

Om dit te illustreren, moeten we bedenken dat we:

* Een instantie van een inhoudsfragment dat bestaat uit drie alinea&#39;s
* En dat bepaalde inhoud al is ingevoegd na de tweede alinea

   * Dit betekent dat de inhoud in tweede parsys zal worden opgeslagen.

Als de alineabstructuur van dit exemplaar verandert (door de variatie, het element of het bereik van de weergegeven alinea&#39;s te wijzigen), kan dit van invloed zijn op de tussenliggende inhoud die wordt weergegeven wanneer de inhoud van het inhoudsfragment:

* Wordt bewerkt en een andere alinea wordt toegevoegd vóór de tweede alinea:

   * De inhoud tussen wordt weergegeven na de nieuwe alinea (de tweede alinea bevat nu de nieuwe alinea).

* Wordt bewerkt en de tweede alinea wordt verwijderd:

   * De inhoud tussen de pagina&#39;s wordt weergegeven na de alinea die eerder de derde alinea was (de tweede alinea bevat nu de vorige derde alinea).

* Is zo gevormd dat slechts de eerste paragraaf wordt getoond:

   * De inhoud in-tussen zal niet worden getoond (tweede parsys wordt niet meer teruggegeven toe te schrijven aan de nieuwe configuratie).

### De component Inhoudsfragment aanpassen {#customizing-the-content-fragment-component}

Als u de uit-van-de-doos component van het inhoudsfragment als blauwdruk voor uitbreiding wilt gebruiken, zou u het volgende contract moeten respecteren:

* U kunt het HTML-renderscript en de bijbehorende POJO opnieuw gebruiken om te zien hoe de functie voor de tussenliggende inhoud is geïmplementeerd.
* Het knooppunt voor inhoudsfragmenten opnieuw gebruiken: `cq:editConfig`

   * De `afterinsert`/ `afteredit`/ `afterdelete` listeners worden gebruikt om JS-gebeurtenissen te activeren. Deze gebeurtenissen worden verwerkt in het dialoogvenster `cq.authoring.editor.plugin.cfm` clientbibliotheek om de bijbehorende inhoud in het zijpaneel weer te geven.
   * De `cq:dropTargets` zijn geconfigureerd voor het slepen van inhoud van fragmentelementen.
   * `cq:inplaceEditing` is geconfigureerd ter ondersteuning van het ontwerpen van een inhoudsfragment in de pagina-editor. De fragmentbewerker ter plekke wordt gedefinieerd in het dialoogvenster `cq.authoring.editor.plugin.cfm` clientbibliotheek en maakt een snelle koppeling mogelijk om de huidige [element/variatie](/help/assets/content-fragments.md#constituent-parts-of-a-content-fragment) in de [fragmenteditor](/help/assets/content-fragments-variations.md).

### Element herschrijven vóór renderen {#asset-rewriting-before-rendering}

Bij Inhoudsfragmentbeheer wordt een intern renderingsproces gebruikt om de uiteindelijke HTML-uitvoer voor een pagina te genereren. Dit wordt intern gebruikt door de component van het Fragment van de Inhoud, maar ook door het achtergrondproces dat referenced fragmenten op het van verwijzingen voorzien pagina&#39;s bijwerkt.

Intern wordt de Sling Rewriter gebruikt voor die rendering. De respectievelijke configuratie is te vinden op `/libs/dam/config/rewriter/cfm` en kan zo nodig worden aangepast. Zie de [Apache Sling Rewriter](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html) voor meer informatie .

De uit-van-de-doos configuratie gebruikt de volgende transformatoren:

* `transformer-cfm-payloadfilter` - voor het ophalen van de `body` deel ( `<body>...</body>`) van alleen de HTML van het fragment

* `transformer-cfm-parfilter` - filtert ongewenste alinea&#39;s uit als er een alineabereik is opgegeven (zoals u kunt doen met de component Content Fragment)
* `transformer-cfm-assetprocessor` - intern wordt gebruikt voor het ophalen van een lijst met elementen die zijn ingesloten in het fragment

Het renderingsproces wordt via ` [com.adobe.cq.dam.cfm.content.FragmentRenderService](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/dam/cfm/ContentFragment.html)` en kan indien nodig worden gebruikt (bijvoorbeeld) door aangepaste componenten.
