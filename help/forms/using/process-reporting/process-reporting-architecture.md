---
title: Hoe procesrapportage werkt
seo-title: How Process Reporting Works
description: Beschrijving van de diensten die de AEM Forms vormen voor JEE Process Reporting en een inleiding op de Process Reporting UI
seo-description: Description of the services that make up the AEM Forms on JEE Process Reporting and an introduction to the Process Reporting UI
uuid: 00a2dd6d-8a6f-4c7b-b03e-81cfd4bcf50d
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: process-reporting
discoiquuid: 4afc68fc-6b39-4c31-95fa-2ef3111c57da
exl-id: 05ef8b08-bb1d-441d-8b02-5f047efbabcb
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 0%

---

# Hoe procesrapportage werkt {#how-process-reporting-works}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Procesrapportage is de rapporteringsmodule van de AEM Forms op JEE.

Met Process Reporting kunt u rapporten uitvoeren over AEM Forms-processen en -taken.

Procesrapportage gebruikt de ingesloten Process Reporting-opslagplaats om Forms-gegevens te publiceren. Vervolgens worden die gegevens gebruikt om rapporten uit te voeren.

Procesrapportage bestaat uit de volgende modules:

* [ProcessDataPublisher-service](/help/forms/using/process-reporting/process-reporting-architecture.md#p-processdatapublisher-service-br-p)
* [ProcessDataStorage-service](/help/forms/using/process-reporting/process-reporting-architecture.md#p-processdatastorageprovider-service-br-p)
* [OSGi-service](/help/forms/using/process-reporting/process-reporting-architecture.md#p-osgi-service-br-p)
* [Query-gegevensserver](/help/forms/using/process-reporting/process-reporting-architecture.md#p-querydataservlet-service-br-p)
* [Gebruikersinterface voor procesrapportage](/help/forms/using/process-reporting/process-reporting-architecture.md#p-process-reporting-user-interface-br-p)

## Procesrapporteringsarchitectuur {#process-reporting-architecture-br}

![procesrapporteringsarchitectuur](assets/processreportingarchitecture.png)

## Procesrapporteringsmodules {#process-reporting-modules}

### ProcessDataPublisher-service {#processdatapublisher-service-br}

De ProcessDataPublisher-server wordt regelmatig uitgevoerd in de AEM Forms-database en extraheert de gegevens die zijn gewijzigd sinds de laatste uitvoering van de service. De gegevens worden vervolgens gepubliceerd naar de service Gegevensopslag verwerken.

Voor details bij het vormen van de dienst, zie [De service ProcessDataPublisher configureren](/help/forms/using/process-reporting/install-start-process-reporting.md#p-reportconfiguration-service-p).

### ProcessDataStorageProvider-service {#processdatastorageprovider-service-br}

De dienst ProcessDataStorageProvider ontvangt procesgegevens van de dienst ProcessDataPublisher en bewaart de gegevens aan de bewaarplaats van de Rapportering van het Proces.

Voor details bij het vormen van de dienst, zie [De service ProcessDataStorageProvider configureren](/help/forms/using/process-reporting/install-start-process-reporting.md#p-to-configure-the-process-reporting-repository-locations-p).

### OSGi-service {#osgi-service-br}

QueryDataServlet gebruikt deze dienst om de rapporteringsgegevens van de Opslagplaats van de Rapportering van het Proces te verkrijgen.

### QueryDataServlet-service {#querydataservlet-service-br}

De dienst QueryDataServlet keurt vragen van het Rapport van het Proces gebruikersinterface goed.

De dienst gebruikt dan diensten OSGi om de relevante het melden gegevens te verkrijgen, de gegevens te verwerken, en de gegevens aan het gebruikersinterface terug te keren.

### Gebruikersinterface voor procesrapportage {#process-reporting-user-interface-br}

Het proces dat gebruikersinterface meldt is een browser-gebaseerde interface van het Web. U gebruikt deze interface om proces- en taakinformatie weer te geven die is gepubliceerd vanuit de AEM Forms-database.

### QueryDataServlet-service {#querydataservlet-service-br-1}

De dienst QueryDataServlet keurt vragen van het Rapport van het Proces gebruikersinterface goed.

De dienst gebruikt dan diensten OSGi om de relevante het melden gegevens te verkrijgen, de gegevens te verwerken, en de gegevens aan het gebruikersinterface terug te keren.

### Aangepaste rapporten {#custom-reports-br}

U kunt uw eigen douanerapporten tot stand brengen en deze rapporten tonen in het lusje van de Rapporten van de Douane van het Proces Meldend gebruikersinterface.

Voor de stappen om een douanerapport tot stand te brengen, zie om een douanerapport in het artikel tot stand te brengen [Aangepaste rapporten in procesrapportage](/help/forms/using/process-reporting/process-reporting-custom-reports.md).
