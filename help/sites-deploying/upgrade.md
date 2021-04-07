---
title: Upgrade naar AEM 6.4
seo-title: Upgrade naar AEM 6.4
description: Leer meer over de basisbeginselen van het upgraden van een oudere AEM naar AEM 6.4.
seo-description: Leer meer over de basisbeginselen van het upgraden van een oudere AEM naar AEM 6.4.
uuid: aa878528-5161-4df3-9fed-cc779fb6bdbe
contentOwner: sarchiz
topic-tags: upgrading
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
discoiquuid: 81ceb91d-039e-45f0-9b0c-b8233901dea8
targetaudience: target-audience upgrader
feature: Bijwerken
exl-id: 791da16c-bf2c-47a9-86a4-0a601a1b017e
translation-type: tm+mt
source-git-commit: bd94d3949f0117aa3e1c9f0e84f7293a5d6b03b4
workflow-type: tm+mt
source-wordcount: '716'
ht-degree: 0%

---

# Bijwerken naar AEM 6.4{#upgrading-to-aem}

In deze sectie gaat het om het upgraden van een AEM naar AEM 6.4:

* [Uw upgrade plannen](/help/sites-deploying/upgrade-planning.md)
* [De complexiteit van upgrades beoordelen met patroondetector](/help/sites-deploying/pattern-detector.md)
* [Achterwaartse compatibiliteit in AEM 6.4](/help/sites-deploying/backward-compatibility.md)
* [Upgradeprocedure](/help/sites-deploying/upgrade-procedure.md)
* [Code en aanpassingen bijwerken](/help/sites-deploying/upgrading-code-and-customizations.md)
* [Onderhoudstaken vóór upgrade](/help/sites-deploying/pre-upgrade-maintenance-tasks.md)
* [Een op locatie uitgevoerde upgrade uitvoeren](/help/sites-deploying/in-place-upgrade.md)
* [Controles en probleemoplossing na upgrade](/help/sites-deploying/post-upgrade-checks-and-troubleshooting.md)
* [Duurzame verbeteringen](/help/sites-deploying/sustainable-upgrades.md)
* [Lazy Content Migration](/help/sites-deploying/lazy-content-migration.md)
* [Herstructurering van de depositaris in AEM 6.4](/help/sites-deploying/repository-restructuring.md)

Om gemakkelijker te kunnen verwijzen naar de AEM gevallen die bij deze procedures betrokken zijn, worden in deze artikelen de volgende termen gebruikt:

* De *source* instantie is de AEM instantie waarvan u een upgrade uitvoert.
* De *target*-instantie is de instantie waarnaar u een upgrade uitvoert.

>[!NOTE]
>
>In het kader van de inspanningen om de betrouwbaarheid van upgrades te verbeteren, heeft AEM 6.4 een alomvattende herstructurering van de opslagplaats ondergaan. Zie [Herstructurering van de opslagplaats in AEM 6.4](/help/sites-deploying/repository-restructuring.md) voor meer informatie over hoe u zich kunt aanpassen aan de nieuwe structuur.

## Wat is er veranderd? {#what-has-changed}

Hieronder vindt u een aantal belangrijke wijzigingen in de laatste paar versies van AEM:

AEM 6.0 introduceerde de nieuwe opslagplaats voor jakobak. Persistentiemanagers zijn vervangen door [Micro Kernels](/help/sites-deploying/recommended-deploys.md). Vanaf versie 6.1 wordt CRX2 niet meer ondersteund. Een migratiehulpmiddel genoemd crx2oak moet worden in werking gesteld om CRX2 bewaarplaatsen van 5.6.1 instanties te migreren. Zie [Het CRX2OAK-migratiehulpmiddel gebruiken](/help/sites-deploying/using-crx2oak.md) voor meer informatie.

Als Asset Insights moet worden gebruikt en u een upgrade uitvoert van een versie die ouder is dan AEM 6.2, moeten middelen worden gemigreerd en id&#39;s worden gegenereerd via een JMX-boon. In onze interne tests werden 125.000 bedrijfsmiddelen op een TarMK-omgeving over een uur gemigreerd, maar de resultaten kunnen afwijken.

AEM 6.3 introduceerde een nieuw formaat voor `SegmentNodeStore`, dat de basis van de implementatie TarMK is. Als u een upgrade uitvoert van een versie die ouder is dan AEM 6.3, is hiervoor een migratie naar de opslagplaats vereist als onderdeel van de upgrade, waarbij systeemdowntime wordt gebruikt.

