---
title: Automatisch opslaan gebruiken in AEM Forms-app
seo-title: Using autosave in AEM Forms app
description: Leer hoe u de functie voor automatisch opslaan in de AEM Forms-app kunt gebruiken om gegevensverlies te voorkomen.
seo-description: Learn how to use autosave feature in AEM Forms app that lets you avoid data loss.
uuid: f18ab6b4-dd4a-4dcb-88e6-e349777d47ea
contentOwner: sashanka
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-app
discoiquuid: 133d93b0-512c-46db-b5f9-f981d77b565f
exl-id: 6eb00c31-6806-478a-99d1-55912798ea69
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 0%

---

# Automatisch opslaan gebruiken in AEM Forms-app {#using-autosave-in-aem-forms-app}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

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
1. Gebruik in het scherm Algemeen de **[!UICONTROL Autosave Frequency]** Selecteer de intervallen waarmee u de ingevoerde gegevens wilt opslaan in de app.
   [ ![Frequentie voor automatisch opslaan instellen](assets/using-autosave-freq-07.png)](assets/using-autosave-freq-07-1.png)

1. Wanneer u de app opnieuw opstart en u bij dezelfde gebruiker aanmeldt, wordt u gevraagd om uw taak te herstellen met het dialoogvenster Niet-opgeslagen taak herstellen. Klikken **[!UICONTROL OK]** in het dialoogvenster Niet-opgeslagen taak herstellen om het werken met de opgeslagen taak te hervatten. U kunt op **[!UICONTROL Cancel]** om de opgeslagen gegevens te verwijderen die overeenkomen met de laatst getriggerde automatische opslag en te beginnen met het werken met een nieuwe taak.

   Wanneer u op **[!UICONTROL OK]**, wordt de taak hersteld met de gegevens die overeenkomen met de laatste automatische opslag die is geactiveerd voordat de app is vastgelopen. Het bevat de formuliergegevens en alle bijlagen die bij de taak horen.
   [ ![Een taak terugkrijgen ](assets/autosave-flow.png)](assets/using-autosave-freq-06.png)**A.** Een werk in uitvoering formulier **B.** App forceerd gesloten **C.** Toepassing opnieuw gestart met dialoogvenster Niet-opgeslagen taak herstellen **D.** Het formulier is hersteld met de oorspronkelijke gegevens
