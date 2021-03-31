---
title: 'Adobe IMS-verificatie en ondersteuning voor Admin Consoles voor AEM Managed Services '
seo-title: 'Adobe IMS-verificatie en ondersteuning voor Admin Consoles voor AEM Managed Services '
description: Leer hoe u de Admin Console in AEM gebruikt.
seo-description: Leer hoe u de Admin Console in AEM gebruikt.
uuid: 3f5b32c7-cf62-41a4-be34-3f71bbf224eb
contentOwner: sarchiz
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: Security
content-type: reference
discoiquuid: f6112dea-a1eb-4fd6-84fb-f098476deab7
translation-type: tm+mt
source-git-commit: e672f4edf87bd4d3af985e2ea598feb4e26d1553
workflow-type: tm+mt
source-wordcount: '1769'
ht-degree: 17%

---


# Adobe IMS-verificatie en ondersteuning voor Admin Consoles voor AEM Managed Services {#adobe-ims-authentication-and-admin-console-support-for-aem-managed-services}

>[!NOTE]
>
>Deze functie is alleen beschikbaar voor klanten van Adobe Managed Services.

## Inleiding {#introduction}

AEM 6.4.3.0 introduceert Admin Console steun voor AEM instanties en Adobe IMS (het Systeem van Identity Management) gebaseerde authentificatie voor **AEM klanten Managed Services**.

AEM aan boord gaan aan de Admin Console zal AEM klanten van Managed Services toestaan om alle gebruikers van de Experience Cloud in één console te beheren. Gebruikers en groepen kunnen worden toegewezen aan productprofielen die aan AEM instanties zijn gekoppeld, zodat zij zich kunnen aanmelden bij een specifieke instantie.

## Belangrijkste kenmerken {#key-highlights}

* AEM IMS-verificatieondersteuning is alleen bedoeld voor AEM-auteurs, -beheerders of -ontwikkelaars, niet voor externe eindgebruikers van de site zoals sitebezoekers
* De Admin Console zal AEM klanten van Managed Services als organisaties IMS en hun Instanties als Contexten van het Product vertegenwoordigen. Systeem- en productbeheerders van klanten kunnen de toegang tot instanties beheren
* AEM Managed Services zal klantentopologieën met de Admin Console synchroniseren. Er zal één geval van AEM het Context van het Product van Managed Services per Instantie in de Admin Console zijn.
* Productprofielen in Admin Console bepalen welke instanties een gebruiker kan openen
* Federatieve verificatie met behulp van eigen SAML 2-compatibele identiteitsproviders van klanten wordt ondersteund
* Alleen Enterprise- of federatieve id&#39;s (voor Single Sign-On van klant) worden ondersteund, geen persoonlijke Adobe-id&#39;s.
* Gebruikersbeheer (in Adobe Admin Console) blijft eigendom van de beheerders van de klant.

## Architectuur {#architecture}

IMS de Authentificatie werkt door het protocol OAuth tussen AEM en het eindpunt van Adobe IMS te gebruiken. Zodra een gebruiker aan IMS is toegevoegd en een Adobe ID heeft, kan deze zich aanmelden bij AEM Managed Services-instanties met IMS-referenties.

De gebruikerslogin stroom wordt hieronder getoond, zal de gebruiker aan IMS en naar keuze aan klant IDP voor bevestiging van SSO worden opnieuw gericht en dan terug naar AEM.

![image2018-9-23_23-55-8](assets/image2018-9-23_23-55-8.png)

## {#how-to-set-up} instellen

### Organisaties on-boarden in Admin Console {#onboarding-organizations-to-admin-console}

De klant die zich aan boord van de Admin Console houdt, is een eerste vereiste voor het gebruik van Adobe IMS voor AEM verificatie.

