---
title: Overzicht van Health Monitor
seo-title: Overview of Health Monitor
description: Dit document geeft een overzicht van de Health Monitor en informatie over hoe u deze kunt openen.
seo-description: This document provides the overview of the Health monitor, and details about how you can access it.
uuid: 5934fd2d-80a5-4c6d-b3ee-882c2865705b
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/health_monitor
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: c303e967-944d-40b0-96ca-f91e2f42a0d0
exl-id: 70ccc0ae-04c6-4af9-9150-72d0d71c945f
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 0%

---

# Overzicht van Health Monitor {#overview-of-health-monitor}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Health Monitor biedt kritieke informatie over het AEM formuliersysteem, zoals serverinformatie, geheugengebruik en processorgebruik. Ook beschikbaar zijn de statistieken van de Manager van het Werk, zoals het aantal werkpunten of banen in de rij en hun status. U kunt de volgende taken uitvoeren met Health Monitor:

* Controleren of uw systeem correct wordt uitgevoerd
* Informatie weergeven om systeemproblemen te diagnostiseren terwijl deze zich voordoen
* Bewerkingen uitvoeren op werkitems of taken die problemen geven
* Verouderde records uit de taakbeheerdatabase verwijderen

De pagina Health Monitor in de beheerconsole heeft drie tabbladen:

* Het lusje van het Systeem toont middel controlerende grafieken en informatie over de vormenserver (of knoop in een gegroepeerde milieu). (Zie [Systeeminformatie weergeven](/help/forms/using/admin-help/view-system-information.md#view-system-information).)
* Op het tabblad Werkbeheer worden gegevens weergegeven die betrekking hebben op Werkbeheer, zoals het aantal werkitems in de werkbeheerwachtrij. U kunt de informatie filteren door diverse criteria te gebruiken of individuele het werkpunten te beheren door de verrichtingshulpmiddelen te gebruiken. (Zie [Statistieken weergeven met betrekking tot Werkbeheer](/help/forms/using/admin-help/view-statistics-related-manager.md#view-statistics-related-to-work-manager).)
* Met het tabblad Planning voor taakverwijdering kunt u verouderde records uit de database van Taakbeheer verwijderen. (Zie [Records uit de taakbeheerdatabase wissen](/help/forms/using/admin-help/purge-records-job-manager-database.md#purge-records-from-the-job-manager-database).)

De webpagina Health Monitor wordt gevuld met statistieken die via een Gemfire-API zijn verzameld. Deze API ontdekt automatisch alle knopen in een cluster. Het lost ook veiligheidskwesties op die voorkomen wanneer het verzamelen van statistieken van achter volmachtsservers of ladingsbalancers. Java-opties zijn beschikbaar om de Health Monitor te verfijnen, waardoor de invloed op de prestaties van de omgeving van uw AEM formulieren afneemt. (Zie [Prestaties van de fijnafgestelde Health Monitor](/help/forms/using/admin-help/fine-tuning-health-monitor-performance.md#fine-tuning-health-monitor-performance).)

**Toegangsmonitor**

1. Klik in de beheerconsole op Health Monitor in de rechterbovenhoek van de pagina.
