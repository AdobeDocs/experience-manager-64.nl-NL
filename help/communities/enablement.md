---
title: Functies van Enablement configureren
seo-title: Functies van Enablement configureren
description: Functies voor activering configureren in Gemeenschappen
seo-description: Functies voor activering configureren in Gemeenschappen
uuid: 27be3128-1a7d-412e-99a9-6e3b3b0aec1c
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 765a3d9b-4552-403e-872c-fdf684ac271d
role: Beheerder
translation-type: tm+mt
source-git-commit: 75312539136bb53cf1db1de03fc0f9a1dca49791
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 0%

---


# Functies {#configuring-enablement-features} configureren

## Overzicht {#overview}

De functies voor activering bieden de mogelijkheid [enablement Communities](overview.md#enablement-community) te maken.

* Deze functie vereist extra licenties voor gebruik in een productieomgeving.

Het gebruik van de functies voor activering vereist het volgende:

Installatie van:

* **SCORMSharable Content**
Object Reference Model (SCORM) is een verzameling standaarden en specificaties voor e-learning. SCORM definieert ook hoe inhoud kan worden verpakt in een overdraagbaar ZIP-bestand.

* ****
MySQLMySQL is een relationele database die voornamelijk wordt gebruikt voor het bijhouden en rapporteren van SCORM-gegevens voor Enablement en voor tabellen voor het bijhouden van videovoortgang. Voor het SCORM for enablement-functiepakket is het MySQL JDBC-stuurprogramma vereist.

* **mpegFFmpeg is een oplossing voor het converteren en streamen van audio en video en wordt, indien geïnstalleerd, gebruikt voor een correcte transcodering van**
Video-elementen [ ](../../help/sites-authoring/default-components-foundation.md#video). Voor gemeenschappen van activering wordt deze methode in de auteursomgeving gebruikt om metagegevens voor geüploade bronnen op te halen en om een miniatuur te genereren die wordt weergegeven wanneer de bron wordt vermeld.

Instellen van:

* **Community**
ManagersVoor gemeenschappen van activering, alleen leden van de 
`Community Enablement Managers` De gebruikersgroep kan de rol van worden toegewezen,  `*Community Site* Enablement Manager`waarvan de toestemmingen inhoudsverwezenlijking, taken, en lidbeheer in het publiceren milieu kunnen omvatten.

Optionele configuratie van:

* **Adobe**
AnalyticsIntegration met Adobe Analytics voegt uitgebreide rapportfuncties toe en ondersteunt de toevoeging Video Heartbeat aan Analytics.

* **Dispatcher**

## Configuratiestappen {#configuration-steps}

Hieronder volgen de stappen die nodig zijn voor gemeenschappen die zich toeleggen op de opvang van vluchtelingen.

Elke stap verbindt met documentatie die de noodzakelijke details verstrekt.

**Op alle auteur-/publicatieinstanties:**

1. **[Installeer het JDBC-stuurprogramma voor](deploy-communities.md#jdbc-driver-for-mysql)**
MySQLUse Web Console (bundels): Installeer  *http://localhost:4502/system/console/*
bundlesInstalleer  ** voordat u SCORM-pakket installeert

1. **[SCORM-](deploy-communities.md#scorm-package)**
pakket installerenPakketbeheer gebruiken: 
*http://localhost:4502/crx/packmgr/*

**Op elke server:**

1. **[MySQL, MySQL Workbench installeren](mysql.md)**

1. **[MySQL-](mysql.md#database-setup)**
databases installerenSQL-scripts uitvoeren die zijn gedownload van de auteurinstantie
\
   MySQL Workbench gebruiken

**Op dezelfde serverhostingauteurinstantie:**

1. **[mpeg installeren](ffmpeg.md)**

**Op alle auteur-/publicatieinstanties:**

1. **[Configureer JDBC-verbindingen](mysql.md#configure-jdbc-connections)**
poolGebruik webconsole (configMgr): 
*http://localhost:4502/system/console/configMgr*

1. **[SCORM engine](mysql.md#aem-communities-scormengine-service)**
serviceUse Web Console (configMgr) configureren: 
*http://localhost:4502/system/console/configMgr*

1. **[vorm CSRF](mysql.md#adobe-granite-csrf-filter)**
filtersGebruik de Console van het Web (configMgr): 
*http://localhost:4502/system/console/configMgr*

**Instantie van auteur:**

1. (*optioneel*) **[Analyseservice configureren](analytics.md)**
Hulpmiddelen, Plaatsing, de console van Cloud Services van het gebruik: 
*http://localhost:4502/etc/cloudservices/sitecatalyst.html*

1. **[Configureer](ffmpeg.md#configure-ffmpeg-transcoding-service)**
FormsUse Workflow/Models-console

1. **[laat de Console van het Web van](deploy-communities.md#tunnel-service-on-author)**
ServiceUse van de Tunnel (configMgr) toe: 
*http://localhost:4502/system/console/configMgr*

1. **[Community-](users.md#creating-community-members)** beheerders makenVoor een auteursomgeving gebruikt u de klassieke UI-beveiligingsconsole:  *http://localhost:4502/*
gebruiker(s) met pad = /home/users/community

   * Voeg leden toe aan de volgende groepen:

      * Community Enablement Managers
      * Administrateurs van Gemeenschappen

## Verzending {#dispatcher}

Wanneer de implementatie [AEM Dispatcher](https://helpx.adobe.com/experience-manager/dispatcher/using/dispatcher.html) bevat, moeten de `clientheader`en `filter`secties worden gewijzigd om de schakelingsfuncties naar behoren te laten werken. Zie [Dispatcher configureren voor Communities](dispatcher.md#enablement).
