---
title: Snelle gids voor het ontwerpen van pagina's
seo-title: Quick Guide to Authoring Pages
description: Een snelle gids op hoog niveau voor de belangrijkste acties van het ontwerpen van pagina-inhoud
seo-description: A quick, high-level guide to the key actions of authoring page content
uuid: 35442d98-caf9-4cdb-8e68-4fc611e66290
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: page-authoring
content-type: reference
discoiquuid: 163a4887-7c33-4305-8c48-882630f2caa1
exl-id: c63e44e7-cc89-4fa0-8ba4-460d682df601
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1574'
ht-degree: 4%

---

# Snelle gids voor het ontwerpen van pagina&#39;s{#quick-guide-to-authoring-pages}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Deze procedures zijn bedoeld als een snelle (high-level) gids voor de belangrijkste acties van het ontwerpen van pagina-inhoud in AEM.

Ontwikkelaars:

* Niet bedoeld als een volledige dekking.
* Koppelingen naar de gedetailleerde documentatie maken.

Zie voor meer informatie over ontwerpen met AEM:

* [Eerste stappen voor auteurs](/help/sites-authoring/first-steps.md)
* [Werken met de ontwerpomgeving](/help/sites-authoring/author-environment-tools.md)

## Enkele snelle tips {#a-few-quick-hints}

Voordat u het overzicht van de details geeft, is er een kleine verzameling algemene tips en tips die het overwegen waard zijn, vooral als u gewend bent aan de [klassieke UI-ontwerpomgeving](/help/sites-classic-ui-authoring/classicui.md).

### Sites-console {#sites-console}

* **Maken**

   * Deze knoop is beschikbaar in vele consoles - de voorgestelde opties zijn contextgevoelig zodat kan variëren afhankelijk van het scenario.

