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
translation-type: tm+mt
source-git-commit: 5ddbcb2addff2d6e3a3e9d7e100a6d9ba89fdd60

---


# Kalenderfunctie {#calendar-feature}

## Inleiding {#introduction}

De kalenderfunctie biedt ondersteuning voor het verschaffen van informatie over gebeurtenissen van de gebruikersgemeenschap in een kalendernotatie aan alle bezoekers van de site of alleen aangemeld bij bezoekers van de site (leden van de gemeenschap), terwijl alleen geautoriseerde leden gebeurtenissen mogen toevoegen.

In dit gedeelte van de documentatie wordt het volgende beschreven:

* De kalenderfunctie toevoegen aan een AEM-site
* Configuratie-instellingen voor `Calendar`componenten

## Een kalender toevoegen aan een pagina {#adding-a-calendar-to-a-page}

Als u een `Calendar` component aan een pagina wilt toevoegen in de ontwerpmodus, gebruikt u de componentbrowser om te zoeken naar

* `Communities / Calendar`

en sleep het naar de juiste positie op een pagina, zoals een positie ten opzichte van de functie die gebruikers kunnen bekijken.

Ga voor de benodigde informatie naar [Community Components Basics](basics.md).

Wanneer de [vereiste client-side bibliotheken](calendar-basics-for-developers.md#essentials-for-client-side) worden opgenomen, wordt de `Calendar` component op deze manier weergegeven.

![chlimage_1-112](assets/chlimage_1-112.png)

### Kalender configureren {#configuring-calendar}

Selecteer de geplaatste `Calendar`component die u wilt openen en selecteer het `Configure` pictogram waarmee het dialoogvenster Bewerken wordt geopend.

![chlimage_1-113](assets/chlimage_1-113.png) ![chlimage_1-114](assets/chlimage_1-114.png)

#### Het tabblad Instellingen {#settings-tab}

Geef op het tabblad **[!UICONTROL Instellingen]** op of labels mogen worden toegepast op kalenderitems.

* **[!UICONTROL Gebeurtenissen per pagina]**

   Hiermee definieert u het aantal gebeurtenissen dat per pagina wordt weergegeven. De standaardwaarde is 10.

* **[!UICONTROL Gematigd]**

   Als deze optie is ingeschakeld, moet het posten van kalendergebeurtenissen en opmerkingen worden goedgekeurd voordat deze op een publicatiesite worden weergegeven. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Gesloten]**

   Als deze optie is ingeschakeld, wordt de kalender gesloten voor nieuwe gebeurtenisitems en opmerkingen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL RTF-editor]**

   Als deze optie is ingeschakeld, kunnen kalendergebeurtenissen en opmerkingen worden ingevoerd met een markering. Standaard is ingeschakeld.

* **[!UICONTROL Tags toestaan]**

   Als deze optie is ingeschakeld, kunnen leden labels toevoegen aan de gebeurtenissen die ze posten (zie tabblad **Tagveld** ). Standaard is ingeschakeld.

* **[!UICONTROL Uploaden van bestanden toestaan]**

   Als deze optie is ingeschakeld, staat u toe dat bestandsbijlagen worden toegevoegd aan een agendagebeurtenis of -opmerking. Standaard is ingeschakeld.

* **[!UICONTROL Volgen toestaan]**

   Als deze optie is ingeschakeld, kunnen leden gebeurtenissen volgen die naar de kalender zijn gepost. Standaard is ingeschakeld.

* **[!UICONTROL Max. bestandsgrootte]**

   Alleen relevant als `Allow File Uploads` is gecontroleerd. Met dit veld wordt de grootte (in bytes) van een geüpload bestand beperkt. De standaardwaarde is 104857600 (10 MB).

* **[!UICONTROL Toegestane bestandstypen]**

   Alleen relevant als `Allow File Uploads` is gecontroleerd. Een door komma&#39;s gescheiden lijst met bestandsextensies met het &quot;punt&quot;-scheidingsteken. Bijvoorbeeld: .jpg, .jpeg, .png, .doc, .docx, .pdf. Als er bestandstypen zijn opgegeven, mogen de niet opgegeven bestandstypen niet worden geüpload. De standaardinstelling is niet opgegeven, zodat alle bestandstypen zijn toegestaan.

* **[!UICONTROL Maximale bestandsgrootte afbeelding bijvoegen]**

   Alleen relevant als Uploaden van bestand toestaan is ingeschakeld. Het maximum aantal bytes dat een geüploade afbeeldingsbestand kan hebben. De standaardwaarde is 2097152 (2 MB).

