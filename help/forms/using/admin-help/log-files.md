---
title: Logbestanden
seo-title: Logbestanden
description: Gebeurtenissen zoals runtime- of opstartfouten worden opgenomen in de logbestanden van de toepassingsserver, die kunnen worden geopend met een teksteditor.
seo-description: Gebeurtenissen zoals runtime- of opstartfouten worden opgenomen in de logbestanden van de toepassingsserver, die kunnen worden geopend met een teksteditor.
uuid: 6ed9fdcd-ff02-4b35-893f-09261a6a557a
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/maintaining_aem_forms
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: cf140483-470f-4bff-8870-304207508aab
translation-type: tm+mt
source-git-commit: d04e08e105bba2e6c92d93bcb58839f1b5307bd8
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 0%

---


# Logbestanden {#log-files}

Gebeurtenissen zoals runtime- of opstartfouten worden opgenomen in de logbestanden van de toepassingsserver. Als u problemen hebt met de implementatie op de toepassingsserver, kunt u de logbestanden gebruiken om het probleem op te sporen. U kunt de logboekdossiers openen gebruikend om het even welke tekstredacteur.

(JBoss) De volgende logbestanden bevinden zich in de `*[appserver root]*/server/*[server]*/log` map:

* boot.log
* server.log.*[jjjj-mm-dd]*
* server.log

(WebLogic) Domeinlogbestanden bevinden zich in de map *[appserverdomain]* en serverlogbestanden bevinden zich in de map *[appserverdomain]/servers/[toepassingsservernaam]/logs *:

* access.log
* *[appserver name]*.log
* *[appserver name]*.out.*[incrementeel nummer]*

(WebSphere) De volgende logbestanden bevinden zich in de map *[appserver root]*/profiles/default/logs/*[appserver name]* :

* SystemErr.log
* SystemOut.log
* StartServer.log

