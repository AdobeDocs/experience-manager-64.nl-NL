---
title: Blogonderdeel
seo-title: Blogonderdeel
description: Informatie van de Gemeenschap in een journalistiek formaat
seo-description: Informatie van de Gemeenschap in een journalistiek formaat
uuid: 01f1a547-d22b-4da6-a69c-ab420e5a9e19
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: d5519211-8a04-4699-97bc-e162ec0f3781
translation-type: tm+mt
source-git-commit: 13d890d08a032fe4eef1dac793dcf2a3e682a52c

---


# Blogonderdeel {#blog-feature}

## Inleiding {#introduction}

De blogfunctie voor AEM Communities is veranderd van een ontwerpactiviteit in een echte gemeenschapsactiviteit die plaatsvindt in de publicatieomgeving.

De blogfunctie ondersteunt het verschaffen van gemeenschapsinformatie in een journalistieke indeling. Blogberichten worden in de publicatieomgeving gemaakt door geautoriseerde leden (geregistreerde, aangemelde gebruikers).

De blogfunctie biedt:

* Blogartikelen en opmerkingen maken
* RTF-bewerking
* Inline-afbeeldingen (met ondersteuning voor slepen en neerzetten)
* Inhoud van ingesloten sociale netwerken (ondersteuning voor[insluiten](blog-developer-basics.md#allowing-rich-media))
* Conceptmodus
* Geplande publicatie
* Namens samenstellen (een [geprivilegieerd lid](users.md#privileged-members-group) kan inhoud namens een ander lid van de Gemeenschap tot stand brengen)
* [In de context en bulkmodernisering](moderate-ugc.md) van blogartikelen en commentaar

In deze sectie van de documentatie wordt beschreven

* De blogfunctie toevoegen aan een AEM-site
* Configuratie-instellingen voor blogcomponenten

>[!NOTE]
>
>De componenten `Journal`en `Journal Sidebar` worden genoemd `Blog` en `Blog Sidebar`.
>
>De blogfunctie in AEM 6.0 en eerdere releases wordt nu verwijderd. Het is gebaseerd op een sjabloon en auteurs mogen alleen inhoud maken in de auteursomgeving.

## Blogcomponenten toevoegen aan een pagina {#adding-blog-components-to-a-page}

Als u een blog wilt toevoegen aan een pagina in de ontwerpmodus, gebruikt u de componentbrowser om de blog te zoeken

* `Communities / Blog`
* `Communities / Blog Sidebar`

En sleep ze naar de juiste plaats op een pagina waarop de blog moet worden weergegeven.

Ga voor de benodigde informatie naar [Community Components Basics](basics.md).

Wanneer de [vereiste client-side bibliotheken](blog-developer-basics.md#essentials-for-client-side) worden opgenomen, ziet u de `Blog`component als volgt:

![chlimage_1-147](assets/chlimage_1-147.png)

En hoe het `Blog Sidebar` zal verschijnen:

![chlimage_1-148](assets/chlimage_1-148.png)

### Blog configureren {#configuring-blog}

Selecteer de geplaatste `Blog` component die u wilt openen en selecteer het `Configure` pictogram waarmee het dialoogvenster Bewerken wordt geopend.

![configureren, pictogram](assets/chlimage_1-149.png) - ![bloginstellingen](assets/Blog-configure.png)

#### Het tabblad Instellingen {#settings-tab}

Geef op het tabblad **[!UICONTROL Instellingen]** de basisfuncties van de blog op:

* **[!UICONTROL Miniatuur]** van bijlage toestaan Als deze optie is ingeschakeld, wordt een miniatuur van de bijgevoegde afbeelding gemaakt.

* **[!UICONTROL Maximale grootte miniatuur]** koppelen Maximale grootte (in pixels) van de miniatuurafbeelding in de bijlage. De standaardwaarde is 800 x 800.

* **[!UICONTROL Minimale afbeeldingsgrootte voor miniatuur]** Minimale afbeeldingsgrootte (in bytes) voor het genereren van miniaturen voor inline-afbeeldingen. De standaardwaarde is 100000bytes (100kb).

* **[!UICONTROL Maximale miniatuurgrootte]** Maximale grootte (in pixels) van de miniatuurafbeelding voor inline-afbeelding. De standaardwaarde is 800 x 800.

* **[!UICONTROL Geprivilegieerde leden]** toestaanAls deze optie is ingeschakeld, mogen alleen geprivilegieerde leden inhoud maken.

* **[!UICONTROL Toegestane geprivilegieerde leden]** Voeg de geprivilegieerde leden toe die inhoud mogen maken.

* **[!UICONTROL Door de gebruiker gegenereerde inhoud blokkeren in de bewerkingsmodus]** Auteur (indien ingeschakeld), wordt door de gebruiker gegenereerde inhoud tijdens het bewerken in de auteurmodus geblokkeerd.

* **[!UICONTROL Dagboektitel]** De blogtitel die op de pagina wordt weergegeven.
   >Opmerking:
   >Met de functie Dagboek wordt automatisch een URL voor de blog gemaakt. Er worden maximaal 50 tekens (met 5 tekens extra voor uniciteit) gebruikt uit de dagboektitel die u hier opgeeft om een URL voor de blog te maken.

* **[!UICONTROL Dagboekbeschrijving]** De blogbeschrijving.

* **[!UICONTROL Onderwerpen per pagina]**

   Hiermee definieert u het aantal blogberichten/opmerkingen dat per pagina wordt weergegeven. De standaardwaarde is 10.

* **[!UICONTROL Gematigd]**

   Als deze optie is ingeschakeld, moet het plaatsen van blogberichten en opmerkingen worden goedgekeurd voordat deze op een publicatiesite worden weergegeven. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Gesloten]**

   Als deze optie is ingeschakeld, wordt de blog afgesloten met nieuwe blogberichten en opmerkingen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL RTF-editor]**

   Als deze optie is ingeschakeld, kunnen blogberichten en opmerkingen worden ingevoerd met een markering. Standaard is ingeschakeld.

* **[!UICONTROL Tags toestaan]**

   Als deze optie is ingeschakeld, kunnen leden labellabels aan hun post toevoegen (zie tabblad **[!UICONTROL Tagveld]** ). De optie Standaard is uitgeschakeld.

* **[!UICONTROL Uploaden van bestanden toestaan]**

   Als deze optie is ingeschakeld, staat u toe dat bestandsbijlagen worden toegevoegd aan een blogbericht of opmerking. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Max. bestandsgrootte]**

   Alleen relevant als `Allow File Uploads` is gecontroleerd. Met dit veld wordt de grootte (in bytes) van een geüpload bestand beperkt. De standaardwaarde is 104857600 (10 MB).

* **[!UICONTROL Toegestane bestandstypen]**

   Alleen relevant als `Allow File Uploads` is gecontroleerd. Een door komma&#39;s gescheiden lijst met bestandsextensies met het &quot;punt&quot;-scheidingsteken. Bijvoorbeeld: .jpg, .jpeg, .png, .doc, .docx, .pdf. Als er bestandstypen zijn opgegeven, mogen de niet opgegeven bestandstypen niet worden geüpload. De standaardinstelling is niet opgegeven, zodat alle bestandstypen zijn toegestaan.

* **[!UICONTROL Maximale bestandsgrootte afbeelding bijvoegen]**

   Alleen relevant als Uploaden van bestand toestaan is ingeschakeld. Het maximum aantal bytes dat een geüploade afbeeldingsbestand kan hebben. De standaardwaarde is 2097152 (2 MB).

* **[!UICONTROL Reacties toestaan]**

   Als deze optie is ingeschakeld, kunt u reacties op opmerkingen op het blogbericht toestaan. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Gebruikers toestaan opmerkingen en onderwerpen te verwijderen]**

   Als deze optie is ingeschakeld, kunnen leden hun opmerkingen en blogberichten verwijderen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Volgen toestaan]**

   Als deze optie is ingeschakeld, neemt u de volgende functie op voor blogartikelen, waarmee leden op de [hoogte](notifications.md) kunnen worden gesteld van nieuwe berichten. De optie Standaard is uitgeschakeld.

