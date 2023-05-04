---
title: Connector configureren voor IBM Content Manager
seo-title: Configuring Connector for IBM Content Manager
description: Configureer de Connector voor IBM Content Manager om communicatie tussen AEM formulieren en IBM Content Manager mogelijk te maken.
seo-description: Configure the Connector for IBM Content Manager to enable communication between AEM forms and IBM Content Manager.
uuid: 3d55169d-93e3-4d4e-b18b-2a3394e1de3b
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/connecting_to_a_content_management_system
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 3094b178-3b1a-46b3-8fbd-c20388afa3a7
exl-id: 8c65531e-f4f0-4cc4-b328-eaefb5662cf1
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 0%

---

# Connector configureren voor IBM Content Manager{#configuring-connector-for-ibm-content-manager}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Connector voor IBM Content Manager maakt communicatie mogelijk tussen AEM formulieren en IBM Content Manager. Zie &quot;Connectors for ECM&quot; in [Servicereferentie](https://www.adobe.com/go/learn_aemforms_services_63).

## De IBM Content Manager-verbinding configureren {#configure-the-ibm-content-manager-connection}

1. Klik in de beheerconsole op Services > Connector voor IBM Content Manager.
1. Voer in het vak Naam datastore de naam in van de datastore van IBM Content Manager waarmee u verbinding wilt maken. Als de database lokaal is, voert u de naam van de database in. Als de database extern is, voert u de naam van de alias in.
1. Voer in het vak Gebruikersnaam de gebruikersnaam in van een gebruiker die verbinding maakt met de datastore van IBM Content Manager.
1. Voer in het vak Wachtwoord het wachtwoord van de gebruiker in.
1. (Optioneel) Voer in het vak Tekenreeks Alias-verbinding aanvullende verbindingsargumenten in. In de meeste gevallen moet dit vak leeg zijn. Raadpleeg de documentatie bij IBM voor meer informatie.
1. Klik op Opslaan.

## Validatie van service-instellingen {#validation-of-service-settings}

Als u een onjuiste alias, gebruikersnaam of wachtwoord voor dataStore invoert, krijgt u de volgende resultaten, afhankelijk van het feit of de Content Repository Connector voor IBM Content Manager momenteel wordt uitgevoerd:

* Als de dienst wordt tegengehouden, wanneer u de informatie van de de dienstconfiguratie opslaat, verschijnt geen fout. Nochtans, de volgende tijd u de dienst begint, zal een uitzondering worden geworpen en de dienst zal niet beginnen.
* Als de dienst is begonnen, wanneer u de informatie van de de dienstconfiguratie opslaat, probeert de dienst om de referentie informatie onmiddellijk te bevestigen. In dit geval treedt een fout op en worden de configuratiegegevens niet opgeslagen.
