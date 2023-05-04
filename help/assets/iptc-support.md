---
title: Ondersteuning voor IPTC-metagegevens
description: Leer hoe Adobe Experience Manager Assets de IPTC-metagegevens, creatieve beoordelingen en trefwoorden ondersteunt die via Adobe Bridge en andere Creative Apps aan middelen zijn toegevoegd.
contentOwner: AG
feature: Metadata
role: User,Admin,Leader
exl-id: 3e22e8e4-3675-4d6d-94f4-fc1a4d4801e8
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 6%

---

# Ondersteuning voor IPTC-metagegevens {#support-for-iptc-metadata}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Leer hoe Adobe Experience Manager Assets de IPTC-metagegevens, creatieve beoordelingen en trefwoorden ondersteunt die via Adobe Bridge en andere Creative Apps aan middelen zijn toegevoegd.

Adobe Experience Manager Assets biedt ondersteuning voor de IPTC-metagegevensstandaard die veel wordt gebruikt om elementen te beschrijven. Zo, [!DNL Experience Manager Assets] de acceptatie van de afbeeldingen van de foto&#39;s door verschillende partijen wordt verbeterd, zoals fotografen, creatieve bureaus, bibliotheken, musea, enzovoort.

In het standaardmetagegevensschema voor elementen zijn nu de IPTC Core- en IPTC-metagegevensschema&#39;s voor extensies opgenomen om uitgebreide metagegevenseigenschappen te definiëren waarmee gebruikers nauwkeurige en betrouwbare gegevens kunnen toevoegen over personen, locaties en producten die in een afbeelding worden weergegeven. Het steunt ook data, namen, en herkenningstekens betreffende de verwezenlijking van het beeld, en een flexibele manier om rechteninformatie uit te drukken.

De pagina Eigenschappen voor elementen bevat nu aparte tabbladen waarmee de metagegevens voor IPTC Core- en IPTC-extensies in bewerkbare velden worden weergegeven.

1. Selecteer een afbeelding in de gebruikersinterface Elementen.
1. Klik of tik op **[!UICONTROL Properties]** op de werkbalk.
1. Klik of tik op de pagina Eigenschappen op de knop **[!UICONTROL IPTC]** om IPTC-metagegevens voor het element weer te geven.
1. Bewerk indien nodig de IPTC-metagegevenseigenschappen.

   ![iptc_tab](assets/iptc_tab.png)

1. Klik of tik op het tabblad **[!UICONTROL IPTC Extension]** om de metadata voor IPTC-uitbreidingen voor de asset weer te geven.
1. Bewerk indien nodig de metagegevenseigenschappen van de ITPC-extensie.
1. Tik of klik op **[!UICONTROL Save & Close]** om de wijzigingen op te slaan.

## Ondersteuning voor creatieve waarderingen {#creative-rating-support}

Naast het weergeven van individuele gebruikersbeoordelingen en het verzamelen van classificaties, wordt op de pagina Eigenschappen nu de classificaties weergegeven die via Adobe Bridge en andere Creative Apps zijn toegewezen aan elementen

Deze classificaties zijn beschikbaar onder de sectie **[!UICONTROL Creative Rating]** op het tabblad **[!UICONTROL Advanced]**.

Deze classificatie is een alleen-lezen eigenschap en ligt tussen 1 en 5. In het deelvenster Zoeken kunt u zoeken naar elementen op basis van hun creatieve waardering.

Deze eigenschap is momenteel echter niet geïndexeerd om conflicten met aangepaste wijzigingen door gebruikers te voorkomen.

## Trefwoordondersteuning {#keyword-support}

De **[!UICONTROL IPTC]** op de pagina Eigenschappen worden ook de trefwoorden weergegeven die via Adobe Bridge en andere Creative Apps aan elementen zijn toegevoegd. U kunt deze trefwoorden ook bewerken en meer trefwoorden toevoegen via het menu **[!UICONTROL IPTC]** tab.

![trefwoorden](assets/keywords.png)
