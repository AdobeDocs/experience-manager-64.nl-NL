---
title: Multi Zone to Single Zone Overnamelijn
seo-title: Multi Zone to Single Zone Overnamelijn
description: 'Volg deze pagina om meer te weten te komen over Multi Zone to Single Zone-overnamelijn in een AEM Screens-project.  '
seo-description: 'Multi Zone to Single Zone-overnamelijn in een AEM Screens-project.  '
translation-type: tm+mt
source-git-commit: 4b2c0f3a1ef8759eb3182b93cffa09c4afc23b6a

---


# Multi Zone to Single Zone Overnamelijn{#single-zoneto-multizone}

## Omschrijving hoofdletter gebruiken {#use-case-description}

In deze sectie wordt een gebruikscasevoorbeeld beschreven waarin wordt benadrukt hoe u een lay-outkanaal met meerdere zones instelt dat met een lay-outkanaal met één zone afwisselt. Elk kanaal heeft het rangschikken beeld/videoactiva.

### Voorwaarden {#preconditions}

Voordat u met dit gebruik begint, moet u controleren hoe u dit kunt doen:

* **[Kanalen maken en beheren](/help/screens/managing-channels.md)**
* **[Locaties maken en beheren](/help/screens/managing-locations.md)**
* **[Planningen maken en beheren](/help/screens/managing-schedules.md)**
* **[Apparaatregistratie](/help/screens/device-registration.md)**

### Primaire acteurs {#primary-actors}

Inhoudsauteurs

##  Het project instellen {#setting-up-the-project}

Voer de onderstaande stappen uit om een project in te stellen:

1. Maak een AEM-schermproject met de naam **OvernameopLoop**, zoals hieronder wordt weergegeven.

   >[!NOTE]
   >
   >Meer over het creëren van en het leiden van projecten in de Schermen van AEM, verwijs naar het [Creëren van een Project](/help/screens/creating-a-screens-project.md).

   ![](assets/takeover-loop1.png)

1. **Een gesplitst-schermkanaal maken**

   1. Selecteer de map **Kanalen** en klik op **Maken** in de actiebalk om de wizard te openen en een kanaal te maken.
   1. Selecteer **Linkerstaafsplitsing > Schermkanaal** in de wizard en maak het kanaal genaamd **MultiZoneLayout**.

      ![](assets/takeover-loop2.png)

   1. Selecteer het kanaal **MultiZoneLayout** en klik op **Bewerken** in de actiebalk om de editor te openen. Sleep de elementen naar elk van de zones. In het volgende voorbeeld worden een video, afbeelding en een tekstbanner in het kanaal getoond, zoals hieronder wordt getoond.
      ![screen_shot_2019-02-21at35932pm](assets/SZtoMZ3.png)

1. **Een 2X2-kanaal maken met vier afbeeldingen**

   1. Selecteer de map **Kanalen** en klik op **Maken** in de actiebalk om de wizard te openen en een kanaal te maken.

   1. Selecteer **2X2 Gesplitste sjabloon van het Kanaal** van het Scherm van de tovenaar en creeer het kanaal genoemd als **TwobyTwoChannel**.

      ![screen_shot_2019-02-21at35932pm](assets/SZtoMZ4.png)
   1. Selecteer het kanaal en klik op **Bewerken** op de actiebalk om de editor te openen en sleep vier afbeeldingen (vier verschillende zones) naar dat kanaal, zoals hieronder wordt weergegeven.
      ![screen_shot_2019-02-21at35932pm](assets/SZtoMZ5.png)

1. **Een 1X2 gesplitst schermkanaal maken met twee afbeeldingen**

   1. Selecteer de map **Kanalen** en klik op **Maken** in de actiebalk om de wizard te openen en een kanaal te maken.

   1. Selecteer **1X2 Gesplitste sjabloon van het Kanaal** van het Scherm van de tovenaar en creeer het kanaal genoemd als **OnebyTwoChannel**.

      ![screen_shot_2019-02-21at35932pm](assets/SZtoMZ6.png)
   1. Selecteer het kanaal en klik op **Bewerken** op de actiebalk om de editor te openen en sleep twee afbeeldingen (twee verschillende zones) naar dat kanaal, zoals hieronder wordt weergegeven.
      ![screen_shot_2019-02-21at35932pm](assets/SZtoMZ7.png)

1. **Een kanaal maken met één video op volledig scherm**

   1. Selecteer de map **Kanalen** en klik op **Maken** in de actiebalk om de wizard te openen en een kanaal te maken.

   1. Selecteer het malplaatje van het Kanaal **van de** Reeks van de tovenaar en creeer het kanaal genoemd als **FullScreensVideo**.

      ![screen_shot_2019-02-21at35932pm](assets/SZtoMZ8.png)
   1. Selecteer het kanaal en klik op **Bewerken** op de actiebalk om de editor te openen, sleep de videocomponent naar dat kanaal en voeg vervolgens de gewenste video toe, zoals hieronder wordt weergegeven.
      ![screen_shot_2019-02-21at35932pm](assets/SZtoMZ9.png)