---
title: Een volledig functionele website (JSP) maken
seo-title: Een volledig functionele website (JSP) maken
description: Met deze zelfstudie kunt u een volledig uitgeruste website maken met AEM
seo-description: Met deze zelfstudie kunt u een volledig uitgeruste website maken met AEM
uuid: bb8d4efd-7631-4cc5-8084-b03c6aabdef3
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: introduction
content-type: reference
discoiquuid: 8d14017d-d311-45e9-8aea-4a5ca46f1a07
translation-type: tm+mt
source-git-commit: b698a1348df3ec2ab455c236422784d10cbcf7c2
workflow-type: tm+mt
source-wordcount: '4528'
ht-degree: 2%

---


# Creeer een volledig-gekenmerkte Website (JSP){#create-a-fully-featured-website-jsp}

>[!CAUTION]
>
>In dit artikel wordt beschreven hoe u een website maakt met JSP en op basis van de klassieke gebruikersinterface. Adobe raadt u aan de nieuwste AEM technologieën voor uw websites te gebruiken, zoals gedetailleerd wordt beschreven in het artikel [Getting Started Developing AEM Sites](/help/sites-developing/getting-started.md).

Met deze zelfstudie kunt u een volledig uitgeruste website maken met Adobe Experience Manager (AEM). De website is gebaseerd op een algemene website en is vooral gericht op webontwikkelaars. Alle ontwikkeling vindt plaats in een auteur-omgeving.

In deze zelfstudie wordt beschreven hoe u:

1. AEM installeren.
1. Access CRXDE Lite (de ontwikkelomgeving).
1. Stel de projectstructuur in CRXDE Lite in.
1. Maak de sjabloon, component en scripts die worden gebruikt als basis voor het maken van inhoudspagina&#39;s.
1. Maak de basispagina voor uw website en stel vervolgens de inhoudspagina&#39;s in.
1. Maak de volgende componenten voor gebruik op uw pagina&#39;s:

   * **[!UICONTROL Top Navigation]**
   * **[!UICONTROL List Children]**
   * **[!UICONTROL Logo]**
   * **[!UICONTROL Image]**
   * **[!UICONTROL Text-Image]**
   * **[!UICONTROL Search]**

1. Verschillende basiscomponenten opnemen.

Nadat u alle stappen hebt uitgevoerd, zien de pagina&#39;s er als volgt uit:

![chlimage_1-99](assets/chlimage_1-99.png)

**Het uiteindelijke resultaat downloaden**

Download website-1.0.zip om de zelfstudie te volgen en niet de oefeningen uit te voeren. Dit bestand is een AEM inhoudspakket dat de resultaten van deze zelfstudie bevat. Gebruik [Pakketbeheer](/help/sites-administering/package-manager.md) om het pakket te installeren naar de auteurinstantie.

>[!NOTE]
>Als u dit pakket installeert, worden alle bronnen op de ontwerpinstantie die u met deze zelfstudie hebt gemaakt, overschreven.

Inhoud van website

[Bestand ophalen](assets/website-1_0.zip)

## Adobe Experience Manager {#installing-adobe-experience-manager} installeren

