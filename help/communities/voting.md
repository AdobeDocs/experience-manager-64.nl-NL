---
title: Stemmen gebruiken
seo-title: Using Voting
description: De component Stemmen toevoegen aan een pagina
seo-description: Adding the Voting component to a page
uuid: 56e6cced-2f2d-434a-8fde-92a6c2478a04
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: 071cac6d-05c5-47ab-85bc-ead6693ca1f4
exl-id: 660a7106-0c21-4073-8319-4d6d20b9bc49
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---

# Stemmen gebruiken {#using-voting}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

De `Voting` is een nuttig hulpmiddel dat communautaire leden toestaat om een bepaald stuk van inhoud, zoals een antwoord binnen een component te schatten QnA. Met de `Voting` leden selecteren pijlen omhoog of omlaag om hun mening aan te geven.

## Stemmen toevoegen aan een pagina {#adding-voting-to-a-page}

Als u een `Voting` van een component aan een pagina op auteurswijze, gebruik componentenbrowser om van `Communities / Voting` en sleep het naar de juiste positie op een pagina, zoals een positie ten opzichte van de functie waar gebruikers op kunnen stemmen.

Voor de nodige informatie gaat u naar [Grondbeginselen van Community-componenten](basics.md).

Wanneer de [vereiste clientbibliotheken](essentials-voting.md#essentials-for-client-side) worden opgenomen, is dit hoe `Voting` wordt weergegeven.

![chlimage_1-307](assets/chlimage_1-307.png)

## Stemmen configureren {#configuring-voting}

Selecteer de geplaatste `Voting` te openen en de component te selecteren `Configure` wordt het dialoogvenster Bewerken geopend.

![chlimage_1-308](assets/chlimage_1-308.png)

Onder de **[!UICONTROL Texts & Labels]** , geeft u de eigenschappen op die worden gebruikt voor het opnemen van stemmen.

![chlimage_1-309](assets/chlimage_1-309.png)

* **[!UICONTROL Positive Response Label]**
(
*Vereist*) De interne eigenschapnaam voor een positieve reactie.

* **[!UICONTROL Negative Response Label]**
(
*Vereist*) De interne eigenschapnaam voor een negatieve reactie.

* **[!UICONTROL Tally Name]**
(
*Vereist*) De interne, identificeerbare eigenschapsnaam voor dit geval van een stemcomponent.

## Ervaring met sitebezoekers {#site-visitor-experience}

### Leden {#members}

De leden kunnen slechts eenmaal stemmen, maar kunnen te allen tijde van stemming veranderen.

### Anoniem {#anonymous}

Anonieme stemming wordt niet ondersteund. Sitebezoekers moeten zich registreren (lid worden) en zich aanmelden om eenmaal aan de stemming deel te nemen.

## Aanvullende informatie {#additional-information}

Meer informatie is te vinden op de [Grondbeginselen van de stemming](essentials-voting.md) pagina voor ontwikkelaars.
