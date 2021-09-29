---
title: Activiteitsstroom in tijdlijn
description: 'In dit artikel wordt beschreven hoe u activiteitenlogboeken voor elementen op de tijdlijn kunt weergeven. '
contentOwner: AG
feature: Asset Management
role: User,Admin
exl-id: 52fa2d59-177f-49ca-a480-7213ce0ca7d7
source-git-commit: 1679bbab6390808a1988cb6fe9b7692c3db31ae4
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 11%

---

# Activiteitsstroom in tijdlijn {#activity-stream-in-timeline}

Deze functie geeft activiteitenlogboeken voor elementen op de tijdlijn weer. Als u een van de volgende bewerkingen met betrekking tot elementen uitvoert in [!DNL Adobe Experience Manager Assets], werkt de functie Activiteitenstroom de tijdlijn bij om de activiteit weer te geven.

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

Bovendien wordt de tijdlijnactiviteit geregistreerd wanneer de nieuwe activa worden geupload of de bestaande activa worden gewijzigd en in Experience Manager via [Adobe activaVerbinding](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/manage-assets-using-adobe-asset-link.ug.html) of [[!DNL Experience Manager] Desktop app](https://experienceleague.adobe.com/docs/experience-manager-desktop-app/using/introduction.html) worden gecontroleerd.

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
