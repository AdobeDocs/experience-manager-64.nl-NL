---
title: Beveiliging
seo-title: Beveiliging
description: De Veiligheid van de toepassing begint tijdens de ontwikkelingsfase
seo-description: De Veiligheid van de toepassing begint tijdens de ontwikkelingsfase
uuid: efd5f3bc-da07-4fc8-a6ce-f1e6f5084c9e
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: introduction
content-type: reference
discoiquuid: d2267663-6c1d-413c-9862-e82e21ae6906
translation-type: tm+mt
source-git-commit: 0fb4d181b700e223becfee8e3e68a84d6f964c1d
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 0%

---


# Beveiliging{#security}

De Veiligheid van de toepassing begint tijdens de ontwikkelingsfase. Adobe raadt aan de volgende best practices op het gebied van beveiliging toe te passen.

## Aanvraagsessie gebruiken {#use-request-session}

Volgens het beginsel van bevoegdheden op het gebied van gegevensopslag, raadt Adobe aan dat elke toegang tot de gegevensopslagruimte wordt uitgevoerd door gebruik te maken van de sessie die is gebonden aan het verzoek van de gebruiker en het juiste toegangsbeheer.

## Protect tegen XSS (Cross-Site Scripting) {#protect-against-cross-site-scripting-xss}

Met XSS (Cross-site scripting) kunnen aanvallers code injecteren in webpagina&#39;s die door andere gebruikers worden weergegeven. Deze kwetsbaarheid op het gebied van beveiliging kan door kwaadaardige webgebruikers worden misbruikt om toegangsbesturingselementen te omzeilen.

AEM past het beginsel toe van het filtreren van alle gebruiker-geleverde inhoud op output. Het voorkomen van XSS krijgt de hoogste prioriteit tijdens zowel ontwikkeling als testen.

Het XSS-beveiligingsmechanisme dat door AEM wordt geboden, is gebaseerd op de [AntiSamy Java-bibliotheek](https://www.owasp.org/index.php/Category:OWASP_AntiSamy_Project) van [OWASP (het Open Web Application Security Project)](https://www.owasp.org/). De standaardconfiguratie van AntiSamy vindt u op

`/libs/cq/xssprotection/config.xml`

Het is belangrijk dat u deze configuratie aan uw eigen veiligheidsbehoeften aanpast door het configuratiedossier te bedekken. De officiële [documentatie](https://www.owasp.org/index.php/Category:OWASP_AntiSamy_Project) AntiSamy zal u van alle informatie voorzien u nodig hebt om uw veiligheidsvereisten uit te voeren.

>[!NOTE]
>
>We raden u ten zeerste aan om altijd toegang te krijgen tot de XSS-beveiligings-API met behulp van de [XSSAPI die door AEM](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/granite/xss/XSSAPI.html)wordt geleverd.

Bovendien, kan een firewall van de Webtoepassing, zoals [mod_security voor Apache](https://www.modsecurity.org), betrouwbare, centrale controle over de veiligheid van het plaatsingsmilieu verstrekken en tegen eerder niet ontdekte dwars-plaats scripting aanvallen beschermen.

## Toegang tot informatie over Cloud Servicen {#access-to-cloud-service-information}

>[!NOTE]
>
>ACLs voor de Informatie van de Cloud Service evenals de montages OSGi die worden vereist om uw instantie te beveiligen worden geautomatiseerd als deel van de Klaar Wijze [van de](/help/sites-administering/production-ready.md)Productie. Terwijl dit betekent dat u niet de configuratieveranderingen manueel hoeft aan te brengen, wordt het nog geadviseerd dat u hen herzien alvorens u met uw plaatsing gaat leven.

Wanneer u uw AEM met de Adobe Marketing Cloud [](/help/sites-administering/marketing-cloud.md) integreert, gebruikt u [Cloud Service configuraties](/help/sites-developing/extending-cloud-config.md). Informatie over deze configuraties, samen met alle verzamelde statistieken, wordt opgeslagen in de gegevensopslagruimte. Wij adviseren dat, als u deze functionaliteit gebruikt, u controleert of de standaardveiligheid op deze informatie uw vereisten aanpast.

De module webservicesSupport schrijft statistieken en configuratiegegevens onder:

`/etc/cloudservices`

Met de standaardmachtigingen:

* Auteursomgeving: `read` for `contributors`

* Publicatie-omgeving: `read` for `everyone`

## Protect tegen aanvallen van smeedmachines voor aanvragen voor meerdere sites {#protect-against-cross-site-request-forgery-attacks}

Voor meer informatie over de veiligheidsmechanismen AEM aanwendingen om aanvallen te verlichten CSRF, zie de sectie van de Filter [van de Verwijzer van de](/help/sites-administering/security-checklist.md#protect-against-cross-site-request-forgery) Verkoper van de Verkoper van de Veiligheid Checklist en de documentatie [van het Kader van de Bescherming](/help/sites-developing/csrf-protection.md)CSRF.