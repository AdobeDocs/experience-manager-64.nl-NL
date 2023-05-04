---
title: Essentiële elementen van agenda
seo-title: Calendar Essentials
description: Overzicht van de functie Kalender
seo-description: Calendar feature overview
uuid: 14ff7a83-b2a7-4f7e-8ee7-88f336329a1a
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 88932a3c-ba7f-47ba-9e0b-206755c2d42e
exl-id: cdf5e5d3-a78c-4f32-ad40-665876392a97
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 0%

---

# Essentiële elementen van agenda {#calendar-essentials}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Deze pagina bevat essentiële informatie over het werken met de kalenderfunctie.

## Essentiële elementen voor client-kant {#essentials-for-client-side}

<table> 
 <tbody>
  <tr>
   <td> <strong>resourceType</strong></td> 
   <td>sociaal/kalender/onderdelen/hbs/kalender</td> 
  </tr>
  <tr>
   <td> <a href="scf.md#add-or-include-a-communities-component"><strong>inclusief</strong></a></td> 
   <td>Nee</td> 
  </tr>
  <tr>
   <td> <a href="client-customize.md#clientlibs-for-scf"><strong>clientllibs</strong></a></td> 
   <td>cq.social.hbs.calendar</td> 
  </tr>
  <tr>
   <td> <strong>sjablonen</strong></td> 
   <td>/libs/social/calendar/components/hbs/calendar/calendar.hbs</td> 
   <td> </td> 
  </tr>
  <tr>
   <td> <strong>css</strong></td> 
   <td>/libs/social/calendar/components/hbs/calendar/clientlibs/css/calendar.css<br /> /libs/social/calendar/components/hbs/calendar/clientlibs/css/jqueryui.css</td> 
  </tr>
  <tr>
   <td><strong> eigenschappen</strong></td> 
   <td>zie <a href="calendar.md">Kalenders gebruiken</a></td> 
  </tr>
 </tbody>
</table>

* [Aanpassingen aan de clientzijde](client-customize.md)

## Essentiële elementen voor server-side {#essentials-for-server-side}

* [Agenda-API&#39;s](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/calendar/client/api/package-summary.html)

* [Kalender-eindpunten](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/calendar/client/endpoints/package-summary.html)

* [Aanpassingen op de server](server-customize.md)

### Kalenderfunctie {#calendar-function}

Een community-sitestructuur die de [Kalenderfunctie](functions.md#calendar-function) zal gevormd c hebben `alendar`component. De functie Kalender ondersteunt het identificeren van een [geprivilegieerde gebruikersgroep](users.md#privileged-members-group).

### Toegang tot agendaberichten (UGC) {#accessing-calendar-posts-ugc}

Met ingang van AEM 6.1. [gemeenschappelijk archief](working-with-srp.md) voor UGC omvat programmatische toegang tot UGC ongeacht de gekozen opslagoptie (zoals ASRP, MSRP of JSRP).

**De locatie en de indeling van de UGC in de opslagplaats kunnen zonder waarschuwing worden gewijzigd**.

Zie:

* [Overzicht opslagbronprovider](srp.md) - overzicht van het gebruik van introducties en opslagplaatsen
* [SRP en UGC Essentials](srp-and-ugc.md) - SRP-hulpprogrammamethoden en -voorbeelden
* [Toegang tot UGC met SRP](accessing-ugc-with-srp.md) - coderingsrichtlijnen
* [SocialUtils Refactoring](socialutils.md) - het in kaart brengen van afgekeurde nutsmethodes aan huidige SRP nutsmethodes
