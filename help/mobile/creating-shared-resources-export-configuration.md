---
title: Configuratie voor gedeelde bronnen exporteren
seo-title: Creating Shared Resources Export Configuration
description: Volg deze pagina voor meer informatie over het exporteren van gedeelde bronnen uit Adobe Experience Manager (AEM) voor uploaden naar AEM Mobile.
seo-description: Follow this page to learn about exporting shared resources from Adobe Experience Manager (AEM) for upload to AEM Mobile.
uuid: 99b8ff94-8135-4643-a15b-aa6fb91f5401
contentOwner: User
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/MOBILE
topic-tags: developing-on-demand-services-app
discoiquuid: 1edf6c76-ccb1-40b6-bdf6-924f1461cd28
exl-id: 92ee8c25-9f11-4743-a8e6-1f4986d09a6a
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 0%

---

# Configuratie voor gedeelde bronnen exporteren{#creating-shared-resources-export-configuration}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

>[!NOTE]
>
>Adobe raadt aan de SPA Editor te gebruiken voor projecten die renderen op basis van één pagina voor toepassingsframework op de client-side vereisen (bijvoorbeeld Reageren). [Meer informatie](/help/sites-developing/spa-overview.md).

>[!CAUTION]
>
>**Vereiste**:
>
>Alvorens over het creëren van en het wijzigen van gedeelde middelen te leren, zie [Inhoud synchroniseren](/help/mobile/mobile-ondemand-contentsync.md) de basisbeginselen te begrijpen.

AEM Mobile-gebruikers gebruiken Content Sync om live-inhoud te exporteren naar statische inhoud voor gebruik in Mobile Apps. Deze export vindt plaats wanneer inhoud vanuit AEM Mobile wordt geüpload naar Mobile On-Demand Services.

De eigenschap ***dps-exportTemplate*** in de bovenstaande tabel wordt het pad naar de exportconfiguraties van de app gedefinieerd. Stel deze eigenschap in om gedeelde bronnen te maken en te wijzigen.

In de volgende bronnen wordt beschreven hoe u gedeelde bronnen van Adobe Experience Manager (AEM) exporteert voor uploaden naar AEM Mobile.

Met gedeelde HTML-bronnen kunnen artikelen HTML-bronnen delen die anders voor alle artikelen moeten worden gedupliceerd en kunnen pictogrammen, lettertypen, javascript en css worden opgenomen.

De configuratie voor inhoudssynchronisatie vindt u op **&lt;dps-exporttemplate>/dps-HTMLResources>** moet worden geconfigureerd om alle inhoud te exporteren die een artikel vereist voor statische rendering van eigenschappen op een apparaat.

>[!CAUTION]
>
>U kunt de onderstaande stappen uitvoeren om voorbeelden van gedeelde bronnen weer te geven, alleen als u beschikt over:
>
>* de voorbeeldinhoud geïnstalleerd
>* uitvoeren, AEM
>* geen gevormde douanecontext of een verschillende haven
>


Zie de onderstaande stappen voor een voorbeeld van een gedeelde bron:

1. Open CRXDE Lite op uw AEM.
1. Bladeren naar dit pad *[/etc/contentSync/templates/dps-we-limited-app/dps-HTMLResources](http://localhost:4502/crx/de/index.jsp#/etc/contentsync/templates/dps-we-unlimited-app/dps-HTMLResources)* om de gedeelde voorbeeldbronnen weer te geven.

   U kunt alle eigenschappen bekijken die voor het creëren van uw gedeelde middelen zoals aangetoond in het hieronder cijfer worden vereist:

   ![chlimage_1-145](assets/chlimage_1-145.png)

>[!NOTE]
>
>De gedeelde middelen zouden moeten worden geupload of worden uitgevoerd naar AEM Mobile On-demand Services wanneer om het even welke gedeelde middelen veranderen.
