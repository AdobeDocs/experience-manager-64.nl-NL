---
title: Dynamic Media-elementen toevoegen aan pagina's
seo-title: Dynamic Media-elementen toevoegen aan pagina's
description: Dynamic Media-componenten aan een pagina toevoegen in AEM
seo-description: Dynamic Media-componenten aan een pagina toevoegen in AEM
uuid: 77abcb87-2df7-449b-be52-540d749890b6
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
discoiquuid: d1f45751-1761-4d6b-b17d-110b2f1117ea
translation-type: tm+mt
source-git-commit: 44fb6e0ae344111385be844dfad1c6618c9209f0
workflow-type: tm+mt
source-wordcount: '2708'
ht-degree: 4%

---


# Dynamic Media-assets aan pagina&#39;s toevoegen {#adding-dynamic-media-assets-to-pages}

Als u de functionaliteit voor dynamische media wilt toevoegen aan elementen die u op uw websites gebruikt, kunt u de component **Dynamic Media** of **Interactive Media** rechtstreeks op de pagina toevoegen. U doet dit door de modus Lay-out in te voeren en de dynamische mediacomponenten in te schakelen. Vervolgens kunt u deze componenten aan de pagina toevoegen en assets aan de component toevoegen. De dynamische media en interactieve mediacomponenten zijn slim: ze weten of u een afbeelding of video toevoegt en de beschikbare opties veranderen dienovereenkomstig.

U voegt dynamische media-elementen rechtstreeks aan de pagina toe als u AEM gebruikt als uw WCM. Als u een oplossing van derden gebruikt voor uw WCM, moet u uw assets [koppelen](linking-urls-to-yourwebapplication.md) of [insluiten](embed-code.md). Voor een responsieve website van derden raadpleegt u het [leveren van geoptimaliseerde afbeeldingen op een responsieve site](responsive-site.md).

>[!NOTE]
>
>U moet elementen publiceren voordat u deze aan pagina&#39;s in AEM toevoegt. Zie [Dynamic Media-middelen publiceren](publishing-dynamicmedia-assets.md).

## Een Dynamic Media-component toevoegen aan een pagina {#adding-a-dynamic-media-component-to-a-page}

Het toevoegen van een Dynamic Media-component aan een pagina is hetzelfde als het toevoegen van een component aan een pagina. De Dynamic Media-componenten worden in de volgende secties uitgebreid beschreven.

>[!NOTE]
>
>Als er een Dynamic Media-component op een webpagina staat die wordt benaderd door een gebruiker met de machtiging Alleen-lezen, worden de pagina-einden en de componenten niet correct weergegeven. De reden hiervoor is dat de pagina opnieuw wordt samengesteld om ervoor te zorgen dat de eigenschappen van de componenten goed zijn en dat de bestanden en configuraties waarnaar wordt verwezen toegankelijk zijn. De pagina wordt vervolgens opnieuw gerenderd, waardoor de componenten worden verbroken. de respectievelijke componentcode op de pagina kan niet opnieuw worden weergegeven vanwege de alleen-lezen toegang van de gebruiker.
>  
>Om dit probleem te voorkomen, moet u ervoor zorgen dat AEM Sites-gebruikers de benodigde machtigingen hebben om toegang te krijgen tot de middelen.

