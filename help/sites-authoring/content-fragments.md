---
title: Pagina's ontwerpen met inhoudsfragmenten
seo-title: Pagina's ontwerpen met inhoudsfragmenten
description: Met AEM inhoudsfragmenten kunt u pagina-onafhankelijke inhoud ontwerpen, maken, beheren en gebruiken
seo-description: Met AEM inhoudsfragmenten kunt u pagina-onafhankelijke inhoud ontwerpen, maken, beheren en gebruiken
uuid: 66ccdff8-1658-4374-8562-97f81f434488
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: page-authoring
content-type: reference
discoiquuid: 076a3064-80c3-454b-93f9-6ae925c54328
translation-type: tm+mt
source-git-commit: c10c0ca79a0dd2e79c2d821f11cce3d28058aaa0
workflow-type: tm+mt
source-wordcount: '1120'
ht-degree: 6%

---


# Pagina&#39;s ontwerpen met inhoudsfragmenten{#page-authoring-with-content-fragments}

>[!CAUTION]
>
>Voor bepaalde functionaliteit voor inhoudsfragmenten is de toepassing van [AEM 6.4 Service Pack 2 (6.4.2.0) of hoger](/help/release-notes/sp-release-notes.md) vereist.

Inhoudsfragmenten van Adobe Experience Manager (AEM) worden [gemaakt en beheerd als paginaonafhankelijke assets](/help/assets/content-fragments.md).

U kunt hiermee kanaalneutrale inhoud maken, samen met (mogelijk kanaalspecifieke) variaties. Vervolgens kunt u deze fragmenten en de variaties ervan gebruiken bij het ontwerpen van de inhoudspagina&#39;s.

Samen met de bijgewerkte JSON-exportfunctie kunnen gestructureerde inhoudsfragmenten ook worden gebruikt om AEM inhoud via Content Services te leveren aan andere kanalen dan AEM pagina&#39;s.

>[!NOTE]
>
>**Content** Fragmentations en  **[Experience](/help/sites-authoring/experience-fragments.md)** Fragmentes zijn verschillende functies in AEM:
>
>* **Inhoudsfragmentaties** zijn redactionele inhoud, voornamelijk tekst en verwante afbeeldingen. Het zijn pure inhoud, zonder ontwerp en lay-out.
>* **De inhoud van de** ervaringen met fragmentatie is volledig afgebakend. een fragment van een webpagina.

>
>
De Fragmenten van de ervaring kunnen inhoud in de vorm van Inhoudsfragmenten bevatten, maar niet andersom.

