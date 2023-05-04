---
title: Blogonderdeel
seo-title: Blog Feature
description: Informatie van de Gemeenschap in een journalistiek formaat
seo-description: Community information in a journaling format
uuid: 01f1a547-d22b-4da6-a69c-ab420e5a9e19
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: d5519211-8a04-4699-97bc-e162ec0f3781
exl-id: 12ae8b4c-73c5-4ec9-beea-b682b55ebdfd
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1510'
ht-degree: 0%

---

# Blogonderdeel {#blog-feature}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Inleiding {#introduction}

De blogfunctie voor AEM Communities is veranderd van een ontwerpactiviteit in een echte gemeenschapsactiviteit die plaatsvindt in de publicatieomgeving.

De blogfunctie ondersteunt het verschaffen van gemeenschapsinformatie in een journalistieke indeling. Blogberichten worden in de publicatieomgeving gemaakt door geautoriseerde leden (geregistreerde, aangemelde gebruikers).

De blogfunctie biedt:

* Blogartikelen en opmerkingen maken
* RTF-bewerking
* Inline-afbeeldingen (met ondersteuning voor slepen en neerzetten)
* Inhoud ingesloten sociale netwerken ([Ondersteuning voor insluiten](blog-developer-basics.md#allowing-rich-media))
* Conceptmodus
* Geplande publicatie
* Samenstellen namens (a) [geprivilegieerd lid](users.md#privileged-members-group) kan inhoud maken namens een ander lid van de gemeenschap)
* [In de context en bulkmatiging](moderate-ugc.md) blogartikelen en commentaar

In deze sectie van de documentatie wordt beschreven

* De blogfunctie toevoegen aan een AEM-site
* Configuratie-instellingen voor blogcomponenten

>[!NOTE]
>
>De componenten `Journal`en `Journal Sidebar` worden `Blog` en `Blog Sidebar`.
>
>De blogfunctie in AEM 6.0 en eerdere versies wordt nu verwijderd. Het is gebaseerd op een sjabloon en auteurs mogen alleen inhoud maken in de auteursomgeving.

## Blogcomponenten toevoegen aan een pagina {#adding-blog-components-to-a-page}

Als u een blog wilt toevoegen aan een pagina in de ontwerpmodus, gebruikt u de componentbrowser om de blog te zoeken

* `Communities / Blog`
* `Communities / Blog Sidebar`

En sleep ze naar de juiste plaats op een pagina waarop de blog moet worden weergegeven.

Voor de nodige informatie gaat u naar [Grondbeginselen van Community-componenten](basics.md).

Wanneer de [vereiste clientbibliotheken](blog-developer-basics.md#essentials-for-client-side) worden opgenomen, is dit hoe `Blog`wordt weergegeven:

![chlimage_1-147](assets/chlimage_1-147.png)

En hoe `Blog Sidebar` wordt weergegeven:

![chlimage_1-148](assets/chlimage_1-148.png)

### Blog configureren {#configuring-blog}

Selecteer de geplaatste `Blog` te openen en de component te selecteren `Configure` wordt het dialoogvenster Bewerken geopend.

![Configuratiepictogram](assets/chlimage_1-149.png) ![Bloginstellingen](assets/Blog-configure.png)

#### Het tabblad Instellingen {#settings-tab}

Onder de **[!UICONTROL Settings]** kunt u de basisfuncties van de blog opgeven:

* **[!UICONTROL Allow Attachment Thumbnail]**
Als deze optie is ingeschakeld, wordt een miniatuur van de bijgevoegde afbeelding gemaakt.

* **[!UICONTROL Max Attach Thumbnail Size]**
Maximale grootte (in pixels) van de miniatuurafbeelding van de bijlage. De standaardwaarde is 800 x 800.

* **[!UICONTROL Min Image Size for Thumbnail]**
Minimale afbeeldingsgrootte (in bytes) voor het genereren van miniaturen voor inline-afbeeldingen. De standaardwaarde is 100000bytes (100kb).

* **[!UICONTROL Max Thumbnail Size]**
Maximale grootte (in pixels) van de miniatuurafbeelding voor inline-afbeelding. De standaardwaarde is 800 x 800.

* **[!UICONTROL Allow Privileged Members]**
Als deze optie is ingeschakeld, mogen alleen leden met Geprivilegieerde inhoud maken.

* **[!UICONTROL Allowed Privileged Members]**
Voeg de geprivilegieerde leden toe die inhoud mogen maken.

* **[!UICONTROL Block User Generated Content in Author Edit Mode]**
Als deze optie is ingeschakeld, wordt door de gebruiker gegenereerde inhoud geblokkeerd tijdens het bewerken in de ontwerpmodus.

* **[!UICONTROL Journal Title]**
De blogtitel die op de pagina moet worden weergegeven.
   >Opmerking:
   >Met de functie Dagboek wordt automatisch een URL voor de blog gemaakt. Er worden maximaal 50 tekens (met 5 tekens extra voor uniciteit) gebruikt uit de dagboektitel die u hier opgeeft om een URL voor de blog te maken.

* **[!UICONTROL Journal Description]**
De blogbeschrijving.

* **[!UICONTROL Topics Per Page]**

   Hiermee definieert u het aantal blogberichten/opmerkingen dat per pagina wordt weergegeven. De standaardwaarde is 10.

* **[!UICONTROL Moderated]**

   Als deze optie is ingeschakeld, moet het plaatsen van blogberichten en opmerkingen worden goedgekeurd voordat deze op een publicatiesite worden weergegeven. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Closed]**

   Als deze optie is ingeschakeld, wordt de blog afgesloten met nieuwe blogberichten en opmerkingen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Rich Text Editor]**

   Als deze optie is ingeschakeld, kunnen blogberichten en opmerkingen worden ingevoerd met een markering. Standaard is ingeschakeld.

* **[!UICONTROL Allow Tagging]**

   Als deze optie is ingeschakeld, kunnen leden labels toevoegen aan hun advertentie (zie **[!UICONTROL Tag field]** ). De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow File Uploads]**

   Als deze optie is ingeschakeld, staat u toe dat bestandsbijlagen worden toegevoegd aan een blogbericht of opmerking. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Max File Size]**

   Alleen relevant als `Allow File Uploads` is ingeschakeld. Met dit veld wordt de grootte (in bytes) van een geüpload bestand beperkt. De standaardwaarde is 104857600 (10 MB).

