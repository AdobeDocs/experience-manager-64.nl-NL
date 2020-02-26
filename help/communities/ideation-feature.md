---
title: Ideatiefunctie
seo-title: Ideatiefunctie
description: De functie Ideatie toevoegen en configureren
seo-description: De functie Ideatie toevoegen en configureren
uuid: b21507da-10c8-4149-9e2c-a4ff5dec582b
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: 7c0a9120-2edb-431b-b460-68398832d5ec
translation-type: tm+mt
source-git-commit: 5ddbcb2addff2d6e3a3e9d7e100a6d9ba89fdd60

---


# Ideatiefunctie {#ideation-feature}

## Inleiding {#introduction}

De functie Ideatie biedt een gebied voor ingetekende sitebezoekers (leden van de community) in de publicatieomgeving voor:

* Creëer ideeën om met de gemeenschap te delen
* Bekijk en becommentariëer ideeën
* Een idee volgen
* Stemming over een idee

In deze sectie van de documentatie wordt beschreven

* De ideatiefunctie toevoegen aan een AEM-site
* Configuratie-instellingen voor de component Idee

## Een idee toevoegen aan een pagina {#adding-a-ideation-to-a-page}

Als u een `Ideation` component wilt toevoegen aan een pagina in de ontwerpmodus, gebruikt u de componentbrowser om de component te zoeken `Communities / Ideation` en naar de gewenste positie op een pagina te slepen.

Ga voor de benodigde informatie naar [Community Components Basics](basics.md).

Wanneer de [vereiste client-side bibliotheken](ideation.md#essentials-for-client-side) worden opgenomen, ziet u de `Ideation`component als volgt:

![chlimage_1-29](assets/chlimage_1-29.png)

## Een idee configureren {#configuring-an-ideation}

Selecteer de geplaatste `Ideation` component die u wilt openen en selecteer het `Configure` pictogram waarmee het dialoogvenster Bewerken wordt geopend.

![chlimage_1-30](assets/chlimage_1-30.png) ![chlimage_1-31](assets/chlimage_1-31.png)

### Het tabblad Instellingen {#settings-tab}

Geef op het tabblad **[!UICONTROL Instellingen]** instellingen op voor ideeën en opmerkingen:

* **[!UICONTROL Titel]** van idee De weergavetotel voor het idee. Standaard is dit `Ideation`.

* **[!UICONTROL Beschrijving]** van idee Een beschrijving die als ondertitel voor het idee moet worden weergegeven. Standaard is geen beschrijving.

* **[!UICONTROL De onderwerpen per Pagina]** bepalen het aantal ideeën/posten dat per pagina wordt getoond. De standaardwaarde is 10.

* **[!UICONTROL Gemoderniseerd]** Als deze optie is ingeschakeld, moet het posten van ideeën en opmerkingen worden goedgekeurd voordat ze op een publicatiesite worden weergegeven. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Gesloten]** Als dit wordt gecontroleerd, is het ideatieforum gesloten voor nieuwe ideeën en opmerkingen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL De Rich Text Editor]** Indien ingeschakeld, kunnen ideeën en opmerkingen worden ingevoerd met markering. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Labelen]** toestaan Als deze optie is ingeschakeld, kunnen leden labellabels aan hun post toevoegen (zie tabblad **[!UICONTROL Tagveld]** ). De optie Standaard is uitgeschakeld.

* **[!UICONTROL Uploaden]** van bestand toestaan Als deze optie is ingeschakeld, kunnen bestandsbijlagen worden toegevoegd aan het idee of de opmerking. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Maximale bestandsgrootte]** alleen relevant als deze `Allow File Uploads` is ingeschakeld. Met dit veld wordt de grootte (in bytes) van een geüpload bestand beperkt. De standaardwaarde is 104857600 (10 MB).

