---
title: Inleiding tot het publiceren van formulieren op een portal
seo-title: Introduction to publishing forms on a portal
description: AEM Forms biedt componenten die u kunt gebruiken om uw formulierportal te maken. In deze artikelen wordt u kennisgemaakt met de beschikbare onderdelen van de portal Formulieren.
seo-description: AEM Forms provides with components that you can use to build your forms portal. This articles introduces you to the available forms portal components.
uuid: 96aa4fe2-a111-4675-a33c-7dee8b82cbc2
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: publish
discoiquuid: 44871fe1-ddc9-492c-8784-5df3ca392f9b
exl-id: a91e23e8-339d-4090-9872-2e066ab66590
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1091'
ht-degree: 0%

---

# Inleiding tot het publiceren van formulieren op een portal {#introduction-to-publishing-forms-on-a-portal}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Overzicht van AEM Forms Portal-componenten {#aem-forms-portal-components-overview}

In een typisch vorm-centric portaalplaatsingsscenario, vormen ontwikkeling en poortontwikkeling zijn twee gescheiden activiteiten. Terwijl formulierontwerpers formulieren ontwerpen en opslaan in een gegevensopslagruimte, maken webontwikkelaars een webtoepassing om formulieren weer te geven en de verzending van formulieren af te handelen. Forms wordt naar de weblaag gekopieerd omdat er geen communicatie is tussen de formulieropslagplaats en de webtoepassing.

Dergelijke scenario&#39;s leiden vaak tot beheerproblemen en productievertragingen. Als er bijvoorbeeld een nieuwere versie van een formulier beschikbaar is in de gegevensopslagruimte, moet u het formulier op de weblaag vervangen, de webtoepassing wijzigen en het formulier opnieuw distribueren op de openbare site. Als u de webtoepassing opnieuw implementeert, kan dit leiden tot serverdowntime. De serverdowntime is doorgaans een geplande activiteit en daarom kunnen de wijzigingen niet onmiddellijk naar de openbare site worden doorgevoerd.

AEM Forms biedt portalcomponenten die de beheerkosten en productievertragingen verminderen. Met deze componenten kunnen webontwikkelaars een formulierportal maken en aanpassen op websites die zijn gemaakt met Adobe Experience Manager (AEM).

![AEM Forms Portal](assets/aem-forms-portal.png)

Met de onderdelen van het formulierportaal kunt u de volgende functionaliteit toevoegen:

* Formulieren weergeven in aangepaste indelingen. De lay-outs Lijstweergave, Kaart en Deelvensterweergave zijn beschikbaar in het vak. U kunt uw eigen aangepaste lay-outs maken.
* Hiermee kunt u aangepaste metagegevens en aangepaste handelingen weergeven terwijl u deze weergeeft.
* Formulieren weergeven die door de gebruikersinterface van AEM Forms zijn gepubliceerd op de publicatie-instantie waar Forms Portal-componenten worden gebruikt.
* Eindgebruikers toestaan formulieren zowel in HTML- als in PDF-indeling te genereren.
* Gebruik een aangepast HTML-profiel om formulieren te genereren.
* U kunt zoeken op formulieren op basis van verschillende criteria inschakelen, zoals formuliereigenschappen, metagegevens en codes.
* Formuliergegevens verzenden naar een servlet.
* Gebruik aangepaste CSS om het uiterlijk van de portal aan te passen.
* Koppelingen naar formulieren maken.
* Hier worden concepten en verzendingen weergegeven die betrekking hebben op een adaptief formulier dat door de eindgebruiker is gemaakt.

## Beschikbare AEM Forms Portal-onderdelen {#available-aem-forms-portal-components}

AEM Forms biedt de volgende poortcomponenten uit het vak, gegroepeerd onder **Document Services** en **Voorspellingen voor documentservices** componentgroepen:

### Zoeken en registreren {#search-amp-lister}

Met de component Zoeken en registreren kunt u formulieren vanuit de formulieropslagplaats op uw portalpagina weergeven en configuratieopties voor het weergeven van formulieren op basis van opgegeven criteria. U kunt hiermee ook zoekcriteria opgeven waarmee gebruikers van uw portal kunnen zoeken in de lijst met formulieren.

### Concepten en verzendingen {#drafts-amp-submissions}

In het onderdeel Zoeken en opslaan worden formulieren weergegeven die door de auteur van Forms openbaar zijn gemaakt, maar in het onderdeel Concepten en verzendingen worden formulieren weergegeven die zijn opgeslagen als concept voor het later invullen van formulieren en die zijn verzonden. Deze component verstrekt gepersonaliseerde ervaring aan om het even welke het programma geopende gebruiker.

### Koppeling {#link}

Met de component Koppeling kunt u overal op de pagina een koppeling naar een formulier maken. Overweeg een scenario waarin u een trainingsprogramma aanbiedt en u wilt dat uw gebruikers een formulier indienen om zich te registreren voor de training. Op uw website hebt u de programmagegevens geplaatst. Onder de details wilt u een koppeling naar het registratieformulier opgeven. De component Link kan u helpen die koppeling te maken.

## Forms Portal Workflow {#forms-portal-workflow}

