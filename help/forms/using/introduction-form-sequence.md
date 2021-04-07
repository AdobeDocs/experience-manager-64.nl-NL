---
title: Inleiding tot een formulierreeks die uit meerdere stappen bestaat
seo-title: Inleiding tot een formulierreeks die uit meerdere stappen bestaat
description: Met AEM Forms kunt u een reeks formulierdeelvensters definiëren waarin gebruikers door een adaptief formulier moeten navigeren en dit moeten invullen.
seo-description: Met AEM Forms kunt u een reeks formulierdeelvensters definiëren waarin gebruikers door een adaptief formulier moeten navigeren en dit moeten invullen.
uuid: b2b94e4c-0c28-47ba-8e23-fd8742baf71c
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: author
discoiquuid: 4a51ebc4-e019-4fc5-93a1-d97f695126f5
feature: Adaptieve Forms
exl-id: eec8bcbe-e2ba-42f1-98ea-08a4ca723e48
translation-type: tm+mt
source-git-commit: bd94d3949f0117aa3e1c9f0e84f7293a5d6b03b4
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 0%

---

# Inleiding tot formulierreeks met meerdere stappen {#introduction-to-multi-step-form-sequence}

Met adaptieve formulieren kunnen auteurs van formulieren in meerdere stappen gegevens vastleggen in alle eenvoud. De klasse wordt geleverd met ingebouwde ondersteuning voor het maken van meerdere deelvensters en het koppelen van elk deelvenster aan verschillende navigatiepatronen. Auteurs van formulieren kunnen formuliervelden groeperen in logische secties en een groep weergeven als deelvenster. De algemene navigatie tussen deelvensters wordt bepaald door de indeling van het deelvenster. Auteurs kunnen ervoor kiezen om deelvensters in verschillende lay-outs te rangschikken, bijvoorbeeld door de wizard-lay-out opeenvolgend te gebruiken of op een ad-hocmanier met de lay-out Tabbed. Zie [Indelingsmogelijkheden van adaptieve formulieren](/help/forms/using/layout-capabilities-adaptive-forms.md) voor informatie over deelvensterlay-outs.

In een typisch voorbeeld van het invullen van formulieren zijn er meer stappen nodig dan alleen het vastleggen van gegevens. Een volledig formulier dat wordt verzonden, kan andere stappen bevatten, zoals het digitaal ondertekenen van het formulier, het controleren van de informatie die is ingevuld in het formulier, het verwerken van betalingen, enzovoort. Het verschilt van geval tot geval.

Als uw gebruikscase een reeks stappen voor het vastleggen van gegevens verplicht stelt of als er regels zijn die bepaalde stappen moeten volgen, biedt AEM Forms een manier om die gemeenschappelijke structuur in alle formulieren af te dwingen. De vooraf ingestelde implementatie van de formulierstructuur definieert de reeks stappen voor een formulier. ![Voorbeeld van een formulierreeks die uit meerdere stappen bestaat](assets/formpipeline.png)

We gebruiken een voorbeeld waarbij u een reeks moet maken voor het invullen, verifiëren, ondertekenen en bevestigen van een formulier. U kunt een dergelijke reeks als volgt maken:

1. Definieer een formuliersjabloon en voeg het vereiste deelvenster toe. Let op: er moet één deelvenster zijn voor elke stap in de reeks. U kunt echter wel subdeelvensters in een deelvenster opnemen.

   In dit voorbeeld kunt u de volgende deelvensters toevoegen:

   * **Vulling**: Het bevat formuliervelden voor het vastleggen van gegevens. Hier kunt u geneste subdeelvensters opnemen om secties te maken voor verschillende soorten informatie, zoals persoonlijke gegevens, familiegegevens, financiële gegevens enzovoort.
   * **Controleren**: Het bevat de  **** verificatiecomponent die kan worden gebruikt in een op XFA gebaseerde adaptieve vorm. De gegevens die in het deelvenster Vulling zijn vastgelegd, worden in de modus Alleen-lezen weergegeven, zodat ze kunnen worden geverifieerd.
   * **E-handtekening**: Het bevat de  **** SigningComponent die in een op XFA-Gebaseerde adaptieve vorm kan worden gebruikt. het biedt de volgende ondertekeningsservices:

      * Adobe Document Cloud eSign-services
      * Krabbelhandtekening
   * **Bevestiging**: Het bevat de component  **** Summiere waarin een bericht wordt weergegeven ter bevestiging van het verzenden van het formulier nadat een gebruiker het formulier heeft ondertekend en de stap Bevestigen (Samenvatting) in de reeks heeft bereikt. Auteurs kunnen de tekst van de component Summary configureren, een bedankbericht weergeven, een koppeling naar de gegenereerde PDF weergeven, enzovoort.


1. Selecteer de layout van het hoofddeelvenster als **[!UICONTROL Wizard]**.
1. Voer de overige stappen uit om de formuliersjabloon te maken. Zie [Een aangepaste formuliersjabloon maken](/help/forms/using/custom-adaptive-forms-templates.md) voor meer informatie.

Nadat u de formuliervolgorde in de formuliersjabloon hebt gedefinieerd, kunt u er formulieren mee maken die de basisstructuur hebben gedefinieerd als de ingestelde reeks. U kunt het formulier echter altijd aan uw wensen aanpassen.
