---
title: Forms Repositoregeling Herstructurering in AEM 6.4
seo-title: Forms Repository Restructuring in AEM 6.4
description: Leer hoe u de noodzakelijke wijzigingen aanbrengt om te migreren naar de nieuwe repository structuur in AEM 6.4 voor Forms.
seo-description: Learn how to make the necessary changes in order to migrate to the new repository structure in AEM 6.4 for Forms.
uuid: e60830d4-23ca-4be9-941a-ee4abe4786a6
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: repo_restructuring
discoiquuid: 1ce9a622-5968-407f-a74b-d325a2bff669
feature: Upgrading
exl-id: a2d6524e-3f5b-4d1e-af64-61ff95889657
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 0%

---

# Forms Repositoregeling Herstructurering in AEM 6.4{#forms-repository-restructuring-in-aem}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Zoals beschreven op het bovenliggende element [Herstructurering van de depositaris in AEM 6.4](/help/sites-deploying/repository-restructuring.md) op de pagina, moeten klanten die een upgrade uitvoeren naar AEM 6.4 deze pagina gebruiken om de werkinspanning te beoordelen die gepaard gaat met wijzigingen in de opslagplaats die gevolgen hebben voor de AEM Forms-oplossing. Sommige veranderingen vereisen het werk inspanning tijdens het AEM 6.4 verbeteringsproces, terwijl anderen tot een verbetering van 6.5 kunnen worden uitgesteld.

**Met 6.4-upgrade**