* **[!UICONTROL Allowed File Types]**

   Alleen relevant als `Allow File Uploads` is ingeschakeld. Een door komma&#39;s gescheiden lijst met bestandsextensies met het &quot;punt&quot;-scheidingsteken. Bijvoorbeeld: .jpg, .jpeg, .png, .doc, .docx, .pdf. Als er bestandstypen zijn opgegeven, mogen de niet opgegeven bestandstypen niet worden geüpload. De standaardinstelling is niet opgegeven, zodat alle bestandstypen zijn toegestaan.

* **[!UICONTROL Max Attach Image File Size]**

   Alleen relevant als Uploaden van bestand toestaan is ingeschakeld. Het maximum aantal bytes dat een geüploade afbeeldingsbestand kan hebben. De standaardwaarde is 2097152 (2 MB).

* **[!UICONTROL Allow Replies]**

   Als deze optie is ingeschakeld, kunt u reacties op opmerkingen op het blogbericht toestaan. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Users to Delete Comments and Topics]**

   Als deze optie is ingeschakeld, kunnen leden hun opmerkingen en blogberichten verwijderen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Following]**

   Indien ingeschakeld, neemt u de volgende functie voor blogartikelen op, waardoor leden kunnen worden [aangemeld](notifications.md) van nieuwe posten. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Email Subscriptions]**

   Als deze optie ingeschakeld is, kunnen leden per e-mail op de hoogte worden gesteld van nieuwe berichten ([abonnement](subscriptions.md)). Vereisten `Allow Following` te controleren en [e-mail geconfigureerd](email.md). De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Voting]**

   Als deze optie is ingeschakeld, voegt u de functie Stemmen toe aan een blogbericht. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Display Badges]**

   Indien ingeschakeld, verdiende en toegewezen weergave [badges](implementing-scoring.md) met het blogbericht van een lid. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Featured Content]**

   als het idee wordt gecontroleerd, kan het worden geïdentificeerd als [aanbevolen inhoud](featured.md). De optie Standaard is uitgeschakeld.

#### Tabblad Gebruikersmodernisering {#user-moderation-tab}

Onder de **[!UICONTROL User Moderation]** tab, geeft u de instellingen voor de moderatie op:

* **[!UICONTROL Deny Posts]**

   Als deze optie wordt ingeschakeld, zullen de verantwoordelijken van de leden hun functie kunnen ontkennen en voorkomen dat de functie op het openbare forum verschijnt. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Close/Reopen Topics]**

   Indien gecontroleerd, kunnen de vertrouwde op lidmoderatoren een onderwerp aan verdere uitgeeft en commentaren sluiten, en kunnen een onderwerp ook heropenen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Flag Posts]**

   Als deze optie is ingeschakeld, kunnen leden onderwerpen of opmerkingen van anderen als ongeschikt markeren. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Flag Reason List]**

   Als deze optie is ingeschakeld, kunnen leden in een vervolgkeuzelijst kiezen waarom een onderwerp of opmerking niet als ongepast wordt gemarkeerd. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Custom Flag Reason]**

   Als deze optie is ingeschakeld, kunnen leden hun eigen reden opgeven om een onderwerp of opmerking als ongeschikt te bestempelen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Moderation Threshold]**

   Ga het aantal tijden in een onderwerp of een commentaar moet door leden worden gemarkeerd alvorens moderators worden meegedeeld. De standaardwaarde is 1 (één keer).

