---
title: ContextHub toevoegen aan Pagina's en Toegang tot Sporen
seo-title: ContextHub toevoegen aan Pagina's en Toegang tot Sporen
description: Voeg ContextHub aan uw pagina's toe om de eigenschappen ContextHub toe te laten en aan de bibliotheken te verbinden JavaScript van ContextHub
seo-description: Voeg ContextHub aan uw pagina's toe om de eigenschappen ContextHub toe te laten en aan de bibliotheken te verbinden JavaScript van ContextHub
uuid: ade37960-21c4-4d64-a525-68f0d199f955
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: personalization
content-type: reference
discoiquuid: ac8f44df-39fb-44ea-ae17-ead0dbd1f6c0
translation-type: tm+mt
source-git-commit: 39b6af8ee815e8f6fa6e0b4a0a6dc80f29165243
workflow-type: tm+mt
source-wordcount: '1033'
ht-degree: 0%

---


# ContextHub toevoegen aan Pagina&#39;s en Toegang tot Sporen {#adding-contexthub-to-pages-and-accessing-stores}

Voeg ContextHub aan uw pagina&#39;s toe om de eigenschappen ContextHub toe te laten en aan de bibliotheken te verbinden JavaScript van ContextHub

De JavaScript-API van ContextHub biedt toegang tot de contextgegevens die door ContextHub worden beheerd. In deze pagina worden kort de belangrijkste functies van de API beschreven voor het benaderen en bewerken van contextgegevens. Volg de koppelingen naar de API-naslagdocumentatie voor gedetailleerde informatie en codevoorbeelden.

## ContextHub toevoegen aan een component van de Pagina {#adding-contexthub-to-a-page-component}

Om de eigenschappen ContextHub toe te laten en aan de bibliotheken te verbinden ContextHub Javascript, omvat de component contexthub in de `head` sectie van uw pagina. De JSP-code voor uw paginacomponent lijkt op het volgende voorbeeld:

```xml
<head>
   <sling:include path="contexthub" resourceType="granite/contexthub/components/contexthub" />
</head>
```

