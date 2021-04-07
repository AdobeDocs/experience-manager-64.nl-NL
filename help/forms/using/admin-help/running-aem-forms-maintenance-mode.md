---
title: AEM formulieren uitvoeren in de onderhoudsmodus
seo-title: AEM formulieren uitvoeren in de onderhoudsmodus
description: De wijze van het onderhoud is nuttig wanneer het uitvoeren van taken zoals het patchen van een DSC, het bevorderen AEM vormen, of het toepassen van een de dienstpak. Meer informatie over het uitvoeren van AEM formulieren in de onderhoudsmodus.
seo-description: De wijze van het onderhoud is nuttig wanneer het uitvoeren van taken zoals het patchen van een DSC, het bevorderen AEM vormen, of het toepassen van een de dienstpak. Meer informatie over het uitvoeren van AEM formulieren in de onderhoudsmodus.
uuid: 9aa3be20-f17e-4384-b4ce-daaee2898c96
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/maintaining_aem_forms
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 94047c12-ba3d-457a-954f-e035c7cc3ecd
exl-id: 2f56bbc7-5e23-4c84-ac0a-03f0b01150b3
translation-type: tm+mt
source-git-commit: bd94d3949f0117aa3e1c9f0e84f7293a5d6b03b4
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 0%

---

# AEM formulieren uitvoeren in onderhoudsmodus {#running-aem-forms-in-maintenance-mode}

De wijze van het onderhoud is nuttig wanneer het uitvoeren van taken zoals het patchen van een DSC, het bevorderen AEM vormen, of het toepassen van een de dienstpak.

U moet voorkomen dat processen worden aangeroepen terwijl de server zich in de onderhoudsmodus bevindt. Dit is wat gebeurt als een proces wordt aangehaald terwijl de server op onderhoudswijze is:

* Als het proces van lange duur is, wordt het toegevoegd aan het baangegevensbestand, maar is niet begonnen. Wanneer u de onderhoudsmodus afsluit, verwerkt AEM formulieren de taken met een lange levensduur in de wachtrij, zelfs als de server opnieuw is gestart in de onderhoudsmodus.
* Als het proces van korte duur is, wordt het meteen verwerkt.

**AEM formulieren in de onderhoudsmodus plaatsen**

1. Voer in een webbrowser de volgende gegevens in:

   `https://`*[]*`:`*[]* `/dsc/servlet/DSCStartupServlet?maintenanceMode=pause&user=`*[hostNamePortadministrator-]*`&password=`*[gebruikersnaamWachtwoord]*

   Een bericht &quot;nu gepauzeerd&quot;wordt getoond in het browser venster.

   >[!NOTE]
   >
   >Als u de server sluit terwijl het onderhoudswijze is, zal het nog op onderhoudswijze zijn wanneer het opnieuw wordt begonnen. U moet de onderhoudsmodus uitschakelen wanneer u klaar bent met uw onderhoudstaken.

**Controleren of AEM formulieren worden uitgevoerd in de onderhoudsmodus**

1. Voer in een webbrowser de volgende gegevens in:

   `https://`*[hostname]:[]*`/dsc/servlet/DSCStartupServlet?maintenanceMode=isPaused&user=`*[portadministrator]* `&password=`*[gebruikersnaam ]*

   De status wordt weergegeven in het browservenster. De status &quot;true&quot; geeft aan dat de server wordt uitgevoerd in de onderhoudsmodus en &quot;false&quot; geeft aan dat de server niet in de onderhoudsmodus staat.

**Onderhoudsmodus uitschakelen**

1. Voer in een webbrowser de volgende gegevens in:

   `https://`*[hostname]:[]*`/dsc/servlet/DSCStartupServlet?maintenanceMode=resume&user=`*[portadministrator]* `&password=`*[gebruikersnaam ]*

   Er wordt een bericht &quot;now running&quot; weergegeven in het browservenster.
