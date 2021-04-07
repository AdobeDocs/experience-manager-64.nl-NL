---
title: Inleiding tot Process Reporting
seo-title: Inleiding tot Process Reporting
description: Inleiding en belangrijkste mogelijkheden van AEM Forms bij JEE Process Reporting
seo-description: Inleiding en belangrijkste mogelijkheden van AEM Forms bij JEE Process Reporting
uuid: a33ea729-7e1f-4093-bdb6-b8dc3afd59a7
content-type: reference
topic-tags: process-reporting
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 0cfe62b8-839e-414b-95e5-1bfce6a9d16a
exl-id: 279b2f89-5b91-4b8f-ab0f-8ade9b9f3932
translation-type: tm+mt
source-git-commit: bd94d3949f0117aa3e1c9f0e84f7293a5d6b03b4
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 0%

---

# Inleiding tot Process Reporting {#introduction-to-process-reporting}

![procesrapportage](assets/process-reporting.png)

De Rapportering van het proces is een browser-gebaseerd hulpmiddel dat u gebruikt om rapporten over de processen en de taken van AEM Forms tot stand te brengen en te bekijken.

De Rapportering van het proces verstrekt een reeks out-of-the-box rapporten die u toestaan om, informatie over lange lopende processen, procesduur, en werkschemavolume te filtreren te bekijken.

De extra Rapportering van het Proces verstrekt een interface om ad hoc vragen in werking te stellen en de meningen van het douanerapport in het Proces te integreren Meldend gebruikersinterface.

Zie [Door AEM Forms ondersteunde Platforms](/help/forms/using/aem-forms-jee-supported-platforms.md) voor de lijst met ondersteunde browsers.

Procesrapportage is gebaseerd op modules die:

* Procesgegevens uit AEM Forms-database lezen
* Procesgegevens publiceren naar een ingesloten Process Reporting-opslagplaats
* Biedt een op een browser gebaseerde gebruikersinterface voor het weergeven van rapporten

## Belangrijke mogelijkheden {#key-capabilities}

### Altijd melden {#always-on-reporting}

![locatiebeheer](assets/site-management.png)

Bekijk de lijst van langdurige processen, kaarten van de procesduur, en looppasvragen gebruikend filters.

De Rapportering van het proces verstrekt ook de optie om het rapport en vraaggegevens in formaat uit te voeren CSV.

### Adhocrapporten {#adhoc-reports}

![afdrukken-&amp;-color](assets/print-&-colour.png)

Gebruik filters om een specifieke weergave van uw gegevens op te halen.

U kunt processen of taken zoeken op ID, duur, begin- en einddatum, initiator van het proces enz.

U kunt meerdere filters combineren om specifieke rapporten te maken.

U kunt de rapportfilters dan opslaan om op een recentere datum of een tijd te lopen.

### Proces/taakgeschiedenis {#process-task-history}

![bestandsbeheer](assets/file-management.png)

AEM Forms-servers voeren een groot aantal processen parallel uit. Deze processen blijven bij de overgang van de ene naar de andere staat. Door Forms-gegevens regelmatig naar de Process Reporting repository te publiceren, behoudt Process Reporting de overgangsinformatie over de processen die in AEM Forms worden uitgevoerd.

### Toegangsbeheer {#access-control-br}

![naamloos](assets/untitled.png)

Process Reporing biedt op toestemming gebaseerde toegang tot de gebruikersinterface.

Dit betekent slechts hebben de gebruikers met het melden van toestemmingen toegang tot het Proces Meldend gebruikersinterface.
