---
title: Gemeenschappen inzetten
seo-title: Deploying Communities
description: AEM Communities implementeren
seo-description: How to deploy AEM Communities
uuid: 1f7faf1a-a339-4eaa-b728-b9110cb350a8
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
content-type: reference
topic-tags: deploying
discoiquuid: d0249609-2a9c-4d3b-92ee-dbc5fbdeaac6
exl-id: 0b7496f0-0b3c-4d12-a659-d95744157f14
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '2192'
ht-degree: 0%

---

# Gemeenschappen inzetten {#deploying-communities}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Vereisten {#prerequisites}

* [AEM 6,4 Platform](../../help/sites-deploying/deploy.md)

* AEM Communities-licentie

* Optionele licenties voor:

   * [Functies van Adobe Analytics for Communities](analytics.md)
   * [MongoDB voor MSRP](msrp.md)
   * [Adobe Cloud voor ASRP](asrp.md)

## Controlelijst voor installatie {#installation-checklist}

**Voor de [AEM](../../help/sites-deploying/deploy.md#what-is-aem)**

* Nieuwste installeren [AEM 6.4 Updates](#aem-updates)

* Als u de standaardpoorten niet gebruikt (4502, 4503), dan [replicatieagents configureren](#replication-agents-on-author)
* [de cryptosleutel repliceren](#replicate-the-crypto-key)
* Als we de globalisering ondersteunen, [geautomatiseerde omzetting instellen](../../help/sites-administering/translation.md)

   (voorbeeldinstelling is beschikbaar voor ontwikkeling)

**Voor de [Gemeenschappen](overview.md)**

* Indien het opstellen van een [publicatiebedrijf](../../help/sites-deploying/recommended-deploys.md#tarmk-farm), [de primaire uitgever identificeren](#primary-publisher)

* [De tunnelservice inschakelen](#tunnel-service-on-author)
* [Sociale aanmelding inschakelen](social-login.md#adobe-granite-oauth-authentication-handler)
* [Adobe Analytics configureren](analytics.md)
* Een [standaard e-mailservice](email.md)
* De keuze voor [gedeelde UGC-opslag](working-with-srp.md) (**SRP**)

   * Indien MongoDB SRP [(MSRP)](msrp.md)

      * [MongoDB installeren en configureren](msrp.md#mongodb-configuration)
      * [Solr configureren](solr.md)
      * [Selecteer MSRP](srp-config.md)
   * Indien relationele database SRP [(DSRP)](dsrp.md)

      * [Installeer het JDBC-stuurprogramma voor MySQL](#jdbc-driver-for-mysql)
      * [Installeer en vorm MySQL voor DSRP](dsrp-mysql.md)
      * [Solr configureren](solr.md)
      * [DSRP selecteren](srp-config.md)
   * Indien Adobe SRP [(ASRP)](asrp.md)

      * Met uw accountvertegenwoordiger samenwerken voor provisioning
      * [Selecteer ASRP](srp-config.md)
   * Als JCR SRP [(JSRP)](jsrp.md)

      * Geen gedeelde UGC-opslag:

         * UGC wordt nooit gerepliceerd
         * UGC is alleen zichtbaar op AEM instantie of cluster waarin de UGC is ingevoerd
      * Standaard is JSRP

   Voor de **[enablement, functie](overview.md#enablement-community)**

   * [Mpeg installeren en configureren](ffmpeg.md)
   * [Installeer het JDBC-stuurprogramma voor MySQL](#jdbc-driver-for-mysql)
   * [AEM Communities SCORM-engine installeren](#scorm-package)
   * [MySQL voor activering installeren en configureren](mysql.md)






## Laatste releases {#latest-releases}

AEM 6.4 Communautaire algemene vergadering omvat het communautaire pakket. Informatie over updates van AEM 6.4 [Gemeenschappen](/help/release-notes/release-notes.md#experience-manager-communities), raadpleegt u [AEM 6.4 Opmerkingen bij de release](/help/release-notes/release-notes.md#release-information).

### AEM 6.4 Updates {#aem-updates}

Vanaf AEM 6.3 worden updates aan de Gemeenschappen geleverd als onderdeel van AEM Cumulative Fix Packs en Service Packs.

Voor de meest recente updates van AEM 6.4 moet u controleren of [Adobe Experience Manager 6.4 Cumulatief repareren van pakketten en servicepacks](https://helpx.adobe.com/experience-manager/aem-releases-updates.html).

### Versiehistorie {#version-history}

Net als bij AEM 6.4 en hoger maken AEM Communities-functies en hotfixes deel uit van AEM Communities-pakketten voor cumulatieve probleemoplossingen en servicepacks. Er zijn dus geen aparte kenmerkpakketten.

### JDBC-stuurprogramma voor MySQL {#jdbc-driver-for-mysql}

Twee eigenschappen van Gemeenschappen gebruiken een gegevensbestand MySQL:

* Voor [inschakelen](enablement.md): SCORM-activiteiten en -studenten opnemen
* Voor [DSRP](dsrp.md): door de gebruiker gegenereerde inhoud opslaan (UGC)

De MySQL-connector moet afzonderlijk worden opgehaald en geïnstalleerd.

De noodzakelijke stappen zijn:

1. Download het ZIP-archief van [https://dev.mysql.com/downloads/connector/j/](https://dev.mysql.com/downloads/connector/j/)

   * Versie moet >= 5.1.38 zijn

1. mysql-connector-java- extraheren&lt;version>-bin.jar (bundel) uit het archief

1. Gebruik de webconsole om de bundel te installeren en te starten:

   * Bijvoorbeeld http://localhost:4502/system/console/bundles
   * Selecteer **`Install/Update`**
   * Bladeren... om de bundel te selecteren die uit het gedownloade ZIP-archief is geëxtraheerd
   * Controleren of *JDBC-stuurprogramma van oracle Corporation voor MySQLcom.mysql.jdbc* is actief en start deze als dit niet het geval is (of controleer de logboeken)

1. Als het installeren op een bestaande plaatsing nadat JDBC is gevormd, dan opnieuw bindt JDBC aan de nieuwe schakelaar door de configuratie JDBC van de Webconsole op te slaan:

   * Bijvoorbeeld http://localhost:4502/system/console/configMgr
   * Zoeken `Day Commons JDBC Connections Pool` configuratie
   * Selecteren om te openen
   * Selecteer `Save`

1. De stappen 3 en 4 op alle auteur herhalen en instanties publiceren

Meer informatie over het installeren van bundels vindt u op de [Webconsole](/help/sites-deploying/web-console.md#bundles) pagina.

#### Voorbeeld: MySQL-connectorbundel is geïnstalleerd {#example-installed-mysql-connector-bundle}

![chlimage_1-410](assets/chlimage_1-410.png)

### SCORM-pakket {#scorm-package}

Shareable Content Object Reference Model (SCORM) is een verzameling standaarden en specificaties voor e-learning. SCORM definieert ook hoe inhoud kan worden verpakt in een overdraagbaar ZIP-bestand.

De AEM Communities SCORM-engine is vereist voor de [inschakelen](overview.md#enablement-community) gebruiken. Scorepakketten die worden ondersteund in AEM Communities 6.4-versie zijn:

* **[cq -social- scorm -package, versie 1.2.11](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Fadobe%2Fpackages%2Fcq640%2Fsocial%2Fscorm%2Fcq-social-scorm-pkg)**. Dit SCORM-pakket wordt ondersteund door alle versies van AEM 6.4.

* **[cq -social- scorm -package, versie 2.2.2](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Fadobe%2Fpackages%2Fcq640%2Fsocial%2Fscorm%2Fcq-social-scorm-2017-pkg)** include [SCORM 2017.1](https://rusticisoftware.com/blog/scorm-engine-2017-released/) motor. Dit SCORM-pakket wordt ondersteund AEM 6.4.2.x-gemeenschappen.

Voor een nieuwe installatie van de SCORM-engine, bevat het pakket [SCORM 2017.1](https://rusticisoftware.com/blog/scorm-engine-2017-released/) (die [  cq -social- scorm -package, versie 2.2.2](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Fadobe%2Fpackages%2Fcq640%2Fsocial%2Fscorm%2Fcq-social-scorm-2017-pkg)) moet worden gebruikt. zodat u de leermiddelen kunt spelen die door SCORM 2017 worden gesteund.

<!--This section used to be an accordion until converted to straight Markdown. When accordions are enabled, revert-->

### Een SCORM-pakket voor de eerste keer installeren

1. Installeer de **[cq-social-scorm-package, versie 2.2.2](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Fadobe%2Fpackages%2Fcq640%2Fsocial%2Fscorm%2Fcq-social-scorm-2017-pkg).**
1. Downloaden **`/libs/social/config/scorm/database_scormengine_data.sql`** van cq instantie en voer het in mysql server uit om een bevorderd schema te creëren scormEngineDB.
1. Toevoegen `/content/communities/scorm/RecordResults` in de eigenschap Uitgesloten paden in het CSRF-filter uit `https://<hostname>;:<port>/system/console/configMgr` op uitgevers.

Bestaande SCORM-installaties kunnen worden bijgewerkt naar [**cq-social-scorm-package, versie 2.2.2**](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Fadobe%2Fpackages%2Fcq640%2Fsocial%2Fscorm%2Fcq-social-scorm-2017-pkg) (gebruikt [SCORM 2017.1](https://rusticisoftware.com/blog/scorm-engine-2017-released/)), als de geschreven cursusinhoud SCORM 2017.1 vereist.

>[!NOTE]
>
>Voor de upgrade naar het SCORM 2017.1-pakket is migratie van de bestaande database vereist (zoals verder wordt uitgelegd).

<!--This section used to be an accordion until converted to straight Markdown. When accordions are enabled, revert-->

### Om versie van uw motor te bevorderen SCORM

1. Maak een back-up van het schema ScormEngineDB.
1. Installeer de **[cq-social-scorm-package, versie 2.2.2](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Fadobe%2Fpackages%2Fcq640%2Fsocial%2Fscorm%2Fcq-social-scorm-2017-pkg).**
1. Download het pakket van `/libs/social/config/scorm/ScormEngine.zip` en extraheren.
1. Ga naar **Installatieprogramma** map van de uitgepakte directory.
1. Bijwerken `SystemDatabaseConnectionString` met uw `scorm db connection url` in bestand **[!UICONTROL EngineInstall.xml]**.
1. Voer het mysql-schema-upgradeprogramma uit in de installatiemap met de opdracht:

   `java -Dlogback.configurationFile=logback.xml -cp "lib/*" RusticiSoftware.ScormContentPlayer.Logic.Upgrade.ConsoleApp EngineInstall.xml`
1. Monitor `engine_upgrade.log` bestand voor een fout of schema-upgrade.
1. Toevoegen `/content/communities/scorm/RecordResults` in **[!UICONTROL Excluded Paths]** eigenschap in CSRF-filter van `https://<hostname>:<port>/system/console/configMgr` op uitgevers.

### SCORM-registratie {#scorm-logging}

Zoals geïnstalleerd, wordt al enablement activiteit uitgebreid geregistreerd aan de systeemconsole.

Indien gewenst, kan het logboekniveau aan WARN voor `RusticiSoftware.*` pakket.

Voor het werken met logboeken, zie [Werken met auditrecords en logbestanden](../../help/sites-deploying/monitoring-and-maintaining.md#working-with-audit-records-and-log-files).

### Geavanceerde MLS AEM {#aem-advanced-mls}

Voor de inzameling SRP (MSRP of DSRP) om geavanceerde meertalige onderzoek (MLS) te steunen, worden nieuwe stop-ins Solr vereist naast een douaneschema en de configuratie Solr. Alle vereiste items worden verpakt in een ZIP-bestand dat kan worden gedownload.

De geavanceerde MLS-download (ook wel &#39;phasetwo&#39; genoemd) is beschikbaar in de gegevensopslagruimte van de Adobe:

* AEM-SOLR-MLS-fasetwo

   Ga voor het geavanceerde MLS-pakket naar [Geavanceerde MLS AEM](deploy-communities.md#aem-advanced-mls) in de op te stellen sectie van de documentatie.

   * Versie 1.2.40, 6 april 2016
   * Download AEM-SOLR-MLS-phasetwo-1.2.40.zip

Ga voor meer informatie en installatie-informatie naar [Solr-configuratie](solr.md) voor SRP.

### Info over Koppelingen naar pakket delen {#about-links-to-package-share}

**Pakketten zichtbaar in Adobe AEM Cloud**

Voor de koppelingen naar pakketten op deze pagina is geen actieve versie van AEM vereist, aangezien deze zijn bestemd voor het verpakken van delen op `adobeaemcloud.com`. Als de pakketten kunnen worden weergegeven, worden de `Install`-knop is voor het installeren van de pakketten op een door Adobe gehoste site. Als u van plan bent op een lokale AEM te installeren, selecteert u `Install`resulteert in een fout.

**Installeren op lokale AEM**

De pakketten installeren die zichtbaar zijn in `adobeaemcloud.com` op een lokale AEM moet het pakket eerst naar een lokale schijf worden gedownload:

* Selecteer **[!UICONTROL Assets]** tab
* Selecteer **[!UICONTROL download to disk]**

Gebruik pakketbeheer in de lokale AEM-instantie (bijvoorbeeld [http://localhost:4502/crx/packmgr/](http://localhost:4502/crx/packmgr/)), om te uploaden naar de lokale AEM.

U kunt het pakket ook openen met het pakket door het lokale AEM te delen (bijvoorbeeld [http://localhost:4502/crx/packageshare/](http://localhost:4502/crx/packageshare/)), de `Download`De knop wordt gedownload naar de pakketdataopslag van de lokale AEM.

Eenmaal in de pakketopslagplaats van de lokale AEM-instantie, gebruikt u pakketbeheer om het pakket te installeren.

Ga voor meer informatie naar [Werken met pakketten](../../help/sites-administering/package-manager.md#package-share).

## Aanbevolen implementaties {#recommended-deployments}

In AEM Communities, wordt een gemeenschappelijke opslag gebruikt om gebruiker geproduceerde inhoud (UGC) op te slaan en vaak bedoeld als [Storage Resource Provider (SRP)](working-with-srp.md). De geadviseerde plaatsingscentra bij het kiezen van een optie SRP voor de gemeenschappelijke opslag.

De gemeenschappelijke opslag steunt matiging van, en analyses op UGC in het publicatiemilieu terwijl het elimineren van de behoefte aan [replicatie](sync.md) van UGC.

* [Community Content Store](working-with-srp.md): bespreekt de opslagopties SRP voor AEM gemeenschappen

* [Aanbevolen topologieën](topologies.md): bespreekt de topologie om afhankelijk van gebruiksgeval en keus te gebruiken SRP

## Bijwerken {#upgrading}

Wanneer u een upgrade uitvoert naar het AEM 6.4-platform van eerdere versies van AEM, is het belangrijk om Upgrade naar AEM 6.4 te lezen.

Naast het upgraden van het platform, leest u [Upgrade uitvoeren naar AEM Communities 6.4](upgrade.md) voor meer informatie over wijzigingen in de Gemeenschappen.

## Configuraties {#configurations}

### Primaire uitgever {#primary-publisher}

Wanneer de gekozen implementatie een [publicatiebedrijf](topologies.md#tarmk-publish-farm)moet vervolgens één AEM publicatieexemplaar worden geïdentificeerd als de **`primary publisher`** voor activiteiten die niet in alle gevallen moeten plaatsvinden, zoals functies die **meldingen** of **Adobe Analytics**.

Standaard worden de `AEM Communities Publisher Configuration` De configuratie OSGi wordt gevormd met **`Primary Publisher`** checkbox controleerde, dusdanig dat alle publiceer instanties in een publicatielandbouwbedrijf zich als primair zouden identificeren.

Daarom moet **bewerk de configuratie op alle secundaire publicatieinstanties** om de controle van **`Primary Publisher`** selectievakje.

![chlimage_1-411](assets/chlimage_1-411.png)

Voor alle andere (secundaire) publiceer instanties in publiceer landbouwbedrijf:

* Aanmelden met beheerdersrechten
* Toegang krijgen tot [webconsole](../../help/sites-deploying/configuring-osgi.md)

   * Bijvoorbeeld: [http://localhost:4503/system/console/configMgr](http://localhost:4503/system/console/configMgr)

* Zoek de `AEM Communities Publisher Configuration`
* Het bewerkingspictogram selecteren
* Schakel het selectievakje **[!UICONTROL Primary Publisher]** box
* Selecteer **[!UICONTROL Save]**

### Replicatieagents op auteur {#replication-agents-on-author}

Replicatie wordt gebruikt voor site-inhoud die in de publicatieomgeving is gemaakt, zoals groepen uit de gebruikersgemeenschap, en voor het beheren van leden en lidgroepen vanuit de auteursomgeving met behulp van de [tunneldienst](#tunnel-service-on-author).

Voor de primaire uitgever zorg ervoor [Replication Agent Config](../../help/sites-deploying/replication.md) geeft de publicatieserver en de geautoriseerde gebruiker correct aan. De standaard geoorloofde gebruiker, `admin,` beschikt al over de juiste machtigingen (is lid van `Communities Administrators`).

Als een andere gebruiker over de juiste machtigingen moet beschikken, moet hij of zij als lid aan de `administrators` gebruikersgroep (ook lid van `Communities Administrators`).

Er zijn twee replicatieagenten in het auteursmilieu die de vervoerconfiguratie nodig hebben correct worden gevormd.

* De console van de Replicatie van de toegang op auteur

   * Vanuit globale navigatie: **[!UICONTROL Tools > Deployment > Replication > Agents on author]**

* Volg de zelfde procedure voor beide agenten:

   * **Standaardagent (publiceren)**
   * **Reverse Replication Agent (publiceren reverse)**

      1. Selecteer de agent
      1. Selecteer **[!UICONTROL edit]**
      1. Selecteer **[!UICONTROL Transport]** tab
      1. Indien niet poort `4503`, bewerkt u de **[!UICONTROL URI]** om de juiste poort op te geven
      1. Indien niet gebruiker `admin`, bewerkt u de **[!UICONTROL User]** en **[!UICONTROL Password]** om een lid van de `administrators` gebruikersgroep

In de volgende afbeeldingen ziet u de resultaten van het wijzigen van de poort van 4503 in 6103 door:

#### Standaardagent (publiceren) {#default-agent-publish}

![chlimage_1-412](assets/chlimage_1-412.png)

#### Reverse Replication Agent (publiceren reverse) {#reverse-replication-agent-publish-reverse}

![chlimage_1-413](assets/chlimage_1-413.png)

### Tunnelservice op auteur {#tunnel-service-on-author}

Wanneer u de ontwerpomgeving gebruikt voor [sites maken](sites-console.md), [site-eigenschappen wijzigen](sites-console.md#modifying-site-properties) of [leden van de gemeenschap beheren](members.md), is het noodzakelijk om toegang te krijgen tot leden (gebruikers) die zijn geregistreerd in de publicatieomgeving, niet tot gebruikers die zijn geregistreerd bij de auteur.

De tunneldienst verleent deze toegang gebruikend de replicatieagent op auteur.

Om de tunneldienst toe te laten:

* Aan **auteur**
* Aanmelden met beheerdersrechten
* Als de uitgever niet localhost is:4503 of de vervoergebruiker niet `admin`,

   Vervolgens [vorm de replicatieagent](#replication-agents-on-author)

* Toegang krijgen tot [Webconsole](../../help/sites-deploying/configuring-osgi.md)

   * Bijvoorbeeld: [http://localhost:4502/system/console/configMgr](http://localhost:4502/system/console/configMgr)

* Zoek de `AEM Communities Publish Tunnel Service`
* Het bewerkingspictogram selecteren
* Controleer de **[!UICONTROL enable]** box
* Selecteer **[!UICONTROL Save]**

![chlimage_1-414](assets/chlimage_1-414.png)

### De cryptosleutel dupliceren {#replicate-the-crypto-key}

Er zijn twee eigenschappen van AEM Communities die alle AEM serverinstanties vereisen om de zelfde encryptiesleutels te gebruiken. Dit zijn [Analyse](analytics.md) en [ASRP](asrp.md).

Vanaf AEM 6.3 wordt het sleutelmateriaal opgeslagen in het bestandssysteem en niet langer in de gegevensopslagruimte.

Om het belangrijkste materiaal van auteur aan alle andere instanties te kopiëren is het noodzakelijk:

* Toegang krijgen tot de AEM instantie, doorgaans een instantie van de auteur, die het te kopiëren toetsmateriaal bevat

   * Zoek de `com.adobe.granite.crypto.file` bundelen in het lokale bestandssysteem

      Bijvoorbeeld,

      * `<author-aem-install-dir>/crx-quickstart/launchpad/felix/bundle21`
      * De `bundle.info` bestand zal de bundel identificeren
   * Navigeren in de gegevensmap

      Bijvoorbeeld,

      * `<author-aem-install-dir>/crx-quickstart/launchpad/felix/bundle21/data`
   * Kopieer de hoofd- en primaire knoopdossiers



* Voor elke AEM

   * Navigeren in de gegevensmap

      Bijvoorbeeld,

      * `<publish-aem-install-dir>/crx-quickstart/launchpad/felix/bundle21/data`
   * Plak de twee eerder gekopieerde bestanden
   * Het is noodzakelijk [De Granite Crypto-bundel vernieuwen](#refresh-the-granite-crypto-bundle) als de AEM momenteel actief is


>[!CAUTION]
>
>Als een andere veiligheidseigenschap reeds is gevormd die op de crypto sleutels gebaseerd is, dan het herhalen van de crypto sleutels kon de configuratie beschadigen. Voor hulp, [contact opnemen met de klantenservice](https://helpx.adobe.com/marketing-cloud/contact-support.html).

#### Replicatie opslagplaats {#repository-replication}

Als het sleutelmateriaal in de bewaarplaats wordt opgeslagen, zoals het geval was voor AEM 6.2 en eerder, kan worden behouden door de volgende systeemeigenschap op te geven bij het eerste opstarten van elke AEM instantie (die de initiële opslagplaats creëert):

* `-Dcom.adobe.granite.crypto.file.disable=true`

>[!NOTE]
>
>Het is belangrijk te controleren of de [replicatieagent bij auteur](#replication-agents-on-author) correct is geconfigureerd.

Met het belangrijkste materiaal dat in de bewaarplaats wordt opgeslagen, is de manier om de crypto sleutel van auteur aan andere instanties te herhalen als volgt:

Gebruiken [CRXDE Lite](../../help/sites-developing/developing-with-crxde-lite.md):

* bladeren naar [https://&lt;server>:&lt;port>/crx/de](http://localhost:4502/crx/de)
* selecteren `/etc/key`
* open `Replication` tab
* selecteren `Replicate`

* [De Granite Crypto-bundel vernieuwen](#refresh-the-granite-crypto-bundle)

![chlimage_1-415](assets/chlimage_1-415.png)

#### De graniet-cryptobundel vernieuwen {#refresh-the-granite-crypto-bundle}

* Ga bij elke publicatie-instantie naar de knop [Webconsole](../../help/sites-deploying/configuring-osgi.md)

   * Bijvoorbeeld: [https://&lt;server>:&lt;port>/systeem/console/bundels](http://localhost:4503/system/console/bundles)

* Zoeken `Adobe Granite Crypto Support` bundle (com.adobe.granite.crypto)
* Selecteer **[!UICONTROL Refresh]**

![chlimage_1-416](assets/chlimage_1-416.png)

* Na een ogenblik **Succes** wordt weergegeven:

   `Operation completed successfully.`

### Apache HTTP Server {#apache-http-server}

Als u de Apache HTTP-server gebruikt, moet u ervoor zorgen dat u de juiste servernaam gebruikt voor alle relevante vermeldingen.

Wees vooral voorzichtig met het gebruik van de juiste servernaam, niet `localhost`in de `RedirectMatch`.

#### httpd.conf, voorbeeld {#httpd-conf-sample}

```shell
<IfModule alias_module>
     # XAMPP does not have a favicon; this prevents any 404 errors which may arise.
     Redirect 404 /favicon.ico
     <Location /favicon.ico>
         ErrorDocument 404 "No favicon"
     </Location>

    # Return from "Sign Out" generates response header directing you to "/", generating a 404 error
    # The RedirectMatch resolves it correctly when modified for the target Community Site:
    RedirectMatch ^/$ https://[server name]/content/sites/engage/en.html
 ...
 </IfModule>
```

### Dispatcher {#dispatcher}

Als u een Dispatcher gebruikt, raadpleegt u:

* AEM [Dispatcher](https://helpx.adobe.com/experience-manager/dispatcher/using/dispatcher.html) documentatie
* [Dispatcher installeren](https://helpx.adobe.com/experience-manager/dispatcher/using/dispatcher-install.html)
* [Dispatcher configureren voor Gemeenschappen](dispatcher.md)
* [Bekende problemen](troubleshooting.md#dispatcher-refetch-fails)

## Verwante documentatie van Gemeenschappen {#related-communities-documentation}

* Bezoek [Communitysites beheren](administer-landing.md) om over het creëren van een communautaire plaats te leren, vormend communautaire plaatssjablonen, het modereren van communautaire inhoud, het leiden van leden, en het vormen overseinen.

* Bezoek [Ontwikkelingsgemeenschappen](communities.md) voor meer informatie over het raamwerk voor sociale componenten (SCF) en het aanpassen van onderdelen en functies van Gemeenschappen.

* Bezoek [Componenten van Gemeenschappen ontwerpen](author-communities.md) om te leren om met te schrijven en de componenten van de Gemeenschappen te vormen.
