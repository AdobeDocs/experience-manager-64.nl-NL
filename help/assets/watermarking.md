---
title: Watermerk toevoegen aan uw digitale elementen
description: Leer hoe u met de functie Watermerken een digitaal watermerk aan elementen kunt toevoegen.
contentOwner: AG
feature: Asset Management
role: User,Admin
exl-id: ed01143c-b516-44f8-aceb-ad2e3f0106b2
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 0%

---

# Watermerk uw digitale elementen {#watermarking}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

[!DNL Adobe Experience Manager Assets] Hiermee kunt u een digitaal watermerk toevoegen aan elementen waarmee gebruikers de authenticiteit en het auteursrecht van de elementen kunnen controleren. [!DNL Experience Manager Assets] ondersteunt tekst die als watermerk moet worden gebruikt op PNG- en JPEG-bestanden.

Met Adobe Experience Manager Assets kunt u een digitaal watermerk toevoegen aan afbeeldingen waarmee gebruikers de authenticiteit en het auteursrecht van de elementen kunnen controleren. [!DNL Experience Manager] Elementen ondersteunen tekst die als watermerk moet worden gebruikt in PNG- en JPEG-bestanden.

Als u een watermerk wilt toepassen op elementen, voegt u de stap Watermerken toe in het dialoogvenster [!UICONTROL DAM Update Asset] workflow.

1. Toegang krijgen tot [!DNL Experience Manager] gebruikersinterface en ga naar **[!UICONTROL Tools]** > **[!UICONTROL Workflow]** > **[!UICONTROL Models]**.
1. Selecteer op de pagina Workflowmodellen de optie **[!UICONTROL DAM Update Asset]** workflow en klik op **[!UICONTROL Edit]**.

1. Sleep vanuit het zijpaneel de **[!UICONTROL Add Watermark]** stap en voeg deze toe aan de [!UICONTROL DAM Update Asset] workflow.

   ![Sleep watermerkstap toevoegen aan de workflow voor DAM-updatebestanden](assets/add_watermark_step_aem_assets.png)

   >[!NOTE]
   >
   >Plaats de [!UICONTROL Add Watermark] stap overal vóór de [!UICONTROL Process Thumbnail] stap.

1. Open de **[!UICONTROL Add Watermark]** stap om de eigenschappen weer te geven.
1. In de **[!UICONTROL Arguments]** op in de verschillende velden geldige waarden, zoals tekst, lettertype, grootte, kleur, positie, richting enzovoort. Klik op **[!UICONTROL Done]**.

   ![Geef de argumenten op in de stap Watermerk toevoegen in Elementen](assets/arguments_add_watermark_aem_assets.png)

1. Sla de **[!UICONTROL DAM Update Asset]** met de [!UICONTROL Watermark] stap.
1. Van de [!DNL Experience Manager] -gebruikersinterface, uploadt u een voorbeeldelement. Het watermerk wordt weergegeven met de tekengrootte, kleur, enzovoort, op de positie die u in de bovenstaande stappen hebt geconfigureerd.

Als u PDF-documenten met watermerk programmatisch of met dynamische informatie wilt gebruiken, kunt u [[!DNL Experience Manager] Document Services](/help/forms/using/overview-aem-document-services.md) aanbieden.

## Tips en beperkingen {#tips-limitations}

* Alleen op tekst gebaseerde watermerken worden ondersteund. Afbeeldingen worden niet gebruikt als watermerken, ook al kunt u afbeeldingen uploaden wanneer u de [!UICONTROL Add Watermark Process].
* Alleen PNG- en JPEG-bestanden worden ondersteund voor een watermerk. Andere indelingen van elementen zijn niet van een watermerk voorzien.
