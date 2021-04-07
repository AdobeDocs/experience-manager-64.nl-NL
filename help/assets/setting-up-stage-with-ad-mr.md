---
title: Een standaardpodium instellen met Autodesk Maya en Mental Ray
seo-title: Een standaardpodium instellen met Autodesk Maya en Mental Ray
description: Een standaardpodium instellen met Autodesk Maya en Mental Ray
seo-description: Een standaardpodium instellen met Autodesk Maya en Mental Ray
uuid: 3895fda6-29ae-46f5-b2bc-abc989808648
contentOwner: Rick Brough
topic-tags: 3D
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
discoiquuid: da8fc33b-84ae-4ead-87bb-5a7870a38b1f
exl-id: facd0411-8a3c-4b1a-af9d-0d59e0399b2c
feature: 3D-middelen
role: Administrator,Business Practitioner
translation-type: tm+mt
source-git-commit: 13eb1d64677f6940332a2eeb4d3aba2915ac7bba
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 0%

---

# Een standaardpodium instellen met Autodesk Maya en Mental Ray {#setting-up-a-standard-stage-with-autodesk-maya-and-mental-ray}

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

   Configureer de renderinstellingen met de volgende suggesties:

   * **[!UICONTROL Common]** tab

      Schakel het selectievakje **[!UICONTROL Alpha channel (mask)]** voor alle renderbare camera&#39;s uit.

   * **[!UICONTROL Quality]** tab

      * **[!UICONTROL Overall quality]** `- 0.5` of minder
      * **[!UICONTROL Indirect Diffuse (GI) Mode]** - `Final Gather`
      * **[!UICONTROL Filter Size]** - `2.0`, `2.0`
   * Render de scène op de standaardafbeeldingsformaten die u wilt gebruiken. Verfijn indien nodig de lichten of Renderinstellingen of voer beide handelingen uit om de gewenste resultaten te bereiken.

      Houd er rekening mee dat rendering met Mental Ray met behulp van op afbeeldingen gebaseerde belichting erg langzaam en CPU-intensief is. Adobe raadt u aan de laagste kwaliteitsinstellingen te configureren die nog steeds de gewenste renderkwaliteit kunnen produceren.


1. Verwijder de verwijzing die u in stap 2 hebt gemaakt.

1. Sla de scène op en sluit Autodesk Maya af.
1. Upload de scène in AEM en wacht tot de uploadverwerking is voltooid.

   Zie [Elementen uploaden](managing-assets-touch-ui.md#uploading-assets).

   Als Autodesk® Maya® niet is geconfigureerd op de AEM server, exporteert u een FBX van Maya en uploadt u deze naar AEM.

1. Elementeigenschappen openen in AEM. Stel **[!UICONTROL Title]** in op een geschikte tekenreeks die wordt weergegeven in de vervolgkeuzelijst **[!UICONTROL Stage Selector]**. Controleer of **[!UICONTROL Class]** is ingesteld op **[!UICONTROL 3D Stage]**. Opslaan en afsluiten.
1. Open een 3D-element, selecteer het nieuwe werkgebied en controleer of het naar behoren wordt weergegeven en weergegeven.
