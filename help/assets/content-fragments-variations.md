---
title: Variaties - Authoring van content voor fragmenten
seo-title: Variations - Authoring Fragment Content
description: Met behulp van variaties kunt u inhoud voor het fragment ontwerpen en vervolgens variaties van die inhoud maken op basis van het doel (indien nodig).
seo-description: Variations allow you to author content for the fragment, then create variations of that content according to purpose (if required).
uuid: affccda0-be5f-47d2-85b6-8701b77ac932
contentOwner: AEM Docs
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: content-fragments
content-type: reference
discoiquuid: 1cdb2dfc-623b-44cf-9a7b-98cfabbb1d0c
exl-id: 15a5fdc9-2878-4f95-83ee-02a2899aeb43
feature: Content Fragments
role: User
source-git-commit: 3358f6b8b492ff2b5858867a1f48a57b06944b1e
workflow-type: tm+mt
source-wordcount: '1708'
ht-degree: 10%

---

# Variaties - Authoring van content voor fragmenten {#variations-authoring-fragment-content}

>[!CAUTION]
>
>Voor bepaalde functies voor inhoudsfragmenten moet de toepassing van [AEM 6.4 Service Pack 2 (6.4.2.0) of later](../release-notes/sp-release-notes.md).

[Variaties](content-fragments.md#constituent-parts-of-a-content-fragment) zijn een belangrijk kenmerk van inhoudsfragmenten, aangezien u hiermee kopieën van de master inhoud kunt maken en bewerken voor gebruik op specifieke kanalen en/of scenario&#39;s.

Van de **Variaties** tabblad kunt u:

* [Voer de inhoud in](#authoring-your-content) voor uw fragment
* [Variaties maken en beheren](#managing-variations) van de **Master** content

Voer een reeks andere acties uit afhankelijk van het gegevenstype dat wordt uitgegeven; bijvoorbeeld:

* [Visuele elementen in een fragment invoegen](#inserting-assets-into-your-fragment) (afbeeldingen)
* Selecteren tussen [RTF](#rich-text), [Onbewerkte tekst](#plain-text) en [Markering](#markdown) voor bewerking

* [Inhoud uploaden](#uploading-content)

* [Belangrijkste statistieken weergeven](#viewing-key-statistics) (over tekst met meerdere regels)
* [Tekst samenvatten](#summarizing-text)

* [Variaties synchroniseren met Master inhoud](#synchronizing-with-master)

>[!CAUTION]
>
>Nadat een fragment is gepubliceerd en/of waarnaar wordt verwezen, geeft AEM een waarschuwing weer wanneer een auteur het fragment opent om opnieuw te bewerken. Hiermee wordt u gewaarschuwd dat wijzigingen in het fragment ook van invloed zijn op de pagina&#39;s waarnaar wordt verwezen.

## Inhoud ontwerpen {#authoring-your-content}

Wanneer u het inhoudsfragment opent voor bewerking, worden de **Variaties** is standaard geopend. Hier kunt u de inhoud ontwerpen, voor Master of andere variaties. U kunt:

* direct wijzigingen aanbrengen in het dialoogvenster **Variaties** tab
* open [full-screen redacteur](#full-screen-editor) tot:

   * Selecteer de [Indeling](#formats)
   * zie meer bewerkingsopties (voor [RTF](#rich-text) bestandsindeling)
   * toegang tot een reeks [handelingen](#actions)

Bijvoorbeeld:

* Een eenvoudig fragment bewerken

   Een eenvoudig fragment bestaat uit één tekstveld met meerdere regels (visuele elementen kunnen worden toegevoegd vanuit de volledige-schermeditor).

   ![cfm-6420-21](assets/cfm-6420-21.png)

* Een fragment met gestructureerde inhoud bewerken

   Een gestructureerd fragment bevat diverse velden, van verschillende gegevenstypen, die zijn gedefinieerd in het inhoudsmodel. Voor velden met meerdere regels geldt het volgende: [full-screen redacteur](#full-screen-editor) is beschikbaar.

   ![cfm-6420-16](assets/cfm-6420-16.png)

### Editor op volledig scherm {#full-screen-editor}

Als u een tekstveld met meerdere regels bewerkt, kunt u de volledige-schermeditor openen:

![cf-fullscreen-editor-icon](assets/cf-fullscreeneditor-icon.png)

De volledige-schermredacteur verstrekt:

* Toegang tot verschillende [handelingen](#actions)
* Afhankelijk van de [format](#formats), aanvullende opmaakopties ([RTF](#rich-text))

### Acties {#actions}

De volgende acties zijn ook beschikbaar (voor alle [formaten](#formats)) als de volledige-schermeditor (d.w.z. tekst met meerdere regels) is geopend:

* Selecteer [format](#formats) ([RTF](#rich-text), [Onbewerkte tekst](#plain-text), [Markering](#markdown))
* [Tekststatistieken tonen](#viewing-key-statistics)
* [Inhoud uploaden](#uploading-content)
* [Synchroniseren met Master](#synchronizing-with-master) (bij het bewerken van een variatie)
* [Tekst samenvatten](#summarizing-text)
* [Annoteren](content-fragments-variations.md#annotating-a-content-fragment) uw tekst

* [Visuele elementen in een fragment invoegen](#inserting-assets-into-your-fragment) (afbeeldingen)

### Indelingen {#formats}

De opties voor het bewerken van tekst met meerdere regels zijn afhankelijk van de geselecteerde indeling:

* [RTF](#rich-text)
* [Onbewerkte tekst](#plain-text)
* [Markering](#markdown)

De indeling kan worden geselecteerd in de schermvullende editor.

### RTF {#rich-text}

Met RTF-bewerkingen kunt u de volgende opmaken:

* Vet
* Cursief
* Onderstrepen
* Uitlijning: links, midden, rechts
* Lijst met opsommingstekens
* Genummerde lijst
* Inspringing: toename, afname
* Hyperlinks maken/verbreken
* Open de volledige-schermredacteur, waar de volgende het formatteren opties beschikbaar zijn:

   * Tekst/tekst uit Word plakken
   * Een tabel invoegen
   * Alineastijl: Alinea, kopje 1/2/3
   * [Visuele elementen invoegen](#inserting-assets-into-your-fragment)
   * Zoeken
   * Zoeken/vervangen
   * Spellingcontrole
   * [Annotaties](content-fragments-variations.md#annotating-a-content-fragment)

De [handelingen](#actions) zijn ook toegankelijk van de volledig-schermredacteur.

### Onbewerkte tekst {#plain-text}

Met platte tekst kunt u snel inhoud invoeren zonder opmaak- of markeringsgegevens. U kunt de volledige-schermeditor ook voor meer informatie openen [handelingen](#actions).

>[!CAUTION]
>
>Als u **Tekst zonder opmaak** selecteert, gaan opmaak, markdown en/of assets die u hebt ingevoegd in **Tekst met opmaak** of **Markdown** verloren.

### Markering {#markdown}

>[!NOTE]
>
>Zie voor meer informatie de [Markering](content-fragments-markdown.md) documentatie.

Hierdoor kunt u de tekst opmaken met behulp van een markering. U kunt het volgende definiëren:

* Koppen
* Alinea&#39;s en regeleinden
* Koppelingen
* Afbeeldingen
* Aanhalingstekens blokkeren
* Lijsten
* Nadruk
* Codeblokken
* backslash-eces

U kunt de volledige-schermeditor ook voor meer informatie openen [handelingen](#actions).

>[!CAUTION]
>
>Als u tussen **Tekst met opmaak** en **Markdown** schakelt, kunt u onverwachte effecten met Blokcitaten en Codeblokken ervaren, aangezien deze twee opmaakindelingen verschillen in hoe zij worden behandeld.

### Belangrijkste statistieken weergeven {#viewing-key-statistics}

Wanneer de volledige-schermeditor open is, zal de actie **Tekststatistieken** allerlei informatie over de tekst tonen. Bijvoorbeeld:

![cfx-6420-22](assets/cfx-6420-22.png)

### Inhoud uploaden {#uploading-content}

Als u het maken van inhoudsfragmenten wilt vereenvoudigen, kunt u tekst uploaden die is voorbereid in een externe editor en deze rechtstreeks aan het fragment toevoegen.

### Tekst samenvatten {#summarizing-text}

Samenvattende tekst is ontworpen om gebruikers te helpen de lengte van hun tekst te beperken tot een vooraf gedefinieerd aantal woorden, terwijl de hoofdpunten en de algemene betekenis behouden blijven.

>[!NOTE]
>
>Op technisch niveau handhaaft het systeem de zinnen die het beschouwt als het leveren van de *beste verhouding tussen informatiedichtheid en uniciteit* volgens specifieke algoritmen.

>[!CAUTION]
>
>Het inhoudsfragment moet een geldige taalmap hebben als voorouder. dit wordt gebruikt om het te gebruiken taalmodel te bepalen.
>
>Bijvoorbeeld: `en/` zoals in het volgende pad:
>
>`/content/dam/my-brand/en/path-down/my-content-fragment`

>[!CAUTION]
>
>Engels is beschikbaar buiten de box.
>
>Andere talen zijn beschikbaar als Pakketten van het Model van de Taal van de Distributie van de Software:
>
>* [Frans (fr) van Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq630/product/smartcontent-model-fr)
>* [Duits (de) van Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq630/product/smartcontent-model-de)
>* [Italiaans (it) van softwaredistributie](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq630/product/smartcontent-model-it)
>* [Spaans (es) van Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq630/product/smartcontent-model-es)
>


1. Selecteren **[!UICONTROL Master]** of de vereiste wijziging.
1. Open de editor voor het volledige scherm.

1. Selecteren **[!UICONTROL Summarize text]** op de werkbalk.

   ![cf-17](assets/cf-17.png)

1. Geef het doelaantal woorden op en selecteer **[!UICONTROL Start]**:
1. De oorspronkelijke tekst wordt naast de voorgestelde samenvatting weergegeven:

   * Alle zinnen die moeten worden verwijderd, worden rood gemarkeerd met doorhaling.
   * Klik op een gemarkeerde zin om deze in de samengevatte inhoud te houden.
   * Klik op een niet-gemarkeerde zin om deze te verwijderen.

   ![cfm-6420-23](assets/cfm-6420-23.png)

1. Selecteren **[!UICONTROL Summarize]** om de wijzigingen te bevestigen.

### Een inhoudsfragment annoteren {#annotating-a-content-fragment}

Een fragment annoteren:

1. Selecteren **[!UICONTROL Master]** of de vereiste wijziging.
1. Open de editor voor het volledige scherm.
1. Selecteer tekst. De **[!UICONTROL Annotate]** wordt beschikbaar.

   ![cfm-6420-24](assets/cfm-6420-24.png)

1. Er wordt een dialoogvenster geopend. Hier kunt u uw annotatie invoeren.

1. Sluit de volledige het schermredacteur en **[!UICONTROL Save]** het fragment.

### Annotaties weergeven, bewerken, verwijderen {#viewing-editing-deleting-annotations}

Annotaties:

* Deze worden aangegeven door de markering in de tekst, zowel in de modus Volledig scherm als in de normale modus van de editor. Alle details van een annotatie kunnen vervolgens worden weergegeven, bewerkt en/of verwijderd door op de gemarkeerde tekst te klikken, waarna het dialoogvenster opnieuw wordt geopend.

   >[!NOTE]
   >
   >Er is een keuzekiezer beschikbaar als er meerdere annotaties zijn toegepast op één stuk tekst.

* Wanneer u de volledige tekst verwijdert waarop de annotatie is toegepast, wordt de annotatie ook verwijderd.

* Kan worden weergegeven en verwijderd door het selectievakje **[!UICONTROL Annotations]** in de fragmenteditor.

   ![cfm-6420-25](assets/cfm-6420-25.png)

* Kan worden weergegeven en verwijderd in [Tijdlijn](https://helpx.adobe.com/experience-manager/6-3/assets/using/content-fragments-managing.html#timeline-for-content-fragments) voor het geselecteerde fragment.

### Elementen invoegen in uw fragment {#inserting-assets-into-your-fragment}

U kunt toevoegen om het ontwerpen van inhoudsfragmenten te vereenvoudigen [Activa](managing-assets-touch-ui.md) (afbeeldingen) rechtstreeks naar het fragment.

Ze worden zonder opmaak toegevoegd aan de alineasequentie van het fragment. de opmaak kan worden uitgevoerd wanneer de [fragment wordt gebruikt of er wordt naar verwezen op een pagina](/help/sites-authoring/content-fragments.md).

>[!CAUTION]
>
>Deze elementen kunnen niet worden verplaatst of verwijderd op een pagina waarnaar wordt verwezen. Dit moet gebeuren in de fragmenteditor.
>
>Opmaak van het element (bv. grootte) moet echter plaatsvinden in het dialoogvenster [paginaeditor](/help/sites-authoring/content-fragments.md). De representatie van het element in de fragmenteditor is uitsluitend bedoeld voor het ontwerpen van de inhoudsstroom.

>[!NOTE]
>
>Er zijn verschillende methoden om toe te voegen [afbeeldingen](content-fragments.md#fragments-with-visual-assets) op het fragment en/of de pagina.

1. Plaats de cursor op de positie waar u de afbeelding wilt toevoegen.
1. Gebruik de **[!UICONTROL Insert Asset]** om het zoekdialoogvenster te openen.

   ![cf-insert-asset-icon](assets/cf-insertasset-icon.png)

1. In het dialoogvenster kunt u:

   * navigeren naar het vereiste element in DAM
   * zoeken naar de middelen in DAM

   Selecteer het gewenste element door op de miniatuur te klikken.

1. Gebruiken **[!UICONTROL Select]** om het element op de huidige locatie toe te voegen aan het alineasysteem van het inhoudsfragment.

   >[!CAUTION]
   >
   >Als u na het toevoegen van een asset de indeling wijzigt in:
   >
   >* **Tekst zonder opmaak**: wordt de asset volledig uit het fragment verwijderd.
   >* **Markdown**: is de asset niet zichtbaar, maar blijft deze aanwezig wanneer u terugkeert naar **Tekst met opmaak**.


## Variaties beheren {#managing-variations}

### Een variatie maken {#creating-a-variation}

Met variaties kunt u de **Master** inhoud en variëren naar gelang van het doel (indien vereist).

Een nieuwe variatie maken:

1. Open het fragment en controleer of het zijpaneel zichtbaar is.
1. Selecteren **[!UICONTROL Variations]** in de pictogrambalk in het zijpaneel.
1. Selecteer **[!UICONTROL Create Variation]**.
1. Er wordt een dialoogvenster geopend waarin u de **[!UICONTROL Title]** en **[!UICONTROL Description]** voor de nieuwe wijziging.
1. Selecteren **[!UICONTROL Add]**; het fragment **[!UICONTROL Master]** wordt gekopieerd naar de nieuwe variant, waarvoor nu een [bewerken](#editing-a-variation).

   >[!NOTE]
   >
   >Bij het maken van een nieuwe variatie is dit altijd **Master** dat wordt gekopieerd, niet de variatie die momenteel open is.

### Een variatie bewerken {#editing-a-variation}

U kunt wijzigingen aanbrengen in de inhoud van de variatie nadat:

* [Uw variatie maken](#creating-a-variation).
* Een bestaand fragment openen en vervolgens de gewenste variant in het zijpaneel selecteren.

![cfm-6420-26](assets/cfm-6420-26.png)

### De naam van een variatie wijzigen {#renaming-a-variation}

Een bestaande variatie een andere naam geven:

1. Open het fragment en selecteer **[!UICONTROL Variations]** in het zijpaneel.
1. Selecteer de gewenste variatie.
1. Selecteren **[!UICONTROL Rename]** van de **[!UICONTROL Actions]** vervolgkeuzelijst.

1. Voer de nieuwe **[!UICONTROL Title]** en/of **[!UICONTROL Description]** in het resulterende dialoogvenster.

1. Bevestig de **[!UICONTROL Rename]** handeling.

>[!NOTE]
>
>Dit heeft alleen invloed op de variatie **Titel**.

### Een variatie verwijderen {#deleting-a-variation}

Een bestaande wijziging verwijderen:

1. Open het fragment en selecteer **[!UICONTROL Variations]** in het zijpaneel.
1. Selecteer de gewenste variatie.
1. Selecteren **[!UICONTROL Delete]** van de **[!UICONTROL Actions]** vervolgkeuzelijst.

1. Bevestig de **[!UICONTROL Delete]** in het dialoogvenster.

>[!NOTE]
>
>U kunt niet verwijderen **Master**.

### Synchroniseren met Master {#synchronizing-with-master}

**Master** maakt integraal deel uit van een inhoudsfragment en bevat per definitie de master kopie van de inhoud, terwijl de variaties de afzonderlijke bijgewerkte en op maat gemaakte versies van die inhoud bevatten. Wanneer Master wordt bijgewerkt, is het mogelijk dat deze wijzigingen ook relevant zijn voor de variaties en daarom aan hen moeten worden doorgegeven.

Wanneer u een variatie bewerkt, hebt u toegang tot de handeling voor het synchroniseren van het huidige element van de variatie met Master. Op deze manier kunt u automatisch wijzigingen kopiëren die u hebt aangebracht in de Master variatie.

>[!CAUTION]
>
>De synchronisatie is alleen beschikbaar om wijzigingen *van **Master**naar de variatie* te kopiëren.
>
>Alleen het huidige element van de variatie wordt gesynchroniseerd.
>
>Synchronisatie werkt alleen op het datatype **Tekst met meerdere regels**.
>
>Het overbrengen van wijzigingen *van een variatie naar **master*** is niet beschikbaar als optie.

1. Open het inhoudsfragment in de fragmenteditor. Zorg ervoor dat de **Master** is bewerkt.
2. Selecteer een specifieke variant en kies vervolgens de gewenste synchronisatiehandeling uit:

   * de **Handelingen** keuzelijst - **Huidig element synchroniseren met master**
   * de werkbalk van de volledige schermweergave - **Synchroniseren met master**

3. Master en de variatie wordt naast elkaar weergegeven:

   * groen geeft de inhoud aan die is toegevoegd (aan de variatie)
   * rood geeft aan dat inhoud is verwijderd (uit de variatie)

   ![cfm-6420-27](assets/cfm-6420-27.png)

4. Selecteren **[!UICONTROL Synchronize]**, wordt de wijziging bijgewerkt en weergegeven.
