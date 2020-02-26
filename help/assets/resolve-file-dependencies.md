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

---


# Bestandsafhankelijkheden oplossen {#resolving-file-dependencies}

Bestandsafhankelijkheden van primaire 3D-modellen, zoals bestanden met structuurafbeeldingen, worden waar mogelijk automatisch opgelost. Deze functionaliteit wordt verwezenlijkt door AEM dichtbij de omslagen van Activa te zoeken naar dossiers met de zelfde namen die in het 3D dossier worden gevonden. Als een of meer afhankelijkheden niet kunnen worden opgelost tijdens het proces voor het maken van een voorvertoning van de verwerking, wordt op de kaart van het element het volgende rode bannerbericht weergegeven in de **[!UICONTROL Kaartweergave]**:

![chlimage_1-124](assets/chlimage_1-124.png)

**Bestandsafhankelijkheden** oplossen:

1. Houd in de **[!UICONTROL Kaartweergave]** de aanwijzer boven het bannerbericht **[!UICONTROL Onopgeloste afhankelijkheden]** op de kaart en tik vervolgens op het pictogram **[!UICONTROL Uitroepteken]** .

   ![chlimage_1-125](assets/chlimage_1-125.png)

1. Tik op het tabblad **[!UICONTROL Afhankelijkheden]** op de pagina Eigenschappen van **** metagegevens.

   De bestanden die niet automatisch kunnen worden omgezet in AEM, worden weergegeven onder de kolom **[!UICONTROL Oorspronkelijke paden]** , in rood.

1. Voer een of meer van de volgende handelingen uit:

   * **Blader naar de afhankelijkheden** en selecteer deze. (Bij deze optie wordt ervan uitgegaan dat u de afhankelijkheidsbestanden al hebt geüpload.

      1. Tik op het pictogram **[!UICONTROL Bestand bladeren]** links van het rode pad.
      1. Navigeer op de pagina Inhoud **** selecteren naar het ontbrekende bestand en tik op de kaart van het bestand om het te selecteren.
      1. Tik in de linkerbovenhoek van de pagina Inhoud **** selecteren op **[!UICONTROL Sluiten]** (X-pictogram) om terug te keren naar de pagina Eigenschappen **[!UICONTROL van]** weergave.
   * **Upload de afhankelijkheden**. (Bij deze optie wordt ervan uitgegaan dat u de ontbrekende bestanden nog niet hebt geüpload.)

      1. Houd rekening met de ontbrekende paden en bestandsnamen.
      1. Tik in de rechterbovenhoek van de pagina met eigenschappen op **[!UICONTROL Sluiten]**.
   Nadat de bestanden zijn geüpload, gaat u terug naar de pagina **[!UICONTROL Weergave-eigenschappen > Afhankelijkheden]** . Het net geüploade element wordt nu correct weergegeven als middelen waarnaar wordt verwezen.

   * **Negeer de afhankelijkheden**.

      Als er geen ontbrekende afhankelijkheid meer nodig is, typt u in het tekstveld links van het ontbrekende bestand onder de kolom **[!UICONTROL Element]** waarnaar wordt verwezen, `n/a` zodat AEM 3D het bestand negeert.



1. Tik in de rechterbovenhoek van de pagina Eigenschappen **[!UICONTROL van]** weergave op **[!UICONTROL Opslaan]**.
1. Tik op **[!UICONTROL Sluiten]** om terug te keren naar de **[!UICONTROL kaartweergave]**.

   Het middel wordt automatisch opnieuw verwerkt met de onlangs opgeloste gebiedsdelen.

