---
title: Het CSRF-beschermingskader
seo-title: The CSRF Protection Framework
description: Het framework maakt gebruik van tokens om te garanderen dat het verzoek van de klant legitiem is
seo-description: The framework makes use of tokens to guarantee that the client request is legitimate
uuid: 7cb222ba-fc7a-46ee-8b49-a5f39a53580b
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: introduction
content-type: reference
discoiquuid: f453427d-c813-48b7-b2f9-adadea39c67d
exl-id: 533c348e-517f-4d70-a89c-bfc87f71a633
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 0%

---

# Het CSRF-beschermingskader{#the-csrf-protection-framework}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Naast het filter Apache Sling Referrer biedt Adobe ook een nieuw CSRF-beschermingskader dat bescherming biedt tegen dit type aanvallen.

Het framework maakt gebruik van tokens om te garanderen dat het verzoek van de klant legitiem is. De tokens worden gegenereerd wanneer het formulier naar de client wordt verzonden en gevalideerd wanneer het formulier naar de server wordt teruggestuurd.

>[!NOTE]
>
>De publicatie-instanties bevatten geen tokens voor anonieme gebruikers.

## Vereisten {#requirements}

### Afhankelijkheden {#dependencies}

Elke component die afhankelijk is van de component `granite.jquery` de afhankelijkheid zal automatisch profiteren van het CSRF-beschermingskader. Als dit niet het geval voor om het even welk van uw componenten is, moet u een gebiedsdeel verklaren aan `granite.csrf.standalone` voordat u het framework kunt gebruiken.

### De crypto-sleutel repliceren {#replicating-crypto-keys}

Als u de tokens wilt gebruiken, moet u de `/etc/keys/hmac` binair aan alle instanties in uw plaatsing. Een handige manier om de HMAC-sleutel naar alle instanties te kopiëren, is door een pakket met de sleutel te maken en deze via Package Manager op alle instanties te installeren.

>[!NOTE]
>
>Zorg ervoor dat u ook de vereiste [Wijzigingen in de configuratie van Dispatcher](https://helpx.adobe.com/experience-manager/dispatcher/user-guide.html) om gebruik te maken van het CSRF-beschermingskader.

>[!NOTE]
>
>Als u het manifestgeheime voorgeheugen met uw Webtoepassing gebruikt, zorg ervoor u &quot;**&amp;asteren;**&quot; aan manifest om ervoor te zorgen neemt het teken niet de CSRF symbolische generatievraag offline. Raadpleeg deze voor meer informatie [link](https://www.w3.org/TR/offline-webapps/).
>
>Voor meer informatie over aanvallen CSRF en manieren om hen te verlichten, zie [OWASP-pagina voor XSS-aanvragen voor andere sites](https://owasp.org/www-community/attacks/csrf).
