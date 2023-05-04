---
title: Upgradestappen voor installatie van toepassingsservers
seo-title: Upgrade Steps for Application Server Installations
description: Leer hoe te om instanties van AEM te bevorderen die via de Servers van de Toepassing worden opgesteld.
seo-description: Learn how to upgrade instances of AEM that are deployed via Application Servers.
uuid: df3fa715-af4b-4c81-b2c5-130fbc82f395
contentOwner: sarchiz
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: upgrading
content-type: reference
discoiquuid: c427c8b6-eb94-45fa-908f-c3d5a337427d
feature: Upgrading
exl-id: 1c72093e-82c8-49ad-bd3c-d61904aaab28
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 0%

---

# Upgradestappen voor installatie van toepassingsservers{#upgrade-steps-for-application-server-installations}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Deze sectie beschrijft de procedure die moet worden gevolgd om AEM voor de installaties van de Server van de Toepassing bij te werken.

Alle voorbeelden in deze procedure gebruiken JBoss als Server van de Toepassing en impliceren dat u een werkende versie van AEM reeds opgesteld hebt. De procedure is bedoeld om upgrades te documenteren die zijn uitgevoerd vanaf **AEM versie 5.6 t/m 6.3**.

1. Start eerst JBoss. In de meeste gevallen kunt u dit doen door de `standalone.sh` startmanuscript, door dit bevel van de terminal in werking te stellen:

   ```shell
   jboss-install-folder/bin/standalone.sh
   ```

1. Als AEM 5.6 al is geïmplementeerd, controleert u of de bundels correct werken door:

   ```shell
   wget https://<serveraddress:port>/cq/system/console/bundles
   ```

1. Verwijder vervolgens AEM 5.6:

   ```shell
   rm jboss-install-folder/standalone/deployments/cq.war
   ```

1. Stop JBoss.

1. Migreer nu de opslagplaats met het crx2oak-migratiehulpprogramma:

   ```shell
   java -jar crx2oak.jar crx-quickstart/repository/ crx-quickstart/oak-repository
   ```

   >[!NOTE]
   >
   >In dit voorbeeld is de eikenopslagplaats de tijdelijke map waarin de nieuwe geconverteerde opslagplaats zich bevindt. Voordat u deze stap uitvoert, moet u de nieuwste versie crx2oak.jar gebruiken.

1. Verwijder de benodigde eigenschappen in het bestand sling.properties door het volgende te doen:

   1. Open het bestand op `crx-quickstart/launchpad/sling.properties`
   1. Staptekst Verwijder de volgende eigenschappen en sla het bestand op:

      1. `sling.installer.dir`
      1. `felix.cm.dir`
      1. `granite.product.version`
      1. `org.osgi.framework.system.packages`
      1. `osgi-core-packages`
      1. `osgi-compendium-services`
      1. `jre-*`
      1. `sling.run.mode.install.options`

1. Verwijder de bestanden en mappen die u niet meer nodig hebt. De items die u specifiek moet verwijderen zijn:

   * De **startblok/startmap**. U kunt het schrappen door het volgende bevel in de terminal in werking te stellen: `rm -rf crx-quickstart/launchpad/startup`
   * De **base.jar, bestand**: `find crx-quickstart/launchpad -type f -name "org.apache.sling.launchpad.base.jar*" -exec rm -f {} \`
   * De **BootstrapCommandFile_timestamp.txt, bestand**: `rm -f crx-quickstart/launchpad/felix/bundle0/BootstrapCommandFile_timestamp.txt`

1. Kopieer de nieuwe gemigreerde segmentstore naar de juiste locatie:

   ```shell
   mv crx-quickstart/oak-repository/segmentstore crx-quickstart/repository/segmentstore
   ```

1. Kopieer ook de datastore:

   ```shell
   mv crx-quickstart/repository/repository/datastore crx-quickstart/repository/datastore
   ```

1. Daarna, moet u de omslag tot stand brengen die de configuraties OSGi zal bevatten die met de nieuwe promotieinstantie zullen worden gebruikt. Meer specifiek moet een map met de naam install worden gemaakt onder **crx-quickstart**.

1. Creëer nu de knoopopslag en de gegevensopslag die met AEM 6.3 zullen worden gebruikt. U kunt dit doen door twee bestanden te maken met de volgende namen onder **crx-quickstart\install**:

   * `org.apache.jackrabbit.oak.segment.SegmentNodeStoreService.cfg`

   * `org.apache.jackrabbit.oak.plugins.blob.datastore.FileDataStore.cfg`

   Deze twee dossiers zullen AEM vormen om een TarMK knoopopslag en een de gegevensopslag van het Dossier te gebruiken.

1. Bewerk de configuratiebestanden om deze gebruiksklaar te maken. Meer specifiek:

   * Voeg de volgende regel toe aan **org.apache.jackrabbit.oak.segment.SegmentNodeStoreService.config**:

      `customBlobStore=true`

   * Voeg vervolgens de volgende regels toe aan **org.apache.jackrabbit.oak.plugins.blob.datastore.FileDataStore.config**:

      ```
      path=./crx-quickstart/repository/datastore
       minRecordLength=4096
      ```

1. Verwijder de crx2 runmode door te lopen:

   ```shell
   find crx-quickstart/launchpad -type f -name "sling.options.file" -exec rm -rf {} \
   ```

1. U moet nu de uitvoeringswijzen in het AEM 6.3 oorlogsdossier veranderen. Hiertoe maakt u eerst een tijdelijke map waarin de AEM 6.3-oorlog is ondergebracht. De naam van de map in dit voorbeeld wordt **temp**. Nadat het oorlogsbestand is gekopieerd, pakt u de inhoud uit door de inhoud uit te voeren vanuit de tijdelijke map:

   ```shell
   jar xvf aem-quickstart-6.3.0.war
   ```

1. Als de inhoud is geëxtraheerd, gaat u naar de **WEB-INF** en bewerk de map `web.xml` bestand om de uitvoermodi te wijzigen. Als u de locatie wilt zoeken waar deze in de XML zijn ingesteld, zoekt u de `sling.run.modes` tekenreeks. Als u deze eenmaal hebt gevonden, wijzigt u de uitvoeringsmodi in de volgende coderegel, die standaard is ingesteld op auteur:

   ```shell
   <param-value >author</param-value>
   ```

1. Wijzig de bovenstaande auteurwaarde en stel de uitvoeringsmodi in op: auteur,crx3,crx3tar Het laatste codeblok moet er als volgt uitzien:

   ```
   <init-param>
   <param-name>sling.run.modes</param-name>
   <param-value>author,crx3,crx3tar</param-value>
   </init-param>
   <load-on-startup>100</load-on-startup>
   </servlet>
   ```

1. De pot opnieuw maken met de gewijzigde inhoud:

   ```shell
   jar cvf aem62.war
   ```

1. Implementeer ten slotte het nieuwe oorlogsbestand:

   ```shell
   cp temp/aem62.war jboss-install-folder/standalone/deployments/aem61.war
   ```
