---
title: Technische vereisten
seo-title: Technische vereisten
description: Een lijst met de ondersteunde client- en serverplatforms voor AEM.
seo-description: Een lijst met de ondersteunde client- en serverplatforms voor AEM.
uuid: d5bdcd41-3585-41f7-860d-8068a2931a72
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: platform
discoiquuid: 4d3c4650-3e2a-43b1-ad2d-8d0ae2254ca9
exl-id: 21c10b39-ca37-4085-86f8-063c30a180ed
translation-type: tm+mt
source-git-commit: bd94d3949f0117aa3e1c9f0e84f7293a5d6b03b4
workflow-type: tm+mt
source-wordcount: '3271'
ht-degree: 0%

---

# Technische vereisten{#technical-requirements}

Adobe ondersteunt Adobe Experience Manager (AEM) op de platforms, zoals wordt beschreven in de volgende informatie in dit document.

Neem voor alle problemen die specifiek betrekking hebben op het platform zelf rechtstreeks contact op met de leverancier van het platform.

>[!NOTE]
>
>Afhankelijk van het platform waarop u AEM installeert, kunnen er verschillende reeksen vereisten voor gebruikersbeheer zijn.

## Vereisten {#prerequisites}

Minimumeisen voor de installatie van Adobe Experience Manager:

