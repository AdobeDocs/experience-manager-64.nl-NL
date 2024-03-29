---
title: Adobe Analytics Framework aanpassen
seo-title: Customizing the Adobe Analytics Framework
description: Adobe Analytics Framework aanpassen
seo-description: null
uuid: 444a29c2-3b4e-4d21-adc0-5f317ece2b77
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: extending-aem
content-type: reference
discoiquuid: 11c0aac6-a7f6-4d6b-a080-b04643045a64
exl-id: 7e465a56-ca26-481e-9b3e-b438ef7fbff0
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1654'
ht-degree: 0%

---

# Adobe Analytics Framework aanpassen{#customizing-the-adobe-analytics-framework}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Het Adobe Analytics-framework bepaalt welke informatie wordt bijgehouden met Adobe Analytics. Als u het standaardframework wilt aanpassen, gebruikt u javascript om aangepaste tracking toe te voegen, Adobe Analytics-plug-ins te integreren en algemene instellingen te wijzigen in het framework dat wordt gebruikt voor bijhouden.

## Over de gegenereerde javascript voor Frameworks {#about-the-generated-javascript-for-frameworks}

Wanneer een pagina is gekoppeld aan een Adobe Analytics-framework en de pagina bevat [verwijzingen naar de module Analytics](/help/sites-administering/adobeanalytics.md)wordt er automatisch een bestand analytics.sitecatalyst.js voor de pagina gegenereerd.

Met het javascript op de pagina wordt een `s_gi`object (dat door de Adobe Analytics-bibliotheek s_code.js wordt gedefinieerd) en waarden worden toegewezen aan de eigenschappen ervan. De naam van de objectinstantie is `s`. De codevoorbeelden die in deze sectie worden weergegeven, verwijzen naar deze `s` variabele.

De volgende voorbeeldcode lijkt op de code in het bestand analytics.sitecatalyst.js:

```
var s_account = "my_sitecatalyst_account";
var s = s_gi(s_account);
s.fpCookieDomainPeriods = "3";
s.currencyCode= 'USD';
s.trackInlineStats= true;
s.linkTrackVars= 'None';
s.charSet= 'UTF-8';
s.linkLeaveQueryString= false;
s.linkExternalFilters= '';
s.linkTrackEvents= 'None';
s.trackExternalLinks= true;
s.linkDownloadFileTypes= 'exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls';
s.linkInternalFilters= 'javascript:,'+window.location.hostname;
s.trackDownloadLinks= true;
        
s.visitorNamespace = "mynamespace";
s.trackingServer = "xxxxxxx.net";
s.trackingServerSecure = "xxxxxxx.net";

/* Plugin Config */
/*
s.usePlugins=false;
function s_doPlugins(s) {
    //add your custom plugin code here
}
s.doPlugins=s_doPlugins;
*/
```

Wanneer u aangepaste javascript-code gebruikt om het framework aan te passen, wijzigt u de inhoud van dit bestand.

## Adobe Analytics-eigenschappen configureren {#configuring-adobe-analytics-properties}

Er zijn een aantal vooraf gedefinieerde variabelen binnen Adobe Analytics die kunnen worden geconfigureerd op een framework**. **De **charset**, **cookieLifetime**, **currencyCode** en **trackInlineStats** in de **Algemene analytische instellingen** lijst standaard.

![aa-22](assets/aa-22.png)

U kunt namen en waarden van variabelen aan de lijst toevoegen. Deze vooraf gedefinieerde variabelen en alle variabelen die u toevoegt, worden gebruikt om de eigenschappen van de `s` in het bestand analytics.sitecatalyst.js. In het volgende voorbeeld wordt getoond hoe de toegevoegde `prop10` eigenschap of value `CONSTANT` wordt vertegenwoordigd in de javascript-code:

```
var s_account = "my_sitecatalyst_account";
var s = s_gi(s_account);
s.fpCookieDomainPeriods = "3";
s.currencyCode= 'USD';
s.trackInlineStats= true;
s.linkTrackVars= 'None';
s.charSet= 'UTF-8';
s.linkLeaveQueryString= false;
s.linkExternalFilters= '';
s.linkTrackEvents= 'None';
s.trackExternalLinks= true;
s.linkDownloadFileTypes= 'exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls';
s.prop10= 'CONSTANT';
s.linkInternalFilters= 'javascript:,'+window.location.hostname;
s.trackDownloadLinks= true;
        
s.visitorNamespace = "mynamespace";
s.trackingServer = "xxxxxxx.net";
s.trackingServerSecure = "xxxxxxx.net";
```

Gebruik de volgende procedure om variabelen aan de lijst toe te voegen:

