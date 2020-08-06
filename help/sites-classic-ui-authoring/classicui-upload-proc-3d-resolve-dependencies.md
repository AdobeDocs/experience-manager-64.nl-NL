---
title: Bestandsafhankelijkheden oplossen
seo-title: Bestandsafhankelijkheden oplossen
description: Bestandsafhankelijkheden van primaire 3D-modellen, zoals bestanden met structuurafbeeldingen, worden waar mogelijk automatisch opgelost. Deze functionaliteit wordt verwezenlijkt door AEM onderzoek dichtbij de omslagen van Activa naar dossiers met de zelfde namen te hebben die in het 3D dossier worden gevonden.
seo-description: Bestandsafhankelijkheden van primaire 3D-modellen, zoals bestanden met structuurafbeeldingen, worden waar mogelijk automatisch opgelost. Deze functionaliteit wordt verwezenlijkt door AEM onderzoek dichtbij de omslagen van Activa naar dossiers met de zelfde namen te hebben die in het 3D dossier worden gevonden.
uuid: b1b83cb7-b6e5-4417-9a53-b6d8bcf8d2e0
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: authoring
content-type: reference
discoiquuid: 14754023-e7c4-4dc5-a9d8-408b81861d95
translation-type: tm+mt
source-git-commit: e2bb2f17035e16864b1dc54f5768a99429a3dd9f
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 0%

---


# Bestandsafhankelijkheden oplossen{#resolving-file-dependencies}

Bestandsafhankelijkheden van primaire 3D-modellen, zoals bestanden met structuurafbeeldingen, worden waar mogelijk automatisch opgelost. Deze functionaliteit wordt verwezenlijkt door AEM onderzoek dichtbij de omslagen van Activa naar dossiers met de zelfde namen te hebben die in het 3D dossier worden gevonden. Als een of meer afhankelijkheden niet kunnen worden opgelost tijdens het proces voor het maken van een voorvertoning van de verwerking, wordt op de kaart van het element het volgende bericht voor een rode banner weergegeven in het [!UICONTROL Card View]venster:

![chlimage_1-189](assets/chlimage_1-189.png)

**Bestandsafhankelijkheden** oplossen:

1. Houd de aanwijzer in het **[!UICONTROL Card View]** venster boven het **[!UICONTROL Unresolved Dependencies]** bannerbericht op de kaart en tik vervolgens op het uitroepteken.

   ![chlimage_1-190](assets/chlimage_1-190.png)

1. Tik op het **[!UICONTROL Dependencies]** tabblad op de pagina met eigenschappen van metagegevens.

   De bestanden die AEM niet automatisch kunnen worden opgelost, worden weergegeven in de kolom Oorspronkelijke paden, in rood.

1. Voer een of meer van de volgende handelingen uit:

   * **[!UICONTROL Browse to and select the dependencies]**. (Bij deze optie wordt ervan uitgegaan dat u de afhankelijkheidsbestanden al hebt geüpload.

      1. Tik op het **[!UICONTROL File Browse]** pictogram links van het rode pad.
      1. Navigeer op de **[!UICONTROL Select Content]** pagina naar het ontbrekende bestand en tik op de kaart van het bestand om het te selecteren.
      1. Tik in de linkerbovenhoek van de **[!UICONTROL Select Content]** pagina op **[!UICONTROL Close]** (X-pictogram) om terug te keren naar de **[!UICONTROL View Properties]** pagina.
   * **[!UICONTROL Upload the dependencies]**. (Bij deze optie wordt ervan uitgegaan dat u de ontbrekende bestanden nog niet hebt geüpload.)

      1. Houd rekening met de ontbrekende paden en bestandsnamen.
      1. Near the upper-right corner of the properties page, tap **[!UICONTROL Close]**.

   Nadat de bestanden zijn geüpload, gaat u terug naar de **[!UICONTROL View Properties > Dependencies]** pagina. Het net geüploade element wordt nu correct weergegeven als middelen waarnaar wordt verwezen.

   * **[!UICONTROL Ignore the dependencies]**.

      Als er geen ontbrekende afhankelijkheid meer nodig is, typt u in de **[!UICONTROL Referenced Asset]** kolom in het tekstveld links van het ontbrekende bestand `n/a` zodat AEM 3D het bestand negeert.



1. Near the upper-right corner of the **[!UICONTROL View Properties]** page, tap **[!UICONTROL Save]**.
1. Tik **[!UICONTROL Close]** om terug te keren naar de **[!UICONTROL Card View]**.

   Het middel wordt automatisch opnieuw verwerkt met de onlangs opgeloste gebiedsdelen.

