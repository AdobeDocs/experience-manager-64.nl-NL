---
title: AEM Forms aanroepen met API's
seo-title: Invoking AEM Forms using APIs
description: Adobe Experience Manager Forms is op J2EE gebaseerde bedrijfssoftware die bestaat uit services die werken binnen een gedeelde infrastructuur. Leer hoe u clienttoepassingen gebruikt om AEM Forms programmatisch aan te roepen met een Java API, webservices, Remoting en REST API.
seo-description: Adobe Experience Manager Forms is J2EE-based enterprise software that consists of services that operate within a shared infrastructure. Learn how to use client applications to invoke AEM Forms programmatically using a Java API, web services, Remoting, and REST API.
uuid: d100e106-e508-4d3c-ba8c-b5fe13c9e2d6
contentOwner: admin
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: development-tools, coding
discoiquuid: 1825e12c-0306-4e0a-9643-47ce1ce82132
role: Developer
exl-id: 6b60209f-aced-4698-97f1-b1a7782eef46
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 0%

---

# AEM Forms aanroepen met API&#39;s {#invoking-aem-forms-using-apis}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Adobe Experience Manager Forms is op J2EE gebaseerde bedrijfssoftware die bestaat uit services die werken binnen een gedeelde infrastructuur. De verrichtingen van de dienst verbruiken typisch of produceren documenten. Met AEM Forms kunt u de formulierwerkstroom combineren met elektronische formulieren, documentbeveiliging en het genereren van documenten in een geïntegreerde en samenhangende set services. Deze diensten kunnen van binnen en buiten de firewall worden betreden.

Clienttoepassingen kunnen AEM Forms-services programmatisch aanroepen met een Java API, webservices, Remoting en REST. Gebruikend beleidsconsole, kunt u de dienst vormen om een eindpunt bloot te stellen dat de diensten van AEM Forms door programmatically te roepen laat. Standaard zijn de meeste services vooraf geconfigureerd om eindpunten van verwijderingen, Java en webservices beschikbaar te maken.

Uw bedrijfsvereisten bepalen welke aanroepingsmethode moet worden gebruikt. Met de Java API kunt u bijvoorbeeld de AEM Forms-functionaliteit integreren in uw Java-bedrijfstoepassingen, zoals Java Entiteiten en Boodbonen. Eveneens, kunt u de functionaliteit van AEM Forms in .NET projecten (of andere projecten integreren die met ontwikkelomgevingen worden ontwikkeld die de normen van de Webdienst steunen) gebruikend de Webdiensten.

Voor services is een servicecontainer vereist die kan worden uitgevoerd, vergelijkbaar met de manier waarop EJB&#39;s (Enterprise JavaBeans™) een J2EE-container vereisen. AEM Forms bevat slechts één implementatie van een servicecontainer. De de dienstcontainer is verantwoordelijk voor het beheren van het leven van de dienst, met inbegrip van het opstellen van het en het verzekeren dat alle verzoeken worden verzonden naar de correcte dienst. Het beheert ook documenten die een dienst verbruikt of produceert.

>[!NOTE]
>
>Programmeren met AEM formulieren bevat geen informatie over het aanroepen van AEM Forms via Gecontroleerde mappen of e-mail.
