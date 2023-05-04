---
title: Opmerkingen gebruiken
seo-title: Using Comments
description: Met de functie Opmerkingen kunnen aangemelde bezoekers hun mening en kennis delen
seo-description: Comments feature lets signed-in site visitors share their opinions and knowledge
uuid: 30fc48ac-134c-4acb-a65c-398855c93829
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: b074ebfa-2894-4a2d-aa8e-28168049971a
exl-id: 8ad5ce3e-c5dd-48d7-8812-43172eda36cc
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '961'
ht-degree: 0%

---

# Opmerkingen gebruiken {#using-comments}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Inleiding {#introduction}

De functie voor opmerkingen wordt gebruikt om bezoekers die zich hebben aangemeld (leden) in staat te stellen hun mening en kennis over de inhoud van de site te delen. Deze functie is vaak al aanwezig in andere functies, maar kan aan elke website worden toegevoegd.

In deze sectie van de documentatie wordt beschreven

* Toevoegen `Comments`naar een pagina
* De montages van de configuratie voor de `Comments`component

>[!NOTE]
>
>Anonieme berichten over opmerkingen worden niet ondersteund. Site-bezoekers moeten zich registreren (lid worden) en zich aanmelden om deel te nemen.

## Opmerkingen toevoegen aan een pagina {#adding-comments-to-a-page}

Als u een `Comments`van een component aan een pagina op auteurswijze, gebruik componentenbrowser om van

* `Communities / Comments`

en sleep het naar de juiste positie op een pagina, zoals een positie ten opzichte van de functie waar gebruikers opmerkingen over kunnen plaatsen, of gewoon onder aan de pagina.

Voor de nodige informatie gaat u naar [Grondbeginselen van Community-componenten](basics.md).

Wanneer de [vereiste clientbibliotheken](essentials-comments.md#essentials-for-client-side) worden opgenomen, is dit hoe `Comments`wordt weergegeven.

![chlimage_1-428](assets/chlimage_1-428.png)

>[!NOTE]
>
>Slechts één `Comments`kan op een pagina voorkomen. Houd er rekening mee dat diverse functies van een Gemeenschappen al opmerkingen bevatten, zoals een blog, agenda, forum, QnA en revisies.

## Opmerkingen configureren {#configuring-comments}

Selecteer de geplaatste `Comments` te openen en de component te selecteren `Configure` wordt het dialoogvenster Bewerken geopend.

![vormen](assets/configure.png) ![commentaarinstellingen](assets/commentssettings.png)

### Tabblad Opmerkingen {#comments-tab}

Onder de **[!UICONTROL Comments]** , geeft u op hoe bezoekers opmerkingen invoeren.

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

   Als deze optie is ingeschakeld, wordt het tekstinvoervak weergegeven met de optie om omhoog of omlaag te stemmen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Following]**

   Als deze optie is ingeschakeld, kunnen leden opmerkingen volgen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Display Badges]**

   Als deze optie is ingeschakeld, kunnen verdiende en toegekende badges worden weergegeven. De optie Standaard is uitgeschakeld.

### Tabblad Gebruikersmodernisering {#user-moderation-tab}

Onder de **[!UICONTROL User Moderation]** , geeft u op hoe de geposte opmerkingen worden beheerd. Zie voor meer informatie [Door gebruiker gegenereerde inhoud modereren](moderate-ugc.md).

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

   Voer het aantal keren in dat een opmerking moet worden gemarkeerd voordat deze wordt verborgen in de openbare weergave. Dit getal moet groter zijn dan of gelijk zijn aan het **[!UICONTROL Moderation Threshold]**. De standaardwaarde is 5.

### Tabblad Instellingen sorteren {#sort-settings-tab}

Onder de **[!UICONTROL Sort Settings]** , geeft u op hoe de geposte opmerkingen worden gesorteerd wanneer deze worden weergegeven.

* **[!UICONTROL Sort Field]**

   Omlaag trekken om een van de volgende opties te selecteren `Newest, Oldest, Last Updated, Most Viewed, Most Active, Most Followed`, of `Most Liked`.

* **[!UICONTROL Sort Order]**

   Omlaag trekken om een van de volgende opties te selecteren `Ascending` of `Descending`.

### Wijzigen in type aangepaste opmerking {#changing-to-a-custom-comment-type}

Door het Type van Middel van Commentaar te veranderen, zal het commentaarsysteem niet meer een geval van een commentaar gebruikend het gebrek, maar eerder een produceren die (uitgebreid) door ontwikkelaars is aangepast.

Zodra de types van douanemiddel gekend zijn, ga binnen [Ontwerpmodus](../../help/sites-authoring/default-components-designmode.md) en dubbelklik op de geplaatste `Comments` om een dialoogvenster met een extra tabblad te openen.

Onder de **[!UICONTROL Resource Types]** tab, specificeer het custom resourceType voor nieuwe instanties van `Comments or Voting`componenten:

![chlimage_1-429](assets/chlimage_1-429.png)

* **[!UICONTROL Comment Resource Type]**

   Navigeer naar het resourceType van uitgebreid `comment`component (enkele opmerking) in /apps. Bijvoorbeeld, `/apps/social/commons/components/hbs/comments/comment`

   Deze bron identificeert het resourceType van de UGC die is gemaakt wanneer een bezoeker een opmerking plaatst.

* **[!UICONTROL Voting Resource Type]**

   Navigeer naar het resourceType van uitgebreid `voting`in /apps. Bijvoorbeeld, `/apps/social/components/hbs/voting`

   Met deze bron wordt het bronnentype van de UGC geïdentificeerd die wordt gemaakt wanneer een bezoeker een stem plaatst.

* **[!UICONTROL Comment System Resource Type]**

   Navigeer naar het resourceType van uitgebreid `comments`component (Opmerkingssysteem) in /apps. Leeg laten, tenzij de paginasjabloon [dynamisch omvat](scf.md#add-or-include-a-communities-component) het Systeem van de Commentaar in het onderliggende manuscript in plaats van wordt toegevoegd aan de pagina als middel (commentaarknoop). Lees meer over de [{{include}} helper](handlebars-helpers.md#include).

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

## Aanvullende informatie {#additional-information}

Meer informatie is te vinden op de [Essentiële opmerkingen](essentials-comments.md) pagina voor ontwikkelaars.

Zie voor een moderatie van gepubliceerde opmerkingen [Door gebruiker gegenereerde inhoud modereren](moderate-ugc.md).

Zie voor een vertaling van geposte opmerkingen [Door gebruiker gegenereerde inhoud vertalen](translate-ugc.md).
