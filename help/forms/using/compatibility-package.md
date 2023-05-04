---
title: Compatibiliteitspakket
seo-title: Compatibility Package
description: Als u het compatibiliteitspakket op AEM Forms 6.4 installeert, kunt u de Correspondence Management-middelen van AEM Forms 6.3 en afgekeurde aangepaste formuliersjablonen en pagina's gebruiken
seo-description: Installing the Compatibility package on AEM Forms 6.4 allows you to use the Correspondence Management assets from AEM Forms 6.3 and deprecated adaptive forms templates and pages
uuid: e50b1ff9-c357-422a-8da8-a791ff805317
contentOwner: gtalwar
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: correspondence-management, installing
geptopics: SG_AEMFORMS/categories/jee
discoiquuid: 38a80992-2eda-4535-89af-0de34b1a9686
role: Admin
exl-id: 0bfa0e65-c4cd-4c37-b42b-bff1b777a7be
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 0%

---

# Compatibiliteitspakket installeren {#compatibility-package}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Als u het compatibiliteitspakket op AEM Forms 6.4 installeert, kunt u de Correspondence Management-middelen van AEM Forms 6.3 en afgekeurde aangepaste formuliersjablonen en pagina&#39;s gebruiken

## Overzicht {#overview}

De interactieve mededeling is het gebrek en geadviseerde benadering om klantenmededelingen in AEM Forms 6.4 tot stand te brengen. Als u de letters van AEM 6.3 Forms en AEM 6.2 Forms wilt blijven gebruiken, moet u de [AEMFD-compatibiliteitspakket](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/forms-updates/aem-forms-releases.html).

Met het compatibiliteitspakket AEMFD kunt u de volgende middelen van AEM Forms 6.3 en 6.2 op AEM Forms 6.4 gebruiken:

* Documentfragmenten gemaakt in AEM Forms 6.3 en 6.2
* Letters
* Gegevenswoordenboeken
* Afgekeurde sjablonen en pagina&#39;s voor adaptieve formulieren

Zie voor meer informatie [Activa die compatibel zijn gemaakt met AEM Forms 6.4 door het compatibiliteitspakket te installeren](/help/forms/using/compatibility-package.md#assetsmadecompatible).

## Voeg ondersteuning toe voor AEM Forms 6.3- en 6.2-middelen in AEM Forms 6.4 {#add-support-for-aem-forms-and-assets-in-aem-forms}

Nadat u een upgrade hebt uitgevoerd, voert u de volgende handelingen uit om het compatibiliteitspakket voor AEMFD te installeren en uw elementen compatibel te maken met 6.4:

Zorg ervoor dat u [Compatibiliteitspakket AEM](/help/sites-deploying/backward-compatibility.md) vooraf geïnstalleerd.

1. Installeer de [Compatibiliteitspakket](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/forms-updates/aem-forms-releases.html).

   Voor meer informatie over het uploaden en installeren van het pakket raadpleegt u [Werken met pakketten](/help/sites-administering/package-manager.md).

1. Start de server opnieuw nadat de logbestanden zijn gestabiliseerd.
1. Gebruik het migratiehulpprogramma om uw middelen compatibel te maken met 6.4.

   Zie voor meer informatie [migratiehulpprogramma](/help/forms/using/migration-utility.md).

## Activa die compatibel zijn gemaakt met AEM Forms 6.4 door het compatibiliteitspakket te installeren {#assetsmadecompatible}

Door het compatibiliteitspakket te installeren, kunt u de volgende elementen en sjablonen compatibel maken met AEM Forms 6.4:

* Correspondentenbeheeractiva uit AEM 6.3 en lager

   * [Letters](/help/forms/using/create-letter.md)
   * [Gegevenswoordenboeken](/help/forms/using/data-dictionary.md)
   * Documentfragmenten

* Afgekeurde sjablonen voor adaptieve formulieren

   * /libs/fd/af/templates/blankTemplate2
   * /libs/fd/af/templates/simpleEnrollmentTemplate
   * /libs/fd/af/templates/simpleEnrollmentTemplate2
   * /libs/fd/af/templates/surveyTemplate
   * /libs/fd/af/templates/surveyTemplate2
   * /libs/fd/af/templates/tabbedEnrollmentTemplate
   * /libs/fd/af/templates/tabbedEnrollmentTemplate2
   * /libs/fd/afaddon/templates/advancedEnrollmentTemplate
   * /libs/fd/afaddon/templates/advancedEnrollmentTemplate2

* Afgekeurde pagina&#39;s voor adaptieve formulieren:

   * /libs/fd/af/components/page/survey
   * /libs/fd/af/components/page/tabbedenrollment
   * /libs/fd/afaddon/components/page/advancedRolment
