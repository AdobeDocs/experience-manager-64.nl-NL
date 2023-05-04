---
title: Groepssjablonen
seo-title: Group Templates
description: Hoe te om tot de console van de Malplaatjes van de Groep toegang te hebben
seo-description: How to access the Group Templates console
uuid: a3c6dfe6-f973-4dcf-9c66-ea52cbe56630
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 9a862756-58e8-47c0-a4b4-5d4aaac021e4
role: Admin
exl-id: ac399a66-0f3b-4f95-969e-a4109c260d1d
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 0%

---

# Groepssjablonen {#group-templates}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

De console van de Malplaatjes van de Groep is zeer gelijkaardig aan [Sitesjablonen](sites.md) console. Beide zijn blauwdrukken voor een set vooraf bekabelde pagina&#39;s en functies die een gemeenschapssite vormen. Het verschil is dat een plaatsmalplaatje voor de belangrijkste gemeenschap is en een groepsmalplaatje voor een communautaire groep, een subgemeenschap die binnen de belangrijkste gemeenschap wordt genesteld.

Een community-groep is in een sitesjabloon opgenomen door de [Groepen, functie](functions.md#groups-function) (dit mag niet de eerste of enige functie in de sjabloon zijn).

Vanaf Gemeenschappen [functiepakket 1](deploy-communities.md#latestfeaturepack), is het mogelijk om groepen te nesten door de functie Groepen binnen een groepsmalplaatje te omvatten.

Op het moment dat de actie wordt ondernomen om een nieuwe communautaire groep tot stand te brengen, wordt het malplaatje (de structuur) van de groep geselecteerd. De selectie hangt van af hoe de functie van Groepen toen toegevoegd aan het plaats of groepsmalplaatje werd gevormd.

>[!NOTE]
>
>De consoles voor het creëren van [communitysites](sites-console.md), [communitysjablonen](sites.md), [communitygroepsjablonen](tools-groups.md) en [communautaire functies](functions.md) zijn alleen bestemd voor gebruik in de ontwerpomgeving.

## Groep sjablonen {#group-templates-console}

In het auteursmilieu, om de console van groepsmalplaatjes te bereiken

* Vanuit globale navigatie: **[!UICONTROL Tools > Communities > Group Templates]**

Deze console toont de malplaatjes waarvan een [community-site](sites-console.md) kunnen worden gemaakt en kunnen nieuwe groepssjablonen worden gemaakt.

![groepstemplaat](assets/groupstemplate.png)

## Groepsjabloon maken {#create-goup-template}

Selecteer **[!UICONTROL Create]**

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
>De functie Geneste groepen is beschikbaar vanaf Gemeenschappen [FP1](communities.md#latestfeaturepack).
>
>Het is nog steeds niet toegestaan een functie Groepen toe te voegen als de eerste of enige functie in een sjabloon.

![grptemplateeditor](assets/grptemplateeditor.png)

Als u communityfuncties wilt toevoegen, sleept u van de rechterkant naar links in de volgorde waarin de koppelingen in het sitemenu moeten worden weergegeven. Stijlen worden toegepast op de sjabloon tijdens het maken van de site.

Als u bijvoorbeeld een forum wilt, sleept u de forumfunctie uit de bibliotheek en zet u de functie neer onder de sjabloonbuilder. Dit zal in de dialoog van de forumconfiguratie resulteren die. Zie de [functies console](functions.md) voor informatie over de configuratievensters.

U kunt doorgaan met slepen en neerzetten van alle andere communityfuncties die voor een subcommunity-site (groep) op basis van deze sjabloon zijn gewenst.

![dragfunctions](assets/dragfunctions.png)

Zodra alle gewenste functies in het gebied van de malplaatjebouwer zijn gelaten vallen en gevormd, uitgezocht **[!UICONTROL Save]** in de rechterbovenhoek.

## Groepssjabloon bewerken {#edit-group-template}

Bij het weergeven van groepen van gemeenschappen in de hoofdmap [Groep sjablonen, console](#group-templates-console), is het mogelijk een bestaande groepssjabloon te selecteren om te bewerken.

Het bewerken van een groepssjabloon heeft geen invloed op communitysites die al van de sjabloon zijn gemaakt. Het is mogelijk rechtstreeks [een communitysite bewerken](sites-console.md#modify-structure)In plaats daarvan de structuur.

Dit proces biedt dezelfde deelvensters als [een groepssjabloon maken](#create-goup-template).
