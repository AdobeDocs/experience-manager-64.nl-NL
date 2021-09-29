---
title: Beperkingen voor het uploaden van middelen configureren
description: Leer hoe u Adobe Experience Manager Assets configureert om het type elementen (bestanden) te beperken dat gebruikers kunnen uploaden.
contentOwner: AG
feature: Upload,Asset Ingestion,Asset Management
role: Admin,Architect
exl-id: 0d817cfa-ae06-442a-ad89-5fe619bb2eff
source-git-commit: 8948bca63f1f5ec9d94ede2fb845ed01b4e23333
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 29%

---

# Beperkingen voor het uploaden van middelen configureren {#configuring-asset-upload-restrictions}

U kunt Adobe Experience Manager Assets zodanig configureren dat het type elementen (bestanden) dat gebruikers kunnen uploaden, wordt beperkt. Met deze functie voorkomt u dat gebruikers elementen in een ongewenste indeling kunnen uploaden of schadelijke bestanden kunnen uploaden. Met de service `Day CQ DAM Asset Upload Restriction` kunt u bepalen welk type bestanden gebruikers kunnen uploaden. Standaard kunnen gebruikers elementen van alle MIME-typen uploaden via [!DNL Experience Manager]. U kunt de service echter zo configureren dat gebruikers alleen bestanden van bepaalde MIME-typen kunnen uploaden.

1. Om de Webconsole van de Manager van de Configuratie te openen, toegang `https://[AEM_server]:[port]/system/console/configMgr`.
1. Open de service **[!UICONTROL Day CQ DAM Asset Upload Restriction]** in de modus Bewerken. Standaard is de optie **Alle MIME** toestaan geselecteerd, waarmee gebruikers bestanden van alle MIME-typen kunnen uploaden.

   ![chlimage_1-378](assets/chlimage_1-378.png)

1. Als u gebruikers wilt beperken zodat zij alleen bestanden van bepaalde MIME-typen kunnen uploaden, schakelt u de optie **[!UICONTROL llow all MIME]** uit en geeft u toegestane MIME-typen op in de velden **[!UICONTROL Allowed Asset MIMEs (regex)]** met behulp van reguliere expressies.

   ![chlimage_1-379](assets/chlimage_1-379.png)

1. Klik of tik op **[!UICONTROL Save]** om de wijzigingen op te slaan. Als u MIME-tekenreeksen opgeeft voor toegestane MIME-typen, mislukt de uploadbewerking voor elke asset met MIME-type dat niet overeenkomt met de geconfigureerde MIME-tekenreeksen in deze velden.
