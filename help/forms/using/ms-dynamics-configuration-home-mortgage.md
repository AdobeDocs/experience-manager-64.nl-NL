---
title: Configureer Microsoft Dynamics 365 voor de workflow voor hypothecair thuis van de website Web.Finance
seo-title: Configure Microsoft Dynamics 365 for the home mortgage workflow of the We.Finance reference site
description: Leer hoe u de Microsoft® Dynamics 365-services kunt gebruiken door adaptieve formulieren te maken voor de workflow voor hypotheken thuis op de website Web.Finance Reference
seo-description: Learn how to leverage the Microsoft® Dynamics 365 services through adaptive forms for the home mortgage workflow of the We.Finance Reference site
uuid: a0656d90-84c7-46d1-9a16-dadcc19ff9ef
products: SG_EXPERIENCEMANAGER/6.3/FORMS
topic-tags: develop, Configuration
discoiquuid: 6b31397a-fb06-4043-9368-59fb4fce8afa
exl-id: 7e1f417e-6a6b-4ef2-a453-866331fe3e96
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 0%

---

# Configureer Microsoft Dynamics 365 voor de workflow voor hypothecair thuis van de website Web.Finance {#configure-microsoft-dynamics-for-the-home-mortgage-workflow-of-the-we-finance-reference-site}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Leer hoe u de Microsoft® Dynamics 365-services kunt gebruiken door adaptieve formulieren te maken voor de workflow voor hypotheken thuis op de website Web.Finance Reference

## Overzicht {#overview}

Microsoft® Dynamics 365 is een ERP-software (Customer Relationship Management) en een ERP-software (Customer Relationship Management) die bedrijfsoplossingen biedt voor het maken en beheren van klantaccounts, contactpersonen, leads, mogelijkheden en gevallen.

AEM Forms biedt een cloudservice voor de integratie van Dynamics 365 met [Forms-gegevensintegratie](/help/forms/using/data-integration.md) module. Het scenario [Doorloop voor toepassing Home Mortgauge met Microsoft® Dynamics](/help/forms/using/finance-reference-site-walkthrough.md#home-mortgage-application-walkthrough-with-microsoft-dynamics) laat zien hoe een klant de referentiesite We.Finance gebruikt om een lening aan te vragen wanneer de site Microsoft® Dynamics for Forms Data Integration gebruikt. Alvorens u de de toepassingsanalyse van de Kortere meetkunde van het Huis met het scenario van de Dynamiek Microsoft® kunt gebruiken, moet u de Dynamica 365 vormen Microsoft® die met de Web.Finance verwijzingsplaats moet worden gebruikt.

## Vereisten {#prerequisites}

Alvorens u begint opstelling en Dynamica 365 te vormen, zorg ervoor dat u hebt:

* [AEM Forms-referentiesites instellen en configureren](/help/forms/using/setup-reference-sites.md).

* AEM 6.3 Forms Service Pack 1 en hoger
* Microsoft® Dynamics 365 account
* Geregistreerde toepassing voor Dynamics 365-service met Microsoft® Azure Active Directory
* Client-id en clientgeheim voor de geregistreerde toepassing

## Koppel de hypotheekcalculator voor woninghypotheken aan de homepage van uw site {#link-the-home-mortgage-calculator-with-your-site-home-page}

1. Ga in de auteurinstantie naar de volgende pagina:

   https://[sderver]:[poort]/editor.html/content/we-finance/global/en/loan-landing-page.html

1. Schuif omlaag naar de rekenmachine voor de beginmeter.
1. Markeer het deelvenster van de rechterkolom (rekenmachine) en tik om het pop-upmenu weer te geven. Tik in het pop-upmenu op Configureren. Het dialoogvenster AEM Forms-container bewerken wordt geopend.

   ![calculatorConfigurpanel](assets/calculatorconfigurepanel.png)

1. Blader in het dialoogvenster AEM Forms-container bewerken door het middelenpad en selecteer Home-hypotheekcalculator op het volgende pad en tik **Bevestigen**:

   formsanddocuments/We.Finance/MS Dynamics/

   ![selectassetpath](assets/selectassetpath.png)

1. Tikken **Gereed**.
1. De bewerkte pagina publiceren.

   >[!NOTE]
   >
   >De band van de calculatorgebieden met FDM wordt preconfigured door het Wij.Finance pakket van de verwijzingsplaats. Als u de binding wilt weergeven, opent u het formulier in de ontwerpmodus en ziet u het veld binden verwijzingen.

1. Als u een aangepaste entiteit wilt maken voor het opslaan van de aanvraagrecord voor hypotheektoepassing op woningen, importeert u het pakket AEMFormsFSIRefsite_1_0.zip-oplossing naar uw Microsoft® Dynamics-instantie:

   1. Download het pakket van:

      `https://[server]:[port]/content/aemforms-refsite-collaterals/we-finance/home-mortgage/ms-dynamics/AEMFormsFSIRefsite_1_0.zip`

   1. Importeer het oplossingspakket naar de Microsoft® Dynamics-instantie. Ga in je Microsoft® Dynamics-instantie naar **Instellingen** > **Oplossingen** en tik vervolgens op **Importeren**.

1. Als u de contactgegevens van de gebruiker wilt instellen die worden gebruikt in de terugzetsite, importeert u het pakket Sarah Rose Contact.CSV naar de instantie Microsoft® Dynamics:

   1. Download het pakket van:

      `https://[server]:[port]/content/aemforms-refsite-collaterals/we-finance/home-mortgage/ms-dynamics/Sarah%20Rose%20Contact.csv`

   1. Importeer het pakket naar de Microsoft® Dynamics-instantie. Ga in je Microsoft® Dynamics-instantie naar **Verkoop** > **Contactpersonen** en tik vervolgens op **Gegevens importeren**.
