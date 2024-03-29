---
title: Essentiële opmerkingen
seo-title: Comments Essentials
description: Overzicht van de component Opmerkingen
seo-description: Comments component overview
uuid: 58b7bb58-f598-4bcb-93ae-b7795cab51cd
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 18f54a1c-52aa-414d-b494-1f19b5c10345
exl-id: 3d5396b5-10e5-49bc-aa11-5a3df93d70c3
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 0%

---

# Essentiële opmerkingen {#comments-essentials}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Deze pagina bevat de belangrijkste elementen van het werken met het opmerkingensysteem (de component comments) en opties voor het beheer van de door de gebruiker gegenereerde inhoud (UGC) die worden gemaakt wanneer leden opmerkingen of antwoorden plaatsen.

De commentaarcomponent vestigt een commentaarsysteem zodat elke afzonderlijke post door een commentaarcomponent (enkelvoudig) wordt vertegenwoordigd. Het is het opmerkingsysteem dat op de pagina is opgenomen. De afzonderlijke opmerkingen worden gemaakt wanneer deze worden aangeroepen.

## Essentiële elementen voor client-kant {#essentials-for-client-side}

<table> 
 <tbody>
  <tr>
   <td> <strong>resourceType</strong></td> 
   <td> social/commons/components/hbs/comments</td> 
  </tr>
  <tr>
   <td> <a href="scf.md#add-or-include-a-communities-component"><strong>inclusief</strong></a></td> 
   <td>Ja - eigenschappen kunnen worden bewerkt in <i>ontwerp </i>mode</td> 
  </tr>
  <tr>
   <td> <a href="client-customize.md#clientlibs-for-scf"><strong>Clientlibs</strong></a></td> 
   <td>cq.ckeditor<br /> cq.social.hbs.comments<br /> cq.social.hbs.stemden</td> 
  </tr>
  <tr>
   <td> <strong>sjablonen</strong></td> 
   <td> /libs/social/commons/components/hbs/comments/comments.hbs<br /> </td> 
  </tr>
  <tr>
   <td> <strong>CSS</strong></td> 
   <td> /libs/social/commons/components/hbs/comments/clientlibs/commentsystem.css</td> 
  </tr>
  <tr>
   <td><strong> eigenschappen</strong></td> 
   <td> Zie <a href="comments.md">Opmerkingen gebruiken</a></td> 
  </tr>
 </tbody>
</table>

[Aanpassingen aan de clientzijde](client-customize.md)

### Eén exemplaar per pagina {#one-instance-per-page}

Paginering en het gebruik van URL&#39;s voor het in cache plaatsen en koppelen vereisen dat de URL uniek is per opmerkingsysteem. Daarom is slechts één instantie van een opmerkingssysteem per pagina toegestaan.

Andere functies zijn al het opmerkingensysteem. Deze zijn:

* [Blog](blog-developer-basics.md)
* [Kalender](calendar-basics-for-developers.md)
* [Bestandsbibliotheek](essentials-file-library.md)
* [Forum](essentials-forum.md)
* [QnA](qna-essentials.md)
* [Revisies](reviews-basics.md)

### Lijst met redenen voor vlag {#flag-reason-list}

De lijst met gemarkeerde redenen kan worden aangepast door een gemarkeerde redenlist.hbs aan uw app toe te voegen om te overschrijven wat zich in

* /libs/social/commons/components/hbs/comments/comment/flagreasonlist.hbs

Dit geldt voor alle componenten die een opmerkingsysteem uitbreiden.

## Essentiële elementen voor server-side {#essentials-for-server-side}

* [API voor opmerkingen](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/commons/comments/api/package-summary.html)

* [Eindpunten opmerkingen](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/commons/comments/endpoints/package-summary.html)

* [Aanpassingen op de server](server-customize.md)

### Toegang tot geposte opmerkingen (UGC) {#accessing-posted-comments-ugc}

UGC moet worden gemoderniseerd met behulp van een van de standaardmethoden voor gematigdheid.\
Zie [Door gebruiker gegenereerde inhoud modereren](moderate-ugc.md).

Met ingang van AEM 6.1. [gemeenschappelijk archief](working-with-srp.md) voor UGC omvat programmatische toegang tot UGC ongeacht de gekozen opslagoptie (zoals ASRP, MSRP of JSRP).

**De locatie en de indeling van de UGC in de opslagplaats kunnen zonder waarschuwing worden gewijzigd**.

Zie:

* [Overzicht opslagbronprovider](srp.md) - Inleiding en overzicht van het gebruik van opslagruimten
* [SRP en UGC Essentials](srp-and-ugc.md) - SRP-hulpprogrammamethoden en -voorbeelden
* [Toegang tot UGC met SRP](accessing-ugc-with-srp.md) - Codeerrichtsnoeren
* [SocialUtils Refactoring](socialutils.md) - Afgekeurde hulpprogrammamethoden toewijzen aan de huidige SRP-hulpprogrammamethoden
