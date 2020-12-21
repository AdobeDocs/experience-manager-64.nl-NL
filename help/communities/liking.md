---
title: Koppeling gebruiken
seo-title: Koppeling gebruiken
description: De Liking-component toevoegen en configureren
seo-description: De Liking-component toevoegen en configureren
uuid: 12103ab7-1a1c-49cd-8dad-6c7508b4550e
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: dcde4e03-78ab-4779-96a1-05ac41f14701
translation-type: tm+mt
source-git-commit: f78f83ef3b9373bcbee3e5179a9bbec4d9462255
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 0%

---


# Koppeling gebruiken {#using-liking}

De `Liking`component is een nuttig hulpmiddel dat gebruikers toestaat om een mening over een bepaald stuk van inhoud, zoals een commentaar binnen een forum te uiten. Met de `Liking`component, selecteren de leden het hartpictogram om op een positieve mening te wijzen.

## Koppeling toevoegen aan een pagina {#adding-liking-to-a-page}

Als u een `Liking`-component in de ontwerpmodus aan een pagina wilt toevoegen, gebruikt u de componentbrowser om te zoeken naar

* `Communities / Liking`

en sleep het naar de juiste positie op een pagina, zoals een positie ten opzichte van de functie die gebruikers leuk kunnen vinden.

Voor noodzakelijke informatie, bezoek [de Grondbeginselen van Componenten van Gemeenschappen](basics.md).

Als de [vereiste client-side bibliotheken](essentials-liking.md#essentials-for-client-side) worden opgenomen, wordt de `Liking`-component op deze manier weergegeven.

![chlimage_1-93](assets/chlimage_1-93.png)

## Koppeling configureren {#configuring-liking}

Selecteer de geplaatste `Liking` component en selecteer `Configure` pictogram dat het Edit dialoog opent.

![chlimage_1-94](assets/chlimage_1-94.png)

Geef onder het tabblad **[!UICONTROL Texts & Labels]** de eigenschappen op die worden gebruikt voor het opnemen van &#39;like&#39;.

![chlimage_1-95](assets/chlimage_1-95.png)

* **[!UICONTROL Positive Response Label]**
(
*Vereist*) De eigenschapsnaam voor een positieve reactie.

* **[!UICONTROL Negative Response Label]**
(
*Vereist*) De eigenschapsnaam voor een negatieve reactie.

* **[!UICONTROL Tally Name]**
(
*Vereist*) De interne, identificeerbare eigenschapsnaam voor dit geval van een stemcomponent.

## Ervaring {#site-visitor-experience} voor bezoekers van site

### Leden {#members}

De leden kunnen te allen tijde van mening veranderen.

### Anonieme {#anonymous}

Anonieme koppelingen worden niet ondersteund. Site-bezoekers moeten zich registreren (lid worden) en zich aanmelden om deel te nemen aan een abonnement.

## Aanvullende informatie {#additional-information}

Meer informatie vindt u op de pagina [Liking Essentials](essentials-liking.md) voor ontwikkelaars.
