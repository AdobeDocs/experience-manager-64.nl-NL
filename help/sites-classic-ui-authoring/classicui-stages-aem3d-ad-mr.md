---
title: Een standaardpodium instellen met Autodesk Maya en Mental Ray
seo-title: Een standaardpodium instellen met Autodesk Maya en Mental Ray
description: Leer hoe u een standaardpodium instelt met Autodesk Maya en Mental Ray.
seo-description: Leer hoe u een standaardpodium instelt met Autodesk Maya en Mental Ray.
uuid: 05c4858b-6261-4de3-a87a-03dd6bc519a4
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: authoring
content-type: reference
discoiquuid: f30c4039-3bbf-4d02-a9b5-bda6ccce16b9
translation-type: tm+mt
source-git-commit: e0ce860380a28a9dcaa6f8ce94ad278cdbe49fad
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 0%

---


# Een standaardpodium instellen met Autodesk Maya en Mental Ray{#setting-up-a-standard-stage-with-autodesk-maya-and-mental-ray}

1. Maak in Maya een nieuwe, lege scène.
1. Maak een (tijdelijke) verwijzing naar een representatief model. Zo kunt u de belichting gemakkelijker evalueren, camera&#39;s instellen en de renderer configureren.

1. Voeg zoals gewoonlijk lichten toe. AEM 3D ondersteunt momenteel de volgende typen licht:

   * Gerichte lichten
   * Spotlichten
   * Puntlichten

   Andere typen licht worden genegeerd of in een van de bovenstaande ondersteunde typen omgezet wanneer het werkgebied wordt geüpload naar AEM 3D. De omgezette types worden gebruikt wanneer u de activa bekijkt en wanneer u teruggeeft gebruikend ingebouwde snelle verfijnen renderer. De oorspronkelijke typen licht worden gebruikt bij rendering met Maya.

1. Maak indien nodig een grondvlak en pas een geschikt materiaal toe.

   Adobe raadt u aan een grondvlak in te stellen als enkelzijdig. Zo weet u zeker dat u het element in AEM 3D onder het element kunt weergeven zonder dat het grondvlak het element verbergt.

1. (Optioneel) Maak en configureer camera&#39;s.

   Laat de camera&#39;s &#39;uitkijken&#39; naar het midden van de scène waar het element wordt ingevoegd. Zorg ervoor dat u de camera&#39;s instelt op renderbaar.

1. Rendering instellen met Mental Ray.

   Configureer de **[!UICONTROL Render Settings]** met de volgende suggesties:

   * **[!UICONTROL Common]** tab

      Schakel het selectievakje **[!UICONTROL Alpha channel (mask)]** voor alle [!UICONTROL Renderable Cameras] uit.

   * **[!UICONTROL Quality]** tab

      * **[!UICONTROL Overall quality]** `- 0.5` of minder
      * **[!UICONTROL Indirect Diffuse (GI) Mode]** - `Final Gather`
      * **[!UICONTROL Filter Size]** - `2.0`, `2.0`
   * Render de scène op de standaardafbeeldingsformaten die u wilt gebruiken. Verfijn indien nodig de lichten, of [!UICONTROL Render settings], of doe allebei om de gewenste resultaten te bereiken.

      Houd er rekening mee dat rendering met Mental Ray met behulp van op afbeeldingen gebaseerde belichting erg langzaam en CPU-intensief is. Adobe raadt u aan de laagste kwaliteitsinstellingen te configureren die nog steeds de gewenste renderkwaliteit kunnen produceren.


1. Verwijder de verwijzing die u in stap 2 hebt gemaakt.
1. Sla de scène op en sluit Autodesk Maya af.
1. Upload de scène in AEM en wacht tot de uploadverwerking is voltooid.

   Zie [Elementen uploaden](/help/assets/managing-assets-touch-ui.md#uploading-assets).

   Als Autodesk® Maya® niet is geconfigureerd op de AEM server, exporteert u een FBX van Maya en uploadt u deze naar AEM.

1. Elementeigenschappen openen in AEM. Stel Titel in op een geschikte tekenreeks die wordt weergegeven in de vervolgkeuzelijst Werkgebiedkiezer. Controleer of **[!UICONTROL Class]** is ingesteld op **[!UICONTROL 3D Stage]**. Opslaan en afsluiten.
1. Open een 3D-element, selecteer het nieuwe werkgebied en controleer of het naar behoren wordt weergegeven en weergegeven.

