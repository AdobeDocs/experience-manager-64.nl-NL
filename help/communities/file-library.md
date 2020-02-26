---
title: Functie bestandsbibliotheek
seo-title: Functie bestandsbibliotheek
description: Met de functie Bestandsbibliotheek kunnen aangemelde sitebezoekers bestanden uploaden, beheren en downloaden
seo-description: Met de functie Bestandsbibliotheek kunnen aangemelde sitebezoekers bestanden uploaden, beheren en downloaden
uuid: 7da94703-8334-4c02-ba2a-55b5cde22e6c
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: cdcae09f-c3cb-471e-863f-b33130e9df0f
translation-type: tm+mt
source-git-commit: 3d2b91565e14e85e9e701663c8d0ded03e5b430c

---


# Functie bestandsbibliotheek {#file-library-feature}

## Inleiding {#introduction}

De functie voor bestandsbibliotheek biedt een plaats voor ingetekende sitebezoekers (leden van de community) voor het uploaden, beheren en downloaden van bestanden binnen de site van de gebruikersgemeenschap.

In deze sectie van de documentatie wordt beschreven

* De bestandsbibliotheekfunctie toevoegen aan een AEM-site
* Configuratie-instellingen voor de `File Library` component

## Een bestandsbibliotheek toevoegen aan een pagina {#adding-a-file-library-to-a-page}

Als u een `File Library` component aan een pagina wilt toevoegen in de ontwerpmodus, zoekt u de component

* `Communities / File Library`

en sleep het naar de juiste plaats op een pagina.

Ga voor de benodigde informatie naar [Community Components Basics](basics.md).

Wanneer de [vereiste client-side bibliotheken](essentials-file-library.md#essentials-for-client-side) worden opgenomen, wordt de `File Library` component als volgt weergegeven:

![chlimage_1-430](assets/chlimage_1-430.png)

## Bestandsbibliotheek configureren {#configuring-file-library}

Selecteer de geplaatste `File Library` component die u wilt openen en selecteer het `Configure` pictogram waarmee het dialoogvenster Bewerken wordt geopend.

![chlimage_1-431](assets/chlimage_1-431.png) ![chlimage_1-432](assets/chlimage_1-432.png)

### Tabblad Opmerkingen {#comments-tab}

Geef op het tabblad **[!UICONTROL Opmerkingen]** op of en hoe opmerkingen voor geüploade bestanden worden weergegeven:

* **[!UICONTROL Opmerkingen over bestanden]** toestaan Als deze optie is ingeschakeld, kunt u opmerkingen over geüploade bestanden toestaan. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Met Opmerkingen per pagina]** beperkt u het aantal opmerkingen dat per pagina wordt weergegeven en het aantal reacties dat wordt weergegeven. De standaardwaarde is **10**.

* **[!UICONTROL Maximale bestandsgrootte]** Deze waarde beperkt de grootte van het geüploade bestand. Standaardlimiet is 104857600 (10 MB).

* **[!UICONTROL Maximale berichtlengte]** Maximum aantal tekens dat in het tekstvak mag worden ingevoerd. De standaardwaarde is 4096 tekens.

* **[!UICONTROL Toegestane bestandstypen]** Een door komma&#39;s gescheiden lijst met bestandsextensies met het &quot;punt&quot;-scheidingsteken. Bijvoorbeeld: .jpg, .jpeg, .png, .doc, .docx, .pdf. Als er bestandstypen worden opgegeven, zijn deze niet toegestaan. De standaardinstelling is niet opgegeven, zodat alle bestandstypen zijn toegestaan.

* **[!UICONTROL De Rich Text Editor]** Als deze optie is ingeschakeld, kunnen opmerkingen worden ingevoerd met een markering. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Opmerkingen]** verwijderen Als deze optie is ingeschakeld, mogen gebruikers hun eigen opmerkingen verwijderen. Standaard is ingeschakeld.

* **[!UICONTROL Labelen]** toestaan Als deze optie is ingeschakeld, wordt de mogelijkheid ingeschakeld om een tag aan het bestand toe te voegen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Toegestane naamruimten]** als Tags toestaan is ingeschakeld, worden de beschikbare tags beperkt tot de geselecteerde naamruimten. Als er geen optie is geselecteerd, zijn alle opties toegestaan. Standaard zijn alle naamruimten.

* **[!UICONTROL Suggestielimiet]** Als Tags toestaan is ingeschakeld, wordt met deze instelling het aantal voorgestelde tags dat wordt weergegeven, beperkt. Indien ingesteld op -1, is er geen limiet. De standaardwaarde is -1.

* **[!UICONTROL Stemmen]** toestaan Als deze optie is ingeschakeld, wordt de mogelijkheid om voor een bestand te stemmen ingeschakeld. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Volgend]** toestaan Als deze optie is ingeschakeld, neemt u de volgende functie op voor blogartikelen, waarmee leden op de [hoogte](notifications.md) kunnen worden gesteld van nieuwe berichten. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Reacties]** met verbindingen toestaan Als deze optie is ingeschakeld, toestaan dat reacties op gepost opmerkingen worden ontvangen. De optie Standaard is uitgeschakeld.

### Tabblad Gebruikersmodernisering {#user-moderation-tab}

Onder het tabblad **[!UICONTROL Gebruikersmodernisering]** configureert u de moderatie van opmerkingen als opmerkingen zijn toegestaan:

* **[!UICONTROL Pre-Moderation]** Als deze optie is ingeschakeld, moeten opmerkingen worden goedgekeurd voordat ze op een publicatiesite worden weergegeven. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Opmerkingen]** verwijderen Als deze optie is ingeschakeld, kan de bezoeker die de opmerking heeft geplaatst deze verwijderen. Standaard is ingeschakeld.

* **[!UICONTROL Ontken Commentaren]** Indien gecontroleerd, sta vertrouwde op lidmoderatoren toe om commentaren te ontkennen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Sluit/open Commentaren]** opnieuw als gecontroleerd, sta vertrouwde op lidmoderatoren toe om commentaren te sluiten en opnieuw te openen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Opmerkingen]** markeren Als deze optie is ingeschakeld, kunnen bezoekers opmerkingen als ongepast markeren. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Lijst]** met redenen voor vlag Geef bezoekers de mogelijkheid om in een vervolgkeuzelijst de reden te kiezen waarom een opmerking niet geschikt is als gemarkeerd. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Reden]** voor aangepaste markering Als dit selectievakje is ingeschakeld, kunnen bezoekers hun eigen reden opgeven om een opmerking te markeren als ongeschikt. De optie Standaard is uitgeschakeld.

* **[!UICONTROL De Drempel]** van de modernisering gaat het aantal tijden in een commentaar moet door bezoekers worden gemarkeerd alvorens de moderatoren op de hoogte worden gebracht. De standaardwaarde is één keer (**1**).

* **[!UICONTROL Markeringslimiet]** Voer het aantal keren in dat een opmerking moet worden gemarkeerd voordat deze wordt verborgen in de openbare weergave. Dit getal moet groter zijn dan of gelijk zijn aan de **moderatiedrempel**. De standaardwaarde is 5.

## Additional Information {#additional-information}

Meer informatie vindt u op de pagina Essentiële elementen [van](essentials-file-library.md) bestandsbibliotheek voor ontwikkelaars.

Voor moderatie van geposte onderwerpen en commentaren, zie het [Modereren van Door Gebruiker Gegenereerde Inhoud](moderate-ugc.md).

Zie Door gebruiker gegenereerde inhoud [](tag-ugc.md)labelen voor informatie over het labelen van geposte onderwerpen en opmerkingen.
