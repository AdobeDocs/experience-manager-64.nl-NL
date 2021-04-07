---
title: Het vormen RTE voor het Produceren van Toegankelijke Plaatsen
seo-title: Het vormen RTE voor het Produceren van Toegankelijke Plaatsen
description: Leer hoe te om de AEM Rich Text Editor te vormen om toegankelijke plaatsen te produceren.
seo-description: Leer hoe te om de AEM Rich Text Editor te vormen om toegankelijke plaatsen te produceren.
uuid: 87539fee-3ecc-49f4-af3d-8dde72399c28
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: operations
content-type: reference
discoiquuid: ff0f006d-461c-4cc4-b6eb-d665f3f3b498
exl-id: 245e1c28-f702-4300-81cf-5139db9d95ec
translation-type: tm+mt
source-git-commit: bd94d3949f0117aa3e1c9f0e84f7293a5d6b03b4
workflow-type: tm+mt
source-wordcount: '937'
ht-degree: 0%

---

# Het vormen RTE voor het Produceren van Toegankelijke Plaatsen {#configuring-rte-for-producing-accessible-sites}

AEM ondersteunt beide:

* standaardtoegankelijkheidsfuncties, waaronder alternatieve tekst voor afbeeldingen
* en extra eigenschappen die kunnen worden betreden wanneer het creëren van inhoud met componenten die de rijke tekstredacteur (RTE) gebruiken

>[!NOTE]
>
>* [Snelle gids aan WCAG 2.0](/help/managing/qg-wcag.md)
>* [Toegankelijke inhoud maken (WCAG 2.0-conformiteit)](/help/sites-authoring/creating-accessible-content.md)


Inhoudsauteurs kunnen functies van de RTE gebruiken om toegankelijkheidsinformatie te verstrekken terwijl ze inhoud aan een pagina toevoegen. Dit kan het toevoegen van structurele informatie door rubrieken en paragraafelementen omvatten.

