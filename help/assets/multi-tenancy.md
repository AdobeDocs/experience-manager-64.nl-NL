---
title: Meerdere paden voor verzamelingen, fragmenten en fragmentsjablonen
description: Segregeer inhoud in de CRX-opslagplaats op basis van de organisatie van de klant om onbevoegde toegang te voorkomen.
contentOwner: AG
feature: Collections
role: Architect,Admin,Leader
exl-id: d00a671a-6707-4941-868d-fa13510b7b60
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 0%

---

# Meerdere paden voor verzamelingen, fragmenten en fragmentsjablonen {#multi-tenancy-for-collections-snippets-and-snippet-templates}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Met de functie Multi-tenancy kunt u inhoud in CRX segregeren op basis van het organisatievoorvoegsel en de organisatie-id om de inhoud te beschermen tegen ongeoorloofde toegang door gebruikers van andere organisaties.

In Adobe Experience Manager (AEM) worden gegevens voor elke organisatie opgeslagen in een ander pad. Elk organisatie-specifiek weg wordt geïdentificeerd door de organisatieprefix en organisatie identiteitskaart
die is opgenomen op de traditionele locatie waar verschillende soorten activa worden opgeslagen in CRX.

Als u bijvoorbeeld een map maakt met de naam `Demo`AEM elementen worden standaard opgeslagen in `../content/dam/Demo` locatie in CRX. Als de functie voor meerdere paden is ingeschakeld, kunt u de gegevens opslaan op `../content/dam/<organization prefix>/<organization id>Demo`.

Bijvoorbeeld voor Adobe Marketing Cloud-gebruikers van AEM Assets (op aanvraag) die zijn toegewezen aan `aodpremium` organisatie, kunt u de multi-huidseigenschap gebruiken om de volgende weg te vormen aan `../content/dam/mac/aodpremiumDemo`scheidt u de inhoud. In dit voorbeeld `mac` is het organisatievoorvoegsel en `aodpremium` is de organisatie-id.

Gebaseerd op de organisatie en identiteitskaart van de gebruiker, wordt dit gekwalificeerde weg getoond in de interface van AEM Assets en diverse tovenaars, met inbegrip van de Beweging en de verwezenlijking van het Fragment tovenaars om seggregatie af te dwingen.

Met de functie voor meerdere paden kunt u de volgende typen elementen en componenten van elkaar scheiden:

* Verzamelingen
* Openbare verzamelingen
* Catalogi (inclusief de wizard Pagina toevoegen/selecteren)
* Sjablonen
* Fragmentsjablonen
* Lichtbak
