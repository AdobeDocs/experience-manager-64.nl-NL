---
title: Meerdere paden voor verzamelingen, fragmenten en fragmentsjablonen
description: Segregeer inhoud in de CRX-opslagplaats op basis van de organisatie van de klant om onbevoegde toegang te voorkomen.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 0d70a672a2944e2c03b54beb3b5f734136792ab1
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 0%

---


# Meerdere paden voor verzamelingen, fragmenten en fragmentsjablonen {#multi-tenancy-for-collections-snippets-and-snippet-templates}

Met de functie Multi-tenancy kunt u inhoud in CRX segregeren op basis van het organisatievoorvoegsel en de organisatie-id om de inhoud te beschermen tegen ongeoorloofde toegang door gebruikers van andere organisaties.

In Adobe Experience Manager (AEM) worden gegevens voor elke organisatie opgeslagen in een ander pad. Elk organisatie-specifiek weg wordt geïdentificeerd door de organisatieprefix en organisatie identiteitskaart
die is opgenomen op de traditionele locatie waar verschillende soorten activa worden opgeslagen in CRX.

Als u bijvoorbeeld een map maakt met de naam `Demo`, slaat AEM middel de map standaard op de `../content/dam/Demo` locatie in CRX op. Als de functie voor meerdere paden is ingeschakeld, kunt u de gegevens opslaan op `../content/dam/<organization prefix>/<organization id>Demo`.

Voor Adobe Marketing Cloud-gebruikers van AEM Assets (op aanvraag) die zijn toegewezen aan een `aodpremium` organisatie, kunt u bijvoorbeeld de functie voor meerdere paden gebruiken om het volgende pad te configureren, `../content/dam/mac/aodpremiumDemo`de inhoud te scheiden. In dit voorbeeld `mac` is het organisatievoorvoegsel en `aodpremium` is het organisatie-id.

Gebaseerd op de organisatie en identiteitskaart van de gebruiker, wordt dit gekwalificeerde weg getoond in de interface van AEM Assets en diverse tovenaars, met inbegrip van de Beweging en de verwezenlijking van het Fragment tovenaars om seggregatie af te dwingen.

Met de functie voor meerdere paden kunt u de volgende typen elementen en componenten van elkaar scheiden:

* Verzamelingen
* Openbare verzamelingen
* Catalogi (inclusief de wizard Pagina toevoegen/selecteren)
* Sjablonen
* Fragmentsjablonen
* Lichtbak