Als eerste stap, zouden de klanten een Organisatie moeten hebben die in Adobe IMS wordt voorzien. Adobe Enterprise-klanten worden vertegenwoordigd als IMS-organisaties in de [Adobe Admin Console](https://helpx.adobe.com/nl/enterprise/using/admin-console.html).

AEM Managed Services-klanten moeten al over een organisatie beschikken en als onderdeel van de IMS-provisioning zullen de exemplaren van de klant in de Admin Console beschikbaar worden gesteld voor het beheer van gebruikersrechten en toegang.

De overgang naar IMS voor gebruikersverificatie is een gezamenlijke inspanning van AMS en klanten, waarbij elk van hen zijn werkschema&#39;s moet voltooien.

Zodra een klant als IMS Organisatie bestaat en AMS met levering van de klant voor IMS wordt gedaan, is dit de samenvatting van de vereiste configuratiewerkschema&#39;s:

![image2018-9-23_23-33-25](assets/image2018-9-23_23-33-25.png)

1. De aangewezen Systeembeheerder ontvangt een uitnodiging om zich aan te melden bij de Admin Console
1. System Admin beweert Domain om de eigendom van het domein te bevestigen (in dit voorbeeld acme.com)
1. Systeembeheer stelt gebruikersmappen in
1. Systeembeheerder configureert de Identiteitsprovider (IDP) in de Admin Console voor SSO-installatie.
1. De AEM Admin beheert de lokale groepen, de toestemmingen en de voorrechten zoals gebruikelijk. Zie Synchronisatie van gebruikers en groepen

>[!NOTE]
>
>Zie het artikel [deze pagina](https://helpx.adobe.com/nl/enterprise/using/set-up-identity.html) voor meer informatie over de Adobe Identity Management Basics, inclusief de IDP-configuratie.
>
>Zie het artikel [deze pagina](https://helpx.adobe.com/nl/enterprise/managing/user-guide.html) voor meer informatie over Enterprise Administration en Admin Console.

### Gebruikers aan boord nemen van de Admin Console {#onboarding-users-to-the-admin-console}

Er zijn drie manieren aan boord van gebruikers afhankelijk van de grootte van de klant en hun voorkeur:

1. Handmatig gebruikers en groepen maken in Admin Console
1. Een CSV-bestand met gebruikers uploaden
1. Synchroniseer gebruikers en groepen van de bedrijfs Actieve Folder van de klant.

#### Handmatige toevoeging via de gebruikersinterface van de Admin Console {#manual-addition-through-admin-console-ui}

Gebruikers en groepen kunnen handmatig worden gemaakt in de gebruikersinterface van de Admin Console. Deze methode kan worden gebruikt als ze niet over een groot aantal gebruikers beschikken om te beheren. Bijvoorbeeld een aantal van minder dan 50 AEM gebruikers.

Gebruikers kunnen ook handmatig worden gemaakt als de klant deze methode al gebruikt voor het beheer van andere Adobe-producten, zoals Analytics-, Target- of Creative Cloud-toepassingen.

![image2018-9-23_20-39-9](assets/image2018-9-23_20-39-9.png)

#### Bestand uploaden in de gebruikersinterface van de Admin Console {#file-upload-in-the-admin-console-ui}

Voor een eenvoudige afhandeling van het maken van gebruikers kan een CSV-bestand worden geüpload om gebruikers in bulk toe te voegen:

![image2018-9-23_18-59-57](assets/image2018-9-23_18-59-57.png)

#### User Sync Tool {#user-sync-tool}

Met het Hulpprogramma voor gebruikerssynchronisatie (UST in het kort) kunnen zakelijke klanten Adobe-gebruikers maken of beheren met Active Directory of andere geteste OpenLDAP-directoryservices. De doelgebruikers zijn de Beheerders van de Identiteit van IT (de Folder van de Onderneming en de Beheerders van het Systeem) die het hulpmiddel zullen kunnen installeren en vormen. Het opensource-programma kan worden aangepast, zodat klanten het kunnen aanpassen aan hun eigen specifieke vereisten.

Wanneer de looppas van de Synchronisatie van de Gebruiker, het een lijst van gebruikers van de Actieve Folder van de organisatie (of een andere compatibele gegevensbron) haalt en het met de lijst van gebruikers binnen de Admin Console vergelijkt. Vervolgens wordt de Adobe User Management-API opgeroepen, zodat de Admin Console wordt gesynchroniseerd met de directory van de organisatie. De wisselstroom is volledig eenrichtingsverkeer; eventuele bewerkingen die in de Admin Console zijn aangebracht, worden niet naar de map doorgestuurd.

Het hulpmiddel staat systeemadmin toe om gebruikersgroepen in de folder van de klant met productconfiguratie en gebruikersgroepen in de Admin Console in kaart te brengen, staat de nieuwe versie UST ook dynamische verwezenlijking van gebruikersgroepen in de Admin Console toe.

Voor het instellen van User Sync moet de organisatie een set referenties maken op dezelfde manier als voor het gebruik van de [User Management-API](https://www.adobe.io/apis/cloudplatform/usermanagement/docs/setup.html).

![image2018-9-23_13-36-56](assets/image2018-9-23_13-36-56.png)

De User Sync wordt op deze locatie gedistribueerd via de Adobe Github-repository:

[https://github.com/adobe-apiplatform/user-sync.py/releases/latest](https://github.com/adobe-apiplatform/user-sync.py/releases/latest)

Merk op dat een pre-versieversie 2.4RC1 met de dynamische steun van de groepsverwezenlijking beschikbaar is en hier kan worden gevonden: [https://github.com/adobe-apiplatform/user-sync.py/releases/tag/v2.4rc1](https://github.com/adobe-apiplatform/user-sync.py/releases/tag/v2.4rc1)

De belangrijkste functies voor deze versie zijn de mogelijkheid om nieuwe LDAP-groepen dynamisch toe te wijzen voor gebruikerslidmaatschap in de Admin Console, en het maken van dynamische gebruikersgroepen.

Meer informatie over de nieuwe groepsfuncties vindt u hier:

[https://github.com/adobe-apiplatform/user-sync.py/blob/v2/docs/en/user-manual/advanced_configuration](https://github.com/adobe-apiplatform/user-sync.py/blob/v2/docs/en/user-manual/advanced_configuration.md#additional-group-options)

>[!NOTE]
>
>Raadpleeg de [documentatiepagina](https://adobe-apiplatform.github.io/user-sync.py/en/) voor meer informatie over het gereedschap Gebruikerssynchronisatie.
>
>
>Het hulpmiddel van de Synchronisatie van de Gebruiker moet als Adobe I/O cliënt UMAPI registreren gebruikend de beschreven procedure [hier](https://adobe-apiplatform.github.io/umapi-documentation/en/UM_Authentication.html).
>
>De documentatie van de Adobe I/O-console vindt u [hier](https://www.adobe.io/apis/cloudplatform/console.html).
>
>
>De gebruikersbeheer-API die wordt gebruikt door het gereedschap Gebruikerssynchronisatie, wordt behandeld op deze [locatie](https://www.adobe.io/apis/cloudplatform/umapi-new.html).

>[!NOTE]
>
>De AEM IMS-configuratie wordt afgehandeld door het Adobe Managed Services-team. De klantbeheerder kan het echter naar wens wijzigen (bijvoorbeeld Automatische groepslidmaatschap of Groepstoewijzing). De IMS-client wordt ook geregistreerd door uw Managed Services-team.

## Het gebruik {#how-to-use}

### Producten en gebruikerstoegang beheren in Admin Console {#managing-products-and-user-access-in-admin-console}

Wanneer de beheerder van het Product van de klant zich bij Admin Console aanmeldt, zullen zij veelvoudige instanties van de Context van het Product van AEM Managed Services zien zoals hieronder getoond:

![screen_shot_2018-09-17at105804pm](assets/screen_shot_2018-09-17at105804pm.png)

In dit voorbeeld heeft de org *AEM-MS-Onboard* 32 instanties die verschillende topologieën en omgevingen omspannen, zoals het werkgebied, Prod, enz.

![screen_shot_2018-09-17at105517pm](assets/screen_shot_2018-09-17at105517pm.png)

De instantiedetails kunnen worden gecontroleerd om de instantie te identificeren:

![screen_shot_2018-09-17at105601pm](assets/screen_shot_2018-09-17at105601pm.png)

Onder elke instantie van de Context van het Product, zal er een bijbehorend Profiel van het Product zijn. Dit productprofiel wordt gebruikt om toegang toe te wijzen aan gebruikers en groepen.

![image2018-9-18_7-48-50](assets/image2018-9-18_7-48-50.png)

Gebruikers en groepen die zijn toegevoegd onder dit productprofiel, kunnen zich aanmelden bij die instantie, zoals in het onderstaande voorbeeld wordt getoond:

![screen_shot_2018-09-17at105623pm](assets/screen_shot_2018-09-17at105623pm.png)

### Aanmelden bij AEM {#logging-into-aem}

#### Aanmelden bij lokale beheerder {#local-admin-login}

AEM kunnen lokale aanmeldingen voor Admin-gebruikers blijven ondersteunen, aangezien het aanmeldingsscherm een optie heeft om zich lokaal aan te melden:

![screen_shot_2018-09-18at121056am](assets/screen_shot_2018-09-18at121056am.png)

#### Op IMS gebaseerde aanmelding {#ims-based-login}

Voor andere gebruikers kan de op IMS gebaseerde aanmelding worden gebruikt zodra IMS in de instantie is geconfigureerd. De gebruiker zal eerst op **Teken binnen met Adobe** knoop zoals hieronder getoond klikken:

![image2018-9-18_0-10-32](assets/image2018-9-18_0-10-32.png)

Vervolgens worden ze omgeleid naar het IMS-aanmeldingsscherm en voeren ze hun referenties in:

![screen_shot_2018-09-17at115629pm](assets/screen_shot_2018-09-17at115629pm.png)

Als een federatieve IDP tijdens de eerste installatie van de Admin Console wordt geconfigureerd, wordt de gebruiker omgeleid naar de klant-IDP voor SSO.

IDP is Okta in het onderstaande voorbeeld:

![screen_shot_2018-09-17at115734pm](assets/screen_shot_2018-09-17at115734pm.png)

Nadat de verificatie is voltooid, wordt de gebruiker teruggeleid naar AEM en aangemeld:

![screen_shot_2018-09-18at120124am](assets/screen_shot_2018-09-18at120124am.png)

### Bestaande gebruikers migreren {#migrating-existing-users}

Voor bestaande AEM instanties die een andere verificatiemethode gebruiken en die nu naar IMS worden gemigreerd, moet er een migratiestap plaatsvinden.

Bestaande gebruikers in de AEM opslagplaats (lokaal, via LDAP of SAML) kunnen worden gemigreerd naar IMS als IDP met behulp van het User Migration Utility.

Dit hulpprogramma wordt door uw AMS-team uitgevoerd als onderdeel van de IMS-provisioning.

### Beherend Toestemmingen en ACLs in AEM {#managing-permissions-and-acls-in-aem}

Toegangsbeheer en toegangsrechten blijven in AEM worden beheerd, dit kan worden bereikt met scheiding van gebruikersgroepen die uit IMS komen (bijvoorbeeld AEM-GRP-008 in het onderstaande voorbeeld) en lokale groepen waarin de machtigingen en toegangsbeheer zijn gedefinieerd. De gebruikersgroepen die van IMS worden gesynchroniseerd kunnen aan lokale groepen worden toegewezen en de toestemmingen erven.

In het onderstaande voorbeeld voegen we gesynchroniseerde groepen toe aan de lokale *Dam_Users*-groep.

Hier is een gebruiker ook toegewezen aan een paar groepen in de Admin Console. (Houd er rekening mee dat gebruikers en groepen kunnen worden gesynchroniseerd via LDAP met behulp van het gebruikerssynchronisatiegereedschap of lokaal kunnen worden gemaakt. Zie het gedeelte **Onboardinggebruikers naar de Admin Console** hierboven).

>[!NOTE]
>
>Gebruikersgroepen worden alleen gesynchroniseerd wanneer de gebruikers zich bij de instantie aanmelden.

![screen_shot_2018-09-17at94207pm](assets/screen_shot_2018-09-17at94207pm.png)

De gebruiker maakt deel uit van de volgende groepen in IMS:

![screen_shot_2018-09-17at94237pm](assets/screen_shot_2018-09-17at94237pm.png)

Wanneer de gebruiker zich aanmeldt, worden diens groepslidmaatschappen gesynchroniseerd zoals hieronder weergegeven:

![screen_shot_2018-09-17at94033pm](assets/screen_shot_2018-09-17at94033pm.png)

AEM kunnen de gebruikersgroepen die via IMS zijn gesynchroniseerd, als leden worden toegevoegd aan bestaande lokale groepen, bijvoorbeeld DAM-gebruikers.

![screen_shot_2018-09-17at95804pm](assets/screen_shot_2018-09-17at95804pm.png)

Zoals hieronder getoond, erft de groep *AEM-GRP_008* de Toestemmingen en Bevoegdheden van Gebruikers DAM. Dit is een effectieve manier om machtigingen voor gesynchroniseerde groepen te beheren. Deze wordt ook veel gebruikt in LDAP-verificatiemethoden.

![screen_shot_2018-09-17at110505pm](assets/screen_shot_2018-09-17at110505pm.png)

