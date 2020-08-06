---
title: Werken met de component 3D-sites
seo-title: Werken met de component 3D-sites
description: AEM 3D bevat een AEM Sites-component die kan worden gebruikt om interactieve weergave van 3D-modellen op webpagina's te implementeren.
seo-description: AEM 3D bevat een AEM Sites-component die kan worden gebruikt om interactieve weergave van 3D-modellen op webpagina's te implementeren.
uuid: 4f06bab3-1e31-49ef-89e3-b26195966538
contentOwner: Rick Brough
topic-tags: 3D
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
content-type: reference
discoiquuid: 9017ab55-6d4a-4306-922f-223ab1b2504b
translation-type: tm+mt
source-git-commit: e2bb2f17035e16864b1dc54f5768a99429a3dd9f
workflow-type: tm+mt
source-wordcount: '1005'
ht-degree: 0%

---


# Werken met de component 3D-sites {#working-with-the-d-sites-component}

AEM 3D bevat een AEM Sites-component waarmee u interactieve weergave van 3D-modellen op webpagina&#39;s kunt implementeren.

Nadat u de 3D-component hebt toegevoegd, kunt u het 3D-element in die component [weergeven.](viewing-3d-assets.md)

## De 3D-component toevoegen aan de paginasjabloon {#adding-the-d-component-to-the-page-template}

