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
workflow-type: tm+mt
source-wordcount: '958'
ht-degree: 0%

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
* De montages van de configuratie voor `Forum`component

## Een forum toevoegen aan een pagina {#adding-a-forum-to-a-page}

Als u een `Forum`-component in de ontwerpmodus aan een pagina wilt toevoegen, gebruikt u de componentbrowser om te zoeken naar

* `Communities / Forum`

En sleep het naar zijn plaats op een pagina waar het forum zou moeten verschijnen.

Voor noodzakelijke informatie, bezoek [de Grondbeginselen van Componenten van Gemeenschappen](basics.md).

Wanneer de [vereiste client-side bibliotheken](essentials-forum.md#essentials-for-client-side) worden opgenomen, wordt de `Forum`component als volgt weergegeven:

![chlimage_1-60](assets/chlimage_1-60.png)

## Een forum {#configuring-a-forum} configureren

Selecteer de geplaatste `Forum` component en selecteer `Configure` pictogram dat het Edit dialoog opent.

![chlimage_1-61](assets/chlimage_1-61.png) ![chlimage_1-62](assets/chlimage_1-62.png)

### Tabblad Instellingen {#settings-tab}

Geef onder het tabblad **[!UICONTROL Settings]** instellingen op voor onderwerpen en antwoorden:

* **[!UICONTROL Topics Per Page]**
Hiermee definieert u het aantal onderwerpen/posts dat per pagina wordt weergegeven. De standaardwaarde is 10.

* **[!UICONTROL Moderated]**
Als deze optie is ingeschakeld, moet het posten van onderwerpen en opmerkingen worden goedgekeurd voordat ze op een publicatiesite worden weergegeven. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Closed]**
Als deze optie ingeschakeld is, wordt het forum afgesloten met nieuwe onderwerpen en opmerkingen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Rich Text Editor]**
Als deze optie is ingeschakeld, kunnen onderwerpen en opmerkingen worden ingevoerd met een markering. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Tagging]**
Als deze optie is ingeschakeld, kunnen leden labellabels aan hun advertentie toevoegen (zie  **[!UICONTROL Tag field]** tabblad). De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow File Uploads]**
Als deze optie ingeschakeld is, staat u toe dat bestandsbijlagen worden toegevoegd aan het onderwerp of de opmerking. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Following]**
Indien deze optie is ingeschakeld, dient u de volgende functie voor forumposten op te nemen, zodat leden op de hoogte kunnen worden  [](notifications.md) gesteld van nieuwe posten. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Pinning]**
Als deze optie ingeschakeld is, kunnen forumonderwerpen boven aan de lijst met onderwerpen worden vastgezet. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Featured Content]**
als deze optie is ingeschakeld, kan het idee worden geïdentificeerd als  [aanbevolen inhoud](featured.md). De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Email Subscriptions]**
Als deze optie is ingeschakeld, kunnen leden via e-mail op de hoogte worden gesteld van nieuwe berichten ([abonnement](subscriptions.md)). `Allow Following` moet worden gecontroleerd en [e-mail geconfigureerd](email.md). De optie Standaard is uitgeschakeld.

* **[!UICONTROL Max File Size]**
Alleen relevant als 
`Allow File Uploads` is ingeschakeld. Met dit veld wordt de grootte (in bytes) van een geüpload bestand beperkt. De standaardwaarde is 104857600 (10 MB).

* **[!UICONTROL Allowed File Types]**
Alleen relevant als 
`Allow File Uploads` is ingeschakeld. Een door komma&#39;s gescheiden lijst met bestandsextensies met het &quot;punt&quot;-scheidingsteken. Bijvoorbeeld: .jpg, .jpeg, .png, .doc, .docx, .pdf. Als er bestandstypen zijn opgegeven, mogen de niet opgegeven bestandstypen niet worden geüpload. De standaardinstelling is niet opgegeven, zodat alle bestandstypen zijn toegestaan.

* **[!UICONTROL Max Attach Image File Size]**
Alleen relevant als Uploaden van bestand toestaan is ingeschakeld. Het maximum aantal bytes dat een geüploade afbeeldingsbestand kan hebben. De standaardwaarde is 2097152 (2 MB).

* **[!UICONTROL Allow Threaded Replies]**
Als deze optie is ingeschakeld, kunt u reacties op opmerkingen die naar het onderwerp zijn verzonden toestaan. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Users to Delete Comments and Topics]**
Als deze optie is ingeschakeld, kunnen leden de opmerkingen en onderwerpen die ze hebben geplaatst verwijderen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Voting]**
Indien ingeschakeld, neemt u de functie Stemmen op met een onderwerp. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Show Breadcrumbs]**
Indien aangekruist, toon navigatiebroodkruimels op onderwerppagina&#39;s. Standaard is ingeschakeld.

