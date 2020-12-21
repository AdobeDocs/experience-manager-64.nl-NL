---
title: SRP - Opslag van communautaire inhoud
seo-title: SRP - Opslag van communautaire inhoud
description: Vanaf AEM Communities 6.1 wordt door de gebruiker gegenereerde inhoud (UGC) opgeslagen in één gemeenschappelijke opslagplaats die wordt geleverd door een opslagprovider (SRP)
seo-description: Vanaf AEM Communities 6.1 wordt door de gebruiker gegenereerde inhoud (UGC) opgeslagen in één gemeenschappelijke opslagplaats die wordt geleverd door een opslagprovider (SRP)
uuid: 651af1d7-70e8-4b56-8c01-871cb397678e
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: e975e026-e815-4445-be3e-b1237ed3f6b2
translation-type: tm+mt
source-git-commit: 8f169bb9b015ae94b9160d3ebbbd1abf85610465
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 0%

---


# SRP - Community Content Storage {#srp-community-content-storage}

## Inleiding {#introduction}

Vanaf AEM Communities 6.1 wordt door de gebruiker gegenereerde inhoud (UGC) opgeslagen in één gemeenschappelijke opslagplaats die wordt geleverd door een opslagbronprovider (SRP). Er zijn verscheidene opties SRP waarvan te kiezen, zoals ASRP, MSRP, en JSRP.

In tegenstelling tot vroegere versies, is er geen omgekeerde/voorwaartse replicatie van UGC over AEM instanties. In plaats daarvan maakt SRP UGC direct toegankelijk voor creeer, lees, update, en schrapt (CRUD) verrichtingen van alle auteur en publiceer instanties, met een uitzondering voor JSRP.