Als u een AEM voor het ontwikkelen van uw website wilt installeren, volgt u de instructies voor het instellen van een [implementatieomgeving met auteur en het publiceren van instanties](/help/sites-deploying/deploy.md#author-and-publish-installs), of voert u een [algemene installatie](/help/sites-deploying/deploy.md#default-local-install) uit. De algemene installatie omvat het downloaden van het AEM QuickStart JAR-bestand, het plaatsen van het bestand license.properties in dezelfde map als het JAR-bestand en het dubbelklikken op het JAR-bestand.

Nadat u AEM hebt geïnstalleerd, toegang tot de ontwikkelomgeving van de CRXDE Lite door de verbinding van de CRXDE Lite op de Welkome pagina te klikken:

![chlimage_1-100](assets/chlimage_1-100.png)

>[!NOTE]
>
>De URL van CRXDE Lite voor een AEM ontwerpinstantie die lokaal wordt geïnstalleerd met de standaardpoort, is [http://localhost:4502/crx/de/](http://localhost:4502/crx/de/).

## De projectstructuur instellen in CRXDE Lite {#setting-up-the-project-structure-in-crxde-lite}

Gebruik CRXDE Lite om de structuur van de mywebsite-toepassing in de opslagplaats te maken:

1. Klik in de structuur links van CRXDE Lite met de rechtermuisknop op de map **`/apps`** en klik op **[!UICONTROL Create > Create Folder]**. Typ `mywebsite` als mapnaam in het dialoogvenster **Map maken** en klik op **OK**.
1. Klik met de rechtermuisknop op de map `/apps/mywebsite` en klik op **[!UICONTROL Create > Create Folder]**. Typ `components` als mapnaam in het dialoogvenster **[!UICONTROL Create Folder]** en klik op **[!UICONTROL OK]**.
1. Klik met de rechtermuisknop op de map `/apps/mywebsite` en klik op **[!UICONTROL Create > Create Folder]**. Typ `templates` als mapnaam in het dialoogvenster **[!UICONTROL Create Folder]** en klik op **[!UICONTROL OK]**.

   De structuur in de boom moet er nu ongeveer als volgt uitzien:

   ![chlimage_1-101](assets/chlimage_1-101.png)

1. Klik op **[!UICONTROL Save All]**.

## Het ontwerp instellen {#setting-up-the-design}

In deze sectie maakt u het ontwerp voor uw toepassing met het gereedschap Designer. Het ontwerp biedt CSS- en afbeeldingsbronnen voor uw website.

>[!NOTE]
>
>Klik op de volgende koppeling om ``mywebsite.zip`` te downloaden. Het archief bevat de bestanden static.css en image voor uw ontwerp.

Voorbeeld van bestand static.css en afbeeldingen

[Bestand ophalen](assets/mywebsite.zip)

1. Voor de AEM Welkome pagina, klik **[!UICONTROL Tools]**. ([http://localhost:4502/libs/cq/core/content/welcome.html](http://localhost:4502/libs/cq/core/content/welcome.html))

   ![chlimage_1-102](assets/chlimage_1-102.png)

1. Selecteer in de mappenstructuur de map **[!UICONTROL Designs]** en klik op **[!UICONTROL New > New Page]**. Typ `mywebsite` als de titel en klik **[!UICONTROL Create]**.

1. Als het mijnwebsite-item niet in de tabel wordt weergegeven, vernieuwt u de structuur of de tabel.

1. [Kopieer het voorbeeldbestand en de ](/help/sites-administering/webdav-access.md) map vanuit het gedownloade bestand mywebsite.zip naar de  `static.css`   `images`   `/etc/designs/mywebsite` map met WebDAV-toegang naar de URL op http://localhost:4502.

   ![chlimage_1-103](assets/chlimage_1-103.png)

## Sjabloon, component en script voor inhoudspagina maken {#creating-the-contentpage-template-component-and-script}

In deze sectie maakt u het volgende:

* De sjabloon voor de inhoudspagina die wordt gebruikt om inhoudspagina&#39;s te maken in de voorbeeldwebsite
* De component contentPage die wordt gebruikt om pagina&#39;s met inhoud te renderen
* Het script contentPage

### Sjabloon voor inhoudspagina {#creating-the-contentpage-template} maken

Maak een sjabloon die u als basis voor de webpagina&#39;s van uw site wilt gebruiken.

Een sjabloon definieert de standaardinhoud van een nieuwe pagina. Complexe websites kunnen verschillende sjablonen gebruiken om de verschillende typen pagina&#39;s op de site te maken. In deze exercitie, zijn alle pagina&#39;s gebaseerd op één eenvoudig malplaatje.

1. Klik in de mappenstructuur van CRXDE Lite met de rechtermuisknop op `/apps/mywebsite/templates` en klik op **[!UICONTROL Create > Create Template]**.

1. Typ de volgende waarden in het dialoogvenster Sjabloon maken en klik op **[!UICONTROL Next]**:

   * **[!UICONTROL Label]**: contentpagina
   * **[!UICONTROL Title]**: Sjabloon voor pagina met inhoud van mijn website
   * **[!UICONTROL Description]**: Dit is mijn pagina-sjabloon voor website-inhoud
   * **[!UICONTROL Resource Type]**: mywebsite/componenten/contentPage

   Gebruik de standaardwaarde voor het Rangschikken bezit.

   ![chlimage_1-104](assets/chlimage_1-104.png)

   Het middeltype identificeert de component die de pagina teruggeeft. In dit geval worden alle pagina&#39;s die zijn gemaakt met de sjabloon contentPage weergegeven door de component `mywebsite/components/contentpage`.

1. Als u de paden wilt opgeven van de pagina&#39;s waarop deze sjabloon kan worden gebruikt, klikt u op de plusknop en typt u `/content(/.*)?` in het tekstvak dat wordt weergegeven. Klik vervolgens op **[!UICONTROL Next]**.

   ![chlimage_1-105](assets/chlimage_1-105.png)

   De waarde van de toegestane padeigenschap is een *reguliere expressie.* Pagina&#39;s die een pad hebben dat overeenkomt met de expressie, kunnen de sjabloon gebruiken. In dit geval komt de reguliere expressie overeen met het pad van de map `/content` en alle subpagina&#39;s.

   Wanneer een auteur een pagina onder `/content` creeert, verschijnt **[!UICONTROL contentpage]** malplaatje in een lijst van beschikbare malplaatjes aan gebruik.

1. Klik **[!UICONTROL Next]** in **[!UICONTROL Allowed Parents]** en **[!UICONTROL Allowed Children]** panelen en klik **[!UICONTROL OK]**. Klik in CRXDE Lite op **[!UICONTROL Save All]**.

   ![chlimage_1-105](assets/chlimage_1-106.png)

#### De component ContentPage {#creating-the-contentpage-component} maken

Creeer *component* die de inhoud bepaalt en de pagina&#39;s teruggeeft die het malplaatje van de inhoudspagina gebruiken. De plaats van de component moet met de waarde van het bezit van het Type van Middel van het contentpage malplaatje beantwoorden.

1. Klik in CRXDE Lite met de rechtermuisknop op `/apps/mywebsite/components` en klik op **[!UICONTROL Create > Component]**.
1. Typ in het dialoogvenster **[!UICONTROL Create Component]** de volgende eigenschapswaarden:

   * **[!UICONTROL Label]**: contentpagina
   * **[!UICONTROL Title]**: Inhoud pagina Mijn website
   * **[!UICONTROL Description]**: Dit is de inhoud van mijn website

   ![chlimage_1-107](assets/chlimage_1-107.png)

   De locatie van de nieuwe component is `/apps/mywebsite/components/contentpage`. Dit pad komt overeen met het middeltype van de sjabloon voor de inhoudspagina (min het oorspronkelijke `/apps/`-gedeelte van het pad).

   Deze correspondentie verbindt het malplaatje met de component en is kritiek aan het correcte functioneren van de website.

1. Klik **[!UICONTROL Next]** tot het **[!UICONTROL Allowed Children]** paneel van de dialoog verschijnt, en dan **[!UICONTROL OK]** klikken. Klik in CRXDE Lite op **[!UICONTROL Save All]**.

   De structuur ziet er nu als volgt uit:

   ![chlimage_1-108](assets/chlimage_1-108.png)

#### Het script voor de component ContentPage {#developing-the-contentpage-component-script} ontwikkelen

Voeg code toe aan het script contentPage.jsp om de pagina-inhoud te definiëren.

1. Open in CRXDE Lite het bestand `contentpage.jsp` in `/apps/mywebsite/components/contentpage`. Het bestand bevat standaard de volgende code:

   ```java
   <%--
   
     My Website Content Page Component component.
   
     This is My Website Content Page Component.
   
   --%><%
   %><%@include file="/libs/foundation/global.jsp"%><%
   %><%@page session="false" %><%
   %><%
       /* TODO add you code here */
   %>
   ```

1. Kopieer de volgende code en plak deze in contentPage.jsp na de standaardcode:

   ```java
   <%@ page language="java" contentType="text/html; charset=ISO-8859-1"
       pageEncoding="ISO-8859-1"%>
   <!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" 
   "https://www.w3.org/TR/html4/loose.dtd">
   <html>
   <head>
   <meta http-equiv="Content-Type" content="text/html; charset=ISO-8859-1">
   <title>My title</title>
   </head>
   <body>
   <div>My body</div>
   </body>
   </html>
   ```

1. Klik **[!UICONTROL Save All]** om uw veranderingen te bewaren.

### Websitepagina&#39;s en inhoudspagina&#39;s maken {#creating-your-website-page-and-content-pages}

In deze sectie maakt u de volgende pagina&#39;s die allemaal de sjabloon voor de inhoudspagina gebruiken: Mijn Website, Engels, Producten, de Diensten, en Klanten.

1. Voor de AEM Welkome pagina ([http://localhost:4502/libs/cq/core/content/welcome.html](http://localhost:4502/libs/cq/core/content/welcome.html)), klik Websites.

   ![chlimage_1-189](assets/chlimage_1-109.png)

1. Selecteer in de mappenstructuur de map **[!UICONTROL Websites]** en klik op **[!UICONTROL New > New Page]**.
1. Voer in het venster **[!UICONTROL Create Page]** het volgende in:

   * **[!UICONTROL Title]**: `My Website`
   * **[!UICONTROL Name]**:  `mywebsite`
   * Selecteer **[!UICONTROL My Website Content Page Template]**

   ![chlimage_1-110](assets/chlimage_1-110.png)

1. Klik op **[!UICONTROL Create]**. Selecteer de pagina `/Websites/My Website` in de mappenstructuur en klik op **[!UICONTROL New > New Page]**.
1. Voer in het dialoogvenster **[!UICONTROL Create Page]** de volgende eigenschapswaarden in en klik op Maken:

   * **[!UICONTROL Title]**: Engels
   * **[!UICONTROL Name]**: en
   * Selecteer **[!UICONTROL My Website Content Page Template]**

1. Selecteer de pagina `/Websites/My Website/English` in de mappenstructuur en klik op **[!UICONTROL New > New Page]**.
1. Voer in het dialoogvenster **[!UICONTROL Create Page]** de volgende eigenschapswaarden in en klik op **[!UICONTROL Create]**:

   * **[!UICONTROL Title]**: Producten
   * Selecteer **[!UICONTROL My Website Content Page Template]**

1. Selecteer de pagina `/Websites/My Website/English` in de mappenstructuur en klik op **[!UICONTROL New > New Page]**.
1. Voer in het dialoogvenster **[!UICONTROL Create Page]** de volgende eigenschapswaarden in en klik op **[!UICONTROL Create]**:

   * **Titel**: Services
   * Selecteer **[!UICONTROL My Website Content Page Template]**

1. Selecteer de pagina `/Websites/My Website/English` in de mappenstructuur en klik op **[!UICONTROL New > New Page]**.
1. Voer in het dialoogvenster **[!UICONTROL Create Page]** de volgende eigenschapswaarden in en klik op **[!UICONTROL Create]**:

   * **Titel**: Klanten
   * Selecteer **[!UICONTROL My Website Content Page Template]**

   Uw structuur ziet er als volgt uit:

   ![chlimage_1-191](assets/chlimage_1-111.png)

1. Als u uw pagina&#39;s wilt koppelen aan het ontwerp van mijn website, selecteert u in CRXDE Lite het knooppunt `/content/mywebsite/en/jcr:content`. Typ op het tabblad **[!UICONTROL Properties]** de volgende waarden voor een nieuwe eigenschap en klik vervolgens op Toevoegen:

   * **[!UICONTROL Name]**: cq:designPath
   * **[!UICONTROL Type]**: Tekenreeks
   * **[!UICONTROL Value]**: /etc/designs/mywebsite

   ![chlimage_1-112](assets/chlimage_1-112.png)

1. Open [http://localhost:4502/content/mywebsite/en/products.html](http://localhost:4502/content/mywebsite/en/products.html) in een nieuw webbrowsertabblad of -venster om de pagina Producten weer te geven:

   ![chlimage_1-113](assets/chlimage_1-113.png)

### Het script voor de inhoudspagina {#enhancing-the-contentpage-script} verbeteren

In deze sectie wordt beschreven hoe u het script voor de inhoudspagina kunt verbeteren met behulp van de scripts van de AEM basis en door uw eigen scripts te schrijven.

De pagina **[!UICONTROL Products]** ziet er als volgt uit:

![chlimage_1-4](assets/chlimage_1-4.jpeg)

#### Het gebruiken van de Manuscripten van de Pagina van de Stichting {#using-the-foundation-page-scripts}

In deze oefening, vormt u uw paginaContent component zodat zijn supertype de AEM component van de Pagina is. Omdat componenten de eigenschappen van hun supertype erven, erft uw pagina-inhoud de scripts en eigenschappen van de component Pagina.

In uw JSP-code van de component kunt u bijvoorbeeld naar de scripts verwijzen die de supertype-component biedt, alsof deze in de component zijn opgenomen.

1. Voeg in CRXDE Lite een eigenschap toe aan het knooppunt `/apps/mywebsite/components/contentpage`.

   1. Selecteer de `/apps/mywebsite/components/contentpage` knoop.
   1. Typ onder aan het tabblad Eigenschappen de volgende eigenschapswaarden en klik op Toevoegen:

      * **[!UICONTROL Name]**: sling:resourceSuperType
      * **[!UICONTROL Type]**: Tekenreeks
      * **[!UICONTROL Value]**: basis/componenten/pagina
   1. Klik op **[!UICONTROL Save All]**.


1. Open het `contentpage.jsp`-bestand onder `/apps/mywebsite/components/contentpage` en vervang de bestaande code door de volgende code:

   ```xml
   <%@include file="/libs/foundation/global.jsp"%><%
   %><%@page session="false" contentType="text/html; charset=utf-8" %><%
   %><!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "https://www.w3.org/TR/html4/strict.dtd">
   <html>
   <cq:include script="head.jsp"/>
   <cq:include script="body.jsp"/>
   </html>
   ```

1. Sla uw wijzigingen op.
1. Laad de pagina **[!UICONTROL Products]** in uw browser opnieuw. Het ziet er als volgt uit:

   ![chlimage_1-5](assets/chlimage_1-5.jpeg)

   Open de paginabron om de elementen javascript en HTML te zien die de manuscripten head.jsp en body.jsp produceerden. Het volgende scriptfragment opent Sidetrap wanneer u de pagina opent:

   ```java
   CQ.WCM.launchSidekick("/content/mywebsite/en/products",
               {propsDialog: "/libs/foundation/components/page/dialog",
                  locked: false locked: false
                }); 
   ```

#### Uw eigen scripts gebruiken {#using-your-own-scripts}

In deze sectie maakt u verschillende scripts die elk een deel van de hoofdtekst van de pagina genereren. Vervolgens maakt u het bestand body.jsp in de component pageContent om het body.jsp van de component AEM Page te overschrijven. In uw body.jsp- dossier, omvat u uw manuscripten die de verschillende delen van de paginakleurtekst produceren.

**Tip:** Wanneer een component een bestand bevat dat dezelfde naam en relatieve locatie heeft als een bestand in het supertype van de component, wordt dit  *bedekken* genoemd.

1. Maak in CRXDE Lite het bestand `left.jsp` onder `/apps/mywebsite/components/contentpage`:

   1. Klik met de rechtermuisknop op het knooppunt `/apps/mywebsite/components/contentpage` en selecteer **[!UICONTROL Create]** en **[!UICONTROL Create File]**.
   1. Typ `left.jsp` in het venster als de *** naam* en klik op **[!UICONTROL OK]**.

1. Bewerk het bestand `left.jsp` om de bestaande inhoud te verwijderen en te vervangen door de volgende code:

   ```java
   <%@include file="/libs/foundation/global.jsp"%><%
   %><div class="left">
   <div>logo</div>
   <div>newslist</div>
   <div>search</div>
   </div>
   ```

1. Sla de wijzigingen op.
1. Maak in CRXDE Lite het bestand `center.jsp` onder `/apps/mywebsite/components/contentpage`:

   1. Klik met de rechtermuisknop op het knooppunt `/apps/mywebsite/components/contentpage`, selecteer **[!UICONTROL Create]** en **[!UICONTROL Create File]**.
   1. Typ `center.jsp` als **[!UICONTROL Name]** in het dialoogvenster en klik op **[!UICONTROL OK]**.

1. Bewerk het bestand `center.jsp` om de bestaande inhoud te verwijderen en vervang het door de volgende code:

   ```java
   <%@include file="/libs/foundation/global.jsp"%><%
   %><div class="center">
   <div>trail</div>
   <div>title</div>
   <div>parsys</div>
   </div>
   ```

1. Sla de wijzigingen op.
1. Maak in CRXDE Lite het bestand `right.jsp` onder `/apps/mywebsite/components/contentpage`:

   1. Klik met de rechtermuisknop op het knooppunt `/apps/mywebsite/components/contentpage`, selecteer **[!UICONTROL Create]** en **[!UICONTROL Create File]**.
   1. Typ `right.jsp` als **[!UICONTROL Name]** in het dialoogvenster en klik op **[!UICONTROL OK]**.

1. Bewerk het bestand `right.jsp` om de bestaande inhoud te verwijderen en te vervangen door de volgende code:

   ```java
   <%@include file="/libs/foundation/global.jsp"%><%
   %><div class="right">
   <div>iparsys</div>
   </div>
   ```

1. Sla de wijzigingen op.
1. Maak in CRXDE Lite het bestand `body.jsp` onder `/apps/mywebsite/components/contentpage`:
1. Bewerk het bestand `body.jsp` om de bestaande inhoud te verwijderen en te vervangen door de volgende code:

   ```java
   <%@include file="/libs/foundation/global.jsp"%><%
   %><body>
   <div id="CQ">
   <div class="topnav">topnav</div>
   <div class="content">
   <cq:include script="left.jsp" />
   <cq:include script="center.jsp" />
   <cq:include script="right.jsp" />
   </div>
   <div class="footer">
   <div class="toolbar">toolbar</div>
   </div>
   </div>
   </body>
   ```

1. Sla de wijzigingen op.
1. Laad de pagina **[!UICONTROL Products]** in uw browser opnieuw. Het ziet er als volgt uit:

   ![chlimage_1-6](assets/chlimage_1-6.jpeg)

### De bovenste navigatiecomponent {#creating-the-top-navigation-component} maken

In deze sectie maakt u een component die koppelingen naar alle pagina&#39;s op hoofdniveau van de website weergeeft om de navigatie te vereenvoudigen. Deze componentinhoud wordt boven aan alle pagina&#39;s weergegeven die zijn gemaakt met de sjabloon voor de inhoudspagina.

In de eerste versie van de bovenste navigatiecomponent (boven) zijn de navigatie-items alleen tekstkoppelingen. In de tweede versie implementeert u bovenaan met koppelingen voor afbeeldingsnavigatie.

Uw topnavigatie ziet er als volgt uit:

![chlimage_1-115](assets/chlimage_1-114.png)

#### De bovenste navigatiecomponent {#creating-the-top-navigation-component-1} maken

1. Klik in CRXDE Lite met de rechtermuisknop op `/apps/mywebsite/components`, selecteer **[!UICONTROL Create]** en **[!UICONTROL Create Component]**.
1. Voer in het venster **[!UICONTROL Create Component]** het volgende in:

   * **[!UICONTROL Label]**:  `topnav`
   * **[!UICONTROL Title]**:  `My Top Navigation Component`
   * **[!UICONTROL Description]**:  `This is My Top Navigation Component`

1. Klik **[!UICONTROL Next]** tot u aan het laatste venster komt waar u **[!UICONTROL OK]** klikt. Sla uw wijzigingen op.

#### Het bovenste navigatiescript maken met tekstkoppelingen {#creating-the-top-navigation-script-with-textual-links}

Voeg het renderscript toe aan bovenliggend item om tekstkoppelingen naar onderliggende pagina&#39;s te genereren:

1. Open in CRXDE Lite het bestand `topnav.jsp` onder `/apps/mywebsite/components/topnav`.
1. Vervang de desbetreffende code door de volgende code te kopiëren en te plakken:

   ```xml
   <%@include file="/libs/foundation/global.jsp"%><% 
   %><%@ page import="java.util.Iterator,
           com.day.text.Text, 
           com.day.cq.wcm.api.PageFilter, com.day.cq.wcm.api.Page" %><% 
       /* get starting point of navigation */
       Page navRootPage = currentPage.getAbsoluteParent(2); 
       if (navRootPage == null && currentPage != null) { 
       navRootPage = currentPage; 
       }
       if (navRootPage != null) { 
           Iterator<Page> children = navRootPage.listChildren(new PageFilter(request));
           while (children.hasNext()) { 
               Page child = children.next(); 
               %><a href="<%= child.getPath() %>.html"><%=child.getTitle() %></a><% 
           } 
       } 
   %> 
   ```

#### De bovenste navigatie opnemen in de component ContentPage {#including-top-navigation-in-the-contentpage-component}

Het onderwerp opnemen in de component ContentPage:

1. Open in CRXDE Lite de `body.jsp` onder `/apps/mywebsite/components/contentpage`en vervang:

   ```xml
   <div class="topnav">topnav</div>
   ```

   met:

   ```xml
   <cq:include path="topnav" resourceType="mywebsite/components/topnav" />
   ```

1. Sla de wijzigingen op.
1. Laad de pagina **[!UICONTROL Products]** in uw browser opnieuw. De bovenste navigatie ziet er als volgt uit:

   ![chlimage_1-114](assets/chlimage_1-115.png)

#### Pagina&#39;s verbeteren met ondertitels {#enhancing-pages-with-subtitles}

De component **[!UICONTROL Page]** definieert eigenschappen waarmee u ondertitels voor pagina&#39;s kunt opgeven. Voeg ondertitels toe die informatie over de pagina-inhoud bevatten.

1. Open de pagina **[!UICONTROL Products]** in uw browser.
1. Klik op **[!UICONTROL Page Properties]** op het tabblad Sidetrap.**[!UICONTROL Page]**
1. Vouw op het tabblad **[!UICONTROL Basic]** van het dialoogvenster **[!UICONTROL More Titles and Description]** uit en typ `what we do` voor de eigenschap **[!UICONTROL Subtitle]**. Klik op **[!UICONTROL OK]**.
1. Herhaal de vorige stappen om de ondertitel **over onze services** toe te voegen aan de pagina **[!UICONTROL Services]**.
1. Herhaal de vorige stappen om de ondertitel **het vertrouwen toe te voegen wij** aan **[!UICONTROL Customers]** pagina verdienen.

   **Tip:** Selecteer in CRXDE Lite het knooppunt /content/mywebsite/nl/products/jcr:content om te controleren of de eigenschap subtitle is toegevoegd.

#### Bovenste navigatie verbeteren door afbeeldingskoppelingen te gebruiken {#enhance-top-navigation-by-using-image-links}

Verbeter het teruggevende manuscript van de hoogste component om beeldverbindingen in plaats van hypertext voor de navigatiecontroles te gebruiken. De afbeelding bevat de titel en de ondertitel van het doel van de koppeling.

Deze oefening toont [Het verkopen verzoekverwerking](/help/sites-developing/the-basics.md#sling-request-processing) aan. Het script topnav.jsp wordt gewijzigd om een script aan te roepen waarmee dynamisch afbeeldingen worden gegenereerd die voor de paginanavigatiekoppelingen kunnen worden gebruikt. Bij deze exercitie wordt met Sling de URL van afbeeldingsbronbestanden geparseerd om te bepalen welk script moet worden gebruikt om de afbeeldingen te renderen.

De bron voor de afbeeldingskoppeling naar de pagina Producten kan bijvoorbeeld http://localhost:4502/content/mywebsite/en/products.navimage.png zijn. Sling ontleedt dit URL om het middeltype en het manuscript te bepalen om het middel terug te geven:

1. Sling bepaalt het pad van de bron die `/content/mwebysite/en/products.png.` moet worden
1. De verkoop past dit weg met de `/content/mywebsite/en/products` knoop aan.
1. Sling bepaalt `sling:resourceType` van deze knoop om `mywebsite/components/contentpage` te zijn.

1. Bij Sling wordt het script in deze component gevonden dat het meest overeenkomt met de URL-kiezer ( `navimage`) en de bestandsextensie ( `png`).

In deze oefening, past het Sling deze URLs aan het manuscript /apps/mywebsite/components/contentpage/navimage.png.java aan dat u creeert.

1. Open in CRXDE Lite de `topnav.jsp` onder `/apps/mywebsite/components/topnav.`De inhoud van het ankerelement zoeken (regel 14):

   ```xml
   <%=child.getTitle() %>
   ```

1. Vervang de ankerinhoud door de volgende code:

   ```xml
   <img alt="<%= child.getTitle() %>" src="<%= child.getPath() %>.navimage.png">
   ```

1. Sla de wijzigingen op.
1. Klik met de rechtermuisknop op het knooppunt `/apps/mywebsite/components/contentpage` en klik op **[!UICONTROL Create > Create File]**.
1. Typ `navimage.png.java` in het venster **[!UICONTROL Create File]** als **[!UICONTROL Name]**.

   De .java-bestandsnaamextensie geeft aan Sling aan dat de Apache Sling Scripting Java Support moet worden gebruikt om het script te compileren en een servlet te maken.

1. Kopieer de volgende code naar `navimage.png.java.`De code breidt de klasse AbstractImageServlet uit:

   * [](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/wcm/commons/AbstractImageServlet.html) AbstractImageServletcreate een voorwerp ImageContext dat de eigenschappen van het huidige middel opslaat.
   * De bovenliggende pagina van de bron wordt geëxtraheerd uit het ImageContext-object. De paginatitel en -ondertitel worden vervolgens opgehaald.
   * [Met ](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/commons/ImageHelper.html) ImageHelperis kunt u de afbeelding genereren op basis van het bestand navimage_bg.jpg van het siteontwerp, de paginatitel en de ondertitel van de pagina.

   ```java
   package apps.mywebsite.components.contentpage;
   
   import java.awt.Color; 
   import java.awt.Paint; 
   import java.awt.geom.Rectangle2D; 
   
   import java.io.IOException;
   import javax.jcr.RepositoryException; 
   
   import com.day.cq.wcm.api.Page; 
   import com.day.cq.wcm.api.PageManager; 
   import com.day.cq.wcm.api.components.Component; 
   import com.day.cq.wcm.api.designer.Designer;
   
   import com.day.cq.commons.SlingRepositoryException; 
   import com.day.cq.wcm.commons.WCMUtils; 
   import com.day.cq.wcm.commons.AbstractImageServlet; 
   import com.day.cq.commons.ImageHelper; 
   
   import com.day.image.Font; 
   import com.day.image.Layer; 
   
   import org.apache.sling.api.SlingHttpServletRequest; 
   import org.apache.sling.api.SlingHttpServletResponse; 
   import org.apache.sling.api.resource.Resource; 
   import org.apache.sling.api.servlets.SlingSafeMethodsServlet; 
   
   /**
     * Renders the navigation image
     */ 
   public class navimage_png extends AbstractImageServlet {
   
         protected Layer createLayer(ImageContext ctx)
                throws RepositoryException, IOException {
            PageManager pageManager = ctx.resolver.adaptTo(PageManager.class);
            Page currentPage = pageManager.getContainingPage(ctx.resource);
   
            /* constants for image appearance */
            int scale = 6;
            int paddingX = 24;
            int paddingY = 24;
            Color bgColor = new Color(0x004a565c, true);
   
            /* obtain the page title */
            String title = currentPage.getTitle();
            if (title == null) {
                title = currentPage.getName();
            }
   
            /* format the title text */
            title = title.toUpperCase();
            Paint titleColor = Color.WHITE;
            Font titleFont = new Font("Myriad Pro", 10 * scale, Font.BOLD);
            int titleBase = 10 * scale;
   
            /* obtain and format the page subtitle */
            String subtitle = currentPage.getProperties().get("subtitle", "");
            Paint subtitleColor = new Color(0xffa9afb1, true);
            Font subTitleFont = new Font("Tahoma", 7);
            int subTitleBase = 20;
   
            /* create a layer that contains the background image from the mywebsite design */
            Designer dg = ctx.resolver.adaptTo(Designer.class);
            String imgPath = new String(dg.getDesignPath(currentPage)+"/images/navimage_bg.jpg");
            Layer bg = ImageHelper.createLayer(ctx.resolver.resolve(imgPath));
   
            /* draw the title text (4 times bigger) */
            Rectangle2D titleExtent = titleFont.getTextExtent(0, 0, 0, 0, title, Font.ALIGN_LEFT, 0, 0);
            Rectangle2D subtitleExtent = subTitleFont.getTextExtent(0, 0, 0, 0, subtitle, Font.ALIGN_LEFT, 0, 0);
   
            /* ensure subtitleExtent is wide enough */
            if ( subtitle.length() > 0 ) {
                int titleWidth = (int)titleExtent.getWidth() / scale;
                if ( subtitleExtent.getWidth() > titleWidth && subtitleExtent.getWidth() + 2 * paddingX >
    bg.getWidth() ) {
                    int charWidth = (int)subtitleExtent.getWidth() / subtitle.length();
                    int maxWidth = (bg.getWidth() > titleWidth + 2  * paddingX ? bg.getWidth() - 2 * paddingX : titleWidth);
                    int len = (maxWidth - ( 2 * charWidth) ) / charWidth;
                    subtitle = subtitle.substring(0, len) + "...";
                    subtitleExtent = subTitleFont.getTextExtent(0, 0, 0, 0, subtitle, Font.ALIGN_LEFT, 0, 0);
                }
            }
            int width = Math.max((int) titleExtent.getWidth(), (int) subtitleExtent.getWidth());
           /* create the text layer */
            Layer text = new Layer(width, (int) titleExtent.getHeight() + 40, new Color(0x01ffffff, true));
            text.setPaint(titleColor);
            text.drawText(0, titleBase, 0, 0, title, titleFont, Font.ALIGN_LEFT | Font.ALIGN_BASE, 0, 0);
            text.resize(text.getWidth() / scale, text.getHeight() / scale);
            text.setX(0);
            text.setY(0);
   
            if (subtitle.length() > 0) {
                /* draw the subtitle normal sized */
                text.setPaint(subtitleColor);
                text.drawText(0, subTitleBase, 0, 0, subtitle, subTitleFont, Font.ALIGN_LEFT | Font.ALIGN_BASE, 0, 0); 
            }
   
            /* merge the image and text layers */
            text.setY(paddingY);
            text.setX(paddingX);
            text.setBackgroundColor(bgColor);
   
            int bgWidth = bg.getWidth();
            if ( text.getWidth() + 2 * paddingX > bgWidth ) {
                bgWidth = text.getWidth() + 2 * paddingX;
                bg.resize(bgWidth, bg.getHeight());
            }
            bg.merge(text);
   
            return bg;
        }
    }
   ```

1. Sla de wijzigingen op.
1. Laad de pagina **[!UICONTROL Products]** in uw browser opnieuw. De bovenste navigatie ziet er nu als volgt uit:

   ![screen_shot_2012-03-07at10047pm](assets/screen_shot_2012-03-07at10047pm.png)

### De component List Children {#creating-the-list-children-component} maken

Maak de component listchildren die een lijst met paginakoppelingen genereert die de titel, beschrijving en datum van pagina&#39;s bevatten (bijvoorbeeld productpagina&#39;s). De koppelingen zijn gericht op de onderliggende pagina&#39;s van de huidige pagina of van een basispagina die is opgegeven in het dialoogvenster van de component.

![chlimage_1-116](assets/chlimage_1-116.png)

#### Productpagina&#39;s maken {#creating-product-pages}

Maak twee pagina&#39;s onder de pagina **[!UICONTROL Products]**. Voor elke pagina, die twee specifieke producten beschrijft, plaatst u een titel, een beschrijving, en een datum.

1. Selecteer in de mappenstructuur van de pagina **[!UICONTROL Websites]** het item **[!UICONTROL Websites/My Website/English/Products]** en klik op **[!UICONTROL New > New Page]**.
1. Voer in het dialoogvenster de volgende eigenschapswaarden in en klik op **[!UICONTROL Create]**:

   * **[!UICONTROL Title]**: Product 1.
   * **[!UICONTROL Name]**: product1.
   * Selecteer **[!UICONTROL My Website Content Page Template]**

1. Maak een andere pagina onder Producten met de volgende eigenschapswaarden:

   * **[!UICONTROL Title]**: Product 2
   * **[!UICONTROL Name]**: product2
   * Selecteer **[!UICONTROL My Website Content Page Template]**

1. Stel in CRXDE Lite een beschrijving en een datum in voor de pagina Product 1:

   1. Selecteer de `/content/mywebsite/en/products/product1/jcr:content` knoop.
   1. Voer op het tabblad **[!UICONTROL Properties]** de volgende waarden in:

      * **[!UICONTROL Name]**:  `jcr:description`
      * **[!UICONTROL Type]**:  `String`
      * **[!UICONTROL Value]**:  `This is a description of the Product 1!.`
   1. Klik op **[!UICONTROL Add]**.
   1. Maak op het tabblad **[!UICONTROL Properties]** een andere eigenschap met de volgende waarden:

      * **[!UICONTROL Name]**: date
      * **[!UICONTROL Type]**: Tekenreeks
      * **[!UICONTROL Value]**: 14-02-2008
      * Klik op **[!UICONTROL Add]**.
   1. Klik op **[!UICONTROL Save All]**.



1. Stel in CRXDE Lite een beschrijving en een datum in voor de pagina Product 2:

   1. Selecteer de `/content/mywebsite/en/products/product2/jcr:content` knoop.
   1. Voer op het tabblad **[!UICONTROL Properties]** de volgende waarden in:

      * **[!UICONTROL Name]**: jcr:beschrijving
      * **[!UICONTROL Type]**: Tekenreeks
      * **[!UICONTROL Value]**: Dit is een beschrijving van Product 2!
   1. Klik op **[!UICONTROL Add]**.
   1. Vervang in dezelfde tekstvakken de vorige waarden door de volgende waarden:

      * **[!UICONTROL Name]**: date
      * **[!UICONTROL Type]**: Tekenreeks
      * **[!UICONTROL Value]**: 11-05-2012
      * Klik op **[!UICONTROL Add]**.
   1. Klik op **[!UICONTROL Save All]**.



#### De component List Children {#creating-the-list-children-component-1} maken

De component listchildren maken:

1. Klik in CRXDE Lite met de rechtermuisknop op `/apps/mywebsite/components`, selecteer **[!UICONTROL Create]** en **[!UICONTROL Create Component]**.
1. Voer in het dialoogvenster de volgende eigenschapswaarden in en klik op **[!UICONTROL Next]**:

   * **[!UICONTROL Label]**: listchildren.
   * **[!UICONTROL Title]**: Mijn component Listchildren.
   * **[!UICONTROL Description]**: Dit is de component My Listchildren.

1. Klik op **[!UICONTROL Next]** totdat het deelvenster **[!UICONTROL Allowed Children]** wordt weergegeven en klik op **[!UICONTROL OK]**.

#### Het creëren van het Manuscript van de Kinderen van de Lijst {#creating-the-list-children-script}

Ontwikkel het manuscript voor de component listchildren.

1. Open in CRXDE Lite het bestand `listchildren.jsp` onder `/apps/mywebsite/components/listchildren`.
1. Vervang de standaardcode door de volgende code:

   ```xml
   <%@include file="/libs/foundation/global.jsp"%><%
   %><%@ page import="java.util.Iterator,
            com.day.cq.wcm.api.PageFilter"%><%
        /* Create a new Page object using the path of the current page */ 
         String listroot = properties.get("listroot", currentPage.getPath());
        Page rootPage = pageManager.getPage(listroot);
        /* iterate through the child pages and gather properties */
        if (rootPage != null) {
            Iterator<Page> children = rootPage.listChildren(new PageFilter(request));
            while (children.hasNext()) {
                Page child = children.next();
                String title = child.getTitle() == null ? child.getName() : child.getTitle();
                String date = child.getProperties().get("date","");
                %><div class="item">
                <a href="<%= child.getPath() %>.html"><b><%= title %></b></a>
                <span><%= date %></span><br>
                <%= child.getProperties().get("jcr:description","") %><br>
                </div><%
            }
        }
    %>
   ```

1. Sla de wijzigingen op.

#### Het creëren van de Dialoogvenster van de Kinderen van de Lijst {#creating-the-list-children-dialog}

Creeer de dialoog die wordt gebruikt om de eigenschappen van de component listchildren te vormen.

1. Maak het dialoogknooppunt onder de component listchildren:

   1. Klik in CRXDE Lite met de rechtermuisknop op het knooppunt `/apps/mywebsite/components/listchildren`en klik op **[!UICONTROL Create > Create Dialog]**.
   1. Voer in het dialoogvenster de volgende eigenschapswaarden in en klik op OK

      * **[!UICONTROL Label]**:  `dialog`
      * **[!UICONTROL Title]**:  `Edit Component` en klik  **[!UICONTROL OK]**.

   ![screen_shot_2012-03-07at45818pm](assets/screen_shot_2012-03-07at45818pm.png)

   Met de volgende eigenschappen:

   ![screen_shot_2012-03-07at50415pm](assets/screen_shot_2012-03-07at50415pm.png)

1. Selecteer de `/apps/mywebsite/components/listchildren/dialog/items/items/tab1` knoop.
1. Wijzig op het tabblad **[!UICONTROL Properties]** de waarde van de eigenschap **[!UICONTROL title]** in `List Children`

   ![chlimage_1-117](assets/chlimage_1-117.png)

1. Selecteer de **tab1** knoop en klik **[!UICONTROL Create > Create Node]**, ga de volgende bezitswaarden in, en klik **[!UICONTROL OK]**:

   * **[!UICONTROL Name]**: items
   * **[!UICONTROL Type]**: cq:WidgetCollection

   ![screen_shot_2012-03-07at51018pm](assets/screen_shot_2012-03-07at51018pm.png)

1. Maak een knooppunt onder het knooppunt Items met de volgende eigenschapswaarden:

   * **[!UICONTROL Name]**: listroot
   * **[!UICONTROL Type]**: cq:Widget

   ![screen_shot_2012-03-07at51031pm](assets/screen_shot_2012-03-07at51031pm.png)

1. Voeg eigenschappen voor de listrootknoop toe om het als tekstgebied te vormen. Elke rij in de volgende tabel vertegenwoordigt een eigenschap. Wanneer gebeëindigd, klik **[!UICONTROL Save All]**.

   | Naam | Type | Waarde |
   |---|---|---|
   | fieldLabel | Tekenreeks | Pad van hoofdmap van lijst |
   | name | Tekenreeks | ./listroot |
   | xtype | Tekenreeks | textfield |

   ![screen_shot_2012-03-07at51433pm](assets/screen_shot_2012-03-07at51433pm.png)

#### Onderliggende items weergeven in de component ContentPage {#including-list-children-in-the-contentpage-component}

Ga als volgt te werk om de component listchildren in uw component contentPage op te nemen:

1. Open in CRXDE Lite het bestand `left.jsp` onder `/apps/mywebsite/components/contentpage` en zoek de volgende code (regel 4):

   ```xml
   <div>newslist</div>
   ```

1. Vervang die code door de volgende code:

   ```xml
   <cq:include path="newslist" resourceType="mywebsite/components/listchildren" />
   ```

1. Sla de wijzigingen op.

#### Onderliggende items weergeven op een pagina {#viewing-list-children-in-a-page}

Als u de volledige werking van deze component wilt zien, kunt u de pagina Producten weergeven:

* als de bovenliggende pagina (&quot;Pad van hoofdmap van lijst&quot;) niet is gedefinieerd.
* als de bovenliggende pagina (&quot;Pad van hoofdmap van lijst&quot;) is gedefinieerd.

1. Laad de pagina **[!UICONTROL Products]** in uw browser opnieuw. De component listchildren ziet er als volgt uit:

   ![chlimage_1-118](assets/chlimage_1-118.png)

1. ![chlimage_1-119](assets/chlimage_1-119.png)

1. Als pad van hoofdmap van lijst voert u in: `/content/mywebsite/en`. Klik op **[!UICONTROL OK]**. De component listchildren op de pagina ziet er nu als volgt uit:

   ![chlimage_1-120](assets/chlimage_1-120.png)

### De component Logo {#creating-the-logo-component} maken

Maak een component die het bedrijfslogo weergeeft en een koppeling naar de startpagina van de site bevat. De component bevat een dialoogvenster voor de ontwerpmodus, zodat de eigenschapswaarden worden opgeslagen in het siteontwerp (/etc/designs/mywebsite):

* De eigenschapswaarden zijn van toepassing op alle instanties van de component die worden toegevoegd aan pagina&#39;s die het ontwerp gebruiken.
* De eigenschappen kunnen worden gevormd gebruikend om het even welke instantie van de component die op een pagina is die het ontwerp gebruikt.

Het dialoogvenster voor de ontwerpmodus bevat eigenschappen voor het instellen van de afbeelding en het koppelingspad. De logocomponent wordt linksboven op alle pagina&#39;s op de website geplaatst.

Het ziet er als volgt uit:

![chlimage_1-121](assets/chlimage_1-121.png)

>[!NOTE]
>
>Adobe Experience Manager biedt een logo met meer volledige functionaliteit ( `/libs/foundation/components/logo`).

#### Het creëren van de Node van de Component van het Logo {#creating-the-logo-component-node}

Voer de volgende stappen uit om het logo-onderdeel te maken:

1. Klik in CRXDE Lite met de rechtermuisknop op /apps/mywebsite/components en selecteer **[!UICONTROL Create]** en **[!UICONTROL Create Component]**.
1. Voer in het dialoogvenster Component maken de volgende eigenschapswaarden in en klik op Volgende:

   * **[!UICONTROL Label]**: `logo`.
   * **[!UICONTROL Title]**:  `My Logo Component`.
   * **[!UICONTROL Description]**:  `This is My Logo Component`.

1. Klik op Volgende totdat u het laatste deelvenster van het dialoogvenster bereikt en klik op **[!UICONTROL OK]**.

#### Het creëren van het Manuscript van het Logo {#creating-the-logo-script}

In deze sectie wordt beschreven hoe u het script maakt om de logoafbeelding weer te geven met een koppeling naar de startpagina.

1. Open in CRXDE Lite het bestand `logo.jsp` onder `/apps/mywebsite/components/logo`.
1. De volgende code maakt de koppeling naar de homepage van de site en voegt een verwijzing naar de logoafbeelding toe. Kopieer de code naar `logo.jsp`:

   ```xml
   <%@include file="/libs/foundation/global.jsp"%><%
   %><%@ page import="com.day.text.Text,
                      com.day.cq.wcm.foundation.Image,
                      com.day.cq.commons.Doctype" %><%
       /* obtain the path for home */
       long absParent = currentStyle.get("absParent", 2L);
       String home = Text.getAbsoluteParent(currentPage.getPath(), (int) absParent);
       /* obtain the image */
       Resource res = currentStyle.getDefiningResource("imageReference");
       if (res == null) {
           res = currentStyle.getDefiningResource("image");
       }
       /* if no image use text link, otherwise draw the image */
       %>
   <a href="<%= home %>.html"><%
       if (res == null) {
           %>Home<%
       } else {
           Image img = new Image(res);
           img.setItemName(Image.NN_FILE, "image");
           img.setItemName(Image.PN_REFERENCE, "imageReference");
           img.setSelector("img");
           img.setDoctype(Doctype.fromRequest(request));
           img.setAlt("Home");
           img.draw(out);
       }
       %></a>
   ```

1. Sla de wijzigingen op.

#### Het maken van het Dialoogvenster van het Ontwerp van het Logo {#creating-the-logo-design-dialog}

Maak het dialoogvenster voor het configureren van de logocomponent in de ontwerpmodus. Dialoogvensterknooppunten in ontwerpmodus moeten de naam `design_dialog` hebben.

1. Maak het dialoogvenster onder de logocomponent:

   1. Klik met de rechtermuisknop op het knooppunt `/apps/mywebsite/components/logo` en klik op **[!UICONTROL Create > Create Dialog]**.
   1. Typ de volgende eigenschapswaarden en klik op **[!UICONTROL OK]**:

      * **[!UICONTROL Label]** `design_dialog`
      * **[!UICONTROL Title]** `Logo (Design)`

1. Klik met de rechtermuisknop op het knooppunt tab1 in de vertakking design_dialog en klik op Verwijderen. Klik op **[!UICONTROL Save All]**.
1. Maak onder het knooppunt `design_dialog/items/items`een nieuw knooppunt met de naam `img` van het type `cq:Widget`. Voeg de volgende eigenschappen toe en klik vervolgens op **[!UICONTROL Save All]**:

   | Naam | Type | Waarde |
   |---|---|---|
   | fileNameParameter | Tekenreeks | ./imageName |
   | fileReferenceParameter | Tekenreeks | ./imageReference |
   | name | Tekenreeks | ./afbeelding |
   | title | Tekenreeks | Afbeelding |
   | xtype | Tekenreeks | html5smartImage |

   ![chlimage_1-122](assets/chlimage_1-122.png)

#### Het logo-renderscript {#creating-the-logo-render-script} maken

Maak het script waarmee de logoafbeelding wordt opgehaald en naar de pagina wordt geschreven.

1. Klik met de rechtermuisknop op het knooppunt voor de logocomponent en klik op **[!UICONTROL Create > Create File]** om het scriptbestand img.GET.java te maken.
1. Open het bestand, kopieer de volgende code naar het bestand en klik op **[!UICONTROL Save All]**:

```java
package apps.mywebsite.components.logo;

import java.io.IOException;
import java.io.InputStream;

import javax.jcr.RepositoryException;
import javax.jcr.Property;
import javax.servlet.http.HttpServletResponse;

import com.day.cq.wcm.foundation.Image;
import com.day.cq.wcm.commons.RequestHelper;
import com.day.cq.wcm.commons.WCMUtils;
import com.day.cq.wcm.commons.AbstractImageServlet;
import com.day.cq.commons.SlingRepositoryException;
import com.day.image.Layer;
import org.apache.commons.io.IOUtils;
import org.apache.sling.api.SlingHttpServletRequest;
import org.apache.sling.api.SlingHttpServletResponse;
import org.apache.sling.api.resource.Resource;
import org.apache.sling.api.resource.ValueMap;
import org.apache.sling.api.servlets.SlingSafeMethodsServlet;

/**
 * Renders an image
 */
public class img_GET extends AbstractImageServlet {

    protected Layer createLayer(ImageContext c)
            throws RepositoryException, IOException {
        /* don't create the layer yet. handle everything later */
        return null;
    }

    protected void writeLayer(SlingHttpServletRequest req,
                              SlingHttpServletResponse resp,
                              ImageContext c, Layer layer)
            throws IOException, RepositoryException {

        Image image = new Image(c.resource);
        image.setItemName(Image.NN_FILE, "image");
        image.setItemName(Image.PN_REFERENCE, "imageReference");
        if (!image.hasContent()) {
            resp.sendError(HttpServletResponse.SC_NOT_FOUND);
            return;
        }
        /* get pure layer */
        layer = image.getLayer(false, false, false);

        /* do not re-encode layer, just spool */
        Property data = image.getData();
        InputStream in = data.getStream();
        resp.setContentLength((int) data.getLength());
        String contentType = image.getMimeType();
        if (contentType.equals("application/octet-stream")) {
            contentType=c.requestImageType;
        }
        resp.setContentType(contentType);
        IOUtils.copy(in, resp.getOutputStream());
        in.close();

        resp.flushBuffer();
    }
}
```

#### De component Logo toevoegen aan de component ContentPage {#adding-the-logo-component-to-the-contentpage-component}

1. Open in CRXDE Lite de `left.jsp` onder `/apps/mywebsite/components/contentpage file` en zoek de volgende coderegel:

   ```xml
   <div>logo</div>
   ```

1. Vervang die code door de volgende coderegel:

   ```xml
   <cq:include path="logo" resourceType="mywebsite/components/logo" />
   ```

1. Sla de wijzigingen op.
1. Laad de pagina **[!UICONTROL Products]** in uw browser opnieuw. Het logo ziet er als volgt uit, hoewel momenteel alleen de onderliggende koppeling zichtbaar is:

   ![chlimage_1-123](assets/chlimage_1-123.png)

#### Het plaatsen van het Beeld van het Logo in een Pagina {#setting-the-logo-image-in-a-page}

In deze sectie wordt beschreven hoe u een afbeelding instelt als uw logo in het dialoogvenster Ontwerpmodus.

1. Open de pagina **[!UICONTROL Products]** in uw browser en klik op de knop **[!UICONTROL Design]** onder aan Sidetrap om de modus **[!UICONTROL Design]** te activeren.

   ![](do-not-localize/chlimage_1-10.png)

1. Klik in het ontwerp van de logobalk op **[!UICONTROL Edit]** om het dialoogvenster te gebruiken voor het bewerken van de instellingen voor de logocomponent.
1. Klik in het dialoogvenster in het deelvenster op het tabblad **[!UICONTROL Image]**, blader naar de `logo.png`-afbeelding die u uit het `mywebsite.zip`-bestand hebt geëxtraheerd en klik op **[!UICONTROL OK]**.

   ![chlimage_1-124](assets/chlimage_1-124.png)

1. Klik op het driehoekje op de titelbalk van de sidetrap om terug te keren naar de modus **[!UICONTROL Edit]**.

   ![chlimage_1-7](assets/chlimage_1-7.jpeg)

1. In CRXDE Lite, ga naar de volgende knoop om de opgeslagen bezitswaarden te zien:

   `/etc/designs/mywebsite/jcr:content/contentpage/logo`

### Inclusief de component Breadcrumb {#including-the-breadcrumb-component}

In deze sectie neemt u de component breadcrumb (trail) op. Dit is een van de basiscomponenten.

1. Blader in CRXDE Lite naar `/apps/mywebsite/components/contentpage`, open het bestand `center.jsp` en vervang:

   ```java
   <div>trail</div>
   ```

   met:

   ```xml
   <cq:include path="trail" resourceType="foundation/components/breadcrumb" />
   ```

1. Sla de wijzigingen op.
1. Laad de pagina **[!UICONTROL Products 1]** in uw browser opnieuw. De trailcomponent ziet er als volgt uit:

   ![chlimage_1-125](assets/chlimage_1-125.png)

### De component Titel {#including-the-title-component} opnemen

In deze sectie neemt u de component title op. Dit is een van de basiscomponenten.

1. Blader in CRXDE Lite naar `/apps/mywebsite/components/contentpage`, open het bestand `center.jsp` en vervang:

   ```xml
   <div>title</div>
   ```

   met:

   ```xml
   <cq:include path="title" resourceType="foundation/components/title" />
   ```

1. Sla de wijzigingen op.
1. Laad de pagina **[!UICONTROL Products]** in uw browser opnieuw. De component title ziet er als volgt uit:

   ![chlimage_1-126](assets/chlimage_1-126.png)

>[!NOTE]
>U kunt een verschillende Titel en Type/Grootte op **[!UICONTROL Edit]** wijze plaatsen.

### Inclusief de component Alineasysteem {#including-the-paragraph-system-component}

Het alineasysteem (parsys) is een belangrijk onderdeel van een website omdat het een lijst met alinea&#39;s beheert. Auteurs kunnen hiermee alineacomponenten aan de pagina toevoegen en beschikken over een goede structuur.

Voeg de component parsys (één van de stichtingscomponenten) aan uw component van de inhoudspagina toe.

1. Blader in CRXDE Lite naar `/apps/mywebsite/components/contentpage`, open het bestand `center.jsp` en zoek de volgende coderegel:

   ```xml
   <div>parsys</div>
   ```

1. Vervang die coderegel door de volgende code en sla de wijzigingen op:

   ```xml
   <cq:include path="par" resourceType="foundation/components/parsys" />
   ```

1. Vernieuw in uw browser de pagina **[!UICONTROL Products]**. Het heeft nu de parsys component, die als volgt wordt gezien:

   ![chlimage_1-127](assets/chlimage_1-127.png)

### Afbeeldingscomponent {#creating-the-image-component} maken

Maak een component die een afbeelding in het alineasysteem weergeeft. Om tijd te besparen, wordt de afbeeldingscomponent gemaakt als een kopie van de logocomponent met enkele eigenschapswijzigingen.

>[!NOTE]
>
>Adobe Experience Manager biedt een imageonderdeel met meer volledige functionaliteit ( `/libs/foundation/components/image`).

#### Afbeeldingscomponent {#creating-the-image-component-1} maken

1. Klik met de rechtermuisknop op het knooppunt `/apps/mywebsite/components/logo` en klik op **[!UICONTROL Copy]**.
1. Klik met de rechtermuisknop op het knooppunt `/apps/mywebsite/components` en klik op **[!UICONTROL Paste]**.
1. Klik met de rechtermuisknop op het knooppunt `Copy of logo`, klik op **[!UICONTROL Rename]**, verwijder de bestaande tekst en typ `image`.

1. Selecteer het componentknooppunt `image` en wijzig de volgende eigenschapswaarden:

   * `jcr:title:` Mijn afbeeldingscomponent.
   * `jcr:description`: Dit is de component Mijn afbeelding.

1. Voeg een bezit aan de `image` knoop met de volgende bezitswaarden toe:

   * **[!UICONTROL Name]**: componentGroup
   * **[!UICONTROL Type]**: Tekenreeks
   * **[!UICONTROL Value]**: MyWebsite

1. Wijzig onder het knooppunt `image` de naam van het knooppunt `design_dialog` in `dialog`.

1. Naam van `logo.jsp` wijzigen in `image.jsp.`

1. Open img.GET.java en verander het pakket in `apps.mywebsite.components.image`.

![chlimage_1-128](assets/chlimage_1-128.png)

#### Afbeeldingsscript {#creating-the-image-script} maken

In deze sectie wordt beschreven hoe u het afbeeldingsscript maakt.

1. Open `/apps/mywebsite/components/image/` `image.jsp`
1. Vervang de bestaande code door de volgende code en sla de wijzigingen vervolgens op:

   ```xml
   <%@include file="/libs/foundation/global.jsp"%><%
   %><%@ page import="com.day.cq.commons.Doctype,
                       com.day.cq.wcm.foundation.Image,
                       com.day.cq.wcm.api.components.DropTarget,
                       com.day.cq.wcm.api.components.EditConfig,
                       com.day.cq.wcm.commons.WCMUtils" %><%
    /* global.jsp provides access to the current resource through the resource object */
           Image img = new Image(resource);
           img.setItemName(Image.NN_FILE, "image");
           img.setItemName(Image.PN_REFERENCE, "imageReference");
           img.setSelector("img");
           img.setDoctype(Doctype.fromRequest(request));
           img.setAlt("Home");
           img.draw(out); %>
   ```

1. Sla de wijzigingen op.

#### Image cq:editConfig Node {#creating-the-image-cq-editconfig-node} maken

Met het knooppunttype `cq:editConfig` kunt u bepaalde gedragingen van componenten configureren tijdens het bewerken van hun eigenschappen.

In deze sectie gebruikt u het knooppunt cq:editConfig om u in staat te stellen elementen van de Inhoudszoeker naar de afbeeldingscomponent te slepen.

1. Maak in CRXDE Lite onder het knooppunt /apps/mywebsite/components/image als volgt een nieuw knooppunt:

   * **[!UICONTROL Name]**: cq:editConfig.
   * **[!UICONTROL Type]**: cq:EditConfig.

1. Maak onder het knooppunt cq:editConfig als volgt een nieuw knooppunt:

   * **[!UICONTROL Name]**: cq:dropTargets.
   * **[!UICONTROL Type]**: cq:DropTargetConfig.

1. Onder het knooppunt cq:dropTargets maakt u als volgt een nieuw knooppunt:

   * **[!UICONTROL Name]**: afbeelding.
   * **[!UICONTROL Type]**: nt:ongestructureerd.

1. In CRXDE stelt u de eigenschappen als volgt in:

| Naam | Type | Waarde |
|---|---|---|
| accepteren | Tekenreeks | image/(gif) | jpeg | png) |
| groepen | Tekenreeks | media |
| propertyName | Tekenreeks | ./imageReference |

![chlimage_1-129](assets/chlimage_1-129.png)

#### Het pictogram {#adding-the-icon} toevoegen

In deze sectie voegt u het pictogram toe dat naast de afbeeldingscomponent wordt weergegeven wanneer deze in Sidetrap wordt weergegeven:

1. Klik in CRXDE Lite met de rechtermuisknop op het bestand `/libs/foundation/components/image/icon.png` en selecteer **[!UICONTROL Copy]**.
1. Klik met de rechtermuisknop op het knooppunt `/apps/mywebsite/components/image` en klik **[!UICONTROL Paste]** en vervolgens op **[!UICONTROL Save All]**.

#### Afbeeldingscomponent {#using-the-image-component} gebruiken

In deze sectie ziet u de pagina **[!UICONTROL Products]** en voegt u de afbeeldingscomponent toe aan het alineasysteem.

1. Laad de pagina **[!UICONTROL Products]** in uw browser opnieuw.
1. Klik in de Sidetrap op het pictogram **[!UICONTROL Design mode]**.
1. Klik op de knop **[!UICONTROL Edit]** om het dialoogvenster voor het ontwerp van par te bewerken.
1. In de dialoog, wordt een lijst van **[!UICONTROL Allowed Components]** getoond; navigeer naar **[!UICONTROL MyWebsite]**, selecteer **[!UICONTROL My Image Component]** en klik **[!UICONTROL OK]**.
1. Terugkeren naar **[!UICONTROL Edit mode]**.
1. Dubbelklik op het frame parsys (op **[!UICONTROL Drag components or assets here]**). De **[!UICONTROL Insert New Component]** en **[!UICONTROL Sidekick]** selecteurs kijken als volgt:

   ![chlimage_1-8](assets/chlimage_1-8.jpeg)

### Inclusief de werkbalkcomponent {#including-the-toolbar-component}

In deze sectie neemt u de werkbalkcomponent op. Dit is een van de basiscomponenten.

U hebt verschillende opties, zowel in de bewerkingsmodus als in de ontwerpmodus.

1. Navigeer in CRXDE Lite naar `/apps/mywebsite/components/contentpage`, open het bestand `body.jsp` en zoek de volgende code:

   ```java
   <div class="toolbar">toolbar</div>
   ```

1. Vervang die code door de volgende code en sla de wijzigingen op.

   ```java
   <cq:include path="toolbar" resourceType="foundation/components/toolbar"/>
   ```

1. Selecteer `Websites/My Website/English` in de mappenstructuur van de pagina AEM Websites en klik vervolgens op **[!UICONTROL New > New Page]**. Geef de volgende eigenschapswaarden op en klik op Maken:

   * **[!UICONTROL Title]**: Werkbalk
   * Selecteer **[!UICONTROL My Website Content Page Template]**

1. Klik in de lijst met pagina&#39;s met de rechtermuisknop op de pagina **[!UICONTROL Toolbar]** en klik op **[!UICONTROL Properties]**. Selecteer **[!UICONTROL Hide In Navigation]** en klik op **[!UICONTROL OK]**.

   Met de optie **[!UICONTROL Hide in Navigation]** voorkomt u dat de pagina wordt weergegeven in navigatiecomponenten, zoals boven- en listchildren.

1. Maak onder **[!UICONTROL Toolbar]** de volgende pagina&#39;s:

   * Contactpersonen
   * Feedback
   * Aanmelden
   * Zoeken

1. Laad de pagina **[!UICONTROL Products]** in uw browser opnieuw. Het ziet er als volgt uit:

   ![chlimage_1-130](assets/chlimage_1-130.png)

### De zoekcomponent {#creating-the-search-component} maken

In deze sectie maakt u de component om te zoeken naar inhoud op de website. Deze zoekcomponent kan in het alineasysteem van elke pagina worden geplaatst (bijvoorbeeld op een gespecialiseerde pagina met zoekresultaten).

Uw zoekinvoervak ziet er op de pagina **[!UICONTROL English]** als volgt uit:

![chlimage_1-131](assets/chlimage_1-131.png)

#### De zoekcomponent {#creating-the-search-component-1} maken

1. Klik in CRXDE Lite met de rechtermuisknop op `/apps/mywebsite/components`, selecteer **[!UICONTROL Create]** en **[!UICONTROL Create Component]**.
1. Gebruik het dialoogvenster om de component te configureren:

   1. Geef in één eerste deelvenster de volgende eigenschapswaarden op:

      * **[!UICONTROL Label]**: zoeken
      * **[!UICONTROL Title]**: Mijn zoekcomponent
      * **[!UICONTROL Description]**: Dit is mijn zoekcomponent
      * **[!UICONTROL Group]**: MyWebsite
   1. Klik **[!UICONTROL Next]**, dan klik **[!UICONTROL Next]** opnieuw.
   1. Klik in het deelvenster **[!UICONTROL Allowed Parents]** op de knop **[!UICONTROL +]** en typ `*/parsys`.
   1. Klik **[!UICONTROL Next]** en klik dan **[!UICONTROL OK]**.


1. Klik op **[!UICONTROL Save All]**.
1. Kopieer de volgende knooppunten en plak deze naar het knooppunt `apps/mywebsite/components/search`:

   * `/libs/foundation/components/search/dialog`
   * `` `/libs/foundation/components/search/i18n`
   * `/libs/foundation/components/search/icon.png`

1. Klik op **[!UICONTROL Save All]**.

#### Zoekscript {#creating-the-search-script} maken

In deze sectie wordt beschreven hoe u het zoekscript maakt:

1. Open het `/apps/mywebsite/components/search/search.jsp` dossier.
1. Kopieer de volgende code naar `search.jsp`:

   ```java
   <%@ page import="com.day.cq.wcm.foundation.Search,com.day.cq.tagging.TagManager" %>
   <%@include file="/libs/foundation/global.jsp" %><%
   %><cq:setContentBundle/><%
       Search search = new Search(slingRequest);
   
       String searchIn = (String) properties.get("searchIn");
       String requestSearchPath = request.getParameter("path");
       if (searchIn != null) {
           /* only allow the "path" request parameter to be used if it
            is within the searchIn path configured */
           if (requestSearchPath != null && requestSearchPath.startsWith(searchIn)) {
               search.setSearchIn(requestSearchPath);
           } else {
               search.setSearchIn(searchIn);
           }
       } else if (requestSearchPath != null) {
           search.setSearchIn(requestSearchPath);
       }
   
       pageContext.setAttribute("search", search);
       TagManager tm = resourceResolver.adaptTo(TagManager.class);
   %><c:set var="trends" value="${search.trends}"/><%
   %><center>
     <form action="${currentPage.path}.html">
       <input size="41" maxlength="2048" name="q" value="${fn:escapeXml(search.query)}"/>
       <input value="<fmt:message key="searchButtonText"/>" type="submit" />
     </form>
   </center>
   <br/>
   <c:set var="result" value="${search.result}"/>
   <c:choose>
     <c:when test="${empty result && empty search.query}">
     </c:when>
     <c:when test="${empty result.hits}">
       <c:if test="${result.spellcheck != null}">
         <p><fmt:message key="spellcheckText"/> <a href="<c:url value="${currentPage.path}.html"><c:param name="q" value="${result.spellcheck}"/></c:url>"><b><c:out value="${result.spellcheck}"/></b></a></p>
       </c:if>
       <fmt:message key="noResultsText">
         <fmt:param value="${fn:escapeXml(search.query)}"/>
       </fmt:message>
     </c:when>
     <c:otherwise>
       <p class="searchmeta">Results ${result.startIndex + 1} - ${result.startIndex + fn:length(result.hits)} of ${result.totalMatches} for <b>${fn:escapeXml(search.query)}</b>. (${result.executionTime} seconds)</p>
      <br/>
   
     <div class="searchresults"> 
       <div class="results">
         <c:forEach var="hit" items="${result.hits}" varStatus="status">
           <div class="hit">
           <a href="${hit.URL}">${hit.title}</a>
           <div class="excerpt">${hit.excerpt}</div>
          <div class="hiturl"> ${hit.URL}<c:if test="${!empty hit.properties['cq:lastModified']}"> - <c:catch><fmt:formatDate value="${hit.properties['cq:lastModified'].time}" dateStyle="medium"/></c:catch></c:if> - <a href="${hit.similarURL}"><fmt:message key="similarPagesText"/></a>
           </div></div>
         </c:forEach>
       </div>
         <br/>
   
        <div class="searchRight">
             <c:if test="${fn:length(trends.queries) > 0}">
                 <p><fmt:message key="searchTrendsText"/></p>
                 <div class="searchTrends">
                     <c:forEach var="query" items="${trends.queries}">
                         <a href="<c:url value="${currentPage.path}.html"><c:param name="q" value="${query.query}"/></c:url>"><span style="font-size:${query.size}px"><c:out value="${query.query}"/></span></a>
                     </c:forEach>
                 </div>
             </c:if> 
             <c:if test="${result.facets.languages.containsHit}">
                 <p>Languages</p>
                 <c:forEach var="bucket" items="${result.facets.languages.buckets}">
                     <c:set var="bucketValue" value="${bucket.value}"/>
                     <c:set var="label" value='<%= new java.util.Locale((String) pageContext.getAttribute("bucketValue")).getDisplayLanguage(request.getLocale()) %>'/>
                     <c:choose>
                         <c:when test="${param.language != null}">${label} (${bucket.count}) - <a href="<cq:requestURL><cq:removeParam name="language"/></cq:requestURL>">remove filter</a></c:when>
                         <c:otherwise><a title="filter results" href="<cq:requestURL><cq:addParam name="language" value="${bucket.value}"/></cq:requestURL>">${label} (${bucket.count})</a></c:otherwise>
                     </c:choose><br/>
                 </c:forEach>
             </c:if> 
             <c:if test="${result.facets.tags.containsHit}">
                 <p>Tags</p>
                 <c:forEach var="bucket" items="${result.facets.tags.buckets}">
                     <c:set var="bucketValue" value="${bucket.value}"/>
                     <c:set var="tag" value="<%= tm.resolve((String) pageContext.getAttribute("bucketValue")) %>"/>
                     <c:if test="${tag != null}">
                         <c:set var="label" value="${tag.title}"/>
                         <c:choose>
                             <c:when test="<%= request.getParameter("tag") != null && java.util.Arrays.asList(request.getParameterValues("tag")).contains(pageContext.getAttribute("bucketValue")) %>">${label} (${bucket.count}) - <a href="<cq:requestURL><cq:removeParam name="tag" value="${bucket.value}"/></cq:requestURL>">remove filter</a></c:when>
                             <c:otherwise><a title="filter results" href="<cq:requestURL><cq:addParam name="tag" value="${bucket.value}"/></cq:requestURL>">${label} (${bucket.count})</a></c:otherwise>
                         </c:choose><br/>
                     </c:if>
                 </c:forEach>
             </c:if> 
             <c:if test="${result.facets.mimeTypes.containsHit}">
                 <jsp:useBean id="fileTypes" class="com.day.cq.wcm.foundation.FileTypes"/>
                 <p>File types</p>
                 <c:forEach var="bucket" items="${result.facets.mimeTypes.buckets}">
                     <c:set var="bucketValue" value="${bucket.value}"/>
                     <c:set var="label" value="${fileTypes[bucket.value]}"/>
                     <c:choose>
                         <c:when test="<%= request.getParameter("mimeType") != null && java.util.Arrays.asList(request.getParameterValues("mimeType")).contains(pageContext.getAttribute("bucketValue")) %>">${label} (${bucket.count}) - <a href="<cq:requestURL><cq:removeParam name="mimeType" value="${bucket.value}"/></cq:requestURL>">remove filter</a></c:when>
                         <c:otherwise><a title="filter results" href="<cq:requestURL><cq:addParam name="mimeType" value="${bucket.value}"/></cq:requestURL>">${label} (${bucket.count})</a></c:otherwise>
                     </c:choose><br/>
                 </c:forEach>
             </c:if>
             <c:if test="${result.facets.lastModified.containsHit}">
                 <p>Last Modified</p>
                 <c:forEach var="bucket" items="${result.facets.lastModified.buckets}">
                     <c:choose>
                         <c:when test="${param.from == bucket.from && param.to == bucket.to}">${bucket.value} (${bucket.count}) - <a href="<cq:requestURL><cq:removeParam name="from"/><cq:removeParam name="to"/></cq:requestURL>">remove filter</a></c:when>
                         <c:otherwise><a title="filter results" href="<cq:requestURL><cq:removeParam name="from"/><cq:removeParam name="to"/><c:if test="${bucket.from != null}"><cq:addParam name="from" value="${bucket.from}"/></c:if><c:if test="${bucket.to != null}"><cq:addParam name="to" value="${bucket.to}"/></c:if></cq:requestURL>">${bucket.value} (${bucket.count})</a></c:otherwise>
                     </c:choose><br/>
                 </c:forEach>
             </c:if>
   
         <c:if test="${fn:length(search.relatedQueries) > 0}">
   
          <br/><br/><div class="related">
           <fmt:message key="relatedSearchesText"/>
           <c:forEach var="rq" items="${search.relatedQueries}">
               <a href="${currentPage.path}.html?q=${rq}"><c:out value="${rq}"/></a>
           </c:forEach></div>
         </c:if>
         </div> 
   
         <c:if test="${fn:length(result.resultPages) > 1}">
           <div class="pagination"> 
               <fmt:message key="resultPagesText"/>
           <c:if test="${result.previousPage != null}">
             <a href="${result.previousPage.URL}"><fmt:message key="previousText"/></a>
           </c:if>
           <c:forEach var="page" items="${result.resultPages}">
             <c:choose>
               <c:when test="${page.currentPage}">${page.index + 1}</c:when>
               <c:otherwise>
                 <a href="${page.URL}">${page.index + 1}</a>
               </c:otherwise>
             </c:choose>
           </c:forEach>
           <c:if test="${result.nextPage != null}">
             <a href="${result.nextPage.URL}"><fmt:message key="nextText"/></a>
           </c:if>
           </div>
         </c:if>
         </div>
   
     </c:otherwise>
   </c:choose>
   ```

1. Sla de wijzigingen op.

#### Een zoekvak opnemen in de component ContentPage {#including-a-search-box-in-the-contentpage-component}

Ga als volgt te werk om een invoervak voor zoekopdrachten op te nemen in de linkersectie van uw inhoudspagina:

1. Open in CRXDE Lite het bestand `left.jsp` onder `/apps/mywebsite/components/contentpage` en zoek de volgende code (regel 2):

   ```xml
   %><div class="left">
   ```

1. Voeg de volgende code *voor* die regel in:

   ```java
   %><%@ page import="com.day.text.Text"%><%
   %><% String docroot = currentDesign.getPath(); 
   String home = Text.getAbsoluteParent(currentPage.getPath(), 2);%><%
   ```

1. Zoek de volgende coderegel:

   ```xml
   <div>search</div>
   ```

1. Vervang die code door de volgende code en sla de wijzigingen op.

   ```java
   <div class="form_1">
        <form class="geo" action="<%= home %>/toolbar/search.html" id="form" >
             <p>
                  <input class="geo" type="text" name="q"><br> 
                  <a href="<%= home %>/toolbar/search.html" class="link_1">advanced search</a> 
             </p>
        </form>
   </div>
   ```

1. Laad de pagina **[!UICONTROL Products]** in uw browser opnieuw. De zoekcomponent ziet er als volgt uit:

   ![chlimage_1-132](assets/chlimage_1-132.png)

#### De zoekcomponent opnemen in de zoekpagina {#including-the-search-component-in-the-search-page}

In deze sectie voegt u uw zoekcomponent toe aan het alineasysteem.

1. Open in uw browser de pagina **Zoeken**.
1. Klik in de Sidetrap op het moduspictogram **[!UICONTROL Design]**.
1. Klik in het ontwerpblok van pari (onder de zoektitel) op **[!UICONTROL Edit]**.
1. Blader in het dialoogvenster omlaag naar de groep **[!UICONTROL My Websites]**, selecteer **[!UICONTROL My Search Component]** en klik op **[!UICONTROL OK]**.
1. Klik op het driehoekje bij Sidetrap om terug te keren naar de modus **[!UICONTROL Edit]**.
1. Sleep de **[!UICONTROL My Search]** component van Sidetrap in het parsys kader. Het ziet er als volgt uit:

   ![chlimage_1-133](assets/chlimage_1-133.png)

1. Navigeer naar uw **[!UICONTROL Products]** pagina. Zoek naar klanten in de invoerdoos en druk **[!UICONTROL Enter]**. U wordt omgeleid aan de **[!UICONTROL Search]** pagina. Overschakelen naar modus **[!UICONTROL Preview]**: de uitvoer heeft een vergelijkbare indeling als de volgende:

   ![chlimage_1-134](assets/chlimage_1-134.png)

### Met inbegrip van de component Iparsys {#including-the-iparsys-component}

In deze sectie, omvat u de component van het Systeem van de Paragraaf van de Overerving (iparsys), die één van de stichtingscomponenten is. Met deze component kunt u een structuur van alinea&#39;s op een bovenliggende pagina maken en onderliggende pagina&#39;s de alinea&#39;s laten overnemen.

Voor deze component kunt u verschillende parameters instellen in zowel de bewerkingsmodus als de ontwerpmodus.

1. Navigeer in CRXDE Lite naar `/apps/mywebsite/components/contentpage`, open het bestand `right.jsp` en vervang:

   ```java
   <div>iparsys</div>
   ```

   met:

   ```java
   <cq:include path="rightpar" resourceType="foundation/components/iparsys" />
   ```

1. Sla de wijzigingen op.
1. Laad de pagina **[!UICONTROL Products]** in uw browser opnieuw. De hele pagina ziet er als volgt uit:

   ![chlimage_1-9](assets/chlimage_1-9.jpeg)

