---
title: Elementen integreren met activiteitsstroom
description: Beschrijft de opnamemogelijkheden van [!DNL Experience Manager] en hoe te vormen [!DNL Experience Manager] om specifieke gebeurtenissen op te nemen.
contentOwner: AG
feature: Asset Management
role: Developer
exl-id: c25a4da7-1c58-41cf-9ff6-c094b50208e6
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 0%

---

# Elementen integreren met activiteitsstroom {#integrating-assets-with-activity-stream}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Gebruikers van Adobe Experience Manager Assets voeren veel handelingen uit, zoals het maken, uploaden en verwijderen van middelen. Deze acties kunnen worden opgenomen zodat u een geschiedenis kunt verstrekken van wat door een gebruiker is gedaan. In deze sectie worden de opnamemogelijkheden van [!DNL Experience Manager] en hoe te vormen [!DNL Experience Manager] om specifieke gebeurtenissen op te nemen.

## Prestatieoverwegingen en standaardgedrag {#performance-considerations-and-default-behavior}

Deze integratie kan CPU- en schijfruimte in beslag nemen, bijvoorbeeld bij het importeren van grote hoeveelheden. Om deze redenen [!DNL Experience Manager] Integratie van elementen met de activiteitsstroom wordt standaard uitgeschakeld.

## Ondersteunde actiegebeurtenissen {#supported-action-events}

De volgende gebeurtenissen kunnen worden geconfigureerd om te worden opgenomen:

* Licentie geaccepteerd (AANVAARD)
* Gemaakte activa (ASSET_CREATED)
* Verplaatst element (ASSET_MOVED)
* Element verwijderd (ASSET_REMOVED)
* Vergunning geweigerd (AFGEWEZEN)
* Gedownload element (GEDOWNLOAD)
* Geversioneerd element (VERSIONED)
* Herstelbare versie van element
* Metagegevens van element bijgewerkt (METADATA_UPDATED)
* Element gepubliceerd naar extern systeem (PUBLISHED_EXTERNAL)
* Oorspronkelijk bijgewerkt element (ORIGINAL_UPDATED)
* Vertoning van element bijgewerkt (RENDITION_UPDATED)
* Vertoning van element verwijderd (RENDITION_REMOVED)
* Submiddel bijgewerkt (SUBASSET_UPDATED)
* Subelement verwijderd (SUBASSET_REMOVED)

## Configureren [!DNL Assets] Gebeurtenissen opnemen {#configuring-aem-assets-events-recording}

De [Webconsole](/help/sites-deploying/configuring-osgi.md) verleent toegang tot [!DNL Assets] Afstelling van gebeurtenisrecorder. Om het [!DNL Assets] Gebeurtenisrecorder, ga als volgt te werk:

1. Ga naar de **[!UICONTROL Web console]**

1. Klik op **[!UICONTROL Configuration]**.

1. Dubbelklikken **[!UICONTROL Day CQ DAM Event Recorder]**.

1. Controleren **[!UICONTROL Enables this service]**.

1. Controleren welke **[!UICONTROL Event Types]** u wilt worden opgenomen in de gebruikersactiviteitsstroom.

1. Klik op **[!UICONTROL Save]**.

## Opgenomen gebeurtenissen lezen {#reading-recorded-events}

De opgenomen gebeurtenissen worden opgeslagen als activiteiten. U kunt hen programmatically lezen door te gebruiken [ActivityManager-API](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/granite/activitystreams/ActivityManager.html).
