---
title: De landinstelling van de gebruikersinterface van de AEM Forms-werkruimte wijzigen
seo-title: Changing the locale of AEM Forms workspace user interface
description: Hoe te om de werkruimte van AEM Forms te wijzigen om tekst, doen ineenstorten categorieën, rijen, en processen, en de datumkiezer op de interface te lokaliseren.
seo-description: How to modify the AEM Forms workspace to localize text, collapsed categories, queues, and processes, and the date picker on the interface.
uuid: f8e7d399-98d9-4655-b51f-0346a5713f06
contentOwner: robhagat
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: e4ca8188-fb9a-44bf-8437-a98abaa7521a
exl-id: 9968f399-454b-4cb2-b6af-2c16428ca7b4
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '593'
ht-degree: 0%

---

# De landinstelling van de gebruikersinterface van de AEM Forms-werkruimte wijzigen {#changing-the-locale-of-aem-forms-workspace-user-interface}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

De werkruimte van AEM Forms biedt vanuit de verpakking ondersteuning voor Engelse, Franse, Duitse en Japanse talen. Het biedt ook de mogelijkheid om de gebruikersinterface van de AEM Forms-werkruimte te lokaliseren naar een andere taal.

De gebruikersinterface van de AEM Forms-werkruimte lokaliseren naar de taal van uw keuze:

* Tekst van de AEM Forms-werkruimte lokaliseren.
* U kunt samengevouwen categorieën, wachtrijen en processen lokaliseren.
* Datumkiezer lokaliseren

Voordat u de bovenstaande stappen uitvoert, moet u de stappen volgen die worden weergegeven in [Algemene stappen voor aanpassing van de AEM Forms-werkruimte](/help/forms/using/generic-steps-html-workspace-customization.md).

>[!NOTE]
>
>Als u de taal van het aanmeldingsscherm van de AEM Forms-werkruimte wilt wijzigen, raadpleegt u [Een nieuw aanmeldingsscherm maken](/help/forms/using/creating-new-login-screen.md).

## Tekst lokaliseren {#localizing-text}

Voer de volgende stappen uit om ondersteuning voor een taal toe te voegen *Nieuw* en de landinstellingscode van de browser *nw*.

1. Meld u aan bij CRXDE Lite.

   De standaard-URL van CRXDE Lite is `https://[server]:[port]/lc/crx/de/index.jsp`.

1. Naar de locatie navigeren `apps/ws/locales` en maak een nieuwe map `nw.`
1. Het bestand kopiëren `translation.json`vanaf de locatie `/apps/ws/locales/en-US` naar locatie `/apps/ws/locales/nw`.
1. Navigeren naar `/apps/ws/locales/nw` en open `translation.json` voor bewerken. Wijzig de landinstelling in het bestand translatie.json.

   De volgende voorbeelden bevatten het bestand translatie.json voor Engelse en Franse landinstellingen van de AEM Forms-werkruimte.

   ![transleren_json_in_en](assets/translation_json_in_en.png) ![transleren_json_in_fr](assets/translation_json_in_fr.png)

## Samengevouwen categorieën, wachtrijen en processen lokaliseren {#localizing-collapsed-categories-queues-and-processes}

