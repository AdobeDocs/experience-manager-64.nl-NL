---
title: Ondersteuning voor nieuwe lokalisatieschermen voor lokalisatie van adaptieve formulieren
seo-title: Ondersteuning voor nieuwe lokalisatieschermen voor lokalisatie van adaptieve formulieren
description: De Vormen AEM staat u toe om nieuwe scènes toe te voegen voor het lokaliseren van adaptieve vormen. De gesteunde scènes door gebrek zijn Engels, Frans, Duits, en Japanner.
seo-description: De Vormen AEM staat u toe om nieuwe scènes toe te voegen voor het lokaliseren van adaptieve vormen. De gesteunde scènes door gebrek zijn Engels, Frans, Duits, en Japanner.
uuid: d4cee51b-c555-4544-9ae9-4aa8d38b2b17
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: Configuration
discoiquuid: e78f539a-109c-444c-8e52-be2260c3509f
translation-type: tm+mt
source-git-commit: c5a78d6c2b8a55cad6266e86e9b990cafc038431

---


# Ondersteuning voor nieuwe lokalisatieschermen voor lokalisatie van adaptieve formulieren {#supporting-new-locales-for-adaptive-forms-localization}

## Informatie over woordenboeken {#about-locale-dictionaries}

De localisatie van adaptieve vormen baseert zich op twee types van scènewoordenboeken:

**Form-specific woordenboek** bevat strings die in adaptieve vormen worden gebruikt. Bijvoorbeeld, etiketten, gebiedsnamen, foutenmeldingen, hulpbeschrijvingen, etc. Het wordt beheerd als reeks XLIFF dossiers voor elke scène en u kunt tot het in https://`<host>`toegang hebben:`<port>`/libs/cq/i18n/translator.html.

**Globale woordenboeken** Er zijn twee globale woordenboeken, die als voorwerpen JSON worden beheerd, in AEM cliëntbibliotheek. Deze woordenboeken bevatten standaardfoutenmeldingen, maandnamen, muntsymbolen, datum en tijdpatronen, etc. U kunt deze woordenboeken in CRXDe Lite bij /libs/fd/xfaforms/clientlibs/I18N vinden. Deze plaatsen bevatten afzonderlijke omslagen voor elke scène. Omdat globale woordenboeken gewoonlijk niet vaak worden bijgewerkt, laat het houden van afzonderlijke dossiers JavaScript voor elke scène browsers toe om hen in het voorgeheugen onder te brengen en het gebruik van de netwerkbandbreedte te verminderen wanneer het toegang tot van verschillende adaptieve vormen op de zelfde server.

### Hoe lokalisatie van adaptieve vorm werkt {#how-localization-of-adaptive-form-works}

Wanneer een adaptieve vorm wordt teruggegeven, identificeert het de gevraagde scène door de volgende parameters in de gespecificeerde orde te bekijken:

* Aanvraagparameter `afAcceptLang`

   Om de browser scène van gebruikers met voeten te treden, kunt u de `afAcceptLang` verzoekparameter overgaan om de scène te dwingen. Bijvoorbeeld, zal volgende URL dwingen om de vorm in Japanse scène terug te geven:

   `https://[*server*]:[*port*]/<*contextPath*>/<*formFolder*>/<*formName*>.html?wcmmode=disabled&afAcceptLang=ja`

* De browser scène die voor de gebruiker wordt geplaatst, die in het verzoek gebruikend de `Accept-Language` kopbal wordt gespecificeerd.

* Taal die van de gebruiker plaatst in AEM wordt gespecificeerd.

Zodra de scène wordt geïdentificeerd, plukken de adaptieve vormen het vorm-specifieke woordenboek. Als het formulier-specifieke woordenboek voor de gevraagde scène niet wordt gevonden, gebruikt het het Engelse (en) woordenboek wordt gebruikt.

Als een cliëntbibliotheek voor de gevraagde scène niet bestaat, controleert het een cliëntbibliotheek voor de taalcode aanwezig in de scène. Bijvoorbeeld, als de gevraagde scène `en_ZA` (Zuid-Afrikaans Engels) is en de cliëntbibliotheek voor `en_ZA` `en` niet bestaat, zal de adaptieve vorm de cliëntbibliotheek voor (Engelse) taal gebruiken, als het bestaat. Nochtans, als geen van hen bestaat, gebruikt de adaptieve vorm het woordenboek voor `en` scène.

## Voeg localisatiesteun voor niet-gesteunde scènes toe {#add-localization-support-for-non-supported-locales}

