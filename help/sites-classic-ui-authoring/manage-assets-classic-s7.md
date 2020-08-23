---
title: Dynamische media Klassieke eigenschappen aan uw pagina toevoegen
seo-title: Dynamische media Klassieke eigenschappen aan uw pagina toevoegen
description: Adobe Dynamic Media Classic is een gehoste oplossing voor het beheren, verbeteren, publiceren en leveren van rijke media-elementen aan webpagina's, mobiele apparaten, e-mailprogramma's en displays en drukapparatuur met internetverbinding.
seo-description: Adobe Dynamic Media Classic is een gehoste oplossing voor het beheren, verbeteren, publiceren en leveren van rijke media-elementen aan webpagina's, mobiele apparaten, e-mailprogramma's en displays en drukapparatuur met internetverbinding.
uuid: 66b9c150-c482-4a41-9772-fa39c135802c
contentOwner: Alva Ware-Bevacqui
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: authoring
content-type: reference
discoiquuid: 9ba95dce-a801-4a36-8798-45d295371b1b
translation-type: tm+mt
source-git-commit: b698a1348df3ec2ab455c236422784d10cbcf7c2
workflow-type: tm+mt
source-wordcount: '3234'
ht-degree: 0%

---


# Dynamische media Klassieke eigenschappen aan uw pagina toevoegen{#adding-scene-features-to-your-page}

