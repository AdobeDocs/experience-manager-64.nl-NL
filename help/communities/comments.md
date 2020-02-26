---
title: Opmerkingen gebruiken
seo-title: Opmerkingen gebruiken
description: Met de functie Opmerkingen kunnen aangemelde bezoekers hun mening en kennis delen
seo-description: Met de functie Opmerkingen kunnen aangemelde bezoekers hun mening en kennis delen
uuid: 30fc48ac-134c-4acb-a65c-398855c93829
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: b074ebfa-2894-4a2d-aa8e-28168049971a
translation-type: tm+mt
source-git-commit: 59d40b5bddc42a4ac057ef600243f396aefc926b

---


# Opmerkingen gebruiken {#using-comments}

## Inleiding {#introduction}

De functie voor opmerkingen wordt gebruikt om bezoekers die zich hebben aangemeld (leden) in staat te stellen hun mening en kennis over de inhoud van de site te delen. Deze functie is vaak al aanwezig in andere functies, maar kan aan elke website worden toegevoegd.

In deze sectie van de documentatie wordt beschreven

* Toevoegen `Comments`aan een pagina
* Configuratie-instellingen voor de `Comments`component

>[!NOTE]
>
>Anonieme berichten over opmerkingen worden niet ondersteund. Site-bezoekers moeten zich registreren (lid worden) en zich aanmelden om deel te nemen.

## Opmerkingen toevoegen aan een pagina {#adding-comments-to-a-page}

Als u een `Comments`component aan een pagina wilt toevoegen in de ontwerpmodus, gebruikt u de componentbrowser om te zoeken naar

* `Communities / Comments`

en sleep het naar de juiste positie op een pagina, zoals een positie ten opzichte van de functie waar gebruikers opmerkingen over kunnen plaatsen, of gewoon onder aan de pagina.

Ga voor de benodigde informatie naar [Community Components Basics](basics.md).

Wanneer de [vereiste client-side bibliotheken](essentials-comments.md#essentials-for-client-side) worden opgenomen, wordt de `Comments`component op deze manier weergegeven.

![chlimage_1-428](assets/chlimage_1-428.png)

>[!NOTE]
>
>Er mag slechts één `Comments`component op een pagina voorkomen. Houd er rekening mee dat diverse functies van een Gemeenschappen al opmerkingen bevatten, zoals een blog, agenda, forum, QnA en revisies.

## Opmerkingen configureren {#configuring-comments}

Selecteer de geplaatste `Comments` component die u wilt openen en selecteer het `Configure` pictogram waarmee het dialoogvenster Bewerken wordt geopend.

![configureren](assets/configure.png) , ![commentaarinstellingen](assets/commentssettings.png)

### Tabblad Opmerkingen {#comments-tab}

Geef op onder het tabblad **[!UICONTROL Opmerkingen]** op hoe bezoekers opmerkingen invoeren.

* **[!UICONTROL Antwoorden toestaan]**

   Als deze optie is ingeschakeld, kunnen leden reageren op bestaande opmerkingen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Opmerkingen per pagina]**

   Hiermee beperkt u het aantal opmerkingen dat per pagina wordt weergegeven en het aantal reacties dat wordt weergegeven. De standaardwaarde is 10.

* **[!UICONTROL Uploaden van bestanden toestaan]**

   Als deze optie is ingeschakeld, wordt het tekstinvoervak weergegeven voor de optie voor het uploaden van een bestand. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Max. bestandsgrootte]**

   Alleen relevant als Uploaden van bestand toestaan is ingeschakeld. Met deze waarde beperkt u de grootte van het geüploade bestand. Standaardlimiet is 10 MB.

* **[!UICONTROL Max. berichtlengte]**

   Maximumaantal tekens dat in het tekstvak kan worden ingevoerd. De standaardwaarde is 4096 tekens.

* **[!UICONTROL Toegestane bestandstypen]**

   Alleen relevant als Uploaden van bestand toestaan is ingeschakeld. Een door komma&#39;s gescheiden lijst met bestandsextensies met het scheidingsteken &#39;punt&#39;. Bijvoorbeeld: .jpg, .jpeg, .png, .doc, .docx, .pdf. Als er bestandstypen zijn opgegeven, zijn deze niet toegestaan. De standaardinstelling is niet opgegeven, zodat alle bestandstypen zijn toegestaan.

* **[!UICONTROL RTF-editor]**

   Als deze optie is ingeschakeld, kunnen opmerkingen worden ingevoerd met een markering. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Stemmen toestaan]**

   Als deze optie is ingeschakeld, wordt het tekstinvoervak weergegeven met de optie om omhoog of omlaag te stemmen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Volgen toestaan]**

   Als deze optie is ingeschakeld, kunnen leden opmerkingen volgen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Badges weergeven]**

   Als deze optie is ingeschakeld, kunnen verdiende en toegekende badges worden weergegeven. De optie Standaard is uitgeschakeld.

### Tabblad Gebruikersmodernisering {#user-moderation-tab}

Geef op onder het tabblad **[!UICONTROL Gebruikersmodernisering]** op hoe de geposte opmerkingen worden beheerd. Voor meer informatie, zie het [Modereren van Gebruiker Gegenereerde Inhoud](moderate-ugc.md).