AEM Forms ondersteunt momenteel de lokalisatie van adaptieve formulieren in het Engels (en), Spaans (ES), Frans (fr), Italiaans (it), Duits (de), Japans (ja), Portugees-Braziliaans (pt-BR, Chinees (zh-CN), Chinees-Taiwan (zh-TW), en Koreaanse (ko-KR) scènes.

Om steun voor een nieuwe scène bij adaptieve vormenruntime toe te voegen:

1. [Voeg een lokalisatie toe aan de GuideLocalizationService](/help/forms/using/supporting-new-language-localization.md#p-add-a-locale-to-the-guide-localization-service-br-p)

1. [Voeg XFA cliëntbibliotheek voor een scène toe](/help/forms/using/supporting-new-language-localization.md#p-add-xfa-client-library-for-a-locale-br-p)

1. [Adaptieve formulierclientbibliotheek toevoegen voor een lokaal](/help/forms/using/supporting-new-language-localization.md#p-add-adaptive-form-client-library-for-a-locale-br-p)
1. [Voeg locale steun voor het woordenboek toe](/help/forms/using/supporting-new-language-localization.md#p-add-locale-support-for-the-dictionary-br-p)
1. [De server opnieuw opstarten](/help/forms/using/supporting-new-language-localization.md#p-restart-the-server-p)

### Voeg een lokalisatie toe aan de lokalisatieservice voor de Guide {#add-a-locale-to-the-guide-localization-service-br}

1. Ga naar `https://[server]:[port]/system/console/configMgr`.
1. Klik hierop om de component **Guide Localization Service** te bewerken.
1. Voeg de scène toe u aan de lijst van gesteunde scènes wilt toevoegen.

![GuideLocalizationService](assets/configservice.png)

### Voeg XFA cliëntbibliotheek voor een scène toe {#add-xfa-client-library-for-a-locale-br}

Creeer een knoop van type `cq:ClientLibraryFolder` onder `etc/<folderHierarchy>`, met categorie `xfaforms.I18N.<locale>`, en voeg de volgende dossiers aan de cliëntbibliotheek toe:

* **I18N.js** die `xfalib.locale.Strings` voor de `<locale>` zoals die in `/etc/clientlibs/fd/xfaforms/I18N/ja/I18N`wordt bepaald bepaalt.

* **js.txt** met de volgende gegevens:

```
/libs/fd/xfaforms/clientlibs/I18N/Namespace.js
I18N.js
/etc/clientlibs/fd/xfaforms/I18N/LogMessages.js
```

### Adaptieve formulierclientbibliotheek toevoegen voor een lokaal {#add-adaptive-form-client-library-for-a-locale-br}

Creeer een knoop van type `cq:ClientLibraryFolder` onder `etc/<folderHierarchy>`, met categorie zoals `guides.I18N.<locale>` en en gebiedsdelen zoals `xfaforms.3rdparty`, `xfaforms.I18N.<locale>` en `guide.common`. &quot;

Voeg de volgende dossiers aan de cliëntbibliotheek toe:

* **i18n.js** die `guidelib.i18n`, met patronen van &quot;kalenderSymbolen&quot;, `datePatterns`, `timePatterns`, `dateTimeSymbols`, `numberPatterns`, `numberSymbols`, `currencySymbols`, `typefaces` volgens de specificaties XFA definieert `<locale>` [](https://helpx.adobe.com/content/dam/Adobe/specs/xfa_spec_3_3.pdf)zoals die in de Vastgestelde Specificatie van de Rand worden beschreven. U kunt ook zien hoe het voor andere gesteunde scènes binnen wordt bepaald `/etc/clientlibs/fd/af/I18N/fr/javascript/i18n.js`.

* **LogMessages.js** die `guidelib.i18n.strings` en `guidelib.i18n.LogMessages` voor `<locale>` zoals bepaald in bepalen `/etc/clientlibs/fd/af/I18N/fr/javascript/LogMessages.js`.

* **js.txt** met de volgende gegevens:

```
i18n.js
LogMessages.js
```

### Voeg locale steun voor het woordenboek toe {#add-locale-support-for-the-dictionary-br}

Voer deze stap slechts uit als `<locale>` u toevoegt niet onder `en`, `de`, `es`, `fr`, `it`, `pt-br`, `zh-cn`, `zh-tw`, `ja``ko-kr`, .

1. Creeer een `nt:unstructured` knoop `languages` onder `etc`, als niet aanwezig reeds.

1. Voeg een multi-getaxeerd koordbezit aan de knoop toe, als niet reeds aanwezig. `languages`
1. Voeg de `<locale>` standaardscènewaarden `de`, `es`, `fr`, `it`, `pt-br`, `zh-cn`, `zh-tw`, `ja`, `ko-kr`, als niet reeds aanwezig toe.

1. Voeg `<locale>` aan de waarden van het `languages` bezit van toe `/etc/languages`.

Het `<locale>` verschijnt om `https://[server]:[port]/libs/cq/i18n/translator.html`.

### De server opnieuw opstarten {#restart-the-server}

Start de AEM-server opnieuw op zodat de toegevoegde scène van kracht wordt.

## De bibliotheken van de steekproef voor het toevoegen van steun voor Spaans {#sample-libraries-for-adding-support-for-spanish}

De cliëntbibliotheken van de steekproef voor het toevoegen van steun voor Spaans

[Bestand ophalen](assets/sample.zip)
