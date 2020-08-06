---
title: Functie Vragen en antwoorden op forum
seo-title: Functie Vragen en antwoorden op forum
description: De functie voor het QnA-forum toevoegen aan een pagina
seo-description: De functie voor het QnA-forum toevoegen aan een pagina
uuid: 006c0bf0-c230-4890-8080-65651f4b4dac
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: bbbe32bb-9d97-461e-822f-a7ddc6c9f9ef
translation-type: tm+mt
source-git-commit: 5ddbcb2addff2d6e3a3e9d7e100a6d9ba89fdd60
workflow-type: tm+mt
source-wordcount: '1119'
ht-degree: 0%

---


# Functie Vragen en antwoorden op forum {#q-a-forum-feature}

## Inleiding {#introduction}

De functie van het QnA-forum (vragen en antwoorden) biedt leden van de gemeenschap de mogelijkheid vragen te stellen en te beantwoorden:

* Nieuwe vragen maken
* Inline-afbeeldingen (met ondersteuning voor slepen en neerzetten)
* Vragen weergeven en beantwoorden
* Zoeken naar een vraag
* De QnA-inhoud helpen matigen
* Beste antwoorden identificeren
* QnA-vragen van de ene pagina naar de andere verplaatsen

In deze sectie van de documentatie wordt beschreven

* De functie voor het QnA-forum toevoegen aan een AEM-site
* Configuratie-instellingen voor de `QnA`component

## Een forum voor vragen en antwoorden toevoegen aan een pagina {#adding-a-q-a-forum-to-a-page}

Om een `QnA` component aan een pagina op auteurswijze toe te voegen, gebruik componentenbrowser om van de plaats de plaats te bepalen `Communities / QnA` en het te slepen op een pagina waar het forum QnA zou moeten verschijnen.

Ga voor de benodigde informatie naar [Community Components Basics](basics.md).

Wanneer de [vereiste client-side bibliotheken](qna-essentials.md#essentials-for-client-side) worden opgenomen, wordt de `QnA` component als volgt weergegeven:

![chlimage_1-280](assets/chlimage_1-280.png)

### QnA configureren {#configuring-qna}

Selecteer de geplaatste `QnA` component die u wilt openen en selecteer het `Configure` pictogram waarmee het dialoogvenster Bewerken wordt geopend.

![chlimage_1-281](assets/chlimage_1-281.png) ![chlimage_1-282](assets/chlimage_1-282.png)

#### Het tabblad Instellingen {#settings-tab}

Geef op het **[!UICONTROL Settings]** tabblad instellingen op voor onderwerpen (vragen) en antwoorden (antwoorden):

* **[!UICONTROL Topics Per Page]**
Hiermee definieert u het aantal vragen/berichten dat per pagina wordt weergegeven. De standaardwaarde is 10.

* **[!UICONTROL Moderated]**
Als deze optie is ingeschakeld, moet het posten van onderwerpen en opmerkingen worden goedgekeurd voordat ze op een publicatiesite worden weergegeven. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Closed]**
Als het forum wordt gecontroleerd, is het gesloten voor nieuwe vragen en commentaren. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Rich Text Editor]**
Als deze optie is ingeschakeld, kunnen onderwerpen en opmerkingen worden ingevoerd met een markering. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Tagging]**
Als deze optie is ingeschakeld, kunnen leden labels aan hun advertentie toevoegen (zie **[!UICONTROL Tag field]** tabblad). De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow File Uploads]**
Als deze optie is ingeschakeld, kunt u bestandsbijlagen toevoegen aan de vraag of opmerking. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Max File Size]**
Alleen relevant als 
`Allow File Uploads` is ingeschakeld. Met dit veld wordt de grootte (in bytes) van een geüpload bestand beperkt. De standaardwaarde is 104857600 (10 MB).

* **[!UICONTROL Allowed File Types]**
Alleen relevant als 
`Allow File Uploads` is ingeschakeld. Een door komma&#39;s gescheiden lijst met bestandsextensies met het &quot;punt&quot;-scheidingsteken. Bijvoorbeeld: .jpg, .jpeg, .png, .doc, .docx, .pdf. Als er bestandstypen zijn opgegeven, mogen de niet opgegeven bestandstypen niet worden geüpload. De standaardinstelling is niet opgegeven, zodat alle bestandstypen zijn toegestaan.

