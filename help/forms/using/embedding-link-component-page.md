---
title: Koppelingscomponent insluiten in een pagina
seo-title: Embedding link component in a page
description: Met de koppelingscomponent kunt u een adaptief document of een adaptief formulier van een willekeurige pagina koppelen.
seo-description: You can use the link component to link an adaptive document or an adaptive form from any page.
uuid: fde56b5f-634c-406f-a026-875f972f7c8f
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: publish
discoiquuid: a4a36e73-3f7a-4173-8807-931f26daa35a
exl-id: eb816a35-0773-4eda-95b2-1d351c71be8b
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 0%

---

# Koppelingscomponent insluiten in een pagina{#embedding-link-component-in-a-page}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Vereisten {#prerequisites}

De koppelingscomponent is een lid van de categorie Document Services. Zorg ervoor dat de categorie Document Services zichtbaar is in de browser met AEM componenten. Als de categorie niet wordt vermeld, voert u de stappen uit die worden weergegeven op [portalcomponenten voor formulieren inschakelen](/help/forms/using/enabling-forms-portal-components.md).

## Component koppelen {#link-component}

Met de component Koppeling kunnen auteurs van formulierportaalpagina&#39;s vanaf elke locatie op een pagina een koppeling naar een adaptief formulier maken. De component van de Verbinding is beschikbaar in de sectie van de Diensten van het Document in componentenbrowser.

Voer de volgende stappen uit om een component van de Verbinding aan de pagina toe te voegen:

1. Sleep de **Koppeling** op de pagina. Selecteer de component en tik op ![cmppr](assets/cmppr.png). Het dialoogvenster Koppelingscomponent bewerken wordt geopend.

   ![edit-link-component](assets/edit-link-component.png)

1. In de **Weergave** kunt u het volgende opgeven:

   * **Bijschrift koppelen**: Tekst of bijschrift voor de koppeling koppelen.
   * **Knopinfo koppeling**: Knopinfo voor de koppeling.
   * **Lay-outsjabloon**: Sjabloon voor de lay-out van de component Koppeling.

1. Open de **Elementinfo** en geeft u het type element op. Een element kan een **formulier**. Afhankelijk van het geselecteerde type element worden de onderstaande opties weergegeven:

   * **Middelpad**: Pad naar opslagplaats waar het element is opgeslagen.
   * **Rendertype**: De renderindeling—PDF, HTML of Automatisch. Met het rendertype Automatisch wordt de gebruikersomgeving gedetecteerd en wordt het formulier dienovereenkomstig weergegeven als HTML of als PDF. Als het formulier bijvoorbeeld wordt geopend vanaf een mobiel apparaat, geeft het rendertype Automatisch het formulier weer in HTML.
   * **URL verzenden:**  URL aan servlet waar de vormgegevens worden voorgelegd.
   * **HTML-profiel**: Profiel voor weergave van het formulier als HTML.
   * **PDF-profiel**: Profiel voor het weergeven van het formulier als PDF-document.

1. Open de **Geavanceerd** tab. U kunt de extra parameters in het sleutel-waarde paarformaat specificeren. Wanneer op de koppeling wordt geklikt, worden deze aanvullende parameters doorgegeven en samen met het formulier doorgegeven.

   Tikken **Gereed** om de configuratie op te slaan.

## Aanbevolen procedures voor het gebruik van de component Koppeling {#best-practices-for-using-link-component-br}

* Zorg ervoor dat u PDF selecteert als het rendertype als het pad dat is opgegeven in Formulierpad, verwijst naar een document met de toegestane renderindeling PDF als.
* De verzendURL voor een formulier kan op verschillende plaatsen worden opgegeven en de prioriteitsvolgorde is als volgt:

   1. Verzenden van URL die is ingesloten in het formulier (in verzendknop) heeft de hoogste prioriteit.
   1. De verzendURL die in Forms Manager wordt vermeld, heeft de middelhoge prioriteit.
   1. De laagste prioriteit voor het verzenden van een URL die in het formulierportaal wordt vermeld.
