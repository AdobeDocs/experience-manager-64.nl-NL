---
title: Dynamic Media Classic-functies aan uw pagina toevoegen
seo-title: Adding Dynamic Media Classic features to your page
description: Adobe Dynamic Media Classic is een gehoste oplossing voor het beheren, verbeteren, publiceren en leveren van rijke media-elementen aan Web, mobiel, e-mail en displays en drukwerk via internet.
seo-description: Adobe Dynamic Media Classic is a hosted solution for managing, enhancing, publishing, and delivering rich media assets to Web, mobile, email, and Internet-connected displays and print.
uuid: 66b9c150-c482-4a41-9772-fa39c135802c
contentOwner: Alva Ware-Bevacqui
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: authoring
content-type: reference
discoiquuid: 9ba95dce-a801-4a36-8798-45d295371b1b
exl-id: 93921d23-a2bf-43b6-b002-58a7482b22b0
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '3189'
ht-degree: 0%

---

# Dynamic Media Classic-functies aan uw pagina toevoegen{#adding-scene-features-to-your-page}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Adobe Dynamic Media Classic is een gehoste oplossing voor het beheren, verbeteren, publiceren en leveren van rijke media-elementen aan Web, mobiel, e-mail en displays en drukwerk via internet.

U kunt AEM middelen bekijken die in Dynamic Media Classic zijn gepubliceerd in verschillende viewers:

* Zoomen
* Flyout
* Video
* Afbeeldingssjabloon
* Afbeelding

U kunt digitale middelen rechtstreeks van AEM naar Dynamic Media Classic publiceren en u kunt digitale middelen van Dynamic Media Classic naar AEM publiceren.

In deze sectie wordt beschreven hoe u digitale elementen kunt publiceren van AEM naar Dynamic Media Classic en vice versa. Viewers worden ook in detail beschreven. Voor informatie over het configureren van AEM voor Dynamic Media Classic raadpleegt u [Dynamic Media Classic integreren met AEM](/help/sites-administering/scene7.md).

Zie ook [Afbeeldingen met hyperlinks toevoegen](/help/assets/image-maps.md).

Raadpleeg de volgende secties voor meer informatie over het gebruik van videocomponenten met AEM:

* [Video](/help/sites-classic-ui-authoring/manage-assets-classic-s7-video.md)

