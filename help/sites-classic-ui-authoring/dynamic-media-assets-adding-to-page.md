---
title: Dynamic Media-assets aan pagina's toevoegen
seo-title: Adding Dynamic Media assets to pages
description: Als u de functionaliteit voor dynamische media wilt toevoegen aan elementen die u op uw websites gebruikt, kunt u de component Dynamic Media of Interactive Media rechtstreeks op de pagina toevoegen.
seo-description: To add the dynamic media functionality to assets you use on your websites, you can add the Dynamic Media or Interactive Media component directly on the page.
uuid: 650d0867-a079-4936-a466-55b7a30803a2
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: authoring
content-type: reference
discoiquuid: 331f4980-5193-4546-a22e-f27e38bb8250
exl-id: b498d54e-ff34-49a1-bfad-c6efbb6f75f4
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1605'
ht-degree: 2%

---

# Dynamic Media-assets aan pagina&#39;s toevoegen{#adding-dynamic-media-assets-to-pages}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Als u de Dynamic Media-functionaliteit wilt toevoegen aan elementen die u op uw websites gebruikt, kunt u de opdracht **[!UICONTROL Dynamic Media]** of **[!UICONTROL Interactive Media]** rechtstreeks op de pagina. U doet dit door in te voeren [!UICONTROL Design] en het inschakelen van de dynamische mediacomponenten. Vervolgens kunt u deze componenten aan de pagina toevoegen en assets aan de component toevoegen. De dynamische media en interactieve mediacomponenten zijn slim: ze weten of u een afbeelding of video toevoegt en de beschikbare opties veranderen dienovereenkomstig.

U voegt dynamische media-elementen rechtstreeks aan de pagina toe als u AEM gebruikt als uw WCM.

>[!NOTE]
>
>Afbeeldingen met hyperlinks zijn beschikbaar in het vak voor carrouselbanners.

## Een Dynamic Media-component aan een pagina toevoegen {#adding-a-dynamic-media-component-to-a-page}

Het toevoegen van [!UICONTROL Dynamic Media] of [!UICONTROL Interactive Media] aan een pagina toevoegen is hetzelfde als een component aan een pagina toevoegen. De [!UICONTROL Dynamic Media] en [!UICONTROL Interactive Media] De componenten worden in de volgende secties uitgebreid beschreven.

Een Dynamic Media-component/viewer toevoegen aan een pagina:

1. Open in AEM de pagina waaraan u de Dynamic Media-component wilt toevoegen.
1. Als er geen Dynamic Media-component beschikbaar is, klikt u op de liniaal in het dialoogvenster [!UICONTROL Sidekick] om binnen te gaan **[!UICONTROL Design]** modus, klikken **[!UICONTROL Edit]** parsys, en selecteer **[!UICONTROL Dynamic Media]** om de Dynamic Media-componenten beschikbaar te maken.

   >[!NOTE]
   >
   >Zie [Componenten configureren in ontwerpmodus](/help/sites-authoring/default-components-designmode.md) voor meer informatie .

