---
title: Overwegingen bij het uitvoeren van AdministrationConsole
seo-title: Considerations when running AdministrationConsole
description: Dit document bevat een aantal punten waarmee u rekening kunt houden wanneer u de beheerconsole uitvoert.
seo-description: This document lists a few points to consider when running Administration Console.
uuid: e260f187-4728-44f3-a5c1-7388ff3965c4
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/maintaining_the_application_server
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 525c4afc-e109-4546-b78c-1efee63edc43
exl-id: 991418fd-5ff8-491e-834e-2324e029e499
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 0%

---

# Overwegingen bij het uitvoeren van beheerconsole {#considerations-when-running-administrationconsole}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Dit zijn sommige dingen om te overwegen wanneer het runnen van de Console van het Beleid:

* Als u tot beleidsconsole toegang hebt gebruikend URL `https://*[hostname]*:*[port]*/adminui`, mag de opgegeven hostnaam geen onderstrepingstekens bevatten. Anders, werken de verbindingen aan sommige gebieden van de beleidsconsole niet behoorlijk.
* Als u beleidsconsole in de Ontdekkingsreiziger van Vensters op Japans OS in werking stelt, kunt u deze problemen omringen:

   * Als u op een koppeling klikt, keert u terug naar de aanmeldingspagina in plaats van naar de verwachte koppeling.
   * Als u op een koppeling klikt, wordt een machtigingsfout weergegeven.

   De beste praktijken worden in werking gesteld beleidsconsole van andere browser, zoals Mozilla Firefox, om ervoor te zorgen dat geen verbindingen zullen ontbreken.

* Gebruik geen backslash-tekens () wanneer u zoekopdrachten uitvoert in de beheerconsole.
