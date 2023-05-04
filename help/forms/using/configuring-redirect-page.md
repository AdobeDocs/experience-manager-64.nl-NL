---
title: Omleidingspagina configureren
seo-title: Configuring redirect page
description: Nadat u een adaptief formulier hebt ingevuld, kunnen gebruikers worden omgeleid naar een webpagina die formulierauteurs kunnen configureren tijdens het maken van het formulier.
seo-description: After filling an adaptive form, users can be redirected to a webpage that form authors can configure while creating the form.
uuid: 5a5f912a-9696-4bc1-af3f-ead78f767e02
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: author
discoiquuid: c51817aa-193a-4d4f-bd83-06518ddfb395
feature: Adaptive Forms
exl-id: bbe10952-d6a7-4adc-bab9-388c1ee8e56a
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 0%

---

# Omleidingspagina configureren {#configuring-redirect-page}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Formulierauteurs kunnen een pagina configureren voor elk formulier, waarnaar de formuliergebruikers worden omgeleid na het verzenden van een formulier.

1. Selecteer in de bewerkingsmodus een component en klik vervolgens op ![op veldniveau](assets/field-level.png) > **Aangepaste formuliercontainer** en klik vervolgens op ![cmppr](assets/cmppr.png).

1. Klik in de zijbalk op **Indiening**.

1. Geef de URL van de omleidingspagina op onder Vorige pagina in de sectie Verzending.
1. Naar keuze, onder Verzenden Actie, voor Submit aan de het eindpuntactie van REST, kunt u de parameter vormen die tot de omleidingspagina wordt overgegaan.

![Pagina-configuratie omleiden](assets/thank-you-setting-1.png)
**Afbeelding:** *Pagina-configuratie omleiden*

Auteurs van formulieren kunnen de volgende parameters gebruiken die worden doorgegeven aan de pagina Bedankt. Voor alle beschikbare verzendacties: `status` en `owner` parameters worden doorgegeven. Naast deze twee parameters worden enkele aanvullende parameters doorgegeven voor de volgende verzendacties:

* **Winkelinhoud, actie** (afgekeurd) : `contentPath`—het pad van het knooppunt in de gegevensopslagruimte waar de verzonden gegevens worden opgeslagen—wordt doorgegeven.

* **PDF opslaan** (afgekeurd) : `contentPath`—van de voorgelegde gegevens en de weg aan de knoop die het PDF dossier in bewaart in bewaarplaats-wordt overgegaan.

* **Verzenden naar Forms-workflow**: Uitvoerparameters die worden geretourneerd uit de formulierwerkstroom, worden doorgegeven.

* **Verzenden naar REST-eindpunt**: Parameters die voor parametertoewijzing in het veld worden toegevoegd, worden doorgegeven. `status` en `owner` parameters worden niet doorgegeven in deze verzendactie. Zie voor meer informatie [Het vormen van Submit aan het eindpunt REST legt actie voor](/help/forms/using/configuring-submit-actions.md).
