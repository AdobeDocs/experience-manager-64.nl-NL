---
title: Inleiding tot een formulierreeks die uit meerdere stappen bestaat
seo-title: Introduction to multi-step form sequence
description: Met AEM Forms kunt u een reeks formulierdeelvensters definiëren waarin gebruikers door een adaptief formulier moeten navigeren en dit moeten invullen.
seo-description: With AEM Forms, you can define a sequence of form panel in which you want users to navigate and fill an adaptive form.
uuid: b2b94e4c-0c28-47ba-8e23-fd8742baf71c
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: author
discoiquuid: 4a51ebc4-e019-4fc5-93a1-d97f695126f5
feature: Adaptive Forms
exl-id: eec8bcbe-e2ba-42f1-98ea-08a4ca723e48
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '544'
ht-degree: 0%

---

# Inleiding tot een formulierreeks die uit meerdere stappen bestaat {#introduction-to-multi-step-form-sequence}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Met adaptieve formulieren kunnen auteurs van formulieren in meerdere stappen gegevens vastleggen in alle eenvoud. De klasse wordt geleverd met ingebouwde ondersteuning voor het maken van meerdere deelvensters en het koppelen van elk deelvenster aan verschillende navigatiepatronen. Auteurs van formulieren kunnen formuliervelden groeperen in logische secties en een groep weergeven als deelvenster. De algemene navigatie tussen deelvensters wordt bepaald door de indeling van het deelvenster. Auteurs kunnen ervoor kiezen om deelvensters in verschillende lay-outs te rangschikken, bijvoorbeeld door de wizard-lay-out opeenvolgend te gebruiken of op een ad-hocmanier met de lay-out Tabbed. Voor informatie over paneellay-outs raadpleegt u [Indelingsmogelijkheden van adaptieve formulieren](/help/forms/using/layout-capabilities-adaptive-forms.md).

In een typisch voorbeeld van het invullen van formulieren zijn er meer stappen nodig dan alleen het vastleggen van gegevens. Een volledig formulier dat wordt verzonden, kan andere stappen bevatten, zoals het digitaal ondertekenen van het formulier, het controleren van de informatie die is ingevuld in het formulier, het verwerken van betalingen, enzovoort. Het verschilt van geval tot geval.

Als uw gebruikscase een reeks stappen voor het vastleggen van gegevens verplicht stelt of als er regels zijn die bepaalde stappen moeten volgen, biedt AEM Forms een manier om die gemeenschappelijke structuur in alle formulieren af te dwingen. De vooraf ingestelde implementatie van de formulierstructuur definieert de reeks stappen voor een formulier. ![Voorbeeld van een formulierreeks die uit meerdere stappen bestaat](assets/formpipeline.png)

We gebruiken een voorbeeld waarbij u een reeks moet maken voor het invullen, verifiëren, ondertekenen en bevestigen van een formulier. U kunt een dergelijke reeks als volgt maken:

1. Definieer een formuliersjabloon en voeg het vereiste deelvenster toe. Let op: er moet één deelvenster zijn voor elke stap in de reeks. U kunt echter wel subdeelvensters in een deelvenster opnemen.

   In dit voorbeeld kunt u de volgende deelvensters toevoegen:

   * **Vullen**: Het bevat formuliervelden voor het vastleggen van gegevens. Hier kunt u geneste subdeelvensters opnemen om secties te maken voor verschillende soorten informatie, zoals persoonlijke gegevens, familiegegevens, financiële gegevens enzovoort.
   * **Verifiëren**: Het bevat de **Verifiëren** component die kan worden gebruikt in een op XFA gebaseerde adaptieve vorm. De gegevens die in het deelvenster Vulling zijn vastgelegd, worden in de modus Alleen-lezen weergegeven, zodat ze kunnen worden geverifieerd.
   * **E-sign**: Het bevat de **Ondertekenen** component die kan worden gebruikt in een op XFA gebaseerde adaptieve vorm. het biedt de volgende ondertekeningsservices:

      * Adobe Document Cloud eSign-services
      * Krabbelhandtekening
   * **Bevestiging**: Het bevat de **Samenvatting** een bericht wordt weergegeven waarin de verzending van het formulier wordt bevestigd nadat een gebruiker het formulier heeft ondertekend en de stap Bevestigen (overzicht) in de reeks heeft bereikt. De auteurs kunnen de tekst van de Summiere component vormen, een dank u bericht tonen, een verbinding aan de geproduceerde PDF tonen, etc.


1. De lay-out van het hoofddeelvenster selecteren als **[!UICONTROL Wizard]**.
1. Voer de overige stappen uit om de formuliersjabloon te maken. Zie voor meer informatie [Een aangepaste aangepaste formuliersjabloon maken](/help/forms/using/custom-adaptive-forms-templates.md).

Nadat u de formuliervolgorde in de formuliersjabloon hebt gedefinieerd, kunt u er formulieren mee maken die de basisstructuur hebben gedefinieerd als de ingestelde reeks. U kunt het formulier echter altijd aan uw wensen aanpassen.
