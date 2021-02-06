---
title: Bestandsafhankelijkheden oplossen
seo-title: Bestandsafhankelijkheden oplossen
description: Hoe te om 3D dossiergebiedsdelen zoals textuurkaartdossiers op te lossen wanneer het auto-oplossen ontbreekt.
seo-description: Hoe te om 3D dossiergebiedsdelen zoals textuurkaartdossiers op te lossen wanneer het auto-oplossen ontbreekt.
uuid: 49cefabf-147b-4a78-90f3-0f2d6a8e8cae
contentOwner: Rick Brough
topic-tags: 3D
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
discoiquuid: 05b7410b-82a1-4267-ac07-2edbc29e9ee8
translation-type: tm+mt
source-git-commit: e2bb2f17035e16864b1dc54f5768a99429a3dd9f
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 0%

---


# Bestandsafhankelijkheden {#resolving-file-dependencies} oplossen

Bestandsafhankelijkheden van primaire 3D-modellen, zoals bestanden met structuurafbeeldingen, worden waar mogelijk automatisch opgelost. Deze functionaliteit wordt verwezenlijkt door AEM onderzoek dichtbij de omslagen van Activa naar dossiers met de zelfde namen te hebben die in het 3D dossier worden gevonden. Als een of meer afhankelijkheden niet kunnen worden opgelost tijdens het proces voor het maken van een voorvertoning van de verwerking, wordt op de kaart van het element het volgende rode bannerbericht weergegeven in **[!UICONTROL Card View]**:

![chlimage_1-124](assets/chlimage_1-124.png)

**Bestandsafhankelijkheden** oplossen:

1. Houd in **[!UICONTROL Card View]** de aanwijzer boven het **[!UICONTROL Unresolved Dependencies]**-bannerbericht op de kaart en tik vervolgens op het **[!UICONTROL Exclamation Point]**-pictogram.

   ![chlimage_1-125](assets/chlimage_1-125.png)

1. Tik op de **[!UICONTROL Metadata Properties]**-pagina op het tabblad **[!UICONTROL Dependencies]**.

   De bestanden die AEM niet automatisch kunnen worden opgelost, worden weergegeven in de kolom **[!UICONTROL Original Paths]**, in rood.

1. Voer een of meer van de volgende handelingen uit:

   * **Blader naar de afhankelijkheden** en selecteer deze. (Bij deze optie wordt ervan uitgegaan dat u de afhankelijkheidsbestanden al hebt geüpload.

      1. Tik op het pictogram **[!UICONTROL File Browse]** links van het rode pad.
      1. Navigeer op de pagina **[!UICONTROL Select Content]** naar het ontbrekende bestand en tik op de kaart van het bestand om het te selecteren.
      1. Tik in de linkerbovenhoek van de pagina **[!UICONTROL Select Content]** (X-pictogram) op **[!UICONTROL Close]** om terug te keren naar de pagina **[!UICONTROL View Properties]**.
   * **Upload de afhankelijkheden**. (Bij deze optie wordt ervan uitgegaan dat u de ontbrekende bestanden nog niet hebt geüpload.)

      1. Houd rekening met de ontbrekende paden en bestandsnamen.
      1. Tik in de rechterbovenhoek van de eigenschappenpagina op **[!UICONTROL Close]**.

   Nadat de bestanden zijn geüpload, gaat u terug naar de pagina **[!UICONTROL View Properties > Dependencies]**. Het net geüploade element wordt nu correct weergegeven als middelen waarnaar wordt verwezen.

   * **Negeer de afhankelijkheden**.

      Als er geen ontbrekende afhankelijkheid meer nodig is, typt u `n/a` in het tekstveld links van het ontbrekende bestand, zodat AEM 3D het bestand negeert.**[!UICONTROL Referenced Asset]**



1. Tik in de rechterbovenhoek van de pagina **[!UICONTROL View Properties]** op **[!UICONTROL Save]**.
1. Tik **[!UICONTROL Close]** om terug te keren naar **[!UICONTROL Card View]**.

   Het middel wordt automatisch opnieuw verwerkt met de onlangs opgeloste gebiedsdelen.

