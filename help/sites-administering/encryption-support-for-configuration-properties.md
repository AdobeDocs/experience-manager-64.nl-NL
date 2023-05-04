---
title: Coderingsondersteuning voor configuratieeigenschappen
seo-title: Encryption Support for Configuration Properties
description: Coderingsondersteuning voor configuratieeigenschappen
seo-description: null
uuid: 26dc5e46-9332-4d9b-8874-895b90391e8c
contentOwner: User
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: security
discoiquuid: 4e08c297-aa4b-44cf-84c8-1e11582d9ebb
exl-id: 077a940d-19de-4d19-ad99-61f465e68205
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 0%

---

# Coderingsondersteuning voor configuratieeigenschappen{#encryption-support-for-configuration-properties}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Overzicht {#overview}

Met deze functie kunnen alle OSGi-configuratie-eigenschappen worden opgeslagen in een beveiligd versleuteld formulier in plaats van tekst te wissen. Het formulier in de gebruikersinterface van de webconsole wordt gebruikt om gecodeerde tekst te maken op basis van wisbare tekst met behulp van de master coderingssleutel voor het hele systeem.

De steun van de Insteekmodule van de Configuratie OSGi werd toegevoegd om het bezit te decrypteren alvorens het door de dienst wordt gebruikt.

>[!NOTE]
>
>De diensten die een gecodeerde waarde verwachten moeten de controle gebruiken IsProtected om te zien of wordt de waarde gecodeerd alvorens te proberen om het te decrypteren, aangezien het reeds kan gedecrypteerd zijn.

## Coderingsondersteuning inschakelen {#enabling-encryption-support}

Deze stappen tonen hoe te om het wachtwoord SMTP voor de dienst van de Post te coderen. U kunt deze stappen uitvoeren voor een OSGI-eigenschap die u wilt coderen.

1. Ga naar de AEM webconsole op *https://&lt;serveraddress>:&lt;serverport>/system/console/configMgr*
1. Ga in de linkerbovenhoek naar **Hoofd - Crypto Steun**

   ![chlimage_1-325](assets/chlimage_1-325.png)

1. De **Adobe Experience Manager Web Console Crypto-ondersteuning** wordt weergegeven.

   ![screen_shot_2018-08-01at113417am](assets/screen_shot_2018-08-01at113417am.png)

1. In de **Onbewerkte tekst** Voer de tekst in van de vertrouwelijke gegevens die u wilt beveiligen.
1. Selecteren **Protect**. De beveiligde tekst wordt weergegeven als gecodeerde tekst.

   ![screen_shot_2018-08-01at113844am](assets/screen_shot_2018-08-01at113844am.png)

1. Kopieer de beveiligde tekst uit Stap#5 en plak deze in de waarde OSGI-formulier. In dit voorbeeld worden de versleutelde **SMTP-wachtwoord** wordt toegevoegd aan de *CQ-mailservice op dag*.

   ![screen_shot_2016-12-18at105809pm](assets/screen_shot_2016-12-18at105809pm.png)

1. Sla de eigenschappen van de Day CQ Mail Service op. Het SMTP-wachtwoord wordt nu verzonden als een gecodeerde waarde.

## Decoderingsondersteuning {#decryption-support}

AEM verstrekt nu een Insteekmodule van de Configuratie om configuratieeigenschappen te decrypteren. Deze AEM insteekmodule zal automatisch de duidelijke teksteigenschappen decoderen en terugwinnen.