* **[!UICONTROL Max Attach Image File Size]**
Alleen relevant als Uploaden van bestand toestaan is ingeschakeld. Het maximum aantal bytes dat een geüploade afbeeldingsbestand kan hebben. De standaardwaarde is 2097152 (2 MB).

* **[!UICONTROL Allow Following]**
Indien deze optie is ingeschakeld, dient u de volgende functie voor forumposten op te nemen, waardoor leden op de [hoogte kunnen worden gebracht](notifications.md) van nieuwe posten. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Pinning]**
Als deze optie ingeschakeld is, kunnen forumonderwerpen boven aan de lijst met onderwerpen worden vastgezet. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Email Subscriptions]**
Als deze optie is ingeschakeld, kunnen leden via e-mail op de hoogte worden gesteld van nieuwe berichten ([abonnement](subscriptions.md)). Moet `Allow Following` worden gecontroleerd en [e-mail wordt gevormd](email.md). De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Replies]**
Als deze optie is ingeschakeld, kunt u reacties op opmerkingen op de vraag toestaan. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Users to Delete Comments and Topics]**
Als deze optie is ingeschakeld, kunnen leden de opmerkingen en vragen die ze hebben geplaatst verwijderen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Voting]**
Als deze optie is ingeschakeld, voegt u de functie Stemmen toe aan een vraag. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Move Selected Answer To The Top]**
Als deze optie ingeschakeld is, wordt een eerste weergegeven antwoord geselecteerd. Standaard is ingeschakeld.

* **[!UICONTROL Display Badges]**
Indien ingeschakeld, verdiende en toegewezen [badges](implementing-scoring.md) bij het blogbericht van een lid weergeven. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Featured Content]**
als deze optie is ingeschakeld, kan het idee worden geïdentificeerd als [aanbevolen inhoud](featured.md). De optie Standaard is uitgeschakeld.

#### Tabblad Gebruikersmodernisering {#user-moderation-tab}

Geef onder het **[!UICONTROL User Moderation]** tabblad op hoe de geposte onderwerpen (vragen) en antwoorden (door de gebruiker gegenereerde inhoud) worden beheerd. Voor meer informatie, zie het [Modereren van Gebruiker Gegenereerde Inhoud](moderate-ugc.md).

* **[!UICONTROL Deny Answers]**
Als deze optie ingeschakeld is, zullen vertrouwde moderatoren van leden geposte antwoorden kunnen weigeren en voorkomen dat het antwoord verschijnt op het openbare forum met vragen en antwoorden. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Close / Reopen Topics]**
Als deze optie ingeschakeld is, kunnen vertrouwde moderatoren van leden een vraag (onderwerp) sluiten om verdere bewerkingen en antwoorden uit te voeren en kunnen ze ook een vraag opnieuw openen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Move Topics]**
Als deze optie ingeschakeld is, stelt u moderatoren aan de publiczijde in staat vragen te verplaatsen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Flag Posts]**
Als deze optie is ingeschakeld, kunnen leden de vragen of antwoorden van anderen als ongeschikt markeren. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Flag Reason List]**
Als deze optie is ingeschakeld, kunnen leden in een vervolgkeuzelijst kiezen waarom een vraag of antwoord onjuist is. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Custom Flag Reason]**
Als deze optie is ingeschakeld, kunnen leden hun eigen reden opgeven om een vraag of antwoord als ongeschikt te bestempelen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Moderation Threshold]**
Voer het aantal keren in dat een vraag of antwoord moet worden gemarkeerd door leden voordat moderatoren op de hoogte worden gesteld. De standaardwaarde is 1 (één keer).

* **[!UICONTROL Flagging Limit]**
Voer het aantal keren in dat een vraag of antwoord moet worden gemarkeerd voordat deze wordt verborgen in de openbare weergave. Indien ingesteld op -1, wordt de gemarkeerde vraag of het gemarkeerde antwoord nooit verborgen voor de openbare weergave. Anders, moet dit aantal groter dan of gelijk aan de Drempel van de Moderatie zijn. De standaardwaarde is 5.

#### Tabblad Tagveld {#tag-field-tab}

