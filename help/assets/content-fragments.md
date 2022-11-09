---
title: Werken met contentfragmenten
seo-title: Working with Content Fragments
description: Leer hoe u met Inhoudsfragmenten pagina-onafhankelijke inhoud kunt ontwerpen, maken, beheren en gebruiken.
seo-description: Learn how Content Fragments allow you to design, create, curate and use page-independent content.
uuid: aa5acda2-4c20-4fe7-929d-6c065b252cf2
contentOwner: AEM Docs
topic-tags: content-fragments
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
content-type: reference
discoiquuid: 22ae0d3a-083f-40e4-bf4a-7a755ae9e312
exl-id: e2804707-7b75-4fae-937e-9e258481878f
feature: Content Fragments
role: User
source-git-commit: 3358f6b8b492ff2b5858867a1f48a57b06944b1e
workflow-type: tm+mt
source-wordcount: '1984'
ht-degree: 3%

---

# Werken met contentfragmenten {#working-with-content-fragments}

>[!CAUTION]
>
>Voor bepaalde functies voor inhoudsfragmenten moet de toepassing van [AEM 6.4 Service Pack 2 (6.4.2.0) of later](/help/release-notes/sp-release-notes.md).

Met Adobe Experience Manager (AEM) Content Fragments kunt u ontwerpen, maken, curven en [pagina-onafhankelijke inhoud publiceren](/help/sites-authoring/content-fragments.md). Hiermee kunt u inhoud voorbereiden die klaar is voor gebruik op meerdere locaties/via meerdere kanalen.

Inhoudsfragmenten kunnen ook worden geleverd in JSON-indeling, waarbij gebruik wordt gemaakt van de JSON-exportmogelijkheden (Sling Model) van AEM kerncomponenten. Deze leveringsvorm:

* biedt u de mogelijkheid om de component te gebruiken om te beheren welke elementen van een fragment moeten worden geleverd
* staat bulklevering toe, door veelvoudige inhoudfragment kerncomponenten op de pagina toe te voegen die voor levering API wordt gebruikt

Deze en de volgende pagina&#39;s bevatten de taken voor het maken, configureren en onderhouden van uw inhoudsfragmenten:

* [Inhoudsfragmenten beheren](content-fragments-managing.md) - maak uw inhoudsfragmenten; vervolgens bewerken, publiceren en verwijzen

* [Modellen van inhoudsfragmenten](content-fragments-models.md) - het inschakelen, maken en definiëren van uw modellen

* [Variaties - Fragmentinhoud ontwerpen](content-fragments-variations.md) - de fragmentinhoud ontwerpen en variaties van de Master inhoud maken

* [Markering](content-fragments-markdown.md) - markeringssyntaxis gebruiken voor uw fragment

* [Gekoppelde inhoud gebruiken](content-fragments-assoc-content.md) - gekoppelde inhoud toevoegen

* [Metagegevens - Fragmenteigenschappen](content-fragments-metadata.md) - de fragmenteigenschappen weergeven en bewerken

>[!NOTE]
>
>Deze pagina&#39;s moeten worden gelezen in combinatie met [Pagina&#39;s ontwerpen met inhoudsfragmenten](/help/sites-authoring/content-fragments.md).

Het aantal communicatiekanalen neemt jaarlijks toe. Doorgaans verwijzen kanalen naar het leveringsmechanisme, als:

* fysiek kanaal; bijvoorbeeld desktop, mobiel.
* Vorm van levering in een fysiek kanaal; Bijvoorbeeld de pagina met productdetails, de pagina met productcategorieën voor desktops of mobiele websites, de pagina met mobiele apps voor mobiele apparaten.

U (waarschijnlijk) wilt echter niet exact dezelfde inhoud gebruiken voor alle kanalen. U moet de inhoud optimaliseren op basis van het specifieke kanaal.

Met inhoudelementen kunt u:

* Overweeg hoe u doelpubliek efficiënt langs verschillende kanalen kunt bereiken.
* Kanaalneutrale redactionele inhoud maken en beheren.
* Stel inhoudsgroepen samen voor een reeks kanalen.
* Ontwerpinhoudvariaties voor specifieke kanalen.
* Voeg afbeeldingen aan de tekst toe door elementen (gemengde-mediafragmenten) in te voegen.

