---
title: Video-uitvoeringen
description: Video-uitvoeringen
contentOwner: AG
feature: Video, uitvoeringen
role: Zakelijke praktiserer
translation-type: tm+mt
source-git-commit: 29e3cd92d6c7a4917d7ee2aa8d9963aa16581633
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 0%

---


# Video-uitvoeringen {#video-renditions}

Met Adobe Experience Manager (AEM)-elementen worden video-uitvoeringen gegenereerd voor video-elementen van verschillende indelingen, zoals OGG, FLV enzovoort.

AEM Assets ondersteunt statische en dynamische uitvoeringen (met DM gecodeerde uitvoeringen) voor media-elementen.

Statische uitvoeringen worden native gegenereerd met behulp van FFMPEG (geïnstalleerd en beschikbaar op het systeempad) en opgeslagen in de inhoudsopslagplaats.

De met DM gecodeerde vertoningen worden opgeslagen in de volmachtsserver en bij runtime gediend.

AEM elementen bieden ondersteuning voor het afspelen van deze uitvoeringen op de client.

Als u de vertoningen van een bepaald video-element wilt weergeven, opent u de elementenpagina en tikt u op het pictogram Algemene navigatie. Kies vervolgens **[!UICONTROL Renditions]** in de lijst.

![chlimage_1-478](assets/chlimage_1-478.png)

De lijst met video-uitvoeringen wordt weergegeven in het deelvenster **[!UICONTROL Renditions]**.

![chlimage_1-479](assets/chlimage_1-479.png)

[Configureer Dynamic Media Cloud-services ](config-dynamic.md) om de proxyserver voor met DM gecodeerde uitvoeringen te configureren.

[Maak een overeenkomstig videoprofiel](video-profiles.md) om video-uitvoeringen met de gewenste parameters te genereren.

Nadat u de proxyserver hebt geconfigureerd en videoprofielen hebt gemaakt, kunt u deze videovoorinstelling opnemen in een verwerkingsprofiel en het verwerkingsprofiel toepassen op een map.

>[!NOTE]
>
>Het afspelen van audio werkt niet voor OGG- en WAV-bestanden in Internet Explorer 11. Er verschijnt een fout &quot;Ongeldige bron&quot; op de pagina met elementdetails voor elementen met de extensie OGG of WAV.
>
>Op MS Edge en iPad worden OGG-bestanden niet afgespeeld en wordt een niet-ondersteunde indelingsfout weergegeven.
