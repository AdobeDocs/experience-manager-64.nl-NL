---
title: Groepssjablonen
seo-title: Groepssjablonen
description: Hoe te om tot de console van de Malplaatjes van de Groep toegang te hebben
seo-description: Hoe te om tot de console van de Malplaatjes van de Groep toegang te hebben
uuid: a3c6dfe6-f973-4dcf-9c66-ea52cbe56630
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 9a862756-58e8-47c0-a4b4-5d4aaac021e4
translation-type: tm+mt
source-git-commit: 13d890d08a032fe4eef1dac793dcf2a3e682a52c

---


# Groepssjablonen {#group-templates}

De console van de Malplaatjes van de Groep is zeer gelijkaardig aan de console van de Malplaatjes [van de](sites.md) Plaats. Beide zijn blauwdrukken voor een set vooraf bekabelde pagina&#39;s en functies die een gemeenschapssite vormen. Het verschil is dat een plaatsmalplaatje voor de belangrijkste gemeenschap is en een groepsmalplaatje voor een communautaire groep, een subgemeenschap die binnen de belangrijkste gemeenschap wordt genesteld.

Een community-groep wordt opgenomen in een sitesjabloon door de functie [](functions.md#groups-function) Groepen op te nemen (die niet de eerste of enige functie in de sjabloon mag zijn).

Vanaf Community [feature pack 1](deploy-communities.md#latestfeaturepack)is het mogelijk om groepen te nesten door de functie Groepen op te nemen in een groepssjabloon.

Op het moment dat de actie wordt ondernomen om een nieuwe communautaire groep tot stand te brengen, wordt het malplaatje (de structuur) van de groep geselecteerd. De selectie hangt van af hoe de functie van Groepen toen toegevoegd aan het plaats of groepsmalplaatje werd gevormd.

>[!NOTE]
>
>De consoles voor de verwezenlijking van [communautaire plaatsen](sites-console.md), de malplaatjes [van de](sites.md)communautaire plaats, [communautaire groepsmalplaatjes](tools-groups.md) en [communautaire functies](functions.md) zijn voor gebruik slechts in het auteursmilieu.

## Groep sjablonen {#group-templates-console}

In het auteursmilieu, om de console van groepsmalplaatjes te bereiken

* Vanuit globale navigatie: **[!UICONTROL Gereedschappen > Gemeenschappen > Sjablonen groeperen]**

Deze console toont de malplaatjes waarvan een [communautaire plaats](sites-console.md) kan worden gecreeerd en laat nieuwe groepsmalplaatjes toe om worden gecreeerd.

![groepstemplaat](assets/groupstemplate.png)

## Groepsjabloon maken {#create-goup-template}

Selecteer **[!UICONTROL Maken om een nieuwe groepssjabloon te gaan maken]**

Hiermee wordt het deelvenster Site-editor weergegeven met drie subdeelvensters:

### Basisinformatie {#basic-info}

![chlimage_1-96](assets/chlimage_1-96.png)

In het deelvenster Basisinformatie worden een naam, beschrijving en of de sjabloon is ingeschakeld of uitgeschakeld, geconfigureerd:

* **[!UICONTROL Nieuwe naam]** groepssjabloon De sjabloonnaam-id

* **[!UICONTROL Beschrijving]** van de sjabloon

* **[!UICONTROL Uitgeschakeld/Toegelaten]** een knevelschakelaar die of het malplaatje van verwijzingen voorziet controleert

### Miniatuur {#thumbnail}

![chlimage_1-97](assets/chlimage_1-97.png)

(Optioneel) Selecteer het pictogram Afbeelding uploaden om een miniatuur met de naam en beschrijving weer te geven aan makers van gemeenschapssites.

### Structuur {#structure}

>[!CAUTION]
>
>Als u werkt met AEM 6.1 Communities FP4 of eerder, voegt u geen groepsfunctie toe aan een groepssjabloon.
>
>De functie Geneste groepen is beschikbaar vanaf [KP1](communities.md#latestfeaturepack)van de Gemeenschappen.
>
>Het is nog steeds niet toegestaan een functie Groepen toe te voegen als de eerste of enige functie in een sjabloon.

![grptemplateeditor](assets/grptemplateeditor.png)

Als u communityfuncties wilt toevoegen, sleept u van de rechterkant naar links in de volgorde waarin de koppelingen in het sitemenu moeten worden weergegeven. Stijlen worden toegepast op de sjabloon tijdens het maken van de site.

Als u bijvoorbeeld een forum wilt, sleept u de forumfunctie uit de bibliotheek en zet u de functie neer onder de sjabloonbuilder. Dit zal in de dialoog van de forumconfiguratie resulteren die. Zie de [functieconsole](functions.md) voor informatie over de configuratievensters.

U kunt doorgaan met slepen en neerzetten van alle andere communityfuncties die voor een subcommunity-site (groep) op basis van deze sjabloon zijn gewenst.

![dragfunctions](assets/dragfunctions.png)

Nadat alle gewenste functies in het sjabloonbuildergebied zijn neergezet en geconfigureerd, selecteert u **[!UICONTROL Opslaan]** in de rechterbovenhoek.

## Groepssjabloon bewerken {#edit-group-template}

Wanneer het bekijken van communautaire groepen in de belangrijkste console [van de Malplaatjes van de](#group-templates-console)Groep, is het mogelijk om een bestaand groepsmalplaatje voor uitgeven te selecteren.

Het bewerken van een groepssjabloon heeft geen invloed op communitysites die al van de sjabloon zijn gemaakt. In plaats daarvan kunt u de structuur van een site [van de community rechtstreeks](sites-console.md#modify-structure)bewerken.

Dit proces biedt dezelfde deelvensters als het [maken van een groepssjabloon](#create-goup-template).
