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
source-git-commit: 2d1e39120d79de029927011d48f7397b53ad91bc

---


# Clientlibs toevoegen {#add-clientlibs}

## Een ClientLibraryFolder (clientlibs) toevoegen {#add-a-clientlibraryfolder-clientlibs}

Maak een ClientLibraryFolder met de naam `clientlibs`die de JS en CSS bevat die worden gebruikt om de pagina&#39;s van uw site weer te geven.

De `categories`eigenschapwaarde die aan deze clientbibliotheek wordt gegeven, is de id die wordt gebruikt om deze client direct vanaf een inhoudspagina in te sluiten of om deze in andere clientlibs in te sluiten.

1. Met **[!UICONTROL CRXDE Lite]** uitvouwen `/etc/designs`

1. Klik met de rechtermuisknop `an-scf-sandbox` en selecteer `Create Node`

   * Naam: `clientlibs`
   * Type: `cq:ClientLibraryFolder`

1. Click **[!UICONTROL OK]**

![chlimage_1-220](assets/chlimage_1-220.png)

Voer op het tabblad **[!UICONTROL Eigenschappen]** voor het nieuwe `clientlibs` knooppunt de **`categories`** eigenschap in:

* Naam: **[!UICONTROL categorieën]**
* Type: **[!UICONTROL String]**
* Waarde: **[!UICONTROL apps.an-scf-sandbox]**
* Click **[!UICONTROL Add]**
* Klik op Alles **[!UICONTROL opslaan]**

Opmerking: De waarde voor categorieën wordt voorafgegaan door &#39;apps&#39;. is een conventie om aan te geven dat de &#39;toepassing die eigenaar is&#39; zich in de map /apps bevindt, niet /libs.  BELANGRIJK: Voeg plaatsaanduiding `js.txt` en `css.txt` bestanden toe. (Het is officieel geen cq:ClientLibraryFolder zonder hen.)


1. Rechtsklik ingeschakeld **`/etc/designs/an-scf-sandbox/clientlibs`**
1. Bestand **[!UICONTROL maken selecteren...]**
1. Voer **[!UICONTROL naam]** in: `css.txt`

1. Bestand **[!UICONTROL maken selecteren...]**
1. Voer **[!UICONTROL naam]** in: `js.txt`

1. Klik op Alles **[!UICONTROL opslaan]**

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

