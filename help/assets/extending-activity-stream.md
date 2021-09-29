---
title: Elementen integreren met activiteitsstroom
description: Beschrijft de opnamemogelijkheden van [!DNL Experience Manager] and how to configure [!DNL Experience Manager] om specifieke gebeurtenissen te registreren.
contentOwner: AG
feature: Asset Management
role: Developer
exl-id: c25a4da7-1c58-41cf-9ff6-c094b50208e6
source-git-commit: cc9b6d147a93688e5f96620d50f8fc8b002e2d0d
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 1%

---

# Elementen integreren met activiteitsstroom {#integrating-assets-with-activity-stream}

Gebruikers van Adobe Experience Manager Assets voeren veel handelingen uit, zoals het maken, uploaden en verwijderen van middelen. Deze acties kunnen worden opgenomen zodat u een geschiedenis kunt verstrekken van wat door een gebruiker is gedaan. In deze sectie worden de opnamemogelijkheden van [!DNL Experience Manager] beschreven en hoe u [!DNL Experience Manager] configureert om specifieke gebeurtenissen op te nemen.

## Prestatieoverwegingen en standaardgedrag {#performance-considerations-and-default-behavior}

Deze integratie kan CPU- en schijfruimte in beslag nemen, bijvoorbeeld bij het importeren van grote hoeveelheden. Om deze redenen is de integratie van [!DNL Experience Manager] Middelen met de Activiteitenstroom standaard uitgeschakeld.

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

## Opname van gebeurtenissen [!DNL Assets] configureren {#configuring-aem-assets-events-recording}

De [Webconsole](/help/sites-deploying/configuring-osgi.md) biedt toegang tot de afstemming van de [!DNL Assets]-gebeurtenisrecorder. Ga als volgt te werk om de [!DNL Assets]-gebeurtenisrecorder te configureren:

1. Navigeer naar **[!UICONTROL Web console]**

1. Klik op **[!UICONTROL Configuration]**.

1. Dubbelklik op **[!UICONTROL Day CQ DAM Event Recorder]**.

1. Vinkje **[!UICONTROL Enables this service]**.

1. Controleer welke **[!UICONTROL Event Types]** u in de stroom van de gebruikersactiviteit wilt worden geregistreerd.

1. Klik op **[!UICONTROL Save]**.

## Opgenomen gebeurtenissen lezen {#reading-recorded-events}

De opgenomen gebeurtenissen worden opgeslagen als activiteiten. U kunt hen programmatically lezen door [ActivityManager API](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/granite/activitystreams/ActivityManager.html) te gebruiken.
