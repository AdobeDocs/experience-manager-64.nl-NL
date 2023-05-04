---
title: Een veilige AEM Forms-app voor iOS maken
seo-title: Building a secure AEM Forms app for iOS
description: Stappen om een veilige AEM Forms-app te maken.
seo-description: Steps to build a secure AEM Forms app.
uuid: 6c4b160f-4d0c-4976-9609-9196795b6c8e
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-app
discoiquuid: 90cd8ba5-4f47-4074-bc54-6a7bb8afe256
exl-id: 7efc657e-b662-47db-8e70-62a37f3a3051
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 0%

---

# Een veilige AEM Forms-app voor iOS maken {#building-a-secure-aem-forms-app-for-ios}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

U moet het Xcode-project voor de AEM Forms-app archiveren om het installatieprogramma (een .ipa-bestand) en een eigenschappenlijst (een .plist-bestand) te maken. Het eigenschappenlijstbestand bevat configuratiegegevens van de interne app die wordt gehost, zoals de naam en de hostlocatie van de app. Voor meer informatie over het dossier van de bezitslijst, zie [Informatie over eigenschappenbestanden](https://developer.apple.com/library/ios/#documentation/general/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html).

1. Meld u aan bij de volgende website:

   [https://developer.apple.com/account/ios/identifier/bundle](https://developer.apple.com/account/ios/identifier/bundle)

1. Maak een toepassings-id. Ga voor gedetailleerde stappen om een toepassings-id te maken naar [Toepassings-id&#39;s maken en configureren](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/MaintainingProfiles/MaintainingProfiles.html).
1. Als u de bundle-id voor de iOS-toepassing voor uw app wilt configureren, klikt u op **[!UICONTROL Configure App ID]**.
1. Selecteer onder aan de webpagina de optie **[!UICONTROL Enable for Data Protection]**. Geef de opties voor gegevensbescherming op.

   Klik op **[!UICONTROL Done]**.

1. Navigeer naar Provisioning->Distributie en maak een nieuw profiel met de toepassings-id die in stap 3 is geconfigureerd.
1. Download en voeg het inrichtingsprofiel toe aan de Xcode en de iPad.
1. Meld u aan bij uw Mac-computer waarop Xcode en iOS SDK zijn geïnstalleerd en geconfigureerd.
1. Open de `AEM Forms.xcodeproj` project in Xcode.
1. Klikken **[!UICONTROL AEM Forms]**, onder **[!UICONTROL TARGETS]**, selecteert u **[!UICONTROL AEM Forms]**. Selecteer **[!UICONTROL Build Settings]** tabblad, zoekt u de **[!UICONTROL Code Signing Entitlement]** en selecteert u in het vervolgkeuzemenu Entitlements de optie **[!UICONTROL LC Enterprise]** optie.
1. Zoek en open de `LC Enterprise.entitlements` in de Xcode voor bewerking. Onder de **XCode aanspraken, **voeg het zelfde zeer belangrijk-waardepaar toe zoals huidig in uw inrichtingsprofiel.
1. In de **[!UICONTROL Build Settings]** tabblad, klikt u op **[!UICONTROL All]** en klik vervolgens op **[!UICONTROL Combined]**.
1. Van de **[!UICONTROL Settings]** lijst, uitvouwen **[!UICONTROL Code Signing]**.
1. Voor **[!UICONTROL Code Signing Identity]** selecteert u de gewenste handtekening. Zorg ervoor dat dezelfde handtekening is geselecteerd voor **[!UICONTROL Debug]**, **[!UICONTROL Release]**, en **[!UICONTROL Any iOS SDK]**.
1. Onder **[!UICONTROL PROJECT]**, selecteert u **[!UICONTROL AEM Forms]** en zorgt ervoor dat de juiste handtekening wordt geselecteerd **[!UICONTROL Code Signing Identity]**, **[!UICONTROL Debug]**, **[!UICONTROL Release]** en **[!UICONTROL Any iOS SDK]**.
1. AEM Forms-app ontwikkelen en distribueren. Ga voor gedetailleerde instructies voor het samenstellen en distribueren van de AEM Forms-app naar [Het installatieprogramma voor de AEM Forms-app maken](setup-xcode-project-build-installer.md#build-the-installer-for-the-mobile-workspace-app).
