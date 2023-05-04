---
title: Herstructurering van de Dynamic Media-opslagplaats in AEM 6.4
seo-title: Dynamic Media repository restructuring in AEM 6.4
description: Leer hoe u de noodzakelijke wijzigingen aanbrengt om te migreren naar de nieuwe repository structuur in AEM 6.4 voor Dynamic Media.
seo-description: Learn how to make the necessary changes in order to migrate to the new repository structure in AEM 6.4 for Dynamic Media.
uuid: e26d61a4-47b6-493a-9ba2-4c58b200ddd9
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: repo_restructuring
discoiquuid: 61cd5751-0dc8-48e0-873e-3a64899489bb
feature: Upgrading
exl-id: 1323ee60-c80c-4eed-b3e5-aa0f0c07e6ee
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 0%

---

# Herstructurering van de Dynamic Media-opslagplaats in AEM 6.4{#dynamic-media-repository-restructuring-in-aem}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Zoals beschreven op het bovenliggende element [Herstructurering van de depositaris in AEM 6.4](/help/sites-deploying/repository-restructuring.md) op de pagina, moeten klanten die een upgrade uitvoeren naar AEM 6.4 deze pagina gebruiken om de werkinspanning te beoordelen die gepaard gaat met wijzigingen in de opslagplaats die gevolgen hebben voor de Dynamic Media-oplossing. Sommige veranderingen vereisen het werk inspanning tijdens het AEM 6.4 verbeteringsproces, terwijl anderen tot een verbetering van 6.5 kunnen worden uitgesteld.

**Vóór upgrade naar 6.5**

