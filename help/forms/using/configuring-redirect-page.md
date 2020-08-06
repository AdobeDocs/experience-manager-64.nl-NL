---
title: Omleidingspagina configureren
seo-title: Omleidingspagina configureren
description: Nadat u een adaptief formulier hebt ingevuld, kunnen gebruikers worden omgeleid naar een webpagina die formulierauteurs kunnen configureren tijdens het maken van het formulier.
seo-description: Nadat u een adaptief formulier hebt ingevuld, kunnen gebruikers worden omgeleid naar een webpagina die formulierauteurs kunnen configureren tijdens het maken van het formulier.
uuid: 5a5f912a-9696-4bc1-af3f-ead78f767e02
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: author
discoiquuid: c51817aa-193a-4d4f-bd83-06518ddfb395
translation-type: tm+mt
source-git-commit: 8cbfa421443e62c0483756e9d5812bc987a9f91d
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 0%

---


# Omleidingspagina configureren {#configuring-redirect-page}

Formulierauteurs kunnen een pagina configureren voor elk formulier, waarnaar de formuliergebruikers worden omgeleid na het verzenden van een formulier.

1. Selecteer in de bewerkingsmodus een component, klik vervolgens op ![veldniveau](assets/field-level.png) > **Aangepaste formuliercontainer** en klik vervolgens op ![cmr](assets/cmppr.png).

1. Klik in de zijbalk op **Verzenden**.

1. Geef de URL van de omleidingspagina op onder Vorige pagina in de sectie Verzending.
1. Naar keuze, onder Verzenden Actie, voor Submit aan de het eindpuntactie van REST, kunt u de parameter vormen die tot de omleidingspagina wordt overgegaan.

![Pagina-configuratie](assets/thank-you-setting-1.png)**figuur omleiden:** *Pagina-configuratie omleiden*

Auteurs van formulieren kunnen de volgende parameters gebruiken die worden doorgegeven aan de pagina Bedankt. Voor alle beschikbare verzendhandelingen `status` en worden `owner` parameters doorgegeven. Naast deze twee parameters worden enkele aanvullende parameters doorgegeven voor de volgende verzendacties:

* **Handeling** voor inhoud opslaan (afgekeurd): `contentPath`—het pad van het knooppunt in de gegevensopslagruimte waar de verzonden gegevens worden opgeslagen—wordt doorgegeven.

* **PDF-handeling** opslaan (afgekeurd): `contentPath`—van de verzonden gegevens en het pad naar het knooppunt dat het PDF-bestand in de gegevensopslagruimte opslaat—wordt doorgegeven.

* **Verzenden naar Forms-workflow**: Uitvoerparameters die worden geretourneerd uit de formulierwerkstroom, worden doorgegeven.

* **Verzenden naar REST-eindpunt**: Parameters die voor parametertoewijzing in het veld worden toegevoegd, worden doorgegeven. `status` en er `owner` worden geen parameters doorgegeven in deze verzendactie. Voor meer informatie, zie het [Vormen van Submit aan REST eindpunt voorlegt actie](/help/forms/using/configuring-submit-actions.md).

