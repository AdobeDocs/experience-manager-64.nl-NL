---
title: Clientlibs toevoegen
seo-title: Clientlibs toevoegen
description: Een ClientLibraryFolder toevoegen
seo-description: Een ClientLibraryFolder toevoegen
uuid: cdc1d258-2011-4517-9206-dd2b5d1f7e0d
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: c84040b0-7850-4960-b676-ffa0a74c8cb2
translation-type: tm+mt
source-git-commit: 805e4411930749ff4b6b05ea4a8b87b4f96d72fd
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 4%

---


# Clientlibs {#add-clientlibs} toevoegen

## Een ClientLibraryFolder (clientlibs) {#add-a-clientlibraryfolder-clientlibs} toevoegen

Maak een ClientLibraryFolder met de naam `clientlibs`die de JS en CSS bevat die worden gebruikt om de pagina&#39;s van uw site weer te geven.

De `categories`eigenschapswaarde die aan deze cliëntbibliotheek wordt gegeven is het herkenningsteken dat wordt gebruikt om deze cliënt van een inhoudspagina direct te omvatten of het in andere clientlibs in te bedden.

1. Vouw `/etc/designs` uit met **[!UICONTROL CRXDE Lite]**

1. Klik met de rechtermuisknop op `an-scf-sandbox` en selecteer `Create Node`

   * Naam: `clientlibs`
   * Type: `cq:ClientLibraryFolder`

1. Klik op **[!UICONTROL OK]**

![chlimage_1-220](assets/chlimage_1-220.png)

Voer op het tabblad **[!UICONTROL Properties]** voor het nieuwe `clientlibs`-knooppunt de eigenschap **`categories`** in:

* Naam: **[!UICONTROL categories]**
* Type: **[!UICONTROL String]**
* Waarde: **[!UICONTROL apps.an-scf-sandbox]**
* Klik op **[!UICONTROL Add]**
* Klik op **[!UICONTROL Save All]**

Opmerking: De waarde voor categorieën wordt voorafgegaan door &#39;apps&#39;. is een conventie om aan te geven dat de &#39;toepassing die eigenaar is&#39; zich in de map /apps bevindt, niet /libs.  BELANGRIJK: Voeg placeholder `js.txt` en `css.txt` dossiers toe. (Het is officieel geen cq:ClientLibraryFolder zonder hen.)


1. Klikken met rechtermuisknop op **`/etc/designs/an-scf-sandbox/clientlibs`**
1. Selecteer **[!UICONTROL Create File...]**
1. Voer **[!UICONTROL Name]** in: `css.txt`

1. Selecteer **[!UICONTROL Create File...]**
1. Voer **[!UICONTROL Name]** in: `js.txt`

1. Klik op **[!UICONTROL Save All]**

![chlimage_1-221](assets/chlimage_1-221.png)

De eerste regel van css.txt en js.txt identificeert de basislocatie van waaruit de volgende lijsten met bestanden moeten worden gevonden.

Stel de inhoud van css.txt in op:

```
#base=.
 style.css
```

Maak vervolgens een bestand onder clientlibs met de naam style.css en stel de inhoud in op:

`body {`

`background-color: #b0c4de;`

`}`

## SCF-clips {#embed-scf-clientlibs} insluiten

