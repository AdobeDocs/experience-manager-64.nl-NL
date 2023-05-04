---
title: Clientlibs toevoegen
seo-title: Add Clientlibs
description: Een ClientLibraryFolder toevoegen
seo-description: Add a ClientLibraryFolder
uuid: cdc1d258-2011-4517-9206-dd2b5d1f7e0d
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: c84040b0-7850-4960-b676-ffa0a74c8cb2
exl-id: 9b8c3d1c-a9b1-4dde-9044-46c8f2b22c22
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '683'
ht-degree: 3%

---

# Clientlibs toevoegen {#add-clientlibs}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Een ClientLibraryFolder (clientlibs) toevoegen {#add-a-clientlibraryfolder-clientlibs}

Een ClientLibraryFolder maken met de naam `clientlibs`die de JS en CSS bevat die worden gebruikt om de pagina&#39;s van uw site weer te geven.

De `categories`De eigenschapwaarde die aan deze clientbibliotheek wordt gegeven, is de id die wordt gebruikt om deze clientlib rechtstreeks vanaf een inhoudspagina in te sluiten of om deze in andere clientlibs in te sluiten.

1. Gebruiken **[!UICONTROL CRXDE Lite]**, uitbreiden `/etc/designs`

1. Rechtsklik ingeschakeld `an-scf-sandbox` en selecteert u `Create Node`

   * Naam: `clientlibs`
   * Type: `cq:ClientLibraryFolder`

1. Klik op **[!UICONTROL OK]**

![chlimage_1-220](assets/chlimage_1-220.png)

In de **[!UICONTROL Properties]** tab voor de nieuwe `clientlibs` knoop, ga in **`categories`** eigenschap:

* Naam: **[!UICONTROL categories]**
* Type: **[!UICONTROL String]**
* Waarde: **[!UICONTROL apps.an-scf-sandbox]**
* Klik op **[!UICONTROL Add]**
* Klik op **[!UICONTROL Save All]**

Opmerking: De waarde voor categorieën wordt voorafgegaan door &#39;apps&#39;. is een conventie om aan te geven dat de &#39;toepassing die eigenaar is&#39; zich in de map /apps bevindt, niet /libs.  BELANGRIJK: Plaatsaanduiding toevoegen `js.txt` en `css.txt` bestanden. (Het is officieel geen cq:ClientLibraryFolder zonder hen.)


1. Rechtsklik ingeschakeld **`/etc/designs/an-scf-sandbox/clientlibs`**
1. Selecteer **[!UICONTROL Create File...]**
1. Enter **[!UICONTROL Name]**: `css.txt`

1. Selecteer **[!UICONTROL Create File...]**
1. Enter **[!UICONTROL Name]**: `js.txt`

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

## SCF-clips insluiten {#embed-scf-clientlibs}

