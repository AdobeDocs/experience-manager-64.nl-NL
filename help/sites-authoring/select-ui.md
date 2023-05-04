---
title: Gebruikersinterface selecteren
seo-title: Selecting your UI
description: Vorm welke interface u zult gebruiken om in AEM te werken
seo-description: Configure which interface you will use to work in AEM
uuid: af956219-178e-477b-a0cd-dd2341ed2ff0
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: introduction
content-type: reference
discoiquuid: 9cadec1b-f435-4fd8-b4bc-1a23a0cf11f3
exl-id: 415efbe0-95f5-4c9e-ac33-c4a384a8271e
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '943'
ht-degree: 0%

---

# Gebruikersinterface selecteren{#selecting-your-ui}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## De gebruikersinterface

In de ontwerpomgeving is het volgende mogelijk:

* [Authoring](/help/sites-authoring/author.md) (inclusief [pagina&#39;s ontwerpen](/help/sites-authoring/author-environment-tools.md), [elementen beheren](/help/assets/home.md), [gemeenschappen](/help/communities/author-communities.md))

* [Beheer](/help/sites-administering/home.md) taken die u nodig hebt bij het genereren en onderhouden van de inhoud van uw website

Hiervoor zijn twee grafische gebruikersinterfaces beschikbaar. Deze zijn toegankelijk via elke moderne browser.

1. Interface met aanraakbediening

   * Dit is de moderne, standaard AEM UI.
   * Het is overwegend grijs, met een schone, vlakke interface.
   * De vormgeving is op alle apparaten hetzelfde en is ontworpen voor zowel touch- als desktopapparaten. [uw bronnen weergeven en selecteren](/help/sites-authoring/basic-handling.md#viewing-and-selecting-resources) verschilt enigszins (tikken versus klikken).

      * Desktop:

   ![screen_shot_2018-03-23at115248](assets/screen_shot_2018-03-23at115248.png)

   * Tabletapparaten (of desktops met een breedte van minder dan 1024 pixels):

   ![screen_shot_2018-03-23at115505](assets/screen_shot_2018-03-23at115505.png)

1. Klassieke interface

   * Dit is de oudere gebruikersinterface en is al vele jaren in AEM beschikbaar.
   * Het is voornamelijk groen.
   * Het is ontworpen voor gebruik op desktopapparaten.
   * De volgende documentatie concentreert zich op moderne UI. Voor informatie over creatie in klassieke UI, zie [Ontwerpdocumentatie voor de klassieke gebruikersinterface](/help/sites-classic-ui-authoring/classicui.md).

   ![chlimage_1-232](assets/chlimage_1-232.png)

## Wisselende UIs

Hoewel de interface met aanraakbediening nu de standaardinterface is en [functiepariteit](../release-notes/touch-ui-features-status.md) is bijna bereikt met het beheer en het bewerken van sites, er kunnen momenten zijn waarop de gebruiker wil overschakelen op de [klassieke gebruikersinterface](/help/sites-classic-ui-authoring/classicui.md). Hiervoor zijn verschillende opties beschikbaar.

>[!NOTE]
>
>Voor details over de status van eigenschappariteit met klassieke UI, zie [Pariteit aanraakinterface](../release-notes/touch-ui-features-status.md) document.

Er zijn verschillende locaties waar u kunt definiëren welke interface moet worden gebruikt:

* [De standaardinterface voor uw instantie configureren](#configuring-the-default-ui-for-your-instance) - Hiermee wordt de standaardinterface ingesteld die bij de gebruikersaanmelding moet worden weergegeven, hoewel de gebruiker deze kan overschrijven en een andere interface kan selecteren voor zijn of haar account of huidige sessie.

* [Klassieke UI-authoring instellen voor uw account](/help/sites-authoring/select-ui.md#setting-classic-ui-authoring-for-your-account) - Hiermee wordt ingesteld dat de gebruikersinterface standaard wordt gebruikt bij het bewerken van pagina&#39;s, maar de gebruiker kan dit overschrijven en een andere gebruikersinterface selecteren voor zijn of haar account of huidige sessie.

* [Overschakelen naar klassieke gebruikersinterface voor de huidige sessie](#switching-to-classic-ui-for-the-current-session) - Deze schakelt over naar de klassieke UI voor de huidige sessie.

* Voor het geval van [pagina het ontwerpen van het systeem maakt bepaalde met betrekking tot UI met voeten treedt](#ui-overrides-for-the-editor).

>[!CAUTION]
>
>Diverse opties voor het schakelen naar klassieke UI zijn niet onmiddellijk beschikbaar uit-van-de-doos, zij moeten specifiek voor uw instantie worden gevormd.
>
>Zie [Toegang tot klassieke gebruikersinterface inschakelen](/help/sites-administering/enable-classic-ui.md) voor meer informatie .

>[!NOTE]
>
>Instanties die zijn bijgewerkt vanaf een vorige versie behouden de klassieke interface voor het ontwerpen van pagina&#39;s.
>
>Na de upgrade wordt het ontwerpen van pagina&#39;s niet automatisch overgeschakeld op de interface met aanraakbediening, maar u kunt dit configureren met de [OSGi-configuratie](/help/sites-deploying/configuring-osgi.md) van de **WCM Authoring UI Mode Service** ( `AuthoringUIMode` service). Zie [UI-overschrijvingen voor de Editor](#ui-overrides-for-the-editor).

## De standaardinterface voor uw instantie configureren {#configuring-the-default-ui-for-your-instance}

Een systeembeheerder kan UI vormen die bij opstarten en login door te gebruiken wordt gezien [Hoofdtoewijzing](/help/sites-deploying/osgi-configuration-settings.md).

Dit kan door gebruikersgebreken of zittingsmontages worden met voeten getreden.

## Klassieke UI-authoring instellen voor uw account {#setting-classic-ui-authoring-for-your-account}

Elke gebruiker heeft toegang tot zijn/haar [gebruikersvoorkeuren](/help/sites-authoring/user-properties.md) om te bepalen of hij/zij klassieke UI voor paginaontwerp (in plaats van het gebrek UI) wenst te gebruiken.

Dit kan door zittingsmontages worden met voeten getreden.

## Schakelen naar klassieke gebruikersinterface voor de huidige sessie {#switching-to-classic-ui-for-the-current-session}

Als gebruikers de interface met aanraakbediening gebruiken, kunnen ze terugkeren naar de klassieke interface (alleen bureaublad). Er zijn verscheidene methodes om op klassieke UI voor de huidige zitting over te schakelen:

* **Navigatiekoppelingen**

   >[!CAUTION]
   >
   >Deze optie voor het schakelen naar klassieke UI is niet onmiddellijk beschikbaar uit-van-de-doos, moet het specifiek voor uw instantie worden gevormd.
   >
   >
   >Zie [Toegang tot klassieke gebruikersinterface inschakelen](/help/sites-administering/enable-classic-ui.md) voor meer informatie .

   Als dit wordt toegelaten, wanneer u muis over een toepasselijke console, een pictogram (symbool van een monitor) verschijnt, zal het tikken van/het klikken dit de aangewezen plaats in klassieke UI openen.

   De koppelingen van **Sites** tot **sitebeheerder**:

   ![screen_shot_2018-03-23at111924](assets/screen_shot_2018-03-23at111924.png)

* **URL**

   De klassieke interface is toegankelijk via de URL voor het welkomstscherm op `welcome.html`. Bijvoorbeeld:

   `http://localhost:4502/welcome.html`

   >[!NOTE]
   >
   >De interface met aanraakbediening is toegankelijk via `sites.html`. Bijvoorbeeld:
   >
   >
   >`http://localhost:4502/sites.html`

### Schakelen naar klassieke gebruikersinterface bij het bewerken van een pagina {#switching-to-classic-ui-when-editing-a-page}

>[!CAUTION]
>
>Deze optie voor het schakelen naar klassieke UI is niet onmiddellijk beschikbaar uit-van-de-doos, moet het specifiek voor uw instantie worden gevormd.
>
>Zie [Toegang tot klassieke gebruikersinterface inschakelen](/help/sites-administering/enable-classic-ui.md) voor meer informatie .

Indien ingeschakeld, **De klassieke gebruikersinterface openen** is beschikbaar via **Pagina-informatie** dialoogvenster:

![chlimage_1-49](assets/chlimage_1-49.png)

### UI-overschrijvingen voor de Editor {#ui-overrides-for-the-editor}

De instellingen die door een gebruiker of systeembeheerder zijn gedefinieerd, kunnen door het systeem worden overschreven bij het ontwerpen van pagina&#39;s.

* Bij het ontwerpen van pagina&#39;s:

   * Het gebruik van de klassieke editor is geforceerd wanneer u de pagina opent met `cf#` in de URL. Bijvoorbeeld:

      `http://localhost:4502/cf#/content/geometrixx/en/products/triangle.html`

   * Het gebruik van de aanraakeditor is verplicht bij gebruik `/editor.html` in de URL of wanneer u een aanraakapparaat gebruikt. Bijvoorbeeld:

      `http://localhost:4502/editor.html/content/geometrixx/en/products/triangle.html`

* Elke forcering is tijdelijk en is alleen geldig voor de browsersessie

   * Een cookie-set wordt ingesteld afhankelijk van of touch-bediening ( `editor.html`) of klassiek ( `cf#`) wordt gebruikt.

* Wanneer u pagina&#39;s opent via `siteadmin`worden controles uitgevoerd op het bestaan van:

   * Het cookie
   * Een gebruikersvoorkeur
   * Als geen van beide bestaan, zal het aan de definities in gebrek blijven die in [OSGi-configuratie](/help/sites-deploying/configuring-osgi.md) van de **WCM Authoring UI Mode Service** ( `AuthoringUIMode` service).

>[!NOTE]
>
>Indien [een gebruiker heeft al een voorkeur voor het ontwerpen van pagina&#39;s gedefinieerd](#setting-classic-ui-authoring-for-your-account), dat niet zal worden met voeten getreden door het bezit te veranderen OSGi.

>[!CAUTION]
>
>Vanwege het gebruik van cookies, zoals hierboven beschreven, wordt het niet aanbevolen om:
>
>* Handmatig de URL bewerken - Een niet-standaard URL kan leiden tot een onbekende situatie en een gebrek aan functionaliteit.
>* Beide editors tegelijk openen, bijvoorbeeld in afzonderlijke vensters.
>