Hieronder volgen de [kenmerken van elke SRP-optie](#characteristics-of-srp-options). Dit is cruciale informatie voor het besluitvormingsproces bij het kiezen van de juiste SRP en [onderliggende implementatie](topologies.md).

Voor details betreffende het gebruik van SRP voor UGC, zie [Overzicht van de Leverancier van het Middel van de Opslag](srp.md).

>[!NOTE]
>
>SRP is slechts op communautaire inhoud van toepassing. Het heeft geen invloed op de opslaglocatie van de site-inhoud ([knooppuntoverslag](../../help/sites-deploying/data-store-config.md)) en heeft geen invloed op de veilige verwerking van gebruikersregistratie, gebruikersprofielen en gebruikersgroepen tussen AEM instanties (zie ook [Gebruikersgegevens beheren](#managing-user-data)).

>[!CAUTION]
>
>Vanaf AEM 6.1 wordt [UGC nooit gerepliceerd](#ugc-never-replicated).
>
>Wanneer de plaatsing geen gemeenschappelijke opslag, zoals het gebrek [JSRP](topologies.md#jsrp) topologie omvat, zal UGC slechts op AEM publiceren of auteursinstantie zichtbaar zijn waarop het was ingegaan. Alleen als de topologie een publicatiecluster bevat, is de UGC zichtbaar op elke publicatieinstantie.

## Kenmerken van SRP-opties {#characteristics-of-srp-options}

[ASRP - Adobe Storage Resource Provider](asrp.md)\
Met deze optie, wordt UGC voortgeduurd ver in een wolkendienst die door Adobe wordt ontvangen en wordt beheerd. Het vereist een aanvullende licentie en samenwerking met een accountvertegenwoordiger om de rekening voor die specifieke licentie te verstrekken.

* Vereist een gekoppelde cloudservice die door Adobe wordt geleverd en ondersteund voor het opslaan van community-inhoud
* Vereist keuze van een datacenter in een specifieke geografische omgeving (VS, EMEA, APAC)
* Vereist alle programmatic toegang tot UGC door SRP API zijn
* Geschikt voor TarMK-publicatiefarm
* Geschikt voor investeringen in lokale opslag

>[!NOTE]
>
>Er geldt een limiet voor het uploaden van bijlagen naar posten (of opmerkingen) in ASRP. Dit is 50 MB.

[MSRP - MongoDB Storage Resource Provider](msrp.md)\
Met deze optie wordt de UGC direct in een lokale MongoDB-instantie voortgezet.

* Vereist een lokale, gelicentieerde installatie van MongoDB om inhoud van de gebruikersgemeenschap op te slaan
* Vereist een lokale installatie van Apache Solr
* Vereist alle programmatic toegang tot UGC door SRP API zijn
* Geschikt voor een bestaand TarMK-publicatiebedrijf
* Geschikt voor een MongoMK- of RdbMK-cluster
* Geschikt wanneer u grote hoeveelheden community-inhoud verwacht

[DSRP - Relational Database Storage Resource Provider](dsrp.md)\
Met deze optie, wordt UGC voortgeduurd direct in een lokale MySQL gegevensbestandinstantie.

* Vereist een lokale installatie van MySQL om inhoud van de gemeenschap op te slaan
* Vereist een lokale installatie van Apache Solr
* Vereist alle programmatic toegang tot UGC door SRP API zijn
* Geschikt voor een bestaand TarMK-publicatiebedrijf
* Geschikt voor een MongoMK- of RdbMK-cluster
* Geschikt wanneer u grote hoeveelheden community-inhoud verwacht

[JSRP - JCR Storage Resource Provider](jsrp.md)\
Met de standaardoptie, is er geen gemeenschappelijke opslag. De UGC wordt alleen gecontinueerd in dezelfde JCR-opslagruimte als de AEM instantie waarin deze is ingevoerd.

* Hiermee wordt community-inhoud opgeslagen in de JCR-opslagruimte van de AEM auteur of publicatie-instantie waarnaar deze is gepost
* Vereist alle programmatic toegang tot UGC door SRP API zijn
* Vereist een publicatiecluster als meer dan één publiceer instantie wordt opgesteld (er is geen replicatiemechanisme onder publiceer instanties in een landbouwbedrijf TarMK)
* De modernisering wordt uitgevoerd slechts in het publicatiemilieu (er is geen omgekeerd/voorwaarts replicatiemechanisme tussen auteur en publiceert)
* Over het algemeen het beste voor ontwikkeling, demonstraties en training

## SRP {#configuring-srp} configureren

De standaardopslagoptie specificeren, die op de onderliggende plaatsing wordt gebaseerd, wordt gemaakt door [de console van de Configuratie van de Opslag](srp-config.md).

Voor configuratiedetails van elke optie, zie:

* [ASRP - Adobe Storage Resource Provider](asrp.md)
* [MSRP - MongoDB Storage Resource Provider](msrp.md)
* [DSRP - Relational Database Storage Resource Provider](dsrp.md)
* [JSRP - JCR Storage Resource Provider](jsrp.md)

Als er geen opslagoptie actief is geselecteerd, wordt JSRP standaard ingeschakeld.

## Aanvullende informatie {#additional-information}

### UGC Nooit gerepliceerd {#ugc-never-replicated}

In de auteursomgeving, creeert een auteur pagina inhoud en herhaalt het aan het publicatiemilieu. Wanneer een pagina een interactieve AEM Communities-functie bevat, zoals opmerkingen, revisies, forum, blog of QnA, resulteert de interactie door leden (aangemeld bij sitebezoekers) op een publicatie-instantie in door gebruikers gegenereerde inhoud (UGC) die wordt ingevoerd in de publicatieomgeving.

Eerder werd deze community-inhoud omgekeerd gerepliceerd naar auteur-instanties en van de auteur gerepliceerd naar publicatie-instanties. Het was problematisch om consistentie tussen AEM instanties met omgekeerde en voorwaartse replicatie te handhaven.

Vanaf AEM Communities 6.1 is de behoefte aan replicatie van UGC geëlimineerd door gedeelde opslag voor UGC te gebruiken, zoals hierboven beschreven.

Terwijl site-inhoud wordt gerepliceerd, wordt UGC nooit gerepliceerd.

### Gebruikersgegevens {#managing-user-data} beheren

Ook van belang voor communites zijn [*gebruikers*, *gebruikersgroepen*, en *gebruikersprofielen*](users.md). Deze op gebruiker betrekking hebbende gegevens, wanneer gecreeerd en bijgewerkt in publicatiemilieu, moeten aan andere publicatieinstanties ter beschikking worden gesteld wanneer de topologie [publicerend landbouwbedrijf](../../help/sites-deploying/recommended-deploys.md#tarmk-farm) is.

Vanaf AEM Communities 6.1 worden gebruikersgerelateerde gegevens gesynchroniseerd met behulp van Verschuivende distributie in plaats van replicatie. Voor meer informatie, surf naar [Gebruikerssynchronisatie](sync.md).

### Upgrade uitvoeren naar AEM Communities 6.2 {#upgrading-to-aem-communities}

Bij de upgrade naar AEM Communities 6.3, als bestaande UGC behouden moet blijven, moeten stappen worden gezet afhankelijk van het feit of de AEM 5.6.1- of AEM 6.0-community gebruikmaakte van Adobe-opslag op aanvraag of on-premise opslag van UGC.

Voor meer informatie gaat u naar [Upgraden naar AEM Communities 6.3](upgrade.md).
