---
title: Snelle gids voor het ontwerpen van pagina's
seo-title: Snelle gids voor het ontwerpen van pagina's
description: Een snelle gids op hoog niveau voor de belangrijkste acties van het ontwerpen van pagina-inhoud
seo-description: Een snelle gids op hoog niveau voor de belangrijkste acties van het ontwerpen van pagina-inhoud
uuid: 35442d98-caf9-4cdb-8e68-4fc611e66290
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: page-authoring
content-type: reference
discoiquuid: 163a4887-7c33-4305-8c48-882630f2caa1
exl-id: c63e44e7-cc89-4fa0-8ba4-460d682df601
translation-type: tm+mt
source-git-commit: bd94d3949f0117aa3e1c9f0e84f7293a5d6b03b4
workflow-type: tm+mt
source-wordcount: '1555'
ht-degree: 4%

---

# Snelle gids voor het Ontwerp van Pagina&#39;s{#quick-guide-to-authoring-pages}

Deze procedures zijn bedoeld als een snelle (high-level) gids voor de belangrijkste acties van het ontwerpen van pagina-inhoud in AEM.

Ontwikkelaars:

* Niet bedoeld als een volledige dekking.
* Koppelingen naar de gedetailleerde documentatie maken.

Zie voor meer informatie over ontwerpen met AEM:

* [Eerste stappen voor auteurs](/help/sites-authoring/first-steps.md)
* [Werken met de ontwerpomgeving](/help/sites-authoring/author-environment-tools.md)

## Enkele snelle tips {#a-few-quick-hints}

Alvorens het overzicht van details te geven, is hier een kleine inzameling van algemene uiteinden en wenken die in mening zijn, vooral als u aan [klassieke UI auteursmilieu](/help/sites-classic-ui-authoring/classicui.md) wordt gebruikt.

### Siteconsole {#sites-console}

* **Maken**

   * Deze knoop is beschikbaar in vele consoles - de voorgestelde opties zijn contextgevoelig zodat kan variëren afhankelijk van het scenario.

