---
title: Automatisch opslaan gebruiken in AEM Forms-app
seo-title: Automatisch opslaan gebruiken in AEM Forms-app
description: 'Leer hoe u de functie voor automatisch opslaan in de AEM Forms-app kunt gebruiken om gegevensverlies te voorkomen. '
seo-description: 'Leer hoe u de functie voor automatisch opslaan in de AEM Forms-app kunt gebruiken om gegevensverlies te voorkomen. '
uuid: f18ab6b4-dd4a-4dcb-88e6-e349777d47ea
contentOwner: sashanka
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-app
discoiquuid: 133d93b0-512c-46db-b5f9-f981d77b565f
translation-type: tm+mt
source-git-commit: e2bb2f17035e16864b1dc54f5768a99429a3dd9f
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 0%

---


# Automatisch opslaan gebruiken in AEM Forms-app {#using-autosave-in-aem-forms-app}

Wanneer een gebruiker gegevens in de Adobe Experience Manager Forms-app invoert, slaat de functie voor automatisch opslaan deze op regelmatige intervallen op. Met de functie voor automatisch opslaan in de AEM Forms-app kunt u gegevensverlies voorkomen als de app per ongeluk wordt gesloten.

Uw app kan per ongeluk worden gesloten:

* Als het apparaat wordt uitgeschakeld als gevolg van een lage accu
* Als de gebruiker de app heeft gedood
* Als er een onverwachte crash optreedt

U kunt de intervallen opgeven waarna de toepassing de ingevoerde gegevens opslaat.

>[!NOTE]
>
>Selecteer de frequentie voor automatisch opslaan verstandig. De regelmatige autosave verrichtingen kunnen een merkbare invloed op de prestaties van uw apparaat hebben.

Voer de volgende stappen uit om de functie voor automatisch opslaan te gebruiken in de AEM Forms-app:

1. Meld u aan bij de app en navigeer naar **[!UICONTROL Settings > General]**.
1. Selecteer in het scherm Algemeen de **[!UICONTROL Autosave Frequency]** optie waarmee u wilt dat de toepassing de ingevoerde gegevens opslaat.
   [ ![Frequentie voor automatisch opslaan instellen](assets/using-autosave-freq-07.png)](assets/using-autosave-freq-07-1.png)

1. Wanneer u de app opnieuw opstart en u bij dezelfde gebruiker aanmeldt, wordt u gevraagd om uw taak te herstellen met het dialoogvenster Niet-opgeslagen taak herstellen. Klik **[!UICONTROL OK]** in het dialoogvenster Niet-opgeslagen taak herstellen om het werken met de opgeslagen taak te hervatten. U kunt klikken **[!UICONTROL Cancel]** om de opgeslagen gegevens te verwijderen die overeenkomen met de laatst getriggerde automatische opslag en beginnen met het werken met een nieuwe taak.

   Wanneer u klikt, wordt de taak hersteld met de gegevens die overeenkomen met de laatste automatische opslag die is geactiveerd voordat de app is vastgelopen. **[!UICONTROL OK]** Het bevat de formuliergegevens en alle bijlagen die bij de taak horen.
   [ ![Een taak](assets/autosave-flow.png)](assets/using-autosave-freq-06.png)**terugkrijgen.**Een formulier in uitvoering, formulier** B.**De toepassing is geforceerd gesloten** C.**App is opnieuw gestart met het dialoogvenster Niet-opgeslagen taak herstellen** D.**Het formulier is hersteld met de oorspronkelijke gegevens

