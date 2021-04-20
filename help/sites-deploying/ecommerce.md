---
title: Overzicht eCommerce
seo-title: Overzicht eCommerce
description: 'AEM algemene eCommerce is beschikbaar als onderdeel van de standaardinstallatie en biedt u de volledige functionaliteit van het eCommerce-kader.  '
seo-description: 'AEM algemene eCommerce is beschikbaar als onderdeel van de standaardinstallatie en biedt u de volledige functionaliteit van het eCommerce-kader.  '
uuid: 7be42b1e-f1d6-4891-96f8-0133b3a299a1
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: e-commerce
content-type: reference
discoiquuid: cb043066-aefc-4b68-b302-2b5dd710a786
feature: Commerce Integration Framework
exl-id: d84cd0ec-4586-45c1-a07a-a4d50fcbb629
translation-type: tm+mt
source-git-commit: bd94d3949f0117aa3e1c9f0e84f7293a5d6b03b4
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 0%

---

# Overzicht eCommerce{#ecommerce-overview}

AEM algemene eCommerce is beschikbaar als onderdeel van een standaardinstallatie en biedt u de volledige functionaliteit van het eCommerce-kader.

Adobe verstrekt twee versies van het Kader van de Integratie van de Handel:

|  | CIF on prem | CIF Cloud |
|-------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------|
| Ondersteunde AEM | AEM on-prem of AMS 6.x | AEM AMS 6.4 en 6.5 |
| Terug | - AEM, Java <br> - Monolithische integratie, pre-build mapping (sjabloon)<br> - JCR-opslagplaats | - Magento <br>- Java en Javascript <br>- Geen gegevens van de Handel opgeslagen in de bewaarplaats van JCR |
| Voorkant | Gerenderde pagina&#39;s AEM op de server | Toepassing gemengde pagina (hybride rendering) |
| Productcatalogus | - Producimporteur, redacteur, caching in AEM <br> - Gewone catalogi met AEM of volmachtspagina&#39;s | - Geen product importeren <br>- Algemene sjablonen <br>- Gegevens op aanvraag via connector |
| Schaalbaarheid | - Kan maximaal een paar miljoen producten ondersteunen (afhankelijk van het gebruik) <br> - Caching op Dispatcher | - Geen volumebeperking <br>- Caching op Dispatcher of CDN |
| Gestandaardiseerd gegevensmodel | Nee | Ja, Magento GraphQL-schema |
| Beschikbaarheid | Ja:<br> - SAP Commerce Cloud (extensie bijgewerkt voor ondersteuning van AEM 6.4 en Hybris 5 (standaard) en handhaaft compatibiliteit met Hybris 4 <br>- Salesforce Commerce Cloud (connector open-sourced voor ondersteuning van AEM 6.4) | Ja via open bron via GitHub. <br> Magento Commerce (Ondersteunt Magento 2.3.2 (standaard) en compatibel met Magento 2.3.1). |
| Wanneer gebruiken | Beperkte gebruiksgevallen: Voor scenario&#39;s waarbij kleine, statische catalogi mogelijk moeten worden geïmporteerd | Voorkeursoplossing in de meeste gebruikscategorieën |


## Andere implementaties {#deploying-other-implementations} implementeren

* [SAP Commerce Cloud](/help/sites-deploying/sap-commerce-cloud.md)
* [Salesforce Commerce Cloud](https://github.com/adobe/commerce-salesforce)
* [Magento](https://www.adobe.io/apis/experiencecloud/commerce-integration-framework/integrations.html#!AdobeDocs/commerce-cif-documentation/master/integrations/02-AEM-Magento.md)

>[!NOTE]
>
>Voor informatie over concepten en het beheren van eCommerce implementaties, zie [Administering eCommerce](/help/sites-administering/ecommerce.md).
>
>Voor informatie over het uitbreiden van de mogelijkheden van de eCommerce, zie [Developing eCommerce](/help/sites-developing/ecommerce.md).
