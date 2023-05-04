---
title: Het beheerderswachtwoord configureren bij installatie
seo-title: Configure the Admin Password on Installation
description: Leer hoe u het beheerderswachtwoord bij AEM installatie wijzigt.
seo-description: Learn how to change the Admin Password on AEM Installation.
uuid: 06da9890-ed63-4fb6-88d5-fd0e16bc4ceb
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: Security
content-type: reference
discoiquuid: 00806e6e-3578-4caa-bafa-064f200a871f
exl-id: 6dd289ee-13fd-46be-82cd-aa69852397c9
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 0%

---

# Het beheerderswachtwoord configureren bij installatie{#configure-the-admin-password-on-installation}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Overzicht {#overview}

Sinds versie 6.3 kan AEM het beheerderswachtwoord via de opdrachtregel worden ingesteld wanneer een nieuwe instantie wordt geïnstalleerd.

Bij eerdere versies van AEM moest het wachtwoord voor de beheerdersaccount, samen met het wachtwoord voor verschillende andere consoles, na de installatie worden gewijzigd.

Deze eigenschap voegt de faciliteit toe om een nieuw beheerderwachtwoord voor de bewaarplaats en de Motor van het Servlet tijdens de installatie van een AEM instantie te plaatsen, zo eliminerend de behoefte om het achteraf manueel te doen.

>[!CAUTION]
>
>Houd er rekening mee dat deze functie niet van toepassing is op de Felix Console, waarvoor het wachtwoord handmatig moet worden gewijzigd. Zie voor meer informatie de relevante [Sectie Beveiligingscontrolelijst](/help/sites-administering/security-checklist.md#change-default-passwords-for-the-aem-and-osgi-console-admin-accounts).

## Hoe gebruik ik het? {#how-do-i-use-it}

Deze functie wordt automatisch geactiveerd als u ervoor kiest AEM te installeren via de opdrachtregel, in plaats van te dubbelklikken op de JAR vanuit een bestandssysteemverkenner.

De algemene synthax voor het runnen van een AEM instantie van de bevellijn is:

```shell
java -jar aem6.3.jar
```

Wanneer u de instantie uitvoert vanaf de opdrachtregel, krijgt u de mogelijkheid om het beheerderswachtwoord te wijzigen tijdens het installatieproces:

![chlimage_1-116](assets/chlimage_1-116.png)

>[!NOTE]
>
>De vraag om het admin wachtwoord te veranderen zal slechts tijdens de installatie van een nieuw AEM geval verschijnen.

## De markering -nointeractive gebruiken {#using-the-nointeractive-flag}

U kunt ook het wachtwoord opgeven in een eigenschappenbestand. Dit wordt gedaan door te gebruiken `-nointeractive` markering gecombineerd met de `-Dadmin.password.file` system, eigenschap.

Hieronder ziet u een voorbeeld:

```shell
java -Dadmin.password.file =/path/to/passwordfile.properties -jar aem6.3.jar -nointeractive
```

Het wachtwoord in de `passwordfile.properties` bestand moet de volgende indeling hebben:

```xml
admin.password = 12345678
```

>[!NOTE]
>
>Als u gewoon de `-nointeractive` parameter zonder `-Dadmin.password.file` systeemeigenschap, AEM het standaardbeheerderswachtwoord gebruiken zonder dat u wordt gevraagd dit te wijzigen, in feite gedrag uit eerdere versies repliceert. Deze niet-interactieve modus kan worden gebruikt voor geautomatiseerde installaties die de opdrachtregel in een installatiescript gebruiken.