Voer op het tabblad **[!UICONTROL Eigenschappen]** voor het `clientlibs` knooppunt de eigenschap String met meerdere waarden in die u wilt **[!UICONTROL insluiten]**. Dit zal de noodzakelijke [cliënt-zijbibliotheken (clientlibs) voor componenten](client-customize.md#clientlibs-for-scf)inbedden SCF. Voor deze zelfstudie zullen we veel clientlibs toevoegen die nodig zijn voor de onderdelen van de Gemeenschappen.

**Merk** op dat dit of niet de gewenste benadering voor een productiesite kan zijn aangezien er overwegingen van gemak tegenover grootte/snelheid van de clientlibs die voor elke pagina worden gedownload zijn.

Als u slechts één functie op één pagina gebruikt, kunt u de volledige clientlib van die functie rechtstreeks op de pagina opnemen, bijvoorbeeld &lt;% ui:includeClientLib categorieën=cq.social.hbs.forum&quot; %>

In dit geval, sluiten wij hen allen, en zo zouden de eenvoudigere SCF clientlibs verkiezen die de auteur clientlibs zijn:

* Naam: **`embed`**
* Type: **`String`**

* Click **`Multi`**
* Waarde: **`cq.social.scf`**

   *&lt;enter> pop-up een dialoogvenster*

   *Klik **[+]**na elke ingang om de volgende cliëntlib categorieën toe te voegen:*

   * **`cq.ckeditor`**
   * **`cq.social.author.hbs.comments`**
   * **`cq.social.author.hbs.forum`**
   * **`cq.social.author.hbs.rating`**
   * **`cq.social.author.hbs.reviews`**
   * **`cq.social.author.hbs.voting`**
   * Click **[!UICONTROL OK]**

* Klik op Alles **[!UICONTROL opslaan]**

![chlimage_1-222](assets/chlimage_1-222.png)

Zo `/etc/designs/an-scf-sandbox/clientlibs` moet het nu in de opslagplaats worden weergegeven:

![chlimage_1-223](assets/chlimage_1-223.png)

## Clientlibs opnemen in PlayPage-sjabloon {#include-clientlibs-in-playpage-template}

Zonder de categorie `apps.an-scf-sandbox` ClientLibraryFolder op de pagina te plaatsen, zijn de SCF-componenten niet functioneel en niet opgemaakt omdat de benodigde JavaScript(s) en stijl(en) niet beschikbaar zijn.

Bijvoorbeeld, zonder de clientlibs op te nemen, lijkt de SCF commentaarcomponent ongestileerd:

![chlimage_1-224](assets/chlimage_1-224.png)

Zodra apps.an-scf-sandbox clientlibs is opgenomen, wordt de SCF-commentaarcomponent vormgegeven:

![chlimage_1-225](assets/chlimage_1-225.png)

De instructie include behoort tot de <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"> van de <html> script. De standaardwaarde **`foundation head.jsp`** bevat een script dat kan worden bedekt: **`headlibs.jsp`**.

**Kopieer koplibs.jsp en neem clientlibs op:**

1. Selecteer met **[!UICONTROL CRXDE Lite]****`/libs/foundation/components/page/headlibs.jsp`**
1. Klik met de rechtermuisknop en selecteer **[!UICONTROL Kopiëren]** (of selecteer Kopiëren in de werkbalk)
1. Selecteer **`/apps/an-scf-sandbox/components/playpage`**
1. Klik met de rechtermuisknop en selecteer **[!UICONTROL Plakken]** (of selecteer Plakken in de werkbalk)
1. Dubbelklik op **`headlibs.jsp`** om het te openen
1. De volgende regel toevoegen aan het einde van het bestand

   **`<ui:includeClientLib categories="apps.an-scf-sandbox"/>`**

1. Klik op Alles **[!UICONTROL opslaan]**


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

Dit pakket staat in de zelfstudie [Een voorbeeldpagina](create-sample-page.md) maken voor gebruikers die niet kunnen wachten om alleen binnen te springen en af te spelen...

Een pakket maken:


* Van **[!UICONTROL CRXDE Lite]**, klik het pictogram van het [Pakket](http://localhost:4502/crx/packmgr/)
* Klik op Pakket **[!UICONTROL maken]**

   * Pakketnaam: `an-scf-sandbox-minimal-pkg`
   * Versie: `0.1`
   * Groep: &lt;Als standaard verlaten>
   * Click **[!UICONTROL OK]**

* Click **[!UICONTROL Edit]**

   * Tabblad **[!UICONTROL Filters]** selecteren

      * Klik op **[!UICONTROL Toevoegen, filter]**
      * Hoofdpad: &lt;browse to `/apps/an-scf-sandbox`>
      * Klik op **[!UICONTROL Gereed]**
      * Klik op **[!UICONTROL Toevoegen, filter]**
      * Hoofdpad: &lt;browse to `/etc/designs/an-scf-sandbox`>
      * Klik op **[!UICONTROL Gereed]**
      * Klik op **[!UICONTROL Toevoegen, filter]**
      * Hoofdpad: &lt;browse to `/content/an-scf-sandbox`>
      * Klik op **[!UICONTROL Gereed]**
   * Click **[!UICONTROL Save]**


* Klik op **[!UICONTROL Samenstellen]**

Nu kunt u **[!UICONTROL Downloaden]** selecteren om het op schijf op te slaan en Pakket **[!UICONTROL elders te]** uploaden, evenals **[!UICONTROL Meer > Repliceren]** selecteren om de zandbak aan een localhost te duwen publiceert instantie om het domein van uw zandbak uit te breiden.
