---
title: Procesgegevens wissen
seo-title: Purging process data
description: Procesgegevens die worden gegenereerd wanneer een langdurig proces wordt aangeroepen, kunnen te groot worden, wat resulteert in lagere AEM formulierprestaties en het gebruik van overbodige schijfruimte. Zie hoe u procesgegevens kunt wissen.
seo-description: Process data that is generated when a long-lived process is invoked can become too large, resulting in lower AEM forms performance and the use of unnecessary disk space. See how you can purge process data.
uuid: 2f04452c-71c6-452c-88c2-7560d35e7dec
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/maintaining_the_aem_forms_database
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 3157bb92-4b07-40f2-be4c-8f5807f9a380
exl-id: ecedde63-abbb-4e69-901e-1e4b7a59f539
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 0%

---

# Procesgegevens wissen {#purging-process-data}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Procesgegevens die worden gegenereerd wanneer een langdurig proces wordt aangeroepen, kunnen te groot worden, wat resulteert in lagere AEM formulierprestaties en het gebruik van overbodige schijfruimte. Het is een goede gewoonte om procesgegevens te wissen wanneer records niet meer nodig zijn. AEM formulieren bieden verschillende manieren om procesgegevens te wissen:

* U kunt beheerconsole gebruiken om een eenmalige verwijdering uit te voeren van verouderde records die verwant zijn aan langlevende processen, of om regelmatige automatische purges te plannen. (Zie [Records uit de taakbeheerdatabase wissen](/help/forms/using/admin-help/purge-records-job-manager-database.md#purge-records-from-the-job-manager-database).)
* Met de Java API voor AEM formulieren en de API voor webservices kunt u procesgegevens met betrekking tot langlevende processen programmatisch wissen. (Zie &quot;Gegevens van procesoptimalisatie leegmaken&quot; in [Programmeren met AEM formulieren](https://www.adobe.com/go/learn_aemforms_programming_63).)
* Gebruik het gereedschap voor het verwijderen van processen om processen op basis van de procesnaam en andere parameters te wissen. Zie voor meer informatie het Lees mij-bestand over het gereedschap Repareren in *[aem_forms, basis]*\sdk\misc\Foundation\ProcessPurgeTool\ReadMe.txt.