Voer op het tabblad **[!UICONTROL Properties]** voor het knooppunt `clientlibs` de eigenschap tekenreeks met meerdere waarden **[!UICONTROL embed]** in. Dit zal de noodzakelijke [cliënt-zijbibliotheken (clientlibs) voor SCF componenten](client-customize.md#clientlibs-for-scf) inbedden. Voor deze zelfstudie zullen we veel clientlibs toevoegen die nodig zijn voor de onderdelen van de Gemeenschappen.

**** Merk op dat dit al dan niet de gewenste benadering voor een productiesite kan zijn aangezien er overwegingen van gemak tegenover grootte/snelheid van de clientlibs die voor elke pagina worden gedownload zijn.

Als u slechts één functie op één pagina gebruikt, kunt u de volledige clientlib van die functie rechtstreeks op de pagina opnemen, bijvoorbeeld &lt;% ui:includeClientLib categorieën=cq.social.hbs.forum&quot; %>

In dit geval, sluiten wij hen allen, en zo zouden de eenvoudigere SCF clientlibs verkiezen die de auteur clientlibs zijn:

* Naam: **`embed`**
* Type: **`String`**

* Klik op **`Multi`**
* Waarde: **`cq.social.scf`**

   *&lt;enter> pop-up van dialoogvenster*

   *Klik **[+]**na elke ingang om de volgende cliëntlib categorieën toe te voegen:*

   * **`cq.ckeditor`**
   * **`cq.social.author.hbs.comments`**
   * **`cq.social.author.hbs.forum`**
   * **`cq.social.author.hbs.rating`**
   * **`cq.social.author.hbs.reviews`**
   * **`cq.social.author.hbs.voting`**
   * Klik op **[!UICONTROL OK]**

* Klik op **[!UICONTROL Save All]**

![chlimage_1-222](assets/chlimage_1-222.png)

Dit is hoe `/etc/designs/an-scf-sandbox/clientlibs` nu in de bewaarplaats moet verschijnen:

![chlimage_1-223](assets/chlimage_1-223.png)

## Clientlibs opnemen in PlayPage-sjabloon {#include-clientlibs-in-playpage-template}

Zonder de categorie `apps.an-scf-sandbox` ClientLibraryFolder op de pagina te plaatsen, zijn de SCF-componenten niet functioneel en niet opgemaakt omdat de benodigde Javascript(s) en stijl(en) niet beschikbaar zijn.

Bijvoorbeeld, zonder de clientlibs op te nemen, lijkt de SCF commentaarcomponent ongestileerd:

![chlimage_1-224](assets/chlimage_1-224.png)

Zodra apps.an-scf-sandbox clientlibs is opgenomen, wordt de SCF-commentaarcomponent vormgegeven:

![chlimage_1-225](assets/chlimage_1-225.png)

De include-instructie behoort tot de sectie `<head>` van het `<html>`-script. De standaard **`foundation head.jsp`** bevat een script dat kan worden bedekt: **`headlibs.jsp`**.

**Kopieer koplibs.jsp en neem clientlibs op:**

1. Selecteer **[!UICONTROL CRXDE Lite]****`/libs/foundation/components/page/headlibs.jsp`**
1. Klik met de rechtermuisknop en selecteer **[!UICONTROL Copy]** (of selecteer Kopiëren in de werkbalk)
1. Selecteer **`/apps/an-scf-sandbox/components/playpage`**
1. Klik met de rechtermuisknop en selecteer **[!UICONTROL Paste]** (of selecteer Plakken in de werkbalk)
1. Dubbelklik op **`headlibs.jsp`** om deze te openen
1. De volgende regel toevoegen aan het einde van het bestand

   **`<ui:includeClientLib categories="apps.an-scf-sandbox"/>`**

1. Klik op **[!UICONTROL Save All]**


```xml
<%@ page session="false" %><%
%><%@include file="/libs/foundation/global.jsp" %><%
%><ui:includeClientLib categories="cq.foundation-main"/><%
%>
<cq:include script="/libs/cq/cloudserviceconfigs/components/servicelibs/servicelibs.jsp"/>
<% currentDesign.writeCssIncludes(pageContext); %>
<ui:includeClientLib categories="apps.an-scf-sandbox"/>
```

Laad uw website in de browser en controleer of de achtergrond geen blauwe tint heeft.

[http://localhost:4502/content/an-scf-sandbox/en/play.html](http://localhost:4502/content/an-scf-sandbox/en/play.html)

![chlimage_1-226](assets/chlimage_1-226.png)

## Uw werk tot nu toe opslaan {#saving-your-work-so-far}

Op dit moment bestaat er een minimalistische sandbox en het kan de moeite waard zijn om op te slaan als een pakket, zodat u tijdens het afspelen, als uw reactie beschadigd raakt en u opnieuw wilt beginnen, de server kunt uitschakelen, de naam van de map crx-quickstart/ wijzigen of verwijderen, de server in kunt schakelen, uploaden en installeren van dit opgeslagen pakket en deze basisstappen niet hoeft te herhalen.

Dit pakket bevindt zich op de zelfstudie [Een voorbeeldpagina maken](create-sample-page.md) voor diegenen die niet kunnen wachten om gewoon binnen te springen en af te spelen!..

Een pakket maken:


* Van **[!UICONTROL CRXDE Lite]**, klik [het pictogram van het Pakket](http://localhost:4502/crx/packmgr/)
* Klik op **[!UICONTROL Create Package]**

   * Pakketnaam: `an-scf-sandbox-minimal-pkg`
   * Versie: `0.1`
   * Groep: &lt;Als standaard verlaten>
   * Klik op **[!UICONTROL OK]**

* Klik op **[!UICONTROL Edit]**

   * Tabblad **[!UICONTROL Filters]** selecteren

      * Klik op **[!UICONTROL Add filter]**
      * Hoofdpad: &lt;blader aan `/apps/an-scf-sandbox`>
      * Klik op **[!UICONTROL Done]**
      * Klik op **[!UICONTROL Add filter]**
      * Hoofdpad: &lt;blader aan `/etc/designs/an-scf-sandbox`>
      * Klik op **[!UICONTROL Done]**
      * Klik op **[!UICONTROL Add filter]**
      * Hoofdpad: &lt;blader aan `/content/an-scf-sandbox`>
      * Klik op **[!UICONTROL Done]**
   * Klik op **[!UICONTROL Save]**


* Klik op **[!UICONTROL Build]**

Nu kunt u **[!UICONTROL Download]** selecteren om het op schijf en **[!UICONTROL Upload Package]** elders te bewaren, evenals **[!UICONTROL More > Replicate]** te selecteren om de zandbak aan een localhost te duwen publiceert instantie om het domein van uw zandbak uit te breiden.