* **[!UICONTROL Display Badges]**
Indien ingeschakeld, verdiende en toegewezen  [](implementing-scoring.md) badges weergeven bij het blogbericht van een lid. De optie Standaard is uitgeschakeld.

>[!NOTE]
>
>Het kan nodig zijn om zowel `AllowThreaded Replies` als `Allow users to Delete Comments and Topics` te controleren om commentaren op een onderwerp toe te laten.

### Tabblad Gebruikersmodernisering {#user-moderation-tab}

Geef onder het tabblad **[!UICONTROL User Moderation]** op hoe de geposte onderwerpen en antwoorden (door de gebruiker gegenereerde inhoud) worden beheerd. Zie [Door gebruiker gegenereerde inhoud modereren](moderate-ugc.md) voor meer informatie.

* **[!UICONTROL Deny Posts]**
Als deze optie wordt ingeschakeld, zullen de verantwoordelijken van de leden hun functie kunnen ontkennen en voorkomen dat de functie op het openbare forum verschijnt. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Close / Reopen Topics]**
Indien gecontroleerd, kunnen de vertrouwde op lidmoderatoren een onderwerp aan verdere uitgeeft en commentaren sluiten, en kunnen een onderwerp ook heropenen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Move Topics]**
Indien gecontroleerd, sta toe publiceert-zijmoderators om onderwerpen te bewegen. Standaard is ingeschakeld.

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

### Tabblad {#tag-field-tab} voor tagveld

Onder het tabblad **[!UICONTROL Tag field]** zijn de tags die kunnen worden toegepast, indien toegestaan onder het tabblad **[!UICONTROL Settings]**, beperkt op basis van de gekozen naamruimten.

* **[!UICONTROL Allowed Namespaces]**
Relevant als  `Allow Tagging` wordt gecontroleerd onder het  **[!UICONTROL Settings]** lusje. De tags die kunnen worden toegepast, zijn beperkt tot de tags binnen de geselecteerde naamruimtecategorieën. De lijst met naamruimten bevat &#39;Standaardtags&#39; (de standaardnaamruimte) en &#39;Alle tags opnemen&#39;. De standaardwaarde is niet ingeschakeld, hetgeen betekent dat alle naamruimten zijn toegestaan.

* **[!UICONTROL Suggestion Limit]**
Voer het aantal tags in dat moet worden weergegeven als suggestie aan het lid dat naar het forum post. Standaard is 
**-** 1 (geen limieten).

### Tabblad Vertaling {#translation-tab}

Als op het tabblad **[!UICONTROL Translation]** vertaling is ingeschakeld voor de site van de gebruikersgemeenschap, kan de vertaling zo worden ingesteld dat het gehele onderwerp of de geselecteerde artikelen worden vertaald.

* **[!UICONTROL Translate All]**
Indien gecontroleerd, wordt de forumdraad vertaald in de aangewezen taal van de gebruiker. De optie Standaard is uitgeschakeld.

### Tabblad Instellingen sorteren {#sort-settings-tab}

Geef onder het tabblad **[!UICONTROL Sort Settings]** op hoe de geposte opmerkingen worden gesorteerd wanneer ze worden weergegeven.

* **[!UICONTROL Sort By]**
Alle toegestane sorteerselecties controleren: 
`Newest, Oldest, Last Updated, Most Viewed, Most Active, Most Followed and Most Liked`. De standaardwaarde is `Newest, Oldest, Last Updated`.

* **[!UICONTROL Set as Default]**
Trek naar beneden om een van de geselecteerde sorteeropties te selecteren die als standaard moeten worden weergegeven. Standaard is 
`Newest`.

* **[!UICONTROL Select Time Options for Analytics Sorting]**
Omlaag trekken om een van de volgende opties te selecteren 
`All, Last 24 Hours, Last 7 Days, Last 30 Days`. De standaardwaarde is `All`.

## Aanvullende informatie {#additional-information}

Meer informatie vindt u op de pagina [Forum Essentials](essentials-forum.md) voor ontwikkelaars.

Zie [Door gebruiker gegenereerde inhoud modereren](moderate-ugc.md) voor de moderatie van geposte onderwerpen en opmerkingen.

Zie [Door gebruiker gegenereerde inhoud labelen](tag-ugc.md) voor het labelen van geposte onderwerpen en opmerkingen.

Zie [Door gebruiker gegenereerde inhoud omzetten](translate-ugc.md) voor een vertaling van geposte onderwerpen en opmerkingen.
