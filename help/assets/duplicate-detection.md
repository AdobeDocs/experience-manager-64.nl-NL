---
title: Dubbele detectie inschakelen
description: Leer hoe u dubbele elementen in AEM kunt detecteren.
contentOwner: AG
feature: Middelenbeheer, Asset Reports
role: Business Practitioner,Administrator
exl-id: 138cf649-9e21-415e-9861-b07caacc85db
translation-type: tm+mt
source-git-commit: bd94d3949f0117aa3e1c9f0e84f7293a5d6b03b4
workflow-type: tm+mt
source-wordcount: '144'
ht-degree: 0%

---

# Dubbele detectie {#enabling-duplicate-detection} inschakelen

Als u probeert een middel te uploaden dat in de Middelen van Adobe Experience Manager (AEM) bestaat, identificeert de dubbele opsporingseigenschap het als dubbel. Dubbele detectie is standaard uitgeschakeld. Voer de volgende stappen uit om de functie in te schakelen:

1. Open de pagina **[!UICONTROL Adobe Experience Manager Web Console Configuration]** op `https://[server]:[port]/system/console/configMgr`.
1. Bewerk de configuratie voor de servlet **[!UICONTROL Day CQ DAM Create Asset]**.
1. Selecteer de optie **[!UICONTROL detect duplicate]** en klik/tik **[!UICONTROL Save]**.

   ![Selecteer de optie Duplicaat detecteren in de servlet](assets/chlimage_1-377.png)

De functie Dupliceren detecteren is nu ingeschakeld in AEM Assets. Wanneer een gebruiker een middel probeert te uploaden dat in AEM bestaat, controleert het systeem op conflict en wijst op het. De elementen worden geïdentificeerd met behulp van SHA-1-hash die is opgeslagen op `jcr:content/metadata/dam:sha1`. Dit betekent dat dubbele elementen worden gedetecteerd, ongeacht de bestandsnamen.

>[!MORELIKETHIS]
>
>* [Elementen dupliceren in een bestaande opslagplaats (een zelfstudie van een lid van de gemeenschap)](https://experience-aem.blogspot.com/2019/06/aem-65-find-duplicate-assets-binaries-in-existing-repository.html)

