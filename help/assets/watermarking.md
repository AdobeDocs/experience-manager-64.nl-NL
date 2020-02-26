---
title: Uw afbeeldingen watermerken
description: Met de functie Watermerken kunt u een digitaal watermerk toevoegen aan PNG- EN JPEG-afbeeldingen.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 0e0e2aa693c30c8e1ef1033b936b82d83e5b348e

---


# Watermerk uw elementen {#watermarking}

Met Adobe Experience Manager (AEM) kunt u een digitaal watermerk aan afbeeldingen toevoegen waarmee gebruikers de authenticiteit en het auteursrecht van de elementen kunnen verifiëren. AEM-elementen ondersteunen tekst die als watermerk moet worden gebruikt in PNG- en JPEG-bestanden.

Als u een watermerk op elementen wilt toepassen, voegt u de stap [!UICONTROL Watermerk] toe in de workflow [!UICONTROL DAM-element] bijwerken.

1. Tik op het AEM-logo en ga naar **[!UICONTROL Gereedschappen]** > **[!UICONTROL Workflow]** > **[!UICONTROL Modellen]**.
1. Selecteer op de pagina Workflowmodellen de workflow **[!UICONTROL DAM Update Asset]** en klik op **[!UICONTROL Bewerken]**.

1. Sleep vanuit het zijpaneel de stap Watermerk **** toevoegen en voeg deze toe aan de workflow [!UICONTROL DAM-element] bijwerken.

   ![Een watermerkstap toevoegen aan de workflow voor DAM-updatebestanden](assets/add_watermark_step_aem_assets.png)

   >[!NOTE]
   >
   >Plaats de stap Watermerk  toevoegen ergens vóór de stap [!UICONTROL Miniatuur] verwerken.

1. Open de stap Watermerk **** toevoegen om de eigenschappen ervan weer te geven.
1. Geef op het tabblad **[!UICONTROL Argumenten]** geldige waarden op in de verschillende velden, zoals tekst, lettertype, grootte, kleur, positie, oriëntatie, enzovoort. Tik op het pictogram Gereed om de wijzigingen te bevestigen.

   ![Geef de argumenten op in de stap Watermerk toevoegen in Elementen](assets/arguments_add_watermark_aem_assets.png)

1. Sla de workflow **[!UICONTROL DAM Update Asset]** op met de stap [!UICONTROL Watermerk] .
1. Upload een voorbeeldelement vanuit de AEM-gebruikersinterface. Het watermerk wordt weergegeven met de tekengrootte, kleur, enzovoort, op de positie die u in de bovenstaande stappen hebt geconfigureerd.
