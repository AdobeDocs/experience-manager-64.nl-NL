---
title: De vormgeving wijzigen
seo-title: De vormgeving wijzigen
description: Het script wijzigen
seo-description: Het script wijzigen
uuid: 6930381b-74c1-4e63-9621-621dbedbc25e
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: da3891d3-fa07-4c88-b4ac-077926b3a674
translation-type: tm+mt
source-git-commit: 1ae2d7f99286e0b958d343778159e2d35095510e
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 1%

---


# De vormgeving wijzigen {#alter-the-appearance}

## Het script wijzigen {#modify-the-script}

Het script comment.hbs is verantwoordelijk voor het maken van de algemene HTML voor elke opmerking.

Als u de avatar niet naast elke geposte opmerking wilt weergeven:

1. Kopiëren `comment.hbs`van `libs`naar `apps`
   1. Selecteer `/libs/social/commons/components/hbs/comments/comment/comment.hbs`
   1. Selecteer **[!UICONTROL Copy]**
   1. Selecteer `/apps/social/commons/components/hbs/comments/comment`
   1. Selecteer **[!UICONTROL Paste]**
1. De bedekking openen `comment.hbs`
   * Dubbelklik op knooppunt `comment.hbs`in `/apps/social/commons/components/hbs/comments/comment folder`
1. Zoek de volgende regels en verwijder of verwijder deze of verwijder ze:

   ```xml
   <aside class="scf-comment-author">
           <img class="scf-comment-avatar {{#if topLevel}}withTopLevel{{/if}}" src="{{author.avatarUrl}}"></img>
   ```

Verwijder de regels of omring ze met &#39;&lt;!—&#39; en &#39;—>&#39; om ze uit te lichten. Bovendien worden de tekens &#39;xxx&#39; toegevoegd als visuele indicator van waar de avatar zou zijn geweest.

```xml
<!-- do not display avatar with comment
    <aside class="scf-comment-author">
        <img class="scf-comment-avatar {{#if topLevel}}withTopLevel{{/if}}" src="{{author.avatarUrl}}"></img>
```

## De bedekking dupliceren {#replicate-the-overlay}

Duw de bedekte commentaarcomponent aan de publicatieinstantie gebruikend het Hulpmiddel van de Replicatie.

>[!NOTE]
>
>Een robuustere vorm van replicatie zou zijn om een pakket in de Manager van het Pakket te creëren en het te [activeren](../../help/sites-administering/package-manager.md#replicating-packages) . Een pakket kan worden geëxporteerd en gearchiveerd.

Selecteer en **[!UICONTROL Tools > Deployment > Replication]** **[!UICONTROL Activate Tree]** kies in de globale navigatie.

Voer voor het beginpad in `/apps/social/commons` en selecteer **[!UICONTROL Activate]**.

![chlimage_1-42](assets/chlimage_1-42.png)

## Resultaten weergeven {#view-results}

Als u zich als beheerder aanmeldt bij de publicatie-instantie, bijvoorbeeld http://localhost:4503/crx/de als beheerder/beheerder, kunt u controleren of de bovenliggende componenten aanwezig zijn.

Als u zich afmeldt en opnieuw aanmeldt als `aaron.mcdonald@mailinator.com/password` en de pagina vernieuwt, ziet u dat de geposte opmerking niet meer wordt weergegeven bij een avatar, maar een eenvoudige &#39;xxx&#39; wordt weergegeven.

![chlimage_1-43](assets/chlimage_1-43.png)

