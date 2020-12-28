---
title: eCommerce
seo-title: eCommerce
description: 'AEM eCommerce helpt marketers merkboodschap, persoonlijke boodschappen op internet, mobiel en sociaal gebied te leveren. '
seo-description: 'AEM eCommerce helpt marketers merkboodschap, persoonlijke boodschappen op internet, mobiel en sociaal gebied te leveren. '
uuid: 14af7a3a-7211-4a56-aeef-1603128d5d8a
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: e-commerce
content-type: reference
discoiquuid: 68799110-8183-40fe-be4f-2a7c7a7b3018
translation-type: tm+mt
source-git-commit: eb1ae2b4910e7adef48865996db4837175f588d9
workflow-type: tm+mt
source-wordcount: '776'
ht-degree: 0%

---


# eCommerce{#ecommerce}

* [Concepten](/help/sites-administering/concepts.md)
* [Beheer (algemeen)](/help/sites-administering/generic.md)
* [SAP Commerce Cloud](/help/sites-administering/sap-commerce-cloud.md)
* [Salesforce Commerce Cloud](https://github.com/adobe/commerce-salesforce)
* [Magento](https://www.adobe.io/apis/experiencecloud/commerce-integration-framework/integrations.html#!AdobeDocs/commerce-cif-documentation/master/integrations/02-AEM-Magento.md)

Adobe verstrekt twee versies van het Kader van de Integratie van de Handel:

|  | CIF on prem | CIF Cloud |
|-------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------|
| Ondersteunde AEM | AEM on-prem of AMS 6.x | AEM AMS 6.4 en 6.5 |
| Terug | - AEM, Java <br> - Monolithische integratie, pre-build mapping (sjabloon)<br> - JCR-opslagplaats | - Magento <br>- Java en Javascript <br>- Geen gegevens van de Handel opgeslagen in de bewaarplaats van JCR |
| Voorkant | Gerenderde pagina&#39;s AEM op de server | Toepassing gemengde pagina (hybride rendering) |
| Productcatalogus | - Producimporteur, redacteur, caching in AEM <br> - Gewone catalogi met AEM of volmachtspagina&#39;s | - Geen product importeren <br>- Algemene sjablonen <br>- Gegevens op aanvraag via connector |
| Schaalbaarheid | - Kan maximaal een paar miljoen producten ondersteunen (afhankelijk van het gebruik) <br> - Caching op Dispatcher | - Geen volumebeperking <br>- Caching op Dispatcher of CDN |
| Gestandaardiseerd gegevensmodel | Nee | Ja, Magento GraphQL-schema |
| Beschikbaarheid | Ja:<br> - SAP Commerce Cloud (extensie bijgewerkt voor ondersteuning van AEM 6.4 en Hybris 5 (standaard) en handhaaft compatibiliteit met Hybris 4 <br>- Salesforce Commerce Cloud (connector open-sourced voor ondersteuning van AEM 6.4) | Ja via open bron via GitHub. <br> Magento Commerce (Ondersteunt Magento 2.3.2 (standaard) en compatibel met Magento 2.3.1). |
| Wanneer gebruiken | Beperkte gebruiksgevallen: Voor scenario&#39;s waarbij kleine, statische catalogi mogelijk moeten worden geïmporteerd | Voorkeursoplossing in de meeste gebruikscategorieën |

eCommerce handelt samen met Product Information Management (PIM) de activiteiten van een website die gericht is op het verkopen van producten via een online-winkel:

* Maken, levensduur en veroudering van een product
* Prijsbeheer
* Transactiebeheer
* Beheer van volledige catalogi
* Live en gecentraliseerde opslagrecords
* Webinterfaces

AEM eCommerce helpt marketers merkboodschap, persoonlijke boodschappen op internet, mobiel en sociaal gebied te leveren. In de AEM ontwerpomgeving kunt u pagina&#39;s en componenten aanpassen op basis van de context en de marketingstrategieën van de doelbezoeker. bijvoorbeeld:

* Productpagina&#39;s
* Winkelwagentjes
* Onderdelen uitchecken

De implementatie maakt realtime toegang tot productinformatie mogelijk. Dit kan worden gebruikt om af te dwingen:

* Integriteit van productinformatie
* Prijzen
* Voorraadinventaris
* Variaties in de toestand van een winkelwagentje

>[!NOTE]
>
>Als u het integratieframework wilt gebruiken met externe eCommerce-providers, moet u eerst de vereiste pakketten installeren. Voor meer informatie, zie [Het Opstellen van eCommerce](/help/sites-deploying/ecommerce.md).
>
>Voor informatie over het uitbreiden van de mogelijkheden van de eCommerce, zie [Developing eCommerce](/help/sites-developing/ecommerce.md).

## Belangrijkste kenmerken {#main-features}

AEM eCommerce biedt:

* Een aantal **out-of-the-box AEM componenten** om te illustreren wat voor uw project kan worden bereikt:

   * Productweergave
   * Winkelwagentje
   * Uitchecken
   * Onlangs bekeken producten
   * Vouchers
   * en andere

   ![chlimage_1-150](assets/chlimage_1-150.png)

   >[!NOTE]
   >
   >Met het integratieframework dat AEM biedt, kunt u ook extra AEM maken voor handelsmogelijkheden, onafhankelijk van uw specifieke eCommerce-engine.

* **Zoeken** :

   * de AEM
   * het zoeken van het eCommerce-systeem
   * een zoekopdracht van derden (zoals Search&amp;Promote)
   * of een combinatie daarvan.

   ![chlimage_1-151](assets/chlimage_1-151.png)

* Gebruikt de AEM mogelijkheid om uw inhoud **op meerdere kanalen te presenteren**, of dat nu het volledige browservenster of het mobiele apparaat is. Hierdoor wordt uw inhoud geleverd in de indeling die uw bezoekers nodig hebben.

   ![chlimage_1-152](assets/chlimage_1-152.png)

* De mogelijkheid om **uw eigen integratieimplementatie te ontwikkelen op basis van het [AEM eCommerce-framework](#the-framework)**.

   De twee momenteel beschikbare implementaties zijn beide op dezelfde basis gebaseerd - bovenop de algemene API (het framework). Het implementeren van een nieuwe integratie houdt alleen in dat u de functies implementeert die uw integratie nodig heeft. De front-end componenten kunnen door om het even welke nieuwe implementatie worden gebruikt aangezien zij interfaces (zo onafhankelijk van de implementatie zijn) gebruiken.

* De mogelijkheid om **ervaringsgestuurde handel te ontwikkelen op basis van verkoopgegevens en activiteit**. Dit staat u toe om vele scenario&#39;s te realiseren:

   * Een voorbeeld hiervan kan zijn het verlagen van de verzendkosten wanneer de totale bestelling een bepaald bedrag overschrijdt.
   * Een andere mogelijkheid is mogelijk om seizoensgebonden aanbiedingen te doen die profielgegevens gebruiken (bijvoorbeeld locatie). Deze kunnen vervolgens worden gemarkeerd, ook als dat nodig is, afhankelijk van andere factoren.

   In het onderstaande voorbeeld ziet u een gummetje omdat de inhoud van het karretje minder dan $75 bedraagt:

   ![chlimage_1-153](assets/chlimage_1-153.png)

   Dit kan worden gewijzigd wanneer de inhoud van het winkelwagentje meer dan $75 bedraagt:

   ![chlimage_1-154](assets/chlimage_1-154.png)

* en andere functies, zoals:

   * De inhoud van het winkelwagentje blijft behouden tijdens sessies
   * Historie van volledige volgorde
   * Catalogusupdate uitvoeren

## Het framework {#the-framework}

In de sectie [Concepts](/help/sites-administering/concepts.md) wordt het framework gedetailleerder beschreven, maar de volgende secties bieden een snelle weergave op hoog niveau van het framework:

### Wat? {#what}

* Het integratieframework biedt de API, een reeks componenten om functionaliteit te illustreren en diverse extensies om voorbeelden van verbindingsmethoden te bieden.
* Het kader biedt de basisstructuur die nodig is voor de uitvoering van een project.
* Het kader is uitbreidbaar.
* Het framework biedt geen kant-en-klare site. Er is altijd een zekere hoeveelheid ontwikkelingswerk nodig om het kader aan uw specificaties aan te passen.

### Waarom? {#why}

* Om de basismechanismen te verstrekken nodig om een aangepaste plaats van de Handel snel te realiseren.
* Tp biedt de flexibiliteit die nodig is voor de ontwikkeling van een echte eCommerce-site.
* Beste werkwijzen illustreren.

