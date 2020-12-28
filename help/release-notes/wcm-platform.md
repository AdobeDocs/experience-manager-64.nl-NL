---
title: AEM Foundation & Repository
seo-title: AEM Foundation & Repository
description: Opmerkingen bij de release specifiek voor Adobe Experience Manager 6.3 AEM Platform en opslagplaats.
seo-description: Opmerkingen bij de release specifiek voor Adobe Experience Manager 6.3 AEM Platform en opslagplaats.
uuid: 147b38d0-cf87-467c-a52d-3399d4af7e6e
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4
topic-tags: release-notes
content-type: reference
discoiquuid: e5dd9d0d-6d67-4430-aeb3-2be91356f624
translation-type: tm+mt
source-git-commit: 966263cc94f44bcad76e7e9ba5c6ecdc93574348
workflow-type: tm+mt
source-wordcount: '733'
ht-degree: 0%

---


# AEM Foundation &amp; Repository {#aem-foundation-repository}

## Lijst met wijzigingen {#list-of-changes}

### Bewaarplaats {#repository}

* Oak Segment Tar MicroKernel

   * Modus Snel comprimeren (staarten comprimeren) voor online revisie opschonen
   * Verbeterde schrijfsnelheden
   * Status van segmentbewerkingen die worden blootgesteld via JMXBean
   * Duur schatting voor opschonen van offlinerevisie

* Oak Mongo Microkernel

   * Continuous Revision Cleanup for MongoMK vervangt gepland onderhoud voor opschonen

