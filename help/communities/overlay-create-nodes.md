---
title: Notities maken
seo-title: Create Nodes
description: Het opmerkingensysteem bedekken
seo-description: Overlay the comments system
uuid: 802ae28b-9989-4c2c-b466-ab76a724efd3
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: cd4f53ee-537b-4f10-a64f-474ba2c44576
exl-id: fc044a4e-0037-405f-8c26-b388c6a98733
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 1%

---

# Notities maken {#create-nodes}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Bedek het opmerkingssysteem met een douaneversie door het minimale aantal dossiers noodzakelijk van /libs in /apps te kopiëren en hen te wijzigen in /apps.

>[!CAUTION]
>
>De inhoud van de map /libs wordt nooit bewerkt, omdat een nieuwe installatie of upgrade de map /libs kan verwijderen of vervangen, terwijl de inhoud van de map /apps ongewijzigd blijft.

Gebruiken [CRXDE Lite](../../help/sites-developing/developing-with-crxde-lite.md) op een auteurinstantie, begin door een weg in de /apps omslag te creëren die aan de overlapte componenten in de /libs omslag identiek is.

Het pad dat wordt gedupliceerd, is

* `/libs/social/commons/components/hbs/comments/comment`

Sommige knooppunten in het pad zijn mappen en andere componenten.

1. Bladeren naar [http://localhost:4502/crx/de/index.jsp](http://localhost:4502/crx/de/index.jsp)
1. Maken `/apps/social` (als deze nog niet bestaat)
   * Selecteren `/apps` node
   * **[!UICONTROL Create > Folder ...]**
      * Naam invoeren: `social`
1. Selecteren `social` node
   * **[!UICONTROL Create > Folder...]**
      * Naam invoeren: `commons`
1. Selecteren `commons` node
   * **[!UICONTROL Create > Folder...]**
      * Naam invoeren: `components`
1. Selecteren `components` node
   * **[!UICONTROL Create > Folder..]**.
      * Naam invoeren: `hbs`
1. Selecteren `hbs` node
   * **[!UICONTROL Create > Create Component...]**
      * Label invoeren: `comments`
      * Titel invoeren: `Comments`
      * Beschrijving invoeren: `List of comments without showing avatars`
      * Supertype: `social/commons/components/comments`
      * Groep invoeren: `Communities`
      * Klikken **[!UICONTROL Next]** tot **[!UICONTROL OK]**
1. Selecteren `comments` node

   * **[!UICONTROL Create > Create Component...]**

      * Label invoeren: `comment`
      * Titel invoeren: `Comment`
      * Beschrijving invoeren: `A comment instance without avatars`
      * Supertype: `social/commons/components/comments/comment`
      * Groep invoeren: `.hidden`
      * Klikken **[!UICONTROL Next]** tot **[!UICONTROL OK]**
   * Selecteer **[!UICONTROL Save All]**
1. De standaardinstelling verwijderen `comments.jsp`
   * Knooppunt selecteren `/apps/social/commons/components/hbs/comments/comments.jsp`
   * Selecteer **[!UICONTROL Delete]**
1. De standaardcomment.jsp verwijderen
   * Selecteer knooppunt `/apps/social/commons/components/hbs/comments/comment/comment.jsp`
   * Selecteer **[!UICONTROL Delete]**
   * Selecteer **[!UICONTROL Save All]**

>[!NOTE]
>
>Om de overervingsketen te behouden, `Super Type` (eigenschap `sling:resourceSuperType`) van de bedekkingscomponenten op dezelfde waarde worden ingesteld als de `Super Type` van de onderdelen die worden bedekt, in dit geval
>
>* `social/commons/components/comments`
>* `social/commons/components/comments/comment`
>


De eigen overlay `Type`(eigenschap `sling:resourceType`) moet een relatieve zelfverwijzing zijn, zodat de inhoud die niet wordt gevonden in /apps, wordt gezocht in /libs.
* Naam: `sling:resourceType`
* Type: `String`
* Waarde: `social/commons/components/hbs/comments`

1. Groen selecteren `[+] Add`
   * Naam: `sling:resourceType`
   * Type: `String`
   * Waarde: `social/commons/components/hbs/comments/comment`
1. Groen selecteren `[+] Add`
   * Selecteer **[!UICONTROL Save All]**

![chlimage_1-4](assets/chlimage_1-4.png)
