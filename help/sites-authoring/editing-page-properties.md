---
title: Pagina-eigenschappen bewerken
seo-title: Editing Page Properties
description: De vereiste eigenschappen voor een pagina definiëren
seo-description: Define the required properties for a page
uuid: c0386cd6-ca01-4741-b8c8-36edb66e50ef
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: page-authoring
content-type: reference
discoiquuid: 8e85ea7f-80ea-43b6-a67c-366852ef86ce
exl-id: b0e579a4-f5bd-4a55-a003-0496224bc940
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1825'
ht-degree: 3%

---

# Pagina-eigenschappen bewerken{#editing-page-properties}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

U kunt de vereiste eigenschappen voor een pagina definiëren. Deze kunnen afhankelijk van de aard van de pagina variëren. Sommige pagina&#39;s kunnen bijvoorbeeld zijn verbonden met een live kopie, andere niet en de live kopie-informatie is beschikbaar, indien van toepassing.

## Pagina-eigenschappen {#page-properties}

De eigenschappen worden verdeeld over verscheidene lusjes.

### Basis {#basic}

* **Titel**

   De titel van de pagina wordt op verschillende locaties weergegeven. De **Websites** en de **Sites** kaart-/lijstweergaven.

   Dit is een verplicht veld.

* **Tags**

   Hier kunt u codes toevoegen aan of verwijderen uit de pagina door de lijst in het selectievak bij te werken:

   * Nadat u een tag hebt geselecteerd, wordt deze weergegeven onder het selectievak. U kunt een tag uit deze lijst verwijderen met de x.
   * U kunt een volledig nieuwe tag invoeren door de naam in een leeg selectievak te typen.

      * De nieuwe tag wordt gemaakt wanneer u op Enter drukt.
      * De nieuwe tag wordt dan weergegeven met een kleine ster aan de rechterkant die aangeeft dat het een nieuwe tag is.
   * Met de vervolgkeuzefunctie kunt u bestaande tags selecteren.
   * Een x wordt weergegeven wanneer u met de muis over een tag-item in het selectievak beweegt. Hiermee kunt u die tag voor deze pagina verwijderen.

   Zie voor meer informatie over tags [Tags gebruiken](/help/sites-authoring/tags.md).

* **Verbergen in navigatie**

   Geeft aan of de pagina wordt weergegeven of verborgen in de paginanavigatie van de resulterende site.

* **Branding**

   Pas een consistente merkidentiteit toe op de verschillende pagina&#39;s door een merkmarkering aan elke paginatitel toe te voegen. Voor deze functionaliteit is het gebruik van de component Pagina vanaf versie 2.14.0 of hoger van het dialoogvenster [Core Components.](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html)

   * **Negeren** - Schakel dit selectievakje in om de merkwitruimte op deze pagina te definiëren.
      * De waarde wordt overgeërfd door onderliggende pagina&#39;s, tenzij deze ook hun **Negeren** ingestelde waarden.
   * **Waarde overschrijven** - De tekst van de merkmarkering die aan de paginatitel moet worden toegevoegd.
      * De waarde wordt toegevoegd aan de paginatitel na een pipe-teken, zoals &quot;Cycling Tuscany&quot; | Altijd klaar voor de WKND&quot;

* **Paginatitel**

   Een titel die op de pagina moet worden gebruikt. Wordt meestal gebruikt door titelcomponenten. Als de **Titel** wordt gebruikt.

* **Navigatietitel**

   U kunt een aparte titel opgeven voor gebruik in de navigatie (bijvoorbeeld als u iets beknopter wilt). Indien leeg, **Titel** wordt gebruikt.

* **Ondertitel**

   Een ondertitel voor gebruik op de pagina.

* **Beschrijving**

   Uw beschrijving van de pagina, het doel of andere details die u wilt toevoegen.

* **Op tijd**

   De datum en het tijdstip waarop de gepubliceerde pagina wordt geactiveerd. Wanneer deze pagina wordt gepubliceerd, blijft deze sluimerend tot de opgegeven tijd.

   Laat deze velden leeg voor pagina&#39;s die u direct wilt publiceren (het normale scenario).

* **Uit-tijd**

   De tijd waarop de gepubliceerde pagina wordt gedeactiveerd.

   Laat deze velden weer leeg voor directe actie.

* **Vanity URL**

   Hiermee kunt u een vanity-URL voor deze pagina invoeren, waarmee u een kortere en/of expressieve URL kunt hebben.

   Als de URL voor Vanity bijvoorbeeld is ingesteld op w `elcome`naar de pagina die wordt aangegeven door het pad / `v1.0/startpage`voor de website h `ttp://example.com,` vervolgens h `ttp://example.com/welcome`zou de vanity URL van h zijn `ttp://example.com/content/v1.0/startpage`

   >[!CAUTION]
   >
   >Vanity-URL&#39;s:
   >
   >* Dit moet uniek zijn, dus zorg ervoor dat de waarde niet al door een andere pagina wordt gebruikt.
   >* Geen ondersteuning voor regex-patronen.