U kunt [deze eigenschappen vormen en aanpassen door de steekmodules van RTE](#configuring-the-plugin-features) voor de component te vormen. Met de `paraformat`-plug-in kunt u bijvoorbeeld extra semantische elementen op blokniveau toevoegen, zoals het uitbreiden van het aantal kopniveaus dat wordt ondersteund, tot voorbij de standaard `H1`, `H2` en `H3`.

De RTE is beschikbaar in een verscheidenheid van componenten van zowel aanraking-toegelaten als klassieke UI. Nochtans, is de primaire component voor het gebruiken van RTE de **component Text**.

De **component Text** in AEM is beschikbaar voor zowel aanraking-toegelaten als klassieke UIs. In de volgende afbeeldingen ziet u de teksteditor met veel insteekmodules, waaronder `paraformat`:

* De **component Text** in de interface met aanraakbediening:

   ![Tekstcomponent (RTE) in de modus Volledig scherm in de gebruikersinterface met aanraakbediening.](assets/chlimage_1-206.png)

* De **component Text** in klassieke UI:

   ![Dialoogvenster voor bewerken (RTE) van de tekstcomponent in de klassieke UI.](assets/chlimage_1-207.png)

>[!NOTE]
>
>Er zijn verschillen tussen de eigenschappen van RTE beschikbaar in klassieke UI en aanraking-toegelaten UI. Zie voor meer informatie
>
>* [Insteekmodules en hun functies](/help/sites-administering/rich-text-editor.md#aboutplugins)
>* [Insteekmodules en hun functies - Interface met aanraakbediening](/help/sites-administering/rich-text-editor.md#aboutplugins)

>



## De insteekmodules {#configuring-the-plugin-features} configureren

De volledige instructies bij het vormen van RTE zijn beschikbaar op [het Vormen van de Rich Text Editor](/help/sites-administering/rich-text-editor.md) pagina. Hieronder vallen alle kwesties, inclusief de belangrijkste stappen:

* [Insteekmodules en hun functies](/help/sites-administering/rich-text-editor.md#aboutplugins)
* [Configuratielocaties](/help/sites-administering/rich-text-editor.md#understand-the-configuration-paths-and-locations)
* [Activeer een Insteekmodule en vorm het eigenschappenBezit](/help/sites-administering/rich-text-editor.md#enable-rte-functionalities-by-activating-plug-ins)
* [Het vormen van Andere Functionaliteit van RTE](/help/sites-administering/rich-text-editor.md#enable-rte-functionalities-by-activating-plug-ins)

Door een plug-in te configureren in de desbetreffende `rtePlugins`-subvertakking in CRXDE Lite (zie de volgende afbeelding), kunt u alle of specifieke functies voor die plug-in activeren.

![CRXDE Lite die een voorbeeld rtePlugin toont.](assets/chlimage_1-208.png)

### Voorbeeld - Het specificeren van de Formaten van de Paragraaf Beschikbaar in het Gebied van de Selectie van RTE {#example-specifying-paragraph-formats-available-in-rte-selection-field}

Nieuwe semantische blokformaten kunnen voor selectie beschikbaar worden gesteld door:

1. Afhankelijk van uw RTE, bepaal en navigeer aan [configuratielocatie](/help/sites-administering/rich-text-editor.md#understand-the-configuration-paths-and-locations).
1. [Het selectieveld](/help/sites-administering/rich-text-editor.md) Alinea inschakelen. door de  [insteekmodule](/help/sites-administering/rich-text-editor.md#enable-rte-functionalities-by-activating-plug-ins) te activeren.
1. [Geef de indelingen op die u beschikbaar wilt hebben in het selectieveld](/help/sites-administering/rich-text-editor.md) Alinea.
1. De paragraafformaten zijn dan beschikbaar aan de inhoudauteur van de selectiegebieden in RTE. Zij kunnen worden betreden:

   * Het pictogram Alinea ([pilcrow](https://en.wikipedia.org/wiki/Pilcrow)) gebruiken in de interface met aanraakbediening:

   ![Alineapictogram (kussen).](do-not-localize/chlimage_1-7.png)

   * Het **Formaat** gebied (drop-down selecteur) in klassieke UI gebruiken.


Met de structuurelementen beschikbaar in RTE via de opties van het paragraafformaat, AEM verstrekt een goede basis voor de ontwikkeling van toegankelijke inhoud. Inhoudsauteurs kunnen de RTE niet gebruiken om de tekengrootte of kleuren of andere verwante kenmerken op te maken, waardoor inlineopmaak niet mogelijk is. In plaats daarvan moeten ze de juiste structuurelementen selecteren, zoals koppen, en algemene stijlen gebruiken die u hebt gekozen bij de optie Stijlen. Zo zorgt u voor meer opmaak, betere opties voor gebruikers die met hun eigen stijlpagina&#39;s en correct gestructureerde inhoud bladeren.

## Het gebruik van de Bron geeft Eigenschap {#use-of-the-source-edit-feature} uit

In sommige gevallen zullen inhoudsauteurs het nodig vinden om de HTML-broncode die met de RTE is gemaakt, te onderzoeken en aan te passen. Bijvoorbeeld, kan een stuk van inhoud die binnen RTE wordt gecreeerd extra prijsverhoging vereisen om naleving WCAG 2.0 te verzekeren. Dit kan met [bron worden gedaan uitgeven](/help/sites-administering/rich-text-editor.md#aboutplugins) optie van RTE. U kunt de [ `sourceedit` eigenschap op `misctools` stop in ](/help/sites-administering/rich-text-editor.md#aboutplugins) specificeren.

>[!CAUTION]
>
>Gebruik de functie `sourceedit` zorgvuldig. Door fouten en/of niet-ondersteunde functies te typen kunnen er meer problemen ontstaan.

## Ondersteuning toevoegen voor extra HTML-elementen en -kenmerken {#adding-support-for-additional-html-elements-and-attributes}

Om de toegankelijkheidskenmerken van AEM verder uit te breiden, is het mogelijk om de bestaande componenten die op RTE (zoals **Text** en **Table** componenten) worden gebaseerd met extra elementen en attributen uit te breiden.

De volgende procedure laat zien hoe u de component **Tabel** kunt uitbreiden met een element **Bijschrift** dat informatie over een gegevenstabel bevat voor gebruikers van ondersteunende technologie:

### Voorbeeld - Bijschrift toevoegen aan het dialoogvenster Tabeleigenschappen {#example-adding-the-caption-to-the-table-properties-dialog}

Voeg in de constructor van de `TablePropertiesDialog` een extra tekstinvoerveld toe dat wordt gebruikt voor het bewerken van het bijschrift. `itemId` moet worden ingesteld op `caption` (d.w.z. de naam van het DOM-kenmerk) om de inhoud ervan automatisch te kunnen verwerken.

In **Lijst** moet u de attributen aan/uit het element van DOM uitdrukkelijk plaatsen of verwijderen. De waarde wordt doorgegeven door het dialoogvenster in het object `config`. DOM-kenmerken moeten worden ingesteld/verwijderd met de corresponderende `CQ.form.rte.Common`-methoden ( `com` is een sneltoets voor `CQ.form.rte.Common`) om gemeenschappelijke valkuilen bij browserimplementaties te voorkomen.

>[!NOTE]
>
>Deze procedure is alleen geschikt voor de klassieke gebruikersinterface.

### Instructies {#step-by-step-instructions} stap voor stap

1. Start CRXDE Lite. Bijvoorbeeld: [http://localhost:4502/crx/de/](http://localhost:4502/crx/de/)
1. Kopiëren:

   `/libs/cq/ui/widgets/source/widgets/form/rte/commands/Table.js`

   tot:

   `/apps/cq/ui/widgets/source/widgets/form/rte/commands/Table.js`

   >[!NOTE]
   >
   >Mogelijk moet u tussenliggende mappen maken als deze nog niet bestaan.

1. Kopiëren:

   `/libs/cq/ui/widgets/source/widgets/form/rte/plugins/TablePropertiesDialog.js`

   tot:

   `/apps/cq/ui/widgets/source/widgets/form/rte/plugins/TablePropertiesDialog.js`.

1. Open het volgende bestand om te bewerken (openen met dubbelklikken):

   `/apps/cq/ui/widgets/source/widgets/form/rte/plugins/TablePropertiesDialog.js`

1. Bij de methode `constructor`, vóór het lezen van de regel:

   ```
   var dialogRef = this;
   ```

   Voeg de volgende code toe:

   ```
   editItems.push({
       "itemId": "caption",
       "name": "caption",
       "xtype": "textfield",
       "fieldLabel": CQ.I18n.getMessage("Caption"),
       "value": (this.table && this.table.caption ? this.table.caption.textContent : "")
   });
   ```

1. Open het volgende bestand:

   `/apps/cq/ui/widgets/source/widgets/form/rte/commands/Table.js`.

1. Voeg de volgende code aan het einde van de methode `transferConfigToTable` toe:

   ```
   /**
    * Adds Caption Element
   */
   var captionElement;
   if (dom.firstChild && dom.firstChild.tagName.toLowerCase() == "caption")
   {
      captionElement = dom.firstChild;
   }
   if (config.caption)
   {
       var captionTextNode = document.createTextNode(config.caption)
       if (captionElement)
       {
          dom.replaceNode(captionElement.firstChild,captionTextNode);
       } else
       {
           captionElement = document.createElement("caption");
           captionElement.appendChild(captionTextNode);
           if (dom.childNodes.length>0)
           {
              dom.insertBefore(captionElement, dom.firstChild);
           } else
           {
              dom.appendChild(captionElement);
           }
       }
   } else if (captionElement)
   {
     dom.removeChild(captionElement);
   }
   ```

1. Wijzigingen opslaan met **Alles opslaan**

>[!NOTE]
>
>Een veld zonder opmaak is niet het enige invoertype dat is toegestaan voor de waarde van het bijschriftelement. Elke ExtJS-widget die de waarde van de ondertitel via de `getValue()`-methode biedt, kan worden gebruikt.
>
>Als u bewerkingsmogelijkheden voor meer aanvullende elementen en kenmerken wilt toevoegen, moet u ervoor zorgen dat:
>
>* De eigenschap `itemId` voor elk overeenkomend veld wordt ingesteld op de naam van het desbetreffende DOM-kenmerk (`TablePropertiesDialog`).
>* Het kenmerk wordt expliciet ingesteld en/of verwijderd op het DOM-element (`Table`).

