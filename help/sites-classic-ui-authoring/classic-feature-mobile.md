---
title: Een pagina ontwerpen voor mobiele apparaten
seo-title: Authoring a Page for Mobile Devices
description: Wanneer u een mobiele pagina ontwerpt, wordt de pagina weergegeven op een manier die het mobiele apparaat emuleert. Wanneer u de pagina ontwerpt, kunt u schakelen tussen verschillende emulators om te zien wat de eindgebruiker ziet wanneer hij of zij de pagina opent.
seo-description: When authoring a mobile page, the page is displayed in a way that emulates the mobile device. When authoring the page, you can switch between several emulators to see what the end-user sees when accessing the page.
uuid: ca16979d-6e5f-444d-b959-ae92542039b2
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: site-features
discoiquuid: 430a27b5-f344-404f-8bf8-0d91b49b605e
exl-id: 26324f89-f5e2-40bc-96b4-0f3faa08bdd1
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 0%

---

# Een pagina ontwerpen voor mobiele apparaten{#authoring-a-page-for-mobile-devices}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Wanneer u een mobiele pagina ontwerpt, wordt de pagina weergegeven op een manier die het mobiele apparaat emuleert. Wanneer u de pagina ontwerpt, kunt u schakelen tussen verschillende emulators om te zien wat de eindgebruiker ziet wanneer hij of zij de pagina opent.

Apparaten worden gegroepeerd in de categoriefunctie, de functie voor slim afdrukken en de functie voor aanraken op basis van de mogelijkheden van de apparaten om een pagina weer te geven. Wanneer de eindgebruiker tot een mobiele pagina toegang heeft, AEM ontdekt het apparaat en verzendt de vertegenwoordiging die aan zijn apparatengroep beantwoordt.

>[!NOTE]
>
>Als u een mobiele site wilt maken op basis van een bestaande standaardsite, maakt u een live kopie van de standaardsite. (Zie [Een actieve kopie maken voor verschillende kanalen](/help/sites-administering/msm-livecopy.md).)
>
>AEM ontwikkelaars kunnen nieuwe apparaatgroepen maken. (Zie [Apparaatgroepfilters maken.](/help/sites-developing/groupfilters.md))

Gebruik de volgende procedure om een mobiele pagina te ontwerpen:

1. Ga in uw browser naar **Siteadmin** console.
1. Open de **Producten** pagina hieronder **Websites** >> **Site voor mobiele demo** >> **Engels**.

1. Schakel over naar een andere emulator. Hiervoor kunt u:

   * Klik op het apparaatpictogram boven aan de pagina.
   * Klik op de knop **Bewerken** in de **Sidetrap** en selecteert u het apparaat in het keuzemenu.

1. Sleep de **Tekst en afbeelding** van het tabblad Mobiel van de Sidetrap naar de pagina.
1. Bewerk de component en voeg wat tekst toe. Klikken **OK** om de wijzigingen op te slaan.

De pagina ziet er hetzelfde uit als:

![mobileipademu](assets/mobileipademu.png)

>[!NOTE]
>
>De emulators worden uitgeschakeld wanneer een pagina op de auteurinstantie wordt opgevraagd bij een mobiel apparaat. U kunt ontwerpen met behulp van de interface met aanraakbediening.
