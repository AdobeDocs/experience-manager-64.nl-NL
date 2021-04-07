---
title: De pagina-exportfunctie
seo-title: De pagina-exportfunctie
description: Leer hoe u de AEM Page Exporter gebruikt.
seo-description: Leer hoe u de AEM Page Exporter gebruikt.
uuid: 2ca2b8f1-c723-4e6b-8c3d-f5886cd0d3f1
contentOwner: Chiradeep Majumdar
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: content
content-type: reference
discoiquuid: 6ab07b5b-ee37-4029-95da-be2031779107
exl-id: a5cb3b7b-d40f-4d86-8473-fb584f1d486c
translation-type: tm+mt
source-git-commit: bd94d3949f0117aa3e1c9f0e84f7293a5d6b03b4
workflow-type: tm+mt
source-wordcount: '1019'
ht-degree: 0%

---

# De pagina-exportfunctie{#the-page-exporter}

AEM kunt u een pagina exporteren als een volledige webpagina met afbeeldingen, .js- en .css-bestanden.

Wanneer het exporteren is geconfigureerd, vraagt u eenvoudig een pagina in uw browser door `html` te vervangen door `export.zip` in de URL en krijgt u een gecomprimeerde bestandsdownload met de weergegeven pagina in HTML-indeling en de bestanden waarnaar wordt verwezen. Alle paden op de pagina, bijvoorbeeld paden naar afbeeldingen, worden herschreven zodat ze verwijzen naar de bestanden in het ZIP-bestand of naar de bronnen op de server.

## Een pagina {#exporting-a-page} exporteren