>[!NOTE]
>
>Als Dynamic Media Classic-elementen niet correct worden weergegeven, controleert u of Dynamic Media [uitgeschakeld](/help/assets/config-dynamic.md#disabling-dynamic-media) en vernieuw vervolgens de pagina.

## Handmatig publiceren naar Dynamic Media Classic vanaf middelen {#manually-publishing-to-scene-from-assets}

U kunt digitale middelen naar Dynamic Media Classic publiceren vanuit de middelenconsole in de klassieke gebruikersinterface of rechtstreeks vanuit het middel.

>[!NOTE]
>
>AEM publiceert asynchroon naar Dynamic Media Classic. Nadat u op **[!UICONTROL Publish]** Het kan enkele seconden duren voordat uw middel naar Dynamic Media Classic is gepubliceerd.

### Publiceren vanaf de middelenconsole {#publishing-from-the-assets-console}

Publiceren naar Dynamic Media Classic vanaf de middelenconsole als de middelen zich in een Dynamic Media Classic-doelmap bevinden:

1. Klik in de AEM klassieke interface op **[!UICONTROL Digital Assets]** toegang tot de beheerder van digitale middelen.

1. Selecteer het element (of de middelen) of de map in de doelmap die u naar Dynamic Media Classic wilt publiceren, klik met de rechtermuisknop en selecteer **[!UICONTROL Publish to Dynamic Media Classic]**. U kunt ook **[!UICONTROL Publish to Dynamic Media Classic]** van de **[!UICONTROL Tools]** -menu.

   ![chlimage_1-76](assets/chlimage_1-76.png)

1. Ga naar Dynamic Media Classic en bevestig dat de middelen beschikbaar zijn.

   >[!NOTE]
   >
   >Als de elementen zich niet in een gesynchroniseerde Dynamic Media Classic-map bevinden, **[!UICONTROL Publish to Dynamic Media Classic]** in beide menu&#39;s is zichtbaar, maar is uitgeschakeld.

### Publiceren vanuit een element {#publishing-from-an-asset}

U kunt een element handmatig publiceren zolang dat element zich in de gesynchroniseerde Dynamic Media Classic-map bevindt.

>[!NOTE]
>
>Als het element zich niet in de gesynchroniseerde Dynamic Media Classic-map bevindt, wordt de koppeling naar **[!UICONTROL Publish to Dynamic Media Classic]** is niet beschikbaar.

**Direct vanuit een digitaal middel publiceren naar Dynamic Media Classic**:

1. Klik in AEM op **[!UICONTROL Digital Assets]** toegang tot de beheerder van digitale middelen.

1. Dubbelklik om een element te openen.

1. Selecteer in het venster Elementdetails de optie **[!UICONTROL Publish to Dynamic Media Classic]**.

   ![screen_shot_2012-02-22at34828pm](assets/screen_shot_2012-02-22at34828pm.png)

1. De koppeling verandert in **[!UICONTROL Publishing ...]** en vervolgens **[!UICONTROL Published]**. Ga naar Dynamic Media Classic en bevestig dat het middel beschikbaar is.

   >[!NOTE]
   >
   >Als het element niet correct wordt gepubliceerd naar Dynamic Media Classic, verandert de koppeling in **[!UICONTROL Publishing Failed]**. Als het element al naar Dynamic Media Classic is gepubliceerd, leest de koppeling **[!UICONTROL Re-Publish to Dynamic Media Classic]**. Met Herpubliceren kunt u wijzigingen aanbrengen in een element in AEM en deze opnieuw publiceren.

### Elementen publiceren van buiten de CQ-doelmap {#publishing-assets-from-outside-the-cq-target-folder}

Adobe raadt u aan elementen alleen naar Dynamic Media Classic te publiceren vanuit middelen in de Dynamic Media Classic-doelmap. Als u echter elementen moet uploaden vanuit een map buiten de doelmap, kunt u dat nog steeds doen door ze te uploaden naar een *ad hoc* op Dynamic Media Classic.

U doet dit door de configuratie van de Wolk voor de pagina te vormen waar de activa zullen verschijnen. Vervolgens voegt u een Dynamic Media Classic-component aan de pagina toe en sleept u een element naar de component. Nadat de pagina-eigenschappen voor die pagina zijn ingesteld, voert u een **[!UICONTROL Publish to Dynamic Media Classic]** wordt weergegeven dat wanneer deze optie is geselecteerd, uploaden naar Dynamic Media Classic wordt geactiveerd.

>[!NOTE]
>
>Elementen in de ad-hocmap worden niet weergegeven in de Dynamic Media Classic-inhoudbrowser.

**Elementen publiceren die zich buiten de CQ-doelmap bevinden**:

1. Klik in AEM in de klassieke gebruikersinterface op **[!UICONTROL Websites]** en navigeer naar de webpagina waaraan u een digitaal element wilt toevoegen dat nog niet naar Dynamic Media Classic is gepubliceerd. (Normale regels voor paginaovererving zijn van toepassing.)

1. Klik in het zijpaneel op de knop **[!UICONTROL Page]** pictogram, klik vervolgens op **[!UICONTROL Page Properties]**.

1. Klik op **[!UICONTROL Cloud Services]> [!UICONTROL Add services] >[!UICONTROL Dynamic Media Classic (Scene7)]**.
1. Selecteer in de vervolgkeuzelijst Adobe Dynamic Media Classic de gewenste configuratie en klik vervolgens op **[!UICONTROL OK]**.

   ![chlimage_1-77](assets/chlimage_1-77.png)

1. Voeg op de webpagina een Dynamic Media Classic-component (Scene7) toe aan de gewenste locatie op de pagina.
1. Sleep een digitaal element vanuit de zoeker naar de component. U ziet een koppeling naar **[!UICONTROL Check Dynamic Media Classic Publication Status]**.

   >[!NOTE]
   >
   >Als het digitale element zich in de CQ-doelmap bevindt, hoeft u geen koppeling te maken naar **[!UICONTROL Check Dynamic Media Classic Publication Status]** wordt weergegeven. De elementen worden eenvoudig in de component geplaatst.

   ![chlimage_1-78](assets/chlimage_1-78.png)

1. Klik op **[!UICONTROL Check Dynamic Media Classic Publication Status]**. Als het middel niet is gepubliceerd, publiceert AEM het middel naar Dynamic Media Classic. Nadat het element is geüpload, bevindt het zich in de ad-hocmap. Standaard bevindt de ad-hocmap zich in de map `name_of_the_company/CQ5_adhoc`. U kunt [deze indien nodig configureren](#configuringtheadhocfolder).

   >[!NOTE]
   >
   >Als het element zich niet in een gesynchroniseerde Dynamic Media Classic-map bevindt en er geen Dynamic Media Classic-cloudconfiguratie is gekoppeld aan de huidige pagina, mislukt het uploaden.

## Dynamic Media Classic (Scene7)-componenten {#scene-components}

De volgende Dynamic Media Classic-componenten zijn beschikbaar in AEM:

* Zoomen
* Flyout (zoomen)
* Afbeeldingssjabloon
* Afbeelding
* Video

>[!NOTE]
>
>Deze componenten zijn standaard niet beschikbaar en moeten worden geselecteerd in **[!UICONTROL Design]** vóór gebruik.

Nadat ze beschikbaar zijn gesteld in **[!UICONTROL Design]** kunt u de componenten aan de pagina toevoegen, net als elke andere AEM. Elementen die nog niet naar Dynamic Media Classic zijn gepubliceerd, worden naar Dynamic Media Classic gepubliceerd als deze zich in een gesynchroniseerde map of op een pagina of met een Dynamic Media Classic-cloudconfiguratie bevinden.

### Eindbericht voor Flash-viewers {#flash-viewers-end-of-life-notice}

Met ingang van 31 januari 2017 heeft Adobe Dynamic Media Classic officieel de ondersteuning voor het Flash-viewerplatform beëindigd.

### Een Dynamic Media Classic-component aan een pagina toevoegen {#adding-a-scene-component-to-a-page}

Het toevoegen van een Dynamic Media Classic-component aan een pagina is hetzelfde als het toevoegen van een component aan een pagina. Dynamic Media Classic-componenten worden in de volgende secties uitgebreid beschreven.

**Een Dynamic Media Classic-component/viewer toevoegen aan een pagina in de klassieke gebruikersinterface**:

1. Open in AEM de pagina waaraan u de Dynamic Media Classic-component wilt toevoegen.

1. Als er geen Dynamic Media Classic-componenten beschikbaar zijn, klikt u op de liniaal in het zijpaneel om het item in te voeren **[!UICONTROL Design]** modus, klikken **[!UICONTROL Edit]** parsys, en selecteer alle **[!UICONTROL Dynamic Media Classic]** componenten om deze beschikbaar te maken.

1. Terug naar **[!UICONTROL Edit]** door op het potlood in het zijpaneel te klikken.

1. Sleep een component vanuit de **[!UICONTROL Dynamic Media Classic]** op de gewenste locatie op de pagina te plaatsen.

1. Klikken **[!UICONTROL Edit]** om de component te openen.

1. Bewerk de component naar wens en klik op **[!UICONTROL OK]** om de wijzigingen op te slaan.

### Interactieve weergaven toevoegen aan een responsieve website {#adding-interactive-viewing-experiences-to-a-responsive-website}

Het responsieve ontwerp voor uw middelen betekent dat uw middelen worden aangepast afhankelijk van waar ze worden weergegeven. Bij een responsief ontwerp worden dezelfde middelen op meerdere apparaten weergegeven.

**Een interactieve kijkervaring toevoegen aan een responsieve site in de klassieke gebruikersinterface**:

1. Meld u aan bij AEM en zorg ervoor dat u beschikt over [geconfigureerde Adobe Dynamic Media Classic-Cloud Services](/help/sites-administering/scene7.md#configuring-scene-integration) en dat Dynamic Media Classic-componenten beschikbaar zijn.

   >[!NOTE]
   >
   >Als Dynamic Media Classic WCM-componenten niet beschikbaar zijn, moet u deze inschakelen via de **[!UICONTROL Design] in.

1. In een website waarvoor de Dynamic Media Classic-componenten zijn ingeschakeld, sleept u een **[!UICONTROL Image]** naar de pagina.
1. Bewerk de component en pas de onderbrekingspunten aan in het dialoogvenster **[!UICONTROL Dynamic Media Classic Settings]** tab.

   ![chlimage_1-79](assets/chlimage_1-79.png)

1. Controleer of de viewers het formaat responsief wijzigen en of alle interacties zijn geoptimaliseerd voor computers, tablets en mobiele apparaten.

### Instellingen die voor alle Dynamic Media Classic-componenten gelden {#settings-common-to-all-scene-components}

Hoewel de configuratieopties variëren, zijn het volgende gemeenschappelijk voor alle componenten van Dynamic Media Classic:

* **[!UICONTROL File Reference]** - Blader naar een bestand waarnaar u wilt verwijzen. De bestandsverwijzing toont de element-URL en niet noodzakelijkerwijs de volledige Dynamic Media Classic-URL inclusief de URL-opdrachten en -parameters. U kunt in dit veld geen Dynamic Media Classic URL-opdrachten en -parameters toevoegen. Ze moeten worden toegevoegd via de bijbehorende functionaliteit in de component.
* **[!UICONTROL Width]** - Hiermee kunt u de breedte instellen.
* **[!UICONTROL Height]** - Hiermee kunt u de hoogte instellen.

U stelt deze configuratieopties in door bijvoorbeeld op een Dynamic Media Classic-component te dubbelklikken wanneer u een **[!UICONTROL Zoom]** component:

![chlimage_1-80](assets/chlimage_1-80.png)

### Zoomen {#zoom}

De HTML5 component van het Gezoem toont een groter beeld wanneer u + knoop drukt.

Het element heeft onderaan zoomgereedschappen. Klikken **[!UICONTROL +]** vergroten. Klikken **[!UICONTROL -]** om te verminderen. Klikken **[!UICONTROL x]** Als u de zoompijl opnieuw instelt, wordt de oorspronkelijke grootte van de afbeelding hersteld. Klik op de diagonale pijlen om deze op volledig scherm weer te geven. Klikken **[!UICONTROL Edit]** om de component te configureren. Met deze component, kunt u vormen [gemeenschappelijke instellingen voor alle Dynamic Media Classic-componenten](#settings-common-to-all-scene-components).

![](do-not-localize/chlimage_1-5.png)

### Flyout {#flyout}

In de HTML5 Flyout-component wordt het element weergegeven als een gesplitst scherm; het element in de opgegeven grootte laten staan; rechts wordt het zoomgedeelte weergegeven. Klikken **[!UICONTROL Edit]** om de component te configureren. Met deze component, kunt u vormen [gemeenschappelijke instellingen voor alle Dynamic Media Classic-componenten](/help/sites-administering/scene7.md#settingscommontoalldynamicmediaclassiccomponents).

>[!NOTE]
>
>Als uw Flyout-component een aangepaste grootte gebruikt, wordt die aangepaste grootte gebruikt en wordt de responsieve instelling van de component uitgeschakeld.
>
>Als de component Flyout de standaardgrootte gebruikt, zoals ingesteld in het dialoogvenster [!UICONTROL Design] wordt de standaardgrootte gebruikt en wordt de component uitgerekt om de paginalay-outgrootte aan te passen met responsieve instelling van de component ingeschakeld. Houd er echter rekening mee dat er een beperking geldt voor de responsieve instelling van de component. Wanneer u de component Flyout met ontvankelijke opstelling gebruikt, zou u het niet met volledige paginalrek moeten gebruiken. Anders kan de Flyout de rechterrand van de pagina overschrijden.

![chlimage_1-81](assets/chlimage_1-81.png)

### Afbeelding {#image}

Met de Dynamic Media Classic Image-component kunt u Dynamic Media Classic-functionaliteit aan uw afbeeldingen toevoegen, zoals Dynamic Media Classic-wijzigingstoetsen, voorinstellingen voor afbeeldingen of viewers en verscherpen. De Dynamic Media Classic-afbeeldingscomponent is vergelijkbaar met andere afbeeldingscomponenten in AEM met speciale Dynamic Media Classic-functionaliteit. In dit voorbeeld heeft de afbeelding de optie Dynamic Media Classic URL, `&op_invert=1` toegepast.

![](do-not-localize/chlimage_1-6.png)

**[!UICONTROL Title, Alt Text]** - In de [!UICONTROL Advanced] , voegt u een titel toe aan de afbeelding en alternatieve tekst voor gebruikers die afbeeldingen hebben uitgeschakeld.

**[!UICONTROL URL, Open in]** - U kunt een element instellen van om een koppeling te openen. Stel de **[!UICONTROL URL]** en **[!UICONTROL Open in]** om aan te geven of u deze in hetzelfde venster of in een nieuw venster wilt openen.

![chlimage_1-82](assets/chlimage_1-82.png)

**[!UICONTROL Viewer preset]** - Selecteer een bestaande viewervoorinstelling in het keuzemenu. Als de viewervoorinstelling die u zoekt niet zichtbaar is, moet u deze mogelijk zichtbaar maken. Zie [Viewer-voorinstellingen beheren](/help/assets/managing-viewer-presets.md). U kunt geen viewervoorinstelling selecteren als u een voorinstelling voor afbeeldingen gebruikt en andersom.

**[!UICONTROL Dynamic Media Classic Configuration]** - Selecteer de Dynamic Media Classic-configuratie die u wilt gebruiken voor het ophalen van actieve voorinstellingen voor afbeeldingen in het Scene7 Publishing System.

**[!UICONTROL Image preset]** - Selecteer een bestaande voorinstelling voor de afbeelding in het keuzemenu. Als de voorinstelling die u zoekt niet zichtbaar is, moet u deze mogelijk zichtbaar maken. Zie [Voorinstellingen afbeelding beheren](/help/assets/managing-image-presets.md). U kunt geen viewervoorinstelling selecteren als u een voorinstelling voor afbeeldingen gebruikt en andersom.

**[!UICONTROL Output Format]** - Selecteer de uitvoerindeling van de afbeelding, bijvoorbeeld JPEG. Afhankelijk van de uitvoerindeling die u selecteert, hebt u mogelijk aanvullende configuratieopties. Zie [Voorinstellingen afbeelding beheren](/help/assets/managing-image-presets.md).

**[!UICONTROL Sharpening]** - Selecteer hoe u de afbeelding wilt verscherpen. Verscherpen wordt gedetailleerd uitgelegd [*Aanbevolen werkwijzen voor Adobe Dynamic Media Classic-beeldkwaliteit en verscherpen*](/help/assets/assets/sharpening_images.pdf).

**[!UICONTROL URL Modifiers]** - U kunt afbeeldingseffecten wijzigen door extra opdrachten voor Dynamic Media Classic-afbeeldingen in te voeren. Deze worden beschreven in [Voorinstellingen afbeelding beheren](/help/assets/managing-image-presets.md) en de [Opdrachtverwijzing](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-serving-api/image-serving-api/http-protocol-reference/command-reference/c-command-reference.html).

**[!UICONTROL Breakpoints]** - Als uw website reageert, wilt u de onderbrekingspunten aanpassen. Onderbrekingspunten moeten worden gescheiden door komma&#39;s `,`.

### Afbeeldingssjabloon {#image-template}

[Dynamic Media Classic-afbeeldingssjablonen](https://experienceleague.adobe.com/docs/dynamic-media-classic/using/template-basics/quick-start-template-basics.html#template-basics) zijn gelaagde Photoshop-inhoud die naar Dynamic Media Classic is geïmporteerd, waar inhoud en eigenschappen zijn geparametriseerd voor variabiliteit. De **[!UICONTROL Image template]** kunt u ;afbeeldingen importeren en de tekst dynamisch in AEM wijzigen. Bovendien kunt u vormen **[!UICONTROL Image template]** gebruiken om waarden uit de clientcontext te gebruiken, zodat elke gebruiker de afbeelding op een gepersonaliseerde manier ervaart.

Klikken **[!UICONTROL Edit]** om de component te configureren. U kunt configureren [gemeenschappelijke instellingen voor alle Dynamic Media Classic-componenten](/help/sites-administering/scene7.md#settingscommontoalldynamicmediaclassicscomponents) en andere instellingen die in deze sectie worden beschreven.

![chlimage_1-83](assets/chlimage_1-83.png)

**[!UICONTROL File Reference, Width, Height]** - Zie de instellingen die gelden voor alle Dynamic Media Classic-componenten.

>[!NOTE]
>
>Dynamic Media Classic URL-opdrachten en -parameters kunnen niet rechtstreeks aan de URL van de bestandsverwijzing worden toegevoegd. Deze kunnen alleen worden gedefinieerd in de interface van de component in het dialoogvenster **[!UICONTROL Parameter]** deelvenster.

**[!UICONTROL Title, Alt Text]** In de [!UICONTROL Dynamic Media Classic Image Template] , voegt u een titel toe aan de afbeelding en alternatieve tekst voor gebruikers die afbeeldingen hebben uitgeschakeld.

**[!UICONTROL URL, Open in]** U kunt een middel van plaatsen om een verbinding te openen. Stel de **[!UICONTROL URL]** en in **[!UICONTROL Open in]** Geef aan of u het venster in hetzelfde venster of in een nieuw venster wilt openen.

![chlimage_1-84](assets/chlimage_1-84.png)

**[!UICONTROL Parameter Panel]** Wanneer u een afbeelding importeert, worden de parameters vooraf gevuld met informatie uit de afbeelding. Als er geen inhoud is die dynamisch kan worden gewijzigd, is dit venster leeg.

![chlimage_1-85](assets/chlimage_1-85.png)

#### Tekst dynamisch wijzigen {#changing-text-dynamically}

Als u de tekst dynamisch wilt wijzigen, voert u nieuwe tekst in de velden in en klikt u op **[!UICONTROL OK]**. In dit voorbeeld wordt **[!UICONTROL Price]** is nu $50 en de verzendkosten zijn 99 cent.

![chlimage_1-86](assets/chlimage_1-86.png)

De tekst in de afbeelding verandert. U kunt de oorspronkelijke waarde van de tekst herstellen door op **[!UICONTROL Reset]** naast het veld.

![chlimage_1-87](assets/chlimage_1-87.png)

#### Tekst wijzigen om de waarde van de context van een client weer te geven {#changing-text-to-reflect-the-value-of-a-client-context-value}

Als u een veld wilt koppelen aan de waarde van een clientcontext, klikt u op **[!UICONTROL Select]** om het client-contextmenu te openen, selecteert u de clientcontext en klikt u op **[!UICONTROL OK]**. In dit voorbeeld verandert de naam op basis van de koppeling van de naam met de opgemaakte naam in het profiel.

![chlimage_1-88](assets/chlimage_1-88.png)

De tekst geeft de naam weer van de gebruiker die momenteel is aangemeld. U kunt de oorspronkelijke waarde van de tekst herstellen door op **[!UICONTROL Reset]** naast het veld.

![chlimage_1-89](assets/chlimage_1-89.png)

#### Een koppeling maken van de Dynamic Media Classic-afbeeldingssjabloon {#making-the-scene-image-template-a-link}

**Een koppeling maken van de Dynamic Media Classic-afbeeldingssjabloon**:

1. Klik op de pagina met de Dynamic Media Classic-component voor afbeeldingssjablonen op **[!UICONTROL Edit]**.
1. In de **[!UICONTROL URL]** Voer de URL in waarnaar gebruikers gaan wanneer op de afbeelding wordt geklikt. In de **[!UICONTROL Open in]** , selecteert u of het doel moet worden geopend (een nieuw venster of hetzelfde venster).

   ![chlimage_1-90](assets/chlimage_1-90.png)

1. Klik op **[!UICONTROL OK]**.

### Video-component {#video-component}

De Dynamic Media Classic **[!UICONTROL Video]** -component (beschikbaar in het Dynamic Media Classic-gedeelte van het hulpprogramma) gebruikt apparaat- en bandbreedtedetectie voor de juiste video voor elk scherm. Dit onderdeel is een HTML5-videospeler. het is één viewer die via meerdere kanalen kan worden gebruikt.

Deze kan worden gebruikt voor adaptieve videosets, één MP4-video of één F4V-video.

Zie [Video](/help/sites-classic-ui-authoring/manage-assets-classic-s7-video.md) voor meer informatie over hoe video&#39;s werken met de integratie van Dynamic Media Classic. Zie ook hoe [de **Dynamic Media Classic-video** component vergelijkt met de stichting **video** component](/help/sites-classic-ui-authoring/manage-assets-classic-s7-video.md).

![chlimage_1-91](assets/chlimage_1-91.png)

### Bekende beperkingen voor de video-component {#known-limitations-for-the-video-component}

Adobe DAM en WCM laten zien of een master video is geüpload. Deze proxy-elementen worden niet weergegeven:

* Dynamic Media Classic-gecodeerde uitvoeringen
* Dynamic Media Classic adaptieve videosets

Wanneer u een adaptieve videoset gebruikt met de Dynamic Media Classic-videocomponent, moet u de grootte van de component aanpassen aan de afmetingen van de video.

## Dynamic Media Classic-inhoudbrowser {#scene-content-browser}

Met de Dynamic Media Classic-inhoudbrowser kunt u inhoud van Dynamic Media Classic rechtstreeks in AEM bekijken. Als u de inhoudbrowser wilt openen, selecteert u in de Inhoudszoeker de optie **[!UICONTROL Dynamic Media Classic]** in de aanraakgeoptimaliseerde gebruikersinterface of de **[!UICONTROL S7]** in de klassieke gebruikersinterface. De functionaliteit is identiek tussen beide gebruikersinterfaces.

Als u meerdere configuraties hebt, AEM standaard de [standaardconfiguratie](/help/sites-administering/scene7.md#configuring-a-default-configuration). U kunt verschillende configuraties rechtstreeks selecteren in de Dynamic Media Classic-inhoudbrowser in de vervolgkeuzelijst.

>[!NOTE]
>
>* Elementen in de ad-hocmap worden niet weergegeven in de Dynamic Media Classic-inhoudbrowser.
>* Wanneer [Beveiligde voorvertoning is ingeschakeld](/help/sites-administering/scene7.md#configuring-the-state-published-unpublished-of-assets-pushed-to-scene), zowel gepubliceerde als niet-gepubliceerde middelen op Dynamic Media Classic worden wel weergegeven in de Dynamic Media Classic-inhoudbrowser.
>* Als u niet ziet **[!UICONTROL Dynamic Media Classic]** of de **[!UICONTROL S7]** als optie in de inhoudbrowser, moet u [Dynamic Media Classic configureren om te werken met AEM](/help/sites-administering/scene7.md).
>
>* Voor video ondersteunt de Dynamic Media Classic-inhoudbrowser:
>
>* Adaptieve videosets: container met alle video-uitvoeringen die nodig zijn voor naadloze weergave op meerdere schermen
>* Eén MP4-video
>* Single F4V-video


### Door inhoud bladeren in de klassieke gebruikersinterface {#browsing-content-in-the-classic-ui}

Door inhoud in Dynamic Media Classic bladeren door op de knop **[!UICONTROL S7]** tab.

U kunt de configuratie veranderen u toegang hebt door de configuratie te selecteren. De mappen veranderen, afhankelijk van de configuratie die u selecteert.

![chlimage_1-92](assets/chlimage_1-92.png)

Net als bij de zoekfunctie voor inhoud naar Middelen kunt u zoeken naar elementen en resultaten filteren. In tegenstelling tot de zoeker bij Elementen wordt bij het invoeren van een trefwoord in het dialoogvenster **[!UICONTROL S7]** tab, de bestandsnaam *begint met* de tekenreeks die u hebt ingevoerd, in plaats van *bevattende* het trefwoord in de bestandsnaam.

Elementen worden standaard weergegeven op bestandsnaam. U kunt resultaten ook filteren op type element.

>[!NOTE]
>
>Voor video ondersteunt de Dynamic Media Classic-inhoudbrowser van WCM:
>
>* Adaptieve videosets: container met alle video-uitvoeringen die nodig zijn voor naadloze weergave op meerdere schermen
>* Eén MP4-video
>* Single F4V-video
>


### Dynamic Media Classic-elementen zoeken met de inhoudbrowser {#searching-for-scene-assets-with-the-content-browser}

Het zoeken naar Dynamic Media Classic-elementen lijkt op het zoeken naar AEM elementen, maar wanneer u een zoekopdracht uitvoert, ziet u in feite een externe weergave van de elementen in het Dynamic Media Classic-systeem in plaats van deze rechtstreeks in AEM te importeren.

U kunt zowel de klassieke interface als de interface met geoptimaliseerde aanrakingen gebruiken om elementen weer te geven en te zoeken. Afhankelijk van de interface, is hoe u zoekt lichtjes verschillend.

Wanneer u in een van beide UI zoekt, kunt u filteren op de volgende criteria (die hier in de voor aanraking geoptimaliseerde UI worden getoond):

**[!UICONTROL Enter keywords]** - U kunt elementen zoeken op naam. Wanneer u de trefwoorden zoekt die u invoert, begint de bestandsnaam met. Als u bijvoorbeeld het woord &quot;zwemmen&quot; typt, wordt gezocht naar namen van elementbestanden die met die letters in die volgorde beginnen. Vergeet niet op Enter te klikken nadat u de term hebt getypt om het element te zoeken.

![chlimage_1-93](assets/chlimage_1-93.png)

**[!UICONTROL Folder/path]** - De naam van de map die wordt weergegeven, is gebaseerd op de configuratie die u hebt geselecteerd. U kunt tot lagere niveaus boor door het omslagpictogram te klikken en een subomslag te selecteren, dan het controleteken te klikken om het te selecteren.

Als u een sleutelwoord ingaat en een omslag selecteert, AEM onderzoeken die omslag en om het even welke subfolders. Als u echter bij het zoeken geen trefwoorden invoert, worden bij het selecteren van de map alleen de elementen in die map weergegeven en worden er geen submappen opgenomen.

AEM zoekt standaard naar de geselecteerde map en naar alle submappen.

![chlimage_1-94](assets/chlimage_1-94.png)

**[!UICONTROL Type of Asset]** Selecteer Dynamic Media Classic om door Dynamic Media Classic-inhoud te bladeren. Deze optie is alleen beschikbaar als u Dynamic Media Classic al hebt geconfigureerd.

![chlimage_1-95](assets/chlimage_1-95.png)

**[!UICONTROL Configuration]** Als u meer dan één Dynamic Media Classic-configuratie hebt gedefinieerd in [!UICONTROL Cloud Services], kunt u deze hier selecteren. Hierdoor wordt de map gewijzigd op basis van de gekozen configuratie.

![chlimage_1-96](assets/chlimage_1-96.png)

**[!UICONTROL Asset type]** In de Dynamic Media Classic-browser kunt u de resultaten filteren en de volgende items opnemen: afbeeldingen, sjablonen, video&#39;s en adaptieve videosets. Als u geen elementtype selecteert, zoekt AEM standaard naar alle elementtypen.

![chlimage_1-97](assets/chlimage_1-97.png)

>[!NOTE]
>
>* Bij het zoeken naar video zoekt u op één vertoning. Resultaten retourneren de oorspronkelijke vertoning (alleen ast; .mp4) en de gecodeerde uitvoering.
>* Wanneer u in een adaptieve videoset zoekt, zoekt u in de map en in alle submappen, maar alleen als u een trefwoord aan de zoekopdracht hebt toegevoegd. Als u geen trefwoord hebt toegevoegd, zoekt AEM niet in de submappen.
>


**[!UICONTROL Publish Status]** U kunt filteren op elementen die zijn gebaseerd op de publicatiestatus: [!UICONTROL Published] of [!UICONTROL Unpublished]. Als u geen [!UICONTROL Publish status]AEM standaard alle publicatiestatussen doorzoeken.

![chlimage_1-98](assets/chlimage_1-98.png)
