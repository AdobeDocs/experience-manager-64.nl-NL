---
title: JCR-integratie
seo-title: JCR Integration
description: Tips voor wanneer u op JCR-niveau moet integreren
seo-description: Tips for when you must integrate at the JCR level
uuid: 11518baf-521e-471d-ad4f-2baa76075cfa
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: best-practices
discoiquuid: e6647a11-a36e-4808-bb61-29b2895c6b1d
exl-id: 3e9727a5-32f8-40ad-aa06-619f50d109b2
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 0%

---

# JCR-integratie{#jcr-integration}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Voorkeur voor de Sling Resource API naar de JCR API {#prefer-the-sling-resource-api-to-jcr-api}

De Sling API werkt op een hoger, abstract niveau dan de JCR API. Hierdoor kan uw code herbruikbaar en onafhankelijk van de onderliggende opslag zijn. Hierdoor wordt het gemakkelijker om externe virtuele gegevens indien nodig via het ResourceProvider-mechanisme op te nemen.

## Vermijd waar mogelijk vragen {#avoid-queries-wherever-possible}

Het is altijd sneller om door de gegevensopslagplaats te navigeren om gegevens op te halen dan om een vraag in werking te stellen. Er zijn gevallen waarin de vragen noodzakelijk zullen zijn, zoals een eindgebruikersvraag of het moeten gestructureerde inhoud van over de volledige bewaarplaats vinden, maar voor alle andere gevallen, wordt het verkieslijk om aan de noodzakelijke knopen te navigeren. Vragen moeten altijd worden vermeden in renderlogica, zoals navigatiecomponenten, een &quot;lijst met recente items&quot;, tellingen van items enzovoort. In deze gevallen is het beter om door de hiërarchie te lopen of het resultaat vooraf in cache te plaatsen, zodat het direct kan worden gebruikt wanneer het wordt gerenderd.

## Het bereik van de GCR-waarneming beperken {#restrict-the-scope-of-jcr-observation}

Bij het luisteren naar gebeurtenissen in de repository is het belangrijk om het bereik zoveel mogelijk te beperken. Het is bijvoorbeeld veel beter te luisteren naar een gebeurtenis op `/etc/mycompany` dan luisteren naar `/etc`. Luister nooit naar gebeurtenissen in de hoofdmap van de opslagplaats. Bovendien, zorg ervoor dat de callback methodes zo snel mogelijk uitvoeren wanneer er niets voor hen is te doen.

## Elimineren van het gebruik van JCR-beheertoegang {#eliminate-use-of-jcr-admin-access}

Vanaf AEM 6, login Administratieve is afgekeurd zoals het krijgen van een administratieve zitting van ResourceResolverFactory. Eerder, zouden de de dienstrekeningen voor de achterkantoorverrichtingen moeten worden gecreeerd die dit type van toegang zouden vereisen en ResourceResolverFactory kan worden gebruikt om een ResourceResolver voor deze rekening te krijgen.