Onder het **[!UICONTROL Tag field]** tabblad zijn de tags die kunnen worden toegepast, indien toegestaan onder het **[!UICONTROL Settings]** tabblad, beperkt op basis van de gekozen naamruimten.

* **[!UICONTROL Allowed Namespaces]**
Relevant indien 
`Allow Tagging` is ingeschakeld onder het tabblad **Instellingen** . De tags die kunnen worden toegepast, zijn beperkt tot de tags binnen de geselecteerde naamruimtecategorieën. De lijst met naamruimten bevat &#39;Standaardtags&#39; (de standaardnaamruimte) en &#39;Alle tags opnemen&#39;. De standaardwaarde is niet ingeschakeld, hetgeen betekent dat alle naamruimten zijn toegestaan.

* **[!UICONTROL Suggestion Limit]**
Voer het aantal tags in dat moet worden weergegeven als suggestie aan het lid dat naar het forum post. Een waarde van 
`-1` betekent geen limieten. De standaardwaarde is 0.

#### Tabblad Instellingen sorteren {#sort-settings-tab}

Geef onder het **[!UICONTROL Sort Settings]** tabblad op hoe de geposte opmerkingen worden gesorteerd wanneer ze worden weergegeven.

* **[!UICONTROL Sort By]**
Alle toegestane sorteerselecties controleren: 
`Newest, Oldest, Last Updated, Most Viewed, Most Active, Most Followed and Most Liked`. Standaard is dit `Newest, Oldest, Last Updated`.

* **[!UICONTROL Set as Default]**
Trek naar beneden om een van de geselecteerde sorteeropties te selecteren die als standaard moeten worden weergegeven. Standaard is 
`Newest`.

* **[!UICONTROL Select Time Options for Analytics Sorting]**
Omlaag trekken om een van de volgende opties te selecteren 
`All, Last 24 Hours, Last 7 Days, Last 30 Days`. Standaard is dit `All`.

## Ervaring met sitebezoekers {#site-visitor-experience}

### Antwoorden identificeren {#identifying-answers}

Eén antwoord kan met de `Select Answer` knop worden gemarkeerd als correct of nuttig. Als een vraag is gemarkeerd als Beantwoord, kan een ander antwoord pas worden geselecteerd als de eerste vraag is uitgeschakeld met de `Unmark Chosen Answer`knop.

Als deze optie eenmaal is geselecteerd als een handig antwoord, is de selectie mogelijk opgeheven met de `Unmark Chosen Answer` knop.

Zodra een antwoord als levensvatbaar antwoord wordt geselecteerd, een aanwijzing dat de vraag naast het vraagonderwerp op de belangrijkste pagina QnA `Answered`wordt getoond.

### Moderatoren en beheerders {#moderators-and-administrators}

Wanneer de ondertekende binnen gebruiker moderator of beheerdervoorrechten heeft, kunnen zij de matigingstaken uitvoeren die door de configuratie van de component worden toegestaan, ongeacht wie de vraag of het antwoord authored.

Ze hebben ook de mogelijkheid om antwoorden te identificeren.

### Leden {#members}

Wanneer de bezoeker van de site zich heeft aangemeld, kunnen deze, afhankelijk van de configuratie

* Nieuwe vraag verzenden
* Door hen geschreven vragen bewerken of verwijderen
* Kan ook vragen of antwoorden van anderen markeren
* Kan antwoorden identificeren voor vragen die ze hebben geschreven

### Anoniem {#anonymous}

Sitebezoekers die niet zijn aangemeld, kunnen alleen geposte vragen en antwoorden lezen, deze vertalen als ze hiervoor ondersteuning krijgen, maar mogen geen vraag of antwoord toevoegen en de berichten van anderen niet markeren.

## Additional Information {#additional-information}

Meer informatie kan op de pagina van de Hoofdzaak [QnA voor ontwikkelaars](qna-essentials.md) worden gevonden.

Voor moderatie van geposte onderwerpen en commentaren, zie het [Modereren van Door Gebruiker Gegenereerde Inhoud](moderate-ugc.md).

Zie Door gebruiker gegenereerde inhoud [](tag-ugc.md)labelen voor informatie over het labelen van geposte onderwerpen en opmerkingen.
