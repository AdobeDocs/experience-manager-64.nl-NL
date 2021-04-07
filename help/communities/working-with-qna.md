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
exl-id: af16f4df-ed8e-40e4-b117-3d612e122947
translation-type: tm+mt
source-git-commit: bd94d3949f0117aa3e1c9f0e84f7293a5d6b03b4
workflow-type: tm+mt
source-wordcount: '1119'
ht-degree: 0%

---

# Functie Vragen en antwoorden forum {#q-a-forum-feature}

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
* De montages van de configuratie voor `QnA`component

## Een forum voor vragen en antwoorden toevoegen aan een pagina {#adding-a-q-a-forum-to-a-page}

Als u een component `QnA` in de modus Schrijver aan een pagina wilt toevoegen, gebruikt u de componentbrowser om `Communities / QnA` te zoeken en deze naar de juiste plaats op een pagina te slepen waar het forum QnA moet worden weergegeven.

Voor noodzakelijke informatie, bezoek [de Grondbeginselen van Componenten van Gemeenschappen](basics.md).

Wanneer de [vereiste client-side bibliotheken](qna-essentials.md#essentials-for-client-side) worden opgenomen, wordt de `QnA`-component op deze manier weergegeven:

![chlimage_1-280](assets/chlimage_1-280.png)

### QnA {#configuring-qna} configureren

Selecteer de geplaatste `QnA` component en selecteer `Configure` pictogram dat het Edit dialoog opent.

![chlimage_1-281](assets/chlimage_1-281.png) ![chlimage_1-282](assets/chlimage_1-282.png)

#### Tabblad Instellingen {#settings-tab}

Geef onder het tabblad **[!UICONTROL Settings]** instellingen op voor onderwerpen (vragen) en antwoorden (antwoorden):

* **[!UICONTROL Topics Per Page]**
Hiermee definieert u het aantal vragen/berichten dat per pagina wordt weergegeven. De standaardwaarde is 10.

* **[!UICONTROL Moderated]**
Als deze optie is ingeschakeld, moet het posten van onderwerpen en opmerkingen worden goedgekeurd voordat ze op een publicatiesite worden weergegeven. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Closed]**
Als het forum wordt gecontroleerd, is het gesloten voor nieuwe vragen en commentaren. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Rich Text Editor]**
Als deze optie is ingeschakeld, kunnen onderwerpen en opmerkingen worden ingevoerd met een markering. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Tagging]**
Als deze optie is ingeschakeld, kunnen leden labellabels aan hun advertentie toevoegen (zie  **[!UICONTROL Tag field]** tabblad). De optie Standaard is uitgeschakeld.

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
Indien deze optie is ingeschakeld, dient u de volgende functie voor forumposten op te nemen, zodat leden op de hoogte kunnen worden  [](notifications.md) gesteld van nieuwe posten. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Pinning]**
Als deze optie ingeschakeld is, kunnen forumonderwerpen boven aan de lijst met onderwerpen worden vastgezet. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Email Subscriptions]**
Als deze optie is ingeschakeld, kunnen leden via e-mail op de hoogte worden gesteld van nieuwe berichten ([abonnement](subscriptions.md)). `Allow Following` moet worden gecontroleerd en [e-mail geconfigureerd](email.md). De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Replies]**
Als deze optie is ingeschakeld, kunt u reacties op opmerkingen op de vraag toestaan. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Users to Delete Comments and Topics]**
Als deze optie is ingeschakeld, kunnen leden de opmerkingen en vragen die ze hebben geplaatst verwijderen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Voting]**
Als deze optie is ingeschakeld, voegt u de functie Stemmen toe aan een vraag. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Move Selected Answer To The Top]**
Als deze optie ingeschakeld is, wordt een eerste weergegeven antwoord geselecteerd. Standaard is ingeschakeld.

