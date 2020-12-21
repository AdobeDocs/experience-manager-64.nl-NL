---
title: 3D-elementen weergeven
seo-title: 3D-elementen weergeven
description: Meer informatie over de interactieve 3D-viewer die beschikbaar is op de pagina met elementdetails in AEM en over hoe u deze kunt gebruiken om 3D-elementen weer te geven.
seo-description: Meer informatie over de interactieve 3D-viewer die beschikbaar is op de pagina met elementdetails in AEM en over hoe u deze kunt gebruiken om 3D-elementen weer te geven.
uuid: 7d8133ac-3110-4979-8e19-e65090e791be
contentOwner: Rick Brough
topic-tags: 3D
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
discoiquuid: 65040923-a8a8-4e27-82c0-67a04348e238
translation-type: tm+mt
source-git-commit: 11b65cf2d180f04168d4c5d0929957c95a372e3c
workflow-type: tm+mt
source-wordcount: '1745'
ht-degree: 0%

---


# 3D-elementen weergeven {#viewing-d-assets}

>[!IMPORTANT]
>
>AEM 3D in AEM 6.4 wordt niet meer ondersteund. Adobe raadt u aan de functie 3D-elementen in [AEM te gebruiken als een Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/dynamicmedia/assets-3d.html) of [AEM 6.5.3 of hoger.](https://docs.adobe.com/content/help/en/experience-manager-65/assets/dynamic/assets-3d.html) om 3D-elementen weer te geven.

In dit document wordt beschreven hoe u 3D-elementen kunt weergeven in de elementdetails en hoe u elementen in de 3D-component kunt bekijken in sites.

## 3D-elementen weergeven op de pagina Elementdetails {#viewing-d-assets-in-the-asset-details-page}

De interactieve 3D-viewer is beschikbaar op de pagina met elementdetails in AEM. De viewer bevat onder andere een verzameling interactieve besturingselementen voor camera waarmee u het 3D-element kunt draaien, zoomen en pannen.

![chlimage_1-139](assets/chlimage_1-139.png)

Naast het gebruik van de standaardstadia in AEM 3D, kunt u stadia ook gebruiken die u in een derdetoepassing hebt gecreeerd en in AEM geupload.

Zie [Informatie over het gebruik van fasen in AEM 3D](about-the-use-of-stages-in-aem-3d.md).

>[!NOTE]
>
>Als u een 3D-element wilt weergeven, moet uw apparaat of desktopbrowser WebGL-compatibel zijn. Bovendien moet de onderliggende grafische hardware over voldoende mogelijkheden en geheugen beschikken om modellen van de gewenste grootte en complexiteit te renderen. Bepaalde voorvertoningsfuncties, zoals schaduw voor gieten, zijn niet in alle browsers beschikbaar.

### Prestatieaspecten wanneer u 3D-elementen weergeeft {#performance-considerations-when-you-view-d-assets}

De tijd die nodig is om een 3D-element te openen in de paginaweergave met elementdetails, is afhankelijk van verschillende factoren. Deze factoren zijn onder andere:

* Bandbreedte en latentie aan de server.
* Modelgrootte (aantal vlakken).
* Aantal en grootte van kaarten.
* Complexiteit van het werkgebied. Bijvoorbeeld de grootte van de IBL-afbeelding.

Bovendien zijn de mogelijkheden van de clientcomputer, zoals een werkstation, laptop of mobiel aanraakapparaat, ook belangrijk om te overwegen wanneer u de camera interactief manipuleert. Een redelijk krachtig systeem met goede grafische mogelijkheden kan de interactieve 3D-kijkervaring vloeiender en gunstiger maken.

**3D-elementen** weergeven:

1. Zorg ervoor dat u 3D-elementen hebt geüpload naar AEM.

   Zie [Informatie over het uploaden en verwerken van 3D-elementen in AEM](upload-processing-3d-assets.md).

1. Tik op **[!UICONTROL Assets]** op de pagina **[!UICONTROL Navigation]** vanaf AEM.
1. Tik in de rechterbovenhoek van de pagina in de vervolgkeuzelijst **[!UICONTROL View]** op **[!UICONTROL Card View]**.
1. Navigeer naar een 3D-element dat u wilt weergeven.
1. Tik op de kaart van het 3D-element om dit te openen op de pagina met elementdetails.
1. Voer een van de volgende handelingen uit:

   * Gebruik in de rechterbenedenhoek van de pagina met elementdetails het palet Camera om verschillende weergaven van het element te wijzigen.

      Als u een niet-aanraakinvoerapparaat gebruikt zonder schuifwiel, zoals een klassieke Apple Single-Button muis, kunt u het zoomen of perspectief van een 3D-element in elke respectievelijke modus nog steeds wijzigen. U kunt de handeling uitvoeren door de `SHIFT`toets ingedrukt te houden terwijl u de muisknop ingedrukt houdt en omhoog of omlaag sleept.

      Wanneer u een aanraakvlak gebruikt op een laptop die doorgaans een laptop is, is het vaak moeilijk om het zoomgedrag of het perspectiefgedrag te bepalen met een beweging met twee vingers. In dergelijke gevallen kunt u `SHIFT`tijdens de handeling ingedrukt houden. Dit soort inspanningen vermindert de snelheid van de knijpbeweging en maakt het eenvoudiger om het gewenste zoomniveau of perspectief te bereiken. U kunt ook met één vinger omhoog of omlaag slepen terwijl de toets `SHIFT`wordt ingedrukt om het zoomgedrag of het perspectiefgedrag te beïnvloeden.
   <table> 
    <tbody> 
      <tr> 
      <td><strong>Naam camerabesturingselement</strong><br /> </td> 
      <td><strong>Beschrijving</strong></td> 
      </tr> 
      <tr> 
      <td><p>In-/uitzoomen</p> <p>or</p> <p>Perp</p> </td> 
      <td><p>Tik of klik om te schakelen tussen de modi Zoomen en Perspectief.</p> <p>U kunt ook de <code>ALT/OPTION</code>-toets ingedrukt houden tijdens de handeling om tijdelijk over te schakelen op de modus Perspectief<br />. Laat de toets los om terug te keren naar de zoommodus.</p> 
      <ul> 
      <li><strong>Zoom</strong>-Dolly gedrag in en uit dat de camera dichter of verder weg van het <br /> materiaal beweegt dat u bekijkt. Zoomen is het standaardgedrag voor het schuifwiel op een muis (indien beschikbaar 0, voor knijpbewegingen met twee vingers op mobiele apparaten of wanneer u Shift ingedrukt houdt terwijl u omhoog of omlaag sleept met de linkermuisknop.</li> 
      <li><strong>Perspectief</strong> - Hiermee wijzigt u de brandpuntsafstand (ook wel gezichtsveld genoemd) van de camera terwijl de relatieve grootte van het element in de weergave behouden blijft. Perspectief is het alternatieve gedrag voor het schuifwiel (indien beschikbaar), voor knijpbewegingen met twee vingers op mobiele apparaten of wanneer u Shift ingedrukt houdt terwijl u omhoog of omlaag sleept met de linkermuisknop.</li> 
      </ul> </td> 
      </tr> 
      <tr> 
      <td><p>Draaien</p> <p>of</p> <p>Pannen</p> </td> 
      <td><p>Tik of klik om te schakelen tussen de modi Draaien en Pannen.</p> <p>U kunt ook de <code>ALT/OPTION</code>-toets tijdens de handeling ingedrukt houden om tijdelijk over te schakelen op de panmodus. Laat de toets los om terug te keren naar de draaien modus.</p> 
      <ul> 
      <li><strong>Draaien</strong> - Verplaatst de weergavecamera op een bol die gecentreerd is op een doelpunt dat zich dichtbij het midden van het 3D-element bevindt, als standaard. Draaien is het standaardgedrag voor het slepen van een knop naar links of het slepen van een knop met één druk op een mobiel apparaat.</li> 
      <li><strong>Pannen</strong> - Verplaatst de camera in het weergavevlak. Het doelpunt wordt dienovereenkomstig verplaatst, zodat de camera bij volgende omloophandelingen om een nieuw doelpunt wordt verplaatst. Pannen is het alternatieve gedrag voor het slepen van de linkerknop en het slepen van één aanraking.</li> 
      </ul> </td> 
      </tr> 
      <tr> 
      <td><p>Onderzoek</p> <p>of</p> <p>Doel</p> </td> 
      <td><p>Tik of klik om te schakelen tussen de modus Onderzoek en de modus Doel.</p> 
      <ul> 
      <li><strong>Onderzoek</strong>-Tik of klik om de wijze van het Doel in te gaan.</li> 
      <li><strong>Doel</strong>-Tik of klik ergens op een punt in het 3D-element om de weergave op dat deel van het element te centreren.<br /> Orbitacties gebruiken het nieuwe doelpunt.</li> 
      </ul> </td> 
      </tr> 
      <tr> 
      <td>Herstellen</td> 
      <td>Tik of klik om het doelpunt van de weergave te herstellen in het midden van het model. Met Herstellen wordt de camera <br /> ook dichter bij of verder weg geplaatst om het middel volledig en bij een redelijke weergavegrootte weer te geven.</td> 
      </tr> 
    </tbody> 
    </table>

   * Tik in de rechterbovenhoek van de pagina met elementdetails op het pictogram **[!UICONTROL Stage Selector]**. Selecteer een werkgebiednaam met de achtergrond en de belichting die u op het 3D-element wilt toepassen.

   ![chlimage_1-140](assets/chlimage_1-140.png)

   De stadia verstrekken milieu-achtergrond, grondvliegtuig, en verlichting-binnen waarin het 3D model wordt bekeken.

   Zie [Informatie over het gebruik van fasen in AEM 3D](about-the-use-of-stages-in-aem-3d.md).

   * Tik in de rechterbovenhoek van de pagina met elementdetails op het pictogram **[!UICONTROL Camera Selector]** en selecteer vervolgens een cameraweergave die u op het 3D-element wilt toepassen.

   ![chlimage_1-141](assets/chlimage_1-141.png)

   De stadia verstrekken vaak vooraf bepaalde camera&#39;s. U kunt de huidige camera opnieuw selecteren om de vooraf gedefinieerde instellingen te herstellen.

   Zie [Informatie over het gebruik van fasen in AEM 3D](about-the-use-of-stages-in-aem-3d.md).

1. Tik in de rechterbovenhoek van de pagina op **[!UICONTROL Save]**.
1. Voer een van de volgende handelingen uit:

   * Het 3D-element renderen.

      Zie [3D-elementen renderen](rendering-3d-assets.md).

   * Tik in de rechterbovenhoek van de pagina op **[!UICONTROL Close]** om terug te keren naar de pagina Middelen.

## 3D-elementen weergeven in de 3D-component Sites {#viewing-d-assets-in-the-sites-d-component}

>[!NOTE]
>
>Deze sectie is alleen van toepassing op de klassieke webGL-viewer die wordt gebruikt voor andere 3D-elementtypen dan Adobe Dimension.

Afhankelijk van het type apparaat hebt u op verschillende manieren toegang tot de functies van de 3D-component.

Raadpleeg de volgende secties voor meer informatie:

* [Aanraakschermapparaten](#touchscreen-devices)
* [Touchpad-apparaten](#touchpad-devices)
* [Muis- en trackbaltoestellen](#mouse-and-trackball-devices)

Zie ook [Een webpagina met een 3D-component voorvertonen](using-the-3d-sites-component.md#previewing-a-web-page-that-has-a-d-component).

![screen_shot_2017-12-11at145654](assets/screen_shot_2017-12-11at145654.png)

### Apparaten {#touchscreen-devices} voor aanraakschermen

Werken met 3D-componenten met apparaten met touchscreen:

1. Gebruik een sleep- of veegbeweging met één vinger om het gezichtspunt (&quot;camera&quot;) rond het object te verplaatsen (&quot;baan&quot;). U kunt het object vanuit elke gewenste richting bekijken.

1. Gebruik een knijpbeweging met twee vingers om de camera dichter bij of verder van het object te plaatsen. Deze actie is vergelijkbaar met in- en uitzoomen en u kunt details van het object controleren. U kunt ook de toetsen + of - ingedrukt houden om de camera dichter bij of verder weg van het object te verplaatsen.

1. Gebruik een slepen met twee vingers om de camera te pannen. Met deze actie verplaatst u de camera zijwaarts, zodat u verschillende delen van het object kunt bekijken terwijl u hebt ingezoomd. Of tik op de knop **[!UICONTROL Orbit/Pan Toggle]** om te schakelen naar de panmodus en sleep met één vinger om de camera te pannen. Tik op de knop **[!UICONTROL Orbit/Pan Toggle]** om terug te keren naar de modus **[!UICONTROL Orbit]**.

1. Tik **[!UICONTROL Reset Viewer]** om de camera opnieuw in te stellen. Met deze handeling wordt het object weer volledig weergegeven en wordt automatisch centrifugeren hervat als dit is ingeschakeld.

1. Tik **[!UICONTROL Full Screen]** om de modus Volledig scherm te activeren (indien ondersteund door het apparaat). Tik nogmaals op **[!UICONTROL Full Screen]** om de 3D-viewer te herstellen naar de modus Pagina ingesloten.

### Touchpad-apparaten {#touchpad-devices}

Werken met 3D-componenten met touchpad-apparaten:

1. Gebruik een sleep met één vinger terwijl u de knop (links) van het aanraakvlak ingedrukt houdt om het gezichtspunt (&quot;camera&quot;) rondom het object te verplaatsen (&quot;baan&quot;). U kunt het object vanuit elke gewenste richting bekijken.

1. Gebruik een slepen met twee vingers omlaag of omhoog met touchpad-knoppen omhoog om de camera dichter bij of verder weg van het object te plaatsen. Deze handeling is vergelijkbaar met in- of uitzoomen en het is mogelijk details op het object te inspecteren. U kunt ook op de knoppen **[!UICONTROL Zoom In]** of **[!UICONTROL Zoom Out]** klikken en deze ingedrukt houden om de camera dichter bij of verder weg van het object te verplaatsen.

1. Gebruik een sleep met één vinger terwijl u de toets **ALT/option** en de knop met het aanraakvlak (links) ingedrukt houdt om de camera te pannen. Met deze actie verplaatst u de camera zijwaarts, zodat u verschillende delen van het object kunt bekijken terwijl u hebt ingezoomd. U kunt ook op de knop **[!UICONTROL Orbit/Pan Toggle]** klikken om naar de modus **[!UICONTROL Pan]** te schakelen en vervolgens met één vinger slepen terwijl u de knop (links) ingedrukt houdt om de camera te pannen. Klik nogmaals op de knop **[!UICONTROL Orbit/Pan Toggle]** om terug te keren naar de modus **[!UICONTROL Orbit]**.

1. Klik **[!UICONTROL Reset Viewer]** om de camera opnieuw in te stellen. Met deze handeling wordt het object weer volledig weergegeven en wordt automatisch centrifugeren hervat als dit is ingeschakeld.

1. Klik **[!UICONTROL Full Screen]** om de modus Volledig scherm te activeren. Gebruik de **Escape**-toets op het toetsenbord of klik nogmaals **[!UICONTROL Full Screen]** om de 3D-viewer te herstellen naar de in pagina ingesloten modus.

### Muis- en trackball-apparaten {#mouse-and-trackball-devices}

Werken met 3D-onderdelen met muis- en trackball-apparaten:

1. Sleep terwijl u de linkermuisknop ingedrukt houdt om het gezichtspunt (&quot;camera&quot;) rond het object te verplaatsen (&quot;baan&quot;). U kunt het object vanuit elke gewenste richting bekijken.

1. Gebruik het schuifwiel om de camera dichter bij of verder van het object te plaatsen. Dit lijkt op in- of uitzoomen en u kunt details van het object controleren. U kunt ook op de knoppen **[!UICONTROL Zoom In]** of **[!UICONTROL Zoom Out]** klikken en deze ingedrukt houden om de camera dichter bij of verder weg van het object te verplaatsen.

1. Sleep terwijl u de toets **ALT/option** ingedrukt houdt en de linkermuisknop om de camera te pannen. Hierdoor wordt de camera zijwaarts verplaatst, zodat u tijdens het inzoomen naar verschillende delen van het object kunt kijken. U kunt ook op de knop **[!UICONTROL Orbit/Pan Toggle]** klikken om te schakelen naar de modus **[!UICONTROL Pan]** en vervolgens slepen terwijl u de linkermuisknop ingedrukt houdt om de camera te pannen. Klik opnieuw **[!UICONTROL Orbit/Pan Toggle]** om aan **[!UICONTROL Orbit]** wijze terug te keren.
1. Klik **[!UICONTROL Reset Viewer]** om de camera opnieuw in te stellen. Met deze handeling wordt het object weer volledig weergegeven en wordt automatisch centrifugeren hervat als dit is ingeschakeld.
1. Klik **[!UICONTROL Full Screen]** om de modus Volledig scherm te activeren. Gebruik de **[!UICONTROL Escape]**-toets op het toetsenbord of klik nogmaals **[!UICONTROL Full Screen]** om de 3D-viewer te herstellen naar de modus Pagina-ingesloten.

