---
title: Eindpunten van Taakbeheer configureren
seo-title: Configuring Task Manager endpoints
description: Leer hoe te om de eindpunten van de Manager van de Taak te vormen.
seo-description: Learn how to configure Task Manager endpoints.
uuid: 07604b10-0bd7-4bce-9624-7ebac4754f56
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/managing_endpoints
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 9c55feb9-23d8-4798-a3c5-70ec736df3ad
exl-id: 546a699e-975f-42a1-8ab5-0de4bd7f4a8f
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 0%

---

# Eindpunten van Taakbeheer configureren {#configuring-task-manager-endpoints}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

De eindpunten van de Manager van de taak laten de gebruikers van de Werkruimte toe om de dienst aan te halen.

**Eindinstellingen taakbeheer**

Gebruik de volgende montages om een eindpunt van de Manager van de Taak te vormen.

**Naam:** (Verplicht) Identificeert het eindpunt. De naam wordt weergegeven in de kaartweergave in Workspace. Neem geen &lt;-teken op omdat de naam die in Workspace wordt weergegeven hierdoor wordt afgekapt. Als u een URL als naam van het eindpunt ingaat, zorg ervoor dat het met de syntaxisregels in overeenstemming is die in RFC1738 worden gespecificeerd.

**Omschrijving:** Een beschrijving van het eindpunt. Neem geen &lt;-teken op omdat de beschrijving die in Workspace wordt weergegeven hierdoor wordt afgekapt.

**Taakinstructies:** Instructies voor de gebruiker die deze workflow start.

**Proceeigenaar:** De naam van de persoon die verantwoordelijk is voor het proces.

**Gebruiker kan taak doorsturen:** Hiermee kan de gebruiker de eerste taak doorsturen.

**Venster Bijlage tonen:** Hiermee kan de gebruiker het venster met bijlagen weergeven.

**Toevoegen van bijlage toestaan:** Hiermee kan de gebruiker bijlagen en notities toevoegen.

**Aanvankelijk vergrendelde taak:** Vergrendelt de eerste taak.

**Voeg ACLs voor Gedeelde Gelijken toe:** De aanvankelijke taak wordt gecreeerd met ACLs voor gedeelde rijgebruikers.

**Indeling:** (Verplicht) De categorie waarin de gebruiker het formulier in Workspace ziet. Selecteer een categorie in de lijst of selecteer Nieuwe categorie om een categorie toe te voegen.

**Bedrijfsnaam:** (Verplicht) Een lijst van verrichtingen die aan het eindpunt kunnen worden toegewezen.