1. Vouw op uw Adobe Analytics-frameworkpagina de **Algemene analytische instellingen** gebied.
1. Klik onder de lijst met variabelen op Item toevoegen om een nieuwe variabele aan de lijst toe te voegen.
1. Voer in de cel links een naam in voor de variabele, bijvoorbeeld `prop10`.

1. Voer in de rechterkolom bijvoorbeeld een waarde voor de variabele in `CONSTANT`.

1. Als u een variabele wilt verwijderen, klikt u op de knop (-) naast de variabele.

>[!NOTE]
>
>Wanneer u variabelen en waarden invoert, moet u ervoor zorgen dat deze op de juiste wijze zijn opgemaakt en gespeld, of **vraag zal niet worden verzonden** met de correcte waarde/het variabele paar. Verkeerd gespelde variabelen en de waarden kunnen vraag zelfs verhinderen voor te komen.
>
>Neem contact op met uw Adobe Analytics-vertegenwoordiger om te controleren of deze variabelen correct zijn ingesteld.

>[!CAUTION]
>
>Sommige variabelen in deze lijst zijn **verplicht** om ervoor te zorgen dat Adobe Analytics-aanroepen correct werken, (bijvoorbeeld **currencyCode**, **charSet**)
>
>Dus zelfs als ze uit het framework zelf worden verwijderd, zullen ze nog steeds met een standaardwaarde worden gekoppeld wanneer de Adobe Analytics-oproep wordt gedaan.

### Aangepaste javascript toevoegen aan een Adobe Analytics Framework {#adding-custom-javascript-to-an-adobe-analytics-framework}

De javascript-vakken &#39;free-from&#39; in het dialoogvenster **Algemene analytische instellingen** kunt u aangepaste code toevoegen aan een Adobe Analytics-framework.

![aa-21](assets/aa-21.png)

De code die u toevoegt, wordt toegevoegd aan het bestand analytics.sitecatalyst.js. Daarom kunt u tot `s` variabele, die een instantie is van de `s_gi` javascript-object dat is gedefinieerd in `s_code.js`. Het toevoegen van de volgende code is bijvoorbeeld gelijk aan het toevoegen van een variabele met de naam `prop10` van waarde `CONSTANT`, wat het voorbeeld is in de vorige sectie:

`s.prop10= 'CONSTANT';`

De code in de [analytics.sitecatalyst.js](/help/sites-developing/extending-analytics-components.md) bestand (dat de inhoud van de Adobe Analytics bevat) `s-code.js` bestand) bevat de volgende code:

`if (s.usePlugins) s.doPlugins(s)`

De volgende procedure laat zien hoe u het vak javascript kunt gebruiken om het bijhouden van Adobe Analytics aan te passen. Als uw javascript Adobe Analytics-plug-ins moet gebruiken, [integreren,](/help/sites-administering/adobeanalytics.md) in AEM.

1. Voeg de volgende javascript-code toe aan het vak, zodat `s.doPlugins` wordt uitgevoerd:

   ```
   s.usePlugins=true;
   function s_doPlugins(s) {
       //add your custom code here
   }
   s.doPlugins=s_doPlugins;
   ```

   >[!CAUTION]
   >
   >Deze code is nodig als u variabelen in een vraag van Adobe Analytics wilt verzenden die op één of andere manier zijn aangepast die niet door de basis belemmering &amp; dalingsinterface OF door gealigneerd javascript in de Mening van Adobe Analytics kan worden gedaan.
   >
   >Als de douanevariabelen buiten de functie s_doPlugins zijn zullen zij als *undefined *in de vraag van Adobe Analytics worden verzonden

1. Voeg uw javascript-code toe in het dialoogvenster **s_doPlugins** functie.

In het volgende voorbeeld worden de gegevens die op een pagina in hiërarchische volgorde zijn vastgelegd, samengevoegd met een algemeen scheidingsteken &quot;|&quot;.

Een Adobe Analytics-framework heeft de volgende configuraties:

* De `prop2` Adobe Analytics-variabele wordt toegewezen aan de `pagedata.sitesection` site-eigenschap.

* De `prop3` Adobe Analytics-variabele wordt toegewezen aan de `pagedata.subsection` site-eigenschap.

* De volgende code wordt toegevoegd aan het vak free-from javascript:

   ```
   s.usePlugins=true; 
    function s_doPlugins(s) { 
    s.prop1 = s.prop2+'|'+s.prop3; 
    } 
    s.doPlugins=s_doPlugins;
   ```

* Wanneer de webpagina die gebruikmaakt van het framework wordt bezocht (of in de bewerkingsmodus wordt de pagina opnieuw geladen of voorvertoond), worden de aanroepen naar Adobe Analytics uitgevoerd.

