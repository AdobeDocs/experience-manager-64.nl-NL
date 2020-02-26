---
title: Activering op kanaalniveau - Afspelen van één gebeurtenis
seo-title: Activering op kanaalniveau - Afspelen van één gebeurtenis
description: Volg deze handleiding om de activering op kanaalniveau te begrijpen met behulp van het afspelen van één gebeurtenis.
seo-description: Volg deze handleiding om de activering op kanaalniveau te begrijpen met behulp van het afspelen van één gebeurtenis.
uuid: 87230344-5f9a-42a4-a7a8-ae4203303612
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.4/SCREENS
topic-tags: authoring
content-type: reference
discoiquuid: c28fd669-f23e-4d53-bec1-a2911274567d
noindex: true
translation-type: tm+mt
source-git-commit: 3addef2141ebb831f8677d011d68faf88e648dc2

---


# Activering op kanaalniveau - Afspelen van één gebeurtenis{#channel-level-activation-single-event-playback}

Het gebruiken van de Activering van het Niveau van het Kanaal behandelt de volgende onderwerpen:

* **[Overzicht](/help/screens/channel-level-activation.md#overview)**
* **[Activering op kanaalniveau gebruiken als één gebeurtenis afspelen](/help/screens/channel-level-activation.md#using-channel-level-activation)**

   * **[Vereisten](/help/screens/channel-level-activation.md#prerequisites)**
   * **[Implementatie](/help/screens/channel-level-activation.md#implementation)**

* **[De resultaten bekijken](/help/screens/channel-level-activation.md#viewing-the-results)**

## Overzicht {#overview}

***De Activering*** van het Niveau van het kanaal staat de kanalen toe om na een bepaald geplaatst programma te schakelen. Het enige gebeurteniskanaal vervangt het hoofdkanaal na een ingesteld programma en speelt gedurende een bepaalde tijd af, totdat de inhoud van het hoofdkanaal opnieuw wordt afgespeeld.

In het volgende voorbeeld wordt een oplossing geboden waarbij de nadruk ligt op de volgende sleuteltermen:

* een ***hoofdvolgordekanaal*** voor de algemene reeks
* één ***gebeurteniskanaal*** dat slechts één keer bij een ingestelde tijd wordt uitgevoerd
* een ***ingesteld schema en een ingestelde prioriteit*** voor de enige afspeelgebeurtenis die plaatsvindt binnen het hoofdkanaal van de reeks

## Activering op kanaalniveau gebruiken {#using-channel-level-activation}

In de volgende sectie wordt uitgelegd hoe u één gebeurtenis afspeelt in een kanaal voor een AEM-rasterproject.

### Vereisten {#prerequisites}

Voordat u begint met het implementeren van deze functionaliteit, moet u ervoor zorgen dat u aan de volgende voorwaarden kunt voldoen om activering op kanaalniveau te kunnen starten:

* Een AEM-schermproject maken (in dit voorbeeld activering **** kanaalniveau)

* Een kanaal maken als **MainAdChannel** onder de map **Kanalen**

* Een ander kanaal maken als **gerichtSinglePlay** onder de map **Kanalen**

* Relevante elementen aan beide kanalen toevoegen

In de volgende afbeelding ziet u het **Kanaalniveauactiveringsproject** met **MainAdChannel** en de **doelkanalen SinglePlay** in de map **Kanalen** .

![screen_shot_2018-11-27at104500am](assets/screen_shot_2018-11-27at104500am.png)

>[!NOTE]
>
>Raadpleeg de volgende bronnen voor meer informatie over het maken van een project en het maken van een volgnummer:
>
>* [Projecten maken en beheren](/help/screens/creating-a-screens-project.md)
   >
   >
* [Een kanaal beheren](/help/screens/managing-channels.md)
>



### Implementatie {#implementation}

Het uitvoeren van de Activering van het Niveau van het Kanaal in een project van het Scherm AEM omvat drie belangrijke taken:

1. **Projecttaxonomie instellen, waaronder Kanalen, Locaties en Weergaven**
1. **Kanalen toewijzen aan weergave**
1. **Een planning en prioriteit instellen**

Voer de volgende stappen uit om de functionaliteit te implementeren:

1. **Een locatie maken**

   Navigeer naar de map **Locations** in uw AEM Screens-project en maak een locatie als **Regio**.

   ![screen_shot_2018-11-27at112112am](assets/screen_shot_2018-11-27at112112am.png)

   >[!NOTE]
   >
   >Zie Locaties **[maken en beheren voor meer informatie over het maken van een locatie](/help/screens/managing-locations.md)**.

1. **Weergave onder locatie maken**

   1. Navigeer naar Activering **op** Kanaalniveau > **Locaties** > **Regio**.
   1. Selecteer **Gebied** en klik op **+ Maken** in de actiebalk.
   1. Selecteer **Weergeven** in de wizard en maak een weergave met de naam **RegioDisplay.**
   ![screen_shot_2018-11-27at112216am](assets/screen_shot_2018-11-27at112216am.png)

1. **Kanalen toewijzen aan weergave**

   Voor **MainAdChannel:**

   1. Navigeer naar Activering **op** Kanaalniveau > **Locaties** > **Regio** > **Weergave** Gebied en klik op Kanaal **** toewijzen op de actiebalk.
   1. **Het dialoogvenster Kanaaltoewijzing** wordt geopend.
   1. Referentiekanaal **** selecteren.. per pad.
   1. Selecteer het **Kanaalpad** als **Kanaalniveauactivering** —> ***Kanalen*** —> ***MainAdChannel***.
   1. De rol **van het** Kanaal wordt bevolkt als **mainadchannel**.
   1. Selecteer **Prioriteit** als **1**.
   1. Selecteer de **Ondersteunde gebeurtenissen** als **Eerste Laden** en **Niet actief scherm**.
   1. Click **Save**.
   ![screen_shot_2018-11-27at124626pm](assets/screen_shot_2018-11-27at124626pm.png)

   >[!NOTE]
   >
   >U kunt ook kanaal toewijzen vanaf het weergavedashboard door naar Activering **** kanaalniveau te navigeren —> **Locaties** —> **Regio** —> **Weergave** Gebied te klikken en op **Dashboard** op de actiebalk te klikken. Klik op **+ Kanaal** toewijzen in het deelvenster **TOEGEWEZEN KANALEN EN SCHADUWEN** .

   Wijs op dezelfde manier kanaal **TargetedSinglePlay** toe voor display**:

   1. Navigeer naar Activering **** Kanaalniveau —> **Locaties** —> **Regio** —> **Weergave** Gebied en klik op Kanaal **** toewijzen op de actiebalk.
   1. **Het dialoogvenster Kanaaltoewijzing** wordt geopend.
   1. Referentiekanaal **** selecteren.. per pad.
   1. Selecteer het **Kanaalpad** als **Kanaalniveauactivering*** —> ***Kanalen*** —> ***Gericht SinglePlay***.*
   1. De rol **van het** Kanaal wordt bevolkt als **gericht singleplay**.
   1. Stel de **prioriteit** in op **2**.
   1. Selecteer de **Ondersteunde gebeurtenissen** als **Eerste belasting**, **Niet-actief scherm** en Timer *****, *zoals in de onderstaande afbeelding wordt getoond.
   1. Kies de datum in **actief van** 27 november 2018 11:59 en in **actief tot** 28 november 2018 12:05 uur.**
   1. Click **Save**.*
*
   >[!CAUTION]
   U moet de prioriteit voor **gerichtSinglePlay** kanaal hoger dan het **MainAdSegment** kanaal plaatsen.

   ![screen_shot_2018-11-27at31206pm](assets/screen_shot_2018-11-27at31206pm.png)

   >[!NOTE]
   Als u dezelfde dag wilt kiezen, moet u de volgende dag selecteren en de datum handmatig op dezelfde dag maar voor een later tijdstip bewerken. Hierdoor kan de gebruiker geen datum uit het verleden selecteren. Raadpleeg het onderstaande voorbeeld:

   ![new1](assets/new1.gif)

## De resultaten bekijken {#viewing-the-results}

Nadat u de instellingen voor kanalen hebt ingesteld en de weergave is voltooid, start u de AEM Screens-speler om de inhoud weer te geven.

De speler geeft de inhoud van **MainAdChannel** weer en precies om 23:59 uur (zoals ingesteld in het schema), geeft het **GerichtSinglePlay** -kanaal de inhoud weer tot 12:05 uur &#39;s avonds en dan wordt het afspelen van de inhoud van het **MainAdChannel** hervat.

>[!NOTE]
Raadpleeg de volgende bronnen voor meer informatie over AEM Screen Player:
* [**AEM-schermPlayer downloadt **](https://download.macromedia.com/screens/)
* [**Werken met AEM Screens Player **](/help/screens/working-with-screens-player.md)



