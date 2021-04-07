---
title: 'Plaatsaanduidingstekst in AEM Forms '
seo-title: 'Plaatsaanduidingstekst in AEM Forms '
description: Plaatsaanduidingstekst is bedoeld om de gebruiker te helpen bij het invoeren van gegevens wanneer het besturingselement geen waarde heeft. Dit kan een samplewaarde of een korte beschrijving van de verwachte indeling zijn.
seo-description: Plaatsaanduidingstekst is bedoeld om de gebruiker te helpen bij het invoeren van gegevens wanneer het besturingselement geen waarde heeft. Dit kan een samplewaarde of een korte beschrijving van de verwachte indeling zijn.
uuid: 553ed988-ad2c-4bdb-bf1e-332e48cf7dfa
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: author
discoiquuid: 2d7367fa-6cb8-40a1-8566-1fd0d46fdfde
feature: Adaptieve Forms
exl-id: 26a1a5f7-b4d4-4f38-81a4-5f2d39702138
translation-type: tm+mt
source-git-commit: bd94d3949f0117aa3e1c9f0e84f7293a5d6b03b4
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 0%

---

# Plaatsaanduidingstekst in AEM Forms {#placeholder-text-in-aem-forms}

De plaatsaanduidingstekst vertegenwoordigt een woord of korte woordgroep. Het is bedoeld om de gebruiker van gegevensingang te helpen wanneer de controle geen waarde heeft. Een plaatsaanduidingstekst kan een voorbeeldwaarde of een korte beschrijving van de verwachte indeling zijn. De tekst van de plaatsaanduiding wordt weergegeven voordat de gebruiker een waarde invoert. De tekst wordt verwijderd wanneer de gebruiker een waarde invoert of selecteert.

>[!NOTE]
>
>De plaatsaanduidingstekst moet, indien opgegeven, een waarde hebben die geen nieuwe regeltekens bevat.

![Datumcomponent met en zonder plaatsaanduidingstekst](assets/dat-picker-place-holder-text.png)

**A.** Date-component met plaatsaanduidingstekst  **B.** Date-component zonder plaatsaanduidingstekst

AEM Forms biedt ondersteuning voor plaatsaanduidingstekst voor de velden Wachtwoord, Datumkiezer, Numeriek vak en Tekstvak.\
Plaatsaanduidingsteksten worden niet ondersteund voor de native HTML5-datumwidget. Een plaatsaanduidingstekst opgeven:

1. Klik met de rechtermuisknop op een component die plaatsaanduidingstekst ondersteunt en klik op **Bewerken**. Het dialoogvenster Component bewerken wordt geopend.

1. Open het tabblad **Titel en tekst**.
1. Geef een woord of korte woordgroep op in het tekstvak **Plaatsaanduiding**. Klik **OK**.

>[!NOTE]
>
>Plaatsaanduidingstekst wordt niet ondersteund in Microsoft Internet Explorer 9.