* **[!UICONTROL Alleen toegestane bestandstypen]** relevant als deze `Allow File Uploads` is ingeschakeld. Een door komma&#39;s gescheiden lijst met bestandsextensies met het &quot;punt&quot;-scheidingsteken. Bijvoorbeeld: .jpg, .jpeg, .png, .doc, .docx, .pdf. Als er bestandstypen zijn opgegeven, mogen de niet opgegeven bestandstypen niet worden geüpload. De standaardinstelling is niet opgegeven, zodat alle bestandstypen zijn toegestaan.

* **[!UICONTROL Maximale bestandsgrootte]** van afbeelding alleen relevant koppelen als Uploaden van bestand toestaan is ingeschakeld. Het maximum aantal bytes dat een geüploade afbeeldingsbestand kan hebben. De standaardwaarde is 2097152 (2 MB).

* **[!UICONTROL Reacties]** toestaan Als deze optie is ingeschakeld, kunt u reacties op opmerkingen die op het idee zijn geplaatst toestaan. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Gebruikers toestaan opmerkingen en onderwerpen]** te verwijderen Als deze optie is ingeschakeld, kunnen leden de opmerkingen en ideeën die ze hebben geplaatst verwijderen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Na]** Indien ingeschakeld, neemt u de volgende functie op voor ideeënposts, waardoor leden op de [hoogte](notifications.md) kunnen worden gesteld van nieuwe posten. De optie Standaard is uitgeschakeld.

* **[!UICONTROL E-mailabonnementen]** toestaan Als deze optie is ingeschakeld, kunnen leden per e-mail op de hoogte worden gesteld van nieuwe berichten ([abonnement](subscriptions.md)). Moet `Allow Following` worden gecontroleerd en [e-mail wordt gevormd](email.md). De optie Standaard is uitgeschakeld.

* **[!UICONTROL Stemmen]** toestaan Indien ingeschakeld, stemmen over de opmerkingen van een idee toestaan. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Badges]** weergeven Indien ingeschakeld, verdiende en toegewezen [badges](implementing-scoring.md) weergeven met het idee van een lid. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Aanbevolen inhoud]** toestaan als deze optie is ingeschakeld, kan het idee worden geïdentificeerd als [aanbevolen inhoud](featured.md). De optie Standaard is uitgeschakeld.

### Tabblad Gebruikersmodernisering {#user-moderation-tab}

Geef op onder het tabblad **[!UICONTROL Gebruikersmodernisering]** op hoe de geposte ideeën en opmerkingen (door de gebruiker gegenereerde inhoud) worden beheerd. Voor meer informatie, zie het [Modereren van Gebruiker Gegenereerde Inhoud](moderate-ugc.md).

* **[!UICONTROL Posten]** weigeren Als deze optie is ingeschakeld, mogen gematigde leden posten weigeren en voorkomen dat de post op het openbare forum verschijnt. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Sluit/heropen Onderwerpen]** Indien gecontroleerd, kunnen de vertrouwde op lidmoderatoren een onderwerp aan verdere uitgeeft en commentaren sluiten, en kunnen een onderwerp ook heropenen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Vlagberichten]** Als deze optie is ingeschakeld, kunnen leden onderwerpen of opmerkingen van anderen als ongeschikt markeren. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Lijst]** met redenen voor vlagAls deze optie is ingeschakeld, kunnen leden in een vervolgkeuzelijst kiezen waarom zij een onderwerp of opmerking als ongeschikt aanmerken. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Reden]** voor aangepaste vlag Als dit selectievakje is ingeschakeld, kunnen leden hun eigen reden opgeven om een onderwerp of opmerking als ongeschikt te bestempelen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL De Drempel]** van de modernisering gaat het aantal tijden in een onderwerp of een commentaar moet door leden worden gemarkeerd alvorens de moderatoren op de hoogte worden gebracht. De standaardwaarde is 1 (één keer).

