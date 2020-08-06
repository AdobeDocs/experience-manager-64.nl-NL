---
title: Communautaire groepen
seo-title: Communautaire groepen
description: Gebruikersgroepen maken
seo-description: Gebruikersgroepen maken
uuid: 05429b23-9083-498c-9eb3-d49b049d9446
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: 868a3d5d-d505-4ce5-8776-5bbe68a30ccb
translation-type: tm+mt
source-git-commit: 8c66f2b0053882bd1c998d8e01dbb0573881bc87
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 0%

---


# Communautaire groepen {#community-groups}

De eigenschap van communautaire groepen is de capaciteit voor een subcommunity dynamisch om binnen een communautaire plaats door erkende gebruikers (leden van de gemeenschap en auteurs) van de publicatie en auteursmilieu&#39;s worden gecreeerd.

Deze mogelijkheid is aanwezig wanneer de functie [](functions.md#groups-function) Groepen aanwezig is in de structuur van de [community-site](sites-console.md) .

Een malplaatje [van de](tools-groups.md) communautaire groep verstrekt het ontwerp van de pagina van de communautaire groep wanneer een communautaire groep dynamisch wordt gecreeerd.

Een of meer groepssjablonen worden geselecteerd voor de groepsfunctie wanneer de functie wordt toegevoegd aan de structuur van een gemeenschapssite of aan een sjabloon voor een gemeenschapssite. Deze lijst van groepsmalplaatjes wordt voorgesteld aan het lid of de auteur die dynamisch tot een nieuwe groep van binnen de communautaire plaats leidt.

## Een nieuwe groep maken {#creating-a-new-group}

Het vermogen om een nieuwe communautaire groep tot stand te brengen hangt van het bestaan van een communautaire plaats af die de groepsfunctie omvat, zoals die van ` [Reference Site Template](sites.md)`wordt gecreeerd.

De volgende voorbeelden maken gebruik van de communitysite die is gemaakt op basis van de `Reference Site Template` beschrijving in de zelfstudie [Aan de slag met AEM Communities](getting-started.md) .

Dit is de pagina die wordt geladen bij het publiceren wanneer het **[!UICONTROL Groups]** menu-item wordt geselecteerd:

![chlimage_1-236](assets/chlimage_1-236.png)

Wanneer u het **[!UICONTROL New Group]** pictogram selecteert, wordt een dialoogvenster voor bewerken geopend.

Onder het **[!UICONTROL Settings]** tabblad geeft u de basiskenmerken van de groep op:

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
`Open Group` Hiermee geeft u aan dat een anonieme sitebezoeker de inhoud kan bekijken en de selectie ongedaan zal maken `Member Only Group`.

* **[!UICONTROL Member Only Group]**
Selecteren 
`Member Only Group` Hiermee geeft u aan dat alleen leden van de groep de inhoud mogen weergeven en dat de selectie wordt opgeheven `Open Group`.

Onder het **[!UICONTROL Template]** lusje is de capaciteit om van de lijst van communautaire groepsmalplaatjes te selecteren die werden gespecificeerd toen de groepsfunctie in de structuur van de communautaire plaats of in een malplaatje van de communautaire plaats werd omvat.

![chlimage_1-238](assets/chlimage_1-238.png)

Onder het **[!UICONTROL Image]** tabblad kunt u een afbeelding uploaden die u wilt weergeven voor de groep op de pagina Groepen van de communautaire site. De afbeelding wordt op het standaardstijlblad vergroot tot 170 x 90 pixels.

![chlimage_1-239](assets/chlimage_1-239.png)

Door de **[!UICONTROL Create Group]** knoop te selecteren, worden de pagina&#39;s voor de groep gecreeerd gebaseerd op het gekozen malplaatje, en een gebruikersgroep wordt gecreeerd voor lidmaatschap en de pagina van Groepen zal worden bijgewerkt om de nieuwe subcommunity te tonen.

De pagina Groepen met een nieuwe subcommunity met de naam &quot;Focus Group&quot;, waarvoor een afbeeldingsminiatuur is geüpload, ziet er bijvoorbeeld als volgt uit (nog steeds aangemeld als beheerder van een communitygroep):

![chlimage_1-240](assets/chlimage_1-240.png)

Als u de `Focus Group` koppeling selecteert, wordt de pagina Focus Group in de browser geopend. De browser krijgt een initiële weergave op basis van de gekozen sjabloon en bevat een submenu onder het menu van de hoofdsite van de community:

![chlimage_1-241](assets/chlimage_1-241.png)

## Component Lijst van leden van groep Gemeenschap {#community-group-member-list-component}

De `Community Group Member List` component is bedoeld voor gebruik door ontwikkelaars van groepssjablonen.

## Additional Information {#additional-information}

Meer informatie vindt u op de pagina [Community Group Essentials](essentials-groups.md) voor ontwikkelaars.

Voor andere informatie met betrekking tot communitygroepen, bezoek de [Managing Gebruikers en Gebruikersgroepen](users.md).
