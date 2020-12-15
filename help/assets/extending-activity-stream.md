---
title: Elementen integreren met activiteitsstroom
description: Beschrijft de opnamemogelijkheden van AEM en hoe te om AEM te vormen om specifieke gebeurtenissen te registreren.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 0d70a672a2944e2c03b54beb3b5f734136792ab1
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 1%

---


# Elementen integreren met activiteitsstroom {#integrating-assets-with-activity-stream}

Adobe Experience Manager (AEM)-middelengebruikers voeren veel handelingen uit, zoals het maken, uploaden en verwijderen van middelen. Deze acties kunnen worden opgenomen zodat u een geschiedenis kunt verstrekken van wat door een gebruiker is gedaan. In deze sectie worden de opnamemogelijkheden van AEM beschreven en wordt beschreven hoe u AEM kunt configureren om specifieke gebeurtenissen op te nemen.

## Prestatieoverwegingen en standaardgedrag {#performance-considerations-and-default-behavior}

Deze integratie kan CPU- en schijfruimte in beslag nemen, bijvoorbeeld bij het importeren van grote hoeveelheden. Om deze redenen is de AEM Assets-integratie met de activiteitsstroom standaard uitgeschakeld.

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

## AEM Assets Events-opname {#configuring-aem-assets-events-recording} configureren

De [webconsole](/help/sites-deploying/configuring-osgi.md) biedt toegang tot de afstemming van de AEM Assets-gebeurtenisrecorder. Ga als volgt te werk om de AEM Assets Event Recorder te configureren:

1. Navigeer naar **[!UICONTROL Web console]**

1. Klik op **[!UICONTROL Configuration]**.

1. Dubbelklik op **[!UICONTROL Day CQ DAM Event Recorder]**.

1. Vinkje **[!UICONTROL Enables this service]**.

1. Controleer welke **[!UICONTROL Event Types]** u in de stroom van de gebruikersactiviteit wilt worden geregistreerd.

1. Klik op **[!UICONTROL Save]**.

## Opgenomen gebeurtenissen {#reading-recorded-events} lezen

De opgenomen gebeurtenissen worden opgeslagen als activiteiten. U kunt hen programmatically lezen door [ActivityManager API](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/granite/activitystreams/ActivityManager.html) te gebruiken.
