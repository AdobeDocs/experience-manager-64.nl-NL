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
translation-type: tm+mt
source-git-commit: 3d2b91565e14e85e9e701663c8d0ded03e5b430c
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 0%

---


# Functie voor activiteitsstromen {#activity-streams-feature}

## Inleiding {#introduction}

De activiteiten van een getekend lid van de gemeenschap, zoals posten op een forum of blog, worden verzameld in een stream die op verschillende manieren kan worden gefilterd en weergegeven door de configuratie van de `Activity Streams` component.

De mogelijkheid om te volgen voegt nog een weergave van activiteiten toe wanneer leden van de gemeenschap belangenverklaringen volgen of de activiteiten van andere leden van de gemeenschap volgen.

In deze sectie van de documentatie wordt beschreven

* De component Activiteitsstromen toevoegen aan een AEM-site
* Configuratie-instellingen voor de component Activiteitenstromen

## Activiteitsstromen toevoegen aan een pagina {#adding-activity-streams-to-a-page}

Als u een `Activity Streams` component in de ontwerpmodus aan een pagina wilt toevoegen, gebruikt u de componentbrowser om te zoeken naar

* `Communities / Activity Streams`

en sleep het naar de juiste plaats op een pagina waar de activiteitenstromen moeten verschijnen.

Ga voor de benodigde informatie naar [Community Components Basics](basics.md).

Wanneer de [vereiste client-side bibliotheken](essentials-activities.md#essentials-for-client-side) worden opgenomen, wordt de `Activity Streams` component als volgt weergegeven:

![chlimage_1-195](assets/chlimage_1-195.png)

## Activiteitenstromen configureren {#configuring-activity-streams}

Selecteer de geplaatste `Activity Streams` component die u wilt openen en selecteer het `Configure` pictogram waarmee het dialoogvenster Bewerken wordt geopend.

![chlimage_1-196](assets/chlimage_1-196.png)

Geef onder het **[!UICONTROL User Activities]** tabblad op welke activiteiten u wilt weergeven:

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

Componenten moeten worden geconfigureerd om het volgende in te schakelen. Functies die het volgende toestaan, zijn [blog](blog-feature.md), [forum](forum.md), [QnA](working-with-qna.md), [agenda](calendar.md), [bestandsbibliotheek](file-library.md)[](comments.md)en commentaren.

![chlimage_1-198](assets/chlimage_1-198.png)

Met de knop **Volg** kunt u items opvolgen als activiteiten, [meldingen](notifications.md)en/of [abonnementen](subscriptions.md). Telkens wanneer de knop **Volgen** is geselecteerd, kunt u een selectie in- of uitschakelen. De `Email Subscriptions` selectie is alleen aanwezig als deze is geconfigureerd.

Als er een methode van het volgende is geselecteerd, verandert de tekst van de knop in **Volgende**. Voor het gemak is het mogelijk om alle methoden uit `Unfollow All` te schakelen.

De knop **Volg** wordt weergegeven:

* Wanneer het bekijken van het profiel van een ander lid
* Op een hoofdpagina met functies, zoals forums, QnA en blogs
   * Volg alle activiteiten voor die algemene functie

* Voor een specifiek bericht, zoals een forumonderwerp, een QnA-vraag of een blogartikel
   * Hiermee wordt alle activiteit voor die specifieke vermelding gevolgd

## Additional Information {#additional-information}

Meer informatie vindt u op de pagina [Activiteitenstromen](essentials-activities.md) voor ontwikkelaars.
