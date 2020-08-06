---
title: 3D-elementen weergeven
seo-title: 3D-elementen weergeven
description: The interactive 3D viewer is available from the asset details page in AEM. De viewer bevat onder andere een verzameling interactieve besturingselementen voor camera waarmee u het 3D-element kunt draaien, zoomen en pannen.
seo-description: The interactive 3D viewer is available from the asset details page in AEM. De viewer bevat onder andere een verzameling interactieve besturingselementen voor camera waarmee u het 3D-element kunt draaien, zoomen en pannen.
uuid: 06dea4d6-c33a-45da-a9a7-7caae9d1717a
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: authoring
content-type: reference
discoiquuid: 5e1e0039-670e-4051-9f2a-e88162482467
translation-type: tm+mt
source-git-commit: cdec5b3c57ce1c80c0ed6b5cb7650b52cf9bc340
workflow-type: tm+mt
source-wordcount: '1026'
ht-degree: 1%

---


# 3D-elementen weergeven{#viewing-d-assets}

The interactive 3D viewer is available from the asset details page in AEM. De viewer bevat onder andere een verzameling interactieve besturingselementen voor camera waarmee u het 3D-element kunt draaien, zoomen en pannen.

![chlimage_1-16](assets/chlimage_1-16.png)

Naast het gebruik van de standaardstadia in AEM 3D, kunt u stadia ook gebruiken die u in een derdetoepassing hebt gecreeerd en in AEM geupload.

Zie [Informatie over het gebruik van fasen in AEM 3D](/help/sites-classic-ui-authoring/classicui-stages-aem3d.md).

>[!NOTE]
>
>Als u een 3D-element wilt weergeven, moet uw apparaat of desktopbrowser WebGL-compatibel zijn. Also, the underlying graphics hardware must have sufficient capabilities and memory to render models of the desired size.

## Prestatieaspecten wanneer u 3D-elementen weergeeft {#performance-considerations-when-you-view-d-assets}

De tijd die nodig is om een 3D-element te openen in de paginaweergave met elementdetails, is afhankelijk van verschillende factoren. Deze factoren zijn onder andere:

* Bandbreedte en latentie aan de server.
* Modelgrootte (aantal vlakken).
* Aantal en grootte van kaarten.
* Complexiteit van het werkgebied. For example, the size of the IBL image.

Bovendien zijn de mogelijkheden van de clientcomputer, zoals een werkstation, laptop of mobiel aanraakapparaat, ook belangrijk om te overwegen wanneer u de camera interactief manipuleert. Een redelijk krachtig systeem met goede grafische mogelijkheden kan de interactieve 3D-kijkervaring vloeiender en gunstiger maken.

**3D-elementen** weergeven:

1. Zorg ervoor dat u 3D-elementen hebt geüpload naar AEM.

   Zie [Informatie over het uploaden en verwerken van 3D-elementen in AEM](/help/sites-classic-ui-authoring/classicui-upload-proc-3d.md).
1. From **[!UICONTROL Adobe Experience Manager]**, on the **[!UICONTROL Navigation]** page, tap **[!UICONTROL Assets]**.
1. Near the upper-right corner of the page, from the **[!UICONTROL View]** drop-down list, tap **[!UICONTROL Card View]**.

1. Navigate to a 3D asset that you want to view.
1. Tap the card of the 3D asset to open it in the asset details page.

