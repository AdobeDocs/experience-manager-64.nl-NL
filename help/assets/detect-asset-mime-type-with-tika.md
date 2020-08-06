---
title: Apache Tika gebruiken om MIME-type van digitale elementen te detecteren
description: Schakel Apache Tika in om AEM Assets te helpen bij het detecteren van het MIME-type van elementen uit de inhoudsstroom tijdens het uploaden in plaats van de bestandsextensie.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 0d70a672a2944e2c03b54beb3b5f734136792ab1
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 3%

---


# Apache Tika gebruiken om MIME-type van digitale elementen te detecteren {#detecting-mime-type-of-assets-using-apache-tika}

Adobe Experience Manager (AEM) Assets detecteert doorgaans het MIME-type van elementen die u uploadt vanuit de bestandsextensie. Als u Apache Tika gebruikt om activa te uploaden, ontdekt AEM Assets hun MIME type van de inhoudsstroom tijdens het uploaden verrichting in plaats van de dossieruitbreiding.

Deze functie is standaard uitgeschakeld. Om de eigenschap toe te laten, vorm de dienst van het Type **van MIME van** Dag CQ DAM van de Manager van de Configuratie.

>[!NOTE]
>
>MIME-typedetectie met behulp van de Apache Tika-bibliotheek is een hulpbronnenintensieve bewerking.

1. Ga naar `https://[AEM_server]:[port]/system/console/configMgr` om de Webconsole van de Manager van de Configuratie te openen.
1. Zoek in de lijst met services het **[!UICONTROL Day CQ DAM Mime Type Service]** pictogram naast het pictogram **[!UICONTROL Edit]** en tik erop om het pictogram in de modus Bewerken te openen.

1. Selecteer de **[!UICONTROL Detect MIME from content]** optie om het parseren van geüploade elementen in te schakelen om het MIME-type te bepalen terwijl bestandsextensies worden genegeerd. Deze optie is standaard uitgeschakeld.

   ![chlimage_1-333](assets/chlimage_1-333.png)

1. Klik of tik op **[!UICONTROL Save]** om de wijzigingen op te slaan.
