---
title: Integreren met Adobe Analytics
seo-title: Integrating with Adobe Analytics
description: Leer hoe u AEM met Adobe Analytics kunt integreren.
seo-description: Learn how to integrate AEM with Adobe Analytics.
uuid: 8329d891-1897-46f6-80ee-40244b079c0e
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: integration
content-type: reference
discoiquuid: 0089394f-0107-49eb-ad73-52e9cabe71b1
exl-id: ca11bfcd-06d1-4ca9-9069-afa91d8a6610
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 18%

---

# Integreren met Adobe Analytics{#integrating-with-adobe-analytics}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Door Adobe Analytics en AEM te integreren, kunt u uw webpaginageactiviteit volgen:

* Met een Adobe Analytics-configuratie kunnen AEM verifiëren met Adobe Analytics.
* Een framework geeft de gegevens aan die naar uw Adobe Analytics-rapportenpakket worden verzonden.

De gegevens omvatten pagina- en gebruikersgegevens; bijvoorbeeld:

* gegevens die AEM componenten verzamelen
* koppelingsklikken
* videogebruiksinformatie
* het aantal pagina-bezoeken van Adobe Analytics

Met de volgende pagina&#39;s kunt u de integratie configureren:

* [Verbinding maken met Adobe Analytics en frameworks maken](/help/sites-administering/adobeanalytics-connect.md)
* [Koppeling bijhouden configureren voor Adobe Analytics](/help/sites-administering/adobeanalytics-link.md)
* [Componentgegevens toewijzen aan Adobe Analytics-eigenschappen](/help/sites-administering/adobeanalytics-mapping.md)
* [Video bijhouden configureren voor Adobe Analytics](/help/sites-administering/adobeanalytics-video.md)

U kunt ook de opdracht [Wizard Inschakelen](/help/sites-administering/opt-in.md) om de integratie gemakkelijk uit te voeren.

>[!NOTE]
>
>Zie ook het &#39;Hoe kan ik?-artikel: [AEM integreren met Adobe Target en Adobe Analytics met behulp van DTM](https://helpx.adobe.com/experience-manager/using/integrate-digital-marketing-solutions.html).

## Aanvullende informatie {#further-information}

Zie:

* [Uitbreiding van de Adobe Analytics-integratie](/help/sites-developing/extending-analytics.md) voor informatie over het ontwikkelen van componenten die gebruikersgegevens verzamelen en het kader van Adobe Analytics aanpassen.
* Het kennisbankartikel, [Adobe Analytics-integratie - problemen oplossen](https://helpx.adobe.com/experience-manager/kb/sitecatalystintegrationtroubleshooting.html), voor informatie over het oplossen van problemen uw integratie van Adobe Analytics.

>[!NOTE]
>
>Als u Adobe Analytics gebruikt met een aangepaste proxyconfiguratie, moet u [twee OSGi-bundels configureren](/help/sites-deploying/configuring-osgi.md) (bijvoorbeeld met de webconsole) die voor de **Apache HTTP Client**-proxyconfiguraties vereist zijn. Beide zijn vereist omdat sommige functies van AEM de 3.x-API&#39;s gebruiken, terwijl andere de 4.x-API&#39;s gebruiken. Configureren:
>
>* **Day Commons HTTP Client 3.1** om de 3.x API te configureren;\
   >  bijvoorbeeld: [http://localhost:4502/system/console/configMgr/com.day.commons.httpclient](http://localhost:4502/system/console/configMgr/com.day.commons.httpclient)
>
>* **Apache HTTP Components Proxy Configuration** om de 4.x API te configureren;
>
>  bijvoorbeeld: [http://localhost:4502/system/console/configMgr/org.apache.http.proxyconfigurator](http://localhost:4502/system/console/configMgr/org.apache.http.proxyconfigurator)
