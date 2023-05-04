---
title: Voorinstellingen voor Dynamic Media-viewers beheren
seo-title: Managing Dynamic Media viewer presets
description: Voorinstellingen voor Dynamic Media-viewers maken en beheren
seo-description: How to create and manage Dynamic Media viewer presets
uuid: 31ef7a4e-2053-43b5-ac6c-cdc4b30c3914
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
discoiquuid: e78bb08a-a923-4399-b3f7-13aa4b7994d5
legacypath: /content/docs/en/aem/6-0/administer/integration/dynamic-media/viewer-presets
exl-id: 53e53cb7-1854-44e9-9516-51bcc99378b4
feature: Viewer Presets
role: Admin,User
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '4114'
ht-degree: 8%

---

# Voorinstellingen voor Dynamic Media-viewers beheren {#managing-viewer-presets}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Een Dynamic Media-viewervoorinstelling is een verzameling instellingen die bepalen hoe gebruikers rich-media-elementen op hun computerschermen en mobiele apparaten weergeven. Beheerders kunnen voorinstellingen voor viewers maken. Er zijn instellingen beschikbaar voor een array met viewerconfiguratieopties. U kunt bijvoorbeeld de weergavegrootte of het zoomgedrag van de viewer wijzigen.

Raadpleeg de HTML Dynamic Media voor instructies voor het maken en aanpassen van uw eigen Adobe5-viewervoorinstellingen *HTML5 Viewer SDK API-documentatie*. De SDK is beschikbaar op de IS-publicatieserver die is ingesloten in de SDK zelf. Elke bibliotheekversie heeft zijn eigen documentatie van SDK inbegrepen.