* **[!UICONTROL E-mailabonnementen toestaan]**

   Als deze optie is ingeschakeld, kunnen leden via e-mail op de hoogte worden gesteld van nieuwe berichten ([abonnement](subscriptions.md)). Moet `Allow Following` worden gecontroleerd en [e-mail wordt gevormd](email.md). De optie Standaard is uitgeschakeld.

* **[!UICONTROL Stemmen toestaan]**

   Als deze optie is ingeschakeld, voegt u de functie Stemmen toe aan een blogbericht. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Badges weergeven]**

   Indien ingeschakeld, verdiende en toegewezen [badges](implementing-scoring.md) bij het blogbericht van een lid weergeven. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Aanbevolen inhoud toestaan]**

   als deze optie is ingeschakeld, kan het idee worden geïdentificeerd als [aanbevolen inhoud](featured.md). De optie Standaard is uitgeschakeld.

#### Tabblad Gebruikersmodernisering {#user-moderation-tab}

Geef onder het tabblad **[!UICONTROL Gebruikersmodernisering]** de moderatie-instellingen op:

* **[!UICONTROL Posten weigeren]**

   Als deze optie wordt ingeschakeld, zullen de verantwoordelijken van de leden hun functie kunnen ontkennen en voorkomen dat de functie op het openbare forum verschijnt. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Onderwerpen sluiten/opnieuw openen]**

   Indien gecontroleerd, kunnen de vertrouwde op lidmoderatoren een onderwerp aan verdere uitgeeft en commentaren sluiten, en kunnen een onderwerp ook heropenen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Vlagberichten]**

   Als deze optie is ingeschakeld, kunnen leden onderwerpen of opmerkingen van anderen als ongeschikt markeren. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Lijst met redenen voor vlag]**

   Als deze optie is ingeschakeld, kunnen leden in een vervolgkeuzelijst kiezen waarom een onderwerp of opmerking niet als ongepast wordt gemarkeerd. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Reden voor aangepaste vlag]**

   Als deze optie is ingeschakeld, kunnen leden hun eigen reden opgeven om een onderwerp of opmerking als ongeschikt te bestempelen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Moderniseringsdrempel]**

   Ga het aantal tijden in een onderwerp of een commentaar moet door leden worden gemarkeerd alvorens moderators worden meegedeeld. De standaardwaarde is 1 (één keer).

