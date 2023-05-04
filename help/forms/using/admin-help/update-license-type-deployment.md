---
title: Het licentietype voor de implementatie bijwerken
seo-title: Update the license type for the deployment
description: Werk het licentietype voor de implementatie bij met behulp van de pagina Change License in de beheerconsole.
seo-description: Update the license type for the deployment by using the Change License page in administration console.
uuid: 0152635e-2c00-4944-b9b6-64b368589a91
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/get_started_with_administering_aem_forms_on_jee
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: e4f31377-ccc9-4986-a3bf-ef2e83d12448
exl-id: 07671470-59dd-4290-be9a-465fcd89ac2d
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 0%

---

# Het licentietype voor de implementatie bijwerken {#update-the-license-type-for-the-deployment}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Als deel van het proces van de AEM vormeninstallatie, gebruikte u de Manager van de Configuratie om de AEM vormenmodules te vormen en op te stellen die u vereist. Door gebrek, worden die modules gevormd met een vergunning van de 60 dagevaluatie. Gebruik de pagina van de Vergunning van de Verandering in beleidsconsole om het licentietype voor de plaatsing te veranderen. De momenteel opgestelde modules worden getoond op de pagina van de Vergunning van de Verandering.

Op de pagina Licentie wijzigen wordt informatie over uw licentie weergegeven:

* Het huidige type licentie
* De datum en tijd waarop de licentie voor het laatst is bijgewerkt
* Wie de laatste update heeft uitgevoerd
* Huidige status van de vergunning
* De datum waarop AEM formulieren zijn geïnstalleerd
* De datum waarop de huidige licentie vervalt

>[!NOTE]
>
>De vergunningsverandering is op alle opgestelde modules van toepassing. Voordat u het licentietype wijzigt, moet u de implementatie van modules die geen licentie hebben. Selecteer het licentietype Productie niet als de lijst met geïmplementeerde modules andere modules bevat dan de modules die u van Adobe hebt gekocht.

## Het licentietype bijwerken {#update-the-license-type}

1. Klik op Licentie verlenen in de beheerconsole.
1. Lees de licentieovereenkomst voor eindgebruikers voor AEM formulieren, selecteer Ik accepteer als u akkoord gaat met de voorwaarden van de overeenkomst en klik op Volgende.
1. Selecteer op de pagina Licentie wijzigen een licentietype:

   * **EVAL:** Evaluatievergunning van 60 dagen
   * **DEV:** Licentie voor permanente ontwikkeling
   * **NFR:** tweejarige evaluatievergunning
   * **IDEV:** 1 jaar abonnement op het Adobe Developer-programma
   * **Productie:** Perpetroleumvergunning

1. Selecteer Ja, wijziging van licentie is geldig voor alle geïmplementeerde modules.
1. Klik op Licentiewijziging bevestigen. Er wordt een bericht weergegeven met de mededeling dat de licentie is bijgewerkt.