De volgende waarden worden bijvoorbeeld gegenereerd in Adobe Analytics:

![aa-20](assets/aa-20.png)

### Global Custom Code toevoegen voor alle Adobe Analytics-frameworks {#adding-global-custom-code-for-all-adobe-analytics-frameworks}

Aangepaste javascript-code opgeven die in alle Adobe Analytics-frameworks is geïntegreerd. Wanneer het Adobe Analytics-framework van een pagina geen aangepaste inhoud bevat [javascript met vrije vorm](/help/sites-administering/adobeanalytics.md), wordt het javascript dat door het script /libs/cq/analytics/components/sitecatalyst/config.js.jsp wordt gegenereerd, toegevoegd aan het [analytics.sitecatalyst.js](/help/sites-administering/adobeanalytics.md) bestand. Het script heeft standaard geen effect omdat het geen opmerkingen bevat. De codesets `s.usePlugins` tot `false`:

```
/* Plugin Config */
/*
s.usePlugins=false;
function s_doPlugins(s) {
    //add your custom plugin code here
}
s.doPlugins=s_doPlugins;
*/
```

De code in het bestand analytics.sitecatalyst.js (die de inhoud van het bestand s_code.js van Adobe Analytics bevat) bevat de volgende code:

als (s.usePlugins) s.doPlugins

Uw javascript moet daarom worden ingesteld `s.usePlugins` tot `true` zodat de code in de `s_doPlugins` functie wordt uitgevoerd. Als u de code wilt aanpassen, bedekt u het bestand config.js.jsp met een bestand dat uw eigen javascript gebruikt. Als uw javascript Adobe Analytics-plug-ins moet gebruiken, [integreren,](/help/sites-administering/adobeanalytics.md) in AEM.

>[!NOTE]
>
>Bewerk het bestand /libs/cq/analytics/components/sitecatalyst/config.js.jsp niet. Bepaalde AEM upgrade- of onderhoudstaken kunnen het oorspronkelijke bestand opnieuw installeren, waardoor uw wijzigingen worden verwijderd.

1. Maak in CRXDE Lite de mapstructuur /apps/cq/analytics/components:

   1. Klik met de rechtermuisknop op de map /apps en klik op Maken > Map maken.
   1. Opgeven `cq` als de mapnaam en klik op OK.
   1. Maak op dezelfde manier de `analytics` en `components` mappen.

1. Klik met de rechtermuisknop op de knop `components` de map die u net hebt gemaakt en klik op Maken > Component maken. Geef de volgende eigenschapswaarden op:

   * Label: `sitecatalyst`
   * Titel: `sitecatalyst`
   * Supertype: `/libs/cq/analytics/components/sitecatalyst`
   * Groep: `hidden`

1. Klik herhaaldelijk op Volgende totdat de knop OK is ingeschakeld en klik vervolgens op OK.

   De component sitecatalyst bevat het automatisch gemaakte bestand sitecatalyst.jsp.

1. Klik met de rechtermuisknop op het bestand sitecatalyst.jsp en klik op Verwijderen.

1. Klik met de rechtermuisknop op de component sitecatalyst en klik op Maken > Bestand maken. Geef de naam op `config.js.jsp` en klik vervolgens op OK.

   Het bestand config.js.jsp wordt automatisch geopend voor bewerking.

1. Voeg de volgende tekst toe aan het bestand en klik op Alles opslaan:

   ```java
   <%@page session="true"%>
   /* Plugin Config */
   s.usePlugins=true;
   function s_doPlugins(s) {
       //add your custom plugin code here
   }
   s.doPlugins=s_doPlugins;
   ```

   De javascript-code die door het script /apps/cq/analytics/components/sitecatalyst/config.js.jsp wordt gegenereerd, wordt nu ingevoegd in het bestand analytics.sitecatalyst.js voor alle pagina&#39;s die een Adobe Analytics-framework gebruiken.

1. Voeg de javascript-code toe die u wilt uitvoeren in het dialoogvenster `s_doPlugins` en klikt u op Alles opslaan.

>[!CAUTION]
>
>Als er tekst aanwezig is in de javascript-vrije vorm van het raamwerk van een pagina (zelfs alleen witruimte), wordt config.js.jsp genegeerd.

### Adobe Analytics-plug-ins in AEM gebruiken {#using-adobe-analytics-plugins-in-aem}

Vraag de javascript-code voor Adobe Analytics-plug-ins aan en integreer deze in AEM in uw Adobe Analytics-framework. De code toevoegen aan een clientbibliotheekmap van de categorie `sitecatalyst.plugins` zodat deze beschikbaar zijn voor uw aangepaste javascript-code.

