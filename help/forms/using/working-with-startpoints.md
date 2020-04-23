---
title: Werken met beginpunten
seo-title: Werken met beginpunten
description: Stappen om met een proces van Vormen AEM van uw Mobiel apparaat te werken dat in Workbench wordt bepaald.
seo-description: Stappen om met een proces van Vormen AEM van uw Mobiel apparaat te werken dat in Workbench wordt bepaald.
uuid: 9c51ce52-e7ba-43d3-a85c-67067f680ccb
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-app
discoiquuid: 265eee8a-364e-4edf-b2a0-f42617169944
translation-type: tm+mt
source-git-commit: f13d358a6508da5813186ed61f959f7a84e6c19f

---


# Werken met beginpunten {#working-with-startpoints}

Een startpunt roept een proces aan dat in Workbench wordt gecreeerd. Het is gekoppeld aan een formulier dat het proces activeert wanneer het formulier wordt verzonden. Zie de analyse van de Verwijzing van de Plaats van de Verwijzing van [de Financiën Geometrixx](/help/forms/using/finance-reference-site-walkthrough.md) om processen te begrijpen.

>[!NOTE]
>
>De termen startpunten, beginproces en vorm worden door elkaar gebruikt wanneer wordt verwezen naar dit concept.

Als u een proces wilt starten vanuit de app AEM Forms, hebt u een beginpunt van het type **Workspace** nodig. U moet ook de optie **[!UICONTROL Zichtbaar in mobiele werkruimte]** selecteren voor het startpunt.

![mws_startpoint_select_option](assets/mws_startpoint_select_option.png)

**Een proces starten dat is gedefinieerd in Workbench**

1. Ga naar het scherm [](/help/forms/using/home-screen.md)Home om de beginpunten weer te geven die beschikbaar zijn in de app AEM Forms.
1. Standaard wordt in het scherm **[!UICONTROL Home]** de lijst **[!UICONTROL Alle formulieren]** weergegeven.

   Het startpunt is gekoppeld aan een formulier. Tik op het aan het formulier gekoppelde startpunt in de lijst om het te openen.

   Het formulier dat aan het startpunt is gekoppeld, wordt geopend.

1. Voer de details in het **[!UICONTROL startpuntformulier]** in.

   U kunt annotaties toevoegen aan deze taak met de [knop Bijlage](/help/forms/using/add-attachments.md) .

1. Tik op de knop **Verzenden** nadat u het formulier hebt ingevuld.

Als de app offline is, worden het formulier en de bijbehorende gegevens opgeslagen in de map Outbox.

Als de app online is, wordt de taak gesynchroniseerd met de AEM Forms-server en toegewezen aan de gebruiker die in het proces is opgegeven.

Zie Een taak [openen](/help/forms/using/open-task.md)voor informatie over het werken met de taak in de takenlijst.
