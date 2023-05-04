---
title: Opmerking toevoegen aan voorbeeldpagina
seo-title: Add Comment to Sample Page
description: Aangepaste opmerkingen toevoegen aan een pagina
seo-description: Add Custom Comments to a page
uuid: 7dbaff4f-9986-435d-9379-7add676ea254
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 7185fb13-46a2-4fa3-aa21-a51e63cdb9be
exl-id: 96ef7e58-66c9-4985-973b-0c6fc7c39fd5
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 0%

---

# Opmerking toevoegen aan voorbeeldpagina {#add-comment-to-sample-page}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Nu de componenten voor het aangepaste opmerkingensysteem in de toepassingsmap (/apps) staan, is het mogelijk om de uitgebreide component te gebruiken. De instantie van het opmerkingssysteem in een website die moet worden beïnvloed moet zijn resourceType plaatsen om het systeem van douanecommentaar te zijn en alle noodzakelijke cliëntbibliotheken te omvatten.

## Vereiste clients identificeren {#identify-required-clientlibs}

De clientbibliotheken die nodig zijn voor de stijl en werking van de standaardopmerkingen zijn ook nodig voor uitgebreide opmerkingen.

De [Community Components Guide](components-guide.md) identificeert de vereiste clientbibliotheken. Blader naar de Component Guide en bekijk de component Comments, bijvoorbeeld:

[http://localhost:4502/content/community-components/en/comments.html](http://localhost:4502/content/community-components/en/comments.html)

Let op de drie clientbibliotheken die nodig zijn voor het renderen en correct functioneren van Opmerkingen. Deze zullen moeten worden opgenomen waar naar de uitgebreide opmerkingen wordt verwezen, alsmede de [uitgebreide clientbibliotheek met opmerkingen](extend-create-components.md#create-a-client-library-folder) ( `apps.custom.comments`).

![chlimage_1-47](assets/chlimage_1-47.png)

## Aangepaste opmerkingen toevoegen aan een pagina {#add-custom-comments-to-a-page}

Aangezien er slechts één opmerkingensysteem per pagina kan zijn, is het eenvoudiger om een voorbeeldpagina te maken, zoals in het kort wordt beschreven [Een voorbeeldpagina maken](create-sample-page.md) zelfstudie.

Als u een aangepaste component hebt gemaakt, typt u de ontwerpmodus en stelt u de componentgroep Custom beschikbaar om de optie `Alt Comments` aan de pagina toe te voegen.

De opmerking wordt alleen weergegeven en werkt alleen correct als de clientbibliotheken voor opmerkingen zijn toegevoegd aan de clientlibslist voor de pagina (zie [Clientlibs voor Community-componenten](clientlibs.md)).

### Opmerkingen Clientlibs op voorbeeldpagina {#comments-clientlibs-on-sample-page}

![Opmerkingen Clientlibs op voorbeeldpagina](assets/chlimage_1-48.png)

### Auteur: Alt-commentaar op voorbeeldpagina {#author-alt-comment-on-sample-page}

![Alt-commentaar op voorbeeldpagina](assets/chlimage_1-49.png)

### Auteur: Opmerkingsknooppunt voor voorbeeldpagina {#author-sample-page-comments-node}

U kunt het resourceType in CRXDE verifiëren door de eigenschappen van de commentaarknoop voor de steekproefpagina te bekijken bij `/content/sites/sample/en/jcr:content/content/primary/comments`.

![chlimage_1-50](assets/chlimage_1-50.png)

### Voorbeeldpagina publiceren {#publish-sample-page}

Nadat de aangepaste component aan de pagina is toegevoegd, is het ook nodig (re) [de pagina publiceren](sites-console.md#publishing-the-site).

### Publiceren: Alt-commentaar op voorbeeldpagina {#publish-alt-comment-on-sample-page}

Nadat u zowel de aangepaste toepassing als de voorbeeldpagina hebt gepubliceerd, moet u een opmerking kunnen invoeren. Bij aanmelding met een van de [demo-gebruiker](tutorials.md#demo-users) Voor beheerders moet het mogelijk zijn om een opmerking te plaatsen.

Hier aaron.mcdonald@mailinator.com vindt u een opmerking:

![chlimage_1-51](assets/chlimage_1-51.png) ![chlimage_1-52](assets/chlimage_1-52.png)

Nu het lijkt of de uitgebreide component correct werkt met de standaardweergave, is het tijd om de weergave te wijzigen.