Pad: `<scene7_domain>/s7sdk/<library_version>/docs/jsdocs/index.html`.\
Bijvoorbeeld 3.10 SDK: [https://s7d1.scene7.com/s7sdk/3.10/docs/jsdoc/index.html](https://s7d1.scene7.com/s7sdk/3.10/docs/jsdoc/index.html)

Zie ook de [Adobe Dynamic Media Viewers Reference Guide](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/library/homeviewers.html).

In deze sectie wordt beschreven hoe u voorinstellingen voor viewers kunt maken, bewerken en beheren. U kunt een viewervoorinstelling op elk gewenst moment op een element toepassen. Zie [Viewer-voorinstellingen toepassen](viewer-presets.md).

>[!NOTE]
>
>Houd er rekening mee dat u alle *Voorinstellingen voor vooraf gedefinieerde viewers buiten de box* is geen ondersteund scenario. Als u probeert een voorinstelling voor een viewer buiten het vak te bewerken, wordt u gevraagd de voorinstelling van de viewer op te slaan onder een andere naam.

## Toetsenbordtoegankelijkheid voor viewers {#keyboard-accessibility-for-viewers}

Alle viewers die niet in de verpakking zijn opgenomen, ondersteunen toegankelijkheid van het toetsenbord.

Zie ook [Toetsenbordtoegankelijkheid en -navigatie](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/library/c-keyboard-accessibility.html).

## Voorinstellingen voor Dynamic Media-viewers beheren {#managing-presets}

U kunt voorinstellingen voor viewers in AEM toevoegen, bewerken, verwijderen, publiceren, ongedaan maken en voorvertonen door erop te tikken **[!UICONTROL Tools > Assets > Viewer Presets]**.

![tools-assets](assets/tools-assets.png)

>[!NOTE]
>
>Standaard geeft het systeem 15 voorinstellingen voor viewers weer wanneer u Viewers selecteert in de gedetailleerde weergave van elementen. U kunt deze limiet verhogen. Zie [Het aantal weergegeven viewervoorinstellingen verhogen](#increasing-the-number-of-viewer-presets-that-display).

## Viewer-ondersteuning voor responsieve webpagina&#39;s {#viewer-support-for-responsive-designed-web-pages}

Verschillende webpagina&#39;s hebben verschillende behoeften. Soms wilt u bijvoorbeeld een webpagina die een koppeling bevat waarmee de HTML5 Viewer in een apart browservenster wordt geopend. In andere gevallen kan het nodig zijn de HTML5 Viewer rechtstreeks in te sluiten op de hostpagina. In het laatste geval kan de webpagina een statische indeling hebben. Of het kan *responsief* en anders weergeven op verschillende apparaten of voor verschillende venstergrootten in de browser. Om aan deze behoeften tegemoet te komen, ondersteunen alle vooraf gedefinieerde, kant-en-klare HTML5 Viewers die bij Dynamic Media worden geleverd zowel statische webpagina&#39;s als responsieve webpagina&#39;s.

Zie [Responsieve afbeeldingsbibliotheek](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-serving-api/image-serving-api/responsive-static-image-library/c-about-responsive-static-image-library.html) in de *Help bij Image Serving API* voor meer informatie over het insluiten van responsieve viewers op uw webpagina&#39;s.

>[!NOTE]
>
>Houd er rekening mee dat u alle viewers uit de verpakking moet publiceren voordat u ze voor het eerst gebruikt.\
>Zie [Voorinstellingen van viewer publiceren.](#publishing-viewer-presets)

## Systeemcompatibiliteit met voorinstellingen van viewer  {#viewer-preset-system-compatibility}

Alle voorinstellingen voor viewers buiten de box die bij Dynamic Media worden geleverd, zijn volledig compatibel met de volgende systemen:

* Desktops
* Apple iPhone
* Apple iPad
* Android Smartphone
* Android-tablet
* Voor video is aanvullende ondersteuning voor het afspelen van MP4 beschikbaar [Blackberry](https://developer.blackberry.com/devzone/develop/supported_media/bb_media_support_at_a_glance.html#kba1328730952678) en [Windows-telefoon 8](https://msdn.microsoft.com/library/windows/apps/ff462087%28v=vs.105%29.aspx).

### Rijke mediatypen voor viewervoorinstellingen {#rich-media-types-for-viewer-presets}

Beheerders kunnen de volgende rich media-typen toevoegen en aanpassen bij het maken van nieuwe viewervoorinstellingen.

| Rijke mediatypen | Beschrijving |
|:---|:---|
| **Carousel-set** | Hotspots of afbeeldingen met hyperlinks of beide worden toegevoegd aan een reeks van twee of meer afbeeldingen. Een klant kan de afbeeldingen naar links of rechts pannen en vervolgens op een hotspot op een afbeelding klikken voor meer informatie of voor directe aankoop van de categorie, de startpagina of de bestemmingspagina&#39;s van een website. |
| **Zoomen met flyout** | Hiermee geeft u een tweede afbeelding van het ingezoomde gebied weer naast de oorspronkelijke afbeelding. Er zijn geen besturingselementen om te gebruiken. Gebruikers verplaatsen de selectie over het gebied dat ze willen weergeven. |
|  | Houd er bij het bepalen van het totale bandbreedtegebruik voor deze viewer rekening mee dat zowel de hoofdafbeelding als de vervolgafbeelding in de viewer worden weergegeven. De grootte van de vervolgafbeelding wordt bepaald door de grootte van de hoofdafbeelding (breedte en hoogte van werkgebied) en de zoomfactor. Als u wilt voorkomen dat de flyout-bestandsgrootte te groot wordt, brengt u de volgende twee waarden met elkaar in evenwicht: Als u een grote hoofdafbeeldingsgrootte hebt, verlaagt u de waarde voor Zoomfactor. (De breedte en hoogte van de Flyout bepalen de grootte van het wegvliegvenster, maar niet de grootte van het vliegend beeld dat aan de kijker wordt gediend.) |
|  | Als de hoofdafbeelding bijvoorbeeld 350 x 350 pixels groot is, met een zoomfactor van 3, is de resulterende uitvliegafbeelding 1050 x 1050 pixels. Als de hoofdafbeeldingsgrootte 300 x 300 pixels is, met een zoomfactor van 4, is de vervolgafbeelding 1200 x 1200 pixels. Afhankelijk van de kwaliteitsinstelling JPEG (aanbevolen instellingen liggen tussen 80 en 90), kunt u de bestandsgrootte aanzienlijk verkleinen. De aanbevolen zoomfactoren zijn 2,5 tot 4, afhankelijk van de grootte van de hoofdafbeelding. |
| **Inline zoomen** | Hiermee geeft u een afbeelding weer van het ingezoomde gebied in de oorspronkelijke viewer. Er zijn geen besturingselementen om te gebruiken. Gebruikers verplaatsen de selectie dus over het gebied dat ze willen weergeven. |
| **Afbeeldingsset** | In de Vastgestelde kijker van het Beeld, kunnen de gebruikers verschillende meningen of kleurenvariaties van een punt zien door een duimnagelbeeld te klikken. Deze viewer beschikt ook over zoomgereedschappen waarmee u afbeeldingen nauwkeurig kunt bekijken. |
| **Interactieve afbeelding** | Hotspots worden toegevoegd aan gedeelten van een afbeelding waarop een klant kan klikken voor meer informatie of voor directe aankoop van de categorie, de startpagina of de bestemmingspagina&#39;s van een website. |
| **Interactieve video** | Miniaturen worden toegevoegd aan tijdlijnsegmenten in een video waarop een klant vervolgens kan klikken voor meer informatie of voor het rechtstreeks kopen vanaf de categorie, de startpagina of de bestemmingspagina van een website. |
| **Gemengde media** | Hiermee geeft u verschillende typen media weer in één viewer. U kunt centrifuges, afbeeldingssets, afbeeldingen en video&#39;s opnemen. |
| **Panoramische afbeelding** | Met de Panoramische afbeelding en de Panoramische VR-viewers worden bolvormige panoramische afbeeldingen weergegeven zodat gebruikers deze kunnen bekijken in een 360°-kijkervaring van een ruimte, eigenschap, locatie of landschap. |
|  | Een geüploade afbeelding kan alleen als een bolvormig panorama worden beschouwd als de afbeelding een van de volgende opties of beide heeft: <ul><li>Een hoogte-breedteverhouding van 2:1.</li><li>Gelabeld met de trefwoorden equirechthoekig, bolvormig en panorama, of bolvormig en panoramisch. Zie [Tags gebruiken](../sites-authoring/tags.md).</li></ul> |
|  | Zowel zijn de aspectverhouding als de sleutelwoordcriteria van toepassing op panoramische activa voor de de detailpagina van activa en de component van &quot;Panoramische Media&quot; WCM. |
|  | Belangrijk: Deze viewer is alleen beschikbaar in de modus Dynamic Media - Scene7. |
| **Set draaien** | Biedt meerdere weergaven van een afbeelding, zodat gebruikers het object kunnen draaien om de verschillende zijden en hoeken te bekijken. |
| **Video** | Speelt video af met progressieve of adaptieve bitsnelheidstreaming. Bij adaptieve bitsnelheidstreaming worden automatisch apparaat- en bandbreedtedetectie uitgevoerd voor de juiste videokwaliteit in de juiste indeling. |
| **Verticaal zoomen** | Met de verticale zoomviewer kunt u een productafbeeldingsweergave maximaliseren, zodat uw gebruikers de beste weergave van een product krijgen. De verticale locatie van stalen doet het volgende: <ul><li>Hiermee zorgt u dat de stalen zich boven de vouw bevinden. Bij horizontale stalen waren, afhankelijk van de grootte van het , stalen pas zichtbaar wanneer de gebruiker de pagina omlaag schuift. Door de stalen verticaal in de viewer te plaatsen, weet u zeker dat ze zichtbaar zijn, ongeacht de schermgrootte van de gebruiker.</li><li>Maximaliseert de hoofdafbeeldingsgrootte. Met horizontale stalen is het nodig ruimte op de pagina te reserveren om ervoor te zorgen dat deze zichtbaar zijn. Hierdoor nam de grootte van de hoofdafbeelding af. Met een verticale staallay-out hoeft u deze ruimte echter niet toe te wijzen. Op die manier kunt u de grootte van de hoofdafbeelding maximaliseren.</li></ul> |
| **Zoomen** | Hiermee kunnen gebruikers inzoomen op het gebied door erop te klikken. Gebruikers kunnen op besturingselementen klikken om in te zoomen, uit te zoomen en de standaardgrootte van de afbeelding te herstellen. |

## Lijst met voorinstellingen voor viewers die buiten de box vallen {#list-of-out-of-the-box-viewer-presets}

In de volgende tabel worden alle vooraf gedefinieerde, offline viewervoorinstellingen weergegeven die bij Dynamic Media worden geleverd.

Zie ook [Live demo&#39;s](https://landing.adobe.com/en/na/dynamic-media/ctir-2755/live-demos.html).

Voor informatie over ondersteunde webbrowsers en besturingssysteemversies voor Viewers kunt u de Opmerkingen bij de release Viewers bekijken.

Zie *Opmerkingen bij de release van viewers* in de inhoudsopgave van de [Referentiehandleiding voor viewers](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/library/homeviewers.html).

>[!NOTE]
>
>Alle voorinstellingen voor viewers die niet in de box staan, zijn al geactiveerd (ingeschakeld), maar u moet ze wel publiceren.\
>Zie [Voorinstellingen van viewer publiceren](#publishing-viewer-presets).
>
>Alle nieuwe voorinstellingen voor viewers die u maakt en toevoegt, moeten beide worden geactiveerd *en* gepubliceerd.\
>Zie [Viewer-voorinstellingen activeren of deactiveren](#activating-or-deactivating-viewer-presets) en [Voorinstellingen van viewer publiceren](#publishing-viewer-presets).

| Titel van voorinstelling van viewer | Type | CSS-bestandsnaam |
|:---|:---|:---|
| Carrousel_Gestippeld_donker | Carousel_Set | html5_carouselviewer_dotted_black.css |
| Carrousel_Gestippeld_licht | Carousel_Set | html5_carouselviewer_dotted_light.css |
| Carousel_Numeric_dark | Carousel_Set | html5_carouselviewer_numeric_donker.css |
| Carousel_Numeric_light | Carousel_Set | html5_carouselviewer_numeric_light.css |
| Flyout | Flyout_Zoom | html5_flyoutviewer.css |
| Afbeeldingsset_donker | Afbeeldingsset | html5_zoomviewer_dark.css |
| ImageSet_light | Afbeeldingsset | html5_zoomviewer_light.css |
| InlineMixedMedia_donker | Gemengd_Media | html5_inlinemixedmediaviewer_dark.css |
| InlineMixedMedia_light | Gemengd_Media | html5_inlinemixedmediaviewer_light.css |
| InlineZoom | Flyout_Zoom | html5_inlinezoomviewer.css |
| GemengdMedia_donker | Gemengd_Media | html5_mixedmediaviewer_dark.css |
| GemengdMedia_licht | Gemengd_Media | html5_mixedmediaviewer_light.css |
| PanoramaImage | Panorama_Afbeelding | html5_panoramicimage.css |
| PanoramaImageVR | Panorama_Afbeelding | html5_panoramicimage.css |
| Shopable_Banner | Interactive_Image | html5_interactiveimage.css |
| Shopable_Video_black | Interactive_Video | html5_interactivevideoviewer_donker.css |
| Shopable_Video_light | Interactive_Video | html5_interactivevideower_light.css |
| SpinSet_donker | Spin_set | html5_spinviewer_dark.css |
| SpinSet_light | Spin_set | html5_spinviewer_light.css |
| Video (inclusief ondersteuning voor ondertiteling) | Video | html5_videoViewer.css |
| Video_social (inclusief ondersteuning voor ondertiteling en sociale media) | Video | html5_videoviewersocial.css |
| Zoomen_donker | Zoomen | html5_basiczoomviewer_dark.css |
| Zoomen_licht | Zoomen | html5_basiczoomviewer_light.css |
| ZoomenVerticaal_donker | Verticaal_Zoomen | html5_zoomverticalviewer_donker.css |
| ZoomVertical_light | Verticaal_Zoomen | html5_zoomverticalviewer_light.css |

### Matrix voor ondersteunde mobiele viewers {#supported-mobile-viewers-gestures-matrix}

In de volgende tabel worden de bewegingen van de mobiele viewer weergegeven die worden ondersteund op iOS-, Android 2.x- en Android 3.x-apparaten.

| Gesture | Zoomen met flyout | Zoomen | Draaien |
|---|---|---|---|
| **Slepen** | Pannen | Pannen | Pannen |
| **Tik op** | Flyout-venster tonen | De gebruikersinterface weergeven of verbergen | De gebruikersinterface weergeven of verbergen |
| **Dubbeltikken** | Niet van toepassing | Inzoomen of voorinstellingen | Inzoomen of voorinstellingen |
| **Kneep open** | Niet van toepassing | Inzoomen (alleen iOS en Android, 3x) | Inzoomen (alleen iOS en Android, 3x) |
| **Kneep dicht** | Niet van toepassing | Uitzoomen (alleen iOS en Android, 3x) | Uitzoomen (alleen iOS en Android, 3x) |
| **Veeggebaar** | Schuift de staalbalk | Afbeeldingen schuiven | Spinnen |
| **Vlikken** | Schuift de staalbalk | Afbeeldingen schuiven | Spinnen |

## Het aantal voorinstellingen voor Dynamic Media-viewers dat wordt weergegeven verhogen {#increasing-the-number-of-viewer-presets-that-display}

AEM toont een groot aantal viewervoorinstellingen wanneer u elementen weergeeft vanuit **[!UICONTROL Detail View > Viewers]**. U kunt het aantal weergegeven viewers verhogen of verlagen.

**Het aantal voorinstellingen voor Dynamic Media-viewers dat wordt weergegeven verhogen**:

1. Navigeren naar **[!UICONTROL CRXDE Lite]** ([http://localhost:4502/crx/de](http://localhost:4502/crx/de)).
1. Ga naar het keuzerondje met voorinstellingen voor viewer op `/libs/dam/gui/coral/content/commons/sidepanels/viewerpresets/viewerpresetslist`

   ![chlimage_1-221](assets/chlimage_1-221.png)

1. Wijzig in de eigenschap **[!UICONTROL limit]** de **[!UICONTROL Value]**, die standaard op 15 is ingesteld, in het gewenste getal.
1. Navigeer naar de vooraf ingestelde gegevensbron voor de viewer op `/libs/dam/gui/coral/content/commons/sidepanels/viewerpresets/viewerpresetslist/datasource`

   ![chlimage_1-222](assets/chlimage_1-222.png)

1. In de **[!UICONTROL limit]** eigenschap, wijzigt u het getal in het gewenste getal, bijvoorbeeld `{empty requestPathInfo.selectors[1] ? "20" : requestPathInfo.selectors[1]}`
1. Tik op **[!UICONTROL Save All]**.

## Een nieuwe voorinstelling voor een Dynamic Media-viewer maken {#creating-a-new-viewer-preset}

Door viewervoorinstellingen te maken, kunt u verschillende instellingen toepassen op weergave en interactie met elementen. U hoeft echter geen nieuwe voorinstellingen voor viewers te maken. Desgewenst kunt u de standaardvoorinstellingen voor viewers gebruiken die al bij AEM Assets worden geleverd.

Als u een nieuwe viewervoorinstelling maakt nadat u deze hebt opgeslagen, wordt de status van de viewer automatisch geactiveerd (ingesteld op **Aan**) in de **[!UICONTROL Viewer Presets]** pagina. Deze status betekent dat deze zichtbaar is in het dialoogvenster **[!UICONTROL Dynamic Media]** en de **[!UICONTROL Interactive Media]** en wanneer u een voorvertoning van een afbeelding of video weergeeft.

Sommige voorinstellingen voor viewers hebben exclusieve instellingen die het gebruik en het algemene gedrag van de viewer kunnen beïnvloeden. Afhankelijk van de viewervoorinstelling die u maakt, is het verstandig rekening te houden met deze speciale overwegingen.

Zie [Speciale overwegingen voor het maken van een voorinstelling voor een interactieve viewer](#special-considerations-for-creating-an-interactive-viewer-preset).

Zie [Speciale overwegingen voor het maken van een voorinstelling voor de Carousel Banner Viewer](#special-considerations-for-creating-a-carousel-banner-viewer-preset).

**Een nieuwe voorinstelling voor een Dynamic Media-viewer maken**:

1. Tik in de linkerbovenhoek van AEM op het AEM-logo en tik vervolgens in de linkerspoorstaaf op **[!UICONTROL Tools > Assets > Viewer Presets]**.

   ![viewervoorinstellingen](assets/viewerpresets.png)

1. Op de **[!UICONTROL Viewer Presets]** pagina, tikt u op de werkbalk op **[!UICONTROL Create]**.
1. In de **[!UICONTROL New Viewer Preset]** in het dialoogvenster **[!UICONTROL Preset Name]** voert u de naam van de nieuwe voorinstelling in. Kies zorgvuldig een naam. U kunt deze niet bewerken nadat u tikt **[!UICONTROL Create]**.

   Wanneer u de voorinstelling later in deze stappen opslaat, wordt de naam weergegeven op de pagina Voorinstellingen viewer onder de **[!UICONTROL Preset Title]** kolomkop.

1. Op de **[!UICONTROL Rich Media Type]** selecteert u het type voorinstelling voor de viewer dat u wilt maken en tikt u vervolgens in de rechterbovenhoek van de pagina op **[!UICONTROL Create]**.

   Zie [Rijke mediatypen voor viewervoorinstellingen](#rich-media-types-for-viewer-presets).

1. Op de **Viewer-voorinstelling bewerken** pagina, tikt u op de **[!UICONTROL Appearance]** tab.
1. Voer een van de volgende handelingen uit:

   * In de **[!UICONTROL Selected Type]** keuzemenu, selecteer een component waarvan visueel ontwerp u wilt aanpassen. U kunt ook op elk visueel element in de viewer tikken om het te selecteren voor configuratie.

      Met de visuele editor kunt u zien welk effect een bepaalde eigenschap heeft op een stijl. Stel een eigenschap in of pas deze aan om direct te zien welk effect het heeft op de viewer met behulp van het voorbeeld links van de editor.

      De CSS-opmaakeigenschappen voor elk type voorinstelling van de viewer worden beschreven in het gedeelte &quot;Aanpassen *&lt;viewer_name>* Help-onderwerp van de viewer [Referentiehandleiding voor viewers](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/library/homeviewers.html).

      Als u bijvoorbeeld een viewervoorinstelling van het type maakt `Mixed_Media`, zie [Gemengde Media Viewer aanpassen](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/library/viewers-aem-assets-dmc/mixed-media/customing-mixed-media/c-html5-mixedmedia-viewer-customizingviewer.html) voor een lijst en beschrijving van elke eigenschap.

   * Als u stijlinstellingen hebt gedefinieerd in een afzonderlijk CSS-bestand, kunt u het CSS-bestand uploaden naar AEM Assets. Tikken **[!UICONTROL Import CSS]** onder de **[!UICONTROL Selected Type]** keuzemenu (u moet mogelijk omhoog schuiven in de visuele editor om dit te zien) om het geüploade CSS-bestand te zoeken en dit te koppelen aan de voorinstelling van de viewer.

      Wanneer u een CSS-bestand importeert, controleert de visuele editor of de CSS de juiste viewermarkeringen gebruikt. Als u bijvoorbeeld een zoomviewer maakt, moeten alle CSS-regels die u importeert, worden gedefinieerd met de naam van de viewerklasse `.s7mixedmediaviewer` gedefinieerd voor een bovenliggend viewerelement.

      U kunt willekeurige, handgemaakte CSS importeren zolang deze de CSS-markeringen voor een bepaalde viewer correct definieert. (CSS-markeertekens worden in elke &quot;Aanpassen&quot; beschreven *&lt;viewer name=&quot;&quot;>* Help-onderwerp van de viewer [Referentiehandleiding voor viewers](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/library/homeviewers.html). Als u bijvoorbeeld wilt lezen over CSS-markeringen voor de Zoomviewer, raadpleegt u [Zoomviewer aanpassen](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/library/viewers-aem-assets-dmc/zoom/customizing-zoom/c-html5-20-zoom-viewer-customizingviewer.html).) Het is echter mogelijk dat de visuele editor bepaalde CSS-waarden niet begrijpt. In dergelijke gevallen probeert de visuele editor de fouten te negeren zodat de CSS nog steeds werkt.
   >[!NOTE]
   >
   >Tik op **[!UICONTROL Show/Hide CSS]** onder de **[!UICONTROL Selected Type]** pull-down menu (u kunt de visuele redacteur moeten omhoog scrollen om het te zien).
   >
   >Net als de visuele editor kunt u direct in de CSS een wijziging aanbrengen in een eigenschap en zo zien welk effect dit heeft op het viewervoorbeeld. En, wordt dat zelfde bezit automatisch bijgewerkt tezelfdertijd in de visuele redacteur. Als zodanig kunt u de onbewerkte CSS-editor of de visuele editor gebruiken, of beide door elkaar gebruiken.

   >[!NOTE]
   >
   >Voor knopillustraties kiest u de 2x-afbeelding en uploadt u illustraties met hoge resolutie. Wanneer u werkt met interactieve afbeeldingen en schokkende banners, kunt u ook verschillende hotspotknoppen uit de doos selecteren.

1. (Optioneel) Boven aan **[!UICONTROL Edit Viewer Preset]** pagina, tikken **[!UICONTROL Desktop]**, **[!UICONTROL Tablet]**, of **[!UICONTROL Phone]** Hiermee definieert u unieke visuele stijlen voor verschillende apparaat- en schermtypen.
1. Op de **[!UICONTROL Edit Viewer Preset]** pagina, tikt u op de **Gedrag** tab. U kunt ook op een visueel element in de viewer tikken of erop klikken om het voor de configuratie te selecteren.
1. Selecteer in het vervolgkeuzemenu **[!UICONTROL Selected Type]** een component waarvan u het gedrag wilt wijzigen.

   Veel componenten in de visuele editor hebben een gedetailleerde beschrijving. Deze beschrijvingen worden weergegeven in blauwe vakken wanneer u een component uitbreidt om de bijbehorende parameters weer te geven.

   Sommige viewertypen bevatten componenten waarmee u opdrachten voor het leveren van afbeeldingen kunt opgeven in een **IS-opdracht** tekstveld. Zie de [Referentie van de API voor het leveren van afbeeldingen](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-serving-api/image-serving-api/c-is-home.html) voor een lijst met opdrachten die u kunt gebruiken.

   >[!NOTE]
   >
   >**Als u een aanraakapparaat gebruikt, zoals een telefoon of tablet...**
   >
   >Nadat u een waarde in het tekstveld hebt getypt, tikt u ergens anders in de gebruikersinterface om de wijziging te verzenden en sluit u het virtuele toetsenbord. Als u tikt op **[!UICONTROL Enter]**, treedt geen actie op.

1. Tik in de rechterbovenhoek van de pagina op **[!UICONTROL Save]**.
1. Publiceer uw nieuwe viewervoorinstelling. U moet de voorinstelling publiceren voordat u deze op uw website kunt gebruiken.

   Zie [Voorinstellingen van viewer publiceren](#publishing-viewer-presets).

## Speciale overwegingen voor het maken van een voorinstelling voor een interactieve viewer {#special-considerations-for-creating-an-interactive-viewer-preset}

**Informatie over weergavemodi voor afbeeldingsminiaturen in het deelvenster**

Wanneer u een voorinstelling voor een interactieve videoviewer maakt of bewerkt, kunt u kiezen **[!UICONTROL Display Mode]** instelling die u wilt gebruiken wanneer u `InteractiveSwatches` van de **[!UICONTROL Selected Component]** keuzemenu onder de **[!UICONTROL Behavior]** tab. De gekozen weergavemodus bepaalt hoe en wanneer miniaturen worden weergegeven terwijl de video wordt afgespeeld. U kunt een van de `segment`weergavemodus (standaard) of een `continuous`weergavemodus.

| Weergavemodus | Beschrijving |
|---|---|
| [!UICONTROL Segment] | [!UICONTROL Segment] is de standaardweergavemodus voor de voorinstellingen Shopable_Video_light en Shopable_Video_donker voor de uit-van-box Interactieve video-viewer en alle interactieve voorinstellingen van de video-viewer die u zelf maakt. |
|  | Als er in deze modus minder miniaturen zijn toegewezen aan een videosegment dan het aantal zichtbare vlekken in het weergavevenster, worden miniaturen van de volgende of vorige subsegmenten niet naar de lege vlekken in het deelvenster getrokken. Met andere woorden, het behoudt de weergave van stalen die aan het specifieke videosegment zijn toegewezen. |
| [!UICONTROL Continuous] | In [!UICONTROL Continuous] Als het aantal miniaturen in een segment kleiner is dan het aantal dat in het deelvenster zichtbaar is, neemt de viewer automatisch de weergave van miniaturen van het volgende segment of van het vorige segment op wanneer de laatste miniatuur wordt weergegeven. |

**Het gedrag Automatisch schuiven in de interactieve video-viewer**

Het gedrag voor automatisch schuiven van miniaturen in de Interactieve videoviewer werkt onafhankelijk van de gekozen weergavemodus.

Wanneer u een voorinstelling voor een interactieve videoviewer maakt of bewerkt, hebt u toegang tot **[!UICONTROL Auto Scroll]** van de **[!UICONTROL Behavior]** tab. Tik in het tabblad Gedrag vanuit het vervolgkeuzemenu **[!UICONTROL Selected Components]** op **[!UICONTROL InteractiveSwatches]**. De **[!UICONTROL Auto Scroll]** wordt weergegeven onder het tekstveld IS-opdracht.

Als u **[!UICONTROL Auto Scroll]** uitschakelt (het selectievakje wist) in de viewervoorinstelling, wordt tijdens het afspelen van video door de gebruiker in het deelvenster alleen de eerste miniatuurafbeelding voor de volledige lengte van de video weergegeven. Een gebruiker kan echter desgewenst handmatig door de miniaturen bladeren met de pictogrammen pijl-omhoog en pijl-omlaag.

Wanneer u **[!UICONTROL Auto Scroll]** inschakelt (selecteert) in de viewervoorinstelling, schuiven miniatuurafbeeldingen die aan een videosegment zijn toegewezen tijdens het afspelen van de video naar het begin van een segment. Er zijn echter gevallen waarin bepaalde miniaturen in een segment tweemaal zo lang worden weergegeven als andere miniaturen ervoor of erna. Dit gedrag treedt op omdat het aantal miniaturen in een segment groter is dan het aantal dat zichtbaar is in het deelvenster en dat aantal niet gelijkmatig kan worden verdeeld.

Stel dat u een videosegment van 30 seconden hebt om dit te illustreren. En er zijn in totaal negen miniaturen die gedurende de 30 seconden moeten worden weergegeven. De grootte van de browser is zodanig dat er vier zichtbare miniatuurposities in het weergavevenster aanwezig zijn. Het 30 tweede videotijdsegment wordt verdeeld in drie subsegmenten. In de volgende tabel wordt de verdeling weergegeven van de miniaturen voor een bepaald tijdsubsegment:

| **Subsegment video** | **Tijd van subsegment in seconden** | **Miniaturen die zichtbaar zijn in het deelvenster** |
|---|---|---|
| 1 | 0-10 | 1, 2, 3, 4 |
| 2 | 10-20 | 4, 5, 6, 7 |
| 3 | 20-30 | 6, 7, 8, 9 |

Subsegment video 3 reikt niet verder dan de miniaturen die eraan zijn toegewezen. De miniaturen 4, 6 en 7 zijn twee keer zo lang in het deelvenster zichtbaar als de andere miniaturen.

De logica die de viewer gebruikt voor het aantal miniaturen dat in het deelvenster wordt weergegeven op basis van het aantal beschikbare posities is als volgt:

* Aantal subsegmenten = afgerond tot het volgende subsegment (aantal miniaturen/aantal zichtbare sleuven in het deelvenster met miniaturen, op basis van de grootte van het browservenster).

   Aan de hand van het voorbeeld in de bovenstaande tabel 9 miniaturen / 4 sleuven = 2,25; De viewerlogica rondt deze tot drie subsegmenten.

* Aantal miniaturen = afgerond tot op de volgende miniatuur (aantal miniaturen / aantal videosubsegmenten).

   In het bovenstaande voorbeeld worden 9 miniaturen / 3 videosubsegmenten = 3 miniaturen gebruikt.

* Duur van het subsegment = totale videoduur / aantal videosubsegmenten.

   Met behulp van het voorbeeld in de bovenstaande tabel, 30 seconden/3 video-subsegmenten = 10 seconden weergave van elk videosubsegment.

### Speciale overwegingen voor het maken van een voorinstelling voor de Carousel Banner-viewer {#special-considerations-for-creating-a-carousel-banner-viewer-preset}

Als u voorinstellingen voor de Carousel Banner-viewer maakt, kunt u de stijl van hotspots als volgt wijzigen:

|  | **Beschrijving** | **Handelingen** |
|---|---|---|
| **Hotspot-pictogram** | Het pictogram voor hotspot wijzigen | Als u de afbeelding van het hotspot-pictogram wilt wijzigen, gaat u naar **[!UICONTROL Appearance]** tab, in **[!UICONTROL Selected Component]**, tikken **[!UICONTROL ImageMapEffect]**. Selecteer onder **[!UICONTROL Icon]** de optie **[!UICONTROL Background]** en ga in het veld **[!UICONTROL Image]** naar de gewenste achtergrondafbeelding. |

## Voorinstellingen voor Dynamic Media-viewer activeren of deactiveren {#activating-or-deactivating-viewer-presets}

De Viewer-voorinstellingen die beschikbaar zijn in de gebruikersinterface, zijn afhankelijk van de vraag welke voorinstellingen actief zijn in de modus Auteur. Een viewervoorinstelling is standaard ingesteld op *Aan* nadat u het hebt gemaakt. Als u de voorinstelling uitschakelt, wordt deze niet weergegeven in de modus Auteur. Als de voorinstelling is gepubliceerd. het wordt altijd gepubliceerd , ongeacht of het wordt in - of uitgeschakeld . U kunt voorinstellingen voor viewers desactiveren als de lijst te log wordt of als u niet wilt dat een voorinstelling voor viewers kan worden gebruikt.

**Voorinstellingen voor Dynamic Media-viewers activeren of deactiveren**:

1. Tik in de linkerbovenhoek van AEM op het AEM-logo en tik vervolgens in de linkerspoorstaaf op **[!UICONTROL Tools > Assets > Viewer Presets]**.
1. Op de **[!UICONTROL Viewer Preset]** pagina, onder de **[!UICONTROL State]** tikken op de schakelknop om een viewervoorinstelling te activeren of deactiveren.

   De viewervoorinstellingen die worden geactiveerd, worden aan de rechterkant weergegeven, in een blauw vak. bij gedeactiveerde viewervoorinstellingen wordt de schakeloptie links weergegeven, in een lichtgrijs vak.

## Voorinstellingen voor Dynamic Media-viewer publiceren {#publishing-viewer-presets}

Activeren (of draaien) *Aan*) betekent de status van een viewer-voorinstelling dat deze zichtbaar is in de Dynamic Media-component, de interactieve component Media en wanneer u een element weergeeft.

Als u echter een element met een viewervoorinstelling wilt leveren, moet de viewervoorinstelling ook worden gepubliceerd. Alle voorinstellingen van de viewer moeten worden geactiveerd *en* gepubliceerd om URL te verkrijgen of code voor een element in te sluiten. U moet alle standaard viewervoorinstellingen die bij dynamische media worden geleverd, activeren en publiceren. Aangepaste viewervoorinstellingen die u maakt en toevoegt, worden automatisch geactiveerd, maar moeten ook worden gepubliceerd.

Zie [Viewer-voorinstellingen activeren of deactiveren](#activating-or-deactivating-viewer-presets).

Zie ook [Elementen voorvertonen](previewing-assets.md).

**Voorinstellingen voor Dynamic Media-viewers publiceren**:

1. Tik in de linkerbovenhoek van AEM op het AEM-logo en tik vervolgens in de linkerspoorstaaf op **[!UICONTROL Tools > Assets > Viewer Presets]**.
1. Selecteer een of meer voorinstellingen voor viewers die u wilt publiceren.
1. Tik op de werkbalk op de knop **[!UICONTROL Publish]** pictogram.

## Voorinstellingen voor Dynamic Media-viewer sorteren {#sorting-viewer-presets}

**Voorinstellingen voor Dynamic Media-viewers sorteren**:

1. Tik in de linkerbovenhoek van AEM op het AEM-logo en tik vervolgens in de linkerspoorstaaf op **Gereedschappen** (hamerpictogram) **[!UICONTROL > Assets > Viewer Presets]**.
1. Klik op **[!UICONTROL Preset Title]**, **[!UICONTROL Type]**, **[!UICONTROL Published]** of **[!UICONTROL State]** om op die kolomkop te sorteren. Klik bijvoorbeeld op **[!UICONTROL Type]** om de typen viewervoorinstellingen in alfabetische of omgekeerd alfabetische volgorde te sorteren.

## Voorinstellingen voor Dynamic Media-viewers bewerken {#editing-viewer-presets}

Houd er rekening mee dat u alle *Voorinstellingen voor vooraf gedefinieerde viewers buiten de box* is geen ondersteund scenario. Als u een voorinstelling voor een viewer buiten de box bewerkt, wordt u gevraagd deze op te slaan onder een andere naam.

**Voorinstellingen voor Dynamic Media-viewers bewerken**:

1. Tik in de linkerbovenhoek van AEM op het AEM-logo en tik vervolgens in de linkerspoorstaaf op **[!UICONTROL Tools > Assets > Viewer Presets]**.
1. Selecteer een voorinstelling door het vakje links van de titel van de voorinstelling voor de viewer in te schakelen.
1. Tik op de werkbalk op **[!UICONTROL Edit]**.
1. Op de **[!UICONTROL Edit Viewer Preset]** De pagina brengt de wijzigingen aan die u wilt aanbrengen in de voorinstelling van de viewer.
1. Voer een van de volgende handelingen uit:

   * Tikken **[!UICONTROL Save]** om uw wijzigingen op te slaan en terug te keren naar de **[!UICONTROL Viewer Preset]** pagina.
   * Tikken **[!UICONTROL Cancel]** om eventuele aangebrachte wijzigingen te voorkomen en terug te keren naar de **[!UICONTROL Viewer Preset]** pagina.

## Aangepaste Dynamic Media-viewervoorinstellingen verwijderen {#deleting-custom-viewer-presets}

U kunt Viewer-voorinstellingen verwijderen die u hebt gemaakt en aan Dynamic Media hebt toegevoegd.

**Aangepaste voorinstellingen voor Dynamic Media-viewers verwijderen**:

1. Tik in de linkerbovenhoek van AEM op het AEM-logo en tik vervolgens in de linkerspoorstaaf op **[!UICONTROL Tools > Assets > Viewer Presets]**.
1. Op de **[!UICONTROL Viewer Presets]** pagina, controleer een **[!UICONTROL Preset Title]** tikt u vervolgens op de knop **[!UICONTROL Trash]** pictogram.
1. Tik op **[!UICONTROL Delete]**.

## Een Dynamic Media-viewervoorinstelling toepassen op een element {#applying-a-viewer-preset-to-an-asset}

Als u zowel de asset als de geselecteerde viewer al hebt gepubliceerd, worden de knoppen **[!UICONTROL URL]** en **[!UICONTROL Embed]** weergegeven nadat u een viewervoorinstelling hebt geselecteerd.

**Een Dynamic Media-viewervoorinstelling toepassen op een element**:

1. Open het element en tik in de linkerbovenhoek van de pagina op het vervolgkeuzemenu en selecteer **[!UICONTROL Viewers]**.

   >[!NOTE]
   >
   >Als u zowel de asset als de geselecteerde viewer al hebt gepubliceerd, worden de knoppen **[!UICONTROL URL]** en **[!UICONTROL Embed]** weergegeven nadat u een viewervoorinstelling hebt geselecteerd.

1. Selecteer een viewervoorinstelling in het linkerdeelvenster om deze toe te passen op het element.

   U kunt [kopiëren naar gedeelde URL](linking-urls-to-yourwebapplication.md) met andere gebruikers.

## Middelen leveren met voorinstellingen voor Dynamic Media-viewers {#delivering-assets-with-viewer-presets}

Als u de URL&#39;s voor Viewer-voorinstellingen wilt ophalen, raadpleegt u [URL&#39;s koppelen aan uw webtoepassing](linking-urls-to-yourwebapplication.md). Zie ook [De video-viewer insluiten op een webpagina](embed-code.md).

Als u AEM gebruikt als uw WCM, kunt u elementen toevoegen met behulp van de voorinstellingen van de viewer rechtstreeks op de pagina. Zie [Dynamic Media-elementen toevoegen aan pagina&#39;s](adding-dynamic-media-assets-to-pages.md).
