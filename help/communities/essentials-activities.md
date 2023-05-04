---
title: Essentiële elementen activiteitsstroom
seo-title: Activity Stream Essentials
description: Lijst van recente activiteiten die door een lid of een lijst van recente activiteiten op één enkele draad van inhoud worden uitgevoerd
seo-description: List of recent activites performed by a member or a list of recent activities on a single thread of content
uuid: 6e4734bb-52a8-4670-b665-e640108b036e
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 8cc04993-4021-4cb7-b973-5afc4da1ed11
exl-id: 74dcbefa-e670-419b-af9b-b3d3c593ebaa
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 0%

---

# Essentiële elementen activiteitsstroom {#activity-stream-essentials}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

De activiteiten van een ondertekend lid van de gemeenschap, zoals het posten aan een forum of blog, worden verzameld in een stroom die op verschillende manieren door configuratie van de component van activiteitenstromen kan worden gefiltreerd en getoond.

De mogelijkheid om te volgen voegt nog een reeks activiteiten toe wanneer leden van de gemeenschap belangenverklaringen of andere leden van de gemeenschap volgen.

Alles [communitysites](overview.md#communitiessites) Neem een gebruikersprofielpagina op voor het aangemelde lid dat de activiteiten van leden op dezelfde manier weergeeft.

## Concepten {#concepts}

An *activiteitsstroom* is de lijst van recente activiteiten die door een lid of een lijst van recente activiteiten op één enkele draad van inhoud, zoals een forumonderwerp of blog worden uitgevoerd.

Een lid kan een activiteitenstroom volgen, door of een ander individu of inhoud te volgen.

A *nieuwsfeed* is een samenvoeging van de activiteitsstromen die door een lid in één enkele stroom worden gevolgd.

A [sociale grafiek](essentials-socialgraph.md) vangt de volgende verhoudingen van één lid aan een andere.

## Essentiële elementen voor client-kant {#essentials-for-client-side}

<table> 
 <tbody>
  <tr>
   <td> <strong>resourceType</strong></td> 
   <td>sociale/activiteitsstromen/componenten/hbs/activiteitsstromen</td> 
  </tr>
  <tr>
   <td> <a href="scf.md#add-or-include-a-communities-component"><strong>inclusief</strong></a></td> 
   <td>Nee</td> 
  </tr>
  <tr>
   <td> <a href="clientlibs.md"><strong>clientllibs</strong></a></td> 
   <td>cq.social.hbs.activitystreams</td> 
  </tr>
  <tr>
   <td> <strong>sjablonen</strong></td> 
   <td> /libs/social/activitystreams/components/hbs/activitystreams/activitystreams.hbs<br /> /libs/social/activitystreams/components/hbs/activitystreams/activity/activity-title.hbs<br /> /libs/social/activitystreams/components/hbs/activitystreams/activity/activity.hbs</td> 
  </tr>
  <tr>
   <td> <strong>css</strong></td> 
   <td> /libs/social/activitystreams/components/hbs/activitystreams/clientlibs/activitystreams.css</td> 
  </tr>
  <tr>
   <td><strong> eigenschappen</strong></td> 
   <td>Zie <a href="activities.md">Functie voor activiteitsstromen</a></td> 
  </tr>
 </tbody>
</table>

* [Aanpassingen aan de clientzijde](client-customize.md)

## Essentiële elementen voor server-side {#essentials-for-server-side}

* [Activity Streams-API](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/activitystreams/api/package-frame.html)

* [Activity Streams Listener-API](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/activitystreams/listener/api/package-frame.html)

* [Aanpassingen op de server](server-customize.md)

### Functie activiteitsstroom {#activity-stream-function}

Een community-sitestructuur die de [Activiteitenstroomfunctie](functions.md#activity-stream-function)bevat een configuratie `activity streams` component.
