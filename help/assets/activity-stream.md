---
title: Activiteitsstroom in tijdlijn
description: 'In dit artikel wordt beschreven hoe u activiteitenlogboeken voor elementen op de tijdlijn kunt weergeven. '
contentOwner: AG
feature: Beheer van bedrijfsmiddelen
role: Business Practice,Administrator
translation-type: tm+mt
source-git-commit: 29e3cd92d6c7a4917d7ee2aa8d9963aa16581633
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 23%

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

Bovendien wordt de tijdlijnactiviteit vastgelegd wanneer nieuwe assets worden geüpload of wanneer bestaande assets worden gewijzigd en gecontroleerd in AEM via de [Adobe Asset Link](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/manage-assets-using-adobe-asset-link.ug.html) of de [AEM-desktopapp](https://experienceleague.adobe.com/docs/experience-manager-desktop-app/using/introduction.html).

>[!NOTE]
>
>Tijdelijke workflows worden niet weergegeven in de tijdlijn, omdat er voor deze workflows geen historiegegevens worden opgeslagen.

Als u de activiteitsstroom wilt weergeven, voert u een of meer bewerkingen uit op het element, selecteert u het element en kiest u **[!UICONTROL Timeline]** in de lijst GlobalNav.

![timeline-3](assets/timeline-3.png)

De tijdlijn geeft de activiteitsstroom weer voor de bewerkingen die u uitvoert op de elementen.

![activity_stream](assets/activity_stream.png)

>[!NOTE]
>
>De standaardopslaglocatie voor logbestanden voor **Publiceren** en **Unpublish**-taken is `/var/audit/com.day.cq.replication/content`. Voor **Move** taken, is de standaardplaats `/var/audit/com.day.cq.wcm.core.page`.
