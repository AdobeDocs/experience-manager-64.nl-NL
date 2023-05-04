---
title: Video-uitvoeringen
description: Video-uitvoeringen
contentOwner: AG
feature: Video,Renditions
role: User
exl-id: 9fc93034-e83a-42b5-901d-7867b4a850a8
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 0%

---

# Video-uitvoeringen {#video-renditions}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Adobe Experience Manager Assets genereert video-uitvoeringen voor video-elementen van verschillende indelingen, zoals OGG, FLV enzovoort.

AEM Assets ondersteunt statische en dynamische uitvoeringen (met DM gecodeerde uitvoeringen) voor media-elementen.

Statische uitvoeringen worden native gegenereerd met behulp van FFMPEG (geïnstalleerd en beschikbaar op het systeempad) en opgeslagen in de inhoudsopslagplaats.

De met DM gecodeerde vertoningen worden opgeslagen in de volmachtsserver en bij runtime gediend.

AEM elementen bieden ondersteuning voor het afspelen van deze uitvoeringen op de client.

Als u de vertoningen van een bepaald video-element wilt weergeven, opent u de elementenpagina en tikt u op het pictogram Algemene navigatie. Kies vervolgens **[!UICONTROL Renditions]** in de lijst.

![chlimage_1-478](assets/chlimage_1-478.png)

De lijst met video-uitvoeringen wordt weergegeven in het dialoogvenster **[!UICONTROL Renditions]** deelvenster.

![chlimage_1-479](assets/chlimage_1-479.png)

Om de volmachtsserver voor DM-Gecodeerde vertoningen te vormen, [Dynamic Media Cloud-services configureren.](config-dynamic.md)

U kunt als volgt video-uitvoeringen met de gewenste parameters genereren: [een overeenkomstig videoprofiel maken](video-profiles.md).

Nadat u de proxyserver hebt geconfigureerd en videoprofielen hebt gemaakt, kunt u deze videovoorinstelling opnemen in een verwerkingsprofiel en het verwerkingsprofiel toepassen op een map.

>[!NOTE]
>
>Het afspelen van audio werkt niet voor OGG- en WAV-bestanden in Internet Explorer 11. Er verschijnt een fout &quot;Ongeldige bron&quot; op de pagina met elementdetails voor elementen met de extensie OGG of WAV.
>
>In MS Edge en iPad worden OGG-bestanden niet afgespeeld en wordt een niet-ondersteunde indelingsfout weergegeven.
