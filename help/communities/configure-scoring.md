---
title: Scores en Badges Essentials
seo-title: Scoring and Badges Essentials
description: Overzicht van de functie Scores en Badges
seo-description: Scoring and Badges feature overview
uuid: 858ca54f-b416-445d-a449-cef7eed33926
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: ddb86546-d04b-4967-937b-50a19b0237a0
exl-id: 84aa46d5-4ca4-4f6e-b0b9-fc9907be00a5
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '983'
ht-degree: 0%

---

# Scores en Badges Essentials {#scoring-and-badges-essentials}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Met de functie AEM Communities scoring en badges kunnen leden van de gemeenschap worden geïdentificeerd en beloond.

De details van het instellen van de functie worden beschreven op

* [Scores en badges van gemeenschappen](implementing-scoring.md)

Deze pagina bevat aanvullende technische details:

* Procedure [een badge weergeven](#displaying-badges) als afbeelding of tekst
* Uitgebreid inschakelen [foutopsporing](#debug-log-for-scoring-and-badging)
* Procedure [toegang tot UGC](#ugc-for-scoring-and-badging) met betrekking tot scoring en badging

>[!CAUTION]
>
>De in CRXDE Lite zichtbare implementatiestructuur kan worden gewijzigd.

## Badges weergeven {#displaying-badges}

Of een badge als tekst of beeld wordt getoond wordt gecontroleerd op de cliëntkant in het malplaatje van GB.

Zoek bijvoorbeeld naar `this.isAssigned` in `/libs/social/forum/components/hbs/topic/list-item.hbs`,:

```
{{#each author.badges}}

  {{#if this.isAssigned}}

    <div class="scf-badge-text">

      {{this.title}}

    </div>

  {{/if}}

{{/each}}

{{#each author.badges}}

  {{#unless this.isAssigned}}

    <img class="scf-badge-image" alt="{{this.title}}" title="{{this.title}}" src="{{this.imageUrl}}" />

  {{/unless}}

{{/each}}
```

Indien waar (true), geeft isAssigned aan dat de badge voor een rol is toegewezen en dat de badge als tekst moet worden weergegeven.

Indien onwaar (false), wordt bij Toewijzen aangegeven dat de badge is toegekend voor een verdiende score en dat het badge moet worden weergegeven als een afbeelding.

Wijzigingen in dit gedrag moeten worden aangebracht in een aangepast script (overschrijven of bedekken). Zie [Aanpassing aan clientzijde](client-customize.md).

## Foutopsporingslogboek voor score en Badging {#debug-log-for-scoring-and-badging}

Voor foutopsporing in scores en badging kan een aangepast logbestand worden ingesteld. De inhoud van dit logbestand kan dan aan de klantenondersteuning worden verstrekt als er problemen met de functie worden ondervonden.

Ga voor gedetailleerde instructies naar [Een aangepast logbestand maken](../../help/sites-deploying/monitoring-and-maintaining.md#create-a-custom-log-file).

U kunt als volgt snel een logbestand instellen:

1. Toegang krijgen tot **[!UICONTROL Adobe Experience Manager Web Console Log Support]** bijvoorbeeld

   * http://localhost:4502/system/console/slinglog

1. Selecteer **[!UICONTROL Add new logger]**

   1. Selecteren `DEBUG` for **[!UICONTROL Log Level]**
   1. Voer een naam in voor **[!UICONTROL Log File]** bijvoorbeeld

      * logs/scoring-debug.log
   1. Twee invoeren **[!UICONTROL Logger]** (klasse) items (gebruiken `+` pictogram)

      * `com.adobe.cq.social.scoring`
      * `com.adobe.cq.social.badging`
   1. Selecteer **[!UICONTROL Save]**



![chlimage_1-248](assets/chlimage_1-248.png)

Logboekvermeldingen weergeven:

* Vanuit de webconsole

   * Onder de **[!UICONTROL Status]** menu
   * Selecteer **[!UICONTROL Log Files]**
   * Zoek naar uw naam van het Logdossier, zoals `scoring-debug`

* Op de lokale schijf van de server

   * Het logbestand bevindt zich op &lt;*server-install-dir*>/crx-quickstart/logs/&lt;*log-file-name*>.log
   * Bijvoorbeeld, `.../crx-quickstart/logs/scoring-debug.log`

![chlimage_1-249](assets/chlimage_1-249.png)

## UGC voor scores en Badging {#ugc-for-scoring-and-badging}

Het is mogelijk om UGC met betrekking tot het scoring en het aanbrengen van merktekens te bekijken wanneer gekozen SRP of JSRP of MSRP, maar niet ASRP is. (Als u deze termen niet kent, raadpleegt u [Opslag van communautaire inhoud](working-with-srp.md) en [Overzicht opslagbronprovider](srp.md).)

In de beschrijvingen voor toegang tot scoring- en badinggegevens wordt JSRP gebruikt, omdat de UGC gemakkelijk toegankelijk is via [CRXDE Lite](../../help/sites-developing/developing-with-crxde-lite.md).

**JSRP bij auteur**: experimenteren in de auteursomgeving resulteert in UGC die alleen zichtbaar is vanuit de auteursomgeving.

**JSRP bij publicatie**: ook als het testen op de publicatieomgeving , is het nodig om toegang te krijgen tot CRXDE Lite met beheerdersrechten voor een publicatie - instantie . Als de publicatie-instantie wordt uitgevoerd in [productiemodus](../../help/sites-administering/production-ready.md) (geen samplcontent runmode), is het nodig dat [CRXDE Lite inschakelen](../../help/sites-administering/enabling-crxde-lite.md).

De basislocatie van UGC op JSRP is `/content/usergenerated/asi/jcr/`.

### API&#39;s voor scores en Badging {#scoring-and-badging-apis}

De volgende API&#39;s zijn beschikbaar voor gebruik:

* [com.adobe.cq.social.scoring.api](https://docs.adobe.com/content/docs/en/aem/6-3/develop/ref/javadoc/com/adobe/cq/social/scoring/api/package-summary.html)
* [com.adobe.cq.social.badging.api](https://docs.adobe.com/content/docs/en/aem/6-3/develop/ref/javadoc/com/adobe/cq/social/badging/api/package-summary.html)

De nieuwste JavaDocs voor de geïnstalleerde toepassingen [lozingen](deploy-communities.md#LatestReleases) zijn beschikbaar voor ontwikkelaars van de opslagplaats van Adobe. Zie [Maven gebruiken voor Gemeenschappen: Javadocs](maven.md#javadocs).

**De locatie en de indeling van de UGC in de opslagplaats kunnen zonder waarschuwing worden gewijzigd**.

### Voorbeeld instellen {#example-setup}

De schermafbeeldingen van gegevensopslagruimte zijn afkomstig van het instellen van scoring en badging voor een forum op twee verschillende AEM sites:

1. Een AEM site met een unieke id (een communitysite die met een wizard is gemaakt):

   * Met behulp van de site Aan de slag met zelfstudies (engineers) die tijdens de [aan de slag - zelfstudie](getting-started.md)
   * Zoek het knooppunt voor forumpagina

      * `/content/sites/engage/en/forum/jcr:content`
   * Eigenschappen voor scoring en badges toevoegen

      * `scoringRules = [/etc/community/scoring/rules/comments-scoring,`

         `/etc/community/scoring/rules/forums-scoring]`
      * `badgingRules =[/etc/community/badging/rules/comments-scoring,`

         `/etc/community/badging/rules/forums-scoring]`
   * Zoek het knooppunt voor de forumcomponent

      * `/content/sites/engage/en/forum/jcr:content/content/primary/forum`

         ( `sling:resourceType = social/forum/components/hbs/forum`)
   * Eigenschap toevoegen aan weergaveknoppen

      * `allowBadges = true`
   * Een gebruiker ondertekent in, maakt een forumonderwerp en krijgt een bronzen badge toegewezen





1. Een AEM *zonder* een unieke id:

   * Met de [Community Components Guide](components-guide.md)
   * Zoek het knooppunt voor forumpagina

      * `/content/community-components/en/forum/jcr:content`
   * Eigenschappen voor scoring en badges toevoegen

      ```
      scoringRules = [/etc/community/scoring/rules/comments-scoring,
      /etc/community/scoring/rules/forums-scoring]
      ```

      ```
      badgingRules =[/etc/community/badging/rules/comments-scoring,
      /etc/community/badging/rules/forums-scoring]
      ```

   * Zoek het knooppunt voor de forumcomponent

      * `/content/community-components/en/forum/jcr:content/content/forum`

         ( `sling:resourceType = social/forum/components/hbs/forum`)
   * Eigenschap toevoegen aan weergaveknoppen

      * `allowBadges = true`
   * Een gebruiker ondertekent in, maakt een forumonderwerp en krijgt een bronzen badge toegewezen




1. Aan een gebruiker wordt een moderatorbadge toegewezen via cURL:

```shell
curl -i -X POST -H "Accept:application/json" -u admin:admin -F ":operation=social:assignBadge" -F "badgeContentPath=/etc/community/badging/images/moderator/jcr:content/moderator.png" http://localhost:4503/home/users/community/w271OOup2Z4DjnOQrviv/profile.social.json
```

Aangezien een gebruiker twee bronzen badges heeft verdiend en een moderatorbadge heeft gekregen, is dit hoe de gebruiker met hun forumingang verschijnt:

![chlimage_1-250](assets/chlimage_1-250.png)

>[!NOTE]
>
>In dit voorbeeld worden de volgende aanbevolen procedures niet gevolgd:
>
>* de namen van scoringregels moeten globaal uniek zijn; ze mogen niet met dezelfde naam eindigen.\
   >  Een voorbeeld van wat *niet* om te doen:\
   >  /etc/community/scoring/rules/site1/forums-scoring\
   >  /etc/community/scoring/rules/site2/forums-scoring
>
>* maken van unieke badge-afbeeldingen voor verschillende AEM sites
>


### Toegang tot UGC-score {#access-scoring-ugc}

Gebruik van de [API&#39;s](#scoring-and-badging-apis) heeft de voorkeur.

Voor onderzoeksdoeleinden, gebruikend JSRP bijvoorbeeld, is de basisomslag die scores bevat

* `/content/usergenerated/asi/jcr/scoring`

De onderliggende node van `scoring`is de naam van de scoreregel. Daarom is het verstandig om regelnamen op een server globaal uniek te scoren.

Voor de plaats van de Ingenieur van de Geometrixx, zijn de gebruiker en hun score in een weg geconstrueerd met de het schrapen regelnaam, plaatsidentiteitskaart van de gemeenschap ( `engage-ba81p`), een unieke id en de id van de gebruiker:

* `.../scoring/forums-scoring/engage-ba81p/6d179715c0e93cb2b20886aa0434ca9b5a540401/riley`

Voor de Community Components Guide-site bevinden de gebruiker en hun score zich in een pad dat is opgebouwd met de naam van de scoreregel, een standaard-id ( `default-site`), een unieke id en de id van de gebruiker:

* `.../scoring/forums-scoring/default-site/b27a17cb4910a9b69fe81fb1b492ba672d2c086e/riley`

De score wordt opgeslagen in de eigenschap `scoreValue_tl` die direct alleen een waarde kunnen bevatten of indirect naar een atomicCounter kunnen verwijzen.

![chlimage_1-251](assets/chlimage_1-251.png)

### Access Badging UGC {#access-badging-ugc}

Gebruik van de [API&#39;s](#scoring-and-badging-apis) heeft de voorkeur.

Voor onderzoeksdoeleinden, gebruikend JSRP bijvoorbeeld, is de basisomslag die informatie over toegewezen of toegekende badges bevat

* /content/usergenerated/asi/jcr

Wordt gevolgd door het pad naar het gebruikersprofiel en eindigt in een map met badges, zoals

* /home/users/community/w271OOup2Z4DjnOQrviv/profile/badges

#### Toegewezen badge {#awarded-badge}

![chlimage_1-252](assets/chlimage_1-252.png)

#### toegewezen badge {#assigned-badge}

![chlimage_1-253](assets/chlimage_1-253.png)

## Aanvullende informatie {#additional-information}

Een gesorteerde lijst met leden weergeven op basis van punten:

* [Leaderboard, functie](functions.md#leaderboard-function) voor opname in een community- of groepssjabloon.
* [Leaderboard-component](enabling-leaderboard.md), de aanbevolen component van de Leaderboard-functie, voor het ontwerpen van pagina&#39;s.
