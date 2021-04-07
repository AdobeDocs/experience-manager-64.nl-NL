---
title: Apache Tika gebruiken om MIME-type van digitale elementen te detecteren
description: Schakel Apache Tika in om AEM Assets te helpen bij het detecteren van het MIME-type van elementen uit de inhoudsstroom tijdens het uploaden in plaats van de bestandsextensie.
contentOwner: AG
feature: Metagegevens,Gereedschappen voor ontwikkelaars,Middelenbeheer
role: Administrator,Architect
exl-id: 6c9e53e9-5e54-4816-9431-41e796340d1e
translation-type: tm+mt
source-git-commit: bd94d3949f0117aa3e1c9f0e84f7293a5d6b03b4
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 3%

---

# Apache Tika gebruiken om MIME-type van digitale elementen {#detecting-mime-type-of-assets-using-apache-tika} te detecteren

Adobe Experience Manager (AEM) Assets detecteert doorgaans het MIME-type van elementen die u uploadt vanuit de bestandsextensie. Als u Apache Tika gebruikt om activa te uploaden, ontdekt AEM Assets hun MIME type van de inhoudsstroom tijdens het uploaden verrichting in plaats van de dossieruitbreiding.

Deze functie is standaard uitgeschakeld. Om de eigenschap toe te laten, vorm de **Dag CQ DAM Mime Type** dienst van de Manager van de Configuratie.

>[!NOTE]
>
>MIME-typedetectie met behulp van de Apache Tika-bibliotheek is een hulpbronnenintensieve bewerking.

1. Ga naar `https://[AEM_server]:[port]/system/console/configMgr` om de Webconsole van de Manager van de Configuratie te openen.
1. Zoek in de lijst met services **[!UICONTROL Day CQ DAM Mime Type Service]** en tik op het pictogram **[!UICONTROL Edit]** naast het pictogram om het te openen in de modus Bewerken.

1. Selecteer de optie **[!UICONTROL Detect MIME from content]** om het parseren van geüploade elementen in te schakelen om het MIME-type te bepalen terwijl bestandsextensies worden genegeerd. Deze optie is standaard uitgeschakeld.

   ![chlimage_1-333](assets/chlimage_1-333.png)

1. Klik of tik op **[!UICONTROL Save]** om de wijzigingen op te slaan.
