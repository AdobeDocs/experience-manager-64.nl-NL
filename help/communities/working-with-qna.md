---
title: Functie Vragen en antwoorden op forum
seo-title: Q&A Forum Feature
description: De functie voor het QnA-forum toevoegen aan een pagina
seo-description: Adding the QnA forum feature to a page
uuid: 006c0bf0-c230-4890-8080-65651f4b4dac
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: bbbe32bb-9d97-461e-822f-a7ddc6c9f9ef
exl-id: af16f4df-ed8e-40e4-b117-3d612e122947
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1143'
ht-degree: 0%

---

# Functie Vragen en antwoorden op forum {#q-a-forum-feature}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

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
* De montages van de configuratie voor de `QnA`component

## Een forum voor vragen en antwoorden toevoegen aan een pagina {#adding-a-q-a-forum-to-a-page}

Als u een `QnA` van een component aan een pagina op auteurswijze, gebruik componentenbrowser om van `Communities / QnA` en sleep het naar zijn plaats op een pagina waar het forum QnA zou moeten verschijnen.

Voor de nodige informatie gaat u naar [Grondbeginselen van Community-componenten](basics.md).

Wanneer de [vereiste clientbibliotheken](qna-essentials.md#essentials-for-client-side) worden opgenomen, is dit hoe `QnA` wordt weergegeven:

![chlimage_1-280](assets/chlimage_1-280.png)

### QnA configureren {#configuring-qna}

Selecteer de geplaatste `QnA` te openen en de component te selecteren `Configure` wordt het dialoogvenster Bewerken geopend.

![chlimage_1-281](assets/chlimage_1-281.png) ![chlimage_1-282](assets/chlimage_1-282.png)

#### Het tabblad Instellingen {#settings-tab}

Onder de **[!UICONTROL Settings]** tabblad, geeft u instellingen op voor onderwerpen (vragen) en antwoorden (antwoorden):

* **[!UICONTROL Topics Per Page]**
Hiermee definieert u het aantal vragen/berichten dat per pagina wordt weergegeven. De standaardwaarde is 10.

* **[!UICONTROL Moderated]**
Als deze optie is ingeschakeld, moet het posten van onderwerpen en opmerkingen worden goedgekeurd voordat ze op een publicatiesite worden weergegeven. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Closed]**
Als het forum wordt gecontroleerd, is het gesloten voor nieuwe vragen en commentaren. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Rich Text Editor]**
Als deze optie is ingeschakeld, kunnen onderwerpen en opmerkingen worden ingevoerd met een markering. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Tagging]**
Als deze optie is ingeschakeld, kunnen leden labels toevoegen aan hun advertentie (zie **[!UICONTROL Tag field]** ). De optie Standaard is uitgeschakeld.

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
Indien deze optie is ingeschakeld, neemt u de volgende functie op voor forumposten, waardoor leden kunnen worden [aangemeld](notifications.md) van nieuwe posten. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Pinning]**
Als deze optie ingeschakeld is, kunnen forumonderwerpen boven aan de lijst met onderwerpen worden vastgezet. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Email Subscriptions]**
Als deze optie ingeschakeld is, kunnen leden per e-mail op de hoogte worden gesteld van nieuwe berichten ([abonnement](subscriptions.md)). Vereisten `Allow Following` te controleren en [e-mail geconfigureerd](email.md). De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Replies]**
Als deze optie is ingeschakeld, kunt u reacties op opmerkingen op de vraag toestaan. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Users to Delete Comments and Topics]**
Als deze optie is ingeschakeld, kunnen leden de opmerkingen en vragen die ze hebben geplaatst verwijderen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Voting]**
Als deze optie is ingeschakeld, voegt u de functie Stemmen toe aan een vraag. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Move Selected Answer To The Top]**
Als deze optie ingeschakeld is, wordt een eerste weergegeven antwoord geselecteerd. Standaard is ingeschakeld.

* **[!UICONTROL Display Badges]**
Indien ingeschakeld, verdiende en toegewezen weergave [badges](implementing-scoring.md) met het blogbericht van een lid. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Featured Content]**
als het idee wordt gecontroleerd, kan het worden geïdentificeerd als [aanbevolen inhoud](featured.md). De optie Standaard is uitgeschakeld.

#### Tabblad Gebruikersmodernisering {#user-moderation-tab}

Onder de **[!UICONTROL User Moderation]** , geeft u op hoe de geposte onderwerpen (vragen) en antwoorden (door de gebruiker gegenereerde inhoud) worden beheerd. Zie voor meer informatie [Door gebruiker gegenereerde inhoud modereren](moderate-ugc.md).

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

Onder de **[!UICONTROL Tag field]** , de tags die kunnen worden toegepast, indien toegestaan onder de **[!UICONTROL Settings]** zijn beperkt op basis van de gekozen naamruimten.

* **[!UICONTROL Allowed Namespaces]**
Relevant indien 
`Allow Tagging` wordt gecontroleerd onder de **Instellingen** tab. De tags die kunnen worden toegepast, zijn beperkt tot de tags binnen de geselecteerde naamruimtecategorieën. De lijst met naamruimten bevat &#39;Standaardtags&#39; (de standaardnaamruimte) en &#39;Alle tags opnemen&#39;. De standaardwaarde is niet ingeschakeld, hetgeen betekent dat alle naamruimten zijn toegestaan.

* **[!UICONTROL Suggestion Limit]**
Voer het aantal tags in dat moet worden weergegeven als suggestie aan het lid dat naar het forum post. Een waarde van 
`-1` betekent geen limieten. De standaardwaarde is 0.

#### Tabblad Instellingen sorteren {#sort-settings-tab}

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

### Antwoorden identificeren {#identifying-answers}

Eén antwoord kan als een correct of nuttig antwoord worden gemarkeerd met de opdracht `Select Answer` knop. Als een vraag is gemarkeerd als Beantwoord, kan een ander antwoord pas worden geselecteerd als de eerste is uitgeschakeld met de optie `Unmark Chosen Answer`knop.

Als de optie eenmaal is geselecteerd als handig antwoord, kan de selectie ongedaan worden gemaakt met de optie `Unmark Chosen Answer` knop.

Zodra een antwoord als levensvatbaar antwoord is gekozen, een indicatie dat de vraag `Answered`wordt getoond naast het vraagonderwerp op de belangrijkste pagina QnA.

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

## Aanvullende informatie {#additional-information}

Meer informatie is te vinden op de [QnA Essentials](qna-essentials.md) pagina voor ontwikkelaars.

Voor moderatie van geposte onderwerpen en commentaren, zie [Door gebruiker gegenereerde inhoud modereren](moderate-ugc.md).

Voor het etiketteren van geposte onderwerpen en commentaren, zie [Door gebruiker gegenereerde inhoud labelen](tag-ugc.md).
