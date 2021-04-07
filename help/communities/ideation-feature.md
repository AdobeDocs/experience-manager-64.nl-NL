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
exl-id: 391885f2-e46d-4eb4-9c88-509233505df8
translation-type: tm+mt
source-git-commit: bd94d3949f0117aa3e1c9f0e84f7293a5d6b03b4
workflow-type: tm+mt
source-wordcount: '975'
ht-degree: 0%

---

# Ideeigenschap {#ideation-feature}

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

Als u een `Ideation`-component in de ontwerpmodus aan een pagina wilt toevoegen, gebruikt u de componentbrowser om `Communities / Ideation` te zoeken en deze naar de juiste positie op een pagina te slepen.

Voor noodzakelijke informatie, bezoek [de Grondbeginselen van Componenten van Gemeenschappen](basics.md).

Wanneer de [vereiste client-side bibliotheken](ideation.md#essentials-for-client-side) worden opgenomen, wordt de `Ideation`component als volgt weergegeven:

![chlimage_1-29](assets/chlimage_1-29.png)

## Een idee {#configuring-an-ideation} configureren

Selecteer de geplaatste `Ideation` component en selecteer `Configure` pictogram dat het Edit dialoog opent.

![chlimage_1-30](assets/chlimage_1-30.png) ![chlimage_1-31](assets/chlimage_1-31.png)

### Tabblad Instellingen {#settings-tab}

Geef onder het tabblad **[!UICONTROL Settings]** instellingen voor ideeën en opmerkingen op:

* **[!UICONTROL Ideation Title]**
De weergavetitel voor het idee. Standaard is 
`Ideation`.

* **[!UICONTROL Ideation Description]**
Een beschrijving die als ondertitel voor het idee moet worden weergegeven. Standaard is geen beschrijving.

* **[!UICONTROL Topics Per Page]**
Hiermee definieert u het aantal ideeën/posts dat per pagina wordt weergegeven. De standaardwaarde is 10.

* **[!UICONTROL Moderated]**
Als deze optie is ingeschakeld, moet het posten van ideeën en opmerkingen worden goedgekeurd voordat ze op een publicatiesite worden weergegeven. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Closed]**
Als het wordt gecontroleerd, is het ideatieforum gesloten voor nieuwe ideeën en commentaren. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Rich Text Editor]**
Als deze optie is ingeschakeld, kunnen ideeën en opmerkingen worden ingevoerd met een markering. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Tagging]**
Als deze optie is ingeschakeld, kunnen leden labellabels aan hun advertentie toevoegen (zie  **[!UICONTROL Tag field]** tabblad). De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow File Uploads]**
Als deze optie is ingeschakeld, kunt u bestandsbijlagen toevoegen aan het idee of de opmerking. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Max File Size]**
Alleen relevant als 
`Allow File Uploads` is ingeschakeld. Met dit veld wordt de grootte (in bytes) van een geüpload bestand beperkt. De standaardwaarde is 104857600 (10 MB).

* **[!UICONTROL Allowed File Types]**
Alleen relevant als 
`Allow File Uploads` is ingeschakeld. Een door komma&#39;s gescheiden lijst met bestandsextensies met het &quot;punt&quot;-scheidingsteken. Bijvoorbeeld: .jpg, .jpeg, .png, .doc, .docx, .pdf. Als er bestandstypen zijn opgegeven, mogen de niet opgegeven bestandstypen niet worden geüpload. De standaardinstelling is niet opgegeven, zodat alle bestandstypen zijn toegestaan.

* **[!UICONTROL Max Attach Image File Size]**
Alleen relevant als Uploaden van bestand toestaan is ingeschakeld. Het maximum aantal bytes dat een geüploade afbeeldingsbestand kan hebben. De standaardwaarde is 2097152 (2 MB).

