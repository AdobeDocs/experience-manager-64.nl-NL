---
title: Lettertypen toevoegen voor grafisch renderen
seo-title: Adding Fonts for Graphic-Rendering
description: AEM kunt u afbeeldingen genereren waarin tekst dynamisch wordt overgenomen van uw inhoud
seo-description: AEM allows you to generate graphics incorporating text dynamically taken from your content
uuid: 67d9b10f-e986-4d29-bde2-10e08075fe17
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: platform
content-type: reference
discoiquuid: 6af48ef5-75e6-4b66-bc0d-ecf254b1c4ef
exl-id: f29868e3-d05c-4898-94d1-0c77ab6b72eb
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 0%

---

# Lettertypen toevoegen voor grafisch renderen{#adding-fonts-for-graphic-rendering}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

AEM kunt u afbeeldingen genereren waarin tekst dynamisch wordt overgenomen van uw inhoud.

Hiervoor kunt u ook uw eigen lettertypen laden en gebruiken.

Momenteel worden alle implementaties van het Java-Platform ondersteund [TrueType](https://en.wikipedia.org/wiki/Truetype) lettertypen.

1. Open CRXDE Lite en navigeer naar de projecttoepassingsmap:

   `/apps/<your-project>/`

1. Onder `/apps/<your-project>/` een nieuw knooppunt maken:

   * **Naam**: `fonts`
   * **Type**: `sling:Folder`

   Sla alle wijzigingen op.

1. Kopieer de lettertypebestanden naar deze map; bijvoorbeeld WebDAV gebruiken.

   >[!NOTE]
   >
   >Fontbestanden in de opslagplaats moeten het achtervoegsel hebben `*.ttf` of `*.TTF`.

1. Werk de [OSGi-configuratie](/help/sites-deploying/configuring-osgi.md) van [Day Commons GFX Font Helper](/help/sites-deploying/osgi-configuration-settings.md). Voeg het pad toe aan de map met lettertypen. d.w.z. `/apps/<your-project>/fonts`.

1. Terug naar CRXDE Lite. U moet nu een `.fontlist` in uw map met de naam van de geïmporteerde lettertypen.

   Deze lettertypen kunnen nu worden gebruikt in de Java API.

Zie voor meer informatie over het gebruik van de lettertypen met de Java API de [documentatie voor de klasse Font van de Java API](https://download.oracle.com/javase/6/docs/api/java/awt/Font.html).
