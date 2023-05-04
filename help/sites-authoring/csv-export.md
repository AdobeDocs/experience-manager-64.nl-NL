---
title: Exporteren naar CSV
seo-title: Export to CSV
description: Informatie over uw pagina's exporteren naar een CSV-bestand op uw lokale systeem
seo-description: Export information about your pages to a CSV file on your local system
uuid: aa03adac-bbfb-4566-a153-25fe6f6843dd
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: page-authoring
content-type: reference
discoiquuid: d4473758-674a-42d6-923a-b536f7f9c1f7
exl-id: 52eb9c2f-ce29-4622-8726-802ac40246d4
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 12%

---

# Exporteren naar CSV{#export-to-csv}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

**CSV-export maken** kunt u informatie over uw pagina&#39;s naar een CSV-bestand op uw lokale systeem exporteren.

* Het gedownloade bestand wordt aangeroepen `export.csv`
* De inhoud is afhankelijk van de eigenschappen die u selecteert.
* U kunt het pad samen met de diepte van het exporteren definiëren.

>[!NOTE]
>
>De downloadfunctie en de standaardbestemming van uw browser worden gebruikt.

Met de wizard CSV-export maken kunt u het volgende selecteren:

* Te exporteren eigenschappen

   * Metagegevens

      * Gewijzigd
      * Gepubliceerd
   * Analyse

      * Paginaweergaven
      * Unieke bezoekers
      * Tijd op pagina


* Diepte

   * Bovenliggend pad
   * Alleen directe kinderen
   * Aanvullende niveaus voor kinderen
   * Niveaus

Het resultaat `export.csv` kan worden geopend in Excel of een andere compatibele toepassing.

![chlimage_1-58](assets/chlimage_1-58.png)

Maak **CSV-export** Deze optie is beschikbaar wanneer u in het dialoogvenster **Sites** console (in lijstweergave): het is een optie van **Maken** vervolgkeuzemenu:

![screen_shot_2018-03-21at154719](assets/screen_shot_2018-03-21at154719.png)

Een CSV-export maken:

1. Open de **Sites**-console en ga indien nodig naar de gewenste locatie.
1. Selecteer op de werkbalk de optie **Maken** dan **CSV-export** om de wizard te openen:

   ![screen_shot_2018-03-21at154758](assets/screen_shot_2018-03-21at154758.png)

1. Selecteer de eigenschappen die u wilt exporteren.
1. Selecteer **Maken**.