[Adobe Dynamic Media Classic](https://help.adobe.com/en_US/scene7/using/WS26AB0D9A-F51C-464e-88C8-580A5A82F810.html) is een gehoste oplossing voor het beheren, verbeteren, publiceren en leveren van rijke media-elementen aan web, mobiele apparaten, e-mail en displays en drukwerk via internet.

U kunt AEM elementen die zijn gepubliceerd in Dynamic Media Classic, in verschillende viewers weergeven:

* In-/uitzoomen
* Flyout
* Video
* Afbeeldingssjabloon
* Afbeelding

U kunt digitale elementen rechtstreeks van AEM naar Dynamic Media Classic publiceren en u kunt digitale elementen van Dynamic Media Classic naar AEM publiceren.

In deze sectie wordt beschreven hoe u digitale elementen kunt publiceren van AEM naar Dynamic Media Classic en omgekeerd. Viewers worden ook in detail beschreven. Voor informatie bij het vormen van AEM voor Dynamische Klassieke Media, zie het [Integreren van Dynamische Klassieke Media met AEM](/help/sites-administering/scene7.md).

Zie ook Afbeeldingskaarten [toevoegen](/help/assets/image-maps.md).

Raadpleeg de volgende secties voor meer informatie over het gebruik van videocomponenten met AEM:

* [Video](/help/sites-classic-ui-authoring/manage-assets-classic-s7-video.md)

>[!NOTE]
>
>Als de dynamische Klassieke activa van Media niet behoorlijk tonen, zorg ervoor dat de Dynamische media wordt [onbruikbaar gemaakt](/help/assets/config-dynamic.md#disabling-dynamic-media) en vernieuw dan de pagina.

## Handmatig publiceren naar Dynamic Media Classic vanaf elementen {#manually-publishing-to-scene-from-assets}

U kunt digitale elementen naar Dynamic Media Classic publiceren vanuit de middelenconsole in de klassieke gebruikersinterface of rechtstreeks vanuit het element.

>[!NOTE]
>
>AEM publiceert asynchroon naar Dynamic Media Classic. Nadat u hebt geklikt, kan het enkele seconden duren voordat uw element naar Dynamic Media Classic wordt gepubliceerd. **[!UICONTROL Publish]**


### Publiceren vanaf de middelenconsole {#publishing-from-the-assets-console}

Publiceren naar Dynamic Media Classic vanaf de middelenconsole als de elementen zich in een Classic-doelmap voor dynamische media bevinden:

1. Klik in de AEM klassieke UI op **[!UICONTROL Digital Assets]** om toegang te krijgen tot het beheer van digitale elementen.

1. Selecteer het element (of de elementen) of de map in de doelmap die u naar Dynamic Media Classic wilt publiceren, klik met de rechtermuisknop en selecteer **[!UICONTROL Publish to Dynamic Media Classic]**. U kunt ook een keuze maken **[!UICONTROL Publish to Dynamic Media Classic]** in het menu **[!UICONTROL Tools] .

   ![chlimage_1-76](assets/chlimage_1-76.png)

1. Ga naar Dynamic Media Classic en bevestig dat de middelen beschikbaar zijn.

   >[!NOTE]
   >
   >Als de elementen zich niet in een gesynchroniseerde dynamische map Media Classic bevinden, zijn **[!UICONTROL Publish to Dynamic Media Classic]** beide menu&#39;s zichtbaar maar uitgeschakeld.

### Publiceren vanuit een element {#publishing-from-an-asset}

U kunt een middel manueel publiceren zolang dat middel binnen de gesynchroniseerde Dynamische omslag van Media Classic wordt gevestigd.

>[!NOTE]
>
>Als het element niet in de gesynchroniseerde map Dynamic Media Classic staat, **[!UICONTROL Publish to Dynamic Media Classic]** is de koppeling naar dit element niet beschikbaar.

**Publiceren naar Dynamic Media Classic rechtstreeks vanaf een digitaal middel**:

1. Klik AEM **[!UICONTROL Digital Assets]** om toegang te krijgen tot de beheerder van digitale elementen.

1. Dubbelklik om een element te openen.

1. Selecteer **[!UICONTROL Publish to Dynamic Media Classic]** in het deelvenster Elementdetails.

   ![screen_shot_2012-02-22at34828pm](assets/screen_shot_2012-02-22at34828pm.png)

1. De koppeling verandert in **[!UICONTROL Publishing ...]** en dan **[!UICONTROL Published]**. Ga naar Dynamic Media Classic en bevestig dat het element beschikbaar is.

   >[!NOTE]
   >
   >Als het element niet correct wordt gepubliceerd naar Dynamic Media Classic, verandert de koppeling in **[!UICONTROL Publishing Failed]**. Als het element al is gepubliceerd naar Dynamic Media Classic, leest de koppeling **[!UICONTROL Re-Publish to Dynamic Media Classic]**. Met Herpubliceren kunt u wijzigingen aanbrengen in een element in AEM en deze opnieuw publiceren.

### Elementen publiceren van buiten de CQ-doelmap {#publishing-assets-from-outside-the-cq-target-folder}

Adobe raadt u aan om elementen alleen vanuit elementen in de Classic-doelmap voor dynamische media naar Dynamic Media Classic te publiceren. Als u echter elementen moet uploaden vanuit een map buiten de doelmap, kunt u dat nog steeds doen door deze naar een *ad-hocmap* te uploaden in Dynamic Media Classic.

U doet dit door de configuratie van de Wolk voor de pagina te vormen waar de activa zullen verschijnen. Vervolgens voegt u een component Dynamic Media Classic aan de pagina toe en sleept u een element naar de component. Nadat de pagina-eigenschappen voor die pagina zijn ingesteld, wordt een **[!UICONTROL Publish to Dynamic Media Classic]** koppeling weergegeven die bij selectie het uploaden naar Dynamic Media Classic activeert.

>[!NOTE]
>
>Elementen die zich in de ad-hocmap bevinden, worden niet weergegeven in de browser met dynamische media klassieke inhoud.

**Elementen publiceren die zich buiten de CQ-doelmap** bevinden:

1. In AEM in klassieke UI, klik **[!UICONTROL Websites]** en navigeer aan de Web-pagina die u een digitaal middel aan dat nog niet gepubliceerd aan Dynamische Klassiek van Media wilt toevoegen. (Normale regels voor paginaovererving zijn van toepassing.)

1. Klik in de assistent op het **[!UICONTROL Page]** pictogram en klik vervolgens op **[!UICONTROL Page Properties]**.

1. Klik op **[!UICONTROL Cloud Services]>[!UICONTROL Add services]>[!UICONTROL Dynamic Media Classic (Scene7)]**.
1. Selecteer in de vervolgkeuzelijst Klassieke Adobe Dynamic Media de gewenste configuratie en klik op **[!UICONTROL OK]**.

   ![chlimage_1-77](assets/chlimage_1-77.png)

1. Voeg op de webpagina een Dynamic Media Classic-component (Scene7) toe aan de gewenste locatie op de pagina.
1. Sleep een digitaal element vanuit de zoeker naar de component. Je ziet een link naar **[!UICONTROL Check Dynamic Media Classic Publication Status]**.

   >[!NOTE]
   >
   >Als het digitale element zich in de CQ-doelmap bevindt, wordt er geen koppeling naar **[!UICONTROL Check Dynamic Media Classic Publication Status]** weergegeven. De elementen worden eenvoudig in de component geplaatst.

   ![chlimage_1-78](assets/chlimage_1-78.png)

1. Klik op **[!UICONTROL Check Dynamic Media Classic Publication Status]**. Als het element niet is gepubliceerd, publiceert AEM het element naar Dynamic Media Classic. Nadat het element is geüpload, bevindt het zich in de ad-hocmap. Standaard bevindt de ad-hocmap zich in de `name_of_the_company/CQ5_adhoc`map. U kunt dit, indien nodig [](#configuringtheadhocfolder)vormen.

   >[!NOTE]
   >
   >Als het element zich niet in een gesynchroniseerde map Dynamic Media Classic bevindt en er geen dynamische Media Classic-cloudconfiguratie is gekoppeld aan de huidige pagina, mislukt het uploaden.

## Dynamic Media Classic (Scene7)-componenten {#scene-components}

De volgende Dynamic Media Classic-componenten zijn beschikbaar in AEM:

* In-/uitzoomen
* Flyout (zoomen)
* Afbeeldingssjabloon
* Afbeelding
* Video

>[!NOTE]
>
>Deze componenten zijn niet standaard beschikbaar en moeten in de **[!UICONTROL Design]** modus worden geselecteerd voordat ze kunnen worden gebruikt.

Nadat ze in de **[!UICONTROL Design]** modus beschikbaar zijn gemaakt, kunt u de componenten net als alle andere AEM aan de pagina toevoegen. Elementen die nog niet zijn gepubliceerd naar Dynamic Media Classic, worden gepubliceerd naar Dynamic Media Classic als ze zich in een gesynchroniseerde map of op een pagina bevinden of met een dynamische Media Classic-cloudconfiguratie.

### Flash viewers end-of-life notice {#flash-viewers-end-of-life-notice}

Met ingang van 31 januari 2017 is ondersteuning voor het Flash Adobe-viewerplatform officieel beëindigd door Dynamic Media Classic.

Zie [Flash Veelgestelde vragen over het einde van de levensduur van de viewer voor meer informatie over deze belangrijke wijziging](https://docs.adobe.com/content/docs/en/aem/6-1/administer/integration/marketing-cloud/scene7/flash-eol.html).

### Een dynamische Media Classic-component aan een pagina toevoegen {#adding-a-scene-component-to-a-page}

Het toevoegen van een dynamische Media Klassieke component aan een pagina is het zelfde als het toevoegen van een component aan om het even welke pagina. De dynamische Klassieke componenten van Media worden beschreven in detail in de volgende secties.

**Een dynamische Media Klassieke component/kijker aan een pagina in klassieke UI** toevoegen:

1. Open in AEM de pagina waaraan u de Klassieke component Dynamische media wilt toevoegen.

1. Als geen Dynamische Klassieke componenten van Media beschikbaar zijn, klik de heerser in sidekick om wijze in te gaan, **[!UICONTROL Design]** parsys te klikken, en alle **[!UICONTROL Edit]** **[!UICONTROL Dynamic Media Classic]** componenten te selecteren om hen beschikbaar te maken.

1. Ga terug naar de **[!UICONTROL Edit]** modus door te klikken op het potlood in het zijpaneel.

1. Sleep een component van de **[!UICONTROL Dynamic Media Classic]** groep in het hulpstuk op de pagina in de gewenste plaats.

1. Klik **[!UICONTROL Edit]** om de component te openen.

1. Bewerk de component naar wens en klik **[!UICONTROL OK]** om de wijzigingen op te slaan.

### Interactieve weergaven toevoegen aan een responsieve website {#adding-interactive-viewing-experiences-to-a-responsive-website}

Het responsieve ontwerp voor uw middelen betekent dat uw middelen worden aangepast afhankelijk van waar ze worden weergegeven. Bij een responsief ontwerp worden dezelfde middelen op meerdere apparaten weergegeven.

**Een interactieve kijkervaring toevoegen aan een responsieve site in de klassieke gebruikersinterface**:

1. Meld u aan bij AEM en zorg ervoor dat u de Klassieke Cloud Services [van Adobe Dynamic Media hebt](/help/sites-administering/scene7.md#configuring-scene-integration) geconfigureerd en dat de Klassieke componenten van Dynamic Media beschikbaar zijn.

   >[!NOTE]
   >
   >Als de Dynamische Klassieke componenten WCM van Media niet beschikbaar zijn, ben zeker om hen door wijze **[!UICONTROL Design] toe te laten.

1. Sleep een **[!UICONTROL Image]** viewer naar de pagina in een website waarvoor de Klassieke Dynamic Media-componenten zijn ingeschakeld.
1. Bewerk de component en pas de onderbrekingspunten op het **[!UICONTROL Dynamic Media Classic Settings]** tabblad aan.

   ![chlimage_1-79](assets/chlimage_1-79.png)

1. Controleer of de viewers het formaat responsief wijzigen en of alle interacties zijn geoptimaliseerd voor computers, tablets en mobiele apparaten.

### Gemeenschappelijke instellingen voor alle dynamische media Klassieke componenten {#settings-common-to-all-scene-components}

Hoewel de configuratieopties variëren, zijn het volgende gemeenschappelijk voor alle Dynamische Klassieke componenten van Media:

* **[!UICONTROL File Reference]** - Blader naar een bestand waarnaar u wilt verwijzen. De verwijzing van het dossier toont activa URL en niet noodzakelijk de volledige Dynamische Klassieke URL van Media met inbegrip van de bevelen URL en de parameters. U kunt in dit veld geen klassieke URL-opdrachten en -parameters voor dynamische media toevoegen. Ze moeten worden toegevoegd via de bijbehorende functionaliteit in de component.
* **[!UICONTROL Width]** - Hiermee kunt u de breedte instellen.
* **[!UICONTROL Height]** - Hiermee kunt u de hoogte instellen.

U stelt deze configuratieopties in door bijvoorbeeld te dubbelklikken op een Klassieke component van Dynamische media wanneer u een **[!UICONTROL Zoom]** component opent:

![chlimage_1-80](assets/chlimage_1-80.png)

### In-/uitzoomen {#zoom}

De component HTML5 Zoom geeft een grotere afbeelding weer wanneer u op de knop + drukt.

Het element heeft onderaan zoomgereedschappen. Klik **[!UICONTROL +]** om te vergroten. Klik **[!UICONTROL -]** om te reduceren. Als u op de zoompijl opnieuw instellen **[!UICONTROL x]** of klikt, wordt de oorspronkelijke grootte van de afbeelding hersteld. Klik op de diagonale pijlen om deze op volledig scherm weer te geven. Klik **[!UICONTROL Edit]** om de component te vormen. Met deze component, kunt u [montages vormen gemeenschappelijk voor alle Dynamische Klassieke componenten](#settings-common-to-all-scene-components)van Media.

![](do-not-localize/chlimage_1-5.png)

### Flyout {#flyout}

In de HTML5 Flyout-component wordt het element weergegeven als gesplitst scherm. het element in de opgegeven grootte laten staan; rechts wordt het zoomgedeelte weergegeven. Klik **[!UICONTROL Edit]** om de component te vormen. Met deze component, kunt u [montages vormen gemeenschappelijk voor alle Dynamische Klassieke componenten](/help/sites-administering/scene7.md#settingscommontoalldynamicmediaclassiccomponents)van Media.

>[!NOTE]
>
>Als uw Flyout-component een aangepaste grootte gebruikt, wordt die aangepaste grootte gebruikt en wordt de responsieve instelling van de component uitgeschakeld.
>
>Als de component Flyout de standaardgrootte gebruikt, zoals die in de [!UICONTROL Design] mening wordt geplaatst, dan wordt de standaardgrootte gebruikt en de componentenrek om de grootte van de paginalay-out met ontvankelijke opstelling van de toegelaten component aan te passen. Houd er echter rekening mee dat er een beperking geldt voor de responsieve installatie van de component. Wanneer u de component Flyout met ontvankelijke opstelling gebruikt, zou u het niet met volledige paginalrek moeten gebruiken. Anders kan de Flyout de rechterrand van de pagina overschrijden.

![chlimage_1-81](assets/chlimage_1-81.png)

### Image {#image}

Met de component Dynamische media Klassieke afbeelding kunt u dynamische media Klassieke functionaliteit toevoegen aan uw afbeeldingen, zoals Dynamische media Klassieke modifiers, afbeelding of viewer-voorinstellingen en verscherpen. De dynamische Media Klassieke afbeeldingscomponent is vergelijkbaar met andere afbeeldingscomponenten in AEM met speciale dynamische Media Klassieke functionaliteit. In dit voorbeeld is de optie Dynamische media Klassieke URL op de afbeelding `&op_invert=1` toegepast.

![](do-not-localize/chlimage_1-6.png)

**[!UICONTROL Title, Alt Text]** - Voeg op het [!UICONTROL Advanced] tabblad een titel toe aan de afbeelding en alternatieve tekst voor gebruikers met afbeeldingen uitgeschakeld.

**[!UICONTROL URL, Open in]** - U kunt een element instellen van om een koppeling te openen. Stel de opties in **[!UICONTROL URL]** en geef **[!UICONTROL Open in]** aan of u deze wilt openen in hetzelfde venster of in een nieuw venster.

![chlimage_1-82](assets/chlimage_1-82.png)

**[!UICONTROL Viewer preset]** - Selecteer een bestaande viewervoorinstelling in het keuzemenu. Als de viewervoorinstelling die u zoekt niet zichtbaar is, moet u deze mogelijk zichtbaar maken. Zie Voorinstellingen [van viewers](/help/assets/managing-viewer-presets.md)beheren. U kunt geen viewervoorinstelling selecteren als u een voorinstelling voor afbeeldingen gebruikt en andersom.

**[!UICONTROL Dynamic Media Classic Configuration]** - Selecteer de configuratie Dynamic Media Classic die u wilt gebruiken om actieve voorinstellingen voor afbeeldingen op te halen uit het Scene7 Publishing System.

**[!UICONTROL Image preset]** - Selecteer een bestaande voorinstelling voor de afbeelding in het keuzemenu. Als de voorinstelling die u zoekt niet zichtbaar is, moet u deze mogelijk zichtbaar maken. Zie [Voorinstellingen](/help/assets/managing-image-presets.md)voor afbeeldingen beheren. U kunt geen viewervoorinstelling selecteren als u een voorinstelling voor afbeeldingen gebruikt en andersom.

**[!UICONTROL Output Format]** - Selecteer de uitvoerindeling van de afbeelding, bijvoorbeeld JPEG. Afhankelijk van de uitvoerindeling die u selecteert, hebt u mogelijk aanvullende configuratieopties. Zie [Voorinstellingen](/help/assets/managing-image-presets.md)voor afbeeldingen beheren.

**[!UICONTROL Sharpening]** - Selecteer hoe u de afbeelding wilt verscherpen. Verscherpen wordt gedetailleerd uitgelegd in de Kwaliteit van dynamische media [*Adobe als afbeelding en in de Aanbevolen werkwijzen*](/help/assets/assets/s7_sharpening_images.pdf) voor verscherpen.

**[!UICONTROL URL Modifiers]** - U kunt afbeeldingseffecten wijzigen door aanvullende opdrachten voor dynamische media in de klassieke afbeelding op te geven. Deze worden beschreven in Voorinstellingen [van het Beeld](/help/assets/managing-image-presets.md) beheren en de verwijzing [van het](https://docs.adobe.com/content/help/en/dynamic-media-developer-resources/image-serving-api/image-serving-api/http-protocol-reference/command-reference/c-command-reference.html)Bevel.

**[!UICONTROL Breakpoints]** - Als uw website reageert, wilt u de onderbrekingspunten aanpassen. Onderbrekingspunten moeten door komma&#39;s van elkaar worden gescheiden `,`.

### Afbeeldingssjabloon {#image-template}

[Dynamische media Klassieke afbeeldingssjablonen](https://help.adobe.com/en_US/scene7/using/WS60B68844-9054-4099-BF69-3DC998A04D3C.html) zijn gelaagde Photoshop-inhoud die is geïmporteerd in Dynamic Media Classic, waar inhoud en eigenschappen zijn geparametereerd voor variabiliteit. Met de **[!UICONTROL Image template]** component kunt u afbeeldingen importeren en de tekst dynamisch in AEM wijzigen. Bovendien kunt u de **[!UICONTROL Image template]** component vormen om waarden van cliëntcontext te gebruiken, zodat elke gebruiker het beeld op een gepersonaliseerde manier ervaart.

Klik **[!UICONTROL Edit]** om de component te vormen. U kunt [montages vormen gemeenschappelijk voor alle Dynamische Klassieke componenten](/help/sites-administering/scene7.md#settingscommontoalldynamicmediaclassicscomponents) van Media evenals andere montages die in deze sectie worden beschreven.

![chlimage_1-83](assets/chlimage_1-83.png)

**[!UICONTROL File Reference, Width, Height]** - Zie de instellingen die gelden voor alle dynamische media Klassieke componenten.

>[!NOTE]
>
>Dynamische media Klassieke URL-opdrachten en -parameters kunnen niet rechtstreeks aan de URL van de bestandsverwijzing worden toegevoegd. Ze kunnen alleen worden gedefinieerd in de gebruikersinterface van de component in het **[!UICONTROL Parameter]** deelvenster.

**[!UICONTROL Title, Alt Text]** Voeg op het [!UICONTROL Dynamic Media Classic Image Template] tabblad een titel toe aan de afbeelding en alternatieve tekst voor gebruikers die afbeeldingen hebben uitgeschakeld.

**[!UICONTROL URL, Open in]** U kunt een middel van plaatsen om een verbinding te openen. Stel de opties in **[!UICONTROL URL]** en geef aan **[!UICONTROL Open in]** of u deze wilt openen in hetzelfde venster of in een nieuw venster.

![chlimage_1-84](assets/chlimage_1-84.png)

**[!UICONTROL Parameter Panel]** Wanneer u een afbeelding importeert, worden de parameters vooraf gevuld met informatie uit de afbeelding. Als er geen inhoud is die dynamisch kan worden gewijzigd, is dit venster leeg.

![chlimage_1-85](assets/chlimage_1-85.png)

#### Tekst dynamisch wijzigen {#changing-text-dynamically}

Als u de tekst dynamisch wilt wijzigen, voert u nieuwe tekst in de velden in en klikt u op **[!UICONTROL OK]**. In dit voorbeeld **[!UICONTROL Price]** is de verzendkosten nu $50 en de verzendkosten 99 cent.

![chlimage_1-86](assets/chlimage_1-86.png)

De tekst in de afbeelding verandert. U kunt de oorspronkelijke waarde van de tekst herstellen door op **[!UICONTROL Reset]** naast het veld te klikken.

![chlimage_1-87](assets/chlimage_1-87.png)

#### Tekst wijzigen om de waarde van de context van een client weer te geven {#changing-text-to-reflect-the-value-of-a-client-context-value}

Als u een veld wilt koppelen aan de waarde van de clientcontext, klikt u **[!UICONTROL Select]** om het contextmenu van de client te openen, selecteert u de context van de client en klikt u op **[!UICONTROL OK]**. In dit voorbeeld verandert de naam op basis van de koppeling van de naam met de opgemaakte naam in het profiel.

![chlimage_1-88](assets/chlimage_1-88.png)

De tekst geeft de naam weer van de gebruiker die momenteel is aangemeld. U kunt de oorspronkelijke waarde van de tekst herstellen door op **[!UICONTROL Reset]** naast het veld te klikken.

![chlimage_1-89](assets/chlimage_1-89.png)

#### Een koppeling maken van de Klassieke afbeeldingssjabloon voor dynamische media {#making-the-scene-image-template-a-link}

**Een koppeling** maken van de Klassieke afbeeldingssjabloon voor dynamische media:

1. Klik op de pagina met de Dynamic Media Classic-afbeeldingssjablooncomponent **[!UICONTROL Edit]**.
1. Voer in het **[!UICONTROL URL]** veld de URL in waarnaar gebruikers gaan wanneer op de afbeelding wordt geklikt. Selecteer in het **[!UICONTROL Open in]** veld of u het doel wilt openen (een nieuw venster of hetzelfde venster).

   ![chlimage_1-90](assets/chlimage_1-90.png)

1. Klik op **[!UICONTROL OK]**.

### Video-component {#video-component}

De dynamische **[!UICONTROL Video]** component van Media Classic (beschikbaar bij de Dynamische sectie van Media Classic van sidekick) gebruikt apparaat en bandbreedtedetectie om de juiste video aan elk scherm te leveren. Deze component is een HTML5-videospeler; het is één viewer die via meerdere kanalen kan worden gebruikt.

Deze kan worden gebruikt voor adaptieve videosets, één MP4-video of één F4V-video.

Zie [Video](/help/sites-classic-ui-authoring/manage-assets-classic-s7-video.md) voor meer informatie over hoe video&#39;s werken met Dynamic Media Classic-integratie. Zie ook hoe [de **Dynamic Media Classic-videocomponent** zich verhoudt tot de stichtingsvideocomponent ****](/help/sites-classic-ui-authoring/manage-assets-classic-s7-video.md).

![chlimage_1-91](assets/chlimage_1-91.png)

### Bekende beperkingen voor de video-component {#known-limitations-for-the-video-component}

Adobe DAM en WCM laten zien of een master video is geüpload. Deze proxy-elementen worden niet weergegeven:

* Dynamische gecodeerde weergaven van Media Classic
* Dynamische Media Classic adaptieve videosets

Wanneer u een adaptieve videoset gebruikt met de Dynamic Media Classic-videocomponent, moet u de grootte van de component aanpassen aan de afmetingen van de video.

## Browser voor dynamische media klassieke inhoud {#scene-content-browser}

Met de browser Dynamische media Klassieke inhoud kunt u inhoud van Dynamic Media Classic rechtstreeks in AEM bekijken. Als u de inhoudbrowser wilt openen, selecteert u in de zoekfunctie voor inhoud de optie **[!UICONTROL Dynamic Media Classic]** in de gebruikersinterface met geoptimaliseerde aanrakingen of het **[!UICONTROL S7]** pictogram in de klassieke gebruikersinterface. De functionaliteit is identiek tussen beide gebruikersinterfaces.

Als u veelvoudige configuraties hebt, AEM door gebrek toont de [standaardconfiguratie](/help/sites-administering/scene7.md#configuring-a-default-configuration). U kunt verschillende configuraties direct selecteren in de Dynamische browser van de Inhoud van Media Klassieke in het drop-down menu.

>[!NOTE]
>
>* Middelen in de ad-hocmap worden niet weergegeven in de browser met dynamische media klassieke inhoud.
>* Wanneer [Beveiligde voorvertoning is ingeschakeld](/help/sites-administering/scene7.md#configuring-the-state-published-unpublished-of-assets-pushed-to-scene), worden zowel gepubliceerde als niet-gepubliceerde elementen op Dynamic Media Classic wel weergegeven in de browser met dynamische media Klassieke inhoud.
>* Als u **[!UICONTROL Dynamic Media Classic]** of het **[!UICONTROL S7]** pictogram niet als optie in inhoudbrowser ziet, moet u Dynamische Klassiek van Media [vormen om met AEM](/help/sites-administering/scene7.md)te werken.

   >
   >
* Voor video ondersteunt de Dynamic Media Classic-inhoudbrowser:
   >
   >
* Adaptieve videosets: container met alle video-uitvoeringen die nodig zijn voor naadloze weergave op meerdere schermen
>* Eén MP4-video
>* Single F4V-video


### Door inhoud bladeren in de klassieke gebruikersinterface {#browsing-content-in-the-classic-ui}

Blader door inhoud in Dynamic Media Classic door op het **[!UICONTROL S7]** tabblad te klikken.

U kunt de configuratie veranderen u toegang hebt door de configuratie te selecteren. De mappen veranderen, afhankelijk van de configuratie die u selecteert.

![chlimage_1-92](assets/chlimage_1-92.png)

Net als bij de zoekfunctie voor inhoud naar Middelen kunt u zoeken naar elementen en resultaten filteren. In tegenstelling tot de zoeker Elementen, begint de bestandsnaam bij het invoeren van een trefwoord op het **[!UICONTROL S7]** tabblad met *de tekenreeks die u hebt ingevoerd, in plaats van* het trefwoord in de bestandsnaam te bevatten ** .

Elementen worden standaard weergegeven op bestandsnaam. U kunt resultaten ook filteren op type element.

>[!NOTE]
>
>Voor video, steunt Dynamische Media Klassieke inhoudbrowser van WCM:
>
>* Adaptieve videosets: container met alle video-uitvoeringen die nodig zijn voor naadloze weergave op meerdere schermen
>* Eén MP4-video
>* Single F4V-video

>



### Dynamische media Klassieke elementen zoeken met de inhoudbrowser {#searching-for-scene-assets-with-the-content-browser}

Het zoeken naar dynamische media Klassieke activa is gelijkaardig aan het zoeken AEM activa behalve dat wanneer u zoekt u eigenlijk een verre mening van de activa in het Dynamische Klassieke systeem van Media ziet, eerder dan hen direct in AEM in te voeren.

U kunt zowel de klassieke interface als de interface met geoptimaliseerde aanrakingen gebruiken om elementen weer te geven en te zoeken. Afhankelijk van de interface, is hoe u zoekt lichtjes verschillend.

Wanneer u in een van beide UI zoekt, kunt u filteren op de volgende criteria (die hier in de voor aanraking geoptimaliseerde UI worden getoond):

**[!UICONTROL Enter keywords]** - U kunt elementen zoeken op naam. Wanneer u de trefwoorden zoekt die u invoert, begint de bestandsnaam met. Als u bijvoorbeeld het woord &quot;zwemmen&quot; typt, wordt gezocht naar namen van elementbestanden die met die letters in die volgorde beginnen. Vergeet niet op Enter te klikken nadat u de term hebt getypt om het element te zoeken.

![chlimage_1-93](assets/chlimage_1-93.png)

**[!UICONTROL Folder/path]** - De naam van de map die wordt weergegeven, is gebaseerd op de configuratie die u hebt geselecteerd. U kunt tot lagere niveaus boor door het omslagpictogram te klikken en een subomslag te selecteren, dan het controleteken te klikken om het te selecteren.

Als u een sleutelwoord ingaat en een omslag selecteert, AEM onderzoeken die omslag en om het even welke subfolders. Als u echter bij het zoeken geen trefwoorden invoert, worden bij het selecteren van de map alleen de elementen in die map weergegeven en worden er geen submappen opgenomen.

AEM zoekt standaard naar de geselecteerde map en naar alle submappen.

![chlimage_1-94](assets/chlimage_1-94.png)

**[!UICONTROL Type of Asset]** Selecteer Dynamische media Klassiek om door dynamische media Klassieke inhoud te bladeren. Deze optie is alleen beschikbaar als u al Dynamic Media Classic hebt geconfigureerd.

![chlimage_1-95](assets/chlimage_1-95.png)

**[!UICONTROL Configuration]** Als u meer dan één Dynamische die configuratie van Media Klassiek binnen hebt wordt bepaald, kunt u het hier selecteren. [!UICONTROL Cloud Services] Hierdoor wordt de map gewijzigd op basis van de gekozen configuratie.

![chlimage_1-96](assets/chlimage_1-96.png)

**[!UICONTROL Asset type]** In Dynamische Media Klassieke browser, kunt u resultaten filtreren om het even welke volgend op te nemen: afbeeldingen, sjablonen, video&#39;s en adaptieve videosets. Als u geen elementtype selecteert, zoekt AEM standaard naar alle elementtypen.

![chlimage_1-97](assets/chlimage_1-97.png)

>[!NOTE]
>
>* Bij het zoeken naar video zoekt u op één vertoning. Resultaten retourneren de oorspronkelijke uitvoering (alleen &amp;ast; .mp4) en de gecodeerde uitvoering.
>* Wanneer u in een adaptieve videoset zoekt, zoekt u in de map en in alle submappen, maar alleen als u een trefwoord aan de zoekopdracht hebt toegevoegd. Als u geen trefwoord hebt toegevoegd, zoekt AEM niet in de submappen.

>



**[!UICONTROL Publish Status]** U kunt filteren op elementen die zijn gebaseerd op de publicatiestatus: [!UICONTROL Published] of [!UICONTROL Unpublished]. Als u niets selecteert [!UICONTROL Publish status], zoekt AEM standaard alle publicatiestatussen.

![chlimage_1-98](assets/chlimage_1-98.png)

