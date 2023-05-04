---
title: Connector configureren voor Microsoft SharePoint
seo-title: Configuring Connector for Microsoft SharePoint
description: Configureer Connector voor Microsoft SharePoint om communicatie tussen AEM formulieren en Microsoft SharePoint mogelijk te maken.
seo-description: Configure Connector for Microsoft SharePoint to enable communication between AEM forms and Microsoft SharePoint.
uuid: f1561b41-da20-4220-b13a-e78472a9449f
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/connecting_to_a_content_management_system
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 0ec881c9-8dcc-4847-9edf-24d9e6c4a7ea
exl-id: 9bd396a3-5da9-4355-ad76-e7132ac8aed8
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 0%

---

# Connector configureren voor Microsoft SharePoint {#configuring-connector-for-microsoft-sharepoint}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Connector voor Microsoft SharePoint maakt communicatie mogelijk tussen AEM formulieren en Microsoft SharePoint. Zie &quot;Connectors for ECM&quot; in [Servicereferentie](https://www.adobe.com/go/learn_aemforms_services_63).

1. Klik in de beheerconsole op Services > Connector voor Microsoft SharePoint.
1. Geef de volgende instellingen op voor uw SharePoint-server:

   **Hostnaam SharePoint-server:** Het poortnummer van de hostnaam van de webtoepassing op de SharePoint-server, in de notatie `[hostname]:[port]`.

   **Gebruikersnaam:** De gebruikersaccount die wordt gebruikt om verbinding te maken met de SharePoint-server.

   **Wachtwoord:** Wachtwoord voor de gebruikersaccount waarmee verbinding wordt gemaakt met de SharePoint-server

   **Domeinnaam:** Domein waar de SharePoint-server zich bevindt.

1. Klik op Opslaan.

## Microsoft SharePoint-configuratieservice {#microsoft-sharepoint-configuration-service}

De Microsoft SharePoint-configuratieservice `(MSSharePointConfigService)` Hiermee kunt u referenties opgeven voor de gebruiker van AEM formulier die imitatierechten heeft. Voor informatie over imitatierechten raadpleegt u [Connector configureren voor Microsoft SharePoint](https://help.adobe.com/en_US/AEMForms/6.1/SharePointConfig/index.html). Voer de volgende stappen uit om instellingen op te geven voor `MSSharePointConfigService`:

1. Klik in de beheerconsole op Services > Toepassingen en services > Servicebeheer.
1. Navigeer in de lijst met services en klik op `MSSharePointConfigService`.
1. Specificeer de volgende montages op de pagina van de Configuratie:

   * Gebruikersnaam voor een gebruiker met imitatierechten
   * Wachtwoord voor bovenstaande gebruiker

1. Klik op Opslaan.
