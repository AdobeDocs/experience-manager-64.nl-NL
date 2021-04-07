---
title: Het filter Referrer instellen op Leeg maken
seo-title: Het filter Referrer instellen op Leeg maken
description: Volg deze pagina voor meer informatie over het filter Referrer. Als u wilt dat de AEM Mobile Application Viewer apps kan weergeven op uw Author-instantie, moet u het HTML-referentiefilter instellen op 'allow empty'.
seo-description: Volg deze pagina voor meer informatie over het filter Referrer. Als u wilt dat de AEM Mobile Application Viewer apps kan weergeven op uw Author-instantie, moet u het HTML-referentiefilter instellen op 'allow empty'.
uuid: 4fb0f95c-ac8f-4a14-8c46-6616d9d4f380
contentOwner: User
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/MOBILE
topic-tags: administering-adobe-phonegap-enterprise
discoiquuid: 8fb7d088-94bf-4799-98b3-8fa58eef83df
exl-id: 81828b4c-cf0f-4722-8ae3-2e24be91a09b
translation-type: tm+mt
source-git-commit: bd94d3949f0117aa3e1c9f0e84f7293a5d6b03b4
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 0%

---

# Het plaatsen van Uw Filter van de Referentie om Leeg{#setting-your-referrer-filter-to-allow-empty} toe te staan

>[!NOTE]
>
>Adobe raadt aan de SPA Editor te gebruiken voor projecten die renderen op basis van één pagina voor toepassingsframework op de client-side vereisen (bijvoorbeeld Reageren). [Meer](/help/sites-developing/spa-overview.md) informatie.

Als u wilt dat de AEM Mobile Application Viewer apps kan weergeven op uw Author-instantie, moet u het HTML-referentiefilter instellen op &#39;allow empty&#39;.

Als u niet van plan bent de Application Viewer te gebruiken om toepassingen in ontwikkelings- en faseringsstaten te bekijken, hoeft u de standaardinstelling van het referentiefilter niet te wijzigen.

Navigeer binnen de actieve versie van Auteur van AEM naar: [http://localhost:4502/system/console/configMgr](http://localhost:4502/system/console/configMgr) en zoek naar &#39;Apache Sling Referrer Filter&#39;. Klik om het referentiefilter te bewerken en schakel het selectievakje &#39;Lege toestaan&#39; in (zie de afbeelding hieronder). Klik vervolgens op de knop Opslaan en sluit de browserpagina.

![Filterinstellingen referentie](assets/chlimage_1-106.png)
