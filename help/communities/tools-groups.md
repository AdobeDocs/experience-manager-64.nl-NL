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
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 0%

---


# Groepssjablonen {#group-templates}

De console van de Malplaatjes van de Groep is zeer gelijkaardig aan [Sitesjablonen](sites.md) console. Beide zijn blauwdrukken voor een set vooraf bekabelde pagina&#39;s en functies die een gemeenschapssite vormen. Het verschil is dat een plaatsmalplaatje voor de belangrijkste gemeenschap is en een groepsmalplaatje voor een communautaire groep, een subgemeenschap die binnen de belangrijkste gemeenschap wordt genesteld.

Een community-groep wordt opgenomen in een sitesjabloon door de functie [Groepen](functions.md#groups-function) (die niet de eerste of enige functie in de sjabloon mag zijn) op te nemen.

Vanaf Communities [feature pack 1](deploy-communities.md#latestfeaturepack), is het mogelijk om groepen te nesten door de functie Groepen op te nemen in een groepssjabloon.

Op het moment dat de actie wordt ondernomen om een nieuwe communautaire groep tot stand te brengen, wordt het malplaatje (de structuur) van de groep geselecteerd. De selectie hangt van af hoe de functie van Groepen toen toegevoegd aan het plaats of groepsmalplaatje werd gevormd.

>[!NOTE]
>
>De consoles voor het maken van [communitysites](sites-console.md), [communitysitesjablonen](sites.md), [communitygroepssjablonen](tools-groups.md) en [communityfuncties](functions.md) zijn alleen bedoeld voor gebruik in de auteursomgeving.

## Console {#group-templates-console} voor groepssjablonen

In het auteursmilieu, om de console van groepsmalplaatjes te bereiken

* Vanuit globale navigatie: **[!UICONTROL Tools > Communities > Group Templates]**

Deze console toont de malplaatjes waarvan een [communityplaats](sites-console.md) kan worden gecreeerd en nieuwe groepsmalplaatjes om worden gecreeerd toe.

![groepstemplaat](assets/groupstemplate.png)

## Groepsjabloon maken {#create-goup-template}

Selecteer **[!UICONTROL Create]** om een nieuwe groepssjabloon te maken

Hiermee wordt het deelvenster Site-editor weergegeven met drie subdeelvensters:

### Basisinformatie {#basic-info}

![chlimage_1-96](assets/chlimage_1-96.png)

In het deelvenster Basisinformatie worden een naam, beschrijving en of de sjabloon is ingeschakeld of uitgeschakeld, geconfigureerd:

* **[!UICONTROL New Group Template Name]**
De sjabloonnaam-id

* **[!UICONTROL Description]**
De sjabloonbeschrijving

* **[!UICONTROL Disabled/Enabled]**
Een schakeloptie die bepaalt of naar de sjabloon kan worden verwezen

### Miniatuur {#thumbnail}

![chlimage_1-97](assets/chlimage_1-97.png)

(Optioneel) Selecteer het pictogram Afbeelding uploaden om een miniatuur met de naam en beschrijving weer te geven aan makers van gemeenschapssites.

### Structuur {#structure}

>[!CAUTION]
>
>Als het werken met AEM 6.1 Gemeenschappen FP4 of vroeger, voeg geen groepsfunctie aan een groepsmalplaatje toe.
>
>De functie Geneste groepen is beschikbaar vanaf de Gemeenschappen [FP1](communities.md#latestfeaturepack).
>
>Het is nog steeds niet toegestaan een functie Groepen toe te voegen als de eerste of enige functie in een sjabloon.

![grptemplateeditor](assets/grptemplateeditor.png)

Als u communityfuncties wilt toevoegen, sleept u van de rechterkant naar links in de volgorde waarin de koppelingen in het sitemenu moeten worden weergegeven. Stijlen worden toegepast op de sjabloon tijdens het maken van de site.

Als u bijvoorbeeld een forum wilt, sleept u de forumfunctie uit de bibliotheek en zet u de functie neer onder de sjabloonbuilder. Dit zal in de dialoog van de forumconfiguratie resulteren die. Zie [functies console](functions.md) voor informatie over de configuratievensters.

U kunt doorgaan met slepen en neerzetten van alle andere communityfuncties die voor een subcommunity-site (groep) op basis van deze sjabloon zijn gewenst.

![dragfunctions](assets/dragfunctions.png)

Nadat alle gewenste functies in het sjabloonbuildergebied zijn neergezet en geconfigureerd, selecteert u **[!UICONTROL Save]** in de rechterbovenhoek.

## Groepssjabloon bewerken {#edit-group-template}

Wanneer het bekijken van communautaire groepen in de belangrijkste [console van de Malplaatjes van de Groep](#group-templates-console), is het mogelijk om een bestaand groepsmalplaatje voor uitgeven te selecteren.

Het bewerken van een groepssjabloon heeft geen invloed op communitysites die al van de sjabloon zijn gemaakt. In plaats daarvan kunt u direct [de structuur van een communitysite](sites-console.md#modify-structure) bewerken.

Dit proces verstrekt de zelfde panelen zoals [creërend een groepsmalplaatje](#create-goup-template).