* Verbeterde efficiëntie voor het opschonen van revisies in documentknooppunten
* Zie [Apache Jackrabbit Oak Jira v. 1.8.0](https://archive.apache.org/dist/jackrabbit/oak/1.8.0/RELEASE-NOTES.txt), [Apache Jackrabbit Oak Jira v. 1.8.1](https://archive.apache.org/dist/jackrabbit/oak/1.8.1/RELEASE-NOTES.txt) en [Apache Jackrabbit Oak Jira v. 1.8.2](https://archive.apache.org/dist/jackrabbit/oak/1.8.2/RELEASE-NOTES.txt) voor een volledig overzicht van vaste problemen.

>[!CAUTION]
>
>* De nieuwe versie van de Oak Segment Tar aanwezig sinds AEM 6.3 vereist een repository migratie. Deze stap is verplicht als u een upgrade uitvoert van een oudere versie van TarMK of als u de nieuwe segmentmarkering wilt overschakelen van een ander type persistentie. Voor meer informatie over wat de voordelen van de nieuwe Tar van het Segment zijn, zie [Migrating to Oak Segment Tar FAQ](/help/sites-deploying/revision-cleanup.md#migrating-to-oak-segment-tar).

>



### {#search-amp-indexing} zoeken en indexeren

* Verbeterde ondersteuning voor indexeringsbewerkingen via &#39;ak-run&#39; (CLI):

   * Indexconsistentiecontrole
   * Indexeringsstatistieken
   * Index configuratie Im/export
   * Opnieuw indexeren

* Verminderde groei van de Luceen-gerelateerde opslagplaats voor een algemene verbeterde systeemprestaties
* Synchrone eigenschapsindexen [(Meer informatie)](https://wiki.apache.org/jackrabbit/Synchronous%20Lucene%20Property%20Indexes)
* Verklaar Vraag in de Manager van de Index steunt nu AEM syntaxis QueryBuilder
* Indexbeheer stelt nu indexcijfers beschikbaar: grootte, laatste bijgewerkte en consistentiecontrole

### Gebruikersinterface {#user-interface}

* Er zijn verschillende verbeteringen aangebracht in de interface om deze productiever en gebruiksvriendelijker te maken.
* Nieuwe contentstructuurrails om snel door een hiërarchie te navigeren. In combinatie met de lijstmening, herstelt dit het Klassieke UI interactiemodel.
* Verbeterd schuiven in kaart en lijstweergave van grote mappen.
* Verbeterde interactie met de zoekresultaten - met de knop Vorige herstelt u het vorige zoekresultaat.
* Extra sneltoetsen voor de meeste algemene handelingen, zoals het openen van een bepaalde rail, het bewerken, verplaatsen en verwijderen van items of het openen van eigenschappen.
* Mogelijkheid om sneltoetsen uit te schakelen (in Voorkeuren in-/uitschakelen).
* Stop met het tonen van tijdstempels in alle UI ten opzichte van na 7 dagen (standaard ingesteld in Voorkeuren).

>[!CAUTION]
>
>* Adobe is niet van plan om verdere verhogingen aan Klassieke UI te maken. AEM 6.4 heeft de klassieke gebruikersinterface inbegrepen, en klanten die van vroegere versies bevorderen kunnen het blijven gebruiken zoals is. Merk op dat Klassieke UI volledig wordt gesteund terwijl wordt afgekeurd [lees meer](/help/sites-deploying/ui-recommendations.md).

>



### Contentdistributie {#content-distribution}

* Verbeterde replicatieprestaties ter ondersteuning van grote volumelicenties
* Steun OAuth 2.0 authentificatie in het vervoer van de Distributie
* Verbeterde prestaties voor VLT-pakketten

### Bewaking {#monitoring}

* Een nieuw Overzicht van het Systeem verstrekt een momentopnamemening op alle prestaties betrekking hebbende systeemstatus &amp; activiteiten
* Nieuwe gezondheidscontroles:

   * Grote Lucene-indexen detecteren
   * Gezondheid van Async-indexering
   * Grote Lucene-indexen
   * Query-prestaties
   * Transversale begrenzingen voor query
   * Gesynchroniseerde klokken
   * Systeemonderhoud - Revisie opschonen
   * Systeemonderhoud - DataStore GC
   * Systeemonderhoud - continue revisie van GC

* De gebruiker kan nu het bereik van de download status.zip definiëren

###  Onderhoud{#maintenance}

* Actieve schrapping van binaire getallen van Lucene die een onderhoudstaak gebruiken
* RevisionGC-onderhoudstaak voor MongoDB is nu uitgeschakeld en werkt nu beter dan Continuous Revision Cleanup. Zie de sectie Repository hierboven.
* Met de configuratie voor het wissen van versies kan een minimumaantal versies worden behouden
* Het leegmaken van de versie stopt aan het einde van een onderhoudsvenster. Het kan ook worden begonnen en manueel worden tegengehouden en het zal incrementeel met de volgende aanvang verdergaan.

### Upgrade {#upgrade}

* Achterwaartse compatibiliteit: De achterwaartse compatibele eigenschappen in 6.4, helpen uw douanecode in de meeste gevallen compatibel blijven en verminderen verbeteringsinspanning.
* Complexiteit-evaluatie van upgrade: Het nieuwe gereedschap Patroondetector om de complexiteit van upgrades te beoordelen.
* Duurzame verbeteringen: De classificatie van het oppervlak en van de Inhoud van API wordt geïntroduceerd om u te helpen beste praktijken voor een efficiënte en naadloze verbetering aan de volgende versie door uw ontwikkelingscyclus gemakkelijk volgen.
* Herstructurering opslagplaats: Aanzienlijke herstructurering (vooral /e.d.) om upgrades te vergemakkelijken en de beste praktijken bij de implementatie te bevorderen. [Lees meer.](/help/sites-deploying/repository-restructuring.md)
* Raadpleeg de [Upgradedocumentatie](/help/sites-deploying/upgrade.md) voor meer informatie over deze functies.

### Cloud Services {#cloud-services}

* Vele Cloud Services zijn nu configureerbaar via Touch UI; de resterende gegevens kunnen worden geconfigureerd met de Verouderde Cloud Services-kaart.
* De omslagen van Plaatsen en van Activa kunnen met Cloud Services worden gevormd die op een contextbewuste manier worden geladen.

### Beveiliging {#security}

* Verbeterde en vereenvoudigde gebruikersinterface met ondersteuning voor meerdere gebruikersprofielen.
* Verbeterde prestaties voor grote groepslidmaatschappen voor gebruikers.

### Projecten en workflows {#projects-and-workflows}

* Druk op de op gebruikersinterface gebaseerde Workfloweditor om workflowmodellen op een meer gestroomlijnde manier te beheren.
* Ondersteuning voor het opschonen van projecttaken bij onderhoudstaken.