Deze inhoudsfragmenten kunnen vervolgens worden samengevoegd om via verschillende kanalen ervaringen op te doen.

## Inhoudsfragmenten en inhoudsservices {#content-fragments-and-content-services}

AEM Content Services zijn ontworpen om de beschrijving en levering van inhoud in of vanuit AEM te veralgemenen, waarbij de aandacht niet op webpagina&#39;s wordt gevestigd.

Zij verstrekken de levering van inhoud aan kanalen die niet traditionele AEM Web-pagina&#39;s zijn, gebruikend gestandaardiseerde methodes die door om het even welke cliënt kunnen worden verbruikt. Deze kanalen kunnen zijn:

* Toepassingen voor één pagina
* Systeemeigen mobiele toepassingen
* andere kanalen en aanraakpunten buiten AEM

De levering wordt uitgevoerd in JSON-indeling.

AEM Inhoudsfragmenten kunnen worden gebruikt om gestructureerde inhoud te beschrijven en te beheren. Gestructureerde inhoud wordt gedefinieerd in modellen die verschillende inhoudstypen kunnen bevatten; waaronder tekst, numerieke gegevens, booleaanse gegevens, datum en tijd en meer.

Samen met de JSON-exportmogelijkheden van AEM kerncomponenten kan deze gestructureerde inhoud vervolgens worden gebruikt om AEM inhoud aan andere kanalen dan AEM pagina&#39;s te leveren.