* Geïnstalleerde Java Platform, Standard Edition JDK, of andere ondersteunde [Java Virtual Machines](#java-virtual-machines)
* QuickStart-bestand voor Experience Manager (standalone JAR of WAR voor implementatie van webtoepassingen)

### Minimale groottevereisten {#minimum-sizing-requirements}

Minimumvereisten voor Adobe Experience Manager:

* 5 GB vrije schijfruimte in de installatiemap
* 2 GB geheugen

>[!NOTE]
>
>* Voor het gebruik van digitale middelen is meer basisgeheugen nodig. Zie [Implementeren en onderhouden](/help/sites-deploying/deploy.md#default-local-install) voor meer informatie.
>* [Voor AEM Forms add-on ](/help/forms/using/installing-configuring-aem-forms-osgi.md) pakketten is 15 GB aan tijdelijke schijfruimte vereist.

>



Zie [Richtlijnen voor hardwaregrootte](/help/managing/hardware-sizing-guidelines.md) voor meer informatie.

### Ondersteuningsniveaus {#support-levels}

In dit document worden de ondersteunde client- en serverplatforms voor Adobe Experience Manager vermeld. Adobe biedt verschillende ondersteuningsniveaus, zowel voor aanbevolen configuraties als voor andere configuraties.

### Ondersteunde configuraties {#supported-configurations}

Adobe raadt deze configuraties aan en biedt volledige ondersteuning als onderdeel van de standaard overeenkomst voor softwareonderhoud.

<table> 
 <tbody> 
  <tr> 
   <td>Ondersteuningsniveau</td> 
   <td>Beschrijving<br /> </td> 
  </tr> 
  <tr> 
   <td><strong>A: Ondersteund</strong></td> 
   <td>Adobe biedt volledige ondersteuning en onderhoud voor deze configuratie. Deze configuratie wordt gedekt door het kwaliteitsborgingsproces van Adobe.</td> 
  </tr> 
  <tr> 
   <td><strong>R: Beperkte ondersteuning</strong></td> 
   <td>Om ervoor te zorgen dat het project van onze klanten slaagt, biedt Adobe volledige steun binnen een beperkt steunprogramma, dat vereist dat aan specifieke voorwaarden wordt voldaan. Voor ondersteuning op R-niveau is een formeel verzoek van de klant en een bevestiging door Adobe vereist. Neem voor meer informatie contact op met de klantenservice van Adobe.</td> 
  </tr> 
 </tbody> 
</table>

### Niet-ondersteunde configuraties {#unsupported-configurations}

| Ondersteuningsniveau | Beschrijving |
|---|---|
| **Z: Niet ondersteund** | De configuratie wordt niet ondersteund. Adobe legt geen verklaringen over of de configuratie werkt, en steunt het niet. |

## Ondersteunde Platforms {#supported-platforms}

### Java Virtual Machines {#java-virtual-machines}

De toepassing vereist dat een Java Virtual Machine wordt uitgevoerd, die wordt geleverd door de JDK-distributie (Java Development Kit).

Adobe Experience Manager werkt met de volgende versies van Java Virtual Machines:

>[!CAUTION]
>
>Het wordt aanbevolen de beveiligingsbulletins van de Java-leverancier bij te houden om de veiligheid en beveiliging van productieomgevingen te garanderen en de nieuwste Java-updates te installeren.

<table> 
 <tbody> 
  <tr> 
   <td>Platform</td> 
   <td>Ondersteuningsniveau<br /> </td> 
  </tr> 
  <tr> 
   <td>Oracle Java SE 11 JDK [1]</td> 
   <td>Z: Niet ondersteund </td> 
  </tr> 
  <tr> 
   <td>Oracle Java SE 10 JDK [1]</td> 
   <td>Z: Niet ondersteund </td> 
  </tr> 
  <tr> 
   <td>Oracle Java SE 9 JDK [1]</td> 
   <td>Z: Niet ondersteund</td> 
  </tr> 
  <tr> 
   <td><strong>Oracle Java SE 8 JDK - 64-bits</strong></td> 
   <td>A: Ondersteund [3]<br /> </td> 
  </tr> 
  <tr> 
   <td>IBM J9 VM - build 2.9, JRE 1.8.0 [2]</td> 
   <td>A: Ondersteund</td> 
  </tr> 
  <tr> 
   <td>IBM J9 VM - build 2.8, JRE 1.8.0 [2]</td> 
   <td>A: Ondersteund</td> 
  </tr> 
 </tbody> 
</table>

1. Oracle is overgestapt op een LTS-model (Long Term Support) voor Oracle Java SE-producten. Java 9 en 10 zijn niet-LTS versies door Oracle (zie [Oracle de steun roadmap van Java SE](https://www.oracle.com/technetwork/java/eol-135779.html)). Adobe biedt alleen ondersteuning voor LTS-releases van Java om AEM in productie te houden.

1. IBM JRE wordt alleen ondersteund in combinatie met WebSphere Application Server.
1. Ondersteuning en distributie van het Oracle Java SE JDK, inclusief alle onderhoudsupdates van LTS-releases na afloop van de openbare updates, wordt door Adobe direct ondersteund voor alle AEM klanten die gebruikmaken van de Oracle Java SE-technologie. Zie [Oracle Java support for Adobe Experience Manager Q&amp;A](assets/adobe-oracle-java-license-agreement.pdf) voor meer informatie.

### Opslag en duurzaamheid {#storage-persistence}

Er zijn verschillende opties om de opslagplaats van Adobe Experience Manager te implementeren. Zie de volgende lijst voor ondersteunde technologieën en opslagopties.

<table> 
 <tbody> 
  <tr> 
   <td><strong>Platform</strong></td> 
   <td><strong>Beschrijving</strong></td> 
   <td><strong>Ondersteuningsniveau</strong></td> 
  </tr> 
  <tr> 
   <td><strong>Bestandssysteem met TAR-bestanden [1]</strong></td> 
   <td>Bewaarplaats</td> 
   <td>A: Ondersteund</td> 
  </tr> 
  <tr> 
   <td><strong>Bestandssysteem met datastore [1]</strong></td> 
   <td>Binden</td> 
   <td>A: Ondersteund</td> 
  </tr> 
  <tr> 
   <td>Binaire bestanden opslaan in TAR-bestanden op bestandssysteem [1]</td> 
   <td>Binden</td> 
   <td>Z: Niet ondersteund voor productie</td> 
  </tr> 
  <tr> 
   <td>Amazon S3</td> 
   <td>Binden</td> 
   <td>A: Ondersteund</td> 
  </tr> 
  <tr> 
   <td>Microsoft Azure Blob-opslag</td> 
   <td>Binden</td> 
   <td>A: Ondersteund</td> 
  </tr> 
  <tr> 
   <td>MongoDB Enterprise 3.6 [5, 6]</td> 
   <td>Bewaarplaats</td> 
   <td>A: Ondersteund met beperkingen</td> 
  </tr> 
  <tr> 
   <td>MongoDB Enterprise 3.4 [2, 3, 6]</td> 
   <td>Bewaarplaats</td> 
   <td>A: Ondersteund met beperkingen</td> 
  </tr> 
  <tr> 
   <td>MySQL 5.7</td> 
   <td>Forms-database</td> 
   <td>A: Ondersteund</td> 
  </tr> 
  <tr> 
   <td>IBM DB2 11.1<br /> </td> 
   <td>Forms-database</td> 
   <td>A: Ondersteund</td> 
  </tr> 
  <tr> 
   <td>IBM DB2 10.5</td> 
   <td>Opslagplaats en Forms-database</td> 
   <td>R: Beperkte ondersteuning (4)</td> 
  </tr> 
  <tr> 
   <td>Database van oracle 12c (12.1.x)</td> 
   <td>Opslagplaats en Forms-database</td> 
   <td>R: Beperkte ondersteuning</td> 
  </tr> 
  <tr> 
   <td>Microsoft SQL Server 2017</td> 
   <td>Forms-database</td> 
   <td>Z: Niet ondersteund (4)</td> 
  </tr> 
  <tr> 
   <td>Microsoft SQL Server 2016</td> 
   <td>Forms-database</td> 
   <td>A: Ondersteund</td> 
  </tr> 
  <tr> 
   <td>Microsoft SQL Server 2014</td> 
   <td>Forms-database</td> 
   <td>R: Beperkte ondersteuning (4)</td> 
  </tr> 
  <tr> 
   <td><strong>Apache Lucene (QuickStart ingebouwd)</strong></td> 
   <td>Zoekservice</td> 
   <td>A: Ondersteund</td> 
  </tr> 
  <tr> 
   <td>Apache Solr</td> 
   <td>Zoekservice</td> 
   <td>A: Ondersteund</td> 
  </tr> 
 </tbody> 
</table>

1. &#39;Bestandssysteem&#39; omvat blokopslag die compatibel is met POSIX. Dit omvat netwerkopslagtechnologie. Houd er rekening mee dat de prestaties van het bestandssysteem kunnen variëren en van invloed zijn op de algehele prestaties. U wordt aangeraden AEM te laden in combinatie met het netwerk-/externe bestandssysteem.
1. Delen via MongoDB wordt niet ondersteund in AEM.
1. MongoDB Storage Engine WiredTiger wordt alleen ondersteund.
1. Niet ondersteund voor AEM Forms.
1. MongoDB Enterprise 3.6 wordt ondersteund vanaf AEM versie 6.4.2.0.
1. De ondersteuning voor MongoDB 3.4 heeft het einde van de levensduur bereikt, terwijl MongoDB 3.6 naar verwachting op 30 april 2021 het EOL zal bereiken. Houd er rekening mee dat Adobe alleen ondersteuning biedt voor AEM productgerelateerde problemen.

>[!NOTE]
>
>Zie [Gemeenschappen implementeren](/help/communities/deploy-communities.md) voor aanvullende informatie over de AEM Communities-mogelijkheden.

>[!NOTE]
>
>MongoDB is software van derden en is niet opgenomen in het AEM licentiepakket. Zie de pagina [MongoDB-licentiebeleid](https://www.mongodb.org/about/licensing/) voor meer informatie.
>
>Om optimaal gebruik te kunnen maken van uw AEM implementatie met MongoDB, raadt Adobe aan een licentie te verlenen voor de versie van MongoDB Enterprise om te kunnen profiteren van professionele ondersteuning. Zie [Aanbevolen implementaties](/help/sites-deploying/recommended-deploys.md#prerequisites-and-recommendations-when-deploying-aem-with-mongomk) voor meer informatie.
>
>De licentie bevat een standaard replicaset, die bestaat uit één primaire en twee secundaire instanties die kunnen worden gebruikt voor de auteur of de publicatieimplementaties.
>
>Als u zowel de auteur als de publicatie op MongoDB wilt uitvoeren, moet u twee aparte licenties aanschaffen.
>
>De klantenservice van Adobe helpt kwalificerende problemen met betrekking tot het gebruik van MongoDB met AEM.
>
>Zie de [MongoDB voor Adobe Experience Manager-pagina](https://www.mongodb.com/lp/contact/mongodb-adobe-experience-manager) voor meer informatie.

>[!NOTE]
>
>Ondersteunde relationele databases zoals hierboven vermeld, zijn software van derden en zijn niet opgenomen in het AEM licentiepakket.
>
>Om AEM 6.4 met een gesteunde relationele gegevensbestand in werking te stellen, wordt een afzonderlijk steuncontract met een gegevensbestandverkoper vereist. De klantenservice van Adobe helpt kwalificatiekwesties die verband houden met het gebruik van relationele databases met AEM 6.4.
>
>**De meeste relationele databases worden momenteel op AEM 6.4 ondersteund in niveau-R, die vergezeld gaat van steuncriteria en een steunprogramma zoals vermeld in de beschrijving van niveau-R hierboven.**

### Servlet-engines/toepassingsservers {#servlet-engines-application-servers}

Adobe Experience Manager kan worden uitgevoerd als een zelfstandige server (het QuickStart JAR-bestand) of als een webtoepassing binnen een externe toepassingsserver (het WAR-bestand).

De minimaal vereiste Servlet API-versie is Servlet 3.1, maar lager dan Servlet 4.0.

| Platform | Ondersteuningsniveau |
|---|---|
| **QuickStart ingebouwde Servlet Engine (Jetty 9.3)** | A: Ondersteund |
| Oracle WebLogic Server 12.2 (12cR2) | A: Ondersteund |
| IBM WebSphere Application Server Continuous Delivery (LibertyProfile) met webprofiel 7.0 en IBM JRE 1.8 | A: Ondersteund |
| IBM WebSphere Application Server 9.0 | A: Ondersteund |
| Apache Tomcat 8.5.x | A: Ondersteund |
| JBoss EAP 7.1.0 met JBoss Application Server | A: Ondersteund (1) |
| JBoss EAP 7.0.0 met JBoss Application Server | A: Ondersteund |

1. Niet ondersteund voor AEM Forms.

### Serverbesturingssystemen {#server-operating-systems}

Adobe Experience Manager werkt met de volgende serverplatforms:

<table> 
 <tbody> 
  <tr> 
   <td><strong>Platform</strong></td> 
   <td><strong>Ondersteuningsniveau</strong></td> 
  </tr> 
  <tr> 
   <td><strong>Linux, gebaseerd op Red Hat-distributie</strong></td> 
   <td>A: Ondersteund (1)</td> 
  </tr> 
  <tr> 
   <td>Linux, gebaseerd op Debian distribution incl. Ubuntu</td> 
   <td>A: Ondersteund (4)</td> 
  </tr> 
  <tr> 
   <td>Linux, gebaseerd op SUSE-distributie</td> 
   <td>A: Ondersteund</td> 
  </tr> 
  <tr> 
   <td>Microsoft Windows Server 2016</td> 
   <td>A: Ondersteund</td> 
  </tr> 
  <tr> 
   <td>Microsoft Windows Server 2012 R2</td> 
   <td>A: Ondersteund</td> 
  </tr> 
  <tr> 
   <td>Oracle Solaris 11</td> 
   <td>A: Ondersteund met beperkingen (3,5,7)<br /> R: Beperkte steun voor nieuwe contracten</td> 
  </tr> 
  <tr> 
   <td>IBM AIX 7.2</td> 
   <td>A: Ondersteund met beperkingen (2,5,7)<br /> R: Beperkte steun voor nieuwe contracten</td> 
  </tr> 
 </tbody> 
</table>

1. Linux Kernel 2.6, 3.x en 4.x omvat derivaten van Red Hat-distributie, waaronder Red Hat Enterprise Linux, CentOS, Oracle Linux en Amazon Linux. AEM Forms-add-onfuncties worden alleen ondersteund in CentOS 7 en Red Hat Enterprise Linux 7.
1. AEM Assets: Zie de sectie [Ondersteuning voor XMP terugschrijven van metagegevens](#requirements-for-aem-assets-xmp-metadata-write-back)
1. AEM Assets: Geen ondersteuning voor Dynamic Media Imaging. Dynamic Media Video wordt ondersteund.
1. AEM Forms wordt alleen ondersteund op Ubuntu 16.04 LTS.
1. AEM Assets: Geen ondersteuning voor [Raw-bestandstransformatie](/help/assets/camera-raw.md)
1. AEM Forms: Geen steun voor productieomgeving
1. AEM Assets: Geen ondersteuning voor [verbeterde PDF Rasterizer](/help/assets/aem-pdf-rasterizer.md)
1. AEM Forms: Niet ondersteund

### Virtuele en Cloud Computing-omgevingen {#virtual-cloud-computing-environments}

Adobe Experience Manager wordt ondersteund en wordt uitgevoerd in een virtuele machine in cloudcomputeromgevingen, zoals Microsoft Azure en Amazon Web Services (AWS), in overeenstemming met de technische vereisten die op deze pagina worden vermeld en volgens de standaardondersteuningsvoorwaarden van Adobe.

Adobe raadt u aan om Adobe Managed Services te gebruiken om AEM in Azure of AWS te implementeren. Adobe Managed Services biedt experts ervaring en vaardigheden voor het implementeren en gebruiken van AEM in deze cloud computing-omgevingen. Raadpleeg onze [aanvullende documentatie over Adobe Managed Services](https://www.adobe.com/marketing-cloud/enterprise-content-management/managed-services-cloud-platform.html?aemClk=t).

In alle andere gevallen van implementatie van AEM op Azure of AWS, of in elke andere cloudcomputeromgeving, wordt de ondersteuning van Adobe beperkt tot de virtuele computeromgeving, in overeenstemming met de technische specificaties die op deze pagina worden vermeld. Alle gemelde problemen met betrekking tot AEM die in een van deze cloudomgevingen worden uitgevoerd, moeten onafhankelijk van eventuele cloudservices die specifiek zijn voor de cloud computing-omgeving kunnen worden gereproduceerd, tenzij de cloudservice specifiek wordt ondersteund als onderdeel van de technische vereisten die op deze pagina worden vermeld, bijvoorbeeld Azure Blob-opslag of AWS S3.

Voor aanbevelingen voor de implementatie van AEM op Azure of AWS, buiten Adobe Managed Services, raden we u ten zeerste aan rechtstreeks samen te werken met de cloud provider of Adobe-partners die de implementatie van AEM in de cloud-omgeving van uw keuze ondersteunen. De geselecteerde cloudprovider of partner is verantwoordelijk voor de groottesortering van de specificaties, het ontwerp en de implementatie van de architectuur., om te voldoen aan uw specifieke vereisten op het gebied van prestaties, belasting, schaalbaarheid en beveiliging.

### Platforms voor verzending (webservers) {#dispatcher-platforms-web-servers}

De Dispatcher is de component voor het in cache plaatsen en taakverdeling. [Download de nieuwste versie](https://helpx.adobe.com/experience-manager/dispatcher/release-notes.html) van Dispatcher. Voor Experience Manager 6.4 is Dispatcher versie 4.3.1 of hoger vereist.

De volgende webservers worden ondersteund voor gebruik met Dispatcher versie 4.3.1:

| Platform | Ondersteuningsniveau |
|---|---|
| **Apache httpd 2.4.x**  (zie ook 1,2 hieronder) | A: Ondersteund |
| Microsoft IIS 10 (Internet Information Server) | A: Ondersteund |
| Microsoft IIS 8.5 (Internet Information Server) | A: Ondersteund |

1. Webservers die op basis van Apache httpd-broncode zijn gemaakt, krijgen hetzelfde ondersteuningsniveau als de versie van httpd waarop deze is gebaseerd. In geval van twijfel, gelieve Adobe om bevestiging van het steunniveau met betrekking tot het respectieve serverproduct te verzoeken. In de volgende gevallen:

   1. De HTTP-server is gemaakt met alleen officiële Apache-brondistributies, of
   1. De HTTP-server is geleverd als onderdeel van het besturingssysteem waarop deze wordt uitgevoerd. Voorbeelden: IBM HTTP Server, Oracle HTTP Server

1. Dispatcher is niet beschikbaar voor Apache 2.4.x voor Windows-besturingssystemen.

## Ondersteunde client-Platforms {#supported-client-platforms}

### Ondersteunde browsers voor gebruikersinterface ontwerpen {#supported-browsers-for-authoring-user-interface}

De Adobe Experience Manager-gebruikersinterface werkt met de volgende clientplatforms. Alle browsers worden getest met de standaardset insteekmodules en invoegtoepassingen.

De AEM gebruikersinterface is geoptimaliseerd voor grotere schermen (doorgaans laptops en desktopcomputers) en tabletvormfactoren (zoals Apple iPad of Microsoft Surface). De telefoonvormfactor wordt niet ondersteund.

>[!NOTE]
>
>**Ondersteuning voor browsers met snelle releasecycli:**
>
>Mozilla Firefox, Google Chrome en Microsoft Edge worden elke paar maanden bijgewerkt. Adobe heeft zich ertoe verbonden updates beschikbaar te stellen voor Adobe Experience Manager om het supportniveau te handhaven zoals hieronder vermeld in de komende versies van deze browsers.

<table> 
 <tbody> 
  <tr> 
   <td><strong>Browser</strong></td> 
   <td><strong>Ondersteuning voor UI<br /> </strong></td> 
   <td><strong>Ondersteuning voor klassieke gebruikersinterface</strong></td> 
  </tr> 
  <tr> 
   <td><strong>Google Chrome (Evergreen)</strong></td> 
   <td>A: Ondersteund</td> 
   <td>A: Ondersteund</td> 
  </tr> 
  <tr> 
   <td>Microsoft Edge (Evergreen)</td> 
   <td>A: Ondersteund</td> 
   <td>A: Ondersteund</td> 
  </tr> 
  <tr> 
   <td>Microsoft Internet Explorer 11</td> 
   <td>A: Ondersteund</td> 
   <td>A: Ondersteund</td> 
  </tr> 
  <tr> 
   <td>Mozilla Firefox (Evergreen)</td> 
   <td>A: Ondersteund</td> 
   <td>A: Ondersteund</td> 
  </tr> 
  <tr> 
   <td>Mozilla Firefox laatste ESR [1]</td> 
   <td>A: Ondersteund</td> 
   <td>A: Ondersteund</td> 
  </tr> 
  <tr> 
   <td>Apple Safari 12.x op macOS</td> 
   <td>A: Ondersteund</td> 
   <td>A: Ondersteund</td> 
  </tr> 
  <tr> 
   <td>Apple Safari 11.x op macOS</td> 
   <td>A: Ondersteund</td> 
   <td>A: Ondersteund</td> 
  </tr> 
  <tr> 
   <td>Apple Safari 10.x op macOS</td> 
   <td>A: Ondersteund</td> 
   <td>A: Ondersteund</td> 
  </tr> 
  <tr> 
   <td>Apple Safari op iOS 12.x</td> 
   <td>A: Ondersteund [2]</td> 
   <td>Z: Niet ondersteund</td> 
  </tr> 
  <tr> 
   <td>Apple Safari op iOS 11.x</td> 
   <td>A: Ondersteund [2]</td> 
   <td>Z: Niet ondersteund</td> 
  </tr> 
  <tr> 
   <td>Apple Safari op iOS 10.3</td> 
   <td>A: Ondersteund [2]</td> 
   <td>Z: Niet ondersteund</td> 
  </tr> 
 </tbody> 
</table>

1. Uitgebreide ondersteuningsrelease van Firefox [Meer informatie hierover vindt u op mozilla.org](https://www.mozilla.org/en-US/firefox/organizations/faq/)
1. ondersteuning voor Apple iPad

### Ondersteunde browsers voor websites {#supported-browsers-for-websites}

Over het algemeen is browserondersteuning voor websites die door AEM Sites worden weergegeven afhankelijk van de implementatie van AEM paginasjablonen, het ontwerp en de uitvoer van onderdelen. Daarom is deze ondersteuning van toepassing op de partij die deze onderdelen implementeert.

### WebDAV-clients {#webdav-clients}

**Microsoft Windows 7+**

Als u verbinding wilt maken met Microsoft Windows 7+ met een AEM die niet met SSL is beveiligd, moet de basisverificatie via een onbeveiligd netwerk zijn ingeschakeld in Windows. Dit vereist een verandering in de Registratie van Vensters van WebClient:

1. De registersubsleutel zoeken:

   * HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\WebClient\Parameters

1. Voeg de BasisAuthLevel registratieingang aan deze subkey toe gebruikend een waarde van 2 of meer.

Zie [Microsoft Support KB 841215](https://support.microsoft.com/default.aspx/kb/841215).

Om ontvankelijkheid van de Cliënt WebDav onder Vensters te verbeteren - zie [de Steun KB 2445570](https://support.microsoft.com/kb/2445570) van Microsoft

## Aanvullende Platforms {#additional-platform-notes}

Deze sectie biedt speciale notities en meer gedetailleerde informatie over het uitvoeren van Adobe Experience Manager en de invoegtoepassingen ervan.

### IPv4 en IPv6 {#ipv-and-ipv}

Alle elementen van Adobe Experience Manager (Instance, Dispatcher) kunnen in zowel IPv4- als IPv6-netwerken worden geïnstalleerd.

De bewerking is naadloos omdat er geen speciale configuratie vereist is. U kunt eenvoudig een IP adres specificeren gebruikend het formaat dat aan uw netwerktype, indien nodig aangewezen is.

Dit betekent dat wanneer een IP adres moet worden gespecificeerd u (zoals vereist) van kunt selecteren:

* een IPv6-adres

   bijvoorbeeld `https://[ab12::34c5:6d7:8e90:1234]:4502`

* een IPv4-adres

   bijvoorbeeld `https://123.1.1.4:4502`

* een servernaam

   bijvoorbeeld `https://www.yourserver.com:4502`

* het standaardgeval van `localhost` zal voor zowel IPv4 als IPv6 netwerkinstallaties worden geïnterpreteerd

   bijvoorbeeld `http://localhost:4502`

### Vereisten voor AEM invoegtoepassing Dynamic Media {#requirements-for-aem-dynamic-media-add-on}

AEM Dynamic Media is standaard uitgeschakeld. Zie [Dynamic Media](/help/assets/config-dynamic.md#enabling-dynamic-media) inschakelen.

Als Dynamic Media is ingeschakeld, gelden de volgende aanvullende systeemvereisten:
>[!NOTE]
>
>De volgende systeemvereisten gelden **_alleen_** als u Dynamic Media - Hybride modus gebruikt. Dynamic Media - Hybride modus heeft een ingesloten imageserver, die alleen op bepaalde besturingssystemen is gecertificeerd.
>
>Voor Dynamic Media-klanten die de Dynamic Media - Scene7-modus uitvoeren (dat wil zeggen **dynamicmedia_scene7** runmode), zijn er geen extra systeemvereisten. alleen dezelfde systeemvereisten als AEM. Dynamic Media - Scene7-modusarchitectuur gebruikt de op cloud gebaseerde beeldservice, niet de service die is ingesloten in AEM.

#### Hardware {#hardware}

De volgende hardwarevereisten gelden voor zowel Linux- als Windows-besturingssystemen:

* Intel Xeon- of AMD Opteron-processor met ten minste vier cores
* Minimaal 16 GB RAM

#### Linux {#linux}

Voor het gebruik van Dynamic Media op Linux zijn de volgende voorwaarden vereist:

* RedHat Enterprise 7 of CentOS 7 en hoger met de nieuwste herstelpatches
* 64-bits besturingssysteem
* Wisselen uitgeschakeld (aanbevolen)
* SELinux uitgeschakeld (zie onderstaande opmerking)

>[!NOTE]
>
>Als de landinstelling zodanig is ingesteld dat LC_CTYPE niet gelijk is aan en_US.UTF-8, voorkomt dit dat dynamische media werken. Om te zien wat zijn waarde &quot;scène&quot;bij de bevelherinnering is. Als het niet aan dat plaatst, dan plaats de LC_CTYPE milieuvariabele aan het lege koord door &quot;uitvoer LC_CTYPE=&quot;te typen alvorens AEM in werking te stellen.

>[!NOTE]
>
>**SELinux uitschakelen:** Afbeeldingsservice werkt niet wanneer SELinux is ingeschakeld. Deze optie is standaard ingeschakeld. U verhelpt dit probleem door het bestand **/etc/selinux/config** te bewerken en de SELinux-waarde te wijzigen van:
>
>`SELINUX=enforcing` tot   `SELINUX=disabled`

>[!NOTE]
>
>**NUMA-architectuur:** systemen met processors met AMD64 en Intel EM64T worden doorgaans geconfigureerd als niet-uniforme geheugenarchitectuurplatforms (NUMA), wat betekent dat de kernel meerdere geheugenknooppunten bij opstarttijd samenstelt in plaats van één geheugenknooppunt te maken.
>
>De meervoudige knoopaannemer kan in geheugenuitputting op één of meerdere knopen resulteren alvorens andere knopen worden uitgeput. Wanneer de geheugenuitputting gebeurt kan de pit besluiten om processen (bijvoorbeeld, de Server van het Beeld of de Server van het Platform) te doden alhoewel er beschikbaar geheugen is.
>
>Daarom adviseert Adobe dat als u zulk een systeem in werking stelt dat u NUMA gebruikend **numa=off** laarsoptie uitzet om kernel te vermijden die deze processen doden.

>[!NOTE]
>
>**Hostnaam van server moet oplosbaar zijn:** zorg ervoor dat hostname van de server aan een IP adres oplosbaar is. Als dat niet mogelijk is, gelieve volledig - gekwalificeerde hostname en het IP adres aan **/etc/hosts** toe te voegen:
>
>`<ip address> <fully qualified hostname>`

#### Windows {#windows}

* Microsoft Windows Server 2016
* Ruimte wisselen gelijk aan minstens tweemaal de hoeveelheid fysiek geheugen (RAM)

Om Dynamic Media op Vensters te gebruiken, moeten Microsoft Visual Studio 2010, 2013, en 2015 redistributables voor x64 en x86 worden geïnstalleerd.

x64

* Microsoft Visual Studio 2010 redistributable kan in [https://www.microsoft.com/en-us/download/details.aspx?id=13523](https://www.microsoft.com/en-us/download/details.aspx?id=13523) worden gevonden
* Microsoft Visual Studio 2013 redistributable kan in [https://www.microsoft.com/en-us/download/details.aspx?id=40784](https://www.microsoft.com/en-us/download/details.aspx?id=40784) worden gevonden
* Microsoft Visual Studio 2015 redistributable kan in [https://www.microsoft.com/en-us/download/details.aspx?id=48145](https://www.microsoft.com/en-us/download/details.aspx?id=48145) worden gevonden

x86

* Microsoft Visual Studio 2010 redistributable kan in [https://www.microsoft.com/en-in/download/details.aspx?id=5555](https://www.microsoft.com/en-in/download/details.aspx?id=5555) worden gevonden
* Microsoft Visual Studio 2013 redistributable kan in [https://www.microsoft.com/en-in/download/details.aspx?id=40769](https://www.microsoft.com/en-in/download/details.aspx?id=40769) worden gevonden
* Microsoft Visual Studio 2015 redistributable kan in [https://www.microsoft.com/en-us/download/details.aspx?id=52685](https://www.microsoft.com/en-us/download/details.aspx?id=52685) worden gevonden

#### MacOS {#macos}

* 10.9.x en hoger
* Alleen ondersteund voor proefversie en demo-doeleinden

### Vereisten voor AEM Forms PDF Generator {#requirements-for-aem-forms-pdf-generator}

<table> 
 <tbody> 
  <tr> 
   <th><p><strong>Product</strong></p> </th> 
   <th><p><strong>Ondersteunde indelingen voor conversie naar PDF</strong></p> </th> 
  </tr> 
  <tr> 
   <td><p><a href="https://helpx.adobe.com/acrobat/release-note/release-notes-acrobat-reader.html">Acrobat 2017 klassiek spoor</a></p> </td> 
   <td><p>XPS, afbeeldingsindelingen (BMP, GIF, JPEG, JPG, TIF, TIFF, PNG, JPF, JPX, JP2, J2K, J2C, JPC), HTML, HTM, DWG, DXF en DWF</p> </td> 
  </tr> 
  <tr> 
   <td>Microsoft® Project 2016</td> 
   <td>MPP</td> 
  </tr> 
  <tr> 
   <td>Microsoft® Publisher 2016</td> 
   <td>PUB</td> 
  </tr> 
  <tr> 
   <td>Microsoft® Office Visio 2016</td> 
   <td>VSD</td> 
  </tr> 
  <tr> 
   <td>Microsoft® Office 2016</td> 
   <td>DOC, DOCX, XLS, XLSX, PPT, PPTX, RTF en TXT</td> 
  </tr> 
  <tr> 
   <td>Microsoft® Office 2013</td> 
   <td>DOC, DOCX, XLS, XLSX, PPT, PPTX, RTF en TXT</td> 
  </tr> 
  <tr> 
   <td>Corel WordPerfect X7</td> 
   <td>WP, WPD<br /> </td> 
  </tr> 
  <tr> 
   <td>OpenOffice 4.1.2</td> 
   <td>ODT, ODP, ODS, ODG, ODF, SXW, SXC, SXC, SXD, XLS, XLSX, DOC, DOCX, PPT, PPTX, afbeeldingsindelingen (BMP, GIF, JPEG, TIF, TIFF, PNG, JPF, JPX, JP2, J2K, J2C, JPC), HTML, HTM, RTF en TXT</td> 
  </tr> 
  <tr> 
   <td><p>OpenOffice 3.4</p> </td> 
   <td><p>ODT, ODP, ODS, ODG, ODF, SXW, SXC, SXC, SXD, XLS, XLSX, DOC, DOCX, PPT, PPTX, afbeeldingsindelingen (BMP, GIF, JPEG, TIF, TIFF, PNG, JPF, JPX, JP2, J2K, J2C, JPC), HTML, HTM, RTF en TXT</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>PDF Generator ondersteunt alleen Engelse, Franse, Duitse en Japanse versies van de ondersteunde besturingssystemen en toepassingen.
>
>Daarnaast:
>
>* PDF Generator vereist [Acrobat 2017 classic track version 17.011.30078 of hoger](https://helpx.adobe.com/acrobat/release-note/release-notes-acrobat-reader.html) om de conversie uit te voeren.
>* AEM Forms ondersteunt alleen 32-bits versies van ondersteunde software.
>* De functies OCR PDF (Doorzoekbare PDF), Optimize PDF en Export PDF worden alleen ondersteund in Microsoft Windows.
>* De HTML2PDF-service is afgekeurd op AIX.
>* Conversies van PDF-generator voor OpenOffice worden alleen ondersteund in Windows, Linux en Solaris.
>* De functies OCR PDF, Optimize PDF en Export PDF worden alleen ondersteund in Windows.
>* Een versie van Acrobat wordt meegeleverd met AEM Forms om de functionaliteit van de PDF Generator in te schakelen. De gebundelde versie mag alleen via programmacode toegankelijk zijn met AEM Forms, tijdens de periode van de AEM Forms-licentie, voor gebruik met AEM Forms PDF Generator. Raadpleeg voor meer informatie de beschrijving van het AEM Forms-product volgens uw implementatie ([On-Premise](https://helpx.adobe.com/legal/product-descriptions/adobe-experience-manager-on-premise.html) of [Managed Services](https://helpx.adobe.com/legal/product-descriptions/adobe-experience-manager-managed-services.html))&quot;

>



### Vereisten voor AEM Forms Designer {#requirements-for-aem-forms-designer}

* Microsoft® Windows® 2012 Server R2, Microsoft® Windows® 2016 Server, Microsoft® Windows® 2019 Server, Microsoft® Windows® 10
* Processor van 1 GHz of sneller met ondersteuning voor PAE, NX en SSE2.
* 1 GB RAM voor 32-bits of 2 GB RAM voor 64-bits besturingssysteem
* 16 GB schijfruimte voor 32-bits of 20 GB schijfruimte voor 64-bits besturingssysteem
* Grafisch geheugen - 128 MB GPU (256 MB aanbevolen)
* 2,35 GB beschikbare ruimte op de vaste schijf
* Monitorresolutie van 1024 x 768 pixels of hoger
* Hardwareversnelling voor video (optioneel)
* Acrobat Pro DC, Acrobat Standard DC of Adobe Acrobat Reader DC
* Beheerdersrechten voor de installatie van Designer

### Vereisten voor het terugschrijven van AEM Assets XMP metagegevens {#requirements-for-aem-assets-xmp-metadata-write-back}

XMP terugschrijven wordt ondersteund en ingeschakeld voor de volgende platforms en bestandsindelingen:

**Besturingssystemen**

* Linux (32-bits, vereist 32-bits toepassingsondersteuning op 64-bits systemen). Voor stappen om cliëntbibliotheken met 32 bits te installeren, zie [hoe te XMP extractie en schrijven-terug op Linux met 64 bits RedHat toe te laten](https://helpx.adobe.com/experience-manager/kb/enable-xmp-write-back-64-bit-redhat.html).

* Windows Server
* Oracle Solaris
* Mac OS X (64-bits)

**Bestandsindelingen**

* JPEG
* PNG
* TIFF
* PDF
* INDD
* AI
* EPS

### Vereisten voor AEM Screens Player {#requirements-for-aem-screens-player}

AEM Screens Player versie 3.3.x ondersteunt de volgende besturingssystemen:

* Microsoft Windows 10 Enterprise LTSB
* Google Chome OS 62+
* Google Android 5.1.1 met bijgewerkte WebView-versie 52+ voor Android-systemen
* Apple iOS 10.3+
* Apple MacOS 10.12+
