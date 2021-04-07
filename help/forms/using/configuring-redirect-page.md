---
title: Omleidingspagina configureren
seo-title: Omleidingspagina configureren
description: Nadat u een adaptief formulier hebt ingevuld, kunnen gebruikers worden omgeleid naar een webpagina die formulierauteurs kunnen configureren tijdens het maken van het formulier.
seo-description: Nadat u een adaptief formulier hebt ingevuld, kunnen gebruikers worden omgeleid naar een webpagina die formulierauteurs kunnen configureren tijdens het maken van het formulier.
uuid: 5a5f912a-9696-4bc1-af3f-ead78f767e02
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: author
discoiquuid: c51817aa-193a-4d4f-bd83-06518ddfb395
feature: Adaptieve Forms
exl-id: bbe10952-d6a7-4adc-bab9-388c1ee8e56a
translation-type: tm+mt
source-git-commit: bd94d3949f0117aa3e1c9f0e84f7293a5d6b03b4
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 0%

---

# Omleidingspagina {#configuring-redirect-page} configureren

Formulierauteurs kunnen een pagina configureren voor elk formulier, waarnaar de formuliergebruikers worden omgeleid na het verzenden van een formulier.

1. Selecteer in de bewerkingsmodus een component en klik op ![veldniveau](assets/field-level.png) > **Aangepaste formuliercontainer**. Klik vervolgens op ![cmp](assets/cmppr.png).

1. Klik in de zijbalk op **Verzending**.

1. Geef de URL van de omleidingspagina op onder Vorige pagina in de sectie Verzending.
1. Naar keuze, onder Verzenden Actie, voor Submit aan de het eindpuntactie van REST, kunt u de parameter vormen die tot de omleidingspagina wordt overgegaan.

![Pagina-](assets/thank-you-setting-1.png)
**configuratie omleidenFiguur:** *Paginasamenstelling omleiden*

Auteurs van formulieren kunnen de volgende parameters gebruiken die worden doorgegeven aan de pagina Bedankt. Voor alle beschikbare verzendacties worden `status`- en `owner`-parameters doorgegeven. Naast deze twee parameters worden enkele aanvullende parameters doorgegeven voor de volgende verzendacties:

* **Handeling**  voor inhoud opslaan (afgekeurd):  `contentPath`—het pad van het knooppunt in de gegevensopslagruimte waar de verzonden gegevens worden opgeslagen—wordt doorgegeven.

* **PDF-handeling**  opslaan (afgekeurd):  `contentPath`—van de verzonden gegevens en het pad naar het knooppunt dat het PDF-bestand in de gegevensopslagruimte opslaat—wordt doorgegeven.

* **Verzenden naar Forms-workflow**: Uitvoerparameters die worden geretourneerd uit de formulierwerkstroom, worden doorgegeven.

* **Verzenden naar REST-eindpunt**: Parameters die voor parametertoewijzing in het veld worden toegevoegd, worden doorgegeven. `status` en er worden geen  `owner` parameters doorgegeven in deze verzendactie. Voor meer informatie, zie [Vormend Submit aan het eindpunt REST verzenden actie](/help/forms/using/configuring-submit-actions.md).
