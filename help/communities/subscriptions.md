---
title: Communityabonnementen
seo-title: Communities Subscriptions
description: Communautaire leden communiceren via e-mail met andere leden
seo-description: Community members interact with other members through email
uuid: a4b98769-c219-4e18-8e80-9a806ab979ff
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 33c85af4-4c56-487a-ba60-55211cb9f72c
role: Admin
exl-id: 8a756328-0405-49b7-b94d-3dd5a87c782a
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 0%

---

# Communityabonnementen {#communities-subscriptions}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Overzicht {#overview}

Vanaf Gemeenschappen [FP1](deploy-communities.md#latestfeaturepack)kunnen leden van de gemeenschap via e-mail communiceren met de gemeenschap via een functie die abonnementen wordt genoemd.

Abonnementen lijken op [meldingen](notifications.md) aangezien leden zich kunnen abonneren bij het volgen van blogartikelen, forumonderwerpen of QnA-vragen.

Abonnementen worden onderscheiden van meldingen:

* Leden mogen zich niet abonneren wanneer zij andere leden volgen
* De enige actie die leden kunnen ondernemen, is het selecteren van `Email Subscriptions` wanneer volgende
* Wanneer e-mailantwoord is geconfigureerd, kunnen leden inhoud effectief posten door eenvoudig te antwoorden op de ontvangen e-mail

### Vereisten {#requirements}

**E-mail configureren**

E-mail moet worden gevormd om abonnementen te functioneren en voor leden te antwoorden per e-mail.

Voor instructies over het instellen van e-mailberichten raadpleegt u [E-mail configureren](email.md).

**Abonnementen inschakelen en volgen**

Componenten moeten worden geconfigureerd om abonnementen in te schakelen *en* volgende. Functies die abonnementen toestaan, zijn [blog](blog-feature.md), [forum](forum.md) en [QnA](working-with-qna.md).

## Abonnementen van volgende {#subscriptions-from-following}

![chlimage_1-5](assets/chlimage_1-5.png)

De **Volg** biedt een manier om vermeldingen als activiteiten, abonnementen en/of meldingen te volgen. Elke keer als **Volg** is geselecteerd, is het mogelijk om een selectie in of uit te schakelen.

Als een van de volgende methoden is geselecteerd, verandert de tekst van de knop in **volgende**. Voor het gemak is het mogelijk om `Unfollow All` om alle methoden uit te schakelen.

De **Volg** bevat de knop `Email Subscriptions` optie slechts wanneer een forum, QnA, of blog wordt gevormd om e-mailabonnementen toe te laten. Deze knop verschijnt

* Op de belangrijkste eigenschappagina voor toegelaten forum, QnA, of blog

   * Hiermee wordt een e-mail verzonden voor alle activiteiten in het kader van die functie

* Voor een specifiek bericht, zoals een forumonderwerp, een QnA-vraag of een blogartikel

   * Wordt een e-mail verzonden wanneer er activiteit is voor dat specifieke item

## Reageren per e-mail {#reply-by-email}

Wanneer e-mail [geconfigureerd voor beantwoorden per e-mail](email.md#configure-polling-importer), ontvangt het lid dat zich heeft geabonneerd een e-mail met de geposte inhoud en een koppeling naar de online-inhoud.

Als ze op het e-mailbericht reageren, wordt de inhoud die ze in het antwoord invoeren, online weergegeven als inhoud.

![chlimage_1-6](assets/chlimage_1-6.png)

De tijd die nodig is om een antwoord te plaatsen, wordt bepaald door de [update-interval opiniepeilingimportmodule](email.md#configure-polling-importer).

![chlimage_1-7](assets/chlimage_1-7.png)
