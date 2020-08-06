---
title: AEM
seo-title: AEM
description: Meer informatie over het oplossen van problemen met AEM.
seo-description: Meer informatie over het oplossen van problemen met AEM.
uuid: d68e9ead-8aa6-4108-9f1e-85d7cd7a370f
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: operations
content-type: reference
discoiquuid: 1bc19f9a-fa3f-43e3-813e-23ab0b708d43
translation-type: tm+mt
source-git-commit: cdec5b3c57ce1c80c0ed6b5cb7650b52cf9bc340
workflow-type: tm+mt
source-wordcount: '555'
ht-degree: 0%

---


# AEM{#troubleshooting-aem}

De volgende sectie behandelt sommige kwesties die u wanneer het gebruiken van AEM kunt ontmoeten, samen met suggesties op hoe te om hen problemen op te lossen.

>[!NOTE]
>
>Raadpleeg [Problemen oplossen bij auteurs als u problemen met het schrijven van oplossingen oplost in AEM.](/help/sites-authoring/troubleshooting.md)

>[!NOTE]
>
>Wanneer het ervaren van problemen het ook de moeite waard is de lijst van [Bekende Kwesties](/help/release-notes/known-issues.md) voor uw instantie (versie en de dienstpakken) te controleren.

## Het oplossen van problemen scenario&#39;s voor Beheerders {#troubleshooting-scenarios-for-administrators}

De volgende lijst verstrekt een overzicht van problemen beheerders kunnen moeten problemen oplossen:

<table> 
 <tbody> 
  <tr> 
   <td><strong>Rol/rollen</strong></td> 
   <td><strong>Probleem </strong></td> 
  </tr> 
  <tr> 
   <td>Systeembeheerder</td> 
   <td><p>Als u dubbelklikt op de Quickstart-jar, heeft dit geen effect en wordt het jar-bestand geopend met een ander programma (bijvoorbeeld archiefbeheer)</p> </td> 
  </tr> 
  <tr> 
   <td><p>Systeembeheerder</p> </td> 
   <td><p>Mijn toepassing die op CRX loopt werpt fouten uit het geheugen</p> </td> 
  </tr> 
  <tr> 
   <td><p>Systeembeheerder</p> </td> 
   <td><p>Het welkomstscherm AEM wordt niet weergegeven in de browser nadat u hebt dubbelgeklikt op AEM CM QuickStart</p> </td> 
  </tr> 
  <tr> 
   <td><p>Systeembeheerder</p> <p>beheerder</p> </td> 
   <td><p>Een Thread Dump maken</p> </td> 
  </tr> 
  <tr> 
   <td><p>Systeembeheerder</p> <p>beheerder</p> </td> 
   <td><p>Controleren op niet-afgesloten JCR-sessies</p> </td> 
  </tr> 
 </tbody> 
</table>

## Installatieproblemen {#installation-issues}

Zie [Gemeenschappelijke Problemen](/help/sites-deploying/troubleshooting.md#common-installation-issues) van de Installatie voor informatie over de volgende het oplossen van problemenscenario&#39;s:

* Dubbelklikken op de Quickstart-strip heeft geen effect op het JAR-bestand met een ander programma (zoals archiefbeheer).
* Toepassingen die op CRX worden uitgevoerd, genereren fouten die zich buiten het geheugen bevinden.
* Het welkomstscherm AEM wordt niet weergegeven in de browser nadat u hebt dubbelgeklikt op AEM QuickStart.

## Methoden voor de Analyse van het Oplossen van problemen {#methods-for-troubleshooting-analysis}

### Een Thread Dump maken {#making-a-thread-dump}

De draadstortplaats is een lijst van alle draden van Java die momenteel actief zijn. Als AEM niet behoorlijk antwoordt, kan de draadstortplaats u helpen kastjes of andere problemen identificeren.

### Dumper met slingerdraad gebruiken {#using-sling-thread-dumper}

1. Open de **AEM webconsole**; bijvoorbeeld om `http://localhost:4502/system/console/`.

1. Selecteer de **Draden** onder **Status** tabel.

![screen_shot_2012-02-13at43925pm](assets/screen_shot_2012-02-13at43925pm.png)

### jstack gebruiken (opdrachtregel) {#using-jstack-command-line}

1. Zoek de PID (process id) van de AEM Java-instantie.

   U kunt bijvoorbeeld `ps -ef` of `jps`.

1. Uitvoeren:

   `jstack <pid>`

1. Dit zal de draadstortplaats tonen.

>[!NOTE]
>
>U kunt de draaddumps aan een logboekdossier toevoegen door de `>>` outputredirection te gebruiken:
>
>`jstack <pid> >> /path/to/logfile.log`

Zie de [Hoe u de Thread Dumps kunt gebruiken vanuit een JVM](https://helpx.adobe.com/cq/kb/TakeThreadDump.html) -documentatie voor meer informatie

### Controleren op niet-afgesloten JCR-sessies {#checking-for-unclosed-jcr-sessions}

Wanneer de functionaliteit voor AEM WCM wordt ontwikkeld, kunnen de zittingen van JCR worden geopend (vergelijkbaar met het openen van een gegevensbestandverbinding). Als de geopende sessies nooit gesloten zijn, kan uw systeem de volgende symptomen ervaren:

* Het systeem wordt langzamer.
* U kunt veel CacheManager zien: resizeAll ingangen in het logboekdossier; het volgende aantal (grootte=&lt;x>) toont het aantal geheime voorgeheugens, elke zittingen opent verscheidene geheime voorgeheugens.
* Van tijd tot tijd heeft het systeem onvoldoende geheugen (na een paar uur, dagen of weken - afhankelijk van de ernst).

Om unclosed zittingen te analyseren en te weten te komen welke code een zitting niet sluit, verwijs naar het artikel van de Kennisbank [analyseert Unclosed Sessions](https://helpx.adobe.com/crx/kb/AnalyzeUnclosedSessions.html).

### De Adobe Experience Manager-webconsole gebruiken {#using-the-adobe-experience-manager-web-console}

De status van de OSGi-bundels kan ook een vroege indicatie geven van mogelijke problemen.

1. Open de **AEM webconsole**; bijvoorbeeld om `http://localhost:4502/system/console/`.

1. Selecteer **Bundels** onder **OSGI** tabblad.

1. Vinkje:

   * de status van de bundels. Als er inactief of ontevreden zijn, kunt u de bundel stoppen en opnieuw starten. Als het probleem zich blijft voordoen, moet u mogelijk verder onderzoeken met andere methoden.
   * of een van de bundels afhankelijkheden mist. Dergelijke details kunnen worden gezien door op de individuele bundelnaam te klikken, die een verbinding is (het volgende voorbeeld heeft geen kwesties):

![screen_shot_2012-02-13at44706pm](assets/screen_shot_2012-02-13at44706pm.png)