Met Forms Portal kunt u formulieren vanuit de formulieropslagplaats op uw portalpagina weergeven. U kunt hiermee ook zoekcriteria opgeven waarmee gebruikers van uw portal kunnen zoeken in de lijst met formulieren. U kunt ook de component Concepten en verzendingen gebruiken om formulieren weer te geven die zijn opgeslagen als concept voor het later invullen van formulieren en die zijn verzonden. U moet een bepaalde set bewerkingen uitvoeren voordat deze functies beschikbaar komen op een sitepagina. Voer de stappen in de vermelde opeenvolging uit om de componenten en respectieve functionaliteit op een plaatspagina beschikbaar te maken:

1. **Forms Portal-componenten inschakelen**: De onderdelen van de portal Formulieren zijn niet beschikbaar voor gebruik. [De componenten van AEM sidekick inschakelen](/help/forms/using/enabling-forms-portal-components.md) voor een AEM Sites-pagina.
1. **Formulieren weergeven op een pagina (pagina Formulierportal maken):** U kunt formulieren weergeven op zowel AEM Sites- als niet-AEM sitepagina&#39;s. De lijst bevat formulieren die beschikbaar zijn in de publicatie-instantie. Een gebruiker kan formulieren openen en invullen. Wanneer een gebruiker een formulier opent, wordt er een nieuw exemplaar van het formulier gemaakt:

   1. **Formulieren weergeven op een AEM Sites-pagina**: Voeg de **[Zoeken en registreren](/help/forms/using/creating-form-portal-page.md)** component aan de pagina en vorm de **[Lijstvenster](/help/forms/using/creating-form-portal-page.md#p-list-pane-p)** hiermee kunt u formulieren op een pagina weergeven. Voeg en vorm toe **[Zoekvenster](/help/forms/using/creating-form-portal-page.md#search-pane)** aan de **Zoeken en registreren** om ook zoekfunctionaliteit aan de pagina toe te voegen. De pagina met de taalcomponent voor formulieren wordt ook wel [pagina Formulierportal](/help/forms/using/creating-form-portal-page.md).
   1. **Formulieren weergeven op een niet-AEM Sites-pagina:** Gebruik de [zoekAPI&#39;s voor formulierportal](/help/forms/using/listing-forms-webpage-using-apis.md) om formulieren op niet-AEM Sites-pagina&#39;s te zoeken, op te halen en weer te geven.

1. **Concepten en verzonden formulieren weergeven op een pagina van een formulierportal**: Voeg de component Concepten en verzendingen toe aan en configureer deze op de pagina Formulierportal. De component bevat een lijst met alle formulieren in het concept en de formulieren die al zijn verzonden.

   Als u een ingediend adaptief formulier wilt weergeven op het tabblad Verzending, stelt u de optie **Handeling verzenden** tot **[Forms Portal-verzendactie](https://helpx.adobe.com/in/experience-manager/6-4/forms/using/configuring-submit-actions.html).** U kunt ook de optie Forms Portal verzenden inschakelen. Wanneer een gebruiker het formulier verzendt, wordt het formulier toegevoegd aan het tabblad Verzending.

1. **Opslag configureren voor het concept en de verzonden formuliergegevens:** Concepten en verzendgegevens worden standaard opgeslagen in de AEM-opslagplaats. In een productieomgeving wordt aanbevolen geen concept- of verzonden formuliergegevens in AEM opslagplaats op te slaan. [Formulierportal-component configureren om gegevens op te slaan op een beveiligde locatie](/help/forms/using/draft-submission-component.md#customizing-the-storage).
1. **(Optioneel) De onderdelen van de portal Formulieren aanpassen:**  [Sjablonen voor pagina&#39;s van uw portal Formulieren aanpassen](/help/forms/using/customizing-templates-forms-portal-components.md) om de componenten een duidelijk uiterlijk te geven.
1. **(Optioneel) Voeg aangepaste metagegevens toe aan formulieren:** [Aangepaste metagegevens toevoegen aan formulieren](/help/forms/using/customizing-templates-forms-portal-components.md) om aanbiedingen en zoekresultaten te verbeteren.
1. **De pagina Formulierportal publiceren:** De pagina Formulierportal is nu gereed. Publiceer de pagina.

## Verwante artikelen {#related-articles}

* [Formulierportonderdelen inschakelen](/help/forms/using/enabling-forms-portal-components.md)
* [Pagina Formulierportal maken](/help/forms/using/creating-form-portal-page.md)
* [Formulieren op een webpagina weergeven met API&#39;s](/help/forms/using/listing-forms-webpage-using-apis.md)
* [Concepten en verzendingscomponent gebruiken](/help/forms/using/draft-submission-component.md)
* [Opslag van concepten en verzonden formulieren aanpassen](/help/forms/using/draft-submission-component.md#customizing-the-storage)
* [Voorbeeld voor het integreren van concepten en verzendingen in de database](https://helpx.adobe.com/in/experience-manager/6-4/forms/using/integrate-draft-submission-database.html)

* [Sjablonen aanpassen voor componenten van een formulierportal](/help/forms/using/customizing-templates-forms-portal-components.md)
* [Inleiding tot het publiceren van formulieren op een portal](/help/forms/using/introduction-publishing-forms.md)