* **[!UICONTROL Display Badges]**
Indien ingeschakeld, verdiende en toegewezen  [](implementing-scoring.md) badges weergeven bij het blogbericht van een lid. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Featured Content]**
als deze optie is ingeschakeld, kan het idee worden geïdentificeerd als  [aanbevolen inhoud](featured.md). De optie Standaard is uitgeschakeld.

#### Tabblad Gebruikersmodernisering {#user-moderation-tab}

Geef onder het tabblad **[!UICONTROL User Moderation]** op hoe de geposte onderwerpen (vragen) en antwoorden (door de gebruiker gegenereerde inhoud) worden beheerd. Zie [Door gebruiker gegenereerde inhoud modereren](moderate-ugc.md) voor meer informatie.

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

#### Tabblad {#tag-field-tab} voor tagveld

Onder het tabblad **[!UICONTROL Tag field]** zijn de tags die kunnen worden toegepast, indien toegestaan onder het tabblad **[!UICONTROL Settings]**, beperkt op basis van de gekozen naamruimten.

* **[!UICONTROL Allowed Namespaces]**
Relevant indien 
`Allow Tagging` wordt gecontroleerd onder de  **** instellingstab. De tags die kunnen worden toegepast, zijn beperkt tot de tags binnen de geselecteerde naamruimtecategorieën. De lijst met naamruimten bevat &#39;Standaardtags&#39; (de standaardnaamruimte) en &#39;Alle tags opnemen&#39;. De standaardwaarde is niet ingeschakeld, hetgeen betekent dat alle naamruimten zijn toegestaan.

* **[!UICONTROL Suggestion Limit]**
Voer het aantal tags in dat moet worden weergegeven als suggestie aan het lid dat naar het forum post. Een waarde van 
`-1` betekent geen limieten. De standaardwaarde is 0.

#### Tabblad Instellingen sorteren {#sort-settings-tab}

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

### Beantwoorden {#identifying-answers} identificeren

Één antwoord kan als correct of nuttig antwoord worden gemerkt gebruikend `Select Answer` knoop. Als een vraag is gemarkeerd als Beantwoord, kan een ander antwoord pas worden geselecteerd als de eerste vraag is uitgeschakeld met de knop `Unmark Chosen Answer`.

Als deze optie eenmaal is geselecteerd als een handig antwoord, is de selectie mogelijk ongedaan gemaakt met de knop `Unmark Chosen Answer`.

Zodra een antwoord als levensvatbaar antwoord wordt geselecteerd, wordt een aanwijzing dat de vraag `Answered`is getoond naast het vraagonderwerp op de belangrijkste pagina QnA.

### Moderatoren en beheerders {#moderators-and-administrators}

Wanneer de ondertekende binnen gebruiker moderator of beheerdervoorrechten heeft, kunnen zij de matigingstaken uitvoeren die door de configuratie van de component worden toegestaan, ongeacht wie de vraag of het antwoord authored.

Ze hebben ook de mogelijkheid om antwoorden te identificeren.

### Leden {#members}

Wanneer de bezoeker van de site zich heeft aangemeld, kunnen deze, afhankelijk van de configuratie

* Nieuwe vraag verzenden
* Door hen geschreven vragen bewerken of verwijderen
* Kan ook vragen of antwoorden van anderen markeren
* Kan antwoorden identificeren voor vragen die ze hebben geschreven

### Anonieme {#anonymous}

Sitebezoekers die niet zijn aangemeld, kunnen alleen geposte vragen en antwoorden lezen, deze vertalen als ze hiervoor ondersteuning krijgen, maar mogen geen vraag of antwoord toevoegen en de berichten van anderen niet markeren.

## Aanvullende informatie {#additional-information}

Meer informatie vindt u op de pagina [QnA Essentials](qna-essentials.md) voor ontwikkelaars.

Zie [Door gebruiker gegenereerde inhoud modereren](moderate-ugc.md) voor de moderatie van geposte onderwerpen en opmerkingen.

Zie [Door gebruiker gegenereerde inhoud labelen](tag-ugc.md) voor het labelen van geposte onderwerpen en opmerkingen.