In de AEM Forms-werkruimte worden afbeeldingen gebruikt om koppen van categorieën, wachtrijen en processen weer te geven. U hebt ontwikkelingspakket nodig om deze koppen te lokaliseren. Voor gedetailleerde informatie over het maken van een ontwikkelingspakket gaat u naar [AEM Forms-werkruimtecode samenstellen.](introduction-customizing-html-workspace.md#building-html-workspace-code)

In de volgende stappen wordt aangenomen dat de nieuwe gelokaliseerde afbeeldingsbestanden *Categorieën_nw.png*, *Wachtrij_nw.png*, en *Processes_nw.png*. De aanbevolen breedte van de afbeeldingen is 19 px.

>[!NOTE]
>
>U kunt als volgt de landinstellingscode van de browser voor de taal vinden. Open `https://[server]:[port]/lc/libs/ws/Locale.html`.

![samenvouwen_deelvensters_afbeelding](assets/collapsing_panels_image.png)

Voer de volgende stappen uit om de afbeeldingen te lokaliseren:

1. Plaats de afbeeldingsbestanden met een WebDAV-client in het dialoogvenster */apps/ws/images* map.
1. Navigeren naar */apps/ws/css*. Openen *newStyle.css* voor het bewerken en toevoegen van de volgende vermeldingen:

   ```
   #categoryListBar .content.nw {
        background: #3e3e3e url(../images/Categories_nw.png) no-repeat 10px 10px;
    }
   
   #filterListBar .content.nw {
       background: #3e3e3e url(../images/Queues_nw.png) no-repeat 10px 10px;
   }
   
   #processNameListBar .content.nw {
       background: #3e3e3e url(../images/Processes_nw.png) no-repeat 10px 10px;
   }
   ```

1. Alle semantische wijzigingen uitvoeren die worden vermeld in het dialoogvenster [Aanpassing werkruimte](/help/forms/using/introduction-customizing-html-workspace.md) artikel.
1. Ga naar de *js/runtime/utility* en open het bestand* usersessie.js* voor bewerking.
1. Zoek de code in het oorspronkelijke codeblok en voeg voorwaarde toe *lang !== &#39;nw&#39;* op de instructie if:

   ```
   // Orignal code
   setLocale = function () {
           var lang = $.trim(i18n.lng());
           if (lang === null || lang === '' || (lang !== 'fr-FR' && lang !== 'de-DE' && lang !== 'ja-JP')) {
               window.lcWorkspace.locale = 'en-US';
           } else {
               window.lcWorkspace.locale = lang;
           }
       }
   ```

   ```
   //new code
    setLocale = function () {
           var lang = $.trim(i18n.lng());
           if (lang === null || lang === '' || (lang !== 'fr-FR' && lang !== 'de-DE' && lang !== 'ja-JP' && lang !== 'nw')) {
               window.lcWorkspace.locale = 'en-US';
           } else {
               window.lcWorkspace.locale = lang;
           }
       }
   ```

## Datumkiezer lokaliseren {#localizing-date-picker}

U hebt ontwikkelingspakket nodig om de *datepicker *API te lokaliseren. Voor gedetailleerde informatie over het maken van een ontwikkelingspakket gaat u naar [AEM Forms-werkruimtecode samenstellen](introduction-customizing-html-workspace.md#building-html-workspace-code).

1. Download en extraheer de [jQuery-UI-pakket](https://jqueryui.com/download/all/), navigeer naar *&lt;extracted jquery=&quot;&quot; ui=&quot;&quot; package=&quot;&quot;>*\jquery-ui-1.10.2.zip\jquery-ui-1.10.2\ui\i18n.
1. Kopieer het bestand jquery.ui.datepicker-nw.js voor de landinstellingscode nu naar apps/ws/js/libs/jqueryui en breng specifieke wijzigingen voor de landinstelling aan in het bestand.
1. Navigeren naar `apps/ws/js` en opent u de `jquery.ui.datepicker-nw.js` bestand voor bewerking.
1. Maak in het bestand main.js een alias voor `jquery.ui.datepicker-nw.js.` De code waarmee een alias voor de `jquery.ui.datepicker-nw.js` bestand is:

   ```
   jqueryuidatepickernw : pathprefix + 'libs/jqueryui/jquery.ui.datepicker-nw'
   ```

1. Alias gebruiken `jqueryuidatepickernw` de `jquery.ui.datepicker-nw.js` in alle bestanden die datepicker gebruiken. De datepicker wordt gebruikt in de volgende bestanden:

   * `js/runtime/views/outofoffice.js`
   * `js/runtime/views/searchtemplatedetails.js`

   De voorbeeldcode hieronder laat zien hoe u de vermelding jquery.ui.datepicker-nw.js toevoegt:

   ```
   //Original Code
   define([
       'jquery',
       'underscore',
       'backbone',
       'jqueryui',
       'jqueryuidatepickerja',
       'jqueryuidatepickerde',
       'jqueryuidatepickerfr',
       'slimscroll',
       'usersearchview',
       'logmanagerutil',
       'loggerutil'
   ], function ($, _, Backbone, jQueryUI, jQueryUIDatePickerJA, jQueryUIDatePickerDE, jQueryUIDatePickerFR, slimScroll, UserSearch, LogManager, Logger) {
   ```

   ```
   // Code with Date Picker alias for new language
   define([
       'jquery',
       'underscore',
       'backbone',
       'jqueryui',
       'jqueryuidatepickerja',
       'jqueryuidatepickerde',
       'jqueryuidatepickerfr',
       'jqueryuidatepickernw', // Date Picker alias
       'slimscroll',
       'usersearchview',
       'logmanagerutil',
       'loggerutil'
   ], function ($, _, Backbone, jQueryUI, jQueryUIDatePickerJA, jQueryUIDatePickerDE, jQueryUIDatePickerFR, jQueryUIDatePickerNW, slimScroll, UserSearch, LogManager, Logger) {
   ```

1. Wijzig in alle bestanden die de datepicker-API gebruiken de standaard datepicker-API-instellingen. De datepicker-API wordt gebruikt in de volgende bestanden:

   * apps\ws\js\runtime\views\searchtemplatedetails.js
   * apps\ws\js\runtime\views\outofoffice.js

   Wijzig de volgende code om de nieuwe landinstelling toe te voegen:

   ```
   if (locale === 'ja-JP') {
      $.datepicker.setDefaults($.datepicker.regional.ja);
   } else if (locale === 'de-DE') {
      $.datepicker.setDefaults($.datepicker.regional.de);
   } else if (locale === 'fr-FR') {
      $.datepicker.setDefaults($.datepicker.regional.fr);
   } else {
      $.datepicker.setDefaults($.datepicker.regional['']);
   }
   ```

tot

```
if (locale === 'ja-JP') {
    $.datepicker.setDefaults($.datepicker.regional.ja);
} else if (locale === 'de-DE') {
    $.datepicker.setDefaults($.datepicker.regional.de);
} else if (locale === 'fr-FR') {
    $.datepicker.setDefaults($.datepicker.regional.fr);
} else if (locale === 'nw') {
    $.datepicker.setDefaults($.datepicker.regional.nw);
} else {
    $.datepicker.setDefaults($.datepicker.regional['']);
}
```
