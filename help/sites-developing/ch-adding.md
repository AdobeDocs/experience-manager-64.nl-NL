---
title: ContextHub toevoegen aan Pagina's en Toegang tot Sporen
seo-title: Adding ContextHub to Pages and Accessing Stores
description: Voeg ContextHub aan uw pagina's toe om de eigenschappen ContextHub toe te laten en aan de bibliotheken te verbinden JavaScript van ContextHub
seo-description: Add ContextHub to your pages to enable the ContextHub features and to link to the ContextHub Javascript libraries
uuid: ade37960-21c4-4d64-a525-68f0d199f955
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: personalization
content-type: reference
discoiquuid: ac8f44df-39fb-44ea-ae17-ead0dbd1f6c0
exl-id: 99efe308-bf8a-41ad-8203-b57fce20820c
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1044'
ht-degree: 0%

---

# ContextHub toevoegen aan Pagina&#39;s en Toegang tot Sporen {#adding-contexthub-to-pages-and-accessing-stores}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Voeg ContextHub aan uw pagina&#39;s toe om de eigenschappen ContextHub toe te laten en aan de bibliotheken te verbinden JavaScript van ContextHub

De JavaScript-API van ContextHub biedt toegang tot de contextgegevens die door ContextHub worden beheerd. In deze pagina worden kort de belangrijkste functies van de API beschreven voor het benaderen en bewerken van contextgegevens. Volg de koppelingen naar de API-naslagdocumentatie voor gedetailleerde informatie en codevoorbeelden.

## ContextHub toevoegen aan een component Page {#adding-contexthub-to-a-page-component}

Om de eigenschappen ContextHub toe te laten en aan de bibliotheken te verbinden ContextHub Javascript, omvat de component ContextHub in `head` van uw pagina. De JSP-code voor uw paginacomponent lijkt op het volgende voorbeeld:

```xml
<head>
   <sling:include path="contexthub" resourceType="granite/contexthub/components/contexthub" />
</head>
```

