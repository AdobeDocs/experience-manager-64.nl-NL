---
title: Opwaarderen naar AEM 6.4 Gemeenschappen
seo-title: Upgrading to AEM 6.4 Communities
description: Hoe te om van een vroegere versie aan AEM 6.4 Gemeenschappen te bevorderen
seo-description: How to upgrade from an earlier version to AEM 6.4 Communities
uuid: c6c2846e-38d4-4e99-9038-bfb486afd8b9
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
content-type: reference
topic-tags: deploying
discoiquuid: 7aa28e36-6b31-4447-b800-cab2dc78c93c
exl-id: ef622ac3-d96d-48bf-bfb2-61516d9deb5c
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 0%

---

# Opwaarderen naar AEM 6.4 Gemeenschappen {#upgrading-to-aem-communities}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Afhankelijk van de topologie en de eigenschappen van elke plaats, kunnen de volgende acties noodzakelijk zijn wanneer bevordering aan AEM Communities 6.4 of het installeren van het recentste eigenschappak.

Deze afdeling is specifiek voor de Gemeenschappen en vormt een aanvulling op de in [Upgrade naar AEM 6.4](../../help/sites-deploying/upgrade.md) (platform).

## Upgrade uitvoeren vanaf AEM 6.1 of hoger {#upgrading-from-aem-or-later}

### Opnieuw indexeren Solr {#reindex-solr}

Wanneer het installeren van een nieuw de eigenschappak van Gemeenschappen op een plaatsing die met MSRP wordt gevormd, zal het noodzakelijk zijn:

1. Installeer de [nieuwste functiepakket](deploy-communities.md#latestfeaturepack)
2. Installeer de [nieuwste configuratiebestanden van Solr](msrp.md#upgrading)
3. MSRP opnieuw indexeren

   zie sectie [MSRP opnieuw indexeren](msrp.md#msrp-reindex-tool)

### Enablement 2.0 {#enablement}

Vanaf AEM 6.3 slaan de enablement eigenschappen niet meer rapporteringsinformatie in MySQL op. De MySQL-afhankelijkheid is alleen beschikbaar voor het bijhouden van SCORM-inhoud.

Neem contact op met [klantenservice](https://helpx.adobe.com/marketing-cloud/contact-support.html) voor hulp bij het migreren van inhoud uit Enablement 1.0.

## Upgrade uitvoeren vanaf AEM 6.0 {#upgrading-from-aem}

Als reeds bestaande UGC moet worden behouden, dan hangt de middelen om dit te doen af van of de plaatsing opgeslagen UGC [op locatie](#on-premise-storage) of in de [Adobe-cloud](#adobe-cloud-storage).

### Adobe Cloud Storage {#adobe-cloud-storage}

Als de geüpgrade site is geconfigureerd voor het gebruik van de Adobe-cloudopslag, wordt deze mogelijk (onjuist) weergegeven alsof alle UGC is verloren omdat de SRP-methoden de reeds bestaande UGC op de oude locatie niet kunnen vinden.

Aldus is er de capaciteit om ASRP te instrueren om te gebruiken `AEM 6.0 compatability-mode` toegang tot UGC.

Voor alle AEM 6.3 auteur- en publicatieinstanties:

1. Aanmelden met beheerdersrechten en configureren [ASRP](asrp.md).
1. Ga als volgt te werk om de bestaande UGC zichtbaar te maken:

   i. Blader naar de webconsole. De standaard-URL is
   `https://localhost:4502/system/console/configMgr`.

   ii. Zoeken **[!UICONTROL AEM Communities Utilities]** en selecteert u deze om het configuratievenster uit te vouwen.

   iii. Uitschakelen **[!UICONTROL Cloud Storage]** en klik op **[!UICONTROL Save]**.

![chlimage_1-126](assets/chlimage_1-126.png)

### Opslag op locatie {#on-premise-storage}

Als de geüpgrade site geen cloudopslag heeft gebruikt, moet eventuele bestaande UGC worden omgezet om te voldoen aan de nieuwe structuur die in AEM 6.1 Communities is geïntroduceerd ter ondersteuning van de gemeenschappelijke opslag.

Voor dit doel, is een open bronmigratiehulpmiddel beschikbaar op GitHub:\
[AEM Communities UGC-migratiehulpprogramma](https://github.com/Adobe-Marketing-Cloud/communities-ugc-migration)

### Java API&#39;s {#java-apis}

Houd er rekening mee dat veel API&#39;s in verschillende pakketten zijn ondergebracht bij de opwaardering van AEM 6.0 sociale gemeenschappen naar AEM 6.3 Gemeenschappen. De meeste moeten gemakkelijk worden opgelost wanneer het gebruiken van winde voor aanpassing van de eigenschappen van Gemeenschappen.

Ga voor meer informatie over het verouderde pakket met sociale hulpmiddelen naar [SocialUtils Refactoring](socialutils.md).

Zie ook [Maven gebruiken voor Gemeenschappen](maven.md).

### Geen JSP-componentsjablonen {#no-jsp-component-templates}

De [sociale component](scf.md) (SCF) gebruikt [HandlebarsJS](https://handlebarsjs.com/) (HBS) sjabloontaal in plaats van JSP (Java Server Pages) die vóór AEM 6.0 wordt gebruikt.

In AEM 6.0 bleven de JSP componenten naast de nieuwe HBS kadercomponenten op dezelfde plaats, met de componenten HBS typisch gevestigd in subfolders genoemd &quot;hbs&quot;.

Vanaf AEM 6.1 werden de JSP-componenten volledig verwijderd. Voor Gemeenschappen, wordt het geadviseerd om al gebruik van componenten JSP met componenten SCF te vervangen.

## AEM Communities UGC-migratiehulpprogramma {#aem-communities-ugc-migration-tool}

De [AEM Communities UGC-migratiehulpprogramma](https://github.com/Adobe-Marketing-Cloud/communities-ugc-migration) is een opensource migratiehulpmiddel, beschikbaar op GitHub, dat kan worden aangepast om UGC van vroegere versies van AEM sociale gemeenschappen uit te voeren en in AEM Communities 6.1 of later in te voeren.

Naast het bewegen van UGC van vroegere versies, is het ook mogelijk om het hulpmiddel te gebruiken om UGC van één te bewegen [SRP](working-with-srp.md) aan een andere, zoals van MSRP aan DSRP.

## Upgrade uitvoeren vanaf AEM 5.6.1 of lager {#upgrading-from-aem-or-earlier}

Conceptueel zijn er drie generaties gemeenschappen componenten:

**Gen 1**: ruwweg CQ 5.4 tot AEM 5.6.0 - dit zijn de **collab** componenten die UGC in de lokale opslagplaats hebben opgeslagen gebruikend replicatie als middel om UGC over platforms te synchroniseren. Andere verschillen betreffen de implementatie met behulp van JSP (Java Server Pages) en de blogfunctie die bestaat uit alleen ontwerpen in de auteursomgeving.

**Gen 2**: van AEM 5.6.1 tot en met AEM 6.1 - dit is een combinatie van **collab** en **sociaal** componenten. AEM 6.0 introduceert het nieuwe [sociale component](scf.md) (SCF) en AEM 6.2 [algemene UGC-opslag](working-with-srp.md) waar UGC wordt benaderd via een [opslagbronprovider](srp.md) (SRP).

**Gen 3**: vanaf AEM 6.2 zijn er alleen **sociaal** componenten, die in SCF als componenten van Handlebars (HBS) worden uitgevoerd die een keus van SRP voor UGC vereisen.
