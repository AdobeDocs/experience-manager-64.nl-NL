---
title: Beperkingen voor het uploaden van middelen configureren
description: Leer hoe u Adobe Experience Manager-middelen (AEM) configureert om het type elementen (bestanden) te beperken dat gebruikers kunnen uploaden.
contentOwner: AG
feature: Developer
role: Beheerder, architect
translation-type: tm+mt
source-git-commit: 29e3cd92d6c7a4917d7ee2aa8d9963aa16581633
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 28%

---


# Beperkingen voor het uploaden van elementen {#configuring-asset-upload-restrictions} configureren

U kunt Adobe Experience Manager-middelen (AEM) configureren om het type elementen (bestanden) te beperken dat gebruikers kunnen uploaden. Met deze functie voorkomt u dat gebruikers elementen in een ongewenste indeling kunnen uploaden of schadelijke bestanden kunnen uploaden. Met de service `Day CQ DAM Asset Upload Restriction` kunt u bepalen welk type bestanden gebruikers kunnen uploaden. Standaard kunnen gebruikers met AEM Assets elementen van alle MIME-typen uploaden. U kunt de service echter zo configureren dat gebruikers alleen bestanden van bepaalde MIME-typen kunnen uploaden.

1. Om de Webconsole van de Manager van de Configuratie te openen, toegang `https://[AEM_server]:[port]/system/console/configMgr`.
1. Open de service **[!UICONTROL Day CQ DAM Asset Upload Restriction]** in de modus Bewerken. Standaard is de optie **Alle MIME** toestaan geselecteerd, waarmee gebruikers bestanden van alle MIME-typen kunnen uploaden.

   ![chlimage_1-378](assets/chlimage_1-378.png)

1. Als u gebruikers wilt beperken zodat zij alleen bestanden van bepaalde MIME-typen kunnen uploaden, schakelt u de optie **[!UICONTROL llow all MIME]** uit en geeft u toegestane MIME-typen op in de velden **[!UICONTROL Allowed Asset MIMEs (regex)]** met behulp van reguliere expressies.

   ![chlimage_1-379](assets/chlimage_1-379.png)

1. Klik of tik op **[!UICONTROL Save]** om de wijzigingen op te slaan. Als u MIME-tekenreeksen opgeeft voor toegestane MIME-typen, mislukt de uploadbewerking voor elke asset met MIME-type dat niet overeenkomt met de geconfigureerde MIME-tekenreeksen in deze velden.
