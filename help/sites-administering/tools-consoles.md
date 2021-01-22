---
title: Gereedschapsconsoles
description: Meer informatie over de verschillende gereedschapsconsoles in Adobe Experience Manager.
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: operations
content-type: reference
translation-type: tm+mt
source-git-commit: 425f1e6288cfafc3053877a43fa0a20fd5d2f3ac
workflow-type: tm+mt
source-wordcount: '875'
ht-degree: 7%

---


# Gereedschapsconsoles{#tools-consoles}

Via de **gereedschapsconsoles** hebt u toegang tot een aantal gespecialiseerde beheertools voor uw websites, digitale elementen en andere aspecten van de content-repository. Er zijn momenteel twee flavors van de **console Tools** afhankelijk van UI u gebruikt:

* [Gereedschappen - Klassieke gebruikersinterface](#tools-classic-ui)
* [Gereedschappen - Touch-Optimized UI](#tools-touch-optimized-ui)

## Gereedschappen - Klassieke UI {#tools-classic-ui}

<table> 
 <tbody> 
  <tr> 
   <th>Pagina of map</th> 
   <th> </th> 
   <th>Doel</th> 
  </tr> 
  <tr> 
   <td><a href="/help/sites-administering/msm.md">MSM-controlecentrum</a></td> 
   <td> </td> 
   <td>Gecentraliseerd punt voor het beheer van uw meerdere sites.</td> 
  </tr> 
  <tr> 
   <td>Clientcontextconfiguraties<br /> </td> 
   <td> </td> 
   <td>De <a href="/help/sites-developing/client-context.md">Clientcontext</a> vertegenwoordigt een dynamisch geassembleerde verzameling van gebruikersgegevens. De standaard en marketing wolkenconfiguraties worden hier gehouden.<br /> </td> 
  </tr> 
  <tr> 
   <td>Cloud Services Configurations<br /> </td> 
   <td> </td> 
   <td>Bevat configuraties gerelateerd aan <a href="/help/sites-administering/marketing-cloud.md">Integratie met de Adobe Marketing Cloud</a>.</td> 
  </tr> 
  <tr> 
   <td><a href="/help/sites-administering/ecommerce.md">Handel</a></td> 
   <td> </td> 
   <td>Biedt toegang tot importeurs en verschillende productgegevens.</td> 
  </tr> 
  <tr> 
   <td>DAM - Digital Rights Management<br /> </td> 
   <td> </td> 
   <td>Biedt toegang tot informatie over digitale rechten en licenties.</td> 
  </tr> 
  <tr> 
   <td>DAM - Health Checker<br /> </td> 
   <td> </td> 
   <td>Vergelijkt <code>/var/dam</code> en <code>/content/dam</code> en controleert op <br /> om het even welke inconsistenties. Alle vermelde bestanden/mappen kunnen vervolgens worden gesynchroniseerd of verwijderd. De types van knopen voor omslagvergelijking zijn configureerbaar in de Webconsole.</td> 
  </tr> 
  <tr> 
   <td>DAM - Adobe InDesign<br /> </td> 
   <td> </td> 
   <td>Scripts voor gebruik in combinatie met Adobe InDesign.</td> 
  </tr> 
  <tr> 
   <td>DAM - Videoprofielen<br /> </td> 
   <td> </td> 
   <td>Configureerbare profielen voor mpeg-transcoderingen.</td> 
  </tr> 
  <tr> 
   <td><a href="/help/sites-administering/dashboards.md">Dashboards</a></td> 
   <td> </td> 
   <td>Hiermee kunt u rapportdashboards maken; Deze vormen een aanpasbare manier om pagina's te definiëren waarop geconsolideerde gegevens worden weergegeven.</td> 
  </tr> 
  <tr> 
   <td><a href="/help/sites-developing/designer.md">Ontwerpen</a></td> 
   <td> </td> 
   <td>Bevat de lijst met gedefinieerde ontwerpen, inclusief de afbeeldingen en CSS-bestanden die moeten worden gebruikt.</td> 
  </tr> 
  <tr> 
   <td>Aangepaste documentatie</td> 
   <td> </td> 
   <td>Wordt gebruikt bij het uitbreiden van de documentatie en online Help.</td> 
  </tr> 
  <tr> 
   <td>Formulierverzendingen</td> 
   <td> </td> 
   <td>Bevat de lijst met ontvangen formulierverzendingen.</td> 
  </tr> 
  <tr> 
   <td>Importeurs - <a href="/help/sites-administering/bulk-editor.md">Bulkeditor</a></td> 
   <td> </td> 
   <td>Hiermee kunt u naar objecten zoeken en deze bulksgewijs bewerken. U kunt ook inhoud (in bulk) exporteren en importeren in de opslagplaats.</td> 
  </tr>
  <tr> 
   <td>Importeur - Invoer van diervoeders</td> 
   <td> </td> 
   <td><p>De importmodule is een raamwerk voor het herhaaldelijk importeren van inhoud uit externe bronnen in uw opslagplaats. Het idee van feed importer is om een externe bron met een opgegeven interval te polen, deze te parseren en knooppunten in de inhoudsopslagplaats te maken die de inhoud van de externe bron vertegenwoordigen.</p> </td> 
  </tr> 
  <tr> 
   <td><a href="/help/sites-administering/external-link-checker.md">Externe koppelingencontrole</a></td> 
   <td> </td> 
   <td>Alle inhoudspagina's binnen uw AEM instantie en controles om het even welke externe verbindingen. Er wordt een lijst met geldige en ongeldige koppelingen weergegeven.</td> 
  </tr> 
  <tr> 
   <td><a href="/help/sites-authoring/mobile.md">Mobiel</a></td> 
   <td> </td> 
   <td>Hiermee kunt u websites maken die zijn ontworpen voor mobiele apparaten.</td> 
  </tr> 
  <tr> 
   <td><a href="/help/sites-administering/msm.md">MSM</a></td> 
   <td> </td> 
   <td>Verwerkt meertalige en multinationale inhoud, waardoor u een evenwicht kunt vinden tussen gecentraliseerde branding en gelokaliseerde inhoud.</td> 
  </tr> 
  <tr> 
   <td><a href="/help/sites-administering/notification.md">Melding</a></td> 
   <td> </td> 
   <td>Meldingssjablonen.</td> 
  </tr> 
  <tr> 
   <td><a href="/help/sites-administering/package-manager.md">Pakketten</a></td> 
   <td> </td> 
   <td>Een alternatieve verbinding aan de Manager van het Pakket die de pakketten toont die voor AEM WCM zijn geladen. Gelijkaardig aan de informatie die in de Manager van het Pakket van CRX wordt getoond.</td> 
  </tr> 
  <tr> 
   <td>Replicatie - <a href="/help/sites-deploying/configuring.md#replication-reverse-replication-and-replication-agents">Replication Agents</a></td> 
   <td> </td> 
   <td>Wordt gebruikt om gegevens van auteur te repliceren voor publicatie bij het publiceren van pagina's of met omgekeerde replicatie om gebruikersopmerkingen van de publicatieomgeving te retourneren aan auteur.</td> 
  </tr> 
  <tr> 
   <td>Importeurs - <a href="/help/sites-authoring/publishing-pages.md#publishing-and-unpublishing-a-tree">Boom activeren</a></td> 
   <td> </td> 
   <td>Via het tabblad Websites kunt u de afzonderlijke pagina's activeren. Wanneer u een aanzienlijk aantal inhoudspagina's hebt ingevoerd of bijgewerkt (die allemaal ingezeten zijn onder dezelfde basispagina), kan het eenvoudiger zijn de gehele structuur in één actie te activeren. U kunt ook een droog programma uitvoeren om een activering na te bootsen en te markeren welke pagina's moeten worden geactiveerd.</td> 
  </tr> 
  <tr> 
   <td><a href="/help/sites-administering/reporting.md">Rapporten</a></td> 
   <td> </td> 
   <td>AEM verstrekt een waaier van aangepaste rapporten, staat u toe om aangepaste rapporten tot stand te brengen en/of uw te ontwikkelen.</td> 
  </tr> 
  <tr> 
   <td><a href="/help/sites-authoring/scaffolding.md">Standaardpaginascheiding</a></td> 
   <td> </td> 
   <td>Met een basisstructuur kunt u een formulier (een basisblad) maken met velden die de gewenste structuur voor uw pagina's weerspiegelen. Met dit formulier kunt u eenvoudig pagina's maken op basis van deze structuur.</td> 
  </tr> 
  <tr> 
   <td>Beveiliging - <a href="/help/sites-administering/notification.md">Self-Service Configuration </a> </td> 
   <td> </td> 
   <td>Hiermee kunt u de e-mails configureren die gebruikers automatisch ontvangen wanneer ze een account maken of een wachtwoord opnieuw instellen, en een opnieuw ingesteld wachtwoord bevestigen.</td> 
  </tr> 
  <tr> 
   <td><a href="/help/sites-administering/campaign-segmentation.md">Segmentering</a></td> 
   <td> </td> 
   <td>De bezoekers van de plaats hebben verschillende belangen en doelstellingen wanneer zij aan een plaats komen. Kennis van deze doelstellingen en het voldoen aan de verwachtingen is een belangrijke succesfactor voor online marketing. Segmentering helpt dit te bereiken door de details van een bezoeker te analyseren en te karakteriseren.<br /> </td> 
  </tr> 
  <tr> 
   <td><a href="/help/communities/working-with-srp.md">socialconfig</a></td> 
   <td> </td> 
   <td>Standaard SRP-configuratie. Zie <a href="/help/communities/srp-config.md">Opslagconfiguratie</a> console.</td> 
  </tr> 
  <tr> 
   <td>taakbeheer</td> 
   <td> </td> 
   <td>Geen actieve functionaliteit met betrekking tot dit item.</td> 
  </tr> 
  <tr> 
   <td>huurders</td> 
   <td> </td> 
   <td>Geen actieve functionaliteit met betrekking tot dit item.</td> 
  </tr> 
  <tr> 
   <td>Versioning - <a href="/help/sites-deploying/version-purging.md">Versies wissen</a></td> 
   <td> </td> 
   <td>Hiermee kunt u de paginaversies naar wens wissen.</td> 
  </tr> 
  <tr> 
   <td>Virtuele opslagplaatsen</td> 
   <td> </td> 
   <td>U kunt een virtuele opslagplaats instellen met behulp van de functie voor het koppelen van werkruimten om inhoudstoepassingen met JCR-functionaliteit vereenvoudigde toegang te bieden tot de infrastructuur voor JCR-inhoud op basis van CRX en de JCR-connectors.</td> 
  </tr> 
  <tr> 
   <td>wachtwoorden</td> 
   <td> </td> 
   <td>Afgekeurd. Zie <a href="/help/communities/moderate-ugc.md#watchwords">Communautaire inhoud moderniseren</a></td> 
  </tr> 
  <tr> 
   <td><a href="/help/sites-administering/workflows.md">Workflow</a></td> 
   <td> </td> 
   <td>Workflows bepalen een reeks handelingen op pagina's of digitale elementen die een redactioneel proces ondersteunen.</td> 
  </tr> 
 </tbody> 
</table>

## Gereedschappen - Voor aanraking geoptimaliseerde gebruikersinterface {#tools-touch-optimized-ui}

<table> 
 <tbody> 
  <tr> 
   <th>Sectie</th> 
   <th>Optie</th> 
   <th>Doel</th> 
  </tr> 
  <tr> 
   <td>Authoring</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> </td> 
   <td><a href="/help/sites-classic-ui-authoring/classic-personalization-campaigns.md">Campagnes</a></td> 
   <td>Beheer uw marketingcampagnes.</td> 
  </tr> 
  <tr> 
   <td> </td> 
   <td><a href="/help/sites-authoring/launches.md">Lanceringen</a></td> 
   <td>Beheer uw marketing lanceringen.</td> 
  </tr> 
  <tr> 
   <td>Taken</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> </td> 
   <td><a href="/help/sites-authoring/task-content.md">Inbox</a></td> 
   <td>Beheer uw Postvak IN-items.</td> 
  </tr> 
  <tr> 
   <td>Bewerkingen</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> </td> 
   <td><a href="/help/sites-administering/security.md">Gebruikers en groepen </a></td> 
   <td>Uw gebruikers en groepen beheren.</td> 
  </tr> 
  <tr> 
   <td> </td> 
   <td><a href="/help/sites-authoring/tags.md">Tagbeheer</a></td> 
   <td>Organiseer uw tags en hun naamruimten.</td> 
  </tr> 
  <tr> 
   <td> </td> 
   <td><a href="https://helpx.adobe.com/cloud-manager/using/using-cloud-manager.html">Cloud Services</a></td> 
   <td>Verbind met Adobe Marketing Cloud.</td> 
  </tr> 
  <tr> 
   <td> </td> 
   <td><a href="/help/sites-administering/workflows.md">Workflows</a></td> 
   <td>Workflows modelleren en beheren.</td> 
  </tr> 
  <tr> 
   <td> </td> 
   <td><a href="/help/sites-deploying/replication.md">Replicatie</a></td> 
   <td>Meerdere websites maken en beheren.</td> 
  </tr> 
  <tr> 
   <td> </td> 
   <td><a href="/help/sites-administering/reporting.md">Rapporten</a></td> 
   <td>Creeer en controleer douanerapporten.<br /> </td> 
  </tr> 
  <tr> 
   <td> </td> 
   <td><a href="/help/sites-developing/hobbes.md">Testen</a></td> 
   <td>Voer tests uit die voor uw toepassing zijn gedefinieerd.</td> 
  </tr> 
  <tr> 
   <td>Graniet</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> </td> 
   <td><a href="/help/sites-developing/developing-with-crxde-lite.md">CRXDE Lite</a></td> 
   <td>Ontwikkel toepassingen met web-based winde.</td> 
  </tr> 
  <tr> 
   <td> </td> 
   <td><a href="/help/sites-administering/package-manager.md">Pakketten</a></td> 
   <td>Toepassingen verpakken en delen.</td> 
  </tr> 
  <tr> 
   <td> </td> 
   <td><a href="/help/sites-administering/package-manager.md#package-share">Package Share</a></td> 
   <td>Download toepassingen van Adobe en de gemeenschap.<br /> </td> 
  </tr> 
  <tr> 
   <td> </td> 
   <td><a href="/help/sites-deploying/offloading.md#administering-topologies">Topologiebrowser</a></td> 
   <td>Bekijk de instantietopologie.</td> 
  </tr> 
  <tr> 
   <td> </td> 
   <td><a href="/help/sites-deploying/offloading.md">Browser verschuiven</a></td> 
   <td>Offloading beheren.</td> 
  </tr> 
  <tr> 
   <td> </td> 
   <td><a href="/help/sites-deploying/monitoring-and-maintaining.md#backups">Back-up</a></td> 
   <td>Voer back-uptaken uit.</td> 
  </tr> 
  <tr> 
   <td> </td> 
   <td>Webconsole<br /> </td> 
   <td>Configureer en beheer het toepassingsplatform.</td> 
  </tr> 
  <tr> 
   <td> </td> 
   <td>Webconsole-configuratiedump<br /> </td> 
   <td>Download de configuratiestatus van de webconsole.<br /> </td> 
  </tr> 
  <tr> 
   <td> </td> 
   <td>Gebruikers</td> 
   <td>Uw gebruikers beheren.</td> 
  </tr> 
  <tr> 
   <td> </td> 
   <td>Groepen</td> 
   <td>Beheer uw groepen.</td> 
  </tr> 
  <tr> 
   <td>Externe bronnen<br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> </td> 
   <td>Documentatie</td> 
   <td>Bekijk de documentatie van het Beheer van de Ervaring van het Web.<br /> </td> 
  </tr> 
  <tr> 
   <td> </td> 
   <td>Bronnen voor ontwikkelaars</td> 
   <td>Bronnen en downloads voor ontwikkelaars.</td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Sommige van de bovenstaande opties zijn eigenlijk gekoppeld aan de klassieke interface.