U moet de 3D-component op de pagina inschakelen voordat u deze op een pagina kunt plaatsen. Zie Sjablonen [](/help/sites-authoring/templates.md#editing-a-template-layout-template-author) bewerken voor meer informatie over het inschakelen van componenten in sjablonen.

**De 3D-component toevoegen aan de paginasjabloon**:

1. Ga naar **[!UICONTROL Tools > General > Templates]**.

1. Navigeer naar de paginasjabloon waarin u de 3D-component wilt inschakelen en selecteer de sjabloon.

1. Tik **[!UICONTROL Edit]** om de sjabloon te openen.
1. Selecteer in de rechterbovenhoek van de pagina de **[!UICONTROL Structure]** modus in het keuzemenu als deze nog niet actief is.

   ![image2017-11-14_15-33-57](assets/image2017-11-14_15-33-57.png)

1. Tik in het **[!UICONTROL Layout Container]** gebied om het te selecteren.

1. Tik op de **[!UICONTROL Policy]** knop om het venster te openen **[!UICONTROL Policy Editor]**.
1. Selecteer in de **[!UICONTROL Properties]** sectie het **[!UICONTROL 3D]** vinkje en tik vervolgens **[!UICONTROL Done]** om de wijzigingen op te slaan en de **[!UICONTROL Policy Editor]** sectie te sluiten.

   U kunt de component 3D-sites nu op alle pagina&#39;s plaatsen die deze sjabloon gebruiken.

## De 3D-viewercomponent toevoegen aan een webpagina {#adding-the-d-viewer-component-to-a-web-page}

>[!CAUTION]
>
>Deze versie van AEM 3D ondersteunt slechts één instantie van de 3D-component op elke webpagina. Meerdere 3D-componenten op dezelfde pagina werken niet correct.

**De 3D-viewercomponent toevoegen aan een webpagina**:

1. Open AEM Sites en selecteer de webpagina waaraan u de 3D-component wilt toevoegen.

1. Tik op het pictogram **[!UICONTROL Edit]** (potlood) om de pagina in de paginaeditor te openen. Zorg ervoor dat de **[!UICONTROL Edit]** modus rechtsboven op de pagina is geselecteerd.

   ![image2017-11-14_15-44-40](assets/image2017-11-14_15-44-40.png)

1. Tik op de spoorkiezer om het zijpaneel te openen.

1. Tik op het pictogram met het plusteken om de **[!UICONTROL Components]** lijst te openen.

1. Sleep de **[!UICONTROL 3D Viewer]** component van de **[!UICONTROL Components]** lijst aan de plaats op de pagina waar u de 3D kijker wilt verschijnen.

## De 3D-component configureren {#configuring-the-d-component}

1. Selecteer in de AEM Sites-pagina-editor de **[!UICONTROL 3D Viewer]** component die u eerder aan de pagina hebt toegevoegd.

1. Tik op het **[!UICONTROL Configuration]** pictogram (moersleutel) om het dialoogvenster voor componentconfiguratie te openen.

   U kunt de volgende componenteigenschappen instellen:

   <table> 
    <tbody> 
    <tr> 
    <td>Eigenschap</td> 
    <td>Beschrijving</td> 
    <td>Toepasselijkheid</td> 
    </tr> 
    <tr> 
    <td>Hoogte (px)</td> 
    <td>Geef de gewenste hoogte van de 3D-component op in pixels. Als deze optie leeg blijft, is de standaardwaarde 600 pixels.</td> 
    <td> </td> 
    </tr> 
    <tr> 
    <td>Werkgebiednaam</td> 
    <td><p>Selecteer een 3D-werkgebied in de lijst met beschikbare stadia. Het werkgebied biedt achtergrond en belichting.</p> <p>Zie <a href="/help/assets/about-the-use-of-stages-in-aem-3d.md" target="_blank">Informatie over het gebruik van fasen in AEM 3D-sites</a>.</p> </td> 
    <td>Genegeerd voor Adobe Dimension-middelen.</td> 
    </tr> 
    <tr> 
    <td>Automatische centrifugesnelheid (rpm)</td> 
    <td><p>De 3D-viewer draait de camera continu na het laden en opnieuw instellen. Automatisch draaien wordt beëindigd wanneer de gebruiker een handmatige omdraaiactie start.</p> <p>U kunt de centrifugesnelheid in RPM opgeven met de volgende waarden:</p> 
        <ul> 
        <li>Een positieve waarde instellen op rechts draaien</li> 
        <li>Een negatieve waarde instellen op links draaien</li> 
        <li>Stel een waarde 0 in om automatisch draaien uit te schakelen.</li> 
        </ul> <p>De standaardwaarde is 3 RPM, gelijk aan 20 seconden per volledige omwenteling.<br /> <br /> <strong>Opmerking:</strong> De centrifugesnelheid neemt een framesnelheid van 60/sec aan. Deze snelheid wordt meestal bereikt met kleine tot middelgrote modellen op krachtigere grafische hardware. Grotere modellen of langzamere apparaten draaien automatisch met lagere snelheden.</p> </td> 
    <td>Genegeerd voor Adobe Dimension-middelen.</td> 
    </tr> 
    <tr> 
    <td>Kleur van navigatieknop</td> 
    <td>Gebruik de kleurkiezer om de primaire kleur voor de besturingsknoppen van de viewer te kiezen.</td> 
    <td>Genegeerd voor Adobe Dimension-assen.</td> 
    </tr> 
    <tr> 
    <td>Navigatieaanwijskleur</td> 
    <td>Gebruik de kleurkiezer om de aanwijskleur/geselecteerde kleur voor de besturingsknoppen van de viewer te kiezen.</td> 
    <td>Genegeerd voor Adobe Dimension-middelen.</td> 
    </tr> 
    <tr> 
    <td>Stalen tonen</td> 
    <td>Voor toekomstig gebruik.</td> 
    <td>Genegeerd voor Adobe Dimension-middelen.</td> 
    </tr> 
    <tr> 
    <td>GLTF-cameravoorinstellingen tonen</td> 
    <td>De voorinstellingen van de camera die aanwezig kunnen zijn in Adobe Dimension-elementen weergeven of verbergen.</td> 
    <td>Alleen voor Adobe Dimension-middelen.</td> 
    </tr> 
    <tr> 
    <td>GLTF-achtergrondkleur</td> 
    <td>Standaardachtergrondkleur als het 3D-model geen achtergrond bevat.</td> 
    <td>Alleen voor Adobe Dimension-middelen.</td> 
    </tr> 
    </tbody> 
   </table>

1. Tik op het vinkje om de wijzigingen op te slaan.

   Naast de instellingen die beschikbaar zijn in het dialoogvenster voor componentconfiguratie, is een aantal algemene configuratie-instellingen beschikbaar die kunnen worden gewijzigd door middel van de CRXDE Lite.
Zie [Geavanceerde configuratie-instellingen](advanced-config-3d.md) voor meer informatie over deze algemene instellingen.

## Een 3D-model toewijzen aan de component {#assigning-a-d-model-to-the-component}

1. Klik in de AEM Sites-pagina-editor op het **[!UICONTROL Assets]** pictogram om de lijst Elementen in het zijpaneel te openen.

1. Selecteer het **[!UICONTROL 3D Models]** filter om ongewenste elementtypen te verbergen.

   ![screen_shot_2017-12-11at124258](assets/screen_shot_2017-12-11at124258.png)

1. Zoek naar of blader aan 3D activa die u op de pagina wilt bekijken die wordt uitgegeven.

1. Sleep het 3D-element van de **[!UICONTROL Assets]** lijst naar de **[!UICONTROL 3D Viewer]** component die eerder op de pagina is geplaatst.

   Adobe Dimension-elementen worden gerenderd met behulp van nieuwe viewertechnologie die is gebaseerd op de open glTF-standaard, terwijl alle andere 3D-elementen afhankelijk zijn van de klassieke AEM 3D webGL-viewer. De component selecteert automatisch de juiste viewer op basis van het type van het 3D-model.

## Een webpagina met een 3D-component voorvertonen {#previewing-a-web-page-that-has-a-d-component}

In de **[!UICONTROL Edit]** modus van de webpagina wordt het 3D-model weergegeven door de 3D-component, maar interactie met het model is niet mogelijk.

U kunt een voorvertoning van de webpagina weergeven in de pagina-editor, met volledige toegang tot de functionaliteit van de 3D-component.

Zie ook 3D-elementen [weergeven in de 3D-component](viewing-3d-assets.md#viewing-d-assets-in-the-sites-d-component)Sites.

**Een voorvertoning weergeven van een webpagina met een 3D-component**:

1. Voer een van de volgende handelingen uit:

   * Klik rechtsboven op de pagina **[!UICONTROL Preview]** om de voorvertoningsmodus te activeren.
   * Verwijder `/edit.html` de URL van de pagina in de browser.

## De pagina en elementen publiceren {#publishing-the-page-and-assets}

Zie Elementen [](managing-assets-touch-ui.md) publiceren voor informatie over het publiceren van elementen. Zie Pagina&#39;s [](/help/sites-authoring/publishing-pages.md) publiceren voor informatie over het publiceren van pagina&#39;s.

>[!NOTE]
>
>Als u het **[!UICONTROL Publish Page]** menu-item in het **[!UICONTROL Page Information]** menu gebruikt, worden de pagina en alle afhankelijkheden van de primaire pagina gepubliceerd. Secundaire afhankelijkheden waarnaar mogelijk wordt verwezen door het 3D-model en/of het 3D-werkgebied, zoals structuurafbeeldingen en IBL-afbeeldingen, worden niet gepubliceerd wanneer u de pagina op deze manier publiceert.
>
>Adobe raadt u aan alle 3D-elementen en hun afhankelijkheden rechtstreeks vanuit AEM Assets te publiceren voordat u de webpagina publiceert die naar deze elementen verwijst.