* Pagina&#39;s in een map opnieuw ordenen

   * Dit kan in [Lijstweergave](/help/sites-authoring/basic-handling.md#list-view) worden gedaan. De wijzigingen worden toegepast en zijn zichtbaar in andere weergaven.

* Gebruikersinterface wijzigen

   * Dit kan van diverse plaatsen worden gedaan. Zie [Uw interface selecteren](/help/sites-authoring/select-ui.md).

### Pagina-ontwerp {#page-authoring}

* Navigeren door koppelingen

   * ***Koppelingen zijn niet beschikbaar voor*** navigatie in de  **** bewerkingsmodus. Als u wilt navigeren met koppelingen, moet u de pagina [voorvertonen met behulp van:](/help/sites-authoring/editing-content.md#previewing-pages)

      * [Voorvertoningsmodus](/help/sites-authoring/editing-content.md#preview-mode)
      * [Weergeven als gepubliceerd](/help/sites-authoring/editing-content.md#view-as-published)

* Workflows en versies worden niet meer gestart of gemaakt vanuit de paginaeditor. dit wordt nu gedaan van [Chronologie](/help/sites-authoring/basic-handling.md#timeline) (toegankelijk van de console).

>[!NOTE]
>
>Er zijn een aantal sneltoetsen die de ontwerpervaring kunnen vereenvoudigen.
>
>* [Sneltoetsen bij het bewerken van pagina&#39;s](/help/sites-authoring/page-authoring-keyboard-shortcuts.md)
>* [Sneltoetsen voor consoles](/help/sites-authoring/keyboard-shortcuts.md)


## Uw pagina {#finding-your-page} zoeken

1. Open de **Sites**-console (met de optie **Sites** in [Algemene navigatie](/help/sites-authoring/basic-handling.md#global-navigation) - deze wordt geactiveerd (vervolgkeuzelijst) wanneer u de Adobe Experience Manager-koppeling selecteert (linksboven).

1. Navigeer omlaag door op de desbetreffende pagina te tikken of te klikken. Hoe de paginabronnen worden vertegenwoordigd, is afhankelijk van de weergave die u gebruikt: - [Kaart, Lijst of Kolom](/help/sites-authoring/basic-handling.md#viewing-and-selecting-resources):

   ![screen_shot_2018-03-21at160214](assets/screen_shot_2018-03-21at160214.png)

1. Navigeer omhoog de boom gebruikend [de broodkruimel in kopbal](/help/sites-authoring/basic-handling.md#the-header), die u toestaat om aan de geselecteerde plaats terug te keren:

   ![chlimage_1-95](assets/chlimage_1-95.png)

### Een nieuwe pagina maken {#creating-a-new-page}

1. [Navigeer naar de ](#finding-your-page) locatie waar u de nieuwe pagina wilt maken.
1. Gebruik het pictogram **Maken** en selecteer vervolgens **Pagina** in de lijst:

   ![screen_shot_2018-03-21at160324](assets/screen_shot_2018-03-21at160324.png)

1. Dit opent de tovenaar die u door het verzamelen van de informatie nodig zal begeleiden wanneer [het creëren van uw nieuwe pagina](/help/sites-authoring/managing-pages.md#creating-a-new-page). Volg de aanwijzingen op het scherm.

## Uw pagina selecteren voor verdere actie {#selecting-your-page-for-further-action}

U kunt een pagina selecteren zodat u actie kunt ondernemen. Als u een pagina selecteert, wordt de werkbalk automatisch bijgewerkt, zodat de acties die voor die bron relevant zijn, worden weergegeven.

Hoe te om een pagina te selecteren hangt van welke mening af u in de console gebruikt:

1. Kaartweergave:

   * Ga selectiemodus door [het selecteren van het vereiste middel](/help/sites-authoring/basic-handling.md#viewing-and-selecting-resources) met:

      * Mobiel apparaat: tikken en vasthouden
      * Desktop: de [snelactie](/help/sites-authoring/basic-handling.md#quick-actions) - tik pictogram:

         ![screen_shot_2018-03-21at160503](assets/screen_shot_2018-03-21at160503.png)

      * De kaart wordt bedekt met een vinkje om aan te geven dat de pagina is geselecteerd.
   >[!NOTE]
   >
   >In de selectiemodus verandert het **Select**-pictogram (een vinkje) in **Deselecteer**-pictogram (een kruis).

1. Lijstweergave:

   * Tik/klik op de miniatuur voor de vereiste bron - de miniatuur wordt bedekt met een verdeelstreepje om aan te geven dat deze is geselecteerd.

1. Kolomweergave:

   * Tik/klik op de miniatuur voor de vereiste bron - de miniatuur wordt bedekt met een verdeelstreepje om aan te geven dat deze is geselecteerd.

## Snelle handelingen (alleen kaartweergave/bureaublad) {#quick-actions-card-view-desktop-only}

1. [Navigeer naar de ](#finding-your-page) pagina waarop u actie wilt ondernemen.
1. Houd de muisaanwijzer boven de kaart die uw vereiste bron vertegenwoordigt; de snelle acties worden weergegeven :

   ![screen_shot_2018-03-21at160503-1](assets/screen_shot_2018-03-21at160503-1.png)

## De pagina-inhoud bewerken {#editing-your-page-content}

1. [Navigeer naar de ](#finding-your-page) pagina die u wilt bewerken.
1. [Open de pagina om deze te ](/help/sites-authoring/managing-pages.md#opening-a-page-for-editing) bewerken met het pictogram Bewerken (potlood):

   ![screen_shot_2018-03-21at160607](assets/screen_shot_2018-03-21at160607.png)

   Dit is toegankelijk via:

   * [Snelle acties (alleen Kaartweergave/Bureaublad) ](#quick-actions-card-view-desktop-only) voor de juiste bron.
   * De werkbalk wanneer uw [pagina is geselecteerd](#selecting-your-page-for-further-action).

1. Wanneer de editor wordt geopend, kunt u:

   * [Voeg een nieuwe compensatie aan uw ](/help/sites-authoring/editing-content.md#inserting-a-component) pagina toe door:

      * openen, zijpaneel
      * het selecteren van het componentenlusje ([componentenbrowser](/help/sites-authoring/author-environment-tools.md#components-browser))
      * Sleep de vereiste component naar de pagina.

      Het zijpaneel kan worden geopend (en gesloten) met:

      ![](do-not-localize/screen_shot_2018-03-21at160738.png)

   * [Bewerk de inhoud van een bestaande ](/help/sites-authoring/editing-content.md#edit-configure-copy-cut-delete-paste) component op de pagina:

      * Open de werkbalk van de component met Tik of klik. Gebruik het pictogram **Bewerken** (potlood) om het dialoogvenster te openen.
      * Open de editor op plaats voor de component met Tikken en vasthouden of dubbelklikken. De beschikbare acties worden weergegeven (voor sommige componenten is dit een beperkte selectie).
      * U kunt als volgt alle beschikbare acties weergeven:

      ![](do-not-localize/screen_shot_2018-03-21at160706.png)

   * [De eigenschappen van een bestaande component configureren](/help/sites-authoring/editing-content.md#component-edit-dialog)

      * Open de werkbalk van de component met Tik of klik. Gebruik **Configure** (moersleutel) pictogram om de dialoog te openen.
   * [Een ](/help/sites-authoring/editing-content.md#moving-a-component) component verplaatsen:

      * Sleep de vereiste component naar de nieuwe locatie.
      * Open de werkbalk van de component met Tik of klik. Gebruik de pictogrammen **Knippen** en **Plakken** indien nodig.
   * [Een ](/help/sites-authoring/editing-content.md#edit-configure-copy-cut-delete-paste) component kopiëren (en plakken):

      * Open de werkbalk van de component met Tik of klik. Gebruik de pictogrammen **Kopiëren** en **Plakken** indien nodig.
      >[!NOTE]
      >
      >U kunt **componenten van het Deeg** aan of de zelfde pagina, of een verschillende pagina. Als u plakt naar een andere pagina die al was geopend vóór de knip-/kopieerbewerking, moet de pagina worden vernieuwd.

   * [component ](/help/sites-authoring/editing-content.md#edit-configure-copy-cut-delete-paste) Deletea:

      * Open de componentwerkbalk met Tik of klik en gebruik vervolgens het pictogram **Delete**.
   * [Voeg ](/help/sites-authoring/annotations.md#annotations) annotaties toe aan de pagina:

      * Selecteer de modus **Annoteren** (pictogram spraakballon). Voeg annotaties toe met het pictogram **Annotatie toevoegen** (plus). Sluit de annotatiemodus af met behulp van de X rechtsboven.

      ![](do-not-localize/screen_shot_2018-03-21at160813.png)

   * [Een voorvertoning van een pagina](/help/sites-authoring/editing-content.md#preview-mode)  weergeven (om te zien hoe deze wordt weergegeven in de publicatieomgeving)

      * Selecteer **Voorvertoning** in de werkbalk.
   * Ga terug naar bewerkingsmodus (of selecteer een andere modus) met de vervolgkeuzelijst **Bewerken**.

   >[!NOTE]
   >
   >Als u wilt navigeren met koppelingen in de inhoud, moet u [Voorvertoningsmodus](/help/sites-authoring/editing-content.md#preview-mode) gebruiken.

## Pagina-eigenschappen bewerken {#editing-the-page-properties}

Er zijn twee (hoofd) methodes van [het uitgeven pagina eigenschappen](/help/sites-authoring/editing-page-properties.md):

* Vanuit de **Sites**-console:

   1. [Navigeer naar de ](#finding-your-page) pagina die u wilt publiceren.
   1. Selecteer het pictogram **Eigenschappen** uit een van de volgende opties:

      * [Snelle acties (alleen Kaartweergave/Bureaublad) ](#quick-actions-card-view-desktop-only) voor de juiste bron.
      * De werkbalk wanneer uw [pagina is geselecteerd](#selecting-your-page-for-further-action).

   ![screen_shot_2018-03-21at160850](assets/screen_shot_2018-03-21at160850.png)

* De pagina-eigenschappen worden weergegeven. U kunt naar wens updates uitvoeren en vervolgens Opslaan gebruiken om deze bij te houden

   * Wanneer [de pagina bewerken](#editing-your-page-content):

      1. Open het menu **Pagina-informatie**.
      1. Selecteer **Eigenschappen openen** om het dialoogvenster te openen voor het bewerken van de eigenschappen.

         ![screen_shot_2018-03-21at160920](assets/screen_shot_2018-03-21at160920.png)

## Uw pagina publiceren (of Publiceren ongedaan maken) {#publishing-your-page-or-unpublishing}

Er zijn twee hoofdmethoden om uw pagina](/help/sites-authoring/publishing-pages.md) te publiceren (en ook om het publiceren ongedaan te maken):[

* Vanuit de **Sites**-console:

   1. [Navigeer naar de ](#finding-your-page) pagina die u wilt publiceren.
   1. Selecteer het pictogram **Snel publiceren** van:

      * [Snelle acties (alleen Kaartweergave/Bureaublad) ](#quick-actions-card-view-desktop-only) voor de juiste bron.
      * De werkbalk wanneer uw [pagina is geselecteerd](#selecting-your-page-for-further-action) (geeft ook toegang tot [Later publiceren](/help/sites-authoring/publishing-pages.md#manage-publication)).

   ![screen_shot_2018-03-21at160957](assets/screen_shot_2018-03-21at160957.png)

* Wanneer [de pagina bewerken](#editing-your-page-content):

   1. Open het menu **Pagina-informatie**.
   1. Selecteer **Pagina publiceren**.

   ![screen_shot_2018-03-21at161026](assets/screen_shot_2018-03-21at161026.png)

* U kunt het publiceren van een pagina vanuit de console alleen ongedaan maken via de optie **Publicatie beheren**, die alleen beschikbaar is op de werkbalk (niet via de snelle acties).

   De optie **Publicatie van pagina opheffen** is nog steeds beschikbaar via het menu **Pagina-informatie** in de editor.

   ![screen_shot_2018-03-21at161059](assets/screen_shot_2018-03-21at161059.png)

   Zie [Pagina&#39;s publiceren](/help/sites-authoring/publishing-pages.md#unpublishing-pages) voor meer informatie.

## De pagina {#move-copy-and-paste-or-delete-your-page} verplaatsen, kopiëren en plakken of verwijderen

1. [Navigeer naar de ](#finding-your-page) pagina die u wilt verplaatsen, kopiëren en plakken of verwijderen.
1. Selecteer het pictogram voor kopiëren (en vervolgens plakken), verplaatsen of verwijderen naar wens met een van de volgende methoden:

   * [Snelle handelingen (alleen Kaartweergave/Bureaublad) ](#quick-actions-card-view-desktop-only) voor de vereiste bron.
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

## De pagina vergrendelen (vervolgens ontgrendelen) {#locking-your-page-then-unlocking}

[Door een pagina te vergrendelen](/help/sites-authoring/editing-content.md#locking-a-page) voorkomt u dat andere auteurs op hetzelfde moment als u op de pagina kunnen werken. Het pictogram/de knop Vergrendelen (en Ontgrendelen) vindt u hier:

* De werkbalk wanneer uw [pagina is geselecteerd](#selecting-your-page-for-further-action).
* Het vervolgkeuzemenu [Pagina-informatie](#editing-the-page-properties) wanneer u een pagina bewerkt.
* De pagina-werkbalk tijdens het bewerken van een pagina (wanneer de pagina is vergrendeld)

Het vergrendelingspictogram ziet er bijvoorbeeld als volgt uit:

![screen_shot_2018-03-21at161124](assets/screen_shot_2018-03-21at161124.png)

## Toegang tot paginaverwijzingen {#accessing-page-references}

[Snelle toegang tot ](/help/sites-authoring/author-environment-tools.md#references) verwijzingen/van een pagina is beschikbaar in de Rail van Verwijzingen.

1. Selecteer **Referenties** gebruikend het toolbarpictogram (of vóór of na [het selecteren van uw pagina](#selecting-your-page-for-further-action)):

   ![screen_shot_2018-03-21at161210](assets/screen_shot_2018-03-21at161210.png)

   Er wordt een lijst met referentietypen weergegeven:

   ![screen_shot_2018-03-21at161315](assets/screen_shot_2018-03-21at161315.png)

1. Tik/klik op het gewenste type verwijzing om meer details weer te geven en (indien van toepassing) verdere acties te ondernemen.

## Een versie van uw pagina maken {#creating-a-version-of-your-page}

1. Als u de tijdlijntrack wilt openen, selecteert u **[Tijdlijn](/help/sites-authoring/basic-handling.md#timeline)** met het werkbalkpictogram (vóór of na [het selecteren van de pagina](#selecting-your-page-for-further-action)):

   ![screen_shot_2018-03-21at161355](assets/screen_shot_2018-03-21at161355.png)

1. Tik/klik op de pijl-omhoog rechtsonder in de kolom Tijdlijn om extra knoppen weer te geven, zoals **Opslaan als versie**.

   ![screen_shot_2018-03-21at161507](assets/screen_shot_2018-03-21at161507.png)

1. Selecteer **Opslaan als versie** en **Maken**.

## Een versie van uw pagina {#restoring-comparing-a-version-of-your-page} herstellen/vergelijken

Hetzelfde basismechanisme wordt gebruikt bij het herstellen en/of vergelijken van versies van uw pagina:

1. Selecteer **[Tijdlijn](/help/sites-authoring/basic-handling.md#timeline)** gebruikend het toolbarpictogram (of vóór of na [het selecteren van uw pagina](#selecting-your-page-for-further-action)):

   ![screen_shot_2018-03-21at161355-1](assets/screen_shot_2018-03-21at161355-1.png)

   Als er al een versie van de pagina is opgeslagen, wordt deze weergegeven in de tijdlijn.

1. Tik/klik op de versie die u wilt herstellen. Hier worden extra actieknoppen weergegeven:

   * **Deze versie herstellen**

      * De versie wordt hersteld.
   * **Verschillen tonen**

      * De pagina wordt geopend met de verschillen (tussen de twee versies) gemarkeerd.
