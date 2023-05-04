---
title: Het programmatisch beheren van PreferencesNodes
seo-title: Programmatically managing the PreferencesNodes
description: Gebruik de API (Java) van de Dienst van de Manager van de Voorkeur om de Knooppunten van de Voorkeur programmatically te beheren.
seo-description: Use the Preferences Manager Service API (Java) to programmatically manage the Preferences Nodes.
uuid: f0cb117a-a6cc-4ca5-8511-b3bc9f6738e9
contentOwner: admin
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: operations
discoiquuid: 9d4dba7f-49d8-4112-bc8a-04dafc99a936
role: Developer
exl-id: d580b32c-a344-4a8c-bd61-0949da76d981
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 0%

---

# Het programmatisch beheren van de Knooppunten van de Voorkeur {#programmatically-managing-the-preferencesnodes}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Dit onderwerp beschrijft hoe u de Dienst API van de Manager van de Voorkeur (Java) kunt gebruiken om de Knoop van de Voorkeur programmatically te beheren.

U kunt configuratie-instellingen handmatig wijzigen via de gebruikersinterface van de beheerder. Als u de opties wilt wijzigen, navigeert u naar `Home>Settings>User Management> Configuration>Manual Configuration`. Importeren `config.xml` na het aanbrengen van de veranderingen, zou u merken dat alle veranderingen behalve veranderingen die bij knoop worden aangebracht `/Adobe/Adobe Experience Manager Forms/Config/UM persist` verloren gaan. In het voorbeeld van het importeren en exporteren van gebruikersbeheer wordt het wijzigen van configuratie-instellingen voor andere componenten niet ondersteund. Deze wijzigingen kunnen nu worden aangebracht met `PreferencesManagerServiceClient` API&#39;s.

**Overzicht van de stappen** Voer de volgende stappen uit om de knooppunten van Voorkeuren programmatisch te beheren:

1. Inclusief projectbestanden.
1. Een PreferencesManagerService-client maken
1. De juiste rol- of machtigingsbewerkingen aanroepen

**Projectbestanden opnemen**

Neem de benodigde bestanden op in uw ontwikkelingsproject. Als u een clienttoepassing maakt met Java, neemt u de benodigde JAR-bestanden op. Als u webservices gebruikt, moet u ervoor zorgen dat u de proxybestanden opneemt.

**Een PreferencesManagerService-client maken**

Alvorens u een verrichting van PreferencesManagerService van het Beheer van de Gebruiker programmatically kunt uitvoeren, moet u een cliënt tot stand brengen PreferencesManagerService. Met de Java API wordt dit verwezenlijkt door een voorwerp te creëren PreferencesManagerServiceClient.

**De juiste rol- of machtigingsbewerkingen aanroepen**

Zodra u de de dienstcliënt hebt gecreeerd, kunt u de verrichtingen van de Manager van de Voorkeur dan aanhalen. De de dienstcliënt staat u toe om toestemmingen te lezen en te plaatsen.
