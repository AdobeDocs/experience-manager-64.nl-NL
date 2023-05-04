---
title: Grondbeginselen van blogs
seo-title: Blog Essentials
description: Blogoverzicht
seo-description: Blog overview
uuid: ce0885de-6276-47a2-8f6c-358f0beb2b89
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: de8d0e6d-827b-45fe-a538-d3fe1dec8427
exl-id: 8cff0b7b-c120-462f-8fce-13822073eabb
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 0%

---

# Grondbeginselen van blogs {#blog-essentials}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Vanaf AEM 6.1 Communities is een blog een gemeenschapsactiviteit. Blogartikelen worden nu vanuit de publicatieomgeving gepost, waar eerder blogartikelen alleen in de auteursomgeving konden worden gemaakt en gepubliceerd.

Blogartikelen kunnen nu door elk lid van de gemeenschap worden gemaakt, tenzij ze beperkt zijn tot geprivilegieerde leden.

Deze pagina bevat de essentiële informatie voor het werken met de blogfunctie.

>[!NOTE]
>
>De onderliggende infrastructuur van de blogfunctie is de journaalfunctie.

## Essentiële elementen voor client-kant {#essentials-for-client-side}

De blogfunctie bestaat uit twee hoofdcomponenten die beschikbaar zijn door het toevoegen van de [Blogfunctie](functions.md#blog-function) of door de componenten aan een pagina in auteur toe te voegen geeft wijze uit.

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
   <td>cq.ckeditor<br /> cq.social.hbs.stemden<br /> cq.social.hbs.journaal</td> 
  </tr>
  <tr>
   <td> <strong>sjablonen</strong></td> 
   <td> /libs/social/journal/components/hbs/journal/journal.hbs<br /> /libs/social/journal/components/hbs/entry_topic/list-item.hbs</td> 
  </tr>
  <tr>
   <td> <strong>css</strong></td> 
   <td> /libs/social/journal/components/hbs/journal/clientlibs/journal.css</td> 
  </tr>
  <tr>
   <td><strong> eigenschappen</strong></td> 
   <td>zie <a href="blog-feature.md">Blogonderdeel</a></td> 
  </tr>
 </tbody>
</table>

### Blog Sidebar {#blog-sidebar}

| **resourceType** | sociaal/journaal/componenten/hbs/zijbalk |
|---|---|
| [**inclusief**](scf.md#add-or-include-a-communities-component) | Nee |
| [**clientllibs**](clientlibs.md) | cq.social.hbs.journal_sidebar |
| **sjablonen** | /libs/social/journal/components/hbs/sidebar/sidebar.hbs |
| **css** | /libs/social/journal/components/hbs/sidebar/clientlibs/sidebar.css |
| **eigenschappen** | zie [Blogonderdeel](blog-feature.md) |

* [Aanpassingen aan de clientzijde](client-customize.md)

## Essentiële elementen voor server-side {#essentials-for-server-side}

* [Blog API](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/journal/client/api/package-summary.html)

* [Blogeindpunten](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/journal/client/endpoints/package-summary.html)

* [Aanpassingen op de server](server-customize.md)

### Blogfunctie {#blog-function}

Een community-sitestructuur die de [Bog, functie](functions.md#blog-function) zal gevormd hebben `Blog` en `Blog Sidebar` componenten. De blogfunctie ondersteunt het identificeren van een [geprivilegieerde gebruikersgroep](users.md#privileged-members-group).

### Toegang tot blogberichten (UGC) {#accessing-blog-entries-ugc}

UGC moet worden gemoderniseerd met behulp van een van de standaardmethoden voor gematigdheid.\
Zie [Door gebruiker gegenereerde inhoud modereren](moderate-ugc.md).

Met ingang van AEM 6.1. [gemeenschappelijk archief](working-with-srp.md) voor UGC omvat programmatische toegang tot UGC ongeacht de gekozen opslagoptie (zoals ASRP, MSRP of JSRP).

**De locatie en de indeling van de UGC in de opslagplaats kunnen zonder waarschuwing worden gewijzigd**.

Zie:

* [Overzicht opslagbronprovider](srp.md) - overzicht van het gebruik van introducties en opslagplaatsen
* [SRP en UGC Essentials](srp-and-ugc.md) - SRP-hulpprogrammamethoden en -voorbeelden
* [Toegang tot UGC met SRP](accessing-ugc-with-srp.md) - coderingsrichtlijnen
* [SocialUtils Refactoring](socialutils.md) - het in kaart brengen van afgekeurde nutsmethodes aan huidige SRP nutsmethodes

## Primaire uitgever {#primary-publisher}

Wanneer de plaatsing een publicatielandbouwbedrijf is, is het noodzakelijk om een primaire uitgever te identificeren die voor te publiceren artikelen zal opiniepeilen.

Zie [Primaire uitgever](deploy-communities.md#primary-publisher) voor meer informatie .

## Rijke media toestaan {#allowing-rich-media}

Het AEM platform blokkeert koppelingen van andere websites om XSS-aanvallen te voorkomen zoals beschreven in

* [Protect tegen XSS (Cross-Site Scripting)](../../help/sites-developing/security.md#protect-against-cross-site-scripting-xss)

Vanaf AEM 6.2 worden de eerder vereiste wijzigingen die handmatig moeten worden aangebracht, opgenomen in het standaard AntiSamy-configuratiebestand.

Rijke media wordt ingesloten in een blogartikel door de optie `Embed Media from External Sites` pictogram:  ![chlimage_1-471](assets/chlimage_1-471.png)
