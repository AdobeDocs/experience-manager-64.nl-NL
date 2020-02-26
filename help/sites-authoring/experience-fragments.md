---
title: Ervaringsfragmenten
seo-title: Ervaringsfragmenten
description: 'null'
seo-description: 'null'
uuid: be1aceef-eb6e-47e5-a920-be5cc6de6191
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: page-authoring
content-type: reference
discoiquuid: 1fe58af0-3005-46fc-8717-5d32557947ed
translation-type: tm+mt
source-git-commit: 6f6952686446359485f180050219a12db9d3969a

---


# Ervaringsfragmenten{#experience-fragments}

Een ervaringsfragment is een groep van een of meer componenten, inclusief inhoud en lay-out, waarnaar op pagina&#39;s kan worden verwezen. Ze kunnen elke gewenste component bevatten.

Een ervaringsfragment:

* Maakt deel uit van een ervaring (pagina).
* Kan op meerdere pagina&#39;s worden gebruikt.
* Is gebaseerd op een malplaatje (editable slechts) om structuur en componenten te bepalen.
* Bestaat uit een of meer componenten, met layout, in een alineasysteem.
* Kan andere ervaringsfragmenten bevatten.
* Kan worden gecombineerd met andere componenten (waaronder andere Experience Fragments) om een volledige pagina (ervaring) te vormen.
* Kan verschillende variaties hebben, die inhoud en/of componenten kunnen delen.
* Kan worden opgedeeld in bouwstenen die kunnen worden gebruikt voor meerdere variaties van het fragment.

U kunt Experience Fragments gebruiken:

* Als een auteur onderdelen (een fragment van een ervaring) van een pagina opnieuw wil gebruiken, moet hij of zij dat fragment kopiëren en plakken. Het maken en onderhouden van deze kopiëren/plakken-ervaringen kost veel tijd en is vaak het gevolg van gebruikersfouten. De Fragmenten van de ervaring elimineren de behoefte aan exemplaar/deeg.
* Om het hoofdloze gebruik-geval CMS te steunen. Auteurs willen AEM alleen gebruiken voor ontwerpen, maar niet voor levering aan de klant. Een systeem/aanraakpunt van derden zou deze ervaring gebruiken en vervolgens leveren aan de eindgebruiker.

>[!NOTE]
>
>Schrijf toegang voor ervaringsfragmenten vereist dat de gebruikersaccount in de groep wordt geregistreerd:
>
>`experience-fragments-editors`
>
>Neem contact op met de systeembeheerder als er problemen optreden.

## Wanneer moet u ervaringsfragmenten gebruiken? {#when-should-you-use-experience-fragments}

Er moeten ervaringsfragmenten worden gebruikt:

* Wanneer u ervaringen wilt hergebruiken.

   * Ervaringen die opnieuw worden gebruikt met dezelfde of vergelijkbare inhoud

* Wanneer u AEM gebruikt als platform voor het leveren van inhoud voor derden.

   * Elke oplossing die AEM als platform voor de levering van inhoud wil gebruiken
   * Inhoud insluiten in aanraakpunten van derden

* Als u ervaring hebt met verschillende variaties of uitvoeringen.

   * Kanaal- of contextspecifieke variaties
   * Ervaringen die zinvol zijn om te groeperen (bijvoorbeeld een campagne met verschillende ervaringen over kanalen)

* Wanneer u Omnichannel Commerce gebruikt.

   * Commerciële inhoud op schaal delen op sociale media
   * Transactie aanraakpunten maken

## Fragmenten voor uw ervaring ordenen {#organizing-your-experience-fragments}

Het wordt aanbevolen:
* mappen gebruiken om uw fragmenten van de ervaring te ordenen,