* [Aangepaste configuraties voor adaptieve videocodering](/help/sites-deploying/dynamicmedia-repository-restructuring-in-aem-6-4.md#custom-adaptive-video-encoding-configurations)
* [Dynamic Media (DMS7) Cloud Configuration](/help/sites-deploying/dynamicmedia-repository-restructuring-in-aem-6-4.md#dynamic-media-dms-cloud-configuration)
* [Configuratie van Dynamic Media (DM Hybrid)-Cloud Service](/help/sites-deploying/dynamicmedia-repository-restructuring-in-aem-6-4.md#cloudserviceconfiguration)
* [Dynamic Media - YouTube Cloud Service Configuration](/help/sites-deploying/dynamicmedia-repository-restructuring-in-aem-6-4.md#youtubecloudserviceconfiguration)
* [Dic](/help/sites-deploying/dynamicmedia-repository-restructuring-in-aem-6-4.md#misc)

## Vóór upgrade naar 6.5 {#prior-to-upgrade}

### Aangepaste configuraties voor adaptieve videocodering  {#custom-adaptive-video-encoding-configurations}

<table> 
 <tbody>
  <tr>
   <td><strong>Vorige locatie</strong></td> 
   <td><code>/etc/dam/video/dynamicmedia</code></td> 
  </tr>
  <tr>
   <td><strong>Nieuwe locatie(s)</strong></td> 
   <td><code>/conf/global/settings/dam/dm/presets/video/jcr:content</code></td> 
  </tr>
  <tr>
   <td><strong>Herstructureringsrichtsnoeren</strong></td> 
   <td><p>U kunt het volgende migratiescript in werking stellen om aan de nieuwe plaats te migreren:</p> <p><em>https://serveraddress:serverport/libs/settings/dam/dm/presets.migratedmcontent.json</em></p> <p>U kunt de configuratie ook bewerken in AEM UI en de wijzigingen worden opgeslagen op de nieuwe locatie.</p> </td> 
  </tr>
  <tr>
   <td><strong>Notities</strong></td> 
   <td>N.v.t.<br /> </td> 
  </tr>
 </tbody>
</table>

### Dynamic Media (DMS7) Cloud-configuratie {#dynamic-media-dms-cloud-configuration}

<table> 
 <tbody>
  <tr>
   <td><strong>Vorige locatie</strong></td> 
   <td><code>/etc/cloudservices/dmscene7</code></td> 
  </tr>
  <tr>
   <td><strong>Nieuwe locatie(s)</strong></td> 
   <td><code>/conf/global/settings/cloudservices/dmscene7</code></td> 
  </tr>
  <tr>
   <td><strong>Herstructureringsrichtsnoeren</strong></td> 
   <td><p>De klant kan een migratiescript bij deze plaats in werking stellen:<br /> </p> 
    <ul> 
     <li><em>https://serveraddress:serverport/libs/settings/dam/dm/presets.migratedmcontent.json</em></li> 
     <li>Start de Dynamic Media OSGi-bundel opnieuw.</li> 
    </ul> </td> 
  </tr>
  <tr>
   <td><strong>Notities</strong></td> 
   <td>N.v.t.</td> 
  </tr>
 </tbody>
</table>

### Dynamic Media (DM Hybrid) configuratie van de Cloud Service {#cloudserviceconfiguration}

<table> 
 <tbody>
  <tr>
   <td><strong>Vorige locatie</strong></td> 
   <td><code>/etc/cloudservices/dynamicmediaservices</code></td> 
  </tr>
  <tr>
   <td><strong>Nieuwe locatie(s)</strong></td> 
   <td><code>/conf/global/settings/dam/dm/cloudservices/dynamicmediaservices</code></td> 
  </tr>
  <tr>
   <td><strong>Herstructureringsrichtsnoeren</strong></td> 
   <td><p>U kunt het migratiescript hieronder in werking stellen om zich aan het recentste model te richten:</p> <p><em>https://serveraddress:serverport/libs/settings/dam/dm/presets.migratedmcontent.jso</em></p> </td> 
  </tr>
  <tr>
   <td><strong>Notities</strong></td> 
   <td>N.v.t.<br /> </td> 
  </tr>
 </tbody>
</table>

### Dynamic Media - configuratie YouTube-Cloud Service  {#youtubecloudserviceconfiguration}

<table> 
 <tbody>
  <tr>
   <td><strong>Vorige locatie</strong></td> 
   <td><code>/etc/cloudservices/youtube</code></td> 
  </tr>
  <tr>
   <td><strong>Nieuwe locatie(s)</strong></td> 
   <td><code>/libs/settings/dam/dm/youtube</code></td> 
  </tr>
  <tr>
   <td><strong>Herstructureringsrichtsnoeren</strong></td> 
   <td><p>1. Alle video's van YouTube verwijderen<br /> 2. De YouTube-configuratie maken met de nieuwe TouchUI (van <code>/conf</code>) inclusief het kopiëren van alle kanalen van de oude locatie<br /> 3. Publiceer alle video's terug naar YouTube.</p> <p>Deze workflow resulteert in nieuwe YouTube-URL's. Als u de publicatie niet ongedaan maakt voordat u een nieuwe TouchUI YouTube-config maakt, worden meerdere YouTube-URL's weergegeven onder Eigenschappen, omdat de opnieuw gemaakte kanalen bij deze gelegenheid opnieuw zullen publiceren. Dit betekent dat u nutteloze URLs hebt die onder Eigenschappen wordt vermeld.</p> </td> 
  </tr>
  <tr>
   <td><strong>Notities</strong></td> 
   <td>N.v.t.<br /> </td> 
  </tr>
 </tbody>
</table>

### Dic {#misc}

<table> 
 <tbody>
  <tr>
   <td><strong>Vorige locatie</strong></td> 
   <td><code>/etc/dam/imageserver/macros</code></td> 
  </tr>
  <tr>
   <td><strong>Nieuwe locatie(s)</strong></td> 
   <td><code>/conf/global/settings/dam/dm/presets/macro</code></td> 
  </tr>
  <tr>
   <td><strong>Herstructureringsrichtsnoeren</strong></td> 
   <td><p>De klant kan het onderstaande migratiescript uitvoeren.</p> <p><em>https://serveraddress:serverport/libs/settings/dam/dm/presets.migratedmcontent.json</em></p> <p>U kunt de configuratie ook bewerken in AEM UI en de wijzigingen worden opgeslagen op de nieuwe locatie.</p> </td> 
  </tr>
  <tr>
   <td><strong>Notities</strong></td> 
   <td>N.v.t.</td> 
  </tr>
 </tbody>
</table>

<table> 
 <tbody>
  <tr>
   <td><strong>Vorige locatie</strong></td> 
   <td><code>/etc/dam/presets/analytics</code></td> 
  </tr>
  <tr>
   <td><strong>Nieuwe locatie(s)</strong></td> 
   <td><code>/libs/settings/dam/dm/analytics</code></td> 
  </tr>
  <tr>
   <td><strong>Herstructureringsrichtsnoeren</strong></td> 
   <td><p>De klant kan het onderstaande migratiescript uitvoeren.</p> <p><em>https://serveraddress:serverport/libs/settings/dam/dm/presets.migratedmcontent.json</em></p> </td> 
  </tr>
  <tr>
   <td><strong>Notities</strong></td> 
   <td>N.v.t.</td> 
  </tr>
 </tbody>
</table>
