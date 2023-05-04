---
title: Formuliersjablonen ontwerpen voor HTML5-formulieren
seo-title: Designing form templates for HTML5 forms
description: AEM Forms biedt de weergave van XFA-formuliersjablonen in de HTML5-indeling. Formulierontwerpers kunnen formuliersjablonen ontwerpen met Designer en de HTML5-uitvoermogelijkheden gebruiken.
seo-description: AEM Forms offers rendering XFA form template to HTML5 format. Form designers can design form templates using Designer and use the HTML5 rendition capability.
uuid: 41a00ec5-d7f9-4717-a961-00d20d8e7b2a
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: hTML5_forms
discoiquuid: e135fa01-fede-4285-b4dd-2d23acbb4d26
feature: Mobile Forms
exl-id: 248e56c7-51b7-41d3-8bc9-a5d737bf178b
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 0%

---

# Formuliersjablonen ontwerpen voor HTML5-formulieren {#designing-form-templates-for-html-forms}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

De HTML5-formuliercomponent in AEM biedt rendering van XFA-formuliersjabloon naar HTML5-indeling. Formulierontwerpers kunnen formuliersjablonen ontwerpen met [Forms Designer](https://www.adobe.com/go/learn_aemforms_designer_63) en gebruik de HTML5-renderingmogelijkheid. Deze formuliersjablonen kunnen samen met hun elementen in AEM opslagplaats, bestandssysteem of beschikbaar worden gemaakt via http. Als u echter van plan bent uw formulieren te beheren met Forms Manager, moeten de sjablonen en middelen zich in de AEM-opslagplaats bevinden.

Hoewel HTML5-formulieren grotendeels overeenkomen met het gedrag van de PDF forms, zijn er bepaalde functies in beide indelingen die niet van toepassing zijn op de andere indeling. De manier waarop streepjescodes worden toegepast op een PDF-formulier in Adobe Reader verschilt bijvoorbeeld per mobiel formulier of de manier waarop een formulier digitaal wordt ondertekend, verschilt ook per indeling. Zie voor meer informatie over dergelijke variaties [Onderscheid tussen HTML5-formulieren en PDF forms](/help/forms/using/feature-differentiation-html5-forms-pdf-forms.md).

Raadpleeg de volgende aanbevolen procedures en richtlijnen voor het ontwerpen van formulieren die in beide indelingen werken voor algemene XFA-functies.

## Mogelijkheden in AEM Forms Designer voor HTML5 Forms {#capabilities-in-aem-forms-designer-for-html-forms}

### Voorvertoning HTML {#preview-html}

Het tabblad Voorbeeld-HTML wordt in de ontwerpmodus toegevoegd, zodat formulierontwerpers tijdens het ontwerpproces een voorbeeld van formulieren in de HTML-indeling kunnen bekijken. Voor meer informatie over het inschakelen en configureren van deze functie in AEM Forms Designer raadpleegt u [Voorvertoning HTML](/help/forms/using/preview-xdp-forms-html.md).

### Krabbelhandtekening {#scribble-signature}

Het belangrijkste doel voor HTML5-formulieren is aanraakapparaten. Daarom wordt een nieuwe controle van de krabbelhandtekening toegevoegd in de Ontwerper van AEM Forms. U kunt op het besturingselement voor krabbelhandtekeningen klikken of het besturingselement voor krabbelhandtekeningen slepen en neerzetten op uw formuliersjabloon en het configureren. Het wordt weergegeven als een krabbelveld in HTML 25-uitvoering en kan worden gebruikt om een handtekening te krabbelen op aanraakapparaten. Op desktopcomputers kan het als krabbelveld worden gebruikt met de muis. Voor meer informatie over het gebruik van deze functie raadpleegt u [XFA-scriptveld](/help/forms/using/scribble-signature.md).

![4](assets/4.png)
