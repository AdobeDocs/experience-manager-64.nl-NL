---
title: Grondbeginselen van blogs
seo-title: Grondbeginselen van blogs
description: Blogoverzicht
seo-description: Blogoverzicht
uuid: ce0885de-6276-47a2-8f6c-358f0beb2b89
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: de8d0e6d-827b-45fe-a538-d3fe1dec8427
exl-id: 8cff0b7b-c120-462f-8fce-13822073eabb
translation-type: tm+mt
source-git-commit: bd94d3949f0117aa3e1c9f0e84f7293a5d6b03b4
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 1%

---

# Grondbeginselen van blog {#blog-essentials}

Vanaf AEM 6.1 Communities is een blog een gemeenschapsactiviteit. Blogartikelen worden nu vanuit de publicatieomgeving gepost, waar eerder blogartikelen alleen in de auteursomgeving konden worden gemaakt en gepubliceerd.

Blogartikelen kunnen nu door elk lid van de gemeenschap worden gemaakt, tenzij ze beperkt zijn tot geprivilegieerde leden.

Deze pagina bevat de essentiële informatie voor het werken met de blogfunctie.

>[!NOTE]
>
>De onderliggende infrastructuur van de blogfunctie is de journaalfunctie.

## Essentiële elementen voor client-side {#essentials-for-client-side}

De blogfunctie bestaat uit twee hoofdcomponenten die beschikbaar zijn door de functie [Blog](functions.md#blog-function) toe te voegen of door de componenten aan een pagina in auteur toe te voegen geeft wijze uit.

### Blog {#blog}

<table> 
 <tbody>
  <tr>
   <td> <strong>resourceType</strong></td> 
   <td>social/journaal/components/hbs/tijdschrift</td> 
  </tr>
  <tr>
   <td> <a href="scf.md#add-or-include-a-communities-component"><strong>inclusief</strong></a></td> 
   <td>Nee</td> 
  </tr>
  <tr>
   <td> <a href="clientlibs.md"><strong>clientllibs</strong></a></td> 
   <td>cq.ckeditor<br /> cq.social.hbs.stem<br /> cq.social.hbs.Journal</td> 
  </tr>
  <tr>
   <td> <strong>templates</strong></td> 
   <td> /libs/social/journal/components/hbs/journal/journal.hbs<br /> /libs/social/journal/components/hbs/entry_topic/list-item.hbs</td> 
  </tr>
  <tr>
   <td> <strong>css</strong></td> 
   <td> /libs/social/journal/components/hbs/journal/clientlibs/journal.css</td> 
  </tr>
  <tr>
   <td><strong> eigenschappen</strong></td> 
   <td>zie <a href="blog-feature.md">Blogfunctie</a></td> 
  </tr>
 </tbody>
</table>

### Blogzijbalk {#blog-sidebar}

| **resourceType** | sociaal/journaal/componenten/hbs/zijbalk |
|---|---|
| [**inclusief**](scf.md#add-or-include-a-communities-component) | Nee |
| [**clientllibs**](clientlibs.md) | cq.social.hbs.journal_sidebar |
| **sjablonen** | /libs/social/journal/components/hbs/sidebar/sidebar.hbs |
| **css** | /libs/social/journal/components/hbs/sidebar/clientlibs/sidebar.css |
| **eigenschappen** | zie [Blogfunctie](blog-feature.md) |

* [Aanpassingen aan de clientzijde](client-customize.md)

## Essentiële elementen voor server-side {#essentials-for-server-side}

* [Blog API](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/journal/client/api/package-summary.html)

* [Blogeindpunten](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/journal/client/endpoints/package-summary.html)

* [Aanpassingen op de server](server-customize.md)

### Blogfunctie {#blog-function}

Een community-sitestructuur die de [Bog-functie](functions.md#blog-function) bevat, heeft `Blog`- en `Blog Sidebar`-componenten geconfigureerd. De functie Blog steunt het identificeren van een [bevoorrechte gebruikersgroep](users.md#privileged-members-group).

### Toegang tot blogberichten (UGC) {#accessing-blog-entries-ugc}

UGC moet worden gemoderniseerd met behulp van een van de standaardmethoden voor gematigdheid.\
Zie [Door gebruiker gegenereerde inhoud modereren](moderate-ugc.md).

Met ingang van AEM 6.1 Communities omvat het gebruik van een [common store](working-with-srp.md) voor UGC programmatische toegang tot UGC, ongeacht de gekozen opslagoptie (zoals ASRP, MSRP of JSRP).

**De locatie en indeling van de UGC in de opslagplaats kunnen zonder waarschuwing** worden gewijzigd.

Zie:

* [Overzicht](srp.md)  van Storage Resource Provider - inleiding en overzicht van opslaggebruik
* [SRP en de Hoofdzaak](srp-and-ugc.md)  UGC - SRP nutsmethodes en voorbeelden
* [Toegang tot UGC met SRP](accessing-ugc-with-srp.md) - coderingsrichtlijnen
* [SocialUtils Refactoring](socialutils.md)  - in kaart gebrachte vervangen nutsmethodes aan huidige SRP hulpprogrammamethodes

## Primaire uitgever {#primary-publisher}

Wanneer de plaatsing een publicatielandbouwbedrijf is, is het noodzakelijk om een primaire uitgever te identificeren die voor te publiceren artikelen zal opiniepeilen.

Zie [Primaire uitgever](deploy-communities.md#primary-publisher) voor meer informatie.

## Rijke media {#allowing-rich-media} toestaan

Het AEM platform blokkeert koppelingen van andere websites om XSS-aanvallen te voorkomen zoals beschreven in

* [Protect tegen XSS (Cross-Site Scripting)](../../help/sites-developing/security.md#protect-against-cross-site-scripting-xss)

Vanaf AEM 6.2 worden de eerder vereiste wijzigingen die handmatig moeten worden aangebracht, opgenomen in het standaard AntiSamy-configuratiebestand.

Rijke media wordt ingesloten in een blogartikel door het pictogram `Embed Media from External Sites` te selecteren:  ![chlimage_1-471](assets/chlimage_1-471.png)
