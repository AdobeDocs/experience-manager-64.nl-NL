---
title: Logbestanden
seo-title: Log files
description: Gebeurtenissen zoals runtime- of opstartfouten worden opgenomen in de logbestanden van de toepassingsserver, die kunnen worden geopend met een teksteditor.
seo-description: Events such as run-time or startup errors are recorded to the application server log files, which can be  opened using any text editor.
uuid: 6ed9fdcd-ff02-4b35-893f-09261a6a557a
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/maintaining_aem_forms
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: cf140483-470f-4bff-8870-304207508aab
exl-id: acce13aa-864c-4999-be5c-6d49b99d5459
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 0%

---

# Logbestanden {#log-files}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Gebeurtenissen zoals runtime- of opstartfouten worden opgenomen in de logbestanden van de toepassingsserver. Als u problemen hebt met de implementatie op de toepassingsserver, kunt u de logbestanden gebruiken om het probleem op te sporen. U kunt de logboekdossiers openen gebruikend om het even welke tekstredacteur.

(JBoss) De volgende logbestanden bevinden zich in de map `*[appserver root]*/server/*[server]*/log` map:

* boot.log
* server.log.*[jjjj-mm-dd]*
* server.log

(WebLogic) Domeinlogbestanden bevinden zich in de *[appserverdomein]* en de dossiers van het serverlogboek worden gevestigd in *[appserverdomein]/servers/[toepassingsnaam]/logs *directory:

* access.log
* *[toepassingsnaam]*.log
* *[toepassingsnaam]*.out.*[incrementeel nummer]*

(WebSphere) De volgende logbestanden bevinden zich in de map *[appserver-hoofdmap]*/profiles/default/logs/*[toepassingsnaam]* map:

* SystemErr.log
* SystemOut.log
* StartServer.log
