---
title: Informatie over AEM Assets
description: Ontdek de gebruiksscenario's van digitale middelen en de aanbieding van deze middelen voor middelenbeheer AEM Adobe.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 077cc39c5ed47371a4e3fae1e991209c7bfe6b80
workflow-type: tm+mt
source-wordcount: '900'
ht-degree: 0%

---


# Informatie over AEM Assets {#about-assets}

Elementen zijn een DAM-hulpmiddel (Digital Asset Management) dat volledig is geïntegreerd met het AEM-platform en waarmee uw onderneming digitale middelen kan delen en distribueren. Gebruikers in een organisatie kunnen afbeeldingen, video&#39;s, documenten, audioclips en rich media, zoals Flash-bestanden, beheren, opslaan en openen voor gebruik op het web, in gedrukte vorm en voor digitale distributie.

## Wat is Digital Asset Management (DAM)? {#what-is-digital-asset-management}

Middelen bieden bedrijfsbreed delen en distribueren van de belangrijkste digitale middelen van een organisatie. Gebruikers in een organisatie kunnen digitale elementen zoals afbeeldingen, afbeeldingen, audio, video en documenten via een webinterface (of een CIFS- of WebDAV-map) opslaan, beheren en benaderen.

Met AEM Assets, volledig geïntegreerd in AEM, kunt u het volgende doen:

* U kunt afbeeldingen, documenten, audiobestanden en videobestanden in verschillende bestandsindelingen toevoegen en delen.
* Elementen beheren door deze te groeperen op tags, lichtbakken of sterren (uw favorieten). Annotaties toevoegen aan elementen.
* U kunt elementen zoeken door te zoeken in bestandsnamen, de volledige tekst van documenten en door datums, documenttype en codes te zoeken.
* Voeg metagegevens voor elementen toe of bewerk deze. Metagegevens worden automatisch bijgewerkt met het bijbehorende element. U kunt metagegevens van elementen importeren of exporteren.
* Voer functies voor het bewerken van afbeeldingen uit, zoals schalen en afbeeldingsfilters toevoegen. U kunt meerdere digitale elementen tegelijk importeren en exporteren met een WebDAV- of CIFS-map.
* Gebruik workflows en meldingen om gezamenlijke verwerking en downloads van een set elementen mogelijk te maken en toegangsrechten voor elementen te beheren.

### AEM Assets is volledig geïntegreerd met AEM WCM-mogelijkheden {#aem-assets-fully-integrated-in-cq-wcm}

AEM Assets is volledig geïntegreerd met CQ WCM en de functionaliteit is beschikbaar via het DAM-pictogram:

<!-- TBD: Update image for branding -->

![screen_shot_2012-04-17at15946pm](assets/screen_shot_2012-04-17at15946pm.png) ![screen_shot_2012-04-17at20100pm](assets/screen_shot_2012-04-17at20100pm.png)

Elementen die binnen CQ DAM worden beheerd, zijn vervolgens toegankelijk via de zoeker naar inhoud van WCM:

<!-- TBD: Update image for branding -->

![screen_shot_2012-04-17at20214pm](assets/screen_shot_2012-04-17at20214pm.png)

>[!NOTE]
>
>De basisnavigatie van gebruikersinterface is het zelfde als de rest van AEM - zie [Overzicht van de Console](/help/sites-authoring/qg-page-authoring.md) GUI voor volledige details.

### Digital Asset Management versus Image-component {#digital-asset-management-versus-image-component}

Houd rekening met de levenscyclus van de afbeelding wanneer u bepaalt of u een afbeelding in AEM Assets wilt plaatsen of de component Image wilt gebruiken:

* Als de afbeelding dezelfde levenscyclus heeft als de pagina, gebruikt u de component Image.
* Als de afbeelding een aparte levenscyclus heeft, bijvoorbeeld als u de afbeelding tweemaal of buiten WCM gebruikt, gebruikt u AEM Assets.

## Wat zijn digitale middelen? {#what-are-digital-assets}

