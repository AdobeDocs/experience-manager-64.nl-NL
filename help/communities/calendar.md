---
title: Kalenderfunctie
seo-title: Kalenderfunctie
description: Biedt informatie over een communautaire gebeurtenis in een kalenderindeling
seo-description: Biedt informatie over een communautaire gebeurtenis in een kalenderindeling
uuid: 6f1f327f-bf4b-4357-b8fd-4bec74016921
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: 8b8e74c5-8b65-4117-9ef0-da9d9e47191f
exl-id: f95d1471-82a1-4c37-ac5b-0eb861c823a1
translation-type: tm+mt
source-git-commit: bd94d3949f0117aa3e1c9f0e84f7293a5d6b03b4
workflow-type: tm+mt
source-wordcount: '1089'
ht-degree: 0%

---

# Kalenderfunctie {#calendar-feature}

## Inleiding {#introduction}

De kalenderfunctie biedt ondersteuning voor het verschaffen van informatie over gebeurtenissen van de gebruikersgemeenschap in een kalendernotatie aan alle bezoekers van de site of alleen aangemeld bij bezoekers van de site (leden van de gemeenschap), terwijl alleen geautoriseerde leden gebeurtenissen mogen toevoegen.

In dit gedeelte van de documentatie wordt het volgende beschreven:

* De kalenderfunctie toevoegen aan een AEM-site
* Configuratie-instellingen voor `Calendar`componenten

## Een kalender toevoegen aan een pagina {#adding-a-calendar-to-a-page}

Als u een `Calendar`-component in de ontwerpmodus aan een pagina wilt toevoegen, gebruikt u de componentbrowser om te zoeken naar

* `Communities / Calendar`

en sleep het naar de juiste positie op een pagina, zoals een positie ten opzichte van de functie die gebruikers kunnen bekijken.

Voor noodzakelijke informatie, bezoek [de Grondbeginselen van Componenten van Gemeenschappen](basics.md).

Als de [vereiste client-side bibliotheken](calendar-basics-for-developers.md#essentials-for-client-side) worden opgenomen, wordt de `Calendar`-component op deze manier weergegeven.

![chlimage_1-112](assets/chlimage_1-112.png)

### Kalender {#configuring-calendar} configureren

Selecteer de geplaatste `Calendar`component om tot `Configure` pictogram toegang te hebben en te selecteren dat het Edit dialoog opent.

![chlimage_1-113](assets/chlimage_1-113.png) ![chlimage_1-114](assets/chlimage_1-114.png)

#### Tabblad Instellingen {#settings-tab}

Geef op het tabblad **[!UICONTROL Settings]** op of labels mogen worden toegepast op kalenderitems.

* **[!UICONTROL Events Per Page]**

   Hiermee definieert u het aantal gebeurtenissen dat per pagina wordt weergegeven. De standaardwaarde is 10.

* **[!UICONTROL Moderated]**

   Als deze optie is ingeschakeld, moet het posten van kalendergebeurtenissen en opmerkingen worden goedgekeurd voordat deze op een publicatiesite worden weergegeven. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Closed]**

   Als deze optie is ingeschakeld, wordt de kalender gesloten voor nieuwe gebeurtenisitems en opmerkingen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Rich Text Editor]**

   Als deze optie is ingeschakeld, kunnen kalendergebeurtenissen en opmerkingen worden ingevoerd met een markering. Standaard is ingeschakeld.

* **[!UICONTROL Allow Tagging]**

   Als deze optie is ingeschakeld, kunnen leden labellabels toevoegen aan de gebeurtenissen die ze posten (zie **Tagveld** tabblad). Standaard is ingeschakeld.

* **[!UICONTROL Allow File Uploads]**

   Als deze optie is ingeschakeld, staat u toe dat bestandsbijlagen worden toegevoegd aan een agendagebeurtenis of -opmerking. Standaard is ingeschakeld.

* **[!UICONTROL Allow Following]**

   Als deze optie is ingeschakeld, kunnen leden gebeurtenissen volgen die naar de kalender zijn gepost. Standaard is ingeschakeld.

* **[!UICONTROL Max File Size]**

   Alleen relevant als `Allow File Uploads` is ingeschakeld. Met dit veld wordt de grootte (in bytes) van een geüpload bestand beperkt. De standaardwaarde is 104857600 (10 MB).

