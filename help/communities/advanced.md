---
title: Geavanceerde scores en Badges
seo-title: Advanced Scoring and Badges
description: Geavanceerde scoring instellen
seo-description: Setting up advanced scoring
uuid: 3854b668-729a-42b8-b7cd-5d5ec1ca8380
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 42fb3c50-8728-4897-ade9-6b839294a10e
role: Admin
exl-id: c9406aae-288e-4cdf-ac01-cb26b423639e
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1164'
ht-degree: 0%

---

# Geavanceerde scores en Badges {#advanced-scoring-and-badges}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Overzicht {#overview}

Met geavanceerd scoren kunnen badges worden toegekend om leden te identificeren als experts. Bij geavanceerd zoeken worden punten toegewezen op basis van de hoeveelheid *en* kwaliteit van de inhoud die door een lid wordt gemaakt, terwijl bij elementaire scoring punten worden toegewezen op basis van de hoeveelheid gemaakte inhoud.

Dit verschil is het gevolg van de scores die zijn gebruikt voor de berekening van de scores. De basisscoring-engine past eenvoudige wiskunde toe. De geavanceerde scoring-engine is een adaptief algoritme dat actieve leden belont die waardevolle en relevante inhoud leveren, afgeleid via de verwerking van natuurlijke talen (NLP) van een onderwerp.

Naast inhoudrelevantie houden de scoringsalgoritmen rekening met lidactiviteiten, zoals het stemmen en het percentage antwoorden. Hoewel deze elementen in de standaardscoring kwantitatief worden opgenomen, worden ze bij geavanceerd scoren op algoritmische wijze gebruikt.