Adobe Engineering schat dit op ongeveer 20 minuten. Herindexering is niet nodig. Bovendien is er een nieuwe versie van het crx2oak-programma uitgebracht om te werken met de nieuwe repository-indeling.

**Deze migratie is niet vereist als een upgrade van AEM 6.3 naar AEM 6.4 wordt uitgevoerd.**

De onderhoudstaken vóór de upgrade zijn geoptimaliseerd ter ondersteuning van automatisering.

De gebruiksopties voor de opdrachtregel van het gereedschap crx2oak zijn gewijzigd en zijn nu automatiseringsvriendelijk en ondersteunen meer upgradepaden.

De controles na de upgrade zijn ook automatiseringsvriendelijk gemaakt.

De periodieke vuilinzameling van revisies en de inzameling van de gegevensopslag zijn nu routinematige onderhoudstaken die periodiek moeten worden uitgevoerd. Met de introductie van AEM 6.3 ondersteunt en raadt Adobe u aan om de revisie online op te schonen. Zie [Revision Cleanup](/help/sites-deploying/revision-cleanup.md) voor informatie over hoe u deze taken kunt configureren.

**AEM 6.4** introduceert het  [Detector van het Patroon ](/help/sites-deploying/pattern-detector.md) voor beoordeling van ingewikkeldheid van de verbetering aangezien u begint met het plannen voor de verbetering. 6.4 heeft ook een sterke nadruk op [achterwaartse verenigbaarheid](/help/sites-deploying/backward-compatibility.md) van eigenschappen. Tot slot worden de beste praktijken voor [duurzame verbeteringen](/help/sites-deploying/sustainable-upgrades.md) ook toegevoegd.

Zie de volledige releaseopmerkingen voor meer informatie over wat er in recente AEM is gewijzigd:

* [https://helpx.adobe.com/experience-manager/6-2/release-notes.html](https://helpx.adobe.com/experience-manager/6-2/release-notes.html)
* [https://helpx.adobe.com/experience-manager/6-3/release-notes.html](https://helpx.adobe.com/experience-manager/6-3/release-notes.html)
* [https://helpx.adobe.com/experience-manager/6-4/release-notes.html](https://helpx.adobe.com/experience-manager/6-4/release-notes.html)

## Overzicht van upgrade {#upgrade-overview}

Het upgraden van AEM is een proces dat uit meerdere stappen bestaat en soms meerdere maanden duurt. Het volgende overzicht is verstrekt als overzicht van wat inbegrepen is in een verbeteringsproject en de inhoud die in deze documentatie is omvat:

![screen_shot_2018-03-30at80708am](assets/screen_shot_2018-03-30at80708am.png)

## Upgradestroom met upgradeverbeteringen {#upgrade-overview-1}

In het onderstaande diagram wordt de algemene aanbevolen stroom gemarkeerd met de upgradeaanpak. Let op de verwijzing naar de nieuwe functies die we hebben geïntroduceerd. De upgrade moet beginnen met de patroondetector (zie [De upgradecomplexiteit met patroondetector](/help/sites-deploying/pattern-detector.md) evalueren). Hiermee kunt u het pad kiezen dat u wilt gebruiken voor compatibiliteit met AEM 6.4 op basis van de patronen in het gegenereerde rapport.

In 6.4 was er veel nadruk op het behoud van alle nieuwe functies achterwaarts compatibel, maar in gevallen waarin er nog enkele problemen met achterwaartse compatibiliteit zijn, kunt u in de compatibiliteitsmodus de ontwikkeling tijdelijk uitstellen om uw aangepaste code compatibel te houden met 6.4. Deze benadering helpt u ontwikkelingsinspanning onmiddellijk na de verbetering te vermijden (zie [Achterwaartse Verenigbaarheid in AEM 6.4](/help/sites-deploying/backward-compatibility.md)).

Tot slot, in uw 6.4 ontwikkelingscyclus, helpen de eigenschappen die onder Duurzame Verbeteringen worden geïntroduceerd (zie [Duurzame Verbeteringen](/help/sites-deploying/sustainable-upgrades.md)) u beste praktijken volgen om toekomstige verbeteringen nog efficiënter en naadloos te maken.

![6_4_upgrade_overviewflow-newpage3](assets/6_4_upgrade_overviewflowchart-newpage3.png)
