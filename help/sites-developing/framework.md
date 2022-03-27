---
title: Kader voor tags AEM
seo-title: AEM Tagging Framework
description: Inhoud labelen en gebruikmaken van de infrastructuur voor tags AEM
seo-description: Tag content and leverage the AEM Tagging infrastructure
uuid: 55ba5977-217b-4b0f-a794-ddb9216ee62b
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: platform
content-type: reference
discoiquuid: 4b680d17-383b-4173-a444-0b7bdb24e6c8
feature: Tagging
exl-id: bae592db-dc36-409f-b841-0582c464c3f6
source-git-commit: 381e760d1634dec6c6cdb933fd4da6b4652e6ff7
workflow-type: tm+mt
source-wordcount: '1764'
ht-degree: 0%

---

# Kader voor tags AEM{#aem-tagging-framework}

Inhoud labelen en de taginfrastructuur AEM gebruiken:

* De tag moet bestaan als een knooppunt van het type [`cq:Tag`](#tags-cq-tag-node-type) onder de [taxonomie root node.](#taxonomy-root-node)
* Het knooppunt voor gecodeerde inhoud `NodeType` moet de [`cq:Taggable`](#taggable-content-cq-taggable-mixin) mixin.
* De [TagID](#tagid) wordt toegevoegd aan de inhoud van het knooppunt [`cq:tags`](#tagged-content-cq-tags-property) eigenschap en wordt omgezet in een knooppunt van het type [`cq:Tag`.](#tags-cq-tag-node-type)

## Tags: cq:Type tagknooppunt  {#tags-cq-tag-node-type}

De declaratie van een tag wordt vastgelegd in de repository in een knooppunt van het type `cq:Tag.`

Een tag kan een eenvoudig woord zijn (bijvoorbeeld `fruit`) of een hiërarchische taxonomie vertegenwoordigen (bijvoorbeeld `fruit/apple`, dat wil zeggen zowel vruchten in het algemeen als de meer specifieke appel).

Tags worden geïdentificeerd door een unieke TagID.

Een tag bevat optionele metagegevens, zoals een titel, gelokaliseerde titels en een beschrijving. De titel moet worden weergegeven in gebruikersinterfaces in plaats van de `TagID`, indien aanwezig.

Met het coderingsframework kunt u auteurs en sitebezoekers ook beperken tot het gebruik van specifieke, vooraf gedefinieerde tags.

### Tagkenmerken {#tag-characteristics}

* Het knooppunttype is `cq:Tag`.
* De knooppuntnaam is een component van [`TagID`.](#tagid)
* De [`TagID`](#tagid) bevat altijd een [naamruimte.](#tag-namespace)
* Optioneel `jcr:title` eigenschap (de titel die moet worden weergegeven in de UI)
* Optioneel `jcr:description` eigenschap
* Als onderliggende knooppunten worden opgenomen, wordt dit een [containertag.](#container-tags)
* Het wordt opgeslagen in de repository onder een basispad dat het [taxonomie root node.](#taxonomy-root-node)

### TagID {#tagid}

A `TagID` identificeert een weg die aan een markeringsknoop in de bewaarplaats oplost.

De `TagID` is een steno die begint met de naamruimte, of het kan een absolute waarde zijn die begint met de [taxonomie root node](#taxonomy-root-node).

Als inhoud is gelabeld en nog niet bestaat, wordt het [`cq:tags`](#tagged-content-cq-tags-property) eigenschap wordt toegevoegd aan het inhoudsknooppunt en de `TagID` wordt toegevoegd aan de arraywaarde van de tekenreeks van de eigenschap.

De `TagID` bestaat uit een [namespace](#tag-namespace) gevolgd door de lokale `TagID`. [Containerlabels](#container-tags) beschikken over subtags die een hiërarchische volgorde in de taxonomie aangeven. Subtags kunnen worden gebruikt om naar labels te verwijzen, net als bij elke lokale tag `TagID`. Inhoud bijvoorbeeld labelen met `fruit` is toegestaan, zelfs als het een containertag met subtags betreft, zoals `fruit/apple` en `fruit/banana`.

### Taxonomy Root Node {#taxonomy-root-node}

Het basisknooppunt van de taxonomie is het basispad voor alle tags in de gegevensopslagruimte. Het taxonomiwortelknooppunt mag geen knooppunt van het type zijn `cq:Tag`.

In AEM is het basispad `/content/cq:tags` en de hoofdnode is van het type `cq:Folder`.

### Tagnaamruimte {#tag-namespace}

Naamruimten staan groepsgegevens toe. Het meest gangbare geval bij gebruik is een naamruimte per site (bijvoorbeeld public, internal en portal) of per grotere toepassing (bijvoorbeeld Sites, Assets, Forms), maar naamruimten kunnen voor verschillende andere behoeften worden gebruikt. Naamruimten worden in de gebruikersinterface gebruikt om alleen de subset van tags (d.w.z. tags van een bepaalde naamruimte) weer te geven die van toepassing is op de huidige inhoud.

De naamruimte van de tag is het eerste niveau in de taxonomy-substructuur. Dit is het knooppunt direct onder de [taxonomie root node](#taxonomy-root-node). Een naamruimte is een knooppunt van het type `cq:Tag` waarvan de ouder geen `cq:Tag` knooppunttype.

Alle tags hebben een naamruimte. Als er geen naamruimte is opgegeven, wordt de tag toegewezen aan de standaardnaamruimte, die `TagID` `default` (titel is `Standard Tags`) dat `/content/cq:tags/default`.

### Containerlabels {#container-tags}

Een containertag is een knooppunt van het type `cq:Tag` met een willekeurig aantal onderliggende knooppunten en een willekeurig type onderliggende knooppunten, waardoor het tagmodel kan worden verbeterd met aangepaste metagegevens.

Bovendien fungeren containercodes (of supercodes) in een taxonomie als de subsom van alle subcodes. Inhoud die bijvoorbeeld is gelabeld met `fruit/apple` wordt beschouwd als getagd met `fruit` ook. Dit betekent dat het zoeken naar inhoud enkel geëtiketteerd met `fruit` zou ook de inhoud vinden waaraan `fruit/apple`.

### TagID&#39;s oplossen {#resolving-tagids}

Als de tag-id een dubbele punt bevat `:`wordt de naamruimte door de dubbele punt gescheiden van de tag of subtaxonomie, die vervolgens worden gescheiden met normale slashes `/`. Als de tag-id geen dubbele punt heeft, wordt de standaardnaamruimte geïmpliceerd.

De standaardlocatie en de enige locatie voor tags is lager dan `/content/cq:tags`.

Label dat verwijst naar niet-bestaande paden of paden die niet verwijzen naar een `cq:Tag` knooppunt wordt als ongeldig beschouwd en wordt genegeerd.

In de volgende tabel ziet u een voorbeeld `TagIDs`, hun elementen en hoe `TagID` wordt omgezet in een absoluut pad in de opslagplaats.

| `TagID` | Naamruimte | Lokale id | Containertag(s) | Label blad | Absoluut pad naar opslagplaats |
|---|---|---|---|---|---|
| `dam:fruit/apple/braeburn` | `dam` | `fruit/apple/braeburn` | `fruit`, `apple` | `braeburn` | `/content/cq:tags/dam/fruit/apple/braeburn` |
| `color/red` | `default` | `color/red` | `color` | `red` | `/content/cq:tags/default/color/red` |
| `sky` | `default` | `sky` | Geen | `sky` | `/content/cq:tags/default/sky` |
| `dam:` | `dam` | Geen | Geen | Geen | `/content/cq:tags/dam` |
| `/content/cq:tags/category/car` | `category` | `car` | `car` | `car` | `/content/cq:tags/category/car` |

### Localisatie van tagtitel {#localization-of-tag-title}

Wanneer de tag de optionele titeltekenreeks bevat (`jcr:title`) het is mogelijk de titel voor weergave te lokaliseren door de eigenschap toe te voegen `jcr:title.<locale>`.

Zie voor meer informatie:

* [Tags in verschillende talen,](/help/sites-developing/building.md#tags-in-different-languages) , waarin het gebruik van de API&#39;s wordt beschreven.
* [Tags beheren in verschillende talen,](/help/sites-administering/tags.md#managing-tags-in-different-languages) , waarin het gebruik van de Tagingconsole wordt beschreven.

### Toegangsbeheer {#access-control}

Tags bestaan als knooppunten in de opslagplaats onder [taxonomie root node.](#taxonomy-root-node) Het toestaan of ontkennen van auteurs en plaatsbezoekers van de capaciteit om markeringen in een bepaalde namespace tot stand te brengen kan worden bereikt door aangewezen ACLs in de bewaarplaats te plaatsen.

Door het weigeren van leesmachtigingen voor bepaalde tags of naamruimten wordt ook de mogelijkheid bepaald om codes toe te passen op specifieke inhoud.

Een typische configuratie omvat:

* De `tag-administrators` groep/rol schrijven toegang tot alle namespaces (toevoegen/wijzigen onder `/content/cq:tags`).
   * Deze groep wordt geleverd met AEM out-of-the-box.
* Gebruikers/auteurs toegang verlenen tot alle naamruimten die voor hen (meestal alle) leesbaar moeten zijn.
* Gebruikers/auteurs toegang toestaan tot naamruimten waar tags vrij kunnen worden gedefinieerd door gebruikers/auteurs (`add_node` krachtens `/content/cq:tags/some_namespace`)

## Tagable Content: cq:Tagable Mixin {#taggable-content-cq-taggable-mixin}

De registratie van het knooppunt ([CND](https://jackrabbit.apache.org/node-type-notation.html)) moet de `cq:Taggable` mengen of `cq:OwnerTaggable` mixin.

De `cq:OwnerTaggable` mixin, dat overerft van `cq:Taggable`, is bedoeld om aan te geven dat de inhoud door de eigenaar/auteur kan worden geclassificeerd. In AEM is het alleen een kenmerk van de `cq:PageContent` knooppunt. De `cq:OwnerTaggable` Het coderingsframework vereist geen mixin.

>[!NOTE]
>
>Het wordt aanbevolen alleen labels in te schakelen op het knooppunt op het hoogste niveau van een samengevoegd inhoudsitem (of op het bijbehorende item `jcr:content` knooppunt). Voorbeelden zijn:
>
>* Pagina&#39;s ( `cq:Page`) waarbij de `jcr:content`node is type `cq:PageContent` die de `cq:Taggable` mixin.
>* Activa ( `cq:Asset`) waarbij de `jcr:content/metadata` node heeft altijd de `cq:Taggable` mixin.


### Node Type Notation (CND) {#node-type-notation-cnd}

Node Type definities bestaan in de bewaarplaats als Cnd- dossiers. De CND-notatie wordt gedefinieerd als onderdeel van de JCR-documentatie [hier](https://jackrabbit.apache.org/node-type-notation.html).

De belangrijkste definities voor de in AEM opgenomen knooppunttypen zijn:

```text
[cq:Tag] > mix:title, nt:base
    orderable
    - * (undefined) multiple
    - * (undefined)
    + * (nt:base) = cq:Tag version

[cq:Taggable]
    mixin
    - cq:tags (string) multiple

[cq:OwnerTaggable] > cq:Taggable
    mixin
```

## Gelabelde inhoud: cq:eigenschap tags {#tagged-content-cq-tags-property}

De `cq:tags` eigenschap is een tekenreeks-array die wordt gebruikt voor het opslaan van een of meer `TagID`s wanneer zij op inhoud door auteurs of plaatsbezoekers worden toegepast. De eigenschap heeft alleen betekenis wanneer deze wordt toegevoegd aan een knooppunt dat is gedefinieerd met het [`cq:Taggable`](#taggable-content-cq-taggable-mixin) mixin.

>[!NOTE]
>
>Als u AEM tagfuncties wilt gebruiken, mogen door aangepaste toepassingen geen andere tageigenschappen worden gedefinieerd dan `cq:tags`.

## Labels verplaatsen en samenvoegen {#moving-and-merging-tags}

Hieronder volgt een beschrijving van de effecten in de repository wanneer u tags verplaatst of samenvoegt met behulp van de [Tagingconsole](/help/sites-administering/tags.md):

* Wanneer een tag A wordt verplaatst of samengevoegd met tag B onder `/content/cq:tags`:

   * Label A wordt niet verwijderd en krijgt een `cq:movedTo` eigenschap.
   * Label B wordt gemaakt (in het geval van een verplaatsing) en krijgt een `cq:backlinks` eigenschap.

* `cq:movedTo` verwijst naar label B.

   * Deze eigenschap betekent dat tag A is verplaatst of samengevoegd met tag B.
   * Als tag B wordt verplaatst, wordt deze eigenschap dienovereenkomstig bijgewerkt. Tag A is dus verborgen en wordt alleen in de opslagplaats bewaard om tag-id&#39;s op te lossen in inhoudsknooppunten die verwijzen naar tag A.
   * De opschoonfunctie voor ongewenste details verwijdert tags zoals tag A, als er geen inhoudsknooppunten meer naar wijzen.
   * Een speciale waarde voor de `cq:movedTo` eigenschap is `nirvana`: wordt toegepast wanneer de tag wordt verwijderd, maar niet kan worden verwijderd uit de repository omdat er subtags zijn met een `cq:movedTo` dat moet worden bewaard.

      >[!NOTE]
      >
      >De `cq:movedTo` De eigenschap wordt alleen aan de verplaatste of samengevoegde tag toegevoegd als aan een van deze voorwaarden wordt voldaan:
      >
      >1. De tag wordt gebruikt in inhoud (wat betekent dat de tag een referentie heeft).
      >1. De tag bevat onderliggende elementen die al zijn verplaatst.


* `cq:backlinks` houdt de verwijzingen in de andere richting, d.w.z. het houdt een lijst bij van alle markeringen die zijn verplaatst naar of samengevoegd met markering B.

   * Dit is meestal vereist om te behouden `cq:movedTo`eigenschappen zijn up-to-date wanneer tag B wordt verplaatst/samengevoegd/verwijderd of wanneer tag B wordt geactiveerd; in dat geval moeten ook alle tags met de achtergrond worden geactiveerd.

>[!NOTE]
>
>De `cq:backlinks` De eigenschap wordt alleen aan de verplaatste of samengevoegde tag toegevoegd als aan een van deze voorwaarden wordt voldaan:
>
>1. De tag wordt gebruikt in inhoud (wat betekent dat de tag een referentie heeft).
>1. De tag bevat onderliggende elementen die al zijn verplaatst.


* Een `cq:tags` De eigenschap van een inhoudsknooppunt omvat het volgende oplossen:

   1. Als er geen overeenkomst onder `/content/cq:tags`, er wordt geen tag geretourneerd.
   1. Als de tag een `cq:movedTo` eigenschap ingesteld, wordt de tag-id waarnaar wordt verwezen gevolgd.

      * Deze stap wordt herhaald zolang de volgende tag een `cq:movedTo` eigenschap.
   1. Als de volgende tag geen `cq:movedTo` eigenschap, wordt de tag gelezen.


* Als u de wijziging wilt publiceren wanneer een tag is verplaatst of samengevoegd, gaat u naar `cq:Tag` node en al zijn backlinks moeten worden gerepliceerd.
   * Dit wordt automatisch gedaan wanneer de markering in de console van het markeringsbeleid wordt geactiveerd.

* Later wordt de pagina bijgewerkt met `cq:tags` de eigenschap wijzigt de &#39;oude&#39; referenties automatisch.
   * Dit wordt geactiveerd omdat het omzetten van een verplaatste tag via de API de doeltag retourneert, waardoor de doeltag-id wordt opgegeven.

## Migratie van tags {#tags-migration}

In Adobe Experience Manager 6.4 en hoger worden tags opgeslagen onder `/content/cq:tags`. In scenario&#39;s waarin Adobe Experience Manager vanaf de vorige versie is geüpgraded, zijn de tags echter nog steeds aanwezig onder de oude locatie `/etc/tags`. In geüpgrade systemen moeten codes worden gemigreerd naar `/content/cq:tags`.

>[!NOTE]
>
>In Pagina-eigenschappen van de pagina Tags wordt aangeraden de tag-id te gebruiken (bijvoorbeeld `geometrixx-outdoors:activity/biking`) in plaats van de harde code het basispad van de tag (bijvoorbeeld `/etc/tags/geometrixx-outdoors/activity/biking`).
>
>Als u labels wilt weergeven, `com.day.cq.tagging.servlets.TagListServlet` kan worden gebruikt.

>[!NOTE]
>
>Het wordt aangeraden de API voor tagbeheer als bron te gebruiken.

### Als Bijgewerkte AEM Instance ondersteuning biedt voor TagManager API*

1. Aan het begin van de component detecteert de API TagManager of het een geüpgrade AEM-instantie is. In een geüpgraded systeem worden codes opgeslagen onder `/etc/tags`.

1. De API van TagManager wordt dan uitgevoerd in achterwaartse verenigbaarheidswijze, wat betekent API gebruikt `/etc/tags` als het basispad. Zo niet, dan wordt een nieuwe locatie gebruikt `/content/cq:tags`.

1. Werk de taglocatie bij.

1. Nadat u tags naar de nieuwe locatie hebt gemigreerd, voert u het volgende script uit.

```java
import org.apache.sling.api.resource.*
import javax.jcr.*

ResourceResolverFactory resourceResolverFactory = osgi.getService(ResourceResolverFactory.class);
ResourceResolver resolver = resourceResolverFactory.getAdministrativeResourceResolver(null);
Session session = resolver.adaptTo(Session.class);

def queryManager = session.workspace.queryManager;
def statement = "/jcr:root/content/cq:tags//element(*, cq:Tag)[jcr:contains(@cq:movedTo,\'/etc/tags\') or jcr:contains(@cq:backlinks,\'/etc/tags\')]";
def query = queryManager.createQuery(statement, "xpath");

println "query = ${query.statement}\n";

def tags = query.execute().getNodes();


tags.each { node ->
        def tagPath = node.path;
        println "tag = ${tagPath}";

        if(node.hasProperty("cq:movedTo") && node.getProperty("cq:movedTo").getValue().toString().startsWith("/etc/tags")){

                def movedTo = node.getProperty("cq:movedTo").getValue().toString();

                println "cq:movedTo = ${movedTo} \n";

                movedTo = movedTo.replace("/etc/tags","/content/cq:tags");
                node.setProperty("cq:movedTo",movedTo);
        } else if(node.hasProperty("cq:backlinks")){

               String[] backLinks = node.getProperty("cq:backlinks").getValues();
               int count = 0;

               backLinks.each { value ->
                       if(value.startsWith("/etc/tags")){
                               println "cq:backlinks = ${value}\n";
                               backLinks[count] = value.replace("/etc/tags","/content/cq:tags");
    }
                       count++;
               }

               node.setProperty("cq:backlinks",backLinks);
  }
}
session.save();

println "---------------------------------Success-------------------------------------"
```

Het script haalt alle tags op die `/etc/tags` in de waarde van `cq:movedTo/cq:backLinks` eigenschap. Het herhaalt dan door de opgehaalde resultaatreeks en lost op `cq:movedTo` en `cq:backlinks` eigenschapswaarden naar `/content/cq:tags` paden (wanneer `/etc/tags` wordt gedetecteerd in de waarde).

### Als Bijgewerkte AEM Instantie op Klassieke UI** loopt

>[!NOTE]
>
>Klassieke UI is niet nul onderbreking volgzaam en steunt niet de nieuwe weg van de markeringsbasis. Als u een klassieke interface wilt gebruiken die groter is dan `/etc/tags` moet worden gecreëerd, gevolgd door `cq-tagging` opnieuw opstarten.

Als de bijgewerkte AEM-instanties worden ondersteund door de API TagManager en worden uitgevoerd in de klassieke gebruikersinterface:

1. Eenmaal verwijzingen naar het oude basispad voor tags `/etc/tags` worden vervangen door tagId of nieuwe taglocatie te gebruiken `/content/cq:tags`kunt u tags migreren naar de nieuwe locatie `/content/cq:tags` in CRX DE gevolgd door het opnieuw opstarten van de component.

1. Nadat u tags naar de nieuwe locatie hebt gemigreerd, voert u het bovenstaande script uit.
