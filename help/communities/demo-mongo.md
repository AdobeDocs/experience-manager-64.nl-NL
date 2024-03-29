---
title: MongoDB voor demo instellen
seo-title: How to Setup MongoDB for Demo
description: Hoe te opstelling MSRP voor één auteursinstantie en één publiceer instantie
seo-description: How to setup MSRP for one author instance and one publish instance
uuid: d2035a9e-f05c-4f90-949d-7cdae9646750
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 0b126218-b142-4d33-a28c-a91ab4fe99ac
role: Admin
exl-id: e32fc619-6226-48c6-bbd7-1910963d1036
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '857'
ht-degree: 0%

---

# MongoDB voor demo instellen {#how-to-setup-mongodb-for-demo}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Inleiding {#introduction}

In deze zelfstudie wordt beschreven hoe u de installatie kunt uitvoeren [MSRP](msrp.md) for *één auteur* instantie en *één publicatie* -instantie.

Met deze opstelling, is de communautaire inhoud toegankelijk van zowel auteur als publicatiemilieu&#39;s zonder het moeten voorwaarts of omgekeerd door:sturen gebruiker geproduceerde inhoud (UGC).

Deze configuratie is geschikt voor *niet-productie* omgevingen zoals voor ontwikkeling en/of demonstratie.

**A *productie* milieu:**

* MongoDB uitvoeren met een replicaset
* SolrCloud gebruiken
* Meerdere uitgeversinstanties bevatten

## MongoDB {#mongodb}

### MongoDB installeren {#install-mongodb}

