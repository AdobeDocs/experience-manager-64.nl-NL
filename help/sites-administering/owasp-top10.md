---
title: OWASP Top 10
seo-title: OWASP Top 10
description: Leer hoe AEM omgaat met de 10 belangrijkste beveiligingsrisico's van OWASP.
seo-description: Leer hoe AEM omgaat met de 10 belangrijkste beveiligingsrisico's van OWASP.
uuid: a5a7e130-e15b-47ae-ba21-448f9ac76074
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: Security
content-type: reference
discoiquuid: e5323ae8-bc37-4bc6-bca6-9763e18c8e76
translation-type: tm+mt
source-git-commit: 280c2b3cc8026988472d4ad0cf6649fa8a7c9c38
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 0%

---


# OWASP Top 10{#owasp-top}

Het [Open Project](https://www.owasp.org) van de Veiligheid van de Toepassing van het Web (OWASP) handhaaft een lijst van wat zij als de [Hoogste 10 Veiligheidsrisico](https://www.owasp.org/index.php/OWASP_Top_Ten_Project)van de Toepassing van het Web beschouwen.

Deze worden hieronder vermeld, samen met een uitleg van de manier waarop CRX ermee omgaat.

## 1. Injectie {#injection}

* SQL - Voorkomen door ontwerp: De standaardopslagopstelling omvat noch vereist een traditionele gegevensbestand, al gegevens wordt opgeslagen in de inhoudsbewaarplaats. Alle toegang is beperkt tot geverifieerde gebruikers en kan alleen worden uitgevoerd via de JCR API. SQL wordt alleen ondersteund voor zoekopdrachten (SELECT). Bovendien biedt SQL ondersteuning voor waardebinding.
* LDAP - LDAP-injectie is niet mogelijk, omdat de verificatiemodule de invoer filtert en de gebruiker importeert met de methode bind.
* OS - Er wordt geen shell-uitvoering uitgevoerd vanuit de toepassing.

## 2. XSS (Cross-Site Scripting) {#cross-site-scripting-xss}

De algemene matigingspraktijk moet alle output van gebruiker-geproduceerde inhoud coderen gebruikend een server-kantXSS beschermingsbibliotheek die op [Codeur](https://www.owasp.org/index.php/OWASP_Java_Encoder_Project) OWASP en [AntiSamy](https://www.owasp.org/index.php/Category:OWASP_AntiSamy_Project)wordt gebaseerd.

XSS is een hoogste prioriteit tijdens zowel het testen als de ontwikkeling, en om het even welke gevonden kwesties worden (typisch) onmiddellijk opgelost.

## 3. Verbroken verificatie- en sessiebeheer {#broken-authentication-and-session-management}

AEM gebruikt geluidstechnieken en beproefde verificatietechnieken, waarbij wordt uitgegaan van [Apache Jackrabbit](https://jackrabbit.apache.org/) en [Apache Sling](https://sling.apache.org/). Browser/HTTP-sessies worden niet gebruikt in AEM.

## 4. Verwijzingen naar onveilige directe objecten {#insecure-direct-object-references}

Alle toegang tot gegevensvoorwerpen wordt bemiddelen door de bewaarplaats en daarom beperkt door op rol gebaseerd toegangsbeheer.

## 5. Cross-Site Request-vervalsing (CSRF) {#cross-site-request-forgery-csrf}

Smeedraaien voor aanvragen tussen sites (CSRF) wordt beperkt door automatisch een cryptografisch token in alle formulieren en AJAX te injecteren en dit token op de server voor elke POST te controleren.

Bovendien AEM schepen met een verwijzing-kopbal gebaseerde filter, die kan worden gevormd om POST verzoeken van specifieke gastheren (die in een lijst worden bepaald *slechts* toe te staan).

## 6. Beveiligingsfout {#security-misconfiguration}

Het is onmogelijk te garanderen dat alle software altijd correct is geconfigureerd. Wij streven er echter naar zoveel mogelijk begeleiding te bieden en de configuratie zo eenvoudig mogelijk te maken. Bovendien AEM schepen met [geïntegreerde Controle](/help/sites-administering/operations-dashboard.md) van de Gezondheid van de Veiligheid die u helpen veiligheidsconfiguratie in een blik controleren.

Controleer de [lijst](/help/sites-administering/security-checklist.md) Beveiligingscontrole voor meer informatie, die u stapsgewijze verhardingsinstructies biedt.

## 7. Onveilige cryptografische opslag {#insecure-cryptographic-storage}

Wachtwoorden worden opgeslagen als cryptografische hashes in het gebruikersknooppunt; deze knooppunten kunnen standaard alleen door de beheerder en de gebruiker zelf worden gelezen.

Gevoelige gegevens zoals referenties van derden worden in gecodeerde vorm opgeslagen met behulp van een voor FIPS 140-2 gecertificeerde cryptografische bibliotheek.

## 8. Kan URL-toegang niet beperken {#failure-to-restrict-url-access}

De opslagplaats staat het plaatsen van [fijnkorrelige voorrechten (zoals gespecificeerd door JCR)](https://docs.adobe.com/content/docs/en/spec/jcr/2.0/16_Access_Control_Management.html) voor om het even welke bepaalde gebruiker of groep op om het even welk bepaald weg toe, door toegangsbeheeringangen. Toegangsbeperkingen worden afgedwongen door de repository.

## 9. Onvoldoende beveiliging van transportlaag {#insufficient-transport-layer-protection}

Gemengde door serverconfiguratie (bijvoorbeeld alleen HTTPS gebruiken).

## 10 Niet-gevalideerde omleidingen en doorsturen {#unvalidated-redirects-and-forwards}

Gematigd door alle omleidingen aan gebruiker-geleverde bestemmingen aan interne plaatsen te beperken.