* **[!UICONTROL Allowed File Types]**

   Alleen relevant als `Allow File Uploads` is ingeschakeld. Een door komma&#39;s gescheiden lijst met bestandsextensies met het &quot;punt&quot;-scheidingsteken. Bijvoorbeeld: .jpg, .jpeg, .png, .doc, .docx, .pdf. Als er bestandstypen zijn opgegeven, mogen de niet opgegeven bestandstypen niet worden geüpload. De standaardinstelling is niet opgegeven, zodat alle bestandstypen zijn toegestaan.

* **[!UICONTROL Max Attach Image File Size]**

   Alleen relevant als Uploaden van bestand toestaan is ingeschakeld. Het maximum aantal bytes dat een geüploade afbeeldingsbestand kan hebben. De standaardwaarde is 2097152 (2 MB).

* **[!UICONTROL Allowed Cover Image Types]**

   Een door komma&#39;s gescheiden lijst met extensies voor afbeeldingsbestanden met het &quot;punt&quot;-scheidingsteken. De standaardwaarde is `.jpg,.jpeg,.png,.gif,.bmp`.

* **[!UICONTROL Allow Threaded Replies]**

   Als deze optie is ingeschakeld, kunt u reacties op opmerkingen die zijn geplaatst voor de agendagebeurtenis toestaan. Standaard is ingeschakeld.

* **[!UICONTROL Allow Users to Delete Comments and Events]**

   Als deze optie is ingeschakeld, kunnen leden de opmerkingen en kalendergebeurtenissen die ze hebben gepost, verwijderen. Standaard is ingeschakeld.

* **[!UICONTROL Allow Voting]**

   Indien ingeschakeld, neemt u de functie Stemmen op met een agendagebeurtenis. Standaard is ingeschakeld.

* **[!UICONTROL Show Breadcrumbs]**

   Breedkruimels tonen op gebeurtenispagina. Standaard is ingeschakeld.

* **[!UICONTROL Date Range Filter]**

   Definieert het aantal dagen dat aan de huidige datum wordt toegevoegd om de waarde &quot;Aan&quot; van het filter voor de paginalijst van kalendergebeurtenissen te berekenen. Het standaardnummer is 30.

* **[!UICONTROL Allow Featured Content]**

   Als deze optie is ingeschakeld, kan het idee worden geïdentificeerd als [aanbevolen inhoud](featured.md). De optie Standaard is uitgeschakeld.

Geef onder het tabblad **[!UICONTROL User Moderation]** op hoe de geposte onderwerpen en antwoorden (door de gebruiker gegenereerde inhoud) worden beheerd. Zie [Door gebruiker gegenereerde inhoud modereren](moderate-ugc.md) voor meer informatie.

#### Tabblad Gebruikersmodernisering {#user-moderation-tab}

* **[!UICONTROL Deny Posts]**

   Als deze optie wordt ingeschakeld, zullen de verantwoordelijken van de leden hun functie kunnen ontkennen en voorkomen dat de functie op het openbare forum verschijnt. Standaard is ingeschakeld.

* **[!UICONTROL Close/Reopen Events]**

   Als deze optie ingeschakeld is, kunnen vertrouwde moderatoren van leden een gebeurtenis sluiten voor verdere bewerkingen en opmerkingen, en kunnen ze ook een gebeurtenis opnieuw openen. Standaard is ingeschakeld.

* **[!UICONTROL Flag Posts]**

   Als deze optie is ingeschakeld, kunnen leden gebeurtenissen of opmerkingen van anderen als ongeschikt markeren. Standaard is ingeschakeld.

* **[!UICONTROL Flag Reason List]**

   Als deze optie is ingeschakeld, kunnen leden in een vervolgkeuzelijst kiezen waarom zij een gebeurtenis of opmerking als ongeschikt aanmerken. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Custom Flag Reason]**

   Als deze optie is ingeschakeld, kunnen leden hun eigen reden opgeven om een gebeurtenis of opmerking als ongeschikt aan te duiden. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Moderation Threshold]**

   Voer het aantal keren in dat een gebeurtenis of opmerking moet worden gemarkeerd door leden voordat moderatoren op de hoogte worden gesteld. De standaardwaarde is 1 (één keer).

* **[!UICONTROL Flagging Limit]**

   Voer het aantal keren in dat een gebeurtenis of opmerking moet worden gemarkeerd voordat deze wordt verborgen in de openbare weergave. Indien ingesteld op -1, wordt het gemarkeerde onderwerp of de opmerking nooit verborgen in de openbare weergave. Anders, moet dit aantal groter dan of gelijk aan de Drempel van de Moderatie zijn. De standaardwaarde is 5.

#### Tabblad {#tag-field-tab} voor tagveld

