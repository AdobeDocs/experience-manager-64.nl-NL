---
title: Terugvallettertypen configureren
seo-title: Configuring fallback fonts
description: Leer hoe u fallback-lettertypen configureert.
seo-description: Learn how to configure fallback fonts.
uuid: 2745541c-8c6d-4bb4-aa14-ec19afd6bc35
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/working_with_pdf_generator
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: d997a268-a40a-462d-badd-94f0731f7ba4
feature: PDF Generator
exl-id: 6942b6fc-8d04-429f-8433-1ab74c68fcc1
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 0%

---

# Terugvallettertypen configureren {#configuring-fallback-fonts}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

U kunt het bestand FontManagerResources.properties handmatig zodanig configureren dat de standaardfonts AEM formulieren worden toegewezen aan fallback (of vervangen) als de standaardfonts niet beschikbaar zijn op de server. Dit eigenschapbestand bevindt zich in het bestand adobe-fontmanager.jar.

>[!NOTE]
>
>De fontconfiguratie van de reserve is ook op de assembleerdienst van toepassing.

1. Navigeren naar de adobe-livecycle-*[appserver]*.ear-bestand in de *[basis van em-formulieren]*/configurationManager/export directory, maak een reservekopie en pak het origineel uit.
1. Zoek het bestand adobe-fontmanager.jar en pak het uit.
1. Zoek het bestand FontManagerResources.properties en open het in een teksteditor.
1. Wijzig desgewenst de locaties en namen van de lettertypen Algemeen en Fallback en sla het bestand op.

   De fontitems in het bestand FontManagerResources.properties zijn relatief ten opzichte van de *[basis van em-formulieren]*/fonts directory. Als u lettertypen opgeeft die niet standaard AEM formulierlettertypen zijn, moet u deze lettertypen installeren in deze mapstructuur (binnen een bestaande map of in een nieuw gemaakte map).

   >[!NOTE]
   >
   >Als het opgegeven lettertype of standaardlettertype geen specifiek Unicode-teken bevat of als dit niet beschikbaar is, wordt het teken volgens de volgende prioriteit van een fallback-lettertype genomen:

   * Landspecifiek font
   * HOOFDLETTERlettertype indien landinstelling niet is ingesteld
   * Algemeen lettertype, doorzocht op volgorde ingesteld in de fallback-tabel

1. Verpak het bestand adobe-fontmanager.jar opnieuw.
1. De adobe-livecycle opnieuw verpakken *[appserver]*.ear dossier en dan herstelt het of manueel of door de Manager van de Configuratie in werking te stellen.

>[!NOTE]
>
>Gebruik Configuration Manager niet om de adobe-livecycle-[appserver].ear-bestand omdat hiermee uw wijzigingen worden overschreven door de standaardwaarden van de AEM formulieren.