Als u bijvoorbeeld de `getQueryParams` insteekmodule kunt u de insteekmodule vanuit de `s_doPlugins` functie van uw aangepaste javascript. De volgende voorbeeldcode verzendt de queryreeks in **&quot;pid&quot;** van de URL van de verwijzende als **eVar1**, wanneer een Adobe Analytics-aanroep wordt geactiveerd.

```
s.usePlugins=true;
function s_doPlugins(s) {
   // take the query string from the referrer
   s.eVar1=s.getQueryParam('pid','',document.referrer); 
}
s.doPlugins=s_doPlugins;
```

AEM installeert de volgende Adobe Analytics-plug-ins, zodat deze standaard beschikbaar zijn:

* getQueryParam()
* getPreviousValue()
* split()

De clientbibliotheekmap /libs/cq/analytics/clientlibs/sitecatalyst/plugins bevat deze plug-ins in de categorie sitecatalyst.plugins.

>[!NOTE]
>
>Maak een nieuwe clientbibliotheekmap voor uw plug-ins. Voeg geen plug-ins toe aan de `/libs/cq/analytics/clientlibs/sitecatalyst/plugins` map. Deze praktijk zorgt ervoor dat uw bijdrage aan de `sitecatalyst.plugins` de categorie wordt niet overschreven tijdens AEM herinstallatietaken of upgradetaken.

Gebruik de volgende procedure om de map met de clientbibliotheek voor uw plug-ins te maken. U hoeft deze procedure slechts eenmaal uit te voeren. Gebruik de volgende procedure om een plug-in toe te voegen aan de map met clientbibliotheken.

1. Open CRXDE Lite in een webbrowser. ([http://localhost:4502/crx/de](http://localhost:4502/crx/de))

1. Klik met de rechtermuisknop op de map /apps/my-app/clientlibs en klik op Maken > Node maken. Voer de volgende eigenschapswaarden in en klik op OK:

   * Naam: Een naam voor de clientbibliotheekmap, zoals mijn plug-ins

   * Type: cq:ClientLibraryFolder

1. Selecteer de clientbibliotheekmap die u net hebt gemaakt en gebruik de onderste eigenschappenbalk rechts om de volgende eigenschap toe te voegen:

   * Naam: categorieën
   * Type: String
   * Waarde: sitecatalyst.plugins
   * Meerdere: geselecteerd

   Klik op OK in het venster Bewerken om de waarde van de eigenschap te bevestigen.

1. Klik met de rechtermuisknop op de clientbibliotheekmap die u net hebt gemaakt en klik op Maken > Bestand maken. Typ js.txt als bestandsnaam en klik op OK.

1. Klik op Alles opslaan.

Gebruik de volgende procedure om de insteekmodulecode op te halen, de code op te slaan in de AEM opslagplaats en de code toe te voegen aan de map met de clientbibliotheek.

1. Aanmelden bij [sc.omniture.com](https://sc.omniture.com) met uw Adobe Analytics-account.
1. Ga op de bestemmingspagina naar Help > Help Home.
1. Klik in de inhoudsopgave aan de linkerkant op Plug-ins voor implementatie.
1. Klik op de koppeling naar de plug-in die u wilt toevoegen. Wanneer de pagina wordt geopend, zoekt u de javascript-broncode voor de plug-in en selecteert u de code en kopieert u deze.

1. Klik met de rechtermuisknop op de clientbibliotheekmap en klik op Maken > Bestand maken. Typ voor de bestandsnaam de naam van de plug-in die u wilt integreren, gevolgd door .js, en klik op OK. Als u bijvoorbeeld de insteekmodule getQueryParam integreert, geeft u het bestand de naam getQueryParam.js.

   Wanneer u het bestand maakt, wordt het geopend voor bewerking.

1. Plak de javascript-insteekmodule in het bestand, klik op Alles opslaan en sluit het bestand.

1. Open het bestand js.txt vanuit de clientbibliotheekmap.

1. Voeg in een nieuwe regel de naam toe van het bestand dat de insteekmodule bevat, bijvoorbeeld getQueryParam.js. Klik vervolgens op Alles opslaan en sluit het bestand.

>[!NOTE]
>
>Als u plug-ins gebruikt, moet u ook eventuele ondersteunende plug-ins integreren. Als dit niet het geval is, herkent de insteekmodule javascript niet de aanroepen die het naar de functies in de ondersteunende plug-in voert. De getPreviousValue()-insteekmodule vereist bijvoorbeeld dat de split()-insteekmodule correct werkt.
>  
>De naam van de ondersteuningsinsteekmodule moet worden toegevoegd aan **js.txt** ook.
