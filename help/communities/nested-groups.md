---
title: Geneste groepen ontwerpen
seo-title: Authoring Nested Groups
description: Geneste groepen maken
seo-description: Create nested groups
uuid: b478454a-24c6-4e1c-a6e0-afeb1bc4992c
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: introduction
content-type: reference
discoiquuid: 955a1876-4882-4926-82e9-846bc8bb332c
exl-id: 87be7ffe-d937-4e85-8d90-5b7c356f0876
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 1%

---

# Geneste groepen ontwerpen {#authoring-nested-groups}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Groepen maken op auteur {#creating-groups-on-author}

Op auteur, van globale navigatie

* Selecteer **[!UICONTROL Communities > Sites]**
* Selecteren **[!UICONTROL engage folder]** openen
* Selecteer de kaart voor de **[!UICONTROL Getting Started Tutorial]**  Engelse site
   * De kaartafbeelding selecteren
   * Do *niet* een pictogram selecteren

Het resultaat is dat de [Groepsconsole](groups.md):

![chlimage_1-53](assets/chlimage_1-53.png)

De groepfunctie wordt weergegeven als een map waarin instanties van groepen worden gemaakt. Selecteer de map Groepen om deze te openen. De groep die bij publicatie wordt gemaakt, is zichtbaar.

![chlimage_1-54](assets/chlimage_1-54.png)

## Hoofdartgroep maken {#create-main-arts-group}

Deze groep kan worden gemaakt omdat de sitestructuur voor de verbinding een groepfunctie bevat. De configuratie van de functie in de site `Reference Template` staat standaard de selectie van een ingeschakelde groepssjabloon toe. De voor deze nieuwe groep gekozen sjabloon is dus `Reference Group`.

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

De `groups` De map moet nu twee groepen bevatten (mogelijk moet u de pagina vernieuwen).

![createcommunitygroup](assets/createcommunitygroup.png)

#### Groep publiceren {#publish-group}

Voordat u groepen maakt die zijn genest in het dialoogvenster `arts`groep, boven de `arts` en selecteer het publicatiepictogram om deze te publiceren.

![chlimage_1-55](assets/chlimage_1-55.png)

Wacht op bevestiging dat de groep is gepubliceerd.

![chlimage_1-56](assets/chlimage_1-56.png)

De `arts` groep moet ook een `groups` , maar een map die leeg is en waarin nieuwe groepen kunnen worden gemaakt. Navigeer naar de map met kunstgroepen en maak drie geneste groepen, elk met een andere lidmaatschapsinstelling:

1. Zichtbaar
   * Titel: `Visual Arts`
   * Naam: `visual`
   * Sjabloon: `Reference Group`
   * Lidmaatschap: selecteren `Optional Membership`
Een openbare groep die voor alle leden open is
1. Controleur
   * Titel: `Auditory Arts`
   * Naam: `auditory`
   * Sjabloon: `Reference Group`
   * Lidmaatschap: selecteren `Required Membership`
Een open groep, beschikbaar voor leden om zich bij te voegen

1. Historie

   * Titel: `Art History`
   * Naam: `history`
   * Sjabloon: `Reference Group`
   * Lidmaatschap: selecteren `Restricted Membership`
Een geheime groep, die alleen zichtbaar is voor uitgenodigde leden als voorbeeld, nodigt 
[demo-gebruiker](tutorials.md#demo-users) `emily.andrews@mailinator.com`

Vernieuw de pagina om alle drie geneste groepen (subgemeenschappen) weer te geven.

Indien nodig, om aan de genestelde groepen van de console van de Plaatsen van Gemeenschappen te navigeren:

* Selecteer **[!UICONTROL engage folder]**
* Selecteren **[!UICONTROL Getting Started Tutorial]** kaart
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

U kunt de verschillende groepen ervaren wanneer u zich aanmeldt, bijvoorbeeld met de [demo-gebruikers](tutorials.md#demo-users) gebruikt voor

* Groepslid illustratie/geschiedenis: emily.andrews@mailinator.com/password
   * De beperkte (geheime) groep, kunst/geschiedenis, zal zichtbaar zijn
   * Kan optionele (openbare) groepen zien
   * Groepen met beperkingen (open groepen) kunnen worden samengevoegd
* Groepsbeheer: aaron.mcdonald@mailinator.com/password
   * Kan optionele (openbare) groepen zien
   * kan zich bij beperkte (open) groepen aansluiten
   * Zal geen beperkte (geheime) groepen zien

Toegang tot de Gemeenschappen [Samenstellingen van leden en groepen](members.md) auteur om andere gebruikers toe te voegen aan verschillende lidgroepen die overeenkomen met de groepen van de gemeenschap.