* **[!UICONTROL Flagging Limit]**

   Voer het aantal keren in dat een onderwerp of opmerking moet worden gemarkeerd voordat het wordt verborgen in de openbare weergave. Indien ingesteld op -1, wordt het gemarkeerde onderwerp of de opmerking nooit verborgen in de openbare weergave. Anders, moet dit aantal groter dan of gelijk aan de Drempel van de Moderatie zijn. De standaardwaarde is 5.

#### Tabblad Tagveld {#tag-field-tab}

Onder de **[!UICONTROL Tag field]** -tab, geeft u op welke tags mogen worden toegepast als **[!UICONTROL Allow Tagging]** wordt gecontroleerd op **[!UICONTROL Settings]** tab:

* **[!UICONTROL Allowed Namespaces]**

   Relevant indien `Allow Tagging` wordt gecontroleerd onder de **[!UICONTROL Settings]** tab. De tags die kunnen worden toegepast, zijn beperkt tot de tags binnen de geselecteerde naamruimtecategorieën. De lijst met naamruimten bevat &#39;Standaardtags&#39; (de standaardnaamruimte) en &#39;Alle tags opnemen&#39;. De standaardwaarde is niet ingeschakeld, hetgeen betekent dat alle naamruimten zijn toegestaan.

* **[!UICONTROL Suggestion Limit]**

   Voer het aantal tags in dat moet worden weergegeven als suggestie aan het lid dat naar het forum post. De waarde -1 betekent geen limieten. De standaardwaarde is 0.

### Blogzijbalk configureren {#configuring-blog-sidebar}

Wanneer u dubbelklikt op de knop `Blog Sidebar` wordt geopend.

Onder de **[!UICONTROL Journal Sidebar Settings]** op, geeft u de datumnotatie voor archieven op en het type items dat op de zijbalk moet worden weergegeven:

![chlimage_1-151](assets/chlimage_1-151.png)

* **[!UICONTROL Date format]**

   De indeling die wordt gebruikt om weer te geven voor archieven van blogberichten. Voor de notatie worden plaatsaanduidingen gebruikt die voldoen aan de Java-conventie.

   * jjjj: volledig jaar, zoals &quot;2015&quot;
   * jj: kort jaar, zoals &#39;15&#39;
   * MMMMM: volledige maand, zoals juni
   * MMM: korte maand, zoals jun
   * MM: maandnummer, bijvoorbeeld 06

   De standaardwaarde is &quot;jjjj MMMMM&quot;, die bijvoorbeeld &quot;2015 juni&quot; zou weergeven

* **[!UICONTROL View Type]**

   De titel en het type blogberichten die op de zijbalk moeten worden weergegeven. De keuze is tussen

   * Auteurs
   * Categorieën
   * Archieven

* **[!UICONTROL Journal Component Path]**

   *(Optioneel)* De locatie van de blogbron waaruit blogartikelen moeten worden vermeld. Indien leeg gelaten, wordt de component van resourceType gebruikt `social/journal/components/hbs/journal` die op dezelfde pagina wordt weergegeven.

   * Bijvoorbeeld, `/content/sites/engage/en/blog/jcr:content/content/primary/blog`

* **[!UICONTROL Suggestion Limit]**

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

Wanneer de ondertekende in gebruiker moderator of beheerdervoorrechten heeft, kunnen zij uitvoeren [matigingstaken](moderate-ugc.md) (zoals toegestaan door de configuratie van de component) op alle blogartikelen en op blogberichten gepost commentaar.

![chlimage_1-152](assets/chlimage_1-152.png)

### Leden {#members}

Wanneer de gebruiker met de aanmelding lid is van de gemeenschap of [geprivilegieerd lid](users.md#privileged-members-group) (afhankelijk van de configuratie), kunnen zij selecteren `New Article` om een nieuw blogartikel te maken en te plaatsen.

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

## Aanvullende informatie {#additional-information}

Meer informatie is te vinden op de [Grondbeginselen van blogs](blog-developer-basics.md) pagina voor ontwikkelaars.

Zie voor de moderatie van blogberichten en commentaar [Door gebruiker gegenereerde inhoud modereren](moderate-ugc.md).

Zie voor het labelen van blogberichten en opmerkingen [Door gebruiker gegenereerde inhoud labelen](tag-ugc.md).

Zie voor een vertaling van blogberichten en opmerkingen [Door gebruiker gegenereerde inhoud vertalen](translate-ugc.md).