Merk op dat u ook moet vormen of de toolbar ContextHub op de wijze van de Voorproef verschijnt. Zie [Het tonen van en het Hiding van ContextHub UI](/help/sites-administering/contexthub-config.md#showing-and-hiding-the-contexthub-ui).

## Informatie over ContextHub-winkels {#about-contexthub-stores}

De opslag van ContextHub van het gebruik om contextgegevens voort te zetten. ContextHub verstrekt de volgende types van opslag die de basis van alle opslagtypes vormen:

* [PersistedStore](/help/sites-developing/contexthub-api.md#contexthub-store-persistedstore)
* [SessionStore](/help/sites-developing/contexthub-api.md#contexthub-store-sessionstore)
* [JSONPStore](/help/sites-developing/contexthub-api.md#contexthub-store-persistedjsonpstore)
* [PersistedJSONPStore](/help/sites-developing/contexthub-api.md#contexthub-store-persistedstore)

Alle opslagtypes zijn uitbreidingen van de [`ContextHub.Store.Core`](/help/sites-developing/contexthub-api.md#contexthub-store-core) klasse. Zie [Aangepaste winkels maken](/help/sites-developing/ch-extend.md#creating-custom-store-candidates) voor informatie over het maken van een nieuw winkeltype. Voor informatie over de types van steekproefopslag, zie [Sample ContextHub Store Candidates](/help/sites-developing/ch-samplestores.md).

### Persistentiemodi {#persistence-modes}

De opslag van de Hub van de context gebruikt één van de volgende persistentiemodi:

* **Lokaal:** gebruikt HTML5 localStorage om gegevens te behouden. Lokale opslag blijft in de browser tijdens sessies behouden.
* **Sessie:** gebruikt HTML5 sessionStorage om gegevens te behouden. De opslag van de zitting wordt voortgeduurd voor de browser zitting en is beschikbaar aan alle browser vensters.
* **Cookie:** gebruikt de native ondersteuning van de browser voor cookies voor gegevensopslag. De gegevens van het koekje worden verzonden naar en van de server in HTTP- verzoeken.
* **Window.name:** Gebruikt het window.name bezit om gegevens voort te zetten.
* **Geheugen:** gebruikt een JavaScript-object om gegevens te behouden.

Door gebrek, gebruikt de Hub van de Context de Lokale persistentiemodus. Als de browser geen ondersteuning biedt voor lokale HTML5-opslag of deze toestaat, wordt de sessiepersistentie gebruikt. Als de browser HTML5 sessionStorage niet ondersteunt of toestaat, wordt de persistentie Window.name gebruikt.

### Gegevens opslaan {#store-data}

Intern vormen opslaggegevens een boomstructuur, waardoor waarden kunnen worden toegevoegd als primaire typen of complexe objecten. Wanneer u complexe objecten toevoegt aan opslagruimten, vormen de objecteigenschappen vertakkingen in de gegevensstructuur. Het volgende complexe object wordt bijvoorbeeld toegevoegd aan een lege opslaglocatie met de naam location:

```xml
Object {
   number: 321,
   data: {
      city: "Basel",
      country: "Switzerland",
      details: {
         population: 173330,
         elevation: 260
      }
   }
}
```

De boomstructuur van de opslaggegevens kan als volgt worden geconceptualiseerd:

```xml
/
|- number
|- data
      |- city
      |- country
      |- details
            |- population
            |- elevation
```

De boomstructuur bepaalt gegevenspunten in de opslag als sleutel/waardeparen. In het bovenstaande voorbeeld komt de sleutel `/number` overeen met de waarde `321` en de sleutel `/data/country` komt overeen met de waarde `Switzerland`.

### Objecten {#manipulating-objects} bewerken

ContextHub verstrekt de [`ContextHub.Utils.JSON.tree`](/help/sites-developing/contexthub-api.md#contexthub-utils-json-tree) klasse voor het manipuleren van voorwerpen Javascript. Gebruik de functies van deze klasse voor het manipuleren van voorwerpen Javascript alvorens u hen aan een opslag toevoegt, of nadat u hen van een opslag verkrijgt.

Daarnaast biedt de klasse [`ContextHub.Utils.JSON`](/help/sites-developing/contexthub-api.md#contexthub-utils-json) functies voor het serieel ordenen van objecten met tekenreeksen en het ongedaan maken van tekenreeksen met objecten. Gebruik deze klasse voor het verwerken van JSON-gegevens om browsers te ondersteunen die de functies `JSON.parse` en `JSON.stringify` niet native bevatten.

## Interactie met de Opslag {#interacting-with-contexthub-stores} van ContextHub

Gebruik het Javascript-object [`ContextHub`](/help/sites-developing/contexthub-api.md#ui-event-constants) om een winkel als een JavaScript-object op te halen. Nadat u het opslagobject hebt verkregen, kunt u de gegevens in het object bewerken. Gebruik [`getAllStores`](/help/sites-developing/contexthub-api.md#getallstores) of [`getStore`](/help/sites-developing/contexthub-api.md#getstore-name) functie om de opslag te verkrijgen.

### Toegang tot opslaggegevens {#accessing-store-data}

De Javascript-klasse [`ContexHub.Store.Core`](/help/sites-developing/contexthub-api.md#contexthub-store-core) definieert verschillende functies voor interactie met opslaggegevens. Met de volgende functies worden meerdere gegevensitems in objecten opgeslagen en opgehaald:

* [addAllItems](/help/sites-developing/contexthub-api.md#addallitems-tree-options)
* [getTree](/help/sites-developing/contexthub-api.md#gettree-includeinternals)

Afzonderlijke gegevensitems worden opgeslagen als een set sleutel-/waardeparen. Als u waarden wilt opslaan en ophalen, geeft u de bijbehorende sleutel op:

* [getItem](/help/sites-developing/contexthub-api.md#getitem-key)
* [setItem](/help/sites-developing/contexthub-api.md#setitem-key-value-options)

Merk op dat de kandidaten van de douaneopslag extra functies kunnen bepalen die toegang verlenen om gegevens op te slaan.

>[!NOTE]
>
>ContextHub is niet door gebrek zich bewust van momenteel het programma geopend op publiceer servers en dergelijke gebruikers worden beschouwd door ContextHub als &quot;Anoniem.&quot;
>
>U kunt ContextHub van het programma geopende gebruikers bewust maken door de profielopslag te laden zoals die in [Wij.Retail verwijzingsplaats](/help/sites-developing/we-retail.md) wordt uitgevoerd. Verwijs naar [relevante code op GitHub hier](https://github.com/Adobe-Marketing-Cloud/aem-sample-we-retail/blob/master/ui.apps/src/main/content/jcr_root/apps/weretail/components/structure/header/clientlib/js/utilities.js).

### ContextHub-gebeurtenis {#contexthub-eventing}

ContextHub omvat een gebeurteniskader dat u toelaat om automatisch te reageren om gebeurtenissen op te slaan. Elk opslagvoorwerp bevat een [`ContextHub.Utils.Eventing`](/help/sites-developing/contexthub-api.md#contexthub-utils-eventing) voorwerp dat als [`eventing`](/help/sites-developing/contexthub-api.md#eventing) bezit van de opslag beschikbaar is. Gebruik de functie [`on`](/help/sites-developing/contexthub-api.md#on-name-handler-selector-triggerforpastevents) of [`once`](/help/sites-developing/contexthub-api.md#once-name-handler-selector-triggerforpastevents) om een functie JavaScript aan een archiefgebeurtenis te binden.

## Het gebruiken van de Hub van de Context om Koekjes {#using-context-hub-to-manipulate-cookies} te manipuleren

De JavaScript-API van de Context Hub biedt ondersteuning voor verschillende browsers voor de verwerking van browsercookies. De naamruimte [`ContextHub.Utils.Cookie`](/help/sites-developing/contexthub-api.md#contexthub-utils-cookie) definieert verschillende functies voor het maken, bewerken en verwijderen van cookies.

## Het bepalen van Opgeloste Segmenten ContextHub {#determining-resolved-contexthub-segments}

De ContextHub segmentmotor laat u toe om te bepalen welke van de geregistreerde segmenten in de huidige context worden opgelost. Gebruik de functie getResolvedSegments van de klasse [`ContextHub.SegmentEngine.SegmentManager`](/help/sites-developing/contexthub-api.md#contexthub-segmentengine-segmentmanager) om opgeloste segmenten terug te winnen. Vervolgens gebruikt u de functie `getName` of `getPath` van de klasse [`ContextHub.SegmentEngine.Segment`](/help/sites-developing/contexthub-api.md#contexthub-segmentengine-segment) om te testen op een segment.

### Geïnstalleerde segmenten {#installed-segments}

De segmenten van ContextHub worden geïnstalleerd onder de `/conf/we-retail/settings/wcm/segments` knoop.

* vrouwelijk
* vrouwen-over-30
* vrouwen onder de 30
* mannetje
* man-over-30
* mannelijk-jonger-30
* order-value-75-to-100
* order-value-over-100
* meer dan 30
* zomer
* zomervrouwtje
* zomer-vrouwelijk-over-30
* zomer-vrouwelijk-jonger-30
* zomermannetje
* zomer-man-over-30
* zomer-mannetje-onder-30
* jonger dan 30 jaar
* winter
* wintervrouwtje
* winter-vrouw-over-30
* winter-vrouw-onder-30
* wintermannetje
* winter-man-over-30
* winter-mannetje-onder-20

De regels die worden gebruikt om deze segmenten op te lossen zijn als volgt samengevat:

* Vrouwen of mannen worden bepaald aan de hand van het `gender`-gegevensitem van de [profile](/help/sites-developing/ch-samplestores.md#granite-profile-sample-store-candidate)-winkel.

* De leeftijd wordt bepaald van het leeftijdsgegevensitem van het profielarchief.
* Het seizoen wordt bepaald aan de hand van het gegevensitem op de breedtegraad van de [geolocatie](/help/sites-developing/ch-samplestores.md#contexthub-geolocation-sample-store-candidate)-opslag en het maandgegevensitem van de surferinfo-opslag.

>[!WARNING]
>
>De geïnstalleerde segmenten worden verstrekt als verwijzingsconfiguraties om u te helpen uw eigen specifieke configuratie voor uw project bouwen en als zodanig niet direct zouden moeten worden gebruikt.

## Het registreren zuivert Berichten voor ContextHub {#logging-debug-messages-for-contexthub}

Vorm de dienst van ContextHub OSGi van Adobe Granite (PID = `com.adobe.granite.contexthub.impl.ContextHubImpl`) om gedetailleerde Debug berichten te registreren die wanneer het ontwikkelen nuttig zijn.

U kunt de service configureren met de [webconsole](/help/sites-deploying/configuring-osgi.md#osgi-configuration-with-the-web-console) of met een [JCR-knooppunt in de opslagruimte](/help/sites-deploying/configuring-osgi.md#osgi-configuration-in-the-repository):

* Webconsole: Om te registreren zuivert berichten, selecteer het Debug bezit.
* JCR-knooppunt: Als u Foutopsporingsberichten wilt registreren, stelt u de Booleaanse eigenschap `com.adobe.granite.contexthub.debug` in op `true`.

## Zie een Overzicht van het Kader ContextHub {#see-an-overview-of-the-contexthub-framework}

ContextHub verstrekt een [diagnostische pagina](/help/sites-developing/ch-diagnostics.md) waar u een overzicht van het kader ContextHub kunt zien.
