---
title: Aanpassing en doelgerichtheid van inhoud
seo-title: Aanpassing en doelgerichtheid van inhoud
description: Leer hoe AEM persoonlijke inhoud kan maken
seo-description: Leer hoe AEM persoonlijke inhoud kan maken
uuid: 3a1aaa3d-5f57-4fb7-a4be-523f0d274b79
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: personalization
discoiquuid: 850da0da-f7c3-4dd7-bb06-404c14a2a791
translation-type: tm+mt
source-git-commit: 80395c4695b326474f9ae0e73caa075a5782eaf6
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 0%

---


# Aanpassing en doelgerichtheid van inhoud {#personalization}

## Aanpassing en doelgerichtheid van inhoud {#personalization-and-content-targeting}

AEM biedt een kader van instrumenten voor het ontwerpen van gerichte inhoud en het presenteren van persoonlijke ervaringen.

## Doelmodus {#targeting-mode}

[Door de auteur wordt de inhoud](/help/sites-authoring/content-targeting-touch.md) bepaald met de doelmodus van AEM. De gerichte wijze en de component van het Doel verstrekken hulpmiddelen om inhoud voor de ervaringen van uw marketing activiteiten tot stand te brengen.

## Activiteiten {#activities}

Met de activiteiten worden uw marketingactiviteiten gedefinieerd en georganiseerd. De activiteiten omvatten het publiek dat u richt, en de periode waarin het richten wordt toegepast.

Bijvoorbeeld, omvat de het productcatalogus van Wij.Retail meters die aandacht op seizoensgebonden producten richten. De activiteit van de Sport van de Zomer bepaalt de marketing segmenten die de telers tijdens zomermaanden richten.

Met de activiteiten wordt ook aangegeven welke [doelengine](/help/sites-authoring/personalization.md#targeting-engine) uw pagina&#39;s gebruiken.

Gebruik de [Activites-console](/help/sites-authoring/activitylib.md) om de activiteiten voor uw merken te maken en te beheren. U kunt ook activiteiten maken terwijl u [doelinhoud](/help/sites-authoring/content-targeting-touch.md)ontwerpt.

## Ervaringen {#experiences}

Voor elke activiteit, bepaalt u één of meerdere ervaringen die het publiek identificeren dat u richt. AEM stelt u in staat de inhoud te beheren die elke ervaring omvat.

De soorten publiek zijn gebaseerd op marketing segmenten die of in AEM of Adobe Target worden gecreeerd. Wanneer een bezoeker een webpagina opent, bepaalt de paginalogica het publiek waartoe zij behoren en geeft deze de inhoud weer die u voor dat publiek hebt gemaakt.

Een activiteit definieert bijvoorbeeld ervaringen voor twee verschillende soorten publiek: vrouwen ouder dan 30 jaar en vrouwen jonger dan 30 jaar. Op de pagina Vrouwen van de website We.Retail staan verschillende producten voor elke ervaring.

U definieert ervaringen voor een activiteit. U kunt de console [van](/help/sites-authoring/activitylib.md#adding-editing-an-activity-using-the-activities-console) Activiteiten of het [richten wijze](/help/sites-authoring/content-targeting-touch.md#adding-and-removing-experiences-using-targeting-mode) gebruiken om ervaringen aan een activiteit toe te voegen.

## Aanbiedingen {#offers}

Een aanbieding is inhoud die op een plaats op een pagina voor een ervaring verschijnt. Gebruik verschillende aanbiedingen voor verschillende ervaringen om de doeltreffendheid van de inhoud voor uw publiek te maximaliseren.

De pagina Vrouwen van de voorbeeldwebsite We.Retail kan bijvoorbeeld aanbiedingen gebruiken als de laserafbeelding die boven aan de pagina wordt weergegeven. Een ander aanbod wordt gebruikt als taser voor vrouwen ouder dan 30 jaar en voor vrouwen jonger dan 30 jaar.

Gebruik de console [](/help/sites-authoring/offerlib.md) Aanbiedingen om aanbiedingen te creëren die u in veelvoudige ervaringen kunt gebruiken. Aanbiedingen voor eenmalig gebruik maken of aanbiedingen uit een aanbiedingsbibliotheek toevoegen wanneer u [doelinhoud](/help/sites-authoring/content-targeting-touch.md)ontwerpt.

## Richtingsmotor {#targeting-engine}

De doelengine is het mechanisme dat de logica voor doelgerichte inhoud aandrijft. [De activiteiten](/help/sites-authoring/activitylib.md) worden gevormd om één van twee te gebruiken richtend motoren die beschikbaar zijn: AEM en Adobe Target.

### AEM {#aem}

AEM verstrekt ingebouwde het richten motor die paginaverzoeken verwerkt en de inhoud aan vertoning bepaalt. Wanneer u de AEM doelengine gebruikt, kunt u alleen segmenten gebruiken die zijn gemaakt in AEM voor het definiëren van het publiek van uw ervaringen.

### Adobe Target {#adobe-target}

De Adobe Target-engine voor doelwitten zorgt ervoor dat informatie die tijdens paginabezoeken is verzameld, wordt bijgehouden in Adobe Target.

* Wanneer u deze doelengine gebruikt, gebruikt u de segmenten die u uit Adobe Target importeert om het publiek voor uw ervaringen te definiëren.
* Activiteiten die gebruikmaken van de Adobe Target-engine worden [gesynchroniseerd met Target](/help/sites-authoring/activitylib.md#synchronizing-activities-with-adobe-target).

U kunt deze engine gebruiken wanneer u deze hebt [geïntegreerd met Adobe Target](/help/sites-administering/opt-in.md).
