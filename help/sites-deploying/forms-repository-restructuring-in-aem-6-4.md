---
title: Forms Repository Herstructurering in AEM 6.4
seo-title: Forms Repository Herstructurering in AEM 6.4
description: Leer hoe u de benodigde wijzigingen aanbrengt om te migreren naar de nieuwe opslagstructuur in AEM 6.4 for Forms.
seo-description: Leer hoe u de benodigde wijzigingen aanbrengt om te migreren naar de nieuwe opslagstructuur in AEM 6.4 for Forms.
uuid: e60830d4-23ca-4be9-941a-ee4abe4786a6
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: repo_restructuring
discoiquuid: 1ce9a622-5968-407f-a74b-d325a2bff669
translation-type: tm+mt
source-git-commit: 7b39a715166eeefdf20eb22a4449068ff1ed0e42

---


# Forms Repository Herstructurering in AEM 6.4{#forms-repository-restructuring-in-aem}

Zoals beschreven op de bovenliggende [Repository Reform in AEM 6.4](/help/sites-deploying/repository-restructuring.md) -pagina, moeten klanten die een upgrade uitvoeren naar AEM 6.4 deze pagina gebruiken om de werkinspanning te beoordelen die gepaard gaat met wijzigingen in de opslagplaats die gevolgen hebben voor de AEM Forms Solution. Sommige veranderingen vereisen werk inspanning tijdens het AEM 6.4 verbeteringsproces, terwijl anderen tot een verbetering van 6.5 kunnen worden uitgesteld.

**Met 6.4-upgrade**