* MongoDB downloaden van [https://www.mongodb.org/](https://www.mongodb.org/)

   * Keuze van besturingssysteem:

      * Linux
      * Mac 10.8
      * Windows 7
   * Keuze van versie:

      * Gebruik minimaal versie 2.6


* Basisconfiguratie

   * Volg de installatie-instructies van MongoDB
   * Configureren voor goddelijk

      * Het is niet nodig om mongo&#39;s te configureren of te sharding
   * De geïnstalleerde MongoDB-map wordt aangeduid als &lt;mongo-install>
   * Het gedefinieerde pad naar de gegevensmap wordt &lt;mongo-dbpath>


* MongoDB kan op dezelfde host worden uitgevoerd als AEM of extern worden uitgevoerd

### MongoDB starten {#start-mongodb}

* &lt;mongo-install>/bin/mongod —dbpath &lt;mongo-dbpath>

Hiermee wordt een MongoDB-server gestart met de standaardpoort 27017.

* Gebruik voor Mac een hogere limiet met de beginmarkering &#39;ulimit -n 2048&#39;

>[!NOTE]
>
>Als MongoDB is gestart *na* AEM, **opnieuw opstarten** alles **AEM** instanties zodat ze verbinding maken met MongoDB.

### Optie voor demoproductie: MongoDB-replicaset instellen {#demo-production-option-setup-mongodb-replica-set}

De volgende opdrachten zijn een voorbeeld van het instellen van een replicaset met 3 knooppunten op localhost:

* bin/mongod —poort 27017 —dbpath data —replSet rs0&amp;
* bin/mongo

   * cfg = {&quot;_id&quot;: &quot;rs0&quot;,&quot;version&quot;: 1,&quot;leden&quot;: [{&quot;_id&quot;: 0,&quot;host&quot;: &quot;127.0.0.1:27017&quot;}]}
   * rs.initiate(cfg)

* bin/mongod —poort 27018 —dbpath data1 —replSet rs0&amp;
* bin/mongod —poort 27019 —dbpath data2 —replSet rs0&amp;
* bin/mongo

   * rs.add(&quot;127.0.0.1:27018&quot;)
   * rs.add(&quot;127.0.0.1:27019&quot;)
   * rs.status()

## Solr {#solr}

### Solo installeren {#install-solr}

* Solr. downloaden van [Apache Lucene](https://archive.apache.org/dist/lucene/solr/):

   * Geschikt voor elk besturingssysteem
   * Versie 4.10 of versie 5 gebruiken
   * Solr vereist Java 1.7 of hoger

* Basisconfiguratie

   * De instelling &#39;example&#39; volgen Solr
   * Er is geen service nodig
   * De geïnstalleerde Solr-map wordt &lt;solr-install>

### Solr voor AEM Communities configureren {#configure-solr-for-aem-communities}

Om een inzameling Solr voor MSRP voor demo te vormen, zijn er twee te nemen besluiten (selecteer de verbindingen aan belangrijkste documentatie voor details):

1. Solr uitvoeren in zelfstandige of [SolrCloud-modus](msrp.md#solrcloudmode)
1. Installeren [standaard](msrp.md#installingstandardmls) of [geavanceerd](msrp.md#installingadvancedmls) meertalig zoeken (MLS)

### Zelfstandige Solr {#standalone-solr}

De methode voor het uitvoeren van Solr kan verschillen, afhankelijk van de versie en wijze van installatie. De [Solo-naslaggids](https://archive.apache.org/dist/lucene/solr/ref-guide/) is de gezaghebbende documentatie.

Voor het gemak, gebruikend versie 4.10 als voorbeeld, begin Solr op standalone wijze:

* cd naar &lt;solrinstall>/example
* java -jar start.jar

Hierdoor wordt een Solr HTTP-server gestart met de standaardpoort 8983. U kunt naar de Solr Console bladeren om een Solr console voor het testen te krijgen.

* standaard solr-console: [http://localhost:8983/solr/](http://localhost:8983/solr/)

>[!NOTE]
>
>Als Solr Console niet beschikbaar is, controleer de logboeken onder &lt;solrinstall>/example/logs. Kijk of SOLR probeert te binden aan een specifieke hostname die niet kan worden opgelost (bijvoorbeeld &quot;user-macbook-pro&quot;).
Als dat het geval is, werkt u het etc/hosts-bestand bij met een nieuwe vermelding voor deze hostnaam (bijvoorbeeld 127.0.0.1 user-macbook-pro) en start Solr op de juiste wijze.

### SolrCloud {#solrcloud}

U kunt een eenvoudige solrCloud-instelling (geen productie) uitvoeren door solr te starten met:

* java -Dbootstrap_confdir=./solr/collection1/conf -Dbootstrap_conf=true -DzkRun -jar start.jar

## MongoDB identificeren als een gemeenschappelijke winkel {#identify-mongodb-as-common-store}

Start de auteur en publiceer AEM indien nodig.

Als AEM actief was voordat MongoDB werd gestart, moeten de AEM instanties opnieuw worden gestart.

Volg de instructies op de hoofddocumentatiepagina: [MSRP - MongoDB Common Store](msrp.md)

## Testen {#test}

Als u de algemene opslag van MongoDB wilt testen en verifiëren, plaatst u een opmerking op de publicatieinstantie en bekijkt u deze op de auteurinstantie, en bekijkt u de UGC in MongoDB en Solr:

1. Blader in de publicatie-instantie naar de [Community Components Guide](http://localhost:4503/content/community-components/en/comments.html) en selecteert u de component Opmerkingen.
1. Meld u aan om een opmerking te plaatsen:
1. Typ tekst in het tekstinvoervak voor opmerkingen en klik op **[!UICONTROL Post]**

   ![chlimage_1-191](assets/chlimage_1-191.png)

1. U kunt de opmerking alleen weergeven op de knop [auteurinstantie](http://localhost:4502/content/community-components/en/comments.html) (waarschijnlijk nog steeds aangemeld als beheerder/beheerder).

   ![chlimage_1-192](assets/chlimage_1-192.png)

   Opmerking: terwijl er JCR-knooppunten onder de *asipath* Op auteur, zijn deze voor het kader SCF. De werkelijke UGC bevindt zich niet in de JCR, maar in de MongoDB.

1. UGC weergeven in mongodb **[!UICONTROL Communities > Collections > Content]**

   ![chlimage_1-193](assets/chlimage_1-193.png)

1. De UGC in Solr weergeven:

   * Bladeren naar Solr-dashboard: [http://localhost:8983/solr/](http://localhost:8983/solr/)
   * Gebruiker `core selector` om `collection1`
   * Selecteer `Query`
   * Selecteer `Execute Query`

   ![chlimage_1-194](assets/chlimage_1-194.png)

## Problemen oplossen {#troubleshooting}

### Geen UGC weergegeven {#no-ugc-appears}

1. Controleer of MongoDB op de juiste wijze is geïnstalleerd en uitgevoerd.

1. Zorg ervoor MSRP is gevormd om de standaardleverancier te zijn:

   * Ga bij alle auteurs en publiceer AEM [Opslagconfiguratieconsole](srp-config.md)

   of controleer de AEM opslagplaats:

   * In JCR, als [/etc/socialconfig](http://localhost:4502/crx/de/index.jsp#/etc/socialconfig/)

      * Bevat geen [srpc](http://localhost:4502/crx/de/index.jsp#/etc/socialconfig/srpc) node, it means the storage provider is JSRP
      * Als het srpc-knooppunt bestaat en het knooppunt bevat [standaardconfiguratie](http://localhost:4502/crx/de/index.jsp#/etc/socialconfig/srpc/defaultconfiguration), zouden de eigenschappen van de standaardconfiguratie MSRP moeten bepalen om de standaardleverancier te zijn


1. Zorg ervoor dat AEM opnieuw is gestart nadat MSRP is geselecteerd.