Daarom vereist de geavanceerde scoring-engine voldoende gegevens om de analyse zinvol te maken. De prestatiedrempel voor het worden van een expert wordt constant opnieuw geëvalueerd aangezien het algoritme voortdurend aan het volume en de kwaliteit van gecreeerde inhoud aanpast. Er is ook een concept *verval* van oudere posten van een lid. Indien een deskundige niet langer deelneemt aan het onderwerp waar hij of zij de status van deskundige heeft verworven, op een vooraf bepaald tijdstip (zie [configuratie van scèneprogramma&#39;s](#configurable-scoring-engine)) kunnen zij hun status als deskundige verliezen.

Geavanceerde scoring instellen is vrijwel hetzelfde als basisscoring:

* De basis en de geavanceerde het scoren en merkingsregels zijn [toegepast op inhoud](implementing-scoring.md#apply-rules-to-content) op dezelfde wijze
   * Basisregels en geavanceerde regels voor scoring en badging kunnen op dezelfde inhoud worden toegepast
* [Badges voor componenten inschakelen](implementing-scoring.md#enable-badges-for-component) is algemeen

De verschillen bij het instellen van de regels voor scoring en badging zijn:

* Configureerbare geavanceerde scores-engine
* Geavanceerde regels voor scoring:
   * `scoringType` instellen op **[!UICONTROL advanced]**
   * Opsommingstekens vereist

* Geavanceerde regels voor badging:
   * `badgingType` instellen op **[!UICONTROL advanced]**
   * `badgingLevels` vastgesteld op het aantal te gunnen deskundigen
   * Vereisten `badgingPaths` array van badges in plaats van drempels, toewijzing van arraypunten aan badges

>[!NOTE]
>
>Als u geavanceerde mogelijkheden voor scoring en badging wilt gebruiken, installeert u de [Expert Identification-pakket](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Fadobe%2Fpackages%2Fcq610%2Fsocial%2Ffeaturepack%2Fcq-social-expert-identification-pkg).

## Configureerbare scores-engine {#configurable-scoring-engine}

De geavanceerde het schrapen motor verstrekt een configuratie OSGi met parameters die het geavanceerde het schrapen algoritme beïnvloeden.

![chlimage_1-260](assets/chlimage_1-260.png)

* **[!UICONTROL Scoring weights]**
Voor een onderwerp, specificeer het werkwoord dat de hoogste prioriteit zou moeten worden gegeven wanneer het berekenen van de score. Een of meer onderwerpen kunnen worden ingevoerd, maar zijn beperkt tot **één werkwoord per onderwerp**. Zie [Onderwerpen en werven](implementing-scoring.md#topics-and-verbs).

   Ingevoerd als `topic,verb` met de komma ontsnapt. Bijvoorbeeld:

   `/social/forum/hbs/social/forum\,ADD`

   Het gebrek wordt geplaatst aan ADD werkwoord voor QnA en forumcomponenten.


* **[!UICONTROL Scoring range]**

   Het bereik voor geavanceerde scores wordt gedefinieerd door deze waarde (hoogst haalbare score) en 0 (laagste haalbare score).

   De standaardwaarde is 100, zodat het scorebereik 0-100 is.


* **[!UICONTROL Entity decay time interval]**

   Deze parameter vertegenwoordigt het aantal uren waarna alle entiteitscores worden gedecayed. Dit is nodig als u oude inhoud niet meer wilt opnemen in scores voor een communitysite.

   De standaardwaarde is 216000 uur (~24 jaar).


* **[!UICONTROL Scoring growth rate]**

   Geeft de score aan. tussen 0 en scores, waarvoorbij de groei vertraagt om het aantal deskundigen te beperken.

   De standaardwaarde is 50.

## Geavanceerde scoreregels {#advanced-scoring-rules}

In de basisscoring is bekend hoeveel er nodig is om een badge te verdienen.

In de geavanceerde scoring wordt de hoeveelheid voortdurend aangepast op basis van de hoeveelheid kwaliteitsgegevens in het systeem. De scoring wordt voortdurend berekend op een manier die lijkt op een klokcurve.

Als een lid een deskundig badge over een onderwerp verdiende dat niet meer actief is, is er een mogelijkheid dat zij hun badge wegens verval in tijd verliezen.

### ScoringType {#scoringtype}

Een scoreregel is een set scoring-subregels, die elk de `scoringType`.

Als u de geavanceerde scoring-engine wilt aanroepen, `scoringType`moet worden ingesteld op `advanced`.

Zie [Subregels voor score](implementing-scoring.md#scoring-sub-rules).

![chlimage_1-261](assets/chlimage_1-261.png)

### Stopwoorden {#stopwords}

Het geavanceerde het scoren pakket installeert een configuratiemap die een stopwoordendossier bevat:

* `/etc/community/scoring/configuration/stopwords`

Het geavanceerde het scoren algoritme gebruikt de lijst van woorden in het chronwoordendossier om gemeenschappelijke Engelse woorden te identificeren die tijdens inhoudsverwerking worden genegeerd.

Er wordt geen wijziging van dit bestand verwacht.

Als het stopwoordenbestand ontbreekt, genereert het geavanceerde scoring-programma een fout.

## Geavanceerde spelregels {#advanced-badging-rules}

De eigenschappen van de geavanceerde badging-regel verschillen van [basiseigenschappen van insigningsregels](implementing-scoring.md#badging-rules).

In plaats van punten te koppelen aan een badge-afbeelding, is het alleen nodig om het toegestane aantal experts en het toe te kennen badge-image te identificeren.

![chlimage_1-262](assets/chlimage_1-262.png)

| **Eigenschap** | **Type** | **Beschrijving van waarde** |
|---------------|----------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| badgingPath | String[] | (Vereist) Een tekenreeks met meerdere waarden voor badge-afbeeldingen tot het aantal badgingLevels. De wegen van het badge beeld moeten worden bevolen zodat eerste aan de hoogste deskundige wordt toegekend. Als er minder badges zijn dan aangegeven door badgingLevels, vult het laatste badge in de array de rest van de array in. Voorbeeld:/etc/community/badging/images/expert-badge/jcr:content/expert.png |
| badgingLevels | Lang | (Optioneel) Hiermee worden de niveaus van deskundigheid aangegeven die moeten worden toegekend. Als er bijvoorbeeld een expert en een bijna expert (twee badges) moeten zijn, moet de waarde worden ingesteld op 2. Het badgingLevel moet overeenkomen met het aantal deskundige badge-afbeeldingen dat voor de eigenschap badgingPath wordt vermeld. De standaardwaarde is 1. |
| badgingType | String | (Vereist) Hiermee wordt de scoring-engine aangeduid als &quot;basis&quot; of &quot;geavanceerd&quot;. Ingesteld op &quot;advanced&quot; anders is de standaardwaarde &quot;basic&quot;. |
| scoringRules | String[] | (Optioneel) Een tekenreeks met meerdere waarden waarmee de badgingregel wordt beperkt tot het scoren van gebeurtenissen die worden aangeduid met de vermelde scoreregel(s).Voorbeeld-item:/etc/community/scoring/rules/adv-comments-scoringDefault is geen beperking. |

## Opgenomen regels en badge {#included-rules-and-badge}

### Ingesloten badge {#included-badge}

In deze bètaversie is één beloning-gebaseerd deskundige badge opgenomen:

* deskundige

   `/etc/community/badging/images/expert-badge/jcr:content/expert.png`

![chlimage_1-263](assets/chlimage_1-263.png)

Om het expertsymbool als beloning voor activiteiten te kunnen weergeven, moeten er twee dingen gebeuren:

* `badges` moet voor de eigenschap, zoals een forum of component QnA worden toegelaten
* geavanceerde regels voor scoring en badging moeten worden toegepast op de pagina (of voorouder) waarop de component is geplaatst

Zie de basisinformatie voor:

* [Het toelaten van merktekens voor een component](implementing-scoring.md#enable-badges-for-component)
* [Toepassingsregels](implementing-scoring.md#apply-rules-to-content)

### Inclusief rangtelregels en subregels {#included-scoring-rules-and-sub-rules}

In de bètaversie zijn twee geavanceerde scoringregels opgenomen voor de [forumfunctie](functions.md#forum-function) (elk voor het forum en de commentaarcomponenten van het forum):

1. /etc/community/scoring/rules/adv-comments-scoring

   * `subRules[]` =

      /etc/community/scoring/rules/sub-rules/adv-comments-rule

      /etc/community/scoring/rules/sub-rules/adv-voice-rule-owner

      /etc/community/scoring/rules/sub-rules/adv-stemregel

2. /etc/community/scoring/rules/adv-forums-scoring

   * `subRules[]` =

      /etc/community/scoring/rules/sub-rules/adv-forums-rule

      /etc/community/scoring/rules/sub-rules/adv-comments-rule

      /etc/community/scoring/rules/sub-rules/adv-voice-rule-owner

**Opmerkingen:**

* Beide `rules`en `sub-rules` knooppunten zijn van het type `cq:Page`
* `subRules` is een kenmerk van het type String[] over de regels `jcr:content` node
* `sub-rules` kunnen worden gedeeld door verschillende scoreregels
* `rules` moet zich bevinden op een opslagplaats met leesmachtigingen voor iedereen
   * regelnamen moeten uniek zijn, ongeacht de locatie

### Ingesloten Badgingregels {#included-badging-rules}

In de release zijn twee geavanceerde regels voor badging opgenomen die overeenkomen met de [geavanceerde forums en regels voor het maken van scores voor opmerkingen](#included-scoring-rules-and-sub-rules).

* /etc/community/badging/rules/adv-comments-badging
* /etc/community/badging/rules/adv-forums-badging

**Opmerkingen:**

* `rules` knooppunten zijn van het type `cq:Page`
* `rules`moet zich bevinden op een opslagplaats met leesmachtigingen voor iedereen
   * regelnamen moeten uniek zijn, ongeacht de locatie
