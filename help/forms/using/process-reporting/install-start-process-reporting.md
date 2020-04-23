---
title: Getting Started with Process Reporting
seo-title: Getting Started with Process Reporting
description: The steps you need to follow to get started with AEM Forms on JEE Process Reporting
seo-description: The steps you need to follow to get started with AEM Forms on JEE Process Reporting
uuid: 86ba17da-57e5-4e7a-a864-583d8c0f830e
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: process-reporting
discoiquuid: a0f81621-6ccd-46e2-85d7-2eb4ee3cdb91
translation-type: tm+mt
source-git-commit: f13d358a6508da5813186ed61f959f7a84e6c19f

---


# Getting Started with Process Reporting {#getting-started-with-process-reporting}

Process Reporting gives AEM Forms users the ability to query information about AEM Forms processes that are currently defined in the AEM Forms implementation. However, Process Reporting does not access data directly from the AEM Forms repository. The data is first published to the Process Reporting repository on a scheduled basis (*by the ProcessDataPublisher &amp; ProcessDataStorage service* s). The reports and queries in Process Reporting are then generated out of the Process Reporting data published to the repository. Process Reporting is installed as part of the Forms Workflow module.

This article details the steps to enable the publishing of AEM Forms data to the Process Reporting repository. Daarna, zult u het Rapport van het Proces kunnen gebruiken om rapporten en vragen in werking te stellen. The article also covers the options available to configure the Process Reporting services.

## Process Reporting Pre-requisites {#process-reporting-pre-requisites}

### Purge non-essential processes {#purge-non-essential-processes}

If you are currently using Forms Workflow, the AEM Forms database can potentially contain a large amount of data

The Process Reporting publishing services will publish all AEM Forms data currently available in the database. This implies, that if the database contains legacy data on which you do not want to run reports and queries, all of that data would also be published to the repository even though it is not required for reporting. You are recommended to purge this data before you run the services to publish the data to the Process Reporting repository. This will improve the performance of both the publisher service and the service that queries the data for reporting.

