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
exl-id: 8ad5ce3e-c5dd-48d7-8812-43172eda36cc
translation-type: tm+mt
source-git-commit: bd94d3949f0117aa3e1c9f0e84f7293a5d6b03b4
workflow-type: tm+mt
source-wordcount: '939'
ht-degree: 0%

---

# Opmerkingen gebruiken {#using-comments}

## Inleiding {#introduction}

De functie voor opmerkingen wordt gebruikt om bezoekers die zich hebben aangemeld (leden) in staat te stellen hun mening en kennis over de inhoud van de site te delen. Deze functie is vaak al aanwezig in andere functies, maar kan aan elke website worden toegevoegd.

In deze sectie van de documentatie wordt beschreven

* `Comments`toevoegen aan een pagina
* De montages van de configuratie voor `Comments`component

>[!NOTE]
>
>Anonieme berichten over opmerkingen worden niet ondersteund. Site-bezoekers moeten zich registreren (lid worden) en zich aanmelden om deel te nemen.

## Opmerkingen toevoegen aan een pagina {#adding-comments-to-a-page}

Als u een `Comments`component wilt toevoegen aan een pagina in de ontwerpmodus, gebruikt u de componentbrowser om te zoeken naar

* `Communities / Comments`

en sleep het naar de juiste positie op een pagina, zoals een positie ten opzichte van de functie waar gebruikers opmerkingen over kunnen plaatsen, of gewoon onder aan de pagina.

Voor noodzakelijke informatie, bezoek [de Grondbeginselen van Componenten van Gemeenschappen](basics.md).

Als de [vereiste client-side bibliotheken](essentials-comments.md#essentials-for-client-side) worden opgenomen, wordt de `Comments`component op deze manier weergegeven.

![chlimage_1-428](assets/chlimage_1-428.png)

>[!NOTE]
>
>Er mag slechts één `Comments`component op een pagina voorkomen. Houd er rekening mee dat diverse functies van een Gemeenschappen al opmerkingen bevatten, zoals een blog, agenda, forum, QnA en revisies.

## Opmerkingen {#configuring-comments} configureren

Selecteer de geplaatste `Comments` component en selecteer `Configure` pictogram dat het Edit dialoog opent.

![](assets/configure.png) ![configurecommenssettings](assets/commentssettings.png)

### Tabblad Opmerkingen {#comments-tab}

Geef onder het tabblad **[!UICONTROL Comments]** op hoe bezoekers opmerkingen invoeren.

* **[!UICONTROL Allow replies]**

   Als deze optie is ingeschakeld, kunnen leden reageren op bestaande opmerkingen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Comments Per Page]**

   Hiermee beperkt u het aantal opmerkingen dat per pagina wordt weergegeven en het aantal reacties dat wordt weergegeven. De standaardwaarde is 10.

* **[!UICONTROL Allow File Uploads]**

   Als deze optie is ingeschakeld, wordt het tekstinvoervak weergegeven voor de optie voor het uploaden van een bestand. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Max File Size]**

   Alleen relevant als Uploaden van bestand toestaan is ingeschakeld. Met deze waarde beperkt u de grootte van het geüploade bestand. Standaardlimiet is 10 MB.

* **[!UICONTROL Max Message Length]**

   Maximumaantal tekens dat in het tekstvak kan worden ingevoerd. De standaardwaarde is 4096 tekens.

* **[!UICONTROL Allowed File Types]**

   Alleen relevant als Uploaden van bestand toestaan is ingeschakeld. Een door komma&#39;s gescheiden lijst met bestandsextensies met het scheidingsteken &#39;punt&#39;. Bijvoorbeeld: .jpg, .jpeg, .png, .doc, .docx, .pdf. Als er bestandstypen zijn opgegeven, zijn deze niet toegestaan. De standaardinstelling is niet opgegeven, zodat alle bestandstypen zijn toegestaan.

* **[!UICONTROL Rich Text Editor]**

   Als deze optie is ingeschakeld, kunnen opmerkingen worden ingevoerd met een markering. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Voting]**

   Als deze optie is ingeschakeld, wordt de optie om omhoog of omlaag te stemmen weergegeven met het tekstinvoervak. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Following]**

   Als deze optie is ingeschakeld, kunnen leden opmerkingen volgen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Display Badges]**

   Als deze optie is ingeschakeld, kunnen verdiende en toegekende badges worden weergegeven. De optie Standaard is uitgeschakeld.

### Tabblad Gebruikersmodernisering {#user-moderation-tab}

Geef onder het tabblad **[!UICONTROL User Moderation]** op hoe de geposte opmerkingen worden beheerd. Zie [Door gebruiker gegenereerde inhoud modereren](moderate-ugc.md) voor meer informatie.