* **[!UICONTROL Toegestane omslagafbeeldingstypen]**

   Een door komma&#39;s gescheiden lijst met extensies voor afbeeldingsbestanden met het &quot;punt&quot;-scheidingsteken. Standaard is dit `.jpg,.jpeg,.png,.gif,.bmp`.

* **[!UICONTROL Reacties met verbindingen toestaan]**

   Als deze optie is ingeschakeld, kunt u reacties op opmerkingen die zijn geplaatst voor de agendagebeurtenis toestaan. Standaard is ingeschakeld.

* **[!UICONTROL Gebruikers toestaan opmerkingen en gebeurtenissen te verwijderen]**

   Als deze optie is ingeschakeld, kunnen leden de opmerkingen en kalendergebeurtenissen die ze hebben gepost, verwijderen. Standaard is ingeschakeld.

* **[!UICONTROL Stemmen toestaan]**

   Indien ingeschakeld, neemt u de functie Stemmen op met een agendagebeurtenis. Standaard is ingeschakeld.

* **[!UICONTROL Broodkruimels tonen]**

   Breedkruimels tonen op gebeurtenispagina. Standaard is ingeschakeld.

* **[!UICONTROL Filter datumbereik]**

   Definieert het aantal dagen dat aan de huidige datum wordt toegevoegd om de waarde &quot;Aan&quot; van het filter voor de paginalijst van kalendergebeurtenissen te berekenen. Het standaardnummer is 30.

* **[!UICONTROL Aanbevolen inhoud toestaan]**

   Als deze optie is ingeschakeld, kan het idee worden geïdentificeerd als [aanbevolen inhoud](featured.md). De optie Standaard is uitgeschakeld.

Onder het lusje van de Moderatie **[!UICONTROL van de]** Gebruiker, specificeer hoe de geposte onderwerpen en de antwoorden (gebruiker geproduceerde inhoud) worden beheerd. Voor meer informatie, zie het [Modereren van Gebruiker Gegenereerde Inhoud](moderate-ugc.md).

#### Tabblad Gebruikersmodernisering {#user-moderation-tab}

* **[!UICONTROL Posten weigeren]**

   Als deze optie wordt ingeschakeld, zullen de verantwoordelijken van de leden hun functie kunnen ontkennen en voorkomen dat de functie op het openbare forum verschijnt. Standaard is ingeschakeld.

* **[!UICONTROL Gebeurtenissen sluiten/opnieuw openen]**

   Als deze optie ingeschakeld is, kunnen vertrouwde moderatoren van leden een gebeurtenis sluiten voor verdere bewerkingen en opmerkingen, en kunnen ze ook een gebeurtenis opnieuw openen. Standaard is ingeschakeld.

* **[!UICONTROL Vlagberichten]**

   Als deze optie is ingeschakeld, kunnen leden gebeurtenissen of opmerkingen van anderen als ongeschikt markeren. Standaard is ingeschakeld.

* **[!UICONTROL Lijst met redenen voor vlag]**

   Als deze optie is ingeschakeld, kunnen leden in een vervolgkeuzelijst kiezen waarom zij een gebeurtenis of opmerking als ongeschikt aanmerken. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Reden voor aangepaste vlag]**

   Als deze optie is ingeschakeld, kunnen leden hun eigen reden opgeven om een gebeurtenis of opmerking als ongeschikt aan te duiden. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Moderniseringsdrempel]**

   Voer het aantal keren in dat een gebeurtenis of opmerking moet worden gemarkeerd door leden voordat moderatoren op de hoogte worden gesteld. De standaardwaarde is 1 (één keer).

* **[!UICONTROL Limiet voor markering]**

   Voer het aantal keren in dat een gebeurtenis of opmerking moet worden gemarkeerd voordat deze wordt verborgen in de openbare weergave. Indien ingesteld op -1, wordt het gemarkeerde onderwerp of de opmerking nooit verborgen in de openbare weergave. Anders, moet dit aantal groter dan of gelijk aan de Drempel van de Moderatie zijn. De standaardwaarde is 5.

#### Tabblad Tagveld {#tag-field-tab}

Onder het tabblad **[!UICONTROL Tagveld]** zijn de tags die kunnen worden toegepast, indien toegestaan op het tabblad **[!UICONTROL Instellingen]** , beperkt op basis van de gekozen naamruimten.

