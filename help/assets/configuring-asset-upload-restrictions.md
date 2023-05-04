---
title: Beperkingen voor het uploaden van middelen configureren
description: Leer hoe u Adobe Experience Manager Assets configureert om het type elementen (bestanden) te beperken dat gebruikers kunnen uploaden.
contentOwner: AG
feature: Upload,Asset Ingestion,Asset Management
role: Admin,Architect
exl-id: 0d817cfa-ae06-442a-ad89-5fe619bb2eff
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 24%

---

# Beperkingen voor het uploaden van middelen configureren {#configuring-asset-upload-restrictions}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

U kunt Adobe Experience Manager Assets zodanig configureren dat het type elementen (bestanden) dat gebruikers kunnen uploaden, wordt beperkt. Met deze functie voorkomt u dat gebruikers elementen in een ongewenste indeling kunnen uploaden of schadelijke bestanden kunnen uploaden. De `Day CQ DAM Asset Upload Restriction` Met deze service kunt u bepalen welk type bestanden gebruikers kunnen uploaden. Standaard, [!DNL Experience Manager] Met elementen kunnen gebruikers elementen van alle MIME-typen uploaden. U kunt de service echter zo configureren dat gebruikers alleen bestanden van bepaalde MIME-typen kunnen uploaden.

1. Om de Webconsole van de Manager van de Configuratie te openen, toegang `https://[AEM_server]:[port]/system/console/configMgr`.
1. Open de **[!UICONTROL Day CQ DAM Asset Upload Restriction]** in de modus Bewerken. Standaard worden de **Alle MIME toestaan** is geselecteerd, zodat gebruikers bestanden van alle MIME-typen kunnen uploaden.

   ![chlimage_1-378](assets/chlimage_1-378.png)

1. Als u gebruikers wilt beperken zodat zij alleen bestanden van bepaalde MIME-typen kunnen uploaden, schakelt u de optie **[!UICONTROL llow all MIME]** uit en geeft u toegestane MIME-typen op in de velden **[!UICONTROL Allowed Asset MIMEs (regex)]** met behulp van reguliere expressies.

   ![chlimage_1-379](assets/chlimage_1-379.png)

1. Klik of tik op **[!UICONTROL Save]** om de wijzigingen op te slaan. Als u MIME-tekenreeksen opgeeft voor toegestane MIME-typen, mislukt de uploadbewerking voor elke asset met MIME-type dat niet overeenkomt met de geconfigureerde MIME-tekenreeksen in deze velden.
