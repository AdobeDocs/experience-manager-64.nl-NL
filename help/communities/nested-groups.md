---
title: Geneste groepen ontwerpen
seo-title: Geneste groepen ontwerpen
description: Geneste groepen maken
seo-description: Geneste groepen maken
uuid: b478454a-24c6-4e1c-a6e0-afeb1bc4992c
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: introduction
content-type: reference
discoiquuid: 955a1876-4882-4926-82e9-846bc8bb332c
translation-type: tm+mt
source-git-commit: 2d1e39120d79de029927011d48f7397b53ad91bc
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 3%

---


# Geneste groepen ontwerpen {#authoring-nested-groups}

## Groepen maken op auteur {#creating-groups-on-author}

Op auteur, van globale navigatie

* Selecteer **[!UICONTROL Communities > Sites]**
* Selecteren **[!UICONTROL engage folder]** om te openen
* Selecteer de kaart voor de **[!UICONTROL Getting Started Tutorial]** Engelse site
   * De kaartafbeelding selecteren
   * Geen ** pictogram selecteren

Het resultaat moet de console [van](groups.md)Groepen bereiken:

![chlimage_1-53](assets/chlimage_1-53.png)

De groepfunctie wordt weergegeven als een map waarin instanties van groepen worden gemaakt. Selecteer de map Groepen om deze te openen. De groep die bij publicatie wordt gemaakt, is zichtbaar.

![chlimage_1-54](assets/chlimage_1-54.png)

## Hoofdartgroep maken {#create-main-arts-group}

Deze groep kan worden gemaakt omdat de sitestructuur voor de verbinding een groepfunctie bevat. De configuratie van de functie in de `Reference Template` standaardinstellingen van de site staat de selectie van een ingeschakelde groepssjabloon toe. De voor deze nieuwe groep gekozen sjabloon is dus de `Reference Group`sjabloon.

Deze consoles lijken erg op de console van de Plaatsen van Gemeenschappen.

* Selecteer **[!UICONTROL Create Group]**
* `1 Community Group Template`:
   * Titel van communautaire groep: Kunst
   * Omschrijving van de communautaire groep: Een bovenliggende groep voor verschillende kunstgroepen.
   * Hoofdmap van communautaire groep: *standaard verlaten*
   * Aanvullende beschikbare talen voor communautaire groepen:gebruik het keuzemenu om de beschikbare talen voor groepen in de gemeenschap te selecteren. In het menu worden alle talen weergegeven waarin de bovenliggende communitysite is gemaakt. Gebruikers kunnen in deze ene stap uit deze talen kiezen om groepen te maken in meerdere landinstellingen. De zelfde groep wordt gecreeerd in veelvoudige gespecificeerde talen in de console van Groepen van de respectieve communautaire plaatsen.
   * Naam communautaire groep: kunst
   * Sjabloon: naar beneden halen om te selecteren `Reference Group`
   * Selecteer `Next`

      ![ouderwetse](assets/parenttonestedgroup.png)

Doorloop de andere deelvensters met deze instellingen:

* **2 Ontwerp**
   * U kunt het ontwerp wijzigen of standaard het ontwerp van de bovenliggende site instellen
   * Selecteer **[!UICONTROL Next]**
* **3 Instellingen**
   * **Moderatie**
      * Leeg laten (overerven van bovenliggende site)
   * **Lidmaatschap**
      * default gebruiken `Optional Membership`
   * **Miniatuur**
      * `optional`
   * Selecteer `Next`
* Selecteer **[!UICONTROL Create]**

### Groepen nesten binnen tekengroep {#nesting-groups-within-arts-group}

De `groups` map moet nu twee groepen bevatten (mogelijk moet u de pagina vernieuwen).

![createcommunitygroup](assets/createcommunitygroup.png)

#### Groep publiceren {#publish-group}

Voordat u groepen maakt die in de `arts`groep zijn genest, houdt u de muisaanwijzer boven de `arts` kaart en selecteert u het publicatiepictogram om deze te publiceren.

![chlimage_1-55](assets/chlimage_1-55.png)

Wacht op bevestiging dat de groep is gepubliceerd.

![chlimage_1-56](assets/chlimage_1-56.png)

De `arts` groep moet ook een `groups` map bevatten, maar een map die leeg is en waarin nieuwe groepen kunnen worden gemaakt. Navigeer naar de map met kunstgroepen en maak drie geneste groepen, elk met een andere lidmaatschapsinstelling:

1. Zichtbaar
   * Titel: `Visual Arts`
   * Naam: `visual`
   * Sjabloonmodel: `Reference Group`
   * Lidmaatschap: Selecteer `Optional Membership`een openbare groep die voor alle leden open is
1. Controleur
   * Titel: `Auditory Arts`
   * Naam: `auditory`
   * Sjabloonmodel: `Reference Group`
   * Lidmaatschap: Selecteer `Required Membership`een open groep, beschikbaar voor leden om zich bij te voegen

1. Historie

   * Titel: `Art History`
   * Naam: `history`
   * Sjabloonmodel: `Reference Group`
   * Lidmaatschap: Selecteer `Restricted Membership`Een geheime groep, die alleen zichtbaar is voor uitgenodigde leden als voorbeeld, nodigen 
[demo-gebruiker](tutorials.md#demo-users) `emily.andrews@mailinator.com`

Vernieuw de pagina om alle drie geneste groepen (subgemeenschappen) weer te geven.

Indien nodig, om aan de genestelde groepen van de console van de Plaatsen van Gemeenschappen te navigeren:

* Selecteer **[!UICONTROL engage folder]**
* Kaart **[!UICONTROL Getting Started Tutorial]** selecteren
* Selecteer **[!UICONTROL Groups folder]**
* Selecteer **[!UICONTROL arts card]**
* Selecteer **[!UICONTROL Groups folder]**

![chlimage_1-57](assets/chlimage_1-57.png)

## Groepen publiceren {#publishing-groups}

![chlimage_1-58](assets/chlimage_1-58.png)

Na publicatie van de hoofdsite van de community is het nodig om

* Elke groep afzonderlijk publiceren
   * Wachten op bevestiging van publicatie van de groep
* bovenliggende groep publiceren voordat groepen worden gepubliceerd die zijn genest binnen
   * Alle groepen moeten van boven naar beneden worden gepubliceerd.

![chlimage_1-59](assets/chlimage_1-59.png)

## Ervaring met publiceren {#experience-on-publish}

Het is mogelijk om de verschillende groepen te ervaren wanneer u zich aanmeldt, bijvoorbeeld met de [demo-gebruikers](tutorials.md#demo-users) die worden gebruikt voor

* Groepslid illustratie/geschiedenis: emily.andrews@mailinator.com/password
   * De beperkte (geheime) groep, kunst/geschiedenis, zal zichtbaar zijn
   * Kan optionele (openbare) groepen zien
   * Groepen met beperkingen (open groepen) kunnen worden samengevoegd
* Groepsbeheer: aaron.mcdonald@mailinator.com/password
   * Kan optionele (openbare) groepen zien
   * kan zich bij beperkte (open) groepen aansluiten
   * Zal geen beperkte (geheime) groepen zien

Toegang tot de [leden en de Groepen van Gemeenschappen consoles](members.md) op auteur om andere gebruikers aan diverse lidgroepen toe te voegen die aan de communautaire groepen beantwoorden.
