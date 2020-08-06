---
title: Opwaarderen naar AEM 6.4 Gemeenschappen
seo-title: Opwaarderen naar AEM 6.4 Gemeenschappen
description: Hoe te om van een vroegere versie aan AEM 6.4 Gemeenschappen te bevorderen
seo-description: Hoe te om van een vroegere versie aan AEM 6.4 Gemeenschappen te bevorderen
uuid: c6c2846e-38d4-4e99-9038-bfb486afd8b9
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
content-type: reference
topic-tags: deploying
discoiquuid: 7aa28e36-6b31-4447-b800-cab2dc78c93c
translation-type: tm+mt
source-git-commit: 3d2b91565e14e85e9e701663c8d0ded03e5b430c
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 0%

---


# Opwaarderen naar AEM 6.4 Gemeenschappen {#upgrading-to-aem-communities}

Afhankelijk van de topologie en de eigenschappen van elke plaats, kunnen de volgende acties noodzakelijk zijn wanneer bevordering aan AEM Communities 6.4 of het installeren van het recentste eigenschappak.

Deze afdeling is specifiek voor de Gemeenschappen en vormt een aanvulling op de informatie in [Bijwerken naar AEM 6.4](../../help/sites-deploying/upgrade.md) (platform).

## Upgrade uitvoeren vanaf AEM 6.1 of hoger {#upgrading-from-aem-or-later}

### Opnieuw indexeren Solr {#reindex-solr}

Wanneer het installeren van een nieuw de eigenschappak van Gemeenschappen op een plaatsing die met MSRP wordt gevormd, zal het noodzakelijk zijn:

