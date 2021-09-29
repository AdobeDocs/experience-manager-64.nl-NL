---
title: Dubbele detectie inschakelen
description: Leer hoe u dubbele elementen in AEM kunt detecteren.
contentOwner: AG
feature: Asset Management,Asset Reports
role: User,Admin
exl-id: 138cf649-9e21-415e-9861-b07caacc85db
source-git-commit: 8948bca63f1f5ec9d94ede2fb845ed01b4e23333
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 0%

---

# Dubbele detectie inschakelen {#enabling-duplicate-detection}

Als u probeert een middel te uploaden dat in de Middelen van Adobe Experience Manager bestaat, identificeert de dubbele opsporingseigenschap het als dubbel. Dubbele detectie is standaard uitgeschakeld. Voer de volgende stappen uit om de functie in te schakelen:

1. Open de pagina **[!UICONTROL Adobe Experience Manager Web Console Configuration]** op `https://[server]:[port]/system/console/configMgr`.
1. Bewerk de configuratie voor de servlet **[!UICONTROL Day CQ DAM Create Asset]**.
1. Selecteer de optie **[!UICONTROL detect duplicate]** en klik/tik **[!UICONTROL Save]**.

   ![Selecteer de optie Duplicaat detecteren in de servlet](assets/chlimage_1-377.png)

De functie voor het opsporen van dubbele gegevens is nu ingeschakeld in Elementen [!DNL Experience Manager]. Wanneer een gebruiker een middel probeert te uploaden dat in AEM bestaat, controleert het systeem op conflict en wijst op het. De elementen worden geïdentificeerd met behulp van SHA-1-hash die is opgeslagen op `jcr:content/metadata/dam:sha1`. Dit betekent dat dubbele elementen worden gedetecteerd, ongeacht de bestandsnamen.

>[!MORELIKETHIS]
>
>* [Elementen dupliceren in een bestaande opslagplaats (een zelfstudie van een lid van de gemeenschap)](https://experience-aem.blogspot.com/2019/06/aem-65-find-duplicate-assets-binaries-in-existing-repository.html)

