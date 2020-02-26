---
title: Eén zone naar meerdere zones
seo-title: Eén zone voor multizone-overname
description: 'Volg deze pagina om over de Enige Zone aan Multizone Overname in een project van het Scherm te leren AEM.  '
seo-description: 'Volg deze pagina om over de Enige Zone aan Multizone Overname in een project van het Scherm te leren AEM.    '
translation-type: tm+mt
source-git-commit: 4b2c0f3a1ef8759eb3182b93cffa09c4afc23b6a

---


# Eén zone naar meerdere zones {#single-zoneto-multizone}

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

1. Maak een AEM-schermproject met de naam **ZonesDemo**, zoals hieronder wordt weergegeven.

   >[!NOTE]
   >
   >Meer over het creëren van en het leiden van projecten in de Schermen van AEM, verwijs naar het [Creëren van een Project](/help/screens/creating-a-screens-project.md).

   ![screen_shot_2019-02-21at35809pm](assets/SZtoMZ1.png)

1. **Een sequentiekanaal maken met één afbeelding**

   1. Selecteer de map **Kanalen** en klik op **Maken** in de actiebalk om de wizard te openen en een kanaal te maken.
   1. Selecteer Kanaal **van de** Opeenvolging van de tovenaar en creeer het kanaal genoemd als **FullScreenOne**.

      ![screen_shot_2019-02-21at35932pm](assets/SZtoMZ2.png)
   1. Selecteer het kanaal en klik op **Bewerken** op de actiebalk om de editor te openen en sleep een afbeelding naar dat kanaal, zoals hieronder wordt weergegeven.
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

## Het overnamekanaal instellen op de overgang van één zone naar meerdere zones {#takeover-channel-setup}

1. **Het Single Zone-kanaal bewerken voor overname van meerdere zones**

   1. Selecteer het kanaal (**FullScreenOne)** dat u in stap 1 hebt gemaakt.
   1. Klik op **Bewerken** op de actiebalk om de editor te openen. Sleep twee kanaalcomponenten en één videocomponent naar de editor.
   ![screen_shot_2019-02-21at40516pm](assets/SZtoMZ10.png)

1. **De componenten vullen die aan het kanaal FullScreenOne zijn toegevoegd**

   1. Selecteer de eerste kanaalcomponent van de redacteur van **FullScreenOne** en de klik **vormt** om aan het kanaal te richten dat in voorafgaande stappen wordt gecreeerd. Voeg het pad naar het kanaal in **Kanaalpad** toe aan zowel de kanaalcomponenten als sleep de video naar de videocomponent, zoals hieronder wordt weergegeven.
   ![screen_shot_2019-02-21at40516pm](assets/SZ_MZvideo1.gif)

1. **De tijdsduur instellen voor de kanalen tijdens de overgang**

   >[!NOTE]
   >
   >De elementen worden standaard na elke 8 seconden overgedragen, maar als u de elementen na een bepaalde tijdsduur wilt laten overgaan, volgt u de onderstaande stap.

   1. Selecteer de tweede kanaalcomponent van de redacteur van **FullScreenOne** en klik **Montages** om de tijdduur voor dit kanaal te vormen. Stel op dezelfde manier de tijdsduur in voor kanaal twee, zoals hieronder wordt weergegeven.
In dit voorbeeld wordt de tijd ingesteld op 3 seconden.
   ![screen_shot_2019-02-21at40516pm](assets/SZ_MZvideo2.gif)

## Voorvertoning van het resultaat {#previewing-result}

U kunt op **Voorproef** van de redacteur klikken en controleren hoe de activa van enige streek aan multizone zullen overgaan.

![](assets/SZ_MZvideo3.gif)
