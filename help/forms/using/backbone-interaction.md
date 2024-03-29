---
title: Backbone-interactie
seo-title: Backbone interaction
description: Conceptuele informatie over het gebruik van backbone-JavaScript-modellen in de AEM Forms-werkruimte.
seo-description: Conceptual information about use of Backbone JavaScript models in AEM Forms workspace.
uuid: c70da848-e514-42bc-a59b-44a7c00aa529
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: d363eec3-172b-413e-9743-ed51804ea1e9
exl-id: f726cb73-732c-4893-bdb5-10ddcf4a340a
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 0%

---

# Backbone-interactie {#backbone-interaction}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Backbone is een bibliotheek die helpt bij het maken en volgen van MVC-architectuur in webtoepassingen. Het basisidee van Backbone is uw interface te organiseren in logische meningen, gesteund door modellen, die elk onafhankelijk kunnen worden bijgewerkt wanneer het model verandert, zonder het moeten de pagina opnieuw tekenen. Voor meer informatie over Backbone, zie [https://backbonejs.org](https://backbonejs.org/).

Enkele belangrijke concepten zijn:

**Backbone-model** Bevat gegevens, en de meeste logica met betrekking tot deze gegevens.

**Achtergrondweergave** Wordt gebruikt om de status van het corresponderende model weer te geven. Een backboneweergave gedraagt zich eigenlijk als een controller, luisterend naar gebruikersinterfacegebeurtenissen zoals klikken door de gebruiker of naar modelgebeurtenissen (zoals gewijzigde gegevens) en wijzigt de gebruikersinterface op de juiste wijze.

**HTML-sjabloon** Een omvattende sjabloon met plaatsaanduidingen die zijn gevuld door het model.

**AEM Forms-werkruimte** Bevat verschillende afzonderlijke componenten. Elke component:

* Vertegenwoordigt één logisch interface-element.
* Dit kan een verzameling van vergelijkbare componenten zijn.
* Opgemaakt uit het model van de Backbone, de mening van de Backbone, en malplaatje van de HTML.
* Bevat verwijzing naar de dienst.
* Bevat een verwijzing naar vereiste hulpprogramma&#39;s.

Wanneer een component wordt geïnitialiseerd, worden de volgende objecten gemaakt:

* Er wordt een nieuwe instantie van het backbonemodel voor de component gemaakt. De service wordt in het model geïnjecteerd.
* Er wordt een nieuw exemplaar van de backboneweergave gemaakt.
* Instantie van het bijbehorende model, de HTML-sjabloon en de hulpprogramma&#39;s worden in de weergave geïnjecteerd.

In de backboneweergave is er een gebeurteniskaart die de verschillende gebeurtenissen in kaart brengt die zich als gevolg van gebruikersinterfaceinteractie met een overeenkomstige manager kunnen voordoen. Deze toewijzing wordt in werking gesteld zodra een component wordt geïnitialiseerd.

Wanneer een mening wordt geïnitialiseerd, roept de mening zijn overeenkomstig model om gegevens van server te halen. Zodra alle gegevens die door een mening worden vereist beschikbaar zijn, geeft de mening de gegevens in het formaat terug dat door het malplaatje van de HTML wordt gespecificeerd. Meerdere weergaven kunnen hetzelfde model voor communicatie delen.

![](do-not-localize/aem_forms_workflow.png)

Een voorbeeld:

1. De gebruiker klikt een taakmalplaatje in de takenlijst.
1. De mening van de taak luistert aan de klik, en de vraag geeft functie op het taakmodel terug.
1. Het model van de taak roept daarna de dienst aan die een gemeenschappelijk punt voor al mededeling met de server van AEM Forms is.
1. De klasse van de dienst roept AEM Forms REST eindpunt voor teruggeeft methode via ajax.
1. De succescallback voor deze Ajax aanroeping wordt bepaald in het taakmodel.
1. Het model van de taak heft een backbonegebeurtenis als bericht op dat vraag teruggeeft volledig is.
1. In een andere weergave luistert de weergave met taakdetails naar deze gebeurtenis vanuit het taakmodel.
1. De mening van de details van de taak verandert dan het malplaatje van taakdetails om de teruggegeven taak (vorm, details, gehechtheid, nota&#39;s, etc.) aan de gebruiker te tonen.
