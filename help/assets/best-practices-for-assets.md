---
title: Aanbevolen procedures voor het beheer van AEM
description: Identificeer en onderschrijf de beste praktijken die systeemstabiliteit en prestaties onder lading verbeteren, afhankelijk van de plaatsing van AEM Assets en eigenschappen die worden gebruikt om activa op te nemen en te verwerken.
contentOwner: AG
feature: Beheer van bedrijfsmiddelen
role: Architect,beheerder
translation-type: tm+mt
source-git-commit: 29e3cd92d6c7a4917d7ee2aa8d9963aa16581633
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 0%

---


# Aanbevolen procedures voor AEM Assets {#best-practices-for-assets}

Adobe Experience Manager (AEM) Assets is een cruciaal onderdeel van het aanbieden van hoogwaardige digitale marketingervaringen die bijdragen tot het bereiken van zakelijke doelen door de snelheid van uw inhoud te verhogen. Als u met een groot aantal middelen in AEM Assets werkt of regelmatig/periodiek een groot aantal middelen uploadt, waaronder video&#39;s en dynamische media, is het optimaliseren van uw ervaring voor het beheer van digitale middelen van essentieel belang voor de efficiëntie van het systeem.

Afhankelijk van hoe u AEM Assets voor uw organisatie hebt gepositioneerd en de functies die u gebruikt rond het opnemen van elementen, het genereren van vertoningen en het ophalen van metagegevens, het identificeren en volgen van de beste praktijken op verschillende gebieden verbetert de systeemstabiliteit en de prestaties onder belasting aanzienlijk.

Na het herzien van de volgende gidsen, zult u de kennis en de hulpmiddelen hebben om een systeem van het ondernemingsmiddelenbeheer te bouwen en te beheren dat aan uw behoeften voldoet.

* [Richting voor afstemmen van middelenprestaties ](performance-tuning-guidelines.md)
Bevat een reeks aanbevolen werkwijzen die op elk moment in uw implementatie kunnen worden gevolgd, zelfs nadat u live gaat, om ervoor te zorgen dat u optimaal profiteert van uw systeem.
* [Middelen op ](assets-sizing-guide.md)
grootteBij het opstellen van schattingen voor een implementatie van Elementen is het belangrijk ervoor te zorgen dat er voldoende bronnen beschikbaar zijn op het gebied van opslag van activa, CPU, geheugen, IO en netwerkdoorvoer. Bij het vergroten van het formaat van veel van deze items moet u weten hoeveel elementen in het systeem worden geladen. Deze gids omvat beste praktijken die helpen efficiënte metriek bepalen voor het schatten van de infrastructuur en de middelen die voor de plaatsing van AEM Assets evenals een rangschikkend hulpmiddel worden vereist.
* [Migratiehandleiding voor middelenAls u middelen van uw oude systeem naar AEM Assets wilt migreren, moet u een aantal stappen nemen om het migratieproces te stroomlijnen. ](assets-migration-guide.md)
De migratiehandleiding bevat tips en trucs voor het uitvoeren van taken om de middelen op een fasige manier in AEM te brengen. Dit omvat het toepassen van metagegevens, het genereren van uitvoeringen en het activeren van de elementen om de implementatie te publiceren.
* [De ](assets-network-considerations.md)
overwegingen van het middelennetwerkWanneer het behandelen van AEM plaatsing, is het begrip van de netwerktopologie belangrijk om netwerkprestaties te begrijpen, chokepoints te identificeren, en de verwachte gebruikerservaring te beschrijven. Het document van de Overwegingen van het Netwerk van Activa bespreekt netwerkoverwegingen wanneer het ontwerpen van uw plaatsing van AEM Activa.
* [De ](assets-monitoring-best-practices.md)
gids van de Controle van activaNadat uw AEM plaatsing wordt opgesteld, zou u bepaalde taken en het systeem in het algemeen moeten controleren om systeemintegriteit en efficiency van verrichtingen te verzekeren. De gids van de Controle omvat beste praktijken voor het controleren van diverse aspecten van uw systeem.
* (Afgekeurd) [Elementen die hulplijn ontladen](assets-offloading-best-practices.md)
Het verwerken van grote bestanden en het uitvoeren van workflows in AEM Assets kan aanzienlijke CPU-, geheugen- en I/O-bronnen in beslag nemen. Als u deze taken verschuift, kunnen de overhead van de CPU, het geheugen en de IO worden verminderd. De gids voor het ontladen van bedrijfsmiddelen bevat aanbevolen gebruiksgevallen en aanbevolen procedures voor het offloaden van bedrijfsmiddelen.
* [AEM best ](https://helpx.adobe.com/experience-manager/desktop-app/aem-desktop-app-best-practices.html)
practices voor bureaubladtoepassingenAEM-bureaubladtoepassing koppelt uw DAM-oplossing (Digital Asset Management) aan uw bureaublad, zodat u de bestanden die beschikbaar zijn in de AEM webinterface rechtstreeks op uw bureaublad kunt openen. AEM de gebruiksvriendelijke workflow van de bureaubladtoepassing is ingeschakeld met de technologie voor netwerkdeling die desktopbesturingssystemen bieden. In deze handleiding worden de belangrijkste mogelijkheden en het aanbevolen gebruik van AEM bureaubladtoepassing uitgelegd.
* [Aanbevolen ](aem-cc-integration-best-practices.md)
werkwijzen voor AEM- en Creative Cloud-integratieU kunt uw AEM-implementatie op meerdere manieren integreren met Creative Cloud. Door de best practices te volgen om uw workflows voor integratie en overdracht van bedrijfsmiddelen te stroomlijnen, kunt u maximale efficiëntie bereiken. Deze handleiding bevat tips en trucs voor de integratie van AEM Assets met Adobe Creative Cloud.
* (Verouderd) [AEM naar map Creative Cloud om aanbevolen werkwijzen te delen](aem-cc-folder-sharing-best-practices.md)
U kunt AEM zodanig configureren dat gebruikers in DAM mappen kunnen delen met gebruikers van het type Creative Cloud (CC), zodat ze beschikbaar zijn als gedeelde mappen in de service Creative Cloud Assets. Deze functie kan worden gebruikt voor het uitwisselen van bestanden tussen creatieve teams en DAM-gebruikers. In deze handleiding worden de aanbevolen werkwijzen uitgelegd voor het gebruik van de functie voor het delen van mappen via AEM naar Creative Cloud.