>[!CAUTION]
>
>Deze pagina moet worden gelezen in combinatie met [Werken met inhoudsfragmenten](/help/assets/content-fragments.md) (en verwante pagina&#39;s), omdat deze basisterminologie en -concepten introduceert en fragmenten maakt en beheert.

Met de inhoudsfragmenten kunt u:

* **Marketings- en Campagne-strategie**

   * Inhoud controleren via centraal beheerde inhoudsfragmenten.

* **Creative Pro**

   * Het bijhouden van creatieve elementen via verzamelingen die zijn gekoppeld aan inhoudsfragmenten.

* **Schrijvers kopiëren**

   * Schrijf in de fragmenteditor voor AEM inhoud.
   * Kan inhoudvariaties maken.
   * Kan relevante inhoud aan het inhoudsfragment koppelen.
   * Kan versioning/workflow gebruiken.
   * Kan inhoudsfragment delen.
   * Kan vertalingen centraal beheren.

* **Producenten en journalisten**

   * Maak een keuze uit vooraf gedefinieerde fragmenten en variaties bij het ontwerpen in AEM.
   * Kan erop vertrouwen dat het fragment en de bijbehorende inhoud altijd up-to-date zijn terwijl kopieerschrijvers en -creatieven hun updates in centraal beheerde fragmenten en elementen maken.
   * Kan voor relevantie vertrouwen op gekoppelde media-inhoud die wordt verwerkt.
   * U kunt ad-hocinhoudvariaties maken terwijl u er toch voor zorgt dat deze variaties centraal worden beheerd in het fragment.

## Een inhoudsfragment toevoegen aan uw pagina {#adding-a-content-fragment-to-your-page}

1. Open de pagina om deze te bewerken.

1. Voeg de **[!UICONTROL Content Fragment]** component toe; in de **[!UICONTROL Components]**-browser of **[!UICONTROL Insert New Component]**.

1. U kunt:

   * Open de browser **[!UICONTROL Assets]** en filter voor **[!UICONTROL Content Fragments]** (de standaardwaarde is Afbeeldingen). Sleep het gewenste fragment vervolgens naar de componentinstantie.
   * Selecteer de component van het inhoudsfragment, dan **[!UICONTROL Configure]** van de toolbar. In het dialoogvenster kunt u het dialoogvenster Selectie openen waarin u de gewenste **[!UICONTROL Content Fragment]** kunt selecteren.

   >[!NOTE]
   >
   >Een andere methode is om een specifiek inhoudsfragment rechtstreeks naar de pagina te slepen. Hiermee wordt automatisch de bijbehorende component (inhoudsfragment) gemaakt.

1. In eerste instantie wordt de inhoud van het **[!UICONTROL Main]**-element en **[!UICONTROL Master]** (variatie) weergegeven. U kunt [andere elementen en/of variaties ](#selecting-the-element-or-variation) selecteren zoals vereist.

   ![cfm-6420-01](assets/cfm-6420-01.png)

   >[!NOTE]
   >
   >Zie ook voor meer informatie over de verdere bewerkingsfunctionaliteit:
   >
   >* [Responsieve lay-out](/help/sites-authoring/responsive-layout.md)
   >* [Paginacontent bewerken](/help/sites-authoring/editing-content.md)


## Element of Variatie selecteren {#selecting-the-element-or-variation}

Open het dialoogvenster **[!UICONTROL Configuration]** van het fragment om het fragment te configureren voor gebruik op de huidige pagina. Het dialoogvenster kan afhankelijk zijn van de gebruikte component.

In het juiste configuratiedialoogvenster kunt u de beschikbare parameters selecteren, waaronder:

* **[!UICONTROL Content Fragment]**

   Geef op welk fragment moet worden gebruikt.

* **[!UICONTROL Display Mode]**:

   * **[!UICONTROL Single Text Element]**
   * **[!UICONTROL Multiple Element]**

* **[!UICONTROL Element]**

   * De standaard **[!UICONTROL Main]** is altijd beschikbaar.
   * Er is een selectie beschikbaar als het fragment met een geschikte sjabloon is gemaakt.

   >[!NOTE]
   >
   >De beschikbare elementen zijn afhankelijk van de gebruikte sjabloon.

* **[!UICONTROL Variation]**

   * De standaard **[!UICONTROL Master]** is altijd beschikbaar.
   * Er is een selectie beschikbaar als er variaties zijn gemaakt voor het fragment.

* **[!UICONTROL Paragraphs]**: het bereik van de alinea(&#39;s) specificeren dat moet worden opgenomen:

   * **[!UICONTROL All]**
   * **[!UICONTROL Range]**: bijvoorbeeld,  `1`,  `3-5`  `9-*`

      * **[!UICONTROL Handle headings as their own paragraphs]**

* **[!UICONTROL Handle headings as their own paragraphs]**

## Snelle verbinding met fragmenteditor {#quick-connection-to-fragment-editor}

U kunt de fragmentbron voor bewerking (het element) openen met het pictogram **[!UICONTROL Edit]** op de componentwerkbalk. Hierdoor kunt u het inhoudsfragment[ bewerken en beheren.](/help/assets/content-fragments.md)

>[!CAUTION]
>
>Zoals altijd heeft het bewerken van de fragmentbron invloed op alle pagina&#39;s die naar dat inhoudsfragment verwijzen.

## Tussenliggende inhoud {#adding-in-between-content} toevoegen

Wanneer een specifiek inhoudsfragment aan de pagina wordt toegevoegd, is er een tijdelijke aanduiding **[!UICONTROL Drag components here]** tussen elke HTML-alinea (en boven/onder) van het fragment.

Hierdoor kunt u extra inhoud [tussen (d.w.z. tussen inhoud)](/help/assets/content-fragments.md#in-between-content-when-page-authoring-with-content-fragments) de fragmentinhoud (op een van de beschikbare punten) toevoegen zonder het basisfragment te hoeven veranderen.

Voor tussenliggende inhoud kunt u:

* Voeg componenten van [Componentbrowser](/help/sites-authoring/author-environment-tools.md#components-browser) toe.
* Voeg elementen toe vanuit de [middelenbrowser](/help/sites-authoring/author-environment-tools.md#assets-browser).
* Gebruik [Gekoppelde inhoud](#using-associated-content) als bron voor tussenliggende inhoud.

>[!CAUTION]
>
>De tussenliggende inhoud is pagina-inhoud. Deze wordt niet opgeslagen in het inhoudsfragment.

![cfm-6420-02](assets/cfm-6420-02.png)

>[!NOTE]
>
>U kunt ook [visuele elementen (afbeeldingen) invoegen in het fragment zelf](/help/assets/content-fragments-variations.md#inserting-assets-into-your-fragment).
>
>Visuele elementen die in het fragment zelf worden ingevoegd, worden aan de voorafgaande alinea in het fragment gekoppeld. Dit betekent dat u geen tussenliggende inhoud tussen een visueel element en de voorgaande alinea kunt plaatsen.

>[!CAUTION]
>
>Nadat u tussenliggende inhoud hebt toegevoegd aan een inhoudsfragment op uw pagina, kan het wijzigen van de structuur van het onderliggende inhoudsfragment (in de editor voor het inhoudsfragment) leiden tot onjuiste/onverwachte resultaten.
>
>Als dit gebeurt, wordt de tussenliggende inhoud als volgt bewaard:
>
>* Tussen componenten heeft een absolute positie binnen de reeks componenten in de fragmentstroom. Deze positie verandert niet, zelfs niet wanneer de inhoud van alinea&#39;s in het fragment verandert.\
   >  Hierdoor kan het lijken alsof de relatieve positionering is gewijzigd, aangezien de tussenliggende alinea&#39;s geen contextafhankelijke relatie hebben met de (fragment)alinea&#39;s naast de alinea&#39;s.
>* Tenzij de twee alinea&#39;s met elkaar in strijd zijn; in dat geval wordt de tussenliggende inhoud niet weergegeven (hoewel deze inhoud intern nog steeds aanwezig is).

>



## Gekoppelde inhoud {#using-associated-content} gebruiken

Als u [content hebt gekoppeld](/help/assets/content-fragments-assoc-content.md) aan het [contentfragment](/help/assets/content-fragments.md), zijn deze assets beschikbaar in het zijpaneel (nadat u het fragment op de contentpagina hebt geplaatst). Gekoppelde content is in feite een speciale bron van content voor [tussenliggende content](#adding-in-between-content).

>[!NOTE]
>
>Er zijn verschillende methoden om [visuele elementen (bijvoorbeeld afbeeldingen)](/help/assets/content-fragments.md#fragments-with-visual-assets) aan het fragment en/of de pagina toe te voegen.

>[!NOTE]
>
>Als er meerdere inhoudsfragmenten op één pagina staan, ziet u op het tabblad **[!UICONTROL Associated Content]** de elementen die geschikt zijn voor alle fragmenten.

Nadat u een fragment met de bijbehorende inhoud aan de pagina hebt toegevoegd, wordt een nieuw tabblad (**[!UICONTROL Associated Content]**) geopend in het zijpaneel.

Van hieruit kunt u de elementen naar de gewenste locatie slepen (naar een bestaande component of naar de gewenste positie waar de juiste component wordt gemaakt):

![cfm-6420-03](assets/cfm-6420-03.png)

## In het fragment ingevoegde elementen {#assets-inserted-into-the-fragment}

Als [elementen (bijvoorbeeld afbeeldingen) in het fragment zelf zijn ingevoegd](/help/assets/content-fragments-variations.md#inserting-assets-into-your-fragment), zijn de opties voor het bewerken van deze elementen in de pagina-editor beperkt.

Voor een afbeelding kunt u bijvoorbeeld

* Snijd, roteer of draai de afbeelding.
* Voeg een titel of alternatieve tekst toe.
* Geef een grootte op.
* U kunt ook de lay-out configureren.

Andere wijzigingen, zoals verplaatsen, kopiëren en verwijderen, moeten worden aangebracht in de fragmenteditor.

## {#publishing} publiceren

Fragmenten moeten worden gepubliceerd zodat ze op gepubliceerde webpagina&#39;s kunnen worden gebruikt:

* Een fragment kan worden gepubliceerd nadat het fragment [in de middelenconsole is gemaakt](/help/assets/content-fragments-managing.md#publishing-and-referencing-a-fragment).
* Als een *niet-gepubliceerd fragment* wordt gebruikt op een pagina die wordt gepubliceerd, kan het fragment ook op dit moment worden gepubliceerd.

