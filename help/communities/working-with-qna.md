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

Geef op het tabblad **[!UICONTROL Instellingen]** instellingen op voor onderwerpen (vragen) en antwoorden (antwoorden):

* **[!UICONTROL Onderwerpen per pagina]** bepalen het aantal vragen/posts dat per pagina wordt weergegeven. De standaardwaarde is 10.

* **[!UICONTROL Gemoderniseerd]** Als deze optie is ingeschakeld, moet het posten van onderwerpen en opmerkingen worden goedgekeurd voordat ze op een publicatiesite worden weergegeven. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Gesloten]** Als deze optie ingeschakeld is, is het forum gesloten voor nieuwe vragen en opmerkingen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL De rijke Redacteur]** van de Tekst als gecontroleerd, onderwerpen en commentaren kunnen met prijsverhoging zijn ingegaan. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Labelen]** toestaan Als deze optie is ingeschakeld, kunnen leden labellabels aan hun post toevoegen (zie tabblad **[!UICONTROL Tagveld]** ). De optie Standaard is uitgeschakeld.

* **[!UICONTROL Uploaden]** van bestand toestaanAls deze optie is ingeschakeld, mogen bestandsbijlagen worden toegevoegd aan de vraag of opmerking. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Maximale bestandsgrootte]** alleen relevant als deze `Allow File Uploads` is ingeschakeld. Met dit veld wordt de grootte (in bytes) van een geüpload bestand beperkt. De standaardwaarde is 104857600 (10 MB).

* **[!UICONTROL Alleen toegestane bestandstypen]** relevant als deze `Allow File Uploads` is ingeschakeld. Een door komma&#39;s gescheiden lijst met bestandsextensies met het &quot;punt&quot;-scheidingsteken. Bijvoorbeeld: .jpg, .jpeg, .png, .doc, .docx, .pdf. Als er bestandstypen zijn opgegeven, mogen de niet opgegeven bestandstypen niet worden geüpload. De standaardinstelling is niet opgegeven, zodat alle bestandstypen zijn toegestaan.

* **[!UICONTROL Maximale bestandsgrootte]** van afbeelding alleen relevant koppelen als Uploaden van bestand toestaan is ingeschakeld. Het maximum aantal bytes dat een geüploade afbeeldingsbestand kan hebben. De standaardwaarde is 2097152 (2 MB).

* **[!UICONTROL Volgend]** toestaan Indien ingeschakeld, neemt u de volgende functie voor forumfuncties op, waardoor leden op de [hoogte](notifications.md) kunnen worden gesteld van nieuwe posten. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Vastzetten]** toestaan Indien ingeschakeld, kunnen forumonderwerpen boven aan de lijst met onderwerpen worden vastgezet. De optie Standaard is uitgeschakeld.

* **[!UICONTROL E-mailabonnementen]** toestaan Als deze optie is ingeschakeld, kunnen leden per e-mail op de hoogte worden gesteld van nieuwe berichten ([abonnement](subscriptions.md)). Moet `Allow Following` worden gecontroleerd en [e-mail wordt gevormd](email.md). De optie Standaard is uitgeschakeld.

* **[!UICONTROL Reacties]** toestaan Als deze optie is ingeschakeld, kunt u reacties op opmerkingen op de vraag toestaan. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Gebruikers toestaan opmerkingen en onderwerpen]** te verwijderen Als deze optie is ingeschakeld, kunnen leden de opmerkingen en vragen die ze hebben geplaatst verwijderen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Stemmen]** toestaan Indien ingeschakeld, neemt u de functie Stemmen op bij een vraag. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Geselecteerd antwoord naar bovenzijde]** verplaatsen Als ingeschakeld, wordt het eerste weergegeven antwoord een geselecteerd antwoord. Standaard is ingeschakeld.

* **[!UICONTROL Badges]** weergeven Indien ingeschakeld, verdiende en toegewezen [badges](implementing-scoring.md) bij het blogbericht van een lid weergeven. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Aanbevolen inhoud]** toestaan als deze optie is ingeschakeld, kan het idee worden geïdentificeerd als [aanbevolen inhoud](featured.md). De optie Standaard is uitgeschakeld.

