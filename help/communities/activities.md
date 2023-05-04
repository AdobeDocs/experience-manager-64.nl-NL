---
title: Functie voor activiteitsstromen
seo-title: Activity Streams Feature
description: Activiteiten van een aangemeld lid van de gemeenschap
seo-description: Activities of a signed-in community member
uuid: 8a05a5ed-0edf-4528-a145-f9dc37d10247
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: ccaebb4c-cc1c-4ee7-b080-99667f348427
exl-id: e62b7c0d-5004-4672-9fdc-566ece2785c9
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 0%

---

# Functie voor activiteitsstromen {#activity-streams-feature}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Inleiding {#introduction}

De activiteiten van een getekend lid van de gemeenschap, zoals posten op een forum of blog, worden verzameld in een stream die op verschillende manieren kan worden gefilterd en weergegeven via de configuratie van de `Activity Streams` component.

De mogelijkheid om te volgen voegt nog een weergave van activiteiten toe wanneer leden van de gemeenschap belangenverklaringen volgen of de activiteiten van andere leden van de gemeenschap volgen.

In deze sectie van de documentatie wordt beschreven

* De component Activiteitsstromen toevoegen aan een AEM-site
* Configuratie-instellingen voor de component Activiteitenstromen

## Activiteitsstromen toevoegen aan een pagina {#adding-activity-streams-to-a-page}

Als u een `Activity Streams` van een component aan een pagina op auteurswijze, gebruik componentenbrowser om van

* `Communities / Activity Streams`

en sleep het naar de juiste plaats op een pagina waar de activiteitenstromen moeten verschijnen.

Voor de nodige informatie gaat u naar [Grondbeginselen van Community-componenten](basics.md).

Wanneer de [vereiste clientbibliotheken](essentials-activities.md#essentials-for-client-side) worden opgenomen, is dit hoe `Activity Streams` wordt weergegeven:

![chlimage_1-195](assets/chlimage_1-195.png)

## Activiteitenstromen configureren {#configuring-activity-streams}

Selecteer de geplaatste `Activity Streams` te openen en de component te selecteren `Configure` wordt het dialoogvenster Bewerken geopend.

![chlimage_1-196](assets/chlimage_1-196.png)

Onder de **[!UICONTROL User Activities]** tabblad, geeft u op welke activiteiten moeten worden weergegeven:

![chlimage_1-197](assets/chlimage_1-197.png)

* **[!UICONTROL Max number of activities]**
Aantal weer te geven activiteiten
* **[!UICONTROL Stream Resource Path]**
Blanco laten om standaard in te stellen op de communitysite of -groep. Het pad naar de streambron identificeert de bron van activiteiten. De standaardwaarde is leeg.
* **[!UICONTROL Display User Activities View]**
indien deze optie is ingeschakeld , zal op de activiteitenpagina een tabblad staan waarop de activiteiten worden gefilterd op basis van de activiteiten die binnen de gemeenschap door het huidige lid worden gegenereerd . Standaard is ingeschakeld.
* **[!UICONTROL Display All Activities View]**
Als deze optie is ingeschakeld, bevat de pagina met activiteiten een tabblad dat alle activiteiten bevat die zijn gegenereerd binnen de gemeenschap waartoe het huidige lid toegang heeft. Standaard is ingeschakeld.
* **[!UICONTROL Display Following View]**
Als deze optie is ingeschakeld, bevat de pagina met activiteiten een tabblad waarop de activiteiten worden gefilterd op basis van de activiteiten die het huidige lid volgt. Standaard is ingeschakeld.

## Volgende weergave {#following-view}

Componenten moeten worden geconfigureerd om het volgende in te schakelen. Functies die het volgende toestaan, zijn [blog](blog-feature.md), [forum](forum.md), [QnA](working-with-qna.md), [kalender](calendar.md), [bestandsbibliotheek](file-library.md), en [opmerkingen](comments.md).

![chlimage_1-198](assets/chlimage_1-198.png)

De **Volg** button biedt een manier om inzendingen te volgen als activiteiten, [meldingen](notifications.md), en/of [abonnementen](subscriptions.md). Elke keer als **Volg** is geselecteerd, is het mogelijk om een selectie in of uit te schakelen. De `Email Subscriptions` selectie is alleen aanwezig als dit is geconfigureerd.

Als een van de volgende methoden is geselecteerd, verandert de tekst van de knop in **volgende**. Voor het gemak is het mogelijk om `Unfollow All` om alle methoden uit te schakelen.

De **Volg** wordt weergegeven:

* Wanneer het bekijken van het profiel van een ander lid
* Op een hoofdpagina met functies, zoals forums, QnA en blogs
   * Volg alle activiteiten voor die algemene functie

* Voor een specifiek bericht, zoals een forumonderwerp, een QnA-vraag of een blogartikel
   * Hiermee wordt alle activiteit voor die specifieke vermelding gevolgd

## Aanvullende informatie {#additional-information}

Meer informatie is te vinden op de [Essentiële elementen voor activiteitsstromen](essentials-activities.md) pagina voor ontwikkelaars.
