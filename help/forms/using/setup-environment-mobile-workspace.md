---
title: Omgeving instellen voor AEM Forms-app
seo-title: Set up environment for AEM Forms app
description: Hardware, software en licenties voor het samenstellen en implementeren van de AEM Forms-app.
seo-description: Hardware, software, and licenses to build and deploy the AEM Forms app.
uuid: 0c8f5259-8e9f-45ce-ade4-e14f1a41c0de
contentOwner: robhagat
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-app
discoiquuid: 72c3a451-fa57-4b12-8d25-fc2e6fa98adb
exl-id: 5c60d1a6-a4a2-4131-81e6-e39a5ab07dcf
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 0%

---

# Omgeving instellen voor AEM Forms-app {#set-up-environment-for-aem-forms-app}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

U hebt de volgende hardware, software en licenties nodig om de AEM Forms-app te maken en te implementeren:

## Voor Windows-apparaten {#for-windows-devices}

* Microsoft Windows 8.1 of Windows 10
* Microsoft Visual Studio 2015
* Microsoft Visual Studio Tools for Apache Cordova

## Voor iOS-apparaten {#for-ios-devices}

* Apple Mac met Intel-processor en Mac OS X 10.9.5 of hoger
* iOS SDK 8.4 of hoger
* Xcode-versie: Xcode 6.4 voor OS X of hoger
* Lidmaatschap van het iOS Developer Enterprise-programma
* Enterprise-certificaat voor de distributie van interne iOS-apps
* Apple iPad met iOS 8.4 of hoger

## Voor Android-apparaten {#for-android-devices}

* Android Development Toolkit (ADT-bundel) die kan worden gedownload van [https://developer.android.com/sdk/index.html](https://developer.android.com/sdk/index.html)
* Als de omgeving is ingesteld op een MAC-systeem, moet ADT worden geïnstalleerd in de map Programma&#39;s.
* Als de ADT op een andere locatie op MAC is geïnstalleerd of als de omgeving op een Windows-systeem is ingesteld, moet het ADT SDK-pad worden bijgewerkt in `local.properties` bestand dat beschikbaar is in `src\android` map in het geëxtraheerde bronarchief `mobileworkspace-src.zip`. Wijs in dit bestand de `sdk.dir` variabele naar de ADT SDK-locatie op uw bureaublad.

>[!NOTE]
>
>adobe-lc-mobileworkspace-src.zip bevat PhoneGap SDK 5.0. Controleer of PhoneGap SDK niet vooraf is geïnstalleerd.
