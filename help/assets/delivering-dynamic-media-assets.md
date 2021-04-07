---
title: Dynamic Media-middelen leveren
seo-title: Dynamic Media-middelen leveren
description: Leer hoe u dynamische media-elementen kunt leveren
seo-description: Leer hoe u dynamische media-elementen kunt leveren
uuid: e87754a9-4c34-4658-9971-cd7ceb26523f
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
discoiquuid: ec394bd3-2fa6-4f50-b974-bc10f643ecac
exl-id: e5110a90-ddc9-4244-8466-f91adfca8469
feature: Beheer van bedrijfsmiddelen
role: Business Practitioner
translation-type: tm+mt
source-git-commit: f9faa357f8de92d205f1a297767ba4176cfd1e10
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 9%

---

# Dynamic Media-middelen {#delivering-dynamic-media-assets} leveren

Hoe u dynamische media-elementen kunt leveren (zowel video als afbeeldingen), hangt af van de manier waarop uw website is geïmplementeerd.

Met Dynamic Media hebt u verschillende opties:

* Als uw website op AEM wordt gehost, wilt u de dynamische media-elementen rechtstreeks aan uw pagina toevoegen.
* Als uw website niet op AEM staat, kunt u kiezen uit:

   * Uw video of afbeelding insluiten op uw website.
   * Koppel URL&#39;s aan uw webtoepassing. Gebruik koppelingen wanneer u een videospeler wilt leveren als een pop-up- of modaal venster.
   * Als uw site reageert, kunt u [geoptimaliseerde afbeeldingen leveren.](responsive-site.md)

>[!NOTE]
>
>Slimme beeldverwerking werkt met bestaande voorinstellingen voor afbeeldingen en maakt gebruik van intelligentie tijdens de laatste milliseconde van levering om de bestandsgrootte van de afbeelding verder te beperken op basis van de snelheid van de browser of netwerkverbinding. Zie [Slimme beeldverwerking](imaging-faq.md) voor meer informatie.

Raadpleeg de volgende onderwerpen voor meer informatie:

* [Dynamic Media-elementen toevoegen aan webpagina&#39;s](adding-dynamic-media-assets-to-pages.md)
* [De video- of afbeeldingsviewer insluiten op een webpagina](embed-code.md)
* [Hotlinkbeveiliging in Dynamic Media activeren](https://helpx.adobe.com/experience-manager/6-4/assets/using/hotlink-protection.html)
* Digimarc (digitaal niet-zichtbaar watermerk) integreren met Dynamic Media (binnenkort beschikbaar)
* [URL&#39;s koppelen aan uw webapplicatie](linking-urls-to-yourwebapplication.md)
* [Geoptimaliseerde afbeeldingen leveren voor een responsieve site](responsive-site.md)
* [HTTP2-levering van content](http2.md)
* [Uw CDN-gecachete content ongeldig maken](invalidate-cdn-cached-content.md)
* [Regelsets gebruiken om URL&#39;s te transformeren](using-rulesets-to-transform-urls.md)

## HTTP/2 levering van Dynamic Media-middelen {#http-delivery-of-dynamic-media-assets}

AEM ondersteunt nu de levering van alle Dynamic Media-inhoud (afbeeldingen en video) via HTTP/2. Dit wil zeggen dat er een gepubliceerde URL of insluitcode voor de afbeelding of video beschikbaar is om te worden geïntegreerd met elke toepassing die een gehoste element accepteert. Dat gepubliceerde element wordt vervolgens geleverd via het HTTP/2-protocol. Deze leveringsmethode verbetert de manier waarop browsers en servers communiceren, waardoor u betere responstijd en laadtijden voor al uw Dynamic Media-middelen krijgt.

Zie [HTTP/2 Levering van Inhoud Veelgestelde Vragen](/help/sites-administering/scene7-http2faq.md) om meer te leren.
