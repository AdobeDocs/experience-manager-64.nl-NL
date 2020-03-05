---
title: Aanbieden en leveren
seo-title: Aanbieden en leveren
description: 'null'
seo-description: 'null'
uuid: 1253b6a5-6bf3-42b1-be3a-efa23b6ddb51
contentOwner: User
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/MOBILE
discoiquuid: 672d5b1e-6b2f-4afe-ab04-c398e5ef45d5
translation-type: tm+mt
source-git-commit: 9d03a3988b2c8e34b9009d80a53d8b8508b5f0aa

---


# Aanbieden en leveren{#rendering-and-delivery}

>[!NOTE]
>
>Adobe adviseert gebruikend de Redacteur van het KUUROORD voor projecten die het enig-paginatoepassings kader-gebaseerde cliënt-zij teruggeven vereisen (b.v. Reageren). [Meer](/help/sites-developing/spa-overview.md)weten?

De inhoud AEM kan gemakkelijk via het [Verdelen StandaardServlets](https://sling.apache.org/documentation/bundles/rendering-content-default-get-servlets.html) worden teruggegeven om [JSON](https://sling.apache.org/documentation/bundles/rendering-content-default-get-servlets.html#default-json-rendering) en andere formaten terug te geven.

Die uit-van-de-doos teruggeeft typisch lopen de bewaarplaats en terugkeren inhoud zoals is.

AEM, via het Sling, steunt ook het ontwikkelen van en het opstellen van douane het slingeren renderers om volledige controle van het teruggegeven schema en de inhoud te nemen.

De Standaard van de Diensten van de inhoud Renderers vult het hiaat tussen uit-van-de-doos het Scheren Gebreken en de Ontwikkeling van de Douane die aanpassing en controle van vele aspecten van de teruggegeven inhoud zonder ontwikkeling toestaan.

Het volgende diagram toont het teruggeven van de inhoudsdiensten.

![chlimage_1-15](assets/chlimage_1-15.png)

## JSON aanvragen {#requesting-json}

Gebruik **&lt;RESOURCE.caas[.&lt;EXPORT-CONFIG][.&lt;EXPORT-CONFIG].json** om JSON aan te vragen.

<table>
 <tbody>
  <tr>
   <td>MIDDEL</td>
   <td>een entiteitmiddel onder /content/entities<br /> of <br /> een inhoudsmiddel onder /content</td>
  </tr>
  <tr>
   <td>EXPORTCONFIG</td>
   <td><p><strong>OPTIONEEL</strong><br /> </p> <p>een de uitvoerconfiguratie die onder /apps/mobileapps/caas/exportConfigs/EXPORT-CONFIG<br /> wordt gevonden <br /> als het weglaten van de standaard de uitvoerconfiguratie zal worden toegepast </p> </td>
  </tr>
  <tr>
   <td>DEPTH-INT</td>
   <td><strong>OPTIONELE</strong><br /> <br /> diepteterugkeer voor het teruggeven van kinderen zoals die in het Verzamelen worden gebruikt</td>
  </tr>
 </tbody>
</table>

## Het creëren van de Vormen van de Uitvoer {#creating-export-configs}

De uitvoer vormt kan worden gecreeerd om het teruggeven aan te passen JSON.

U kunt een configuratieknooppunt onder */apps/mobileapps/caas/exportConfigs tot stand brengen.*

| Naam knooppunt | Naam van de configuratie (voor het teruggeven van selecteur) |
|---|---|
| jcr:primaryType | niet:ongestructureerd |

De volgende lijst toont de eigenschappen van de Uitvoer vormt:

<table>
 <tbody>
  <tr>
   <td><strong>Naam</strong></td>
   <td><strong>Type</strong></td>
   <td><strong>Standaard (als, niet reeks)</strong></td>
   <td><strong>Waarde</strong></td>
   <td><strong>Beschrijving</strong></td>
  </tr>
  <tr>
   <td>includeComponents</td>
   <td>Tekenreeks[]</td>
   <td>alles opnemen</td>
   <td>slingeren:resourceType</td>
   <td>sluit details voor knopen met gespecificeerde sling uit:resourceType van de uitvoer van JSON</td>
  </tr>
  <tr>
   <td>uitsluitenOnderdelen</td>
   <td>Tekenreeks[]</td>
   <td>niets uitsluiten</td>
   <td>slingeren:resourceType</td>
   <td>omvat details slechts voor knopen met gespecificeerde sling:resourceType van de uitvoer van JSON</td>
  </tr>
  <tr>
   <td>uitsluitenPropertyPrefixen</td>
   <td>Tekenreeks[]</td>
   <td>niets uitsluiten</td>
   <td>Voorvoegsels voor onroerend goed</td>
   <td>sluit eigenschappen uit die met gespecificeerde prefixen van de uitvoer JSON beginnen</td>
  </tr>
  <tr>
   <td>uitsluitenEigenschappen</td>
   <td>Tekenreeks[]</td>
   <td>niets uitsluiten</td>
   <td>Eigendomsnamen</td>
   <td>sluit gespecificeerde eigenschappen van de uitvoer uit JSON</td>
  </tr>
  <tr>
   <td>includeProperties</td>
   <td>Tekenreeks[]</td>
   <td>alles opnemen</td>
   <td>Eigendomsnamen</td>
   <td><p>als de set<br /> van de prefixPropertyPrefixes dit gespecificeerde eigenschappen omvat ondanks het aanpassen van de prefix die wordt uitgesloten,</p> <p>anders (sluit genegeerde eigenschappen uit) omvat slechts deze eigenschappen</p> </td>
  </tr>
  <tr>
   <td>inclusiefChildren</td>
   <td>Tekenreeks[]</td>
   <td>alles opnemen</td>
   <td>onderliggende namen</td>
   <td>sluit gespecificeerde kinderen van de uitvoer van JSON uit</td>
  </tr>
  <tr>
   <td>uitsluitenKinderen</td>
   <td>Tekenreeks[]<br /> <br /> </td>
   <td>niets uitsluiten</td>
   <td>onderliggende namen</td>
   <td>omvatten slechts gespecificeerde kinderen van de uitvoer van JSON, sluit andere uit</td>
  </tr>
  <tr>
   <td>naam wijzigenEigenschappen</td>
   <td>Tekenreeks[]<br /> <br /> </td>
   <td>noem niets anders</td>
   <td>&lt;actual_property_name&gt;,&lt;replacement_property_name&gt;</td>
   <td>noem eigenschappen anders gebruikend vervangingen</td>
  </tr>
 </tbody>
</table>

### Het type van bron de uitvoer treedt met voeten {#resource-type-export-overrides}

Creeer een configuratieknooppunt onder */apps/mobileapps/caas/exportConfigs.*

| name | resourceTypeOverrijdt |
|---|---|
| jcr:primaryType | niet:ongestructureerd |

De volgende lijst toont de eigenschappen:

<table>
 <tbody>
  <tr>
   <td><strong>Naam</strong></td>
   <td><strong>Type</strong></td>
   <td><strong>Standaard (als, niet reeks)</strong></td>
   <td><strong>Waarde</strong></td>
   <td><strong>Beschrijving</strong></td>
  </tr>
  <tr>
   <td>&lt;SELECTOR_TO_INC&gt;</td>
   <td>Tekenreeks[] </td>
   <td>-</td>
   <td>slingeren:resourceType</td>
   <td>Voor de volgende het slingeren middeltypes, keer niet de de mislukte uitvoer van CaaS terug.<br /> Keer een klant terug json de uitvoer door het middel terug te geven zoals;<br /> &lt;BRON&gt;.&lt;SELECTOR_TO_INC&gt;.json </td>
  </tr>
 </tbody>
</table>

### Bestaande contentservices exporteren Configureer {#existing-content-services-export-configs}

De Diensten van de inhoud omvatten twee de uitvoerconfiguraties:

* gebrek (geen gespecificeerde config)
* pagina (om plaatspagina&#39;s terug te geven)

#### Standaard exportconfiguratie {#default-export-configuration}

De standaard de uitvoerconfiguratie van de Diensten van de inhoud zal worden toegepast als config in gevraagde URI wordt gespecificeerd.

&lt;RESOURCE>.caas[.&lt;DEPTH-INT>].json

<table>
 <tbody>
  <tr>
   <td><strong>Naam</strong></td>
   <td><strong>Waarde</strong></td>
  </tr>
  <tr>
   <td>uitsluitenEigenschappen</td>
   <td> </td>
  </tr>
  <tr>
   <td>uitsluitenPropertyPrefixen</td>
   <td>jcr:,sling:,cq:,eik:,pge-</td>
  </tr>
  <tr>
   <td>includeProperties</td>
   <td>jcr:tekst,<br /> tekst jcr:titel,titel<br /> jcr:beschrijving,beschrijving<br /> jcr:lastModified,lastModified<br /> cq:tags,tags<br /> cq:lastModified,lastModified</td>
  </tr>
  <tr>
   <td>includeComponents</td>
   <td> </td>
  </tr>
  <tr>
   <td>uitsluitenOnderdelen</td>
   <td> </td>
  </tr>
  <tr>
   <td>inclusiefChildren</td>
   <td> </td>
  </tr>
  <tr>
   <td>uitsluitenKinderen</td>
   <td> </td>
  </tr>
  <tr>
   <td>Sling JSON Overrijdt</td>
   <td>stichting/onderdelen/afbeelding<br /> wcm/stichting/componenten/image<br /> mobiele apps/caas/componenten/gegevens/inhoudReferentie<br /> mobiele apps/caas/componenten/data/assetlist</td>
  </tr>
 </tbody>
</table>

#### Configuratie voor exporteren pagina {#page-export-configuration}

Deze configuratie breidt het gebrek uit om groeperende kinderen onder een kindknoop te omvatten.

&lt;SITE_PAGE>.caas.page[.&lt;DEPTH-INT>].json

### Additional Resources {#additional-resources}

Zie de middelen hieronder over extra onderwerpen in de Diensten van de Inhoud leren:

* [Modellen ontwikkelen](/help/mobile/administer-mobile-apps.md)
* [Content Services ontwerpen](/help/mobile/develop-content-as-a-service.md)
* [Beheer van contentservices](/help/mobile/developing-content-services.md)

