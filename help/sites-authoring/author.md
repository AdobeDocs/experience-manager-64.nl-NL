---
title: Concept of Authoring
seo-title: Concept of Authoring
description: Concepten van ontwerpen in AEM
seo-description: Concepten van ontwerpen in AEM
uuid: 824c8b91-07c7-471b-b3aa-5a73d6d48414
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: introduction
content-type: reference
discoiquuid: 72ee013a-7a60-41ee-9421-2846e4c6bc68
translation-type: tm+mt
source-git-commit: 8b75cf8fd862302446fbb3d8823eec2bd708febe
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 0%

---


# Concept of Authoring and Publishing{#authoring}

AEM biedt u twee omgevingen:

* Auteur
* Publicatie

These interact to enable you to make content available on your website - so that your visitors can read it.

The author environment provides the mechanisms for creating, updating and reviewing this content before actually publishing it:

* Een auteur maakt en beoordeelt de inhoud (dit kan van verschillende typen zijn). bijvoorbeeld pagina&#39;s, middelen, publicaties, enz.)
* die op een gegeven moment op uw website worden gepubliceerd.

![chlimage_1-289](assets/chlimage_1-289.png)

Op het auteursmilieu wordt de functionaliteit van AEM ter beschikking gesteld door twee UIs. For the publish environment you design the entire look-and-feel of the interface made available to your users.

>[!NOTE]
>
>AEM en de Dispatcher worden gebruikt om deze AEM documentatie te publiceren.

## Auteursomgeving {#author-environment}

The author works in what is known as the **[author environment](/help/sites-authoring/home.md)**. This provides an easy to use interface (graphical user interface (GUI or UI)) for creating the content. It is usually located behind a company&#39;s firewall that provides full protection and requires the author to login, using an account that has been assigned the appropriate access rights.

>[!NOTE]
>
>Your account needs the appropriate access rights to create, edit or publish content.

Depending on how your instance and your personal access rights are configured you can perform many tasks on your content, including (amongst others):

* generate new content, or edit existing content, on a page
* use predefined templates to create new content pages
* create, edit and manage your assets and collections
* uw publicaties maken, bewerken en beheren
* develop your campaigns and the related resources
* develop and manage community sites
* move, copy or delete content pages, assets, etc
* publish (or unpublish) pages, assets, etc

Additionally, there are administrative tasks that help you manage your content:

* workflows that control how changes are managed; for example. enforcing a review before publication
* projects that coordinate individual tasks

>[!NOTE]
>
>AEM is also [administered](/help/sites-administering/home.md) (for a majority of tasks) from the author environment.

## Publicatie-omgeving {#publish-environment}

When ready, the AEM site&#39;s content is published to the **publish environment**. Here the website&#39;s pages are made available to the intended audience in accordance with the look-and-feel of the designed interface.

Meestal bevindt de publicatieomgeving zich in de gedemilitariseerde zone. met andere woorden , beschikbaar voor het internet , maar niet langer onder volledige bescherming van het interne netwerk .

Wanneer de AEM site een [gemeenschapssite](/help/communities/overview.md)is of onderdelen [van de](/help/communities/author-communities.md)Community bevat, kunnen bezoekers (leden) die zich hebben aangemeld, communiceren met de kenmerken van de Community. Ze kunnen bijvoorbeeld posten naar een forum, een opmerking plaatsen of andere leden volgen. Leden kunnen toestemming krijgen om activiteiten uit te voeren die normaal gesproken beperkt zijn tot de auteursomgeving, zoals het maken van nieuwe pagina&#39;s (groepen van gemeenschappen), blogartikelen en gematigde posten van andere leden.

>[!NOTE]
>
>Helaas is er soms sprake van een overlapping in de gebruikte terminologie. Dit kan gebeuren met:
>
>* **Publiceren/Publiceren ongedaan maken**
   >  Dit zijn de belangrijkste termen voor de acties die uw inhoud openbaar maken in uw publicatieomgeving (of niet).
   >
   >
* **Activeren/deactiveren**
   >  These terms are synonymous with publish/unpublish. They are more common in the classic UI.
   >
   >
* **Replicate / Replication**
   >  Dit zijn de technische termen die worden gebruikt om de verplaatsing van gegevens (bijvoorbeeld pagina-inhoud, bestanden, code, gebruikersopmerkingen) van de ene omgeving naar de andere aan te geven; d.w.z. bij het publiceren of omgekeerd repliceren van gebruikersopmerkingen.
>



## Dispatcher {#dispatcher}

To optimize performance for visitors to your website, the **[dispatcher](https://helpx.adobe.com/experience-manager/dispatcher/user-guide.html)**implements load balancing and caching.
