---
title: Functie van forum
seo-title: Functie van forum
description: Hoe te om de forumeigenschap toe te voegen en te vormen
seo-description: Hoe te om de forumeigenschap toe te voegen en te vormen
uuid: ced860ef-6f8a-4df2-acc8-6a48140fca83
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: 3495f983-d71e-4704-be4e-8a42a63f72db
translation-type: tm+mt
source-git-commit: 28948f1f8678512f8fc970a4289cb01cde86c5c2

---


# Functie van forum {#forum-feature}

## Inleiding {#introduction}

De functie Forum biedt een gebied voor ingetekende sitebezoekers (leden van de community) in de publicatieomgeving voor:

* Nieuwe onderwerpen maken
* Onderwerpen weergeven en antwoorden
* Een onderwerp volgen
* Een forum zoeken
* Help de inhoud van het forum te matigen
* Forumonderwerpen van de ene pagina naar de andere verplaatsen

In deze sectie van de documentatie wordt beschreven

* De forumfunctie toevoegen aan een AEM-site
* Configuratie-instellingen voor de `Forum`component

## Een forum toevoegen aan een pagina {#adding-a-forum-to-a-page}

Als u een `Forum` component aan een pagina wilt toevoegen in de ontwerpmodus, gebruikt u de componentbrowser om te zoeken naar

* `Communities / Forum`

En sleep het naar zijn plaats op een pagina waar het forum zou moeten verschijnen.

Ga voor de benodigde informatie naar [Community Components Basics](basics.md).

Wanneer de [vereiste client-side bibliotheken](essentials-forum.md#essentials-for-client-side) worden opgenomen, ziet u de `Forum`component als volgt:

![chlimage_1-60](assets/chlimage_1-60.png)

## Een forum configureren {#configuring-a-forum}

Selecteer de geplaatste `Forum` component die u wilt openen en selecteer het `Configure` pictogram waarmee het dialoogvenster Bewerken wordt geopend.

![chlimage_1-61](assets/chlimage_1-61.png) ![chlimage_1-62](assets/chlimage_1-62.png)

### Het tabblad Instellingen {#settings-tab}

Geef op het tabblad **[!UICONTROL Instellingen]** instellingen op voor onderwerpen en antwoorden:

* **[!UICONTROL Onderwerpen per pagina]** bepalen het aantal onderwerpen/posten dat per pagina wordt weergegeven. De standaardwaarde is 10.

* **[!UICONTROL Gemoderniseerd]** Als deze optie is ingeschakeld, moet het posten van onderwerpen en opmerkingen worden goedgekeurd voordat ze op een publicatiesite worden weergegeven. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Gesloten]** Als deze optie ingeschakeld is, is het forum gesloten voor nieuwe onderwerpen en opmerkingen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL De rijke Redacteur]** van de Tekst als gecontroleerd, onderwerpen en commentaren kunnen met prijsverhoging zijn ingegaan. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Labelen]** toestaan Als deze optie is ingeschakeld, kunnen leden labellabels aan hun post toevoegen (zie tabblad **[!UICONTROL Tagveld]** ). De optie Standaard is uitgeschakeld.

* **[!UICONTROL Bestand uploaden]** toestaan Als deze optie is ingeschakeld, mogen bestandsbijlagen worden toegevoegd aan het onderwerp of de opmerking. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Volgend]** toestaan Indien ingeschakeld, neemt u de volgende functie voor forumfuncties op, waardoor leden op de [hoogte](notifications.md) kunnen worden gesteld van nieuwe posten. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Vastzetten]** toestaan Indien ingeschakeld, kunnen forumonderwerpen boven aan de lijst met onderwerpen worden vastgezet. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Aanbevolen inhoud]** toestaan als deze optie is ingeschakeld, kan het idee worden geïdentificeerd als [aanbevolen inhoud](featured.md). De optie Standaard is uitgeschakeld.