* **[!UICONTROL Toegestane naamruimten]**

   Relevant als `Allow Tagging` is ingeschakeld onder het tabblad **[!UICONTROL Instellingen]** . De tags die kunnen worden toegepast, zijn beperkt tot de tags binnen de geselecteerde naamruimtecategorieën. De lijst met naamruimten bevat &#39;Standaardtags&#39; (de standaardnaamruimte) en &#39;Alle tags opnemen&#39;. De standaardwaarde is niet ingeschakeld, hetgeen betekent dat alle naamruimten zijn toegestaan.

* **[!UICONTROL Suggestiegrenswaarde]**

   Voer het aantal tags in dat moet worden weergegeven als suggestie aan het lid dat naar het forum post. De standaardwaarde is `-1` (geen limieten).

>[!NOTE]
>
>Ga naar [Tags](../../help/sites-administering/tags.md) beheren voor meer informatie over het toevoegen van een nieuwe naamruimte voor tags (taxonomie).

#### Tabblad Vertaling {#translation-tab}

Als op het tabblad **[!UICONTROL Vertaling]** vertaling is ingeschakeld voor de site van de gebruikersgemeenschap, kan de vertaling zo worden ingesteld dat de volledige thread (gebeurtenis en opmerkingen) wordt vertaald in plaats van specifieke posts.

* **[!UICONTROL Alles vertalen]**

   Als deze optie is ingeschakeld, worden de gebeurtenis en de opmerkingen vertaald naar de voorkeurstaal van de gebruiker. Standaard is ingeschakeld.

## Ervaring met sitebezoekers {#site-visitor-experience}

In de publicatieomgeving wordt met de kalenderfunctie een zoekveld weergegeven met een standaarddatumbereik en alle kalendergebeurtenissen die binnen dat bereik vallen.

Wanneer een agendagebeurtenis is geselecteerd, worden de details, beschrijving en opmerkingen van de kalendergebeurtenis weergegeven.

Andere vaardigheden hangen af van het feit of de bezoeker van de site een moderator, beheerder, lid van de gemeenschap, geprivilegieerd lid of anoniem is.

### Moderatoren en beheerders {#moderators-and-administrators}

Wanneer de ondertekende in gebruiker moderator of beheerdervoorrechten heeft, kunnen zij [matigingstaken](moderate-ugc.md) (zoals toegelaten door de configuratie van de component) op alle kalendergebeurtenissen en commentaren uitvoeren die aan een gebeurtenis worden gepost.

![chlimage_1-115](assets/chlimage_1-115.png)

### Leden {#members}

Wanneer de ondertekende in gebruiker een lid van de gemeenschap of een [geprivilegieerd lid](users.md#privileged-members-group) (afhankelijk van configuratie) is, kunnen zij selecteren `New Event` om een nieuwe kalendergebeurtenis tot stand te brengen en te posten.

Specifiek kunnen zij

* Een nieuwe agendagebeurtenis maken
* Opmerkingen verzenden naar een agendagebeurtenis
* Een eigen agendagebeurtenis of commentaar bewerken
* Verwijder hun eigen agendagebeurtenis of commentaar
* Andere kalendergebeurtenissen of opmerkingen markeren

![chlimage_1-116](assets/chlimage_1-116.png) ![chlimage_1-117](assets/chlimage_1-117.png)

### Anoniem {#anonymous}

Sitebezoekers die niet zijn aangemeld, kunnen alleen geposte kalendergebeurtenissen lezen, deze vertalen indien deze worden ondersteund, maar kunnen geen gebeurtenis of opmerking toevoegen en de gebeurtenissen of opmerkingen van anderen niet markeren.

![chlimage_1-118](assets/chlimage_1-118.png)

## Additional Information {#additional-information}

Meer informatie vindt u op de pagina [Kalender Essentials](calendar-basics-for-developers.md) voor ontwikkelaars.

Voor moderatie van kalendergebeurtenissen en commentaren, zie het [Modereren van Door Gebruiker Gegenereerde Inhoud](moderate-ugc.md).

Zie Door gebruiker gegenereerde inhoud [](tag-ugc.md)labelen voor informatie over het labelen van agendagebeurtenissen en opmerkingen.

Zie Door gebruiker gegenereerde inhoud [vertalen voor meer informatie over kalendergebeurtenissen en opmerkingen](translate-ugc.md).
