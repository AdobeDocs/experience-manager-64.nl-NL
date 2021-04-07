---
title: Functie voor activiteitsstromen
seo-title: Functie voor activiteitsstromen
description: Activiteiten van een aangemeld lid van de gemeenschap
seo-description: Activiteiten van een aangemeld lid van de gemeenschap
uuid: 8a05a5ed-0edf-4528-a145-f9dc37d10247
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: ccaebb4c-cc1c-4ee7-b080-99667f348427
exl-id: e62b7c0d-5004-4672-9fdc-566ece2785c9
translation-type: tm+mt
source-git-commit: bd94d3949f0117aa3e1c9f0e84f7293a5d6b03b4
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 0%

---

# Functie voor activiteitsstromen {#activity-streams-feature}

## Inleiding {#introduction}

De activiteiten van een ondertekend lid van de gemeenschap, zoals het posten aan een forum of blog, worden verzameld in een stroom die op verschillende manieren door configuratie van `Activity Streams` component kan worden gefiltreerd en getoond.

De mogelijkheid om te volgen voegt nog een weergave van activiteiten toe wanneer leden van de gemeenschap belangenverklaringen volgen of de activiteiten van andere leden van de gemeenschap volgen.

In deze sectie van de documentatie wordt beschreven

* De component Activiteitsstromen toevoegen aan een AEM-site
* Configuratie-instellingen voor de component Activiteitenstromen

## Activiteitsstromen toevoegen aan een pagina {#adding-activity-streams-to-a-page}

Als u een component `Activity Streams` in de ontwerpmodus aan een pagina wilt toevoegen, gebruikt u de componentbrowser om te zoeken naar

* `Communities / Activity Streams`

en sleep het naar de juiste plaats op een pagina waar de activiteitenstromen moeten verschijnen.

Voor noodzakelijke informatie, bezoek [de Grondbeginselen van Componenten van Gemeenschappen](basics.md).

Wanneer de [vereiste client-side bibliotheken](essentials-activities.md#essentials-for-client-side) worden opgenomen, wordt de `Activity Streams`-component op deze manier weergegeven:

![chlimage_1-195](assets/chlimage_1-195.png)

## Activiteitenstromen configureren {#configuring-activity-streams}

Selecteer de geplaatste `Activity Streams` component en selecteer `Configure` pictogram dat het Edit dialoog opent.

![chlimage_1-196](assets/chlimage_1-196.png)

Geef onder het tabblad **[!UICONTROL User Activities]** op welke activiteiten u wilt weergeven:

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

## Na weergave {#following-view}

Componenten moeten worden geconfigureerd om het volgende in te schakelen. Functies die het volgende toestaan, zijn [blog](blog-feature.md), [forum](forum.md), [QnA](working-with-qna.md), [agenda](calendar.md), [bestandsbibliotheek](file-library.md) en [commentaren](comments.md).

![chlimage_1-198](assets/chlimage_1-198.png)

Met de knop **Follow** kunt u vermeldingen als activiteiten, [meldingen](notifications.md) en/of [abonnementen](subscriptions.md) volgen. Telkens wanneer de **Follow** knoop wordt geselecteerd, is het mogelijk om of van een selectie van een knevel te voorzien. De `Email Subscriptions` selectie is slechts aanwezig wanneer gevormd.

Als een methode van het volgende wordt geselecteerd, verandert de tekst van de knoop in **volgend**. Voor het gemak, is het mogelijk om `Unfollow All` te selecteren om alle methodes van een knevel te voorzien.

De **Follow** knoop zal verschijnen:

* Wanneer het bekijken van het profiel van een ander lid
* Op een hoofdpagina met functies, zoals forums, QnA en blogs
   * Volg alle activiteiten voor die algemene functie

* Voor een specifiek bericht, zoals een forumonderwerp, een QnA-vraag of een blogartikel
   * Hiermee wordt alle activiteit voor die specifieke vermelding gevolgd

## Aanvullende informatie {#additional-information}

Meer informatie vindt u op de pagina [Activiteitsstromen Essentials](essentials-activities.md) voor ontwikkelaars.