1. Installeer het [nieuwste functiepakket](deploy-communities.md#latestfeaturepack)
2. Installeer de [nieuwste configuratiebestanden](msrp.md#upgrading)
3. MSRP opnieuw indexeren

   zie sectie [MSRP Reindex Tool](msrp.md#msrp-reindex-tool)

### Enablement 2.0 {#enablement}

Vanaf AEM 6.3 slaan de enablement eigenschappen niet meer rapporteringsinformatie in MySQL op. De MySQL-afhankelijkheid is alleen beschikbaar voor het bijhouden van SCORM-inhoud.

Neem contact op met de [klantenservice](https://helpx.adobe.com/marketing-cloud/contact-support.html) voor hulp bij het migreren van inhoud uit Enablement 1.0.

## Upgrade uitvoeren vanaf AEM 6.0 {#upgrading-from-aem}

Als bestaande UGC moet worden behouden, hangt de manier om dit te doen af van of de plaatsing [op-gebouw](#on-premise-storage) UGC of in de [Adobe wolk](#adobe-cloud-storage)opslaat.

### Adobe Cloud Storage {#adobe-cloud-storage}

Als de geüpgrade site is geconfigureerd voor het gebruik van de Adobe-cloudopslag, wordt deze mogelijk (onjuist) weergegeven alsof alle UGC is verloren omdat de SRP-methoden de reeds bestaande UGC op de oude locatie niet kunnen vinden.

Aldus, is er de capaciteit om ASRP op te dragen om `AEM 6.0 compatability-mode` tot UGC toegang te hebben.

Voor alle AEM 6.3 auteur- en publicatieinstanties

1. Aanmelden met beheerdersrechten
2. Configureer [ASRP](asrp.md)
3. Ga als volgt te werk om bestaande UGC zichtbaar te maken:
i. Naar de webconsole bladeren, bijvoorbeeld
   [https://&lt;host>:&lt;port>/system/console/configMgr](http://localhost:4502/system/console/configMgr)ii. Zoek **[!UICONTROL AEM Communities Utilities]** configuratieiii. Selecteren om configuratievenster uit te vouwen
   * *Uitschakelen* **`Cloud Storage`**
   * Selecteer **[!UICONTROL Save]**

![chlimage_1-126](assets/chlimage_1-126.png)

### Opslag op locatie {#on-premise-storage}

Als de geüpgrade site geen cloudopslag heeft gebruikt, moet eventuele bestaande UGC worden omgezet om te voldoen aan de nieuwe structuur die in AEM 6.1 Communities is geïntroduceerd ter ondersteuning van de gemeenschappelijke opslag.

Voor dit doel, is een open bronmigratiehulpmiddel beschikbaar op GitHub:\
[AEM Communities UGC-migratiehulpprogramma](https://github.com/Adobe-Marketing-Cloud/communities-ugc-migration)

### Java API&#39;s {#java-apis}

Houd er rekening mee dat veel API&#39;s in verschillende pakketten zijn ondergebracht bij de opwaardering van AEM 6.0 sociale gemeenschappen naar AEM 6.3 Gemeenschappen. De meeste moeten gemakkelijk worden opgelost wanneer het gebruiken van winde voor aanpassing van de eigenschappen van Gemeenschappen.

Voor details op het verouderde pakket SocialUtils, bezoek Refactoring [SocialUtils](socialutils.md).

Zie ook [Maven gebruiken voor Gemeenschappen](maven.md).

### Geen JSP-componentsjablonen {#no-jsp-component-templates}

Het [sociale componentenkader](scf.md) (SCF) gebruikt de [Sjabloontaal HandlebarsJS](https://www.handlebarsjs.com/) (HBS) in plaats van Java Server Pages (JSP) die vóór AEM 6.0 wordt gebruikt.

In AEM 6.0 bleven de JSP componenten naast de nieuwe HBS kadercomponenten op dezelfde plaats, met de componenten HBS typisch gevestigd in subfolders genoemd &quot;hbs&quot;.

Vanaf AEM 6.1 werden de JSP-componenten volledig verwijderd. Voor Gemeenschappen, wordt het geadviseerd om al gebruik van componenten JSP met componenten SCF te vervangen.

## AEM Communities UGC-migratiehulpprogramma {#aem-communities-ugc-migration-tool}

Het migratiehulpmiddel [van](https://github.com/Adobe-Marketing-Cloud/communities-ugc-migration) AEM Communities UGC is een open bronmigratiehulpmiddel, beschikbaar op GitHub, dat kan worden aangepast om UGC van vroegere versies van AEM sociale gemeenschappen uit te voeren en in AEM Communities 6.1 of later in te voeren.

Naast het bewegen van UGC van vroegere versies, is het ook mogelijk om het hulpmiddel te gebruiken om UGC van één [SRP](working-with-srp.md) naar een andere, zoals van MSRP aan DSRP te bewegen.

## Upgrade uitvoeren vanaf AEM 5.6.1 of lager {#upgrading-from-aem-or-earlier}

Conceptueel zijn er drie generaties gemeenschappen componenten:

**Gen 1**: grofweg CQ 5.4 door AEM 5.6.0 - dit zijn de componenten **collab** die UGC in de lokale bewaarplaats gebruikend replicatie als middel om UGC over platforms te synchroniseren opslaagde. Andere verschillen betreffen de implementatie met behulp van JSP (Java Server Pages) en de blogfunctie die bestaat uit alleen ontwerpen in de auteursomgeving.

**Gen 2**: van AEM 5.6.1 tot en met AEM 6.1 is dit een combinatie van **collab** en **sociale** componenten . AEM 6.0 introduceerde het nieuwe [sociale componentenkader](scf.md) (SCF) en AEM 6.2 introduceerde een [gemeenschappelijke opslag](working-with-srp.md) UGC waar UGC wordt betreden gebruikend een leverancier [van](srp.md) opslagmiddelen (SRP).

**Gen 3**: vanaf AEM 6.2 zijn er alleen **sociale** componenten, geïmplementeerd in SCF als HBS-componenten (Handlebars) waarvoor een keuze van SRP voor UGC vereist is.
