---
title: Compatibiliteitspakket
seo-title: Compatibiliteitspakket
description: 'Als u het compatibiliteitspakket op AEM Forms 6.4 installeert, kunt u de Correspondentenbeheermiddelen van AEM Forms 6.3 en afgekeurde adaptieve formuliersjablonen en pagina''s gebruiken '
seo-description: Als u het compatibiliteitspakket op AEM Forms 6.4 installeert, kunt u de Correspondentenbeheermiddelen van AEM Forms 6.3 en afgekeurde adaptieve formuliersjablonen en pagina's gebruiken
uuid: e50b1ff9-c357-422a-8da8-a791ff805317
contentOwner: gtalwar
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: correspondence-management
geptopics: SG_AEMFORMS/categories/jee
discoiquuid: 38a80992-2eda-4535-89af-0de34b1a9686
translation-type: tm+mt
source-git-commit: 9a2ebded0068213903020d2c5633a05b6ffb07ef

---


# Compatibiliteitspakket installeren {#compatibility-package}

Als u het compatibiliteitspakket op AEM Forms 6.4 installeert, kunt u de Correspondentenbeheermiddelen van AEM Forms 6.3 en afgekeurde adaptieve formuliersjablonen en pagina&#39;s gebruiken

## Overzicht {#overview}

De interactieve mededeling is het gebrek en geadviseerde benadering om klantenmededelingen in Vormen 6.4 tot stand te brengen AEM. Als u de letters van AEM 6.3 Forms en AEM 6.2 Forms wilt blijven gebruiken, moet u het [compatibiliteitspakket](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/fd/AEM-FORMS-6.4-COMPAT)AEMFD installeren.

Met het pakket AEMFD-compatibiliteit kunt u de volgende elementen van AEM Forms 6.3 en 6.2 op AEM Forms 6.4 gebruiken:

* Documentfragmenten die zijn gemaakt in AEM Forms 6.3 en 6.2
* Letters
* Gegevenswoordenboeken
* Afgekeurde sjablonen en pagina&#39;s voor adaptieve formulieren

Zie [Elementen die compatibel zijn gemaakt met AEM Forms 6.4 door het compatibiliteitspakket](/help/forms/using/compatibility-package.md#assetsmadecompatible)te installeren voor meer informatie.

## Voeg ondersteuning toe voor AEM Forms 6.3- en 6.2-elementen in AEM Forms 6.4 {#add-support-for-aem-forms-and-assets-in-aem-forms}

Nadat u een upgrade hebt uitgevoerd, voert u de volgende handelingen uit om het compatibiliteitspakket voor AEMFD te installeren en uw elementen compatibel te maken met 6.4:

Zorg ervoor dat u het [AEM-compatibiliteitspakket](/help/sites-deploying/backward-compatibility.md) vooraf hebt geïnstalleerd.

1. Installeer het [compatibiliteitspakket](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/fd/AEM-FORMS-6.4-COMPAT).

   Zie [Werken met pakketten](/help/sites-administering/package-manager.md)voor meer informatie over het uploaden en installeren van het pakket.

1. Start de server opnieuw nadat de logbestanden zijn gestabiliseerd.
1. Gebruik het migratiehulpprogramma om uw middelen compatibel te maken met 6.4.

   Zie [migratiehulpprogramma](/help/forms/using/migration-utility.md)voor meer informatie.

## Elementen die compatibel zijn gemaakt met AEM Forms 6.4 door het compatibiliteitspakket te installeren {#assetsmadecompatible}

Door het compatibiliteitspakket te installeren, kunt u de volgende elementen en sjablonen compatibel maken met AEM Forms 6.4:

* Correspondentenbeheeractiva van AEM 6.3 en lager

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