* [Dic](/help/sites-deploying/forms-repository-restructuring-in-aem-6-4.md#misc)

**Vóór upgrade naar 6.5**

* [Configuratie EchoSign-Cloud Service](/help/sites-deploying/forms-repository-restructuring-in-aem-6-4.md#echosign-cloud-service-configuration)
* [Configuraties van Recaptcha-Cloud Servicen](/help/sites-deploying/forms-repository-restructuring-in-aem-6-4.md#recaptcha-cloud-service-configurations)
* [Configuraties van Typekit-Cloud Servicen](/help/sites-deploying/forms-repository-restructuring-in-aem-6-4.md#typekit-cloud-service-configurations)
* [Dic](/help/sites-deploying/forms-repository-restructuring-in-aem-6-4.md#misc)

## Met 6.4-upgrade {#with-upgrade}

### Dic {#misc}

| **Vorige locatie** | `/etc/clientlibs/fd/fp` |
|---|---|
| **Nieuwe locatie(s)** | `/libs/fd/fp/components` |
| **Herstructureringsrichtsnoeren** | Om het even welke expliciete verwijzingen in douanecode aan de plaats van de Oudheid moeten aan de Nieuwe plaats worden bijgewerkt. |
| **Notities** | Deze clientbibliotheken mogen niet worden gewijzigd of uitgebreid. |

| **Vorige locatie** | `/etc/clientlibs/fd/rte` |
|---|---|
| **Nieuwe locatie(s)** | `/libs/fd/rte` |
| **Herstructureringsrichtsnoeren** | Voor de middelen in de cliëntbibliotheken die door absolute wegen kunnen worden bedoeld, moet u nieuwere wegen in verse activa gebruiken. |
| **Notities** | N.v.t. |

| **Vorige locatie** | `/etc/clientlibs/fd/af` |
|---|---|
| **Nieuwe locatie(s)** | `/libs/fd/af/authoring/clientlibs` |
| **Herstructureringsrichtsnoeren** | Voor de middelen in de cliëntbibliotheken die door absolute wegen kunnen worden bedoeld, moet u nieuwere wegen in verse activa gebruiken. |
| **Notities** | N.v.t. |

| **Vorige locatie** | `/etc/clientlibs/fd/xfaforms` |
|---|---|
| **Nieuwe locatie(s)** | `/libs/fd/xfaforms/clientlibs/` |
| **Herstructureringsrichtsnoeren** | Voor de middelen in de cliëntbibliotheken die door absolute wegen kunnen worden bedoeld, moet u nieuwere wegen in verse activa gebruiken. |
| **Notities** | N.v.t. |

| **Vorige locatie** | `/etc/clientlibs/fd/af` |
|---|---|
| **Nieuwe locatie(s)** | `/libs/fd/af/runtime/clientlibs` |
| **Herstructureringsrichtsnoeren** | Voor de middelen in de cliëntbibliotheken die door absolute wegen kunnen worden bedoeld, moet u nieuwere wegen in verse activa gebruiken. |
| **Notities** | N.v.t. |

| **Vorige locatie** | `/etc/clientlibs/fd/af` |
|---|---|
| **Nieuwe locatie(s)** | `/libs/fd/af/runtime/clientlibs` |
| **Herstructureringsrichtsnoeren** | Voor de middelen in de cliëntbibliotheken die door absolute wegen kunnen worden bedoeld, moet u nieuwere wegen in verse activa gebruiken. |
| **Notities** | N.v.t. |

| **Vorige locatie** | `/etc/clientlibs/fd/expeditor` |
|---|---|
| **Nieuwe locatie(s)** | `/libs/fd/expeditor/clientlibs` |
| **Herstructureringsrichtsnoeren** | Voor de middelen in de cliëntbibliotheken die door absolute wegen kunnen worden bedoeld, moet u nieuwere wegen in verse activa gebruiken. |
| **Notities** | N.v.t. |

| **Vorige locatie** | `/etc/clientlibs/fd/fmaddon` |
|---|---|
| **Nieuwe locatie(s)** | `/libs/fd/fmaddon` |
| **Herstructureringsrichtsnoeren** | Het wijzigen van deze clientlibs is nooit aanbevolen of ondersteund. Als deze clientlibs zijn gewijzigd, moeten ze worden teruggedraaid om de AEM code te gebruiken. |
| **Notities** | N.v.t. |

| **Vorige locatie** | `/etc/aep` |
|---|---|
| **Nieuwe locatie(s)** | `/var/fd/content/annotations` |
| **Herstructureringsrichtsnoeren** | Het wijzigen van deze clientlibs is nooit aanbevolen of ondersteund. Als deze clientlibs zijn gewijzigd, moeten ze worden teruggedraaid om de AEM code te gebruiken. |
| **Notities** | N.v.t. |

## Vóór upgrade naar 6.5 {#prior-to-upgrade}

### Configuratie EchoSign-Cloud Service {#echosign-cloud-service-configuration}

| **Vorige locatie** | `/etc/cloudservices/echosign` |
|---|---|
| **Nieuwe locatie(s)** | `/conf/<tenant>/settings/cloudconfigs/echosign` |
| **Herstructureringsrichtsnoeren** | De [Lazy Content Migration](/help/sites-deploying/lazy-content-migration.md) te activeren hulpprogramma vanuit de gebruikersinterface van Forms Migration. |
| **Notities** | N.v.t. |

### Configuraties van Recaptcha-Cloud Servicen {#recaptcha-cloud-service-configurations}

| **Vorige locatie** | `/etc/cloudservices/recaptcha` |
|---|---|
| **Nieuwe locatie(s)** | `/conf/<tenant>/settings/cloudconfigs/recaptcha` |
| **Herstructureringsrichtsnoeren** | De [Lazy Content Migration](/help/sites-deploying/lazy-content-migration.md) te activeren hulpprogramma vanuit de gebruikersinterface van Forms Migration. |
| **Notities** | N.v.t. |

### Configuraties van Typekit-Cloud Servicen {#typekit-cloud-service-configurations}

| **Vorige locatie** | `/etc/cloudservices/typekit` |
|---|---|
| **Nieuwe locatie(s)** | `/conf/<tenant>/settings/cloudconfigs/typekit` |
| **Herstructureringsrichtsnoeren** | De [Lazy Content Migration](/help/sites-deploying/lazy-content-migration.md) te activeren hulpprogramma vanuit de gebruikersinterface van Forms Migration. |
| **Notities** | N.v.t. |

### Dic {#misc-1}

| **Vorige locatie** | `/etc/cloudservices/fdm` |
|---|---|
| **Nieuwe locatie(s)** | `/conf/<tenant>/settings/cloudconfigs/fdm` |
| **Herstructureringsrichtsnoeren** | De [Lazy Content Migration](/help/sites-deploying/lazy-content-migration.md) te activeren hulpprogramma vanuit de gebruikersinterface van Forms Migration. |
| **Notities** | N.v.t. |

| **Vorige locatie** | `/etc/designs/fd/fp` |
|---|---|
| **Nieuwe locatie(s)** | `/libs/fd/fp` |
| **Herstructureringsrichtsnoeren** | Eventuele verwijzingen naar de sjablonen /etc moeten uiteindelijk worden bijgewerkt zodat ze verwijzen naar hun `/libs` tegenhangers. |
| **Notities** | N.v.t. |
