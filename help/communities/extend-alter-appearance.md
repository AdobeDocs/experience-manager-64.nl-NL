---
title: De weergave wijzigen (GB)
seo-title: De vormgeving wijzigen
description: De HBS-scripts wijzigen
seo-description: De HBS-scripts wijzigen
uuid: 6e1030af-f170-4a60-9d3f-439afd05de57
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 70be208d-185b-4b27-8e01-74e62f656344
translation-type: tm+mt
source-git-commit: 2d1e39120d79de029927011d48f7397b53ad91bc
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 0%

---


# De vormgeving wijzigen (HBS) {#alter-the-appearance-hbs}

Nu de componenten voor het systeem van de douanecommentaar in de toepassingsfolder (/apps) op zijn plaats zijn, met een resourceSuperType die naar het standaardcommentaarsysteem en het aangepaste Model/Beeld verwijzen geregistreerd, is het mogelijk om de implementatie te wijzigen.

Voor een eenvoudige demonstratie, een visuele functie, wordt de avatar verwijderd die wordt getoond van de aangemelde gebruiker die een opmerking plaatst.

>[!NOTE]
>
>Om van de uitbreiding gebruik te maken, moet de instantie van het opmerkingssysteem in een te beïnvloeden website (/content) zijn resourceType plaatsen om het systeem van douanecommentaar te zijn.

## Wijzig de Manuscripten van GB {#modify-the-hbs-scripts}

Met [CRXDE Lite](../../help/sites-developing/developing-with-crxde-lite.md):

* [/apps/custom/components/comments/comment/comment.hbs](http://localhost:4502/crx/de/index.jsp#/apps/custom/components/comments/comment/comment.hbs) openen

   * Plaats een opmerking bij de tag die de avatar bevat voor een commentaarbericht (~ regel 21):

      ```
      <!--
       <<img class="scf-comment-avatar {{#if topLevel}}withTopLevel{{/if}}" src="{{author.avatarUrl}}"></img>
       -->
      ```

* [/apps/custom/components/comments/comments.hbs](http://localhost:4502/crx/de/index.jsp#/apps/custom/components/comments/comments.hbs) openen

   * Verwijder de commentaarmarkering die de avatar voor de volgende commentaaringang (~ lijn 44) omvat:

      ```
      <!--
       <img class="scf-composer-avatar" src="{{loggedInUser.avatarUrl}}"></img>
       -->
      ```

* Selecteer **Alles opslaan**

## Aangepaste app {#replicate-custom-app} repliceren

Nadat de toepassing is gewijzigd, moet de aangepaste component opnieuw worden gerepliceerd.

Een manier om dit te doen is

* Vanuit het hoofdmenu

   * Selecteer **[!UICONTROL Tools > Operations > Replication]**
   * Selecteer `Activate Tree`
   * `Start Path` instellen: tot `/apps/custom`
   * `Only Modified` uitschakelen
   * Knop `Activate` selecteren

## Gewijzigde opmerking weergeven op gepubliceerde voorbeeldpagina {#view-modified-comment-on-published-sample-page}

[Als u doorgaat met de ](extend-sample-page.md#publish-sample-page) ervaring met het publicatieexemplaar, dat nog steeds is aangemeld als dezelfde gebruiker, kunt u de pagina nu vernieuwen in de publicatieomgeving om de wijziging te bekijken om de avatar te verwijderen:

![chlimage_1-81](assets/chlimage_1-81.png)

## Voorbeeld van extensiepakket voor opmerkingen {#sample-comment-extension-package}

Bijgevoegd is een pakket van de toepassing van douanecommentaren die in dit leerprogramma wordt gecreeerd.

[Bestand ophalen](assets/sample-comment-extension-6-1-fp3.zip)