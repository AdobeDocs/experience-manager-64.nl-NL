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

## Info Badges {#about-badges}

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

## Badge maken {#create-badge}

Een badge wordt gemaakt door het uploaden van een voldoende kleine afbeelding (72 dpi met een hoogte tussen 26 en 32 pixels) en het opgeven van een naam. De badge-afbeelding wordt opgeslagen in de opslagplaats in `/etc/community/badging/images` en wordt automatisch gerepliceerd naar de publicatieomgeving.

Als het publicatiemilieu een landbouwbedrijf van uitgevers is, is het noodzakelijk om [gebruikerssynchronisatie](sync.md)te vormen.

![chlimage_1-243](assets/chlimage_1-243.png)

* **[!UICONTROL Upload Image]**

   (*Vereist*) Een badge-afbeelding met een aanbevolen grootte van 32 x 32 pixels bij 72 dpi in de JPEG- of PNG-indeling.

* **[!UICONTROL Name]**

   (*Vereist*) De badge name. Dit is de standaardnaam `Display Name` en de naam van het knooppunt in de repository. Als het knooppunt geen geldige naam voor een opslagplaats `Name` is, wordt het gewijzigd.

* **[!UICONTROL Display Name]**

   (*Optioneel*) De naam die voor de badge in de gebruikersinterface moet worden weergegeven. De standaardinstelling is de ongewijzigde tekst die voor de `Name`code wordt ingevoerd.

* **[!UICONTROL Description]**

   (*Optioneel*) Een beschrijving van de badge.

## Additional Information {#additional-information}

Zie [Scores en Badges](implementing-scoring.md)voor meer informatie over het instellen van regels voor scoring en badges.

Zie [Ledenconsole](members.md)voor informatie over het beheren van badges voor leden.