* **[!UICONTROL Allow Replies]**
Als deze optie is ingeschakeld, kunt u reacties op opmerkingen op het idee toestaan. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Users to Delete Comments and Topics]**
Als deze optie is ingeschakeld, kunnen leden de opmerkingen en ideeën die ze hebben geplaatst verwijderen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Following]**
Als deze optie is ingeschakeld, neemt u de volgende functie op voor ideeënposts, waardoor leden op de hoogte kunnen worden  [](notifications.md) gesteld van nieuwe posten. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Email Subscriptions]**
Als deze optie is ingeschakeld, kunnen leden via e-mail op de hoogte worden gesteld van nieuwe berichten ([abonnement](subscriptions.md)). `Allow Following` moet worden gecontroleerd en [e-mail geconfigureerd](email.md). De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Voting]**
Als deze optie ingeschakeld is, kunt u stemmen over de opmerkingen van een idee. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Display Badges]**
Als deze optie is ingeschakeld, worden verdiende en toegewezen  [](implementing-scoring.md) badges weergegeven bij het idee van een lid. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Featured Content]**
als deze optie is ingeschakeld, kan het idee worden geïdentificeerd als  [aanbevolen inhoud](featured.md). De optie Standaard is uitgeschakeld.

### Tabblad Gebruikersmodernisering {#user-moderation-tab}

Geef onder het tabblad **[!UICONTROL User Moderation]** op hoe de geposte ideeën en opmerkingen (door de gebruiker gegenereerde inhoud) worden beheerd. Zie [Door gebruiker gegenereerde inhoud modereren](moderate-ugc.md) voor meer informatie.

* **[!UICONTROL Deny Posts]**
Als deze optie wordt ingeschakeld, zullen de verantwoordelijken van de leden hun functie kunnen ontkennen en voorkomen dat de functie op het openbare forum verschijnt. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Close / Reopen Topics]**
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

### Tabblad {#tag-field-tab} voor tagveld

Onder het tabblad **[!UICONTROL Tag field]** zijn de tags die kunnen worden toegepast, indien toegestaan onder het tabblad **[!UICONTROL Settings]**, beperkt op basis van de gekozen naamruimten.

* **[!UICONTROL Allowed Namespaces]**
Relevant indien 
`Allow Tagging` wordt gecontroleerd onder de  **** instellingstab. De tags die kunnen worden toegepast, zijn beperkt tot de tags binnen de geselecteerde naamruimtecategorieën. De lijst met naamruimten bevat &#39;Standaardtags&#39; (de standaardnaamruimte) en &#39;Alle tags opnemen&#39;. De standaardwaarde is niet ingeschakeld, hetgeen betekent dat alle naamruimten zijn toegestaan.

* **[!UICONTROL Suggestion Limit]**
Voer het aantal tags in dat moet worden weergegeven als suggestie aan het lid dat naar het forum post. Een waarde van 
**-** 1 betekent geen limiet. De standaardwaarde is 0.

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

## Ervaring {#site-visitor-experience} voor bezoekers van site

### Ideaal maken {#creating-idea}

Net als bij alle andere communautaire kenmerken kan een bezoeker van de site alleen ideeën lezen en andere meningen bekijken (door opmerkingen en stemmen/houden) als hij niet is aangemeld.

Na aanmelding kan een lid een nieuw idee maken.

![chlimage_1-32](assets/chlimage_1-32.png)

Voordat het idee wordt verzonden, kan het lid een concept opslaan.

Als u de knop `Save as Draft` selecteert, wordt een concept opgeslagen.

![chlimage_1-33](assets/chlimage_1-33.png)

Als u opgeslagen concepten weergeeft op het tabblad `My Drafts`, selecteert u `Read More` om de bewerkingsmodus opnieuw in te schakelen:

![chlimage_1-34](assets/chlimage_1-34.png)

#### Feedback geven {#providing-feedback}

Als het idee eenmaal is gepubliceerd, kunnen andere leden zich aanmelden, het idee openen ( `Read More`) en het idee zo weergeven, waardoor het aantal stemmen wordt vergroot en opmerkingen worden gemaakt.

![chlimage_1-35](assets/chlimage_1-35.png)

### Aanvullende informatie {#additional-information}

Meer informatie vindt u op de pagina [Essentiële elementen voor ideeën](ideation.md) voor ontwikkelaars.

Zie [Door gebruiker gegenereerde inhoud modereren](moderate-ugc.md) voor de moderatie van geposte onderwerpen en opmerkingen.

Zie [Door gebruiker gegenereerde inhoud labelen](tag-ugc.md) voor het labelen van geposte onderwerpen en opmerkingen.
