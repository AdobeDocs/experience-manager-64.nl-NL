---
title: Een HTML5-formulier opslaan als concept
seo-title: Saving an HTML5 form as a draft
description: Sla een HTML5-formulier op als concept en hervat het invullen van het formulier in een later stadium.
seo-description: Save an HTML5 form as a draft and resume filling the form at a later stage.
uuid: 70cd5f6f-f125-470c-8cee-ee14d2127713
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: hTML5_forms
discoiquuid: 445e24af-cd1a-414d-bd01-9feb6631bbef
feature: Mobile Forms
exl-id: 8e4ffda9-ea92-4abc-8746-5d1852e4599b
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 0%

---

# Een HTML5-formulier opslaan als concept {#saving-an-html-form-as-a-draft}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

U kunt een HTML5-formulier opslaan als concept en het invullen van het formulier later hervatten. Met Forms Portal kunnen gebruikers een HTML5-formulier opslaan en herstellen. Voeg de volgende configuraties toe aan het profielknooppunt om de functie Opslaan als concept in te schakelen:

## Aangepast profiel om de functie Opslaan als concept toe te staan {#custom-profile-to-allow-save-as-draft-feature}

AEM Forms biedt een **Opslaan als concept** profiel. U kunt een formulier weergeven met het profiel Opslaan als concept om de conceptfunctionaliteit voor een HTML5-formulier in te schakelen. U kunt het HTML-renderprofiel voor een formulier opgeven in [Forms Manager](/help/forms/using/introduction-managing-forms.md).

Opslaan als concept inschakelen voor uw bestaande [aangepast profiel](/help/forms/using/custom-profile.md)voegt u de volgende eigenschappen toe aan het aangepaste profielknooppunt:

<table> 
 <tbody> 
  <tr> 
   <td><strong>Eigenschapnaam</strong></td> 
   <td><strong>Type</strong></td> 
   <td><strong>Waarde</strong></td> 
   <td><strong>Beschrijving</strong></td> 
  </tr> 
  <tr> 
   <td>mfAllowFPDraft</td> 
   <td>String</td> 
   <td>true</td> 
   <td><p>Hiermee wordt de functie Opslaan als concept ingeschakeld</p> <p>voor dit profiel.</p> </td> 
  </tr> 
  <tr> 
   <td>mfAllowAttachments</td> 
   <td>String</td> 
   <td>true</td> 
   <td><p>Hiermee kunt u bijlagen uploaden</p> <p>met dit profiel.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Opslag en aanbieding opstellen {#drafts-storage-and-listing}

Nadat u de functie Opslaan als concept hebt ingeschakeld voor een formulier; wanneer het formulier wordt opgeslagen, wordt het weergegeven in het dialoogvenster [Concepten en verzendingscomponent](/help/forms/using/draft-submission-component.md). U kunt het opgeslagen formulier ophalen en invullen met de component Concept en Verzending.

Voeg de volgende eigenschap toe aan het profielknooppunt om formuliervermelding in te schakelen voor de component Concept en Verzending:

<table> 
 <tbody> 
  <tr> 
   <td><strong>Eigenschapnaam</strong></td> 
   <td><strong>Type</strong></td> 
   <td><strong>Waarde</strong></td> 
   <td><strong>Beschrijving</strong></td> 
  </tr> 
  <tr> 
   <td>fp.enablePortalSubmit</td> 
   <td>String</td> 
   <td>true</td> 
   <td>Concepten en formulieren weergeven in<br /> Forms Portal Concepten en verzendingen na verzending</td> 
  </tr> 
 </tbody> 
</table>

Standaard slaat AEM Forms de gebruikersgegevens die zijn gekoppeld aan het concept en de verzending van een formulier op in het knooppunt /content/forms/fp in het exemplaar Publish. U kunt uw aangepaste opslagprovider toevoegen. Zie voor meer informatie [Aangepaste opslag voor component Concepten en verzendingen](/help/forms/using/adding-custom-storage-provider-forms.md).
