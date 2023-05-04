---
title: Configureren voor AEM toepassingen
seo-title: Configuring for AEM Apps
description: Leer hoe u AEM toepassingen configureert.
seo-description: Learn how to configure AEM Apps.
uuid: ab9acd93-da7f-4bb7-8d26-224044899068
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: operations
content-type: reference
discoiquuid: 34f24837-f5e2-41f0-a359-fdb695e1b8f2
exl-id: 593a588c-02f1-4b48-ac57-9348d6652bcc
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 0%

---

# Configureren voor AEM toepassingen{#configuring-for-aem-apps}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Adobe Experience Manager Apps biedt de mogelijkheid om de inhoud van uw toepassing via de lucht (OTA) bij te werken. De bijgewerkte inhoud wordt opgeslagen in de publicatieinstantie. Om de toepassing op uw apparaat toe te staan verbinding te maken met de publicatie-instantie en te controleren op updates, moet de publicatie-instantie worden geconfigureerd om een lege verwijzingskoptekst toe te staan.

## Leeg verwijzingskoptekst configureren {#configuring-empty-referrer-header}

Om de dienst van het verwijzingsfilter te vormen:

* Open de Apache Felix-console (**Configuraties**) om:
* https://&lt;server>:&lt;port_number>/system/console/configMgr
* Aanmelden als beheerder.
* In de **Configuraties** -menu, selecteert u: *Filter Apache Sling Referrer*
* Schakel het veld Lege toestaan in om lege/ontbrekende verwijzingskoppen toe te staan.
* Klikken **Opslaan** om uw wijzigingen op te slaan.

![chlimage_1-58](assets/chlimage_1-58.png)

Zie de [OSGI-configuratie-instellingen](/help/sites-deploying/osgi-configuration-settings.md) en [Beveiligingscontrolelijst - Problemen met de XSS-functie voor aanvragen voor andere sites](/help/sites-administering/security-checklist.md#protect-against-cross-site-request-forgery) voor nadere bijzonderheden.
