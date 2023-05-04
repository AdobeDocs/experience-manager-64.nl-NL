---
title: Consistentie- en reiscontroles
seo-title: Consistency and Traversal Checks
description: Leer hoe u consistentiecontroles en transversale controles uitvoert.
seo-description: Learn how to perform consistency and traversal checks.
uuid: 0304e378-7c60-4bf5-9052-d01149d2a6df
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
discoiquuid: af9a3e9d-194a-42e5-be28-b238e0c1e55e
feature: Configuring
exl-id: 67dfa0f7-24ac-41ae-83c9-3bb1a8656502
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 0%

---

# Consistentie- en reiscontroles{#consistency-and-traversal-checks}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Bij de upgrade kunnen er problemen optreden als gevolg van inconsistenties in de werkruimte. U kunt of een testverbetering in werking stellen om te zien of zal dit een kwestie zijn, of de consistentiecontroles als preventieve actie in werking stellen.

Als u een testverbetering in werking stelt die wegens werkruimteinconsistenties ontbreekt zult u ingangen gelijkend op het volgende in crx-quickstart/logs/crx/error.log zien:

```xml
*ERROR* TarPersistenceManager: No bundle found for uuid 'deadbeef-cafe-babe-cafe-babecafebabe'
 ...
*ERROR* RepositoryImpl: Failed to initialize workspace 'crx.default'
javax.jcr.RepositoryException: Error indexing workspace: Error indexing workspace: Error indexing workspace
...
```

## Een consistentiecontrole uitvoeren {#perform-a-consistency-check}

Als u een consistentiecontrole wilt uitvoeren, navigeert u naar de beheerpagina voor JMX Mbean** com.adobe.granite (Repository)**. Ga in het AEM hoofdscherm naar:

**Gereedschappen > Webconsole > Main (op menubalk) > JMX > com.adobe.granite (opslagplaats)**

Op een standaardinstallatie vindt u deze hier:  **[|Toon mij|](http://localhost:4502/system/console/jmx/com.adobe.granite%3Atype%3DRepository)**

In de **Bewerkingen** op de pagina vindt u twee methoden: **`traversalCheck`** en **`consistencyCheck`**. Als u een controle wilt uitvoeren, klikt u op de bewerking en voert u de gewenste parameters in.

![chlimage_1-117](assets/chlimage_1-117.png)
