---
title: Rapportenconsole
seo-title: Reports Console
description: Leer hoe u rapporten kunt openen
seo-description: Learn how to access reports
uuid: 580f5eb8-24b2-4404-90d4-81f7108d1ee6
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 0042893e-3d2c-469e-8759-404be16e7436
role: Admin
exl-id: 766711ea-f3d3-49ab-8346-4e4477c261bd
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 0%

---

# Rapportenconsole {#reports-console}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Overzicht {#overview}

Voor AEM Communities zijn er diverse rapporten die op verschillende manieren toegankelijk zijn vanuit de auteursomgeving.

In het algemeen zijn de verschillende verslagen:

* [Toewijzingsrapport](#assignments-report) - voor een [enablement community](overview.md#enablement-community), biedt een overzicht van de vorderingen van studenten met hun taken, inclusief een bijbehorende score bij de implementatie van de SCORM-standaard
* [Rapport Weergaven](#views-report) - geeft een overzicht van de opvattingen van leden van de gemeenschap en sitebezoekers over de inhoud van een site van de gemeenschap
* [Post Report](#posts-report) - geeft een overzicht van de verschillende soorten posten van de leden van de gemeenschap op elke site van de gemeenschap

Wanneer [Adobe Analytics is ingeschakeld](sites-console.md#analytics), bevatten rapporten het aantal weergaven, afspelen, opmerkingen en beoordelingen voor elke bron van activering in de loop van de tijd

Rapporten in tabelvorm kunnen worden geëxporteerd in de .csv-indeling voor verdere verwerking.

## Consoles rapporteren {#reporting-consoles}

### Verslagen voor communautaire sites {#reports-for-community-sites}

* Vanuit globale navigatie: **[!UICONTROL Navigation > Communities > Reports]**
* Kiezen uit
   * **[!UICONTROL Assignments Report]**
      * Genereer een rapport voor geselecteerde communautaire Plaats, Gebruiker of Groep, en Toewijzing
   * **[!UICONTROL Posts Report]**
      * Genereer een rapport voor een geselecteerde Community Site, Type inhoud en Tijdsperiode
   * **[!UICONTROL Views Report]**
      * Genereer een rapport voor een geselecteerde Community Site, Type inhoud en Tijdsperiode
         ![chlimage_1-156](assets/chlimage_1-156.png)

### Rapporten voor Middelen Enablement en het Leren Wegen {#reports-for-enablement-resources-and-learning-paths}

* Vanuit globale navigatie: **[!UICONTROL Navigation > Communities > Resources]**
* Een bestaande community-site voor inschakelen selecteren
   * Selecteren **[!UICONTROL Report]** pictogram om rapporten te genereren die alle bronnen voor activering bestrijken
   * Een leerpad voor inschakelen selecteren
   * Selecteren **[!UICONTROL Report]** pictogram om rapporten te genereren voor
      * De meegeleverde middelen voor activering
      * De leerlingen die zijn toegewezen aan het leerpad
* Deze verslagen bevatten:
   * Tabelgegevens, downloadbaar als CSV
      * Student identificeren
      * Hun status
      * Of toegewezen of benaderd via catalogus
      * Aantal gemaakte opmerkingen
      * Sterrenclassificatie gegeven

Zie voor meer informatie [Sectie Rapporten](resources.md#report) van de console van Middelen.

## Toewijzingsrapport {#assignments-report}

Met de toewijzingsconsole kunnen rapporten worden gefilterd door de communitysite, gebruikers of groepen en toewijzing in te schakelen.

Het verslag bevat informatie over de voortgang van de activiteiten en eventuele opmerkingen of beoordelingen.

![chlimage_1-157](assets/chlimage_1-157.png)

Selecteer de criteria voor het rapport:

* **[!UICONTROL Site]**
Een community-site voor activering selecteren
* **[!UICONTROL User or Group]**
   * Selecteer Gebruiker om een rapport voor één student te genereren
   * Selecteer Groep om een rapport voor een groep studenten te produceren De tunnelservice zal tot leden en lidgroepen van het publicatiemilieu toegang hebben
* **[!UICONTROL Assignment]**
Maak een keuze uit de instellingsbronnen die aan de geselecteerde studenten zijn toegewezen

Selecteren **[!UICONTROL Generate]** om het rapport op te stellen:

![chlimage_1-158](assets/chlimage_1-158.png)

## Rapport Weergaven {#views-report}

Met de weergaveconsole kunnen rapporten gedurende een bepaalde periode worden gegenereerd op paginaweergaven door een of meer algemene functies.

![chlimage_1-159](assets/chlimage_1-159.png)

Selecteer de criteria voor het rapport:

* **[!UICONTROL Site]**
Een communitysite selecteren
* **[!UICONTROL Content Type]**
Kan Alle inhoud kiezen of een van de functies op de site selecteren
* Tijdkader Selecteer een van de volgende opties:
   * Laatste 7 dagen
   * Laatste 30 dagen
   * Laatste 90 dagen
   * Vorig jaar

Selecteren **[!UICONTROL Generate]** om het rapport op te stellen:

![chlimage_1-160](assets/chlimage_1-160.png)

## Post Report {#posts-report}

Met de Post-console kunnen rapporten gedurende een bepaalde periode worden gegenereerd op het aantal posten voor een of meer algemene functies.

![chlimage_1-161](assets/chlimage_1-161.png)

Selecteer de criteria voor het rapport:

* **[!UICONTROL Site]**
Een communitysite selecteren
* **[!UICONTROL Content Type]**
Kan Alle inhoud kiezen of een van de functies op de site selecteren
* Tijdkader Selecteer een van de volgende opties:
   * Laatste 7 dagen
   * Laatste 30 dagen
   * Laatste 90 dagen
   * Vorig jaar

Selecteren **[!UICONTROL Generate]** om het rapport op te stellen:

![chlimage_1-162](assets/chlimage_1-162.png)

## Problemen oplossen {#troubleshooting}

### Geen community-sites vermeld {#no-community-sites-listed}

Als er geen community-sites worden vermeld, moet u ervoor zorgen dat Adobe Analytics is ingeschakeld voor een site. Als u rapporten over toewijzingen kiest, moet u ervoor zorgen dat de toewijzingsfunctie zich in de structuur van de gemeenschapssite bevindt.