For details on purging AEM Forms process data, see [Purging Process Data](https://help.adobe.com/en_US/livecycle/11.0/AdminHelp/WS92d06802c76abadb-5145d5d12905ce07e7-7cb2.2.html).

>[!NOTE]
>
>For the tips and tricks of Purge Utility, see Adobe Developer Connection article on [Purging processes and jobs](https://www.adobe.com/content/dam/Adobe/en/devnet/livecycle/pdfs/purging_processes_jobs.pdf).

## Configuring Process Reporting services {#configuring-process-reporting-services}

### Schedule process data publishing {#schedule-process-data-publishing}

The Process Reporting services publish data from the AEM Forms database to the Process Reporting repository on a scheduled basis.

This operation can be resource-intensive and can impact the performance of the AEM Forms servers. You are recommended to schedule this outside your AEM Forms server busy time-slots.

By default, the publishing of data is schedule to run every day at 2:00 am.

Perform the following steps to change the publishing schedule:

>[!NOTE]
>
>Als u de implementatie van AEM Forms uitvoert op een cluster, voert u de volgende stappen uit op elk knooppunt van de cluster.

1. Stop the AEM Forms server instance.
   * (For Windows) Open the `[*JBoss root*]/bin/run.conf.bat` file in an editor.
   * (For Linux, AIX and Solaris) `[*JBoss root*]/bin/run.conf.sh` file in an editor.

1. Add the JVM argument `-Dreporting.publisher.cron = <expression>.`

   Example: The following cron expression causes Process Reporting to publish AEM Forms data to the Process Reporting repository every 5 hours:

   * `-Dreporting.publisher.cron = 0_0_0/5_*_*_?`

1. Sla het `run.conf.bat` bestand op en sluit het.

1. Restart the AEM Forms server instance.

1. Stop the AEM Forms server instance.
1. Log in to the WebSphere Administrative Console. In the navigation tree, click **Servers** >  **Application servers** and then, in the right pane, click the server name.

1. Under Server Infrastructure, click **Java and Process Management** > **Process Definition**.

1. Under Additional Properties, click **Java Virtual Machine**.

   In the Generic JVM arguments box, add the argument `-Dreporting.publisher.cron = <expression>.`

   **Example**: The following cron expression causes Process Reporting to publish AEM Forms data to the Process Reporting repository every 5 hours:

   * `-Dreporting.publisher.cron = 0_0_0/5_*_*_?`

1. Click **Apply**, click OK, and then click **Save directly to the master configuration**.

1. Restart the AEM Forms server instance.

1. Stop the AEM Forms server instance.
1. Log in to the WebLogic Administration Console. The default address of WebLogic Administration Console is `https://[hostname]:[port]/console`.

1. Under Change Center, click **Lock &amp; Edit**.

1. Under Domain Structure, click **Environment** >  **Servers** and, in the right pane, click the managed server name.

1. On the next screen, click the **Configuration** tab > **Server Start** tab.

1. In the Arguments box, add the JVM argument `-Dreporting.publisher.cron = <expression>`.

   **Example**: The following cron expression causes Process Reporting to publish AEM Forms data to the Process Reporting repository every 5 hours:

   `-Dreporting.publisher.cron = 0_0_0/5_*_*_?`

1. Click **Save** and then click **Activate Changes**.

1. Restart the AEM Forms server instance.

![processdatapublisherservice](assets/processdatapublisherservice.png)

### ProcessDataStorage-service {#processdatastorage-service}

De dienst ProcessDataStorageProvider ontvangt procesgegevens van de dienst ProcessDataPublisher en bewaart de gegevens aan de bewaarplaats van de Rapportering van het Proces.

At each publishing cycle, the data is saved to subfolders of a pre-defined root folder.

You can use the Administration console to configure the root (**default**: `/content/reporting/pm`) location and subfolder (**default**: `/yyyy/mm/dd/hh/mi/ss`) hierarchy format where the process data would be stored.

#### To configure the Process Reporting repository locations {#to-configure-the-process-reporting-repository-locations}

1. Log in to **Administration Console** with administrator credentials. The default URL of Administration Console is `https://[server]:[port]/adminui`
1. Navigate to **Home** >  **Services** >  **Applications and Services** > **Service Management** and open the **ProcessDataStorageProvider** service.

   ![process-data-storage-service](assets/process-data-storage-service.png)

   **RootFolder**

   The CRX location inside which the process data would be stored for reporting.

   `Default`: `/content/reporting/pm`

   **Folder Hierarchy**

   The folder hierarchy inside which the process data would be stored based on the process creation time.

   `Default`: `/yyyy/mm/dd/hh/mi/ss`

1. Click **Save**.

### ReportConfiguration service {#reportconfiguration-service}

The ReportConfiguration service is used by Process Reporting for configuring the process reporting query service.

#### To configure the ReportingConfiguration service {#to-configure-the-reportingconfiguration-service}

1. Log in to **Configuration Manager** with CRX administrator credentials. The default URL of Configuration Manager is `https://[*server*]:[*port*]/lc/system/console/configMgr`
1. Open the **ReportingConfiguration** service.
1. **Number of Records**

   When running a query on the repository, a result can potentially contain a large number of records. If the resultset is large, the query execution can consume server resources.

   To handle large resultsets, the ReportConfiguration service splits the query processing into batches of records. This reduces the system load.

   `Default`: `1000`

   **CRX Storage Path**

   The CRX location inside which the process data is to be stored for reporting.

   `Default`: `/content/reporting/pm`

   >[!NOTE]
   >
   >This is the same location as specified in the ProcessDataStorage configuration option **Root Folder**.
   >
   >Als u de optie van de Omslag van de Wortel in de configuratie ProcessDataStorage bijwerkt, moet u de plaats van de Weg van de Opslag CRX in de dienst ReportConfiguration bijwerken.

1. Click **Save** and close **CQ Configuration Manager**.

### ProcessDataPublisher-service {#processdatapublisher-service}

The ProcessDataPublisher service imports process data from the AEM Forms database and publishes the data to the ProcessDataStorageProvider service for storage.

#### De service ProcessDataPublisher configureren {#to-configure-processdatapublisher-service-nbsp}

1. Meld u aan bij de **beheerconsole** met beheerdersreferenties.

   De standaard-URL is `https://[server]:port]/adminui/`.

1. Ga naar **Home** > **Services** > **Toepassingen en services** > **Servicebeheer** en open de **ProcessDataPublisher** -service.

![processdatapublisherservice-1](assets/processdatapublisherservice-1.png)

**Gegevens publiceren**

Schakel deze optie in om te beginnen met het publiceren van procesgegevens. De optie is standaard uitgeschakeld.

Schakel Process Reporting alleen in als alle configuraties met betrekking tot Process Reporting-componenten op de juiste wijze zijn ingesteld.

U kunt deze optie ook gebruiken om het publiceren van procesgegevens uit te schakelen wanneer dit niet langer verplicht is.

`Default`: `Off`

**Batchinterval (sec)**

Telkens als de dienst ProcessDataPublisher loopt, verdeelt de dienst eerst de tijd sinds de laatste looppas van de dienst door het Interval van de Partij. De dienst verwerkt dan elk interval van de gegevens van Vormen AEM afzonderlijk.

Zo kunt u de grootte bepalen van de gegevens die de uitgever verwerkt tijdens elke uitvoering (batch) binnen een cyclus.

Bijvoorbeeld, als de uitgever elke dag in werking stelt, dan in plaats van het verwerken van de volledige gegevens één dag in één enkele looppas, door gebrek, wordt het de verwerking in 24 partijen van elk één uur verdeeld.

`Default`: `3600`

`Unit`: `Seconds`

**Time-out vergrendelen (sec)**

De uitgeversservice verkrijgt een vergrendeling wanneer de verwerking van gegevens wordt gestart, zodat meerdere exemplaren van de uitgever niet gelijktijdig met het uitvoeren en verwerken van gegevens beginnen.

Als een uitgeversdienst die een slot heeft verworven, nutteloos voor het aantal seconden is die door de waarde van de Onderbreking van het Slot wordt bepaald, dan wordt zijn slot vrijgegeven zodat andere instanties van de uitgeversdienst kunnen blijven verwerken.

`Default`: `3600`

`Unit`: `Seconds`

**Gegevens publiceren vanuit**

De omgeving van AEM Forms bevat gegevens uit de tijd dat de omgeving is ingesteld.

Standaard importeert de dienst ProcessDataPublisher alle gegevens uit de database van AEM Forms.

Afhankelijk van uw rapporteringsbehoeften, als u van plan bent om rapporten en vragen over gegevens na een bepaalde datum en een tijd in werking te stellen, adviseert men dat u de datum en de tijd specificeert. De publicatieservice publiceert vervolgens de datum vanaf die datum.

`Default`: `01-01-1970 00:00:00`

`Format`: `dd-MM-yyyy HH:mm:ss`

## Toegang tot de gebruikersinterface Process Reporting {#accessing-the-process-reporting-user-interface}

De gebruikersinterface voor Process Reporting is browsergebaseerd.

Nadat u de Rapportering van het Proces van de opstelling hebt, kunt u beginnen met het Proces Meldend bij de volgende plaats in uw installatie van Vormen AEM:

`https://<server>:<port>/lc/pr`

### Aanmelden bij procesrapportage {#log-in-to-process-reporting}

Wanneer u naar de URL voor Process Reporting (https://&lt;server>:&lt;port>/lc/pr) navigeert, wordt het aanmeldingsscherm weergegeven.

Specificeer uw geloofsbrieven aan login aan de module van de Rapportering van het Proces.

>[!NOTE]
>
>Als u zich wilt aanmelden bij de gebruikersinterface Process Reporting, hebt u de volgende AEM Forms-machtigingen nodig:
>
>`PERM_PROCESS_REPORTING_USER`

![vastleggen](assets/capture.png)

Als u zich aanmeldt bij Process Reporting, wordt het scherm **[!UICONTROL Home]** weergegeven.

### Process Reporting Home-scherm {#process-reporting-home-screen}

![proces-reporting-home-screen](assets/process-reporting-home-screen.png)

**De mening van de boom van de Rapportering van het proces:** De boomstructuurweergave aan de linkerkant van het Homescherm bevat de items voor de modules Procesrapportage.

De boomstructuurweergave bestaat uit de volgende items op hoofdniveau:

**Rapporten:** Dit item bevat de out-of-the-box rapporten die worden verzonden met Process Reporting.

Zie [Vooraf gedefinieerde rapporten in Process Reporting](pre-defined-reports-in-process-reporting.md)voor meer informatie over de vooraf gedefinieerde rapporten.

**Adhoc-query&#39;s:** Dit item bevat opties voor het uitvoeren van op filters gebaseerde zoekopdrachten naar processen en taken.

Voor details op ad-hoc vragen, zie [Ad-hoc Vragen in het Rapporteren](adhoc-queries-in-process-reporting.md)van het Proces.

**Aangepast:** Het knooppunt Aangepast geeft aangepaste rapporten weer die u maakt.

Voor de procedure om douanerapporten tot stand te brengen en te tonen, zie de Rapporten van de [Douane in de Rapportering](/help/forms/using/process-reporting/process-reporting-custom-reports.md)van het Proces.

**Procesrapportage, titelbalk:** De de titelbar van de Rapportering van het Proces bevat sommige generische opties die u wanneer het werken in het gebruikersinterface kunt gebruiken.

**Titel van procesrapportage:** De titel Procesrapportage wordt in de linkerhoek van de titelbalk weergegeven.

Klik op de titel om terug te keren naar het scherm Home.

**Tijd laatste update:** De procesgegevens worden op geplande basis gepubliceerd vanuit de AEM Forms-database naar de Process Reporting-opslagplaats.

De laatste tijd van de Update toont de laatste datum en de tijd tot waarvan de gegevensupdates aan de bewaarplaats van de Rapportering van het Proces werden geduwd.

Voor details op de gegevens het publiceren dienst en hoe te om deze dienst te plannen, zie het [procesgegevens van het Programma publiceren](/help/forms/using/process-reporting/install-start-process-reporting.md#p-schedule-process-data-publishing-p) in het artikel dat met het Melden van het Proces wordt begonnen.

**Gebruiker voor procesrapportage:** De aangemelde gebruikersnaam wordt rechts van de laatste update weergegeven.

**Verwerking van vervolgkeuzelijst titelbalk rapportage:** De vervolgkeuzelijst in de rechterhoek van de titelbalk van Procesrapportage bevat de volgende opties:

* **[!UICONTROL Synchroniseren]**: Synchroniseer de ingesloten Process Reporting-opslagplaats met de AEM Forms-database.
* **[!UICONTROL Help]**: Raadpleeg de Help-documentatie bij Process Reporting.
* **[!UICONTROL Afmelden]**: Afmelden bij procesrapportage


