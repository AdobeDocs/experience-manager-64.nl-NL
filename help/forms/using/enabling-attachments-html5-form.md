---
title: Bijlagen inschakelen voor een HTML5-formulier
seo-title: Enabling attachments for an HTML5 form
description: Standaard is de ondersteuning voor bijlagen voor HTML5-formulieren uitgeschakeld.
seo-description: By default, the attachment support for HTML5 forms is disabled.
uuid: 2c62ac3e-4b27-46c7-a61d-a805fb5d26fb
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: hTML5_forms
discoiquuid: 8eebfcd6-0597-44ed-b718-bf9a1baa6c12
feature: Mobile Forms
exl-id: 82a843c4-5cb2-4f5e-ad4d-cf2e9ea6cdb8
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 0%

---

# Bijlagen inschakelen voor een HTML5-formulier {#enabling-attachments-for-an-html-form}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

U kunt bijlagen uploaden, een voorbeeld bekijken en verzenden met HTML5-formulieren. Standaard is de ondersteuning voor bijlagen uitgeschakeld. De ondersteuning voor bijlagen inschakelen:

1. Een [aangepast profiel](/help/forms/using/custom-profile.md) met multiselect, tekenreekseigenschap `mfAttachmentOptions`.
1. Geef in het aangepaste profiel eigenschappen op `fileSizeLimit`, `multiSelect`, en `buttonTex`Hiermee configureert u opties voor de bestandsbijlage-widget. Desgewenst kunt u ook meer aangepaste eigenschappen opgeven.

1. Gebruik de volgende configuraties in het aangepaste profiel:

   * **multiSelect** -> true of false (standaard true)
   * **fileSizeLimit** -> value_in_mb (say 5) (standaard 2 MB)
   * **buttonText** -> Knoptekst voor pop-upvenster (&quot;Bijvoegen&quot; standaard)
   * **accepteren** -> te accepteren bestandstypen (&quot;audio/&amp;ast;, video/&amp;ast;, afbeelding/&amp;ast;, tekst/&amp;ast;, standaard .pdf&quot;)

   >[!NOTE]
   >
   >In Microsoft Internet Explorer 9 kunnen gebruikers bestanden bijvoegen die groter zijn dan de opgegeven limiet. Het is een bekend probleem.

1. Gebruik de [metagegevenseditor](/help/forms/using/manage-form-metadata.md) om het aangepaste profiel te selecteren dat u hierboven hebt gemaakt voor HTML 5-formulieren.
1. U geeft de formuliersjabloon weer met een aangepast profiel en het pictogram Bijlagen wordt weergegeven op de werkbalk Formulieren.

   >[!NOTE]
   >
   >Het portal Formulieren bevat een aangepast profiel met de mogelijkheden voor concepten en bijlagen ingeschakeld. Voor meer informatie over de **Opslaan als concept** profiel, zie [HTML5-formulieren opslaan als concept](/help/forms/using/saving-html5-form-draft.md).

1. Klik op het pictogram voor bijlagen en er verschijnt een dialoogvenster voor het selecteren van bijlagen. Blader en selecteer de bijlage en klik op **Koppelen**.

   >[!NOTE]
   >
   >Klik op de naam van een bijlage om een voorbeeld van een bijlage weer te geven.

   >[!NOTE]
   >
   >De optie voor het voorvertonen van bestanden is niet beschikbaar voor anonieme gebruikers.

## Indeling voor het verzenden van bijlagen {#attachment-submission-format}

Als bijlagen zijn ingeschakeld, verzendt HTML5-formulier meerdelige gegevens. De uit meerdere delen bestaande indieningsgegevens bestaan uit twee delen **dataXml** en **bijlagen**.

>[!NOTE]
>
>Voor achterwaartse compatibiliteit, als `mfAllowAttachments`is uitgeschakeld, worden de meerdelige gegevens niet verzonden door de HTML5-formulieren. Het verzendt eenvoudige gegevens-xml in **application/xml** gebruiken.

Als de markering mfAllowAttachments is ingeschakeld, [service-proxy verzenden](/help/forms/using/service-proxy.md) Hiermee worden ook meerdelige gegevens gepost met dataXml en bijlagen.
