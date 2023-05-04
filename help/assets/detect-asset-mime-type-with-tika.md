---
title: Apache Tika gebruiken om MIME-type van digitale elementen te detecteren
description: Help bij Apache Tika inschakelen [!DNL Experience Manager] Elementen detecteren het MIME-type van elementen van de inhoudsstroom tijdens het uploaden in plaats van de bestandsextensie.
contentOwner: AG
feature: Metadata,Developer Tools,Asset Management
role: Admin,Architect
exl-id: 6c9e53e9-5e54-4816-9431-41e796340d1e
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 2%

---

# Apache Tika gebruiken om MIME-type van digitale elementen te detecteren {#detecting-mime-type-of-assets-using-apache-tika}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Adobe Experience Manager Assets detecteert doorgaans het MIME-type van elementen die u uploadt vanuit de bestandsextensie. Als u Apache Tika gebruikt om activa te uploaden, [!DNL Experience Manager] Elementen detecteren het MIME-type van de inhoudsstroom tijdens het uploaden in plaats van de bestandsextensie.

Deze functie is standaard uitgeschakeld. Om de eigenschap toe te laten, vorm **CQ DAM MIME-type dag** service van Configuration Manager.

>[!NOTE]
>
>MIME-typedetectie met behulp van de Apache Tika-bibliotheek is een hulpbronnenintensieve bewerking.

1. Ga naar `https://[AEM_server]:[port]/system/console/configMgr` om de Webconsole van de Manager van de Configuratie te openen.
1. Van de lijst van de diensten, bepaal de plaats van **[!UICONTROL Day CQ DAM Mime Type Service]** en tik/klik op de knop **[!UICONTROL Edit]** naast het pictogram om het in Edit wijze te openen.

1. Selecteer **[!UICONTROL Detect MIME from content]** optie om het parseren van geüploade elementen in staat te stellen hun MIME-type te bepalen terwijl bestandsextensies worden genegeerd. Deze optie is standaard uitgeschakeld.

   ![chlimage_1-333](assets/chlimage_1-333.png)

1. Klik of tik op **[!UICONTROL Save]** om de wijzigingen op te slaan.