1. Open in AEM de pagina waaraan u de Dynamic Media-component wilt toevoegen.
1. Klik op het pictogram **[!UICONTROL Components]** in het deelvenster aan de linkerkant van de pagina (mogelijk moet u de weergave van het zijpaneel in- of uitschakelen).
1. Selecteer **[!UICONTROL Dynamic Media]** onder de kop **[!UICONTROL Components]** in de vervolgkeuzelijst. Als er geen lijst met Dynamic Media-componenten beschikbaar is, moet u waarschijnlijk de Dynamic Media-componenten inschakelen die u wilt gebruiken. Zie [Dynamic Media-componenten inschakelen](#enabling-dynamic-media-components).

   ![chlimage_1-537](assets/chlimage_1-537.png)

1. Sleep een Dynamic Media-component die u wilt gebruiken naar de pagina op de gewenste locatie.
1. Houd de muisaanwijzer rechtstreeks boven de component. Tik eenmaal om de werkbalk van de component weer te geven wanneer de component is omringd door een blauw vak. Tik op het pictogram **[!UICONTROL Configuration]** (moersleutel).
1. [Bewerk indien nodig de ](#dynamic-media-components) componenten en klik op het vinkje om de wijzigingen op te slaan.

### Dynamic Media-componenten {#enabling-dynamic-media-components} inschakelen

Als er geen Dynamic Media-componenten beschikbaar zijn om aan een pagina toe te voegen, betekent dit waarschijnlijk dat u eerst de componenten moet inschakelen die u wilt gebruiken.

1. Open in AEM de pagina waaraan u de Dynamic Media-component wilt toevoegen.
1. Tik links op de werkbalk naast de pagina op het pictogram Pagina-informatie en tik vervolgens op **[!UICONTROL Edit Template]** in de vervolgkeuzelijst.

   ![edit-template](/help/assets/assets-dm/edit-template.png)

1. Tik in de vervolgkeuzelijst rechts van de werkbalk naast de pagina op **[!UICONTROL Structure]**.

   ![Beleid](/help/assets/assets-dm/structure-mode.png)

1. Tik onder aan de pagina op **[!UICONTROL Layout Container]** om de werkbalk te openen en tik vervolgens op het pictogram Beleid.
1. Controleer of op de pagina **[!UICONTROL Layout Container]** onder de kop **[!UICONTROL Properties]** het tabblad **[!UICONTROL Allowed Components]** is geselecteerd.

   ![Toegestane componenten](/help/assets/assets-dm/allowed-components.png)

1. Schuif totdat u **[!UICONTROL Dynamic Media]** ziet.
1. Tik op het pictogram > links van **[!UICONTROL Dynamic Media]** om de lijst uit te vouwen, selecteer de Dynamic Media-componenten die u wilt inschakelen.

   ![Lijst met Dynamic Media-componenten](/help/assets/assets-dm/dm-components-select.png)

1. Tik in de rechterbovenhoek van de pagina **[!UICONTROL Layout Container]** op het pictogram Gereed (vinkje).

1. Tik in de vervolgkeuzelijst rechts op de werkbalk boven aan de pagina op **[!UICONTROL Initial Content]** en voeg vervolgens [zoals gewoonlijk een Dynamic Media-component toe aan een pagina](#adding-a-dynamic-media-component-to-a-page).

## Dynamic Media-componenten lokaliseren {#localizing-dynamic-media-components}

U kunt Dynamic Media-componenten op twee manieren lokaliseren:

* Open **[!UICONTROL Properties]** en selecteer het tabblad **[!UICONTROL Advanced]** op een webpagina in Sites. Selecteer de gewenste taal voor lokalisatie.

   ![chlimage_1-538](assets/chlimage_1-538.png)

* Selecteer de gewenste pagina of paginagroep in de sitekiezer. Tik **[!UICONTROL Properties]** en selecteer het tabblad **[!UICONTROL Advanced]**. Selecteer de gewenste taal voor lokalisatie.

   >[!NOTE]
   >
   >Niet alle talen in het menu **[!UICONTROL Language]** hebben tokens toegewezen.

## Dynamic Media-componenten {#dynamic-media-components}

Dynamic Media en Interactieve media zijn beschikbaar onder het tabblad [!UICONTROL Dynamic Media] in [!UICONTROL Components]. U gebruikt de component [!UICONTROL Interactive Media] voor alle interactieve elementen, zoals interactieve video, interactieve afbeeldingen of carrouselsets. Gebruik de Dynamic Media-component voor alle andere dynamische mediacomponenten.

>[!NOTE]
>
>Deze componenten zijn niet standaard beschikbaar en moeten via de sjablooneditor beschikbaar worden gemaakt voordat ze kunnen worden gebruikt. [Nadat ze in de sjablooneditor ](/help/sites-authoring/templates.md#editing-templates-template-authors) beschikbaar zijn gesteld, kunt u de componenten aan de pagina toevoegen, net als elke andere AEM.

![chlimage_1-539](assets/chlimage_1-539.png)

### Dynamic Media-component {#dynamic-media-component}

De Dynamic Media-component is slim. Afhankelijk van het feit of u een afbeelding of video toevoegt, hebt u verschillende opties. De component ondersteunt voorinstellingen voor afbeeldingen, op afbeeldingen gebaseerde viewers, zoals afbeeldingssets, centrifuges, gemengde mediasets en video. Bovendien reageert de viewer snel. De grootte van het scherm verandert dus automatisch op basis van de schermgrootte. Alle viewers zijn HTML5-viewers.

>[!NOTE]
>
>Als er een Dynamic Media-component, een interactieve mediacomponent of beide aanwezig zijn op een webpagina die wordt geopend door een gebruiker met de machtiging Alleen-lezen, worden de pagina-einden en de componenten niet correct weergegeven. De reden hiervoor is dat de pagina opnieuw wordt samengesteld om ervoor te zorgen dat de eigenschappen van de componenten goed zijn en dat de bestanden en configuraties waarnaar wordt verwezen toegankelijk zijn. De pagina wordt vervolgens opnieuw gerenderd, waardoor de componenten worden verbroken. de respectievelijke componentcode op de pagina kan niet opnieuw worden weergegeven vanwege de alleen-lezen toegang van de gebruiker.
>  
>Om dit probleem te voorkomen, moet u ervoor zorgen dat AEM Sites-gebruikers de benodigde machtigingen hebben om toegang te krijgen tot de middelen.

>[!NOTE]
>
>Wanneer u de Dynamic Media-component toevoegt en **[!UICONTROL Dynamic Media Settings]** leeg is of wanneer u een element niet correct kunt toevoegen, controleert u het volgende:
>
>* U hebt [ingeschakelde Dynamic Media](config-dynamic.md). Dynamic Media is standaard uitgeschakeld.
>* De afbeelding heeft een piramideTIFF-bestand. Afbeeldingen die zijn geïmporteerd voordat dynamische media is ingeschakeld, hebben geen TIFF-bestand met piramide.

>



#### Wanneer u werkt met afbeeldingen {#when-working-with-images}

Met de Dynamic Media-component kunt u dynamische afbeeldingen toevoegen, zoals afbeeldingssets, centrifuges en gemengde mediasets. U kunt inzoomen, uitzoomen en, indien van toepassing, een afbeelding binnen een centrifugeset draaien of een afbeelding van een ander type set selecteren.

U kunt de viewervoorinstelling, afbeeldingsvoorinstelling of afbeeldingsindeling ook rechtstreeks in de component configureren. Als u een afbeelding responsief wilt maken, kunt u de onderbrekingspunten instellen of een responsieve voorinstelling voor de afbeelding toepassen.

U moet de volgende Dynamic Media-instellingen bewerken door op het pictogram **[!UICONTROL Edit]** in de component te klikken en vervolgens **[!UICONTROL Dynamic Media Settings]**.

![dm-settings-image-preset](assets/dm-settings-image-preset.png)

>[!NOTE]
>
>Standaard is de afbeeldingscomponent voor dynamische media adaptief. Als u van het een vaste grootte wilt maken, plaats het in de component op het **[!UICONTROL Advanced]** lusje met **[!UICONTROL Width]** en **[!UICONTROL Height]** montages.

* **[!UICONTROL Viewer preset]**
Selecteer een bestaande viewervoorinstelling in het keuzemenu. Als de viewervoorinstelling die u zoekt niet zichtbaar is, moet u deze mogelijk zichtbaar maken. Zie Viewer-voorinstellingen beheren. U kunt geen viewervoorinstelling selecteren als u een voorinstelling voor afbeeldingen gebruikt en andersom.
Dit is de enige beschikbare optie als u beeldreeksen, spin reeksen, of gemengde media reeksen bekijkt. De weergegeven viewervoorinstellingen zijn ook slim. Alleen relevante viewervoorinstellingen worden weergegeven.

* **[!UICONTROL Viewer modifiers]**
Viewer-modifiers hebben de vorm van name=value pair met een &amp;-scheidingsteken en laten u viewers wijzigen zoals wordt beschreven in de Viewer Reference Guide. Een voorbeeld van een viewermodifier is posterimage=img.jpg&amp;caption=text.vtt,1, die een andere afbeelding instelt voor de videominiatuur en een bestand met een gesloten bijschrift/subtitel koppelt aan de video.

* **[!UICONTROL Image preset]**
Selecteer een bestaande voorinstelling voor afbeeldingen in het keuzemenu. Als de voorinstelling die u zoekt niet zichtbaar is, moet u deze mogelijk zichtbaar maken. Zie Voorinstellingen afbeelding beheren. U kunt geen viewervoorinstelling selecteren als u een voorinstelling voor afbeeldingen gebruikt en andersom.
Deze optie is niet beschikbaar als u afbeeldingssets, centrifuges of gemengde mediasets bekijkt.

* **[!UICONTROL Image Modifiers]**
U kunt afbeeldingseffecten toepassen door extra opdrachten voor afbeeldingen te geven. Deze worden beschreven in Voorinstellingen afbeelding en de verwijzing Opdracht Beeldserver.
Deze optie is niet beschikbaar als u afbeeldingssets, centrifuges of gemengde mediasets bekijkt.

* **[!UICONTROL Breakpoints]**
Als u dit middel op een ontvankelijke plaats gebruikt, moet u de beeldbreekpunten toevoegen. Afbeeldingsonderbrekingspunten moeten door komma&#39;s (,) worden gescheiden. Deze optie werkt wanneer er geen hoogte of breedte is gedefinieerd in een voorinstelling voor afbeeldingen.
Deze optie is niet beschikbaar als u afbeeldingssets, centrifuges of gemengde mediasets bekijkt.
U kunt de volgende Geavanceerde Montages uitgeven door **[!UICONTROL Edit]** in de component te klikken.

* **[!UICONTROL Title]**
Wijzig de titel van de afbeelding.

* **[!UICONTROL Alt Text]**
Voeg een titel toe aan de afbeelding voor gebruikers die afbeeldingen hebben uitgeschakeld.
Deze optie is niet beschikbaar als u afbeeldingssets, centrifuges of gemengde mediasets bekijkt.

* **[!UICONTROL URL, Open in]**
U kunt een element zo instellen dat een koppeling wordt geopend. Stel de URL in en kies Openen in om aan te geven of deze in hetzelfde venster of in een nieuw venster moet worden geopend.
Deze optie is niet beschikbaar als u afbeeldingssets, centrifuges of gemengde mediasets bekijkt.

* **[!UICONTROL Width]** en  **[!UICONTROL Height]**
Voer een waarde in pixels in als u wilt dat de afbeelding een vaste grootte heeft. Als u deze waarden niet invult, wordt het element adaptief.

#### Bij het werken met video {#when-working-with-video}

Met de Dynamic Media-component kunt u dynamische video toevoegen aan uw webpagina&#39;s. Wanneer u de component bewerkt, kunt u een vooraf gedefinieerde videoviewer gebruiken om de video op de pagina af te spelen.

![chlimage_1-540](assets/chlimage_1-540.png)

U moet de volgende Dynamic Media-instellingen bewerken door in de component op **[!UICONTROL Edit]** te klikken.

>[!NOTE]
>
>De Dynamic Media-videocomponent is standaard adaptief. Als u van het een vaste grootte wilt maken, plaats het in de component met **[!UICONTROL Width]** en **[!UICONTROL Height]** in [!UICONTROL Advanced] tabel.

* **[!UICONTROL Viewer preset]**
Selecteer een bestaande voorinstelling voor een videoviewer in het keuzemenu. Als de viewervoorinstelling die u zoekt niet zichtbaar is, moet u deze mogelijk zichtbaar maken. Zie Viewer-voorinstellingen beheren.

* **[!UICONTROL Viewer modifiers]**
Viewer-modifiers hebben de vorm van name=value pair met een &amp;-scheidingsteken en laten u viewers wijzigen zoals beschreven in de Adobe Viewers Reference Guide. Een voorbeeld van een viewermodifier is posterimage=img.jpg&amp;caption=text.vtt,1

   Met viewermodifiers kunt u bijvoorbeeld het volgende doen:

   * Een bijschriftbestand koppelen aan een video [bijschrift.](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/library/viewers-aem-assets-dmc/video/command-reference-url-video/r-html5-video-viewer-url-caption.html)
   * Koppel een navigatiebestand aan een video [navigatie.](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/library/viewers-aem-assets-dmc/video/command-reference-url-video/r-html5-video-viewer-url-navigation.html)

U kunt de volgende [!UICONTROL Advanced Settings] uitgeven door **[!UICONTROL Edit]** in de component te klikken.

* **[!UICONTROL Title]**
Wijzig de titel van de video.

* **[!UICONTROL Width]** en  **[!UICONTROL Height]**
Voer een waarde in pixels in als u wilt dat de video een vaste grootte heeft. Als u deze waarden niet invult, wordt het adaptief.

#### Wanneer u werkt met Slim uitsnijden {#when-working-with-smart-crop}

Met de Dynamic Media-component kunt u SmartCrop-afbeeldingselementen toevoegen aan uw webpagina&#39;s. Wanneer u de component bewerkt, kunt u een vooraf gedefinieerde videoviewer gebruiken om de video op de pagina af te spelen.

Zie ook [Afbeeldingsprofielen](image-profiles.md).

![dm-settings-smart-crop](assets/dm-settings-smart-crop.png)

U kunt de volgende [!UICONTROL Dynamic Media Settings] uitgeven door **[!UICONTROL Edit]** in de component te klikken.

>[!NOTE]
>
>Standaard is de afbeeldingscomponent voor dynamische media adaptief. Als u een vaste grootte wilt instellen, stelt u dit in de component op het tabblad [!UICONTROL Advanced] met **[!UICONTROL Width]** en **[!UICONTROL Height]** in.

* **[!UICONTROL Image Modifiers]**
U kunt afbeeldingseffecten toepassen door extra opdrachten voor afbeeldingen te geven. Deze worden beschreven in Voorinstellingen afbeelding en de verwijzing Opdracht Beeldserver.
Deze optie is niet beschikbaar als u afbeeldingssets, centrifuges of gemengde mediasets bekijkt.

U kunt de volgende **[!UICONTROL Advanced]** montages uitgeven door **[!UICONTROL Edit]** in de component te klikken.

* **[!UICONTROL Title]**
Wijzig de titel van de afbeelding voor slim uitsnijden.

* **[!UICONTROL Alt Text]**
Voeg een titel toe aan de slimme-uitsnijdafbeelding voor gebruikers die afbeeldingen hebben uitgeschakeld.
Deze optie is niet beschikbaar als u afbeeldingssets, centrifuges of gemengde mediasets bekijkt.

* **[!UICONTROL URL, Open in]**
U kunt een element zo instellen dat een koppeling wordt geopend. Stel de URL in en kies Openen in om aan te geven of deze in hetzelfde venster of in een nieuw venster moet worden geopend.
Deze optie is niet beschikbaar als u afbeeldingssets, centrifuges of gemengde mediasets bekijkt.

* **[!UICONTROL Height]** en  **[!UICONTROL Width]**
Voer een waarde in pixels in als u wilt dat de slimme uitsnijdafbeelding een vaste grootte heeft. Als u deze waarden niet invult, wordt het adaptief.

### Interactieve mediacomponent {#interactive-media-component}

De interactieve component van Media is voor die activa die interactiviteit op hen zoals hotspots of beeldkaarten hebben. Als u een interactieve afbeelding, interactieve video of carrouselbanner hebt, gebruikt u de component Interactieve media.

De component Interactieve media is slim. Afhankelijk van het feit of u een afbeelding of video toevoegt, hebt u verschillende opties. Bovendien reageert de viewer snel - de grootte van het scherm verandert automatisch op basis van de schermgrootte. Alle viewers zijn HTML5-viewers.

>[!NOTE]
>
>Als er een Dynamic Media-component, een interactieve mediacomponent of beide aanwezig zijn op een webpagina die wordt geopend door een gebruiker met de machtiging Alleen-lezen, worden de pagina-einden en de componenten niet correct weergegeven. De reden hiervoor is dat de pagina opnieuw wordt samengesteld om ervoor te zorgen dat de eigenschappen van de componenten goed zijn en dat de bestanden en configuraties waarnaar wordt verwezen toegankelijk zijn. De pagina wordt vervolgens opnieuw gerenderd, waardoor de componenten worden verbroken. de respectievelijke componentcode op de pagina kan niet opnieuw worden weergegeven vanwege de alleen-lezen toegang van de gebruiker.
> 
>Om dit probleem te voorkomen, moet u ervoor zorgen dat AEM Sites-gebruikers de benodigde machtigingen hebben om toegang te krijgen tot de middelen.

![chlimage_1-540](assets/chlimage_1-541.png)

U kunt de volgende **[!UICONTROL General]** montages uitgeven door **[!UICONTROL Edit]** in de component te klikken.

* **[!UICONTROL Viewer preset]**
Selecteer een bestaande viewervoorinstelling in het keuzemenu. Als de viewervoorinstelling die u zoekt niet zichtbaar is, moet u deze mogelijk zichtbaar maken. Voorinstellingen voor viewers moeten worden gepubliceerd voordat ze kunnen worden gebruikt. Zie Viewer-voorinstellingen beheren.

* **[!UICONTROL Title]**
Wijzig de titel van de video.

* **[!UICONTROL Width]** en  **[!UICONTROL Height]**
Voer een waarde in pixels in als u wilt dat de video een vaste grootte heeft. Als u deze waarden niet invult, wordt het adaptief.

U kunt de volgende **[!UICONTROL Add To Cart]** montages uitgeven door **[!UICONTROL Edit]** in de component te klikken.

* **[!UICONTROL Show Product Asset]**
Deze waarde is standaard geselecteerd. Het productelement toont een afbeelding van het product zoals gedefinieerd in de module Handel. Schakel het vinkje uit om het productelement niet weer te geven.

* **[!UICONTROL Show Product Price]**
Deze waarde is standaard geselecteerd. De prijs van het product is de prijs van het object zoals gedefinieerd in de module Handel. Schakel het vinkje uit om de productprijs niet weer te geven.

* **[!UICONTROL Show Product Form]**
Deze waarde is standaard niet geselecteerd. Het productformulier bevat alle productvarianten zoals grootte en kleur. Schakel het vinkje uit om de productvarianten niet weer te geven.

### Panoramische mediacomponent {#panoramic-media-component}

Panoramische media-component is bedoeld voor die elementen die bolvormige panoramische afbeeldingen zijn. Dergelijke afbeeldingen bieden een kijkervaring van 360° voor een ruimte, eigenschap, locatie of landschap. Een afbeelding kan alleen als bolvormig panorama worden beschouwd als de afbeelding een van de volgende opties of beide heeft:

* Een hoogte-breedteverhouding van 2:1.
* Gelabeld met de trefwoorden &quot;equirechthoekig&quot; of (&quot;bolvormig&quot; + &quot;panorama&quot;) of (&quot;bolvormig&quot; + &quot;panoramisch&quot;). Zie [Tags gebruiken](/help/sites-authoring/tags.md).

Zowel zijn de aspectverhouding als de sleutelwoordcriteria van toepassing op panoramische activa voor de de detailpagina van activa en de component van &quot;Panoramische Media&quot; WCM.

![panoramisch-media-viewer-voorinstelling](assets/panoramic-media-viewer-preset.png)

U kunt de volgende instelling bewerken door te tikken op **[!UICONTROL Configure]** in de component.

* **[!UICONTROL Viewer Preset]**
Selecteer een bestaande viewer in het vervolgkeuzemenu met voorinstellingen voor viewer.

Als de viewervoorinstelling die u zoekt niet zichtbaar is, controleert u of deze is gepubliceerd. U moet viewervoorinstellingen publiceren voordat u deze kunt gebruiken. Zie [Viewer-voorinstellingen beheren](managing-viewer-presets.md).

### HTTP/2 gebruiken om Dynamic Media-elementen {#using-http-to-delivery-dynamic-media-assets} te leveren

HTTP/2 is het nieuwe, bijgewerkte webprotocol dat de manier verbetert waarop browsers en servers communiceren. Het zorgt voor een snellere overdracht van informatie en vermindert de hoeveelheid verwerkingskracht die nodig is. De levering van Dynamic Media-middelen kan nu plaatsvinden via HTTP/2, wat betere responstijd en laadtijden biedt.

Zie [HTTP2 Levering van Inhoud](http2.md) voor volledige informatie over het gaan gebruiken van HTTP/2 met uw Dynamic Media-account.

>[!MORELIKETHIS]
>
>* [Werken met kleurbeheer met AEM Dynamic Media](https://helpx.adobe.com/experience-manager/kt/assets/using/dynamic-media-color-management-technical-video-setup.html)
>* [Aangepaste videominiatuur gebruiken met AEM Dynamic Media](https://helpx.adobe.com/experience-manager/kt/assets/using/dynamic-media-video-thumbnails-feature-video-use.html)
>* [De Asset Viewer begrijpen met AEM Dynamic Media](https://helpx.adobe.com/experience-manager/kt/assets/using/dynamic-media-viewer-feature-video-understand.html)
>* [Interactieve video gebruiken met AEM Dynamic Media](https://helpx.adobe.com/experience-manager/kt/assets/using/dynamic-media-interactive-video-feature-video-use.html)
>* [De videospeler in AEM Dynamic Media gebruiken](https://helpx.adobe.com/experience-manager/kt/assets/using/dynamic-media-video-player-feature-video-use.html)
>* [Afbeeldingen verscherpen gebruiken met AEM Dynamic Media](https://helpx.adobe.com/experience-manager/6-4/assets/using/best-practices-for-optimizing-the-quality-of-your-images.html)

