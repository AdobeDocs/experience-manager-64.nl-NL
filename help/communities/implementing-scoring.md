---
title: Scores en badges van gemeenschappen
seo-title: Communities Scoring and Badges
description: Met AEM Communities scoring en badges kunt u leden van de gebruikersgemeenschap identificeren en belonen
seo-description: AEM Communities scoring and badges lets you identify and reward community members
uuid: ca6f22d6-f25d-4f26-b589-81d1f2c830f9
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: b19b3c24-82a0-468c-a077-9f3edb96afc9
tagskeywords: scoring, badging, badges, gamification
role: Admin
exl-id: 54a4a053-ca44-451a-9a31-f1c1e8cb7002
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '2897'
ht-degree: 1%

---

# Scores en badges van gemeenschappen {#communities-scoring-and-badges}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Overzicht {#overview}

Met de functie AEM Communities scoring en badges kunnen leden van de gemeenschap worden geïdentificeerd en beloond.

De belangrijkste aspecten van scoring en badges zijn:

* [Badges toewijzen](#assign-and-revoke-badges) de rol van een lid in de gemeenschap te bepalen

* [Basistoekenning van badges](#enable-scoring) aan de leden om hun deelname aan te moedigen (hoeveelheid geschapen inhoud)
* [Geavanceerde toekenning van badges](advanced.md) om leden te identificeren als deskundigen (kwaliteit van de gemaakte inhoud)

**Opmerking** de toekenning van badges [standaard niet ingeschakeld](implementing-scoring.md#main-pars-text-237875536).

>[!CAUTION]
>
>De implementatiestructuur die zichtbaar is in CRXDE Lite, kan worden gewijzigd zodra de interface beschikbaar is.

## Badges {#badges}

De badges worden onder de naam van een lid geplaatst om hun rol of hun status in de gemeenschap aan te geven. Badges kunnen als een afbeelding of als een naam worden weergegeven. Wanneer de naam als afbeelding wordt weergegeven, wordt deze opgenomen als alternatieve tekst voor toegankelijkheid.

Standaard bevinden badges zich in de dataopslag op

* /etc/community/badging/images

Als ze op een andere locatie zijn opgeslagen, moeten ze door iedereen toegankelijk worden gelezen.

De badges zijn in de UGC verschillend wat betreft de vraag of zij volgens de regels werden toegewezen of verdiend. Momenteel worden toegewezen badges weergegeven als tekst en worden verdiende badges als een afbeelding weergegeven.

### Bandenbeheer-interface {#badge-management-ui}

De Gemeenschappen [Badges-console](badges.md) biedt de mogelijkheid om aangepaste badges toe te voegen die voor een lid kunnen worden weergegeven wanneer het lid zijn verdiend (toegekend) of wanneer het een specifieke rol in de gemeenschap (toegewezen) op zich neemt.

### Toegewezen badges {#assigned-badges}

Op rollen gebaseerde badges worden door een beheerder toegewezen aan leden van de community op basis van hun rol in de community.

Toegewezen (en aangepaste) badges worden opgeslagen in de geselecteerde [SRP](srp.md) en niet rechtstreeks toegankelijk zijn. Totdat een GUI beschikbaar is, is het enige middel om op rol-gebaseerde badges toe te wijzen dit met code of cURL. Zie de sectie over cURL-instructies [Badges toewijzen en intrekken](#assign-and-revoke-badges).

In de release zijn drie badges op basis van rollen opgenomen:

* Moderator

   `/etc/community/badging/images/moderator/jcr:content/moderator.png`

* Groepsbeheer

   `/etc/community/badging/images/group-manager/jcr:content/group-manager.png`

* Geprivilegiseerd lid

   `/etc/community/badging/images/privileged-member/jcr:content/privileged-member.png`

![chlimage_1-366](assets/chlimage_1-366.png)

### Toegewezen badges {#awarded-badges}

Op basis van beloningen ontvangen de leden van de gemeenschap een toegangspasje met een score op basis van regels die gelden voor hun activiteiten in de gemeenschap.

Om badges als beloning voor activiteit te kunnen weergeven, moeten er twee dingen gebeuren:

* Badging moet [enabled](#enable-badges-for-component) voor de component feature
* Scorebord en badgregels moeten [toegepast](#apply-rules-to-content) op de pagina (of voorouder) waarop de component is geplaatst

De release bevat drie beloningsbadges:

* Goud

   `/etc/community/badging/images/gold-badge/jcr:content/gold.png`

* Zilver

   `/etc/community/badging/images/silver-badge/jcr:content/silver.png`

* Brons

   `/etc/community/badging/images/bronze-badge/jcr:content/bronze.png`

![chlimage_1-367](assets/chlimage_1-367.png)

>[!NOTE]
>
>Scoreregels kunnen worden geconfigureerd om negatieve punten toe te wijzen voor posten die als onjuist zijn gemarkeerd en beïnvloeden zo de score. Als een badge echter eenmaal is behaald, wordt deze niet automatisch verwijderd vanwege wijzigingen in de score- of scoringregel.
>
>Toegewezen badges kunnen op dezelfde wijze worden ingetrokken als toegewezen badges. Zie de [Badges toewijzen en intrekken](#assign-and-revoke-badges) sectie. De toekomstige verbeteringen zullen een UI omvatten om de badges van leden te beheren.

### Aangepaste badges {#custom-badges}

Aangepaste badges kunnen worden geïnstalleerd met de [Badges-console](badges.md) en toegewezen of opgegeven in badgingregels.

Wanneer deze vanaf de Badges-console zijn geïnstalleerd, worden aangepaste badges automatisch naar de publicatieomgeving gerepliceerd.

## Muziek inschakelen {#enable-scoring}

Scores is niet standaard ingeschakeld. De basisstappen voor het opzetten en mogelijk maken van scoring en toekenning van badges zijn:

* Regels identificeren voor het verdienen van punten ([scores](#scoring-rules))
* Voor punten die per scoreregels worden geaccumuleerd, wijst u [badges](#badges) ([spelregels](#badging-rules))

* [De regels voor scoring en badges toepassen op een gemeenschapssite](#apply-rules-to-content)
* [Naamgeving voor community-functies inschakelen](#enable-badges-for-component)

Zie de [Snel testen](#quick-test) om het scoren voor een communautaire site mogelijk te maken met de standaardregels voor scoring en badging voor forums en opmerkingen.

### Regels toepassen op inhoud {#apply-rules-to-content}

Als u scoring en badges wilt inschakelen, voegt u de eigenschappen toe `scoringRules` en `badgingRules`naar een knooppunt in de inhoudsstructuur voor de site.

Als de site al is gepubliceerd nadat alle regels zijn toegepast en componenten zijn ingeschakeld, publiceert u de site opnieuw.

De regels die op een badging-toegelaten component van toepassing zijn zijn die voor de huidige knoop of zijn voorvader.

Als het knooppunt van het type is `cq:Page` (aanbevolen), voegt u met behulp van CRXDE|Lite de eigenschappen toe aan de bijbehorende `jcr:content`knooppunt.

| **Eigenschap** | **Type** | **Beschrijving** |
|---|---|---|
| badgingRules | String[] | een arraylijst met [spelregels](#badging-rules) |
| scoringRules | String[] | een arraylijst met [scores](#scoring-rules) |

>[!NOTE]
>
>Als een het scoren regel geen effect op het verlenen van badges lijkt te hebben, zorg ervoor de het scoren regel niet door het scoringRules bezit van de merkingsregel is geblokkeerd. Zie de sectie met de titel [Badgingregels](#badging-rules).

### Badges voor component inschakelen {#enable-badges-for-component}

De regels voor inschalen en insluiten zijn alleen van toepassing op instanties van componenten die intekenen hebben ingeschakeld door de componentconfiguratie te bewerken in [ontwerpmodus](author-communities.md).

Een Booleaanse eigenschap, `allowBadges`schakelt u de weergave van badges voor een componentinstantie in of uit. Het is configureerbaar in [dialoogvenster voor bewerken van componenten](author-communities.md) voor forum, QnA en commentaarcomponenten door een checkbox geëtiketteerd **Badges weergeven**.

#### Voorbeeld: allowBadges voor de componentinstantie Forum {#example-allowbadges-for-forum-component-instance}

![chlimage_1-368](assets/chlimage_1-368.png)

>[!NOTE]
>
>Elke component kan worden bedekt om badges weer te geven met behulp van de GB-code in forums, QnA en opmerkingen als voorbeeld.

## Scoreregels {#scoring-rules}

Scoreregels vormen de basis voor scoring met het oog op het toekennen van badges.

Heel eenvoudig, is elke het scoren regel een lijst van één of meerdere sub-regels. Scoreregels worden toegepast op de inhoud van de communautaire plaats om de regels te identificeren om toe te passen wanneer de badges worden toegelaten.

Scoreregels worden overgeërfd, maar niet additief. Bijvoorbeeld:

* Als page2 het schrapen regel2 bevat en zijn voorouder page1 het schrapen regel1 bevat
* Een actie op een page2 component zal zowel rule1 als rule2 aanhalen
* Indien beide regels toepasselijke subregels bevatten voor hetzelfde `topic/verb`:

   * Alleen de subregel van regel2 heeft invloed op de score
   * De scores van beide subregels worden niet bij elkaar opgeteld

Wanneer er meer dan één scoreregel is, worden de scores afzonderlijk gehandhaafd voor elke regel.

Scoreregels zijn knooppunten van het type `cq:Page` met eigenschappen `jcr:content`knooppunt dat de lijst opgeeft met subregels die deze definiëren.

Scores worden opgeslagen in SRP.

>[!NOTE]
>
>Beste praktijken: Geef elke scoreregel een unieke naam.
>
>Namen van scoreregelregels moeten globaal uniek zijn. ze mogen niet met dezelfde naam eindigen.
>
>Een voorbeeld van wat *niet* om te doen:\
>/etc/community/scoring/rules/site1/forums-scoring\
>/etc/community/scoring/rules/site2/forums-scoring

### Subregels voor score {#scoring-sub-rules}

De scoringsubregels bevatten de eigenschappen die de waarden voor deelname aan de gemeenschap in detail beschrijven.

Elke scoring-subregel identificeert

* Welke activiteiten worden bijgehouden
* Welke specifieke communautaire functie is hierbij betrokken?
* Hoeveel punten worden toegekend

Standaard worden punten toegewezen aan het lid dat de handeling uitvoert, tenzij in de subregel wordt aangegeven dat de eigenaar van de inhoud de punten ontvangt ( `forOwner`).

Elke subregel kan in een of meer scoreregels worden opgenomen.

De naam van de subregel volgt doorgaans het patroon van het gebruik van een *onderwerp, object* en *werkwoord*. Bijvoorbeeld:

* member-comment-create
* lid-ondervraagden

Subregels zijn knooppunten van het type `cq:Page` met eigenschappen `jcr:content`knooppunt dat de [werkwoorden en onderwerpen](#topics-and-verbs) .

<table> 
 <tbody> 
  <tr> 
   <th>Eigenschap</th> 
   <th>Type</th> 
   <th> Beschrijving van waarde</th> 
  </tr> 
  <tr> 
   <td><i><code>VERB</code></i></td> 
   <td>Lang</td> 
   <td> 
    <ul> 
     <li>vereist; het werkwoord correspondeert met een gebeurtenisactie</li> 
     <li>er moet minstens één werkb-eigenschap zijn</li> 
     <li>het werkwoord moet in alle HOOFDLETTERS worden ingevoerd</li> 
     <li>er kunnen meerdere werkbalkeigenschappen zijn, maar geen duplicaten</li> 
     <li>de waarde is de score die moet worden toegepast voor deze gebeurtenis</li> 
     <li>de waarde kan positief of negatief zijn</li> 
     <li>een lijst met in de release ondersteunde werkwoorden vindt u in de <a href="#topics-and-verbs">Onderwerpen en werven</a> sectie</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td><code>topics</code></td> 
   <td>String[]</td> 
   <td> 
    <ul> 
     <li>facultatief; beperkt subregel tot componenten van de gemeenschap die door gebeurtenisonderwerpen worden geïdentificeerd</li> 
     <li>indien gespecificeerd: waarde is een tekenreeks met meerdere waarden voor gebeurtenisonderwerpen</li> 
     <li>een lijst met onderwerpen in de release staat in de <a href="#topics-and-verbs">Onderwerpen en werven</a> sectie</li> 
     <li>Standaard is dit van toepassing op alle onderwerpen die aan het werkwoord of de werkwoorden zijn gekoppeld</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td><code>forOwner</code></td> 
   <td>Boolean</td> 
   <td> 
    <ul> 
     <li>facultatief; niet van belang wanneer een lid handelt over de inhoud die hij bezit</li> 
     <li>indien waar (true), score toepassen op de eigenaar van inhoud waarop wordt gehandeld</li> 
     <li>Indien onwaar (false), score toepassen op een lid dat actie onderneemt</li> 
     <li>default is false</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td><code>scoringType</code></td> 
   <td>String</td> 
   <td> 
    <ul> 
     <li>facultatief; geeft de scores aan</li> 
     <li>indien "basic", de scoring-engine op basis van de hoeveelheid 
      <ul> 
       <li>opgenomen in de release</li> 
      </ul> </li> 
     <li>geeft, indien "geavanceerd", de scores aan op basis van kwaliteit en hoeveelheid 
      <ul> 
       <li>vereist een <a href="advanced.md">extra pakket</a></li> 
      </ul> </li> 
     <li>default is "basic"</li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Inclusief rangtelregels en subregels {#included-scoring-rules-and-sub-rules}

In de release zijn twee scoreregels opgenomen voor de [Functie van forum](functions.md#forum-function) (elk voor de onderdelen Forum en Opmerkingen van het Forum):

1. /etc/community/scoring/rules/comments-scoring

   * subRules[] =

      /etc/community/scoring/rules/sub-rules/member-comment-create

      /etc/community/scoring/rules/sub-rules/member-receive-voice

      /etc/community/scoring/rules/sub-rules/member-giving-voice

      /etc/community/scoring/rules/sub-rules/member-is-moderated

1. /etc/community/scoring/rules/forums-scoring

   * subRules[] =

      /etc/community/scoring/rules/sub-rules/member-forum-create

      /etc/community/scoring/rules/sub-rules/member-receive-voice

      /etc/community/scoring/rules/sub-rules/member-giving-voice

      /etc/community/scoring/rules/sub-rules/member-is-moderated

**Opmerkingen:**

* Beide `rules`en `sub-rules` knooppunten zijn van het type cq:Page

* `subRules`is een kenmerk van het type String[] over de regels `jcr:content` node

* `sub-rules` kunnen worden gedeeld door verschillende scoreregels
* `rules`moet zich bevinden op een opslagplaats met leesmachtigingen voor iedereen

   * Namen van regels moeten uniek zijn, ongeacht de locatie

### Aangepaste sorteerregels activeren {#activating-custom-scoring-rules}

Wijzigingen of toevoegingen aan de in de ontwerpomgeving aangebrachte scoreregels of subregels moeten bij publicatie worden geïnstalleerd.

## Badgingregels {#badging-rules}

De regels van de Badging koppelen het scoring regels aan badges door te specificeren:

* Welke scoreregel
* De score die nodig is om een specifieke badge te ontvangen

Badgingregels zijn knooppunten van het type `cq:Page` met eigenschappen `jcr:content`knooppunt dat de correlatie heeft tussen de scoreregels en scores en badges.

De regels voor het aanbrengen van een kenteken bestaan uit een verplicht `thresholds`eigenschap die een geordende lijst is met scores die aan badges zijn toegewezen. De scores moeten in stijgende waarde worden bevolen. Bijvoorbeeld:

* `1|/etc/community/badging/images/bronze-badge/jcr:content/bronze.png`

   * Een bronzen badge wordt gebruikt om 1 punt te verdienen

* `60|/etc/community/badging/images/silver-badge/jcr:content/silver.png`

   * Een zilveren badge wordt toegekend wanneer 60 punten zijn opgebouwd

* `80|/etc/community/badging/images/gold-badge/jcr:content/gold.png`

   * Een gouden badge wordt afgelezen wanneer 80 punten zijn verzameld

De regels van de Badging zijn gepareerd met het scoring regels, die bepalen hoe de punten zich ophopen. Zie de sectie met de titel [Regels toepassen op inhoud](#apply-rules-to-content).

De `scoringRules`het bezit op een merkingsregel beperkt eenvoudig welke het schatten regels met die bepaalde merkingsregel kunnen worden geparineerd.

>[!NOTE]
>
>Beste praktijken: maak badge-afbeeldingen die uniek zijn voor elke AEM site.

![chlimage_1-369](assets/chlimage_1-369.png)

<table> 
 <tbody> 
  <tr> 
   <th>Eigenschap</th> 
   <th>Type</th> 
   <th>Beschrijving van waarde</th> 
  </tr> 
  <tr> 
   <td>drempelwaarden</td> 
   <td>String[]</td> 
   <td><em>(vereist)</em> Een tekenreeks met meerdere waarden van het formulier 'number|path' 
    <ul> 
     <li>number = score</li> 
     <li>| = de verticale lijn (U+007C)</li> 
     <li>path = full path to badge image resource</li> 
    </ul> De tekenreeksen moeten worden geordend, zodat de getallen in waarde toenemen en er mag geen lege ruimte tussen het getal en het pad worden weergegeven.<br /> Voorbeeld:<br /> <code>80|/etc/community/badging/images/gold-badge/jcr:content/gold.png</code></td> 
  </tr> 
  <tr> 
   <td>badgingType</td> 
   <td>String</td> 
   <td><em>(optioneel)</em> Hiermee wordt de scoring-engine aangeduid als "basic" of "advanced". Zie <a href="advanced.md">Geavanceerde scores en Badges</a>. De standaardwaarde is "basic".</td> 
  </tr> 
  <tr> 
   <td> 
    <code>scoringRules </code></td> 
   <td>String[]</td> 
   <td>(<em>optioneel</em>) Een tekenreeks met meerdere waarden waarmee de merkingsregel wordt beperkt tot het scoren van gebeurtenissen die worden bepaald door de scoreregels</td> 
  </tr> 
 </tbody> 
</table>

### Ingesloten Badgingregels {#included-badging-rules}

In de release zijn twee Badging Rules opgenomen die overeenkomen met de [Scoreregels voor forums en opmerkingen](#includedscoringrules).

* /etc/community/badging/rules/comments-badging
* /etc/community/badging/rules/forums-badging

**Opmerkingen:**

* `rules` knooppunten zijn van het type cq:Page
* `rules`moet zich bevinden op een opslagplaats met leesmachtigingen voor iedereen

   * Namen van regels moeten uniek zijn, ongeacht de locatie

### Aangepaste Badgingregels activeren {#activating-custom-badging-rules}

Wijzigingen of toevoegingen aan badgingregels of afbeeldingen die in de ontwerpomgeving zijn aangebracht, moeten bij publicatie worden geïnstalleerd.

## Badges toewijzen en intrekken {#assign-and-revoke-badges}

De badges kunnen aan de leden worden toegekend met behulp van de [ledenconsole](members.md#badges-tab) of via programmacode met cURL-opdrachten.

De volgende cURL-opdrachten tonen wat nodig is voor een HTTP-aanvraag voor het toewijzen en intrekken van badges. De basisindeling is:

cURL -i -X POST -H *header* -u *signin * -F *operation * -F *badge * *member-profile-url*

*header* = &quot;Accept:application/json&quot;\
aangepaste header die aan de server moet worden doorgegeven (vereist)

*handtekening* = administrator-id:password\
bijvoorbeeld: admin:admin

*bewerking* = &quot;:operation=social:assignBadge&quot; OF &quot;:operation=social:deleteBadge&quot;

*badge* = &quot;badgeContentPath=*badge-image-file*&quot;

*badge-image-file* = de locatie van het merkimagebestand in de gegevensopslagruimte\
bijvoorbeeld: /etc/community/badging/images/moderator/jcr:content/moderator.png

*member-profile-url* = het eindpunt voor het profiel van het lid bij publicatie\
bijvoorbeeld: https://&lt;server>:&lt;port>/home/users/community/riley/profile.social.json

>[!NOTE]
>
>De *member-profile-url*
>
>* Kan verwijzen naar een instantie van de auteur als de [Tunnelservice](users.md#tunnel-service) is ingeschakeld
>* Kan een duistere, willekeurige naam zijn - zie [Beveiligingscontrolelijst](../../help/sites-administering/security-checklist.md#verify-that-you-are-not-disclosing-personally-identifiable-information-in-the-users-home-path) betreffende toegestane id
>


### Voorbeelden: {#examples}

#### Een moderatorbadge toewijzen {#assign-a-moderator-badge}

```shell
curl -i -X POST -H "Accept:application/json" -u admin:admin -F ":operation=social:assignBadge" -F "badgeContentPath=/etc/community/badging/images/moderator/jcr:content/moderator.png" /home/users/community/updcs9DndLEI74DB9zsB/profile.social.json
```

#### Toegewezen zilverbadge intrekken {#revoke-an-assigned-silver-badge}

```shell
curl -i -X POST -H "Accept:application/json" -u admin:admin -F ":operation=social:deleteBadge" -F "badgeContentPath=/etc/community/badging/images/silver/jcr:content/silver.png" /home/users/community/updcs9DndLEI74DB9zsB/profile.social.json
```

>[!NOTE]
>
>Het gebruik van cURL om badges toe te wijzen en in te trekken werkt voor elke badge-afbeelding, maar als deze is toegewezen in plaats van verdiend, worden ze gemarkeerd als toegewezen badges en dienovereenkomstig afgehandeld.

## Scores en badges voor aangepaste componenten {#scoring-and-badges-for-custom-components}

Het scoren en het merkteken de regels kunnen voor douanecomponenten worden gecreeerd door de gebeurtenisonderwerpen te associëren die voor de component met werkwoorden worden gecreeerd.

## Onderwerpen en werven {#topics-and-verbs}

Wanneer leden communiceren met functies van gemeenschappen, worden gebeurtenissen verzonden die asynchrone listeners, zoals meldingen en scoring, kunnen activeren.

De instantie SocialEvent van een component registreert de gebeurtenissen als `actions`die voor een `topic`. De SocialEvent bevat een methode om een `verb`aan de handeling is gekoppeld. Er is een *n-1* relatie tussen `actions`en `verbs`.

Voor de geleverde community-componenten worden in de volgende tabellen de volgende `verbs`gedefinieerd voor elk `topic`beschikbaar voor gebruik in [scoring-subregels](#scoring-sub-rules).

>[!NOTE]
>
>Een nieuwe booleaanse eigenschap, `allowBadges`schakelt u de weergave van badges voor een componentinstantie in of uit. Het zal configureerbaar in bijgewerkt zijn [dialoogvensters voor bewerken van componenten](author-communities.md) via een selectievakje met label **Badges weergeven**.

**[Kalendercomponent](calendar.md)**
SocialEvent `topic`= com/adobe/cq/social/agenda

| **Verb** | **Beschrijving** |
|---|---|
| POST | lid maakt een agendagebeurtenis |
| TOEVOEGEN | opmerkingen van leden over een agendagebeurtenis |
| BIJWERKEN | agendagebeurtenis of commentaar van lid wordt bewerkt |
| DELETE | agendagebeurtenis of commentaar van lid wordt verwijderd |

**[Component Opmerkingen](comments.md)**
SocialEvent `topic`= com/adobe/cq/social/comment

| **Verb** | **Beschrijving** |
|---|---|
| POST | lid maakt een opmerking |
| TOEVOEGEN | reactie van lid op opmerking |
| BIJWERKEN | commentaar van lid is bewerkt |
| DELETE | commentaar van lid is verwijderd |

**[Bestandsbibliotheekcomponent](file-library.md)**
SocialEvent `topic`= com/adobe/cq/social/fileLibrary

| **Verb** | **Beschrijving** |
|---|---|
| POST | lid maakt een map |
| ATTACH | lid uploadt een bestand |
| BIJWERKEN | lid werkt een map of bestand bij |
| DELETE | lid verwijdert een map of bestand |

**[Forum-component](forum.md)**
SocialEvent `topic`= com/adobe/cq/social/forum

| **Verb** | **Beschrijving** |
|---|---|
| POST | lid maakt forum-onderwerp |
| TOEVOEGEN | reacties van leden op forum onderwerp |
| BIJWERKEN | onderwerp of antwoord van lid wordt bewerkt |
| DELETE | forumonderwerp of antwoord van lid wordt verwijderd |

**[Journal-component](blog-feature.md)**
SocialEvent `topic`= com/adobe/cq/social/journaal

| **Verb** | **Beschrijving** |
|---|---|
| POST | lid maakt een blogartikel |
| TOEVOEGEN | commentaar van leden op blogartikel |
| BIJWERKEN | blogartikel of commentaar van lid wordt bewerkt |
| DELETE | blogartikel of commentaar van lid is verwijderd |

**[QnA-component](working-with-qna.md)**
SocialEvent `topic` = com/adobe/cq/social/qna

| **Verb** | **Beschrijving** |
|---|---|
| POST | lid maakt een QnA-vraag |
| TOEVOEGEN | lid maakt een QnA-antwoord |
| BIJWERKEN | Vraag of antwoord van lid wordt bewerkt |
| SELECT | het antwoord van lid is geselecteerd |
| SELECTEREN OPHEFFEN | het antwoord van het lid is gedeselecteerd |
| DELETE | Vraag of antwoord van lid wordt verwijderd |

**[Component Reviews](reviews.md)**
SocialEvent `topic`= com/adobe/cq/social/review

| **Verb** | **Beschrijving** |
|---|---|
| POST | lid maakt beoordeling |
| BIJWERKEN | beoordeling door lid wordt bewerkt |
| DELETE | beoordeling door lid is verwijderd |

**[Beoordelingscomponent](rating.md)**
SocialEvent `topic`= com/adobe/cq/social/tally/rating

| **Verb** | **Beschrijving** |
|---|---|
| WAARDERING TOEVOEGEN | de inhoud van het lid is opgegeven |
| RATING VERWIJDEREN | de inhoud van het lid is neergezet |

**[Stemcomponent](voting.md)**
SocialEvent `topic`= com/adobe/cq/social/tally/stemgerechtigd

| **Verb** | **Beschrijving** |
|---|---|
| STEMMING TOEVOEGEN | de inhoud van het lid is in stemming gebracht |
| STEMMING VERWIJDEREN | over de inhoud van het lid is gestemd |

**Componenten met moderatie**
SocialEvent `topic`= com/adobe/cq/social/moderation

| **Verb** | **Beschrijving** |
|---|---|
| DENKEN | inhoud van lid wordt geweigerd |
| VLAG ALS ONJUIST | inhoud van lid is gemarkeerd |
| ONGESCHIKTE LAG ALS ONJUIST | inhoud van lid is ongemarkeerd |
| ACCEPTEREN | de inhoud van het lid wordt goedgekeurd door moderator |
| SLUITEN | lid sluit commentaar op bewerkingen en reacties |
| OPENEN | opmerking opnieuw openen lid |

### Aangepaste componentgebeurtenissen {#custom-component-events}

Voor een aangepaste component wordt een SocialEvent geïnstantieerd om de gebeurtenissen van de component op te nemen als `actions`die voor een `topic`.

Ter ondersteuning van scoring moet de methode SocialEvent worden overschreven `getVerb()` zodat `verb`is geretourneerd voor elk `action`. De `verb` De geretourneerde waarde voor een handeling kan een veelgebruikte handeling zijn (zoals `POST`) of een voor de component gespecialiseerde instantie (zoals `ADD RATING`). Er is een *n-1* relatie tussen `actions`en `verbs`.

## Problemen oplossen {#troubleshooting}

### Badges worden niet weergegeven {#badges-are-not-appearing}

Als op de inhoud van de website wel scoring- en badingregels zijn toegepast, maar er geen badges worden gereserveerd voor enige activiteit, moet u ervoor zorgen dat badges zijn ingeschakeld voor de instantie van die component.

Zie [Badges voor component inschakelen](#enable-badges-for-component).

### Scoreregel heeft geen effect {#scoring-rule-has-no-effect}

Als op de inhoud van de website scoring- en badingregels zijn toegepast en badges worden toegekend voor bepaalde acties, maar niet voor andere, controleert u of de regel voor badging de scoringregels waarop deze van toepassing is, niet heeft beperkt.

Zie de `scoringRules`eigenschap van [Badgingregels](#badging-rules).

### Hoofdlettergevoelig (typ) {#case-sensitive-typo}

De meeste eigenschappen en waarden, met name de werkwoorden, zijn hoofdlettergevoelig. Bij gebruik in een scoringsubregel moeten de hoekpunten allemaal HOOFDLETTERS zijn.

Als de functie niet naar behoren werkt, controleert u of de gegevens correct zijn ingevoerd.

## Snel testen {#quick-test}

Het is mogelijk om snel scoring en badge te proberen met de [Zelfstudie Aan de slag](getting-started.md) site:

* CRXDE Lite benaderen bij auteur
* Blader naar de basispagina:

   * /content/sites/engc/nl/jcr:content

* Voeg de eigenschap badgingRules toe:

   * **Naam**: `badgingRules`
   * **Type**: `String`
   * Selecteer **[!UICONTROL Multi]**
   * Selecteer **[!UICONTROL Add]**
   * Enter `/etc/community/badging/rules/forums-badging`
   * Selecteer `+`
   * Enter `/etc/community/badging/rules/comments-badging`
   * Selecteer **[!UICONTROL OK]**

* Voeg de eigenschap scoringRules toe:

   * **Naam**: `scoringRules`
   * **Type**: `String`
   * Selecteer **[!UICONTROL Multi]**
   * Selecteer **[!UICONTROL Add]**
   * Enter `/etc/community/scoring/rules/forums-scoring`
   * Selecteer `+`
   * Enter `/etc/community/scoring/rules/comments-scoring`
   * Selecteer **[!UICONTROL OK]**

* Selecteer **[!UICONTROL Save All]**

![chlimage_1-370](assets/chlimage_1-370.png)

Zorg er daarna voor dat de forum- en commentaarcomponenten het weergeven van badges toestaan:

* Opnieuw CRXDE Lite gebruiken
* Bladeren naar de forumcomponent

   * `/content/sites/engage/en/forum/jcr:content/content/primary/forum`

* Voeg de Booleaanse eigenschap allowBadges toe, indien nodig, en zorg ervoor dat dit waar is

   * **Naam**: `allowBadges`
   * **Type**: `Boolean`
   * **Waarde**: `true`

![chlimage_1-371](assets/chlimage_1-371.png)

Volgende, [herpubliceren](sites-console.md#publishing-the-site) de site van de gemeenschap.

Tot slot:

* Bladeren naar de component in de publicatie-instantie
* Aanmelden als lid van de gemeenschap (bijvoorbeeld: weston.mccall@dodgit.com/password)
* Plaats een nieuw forumonderwerp
* De badge wordt alleen weergegeven als de pagina is vernieuwd

   * Afmelden en aanmelden als een ander lid van de gemeenschap (bijvoorbeeld: aaron.mcdonald@mailinator.com/password)

* Selecteer het forum

Dit zou het lid van de gemeenschap een bronzen badge moeten verdienen die met hun forumpost zichtbaar is omdat de eerste drempel van de forums-badging regel een score van 1 is.

![bronzebadge](assets/bronzebadge.png)

## Aanvullende informatie {#additional-information}

Meer informatie is te vinden op de [Scores en Badges Essentials](configure-scoring.md) pagina voor ontwikkelaars.

Voor informatie over de geavanceerde scoring-engine raadpleegt u [Geavanceerde scores en Badges](advanced.md).

Het configureerbare Leaderboard [component](enabling-leaderboard.md) en [function](functions.md#leaderboard-function) vereenvoudigt de weergave van leden en hun scores op een community-site.
