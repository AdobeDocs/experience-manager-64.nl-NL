---
title: portalcomponenten voor formulieren inschakelen
seo-title: Enabling forms portal components
description: Forms Portal-componenten zijn uitgeschakeld. Schakel Document Services en Document Services Predicates-groepen in om Forms Portal-componenten in te schakelen.
seo-description: Out of the box, Forms Portal components are disabled. Enable Document Services and Document Services Predicates groups to enable Forms Portal components.
uuid: 92d25da6-f1df-4ac0-bf84-2edf9e2722b3
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: publish
discoiquuid: 4d318908-c724-4582-a82b-6e9b1c55705b
feature: Forms Portal
exl-id: 01c5eb6b-b097-4354-84b2-8bee7b7626f2
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 0%

---

# portalcomponenten voor formulieren inschakelen {#enabling-forms-portal-components}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

De onderdelen van de portal Formulieren zijn niet beschikbaar voor gebruik. Voer de volgende stappen uit om de componenten weer te geven in de lijst met beschikbare componenten in AEM sidekick:

1. Meld u aan bij de auteur van uw website en open een AEM Sites-pagina.

1. Voer de volgende stappen uit voor de pagina&#39;s die een statische sjabloon gebruiken:

   1. Tik in de paginakoptekst op ![canvas-drop-down](assets/canvas-drop-down.png) > **Ontwerp** om de pagina in de ontwerpmodus te openen.
   1. Tik op een component (met een blauwe rand) en tik vervolgens op ![op veldniveau](assets/field-level.png) om het alineasysteem te selecteren dat de huidige component bevat.
   1. Tik in het alineasysteem op ![settings_icon](assets/settings_icon.png) om het dialoogvenster Bewerken voor het alineasysteem te openen.
   1. Uit de lijst met **[!UICONTROL Allowed Components]** Schakel selectievakjes in voor **[!UICONTROL Document Services]** en **[!UICONTROL Document Services Predicates]** componenten. Tik op **[!UICONTROL OK]**.

1. Voer de volgende stappen uit voor de pagina&#39;s die een dynamische sjabloon gebruiken:

   1. Tik in de paginakoptekst op ![eigenschappen](assets/properties.png) > **Sjabloon bewerken** om de sjabloon van de pagina te openen.
   1. Tikken **Layout Container** en tikken ![FeedManagement](assets/FeedManagement.png). In de **Toegestane componenten** tab, inschakelen **Documentservices en prognoses voor documentservices** en tikken ![aem_6_3_forms_save](assets/aem_6_3_forms_save.png).

>[!NOTE]
>
>U kunt ook specifieke componenten van deze categorieën inschakelen door de componenten te selecteren. Voor meer informatie over de componenten en hun gebruik, zie [Een pagina met een formulierportal maken](/help/forms/using/creating-form-portal-page.md) en [Koppelingscomponent insluiten in een pagina](/help/forms/using/embedding-link-component-page.md).

De componentcategorieën Document Services en Document Services Predicates zijn nu beschikbaar in de componentbrowser. De componenten worden ingeschakeld voor alle pagina&#39;s die dezelfde sjabloon gebruiken.

## Verwante artikelen

* [Formulierportonderdelen inschakelen](/help/forms/using/enabling-forms-portal-components.md)
* [Pagina Formulierportal maken](/help/forms/using/creating-form-portal-page.md)
* [Formulieren op een webpagina weergeven met API&#39;s](/help/forms/using/listing-forms-webpage-using-apis.md)
* [Concepten en verzendingscomponent gebruiken](/help/forms/using/draft-submission-component.md)
* [Opslag van concepten en verzonden formulieren aanpassen](/help/forms/using/draft-submission-component.md)
* [Voorbeeld voor het integreren van concepten en verzendingen in de database](/help/forms/using/integrate-draft-submission-database.md)
* [Sjablonen aanpassen voor componenten van een formulierportal](/help/forms/using/customizing-templates-forms-portal-components.md)
* [Inleiding tot het publiceren van formulieren op een portal](/help/forms/using/introduction-publishing-forms.md)
