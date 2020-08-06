---
title: Uw afbeeldingen watermerken
description: Met de functie Watermerken kunt u een digitaal watermerk toevoegen aan PNG- EN JPEG-afbeeldingen.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 04de28347ddf0082d2e224aa3853297cad3aacd8
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 0%

---


# Watermerk uw elementen {#watermarking}

Met Adobe Experience Manager (AEM) Assets kunt u een digitaal watermerk toevoegen aan afbeeldingen waarmee gebruikers de authenticiteit en het auteursrecht van de elementen kunnen controleren. AEM Assets ondersteunt tekst die als watermerk moet worden gebruikt in PNG- en JPEG-bestanden.

Als u een watermerk op elementen wilt toepassen, voegt u de [!UICONTROL Watermark] stap in de [!UICONTROL DAM Update Asset] workflow toe.

1. Tap the AEM logo, and go to **[!UICONTROL Tools]** > **[!UICONTROL Workflow]** > **[!UICONTROL Models]**.
1. Selecteer de **[!UICONTROL DAM Update Asset]** workflow op de pagina Workflowmodellen en klik **[!UICONTROL Edit]**.

1. Sleep de **[!UICONTROL Add Watermark]** stap vanuit het zijpaneel en voeg deze toe aan de [!UICONTROL DAM Update Asset] workflow.

   ![Een watermerkstap toevoegen aan de workflow voor DAM-updatebestanden](assets/add_watermark_step_aem_assets.png)

   >[!NOTE]
   >
   >Plaats de [!UICONTROL Add Watermark] stap ergens voor de [!UICONTROL Process Thumbnail] stap.

1. Open de **[!UICONTROL Add Watermark]** stap om de eigenschappen ervan weer te geven.
1. Geef op het **[!UICONTROL Arguments]** tabblad geldige waarden op in de verschillende velden, zoals tekst, lettertype, grootte, kleur, positie, richting enzovoort. Tik op het pictogram Gereed om de wijzigingen te bevestigen.

   ![Geef de argumenten op in de stap Watermerk toevoegen in Elementen](assets/arguments_add_watermark_aem_assets.png)

1. Save the **[!UICONTROL DAM Update Asset]** workflow with the [!UICONTROL Watermark] step.
1. Upload een voorbeeldelement vanuit de AEM gebruikersinterface. Het watermerk wordt weergegeven met de tekengrootte, kleur, enzovoort, op de positie die u in de bovenstaande stappen hebt geconfigureerd.

Als u PDF-documenten programmatisch of met dynamische informatie wilt voorzien van een watermerk, kunt u [AEM Document Services](/help/forms/using/overview-aem-document-services.md) -aanbieding gebruiken.
