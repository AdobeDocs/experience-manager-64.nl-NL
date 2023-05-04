---
title: Ideatiefunctie
seo-title: Ideation Feature
description: De functie Ideatie toevoegen en configureren
seo-description: Adding and configuring the Ideation feature
uuid: b21507da-10c8-4149-9e2c-a4ff5dec582b
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: 7c0a9120-2edb-431b-b460-68398832d5ec
exl-id: 391885f2-e46d-4eb4-9c88-509233505df8
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1003'
ht-degree: 0%

---

# Ideatiefunctie {#ideation-feature}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

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

Als u een `Ideation` van een component aan een pagina op auteurswijze, gebruik componentenbrowser om van `Communities / Ideation` en sleep het naar de gewenste plaats op een pagina.

Voor de nodige informatie gaat u naar [Grondbeginselen van Community-componenten](basics.md).

Wanneer de [vereiste clientbibliotheken](ideation.md#essentials-for-client-side) worden opgenomen, is dit hoe `Ideation`wordt weergegeven:

![chlimage_1-29](assets/chlimage_1-29.png)

## Een idee configureren {#configuring-an-ideation}

Selecteer de geplaatste `Ideation` te openen en de component te selecteren `Configure` wordt het dialoogvenster Bewerken geopend.

![chlimage_1-30](assets/chlimage_1-30.png) ![chlimage_1-31](assets/chlimage_1-31.png)

### Het tabblad Instellingen {#settings-tab}

Onder de **[!UICONTROL Settings]** tabblad, geeft u instellingen voor ideeën en opmerkingen op:

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
Als deze optie is ingeschakeld, kunnen leden labels toevoegen aan hun advertentie (zie **[!UICONTROL Tag field]** ). De optie Standaard is uitgeschakeld.

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
Als deze optie is ingeschakeld, neemt u de volgende functie op voor ideeënposts, waardoor leden kunnen worden [aangemeld](notifications.md) van nieuwe posten. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Email Subscriptions]**
Als deze optie ingeschakeld is, kunnen leden per e-mail op de hoogte worden gesteld van nieuwe berichten ([abonnement](subscriptions.md)). Vereisten `Allow Following` te controleren en [e-mail geconfigureerd](email.md). De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Voting]**
Als deze optie ingeschakeld is, kunt u stemmen over de opmerkingen van een idee. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Display Badges]**
Indien ingeschakeld, verdiende en toegewezen weergave [badges](implementing-scoring.md) met het idee van een lid. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Featured Content]**
als het idee wordt gecontroleerd, kan het worden geïdentificeerd als [aanbevolen inhoud](featured.md). De optie Standaard is uitgeschakeld.

### Tabblad Gebruikersmodernisering {#user-moderation-tab}

Onder de **[!UICONTROL User Moderation]** , geeft u op hoe de geposte ideeën en opmerkingen (door de gebruiker gegenereerde inhoud) worden beheerd. Zie voor meer informatie [Door gebruiker gegenereerde inhoud modereren](moderate-ugc.md).

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

### Tabblad Tagveld {#tag-field-tab}

Onder de **[!UICONTROL Tag field]** , de tags die kunnen worden toegepast, indien toegestaan onder de **[!UICONTROL Settings]** zijn beperkt op basis van de gekozen naamruimten.

* **[!UICONTROL Allowed Namespaces]**
Relevant indien 
`Allow Tagging` wordt gecontroleerd onder de **Instellingen** tab. De tags die kunnen worden toegepast, zijn beperkt tot de tags binnen de geselecteerde naamruimtecategorieën. De lijst met naamruimten bevat &#39;Standaardtags&#39; (de standaardnaamruimte) en &#39;Alle tags opnemen&#39;. De standaardwaarde is niet ingeschakeld, hetgeen betekent dat alle naamruimten zijn toegestaan.

* **[!UICONTROL Suggestion Limit]**
Voer het aantal tags in dat moet worden weergegeven als suggestie aan het lid dat naar het forum post. Een waarde van 
**-** 1 betekent geen limiet. De standaardwaarde is 0.

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

## Ervaring met sitebezoekers {#site-visitor-experience}

### Idea maken {#creating-idea}

Net als bij alle andere communautaire kenmerken kan een bezoeker van de site alleen ideeën lezen en andere meningen bekijken (door opmerkingen en stemmen/houden) als hij niet is aangemeld.

Na aanmelding kan een lid een nieuw idee maken.

![chlimage_1-32](assets/chlimage_1-32.png)

Voordat het idee wordt verzonden, kan het lid een concept opslaan.

Als u `Save as Draft` wordt een concept opgeslagen.

![chlimage_1-33](assets/chlimage_1-33.png)

Bij weergave van opgeslagen concepten in de `My Drafts` tab, selecteert u `Read More` om de bewerkingsmodus opnieuw te activeren:

![chlimage_1-34](assets/chlimage_1-34.png)

#### Feedback geven {#providing-feedback}

Als het idee eenmaal is gepubliceerd, kunnen andere leden zich aanmelden, het idee openen ( `Read More`) en het idee, waardoor het aantal stemmen wordt vergroot en er opmerkingen over worden gemaakt.

![chlimage_1-35](assets/chlimage_1-35.png)

### Aanvullende informatie {#additional-information}

Meer informatie is te vinden op de [Essentiële elementen voor ideeën](ideation.md) pagina voor ontwikkelaars.

Voor moderatie van geposte onderwerpen en commentaren, zie [Door gebruiker gegenereerde inhoud modereren](moderate-ugc.md).

Voor het etiketteren van geposte onderwerpen en commentaren, zie [Door gebruiker gegenereerde inhoud labelen](tag-ugc.md).
