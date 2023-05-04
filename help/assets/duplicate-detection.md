---
title: Dubbele detectie inschakelen
description: Leer hoe u dubbele elementen in AEM kunt detecteren.
contentOwner: AG
feature: Asset Management,Asset Reports
role: User,Admin
exl-id: 138cf649-9e21-415e-9861-b07caacc85db
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 0%

---

# Dubbele detectie inschakelen {#enabling-duplicate-detection}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Als u probeert een middel te uploaden dat in de Middelen van Adobe Experience Manager bestaat, identificeert de dubbele opsporingseigenschap het als dubbel. Dubbele detectie is standaard uitgeschakeld. Voer de volgende stappen uit om de functie in te schakelen:

1. Open de **[!UICONTROL Adobe Experience Manager Web Console Configuration]** pagina bij `https://[server]:[port]/system/console/configMgr`.
1. De configuratie van de servlet bewerken **[!UICONTROL Day CQ DAM Create Asset]**.
1. Selecteer **[!UICONTROL detect duplicate]** en klikken/tikken **[!UICONTROL Save]**.

   ![Selecteer de optie Duplicaat detecteren in de servlet](assets/chlimage_1-377.png)

De functie Dupliceren detecteren is nu ingeschakeld in [!DNL Experience Manager] Elementen. Wanneer een gebruiker een middel probeert te uploaden dat in AEM bestaat, controleert het systeem op conflict en wijst op het. De elementen worden geïdentificeerd met behulp van SHA-1-hash die is opgeslagen op `jcr:content/metadata/dam:sha1`, wat betekent dat dubbele elementen worden gedetecteerd, ongeacht de bestandsnamen.

>[!MORELIKETHIS]
>
>* [Elementen dupliceren in een bestaande opslagplaats (een zelfstudie van een lid van de gemeenschap)](https://experience-aem.blogspot.com/2019/06/aem-65-find-duplicate-assets-binaries-in-existing-repository.html)

