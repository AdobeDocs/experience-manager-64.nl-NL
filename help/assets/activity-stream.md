---
title: Activiteitsstroom in tijdlijn
description: 'In dit artikel wordt beschreven hoe u activiteitenlogboeken voor elementen op de tijdlijn kunt weergeven. '
contentOwner: AG
translation-type: tm+mt
source-git-commit: 0d70a672a2944e2c03b54beb3b5f734136792ab1
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 26%

---


# Activiteitsstroom in tijdlijn {#activity-stream-in-timeline}

Deze functie geeft activiteitenlogboeken voor elementen op de tijdlijn weer. Als u een van de volgende bewerkingen met betrekking tot elementen uitvoert in Adobe Experience Manager (AEM) Assets, werkt de functie Activiteitsstroom de tijdlijn bij om de activiteit weer te geven.

De volgende bewerkingen worden in de activiteitsstroom aangemeld:

* Maken
* Verwijderen
* Downloaden (inclusief uitvoeringen)
* Publicatie
* Publiceren ongedaan maken
* Goedkeuren
* Afwijzen
* Verplaatsen

De activiteitenlogboeken die in de tijdlijn moeten worden weergegeven, worden opgehaald vanaf de locatie `/var/audit/com.day.cq.dam/content/dam` in CRX, waar logboekbestanden worden opgeslagen. 

Bovendien wordt de tijdlijnactiviteit vastgelegd wanneer nieuwe assets worden geüpload of wanneer bestaande assets worden gewijzigd en gecontroleerd in AEM via de [Adobe Asset Link](https://helpx.adobe.com/nl/enterprise/using/manage-assets-using-adobe-asset-link.html) of de [AEM-desktopapp](https://docs.adobe.com/content/help/en/experience-manager-desktop-app/using/introduction.html).

>[!NOTE]
>
>Tijdelijke workflows worden niet weergegeven in de tijdlijn, omdat er voor deze workflows geen historiegegevens worden opgeslagen.

Als u de activiteitsstroom wilt weergeven, voert u een of meer bewerkingen uit op het element, selecteert u het element en kiest u een optie in de lijst GlobalNav. **[!UICONTROL Timeline]**

![timeline-3](assets/timeline-3.png)

De tijdlijn geeft de activiteitsstroom weer voor de bewerkingen die u uitvoert op de elementen.

![activity_stream](assets/activity_stream.png)

>[!NOTE]
>
>The default log storage location for **Publish** and **Unpublish** tasks is `/var/audit/com.day.cq.replication/content`. For **Move** tasks, the default location is `/var/audit/com.day.cq.wcm.core.page`.