>[!NOTE]
>
>**Inhoudsfragmenten** en **[Ervaar fragmenten](/help/sites-authoring/experience-fragments.md)** zijn verschillende functies in AEM:
>
>* **Inhoudsfragmenten** zijn redactionele inhoud, voornamelijk tekst en verwante afbeeldingen. Het zijn pure inhoud, zonder ontwerp en lay-out.
>* **Ervaar fragmenten** volledig zijn ingedeeld; een fragment van een webpagina.
>
>De Fragmenten van de ervaring kunnen inhoud in de vorm van Inhoudsfragmenten bevatten, maar niet andersom.
>
>Zie ook voor meer informatie [Inhoudsfragmenten en ervaringsfragmenten in AEM](https://helpx.adobe.com/experience-manager/kt/platform-repository/using/content-fragments-experience-fragments-article-understand.html).

>[!CAUTION]
>
>Inhoudsfragmenten zijn niet beschikbaar in de klassieke UI.
>
>De component van het Fragment van de Inhoud kan in klassieke UI hulpje worden gezien, maar de verdere functionaliteit is niet beschikbaar.

>[!NOTE]
>
>AEM ondersteunt ook het vertalen van fragmentinhoud. Zie [Vertaalprojecten maken voor inhoudsfragmenten](creating-translation-projects-for-content-fragments.md) voor nadere informatie.

## Typen inhoudsfragmenten {#types-of-content-fragment}

Inhoudsfragmenten kunnen:

* Eenvoudige fragmenten

   * Deze hebben geen vooraf gedefinieerde structuur. Ze bevatten alleen tekst en afbeeldingen.
   * Deze zijn gebaseerd op de sjabloon Eenvoudig fragment.

* Fragmenten die gestructureerde inhoud bevatten

   * Deze zijn gebaseerd op een [Inhoudsfragmentmodel](content-fragments-models.md), waarin een vooraf gedefinieerde structuur voor het resulterende fragment wordt gedefinieerd.
   * Deze kunnen ook worden gebruikt om Content Services te realiseren met behulp van JSON Exporter.

## Inhoudstype {#content-type}

Inhoudsfragmenten zijn:

* Opgeslagen als **Activa**:

   * Inhoudsfragmenten (en hun variaties) kunnen worden gemaakt en onderhouden op basis van de **Activa** console.
   * Gemaakt en bewerkt in de Inhoudsfragmenteditor.

* Gebruikt in de [pagina-editor via de component Inhoudsfragment](/help/sites-authoring/content-fragments.md) (verwijzende component):

   * De **Inhoudsfragment** is beschikbaar voor auteurs van pagina&#39;s. Hiermee kunnen ze naar het vereiste inhoudsfragment verwijzen en dit leveren in HTML- of JSON-indeling.

Inhoudsfragmenten zijn een inhoudsstructuur die:

* Zijn zonder lay-out of ontwerp (wat tekst het formatteren is mogelijk op Rich Text wijze).
* Bevat een of meer, [samenstellende delen](#constituent-parts-of-a-content-fragment).
* Kan [afbeeldingen bevatten of ermee verbonden zijn](#fragments-with-visual-assets).
* Kan gebruiken [tussenliggende inhoud](#in-between-content-when-page-authoring-with-content-fragments) wanneer verwezen op een pagina.

* zijn onafhankelijk van het leveringsmechanisme (d.w.z. pagina, kanaal).

### Fragmenten met visuele elementen {#fragments-with-visual-assets}

Om auteurs meer controle over hun inhoud te geven, kunnen afbeeldingen worden toegevoegd aan en/of geïntegreerd met een inhoudsfragment.

Elementen kunnen op verschillende manieren met een inhoudsfragment worden gebruikt. elk met zijn eigen voordeel:

* **Element invoegen** in een fragment (gemengde-mediafragmenten)

   * Vormen een integrerend deel van het fragment (zie [Delen van een inhoudsfragment maken](#constituent-parts-of-a-content-fragment)).
   * De positie van het element definiëren.
   * Zie [Elementen invoegen in uw fragment](content-fragments-variations.md#inserting-assets-into-your-fragment) in de fragmenteditor voor meer informatie.

   >[!NOTE]
   >
   >Visuele elementen die in het inhoudsfragment zelf zijn ingevoegd, worden aan de voorafgaande alinea gekoppeld. Wanneer het fragment aan een pagina wordt toegevoegd, worden deze elementen ten opzichte van die alinea verplaatst wanneer tussenliggende inhoud wordt toegevoegd.

* **Gekoppelde inhoud**

   * zijn verbonden met een fragment; maar geen vast deel van het fragment (zie [Delen van een inhoudsfragment maken](#constituent-parts-of-a-content-fragment)).
   * Biedt enige flexibiliteit voor positionering.
   * U kunt het fragment gemakkelijk gebruiken (als tussenliggende inhoud) op een pagina.
   * Zie [Gekoppelde inhoud](content-fragments-assoc-content.md) voor meer informatie .

* Assets die beschikbaar zijn in de **assetbrowser** van de pagina-editor

   * Volledige flexibiliteit toestaan voor de selectie van een element.
   * Biedt enige flexibiliteit voor positionering.
   * Bevat niet het concept dat voor een specifiek fragment wordt goedgekeurd.
   * Zie [Browser voor middelen](/help/sites-authoring/author-environment-tools.md#assets-browser) voor meer informatie .

### Delen van een inhoudsfragment maken {#constituent-parts-of-a-content-fragment}

De elementen van het inhoudsfragment bestaan uit de volgende onderdelen (direct of indirect):

* **Fragmentelementen**

   * Elementen correleren met de gegevensvelden die inhoud bevatten.
   * Voor fragmenten met gestructureerde inhoud gebruikt u een inhoudsmodel om het inhoudsfragment te maken. De elementen (velden) die in het model zijn opgegeven, definiëren de structuur van het fragment. Deze elementen (velden) kunnen van verschillende gegevenstypen zijn.
   * Voor eenvoudige fragmenten:

      * De inhoud bevindt zich in een (of meer) tekstveld(en) met meerdere regels of in een of meer elementen.
      * De elementen worden gedefinieerd in de fragmentsjabloon (kunnen niet worden gedefinieerd tijdens het ontwerpen van het fragment, zie [Sjablonen voor inhoudsfragmenten](/help/sites-developing/content-fragment-templates.md)).

* **Fragmentalinea&#39;s**

   * Tekstblokken, dat wil zeggen:

      * gescheiden door verticale spaties (harde return)
      * in tekstelementen met meerdere regels; in eenvoudige of gestructureerde fragmenten
   * In de modi [Tekst met opmaak](content-fragments-variations.md#rich-text) en [Markdown](content-fragments-variations.md#markdown) kan een alinea worden opgemaakt als een koptekst. In dat geval horen die alinea en de volgende alinea bij elkaar als één eenheid.
   * Inhoudsbeheer tijdens het ontwerpen van pagina&#39;s inschakelen.


* **Elementen die in een fragment zijn ingevoegd (gemengde-mediafragmenten)**

   * Elementen (afbeeldingen) die in het feitelijke fragment zijn ingevoegd en worden gebruikt als de interne inhoud van een fragment.
   * zijn ingesloten in het alineasysteem van het fragment.
   * Kan worden opgemaakt wanneer de [fragment wordt gebruikt of er wordt naar verwezen op een pagina](/help/sites-authoring/content-fragments.md).
   * Kan alleen met de fragmenteditor worden toegevoegd aan, verwijderd uit of verplaatst binnen een fragment. Deze handelingen kunnen niet worden uitgevoerd in de paginaeditor.
   * Kan alleen worden toegevoegd aan, verwijderd uit of verplaatst binnen een fragment met [Opmaak RTF in de fragmenteditor](content-fragments-variations.md#inserting-assets-into-your-fragment).
   * Kan alleen worden toegevoegd aan tekstelementen met meerdere regels (elk fragmenttype).
   * Aan de voorgaande tekst (alinea) worden toegevoegd.

   >[!CAUTION]
   >
   >Kan (per ongeluk) uit een fragment worden verwijderd door over te schakelen op de indeling Onbewerkte tekst.

   >[!NOTE]
   >
   >Elementen kunnen ook worden toegevoegd als [extra inhoud (tussen)](/help/sites-authoring/content-fragments.md#using-associated-content) bij het gebruik van een fragment op een pagina; het gebruiken van of Bijbehorende Inhoud of activa van browser van Activa.

* **Gekoppelde inhoud**

   * Dit is inhoud die zich buiten een fragment bevindt, maar die van redactionele betekenis is. Meestal worden afbeeldingen, video&#39;s of andere fragmenten weergegeven.
   * De afzonderlijke elementen in de verzameling zijn beschikbaar voor gebruik met het fragment in de pagina-editor wanneer het aan een pagina wordt toegevoegd. Dit betekent dat ze optioneel zijn, afhankelijk van de vereisten van het specifieke kanaal.
   * De activa zijn [gekoppeld aan fragmenten via verzamelingen](content-fragments-assoc-content.md); Met gekoppelde verzamelingen kan de auteur beslissen welke elementen worden gebruikt wanneer deze de pagina ontwerpt.

      * Verzamelingen kunnen tijdens het ontwerpen van fragmenten worden gekoppeld aan fragmenten via sjablonen, als standaardinhoud of door auteurs.
      * [Activa (DAM) Inzamelingen](managing-collections-touch-ui.md) vormen de basis voor de bijbehorende inhoud van fragmenten.
   * Desgewenst kunt u het fragment zelf ook aan een verzameling toevoegen om het bijhouden van het fragment te vergemakkelijken.


* **Fragmentmetagegevens**

   * Gebruik de [Metagegevensschema&#39;s voor elementen](metadata.md).
   * Tags kunnen worden gemaakt wanneer u:

      * Het fragment maken en ontwerpen
      * of hoger:

         * Door het fragment weer te geven/te bewerken **Eigenschappen** vanaf de console
         * Door de **Metagegevens** wanneer in de fragmenteditor

   >[!CAUTION]
   >
   >Metagegevensverwerkingsprofielen zijn niet van toepassing op inhoudsfragmenten.

* **Master**

   * Een integraal onderdeel van het fragment

      * Elk inhoudsfragment heeft één instantie van Master.
      * Master kan niet worden verwijderd.
   * Master is toegankelijk in de fragmenteditor onder **[Variaties](content-fragments-variations.md)**.
   * Master is geen variatie als zodanig, maar is de basis van alle variaties.


* **Variaties**

   * Uitvoeringen van fragmenttekst die specifiek zijn voor redactionele doeleinden; kan verband houden met het kanaal, maar is niet verplicht, en kan ook voor ad-hoclokale aanpassingen worden gebruikt.
   * Wordt gemaakt als kopieën van **Master**, maar kan vervolgens naar behoefte worden bewerkt; er is gewoonlijk inhoudsoverlap tussen de variaties zelf.
   * Kan worden gedefinieerd tijdens het ontwerpen van fragmenten of vooraf worden gedefinieerd in fragmentsjablonen.
   * Opgeslagen in het fragment, om spreiding van inhoudskopieën te voorkomen.
   * Variaties kunnen [gesynchroniseerd](content-fragments-variations.md#synchronizing-with-master) master als de Master inhoud is bijgewerkt.
   * Kan [Samengevat](content-fragments-variations.md#summarizing-text) om de tekst snel af te kappen tot een vooraf gedefinieerde lengte.
   * Beschikbaar onder [Variaties](content-fragments-variations.md) tabblad van de fragmenteditor.

### Tussen inhoud wanneer pagina&#39;s worden gemaakt met inhoudsfragmenten {#in-between-content-when-page-authoring-with-content-fragments}

Tussen inhoud:

* Is beschikbaar voor gebruik in [Pagina-editor wanneer u werkt met inhoudsfragmenten](/help/sites-authoring/content-fragments.md).
* Is [extra inhoud die is toegevoegd binnen de stroom van een fragment](/help/sites-authoring/content-fragments.md#adding-in-between-content) als er op een pagina naar is verwezen of er gebruik van is gemaakt.
* Tussen-inhoud kan aan elk fragment worden toegevoegd, waarbij slechts één element zichtbaar is.
* De bijbehorende inhoud kan worden gebruikt, evenals activa en/of componenten van aangewezen browser.

>[!CAUTION]
>
>De tussenliggende inhoud is pagina-inhoud. Deze wordt niet opgeslagen in het inhoudsfragment.

### Vereist door fragmenten {#required-by-fragments}

Voor het maken, bewerken en gebruiken van inhoudsfragmenten hebt u ook het volgende nodig:

* **Inhoudsmodel**

   * zijn [ingeschakeld en vervolgens gemaakt met Gereedschappen](content-fragments-models.md).
   * Vereist voor [een gestructureerd fragment maken](content-fragments-managing.md#creating-content-fragments).
   * Definieert de structuur van een fragment (titel, inhoudselementen, tagdefinities).
   * Definities van inhoudsmodellen vereisen een titel en één gegevenselement. alles is optioneel . Het model definieert een minimaal bereik van het fragment en de standaardinhoud, indien van toepassing. Auteurs kunnen de gedefinieerde structuur niet wijzigen tijdens het ontwerpen van fragmentinhoud.

* **Fragmentsjabloon**

   * Vereist voor [een eenvoudig fragment maken](content-fragments-managing.md#creating-content-fragments).
   * Meestal [ontwikkeld tijdens de uitvoering van het project](/help/sites-developing/content-fragment-templates.md); kan niet worden gemaakt tijdens het ontwerpen.
   * Definieert de basiseigenschappen van een eenvoudig fragment (titel, aantal tekstelementen, tagdefinities).
   * Sjabloondefinities vereisen een titel en één tekstelement. alles is optioneel . De sjabloon definieert een minimaal bereik van het fragment en de standaardinhoud, indien van toepassing. Auteurs kunnen later een fragment uitbreiden dat verder gaat dan in de sjabloon is gedefinieerd.

* **Component Inhoudsfragment**

   * Instrumentaal voor het leveren van het fragment in HTML- en/of JSON-indeling.
   * Vereist voor [verwijzen naar het fragment op een pagina](/help/sites-authoring/content-fragments.md).
   * Verantwoordelijk voor de lay-out en levering van een fragment; d.w.z. kanalen.
   * Fragmenten hebben een of meer specifieke componenten nodig om de lay-out te definiëren en om enkele of alle elementen/variaties en bijbehorende inhoud te leveren.
   * Als u een fragment naar een pagina sleept tijdens het ontwerpen, wordt de vereiste component automatisch gekoppeld.

## Voorbeeldgebruik {#example-usage}

Een fragment met de elementen en variaties kan worden gebruikt om coherente inhoud voor meerdere kanalen te maken. Bij het ontwerpen van het fragment moet u rekening houden met de plaats waar het fragment wordt gebruikt.

### We.Handelsvoorbeeld {#we-retail-sample}

Een voorbeeldfragment is zichtbaar bij:

[http://localhost:4502/assets.html/content/dam/we-retail/en/experiences/arctic-surfing-in-lofoten](http://localhost:4502/assets.html/content/dam/we-retail/en/experiences/arctic-surfing-in-lofoten)