* Pagina&#39;s in een map opnieuw ordenen

   * Dit kan worden gedaan in [Lijstweergave](/help/sites-authoring/basic-handling.md#list-view). De wijzigingen worden toegepast en zijn zichtbaar in andere weergaven.

* Gebruikersinterface wijzigen

   * Dit kan van diverse plaatsen worden gedaan. Zie [Gebruikersinterface selecteren](/help/sites-authoring/select-ui.md).

### Pagina&#39;s ontwerpen {#page-authoring}

* Navigeren door koppelingen

   * ***Koppelingen zijn niet beschikbaar voor navigatie*** wanneer u binnen bent **Bewerken** in. Als u wilt navigeren met koppelingen, moet u [voorvertoning van de pagina](/help/sites-authoring/editing-content.md#previewing-pages) door gebruik te maken van:

      * [Voorvertoningsmodus](/help/sites-authoring/editing-content.md#preview-mode)
      * [Weergeven als gepubliceerd](/help/sites-authoring/editing-content.md#view-as-published)

* Workflows en versies worden niet meer gestart of gemaakt vanuit de paginaeditor. dit gebeurt nu vanaf [Tijdlijn](/help/sites-authoring/basic-handling.md#timeline) (toegankelijk vanaf de console).

>[!NOTE]
>
>Er zijn een aantal sneltoetsen die de ontwerpervaring kunnen vereenvoudigen.
>
>* [Sneltoetsen bij het bewerken van pagina&#39;s](/help/sites-authoring/page-authoring-keyboard-shortcuts.md)
>* [Sneltoetsen voor consoles](/help/sites-authoring/keyboard-shortcuts.md)


## Uw pagina zoeken {#finding-your-page}

1. Open de **Sites** console (met de **Sites** in de [Algemene navigatie](/help/sites-authoring/basic-handling.md#global-navigation) - deze wordt geactiveerd (vervolgkeuzelijst) wanneer u de Adobe Experience Manager-koppeling selecteert (linksboven).

1. Navigeer omlaag door op de desbetreffende pagina te tikken of te klikken. Hoe de paginabronnen worden weergegeven, is afhankelijk van de weergave die u gebruikt - [Kaart, lijst of kolom](/help/sites-authoring/basic-handling.md#viewing-and-selecting-resources):

   ![screen_shot_2018-03-21at160214](assets/screen_shot_2018-03-21at160214.png)

1. Navigeren door de structuur met [de broodkruimel in de koptekst](/help/sites-authoring/basic-handling.md#the-header)Hiermee kunt u terugkeren naar de geselecteerde locatie:

   ![chlimage_1-95](assets/chlimage_1-95.png)

### Een nieuwe pagina maken {#creating-a-new-page}

1. [Naar de locatie navigeren](#finding-your-page) op de plaats waar u de nieuwe pagina wilt maken.
1. Gebruik de **Maken** pictogram en selecteer vervolgens **Pagina** in de lijst:

   ![screen_shot_2018-03-21at160324](assets/screen_shot_2018-03-21at160324.png)

1. Dit opent de tovenaar die u door het verzamelen van informatie nodig zal begeleiden wanneer [uw nieuwe pagina maken](/help/sites-authoring/managing-pages.md#creating-a-new-page). Volg de aanwijzingen op het scherm.

## Uw pagina selecteren voor verdere actie {#selecting-your-page-for-further-action}

U kunt een pagina selecteren zodat u actie kunt ondernemen. Als u een pagina selecteert, wordt de werkbalk automatisch bijgewerkt, zodat de acties die voor die bron relevant zijn, worden weergegeven.

Hoe te om een pagina te selecteren hangt van welke mening af u in de console gebruikt:

1. Kaartweergave:

   * Selectiemodus openen met [de vereiste bron selecteren](/help/sites-authoring/basic-handling.md#viewing-and-selecting-resources) met:

      * Mobiel apparaat: tikken en vasthouden
      * Desktop: de [snelle actie](/help/sites-authoring/basic-handling.md#quick-actions) - tik pictogram:

         ![screen_shot_2018-03-21at160503](assets/screen_shot_2018-03-21at160503.png)

      * De kaart wordt bedekt met een vinkje om aan te geven dat de pagina is geselecteerd.
   >[!NOTE]
   >
   >Eenmaal in de selectiemodus **Selecteren** wordt gewijzigd in **Deselecteren** pictogram (een kruis).

1. Lijstweergave:

   * Tik/klik op de miniatuur voor de vereiste bron - de miniatuur wordt bedekt met een verdeelstreepje om aan te geven dat deze is geselecteerd.

1. Kolomweergave:

   * Tik/klik op de miniatuur voor de vereiste bron - de miniatuur wordt bedekt met een verdeelstreepje om aan te geven dat deze is geselecteerd.

## Snelle handelingen (alleen kaartweergave/bureaublad) {#quick-actions-card-view-desktop-only}

1. [Naar de pagina navigeren](#finding-your-page) Je wilt actie ondernemen.
1. Houd de muisaanwijzer boven de kaart die uw vereiste bron vertegenwoordigt; de snelle acties worden weergegeven :

   ![screen_shot_2018-03-21at160503-1](assets/screen_shot_2018-03-21at160503-1.png)

## De pagina-inhoud bewerken {#editing-your-page-content}

1. [Naar de pagina navigeren](#finding-your-page) wilt bewerken.
1. [Uw pagina openen om te bewerken](/help/sites-authoring/managing-pages.md#opening-a-page-for-editing) met het pictogram Bewerken (potlood):

   ![screen_shot_2018-03-21at160607](assets/screen_shot_2018-03-21at160607.png)

   Dit is toegankelijk via:

   * [Snelle handelingen (alleen kaartweergave/bureaublad)](#quick-actions-card-view-desktop-only) voor de juiste bron.
   * De werkbalk wanneer uw [pagina is geselecteerd](#selecting-your-page-for-further-action).

1. Wanneer de editor wordt geopend, kunt u:

   * [Een nieuwe versie van uw pagina toevoegen](/help/sites-authoring/editing-content.md#inserting-a-component) door:

      * openen, zijpaneel
      * het selecteren van de componenten tabel (het [componentenbrowser](/help/sites-authoring/author-environment-tools.md#components-browser))
      * Sleep de vereiste component naar de pagina.

      Het zijpaneel kan worden geopend (en gesloten) met:

      ![](do-not-localize/screen_shot_2018-03-21at160738.png)

   * [De inhoud van een bestaande component bewerken](/help/sites-authoring/editing-content.md#edit-configure-copy-cut-delete-paste) op de pagina:

      * Open de werkbalk van de component met Tik of klik. Gebruik de **Bewerken** (potlood) pictogram om het dialoogvenster te openen.
      * Open de editor op plaats voor de component met Tikken en vasthouden of dubbelklikken. De beschikbare acties worden weergegeven (voor sommige componenten is dit een beperkte selectie).
      * U kunt als volgt alle beschikbare acties weergeven:

      ![](do-not-localize/screen_shot_2018-03-21at160706.png)

   * [De eigenschappen van een bestaande component configureren](/help/sites-authoring/editing-content.md#component-edit-dialog)

      * Open de werkbalk van de component met Tik of klik. Gebruik de **Configureren** (moersleutel) om het dialoogvenster te openen.
   * [Een component verplaatsen](/help/sites-authoring/editing-content.md#moving-a-component) ofwel:

      * Sleep de vereiste component naar de nieuwe locatie.
      * Open de werkbalk van de component met Tik of klik. Gebruik de **Knippen** dan **Plakken** pictogrammen indien nodig.
   * [Kopiëren (en Plakken)](/help/sites-authoring/editing-content.md#edit-configure-copy-cut-delete-paste) een component:

      * Open de werkbalk van de component met Tik of klik. Gebruik de **Kopiëren** dan **Plakken** pictogrammen naar wens.
      >[!NOTE]
      >
      >U kunt **Plakken** op dezelfde pagina of op een andere pagina. Als u plakt naar een andere pagina die al was geopend vóór de knip-/kopieerbewerking, moet de pagina worden vernieuwd.

   * [Verwijderen](/help/sites-authoring/editing-content.md#edit-configure-copy-cut-delete-paste) een component:

      * Open de werkbalk van de component met Tik of klik en gebruik vervolgens de knop **Verwijderen** pictogram.
   * [Annotaties toevoegen](/help/sites-authoring/annotations.md#annotations) op de pagina:

      * Selecteer **Annoteren** (pictogram spraakballon). Annotaties toevoegen met de opdracht **Annotatie toevoegen** (plus). Sluit de annotatiemodus af met behulp van de X rechtsboven.

      ![](do-not-localize/screen_shot_2018-03-21at160813.png)

   * [Een voorvertoning van een pagina weergeven](/help/sites-authoring/editing-content.md#preview-mode) (om te zien hoe het in het publicatiemilieu zal verschijnen)

      * Selecteren **Voorvertoning** op de werkbalk.
   * Ga terug naar de bewerkingsmodus (of selecteer een andere modus) met de opdracht **Bewerken** keuzelijst.

   >[!NOTE]
   >
   >Als u wilt navigeren met koppelingen in de inhoud, moet u deze gebruiken [Voorvertoningsmodus](/help/sites-authoring/editing-content.md#preview-mode).

## De pagina-eigenschappen bewerken {#editing-the-page-properties}

Er zijn twee (belangrijkste) methoden [bewerken, pagina-eigenschappen](/help/sites-authoring/editing-page-properties.md):

* Van de **Sites** console:

   1. [Naar de pagina navigeren](#finding-your-page) wilt publiceren.
   1. Selecteer **Eigenschappen** pictogram uit:

      * [Snelle handelingen (alleen kaartweergave/bureaublad)](#quick-actions-card-view-desktop-only) voor de juiste bron.
      * De werkbalk wanneer uw [pagina is geselecteerd](#selecting-your-page-for-further-action).

   ![screen_shot_2018-03-21at160850](assets/screen_shot_2018-03-21at160850.png)

* De pagina-eigenschappen worden weergegeven. U kunt naar wens updates uitvoeren en vervolgens Opslaan gebruiken om deze bij te houden

   * Wanneer [bewerken van uw pagina](#editing-your-page-content):

      1. Open de **Pagina-informatie** -menu.
      1. Selecteren **Eigenschappen openen** om het dialoogvenster voor het bewerken van de eigenschappen te openen.

         ![screen_shot_2018-03-21at160920](assets/screen_shot_2018-03-21at160920.png)

## Uw pagina publiceren (of Publiceren ongedaan maken) {#publishing-your-page-or-unpublishing}

Er zijn twee hoofdmethoden [publiceren, uw pagina](/help/sites-authoring/publishing-pages.md) (en ook bij niet-publicatie):

* Van de **Sites** console:

   1. [Naar de pagina navigeren](#finding-your-page) wilt publiceren.
   1. Selecteer **Snel publiceren** pictogram uit:

      * [Snelle handelingen (alleen kaartweergave/bureaublad)](#quick-actions-card-view-desktop-only) voor de juiste bron.
      * De werkbalk wanneer uw [pagina is geselecteerd](#selecting-your-page-for-further-action) (biedt ook toegang tot [Later publiceren](/help/sites-authoring/publishing-pages.md#manage-publication)).

   ![screen_shot_2018-03-21at160957](assets/screen_shot_2018-03-21at160957.png)

* Wanneer [bewerken van uw pagina](#editing-your-page-content):

   1. Open de **Pagina-informatie** -menu.
   1. Selecteren **Pagina publiceren**.

   ![screen_shot_2018-03-21at161026](assets/screen_shot_2018-03-21at161026.png)

* U kunt het publiceren van een pagina vanuit de console alleen ongedaan maken via de optie **Publicatie beheren**, die alleen beschikbaar is op de werkbalk (niet via de snelle acties).

   De **Publicatie van pagina ongedaan maken** deze optie is nog steeds beschikbaar via de **Pagina-informatie** in de editor.

   ![screen_shot_2018-03-21at161059](assets/screen_shot_2018-03-21at161059.png)

   Zie [Pagina&#39;s publiceren](/help/sites-authoring/publishing-pages.md#unpublishing-pages) voor meer informatie .

## De pagina verplaatsen, kopiëren en plakken of verwijderen {#move-copy-and-paste-or-delete-your-page}

1. [Naar de pagina navigeren](#finding-your-page) u wilt verplaatsen, kopiëren en plakken of verwijderen.
1. Selecteer het pictogram voor kopiëren (en vervolgens plakken), verplaatsen of verwijderen naar wens met een van de volgende methoden:

   * [Snelle handelingen (alleen kaartweergave/bureaublad)](#quick-actions-card-view-desktop-only) voor de vereiste bron.
   * De werkbalk wanneer uw [pagina is geselecteerd](#selecting-your-page-for-further-action).

   * Kopiëren:

      * Vervolgens moet u naar de nieuwe locatie navigeren en plakken.
   * Verplaatsen:

      * De wizard wordt geopend om de gegevens te verzamelen die nodig zijn om de pagina te verplaatsen. Volg de aanwijzingen op het scherm.
   * Verwijderen:

      * U wordt gevraagd de actie te bevestigen.
   >[!NOTE]
   >
   >Verwijderen is niet beschikbaar als een snelle handeling.

## De pagina vergrendelen (en vervolgens ontgrendelen) {#locking-your-page-then-unlocking}

[Door een pagina te vergrendelen](/help/sites-authoring/editing-content.md#locking-a-page) voorkomt u dat andere auteurs op hetzelfde moment als u op de pagina kunnen werken. Het pictogram/de knop Vergrendelen (en Ontgrendelen) vindt u hier:

* De werkbalk wanneer uw [pagina is geselecteerd](#selecting-your-page-for-further-action).
* De [Paginagegevens, vervolgkeuzelijst](#editing-the-page-properties) wanneer u een pagina bewerkt.
* De pagina-werkbalk tijdens het bewerken van een pagina (wanneer de pagina is vergrendeld)

Het vergrendelingspictogram ziet er bijvoorbeeld als volgt uit:

![screen_shot_2018-03-21at161124](assets/screen_shot_2018-03-21at161124.png)

## Paginaverwijzingen openen {#accessing-page-references}

[Snelle toegang tot verwijzingen](/help/sites-authoring/author-environment-tools.md#references) van of naar een pagina zijn beschikbaar in de References Rail.

1. Selecteren **Verwijzingen** met het pictogram van de werkbalk (voor of na [pagina selecteren](#selecting-your-page-for-further-action)):

   ![screen_shot_2018-03-21at161210](assets/screen_shot_2018-03-21at161210.png)

   Er wordt een lijst met referentietypen weergegeven:

   ![screen_shot_2018-03-21at161315](assets/screen_shot_2018-03-21at161315.png)

1. Tik/klik op het gewenste type verwijzing om meer details weer te geven en (indien van toepassing) verdere acties te ondernemen.

## Een versie van uw pagina maken {#creating-a-version-of-your-page}

1. Selecteer **[Tijdlijn](/help/sites-authoring/basic-handling.md#timeline)** met het pictogram van de werkbalk (voor of na [pagina selecteren](#selecting-your-page-for-further-action)):

   ![screen_shot_2018-03-21at161355](assets/screen_shot_2018-03-21at161355.png)

1. Tik/klik op de pijl-omhoog rechtsonder in de kolom Tijdlijn om extra knoppen weer te geven, waaronder **Opslaan als versie**.

   ![screen_shot_2018-03-21at161507](assets/screen_shot_2018-03-21at161507.png)

1. Selecteren **Opslaan als versie** vervolgens **Maken**.

## Een versie van uw pagina herstellen/vergelijken {#restoring-comparing-a-version-of-your-page}

Hetzelfde basismechanisme wordt gebruikt bij het herstellen en/of vergelijken van versies van uw pagina:

1. Selecteren **[Tijdlijn](/help/sites-authoring/basic-handling.md#timeline)** met het pictogram van de werkbalk (voor of na [pagina selecteren](#selecting-your-page-for-further-action)):

   ![screen_shot_2018-03-21at161355-1](assets/screen_shot_2018-03-21at161355-1.png)

   Als er al een versie van de pagina is opgeslagen, wordt deze weergegeven in de tijdlijn.

1. Tik/klik op de versie die u wilt herstellen. Hier worden extra actieknoppen weergegeven:

   * **Deze versie herstellen**

      * De versie wordt hersteld.
   * **Verschillen tonen**

      * De pagina wordt geopend met de verschillen (tussen de twee versies) gemarkeerd.
