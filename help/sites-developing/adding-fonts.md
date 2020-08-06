---
title: Lettertypen toevoegen voor grafisch renderen
seo-title: Lettertypen toevoegen voor grafisch renderen
description: AEM kunt u afbeeldingen genereren waarin tekst dynamisch wordt overgenomen van uw inhoud
seo-description: AEM kunt u afbeeldingen genereren waarin tekst dynamisch wordt overgenomen van uw inhoud
uuid: 67d9b10f-e986-4d29-bde2-10e08075fe17
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: platform
content-type: reference
discoiquuid: 6af48ef5-75e6-4b66-bc0d-ecf254b1c4ef
translation-type: tm+mt
source-git-commit: 00317d1ba79f10e98b4c52713d845092b7cc6c2e
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 0%

---


# Lettertypen toevoegen voor grafisch renderen{#adding-fonts-for-graphic-rendering}

AEM kunt u afbeeldingen genereren waarin tekst dynamisch wordt overgenomen van uw inhoud.

Hiervoor kunt u ook uw eigen lettertypen laden en gebruiken.

Momenteel ondersteunen alle implementaties van het Java-Platform [TrueType](https://en.wikipedia.org/wiki/Truetype) -lettertypen.

1. Open CRXDE Lite en navigeer naar de projecttoepassingsmap:

   `/apps/<your-project>/`

1. Onder `/apps/<your-project>/` maak een nieuw knooppunt:

   * **Naam**: `fonts`
   * **Type**: `sling:Folder`

   Sla alle wijzigingen op.

1. Kopieer de lettertypebestanden naar deze map; bijvoorbeeld WebDAV gebruiken.

   >[!NOTE]
   >
   >Fontbestanden in de opslagplaats moeten het achtervoegsel `*.ttf` of `*.TTF`.

1. Werk de [OSGi-configuratie](/help/sites-deploying/configuring-osgi.md) van de Helper [van het Font van GFX van de](/help/sites-deploying/osgi-configuration-settings.md)Dag bij. Voeg het pad toe aan de map met lettertypen. d.w.z. `/apps/<your-project>/fonts`.

1. Terug naar CRXDE Lite. Er wordt nu een `.fontlist` knooppunt in uw map weergegeven dat de naam van de geïmporteerde lettertypen bevat.

   Deze lettertypen kunnen nu worden gebruikt in de Java API.

Zie de [documentatie voor de klasse Font van de Java API](https://download.oracle.com/javase/6/docs/api/java/awt/Font.html)voor meer informatie over het gebruik van de lettertypen met de Java API.