* **[!UICONTROL Laginglimiet]** Voer het aantal keren in dat een onderwerp of opmerking moet worden gemarkeerd voordat het wordt verborgen in de openbare weergave. Indien ingesteld op -1, wordt het gemarkeerde onderwerp of de opmerking nooit verborgen in de openbare weergave. Anders, moet dit aantal groter dan of gelijk aan de Drempel van de Moderatie zijn. De standaardwaarde is 5.

### Tabblad Tagveld {#tag-field-tab}

Onder het tabblad **[!UICONTROL Tagveld]** zijn de tags die kunnen worden toegepast, indien toegestaan op het tabblad **[!UICONTROL Instellingen]** , beperkt op basis van de gekozen naamruimten.

* **[!UICONTROL Toegestane naamruimten]** relevant als deze `Allow Tagging` is ingeschakeld op het tabblad **Instellingen** . De tags die kunnen worden toegepast, zijn beperkt tot de tags binnen de geselecteerde naamruimtecategorieën. De lijst met naamruimten bevat &#39;Standaardtags&#39; (de standaardnaamruimte) en &#39;Alle tags opnemen&#39;. De standaardwaarde is niet ingeschakeld, hetgeen betekent dat alle naamruimten zijn toegestaan.

* **[!UICONTROL Suggestielimiet]** Voer het aantal tags in dat moet worden weergegeven als suggestie aan het lid dat naar het forum post. De waarde **** -1 betekent geen limiet. De standaardwaarde is 0.

### Tabblad Instellingen sorteren {#sort-settings-tab}

Geef op onder het tabblad **[!UICONTROL Sorteerinstellingen]** op hoe de geposte opmerkingen worden gesorteerd wanneer ze worden weergegeven.

* **[!UICONTROL Sorteren op]** Alle toegestane sorteerselecties controleren: `Newest, Oldest, Last Updated, Most Viewed, Most Active, Most Followed and Most Liked`. Standaard is dit `Newest, Oldest, Last Updated`.

* **[!UICONTROL Als Standaard]** omlaag schuiven instellen om een van de geselecteerde sorteeropties te selecteren die als standaardopties moeten worden weergegeven. Standaard is dit `Newest`.

* **[!UICONTROL Selecteer Tijdopties voor Analytische sortering]** Pull omlaag om een van `All, Last 24 Hours, Last 7 Days, Last 30 Days`deze opties te selecteren. Standaard is dit `All`.

## Ervaring met sitebezoekers {#site-visitor-experience}

### Idea maken {#creating-idea}

Net als bij alle andere communautaire kenmerken kan een bezoeker van de site alleen ideeën lezen en andere meningen bekijken (door opmerkingen en stemmen/houden) als hij niet is aangemeld.

Na aanmelding kan een lid een nieuw idee maken.

![chlimage_1-32](assets/chlimage_1-32.png)

Voordat het idee wordt verzonden, kan het lid een concept opslaan.

Als u de `Save as Draft` knop selecteert, wordt een concept opgeslagen.

![chlimage_1-33](assets/chlimage_1-33.png)

Als u opgeslagen concepten op het `My Drafts` tabblad weergeeft, selecteert u `Read More` om de bewerkingsmodus opnieuw in te schakelen:

![chlimage_1-34](assets/chlimage_1-34.png)

#### Feedback geven {#providing-feedback}

Zodra het idee is gepubliceerd, kunnen andere leden zich aanmelden, het idee ( `Read More`) openen en het idee volgen, en zo het aantal stemmen verhogen en opmerkingen maken.

![chlimage_1-35](assets/chlimage_1-35.png)

### Additional Information {#additional-information}

Meer informatie kunt u vinden op de pagina [Ideatie Essentials](ideation.md) voor ontwikkelaars.

Voor moderatie van geposte onderwerpen en commentaren, zie het [Modereren van Door Gebruiker Gegenereerde Inhoud](moderate-ugc.md).

Zie Door gebruiker gegenereerde inhoud [](tag-ugc.md)labelen voor informatie over het labelen van geposte onderwerpen en opmerkingen.
