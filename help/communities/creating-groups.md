---
title: Communautaire groepen
seo-title: Community Groups
description: Gebruikersgroepen maken
seo-description: Creating community groups
uuid: 05429b23-9083-498c-9eb3-d49b049d9446
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: 868a3d5d-d505-4ce5-8776-5bbe68a30ccb
exl-id: 4b663228-9cb6-45c0-99dd-8dd7fc2aa4a6
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 0%

---

# Communautaire groepen {#community-groups}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

De eigenschap van communautaire groepen is de capaciteit voor een subcommunity dynamisch om binnen een communautaire plaats door erkende gebruikers (leden van de gemeenschap en auteurs) van de publicatie en auteursmilieu&#39;s worden gecreeerd.

Deze mogelijkheid is aanwezig wanneer de [group, functie](functions.md#groups-function) aanwezig is in het dialoogvenster [community-site](sites-console.md) structuur.

A [communitygroepsjabloon](tools-groups.md) verstrekt het ontwerp van de communautaire groepspagina wanneer een communautaire groep dynamisch wordt gecreeerd.

Een of meer groepssjablonen worden geselecteerd voor de groepsfunctie wanneer de functie wordt toegevoegd aan de structuur van een gemeenschapssite of aan een sjabloon voor een gemeenschapssite. Deze lijst van groepsmalplaatjes wordt voorgesteld aan het lid of de auteur die dynamisch tot een nieuwe groep van binnen de communautaire plaats leidt.

## Een nieuwe groep maken {#creating-a-new-group}

De mogelijkheid om een nieuwe community-groep te maken, is afhankelijk van het bestaan van een community-site die de groepfunctie bevat, zoals een site die is gemaakt op basis van de ` [Reference Site Template](sites.md)`.

De volgende voorbeelden gebruiken de communitysite die is gemaakt op basis van de `Reference Site Template` zoals beschreven in de [Aan de slag met AEM Communities](getting-started.md) zelfstudie.

Dit is de pagina die wordt geladen bij publicatie wanneer de **[!UICONTROL Groups]** menu-item is geselecteerd:

![chlimage_1-236](assets/chlimage_1-236.png)

Wanneer u **[!UICONTROL New Group]** wordt geopend.

Onder de **[!UICONTROL Settings]** tabblad geeft u de basisfuncties van de groep op:

![chlimage_1-237](assets/chlimage_1-237.png)

* **[!UICONTROL Group Name]**
De titel van de groep die op de communitysite moet worden weergegeven.

* **[!UICONTROL Description]**
Een beschrijving van de groep die op de communitysite moet worden weergegeven.

* **[!UICONTROL Invite]**
Een lijst met leden die moeten worden uitgenodigd om deel te nemen aan de groep. Bij het zoeken naar vooraf bepaalde typen worden suggesties van leden van de gemeenschap geleverd die u wilt uitnodigen.

* **[!UICONTROL Group URL Name]**
De naam voor de groepspagina die deel van URL wordt.

* **[!UICONTROL Open Group]**
Selecteren 
`Open Group` geeft aan dat een anonieme sitebezoeker de inhoud mag bekijken en de selectie ongedaan zal maken `Member Only Group`.

* **[!UICONTROL Member Only Group]**
Selecteren 
`Member Only Group` Hiermee geeft u aan dat alleen leden van de groep de inhoud mogen weergeven en de selectie ongedaan maken `Open Group`.

Onder de **[!UICONTROL Template]** tab is de mogelijkheid om een keuze te maken uit de lijst met sjablonen voor groepen die zijn opgegeven toen de groepsfunctie was opgenomen in de structuur van de site van de community of in een sjabloon voor een community-site.

![chlimage_1-238](assets/chlimage_1-238.png)

Onder de **[!UICONTROL Image]** is de mogelijkheid om een afbeelding te uploaden die voor de groep op de pagina Groepen van de communautaire site moet worden weergegeven. De afbeelding wordt op het standaardstijlblad vergroot tot 170 x 90 pixels.

![chlimage_1-239](assets/chlimage_1-239.png)

Als u **[!UICONTROL Create Group]** , worden de pagina&#39;s voor de groep gemaakt op basis van de gekozen sjabloon, wordt een gebruikersgroep gemaakt voor lidmaatschap en wordt de pagina Groepen bijgewerkt om de nieuwe subcommunity weer te geven.

De pagina Groepen met een nieuwe subcommunity met de naam &quot;Focus Group&quot;, waarvoor een afbeeldingsminiatuur is geüpload, ziet er bijvoorbeeld als volgt uit (nog steeds aangemeld als beheerder van een communitygroep):

![chlimage_1-240](assets/chlimage_1-240.png)

Het selecteren van `Focus Group` Met de koppeling wordt de pagina Focus Group geopend in de browser, die een eerste weergave heeft op basis van de gekozen sjabloon, en een submenu bevat onder het menu van de hoofdsite van de community:

![chlimage_1-241](assets/chlimage_1-241.png)

## Component Lijst van leden van groep Gemeenschap {#community-group-member-list-component}

De `Community Group Member List` is bedoeld voor gebruik door ontwikkelaars van groepssjablonen.

## Aanvullende informatie {#additional-information}

Meer informatie is te vinden op de [Essentiële elementen van gebruikersgroepen](essentials-groups.md) pagina voor ontwikkelaars.

Voor andere informatie over groepen van gemeenschappen gaat u naar [Gebruikers en gebruikersgroepen beheren](users.md).
