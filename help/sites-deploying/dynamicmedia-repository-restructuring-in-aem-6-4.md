---
title: Herstructurering van dynamische opslagplaats voor media in AEM 6.4
seo-title: Herstructurering van dynamische opslagplaats voor media in AEM 6.4
description: Leer hoe u de noodzakelijke wijzigingen aanbrengt om te migreren naar de nieuwe opslagstructuur in AEM 6.4 voor Dynamic Media.
seo-description: Leer hoe u de noodzakelijke wijzigingen aanbrengt om te migreren naar de nieuwe opslagstructuur in AEM 6.4 voor Dynamic Media.
uuid: e26d61a4-47b6-493a-9ba2-4c58b200ddd9
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: repo_restructuring
discoiquuid: 61cd5751-0dc8-48e0-873e-3a64899489bb
translation-type: tm+mt
source-git-commit: 5dce4bcf4b10cce65798fd142a3eeb1956caf726
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 1%

---


# Herstructurering van dynamische opslagplaats voor media in AEM 6.4{#dynamic-media-repository-restructuring-in-aem}

Zoals beschreven in de moederherstructurering van de [opslagplaats in AEM 6.4](/help/sites-deploying/repository-restructuring.md) pagina, zouden klanten die tot AEM 6.4 opwaarderen deze pagina moeten gebruiken om de werkinspanning te beoordelen verbonden aan veranderingen in de opslagplaats die gevolgen hebben voor de Dynamic Media Solution. Sommige veranderingen vereisen het werk inspanning tijdens het AEM 6.4 verbeteringsproces, terwijl anderen tot een verbetering van 6.5 kunnen worden uitgesteld.

**Vóór upgrade naar 6.5**

* [Aangepaste configuraties voor adaptieve videocodering](/help/sites-deploying/dynamicmedia-repository-restructuring-in-aem-6-4.md#custom-adaptive-video-encoding-configurations)
* [Dynamische media (DMS7) Cloud Configuration](/help/sites-deploying/dynamicmedia-repository-restructuring-in-aem-6-4.md#dynamic-media-dms-cloud-configuration)
* [Configuratie van dynamische Cloud Service (DM Hybrid)](/help/sites-deploying/dynamicmedia-repository-restructuring-in-aem-6-4.md#cloudserviceconfiguration)
* [Dynamische media - configuratie YouTube-Cloud Service](/help/sites-deploying/dynamicmedia-repository-restructuring-in-aem-6-4.md#youtubecloudserviceconfiguration)
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
   <td><strong>Opmerkingen</strong></td> 
   <td>N/A<br /> </td> 
  </tr>
 </tbody>
</table>

### Dynamische media (DMS7) Cloud-configuratie {#dynamic-media-dms-cloud-configuration}

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
     <li>Start Dynamic Media OSGi-bundel opnieuw.</li> 
    </ul> </td> 
  </tr>
  <tr>
   <td><strong>Opmerkingen</strong></td> 
   <td>N.v.t.</td> 
  </tr>
 </tbody>
</table>

### Configuratie van dynamische Cloud Servicen (DM Hybrid) {#cloudserviceconfiguration}

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
   <td><strong>Opmerkingen</strong></td> 
   <td>N/A<br /> </td> 
  </tr>
 </tbody>
</table>

### Dynamische media - configuratie YouTube-Cloud Service  {#youtubecloudserviceconfiguration}

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
   <td><p>1. Publiceer alle video's van YouTube<br /> 2 ongedaan. Maak de YouTube-configuratie met de nieuwe TouchUI (van <code>/conf</code>), inclusief het kopiëren van alle kanalen vanaf de oude locatie<br /> 3. Publiceer alle video's terug naar YouTube.</p> <p>Deze workflow resulteert in nieuwe YouTube-URL's. Als u de publicatie niet ongedaan maakt voordat u een nieuwe TouchUI YouTube-config maakt, worden er meerdere YouTube-URL's weergegeven onder Eigenschappen, omdat de opnieuw gemaakte kanalen bij deze gelegenheid opnieuw zullen publiceren. Dit betekent dat u nutteloze URLs hebt die onder Eigenschappen wordt vermeld.</p> </td> 
  </tr>
  <tr>
   <td><strong>Opmerkingen</strong></td> 
   <td>N/A<br /> </td> 
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
   <td><strong>Opmerkingen</strong></td> 
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
   <td><strong>Opmerkingen</strong></td> 
   <td>N.v.t.</td> 
  </tr>
 </tbody>
</table>

