---
title: QnA Essentials
seo-title: QnA Essentials
description: Functie van forum met vragen en antwoorden
seo-description: Questions and answers forum feature
uuid: c718a8e3-b3bd-4db9-8c0f-6dd973d40583
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: ceace3aa-78a5-485e-b519-630479e087d8
exl-id: 99f8afda-1771-471b-bd0c-99960a453bc9
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 0%

---

# QnA Essentials {#qna-essentials}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Deze pagina bevat de essentiële informatie voor het werken met de functie voor vragen en antwoorden (QnA)-forums.

## Essentiële elementen voor client-kant {#essentials-for-client-side}

<table> 
 <tbody>
  <tr>
   <td> resourceType</td> 
   <td>social/qna/components/hbs/qnaforum</td> 
  </tr>
  <tr>
   <td> <a href="scf.md#add-or-include-a-communities-component">inclusief</a></td> 
   <td>Nee</td> 
  </tr>
  <tr>
   <td> <a href="clientlibs.md">clientllibs</a></td> 
   <td>cq.ckeditor<br /> cq.social.hbs.stemden<br /> cq.social.hbs.qna</td> 
  </tr>
  <tr>
   <td> sjablonen</td> 
   <td> /libs/social/qna/components/hbs/qnaforum/qnaforum.hbs<br /> /libs/social/qna/components/hbs/qnaforum/activity-title.hbs</td> 
  </tr>
  <tr>
   <td> css</td> 
   <td> /libs/social/qna/components/hbs/qnaforum/clientlibs/qnaforum.css</td> 
  </tr>
  <tr>
   <td> eigenschappen</td> 
   <td>Zie <a href="working-with-qna.md">QnA-forumfunctie</a></td> 
  </tr>
 </tbody>
</table>

* [Aanpassingen aan de clientzijde](client-customize.md)

## Essentiële elementen voor server-side {#essentials-for-server-side}

* [QnA API](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/qna/client/api/package-summary.html)

* [QnA-eindpunten](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/qna/client/endpoints/package-summary.html)

* [Aanpassingen op de server](server-customize.md)

### QnA-functie {#qna-function}

Een community-sitestructuur die de [QnA-functie](functions.md#qna-function) zal gevormd hebben `QnA` en instellingen die invloed hebben op de matiging en het labelen. De functie QnA ondersteunt het identificeren van een [geprivilegieerde gebruikersgroep](users.md#privileged-members-group).

### Toegang tot berichten van het Forum QnA (UGC) {#accessing-qna-forum-posts-ugc}

UGC moet worden gemoderniseerd met behulp van een van de standaardmethoden voor gematigdheid.\
Zie [Door gebruiker gegenereerde inhoud modereren](moderate-ugc.md).

Met ingang van AEM 6.1. [gemeenschappelijk archief](working-with-srp.md) voor UGC omvat programmatische toegang tot UGC ongeacht de gekozen opslagoptie (zoals ASRP, MSRP of JSRP).

**De locatie en de indeling van de UGC in de opslagplaats kunnen zonder waarschuwing worden gewijzigd**.

Zie:

* [Overzicht opslagbronprovider](srp.md) - overzicht van het gebruik van introducties en opslagplaatsen
* [SRP en UGC Essentials](srp-and-ugc.md) - SRP-hulpprogrammamethoden en -voorbeelden
* [Toegang tot UGC met SRP](accessing-ugc-with-srp.md) - coderingsrichtlijnen
* [SocialUtils Refactoring](socialutils.md) - het in kaart brengen van afgekeurde nutsmethodes aan huidige SRP nutsmethodes