1. Terug naar **[!UICONTROL Edit]** door op het potloodpictogram in het dialoogvenster [!UICONTROL Sidekick].
1. Sleep de **[!UICONTROL Dynamic Media]** of **[!UICONTROL Interactive Media]** uit de **[!UICONTROL Other]** op de gewenste locatie op de pagina te plaatsen.
1. Klikken **[!UICONTROL Edit]** om de component te openen.
1. [De component bewerken](#dynamic-media-component) indien nodig en klik op **[!UICONTROL OK]** om de wijzigingen op te slaan.

## Dynamic Media-componenten {#dynamic-media-components}

[!UICONTROL Dynamic Media] en [!UICONTROL Interactive Media] zijn beschikbaar in [!UICONTROL Sidekick] krachtens **[!UICONTROL Dynamic Media]**. U gebruikt de **[!UICONTROL Interactive Media]** voor interactieve elementen, zoals interactieve video, interactieve afbeeldingen of carrouselsets. Voor alle andere dynamische mediacomponenten gebruikt u de **[!UICONTROL Dynamic Media]** component.

![chlimage_1-71](assets/chlimage_1-71.png)

>[!NOTE]
>
>Deze componenten zijn niet standaard beschikbaar en moeten in de ontwerpmodus worden geselecteerd voordat ze kunnen worden gebruikt. [Nadat ze in de ontwerpmodus beschikbaar zijn gemaakt](/help/sites-authoring/default-components-designmode.md)kunt u de componenten aan de pagina toevoegen, net als elke andere AEM.

### Dynamic Media-component {#dynamic-media-component}

De Dynamic Media-component is slim. Afhankelijk van het feit of u een afbeelding of video toevoegt, hebt u verschillende opties. De component ondersteunt voorinstellingen voor afbeeldingen, op afbeeldingen gebaseerde viewers, zoals afbeeldingssets, centrifuges, gemengde mediasets en video. Bovendien reageert de viewer snel. De grootte van het scherm verandert dus automatisch op basis van de schermgrootte. Alle viewers zijn op HTML5 gebaseerde viewers.

>[!NOTE]
>
>Wanneer u de [!UICONTROL Dynamic Media] en **[!UICONTROL Dynamic Media Settings]** is leeg of u kunt een element niet correct toevoegen, controleer het volgende:
>
>* U hebt [Dynamic Media ingeschakeld](/help/assets/config-dynamic.md). Dynamic Media is standaard uitgeschakeld.
>* De afbeelding heeft een piramideTIFF-bestand. Afbeeldingen die zijn geïmporteerd voordat dynamische media is ingeschakeld, hebben geen TIFF-bestand met piramide.
>


#### Wanneer u met afbeeldingen werkt {#when-working-with-images}

De [!UICONTROL Dynamic Media] kunt u dynamische afbeeldingen toevoegen, zoals afbeeldingssets, centrifuges en gemengde mediasets. U kunt inzoomen, uitzoomen en, indien van toepassing, een afbeelding binnen een centrifugeset draaien of een afbeelding van een ander type set selecteren.

U kunt de viewervoorinstelling, afbeeldingsvoorinstelling of afbeeldingsindeling ook rechtstreeks in de component configureren. Als u een afbeelding responsief wilt maken, kunt u de onderbrekingspunten instellen of een responsieve voorinstelling voor de afbeelding toepassen.

![chlimage_1-72](assets/chlimage_1-72.png)

U kunt de volgende Dynamic Media-instellingen bewerken door op **[!UICONTROL Edit]** in de component en klik vervolgens op de knop **[!UICONTROL Dynamic Media Settings]** tab.

![chlimage_1-73](assets/chlimage_1-73.png)

>[!NOTE]
>
>Standaard is de afbeeldingscomponent voor dynamische media adaptief. Als u van het een vaste grootte wilt maken, plaats het in de component in **[!UICONTROL Advanced]** met de **[!UICONTROL Width]** en **[!UICONTROL Height]** eigenschappen.

**[!UICONTROL Viewer preset]** - Selecteer een bestaande viewervoorinstelling in het keuzemenu. Als de viewervoorinstelling die u zoekt niet zichtbaar is, moet u deze mogelijk zichtbaar maken. Zie [Viewer-voorinstellingen beheren](/help/assets/managing-viewer-presets.md). U kunt geen viewervoorinstelling selecteren als u een voorinstelling voor afbeeldingen gebruikt en andersom.

Dit is de enige beschikbare optie als u beeldreeksen, spin reeksen, of gemengde media reeksen bekijkt. De weergegeven viewervoorinstellingen zijn ook slim. Alleen relevante viewervoorinstellingen worden weergegeven.

**[!UICONTROL Image preset]** - Selecteer een bestaande voorinstelling voor de afbeelding in het keuzemenu. Als de voorinstelling die u zoekt niet zichtbaar is, moet u deze mogelijk zichtbaar maken. Zie [Voorinstellingen afbeelding beheren](/help/assets/managing-image-presets.md). U kunt geen viewervoorinstelling selecteren als u een voorinstelling voor afbeeldingen gebruikt en andersom.

Deze optie is niet beschikbaar als u afbeeldingssets, centrifuges of gemengde mediasets bekijkt.

**[!UICONTROL Image Modifiers]** - U kunt afbeeldingseffecten wijzigen door extra opdrachten voor afbeeldingen in te voeren. Deze worden beschreven in [Voorinstellingen afbeelding beheren](/help/assets/managing-viewer-presets.md) en de [Opdrachtverwijzing](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-serving-api/image-serving-api/http-protocol-reference/command-reference/c-command-reference.html).

Deze optie is niet beschikbaar als u afbeeldingssets, centrifuges of gemengde mediasets bekijkt.

**[!UICONTROL Breakpoints]** - Als u dit element gebruikt op een responsieve site, moet u de pagina-onderbrekingspunten toevoegen. Afbeeldingsonderbrekingspunten moeten door komma&#39;s (,) worden gescheiden. Deze optie werkt wanneer er geen hoogte of breedte is gedefinieerd in een voorinstelling voor afbeeldingen.

Deze optie is niet beschikbaar als u afbeeldingssets, centrifuges of gemengde mediasets bekijkt.

U kunt het volgende bewerken [!UICONTROL Advanced Settings] door te klikken **[!UICONTROL Edit]** in de component.

**[!UICONTROL Title]** - Wijzig de titel van de afbeelding.

**[!UICONTROL Alt Text]** - Voeg een titel aan de afbeelding toe voor gebruikers die afbeeldingen hebben uitgeschakeld.

Deze optie is niet beschikbaar als u afbeeldingssets, centrifuges of gemengde mediasets bekijkt.

**[!UICONTROL URL, Open in]** - U kunt een element instellen van om een koppeling te openen. Stel de **[!UICONTROL URL]** en **[!UICONTROL Open in]** om aan te geven of u deze in hetzelfde venster of in een nieuw venster wilt openen.

Deze optie is niet beschikbaar als u afbeeldingssets, centrifuges of gemengde mediasets bekijkt.

**[!UICONTROL Width and Height]** - Voer een waarde in pixels in als u wilt dat de afbeelding een vaste grootte heeft. Als u deze waarden niet invult, wordt het element adaptief.

#### Wanneer u werkt met video {#when-working-with-video}

Gebruik de [!UICONTROL Dynamic Media] om dynamische video toe te voegen aan uw webpagina&#39;s. Wanneer u de component bewerkt, kunt u een vooraf gedefinieerde videoviewer gebruiken om de video op de pagina af te spelen.

![chlimage_1-74](assets/chlimage_1-74.png)

U kunt het volgende bewerken [!UICONTROL Dynamic Media Settings] door te klikken **[!UICONTROL Edit]** in de component.

>[!NOTE]
>
>De Dynamic Media-videocomponent is standaard adaptief. Als u van het een vaste grootte wilt maken, plaats het in de component met **[!UICONTROL Width]** en **[!UICONTROL Height]** in de **[!UICONTROL Advanced]** tab.

**[!UICONTROL Viewer preset]** - Selecteer een bestaande voorinstelling voor een videoviewer in het keuzemenu. Als de viewervoorinstelling die u zoekt niet zichtbaar is, moet u deze mogelijk zichtbaar maken. Zie [Viewer-voorinstellingen beheren](/help/assets/managing-viewer-presets.md).

U kunt het volgende bewerken [!UICONTROL Advanced] instellingen door te klikken **[!UICONTROL Edit]** in de component.

**[!UICONTROL Title]** - Wijzig de titel van de video.

**[!UICONTROL Width and Height]** - Voer een waarde in pixels in als u wilt dat de video een vaste grootte heeft. Als u deze waarden niet invult, wordt het adaptief.

#### Beveiligde video leveren {#how-to-delivery-secure-video}

In AEM 6.2, wanneer u installeert [FP-13480](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq620/featurepack/cq-6.2.0-featurepack-13480)kunt u bepalen of een video wordt geleverd via een HTTPS-verbinding (Secure SSL) of een onveilige verbinding (HTTP). Standaard wordt het video-leveringsprotocol automatisch overgenomen van het protocol van de ingesloten webpagina. Als de webpagina via HTTPS wordt geladen, wordt de video ook via HTTPS geleverd. En omgekeerd, als de webpagina zich op HTTP bevindt, wordt de video geleverd via HTTP. In de meeste gevallen, is dit standaardgedrag fijn en er is geen behoefte om het even welke configuratieveranderingen aan te brengen. U kunt dit standaardgedrag echter negeren door het toe te voegen `VideoPlayer.ssl=on` aan het einde van een URL-pad of aan de lijst met andere parameters voor viewerconfiguratie in een ingesloten codefragment, om veilige videoverzending te forceren.

Voor meer informatie over veilige video-levering en het gebruik van de `VideoPlayer.ssl` configuratiekenmerk in uw URL-pad, zie [Beveiligde video-levering](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/library/viewers-aem-assets-dmc/video/c-html5-video-viewer-20-securevideodelivery.html) in de Referentiehandleiding voor viewers. Naast de videoviewer is beveiligde video-levering beschikbaar voor de viewer voor gemengde media en de interactieve videoviewer.

### Interactieve mediacomponent {#interactive-media-component}

De interactieve component van Media is voor die activa die interactiviteit op hen zoals hotspots of beeldkaarten hebben. Als u een interactieve afbeelding, interactieve video of carrouselbanner hebt, gebruikt u de opdracht **[!UICONTROL Interactive Media]** component.

De [!UICONTROL Interactive Media] is slim. Afhankelijk van het feit of u een afbeelding of video toevoegt, hebt u verschillende opties. Bovendien reageert de viewer snel. De grootte van het scherm verandert dus automatisch op basis van de schermgrootte. Alle viewers zijn op HTML5 gebaseerde viewers.

![chlimage_1-75](assets/chlimage_1-75.png)

U kunt het volgende bewerken **[!UICONTROL General]** instellingen door te klikken **[!UICONTROL Edit]** in de component.

**[!UICONTROL Viewer preset]** - Selecteer een bestaande viewervoorinstelling in het keuzemenu. Als de viewervoorinstelling die u zoekt niet zichtbaar is, moet u deze mogelijk zichtbaar maken. Voorinstellingen voor viewers moeten worden gepubliceerd voordat ze kunnen worden gebruikt. Zie Viewer-voorinstellingen beheren.

**[!UICONTROL Title]** - Wijzig de titel van de video.

**[!UICONTROL Width and Height]** - Voer een waarde in pixels in als u wilt dat de video een vaste grootte heeft. Als u deze waarden niet invult, wordt het adaptief.

U kunt het volgende bewerken **[!UICONTROL Add To Cart]** instellingen door te klikken **[!UICONTROL Edit]** in de component.

**[!UICONTROL Show Product Asset]** - Deze waarde is standaard geselecteerd. Het productelement toont een afbeelding van het product zoals gedefinieerd in de module Handel. Schakel het vinkje uit om het productelement niet weer te geven.

**[!UICONTROL Show Product Price]** - Deze waarde is standaard geselecteerd. De prijs van het product is de prijs van het object zoals gedefinieerd in de module Handel. Schakel het vinkje uit om de productprijs niet weer te geven.

**[!UICONTROL Show Product Form]** - Deze waarde is standaard niet geselecteerd. Het productformulier bevat alle productvarianten zoals grootte en kleur. Schakel het vinkje uit om de productvarianten niet weer te geven.
