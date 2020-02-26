---
title: Bestandsafhankelijkheden oplossen
seo-title: Bestandsafhankelijkheden oplossen
description: Bestandsafhankelijkheden van primaire 3D-modellen, zoals bestanden met structuurafbeeldingen, worden waar mogelijk automatisch opgelost. Deze functionaliteit wordt verwezenlijkt door AEM dichtbij de omslagen van Activa te zoeken naar dossiers met de zelfde namen die in het 3D dossier worden gevonden.
seo-description: Bestandsafhankelijkheden van primaire 3D-modellen, zoals bestanden met structuurafbeeldingen, worden waar mogelijk automatisch opgelost. Deze functionaliteit wordt verwezenlijkt door AEM dichtbij de omslagen van Activa te zoeken naar dossiers met de zelfde namen die in het 3D dossier worden gevonden.
uuid: b1b83cb7-b6e5-4417-9a53-b6d8bcf8d2e0
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: authoring
content-type: reference
discoiquuid: 14754023-e7c4-4dc5-a9d8-408b81861d95
translation-type: tm+mt
source-git-commit: e2bb2f17035e16864b1dc54f5768a99429a3dd9f

---


# Bestandsafhankelijkheden oplossen{#resolving-file-dependencies}

Bestandsafhankelijkheden van primaire 3D-modellen, zoals bestanden met structuurafbeeldingen, worden waar mogelijk automatisch opgelost. Deze functionaliteit wordt verwezenlijkt door AEM dichtbij de omslagen van Activa te zoeken naar dossiers met de zelfde namen die in het 3D dossier worden gevonden. Als een of meer afhankelijkheden niet kunnen worden opgelost tijdens het proces voor het maken van een voorvertoning van de verwerking, wordt op de kaart van het element het volgende rode bannerbericht weergegeven in de [!UICONTROL Kaartweergave]:

![chlimage_1-189](assets/chlimage_1-189.png)

**Bestandsafhankelijkheden** oplossen:

1. Houd in de **[!UICONTROL Kaartweergave]** de aanwijzer boven het bannerbericht **[!UICONTROL Onopgeloste afhankelijkheden]** op de kaart en tik vervolgens op het pictogram van het uitroepteken.

   ![chlimage_1-190](assets/chlimage_1-190.png)

1. Tik op het tabblad **[!UICONTROL Afhankelijkheden]** op de pagina met eigenschappen van metagegevens.

   De bestanden die niet automatisch kunnen worden omgezet in AEM, worden weergegeven onder de kolom Oorspronkelijke paden, in rood.

1. Voer een of meer van de volgende handelingen uit:

   * **[!UICONTROL Blader naar de afhankelijkheden]** en selecteer deze. (Bij deze optie wordt ervan uitgegaan dat u de afhankelijkheidsbestanden al hebt geüpload.

      1. Tik op het pictogram **[!UICONTROL Bestand bladeren]** links van het rode pad.
      1. Navigeer op de pagina Inhoud **** selecteren naar het ontbrekende bestand en tik op de kaart van het bestand om het te selecteren.
      1. Tik in de linkerbovenhoek van de pagina Inhoud **** selecteren op **[!UICONTROL Sluiten]** (X-pictogram) om terug te keren naar de pagina Eigenschappen **[!UICONTROL van]** weergave.
   * **[!UICONTROL Upload de afhankelijkheden]**. (Bij deze optie wordt ervan uitgegaan dat u de ontbrekende bestanden nog niet hebt geüpload.)

      1. Houd rekening met de ontbrekende paden en bestandsnamen.
      1. Tik in de rechterbovenhoek van de pagina met eigenschappen op **[!UICONTROL Sluiten]**.
   Nadat de bestanden zijn geüpload, gaat u terug naar de pagina **[!UICONTROL Weergave-eigenschappen > Afhankelijkheden]** . Het net geüploade element wordt nu correct weergegeven als middelen waarnaar wordt verwezen.

   * **[!UICONTROL Negeer de afhankelijkheden]**.

      Als er geen ontbrekende afhankelijkheid meer nodig is, typt u in het tekstveld links van het ontbrekende bestand onder de kolom **[!UICONTROL Element]** waarnaar wordt verwezen, `n/a` zodat AEM 3D het bestand negeert.



1. Tik in de rechterbovenhoek van de pagina Eigenschappen **[!UICONTROL van]** weergave op **[!UICONTROL Opslaan]**.
1. Tik op **[!UICONTROL Sluiten]** om terug te keren naar de **[!UICONTROL kaartweergave]**.

   Het middel wordt automatisch opnieuw verwerkt met de onlangs opgeloste gebiedsdelen.