* [configureer de toegestane sjablonen voor deze mappen](#configure-allowed-templates-folder).

Door mappen te maken kunt u:

* een zinvolle structuur voor uw ervaringsfragmenten maken; bijvoorbeeld volgens classificatie

   >[!NOTE]
   >
   >U hoeft de structuur van uw ervaringsfragmenten niet uit te lijnen met de paginastructuur van uw site.

* [de toegestane sjablonen toewijzen op mapniveau](#configure-allowed-templates-folder)

   >[!NOTE]
   >
   >U kunt de [sjablooneditor](/help/sites-authoring/templates.md) gebruiken om uw eigen sjabloon te maken.

In het volgende voorbeeld ziet u de gestructureerde fragmenten van de ervaring `Contributors`. De gebruikte structuur illustreert ook hoe andere functies, zoals beheer voor meerdere sites (inclusief taalkopieën), kunnen worden gebruikt.

>[!CAUTION]
>
>De volgende schermafbeelding is als cloudservice genomen van de WKND-site met Adobe Experience Manager.

![Mappen voor ervaringsfragmenten](assets/xf-folders.png)

## Het creëren van en het Vormen van een Omslag voor uw Fragmenten van de Ervaring {#creating-and-configuring-a-folder-for-your-experience-fragments}

Om een omslag voor uw Fragments van de Ervaring tot stand te brengen en te vormen wordt het geadviseerd:

1. [Maak een map](/help/sites-authoring/managing-pages.md#creating-a-new-folder).

1. [Configureer de toegestane sjablonen voor ervaringsfragmenten voor die map](#configure-allowed-templates-folder).

>[!NOTE]
>
>Het is ook mogelijk om de [Toegestane Malplaatjes voor uw instantie](#configure-allowed-templates-instance)te vormen, maar deze methode wordt **niet** geadviseerd aangezien de waarden op verbetering kunnen worden beschreven.

### Configureer de toegestane sjablonen voor uw map {#configure-allowed-templates-folder}

>[!NOTE]
>
>Dit is de geadviseerde methode om de **[!UICONTROL Toegestane Malplaatjes]** te specificeren, aangezien de waarden niet op verbetering zullen worden beschreven.

1. Navigeer naar de map met vereiste **[!UICONTROL ervaringsfragmenten]** .

1. Selecteer de map en vervolgens **[!UICONTROL Eigenschappen]**.

1. Geef de reguliere expressie op voor het ophalen van de vereiste sjablonen in het veld **[!UICONTROL Toegestane sjablonen]** .

   Bijvoorbeeld:
   `/conf/(.*)/settings/wcm/templates/experience-fragment(.*)?`

   ![Ervaar fragmenteigenschappen - Toegestane sjablonen](assets/xf-folders-templates.png)

1. Selecteer **[!UICONTROL Opslaan en Sluiten]**.

### Vorm de Toegestane Malplaatjes voor uw Instantie {#configure-allowed-templates-instance}

>[!CAUTION]
>
>Het wordt afgeraden de **[!UICONTROL toegestane sjablonen]** met deze methode te wijzigen, omdat de opgegeven sjablonen tijdens de upgrade kunnen worden overschreven.
>
>Gebruik dit dialoogvenster alleen ter informatie.

1. Navigeer naar de vereiste **[!UICONTROL console van Fragments]** van de Ervaring.

1. Selecteer **[!UICONTROL configuratieopties]**:

   ![Knop Configuratie](assets/xf-folders-18.png)

1. Geef de vereiste sjablonen op in het dialoogvenster Fragmenten **[!UICONTROL voor ervaring]** configureren:

   ![Fragmenten voor ervaring configureren](assets/xf-folders-19.png)

1. Selecteer **[!UICONTROL Opslaan]**.

## Een ervaringsfragment maken {#creating-an-experience-fragment}

Een ervaringsfragment maken:

1. Selecteer Fragmenten **[!UICONTROL van de]** Ervaring van de Globale Navigatie.

   ![screen_shot_2018-04-05at92221am1](assets/screen_shot_2018-04-05at92221am1.png)

1. Navigeer naar de gewenste map en selecteer **[!UICONTROL Maken]**.

1. Selecteer Fragment **[!UICONTROL van de]** Ervaring om de **[!UICONTROL Create tovenaar van het Fragment]** van de Ervaring te openen.

   Selecteer de vereiste **[!UICONTROL sjabloon]** en **[!UICONTROL kies Volgende]**:

   ![xf-authoring-02](assets/xf-authoring-02.png)


1. Voer de **[!UICONTROL eigenschappen]** voor het fragment Ervaring in.

   Een **[!UICONTROL titel]** is verplicht. Als de **[!UICONTROL naam]** leeg blijft, wordt deze afgeleid van de **[!UICONTROL titel]**.

   ![xf-authoring-03](assets/xf-authoring-03.png)

1. Klik op **[!UICONTROL Maken]**.

   Er wordt een bericht weergegeven. Selecteer:

   * **[!UICONTROL Gereed]** om terug te keren naar de console
   * **[!UICONTROL Openen]** om de fragmenteditor te openen

## Uw ervaringsfragment bewerken {#editing-your-experience-fragment}

De Experience Fragment Editor biedt u vergelijkbare mogelijkheden als de normale pagina-editor. Zie Pagina-inhoud [](/help/sites-authoring/editing-content.md) bewerken voor meer informatie over het gebruik ervan.

De volgende voorbeeldprocedure laat zien hoe u een gummetje voor een product kunt maken:

1. Sleep een **[!UICONTROL categorietwitter]** vanuit de [Componentbrowser](/help/sites-authoring/author-environment-tools.md#components-browser).

   ![xf-authoring-04](assets/xf-authoring-04.png)

1. Selecteer **[!UICONTROL Vorm](/help/sites-authoring/editing-content.md#edit-configure-copy-cut-delete-paste)**van de componententoolbar.
1. Voeg het **[!UICONTROL element]** toe en definieer desgewenst de **[!UICONTROL eigenschappen]** .
1. Bevestig de definities met **[!UICONTROL Gereed]** (vinkje).
1. Voeg desgewenst meer componenten toe.

## Een ervaringsfragmentvariatie maken {#creating-an-experience-fragment-variation}

U kunt variaties van uw Fragment van de Ervaring tot stand brengen, afhankelijk van uw behoeften:

1. Open het fragment om het te [bewerken](/help/sites-authoring/experience-fragments.md#editing-your-experience-fragment).
1. Open het tabblad **[!UICONTROL Variaties]** .

   ![xf-authoring-06](assets/xf-authoring-06.png)

1. **Met Maken** kunt u:

   * **[!UICONTROL Variatie]**
   * **[!UICONTROL Variatie als live-kopie]**.

1. Definieer de vereiste eigenschappen:

   * **[!UICONTROL Sjabloonmodel]**
   * **[!UICONTROL Titel]**
   * **[!UICONTROL Naam]**; indien niet ingevuld, wordt het afgeleid van de titel
   * **[!UICONTROL Beschrijving]**
   * **[!UICONTROL Variatietags]**
   ![xf-authoring-06](assets/xf-authoring-07.png)

1. Bevestig met **[!UICONTROL Gereed]** (vinkpictogram), de nieuwe variant wordt weergegeven in het paneel:

   ![xf-authoring-08](assets/xf-authoring-08.png)

## Uw ervaringsfragment gebruiken {#using-your-experience-fragment}

U kunt het fragment van de Ervaring nu gebruiken wanneer het ontwerpen van uw pagina&#39;s:

1. Open een pagina om te bewerken.

   Bijvoorbeeld: [http://localhost:4502/editor.html/content/we-retail/language-masters/en/products/men.html](http://localhost:4502/editor.html/content/we-retail/language-masters/en/products/men.html)

1. Maak een instantie van de component Experience Fragment door de component van de browser Components naar het alineasysteem van de pagina te slepen:

   ![xf-authoring-09](assets/xf-authoring-09.png)

1. Voeg het daadwerkelijke fragment van de Ervaring aan de componenteninstantie toe; ofwel:

   * Sleep het vereiste fragment vanuit de middelenbrowser en zet het neer op de component
   * Selecteer **[!UICONTROL Vorm]** van de componententoolbar en specificeer het te gebruiken fragment, bevestig met **Gedaan** (tikken)
   ![xf-authoring-10](assets/xf-authoring-10.png)

   >[!NOTE]
   >
   >Bewerken werkt op de werkbalk van de component als een sneltoets waarmee het fragment in de fragmenteditor wordt geopend.

## Building Blocks {#building-blocks}

U kunt een of meer componenten selecteren om een bouwsteen voor recycling binnen uw fragment te maken:

### Een bouwblok maken {#creating-a-building-block}

Een nieuw bouwblok maken:

1. In de redacteur van het Fragment van de Ervaring, selecteer de componenten u wilt hergebruiken:

   ![xf-authoring-12](assets/xf-authoring-12.png)

1. Selecteer op de werkbalk Componenten de optie **[!UICONTROL Omzetten in bouwsteen]**:

   ![xf-authoring-13-icon](assets/xf-authoring-13-icon.png)

   Bijvoorbeeld:

   ![xf-authoring-13](assets/xf-authoring-13.png)

1. Voer de naam van het **[!UICONTROL bouwblok]** in en bevestig dit met **[!UICONTROL Omzetten]**:

   ![xf-authoring-14](assets/xf-authoring-14.png)

1. Het **bouwblok** wordt weergegeven op het tabblad en kan worden geselecteerd in het alineasysteem:

   ![xf-authoring-15](assets/xf-authoring-15.png)

### Een bouwblok beheren {#managing-a-building-block}

Uw bouwsteen is zichtbaar in de Blokken van de **[!UICONTROL Bouwstijl]** tabel. Voor elk blok zijn de volgende acties beschikbaar:

* Ga naar stramien: de hoofdvariant openen op een nieuw tabblad
* Naam wijzigen
* Verwijderen

![xf-authoring-16](assets/xf-authoring-16.png)

### Een bouwsteen gebruiken {#using-a-building-block}

U kunt de bouwsteen naar het alineasysteem van om het even welk fragment slepen, zoals met om het even welke component.

## De normale HTML-uitvoering {#the-plain-html-rendition}

Met de `.plain.` kiezer in de URL hebt u toegang tot de onbewerkte HTML-uitvoering.

Dit is beschikbaar in de browser, maar het primaire doel is om andere toepassingen (bijvoorbeeld webapps van derden, aangepaste mobiele implementaties) rechtstreeks toegang te geven tot de inhoud van het Experience Fragment door alleen de URL te gebruiken.

De normale HTML-uitvoering voegt het protocol-, host- en contextpad toe aan paden die:

* van het type: `src`, `href`of `action`

* of eindigen met: `-src`, of `-href`

Bijvoorbeeld:

`.../brooklyn-coat/master.plain.html`

>[!NOTE]
>
>Koppelingen verwijzen altijd naar de publicatie-instantie. Ze zijn bedoeld om door derden te worden gebruikt, dus de koppeling wordt altijd aangeroepen vanuit het publicatieexemplaar, niet vanuit de auteur.

![xf-authoring-17](assets/xf-authoring-17.png)

## Exporteren van ervaringsfragmenten {#exporting-experience-fragments}

Experience Fragments worden standaard geleverd in de HTML-indeling. Dit kan zowel door AEM als derdekanalen worden gebruikt.

Voor exporteren naar Adobe Target wordt HTML gebruikt. Zie [Doelintegratie met de Fragmenten](/help/sites-administering/experience-fragments-target.md) van de Ervaring voor volledige informatie.