#### Tabblad Gebruikersmodernisering {#user-moderation-tab}

Geef onder het tabblad **[!UICONTROL Gebruikersmodernisering]** op hoe de geposte onderwerpen (vragen) en antwoorden (door de gebruiker gegenereerde inhoud) worden beheerd. Voor meer informatie, zie het [Modereren van Gebruiker Gegenereerde Inhoud](moderate-ugc.md).

* **[!UICONTROL Ontken Antwoorden]** Indien gecontroleerd, zullen de vertrouwde op lidmoderatoren geposte antwoorden kunnen ontkennen en het antwoord verhinderen op het openbare forum van Vragen en antwoorden te verschijnen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Sluit / heropen Onderwerpen]** Indien gecontroleerd, kunnen de vertrouwde op lidmoderatoren een vraag (onderwerp) aan verdere uitgeeft en antwoorden sluiten, en kunnen een vraag ook heropenen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Onderwerpen]** van de beweging indien gecontroleerd, sta toe publiceert-zijmoderators om vragen te bewegen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Vlagberichten]** Als deze optie is ingeschakeld, kunnen leden vragen of antwoorden van anderen als ongeschikt markeren. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Lijst]** met redenen voor vlagAls deze optie is ingeschakeld, kunnen leden in een vervolgkeuzelijst kiezen waarom een vraag of antwoord als onjuist moet worden gemarkeerd. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Reden]** voor aangepaste vlag Als dit selectievakje is ingeschakeld, kunnen leden hun eigen reden opgeven om een vraag of antwoord als ongeschikt te bestempelen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL De Drempel]** van de modernisering gaat het aantal tijden in een vraag of een antwoord door leden moet worden gemarkeerd alvorens moderators worden meegedeeld. De standaardwaarde is 1 (één keer).

* **[!UICONTROL Laginglimiet]** Voer het aantal keren in dat een vraag of antwoord moet worden gemarkeerd voordat deze wordt verborgen in de openbare weergave. Indien ingesteld op -1, wordt de gemarkeerde vraag of het gemarkeerde antwoord nooit verborgen voor de openbare weergave. Anders, moet dit aantal groter dan of gelijk aan de Drempel van de Moderatie zijn. De standaardwaarde is 5.

#### Tabblad Tagveld {#tag-field-tab}

Onder het tabblad **[!UICONTROL Tagveld]** zijn de tags die kunnen worden toegepast, indien toegestaan op het tabblad **[!UICONTROL Instellingen]** , beperkt op basis van de gekozen naamruimten.

* **[!UICONTROL Toegestane naamruimten]** relevant als deze `Allow Tagging` is ingeschakeld op het tabblad **Instellingen** . De tags die kunnen worden toegepast, zijn beperkt tot de tags binnen de geselecteerde naamruimtecategorieën. De lijst met naamruimten bevat &#39;Standaardtags&#39; (de standaardnaamruimte) en &#39;Alle tags opnemen&#39;. De standaardwaarde is niet ingeschakeld, hetgeen betekent dat alle naamruimten zijn toegestaan.

* **[!UICONTROL Suggestielimiet]** Voer het aantal tags in dat moet worden weergegeven als suggestie aan het lid dat naar het forum post. Een waarde van `-1` betekent geen limieten. De standaardwaarde is 0.

#### Tabblad Instellingen sorteren {#sort-settings-tab}

Geef op onder het tabblad **[!UICONTROL Sorteerinstellingen]** op hoe de geposte opmerkingen worden gesorteerd wanneer ze worden weergegeven.

* **[!UICONTROL Sorteren op]** Alle toegestane sorteerselecties controleren: `Newest, Oldest, Last Updated, Most Viewed, Most Active, Most Followed and Most Liked`. Standaard is dit `Newest, Oldest, Last Updated`.

* **[!UICONTROL Als Standaard]** omlaag schuiven instellen om een van de geselecteerde sorteeropties te selecteren die als standaardopties moeten worden weergegeven. Standaard is dit `Newest`.

* **[!UICONTROL Selecteer Tijdopties voor Analytische sortering]** Pull omlaag om een van `All, Last 24 Hours, Last 7 Days, Last 30 Days`deze opties te selecteren. Standaard is dit `All`.

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
