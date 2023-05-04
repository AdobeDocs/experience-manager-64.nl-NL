---
title: Formulieruitvoer configureren
seo-title: Configuring form output
description: Leer hoe u formulieruitvoer configureert.
seo-description: Learn how to configure form output.
uuid: 70aad14e-c845-4ef3-a751-ad8860d5d505
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_forms
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 17c9b69a-3c6f-47e3-a828-841bb90eba8b
exl-id: b19cae88-a549-41ba-b4a6-4b065a995296
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 0%

---

# Formulieruitvoer configureren{#configuring-form-output}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Het type HTML-uitvoer opgeven dat wordt geretourneerd aan de webbrowser {#specify-the-type-of-html-output-returned-to-the-web-browser}

1. Klik in de beheerconsole op Services > Formulieren.
1. Selecteer onder Uitvoer formulier in de lijst Uitvoertype een van de volgende opties:

   **Volledige HTML:** Het formulier weergeven binnen volledige HTML-tags (een volledige HTML-pagina). Dit is de standaardwaarde.

   **Hoofdtekst van formulier:** Het formulier weergeven binnen `<BODY>` -tags (geen volledige HTML-pagina).

1. Klik op Opslaan.

## De locatie opgeven waar PDF-inhoud wordt gerenderd {#specify-the-location-where-pdf-content-is-rendered}

1. Selecteer onder Formulieruitvoer in de lijst Renderen op een van de volgende opties:

   **Client:** PDF forms renderen in Adobe Acrobat of Adobe Reader. Rendering op de client verbetert de prestaties van AEM formulieren en is alleen van toepassing op PDFForm-transformatie.

   **Server:** PDF forms renderen op de toepassingsserver.

   **Automatisch:** Het PDF-formulier weergeven op de locatie die door de `dynamicRender` configuratiewaarde van het XDP-bestand. Dit is de standaardwaarde.

1. Klik op Opslaan.

## Aanroepen van aangepaste scripts configureren voordat het formulier wordt verzonden {#configuring-invocation-of-custom-scripts-before-form-submit}

Voer de volgende stappen uit om de functie in te schakelen:

1. Meld u aan bij de beheerconsole.
1. Ga naar **Services** > **formulieren**.
1. Geef het uitvoertype op als Formulierhoofdtekst.
1. Sla de instellingen op.
1. Declareer een JavaScript-variabele, __CUSTOM_SCRIPTS_VERSION, in de kopsectie van de HTML-code en stel de waarde ervan in op 1.

   >[!NOTE]
   >
   >*Als u de functie wilt uitschakelen, kunt u de JavaScript-variabele verwijderen of de waarde ervan instellen op 0.*
