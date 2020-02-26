---
title: Een IBL-podium instellen met Autodesk Maya en Mental Ray
seo-title: Een IBL-podium instellen met Autodesk Maya en Mental Ray
description: Een IBL-podium instellen met Autodesk Maya en Mental Ray
seo-description: Een IBL-podium instellen met Autodesk Maya en Mental Ray
uuid: 353ff561-0d30-4d62-8cad-68890c883c92
contentOwner: Rick Brough
topic-tags: 3D
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
discoiquuid: 752e521f-198f-425a-abfa-051993f9c694
translation-type: tm+mt
source-git-commit: 4b05b24a91ba9c31a19a5a96fb481d2ffc4c9bfc

---


# Een IBL-podium instellen met Autodesk Maya en Mental Ray {#setting-up-an-ibl-stage-with-autodesk-maya-and-mental-ray}

1. Maak in Maya een nieuwe, lege scène.

1. Maak een (tijdelijke) verwijzing naar een representatief model. Zo kunt u de belichting gemakkelijker evalueren, camera&#39;s instellen en de renderer configureren.
1. Op afbeeldingen gebaseerde belichting instellen.

   1. Selecteer Rendering **[!UICONTROL met]****[!UICONTROL : mentale straal]** en open het tabblad Scène.
   1. Open de accordeon **[!UICONTROL Renderomgeving]** en klik op **[!UICONTROL Rendering Create Image Based Lighting**.
   1. Klik op het vakpictogram met een pijl naar rechts links in het vak om het IBL-knooppunt te selecteren `mentalRayIblShape1`en sluit **[!UICONTROL Renderinstellingen]** af.
   1. In de Redacteur **[!UICONTROL van]** Attributen, selecteer de transformatieknoop `mentalRayIbl1`, dan noem de transformatieknoopknoop aan `AdobeIbl`.
   1. Stel de schaal van het knooppunt in om de omgevingssfeer aanzienlijk groter te maken dan het grootste 3D-object dat met dit werkgebied moet worden weergegeven (bijvoorbeeld `10000,10000,10000`).
   1. Selecteer het `AdobeIblShape` knooppunt en configureer het als volgt:

      * **[!UICONTROL Toewijzing]** , bolvormig
      * **[!UICONTROL Type]** - afbeeldingsbestand
      * **[!UICONTROL Licht]** plaatsen - waar
   1. Koppel de gewenste 32-bits TIFF-afbeelding aan het `AdobeIbl` knooppunt.


1. Stel het grondvlak in.

   * Maak een geschikt vlak voor gebruik als grondvlak en pas het aan de IBL-bol aan, waarbij het door de oorsprong van de coördinaten loopt.
   * Koppel achtergrondmateriaal **[!UICONTROL gebruiken]** aan het grondvlak en noem het materiaal `AdobeUseBackground` en koppel het aan het grondvlakobject.

1. (Optioneel) Maak en configureer camera&#39;s.

   Laat de camera&#39;s &#39;uitkijken&#39; naar het midden van de scène waar het element wordt ingevoegd. Zorg ervoor dat u de camera&#39;s instelt op renderbaar.

1. Rendering instellen met Mental Ray.

   Configureer de **[!UICONTROL renderinstellingen]** met de volgende suggesties.

   * **[!UICONTROL Algemeen]** tabblad

      Schakel het selectievakje **[!UICONTROL Alfakanaal (masker)]** voor alle **[!UICONTROL renderbare camera&#39;s]** uit.

   * **[!UICONTROL Het tabblad Kwaliteit]**

      * **Algemene kwaliteit** - `0.5` of minder
      * **Modus** Indirect onscherp - `Final Gather`
      * &quot;**Filtergrootte** - `2.0`, `2.0`
   * Render de scène op de standaardafbeeldingsformaten die u wilt gebruiken. Verfijn indien nodig de lichten, Renderinstellingen of beide om de gewenste resultaten te bereiken.

      Houd er rekening mee dat rendering met Mental Ray met behulp van op afbeeldingen gebaseerde belichting erg langzaam en CPU-intensief is. Adobe raadt u aan de instellingen voor de laagste kwaliteit te configureren die nog steeds de gewenste renderkwaliteit kunnen produceren.


1. Verwijder de verwijzing die u in stap 2 hebt gemaakt.

1. Sla de scène op en sluit Autodesk Maya af.

1. Upload de scène en de IBL PTIFF naar AEM en wacht tot het uploaden is voltooid.

   Zie Elementen [uploaden](managing-assets-touch-ui.md#uploading-assets).

1. Los om het even welke dossiergebiedsdelen op.

   Zie [Bestandsafhankelijkheden](resolve-file-dependencies.md)oplossen.

   AEM 3D kan mogelijk het IBL-beeld dat in het werkgebied is geconfigureerd, niet detecteren. In dergelijke situaties, moet u de ontbrekende gebiedsdelen manueel oplossen. U kunt dezelfde eerder geüploade IBL PTIFF-afbeelding toewijzen voor elk van de ontbrekende afhankelijkheden. U kunt ook verschillende afbeeldingen toewijzen om de IBL-effecten verder te beheren. Nadat u de afhankelijkheden hebt opgelost, moet u op **[!UICONTROL Opslaan]** tikken om de verwerking te starten.

1. Eigenschappen van element openen in AEM. Stel **[!UICONTROL Titel]** in op een geschikte tekenreeks die wordt weergegeven in de vervolgkeuzelijst **[!UICONTROL Werkgebiedkiezer]** . Controleer of **[!UICONTROL Class]** is ingesteld op **[!UICONTROL 3D-werkgebied]**. Opslaan en afsluiten.

1. Open een 3D-element, selecteer het nieuwe werkgebied en controleer of het naar behoren wordt weergegeven en weergegeven.

