---
title: Werken met beginpunten
seo-title: Working with Startpoints
description: Stappen om met een AEM Forms-proces te werken vanaf uw mobiele apparaat dat is gedefinieerd in Workbench.
seo-description: Steps to work with a AEM Forms process from your Mobile device defined in Workbench.
uuid: 9c51ce52-e7ba-43d3-a85c-67067f680ccb
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-app
discoiquuid: 265eee8a-364e-4edf-b2a0-f42617169944
exl-id: ef9352c7-c164-4cbf-8f18-5b97aa5f56be
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 0%

---

# Werken met beginpunten {#working-with-startpoints}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Een startpunt roept een proces aan dat in Workbench wordt gecreeerd. Het is gekoppeld aan een formulier dat het proces activeert wanneer het formulier wordt verzonden. Zie [Analyse van de Referentie-site van Geometrixx Finance](/help/forms/using/finance-reference-site-walkthrough.md) om processen te begrijpen.

>[!NOTE]
>
>De termen startpunten, beginproces en vorm worden door elkaar gebruikt wanneer wordt verwezen naar dit concept.

Als u een proces wilt starten vanuit de AEM Forms-app, hebt u een beginpunt van het type nodig **Werkruimte** in uw proces. Ook moet u de optie **[!UICONTROL Visible in Mobile Workspace]** voor het startpunt.

![mws_startpoint_select_option](assets/mws_startpoint_select_option.png)

**Een proces starten dat is gedefinieerd in Workbench**

1. Ga naar [Startscherm](/help/forms/using/home-screen.md).
1. Op de **[!UICONTROL Home]** het scherm, door gebrek **[!UICONTROL All Forms]** wordt weergegeven.

   Het startpunt is gekoppeld aan een formulier. Tik op het aan het formulier gekoppelde startpunt in de lijst om het te openen.

   Het formulier dat aan het startpunt is gekoppeld, wordt geopend.

1. Voer de gegevens in het dialoogvenster **[!UICONTROL Startpoint]** formulier.

   U kunt annotaties toevoegen aan deze taak met de opdracht [bijlage](/help/forms/using/add-attachments.md) knop.

1. Tik op de knop **Verzenden** knop.

Als de app offline is, worden het formulier en de bijbehorende gegevens opgeslagen in de map Outbox.

Als de app online is, wordt de taak gesynchroniseerd met de AEM Forms-server en toegewezen aan de gebruiker die in het proces is opgegeven.

Als u met de taak in uw takenlijst wilt werken, raadpleegt u [Een taak openen](/help/forms/using/open-task.md).
