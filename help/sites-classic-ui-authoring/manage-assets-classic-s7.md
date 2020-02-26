---
title: Dynamische media Klassieke eigenschappen aan uw pagina toevoegen
seo-title: Dynamische media Klassieke eigenschappen aan uw pagina toevoegen
description: Adobe Dynamic Media Classic is een gehoste oplossing voor het beheren, verbeteren, publiceren en leveren van geavanceerde media-elementen aan webpagina's, mobiele apparaten, e-mailprogramma's en displays en afdrukdocumenten via internet.
seo-description: Adobe Dynamic Media Classic is een gehoste oplossing voor het beheren, verbeteren, publiceren en leveren van geavanceerde media-elementen aan webpagina's, mobiele apparaten, e-mailprogramma's en displays en afdrukdocumenten via internet.
uuid: 66b9c150-c482-4a41-9772-fa39c135802c
contentOwner: Alva Ware-Bevacqui
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: authoring
content-type: reference
discoiquuid: 9ba95dce-a801-4a36-8798-45d295371b1b
translation-type: tm+mt
source-git-commit: ea520d6a1b714a21f2b3aeb36932a50d958bd162

---


# Dynamische media Klassieke eigenschappen aan uw pagina toevoegen{#adding-scene-features-to-your-page}

[Adobe Dynamic Media Classic](https://help.adobe.com/en_US/scene7/using/WS26AB0D9A-F51C-464e-88C8-580A5A82F810.html) is een gehoste oplossing voor het beheren, verbeteren, publiceren en leveren van rijke media-elementen aan web, mobiele apparaten, e-mail en displays en drukwerk via internet.

U kunt AEM-elementen die zijn gepubliceerd in Dynamic Media Classic, in verschillende viewers weergeven:

* In-/uitzoomen
* Flyout
* Video
* Afbeeldingssjabloon
* Afbeelding

U kunt digitale elementen rechtstreeks van AEM naar Dynamic Media Classic publiceren en u kunt digitale elementen van Dynamic Media Classic naar AEM publiceren.

In deze sectie wordt beschreven hoe u digitale elementen kunt publiceren van AEM naar Dynamic Media Classic en vice versa. Viewers worden ook in detail beschreven. Voor informatie bij het vormen van AEM voor Dynamische Klassiek van Media, zie het [Integreren van Dynamische Klassieke Media met AEM](/help/sites-administering/scene7.md).

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
>AEM publiceert asynchroon naar Dynamic Media Classic. Nadat u op **[!UICONTROL Publiceren]** hebt geklikt, kan het enkele seconden duren voordat uw element naar Dynamic Media Classic wordt gepubliceerd.


### Publiceren vanaf de middelenconsole {#publishing-from-the-assets-console}

Publiceren naar Dynamic Media Classic vanaf de middelenconsole als de elementen zich in een Classic-doelmap voor dynamische media bevinden:

1. Klik in de klassieke UI van AEM op **[!UICONTROL Digital Assets]** om toegang te krijgen tot het beheer van digitale elementen.

1. Selecteer het element (of de elementen) of de map in de doelmap die u naar Dynamic Media Classic wilt publiceren, klik met de rechtermuisknop en selecteer **[!UICONTROL Publiceren naar Dynamic Media Classic]**. U kunt ook Publiceren **[!UICONTROL naar dynamische media Klassiek]** selecteren in het menu **[!UICONTROL Extra] .

   ![chlimage_1-76](assets/chlimage_1-76.png)

1. Ga naar Dynamic Media Classic en bevestig dat de middelen beschikbaar zijn.

   >[!NOTE]
   >
   >Als de elementen zich niet in een gesynchroniseerde map Dynamic Media Classic bevinden, is **[!UICONTROL Publiceren naar Dynamic Media Classic]** in beide menu&#39;s zichtbaar maar uitgeschakeld.

### Publiceren vanuit een element {#publishing-from-an-asset}

U kunt een middel manueel publiceren zolang dat middel binnen de gesynchroniseerde Dynamische omslag van Media Classic wordt gevestigd.

>[!NOTE]
>
>Als het element zich niet in de dynamische gesynchroniseerde map Media Classic bevindt, is de koppeling naar **[!UICONTROL Publiceren naar Dynamic Media Classic]** niet beschikbaar.

**Publiceren naar Dynamic Media Classic rechtstreeks vanaf een digitaal middel**:

1. Klik in AEM op **[!UICONTROL Digitale elementen]** om toegang te krijgen tot het beheer van digitale elementen.

1. Dubbelklik om een element te openen.

1. Selecteer in het deelvenster Elementdetails de optie **[!UICONTROL Publiceren naar dynamische media Klassiek]**.

   ![screen_shot_2012-02-22at34828pm](assets/screen_shot_2012-02-22at34828pm.png)

1. **[!UICONTROL De koppeling verandert in]** Publiceren... en vervolgens **[!UICONTROL Gepubliceerd]**. Ga naar Dynamic Media Classic en bevestig dat het element beschikbaar is.

   >[!NOTE]
   >
   >Als het element niet correct wordt gepubliceerd naar Dynamic Media Classic, is de koppeling gewijzigd in **[!UICONTROL Publiceren mislukt]**. Als het element al is gepubliceerd naar Dynamic Media Classic, leest de koppeling **[!UICONTROL Opnieuw publiceren naar Dynamic Media Classic]**. Met Herpubliceren kunt u wijzigingen aanbrengen in een element in AEM en deze opnieuw publiceren.

### Elementen publiceren van buiten de CQ-doelmap {#publishing-assets-from-outside-the-cq-target-folder}

Adobe raadt u aan elementen alleen vanuit elementen in de doelmap Dynamic Media Classic naar Dynamic Media Classic te publiceren. Als u echter elementen moet uploaden vanuit een map buiten de doelmap, kunt u dat nog steeds doen door deze naar een *ad-hocmap* te uploaden in Dynamic Media Classic.

U doet dit door de configuratie van de Wolk voor de pagina te vormen waar de activa zullen verschijnen. Vervolgens voegt u een component Dynamic Media Classic aan de pagina toe en sleept u een element naar de component. Nadat de pagina-eigenschappen voor die pagina zijn ingesteld, wordt een koppeling **[!UICONTROL Publiceren naar Dynamic Media Classic]** weergegeven die het uploaden naar Dynamic Media Classic activeert wanneer deze optie is geselecteerd.

>[!NOTE]
>
>Elementen die zich in de ad-hocmap bevinden, worden niet weergegeven in de browser met dynamische media klassieke inhoud.

**Elementen publiceren die zich buiten de CQ-doelmap** bevinden:

1. Klik in AEM in de klassieke UI op **[!UICONTROL Websites]** en navigeer naar de webpagina waaraan u een digitaal element wilt toevoegen dat nog niet is gepubliceerd naar Dynamic Media Classic. (Normale regels voor paginaovererving zijn van toepassing.)

1. Klik in het hulpgedeelte op het pictogram **[!UICONTROL Pagina]** en klik vervolgens op **[!UICONTROL Pagina-eigenschappen]**.

1. Klik op **[!UICONTROL Cloud Services > Services toevoegen > Dynamic Media Classic (Scene7)**.
1. Selecteer in de vervolgkeuzelijst Adobe Dynamic Media Classic de gewenste configuratie en klik op **[!UICONTROL OK]**.

   ![chlimage_1-77](assets/chlimage_1-77.png)

1. Op de Web-pagina, voeg een Dynamische Klassieke component van Media (Scene7) aan de gewenste plaats op de pagina toe.
1. Sleep een digitaal element vanuit de zoeker naar de component. Er verschijnt een koppeling naar **[!UICONTROL Controleer de Klassieke publicatiestatus]** van dynamische media.

   >[!NOTE]
   >
   >Als het digitale element zich in de CQ-doelmap bevindt, wordt er geen koppeling naar **[!UICONTROL Check Dynamic Media Classic Publication Status]** weergegeven. De elementen worden eenvoudig in de component geplaatst.

   ![chlimage_1-78](assets/chlimage_1-78.png)

1. Klik op **[!UICONTROL Dynamische mediapublicatiestatus]** controleren. Als het element niet is gepubliceerd, publiceert AEM het element naar Dynamic Media Classic. Nadat het element is geüpload, bevindt het zich in de ad-hocmap. Standaard bevindt de ad-hocmap zich in de `name_of_the_company/CQ5_adhoc`map. U kunt dit, indien nodig [](#configuringtheadhocfolder)vormen.

   >[!NOTE]
   >
   >Als het element zich niet in een gesynchroniseerde map Dynamic Media Classic bevindt en er geen dynamische Media Classic-cloudconfiguratie is gekoppeld aan de huidige pagina, mislukt het uploaden.

## Dynamische media Klassieke (Scene7) componenten {#scene-components}

De volgende Dynamic Media Classic-componenten zijn beschikbaar in AEM:

* In-/uitzoomen
* Flyout (zoomen)
* Afbeeldingssjabloon
* Afbeelding
* Video

>[!NOTE]
>
>Deze componenten zijn niet standaard beschikbaar en moeten in de **[!UICONTROL ontwerpmodus]** worden geselecteerd voordat ze kunnen worden gebruikt.

Nadat ze in de **[!UICONTROL ontwerpmodus]** beschikbaar zijn gemaakt, kunt u de componenten net als alle andere AEM-componenten aan de pagina toevoegen. Elementen die nog niet zijn gepubliceerd naar Dynamic Media Classic, worden gepubliceerd naar Dynamic Media Classic als ze zich in een gesynchroniseerde map of op een pagina bevinden of met een dynamische Media Classic-cloudconfiguratie.

### Flash viewers end-of-life notice {#flash-viewers-end-of-life-notice}

Vanaf 31 januari 2017 werd de ondersteuning voor het Flash-viewerplatform door Adobe Dynamic Media Classic officieel beëindigd.

Zie Veelgestelde vragen over eindversies van de [Flash-viewer voor meer informatie over deze belangrijke wijziging](https://docs.adobe.com/content/docs/en/aem/6-1/administer/integration/marketing-cloud/scene7/flash-eol.html).

### Een dynamische Media Classic-component aan een pagina toevoegen {#adding-a-scene-component-to-a-page}

Het toevoegen van een dynamische Media Klassieke component aan een pagina is het zelfde als het toevoegen van een component aan om het even welke pagina. De dynamische Klassieke componenten van Media worden beschreven in detail in de volgende secties.

**Een dynamische Media Klassieke component/kijker aan een pagina in klassieke UI** toevoegen:

1. Open in AEM de pagina waaraan u de Klassieke component Dynamische media wilt toevoegen.

1. Als geen Dynamische Klassieke componenten van Media beschikbaar zijn, klik de heerser in sidekick om de wijze van het **[!UICONTROL Ontwerp]** in te gaan, **[!UICONTROL geef]** parsys uit, en selecteer alle **[!UICONTROL Dynamische componenten van Media Klassieke]** om hen ter beschikking te stellen.

1. Keer terug naar de modus **[!UICONTROL Bewerken]** door op het potlood in het zijpaneel te klikken.

1. Sleep een component van de **[!UICONTROL Dynamische Klassieke]** groep van Media in sidekick op de pagina in de gewenste plaats.

1. Klik op **[!UICONTROL Bewerken]** om de component te openen.

1. Bewerk de component naar wens en klik op **[!UICONTROL OK]** om de wijzigingen op te slaan.

### Interactieve weergaven toevoegen aan een responsieve website {#adding-interactive-viewing-experiences-to-a-responsive-website}

Het responsieve ontwerp voor uw middelen betekent dat uw middelen worden aangepast afhankelijk van waar ze worden weergegeven. Bij een responsief ontwerp worden dezelfde middelen op meerdere apparaten weergegeven.

**Een interactieve kijkervaring toevoegen aan een responsieve site in de klassieke gebruikersinterface**:

1. Meld u aan bij AEM en controleer of u Adobe Dynamic Media Classic Cloud Services [hebt](/help/sites-administering/scene7.md#configuring-scene-integration) geconfigureerd en of er dynamische Media Classic-componenten beschikbaar zijn.

   >[!NOTE]
   >
   >Als de Dynamische Klassieke componenten WCM van Media niet beschikbaar zijn, zeker om hen door de wijze van het[!UICONTROL Ontwerp] **toe te laten.

1. In een website waarvoor de dynamische Media Klassieke componenten zijn ingeschakeld, sleept u een **[!UICONTROL Afbeeldingsviewer]** naar de pagina.
1. Bewerk de component en pas de onderbrekingspunten aan op het tabblad Klassieke instellingen voor **[!UICONTROL dynamische media]** .

   ![chlimage_1-79](assets/chlimage_1-79.png)

1. Controleer of de viewers het formaat responsief wijzigen en of alle interacties zijn geoptimaliseerd voor computers, tablets en mobiele apparaten.

### Gemeenschappelijke instellingen voor alle dynamische media Klassieke componenten {#settings-common-to-all-scene-components}

Hoewel de configuratieopties variëren, zijn het volgende gemeenschappelijk voor alle Dynamische Klassieke componenten van Media:

* **[!UICONTROL Bestandsverwijzing]** - Blader naar een bestand waarnaar u wilt verwijzen. De verwijzing van het dossier toont activa URL en niet noodzakelijk de volledige Dynamische Klassieke URL van Media met inbegrip van de bevelen URL en de parameters. U kunt in dit veld geen klassieke URL-opdrachten en -parameters voor dynamische media toevoegen. Ze moeten worden toegevoegd via de bijbehorende functionaliteit in de component.
* **[!UICONTROL Breedte]** - Hiermee kunt u de breedte instellen.
* **[!UICONTROL Hoogte]** - Hiermee kunt u de hoogte instellen.

U stelt deze configuratieopties in door bijvoorbeeld te dubbelklikken op een Klassieke component Dynamische media wanneer u een **[!UICONTROL component Zoom]** opent:

![chlimage_1-80](assets/chlimage_1-80.png)

### In-/uitzoomen {#zoom}

De component HTML5 Zoom geeft een grotere afbeelding weer wanneer u op de knop + drukt.

Het element heeft onderaan zoomgereedschappen. Klik **[!UICONTROL +]** om te vergroten. Klik **[!UICONTROL -]** om te verminderen. Als u op **[!UICONTROL x]** of de zoompijl opnieuw instellen klikt, wordt de oorspronkelijke grootte van de afbeelding hersteld. Klik op de diagonale pijlen om deze op volledig scherm weer te geven. Klik op **[!UICONTROL Bewerken]** om de component te configureren. Met deze component, kunt u [montages vormen gemeenschappelijk voor alle Dynamische Klassieke componenten](#settings-common-to-all-scene-components)van Media.

![](do-not-localize/chlimage_1-5.png)

### Flyout {#flyout}

In de HTML5 Flyout-component wordt het element weergegeven als gesplitst scherm. het element in de opgegeven grootte laten staan; rechts wordt het zoomgedeelte weergegeven. Klik op **[!UICONTROL Bewerken]** om de component te configureren. Met deze component, kunt u [montages vormen gemeenschappelijk voor alle Dynamische Klassieke componenten](/help/sites-administering/scene7.md#settingscommontoalldynamicmediaclassiccomponents)van Media.

>[!NOTE]
>
>Als uw Flyout-component een aangepaste grootte gebruikt, wordt die aangepaste grootte gebruikt en wordt de responsieve instelling van de component uitgeschakeld.
>
>Als de component Flyout de standaardgrootte gebruikt, zoals die in de mening van het [!UICONTROL Ontwerp] wordt geplaatst, dan wordt de standaardgrootte gebruikt en de component rekt om de grootte van de paginalay-out met ontvankelijke opstelling van de toegelaten component aan te passen. Houd er echter rekening mee dat er een beperking geldt voor de responsieve installatie van de component. Wanneer u de component Flyout met ontvankelijke opstelling gebruikt, zou u het niet met volledige paginalrek moeten gebruiken. Anders kan de Flyout de rechterrand van de pagina overschrijden.

![chlimage_1-81](assets/chlimage_1-81.png)

### Image {#image}

Met de component Dynamische media Klassieke afbeelding kunt u dynamische media Klassieke functionaliteit toevoegen aan uw afbeeldingen, zoals Dynamische media Klassieke modifiers, afbeelding of viewer-voorinstellingen en verscherpen. De dynamische Media Klassieke afbeeldingscomponent is vergelijkbaar met andere afbeeldingscomponenten in AEM met speciale functionaliteit voor dynamische media Klassieke. In dit voorbeeld is de optie Dynamische media Klassieke URL op de afbeelding `&op_invert=1` toegepast.

![](do-not-localize/chlimage_1-6.png)

**[!UICONTROL Titel, Alt-tekst]** - Voeg op het tabblad [!UICONTROL Geavanceerd] een titel toe aan de afbeelding en alternatieve tekst voor gebruikers die afbeeldingen hebben uitgeschakeld.

**[!UICONTROL URL, Openen in]** - U kunt een middel van plaatsen om een verbinding te openen. Stel de **[!UICONTROL URL]** en **[!UICONTROL Openen in]** in om aan te geven of deze in hetzelfde venster of in een nieuw venster moet worden geopend.

![chlimage_1-82](assets/chlimage_1-82.png)

**[!UICONTROL Viewer-voorinstelling]** - Selecteer een bestaande viewervoorinstelling in het keuzemenu. Als de viewervoorinstelling die u zoekt niet zichtbaar is, moet u deze mogelijk zichtbaar maken. Zie Voorinstellingen [van viewers](/help/assets/managing-viewer-presets.md)beheren. U kunt geen viewervoorinstelling selecteren als u een voorinstelling voor afbeeldingen gebruikt en andersom.

**[!UICONTROL Dynamische Klassieke Configuratie]** van Media - selecteer de Dynamische Klassieke configuratie van Media u wilt gebruiken om actieve beeldvoorinstellingen van het het Publiceren Scene7 Systeem te halen.

**[!UICONTROL Voorinstelling]** afbeelding - Selecteer een bestaande voorinstelling voor de afbeelding in het keuzemenu. Als de voorinstelling die u zoekt niet zichtbaar is, moet u deze mogelijk zichtbaar maken. Zie [Voorinstellingen](/help/assets/managing-image-presets.md)voor afbeeldingen beheren. U kunt geen viewervoorinstelling selecteren als u een voorinstelling voor afbeeldingen gebruikt en andersom.

**[!UICONTROL Uitvoerindeling]** - Selecteer de uitvoerindeling van de afbeelding, bijvoorbeeld jpeg. Afhankelijk van de uitvoerindeling die u selecteert, hebt u mogelijk aanvullende configuratieopties. Zie [Voorinstellingen](/help/assets/managing-image-presets.md)voor afbeeldingen beheren.

**[!UICONTROL Verscherpen]** - Selecteer hoe u de afbeelding wilt verscherpen. Verscherpen wordt gedetailleerd uitgelegd in de [*Adobe Dynamic Media Classic Image Quality en de aanbevolen procedures *](/help/assets/assets/s7_sharpening_images.pdf)voor verscherpen.

**[!UICONTROL URL-wijzigingstoetsen]** - U kunt afbeeldingseffecten wijzigen door aanvullende opdrachten voor dynamische media in de klassieke afbeelding op te geven. Deze worden beschreven in Voorinstellingen [van het Beeld](/help/assets/managing-image-presets.md) beheren en de verwijzing [van het](https://marketing.adobe.com/resources/help/en_US/s7/is_ir_api/is_api/http_ref/c_command_reference.html)Bevel.

**[!UICONTROL Onderbrekingspunten]** - Als uw website reageert, wilt u de onderbrekingspunten aanpassen. Onderbrekingspunten moeten door komma&#39;s van elkaar worden gescheiden `,`.

### Afbeeldingssjabloon {#image-template}

[Dynamische media Klassieke afbeeldingssjablonen](https://help.adobe.com/en_US/scene7/using/WS60B68844-9054-4099-BF69-3DC998A04D3C.html) zijn gelaagde Photoshop-inhoud die naar Dynamic Media Classic is geïmporteerd, waarbij voor de inhoud en eigenschappen parameters zijn ingesteld voor variabiliteit. Met de sjablooncomponent **[!UICONTROL Afbeelding]** kunt u afbeeldingen importeren en de tekst dynamisch wijzigen in AEM. Daarnaast kunt u de sjablooncomponent **[!UICONTROL Afbeelding]** zodanig configureren dat waarden van de clientcontext worden gebruikt, zodat elke gebruiker de afbeelding op een gepersonaliseerde manier ervaart.

Klik op **[!UICONTROL Bewerken]** om de component te configureren. U kunt [montages vormen gemeenschappelijk voor alle Dynamische Klassieke componenten](/help/sites-administering/scene7.md#settingscommontoalldynamicmediaclassicscomponents) van Media evenals andere montages die in deze sectie worden beschreven.

![chlimage_1-83](assets/chlimage_1-83.png)

**[!UICONTROL Bestandsverwijzing, Breedte, Hoogte]** - Zie de instellingen die gelden voor alle Klassieke dynamische media-componenten.

>[!NOTE]
>
>Dynamische media Klassieke URL-opdrachten en -parameters kunnen niet rechtstreeks aan de URL van de bestandsverwijzing worden toegevoegd. Ze kunnen alleen worden gedefinieerd in de gebruikersinterface van de component in het deelvenster **[!UICONTROL Parameter]** .

**[!UICONTROL Titel, Alt-tekst]** op het tabblad [!UICONTROL Dynamische media - Klassieke afbeeldingssjabloon] : voeg een titel toe aan de afbeelding en alternatieve tekst voor gebruikers die afbeeldingen hebben uitgeschakeld.

**[!UICONTROL URL, Openen in]** U kunt een middel van plaatsen om een verbinding te openen. Stel de **[!UICONTROL URL]** in en **** Open in om aan te geven of u deze wilt openen in hetzelfde venster of in een nieuw venster.

![chlimage_1-84](assets/chlimage_1-84.png)

**[!UICONTROL Het deelvenster]** Parameter wanneer u een afbeelding importeert, worden de parameters vooraf gevuld met informatie uit de afbeelding. Als er geen inhoud is die dynamisch kan worden gewijzigd, is dit venster leeg.

![chlimage_1-85](assets/chlimage_1-85.png)

#### Tekst dynamisch wijzigen {#changing-text-dynamically}

Als u de tekst dynamisch wilt wijzigen, voert u nieuwe tekst in de velden in en klikt u op **[!UICONTROL OK]**. In dit voorbeeld is de **[!UICONTROL Prijs]** nu $50 en de verzendkosten 99 cent.

![chlimage_1-86](assets/chlimage_1-86.png)

De tekst in de afbeelding verandert. U kunt de oorspronkelijke waarde van de tekst herstellen door op **[!UICONTROL Herstellen]** naast het veld te klikken.

![chlimage_1-87](assets/chlimage_1-87.png)

#### Tekst wijzigen om de waarde van de context van een client weer te geven {#changing-text-to-reflect-the-value-of-a-client-context-value}

Als u een veld wilt koppelen aan de waarde van de clientcontext, klikt u op **[!UICONTROL Selecteren]** om het contextmenu van de client te openen, selecteert u de context van de client en klikt u op **[!UICONTROL OK]**. In dit voorbeeld verandert de naam op basis van de koppeling van de naam met de opgemaakte naam in het profiel.

![chlimage_1-88](assets/chlimage_1-88.png)

De tekst geeft de naam weer van de gebruiker die momenteel is aangemeld. U kunt de oorspronkelijke waarde van de tekst herstellen door op **[!UICONTROL Herstellen]** naast het veld te klikken.

![chlimage_1-89](assets/chlimage_1-89.png)

#### Een koppeling maken van de Klassieke afbeeldingssjabloon voor dynamische media {#making-the-scene-image-template-a-link}

**Een koppeling** maken van de Klassieke afbeeldingssjabloon voor dynamische media:

1. Klik op de pagina met de Dynamic Media Classic-afbeeldingssjablooncomponent op **[!UICONTROL Bewerken]**.
1. Voer in het veld **[!UICONTROL URL]** de URL in waarnaar gebruikers gaan wanneer op de afbeelding wordt geklikt. Selecteer in het veld **[!UICONTROL Openen in]** of u het doel wilt openen (een nieuw venster of hetzelfde venster).

   ![chlimage_1-90](assets/chlimage_1-90.png)

1. Click **[!UICONTROL OK]**.

### Video-component {#video-component}

De dynamische Media Klassieke **[!UICONTROL Video]** component (beschikbaar bij de Dynamische Klassieke sectie van Media van sidekick) gebruikt apparaat en bandbreedteopsporing om de juiste video aan elk scherm te dienen. Deze component is een HTML5-videospeler; het is één viewer die via meerdere kanalen kan worden gebruikt.

Deze kan worden gebruikt voor adaptieve videosets, één MP4-video of één F4V-video.

Zie [Video](/help/sites-classic-ui-authoring/manage-assets-classic-s7-video.md) voor meer informatie over hoe video&#39;s werken met Dynamic Media Classic-integratie. Zie ook hoe [de **Dynamic Media Classic-videocomponent** zich verhoudt tot de stichtingsvideocomponent ****](/help/sites-classic-ui-authoring/manage-assets-classic-s7-video.md).

![chlimage_1-91](assets/chlimage_1-91.png)

### Bekende beperkingen voor de video-component {#known-limitations-for-the-video-component}

Adobe DAM en WCM tonen of een hoofdvideo wordt geüpload. Deze proxy-elementen worden niet weergegeven:

* Dynamische gecodeerde weergaven van Media Classic
* Dynamische Media Classic adaptieve videosets

Wanneer u een adaptieve videoset gebruikt met de Dynamic Media Classic-videocomponent, moet u de grootte van de component aanpassen aan de afmetingen van de video.

## Browser voor dynamische media klassieke inhoud {#scene-content-browser}

Met de browser Dynamische media Klassieke inhoud kunt u inhoud van Dynamic Media Classic rechtstreeks in AEM weergeven. Als u de inhoudbrowser wilt openen, selecteert u in de Inhoudszoeker de optie **[!UICONTROL Dynamische media Klassiek]** in de gebruikersinterface met geoptimaliseerde aanrakingen of het pictogram **[!UICONTROL S7]** in de klassieke gebruikersinterface. De functionaliteit is identiek tussen beide gebruikersinterfaces.

Als u veelvoudige configuraties hebt, toont AEM door gebrek de [standaardconfiguratie](/help/sites-administering/scene7.md#configuring-a-default-configuration). U kunt verschillende configuraties direct selecteren in de Dynamische browser van de Inhoud van Media Klassieke in het drop-down menu.

>[!NOTE]
>
>* Middelen in de ad-hocmap worden niet weergegeven in de browser met dynamische media klassieke inhoud.
>* Wanneer [Beveiligde voorvertoning is ingeschakeld](/help/sites-administering/scene7.md#configuring-the-state-published-unpublished-of-assets-pushed-to-scene), worden zowel gepubliceerde als niet-gepubliceerde elementen op Dynamic Media Classic wel weergegeven in de browser met dynamische media Klassieke inhoud.
>* Als u geen **[!UICONTROL Dynamische Klassieke]** Media of het pictogram **[!UICONTROL S7]** als optie in inhoudbrowser ziet, moet u Dynamische Klassiek van Media [vormen om met AEM](/help/sites-administering/scene7.md)te werken.
   >
   >
* Voor video ondersteunt de Dynamic Media Classic-inhoudbrowser:
   >
   >
* Adaptieve videosets: container met alle video-uitvoeringen die nodig zijn voor naadloze weergave op meerdere schermen
>* Eén MP4-video
>* Single F4V-video


### Door inhoud bladeren in de klassieke gebruikersinterface {#browsing-content-in-the-classic-ui}

Blader door inhoud in Dynamic Media Classic door op het tabblad **[!UICONTROL S7]** te klikken.

U kunt de configuratie veranderen u toegang hebt door de configuratie te selecteren. De mappen veranderen, afhankelijk van de configuratie die u selecteert.

![chlimage_1-92](assets/chlimage_1-92.png)

Net als bij de zoekfunctie voor inhoud naar Middelen kunt u zoeken naar elementen en resultaten filteren. In tegenstelling tot de zoeker bij Elementen, bij het invoeren van een trefwoord op het tabblad **[!UICONTROL S7]** , *begint de bestandsnaam echter met* de tekenreeks die u hebt ingevoerd, in plaats van *het trefwoord in de bestandsnaam te bevatten* .

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

Het zoeken naar dynamische media Klassieke activa is gelijkaardig aan het zoeken van activa AEM behalve dat wanneer u zoekt u eigenlijk een verre mening van de activa in het Dynamische Klassieke systeem van Media ziet, eerder dan hen direct in AEM in te voeren.

U kunt zowel de klassieke interface als de interface met geoptimaliseerde aanrakingen gebruiken om elementen weer te geven en te zoeken. Afhankelijk van de interface, is hoe u zoekt lichtjes verschillend.

Wanneer u in een van beide UI zoekt, kunt u filteren op de volgende criteria (die hier in de voor aanraking geoptimaliseerde UI worden getoond):

**[!UICONTROL Trefwoorden]** invoeren - U kunt elementen zoeken op naam. Wanneer u de trefwoorden zoekt die u invoert, begint de bestandsnaam met. Als u bijvoorbeeld het woord &quot;zwemmen&quot; typt, wordt gezocht naar namen van elementbestanden die met die letters in die volgorde beginnen. Vergeet niet op Enter te klikken nadat u de term hebt getypt om het element te zoeken.

![chlimage_1-93](assets/chlimage_1-93.png)

**[!UICONTROL Map/pad]** - De naam van de map die wordt weergegeven, is gebaseerd op de configuratie die u hebt geselecteerd. U kunt tot lagere niveaus boor door het omslagpictogram te klikken en een subomslag te selecteren, dan het controleteken te klikken om het te selecteren.

Als u een trefwoord invoert en een map selecteert, doorzoekt AEM die map en eventuele submappen. Als u echter bij het zoeken geen trefwoorden invoert, worden bij het selecteren van de map alleen de elementen in die map weergegeven en worden er geen submappen opgenomen.

Standaard zoekt AEM naar de geselecteerde map en naar alle submappen.

![chlimage_1-94](assets/chlimage_1-94.png)

**[!UICONTROL Type element]** Selecteer Dynamic Media Classic om te bladeren naar dynamische media Klassieke inhoud. Deze optie is alleen beschikbaar als u al Dynamic Media Classic hebt geconfigureerd.

![chlimage_1-95](assets/chlimage_1-95.png)

**[!UICONTROL Configuratie]** Als u meer dan één Dynamische Klassieke configuratie van Media die in de Diensten [!UICONTROL van de]Wolk wordt bepaald hebt, kunt u het hier selecteren. Hierdoor wordt de map gewijzigd op basis van de gekozen configuratie.

![chlimage_1-96](assets/chlimage_1-96.png)

**[!UICONTROL Het type]** element in de Klassieke browser Dynamic Media kunt u de resultaten filteren en een van de volgende opties opnemen: afbeeldingen, sjablonen, video&#39;s en adaptieve videosets. Als u geen elementtype selecteert, worden standaard alle elementtypen doorzocht.

![chlimage_1-97](assets/chlimage_1-97.png)

>[!NOTE]
>
>* Bij het zoeken naar video zoekt u op één vertoning. Resultaten retourneren de oorspronkelijke uitvoering (alleen &amp;ast; .mp4) en de gecodeerde uitvoering.
>* Wanneer u in een adaptieve videoset zoekt, zoekt u in de map en in alle submappen, maar alleen als u een trefwoord aan de zoekopdracht hebt toegevoegd. Als u geen trefwoord hebt toegevoegd, doorzoekt AEM de submappen niet.
>



**[!UICONTROL Publicatiestatus]** U kunt filteren op elementen die zijn gebaseerd op de publicatiestatus: [!UICONTROL Gepubliceerd] of [!UICONTROL Niet gepubliceerd]. Als u geen [!UICONTROL publicatiestatus]selecteert, worden standaard alle publicatiestatussen doorzocht.

![chlimage_1-98](assets/chlimage_1-98.png)

