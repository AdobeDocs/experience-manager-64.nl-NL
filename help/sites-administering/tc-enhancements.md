---
title: Verbeterde vertaling
seo-title: Translation Enhancements
description: Verbeterde vertaalfuncties in AEM.
seo-description: Translation enhancements in AEM.
uuid: 0563603f-327b-48f1-ac14-6777c06734b9
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: site-features
content-type: reference
discoiquuid: 42df2db3-4d3c-4954-a03e-221e2f548305
feature: Language Copy
exl-id: 57a77cec-e228-4ec7-8502-e6e23baddd92
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 0%

---

# Verbeterde vertaling{#translation-enhancements}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Deze pagina biedt incrementele verbeteringen en verfijningen voor AEM vertaalbeheermogelijkheden.

## Automatisering van vertaalprojecten {#translation-project-automation}

Er zijn opties toegevoegd om de productiviteit bij vertaalprojecten te verbeteren, zoals het automatisch promoten en verwijderen van lanceringen van vertalingen en het plannen van de terugkerende uitvoering van een vertaalproject.

1. Klik of tik in het vertaalproject op de ellips onder aan het **Omzettingsoverzicht** tegel.

   ![screen_shot_2018-04-19at222622](assets/screen_shot_2018-04-19at222622.jpg)

1. Naar de **Geavanceerd** tab. Onderaan kunt u **Automatisch introducties voor vertaling bevorderen**.

   ![screen_shot_2018-04-19at223430](assets/screen_shot_2018-04-19at223430.jpg)

1. U kunt desgewenst instellen of het starten van vertalingen na ontvangst van vertaalde inhoud automatisch moet worden bevorderd en verwijderd.

   ![screen_shot_2018-04-19at224033](assets/screen_shot_2018-04-19at224033.jpg)

1. Selecteer de frequentie met de vervolgkeuzelijst onder om de terugkerende uitvoering van een vertaalproject te selecteren **Vertaling herhalen**. Het terugkomen van projectuitvoering zal automatisch vertaalbanen in de gespecificeerde intervallen creëren en uitvoeren.

   ![screen_shot_2018-04-19at223820](assets/screen_shot_2018-04-19at223820.jpg)

## Meertalige vertaalprojecten {#multilingual-translation-projects}

Het is mogelijk om veelvoudige doeltalen in een vertaalproject te vormen, om het totale aantal gecreeerde vertaalprojecten te verminderen.

1. Klik of tik in uw vertaalproject op de stippen onder aan het **Omzettingsoverzicht** tegel.

   ![screen_shot_2018-04-19at222622](assets/screen_shot_2018-04-19at222622.jpg)

1. Naar de **Geavanceerd** tab. U kunt meerdere talen toevoegen onder **Doeltaal**.

   ![screen_shot_2018-04-22at212601](assets/screen_shot_2018-04-22at212601.jpg)

1. U kunt ook talen toevoegen en **Vertaalproject voor meerdere talen maken**.

   ![screen_shot_2018-04-22at212941](assets/screen_shot_2018-04-22at212941.jpg)

1. In het project worden vertaalbanen gecreëerd voor elke doeltaal. Zij kunnen of één voor één binnen het project, of allen in één keer zijn begonnen door het project globaal in Projecten Admin uit te voeren.

   ![screen_shot_2018-04-22at213854](assets/screen_shot_2018-04-22at213854.jpg)

## Updates van vertaalgeheugen {#translation-memory-updates}

Handmatige bewerkingen van vertaalde inhoud kunnen worden gesynchroniseerd met het TMS (Translation Management System) om het vertaalgeheugen te trainen.

1. Selecteer vanuit de Sites-console na het bijwerken van tekstinhoud in een vertaalde pagina de optie **Vertaalgeheugen bijwerken**.

   ![screen_shot_2018-04-22at234430](assets/screen_shot_2018-04-22at234430.jpg)

1. Een lijstmening toont een zij-aan-zij vergelijking van de bron en de vertaling voor elke tekstcomponent die werd uitgegeven. Selecteer welke vertalingsupdates moeten worden gesynchroniseerd met Vertaalgeheugen en selecteer **Geheugen bijwerken**.

   ![screen_shot_2018-04-22at235024](assets/screen_shot_2018-04-22at235024.jpg)

   >[!NOTE]
   >
   >AEM stuurt de geselecteerde tekenreeksen terug naar het vertaalbeheersysteem.

## Taalkopieën op meerdere niveaus {#language-copies-on-multiple-levels}

Taalwortels kunnen nu worden gegroepeerd onder knooppunten, bijvoorbeeld per regio, terwijl ze nog steeds worden herkend als wortels van taalkopieën.

![screen_shot_2018-04-23at144012](assets/screen_shot_2018-04-23at144012.jpg)

>[!CAUTION]
>
>Er is slechts één niveau toegestaan. Met de volgende code kan de pagina &#39;es&#39; bijvoorbeeld niet worden omgezet in een taalkopie:
>
>* `/content/we-retail/language-masters/en`
>* `/content/we-retail/language-masters/americas/central-america/es`
>
>Dit `es` taalkopie wordt niet gedetecteerd omdat het zich op twee niveaus (americas/centraal-america) van de `en` knooppunt.

>[!NOTE]
>
>Taalwortels kunnen elke paginanaam hebben, in plaats van alleen de ISO-code van de taal. AEM zal altijd het pad en de naam eerst controleren, maar als de paginanaam geen taal identificeert, zal AEM de eigenschap cq:language van de pagina controleren op de taalidentificatie.

## Vertaalstatus rapporteren {#translation-status-reporting}

Een eigenschap kan nu worden geselecteerd in de lijstweergave Sites, die aangeeft of een pagina is vertaald, vertaald of nog niet is vertaald. Deze weergeven:

1. Ga in Sites naar **Lijstweergave.**

   ![screen_shot_2018-04-23at130646](assets/screen_shot_2018-04-23at130646.jpg)

1. Klikken of tikken **Instellingen weergeven**.

   ![screen_shot_2018-04-23at130844](assets/screen_shot_2018-04-23at130844.jpg)

1. Controleren **Vertaald** selectievakje onder **Vertaling** en tik/klik **Bijwerken**.

   ![screen_shot_2018-04-23at130955](assets/screen_shot_2018-04-23at130955.jpg)

U kunt nu een **Vertaald** kolom met de vertaalstatus van de pagina&#39;s.

![screen_shot_2018-04-23at133821](assets/screen_shot_2018-04-23at133821.jpg)
