---
title: Deelnemen aan workflows
seo-title: Participating in Workflows
description: Workflows bevatten doorgaans stappen die vereisen dat een persoon een activiteit op een pagina of element uitvoert. De werkstroom selecteert een gebruiker of groep om de activiteit uit te voeren en wijst een het werkpunt aan die persoon of groep toe.
seo-description: Workflows typically include steps that require a person to perform an activity on a page or asset. The workflow selects a user or group to perform the activity and assigns a work item to that person or group.
uuid: 04dcc8f2-dc11-430f-b0ae-47ef2cb069a2
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: site-features
discoiquuid: 1d7a4889-82c5-4096-8567-8f66215a8458
exl-id: a4f0f0c4-3050-4348-8d51-2ca91839208c
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '579'
ht-degree: 3%

---

# Deelnemen aan workflows{#participating-in-workflows}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Workflows bevatten doorgaans stappen die vereisen dat een persoon een activiteit op een pagina of element uitvoert. De werkstroom selecteert een gebruiker of groep om de activiteit uit te voeren en wijst een het werkpunt aan die persoon of groep toe.

## Uw werkitems verwerken {#processing-your-work-items}

U kunt de volgende handelingen uitvoeren om een werkitem te verwerken:

* **Voltooid**

   U kunt een item voltooien zodat de workflow naar de volgende stap kan gaan.

* **Delegeren**

   Als een stap aan u is toegewezen, maar om het even welke reden u geen actie kunt ondernemen, kunt u de stap aan een andere gebruiker of een groep delegeren.

   De gebruikers die voor delegatie beschikbaar zijn hangen af van wie het het werkpunt werd toegewezen:

   * Als het het werkpunt aan een groep werd toegewezen, zijn de groepsleden beschikbaar.
   * Als het het werkpunt aan een groep werd toegewezen en dan aan een gebruiker werd afgevaardigd, zijn de groepsleden en de groep beschikbaar.
   * Als het het werkpunt aan één enkele gebruiker werd toegewezen, kan het het werkpunt niet worden afgevaardigd.

* **Stap terug**

   Als u ontdekt dat een stap, of een reeks stappen, moet worden herhaald kunt u achteruit stappen. Op deze manier kunt u een stap selecteren die eerder in de workflow is opgetreden voor opwerking. De werkstroom keert aan de stap terug u specificeert, dan gaat van daar te werk.

## Deelnemen aan een workflow {#participating-in-a-workflow}

### Meldingen van toegewezen workflowhandelingen {#notifications-of-assigned-workflow-actions}

Wanneer u een werkitem wordt toegewezen (bijvoorbeeld **Inhoud goedkeuren**), worden verschillende waarschuwingen en/of meldingen weergegeven:

* De **Status** De kolom van de console Websites wijst erop wanneer een pagina in een werkschema is:

   ![workflowstatus-1](assets/workflowstatus-1.png)

* Wanneer u, of een groep die u tot behoort, een het werkpunt als deel van een werkschema wordt toegewezen, verschijnt het het werkpunt in uw Inbox van het Werkschema van de AEM.

   ![workflowinbox](assets/workflowinbox.png)

### Een deelnemersstap voltooien {#completing-a-participant-step}

Nadat u de aangegeven actie hebt uitgevoerd, kunt u het werkitem voltooien, zodat de workflow kan worden voortgezet. Voer de volgende procedure uit om het werkitem te voltooien.

1. Selecteer de workflowstap en klik op de knop **Voltooid** in de bovenste navigatiebalk.
1. Selecteer in het dialoogvenster dat wordt weergegeven de optie **Volgende stap**; dat wil zeggen, de volgende stap die moet worden uitgevoerd. In een vervolgkeuzelijst worden alle geschikte doelen weergegeven. A **Opmerking** kan ook worden ingevoerd.

   ![workflowvoltooid](assets/workflowcomplete.png)

   Het aantal vermelde stappen is afhankelijk van het ontwerp van het workflowmodel.

1. Klikken **OK** om de actie te bevestigen.

### Een deelnemersstap delegeren {#delegating-a-participant-step}

Gebruik de volgende procedure om een het werkpunt te delegeren.

1. Klik op de knop **Delegeren** in de bovenste navigatiebalk.
1. Selecteer in het dialoogvenster de vervolgkeuzelijst **Gebruiker** om het het werkpunt aan te delegeren. U kunt ook een **Opmerking**.

   ![workflowgedelegeerde](assets/workflowdelegate.png)

1. Klikken **OK** om de actie te bevestigen.

### Stap terug op een Stap van de Deelnemer uitvoeren {#performing-step-back-on-a-participant-step}

Gebruik de volgende procedure om terug te gaan.

1. Klik op de knop Stap terug in de bovenste navigatiebalk.
1. Selecteer in het dialoogvenster dat wordt weergegeven de optie Vorige stap; dat wil zeggen, de volgende stap uitvoeren - ook al is het een stap die eerder in de workflow plaatsvindt. In een vervolgkeuzelijst worden alle geschikte doelen weergegeven.

   ![screen_shot_2018-08-10at155325](assets/screen_shot_2018-08-10at155325.jpg)

1. Klik op OK om de handeling te bevestigen.
