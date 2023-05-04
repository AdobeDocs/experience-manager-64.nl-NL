---
title: Classificaties gebruiken
seo-title: Using Ratings
description: Een beoordelingscomponent toevoegen aan een pagina
seo-description: Adding a Rating component to a page
uuid: a986970b-1221-4648-9a69-410f4480e0ae
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: a0e5491e-66bc-47b0-94a5-45a02bc558da
exl-id: 1de28140-5334-4ca2-a476-5ad253809808
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 0%

---

# Classificaties gebruiken {#using-ratings}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

De `Rating`wordt gebruikt op zichzelf of in combinatie met andere communautaire kenmerken. Met deze component kunnen leden van de gemeenschap die zich hebben aangemeld hun mening kenbaar maken door inhoud te beoordelen.

## Een waardering toevoegen aan een pagina {#adding-a-rating-to-a-page}

Als u een `Rating`naar een pagina in de modus Schrijver, zoek de component `Communities / Rating` en sleep het naar de juiste positie op een pagina, zoals een positie ten opzichte van de functie die leden kunnen waarderen.

Voor de nodige informatie gaat u naar [Grondbeginselen van Community-componenten](basics.md).

Wanneer de [vereiste clientbibliotheken](rating-basics.md#essentials-for-client-side) worden opgenomen, is dit hoe `Rating` wordt weergegeven.

![chlimage_1-493](assets/chlimage_1-493.png)

## Classificatie configureren {#configuring-rating}

Selecteer de geplaatste `Rating` te openen en de component te selecteren `Configure` wordt het dialoogvenster Bewerken geopend.

![chlimage_1-494](assets/chlimage_1-494.png)

Onder de **[!UICONTROL Texts & Labels]** geeft u de interne id voor de waardering op.

![chlimage_1-495](assets/chlimage_1-495.png)

**[!UICONTROL Tally Name]**
(*Vereist*) Een eenvoudige naam voor de `Rating`die dit exemplaar uniek identificeert. Moet een geldige knooppuntnaam voor de bewaarplaats zijn.

## Ervaring met sitebezoekers {#site-visitor-experience}

### Leden {#members}

Er is slechts één score per lid toegestaan. Het lid kan zijn rating te allen tijde wijzigen.

### Anoniem {#anonymous}

Anonieme detachering van een rating wordt niet ondersteund. Site-bezoekers moeten zich registreren (lid worden) en zich aanmelden om deel te nemen.

## Aanvullende informatie {#additional-information}

Meer informatie is te vinden op de [Grondbeginselen van classificaties](rating-basics.md) pagina voor ontwikkelaars.
