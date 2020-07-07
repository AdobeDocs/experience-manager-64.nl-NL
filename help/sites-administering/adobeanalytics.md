---
title: Integreren met Adobe Analytics
seo-title: Integreren met Adobe Analytics
description: Leer hoe u AEM kunt integreren met Adobe Analytics.
seo-description: Leer hoe u AEM kunt integreren met Adobe Analytics.
uuid: 8329d891-1897-46f6-80ee-40244b079c0e
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: integration
content-type: reference
discoiquuid: 0089394f-0107-49eb-ad73-52e9cabe71b1
translation-type: tm+mt
source-git-commit: 98fae2d51d73bda946f3c398e9276fe4d5a8a0fe
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 21%

---


# Integreren met Adobe Analytics{#integrating-with-adobe-analytics}

Door Adobe Analytics en AEM te integreren, kunt u uw webpaginageactiviteit volgen:

* Met een Adobe Analytics-configuratie kan AEM verifiëren met Adobe Analytics.
* Een framework geeft de gegevens aan die naar uw Adobe Analytics-rapportenpakket worden verzonden.

De gegevens omvatten pagina- en gebruikersgegevens; bijvoorbeeld:

* gegevens die door AEM-componenten worden verzameld
* koppelingsklikken
* videogebruiksinformatie
* het aantal pagina-bezoeken van Adobe Analytics

Met de volgende pagina&#39;s kunt u de integratie configureren:

* [Verbinding maken met Adobe Analytics en frameworks maken](/help/sites-administering/adobeanalytics-connect.md)
* [Koppelingen bijhouden configureren voor Adobe Analytics](/help/sites-administering/adobeanalytics-link.md)
* [Componentgegevens toewijzen aan Adobe Analytics-eigenschappen](/help/sites-administering/adobeanalytics-mapping.md)
* [Video bijhouden configureren voor Adobe Analytics](/help/sites-administering/adobeanalytics-video.md)

U kunt de [Opt-in tovenaar](/help/sites-administering/opt-in.md) ook gebruiken om de integratie gemakkelijk uit te voeren.

>[!NOTE]
>
>Zie ook het &#39;Hoe kan ik?-artikel: [AEM integreren met Adobe Target en Adobe Analytics met behulp van DTM](https://helpx.adobe.com/experience-manager/using/integrate-digital-marketing-solutions.html).

## Aanvullende informatie {#further-information}

Zie:

* [De Adobe Analytics-integratie](/help/sites-developing/extending-analytics.md) uitbreiden voor informatie over het ontwikkelen van componenten die gebruikersgegevens verzamelen en het Adobe Analytics-framework aanpassen.
* Het kennisbankartikel, [Adobe Analytics-integratie - Problemen](https://helpx.adobe.com/experience-manager/kb/sitecatalystintegrationtroubleshooting.html)oplossen, voor informatie over het oplossen van problemen met uw integratie in Adobe Analytics.

>[!NOTE]
>
>Als u Adobe Analytics gebruikt met een aangepaste proxyconfiguratie, moet u [twee OSGi-bundels configureren](/help/sites-deploying/configuring-osgi.md) (bijvoorbeeld met de webconsole) die voor de **Apache HTTP Client**-proxyconfiguraties vereist zijn. Beide zijn vereist omdat sommige functies van AEM de 3.x-API&#39;s gebruiken, terwijl andere de 4.x-API&#39;s gebruiken. Configureren:
>
>* **Day Commons HTTP Client 3.1** om de 3.x API te configureren;\
   >  bijvoorbeeld [http://localhost:4502/system/console/configMgr/com.day.commons.httpclient](http://localhost:4502/system/console/configMgr/com.day.commons.httpclient)
   >
   >
* **Apache HTTP Components Proxy Configuration** om de 4.x API te configureren;
>
>  
bijvoorbeeld [http://localhost:4502/system/console/configMgr/org.apache.http.proxyconfigurator](http://localhost:4502/system/console/configMgr/org.apache.http.proxyconfigurator)

