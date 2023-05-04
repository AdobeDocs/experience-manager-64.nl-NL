---
title: Overzicht eCommerce
seo-title: eCommerce Overview
description: AEM algemene eCommerce is beschikbaar als onderdeel van de standaardinstallatie en biedt u de volledige functionaliteit van het eCommerce-kader.
seo-description: AEM generic eCommerce is available as part of the standard installation and provides you with the full functionality of the eCommerce framework.
uuid: 7be42b1e-f1d6-4891-96f8-0133b3a299a1
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: e-commerce
content-type: reference
discoiquuid: cb043066-aefc-4b68-b302-2b5dd710a786
feature: Commerce Integration Framework
exl-id: d84cd0ec-4586-45c1-a07a-a4d50fcbb629
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 0%

---

# Overzicht eCommerce{#ecommerce-overview}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

AEM algemene eCommerce is beschikbaar als onderdeel van een standaardinstallatie en biedt u de volledige functionaliteit van het eCommerce-kader.

Adobe verstrekt twee versies van het Kader van de Integratie van de Handel:

|  | CIF on prem | CIF Cloud |
|-------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------|
| Ondersteunde AEM | AEM on-prem of AMS 6.x | AEM AMS 6.4 en 6.5 |
| Terug | - AEM, Java <br> - Monolithische integratie, pre-build-toewijzing (sjabloon)<br> - JCR-opslagplaats | - Magento <br>- Java en JavaScript <br>- Geen gegevens over handel opgeslagen in de gegevensopslagruimte van het GCO |
| Voorkant | Gerenderde pagina&#39;s AEM op de server | Toepassing gemengde pagina (hybride rendering) |
| Productcatalogus | - Producimporteur, redacteur, caching in AEM <br>- Gewone catalogi met AEM- of proxypagina&#39;s | - Geen producten importeren <br>- Algemene sjablonen <br>- Gegevens op aanvraag via connector |
| Schaalbaarheid | - Kan maximaal een paar miljoen producten ondersteunen (afhankelijk van het gebruiksgeval) <br> - Caching on Dispatcher | - Geen volumebeperking <br>- Caching op Dispatcher of CDN |
| Gestandaardiseerd gegevensmodel | Nee | Ja, Magento GraphQL-schema |
| Beschikbaarheid | Ja:<br> - SAP Commerce Cloud (extensie die wordt bijgewerkt ter ondersteuning van AEM 6.4 en Hybris 5 (standaard) en die compatibel blijft met Hybris 4 <br>- Salesforce Commerce Cloud (connector open-sourced voor ondersteuning van AEM 6.4) | Ja via open bron via GitHub. <br> Magento Commerce (Ondersteunt Magento 2.3.2 (standaard) en compatibel met Magento 2.3.1). |
| Wanneer gebruiken | Beperkte gebruiksgevallen: Voor scenario&#39;s waarbij kleine, statische catalogi mogelijk moeten worden geïmporteerd | Voorkeursoplossing in de meeste gebruikscategorieën |


## Andere implementaties implementeren {#deploying-other-implementations}

* [SAP Commerce Cloud](/help/sites-deploying/sap-commerce-cloud.md)
* [Salesforce Commerce Cloud](https://github.com/adobe/commerce-salesforce)
* [Magento](https://www.adobe.io/apis/experiencecloud/commerce-integration-framework/integrations.html#!AdobeDocs/commerce-cif-documentation/master/integrations/02-AEM-Magento.md)

>[!NOTE]
>
>Voor informatie over concepten en het beheren van eCommerce implementaties, zie [eCommerce beheren](/help/sites-administering/ecommerce.md).
>
>Voor informatie over het uitbreiden van eCommerce-mogelijkheden raadpleegt u [Ontwikkeling van eCommerce](/help/sites-developing/ecommerce.md).