1. Voer een van de volgende handelingen uit:

   * In the lower-right corner of the asset details page, use the camera control palette to change various views of the asset.

      If you use a non-touch input device without a scroll wheel, such as a classic Apple single-button mouse, you can still change the zoom or perspective of a 3D asset, while in each respective mode. U kunt de handeling uitvoeren door de `SHIFT`toets ingedrukt te houden terwijl u de muisknop ingedrukt houdt en omhoog of omlaag sleept.

      When using a touch pad on a typical notebook computer, it is often difficult to control the zoom or perspective behaviors with the two-finger gesture. In such cases, you can press and hold down `SHIFT`during the action. This kind of effort reduces the velocity of the pinch gesture and makes it easier to achieve the exact zoom level or perspective that you want. U kunt ook met één vinger omhoog of omlaag slepen terwijl op de `SHIFT`toets wordt gedrukt om het zoomgedrag of het perspectiefgedrag te beïnvloeden.
   <table> 
    <tbody> 
      <tr> 
      <td><strong>Naam camerabesturingselement</strong><br /> </td> 
      <td><strong>Beschrijving</strong></td> 
      </tr> 
      <tr> 
      <td><p>In-/uitzoomen</p> <p>or</p> <p>Perp</p> </td> 
      <td><p>Tik of klik om te schakelen tussen de modi Zoomen en Perspectief.</p> <p>Or, press and hold down the <code>ALT/OPTION</code> key during the action to temporarily toggle to Perspective<br /> mode. Laat de toets los om terug te keren naar de zoommodus.</p> 
        <ul> 
        <li><strong>Zoom</strong>-Dolly in and out behavior which moves the camera closer or further away from the asset<br /> that you are viewing. Zoom is the default behavior for the scroll wheel on a mouse (if available0, for two-finger pinch gestures on mobile devices, or when you hold down the Shift key while dragging up or down using the left mouse button.</li> 
        <li><strong>Perspectief</strong>- Hiermee wijzigt u de brandpuntsafstand (ook wel gezichtsveld genoemd) van de camera terwijl de relatieve grootte van het element in de weergave behouden blijft. Perspective is the alternate behavior for the scroll wheel (if available), for two-finger pinch gestures on mobile devices, or when you hold down the Shift key while dragging up or down using the left mouse button.</li> 
        </ul> </td> 
      </tr> 
      <tr> 
      <td><p>Draaien</p> <p>or</p> <p>Pan</p> </td> 
      <td><p>Tik of klik om te schakelen tussen de modi Draaien en Pannen.</p> <p>U kunt ook de <code>ALT/OPTION</code> toets ingedrukt houden tijdens de handeling om tijdelijk over te schakelen op de modus Pannen. Release the key to revert to Orbit mode.</p> 
        <ul> 
        <li><strong>Orbit</strong>- Moves the viewing camera on a sphere centered on a target point which is located near the center of the 3D asset be default. Draaien is het standaardgedrag voor het slepen van een knop naar links of het slepen van een knop met één druk op een mobiel apparaat.</li> 
        <li><strong>Pan</strong>-Moves the camera in the viewing plane. Het doelpunt wordt dienovereenkomstig verplaatst, zodat de camera bij volgende omloophandelingen om een nieuw doelpunt wordt verplaatst. Pannen is het alternatieve gedrag voor het slepen van de linkerknop en het slepen van één aanraking.</li> 
        </ul> </td> 
      </tr> 
      <tr> 
      <td><p>Onderzoek</p> <p>or</p> <p>Doel</p> </td> 
      <td><p>Tik of klik om te schakelen tussen de modi Onderzoek en Doel.</p> 
        <ul> 
        <li><strong>Onderzoek</strong>-Tik of klik om de wijze van het Doel in te gaan.</li> 
        <li><strong>Doel</strong>-Tik of klik ergens op een punt in het 3D-element om de weergave op dat deel van het element te centreren.<br /> Orbitacties gebruiken het nieuwe doelpunt.</li> 
        </ul> </td> 
      </tr> 
      <tr> 
      <td>Herstellen</td> 
      <td>Tik of klik om het doelpunt van de weergave te herstellen in het midden van het model. Met Herstellen wordt de camera<br /> ook dichter bij of verder weg geplaatst om het element in zijn geheel en met een redelijke weergavegrootte weer te geven.</td> 
      </tr> 
    </tbody> 
    </table>

1. Tik in de rechterbovenhoek van de pagina met elementdetails op het **[!UICONTROL Stage Selector]** pictogram. Selecteer een werkgebiednaam met de achtergrond en de belichting die u op het 3D-element wilt toepassen.

   ![](do-not-localize/chlimage_1-2.png)

   De stadia verstrekken milieu-achtergrond, grondvliegtuig, en verlichting-binnen waarin het 3D model wordt bekeken.

   Zie [Informatie over het gebruik van fasen in AEM 3D](/help/sites-classic-ui-authoring/classicui-stages-aem3d.md).

1. Tik in de rechterbovenhoek van de pagina met elementdetails op het **[!UICONTROL Camera Selector]** pictogram en selecteer een cameraweergave die u op het 3D-element wilt toepassen.

   ![](do-not-localize/chlimage_1-3.png)

   De stadia verstrekken vaak vooraf bepaalde camera&#39;s. U kunt de huidige camera opnieuw selecteren om de vooraf gedefinieerde instellingen te herstellen.

   Zie [Informatie over het gebruik van fasen in AEM 3D](/help/sites-classic-ui-authoring/classicui-stages-aem3d.md).

1. In the upper-right corner of the page, tap **[!UICONTROL Save]**.
1. Voer een van de volgende handelingen uit:

   * Het 3D-element renderen.

      Zie 3D- [elementen](/help/sites-classic-ui-authoring/classicui-rendering-3d.md)renderen.

   * Tik in de rechterbovenhoek van de pagina op **[!UICONTROL Close]** om terug te keren naar de middelenpagina.

