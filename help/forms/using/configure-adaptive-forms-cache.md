---
title: Cache voor aangepaste formulieren configureren
seo-title: Configure adaptive forms cache
description: De cache voor adaptieve formulieren is speciaal ontworpen voor adaptieve formulieren en documenten. Het slaat adaptieve formulieren en adaptieve documenten in het cachegeheugen op om de tijd te verkorten die nodig is om een adaptief formulier of document op de client te genereren.
seo-description: The adaptive forms cache is designed specifically for adaptive forms and documents. It caches adaptive forms and adaptive documents with the objective of reducing the time required to render an adaptive form or document on the client.
uuid: 3bd4e405-1eab-4e02-95cd-eb6ac25d18e3
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: Configuration
discoiquuid: dd18f7b5-882d-4e81-ab3d-85f1e5d74992
role: Admin
exl-id: 6a610e9d-beec-486d-b1d2-78b5fec44c52
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 0%

---

# Cache voor aangepaste formulieren configureren {#configure-adaptive-forms-cache}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Een cache is een mechanisme om de toegangstijd voor gegevens te verkorten, de latentie te verminderen en de invoer-/uitvoersnelheid (I/O) te verbeteren. In de cache van adaptieve formulieren worden alleen de HTML-inhoud en de JSON-structuur van een adaptief formulier opgeslagen zonder dat vooraf ingevulde gegevens worden opgeslagen. Hierdoor wordt de tijd die nodig is om een adaptief formulier of document op de client te genereren, verkort. Het is specifiek ontworpen voor adaptieve formulieren en ondersteunt ook adaptieve documenten.

>[!NOTE]
>
>Wanneer u de cache voor adaptieve formulieren gebruikt, gebruikt u de AEM Dispatcher om clientbibliotheken (CSS en JavaScript) van een adaptief formulier of document in cache te plaatsen.

>[!NOTE]
>
>Zorg tijdens het ontwikkelen van aangepaste componenten op de server die wordt gebruikt voor ontwikkeling dat de cache van adaptieve formulieren uitgeschakeld blijft.

## De cache configureren {#configure-the-cache}

Voer de volgende stappen uit om de cache voor adaptieve formulieren te configureren:

1. Ga naar AEM webconsoleconfiguratiebeheer op `https://[server]:[port]/system/console/configMgr`.
1. Klikken **Adaptieve vorm en interactieve communicatie Webkanaalconfiguratie** om de configuratiewaarden te bewerken.
1. Geef in het dialoogvenster Configuratiewaarden bewerken het maximumaantal formulieren of documenten op dat een instantie van de AEM Forms-server in cache kan plaatsen in het dialoogvenster **Aantal adaptieve Forms** veld. De standaardwaarde is 100.

   >[!NOTE]
   >
   >Als u de cache wilt uitschakelen, stelt u de waarde in het veld Number Adaptive Forms in op **0**. De cache wordt opnieuw ingesteld en alle formulieren en documenten worden uit de cache verwijderd wanneer u de cachemonfiguratie uitschakelt of wijzigt.

   ![Dialoogvenster Configuratie voor HTML-cache van adaptieve formulieren](assets/cache-configuration-edit.png)

1. Klikken **Opslaan** om de configuratie op te slaan.