* **[!UICONTROL Limiet voor markering]**

   Voer het aantal keren in dat een onderwerp of opmerking moet worden gemarkeerd voordat het wordt verborgen in de openbare weergave. Indien ingesteld op -1, wordt het gemarkeerde onderwerp of de opmerking nooit verborgen in de openbare weergave. Anders, moet dit aantal groter dan of gelijk aan de Drempel van de Moderatie zijn. De standaardwaarde is 5.

#### Tabblad Tagveld {#tag-field-tab}

Geef onder het tabblad **[!UICONTROL Tagveld]** op welke tags kunnen worden toegepast als **[!UICONTROL Tags]** toestaan is ingeschakeld op het tabblad **[!UICONTROL Instellingen]** :

* **[!UICONTROL Toegestane naamruimten]**

   Relevant als `Allow Tagging` is ingeschakeld onder het tabblad **[!UICONTROL Instellingen]** . De tags die kunnen worden toegepast, zijn beperkt tot de tags binnen de geselecteerde naamruimtecategorieën. De lijst met naamruimten bevat &#39;Standaardtags&#39; (de standaardnaamruimte) en &#39;Alle tags opnemen&#39;. De standaardwaarde is niet ingeschakeld, hetgeen betekent dat alle naamruimten zijn toegestaan.

* **[!UICONTROL Suggestiegrenswaarde]**

   Voer het aantal tags in dat moet worden weergegeven als suggestie aan het lid dat naar het forum post. De waarde -1 betekent geen limieten. De standaardwaarde is 0.

### Blogzijbalk configureren {#configuring-blog-sidebar}

Wanneer u dubbelklikt op de `Blog Sidebar` component, wordt een dialoogvenster voor bewerken geopend.

Geef onder het tabblad **[!UICONTROL Dagboekzijbalkinstellingen]** de datumnotatie voor archieven op en het type items dat u wilt weergeven op de zijbalk:

![chlimage_1-151](assets/chlimage_1-151.png)

* **[!UICONTROL Datumnotatie]**

   De indeling die wordt gebruikt om weer te geven voor archieven van blogberichten. Voor de notatie worden plaatsaanduidingen gebruikt die voldoen aan de Java-conventie.

   * jjjj: volledig jaar, zoals &quot;2015&quot;
   * jj: kort jaar, zoals &#39;15&#39;
   * MMMMM: volledige maand, zoals juni
   * MMM: korte maand, zoals jun
   * MM: maandnummer, bijvoorbeeld 06
   De standaardwaarde is &quot;jjjj MMMMM&quot;, die bijvoorbeeld &quot;2015 juni&quot; zou weergeven

