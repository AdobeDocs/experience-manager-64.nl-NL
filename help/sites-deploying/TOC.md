---
cloud: experience-cloud
product: adobe experience manager
audience: end-user
user-guide-title: AEM 6.4-implementatiegids
user-guide-description: Learn more about installing, deploying, and the architecture of Adobe Experience Manager 6.4, including our Adobe Managed Services cloud deployment.
translation-type: tm+mt
source-git-commit: 27db148008709e28bab42f25e79f530fe37affb4
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 1%

---


# AEM 6.4 Gebruikershandleiding implementeren {#deploying}

+ [Gebruikershandleiding implementeren](home.md)
+ Inleiding tot het AEM-Platform {#introduction}
   + [Inleiding tot het AEM-Platform](platform.md)
   + [Technische vereisten](technical-requirements.md)
   + [Opslagelementen in AEM 6.4](storage-elements-in-aem-6.md)
   + [AEM met MongoDB](aem-with-mongodb.md)
+ AEM implementeren {#deploying}
   + [Implementeren en onderhouden](deploy.md)
   + [Aanbevolen implementaties](recommended-deploys.md)
   + [Installeren van toepassingsserver](application-server-install.md)
   + [Aangepaste standalone installatie](custom-standalone-install.md)
   + [Start en stop opdrachtregel](command-line-start-and-stop.md)
   + [Opslaan van knooppunten en gegevensopslag configureren in AEM 6](data-store-config.md)
   + [Revisie opschonen](revision-cleanup.md)
   + [AEM uitvoeren met TarMK Cold Standby](tarmk-cold-standby.md)
   + [RDBMS-ondersteuning in AEM 6.4](rdbms-support-in-aem.md)
   + [Oak-query&#39;s en indexering](queries-and-indexing.md)
   + [Indexering via de eiken-run-jar](indexing-via-the-oak-run-jar.md)
   + [Gebruiksscenario&#39;s voor indexeren van eikenrun.jar](oak-run-indexing-usecases.md)
   + [Probleemoplossing voor Oak-indexen](troubleshooting-oak-indexes.md)
   + [Opteren in verzameling van samengevoegde verbruiksstatistieken](opt-in-aggregated-usage-statistics.md)
   + [Definities van releasevoertuig bijwerken](update-release-vehicle-definitions.md)
   + [Problemen oplossen](troubleshooting.md)
+ AEM configureren {#configuring}
   + [Basisconfiguratieconcepten](configuring.md)
   + [Logboekregistratie](configure-logging.md)
   + [OSGi configureren](configuring-osgi.md)
   + [OSGi-configuratie-instellingen](osgi-configuration-settings.md)
   + [Modi uitvoeren](configure-runmodes.md)
   + [Webconsole](web-console.md)
   + [Replicatie](replication.md)
   + [Repliceren met wederzijdse SSL](mssl-replication.md)
   + [Problemen met replicatie oplossen](troubleshoot-rep.md)
   + [Verlopen van statische objecten](expiration-static-objects.md)
   + [Versie leegmaken](version-purging.md)
   + [Uw AEM-instantie bewaken en onderhouden](monitoring-and-maintaining.md)
   + [Taken verschuiven](offloading.md)
   + [Single Sign On](single-sign-on.md)
   + [Brontoewijzing](resource-mapping.md)
   + [HTTP via SSL inschakelen](/help/sites-administering/ssl-by-default.md)
   + [Consistentie- en reiscontroles](consistency-check.md)
   + [Richtlijnen voor prestaties](performance-guidelines.md)
   + [Optimalisatie van prestaties](configuring-performance.md)
   + [Prestatiehandleiding voor middelen](assets-performance-sizing.md)
   + [Hoe kan ik-artikelen configureren](ht-deploy.md)
   + [Geometrixsites verwijderen](removing-the-geometrixx-sites.md)
   + [Webconsole configureren](configuring-web-console.md)
+ Upgrade uitvoeren naar AEM 6.4 {#upgrading}
   + [Upgrade uitvoeren naar AEM 6.4](upgrade.md)
   + [Uw upgrade plannen](upgrade-planning.md)
   + [De complexiteit van upgrades beoordelen met de patroondetector](pattern-detector.md)
   + [Achterwaartse compatibiliteit in AEM 6.4](backward-compatibility.md)
   + [Upgradeprocedure](upgrade-procedure.md)
   + [Een op locatie uitgevoerde upgrade uitvoeren](in-place-upgrade.md)
   + [Lazy Content Migration](lazy-content-migration.md)
   + [Het CRX2Oak-migratiehulpprogramma gebruiken](using-crx2oak.md)
   + [Onderhoudstaken vóór upgrade](pre-upgrade-maintenance-tasks.md)
   + [Controles en probleemoplossing na upgrade](post-upgrade-checks-and-troubleshooting.md)
   + [Aangepaste zoekformulieren bijwerken](upgrading-custom-search-forms.md)
   + [Duurzame verbeteringen](sustainable-upgrades.md)
   + [Code en aanpassingen bijwerken](upgrading-code-and-customizations.md)
   + [Upgradestappen voor installatie van toepassingsservers](app-server-upgrade.md)
   + [Lijst met verouderde bundels die na de upgrade zijn verwijderd](obsolete-bundles.md)
+ Repositoregeling {#restructuring}
   + [Repositoregeling herstructurering in AEM 6.4](repository-restructuring.md)
   + [Herstructurering van de gemeenschappelijke opslagplaats in AEM 6.4](all-repository-restructuring-in-aem-6-4.md)
   + [Sites Repositoregeling Herstructurering AEM 6.4](sites-repository-restructuring-in-aem-6-4.md)
   + [Herstructurering van activa Bewaarinstelling in AEM 6.4](assets-repository-restructuring-in-aem-6-4.md)
   + [Herstructurering van de Dynamic Media in AEM 6.4](dynamicmedia-repository-restructuring-in-aem-6-4.md)
   + [Forms Repository Herstructurering in AEM 6.4](forms-repository-restructuring-in-aem-6-4.md)
   + [Herstructurering van de opslagplaats voor elektronische handel in AEM 6.4](ecommerce-repository-restructuring-in-aem-6-4.md)
   + [Herstructurering van de opslagplaats voor AEM Communities in punt 6.4](communities-repository-restructuring-in-aem-6-4.md)
+ eCommerce {#ecommerce}
   + [Overzicht eCommerce](ecommerce.md)
   + [SAP Commerce Cloud](sap-commerce-cloud.md)
   + [Salesforce Commerce Cloud](https://github.com/adobe/commerce-salesforce)
   + [Magento](https://www.adobe.io/apis/experiencecloud/commerce-integration-framework/integrations.html#!AdobeDocs/commerce-cif-documentation/master/integrations/02-AEM-Magento.md)
+ Best practices voor {#practices}
   + [Best practices implementeren](best-practices.md)
   + [Prestatieschema](performance-tree.md)
   + [Best practices voor het testen van prestaties](best-practices-for-performance-testing.md)
   + [Beste praktijken voor Vragen en het Indexeren](best-practices-for-queries-and-indexing.md)
   + [Aanbevelingen voor gebruikersinterface voor klanten](ui-recommendations.md)
   + [Prestaties en schaalbaarheid](performance.md)


<!--

To be removed:
[Quickstart for AEM Screens](setting-up-a-basic-project-screens.md)
[Device Control Center](device-control-center.md)
[repository-restructuring-in-aem64](repository-restructuring-in-aem64.md)
[Web Console] (configuring-web-console.md)
[Configuring and Deploying AEM Screens](configuring-screens-introduction.md)
[Kickstart Guide](kickstart-for-aem-screens.md)
/help/sites/deploying/using/performance-lp.md
/help/sites-deploying/do-not-delete-performance-guidelines-pdf.md
/help/sites-deploying/removing-the-geometrixx-sites.md
/help/sites-deploying/consistency-check.md

Redirects:
[(Enabling HTTP Over SSL)](config-ssl.md) redirect to /content/help/en/experience-manager/6-4/sites-administering/ssl-by-default
-->
