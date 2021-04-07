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
exl-id: 01a20578-56c3-41b3-8a0e-281104af2481
translation-type: tm+mt
source-git-commit: bd94d3949f0117aa3e1c9f0e84f7293a5d6b03b4
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 1%

---

# De weergave wijzigen {#alter-the-appearance}

## Het script {#modify-the-script} wijzigen

Het script comment.hbs is verantwoordelijk voor het maken van de algemene HTML voor elke opmerking.

Als u de avatar niet naast elke geposte opmerking wilt weergeven:

1. `comment.hbs`kopiëren van `libs`naar `apps`
   1. Selecteer `/libs/social/commons/components/hbs/comments/comment/comment.hbs`
   1. Selecteer **[!UICONTROL Copy]**
   1. Selecteer `/apps/social/commons/components/hbs/comments/comment`
   1. Selecteer **[!UICONTROL Paste]**
1. De bedekking `comment.hbs` openen
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

## De overlay {#replicate-the-overlay} dupliceren

Duw de bedekte commentaarcomponent aan de publicatieinstantie gebruikend het Hulpmiddel van de Replicatie.

>[!NOTE]
>
>Een robuustere vorm van replicatie zou zijn om een pakket in de Manager van het Pakket te creëren en [activeer ](../../help/sites-administering/package-manager.md#replicating-packages) het. Een pakket kan worden geëxporteerd en gearchiveerd.

Selecteer **[!UICONTROL Tools > Deployment > Replication]** en **[!UICONTROL Activate Tree]** in de globale navigatie.

Typ `/apps/social/commons` voor het beginpad en selecteer **[!UICONTROL Activate]**.

![chlimage_1-42](assets/chlimage_1-42.png)

## Resultaten weergeven {#view-results}

Als u zich als beheerder aanmeldt bij de publicatie-instantie, bijvoorbeeld http://localhost:4503/crx/de als beheerder/beheerder, kunt u controleren of de bovenliggende componenten aanwezig zijn.

Als u zich afmeldt en opnieuw inlogt als `aaron.mcdonald@mailinator.com/password` en de pagina vernieuwt, zult u merken dat de geposte opmerking niet meer wordt weergegeven met een avatar, in plaats daarvan wordt een eenvoudige &#39;xxx&#39; weergegeven.

![chlimage_1-43](assets/chlimage_1-43.png)
