---
title: Formuliersjablonen ontwerpen voor HTML5-formulieren
seo-title: Formuliersjablonen ontwerpen voor HTML5-formulieren
description: 'AEM Forms biedt rendering van XFA-formuliersjablonen naar HTML5-indeling. Formulierontwerpers kunnen formuliersjablonen ontwerpen met Designer en de HTML5-renderingmogelijkheden gebruiken. '
seo-description: 'AEM Forms biedt rendering van XFA-formuliersjablonen naar HTML5-indeling. Formulierontwerpers kunnen formuliersjablonen ontwerpen met Designer en de HTML5-renderingmogelijkheden gebruiken. '
uuid: 41a00ec5-d7f9-4717-a961-00d20d8e7b2a
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: hTML5_forms
discoiquuid: e135fa01-fede-4285-b4dd-2d23acbb4d26
translation-type: tm+mt
source-git-commit: f13d358a6508da5813186ed61f959f7a84e6c19f
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 0%

---


# Formuliersjablonen ontwerpen voor HTML5-formulieren {#designing-form-templates-for-html-forms}

De HTML5-formuliercomponent in AEM biedt rendering van XFA-formuliersjablonen naar HTML5-indeling. Formulierontwerpers kunnen formuliersjablonen ontwerpen met behulp van [Forms Designer](https://www.adobe.com/go/learn_aemforms_designer_63) en de mogelijkheid van HTML5-uitvoering gebruiken. Deze formuliersjablonen kunnen samen met hun elementen in AEM opslagplaats, bestandssysteem of beschikbaar worden gemaakt via http. Als u echter van plan bent uw formulieren te beheren met Forms Manager, moeten de sjablonen en middelen zich in de AEM-opslagplaats bevinden.

Hoewel HTML5-formulieren grotendeels overeenkomen met het gedrag van de PDF forms, zijn er bepaalde functies in beide indelingen die niet van toepassing zijn op de andere indeling. De manier waarop streepjescodes worden toegepast op een PDF-formulier in Adobe Reader verschilt bijvoorbeeld per mobiel formulier of de manier waarop een formulier digitaal wordt ondertekend, verschilt ook per indeling. Zie [Verschillen in functies tussen HTML5-formulieren en PDF forms](/help/forms/using/feature-differentiation-html5-forms-pdf-forms.md) voor meer informatie over dergelijke variaties.

Raadpleeg de volgende aanbevolen procedures en richtlijnen voor het ontwerpen van formulieren die in beide indelingen werken voor algemene XFA-functies.

## Mogelijkheden in AEM Forms Designer voor HTML5 Forms {#capabilities-in-aem-forms-designer-for-html-forms}

### HTML {#preview-html} voorvertonen

Het tabblad Voorbeeld-HTML wordt in de ontwerpmodus toegevoegd zodat formulierontwerpers tijdens het ontwerpproces formulieren in HTML5-indeling kunnen bekijken. Zie [HTML voorvertonen](/help/forms/using/preview-xdp-forms-html.md) voor meer informatie over het in- en uitschakelen van deze functie in AEM Forms Designer.

### Krabbelhandtekening {#scribble-signature}

Het belangrijkste doel voor HTML5-formulieren is aanraakapparaten. Daarom wordt een nieuwe controle van de krabbelhandtekening toegevoegd in de Ontwerper van AEM Forms. U kunt op het besturingselement voor krabbelhandtekeningen klikken of het besturingselement voor krabbelhandtekeningen slepen en neerzetten op uw formuliersjabloon en het configureren. Het wordt weergegeven als een krabbelveld in HTML5-uitvoering en kan worden gebruikt om een handtekening te krabbelen op aanraakapparaten. Op desktopcomputers kan het als krabbelveld worden gebruikt met de muis. Zie [XFA-scriptveld](/help/forms/using/scribble-signature.md) voor meer informatie over het gebruik van deze functie.

![4](assets/4.png)
