---
title: Een adaptief formulier gebruiken in HTML Workspace
seo-title: Een adaptief formulier gebruiken in HTML Workspace
description: Een adaptief formulier gebruiken in HTML Workspace
seo-description: Een adaptief formulier gebruiken in HTML Workspace
uuid: 1ebe81ae-5c0b-4c07-8cd1-86efdf8415be
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: 2f514072-81d9-48de-8369-cca94a330f1d
translation-type: tm+mt
source-git-commit: 0797eeae57ac5a9676c6d308eaf2aaffab999d18
workflow-type: tm+mt
source-wordcount: '684'
ht-degree: 0%

---


# Een adaptief formulier gebruiken in HTML Workspace {#using-an-adaptive-form-in-html-workspace}

AEM Forms on JEE biedt de mogelijkheid om een adaptief formulier te gebruiken in HTML Workspace.

Aangezien u tijdens het ontwerpen van processen een XDP kunt selecteren, is de mogelijkheid om vanuit een bestaande adaptieve AEM opslagplaats te bladeren toegevoegd. Het vermogen geeft de ontwerper van het Proces de capaciteit om een adaptief vorm in BeginPunt evenals in Taak te vormen.

## Procesontwerpervaring {#process-design-experience}

Voer het volgende uit om het gebruik van adaptieve formulieren in procesontwerp mogelijk te maken:

* In Taak toewijzen en Beginpunt kunt u naar een adaptief formulierelement in de CRX-opslagruimte bladeren wanneer u een formulierelement aan een taak toewijst.
* In de Werkbank Werkbank toewijzen aan taak/beginpunt kunt u de werkbalk op hoofdniveau/algemeen van een adaptief formulier verbergen.
* U kunt nieuwe actieprofielen gebruiken voor het renderen en verzenden van handelingen in adaptieve formulieren.

### LiveCycle-toepassing exporteren en importeren {#livecycle-application-export-and-import}

Omdat adaptieve formulieren zich in de AEM opslagplaats bevinden, bevat de export van de LiveCycle-toepassing alleen de referenties voor gebruikte adaptieve formulieren. Daarom is het exporteren en importeren van LiveCycle-toepassingen een proces in twee stappen. De toepassing LiveCycle bevat procesdefinities, enzovoort. Een afzonderlijk pakket met adaptieve formulieren wordt vanuit AEM geëxporteerd als een ZIP-bestand. Tijdens het importeren wordt de LiveCycle-toepassing geïmporteerd via Workbench en worden adaptieve formulieren geïmporteerd via AEM.

## Gebruikerservaring van adaptief formulier in HTML Workspace {#user-experience-of-adaptive-form-in-html-workspace}

De HTML-werkruimte bevat enkele adaptieve formulierspecifieke besturingselementen naast de besturingselementen die beschikbaar zijn voor mobiele formulieren. Een gebruiker kan bijlagen toevoegen, opslaan, ondertekenen, verzenden en door de aangepaste formulieren in HTML Workspace navigeren wanneer de gebruiker een taak of beginpunt opent. Hieronder volgen de specifieke kenmerken:

1. Voor **attach **files gebruiken Taakbijlagen, net als voor Mobile Forms. Een knop van het type bestandsbijlage van het adaptieve formulier is verborgen.

1. Als u een adaptief formulier wilt opslaan, klikt u op **Opslaan**, net als in Mobile Forms. Elke knop voor het type Opslaan van het adaptieve formulier is verborgen.

1. Als u een adaptief formulier wilt verzenden, gebruikt u de beschikbare **knop Verzenden** of routeacties, zoals in Mobile Forms. De knop Verzendtype van het adaptieve formulier is verborgen.

1. **Zichtbaarheid van de werkbalk Adaptief formulier Global**: Als de procesontwerper de algemene werkbalk of de werkbalk op hoofdniveau verbergt, worden de werkbalk en de knoppen niet weergegeven op adaptieve formulieren.

1. **Workspace navigation controls for Adaptive Forms**: De knoppen Volgende/Vorige zijn beschikbaar samen met de knoppen Handeling opslaan, Verzenden en Route voor een adaptief formulier in HTML Workspace. Klik op de knoppen Volgende/Vorige om door de deelvensters met adaptieve formulieren in de HTML-werkruimte te navigeren. De knoppen Volgende/Vorige bieden diepgaande navigatie, vergelijkbaar met navigatiebesturingselementen in de weergave Mobiel van adaptieve formulieren.

1. **eSign Services en Samenvattingscomponent van adaptief formulier**: De component Summary werkt niet in HTML Workspace. Met andere woorden, als een adaptief formulier een overzichtscomponent heeft, is het niet zichtbaar in de werkruimte. In plaats van Automatisch verzenden in de component Esign klikt de werkruimteconstructie op Verzenden of een routeactie in de Werkruimte van HTML. Nadat een document is ondertekend, is het zichtbaar als een vlak ondertekend document. Klik **voorleggen** of een routeactie om de taak of Punt van het Begin te sluiten/te voltooien.

   Het ondertekende document wordt verzameld van de eSign-serviceserver en het data-xml-bestand wordt doorgestuurd naar de volgende stap in het proces.

## Stappen voor het gebruik van adaptieve formulieren in procesontwerp {#steps-to-use-adaptive-forms-in-process-design}

1. Open Adobe Experience Manager Forms Workbench.

1. Ga naar **Bestand > Nieuw > Toepassing** of gebruik de bestaande toepassing om een toepassing te maken.

   ![Nieuwe toepassing maken](assets/create_new_appl.png)

1. Maak een proces of gebruik een bestaand proces in de toepassing.

   ![Nieuw proces maken](assets/create_new_process.png)

1. Creeer een Punt van het Begin of wijs Taak toe en klik het tweemaal.
1. Selecteer onder de **[!UICONTROL Presentation & Data]** sectie de ellipsen **[!UICONTROL use a CRX asset]** en klik op het element.

   ![Een CRX-element gebruiken](assets/use_crx_asset.png)

1. Selecteer het aangepaste formulier dat u via de gebruikersinterface Middelen beheren hebt gemaakt en klik op **[!UICONTROL OK]**.

   ![Een adaptief formulier selecteren](assets/selecting_form.png)

   >[!NOTE]
   >
   >Zie Een adaptief formulier [maken voor meer informatie over het maken van een adaptief formulier](/help/forms/using/creating-adaptive-form.md).
   >
   >Zie [Processen](https://help.adobe.com/en_US/AEMForms/6.1/WorkbenchHelp/WS92d06802c76abadb-1cc35bda128261a20dd-7ff7.2.html)maken en beheren voor meer informatie over het maken van een proces.

