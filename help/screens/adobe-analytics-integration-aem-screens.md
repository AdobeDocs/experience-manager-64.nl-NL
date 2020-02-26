---
title: Adobe Analytics Integration with AEM Screens
seo-title: Adobe Analytics Integration with AEM Screens
description: Volg deze pagina om meer te weten te komen over de integratie van AEM-schermen in de box met Adobe Analytics en geeft u een proefdruk van het afspelen.
seo-description: Volg deze pagina om meer te weten te komen over de integratie van AEM-schermen in de box met Adobe Analytics en geeft u een proefdruk van het afspelen.
uuid: f4f71c85-ab6b-4e4d-94d3-5ba55ec0a246
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/SCREENS
topic-tags: administering
discoiquuid: 2784b590-3402-492f-94a6-36fe16633e89
translation-type: tm+mt
source-git-commit: cdec5b3c57ce1c80c0ed6b5cb7650b52cf9bc340

---


# Adobe Analytics Integration with AEM Screens{#adobe-analytics-integration-with-aem-screens}

>[!CAUTION]
>
>Deze AEM-schermfunctionaliteit is alleen beschikbaar als u AEM 6.4.2 Feature Pack 2 en AEM 6.3.3 Feature Pack 4 hebt geïnstalleerd.

>Als u toegang wilt krijgen tot een van deze functiepakketten, neemt u contact op met de ondersteuning van Adobe en vraagt u om toegang. Als u beschikt over de juiste machtigingen, kunt u deze downloaden via Pakket delen.
>
In deze sectie worden de volgende onderwerpen behandeld:

* **Overzicht**
* **Architectuurafbeeldingen**
* **Eigenschappen configureren**

## Overzicht {#overview}

***AEM Screens*** gebruikt de Analytics van Adobe, en daarmee kunt u iets uniek in de markt - dwars-kanaalanalyses bereiken die helpen inhoud correleren die in plaats met andere gegevensbronnen wordt getoond.

AEM Screens verstrekt een out-of-the-box integratie met de Analytics van Adobe en verstrekt u een bewijs van spel.

In deze sectie wordt de volgende functionaliteit beschreven die betrokken is bij het verbinden van een AEM Screens-project met Adobe Analytics:

* Staat voor bewijs van spel rapportering door apparaat toe
* Staat toe dat de verslaggeving van de play-out per actief wordt aangetoond
* Hiermee zorgt u ervoor dat alle spelergebeurtenissen worden vastgelegd en voorzien van een tijdstempel
* Hiermee zorgt u ervoor dat alle spelergebeurtenissen lokaal worden opgeslagen als het afspelen niet is verbonden met een netwerk

De integratie van Adobe Analytics met AEM Screens handhaaft zo de volgende *doelstellingen*:

* ROI van de implementatie van de digitale handtekening inschakelen
* Analyses integreren als basis voor toekomstige mogelijkheden voor het verzamelen en analyseren van gebruiksinformatie

## Architectuurafbeeldingen {#architectural-details}

In het volgende architectuurdiagram wordt de integratie van Adobe Analytics met AEM-schermen uitgelegd:

![screen_shot_2018-09-12at85611am](assets/screen_shot_2018-09-12at85611am.png)

## Adobe-analysemogelijkheden inschakelen in AEM-schermen {#enabling-adobe-analytics-in-aem-screens}

De Adobe Analytics-instellingen kunnen worden geconfigureerd via de OSGi-console.

Ga naar de webconsoleconfiguratie **van** Adobe Experience Manager om Adobe Analytics voor AEM Screens te configureren, zoals in de onderstaande afbeelding wordt getoond:

![screen_shot_2018-09-04at25550pm](assets/screen_shot_2018-09-04at25550pm.png)

### Eigenschappen configureren {#configuring-the-properties}

>[!CAUTION]
Voordat u de eigenschappen configureert, neemt u contact op met uw Adobe-relatiebeheerder om een ticket te maken voor een **Anaytics API Key** and **Anaytics Project** voor gebruik met AEM-schermen.

In de volgende tabel worden de eigenschappen met hun beschrijving gemarkeerd voor het configureren van Adobe Analytics voor AEM-schermen:

<table> 
 <tbody>
  <tr>
   <td><strong>Eigenschap</strong></td> 
   <td><strong>Beschrijving</strong></td> 
  </tr>
  <tr>
   <td><strong>URL voor analyse</strong></td> 
   <td>URL om analysegegevens van de speler te posten<br /> </td> 
  </tr>
  <tr>
   <td><strong>Sleutel Analytics API</strong></td> 
   <td>API-sleutel voor verificatie bij de Adobe Analytics-server (meegeleverd door Accounts Manager)</td> 
  </tr>
  <tr>
   <td><strong>Analyseproject</strong></td> 
   <td>AEM Screens project dat op uw analyses wordt gevormd om gegevens (die door de Manager van Rekeningen worden verstrekt) te ontvangen</td> 
  </tr>
  <tr>
   <td><strong>Omgeving</strong></td> 
   <td><p>Fase- of productieomgeving.</p> <p><em>Voor ontwikkeling/fase</em> - https://cc-api-data-stage.adobe.io/ingest/<br /> <em>For Production</em> - https://cc-api-data.adobe.io/ingest/</p> </td> 
  </tr>
  <tr>
   <td><strong>Verzendfrequentie voor analyse</strong></td> 
   <td>Frequentie in minuten voor het verzenden van analysegegevens van de spelers. De standaardwaarde is 15 minuten.</td> 
  </tr>
 </tbody>
</table>

>[!NOTE]
Standaard is de **Analytics Send Frequency **15 minuten.

#### Adobe Analytics Service gebruiken in AEM-schermen {#using-adobe-analytics-service-in-aem-screens}

Dit scenario haalt Analytics API door de vraag van het HART van een analysedienst in de ingebouwde programmatuur en de apparaat scherm-kern componenten aan om gebeurtenissen uitdrukkelijk tot stand te brengen en te verzenden specifiek voor een bepaald gebruiksgeval terwijl het toestaan van rekbaarheid waar om het even welk douanebericht naar Analytics van een douane ontwikkeld kanaal kan worden verzonden.

Analytische gebeurtenissen worden offline opgeslagen in geïndexeerdeDB en later afgekapt en naar de cloud verzonden.

>[!NOTE]
Meer informatie over de ***Opeenvolging*** en het ***Standaard Gegevensmodel voor Gebeurtenissen***, gelieve te verwijzen naar het [Vormen de Analytics van Adobe voor de Schermen](configuring-adobe-analytics-aem-screens.md) van AEM in de sectie van de Ontwikkelaar van de Schermen AEM.