* **Redirect Vanity URL**

   Hiermee geeft u aan of u wilt dat de pagina de vanity-URL gebruikt.

### Geavanceerd {#advanced}

* **Taal**

   De paginataal.

* **Omleiden**

   Geef de pagina op waarnaar deze pagina automatisch moet worden omgeleid.

* **Ontwerp**

   Geef de [ontwerp](/help/sites-developing/designer.md) die voor deze pagina moet worden gebruikt.

* **Alias**

   Geef een alias op die voor deze pagina moet worden gebruikt.

   * Als u bijvoorbeeld een alias definieert van `private` voor de pagina `/content/wknd/us/en/magazine/members-only`, kan deze pagina ook worden geopend via `/content/wknd/us/en/magazine/private`.
   * Het creëren van een aliasreeksen `sling:alias` eigenschap op het paginaknooppunt, die alleen invloed heeft op de bron, niet op het pad naar de opslagplaats.
   * Pagina&#39;s die door aliassen in de editor worden benaderd, kunnen niet worden gepubliceerd. [Publicatieopties](/help/sites-authoring/publishing-pages.md) in de editor zijn alleen beschikbaar voor pagina&#39;s die via hun werkelijke paden worden benaderd.
   * Zie voor meer informatie [Gelokaliseerde paginanamen onder SEO- en URL-beheertips](/help/managing/seo-and-url-management.md#localized-page-names)

* **Toegestane sjablonen**

   [De lijst met beschikbare sjablonen definiëren](/help/sites-authoring/templates.md#enabling-and-allowing-a-template-template-author) binnen dit subbijkantoor.

* **Verificatievereiste**

   Hiermee wordt het gebruik van verificatie voor toegang tot de pagina ingeschakeld (of uitgeschakeld).

   Het vereiste om authentificatie te hebben kan hier samen met een aangewezen openings van een sessiepagina worden geplaatst. Gesloten gebruikersgroepen voor de pagina worden gedefinieerd op de **[Machtigingen](/help/sites-authoring/editing-page-properties.md#permissions)** tab.

   >[!CAUTION]
   >
   >De **[Machtigingen](/help/sites-authoring/editing-page-properties.md#permissions)** kunt u CUG-configuraties bewerken op basis van de aanwezigheid van de `granite:AuthenticationRequired` mixin. Als de paginamachtigingen gebruikend verouderde configuraties van de GIDS worden gevormd, die op de aanwezigheid van cq worden gebaseerd:cugEnabled bezit, zal een waarschuwingsbericht onder worden getoond **Verificatievereiste** en de optie zal niet bewerkbaar zijn, en de [Machtigingen](/help/sites-authoring/editing-page-properties.md#permissions) bewerkbaar zijn.
   >
   >
   >In dat geval moeten de CUG-machtigingen worden bewerkt in het dialoogvenster [klassieke gebruikersinterface](/help/sites-classic-ui-authoring/classic-page-author-edit-page-properties.md).

* **Aanmeldingspagina**

   De pagina die voor login moet worden gebruikt.

* **Configuratie exporteren**

   Geef een exportconfiguratie op.

### Miniatuur {#thumbnail}

1. **Paginaminiatuur**

   Hiermee geeft u de miniatuurafbeelding van de pagina weer. U kunt:

   * **Voorvertoning genereren**

      Genereer een voorvertoning van de pagina die u als miniatuur wilt gebruiken.

   * **Afbeelding uploaden**

      Upload een afbeelding die u als miniatuur wilt gebruiken.

### Sociale media {#social-media}

* **Delen via sociale media**

   Definieert de opties voor delen die beschikbaar zijn op de pagina. Hiermee geeft u de opties weer die beschikbaar zijn voor de [De kerncomponent delen](https://helpx.adobe.com/experience-manager/core-components/using/sharing.html).

   * **Delen door gebruikers voor Facebook inschakelen**
   * **Delen door gebruikers voor Pinterest inschakelen**
   * **Voorkeurswijziging XF**
De fragmentvariatie definiëren die wordt gebruikt voor het genereren van metagegevens voor de pagina

### Cloud Services {#cloud-services}

* **Cloud Services**

   Eigenschappen definiëren voor [cloudservices](/help/sites-developing/extending-cloud-config.md).

### Personalisatie {#personalization}

* **Personalisatie**

   Selecteer een [Merk om een werkingsgebied voor het richten te specificeren](/help/sites-authoring/personalization.md).

### Machtigingen {#permissions}

* **Machtigingen**

   Op dit tabblad kunt u het volgende doen:

   * [Machtigingen toevoegen](/help/sites-administering/user-group-ac-admin.md)
   * [Gesloten gebruikersgroep bewerken](/help/sites-administering/cug.md#applying-your-closed-user-group-to-content-pages)
   * De weergave van [Effectieve machtigingen](/help/sites-administering/user-group-ac-admin.md)

   >[!CAUTION]
   >
   >De **Machtigingen** kunt u CUG-configuraties bewerken op basis van de aanwezigheid van de `granite:AuthenticationRequired` mixin. Als de paginamachtigingen gebruikend verouderde configuraties van de KUG worden gevormd, gebaseerd op de aanwezigheid van `cq:cugEnabled` eigenschap, wordt een waarschuwingsbericht weergegeven en zijn de CUG-machtigingen niet bewerkbaar. Ook is het vereiste voor verificatie niet van toepassing op de [Geavanceerd](/help/sites-authoring/editing-page-properties.md#advanced) te bewerken.
   >
   >
   >In dat geval moeten de CUG-machtigingen worden bewerkt in het dialoogvenster [klassieke gebruikersinterface](/help/sites-classic-ui-authoring/classic-page-author-edit-page-properties.md).

   >[!NOTE]
   >
   >Het lusje van Toestemmingen staat niet de verwezenlijking van lege groepen CUG toe, die als eenvoudige manier kunnen nuttig zijn om toegang tot elke gebruiker te ontkennen. Om dit te doen moet de Ontdekkingsreiziger van CRX worden gebruikt. Zie het document [Beheer van gebruikers-, groep- en toegangsrechten](/help/sites-administering/user-group-ac-admin.md) voor meer informatie .

### Blauwdruk {#blueprint}

* **Blauwdruk**

   Eigenschappen definiëren voor een pagina Vervagen in [beheer op meerdere locaties](/help/sites-administering/msm.md). Hiermee bepaalt u de omstandigheden waaronder wijzigingen worden doorgegeven aan Live kopie.

### Live kopie {#live-copy}

* **Livecopy**

   Eigenschappen definiëren voor een pagina van Live kopie binnen [beheer op meerdere locaties](/help/sites-administering/msm.md). Hiermee bepaalt u de omstandigheden waaronder wijzigingen worden doorgegeven via het blauwdruk.

### Sitestructuur {#site-structure}

* Koppelingen maken naar pagina&#39;s die functionaliteit voor de hele site bieden, zoals **Aanmeldingspagina**, **Offline pagina**, onder andere.

## Pagina-eigenschappen bewerken {#editing-page-properties-2}

U kunt pagina-eigenschappen definiëren:

* Van de **Sites** console:

   * [Een nieuwe pagina maken](/help/sites-authoring/managing-pages.md#creating-a-new-page) (een subset van de eigenschappen)
   * Klikken of tikken **Eigenschappen**

      * Voor één pagina
      * Voor meerdere pagina&#39;s (alleen een subset van de eigenschappen is beschikbaar voor massabewerking)

* Vanuit de pagina-editor:

   * **Pagina-informatie** gebruiken (en vervolgens **Eigenschappen openen**)

### Vanuit de siteconsole - Eén pagina {#from-the-sites-console-single-page}

Klikken of tikken **Eigenschappen** om de pagina-eigenschappen te definiëren:

1. Met de **Sites** navigeer naar de locatie van de pagina waarvan u de eigenschappen wilt weergeven en bewerken.

1. Selecteer **Eigenschappen** optie voor de vereiste pagina met behulp van:

   * [Snelle acties](/help/sites-authoring/basic-handling.md#quick-actions)
   * [Selectiemodus](/help/sites-authoring/basic-handling.md#viewing-and-selecting-resources)

   De pagina-eigenschappen worden weergegeven met de juiste tabbladen.

1. Bekijk of bewerk de eigenschappen naar wens.

1. Gebruik vervolgens **Opslaan** om uw updates op te slaan, gevolgd door **Sluiten** om naar de console terug te keren.

### Bij het bewerken van een pagina {#when-editing-a-page}

Wanneer u een pagina bewerkt, kunt u **Pagina-informatie** om de pagina-eigenschappen te definiëren:

1. Open de pagina waarvan u de eigenschappen wilt bewerken.

1. Selecteer **Pagina-informatie** pictogram om het selectiemenu te openen:

   ![screen_shot_2018-03-22at095740](assets/screen_shot_2018-03-22at095740.png)

1. Selecteren **Eigenschappen openen** en er wordt een dialoogvenster geopend waarin u de eigenschappen kunt bewerken, gesorteerd op het juiste tabblad. De volgende knoppen zijn ook beschikbaar aan de rechterkant van de werkbalk:

   * **Annuleren**
   * **Opslaan en sluiten**

1. Gebruik de **Opslaan en sluiten** om de wijzigingen op te slaan.

### Van de Console van Plaatsen - Meerdere Pagina&#39;s {#from-the-sites-console-multiple-pages}

Vanuit de **Sites**-console kunt u meerdere pagina&#39;s selecteren en vervolgens **Eigenschappen weergeven** gebruiken om de pagina-eigenschappen te bekijken en/of te bewerken. Dit wordt het bulkgewijs bewerken van pagina-eigenschappen genoemd.

>[!NOTE]
>
>Bulkbewerking van eigenschappen is ook beschikbaar voor Elementen. Het is erg vergelijkbaar, maar op een paar punten verschilt het. Zie [Eigenschappen van meerdere elementen bewerken](/help/assets/managing-multiple-assets.md) voor meer informatie.
>
>Er is ook [Bulkeditor](/help/sites-administering/bulk-editor.md), waarmee u naar inhoud van meerdere pagina&#39;s kunt zoeken met GQL (Google Query Language) en de inhoud vervolgens rechtstreeks in de grote editor kunt bewerken voordat u de wijzigingen opslaat op de pagina&#39;s die beginnen.

U kunt meerdere pagina&#39;s selecteren voor bulkbewerking op verschillende manieren, zoals:

* Wanneer u door de **Sites** console
* Na gebruik van **Zoeken** om een set pagina&#39;s te zoeken

![screen_shot_2018-03-22at100039](assets/screen_shot_2018-03-22at100039.png)

Nadat u de pagina&#39;s hebt geselecteerd en vervolgens op de knop **Eigenschappen** de bulkeigenschappen worden weergegeven:

![screen_shot_2018-03-22at100114](assets/screen_shot_2018-03-22at100114.png)

U kunt alleen pagina&#39;s bulksgewijs bewerken die:

* Hetzelfde brontype delen
* Maakt geen deel uit van een livecopy

   * Als een van de pagina&#39;s zich in een live kopie bevindt, wordt een bericht weergegeven wanneer de eigenschappen worden geopend.

Nadat u de optie Bulk bewerken hebt ingevoerd, kunt u:

* **Weergave**

   Wanneer u pagina-eigenschappen weergeeft voor meerdere pagina&#39;s, kunt u het volgende zien:

   * Een lijst met de betrokken pagina&#39;s

      * U kunt desgewenst selecteren/deselecteren
   * Tabs

      * Net als bij het weergeven van eigenschappen voor één pagina, worden de eigenschappen onder tabbladen geordend.
   * Een subset van eigenschappen

      * Eigenschappen die beschikbaar zijn op alle geselecteerde pagina&#39;s en die expliciet zijn gedefinieerd als beschikbaar voor bulkbewerking, zijn zichtbaar.
      * Als u de paginaselectie tot één pagina reduceert, zijn alle eigenschappen zichtbaar.
   * Algemene eigenschappen met een gemeenschappelijke waarde

      * Alleen eigenschappen met een gemeenschappelijke waarde worden weergegeven in de weergavemodus.
      * Als het veld meerdere waarden heeft (bijvoorbeeld Codes), worden waarden alleen weergegeven als *alles* vaak voorkomen. Als slechts enkele van deze voorbeelden algemeen zijn, worden deze alleen weergegeven tijdens het bewerken.

   Wanneer er geen eigenschappen met een gemeenschappelijke waarde bestaan, wordt een bericht weergegeven.

* **Bewerken**

   Bij het bewerken van Pagina-eigenschappen voor meerdere pagina&#39;s:

   * U kunt de waarden in de beschikbare velden bijwerken.

      * De nieuwe waarden worden toegepast op alle geselecteerde pagina&#39;s wanneer u **Gereed**.
      * Wanneer het veld meerdere waarden heeft (bijvoorbeeld Codes), kunt u een nieuwe waarde toevoegen of een gemeenschappelijke waarde verwijderen.
   * Velden die veel voorkomen, maar verschillende waarden op de verschillende pagina&#39;s hebben, worden aangegeven met een speciale waarde, zoals de tekst `<Mixed Entries>`. Bij het bewerken van dergelijke velden moet de nodige aandacht worden besteed om gegevensverlies te voorkomen.


>[!NOTE]
>
>De paginacomponent kan worden gevormd om de gebieden te specificeren beschikbaar voor bulkbewerking. Zie [De pagina configureren voor het bulksgewijs bewerken van pagina-eigenschappen](/help/sites-developing/bulk-editing.md).
