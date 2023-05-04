---
title: Functie bestandsbibliotheek
seo-title: File Library Feature
description: Met de functie Bestandsbibliotheek kunnen aangemelde sitebezoekers bestanden uploaden, beheren en downloaden
seo-description: The File Library feature lets signed-in site visitors upload, manage, and download files
uuid: 7da94703-8334-4c02-ba2a-55b5cde22e6c
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: cdcae09f-c3cb-471e-863f-b33130e9df0f
exl-id: c72b246d-442e-4841-810d-1045e83f60f9
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '639'
ht-degree: 0%

---

# Functie bestandsbibliotheek {#file-library-feature}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Inleiding {#introduction}

De functie voor bestandsbibliotheek biedt een plaats voor ingetekende sitebezoekers (leden van de community) voor het uploaden, beheren en downloaden van bestanden binnen de site van de gebruikersgemeenschap.

In deze sectie van de documentatie wordt beschreven

* De functie voor de bestandsbibliotheek toevoegen aan een AEM site
* De montages van de configuratie voor de `File Library` component

## Een bestandsbibliotheek toevoegen aan een pagina {#adding-a-file-library-to-a-page}

Als u een `File Library` naar een pagina in de modus Schrijver, zoek de component

* `Communities / File Library`

en sleep het naar de juiste plaats op een pagina.

Voor de nodige informatie gaat u naar [Grondbeginselen van Community-componenten](basics.md).

Wanneer de [vereiste clientbibliotheken](essentials-file-library.md#essentials-for-client-side) worden opgenomen, is dit hoe `File Library` wordt weergegeven:

![chlimage_1-430](assets/chlimage_1-430.png)

## Bestandsbibliotheek configureren {#configuring-file-library}

Selecteer de geplaatste `File Library` te openen en de component te selecteren `Configure` wordt het dialoogvenster Bewerken geopend.

![chlimage_1-431](assets/chlimage_1-431.png) ![chlimage_1-432](assets/chlimage_1-432.png)

### Tabblad Opmerkingen {#comments-tab}

Onder de **[!UICONTROL Comments]** , geeft u op of en hoe opmerkingen voor geüploade bestanden worden weergegeven:

* **[!UICONTROL Allow Comments on Files]**
Als deze optie is ingeschakeld, kunt u opmerkingen op geüploade bestanden toestaan. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Comments Per Page]**
Hiermee beperkt u het aantal opmerkingen dat per pagina wordt weergegeven en het aantal reacties dat wordt weergegeven. Standaard is 
**10**.

* **[!UICONTROL Max File Size]**
Met deze waarde beperkt u de grootte van het geüploade bestand. Standaardlimiet is 104857600 (10 MB).

* **[!UICONTROL Max Message Length]**
Maximumaantal tekens dat in het tekstvak kan worden ingevoerd. De standaardwaarde is 4096 tekens.

* **[!UICONTROL Allowed File Types]**
Een door komma&#39;s gescheiden lijst met bestandsextensies met het &quot;punt&quot;-scheidingsteken. Bijvoorbeeld: .jpg, .jpeg, .png, .doc, .docx, .pdf. Als er bestandstypen worden opgegeven, zijn deze niet toegestaan. De standaardinstelling is niet opgegeven, zodat alle bestandstypen zijn toegestaan.

* **[!UICONTROL Rich Text Editor]**
Als deze optie is ingeschakeld, kunnen opmerkingen worden ingevoerd met een markering. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Delete Comments]**
Als deze optie is ingeschakeld, mogen gebruikers hun eigen opmerkingen verwijderen. Standaard is ingeschakeld.

* **[!UICONTROL Allow Tagging]**
Als deze optie is ingeschakeld, wordt de mogelijkheid ingeschakeld om een tag aan het bestand toe te voegen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allowed Namespaces]**
Als Tags toestaan is ingeschakeld, worden de beschikbare tags beperkt tot de geselecteerde naamruimten. Als er geen optie is geselecteerd, zijn alle opties toegestaan. Standaard zijn alle naamruimten.

* **[!UICONTROL Suggestion Limit]**
Als u Tags toestaan inschakelt, beperkt deze instelling het aantal voorgestelde tags dat wordt weergegeven. Indien ingesteld op -1, is er geen limiet. De standaardwaarde is -1.

* **[!UICONTROL Allow Voting]**
Als deze optie is ingeschakeld, wordt de mogelijkheid om voor een bestand te stemmen ingeschakeld. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Following]**
Indien ingeschakeld, neemt u de volgende functie voor blogartikelen op, waardoor leden kunnen worden [aangemeld](notifications.md) van nieuwe posten. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Allow Threaded Replies]**
Als deze optie is ingeschakeld, kunt u reacties op geposte opmerkingen toestaan. De optie Standaard is uitgeschakeld.

### Tabblad Gebruikersmodernisering {#user-moderation-tab}

Onder de **[!UICONTROL User Moderation]** tab, configureer de moderatie van opmerkingen als opmerkingen zijn toegestaan:

* **[!UICONTROL Pre-Moderation]**
Als deze optie is ingeschakeld, moeten opmerkingen worden goedgekeurd voordat ze op een publicatiesite worden weergegeven. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Delete Comments]**
Als deze optie is ingeschakeld, kan de bezoeker die de opmerking heeft geplaatst deze verwijderen. Standaard is ingeschakeld.

* **[!UICONTROL Deny Comments]**
Als deze optie is ingeschakeld, staat u vertrouwde moderatoren toe opmerkingen te weigeren. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Close / Reopen Comments]**
Als deze optie is ingeschakeld, moet u vertrouwde moderatoren van leden toestaan opmerkingen te sluiten en opnieuw te openen. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Flag Comments]**
Als deze optie is ingeschakeld, kunnen bezoekers opmerkingen als ongeschikt markeren. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Flag Reason List]**
Als deze optie is ingeschakeld, kunnen bezoekers in een vervolgkeuzelijst de reden kiezen waarom een opmerking als onjuist is gemarkeerd. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Custom Flag Reason]**
Als deze optie is ingeschakeld, kunnen bezoekers hun eigen reden opgeven om een opmerking als ongeschikt te markeren. De optie Standaard is uitgeschakeld.

* **[!UICONTROL Moderation Threshold]**
Voer het aantal keren in dat een opmerking moet worden gemarkeerd door bezoekers voordat moderatoren op de hoogte worden gesteld. Standaard is dit één keer (
**1**).

* **[!UICONTROL Flagging Limit]**
Voer het aantal keren in dat een opmerking moet worden gemarkeerd voordat deze wordt verborgen in de openbare weergave. Dit getal moet groter zijn dan of gelijk zijn aan het 
**Moderniseringsdrempel**. De standaardwaarde is 5.

## Aanvullende informatie {#additional-information}

Meer informatie is te vinden op de [Essentiële elementen bestandsbibliotheek](essentials-file-library.md) pagina voor ontwikkelaars.

Voor moderatie van geposte onderwerpen en commentaren, zie [Door gebruiker gegenereerde inhoud modereren](moderate-ugc.md).

Voor het etiketteren van geposte onderwerpen en commentaren, zie [Door gebruiker gegenereerde inhoud labelen](tag-ugc.md).