Onder het tabblad **[!UICONTROL Tag field]** zijn de tags die kunnen worden toegepast, indien toegestaan onder het tabblad **[!UICONTROL Settings]**, beperkt op basis van de gekozen naamruimten.

* **[!UICONTROL Allowed Namespaces]**

   Relevant als `Allow Tagging` wordt gecontroleerd onder **[!UICONTROL Settings]** tabel. De tags die kunnen worden toegepast, zijn beperkt tot de tags binnen de geselecteerde naamruimtecategorieën. De lijst met naamruimten bevat &#39;Standaardtags&#39; (de standaardnaamruimte) en &#39;Alle tags opnemen&#39;. De standaardwaarde is niet ingeschakeld, hetgeen betekent dat alle naamruimten zijn toegestaan.

* **[!UICONTROL Suggestion Limit]**

   Voer het aantal tags in dat moet worden weergegeven als suggestie aan het lid dat naar het forum post. De standaardwaarde is `-1` (geen limieten).

>[!NOTE]
>
>Bezoek [Tags beheren](../../help/sites-administering/tags.md) voor informatie over het toevoegen van een nieuwe naamruimte voor tags (taxonomie).

#### Tabblad Vertaling {#translation-tab}

Als op het tabblad **[!UICONTROL Translation]** vertaling is ingeschakeld voor de communitysite, kan de vertaling zo worden ingesteld dat de volledige thread (gebeurtenis en opmerkingen) wordt vertaald in plaats van specifieke posts.

* **[!UICONTROL Translate All]**

   Als deze optie is ingeschakeld, worden de gebeurtenis en de opmerkingen vertaald naar de voorkeurstaal van de gebruiker. Standaard is ingeschakeld.

## Ervaring {#site-visitor-experience} voor bezoekers van site

In de publicatieomgeving wordt met de kalenderfunctie een zoekveld weergegeven met een standaarddatumbereik en alle kalendergebeurtenissen die binnen dat bereik vallen.

Wanneer een agendagebeurtenis is geselecteerd, worden de details, beschrijving en opmerkingen van de kalendergebeurtenis weergegeven.

Andere vaardigheden hangen af van het feit of de bezoeker van de site een moderator, beheerder, lid van de gemeenschap, geprivilegieerd lid of anoniem is.

### Moderatoren en beheerders {#moderators-and-administrators}

Wanneer de ondertekende binnen gebruiker moderator of beheerdervoorrechten heeft, kunnen zij [moderatietaken](moderate-ugc.md) (zoals toegelaten door de configuratie van de component) op alle kalendergebeurtenissen en commentaren uitvoeren die aan een gebeurtenis worden gepost.

![chlimage_1-115](assets/chlimage_1-115.png)

### Leden {#members}

Wanneer de aangemelde gebruiker een communitylid of [geprivilegieerd lid](users.md#privileged-members-group) is (afhankelijk van de configuratie), kunnen ze `New Event` selecteren om een nieuwe agendagebeurtenis te maken en te plaatsen.

Specifiek kunnen zij

* Een nieuwe agendagebeurtenis maken
* Opmerkingen verzenden naar een agendagebeurtenis
* Een eigen agendagebeurtenis of commentaar bewerken
* Verwijder hun eigen agendagebeurtenis of commentaar
* Andere kalendergebeurtenissen of opmerkingen markeren

![chlimage_1-116](assets/chlimage_1-116.png) ![chlimage_1-117](assets/chlimage_1-117.png)

### Anonieme {#anonymous}

Sitebezoekers die niet zijn aangemeld, kunnen alleen geposte kalendergebeurtenissen lezen, deze vertalen indien deze worden ondersteund, maar kunnen geen gebeurtenis of opmerking toevoegen en de gebeurtenissen of opmerkingen van anderen niet markeren.

![chlimage_1-118](assets/chlimage_1-118.png)

## Aanvullende informatie {#additional-information}

Meer informatie vindt u op de pagina [Kalender Essentials](calendar-basics-for-developers.md) voor ontwikkelaars.

Zie [Door gebruiker gegenereerde inhoud modereren](moderate-ugc.md) voor de moderatie van kalendergebeurtenissen en opmerkingen.

Zie [Door gebruiker gegenereerde inhoud labelen](tag-ugc.md) voor het labelen van agendagebeurtenissen en opmerkingen.

Zie [Door gebruiker gegenereerde inhoud omzetten](translate-ugc.md) voor een vertaling van kalendergebeurtenissen en opmerkingen.
