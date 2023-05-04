---
title: Aanbevolen procedures voor het beheer van AEM
description: Identificeer en houd zich aan de beste praktijken die systeemstabiliteit en prestaties onder lading verbeteren, afhankelijk van [!DNL Experience Manager] De plaatsing van activa en eigenschappen die worden gebruikt om activa in te voeren en te verwerken.
contentOwner: AG
feature: Asset Management
role: Architect,Admin
exl-id: e2ab924b-53cb-4011-8c0a-9e8e59dd2f16
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 0%

---

# Aanbevolen procedures voor [!DNL Experience Manager] Activa {#best-practices-for-assets}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Adobe Experience Manager Assets is een cruciaal onderdeel van het aanbieden van hoogwaardige digitale marketingervaringen die bijdragen tot het bereiken van zakelijke doelen door de snelheid van uw inhoud te verhogen. Als u met een groot aantal elementen werkt binnen [!DNL Assets] of uploadt regelmatig/periodiek een groot aantal middelen, waaronder video&#39;s en dynamische media, waardoor het optimaliseren van uw ervaring voor het beheer van digitale middelen van essentieel belang is voor de efficiëntie van het systeem.

Afhankelijk van de positie [!DNL Assets] voor uw organisatie en de functies die u gebruikt rond het opnemen van elementen, het genereren van uitvoeringen en het ophalen van metagegevens, het identificeren en volgen van de beste praktijken op verschillende gebieden verbetert de stabiliteit en prestaties van het systeem aanzienlijk onder belasting.

Na het herzien van de volgende gidsen, zult u de kennis en de hulpmiddelen hebben om een systeem van het ondernemingsmiddelenbeheer te bouwen en te beheren dat aan uw behoeften voldoet.

* [Richtlijnen voor afstelling van middelenprestaties](performance-tuning-guidelines.md)
Bevat een reeks aanbevolen procedures die op elk moment in uw implementatie kunnen worden gevolgd, zelfs nadat u live gaat, om ervoor te zorgen dat u optimaal profiteert van uw systeem.
* [Hulplijn voor middelengrootte](assets-sizing-guide.md)
Bij het opstellen van ramingen voor een implementatie van Elementen, is het belangrijk om ervoor te zorgen dat er voldoende middelen in termen van activaopslag, cpu, geheugen, IO en netwerkproductie beschikbaar zijn. Bij het vergroten van het formaat van veel van deze items moet u weten hoeveel elementen in het systeem worden geladen. Deze gids omvat beste praktijken die helpen efficiënte metriek bepalen voor het schatten van de infrastructuur en de middelen die voor het opstellen worden vereist [!DNL Experience Manager] Elementen en een formaatwijziging.
* [Richtlijnen voor migratie van middelen](assets-migration-guide.md)
Als u elementen van uw oudere systeem wilt migreren naar [!DNL Experience Manager] Middelen, er zijn verscheidene stappen om het migratieproces te stroomlijnen. De migratiehandleiding bevat tips en trucs voor de taken die u uitvoert om de middelen over te brengen naar [!DNL Experience Manager] geleidelijk. Dit omvat het toepassen van metagegevens, het genereren van uitvoeringen en het activeren van de elementen om de implementatie te publiceren.
* [Elementennetwerkoverwegingen](assets-network-considerations.md)
Bij verwerking [!DNL Experience Manager] de plaatsing, het begrip van de netwerktopologie is belangrijk om netwerkprestaties te begrijpen, chokepoints te identificeren, en de verwachte gebruikerservaring te beschrijven. Het document van de Overwegingen van het Netwerk van Activa bespreekt netwerkoverwegingen wanneer het ontwerpen van uw [!DNL Experience Manager] Asset-implementatie.
* [Handleiding voor middelenbewaking](assets-monitoring-best-practices.md)
Na uw [!DNL Experience Manager] implementatie wordt geïmplementeerd, dient u bepaalde taken en het systeem in het algemeen te controleren om de systeemintegriteit en efficiëntie van bewerkingen te waarborgen. De gids van de Controle omvat beste praktijken voor het controleren van diverse aspecten van uw systeem.
* (Afgekeurd) [Verschuivingsgids voor elementen](assets-offloading-best-practices.md)
Grote bestanden verwerken en workflows uitvoeren in [!DNL Experience Manager] Elementen kunnen aanzienlijke CPU-, geheugen- en I/O-bronnen verbruiken. Als u deze taken verschuift, kunnen de overhead van de CPU, het geheugen en de IO worden verminderd. De gids voor het ontladen van bedrijfsmiddelen bevat aanbevolen gebruiksgevallen en aanbevolen procedures voor het offloaden van bedrijfsmiddelen.
* [[!DNL Experience Manager] best practices voor bureaubladtoepassingen](https://helpx.adobe.com/experience-manager/desktop-app/aem-desktop-app-best-practices.html)
   [!DNL Experience Manager] de bureaubladtoepassing koppelt uw DAM-oplossing (Digital Asset Management) aan uw bureaublad, zodat u de bestanden kunt openen die beschikbaar zijn in het dialoogvenster [!DNL Experience Manager] webinterface rechtstreeks op bureaublad. [!DNL Experience Manager] de gebruiksvriendelijke workflow van de bureaubladtoepassing wordt ingeschakeld met de technologie voor netwerkdeling die desktopbesturingssystemen bieden. In deze handleiding worden de belangrijkste mogelijkheden en het aanbevolen gebruik van [!DNL Experience Manager] bureaubladtoepassing.
* [[!DNL Experience Manager] en Creative Cloud integratie beste praktijken](aem-cc-integration-best-practices.md)
U kunt uw [!DNL Experience Manager] plaatsing met Creative Cloud op veelvoudige manieren. Door de best practices te volgen om uw workflows voor integratie en overdracht van bedrijfsmiddelen te stroomlijnen, kunt u maximale efficiëntie bereiken. Deze gids omvat beste praktijken rond het integreren [!DNL Experience Manager] Middelen bij Adobe Creative Cloud.
* (Afgekeurd) [[!DNL Experience Manager] naar map Creative Cloud die aanbevolen werkwijzen deelt](aem-cc-folder-sharing-best-practices.md)
U kunt configureren [!DNL Experience Manager] om gebruikers in DAM toe te staan om omslagen met de gebruikers van de Creative Cloud te delen, zodat zijn zij beschikbaar als gedeelde omslagen in de dienst van de Activa van de Creative Cloud. Deze functie kan worden gebruikt voor het uitwisselen van bestanden tussen creatieve teams en DAM-gebruikers. In deze handleiding worden de aanbevolen procedures voor het benutten van de [!DNL Experience Manager] naar Creative Cloud-functie voor het delen van mappen.