* [Dic](/help/sites-deploying/forms-repository-restructuring-in-aem-6-4.md#misc)

**Vóór upgrade naar 6.5**

* [Configuratie EchoSign Cloud-service](/help/sites-deploying/forms-repository-restructuring-in-aem-6-4.md#echosign-cloud-service-configuration)
* [Configuraties van de Recaptcha Cloud-service](/help/sites-deploying/forms-repository-restructuring-in-aem-6-4.md#recaptcha-cloud-service-configurations)
* [Configuraties van Typekit Cloud-service](/help/sites-deploying/forms-repository-restructuring-in-aem-6-4.md#typekit-cloud-service-configurations)
* [Dic](/help/sites-deploying/forms-repository-restructuring-in-aem-6-4.md#misc)

## Met 6.4-upgrade {#with-upgrade}

### Dic {#misc}

| **Vorige locatie** | `/etc/clientlibs/fd/fp` |
|---|---|
| **Nieuwe locatie(s)** | `/libs/fd/fp/components` |
| **Herstructureringsrichtsnoeren** | Om het even welke expliciete verwijzingen in douanecode aan de plaats van de Oudheid moeten aan de Nieuwe plaats worden bijgewerkt. |
| **Opmerkingen** | Deze clientbibliotheken mogen niet worden gewijzigd of uitgebreid. |

| **Vorige locatie** | `/etc/clientlibs/fd/rte` |
|---|---|
| **Nieuwe locatie(s)** | `/libs/fd/rte` |
| **Herstructureringsrichtsnoeren** | Voor de middelen in de cliëntbibliotheken die door absolute wegen kunnen worden bedoeld, moet u nieuwere wegen in verse activa gebruiken. |
| **Opmerkingen** | N.v.t. |

| **Vorige locatie** | `/etc/clientlibs/fd/af` |
|---|---|
| **Nieuwe locatie(s)** | `/libs/fd/af/authoring/clientlibs` |
| **Herstructureringsrichtsnoeren** | Voor de middelen in de cliëntbibliotheken die door absolute wegen kunnen worden bedoeld, moet u nieuwere wegen in verse activa gebruiken. |
| **Opmerkingen** | N.v.t. |

| **Vorige locatie** | `/etc/clientlibs/fd/xfaforms` |
|---|---|
| **Nieuwe locatie(s)** | `/libs/fd/xfaforms/clientlibs/` |
| **Herstructureringsrichtsnoeren** | Voor de middelen in de cliëntbibliotheken die door absolute wegen kunnen worden bedoeld, moet u nieuwere wegen in verse activa gebruiken. |
| **Opmerkingen** | N.v.t. |

| **Vorige locatie** | `/etc/clientlibs/fd/af` |
|---|---|
| **Nieuwe locatie(s)** | `/libs/fd/af/runtime/clientlibs` |
| **Herstructureringsrichtsnoeren** | Voor de middelen in de cliëntbibliotheken die door absolute wegen kunnen worden bedoeld, moet u nieuwere wegen in verse activa gebruiken. |
| **Opmerkingen** | N.v.t. |

| **Vorige locatie** | `/etc/clientlibs/fd/af` |
|---|---|
| **Nieuwe locatie(s)** | `/libs/fd/af/runtime/clientlibs` |
| **Herstructureringsrichtsnoeren** | Voor de middelen in de cliëntbibliotheken die door absolute wegen kunnen worden bedoeld, moet u nieuwere wegen in verse activa gebruiken. |
| **Opmerkingen** | N.v.t. |

| **Vorige locatie** | `/etc/clientlibs/fd/expeditor` |
|---|---|
| **Nieuwe locatie(s)** | `/libs/fd/expeditor/clientlibs` |
| **Herstructureringsrichtsnoeren** | Voor de middelen in de cliëntbibliotheken die door absolute wegen kunnen worden bedoeld, moet u nieuwere wegen in verse activa gebruiken. |
| **Opmerkingen** | N.v.t. |

| **Vorige locatie** | `/etc/clientlibs/fd/fmaddon` |
|---|---|
| **Nieuwe locatie(s)** | `/libs/fd/fmaddon` |
| **Herstructureringsrichtsnoeren** | Het wijzigen van deze clientlibs is nooit aanbevolen of ondersteund. Als deze clientlibs zijn gewijzigd, moeten ze worden teruggedraaid om de door AEM verschafte code te gebruiken. |
| **Opmerkingen** | N.v.t. |

| **Vorige locatie** | `/etc/aep` |
|---|---|
| **Nieuwe locatie(s)** | `/var/fd/content/annotations` |
| **Herstructureringsrichtsnoeren** | Het wijzigen van deze clientlibs is nooit aanbevolen of ondersteund. Als deze clientlibs zijn gewijzigd, moeten ze worden teruggedraaid om de door AEM verschafte code te gebruiken. |
| **Opmerkingen** | N.v.t. |

## Vóór upgrade naar 6.5 {#prior-to-upgrade}

### Configuratie EchoSign Cloud-service {#echosign-cloud-service-configuration}

| **Vorige locatie** | `/etc/cloudservices/echosign` |
|---|---|
| **Nieuwe locatie(s)** | `/conf/<tenant>/settings/cloudconfigs/echosign` |
| **Herstructureringsrichtsnoeren** | Het hulpprogramma [Lazy Content Migration](/help/sites-deploying/lazy-content-migration.md) dat moet worden geactiveerd vanuit de gebruikersinterface voor Forms Migration. |
| **Opmerkingen** | N.v.t. |

### Configuraties van de Recaptcha Cloud-service {#recaptcha-cloud-service-configurations}

| **Vorige locatie** | `/etc/cloudservices/recaptcha` |
|---|---|
| **Nieuwe locatie(s)** | `/conf/<tenant>/settings/cloudconfigs/recaptcha` |
| **Herstructureringsrichtsnoeren** | Het hulpprogramma [Lazy Content Migration](/help/sites-deploying/lazy-content-migration.md) dat moet worden geactiveerd vanuit de gebruikersinterface voor Forms Migration. |
| **Opmerkingen** | N.v.t. |

### Configuraties van Typekit Cloud-service {#typekit-cloud-service-configurations}

| **Vorige locatie** | `/etc/cloudservices/typekit` |
|---|---|
| **Nieuwe locatie(s)** | `/conf/<tenant>/settings/cloudconfigs/typekit` |
| **Herstructureringsrichtsnoeren** | Het hulpprogramma [Lazy Content Migration](/help/sites-deploying/lazy-content-migration.md) dat moet worden geactiveerd vanuit de gebruikersinterface voor Forms Migration. |
| **Opmerkingen** | N.v.t. |

### Dic {#misc-1}

| **Vorige locatie** | `/etc/cloudservices/fdm` |
|---|---|
| **Nieuwe locatie(s)** | `/conf/<tenant>/settings/cloudconfigs/fdm` |
| **Herstructureringsrichtsnoeren** | Het hulpprogramma [Lazy Content Migration](/help/sites-deploying/lazy-content-migration.md) dat moet worden geactiveerd vanuit de gebruikersinterface voor Forms Migration. |
| **Opmerkingen** | N.v.t. |

| **Vorige locatie** | `/etc/designs/fd/fp` |
|---|---|
| **Nieuwe locatie(s)** | `/libs/fd/fp` |
| **Herstructureringsrichtsnoeren** | Eventuele verwijzingen naar de sjablonen /etc moeten uiteindelijk worden bijgewerkt zodat ze naar hun `/libs` tegenhangers verwijzen. |
| **Opmerkingen** | N.v.t. |