* **[!UICONTROL Pre-moderatie]**

   Als deze optie is ingeschakeld, moeten opmerkingen worden goedgekeurd voordat ze op een publicatiesite worden weergegeven. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Opmerkingen verwijderen]**

   Als deze optie is ingeschakeld, kan het lid dat de opmerking heeft geplaatst deze verwijderen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Opmerkingen weigeren]**

   Indien gecontroleerd, sta moderators toe om commentaren te ontkennen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Opmerkingen sluiten/opnieuw openen]**

   Als deze optie ingeschakeld is, kan de moderator opmerkingen sluiten en opnieuw openen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Opmerkingen markeren]**

   Als deze optie is ingeschakeld, kunnen leden opmerkingen als onjuist markeren. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Lijst met redenen voor vlag]**

   Als deze optie is ingeschakeld, kunnen leden in een vervolgkeuzelijst de reden kiezen waarom een opmerking als onjuist wordt gemarkeerd. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Reden voor aangepaste vlag]**

   Als deze optie is ingeschakeld, kunnen leden hun eigen reden opgeven om een opmerking als ongeschikt te markeren. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Moderniseringsdrempel]**

   Voer het aantal keren in dat een opmerking moet worden gemarkeerd door leden voordat moderatoren op de hoogte worden gesteld. De standaardwaarde is één keer (1).

* **[!UICONTROL Limiet voor markering]**

   Voer het aantal keren in dat een opmerking moet worden gemarkeerd voordat deze wordt verborgen in de openbare weergave. Dit getal moet groter zijn dan of gelijk zijn aan de **[!UICONTROL moderatiedrempel]**. De standaardwaarde is 5.

### Tabblad Instellingen sorteren {#sort-settings-tab}

Geef op onder het tabblad **[!UICONTROL Sorteerinstellingen]** op hoe de geposte opmerkingen worden gesorteerd wanneer ze worden weergegeven.

* **[!UICONTROL Veld sorteren]**

   Trek omlaag om een van `Newest, Oldest, Last Updated, Most Viewed, Most Active, Most Followed`, of `Most Liked`te selecteren.

* **[!UICONTROL Sorteervolgorde]**

   Trek omlaag om een van `Ascending` of `Descending`te selecteren.

### Wijzigen in type aangepaste opmerking {#changing-to-a-custom-comment-type}

Door het Type van Middel van Commentaar te veranderen, zal het commentaarsysteem niet meer een geval van een commentaar gebruikend het gebrek, maar eerder een produceren die (uitgebreid) door ontwikkelaars is aangepast.

Zodra de types van douanemiddel bekend zijn, ga de Wijze [van het](../../help/sites-authoring/default-components-designmode.md) Ontwerp in en klik op de geplaatste `Comments` component tweemaal om een dialoog met een extra lusje te openen.

Onder het lusje van de Types **[!UICONTROL van Middel, specificeer douane resourceType voor nieuwe instanties van de]** `Comments or Voting`componenten:

![chlimage_1-429](assets/chlimage_1-429.png)

* **[!UICONTROL Type bron van opmerking]**

   Navigeer naar het resourceType van een uitgebreide `comment`component (enige commentaar) in /apps. Bijvoorbeeld, `/apps/social/commons/components/hbs/comments/comment`

   Deze bron identificeert het resourceType van de UGC die is gemaakt wanneer een bezoeker een opmerking plaatst.

* **[!UICONTROL Type stembron]**

   Navigeer aan resourceType van een uitgebreide `voting`component in /apps. Bijvoorbeeld, `/apps/social/components/hbs/voting`

   Met deze bron wordt het bronnentype van de UGC geïdentificeerd die wordt gemaakt wanneer een bezoeker een stem plaatst.

* **[!UICONTROL Brontype voor opmerkingensysteem]**

   Navigeer aan resourceType van een uitgebreide `comments`component (het Systeem van de Commentaar) in /apps. Leeg laten tenzij het paginasjabloon het opmerkingensysteem [dynamisch in het onderliggende script bevat](scf.md#add-or-include-a-communities-component) in plaats van als bron (knooppunt comments) aan de pagina te worden toegevoegd. Lees meer over de [{include} helper](handlebars-helpers.md#include).

## Ervaring met sitebezoekers {#site-visitor-experience}

### Moderatoren en beheerders {#moderators-and-administrators}

Wanneer de ondertekende binnen gebruiker moderator of beheerdervoorrechten heeft, kunnen zij de matigingstaken uitvoeren die door de configuratie van de component worden toegelaten, ongeacht wie de commentaar authored.

### Leden {#members}

Wanneer de bezoeker van de site zich heeft aangemeld, kunnen deze, afhankelijk van de configuratie

* Een nieuwe opmerking plaatsen
* Een eigen opmerking bewerken
* Een eigen opmerking verwijderen
* Opmerkingen van anderen markeren

### Anoniem {#anonymous}

Sitebezoekers die niet zijn aangemeld, kunnen alleen geposte opmerkingen lezen, deze vertalen indien deze worden ondersteund, maar kunnen geen opmerking toevoegen of opmerkingen van anderen markeren.

## Additional Information {#additional-information}

Meer informatie vindt u op de pagina [Comments Essentials](essentials-comments.md) voor ontwikkelaars.

Zie Door gebruiker gegenereerde inhoud [modereren voor moderatie van geposte opmerkingen](moderate-ugc.md).

Zie Door gebruiker gegenereerde inhoud [vertalen voor een vertaling van geposte opmerkingen](translate-ugc.md).