* **[!UICONTROL E-mailabonnementen]** toestaan Als deze optie is ingeschakeld, kunnen leden per e-mail op de hoogte worden gesteld van nieuwe berichten ([abonnement](subscriptions.md)). Moet `Allow Following` worden gecontroleerd en [e-mail wordt gevormd](email.md). De optie Standaard is uitgeschakeld.

* **[!UICONTROL Maximale bestandsgrootte]** alleen relevant als deze `Allow File Uploads` is ingeschakeld. Met dit veld wordt de grootte (in bytes) van een geüpload bestand beperkt. De standaardwaarde is 104857600 (10 MB).

* **[!UICONTROL Alleen toegestane bestandstypen]** relevant als deze `Allow File Uploads` is ingeschakeld. Een door komma&#39;s gescheiden lijst met bestandsextensies met het &quot;punt&quot;-scheidingsteken. Bijvoorbeeld: .jpg, .jpeg, .png, .doc, .docx, .pdf. Als er bestandstypen zijn opgegeven, mogen de niet opgegeven bestandstypen niet worden geüpload. De standaardinstelling is niet opgegeven, zodat alle bestandstypen zijn toegestaan.

* **[!UICONTROL Maximale bestandsgrootte]** van afbeelding alleen relevant koppelen als Uploaden van bestand toestaan is ingeschakeld. Het maximum aantal bytes dat een geüploade afbeeldingsbestand kan hebben. De standaardwaarde is 2097152 (2 MB).

* **[!UICONTROL Reacties]** met verbindingen toestaan Als deze optie is ingeschakeld, kunt u reacties op opmerkingen die naar het onderwerp zijn gepost toestaan. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Gebruikers toestaan opmerkingen en onderwerpen]** te verwijderen Als deze optie is ingeschakeld, kunnen leden de opmerkingen en onderwerpen die ze hebben geplaatst verwijderen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Stemmen]** toestaan Indien ingeschakeld, neemt u de functie Stemmen op met een onderwerp. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Breadcrumbs]** tonen Indien ingeschakeld, blanco overzichten weergeven op onderwerppagina&#39;s. Standaard is ingeschakeld.

* **[!UICONTROL Badges]** weergeven Indien ingeschakeld, verdiende en toegewezen [badges](implementing-scoring.md) bij het blogbericht van een lid weergeven. De optie Standaard is uitgeschakeld.

>[!NOTE]
>
>Het kan nodig zijn om zowel `AllowThreaded Replies` als `Allow users to Delete Comments and Topics` om opmerkingen over een onderwerp mogelijk te maken.

### Tabblad Gebruikersmodernisering {#user-moderation-tab}

Onder het lusje van de Moderatie **[!UICONTROL van de]** Gebruiker, specificeer hoe de geposte onderwerpen en de antwoorden (gebruiker geproduceerde inhoud) worden beheerd. Voor meer informatie, zie het [Modereren van Gebruiker Gegenereerde Inhoud](moderate-ugc.md).

* **[!UICONTROL Posten]** weigeren Als deze optie is ingeschakeld, mogen gematigde leden posten weigeren en voorkomen dat de post op het openbare forum verschijnt. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Sluit/heropen Onderwerpen]** Indien gecontroleerd, kunnen de vertrouwde op lidmoderatoren een onderwerp aan verdere uitgeeft en commentaren sluiten, en kunnen een onderwerp ook heropenen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Onderwerpen]** van de beweging indien gecontroleerd, sta toe publiceert-zijmoderators om onderwerpen te bewegen. Standaard is ingeschakeld.

* **[!UICONTROL Vlagberichten]** Als deze optie is ingeschakeld, kunnen leden onderwerpen of opmerkingen van anderen als ongeschikt markeren. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Lijst]** met redenen voor vlagAls deze optie is ingeschakeld, kunnen leden in een vervolgkeuzelijst kiezen waarom zij een onderwerp of opmerking als ongeschikt aanmerken. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Reden]** voor aangepaste vlag Als dit selectievakje is ingeschakeld, kunnen leden hun eigen reden opgeven om een onderwerp of opmerking als ongeschikt te bestempelen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL De Drempel]** van de modernisering gaat het aantal tijden in een onderwerp of een commentaar moet door leden worden gemarkeerd alvorens de moderatoren op de hoogte worden gebracht. De standaardwaarde is 1 (één keer).