* **[!UICONTROL Pre-Moderation]**

   Als deze optie is ingeschakeld, moeten opmerkingen worden goedgekeurd voordat ze op een publicatiesite worden weergegeven. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Delete Comments]**

   Als deze optie is ingeschakeld, kan het lid dat de opmerking heeft geplaatst deze verwijderen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Deny Comments]**

   Indien gecontroleerd, sta moderators toe om commentaren te ontkennen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Close/Reopen Comments]**

   Als deze optie ingeschakeld is, kan de moderator opmerkingen sluiten en opnieuw openen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Flag Comments]**

   Als deze optie is ingeschakeld, kunnen leden opmerkingen als onjuist markeren. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Flag Reason List]**

   Als deze optie is ingeschakeld, kunnen leden in een vervolgkeuzelijst de reden kiezen waarom een opmerking als onjuist wordt gemarkeerd. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Custom Flag Reason]**

   Als deze optie is ingeschakeld, kunnen leden hun eigen reden opgeven om een opmerking als ongeschikt te markeren. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Moderation Threshold]**

   Voer het aantal keren in dat een opmerking moet worden gemarkeerd door leden voordat moderatoren op de hoogte worden gesteld. De standaardwaarde is één keer (1).

* **[!UICONTROL Flagging Limit]**

   Voer het aantal keren in dat een opmerking moet worden gemarkeerd voordat deze wordt verborgen in de openbare weergave. Dit getal moet groter dan of gelijk zijn aan **[!UICONTROL Moderation Threshold]**. De standaardwaarde is 5.

### Tabblad Instellingen sorteren {#sort-settings-tab}

Geef onder het tabblad **[!UICONTROL Sort Settings]** op hoe de geposte opmerkingen worden gesorteerd wanneer ze worden weergegeven.

* **[!UICONTROL Sort Field]**

   Trek neer om één van `Newest, Oldest, Last Updated, Most Viewed, Most Active, Most Followed`, of `Most Liked` te selecteren.

* **[!UICONTROL Sort Order]**

   Trek neer om één van `Ascending` of `Descending` te selecteren.

### Wijzigen in type aangepaste opmerking {#changing-to-a-custom-comment-type}

Door het Type van Middel van Commentaar te veranderen, zal het commentaarsysteem niet meer een geval van een commentaar gebruikend het gebrek, maar eerder een produceren die (uitgebreid) door ontwikkelaars is aangepast.

Zodra de types van douanemiddel bekend zijn, ga [Ontwerpwijze](../../help/sites-authoring/default-components-designmode.md) in en klik op de geplaatste `Comments` component tweemaal om een dialoog met een extra lusje te openen.

Geef onder het tabblad **[!UICONTROL Resource Types]** het aangepaste resourceType op voor nieuwe instanties van de `Comments or Voting`componenten:

![chlimage_1-429](assets/chlimage_1-429.png)

* **[!UICONTROL Comment Resource Type]**

   Navigeer naar het resourceType van uitgebreide `comment`component (enige commentaar) in /apps. Bijvoorbeeld, `/apps/social/commons/components/hbs/comments/comment`

   Deze bron identificeert het resourceType van de UGC die is gemaakt wanneer een bezoeker een opmerking plaatst.

* **[!UICONTROL Voting Resource Type]**

   Navigeer naar het resourceType van een uitgebreide `voting`component in /apps. Bijvoorbeeld, `/apps/social/components/hbs/voting`

   Met deze bron wordt het bronnentype van de UGC geïdentificeerd die wordt gemaakt wanneer een bezoeker een stem plaatst.

* **[!UICONTROL Comment System Resource Type]**

   Navigeer naar het resourceType van uitgebreide `comments`component (het Systeem van de Commentaar) in /apps. Leeg laten tenzij het paginamalplaatje [dynamisch ](scf.md#add-or-include-a-communities-component) het Systeem van de Commentaar in het onderliggende manuscript in plaats van wordt toegevoegd aan de pagina als middel (commentaarknoop) omvat. Leer meer door over [ te lezen {{include} helper](handlebars-helpers.md#include).

## Ervaring {#site-visitor-experience} voor bezoekers van site

### Moderatoren en beheerders {#moderators-and-administrators}

Wanneer de ondertekende binnen gebruiker moderator of beheerdervoorrechten heeft, kunnen zij de matigingstaken uitvoeren die door de configuratie van de component worden toegelaten, ongeacht wie de commentaar authored.

### Leden {#members}

Wanneer de bezoeker van de site zich heeft aangemeld, kunnen deze, afhankelijk van de configuratie

* Een nieuwe opmerking plaatsen
* Een eigen opmerking bewerken
* Een eigen opmerking verwijderen
* Opmerkingen van anderen markeren

### Anonieme {#anonymous}

Sitebezoekers die niet zijn aangemeld, kunnen alleen geposte opmerkingen lezen, deze vertalen indien deze worden ondersteund, maar kunnen geen opmerking toevoegen of opmerkingen van anderen markeren.

## Aanvullende informatie {#additional-information}

Meer informatie vindt u op de pagina [Comments Essentials](essentials-comments.md) voor ontwikkelaars.

Zie [Door gebruiker gegenereerde inhoud modereren](moderate-ugc.md) voor de moderatie van geposte opmerkingen.

Zie [Door gebruiker gegenereerde inhoud omzetten](translate-ugc.md) voor een vertaling van geposte opmerkingen.