Middelen zijn digitale documenten, afbeeldingen, video of audio (of een deel daarvan) die meerdere uitvoeringen kunnen hebben en subelementen kunnen bevatten (bijvoorbeeld lagen in een Photoshop-bestand, dia&#39;s in een PowerPoint-bestand, pagina&#39;s in een PDF, bestanden in een ZIP).

Een element is in wezen een binair plus metagegevens plus uitvoeringen plus subelementen. Raadpleeg de [DAM Performance Guide](/help/sites-deploying/assets-performance-sizing.md) voor meer informatie.

>[!CAUTION]
>
>Het uploaden en/of bewerken van een groot volume aan elementen (in het bijzonder afbeeldingen) kan de prestaties van uw CQ-instantie beïnvloeden.

### AEM Assets-terminologie {#aem-assets-terminology}

Wanneer u met digitale middelen in AEM werkt, moet u de volgende terminologie begrijpen:

* **Verzameling:** Een verzameling elementen op basis van de fysieke locatie (map), algemene eigenschappen (opgeslagen zoekmap) of gebruikersselectie (lichtbakmappen).

* **Metagegevens:** Elementen hebben metagegevens; bijvoorbeeld auteur, vervaldatum, DRM-informatie (Digital Rights Management) enzovoort. Metagegevens zijn toegankelijk. AEM Assets biedt ondersteuning voor de volgende algemene metagegevensschema&#39;s in het vak:

   * **Dublin Core**: inclusief auteur, beschrijving, datum, onderwerp, enzovoort.
   * **IPTC**: inclusief gebeurtenis, model, locatie, enzovoort.
   * **WCM**: inclusief pagina-eigenschappen, op tijd en uit, enzovoort.

* **Tags:** Elementen kunnen worden gelabeld en geclassificeerd. Zie Tags gebruiken en Tags beheren.

* **Uitvoeringen:** Een vertoning is de binaire representatie van een element. Elementen hebben altijd een primaire representatie, namelijk die van het geüploade bestand. Ze kunnen een willekeurig aantal aanvullende voorstellingen hebben die worden gemaakt, bijvoorbeeld door aangepaste workflowstappen of wanneer een element wordt geüpload. Uitvoeringen kunnen een andere grootte hebben, met een andere resolutie, met een toegevoegd watermerk of een ander gewijzigd kenmerk.

* **Versies:** Met Versioning maakt u een momentopname van digitale elementen op een bepaald tijdstip. U kunt middelen aan vorige versies herstellen. Zie [versioning in AEM Assets](managing-assets-touch-ui.md#asset-versioning).

* **Subactiva:** Subelementen zijn elementen die een element vormen, bijvoorbeeld lagen in een Adobe Photoshop-bestand of pagina&#39;s in een PDF-bestand. In AEM Assets kunt u subelementen op dezelfde manier beheren als elementen.

### Werken met middelen {#how-to-work-with-assets}

U voert een actie op een middel of een inzameling uit. Met handelingen kunt u elementen, verzamelingen en uitvoeringen maken of wijzigen. Veel van de basishandelingen die u uitvoert op elementen - uploaden, verwijderen, bijwerken, opslaan van subelementen - activeren vooraf geconfigureerde workflows. Deze worden automatisch in AEM Assets ingeschakeld en worden in AEM Assets in detail beschreven.

De taken u met deze vooraf geconfigureerde workflows kunt uitvoeren:

* Sla het middel op in de opslagplaats of verwijder het middel uit de opslagplaats.
* Metagegevens voor het element extraheren en opslaan; de afzonderlijke metagegevensitems worden opgeslagen als XMP.
* Uitvoeringen en miniaturen genereren voor het element; inclusief, waar nodig, automatisch vergroten/verkleinen en uitsnijden.
* Transcodeer het element waar nodig. Zo wordt video voor mobiel gebruik en webgebruik getranscodeerd met 24 frames per seconde. Download video met 30 frames per seconde. Audio voor mobiel en webgebruik wordt getranscodeerd met 128 kbps, audio voor downloaden met 192 kbps.

Natuurlijk kunt u werkstromen ook handmatig toepassen. Zie [AEM Assets Media](media-handlers.md)Handlersfor a list of default workflows.

## AEM DAM en AEM MediaLibrary {#cq-dam-vs-cq-medialibrary}

Zie [AEM DAM en AEM MediaLibrary](medialibrary.md) voor informatie over de verschillen.