* **[!UICONTROL Type weergave]**

   De titel en het type blogberichten die op de zijbalk moeten worden weergegeven. De keuze is tussen

   * Auteurs
   * Categorieën
   * Archieven

* **[!UICONTROL Pad van component Journal]**

   *(Optioneel)* De locatie van de blogbron waaruit blogartikelen moeten worden vermeld. Als deze optie leeg wordt gelaten, wordt de component resourceType gebruikt die op dezelfde pagina wordt weergegeven. `social/journal/components/hbs/journal`

   * Bijvoorbeeld, `/content/sites/engage/en/blog/jcr:content/content/primary/blog`

* **[!UICONTROL Suggestiegrenswaarde]**

   Het aantal blogartikelen dat moet worden weergegeven. De waarde -1 betekent geen limiet. De standaardwaarde is -1.

## Ervaring met sitebezoekers {#site-visitor-experience}

In de publicatieomgeving wordt met de blogfunctie het meest recente blogartikel weergegeven, gevolgd door oudere blogartikelen in aflopende volgorde van ontwerp. Met blogzijbalken kunnen sitebezoekers filters toepassen om de selectie van weergegeven blogartikelen te beperken.

Het blogartikel wordt gevolgd door een koppeling om opmerkingen te plaatsen of weer te geven.

Wanneer een blogartikel is geselecteerd, worden het blogartikel en de opmerkingen weergegeven (indien ingeschakeld).

Andere vaardigheden hangen af van het feit of de bezoeker van de site een moderator, beheerder, lid van de gemeenschap, geprivilegieerd lid of anoniem is.

### Werken met artikelen {#working-with-articles}

Wanneer u een nieuw blogartikel maakt, kunt u

1. Direct publiceren
1. Een concept publiceren
1. Publiceren op een geplande datum en tijd

De blogartikelen worden op het juiste tabblad (Gepubliceerd, Concepten of Gepland) weergegeven voor leden die tijdens het publiceren kunnen ontwerpen.

#### Moderatoren en beheerders {#moderators-and-administrators}

Wanneer de aangemelde gebruiker moderator of beheerdersrechten heeft, kunnen zij [moderatietaken](moderate-ugc.md) uitvoeren (zoals toegestaan door de configuratie van de component) op alle blogartikelen en commentaar dat op een blog wordt geplaatst.

![chlimage_1-152](assets/chlimage_1-152.png)

### Leden {#members}

Wanneer de aangemelde gebruiker een lid van de gemeenschap of een [geprivilegieerd lid](users.md#privileged-members-group) is (afhankelijk van de configuratie), kunnen deze selecteren `New Article` om een nieuw blogartikel te maken en te plaatsen.

Zij kunnen met name:

* Een nieuw blogartikel maken
* Plaats een nieuw blogartikel namens een ander lid
* Opmerkingen op een blogartikel plaatsen
* Uw eigen blogartikel of commentaar bewerken
* Hun eigen blogartikel of commentaar verwijderen
* Blogartikelen of opmerkingen van anderen markeren

![chlimage_1-153](assets/chlimage_1-153.png) ![chlimage_1-154](assets/chlimage_1-154.png)

### Anoniem {#anonymous}

Sitebezoekers die niet zijn aangemeld, kunnen alleen geposte blogartikelen en opmerkingen lezen, deze vertalen als ze worden ondersteund, maar mogen geen blogartikel of commentaar toevoegen en de artikelen of opmerkingen van anderen niet markeren.

![chlimage_1-155](assets/chlimage_1-155.png)

## Additional Information {#additional-information}

Meer informatie vindt u op de pagina [Blog Essentials](blog-developer-basics.md) voor ontwikkelaars.

Zie Door gebruiker gegenereerde inhoud [modereren voor de moderatie van blogberichten en opmerkingen](moderate-ugc.md).

Zie Door gebruiker gegenereerde inhoud [](tag-ugc.md)labelen voor het labelen van blogberichten en opmerkingen.

Zie Door gebruiker gegenereerde inhoud [vertalen voor een vertaling van blogberichten en opmerkingen](translate-ugc.md).
