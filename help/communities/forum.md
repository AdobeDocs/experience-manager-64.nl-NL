---
title: Functie van forum
seo-title: Forum Feature
description: Hoe te om de forumeigenschap toe te voegen en te vormen
seo-description: How to add and configure the forum feature
uuid: ced860ef-6f8a-4df2-acc8-6a48140fca83
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: 3495f983-d71e-4704-be4e-8a42a63f72db
exl-id: fa6f28b4-3217-4b6a-b223-506da0ecca9e
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '984'
ht-degree: 0%

---

# Functie van forum {#forum-feature}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

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
* De montages van de configuratie voor de `Forum`component

## Een forum toevoegen aan een pagina {#adding-a-forum-to-a-page}

Als u een `Forum` van een component aan een pagina op auteurswijze, gebruik componentenbrowser om van

* `Communities / Forum`

En sleep het naar zijn plaats op een pagina waar het forum zou moeten verschijnen.

Voor de nodige informatie gaat u naar [Grondbeginselen van Community-componenten](basics.md).

Wanneer de [vereiste clientbibliotheken](essentials-forum.md#essentials-for-client-side) worden opgenomen, is dit hoe `Forum`wordt weergegeven:

![chlimage_1-60](assets/chlimage_1-60.png)

## Een forum configureren {#configuring-a-forum}

Selecteer de geplaatste `Forum` te openen en de component te selecteren `Configure` wordt het dialoogvenster Bewerken geopend.

![chlimage_1-61](assets/chlimage_1-61.png) ![chlimage_1-62](assets/chlimage_1-62.png)

### Het tabblad Instellingen {#settings-tab}

Onder de **[!UICONTROL Settings]** tabblad, geeft u instellingen voor onderwerpen en antwoorden op:

* **[!UICONTROL Topics Per Page]**
Hiermee definieert u het aantal onderwerpen/posts dat per pagina wordt weergegeven. De standaardwaarde is 10.

* **[!UICONTROL Moderated]**
Als deze optie is ingeschakeld, moet het posten van onderwerpen en opmerkingen worden goedgekeurd voordat ze op een publicatiesite worden weergegeven. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Closed]**
Als deze optie ingeschakeld is, wordt het forum afgesloten met nieuwe onderwerpen en opmerkingen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Rich Text Editor]**
Als deze optie is ingeschakeld, kunnen onderwerpen en opmerkingen worden ingevoerd met een markering. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Tagging]**
Als deze optie is ingeschakeld, kunnen leden labels toevoegen aan hun advertentie (zie **[!UICONTROL Tag field]** ). De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow File Uploads]**
Als deze optie ingeschakeld is, staat u toe dat bestandsbijlagen worden toegevoegd aan het onderwerp of de opmerking. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Following]**
Indien deze optie is ingeschakeld, neemt u de volgende functie op voor forumposten, waardoor leden kunnen worden [aangemeld](notifications.md) van nieuwe posten. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Pinning]**
Als deze optie ingeschakeld is, kunnen forumonderwerpen boven aan de lijst met onderwerpen worden vastgezet. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Featured Content]**
als het idee wordt gecontroleerd, kan het worden geïdentificeerd als [aanbevolen inhoud](featured.md). De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Email Subscriptions]**
Als deze optie ingeschakeld is, kunnen leden per e-mail op de hoogte worden gesteld van nieuwe berichten ([abonnement](subscriptions.md)). Vereisten `Allow Following` te controleren en [e-mail geconfigureerd](email.md). De optie Standaard is uitgeschakeld.

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
Indien ingeschakeld, verdiende en toegewezen weergave [badges](implementing-scoring.md) met het blogbericht van een lid. De optie Standaard is uitgeschakeld.

>[!NOTE]
>
>Het kan nodig zijn om `AllowThreaded Replies` en `Allow users to Delete Comments and Topics` om commentaar op een onderwerp toe te laten.

### Tabblad Gebruikersmodernisering {#user-moderation-tab}

Onder de **[!UICONTROL User Moderation]** tabblad, geeft u op hoe de geposte onderwerpen en antwoorden (door de gebruiker gegenereerde inhoud) worden beheerd. Zie voor meer informatie [Door gebruiker gegenereerde inhoud modereren](moderate-ugc.md).

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

### Tabblad Tagveld {#tag-field-tab}

Onder de **[!UICONTROL Tag field]** , de tags die kunnen worden toegepast, indien toegestaan onder de **[!UICONTROL Settings]** zijn beperkt op basis van de gekozen naamruimten.

* **[!UICONTROL Allowed Namespaces]**
Relevant indien `Allow Tagging` wordt gecontroleerd onder de **[!UICONTROL Settings]** tab. De tags die kunnen worden toegepast, zijn beperkt tot de tags binnen de geselecteerde naamruimtecategorieën. De lijst met naamruimten bevat &#39;Standaardtags&#39; (de standaardnaamruimte) en &#39;Alle tags opnemen&#39;. De standaardwaarde is niet ingeschakeld, hetgeen betekent dat alle naamruimten zijn toegestaan.

* **[!UICONTROL Suggestion Limit]**
Voer het aantal tags in dat moet worden weergegeven als suggestie aan het lid dat naar het forum post. Standaard is 
**-** 1 (geen limieten).

### Tabblad Vertaling {#translation-tab}

Onder de **[!UICONTROL Translation]** tab, als vertaling voor de communautaire plaats wordt toegelaten, kan de vertaling worden geplaatst om het volledige onderwerp of geselecteerde posten te vertalen.

* **[!UICONTROL Translate All]**
Indien gecontroleerd, wordt de forumdraad vertaald in de aangewezen taal van de gebruiker. De optie Standaard is uitgeschakeld.

### Tabblad Instellingen sorteren {#sort-settings-tab}

Onder de **[!UICONTROL Sort Settings]** , geeft u op hoe de geposte opmerkingen worden gesorteerd wanneer deze worden weergegeven.

* **[!UICONTROL Sort By]**
Alle toegestane sorteerselecties controleren: 
`Newest, Oldest, Last Updated, Most Viewed, Most Active, Most Followed and Most Liked`. Standaard is `Newest, Oldest, Last Updated`.

* **[!UICONTROL Set as Default]**
Trek naar beneden om een van de geselecteerde sorteeropties te selecteren die als standaard moeten worden weergegeven. Standaard is 
`Newest`.

* **[!UICONTROL Select Time Options for Analytics Sorting]**
Omlaag trekken om een van de volgende opties te selecteren 
`All, Last 24 Hours, Last 7 Days, Last 30 Days`. Standaard is `All`.

## Aanvullende informatie {#additional-information}

Meer informatie is te vinden op de [Essentiële elementen van forum](essentials-forum.md) pagina voor ontwikkelaars.

Voor moderatie van geposte onderwerpen en commentaren, zie [Door gebruiker gegenereerde inhoud modereren](moderate-ugc.md).

Voor het etiketteren van geposte onderwerpen en commentaren, zie [Door gebruiker gegenereerde inhoud labelen](tag-ugc.md).

Voor een vertaling van geposte onderwerpen en opmerkingen raadpleegt u [Door gebruiker gegenereerde inhoud vertalen](translate-ugc.md).
