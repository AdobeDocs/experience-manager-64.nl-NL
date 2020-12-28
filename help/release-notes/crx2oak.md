---
title: CRX2OAK-migratiehulpprogramma
seo-title: CRX2OAK-migratiehulpprogramma
description: Opmerkingen bij de release die specifiek zijn voor het Adobe Experience Manager 6.4 CRX2OAK-migratiehulpprogramma.
seo-description: Opmerkingen bij de release die specifiek zijn voor het Adobe Experience Manager 6.4 CRX2OAK-migratiehulpprogramma.
uuid: 1b582faf-2dc6-41a2-9419-7e82347f9d6c
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4
topic-tags: release-notes
content-type: reference
discoiquuid: cfdaceac-a5b3-4070-ad4c-f1457b1e2e4b
translation-type: tm+mt
source-git-commit: f8ba597c62379ba413309303c2ad066ab7afce1e
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 0%

---


# CRX2OAK-migratiehulpmiddel {#crx-oak-migration-tool}

## Lijst met wijzigingen en correcties {#list-of-changes-and-fixes}

### 1.8.6 (juni 2018) {#june}

* OAK-7339 Los alle graden die met UnsupportedOperationException op MissingBlobStore breken door LoopbackBlobStore te introduceren op
* Eik 1.8.4 gebruiken

### 1.8.4 (april 2018) {#april}

* Eak-versie 1.8.2 gebruiken
* GRANITE-18104 Repo-migratiefout van 6.3 naar 6.4 zou zinvoller moeten zijn
* GRANITE-16571 Vervang het gebruik van SHA-1

   * De controlesom voor het gereedschap is nu SHA-512 bij gebruik van de optie —version

* GRANITE-17601 Embed oak-upgrade in CRX2Oak met eak-blob-cloud
* GRANITE-1853 crx2oak verlaat versie-eigenschappen op de knoop zelfs wanneer de versies niet worden gemigreerd

### Versie 1.6.8 (maart 2017) {#version-march}

* Bijgewerkte eik-versie naar 1.6.1
* CQ-61847 Voeg crx2oak-quickstart-extensie samen met crx2oak (toegevoegde migratieprofielen)
* CQ-97488 Het bevorderen van en het laten vallen AEM looppas wijzen (door sling.options.file te herschrijven)
* GRANITE-12798/OAK-4260 Mogelijkheid om van het eiken-segment naar het eiken-segmentteer te gaan

### Versie 1.4.2 (maart 2016) {#version-march-1}

* Oak-versie upgraden naar 1.4.1
* OAK-3846 / GRANITE-10748 noem SNS knopen anders als zij nodetype beperkingen overtreden
* OAK-3910 / GRANITE-10730 Migrerend knoop die van `mix:versionable` zonder versiegeschiedenis erft
* OAK-4128/GRANITE-11757 `RepositorySidegrade` kopieert de eigenschappen van de wortelknoop niet

### Versie 1.3.4 (januari 2016) {#version-january}

* Oak-versie upgraden naar 1.3.16
* OAK-3844/GRANITE-10730 Betere steun voor versieable knopen zonder versiegeschiedenissen
* OAK-3846 anders noem SNS knopen als zij nodetype beperkingen schenden

### Versie 1.3.2 (december 2015) {#version-december}

* Hiermee wordt de eik-versie bijgewerkt naar 1.3.12
* Datastore-directory mag niet worden verplaatst na de migratie (GRANITE-10447)
* crx2oak-quickstart-extension samenvoegen met crx2oak (CQ-61847)
* crx2oak mislukt op dubbele waarden in de gegevensopslagruimte (CQ-61906)
* Lange AEM start na migratie vanuit CQ 5.x (GRANITE-10309)
* Ondersteuning voor meerdere LDAP-servers in crx2oak (GRANITE-9917)
* Controle voor maximale lengte van knooppuntnamen afdwingen (OAK-3111)
* Ondersteuning voor S3DataSource als migratiebron (OAK-3685)
