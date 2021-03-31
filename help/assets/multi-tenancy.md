---
title: Meerdere paden voor verzamelingen, fragmenten en fragmentsjablonen
description: Segregeer inhoud in de CRX-opslagplaats op basis van de organisatie van de klant om onbevoegde toegang te voorkomen.
contentOwner: AG
feature: Verzamelingen
role: Architect,Beheerder,Leader
translation-type: tm+mt
source-git-commit: 29e3cd92d6c7a4917d7ee2aa8d9963aa16581633
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 1%

---


# Meerdere paden voor verzamelingen, fragmenten en fragmentsjablonen {#multi-tenancy-for-collections-snippets-and-snippet-templates}

Met de functie Multi-tenancy kunt u inhoud in CRX segregeren op basis van het organisatievoorvoegsel en de organisatie-id om de inhoud te beschermen tegen ongeoorloofde toegang door gebruikers van andere organisaties.

In Adobe Experience Manager (AEM) worden gegevens voor elke organisatie opgeslagen in een ander pad. Elk organisatie-specifiek weg wordt geïdentificeerd door de organisatieprefix en organisatie identiteitskaart
die is opgenomen op de traditionele locatie waar verschillende soorten activa worden opgeslagen in CRX.

Als u bijvoorbeeld een map maakt met de naam `Demo`, slaat AEM middelen de map standaard op de locatie `../content/dam/Demo` in CRX op. Als de functie voor meerdere paden is ingeschakeld, kunt u de gegevens opslaan op `../content/dam/<organization prefix>/<organization id>Demo`.

Voor Adobe Marketing Cloud-gebruikers van AEM Assets (op aanvraag) die zijn toegewezen aan `aodpremium`-organisatie, kunt u bijvoorbeeld de functie voor meerdere paden gebruiken om het volgende pad naar `../content/dam/mac/aodpremiumDemo` te configureren, de inhoud te scheiden. In dit voorbeeld is `mac` het organisatievoorvoegsel en `aodpremium` is de organisatie-id.

Gebaseerd op de organisatie en identiteitskaart van de gebruiker, wordt dit gekwalificeerde weg getoond in de interface van AEM Assets en diverse tovenaars, met inbegrip van de Beweging en de verwezenlijking van het Fragment tovenaars om seggregatie af te dwingen.

Met de functie voor meerdere paden kunt u de volgende typen elementen en componenten van elkaar scheiden:

* Verzamelingen
* Openbare verzamelingen
* Catalogi (inclusief de wizard Pagina toevoegen/selecteren)
* Sjablonen
* Fragmentsjablonen
* Lichtbak
