---
title: De weergave wijzigen (GB)
seo-title: Alter the Appearance
description: De HBS-scripts wijzigen
seo-description: Modify the HBS scripts
uuid: 6e1030af-f170-4a60-9d3f-439afd05de57
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 70be208d-185b-4b27-8e01-74e62f656344
exl-id: 358b70b8-8122-4eda-baa7-d9a58d6901f9
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 0%

---

# De weergave wijzigen (GB) {#alter-the-appearance-hbs}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Nu de componenten voor het systeem van de douanecommentaar in de toepassingsfolder (/apps) op zijn plaats zijn, met een resourceSuperType die naar het standaardcommentaarsysteem en het aangepaste Model/Beeld verwijzen geregistreerd, is het mogelijk om de implementatie te wijzigen.

Voor een eenvoudige demonstratie, een visuele functie, wordt de avatar verwijderd die wordt getoond van de aangemelde gebruiker die een opmerking plaatst.

>[!NOTE]
>
>Om van de uitbreiding gebruik te maken, moet de instantie van het opmerkingssysteem in een te beïnvloeden website (/content) zijn resourceType plaatsen om het systeem van douanecommentaar te zijn.

## De HBS-scripts wijzigen {#modify-the-hbs-scripts}

Gebruiken [CRXDE Lite](../../help/sites-developing/developing-with-crxde-lite.md):

* Openen [/apps/custom/components/comments/comment/comment.hbs](http://localhost:4502/crx/de/index.jsp#/apps/custom/components/comments/comment/comment.hbs)

   * Plaats een opmerking bij de tag die de avatar bevat voor een commentaarbericht (~ regel 21):

      ```
      <!--
       <<img class="scf-comment-avatar {{#if topLevel}}withTopLevel{{/if}}" src="{{author.avatarUrl}}"></img>
       -->
      ```

* Openen [/apps/custom/components/comments/comments.hbs](http://localhost:4502/crx/de/index.jsp#/apps/custom/components/comments/comments.hbs)

   * Verwijder de commentaarmarkering die de avatar voor de volgende commentaaringang (~ lijn 44) omvat:

      ```
      <!--
       <img class="scf-composer-avatar" src="{{loggedInUser.avatarUrl}}"></img>
       -->
      ```

* Selecteren **Alles opslaan**

## Aangepaste app repliceren {#replicate-custom-app}

Nadat de toepassing is gewijzigd, moet de aangepaste component opnieuw worden gerepliceerd.

Een manier om dit te doen is

* Vanuit het hoofdmenu

   * Selecteer **[!UICONTROL Tools > Operations > Replication]**
   * Selecteer `Activate Tree`
   * Set `Start Path`: tot `/apps/custom`
   * Uitschakelen `Only Modified`
   * Selecteren `Activate` knop

## Gewijzigde opmerking weergeven op gepubliceerde voorbeeldpagina {#view-modified-comment-on-published-sample-page}

[De ervaring voortzetten](extend-sample-page.md#publish-sample-page) op de publicatie-instantie, die nog steeds als dezelfde gebruiker is aangemeld, is het nu mogelijk de pagina in de publicatieomgeving te vernieuwen om de wijziging voor het verwijderen van de avatar weer te geven:

![chlimage_1-81](assets/chlimage_1-81.png)

## Voorbeeld van extensiepakket voor opmerkingen {#sample-comment-extension-package}

Bijgevoegd is een pakket van de toepassing van douanecommentaren die in dit leerprogramma wordt gecreeerd.

[Bestand ophalen](assets/sample-comment-extension-6-1-fp3.zip)
