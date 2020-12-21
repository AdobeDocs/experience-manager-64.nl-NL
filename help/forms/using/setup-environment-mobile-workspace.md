---
title: Omgeving instellen voor AEM Forms-app
seo-title: Omgeving instellen voor AEM Forms-app
description: Hardware, software en licenties voor het samenstellen en implementeren van de AEM Forms-app.
seo-description: Hardware, software en licenties voor het samenstellen en implementeren van de AEM Forms-app.
uuid: 0c8f5259-8e9f-45ce-ade4-e14f1a41c0de
contentOwner: robhagat
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-app
discoiquuid: 72c3a451-fa57-4b12-8d25-fc2e6fa98adb
translation-type: tm+mt
source-git-commit: f13d358a6508da5813186ed61f959f7a84e6c19f
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 0%

---


# Omgeving instellen voor AEM Forms-app {#set-up-environment-for-aem-forms-app}

U hebt de volgende hardware, software en licenties nodig om de AEM Forms-app te maken en te implementeren:

## Voor Windows-apparaten {#for-windows-devices}

* Microsoft Windows 8.1 of Windows 10
* Microsoft Visual Studio 2015
* Microsoft Visual Studio Tools for Apache Cordova

## Voor iOS-apparaten {#for-ios-devices}

* Op Intel gebaseerde Apple Mac met Mac OS X 10.9.5 of hoger
* iOS SDK 8.4 of hoger
* Xcode-versie: Xcode 6.4 voor OS X of hoger
* Lidmaatschap van het iOS Developer Enterprise-programma
* Enterprise-certificaat voor de distributie van interne iOS-apps
* Apple iPad met iOS 8.4 of hoger

## Voor Android-apparaten {#for-android-devices}

* Android Development Toolkit (ADT-bundel) die kan worden gedownload van [https://developer.android.com/sdk/index.html](https://developer.android.com/sdk/index.html)
* Als het milieu opstelling op een systeem van MAC is, zou ADT in de omslag van Toepassingen moeten worden geïnstalleerd.
* Als ADT op een andere plaats op MAC geïnstalleerd is, of als het milieu opstelling op een systeem van Vensters is, moet de weg van ADT SDK in `local.properties` dossier worden bijgewerkt dat in `src\android` omslag in het gehaalde bronarchief `mobileworkspace-src.zip` beschikbaar is. Wijs in dit bestand de variabele `sdk.dir` naar de ADT SDK-locatie op uw bureaublad.

>[!NOTE]
>
>adobe-lc-mobileworkspace-src.zip bevat PhoneGap SDK 5.0. Controleer of PhoneGap SDK niet vooraf is geïnstalleerd.
