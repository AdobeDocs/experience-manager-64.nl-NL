---
title: Badges-console
seo-title: Badges-console
description: Met de console Gemeenschapsbadges kunt u aangepaste badges toevoegen die kunnen worden weergegeven voor leden die hun geld hebben verdiend (toegekend) of die een specifieke rol in de gemeenschap hebben (toegewezen)
seo-description: Met de console Gemeenschapsbadges kunt u aangepaste badges toevoegen die kunnen worden weergegeven voor leden die hun geld hebben verdiend (toegekend) of die een specifieke rol in de gemeenschap hebben (toegewezen)
uuid: 9eeba240-f0d4-4937-baba-8bac0e0b2a36
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 4194278f-5127-4105-b181-60961c7a1def
translation-type: tm+mt
source-git-commit: 59d40b5bddc42a4ac057ef600243f396aefc926b
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 0%

---


# Badges-console {#badges-console}

## Informatie over Badges {#about-badges}

De console van de Badges van de Gemeenschappen verstrekt de capaciteit om douanebadges toe te voegen die voor een lid kunnen worden getoond wanneer verdiend (toegekend) of wanneer zij een specifieke rol in de gemeenschap (toegewezen) nemen.

### Zichtbaarheid badge {#badge-visibility}

Badges die een lid van de gemeenschap verdient of toegewezen krijgt, worden samen met zijn naam en avatar op de volgende locaties weergegeven:

* Profielen
* [Forums](forum.md)
* [QnA](working-with-qna.md)
* [Leaderboards](enabling-leaderboard.md)
* [Ideatie](ideation-feature.md)

In de auteursomgeving, om de console van Badges te bereiken

* Vanuit globale navigatie: **[!UICONTROL Tools > Communities > Badges]**

Op deze console worden de badges weergegeven die momenteel beschikbaar zijn en waaruit nieuwe badges kunnen worden toegevoegd.

![chlimage_1-242](assets/chlimage_1-242.png)

## Badge {#create-badge} maken

Een badge wordt gemaakt door het uploaden van een voldoende kleine afbeelding (72 dpi met een hoogte tussen 26 en 32 pixels) en het opgeven van een naam. De badge-afbeelding wordt opgeslagen in de opslagplaats op `/etc/community/badging/images` en wordt automatisch gerepliceerd naar de publicatieomgeving.

Als de publicatieomgeving een bedrijf van uitgevers is, is het nodig om [user sync](sync.md) te configureren.

![chlimage_1-243](assets/chlimage_1-243.png)

* **[!UICONTROL Upload Image]**

   (*Required*) Een afbeelding met een badge met een aanbevolen grootte van 32 x 32 pixels bij 72 dpi in JPEG- of PNG-indeling.

* **[!UICONTROL Name]**

   (*Required*) De merknaam. Het is de standaard `Display Name` evenals de naam van de repository node. Als `Name` geen geldige naam voor een opslagplaats is, wordt deze gewijzigd.

* **[!UICONTROL Display Name]**

   (*Optioneel*) De naam die moet worden weergegeven voor de badge in de gebruikersinterface. Standaard is de ongewijzigde tekst die voor `Name` wordt ingevoerd.

* **[!UICONTROL Description]**

   (*Optioneel*) Een beschrijving voor de badge.

## Aanvullende informatie {#additional-information}

Zie [Scores en Badges](implementing-scoring.md) voor meer informatie over het instellen van regels voor scoring en badging.

Zie [Ledenconsole](members.md) voor het beheren van badges voor leden.