De volgende stappen beschrijven hoe te om een pagina uit te voeren, en veronderstellen dat een malplaatje van de de uitvoerconfiguratie voor uw plaats bestaat. Een configuratiesjabloon definieert de manier waarop een pagina wordt geëxporteerd en is specifiek voor uw site. Om een configuratiemalplaatje tot stand te brengen verwijs naar [Creërend een Configuratie van de Exporteur van de Pagina voor uw sectie ](#creating-a-page-exporter-configuration-for-your-site).

Een pagina exporteren:

1. Open de pagina in uw browser. Bijvoorbeeld:
1. `http://localhost:4502/content/geometrixx/en/products/triangle.html`
1. Open het dialoogvenster met pagina-eigenschappen, selecteer het tabblad **Geavanceerd** en vouw de veldset **Exporteren** uit.

1. Klik op het vergrootpictogram en selecteer een configuratiesjabloon. Selecteer de sjabloon **geometrixx**, aangezien dit de standaardsjabloon is voor de site Geometrixx. Klik **OK**.

1. Klik **OK** om het dialoogvenster Pagina-eigenschappen te sluiten.
1. Vraag de pagina aan door `html` door `export.zip` in URL te vervangen.

1. Download het bestand `<page-name>.export.zip` naar uw bestandssysteem.

1. Pak in uw bestandssysteem het bestand uit:

   * het pagina-html-bestand ( `<page-name>.html`) is beschikbaar onder `<unzip-dir>/<page-path>`
   * andere bronnen (.js-bestanden, .css-bestanden, afbeeldingen, ...) bevinden zich volgens de instellingen in de exportsjabloon. In dit voorbeeld zijn sommige bronnen onder `<unzip-dir>/etc`, sommige onder `<unzip-dir>/<page-path>`.

1. Open het pagina-HTML-bestand ( `<unzip-dir>/<page-path>.html`) in uw browser om de rendering te controleren.

## Een configuratie voor paginaexportters maken voor uw site {#creating-a-page-exporter-configuration-for-your-site}

De pagina-exportfunctie is gebaseerd op het Content Sync framework. De configuraties die beschikbaar zijn in het dialoogvenster Pagina-eigenschappen zijn configuratiesjablonen. Zij bepalen alle vereiste gebiedsdelen voor een pagina. Wanneer een paginauitvoer wordt teweeggebracht, wordt het configuratiesjabloon gebruikt en zowel de paginadad als de ontwerppad dynamisch toegepast op de configuratie. Het ZIP-bestand wordt vervolgens gemaakt met de standaardfunctionaliteit voor het synchroniseren van inhoud.

AEM sluit een aantal sjablonen in, waaronder:

* Een standaard bij `/etc/contentsync/templates/default`. Deze sjabloon:

   * Is het fallback malplaatje wanneer geen configuratiemalplaatje in de bewaarplaats wordt gevonden.
   * Kan als basis voor een nieuw configuratiesjabloon dienen.

* Een site die is toegewezen aan de **Geometrixx**-site, op `/etc/contentsync/templates/geometrixx`. Deze sjabloon kan als voorbeeld worden gebruikt om een nieuwe sjabloon te maken.

Een configuratiesjabloon voor een pagina-exportfunctie maken:

1. Maak in **CRXDE Lite** een knooppunt onder `/etc/contentsync/templates`:

   * Naam: bijv. `mysite`. De naam wordt weergegeven in het dialoogvenster Pagina-eigenschappen wanneer u de sjabloon voor het exporteren van pagina&#39;s kiest.
   * Type: `nt:unstructured`

1. Onder de malplaatjeknoop, genoemd hier `mysite`, creeer een knoopstructuur gebruikend de hieronder beschreven configuratieknopen.

### Configuratieknooppunten van pagina-exportter {#page-exporter-configuration-nodes}

Het configuratiesjabloon bestaat uit een nodestructuur. Elk knooppunt heeft een eigenschap `type` die een specifieke handeling definieert in het aanmaakproces van het ZIP-bestand. Voor meer details over het typebezit, verwijs naar het Overzicht van configuratietypes in de het kaderpagina van de Synchronisatie van de Inhoud.

De volgende knopen kunnen worden gebruikt om een malplaatje van de de uitvoerconfiguratie te bouwen:

**page** nodeThe page node is used to copy the page html to the zip file. Het heeft de volgende kenmerken:

* Is een verplicht knooppunt.
* Wordt onder `/etc/contentsync/templates/<sitename>` geplaatst.
* De naam is `page`.
* Het knooppunttype is `nt:unstructured`

Het knooppunt `page` heeft de volgende eigenschappen:

* Een eigenschap `type` ingesteld met de waarde `pages`.

* Het heeft geen `path` bezit aangezien het huidige paginapad dynamisch aan de configuratie wordt gekopieerd.

* De andere eigenschappen worden beschreven in het gedeelte Overzicht van configuratietypen van het Content Sync-framework.

**herschrijven** nodeHet knooppunt rewrite definieert hoe de koppelingen in de geëxporteerde pagina worden herschreven. De herschreven koppelingen kunnen verwijzen naar de bestanden in het ZIP-bestand of naar de bronnen op de server.

Raadpleeg de pagina Content Sync voor een volledige beschrijving van het knooppunt `rewrite`.

**ontwerpknooppuntHet** ontwerpknooppunt wordt gebruikt om het ontwerp te kopiëren dat voor de geëxporteerde pagina wordt gebruikt. Het heeft de volgende kenmerken:

* Is optioneel.
* Wordt onder `/etc/contentsync/templates/<sitename>` geplaatst.
* De naam is `design`.
* Het knooppunttype is `nt:unstructured`.

Het knooppunt `design` heeft de volgende eigenschappen:

* Een eigenschap `type` ingesteld op de waarde `copy`.

* Het heeft geen `path` bezit aangezien het huidige paginapad dynamisch aan de configuratie wordt gekopieerd.

**algemeen** nodeA algemeen knooppunt wordt gebruikt om bronnen zoals clientBPS .js- of CSS-bestanden naar het ZIP-bestand te kopiëren. Het heeft de volgende kenmerken:

* Is optioneel.
* Wordt onder `/etc/contentsync/templates/<sitename>` geplaatst.
* Heeft geen specifieke naam.
* Het knooppunttype is `nt:unstructured`.
* Bevat een `type`-eigenschap en eventuele `type`-gerelateerde eigenschappen zoals gedefinieerd in de sectie Overzicht van configuratietypen van het Content Sync-framework.

Met het volgende configuratieknooppunt kopieert u bijvoorbeeld de bestanden geometrixx client.js naar het ZIP-bestand:

```xml
"geometrixx.clientlibs.js": {
    "extension": "js",
    "type": "clientlib",
    "path": "/etc/designs/geometrixx/clientlibs",
    "jcr:primaryType": "nt:unstructured"
}
```

Het **Geometrixx** malplaatje van de de paginatransportconfiguratie toont u hoe een paginauitvoer kan worden gevormd. Als u de knooppuntstructuur van de sjabloon in uw browser wilt weergeven als een JPEG-indeling, vraagt u om de volgende URL:

`http://localhost:4502/etc/contentsync/templates/geometrixx.-1.json`

**Een aangepaste configuratie implementeren**

Aangezien u in de knoopstructuur kunt opgemerkt, **Geometrixx** heeft het malplaatje van de paginatransportconfiguratie een `logo` knoop met een `type` bezit dat aan `image` wordt geplaatst. Dit is een speciaal configuratietype dat is gemaakt om het afbeeldingslogo naar het ZIP-bestand te kopiëren. Om aan sommige specifieke vereisten te voldoen, kunt u een douane `type` bezit moeten uitvoeren: Raadpleeg hiervoor de sectie Een aangepaste update-handler implementeren in de pagina Content Sync.

## Een pagina {#programmatically-exporting-a-page} programmatisch exporteren

Als u een pagina programmatisch wilt exporteren, kunt u de service [PageExporter](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/index.html?com/day/cq/wcm/contentsync/PageExporter.html) OSGI gebruiken. Met deze service kunt u:

* Exporteer een pagina en schrijf naar de HTTP-servletreactie.
* Exporteer een pagina en sla het ZIP-bestand op een specifieke locatie op.

De servlet die aan `export` selecteur en `zip` uitbreiding verbindt gebruikt de dienst PageExporter.

## Problemen oplossen {#troubleshooting}

Als er een probleem optreedt met het downloaden van het ZIP-bestand, kunt u het `/var/contentsync`-knooppunt in de gegevensopslagruimte verwijderen en het exportverzoek opnieuw verzenden.