Merk op dat u ook moet vormen of de toolbar ContextHub op de wijze van de Voorproef verschijnt. Zie [Het tonen van en het Verbergen van ContextHub UI](/help/sites-administering/contexthub-config.md#showing-and-hiding-the-contexthub-ui).

## Informatie over ContextHub-winkels {#about-contexthub-stores}

De opslag van ContextHub van het gebruik om contextgegevens voort te zetten. ContextHub verstrekt de volgende types van opslag die de basis van alle opslagtypes vormen:

* [PersistedStore](/help/sites-developing/contexthub-api.md#contexthub-store-persistedstore)
* [SessionStore](/help/sites-developing/contexthub-api.md#contexthub-store-sessionstore)
* [JSONPStore](/help/sites-developing/contexthub-api.md#contexthub-store-persistedjsonpstore)
* [PersistedJSONPStore](/help/sites-developing/contexthub-api.md#contexthub-store-persistedstore)

Alle winkeltypen zijn extensies van de [`ContextHub.Store.Core`](/help/sites-developing/contexthub-api.md#contexthub-store-core) klasse. Voor informatie over het maken van een nieuw winkeltype raadpleegt u [Aangepaste winkels maken](/help/sites-developing/ch-extend.md#creating-custom-store-candidates). Voor informatie over de types van steekproefopslag, zie [Voorbeeld van ContextHub Store-kandidaten](/help/sites-developing/ch-samplestores.md).

### Persistentiemodi {#persistence-modes}

De opslag van de Hub van de context gebruikt één van de volgende persistentiemodi:

* **Lokaal:** Gebruikt HTML5 localStorage om gegevens te behouden. Lokale opslag blijft in de browser tijdens sessies behouden.
* **Sessie:** Gebruikt HTML5 sessionStorage om gegevens te handhaven. De opslag van de zitting wordt voortgeduurd voor de browser zitting en is beschikbaar aan alle browser vensters.
* **Koekje:** Gebruikt de native ondersteuning van de browser voor cookies voor gegevensopslag. De gegevens van het koekje worden verzonden naar en van de server in HTTP- verzoeken.
* **Window.name:** Gebruikt de eigenschap window.name om gegevens te behouden.
* **Geheugen:** Gebruikt een Javascript-object om gegevens te behouden.

Door gebrek, gebruikt de Hub van de Context de Lokale persistentiemodus. Als de browser geen ondersteuning biedt voor HTML5 localStorage of als dit niet is toegestaan, wordt de sessiepersistentie gebruikt. Als de browser HTML5 sessionStorage niet ondersteunt of toestaat, wordt Window.name persistence gebruikt.

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

De boomstructuur bepaalt gegevenspunten in de opslag als sleutel/waardeparen. In het bovenstaande voorbeeld wordt de toets `/number` komt overeen met de waarde `321`en de sleutel `/data/country` komt overeen met de waarde `Switzerland`.

### Objecten bewerken {#manipulating-objects}

ContextHub biedt de [`ContextHub.Utils.JSON.tree`](/help/sites-developing/contexthub-api.md#contexthub-utils-json-tree) klasse voor het bewerken van Javascript-objecten. Gebruik de functies van deze klasse voor het manipuleren van voorwerpen Javascript alvorens u hen aan een opslag toevoegt, of nadat u hen van een opslag verkrijgt.

Daarnaast worden de [`ContextHub.Utils.JSON`](/help/sites-developing/contexthub-api.md#contexthub-utils-json) klasse biedt functies voor het serieel ordenen van objecten op tekenreeksen en het ongedaan maken van tekenreeksen op objecten. Gebruik deze klasse voor het verwerken van JSON-gegevens ter ondersteuning van browsers die zelf geen `JSON.parse` en `JSON.stringify` functies.

## Interactief werken met ContextHub-winkels {#interacting-with-contexthub-stores}

Gebruik de [`ContextHub`](/help/sites-developing/contexthub-api.md#ui-event-constants) Javascript-object om een winkel als een JavaScript-object te verkrijgen. Nadat u het opslagobject hebt verkregen, kunt u de gegevens in het object bewerken. Gebruik de [`getAllStores`](/help/sites-developing/contexthub-api.md#getallstores) of de [`getStore`](/help/sites-developing/contexthub-api.md#getstore-name) om de winkel te verkrijgen.

### Winkelgegevens openen {#accessing-store-data}

De [`ContexHub.Store.Core`](/help/sites-developing/contexthub-api.md#contexthub-store-core) De Javascript-klasse definieert verschillende functies voor interactie met opslaggegevens. Met de volgende functies worden meerdere gegevensitems in objecten opgeslagen en opgehaald:

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
>U kunt ContextHub van het programma geopende gebruikers bewust maken door de profielopslag te laden zoals die in wordt uitgevoerd [We.Retail-referentiesite](/help/sites-developing/we-retail.md). Zie de [relevante code op GitHub hier](https://github.com/Adobe-Marketing-Cloud/aem-sample-we-retail/blob/master/ui.apps/src/main/content/jcr_root/apps/weretail/components/structure/header/clientlib/js/utilities.js).

### ContextHub Event {#contexthub-eventing}

ContextHub omvat een gebeurteniskader dat u toelaat om automatisch te reageren om gebeurtenissen op te slaan. Elk winkelobject bevat een [`ContextHub.Utils.Eventing`](/help/sites-developing/contexthub-api.md#contexthub-utils-eventing) object dat beschikbaar is als de opslagruimte [`eventing`](/help/sites-developing/contexthub-api.md#eventing) eigenschap. Gebruik de [`on`](/help/sites-developing/contexthub-api.md#on-name-handler-selector-triggerforpastevents) of [`once`](/help/sites-developing/contexthub-api.md#once-name-handler-selector-triggerforpastevents) functie om een functie JavaScript aan een archiefgebeurtenis te binden.

## Contexthub gebruiken om cookies te manipuleren {#using-context-hub-to-manipulate-cookies}

De JavaScript-API van de Context Hub biedt ondersteuning voor verschillende browsers voor de verwerking van browsercookies. De [`ContextHub.Utils.Cookie`](/help/sites-developing/contexthub-api.md#contexthub-utils-cookie) namespace bepaalt verscheidene functies voor het creëren van, het manipuleren van, en het schrappen van koekjes.

## Opgeloste ContextHub-segmenten bepalen {#determining-resolved-contexthub-segments}

De ContextHub segmentmotor laat u toe om te bepalen welke van de geregistreerde segmenten in de huidige context worden opgelost. Gebruik de functie getResolvedSegments van het [`ContextHub.SegmentEngine.SegmentManager`](/help/sites-developing/contexthub-api.md#contexthub-segmentengine-segmentmanager) om opgeloste segmenten op te halen. Gebruik vervolgens de `getName` of `getPath` de functie van de [`ContextHub.SegmentEngine.Segment`](/help/sites-developing/contexthub-api.md#contexthub-segmentengine-segment) klasse om te testen op een segment.

### Geïnstalleerde segmenten {#installed-segments}

ContextHub-segmenten worden onder de `/conf/we-retail/settings/wcm/segments` knooppunt.

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
* Zomer-vrouw
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

* Vrouwelijk of mannelijk wordt bepaald aan de hand van de `gender` gegevensitem van de [profiel](/help/sites-developing/ch-samplestores.md#granite-profile-sample-store-candidate) opslaan.

* De leeftijd wordt bepaald van het leeftijdsgegevensitem van het profielarchief.
* Het seizoen wordt bepaald op basis van het item met breedtegegevens van het dialoogvenster [geolocatie](/help/sites-developing/ch-samplestores.md#contexthub-geolocation-sample-store-candidate) opslag, en het maandgegevenspunt van de surferinfo opslag.

>[!WARNING]
>
>De geïnstalleerde segmenten worden verstrekt als verwijzingsconfiguraties om u te helpen uw eigen specifieke configuratie voor uw project bouwen en als zodanig niet direct zouden moeten worden gebruikt.

## Het registreren zuivert Berichten voor ContextHub {#logging-debug-messages-for-contexthub}

Vorm de Adobe Granite ContextHub OSGi dienst (PID = `com.adobe.granite.contexthub.impl.ContextHubImpl`) om gedetailleerde Debug berichten te registreren die wanneer het ontwikkelen nuttig zijn.

Om de dienst te vormen kunt u of gebruiken [Webconsole](/help/sites-deploying/configuring-osgi.md#osgi-configuration-with-the-web-console) of een [JCR-knooppunt in de gegevensopslagruimte](/help/sites-deploying/configuring-osgi.md#osgi-configuration-in-the-repository):

* Webconsole: Om te registreren zuivert berichten, selecteer het Debug bezit.
* JCR-knooppunt: Om te registreren zuivert berichten, plaats boolean `com.adobe.granite.contexthub.debug` eigenschap aan `true`.

## Zie een Overzicht van het Kader ContextHub {#see-an-overview-of-the-contexthub-framework}

ContextHub biedt een [diagnosepagina](/help/sites-developing/ch-diagnostics.md) waar u een overzicht van het kader kunt zien ContextHub.