* **[!UICONTROL Laginglimiet]** Voer het aantal keren in dat een onderwerp of opmerking moet worden gemarkeerd voordat het wordt verborgen in de openbare weergave. Indien ingesteld op -1, wordt het gemarkeerde onderwerp of de opmerking nooit verborgen in de openbare weergave. Anders, moet dit aantal groter dan of gelijk aan de Drempel van de Moderatie zijn. De standaardwaarde is 5.

### Tabblad Tagveld {#tag-field-tab}

Onder het tabblad **[!UICONTROL Tagveld]** zijn de tags die kunnen worden toegepast, indien toegestaan op het tabblad **[!UICONTROL Instellingen]** , beperkt op basis van de gekozen naamruimten.

* **[!UICONTROL Toegestane naamruimten]** relevant als deze `Allow Tagging` is ingeschakeld op het tabblad **[!UICONTROL Instellingen]** . De tags die kunnen worden toegepast, zijn beperkt tot de tags binnen de geselecteerde naamruimtecategorieën. De lijst met naamruimten bevat &#39;Standaardtags&#39; (de standaardnaamruimte) en &#39;Alle tags opnemen&#39;. De standaardwaarde is niet ingeschakeld, hetgeen betekent dat alle naamruimten zijn toegestaan.

* **[!UICONTROL Suggestielimiet]** Voer het aantal tags in dat moet worden weergegeven als suggestie aan het lid dat naar het forum post. De standaardwaarde is **-** 1 (geen limieten).

### Tabblad Vertaling {#translation-tab}

Als op het tabblad **[!UICONTROL Vertaling]** vertaling is ingeschakeld voor de site van de gebruikersgemeenschap, kan de vertaling worden ingesteld op het vertalen van het gehele onderwerp of van geselecteerde artikelen.

* **[!UICONTROL Vertaal allen]** indien gecontroleerd, wordt de forumdraad vertaald in de aangewezen taal van de gebruiker. De optie Standaard is uitgeschakeld.

### Tabblad Instellingen sorteren {#sort-settings-tab}

Geef op onder het tabblad **[!UICONTROL Sorteerinstellingen]** op hoe de geposte opmerkingen worden gesorteerd wanneer ze worden weergegeven.

* **[!UICONTROL Sorteren op]** Alle toegestane sorteerselecties controleren: `Newest, Oldest, Last Updated, Most Viewed, Most Active, Most Followed and Most Liked`. Standaard is dit `Newest, Oldest, Last Updated`.

* **[!UICONTROL Als Standaard]** omlaag schuiven instellen om een van de geselecteerde sorteeropties te selecteren die als standaardopties moeten worden weergegeven. Standaard is dit `Newest`.

* **[!UICONTROL Selecteer Tijdopties voor Analytische sortering]** Pull omlaag om een van `All, Last 24 Hours, Last 7 Days, Last 30 Days`deze opties te selecteren. Standaard is dit `All`.

## Additional Information {#additional-information}

Meer informatie kunt u vinden op de pagina [Forum Essentials](essentials-forum.md) voor ontwikkelaars.

Voor moderatie van geposte onderwerpen en commentaren, zie het [Modereren van Door Gebruiker Gegenereerde Inhoud](moderate-ugc.md).

Zie Door gebruiker gegenereerde inhoud [](tag-ugc.md)labelen voor informatie over het labelen van geposte onderwerpen en opmerkingen.

Zie Door gebruiker gegenereerde inhoud [vertalen voor een vertaling van geposte onderwerpen en opmerkingen](translate-ugc.md).