In de **[!UICONTROL Properties]** tab voor de `clientlibs` node, voer de eigenschap String voor meerdere waarden in **[!UICONTROL embed]**. Hierdoor worden de noodzakelijke [client-side bibliotheken (clientlibs) voor SCF-componenten](client-customize.md#clientlibs-for-scf). Voor deze zelfstudie zullen we veel clientlibs toevoegen die nodig zijn voor de onderdelen van de Gemeenschappen.

**Opmerking** dat dit al dan niet de gewenste benadering voor een productiesite kan zijn aangezien er overwegingen van gemak tegenover grootte/snelheid van de clientlibs die voor elke pagina worden gedownload zijn.

Als u slechts één functie op één pagina gebruikt, kunt u de volledige clientlib van die functie rechtstreeks op de pagina opnemen, bijvoorbeeld &lt;% ui:includeClientLib categorieën=cq.social.hbs.forum&quot; %>

In dit geval, sluiten wij hen allen, en zo zouden de eenvoudigere SCF clientlibs verkiezen die de auteur clientlibs zijn:

* Naam: **`embed`**
* Type: **`String`**

* Klik op **`Multi`**
* Waarde: **`cq.social.scf`**

   *&lt;enter> pop-up van dialoogvenster*

   *Klikken **[+]**na elke vermelding om de volgende clientlib-categorieën toe te voegen:*

   * **`cq.ckeditor`**
   * **`cq.social.author.hbs.comments`**
   * **`cq.social.author.hbs.forum`**
   * **`cq.social.author.hbs.rating`**
   * **`cq.social.author.hbs.reviews`**
   * **`cq.social.author.hbs.voting`**
   * Klik op **[!UICONTROL OK]**

* Klik op **[!UICONTROL Save All]**

![chlimage_1-222](assets/chlimage_1-222.png)

Zo `/etc/designs/an-scf-sandbox/clientlibs` moet nu worden weergegeven in de gegevensopslagruimte:

![chlimage_1-223](assets/chlimage_1-223.png)

## Clientlibs opnemen in PlayPage-sjabloon {#include-clientlibs-in-playpage-template}

Zonder de `apps.an-scf-sandbox` De categorie ClientLibraryFolder op de pagina, de SCF-componenten zijn niet functioneel en niet opgemaakt omdat de benodigde Javascript(s) en stijl(en) niet beschikbaar zijn.

Bijvoorbeeld, zonder de clientlibs op te nemen, lijkt de SCF commentaarcomponent ongestileerd:

![chlimage_1-224](assets/chlimage_1-224.png)

Zodra apps.an-scf-sandbox clientlibs is opgenomen, wordt de SCF-commentaarcomponent vormgegeven:

![chlimage_1-225](assets/chlimage_1-225.png)

De instructie include behoort tot de `<head>` van de `<html>` script. De standaardwaarde **`foundation head.jsp`** bevat een script dat kan worden bedekt: **`headlibs.jsp`**.

**Kopieer koplibs.jsp en neem clientlibs op:**

1. Gebruiken **[!UICONTROL CRXDE Lite]**, selecteert u **`/libs/foundation/components/page/headlibs.jsp`**
1. Klikken met rechtermuisknop en selecteren **[!UICONTROL Copy]** (of selecteer Kopiëren in de werkbalk)
1. Selecteer **`/apps/an-scf-sandbox/components/playpage`**
1. Klikken met rechtermuisknop en selecteren **[!UICONTROL Paste]** (of selecteer Plakken in de werkbalk)
1. Dubbelklikken op **`headlibs.jsp`** openen
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

Dit pakket is beschikbaar op het tabblad [Een voorbeeldpagina maken](create-sample-page.md) zelfstudie voor hen die niet kunnen wachten om gewoon binnen te springen en te beginnen met afspelen...

Een pakket maken:


* Van **[!UICONTROL CRXDE Lite]** klikt u op de knop [Pakketpictogram](http://localhost:4502/crx/packmgr/)
* Klik op **[!UICONTROL Create Package]**

   * Pakketnaam: `an-scf-sandbox-minimal-pkg`
   * Versie: `0.1`
   * Groep: &lt;leave as=&quot;&quot; default=&quot;&quot;>
   * Klik op **[!UICONTROL OK]**

* Klik op **[!UICONTROL Edit]**

   * Selecteren **[!UICONTROL Filters]** tab

      * Klik op **[!UICONTROL Add filter]**
      * Hoofdpad: &lt;browse to=&quot;&quot; span=&quot;&quot; id=&quot;0&quot; translate=&quot;no&quot; />>`/apps/an-scf-sandbox`
      * Klik op **[!UICONTROL Done]**
      * Klik op **[!UICONTROL Add filter]**
      * Hoofdpad: &lt;browse to=&quot;&quot; span=&quot;&quot; id=&quot;0&quot; translate=&quot;no&quot; />>`/etc/designs/an-scf-sandbox`
      * Klik op **[!UICONTROL Done]**
      * Klik op **[!UICONTROL Add filter]**
      * Hoofdpad: &lt;browse to=&quot;&quot; span=&quot;&quot; id=&quot;0&quot; translate=&quot;no&quot; />>`/content/an-scf-sandbox`
      * Klik op **[!UICONTROL Done]**
   * Klik op **[!UICONTROL Save]**


* Klik op **[!UICONTROL Build]**

Nu kunt u **[!UICONTROL Download]** opslaan naar schijf en **[!UICONTROL Upload Package]** en selecteert u **[!UICONTROL More > Replicate]** om de sandbox naar een publicatieinstantie van de localhost te verplaatsen en het domein van de sandbox uit te breiden.
