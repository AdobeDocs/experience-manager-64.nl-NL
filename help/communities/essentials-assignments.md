---
title: Essentiële toewijzingen
seo-title: Essentiële toewijzingen
description: Overzicht van de toewijzingsfuncties voor gemeenschappen die in staat zijn om te werken
seo-description: Overzicht van de toewijzingsfuncties voor gemeenschappen die in staat zijn om te werken
uuid: 8310decf-174d-4e93-8c92-4a9583077b7a
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 796781e6-5cab-4ea1-b484-0945bc8febbf
translation-type: tm+mt
source-git-commit: 4d64494dff34108d32e060a96209df697b2ce11f
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 0%

---


# Hoofdzaak van toewijzingen {#assignments-essentials}

Deze pagina verstrekt de essentiële informatie voor het werken met de toewijzingseigenschap van [enablement community](overview.md#enablement-community) plaatsen.

De toewijzingsfunctie is de mogelijkheid om bronnen voor activering en leerpaden toe te wijzen aan leden van gemeenschappen die activering mogelijk maken.

## Essentiële elementen voor client-side {#essentials-for-client-side}

<table> 
 <tbody>
  <tr>
   <td> <strong>resourceType</strong></td> 
   <td>social/enablement/components/hbs/myassigned</td> 
  </tr>
  <tr>
   <td> <a href="scf.md#add-or-include-a-communities-component"><strong>inclusief</strong></a></td> 
   <td>Nee</td> 
  </tr>
  <tr>
   <td> <a href="clientlibs.md"><strong>clientllibs</strong></a></td> 
   <td>cq.social.enablement.hbs.breadcrumbs<br /> cq.social.enablement.hbs.myassigned<br /> cq.social.enablement.hbs.resource<br /> cq.social.enablement.hbs.learningpath</td> 
  </tr>
  <tr>
   <td> <strong>templates</strong></td> 
   <td> /libs/social/enablement/components/hbs/myassigned/myassigned.hbs</td> 
  </tr>
  <tr>
   <td> <strong>css</strong></td> 
   <td> /libs/social/enablement/components/hbs/myassigned/clientlibs/myassigned.css</td> 
  </tr>
  <tr>
   <td><strong> eigenschappen</strong></td> 
   <td>Zie <a href="assignments.md">Toewijzingsfunctie</a></td> 
  </tr>
 </tbody>
</table>

### Voltooiings- en successtatus {#completion-and-success-status}

De voltooiings- en successtatus worden gebruikt in rapporten en statusbanners bij toewijzingen.

Voltooiingsstatus:

* Niet toegewezen
* Niet gestart (nieuw)
* In uitvoering
* Voltooid

Successtatus:

* Onbekend
* Voldoende
* Mislukt

De enige mogelijke combinaties van Voltooiing en Successtatus zijn:

| **Voltooiing** | **Succes** |
|---|---|
| Niet gestart | Onbekend |
| In uitvoering | Onbekend |
| Voltooid | Voldoende |
| Voltooid | Mislukt |

## Essentiële elementen voor server-side {#essentials-for-server-side}

### Toewijzingsfunctie {#assignments-function}

Een community-sitestructuur die de [toewijzingsfunctie](functions.md#assignments-function) bevat, bevat een geconfigureerde ` [assignments](assignments.md)`-component.

### Referentie-API&#39;s {#reference-apis}

* [Inschakelings-API](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/enablement/reporting/model/api/package-summary.html)

* [API voor rapportage](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/reporting/dv/api/package-summary.html)

* [API voor analyse van rapporten](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/reporting/analytics/api/package-summary.html)