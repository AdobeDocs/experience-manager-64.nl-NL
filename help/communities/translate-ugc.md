---
title: Door gebruiker gegenereerde inhoud vertalen
seo-title: Translating User Generated Content
description: De werking van de vertaalfunctie
seo-description: How the translation feature works
uuid: 7ee3242c-2aca-4787-a60d-b807161401ad
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: bfaf80c5-448b-47fb-9f22-57ee0eb169b2
role: Admin
exl-id: b8cbc429-b0c3-4f6e-a15f-4aef54733c8e
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1117'
ht-degree: 0%

---

# Door gebruiker gegenereerde inhoud vertalen {#translating-user-generated-content}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

De vertaalfunctie voor AEM Communities breidt het concept van [pagina-inhoud omzetten](../../help/sites-administering/translation.md) aan de gebruiker geproduceerde inhoud (UGC) die aan communautaire plaatsen wordt gepost gebruikend [SCF-componenten (Social Component Framework)](scf.md).

De vertaling van UGC stelt bezoekers en leden van de site in staat een wereldwijde gemeenschap te ervaren door taalbarrières te verwijderen.

Als voorbeeld, veronderstel:

* Een Franse afgevaardigde plaatst een recept in het Frans op het communautair forum van een multinationale kookwebsite
* Een ander Japans lid gebruikt de vertaalfunctie om het recept van het Frans naar het Japans te vertalen
* Na het lezen van het recept in het Japans schrijft het Japanse lid een opmerking in het Japans
* Het Franse lid gebruikt de vertaalfunctie om de Japanse opmerking in het Frans te vertalen
* Wereldwijde communicatie!

## Overzicht {#overview}

In deze sectie van de documentatie wordt specifiek besproken hoe de vertaalservice werkt met UGC en wordt een inzicht in de manier waarop u AEM met een [vertaalserviceprovider](../../help/sites-administering/translation.md#connectingtoatranslationserviceprovider) en integreer die dienst in een website door te vormen [vertaalintegratiekader](../../help/sites-administering/tc-tic.md).

Wanneer een vertaaldienstverlener met de plaats wordt geassocieerd, handhaaft elke taalexemplaar van de plaats zijn eigen draden van UGC die door componenten SCF zoals commentaren wordt gepost.

Wanneer een kader van de vertaalintegratie naast de vertaaldienstverlener wordt gevormd, is het mogelijk voor elke taalexemplaar van de plaats om één enkele draad van UGC te delen, waarbij globale mededeling over taalexemplaren wordt verstrekt. In plaats van een besprekingsdraad die door taal wordt gescheiden, gevormd [algemene gedeelde opslag](#global-translation-of-ugc) laat de volledige draad toe om zichtbaar te zijn ongeacht welke taal het wordt bekeken. Bovendien kunnen de veelvoudige configuraties van de vertaalintegratie worden gevormd specificerend verschillende globale gedeelde opslag voor een logische groepering van globale deelnemers, zoals door gebieden.

## De standaardvertaalservice {#the-default-translation-service}

AEM Communities bevat een [proeflicentie](../../help/sites-administering/tc-msconf.md#microsoft-translator-trial-license) voor een [standaardvertaalservice](../../help/sites-administering/tc-msconf.md) ingeschakeld voor meerdere talen.

Wanneer [het creëren van een communautaire plaats](sites-console.md), wordt de standaardvertaalservice ingeschakeld wanneer `Allow Machine Translation` wordt gecontroleerd door [VERTALING](sites-console.md#translation) subpanel.

>[!CAUTION]
>
>De standaardvertaalservice is alleen bedoeld voor demonstratie.
>
>Voor een productiesysteem is een vertaaldienst met licentie vereist. Als er geen licentie wordt verleend, moet de standaardvertaalservice [uitgeschakeld](../../help/sites-administering/tc-msconf.md#microsoft-translator-trial-license-geometrixx-outdoors).

## Wereldwijde omzetting van UGC {#global-translation-of-ugc}

Wanneer een website meerdere [taalkopieën](../../help/sites-administering/tc-prep.md), erkent de standaardvertaaldienst niet dat UGC ingegaan op één plaats met UGC zou kunnen verwant zijn ingegaan op een andere, aangezien wanneer UGC, hoofdzakelijk, door de zelfde component (de taalexemplaar van de pagina die de component bevat) wordt geproduceerd.

Het is vergelijkbaar met groepen mensen die een onderwerp bespreken dat niet op de hoogte is van opmerkingen die in andere groepen dan hun eigen groepen worden gemaakt, in vergelijking met iedereen in één grote groep die aan één gesprek deelneemt.

Als &quot;één groepsgesprek&quot;wordt gewenst, is het mogelijk om globale vertaling over een website met veelvoudige taalexemplaren toe te laten, zodat de volledige draad zichtbaar is ongeacht welke taalexemplaar het wordt bekeken.

Bijvoorbeeld, als een forum op de basisplaats werd gevestigd, gemaakte taalexemplaren, en globale vertaling werd toegelaten, dan zou een onderwerp dat aan het forum in één taalexemplaar wordt gemaakt in alle taalexemplaren verschijnen. Hetzelfde geldt voor alle antwoorden, ongeacht van welke taalkopie het antwoord is ingevuld. Het resultaat zou zijn dat het onderwerp en zijn volledige draad van antwoorden ongeacht van welke taalexemplaar het onderwerp wordt bekeken zichtbaar zijn.

>[!CAUTION]
>
>UGC&#39;s die vóór de algemene vertaling bestonden, zijn niet meer zichtbaar.
>
>Terwijl de UGC zich nog steeds in de [gemeenschappelijk archief](working-with-srp.md), wordt het gevestigd onder de taal-specifieke plaats UGC, terwijl de nieuwe inhoud, die na globale vertaling wordt toegevoegd, van de globale gedeelde opslagplaats wordt teruggewonnen.
>
>Er is geen migratiehulpmiddel om taalspecifieke inhoud in de globale gedeelde opslag te bewegen of samen te voegen.

### Configuratie vertaalintegratie {#translation-integration-configuration}

Om een nieuwe Vertaalintegratie tot stand te brengen, die een schakelaar van de Vertaaldienst met de website op de auteursinstantie integreert:

* Aanmelden als beheerder
* Van de [hoofdmenu](http://localhost:4502/)
* Selecteer **[!UICONTROL Tools]**
* Selecteer **[!UICONTROL Operations]**
* Selecteer **[!UICONTROL Cloud]**
* Selecteer **[!UICONTROL Cloud Services]**
* Omlaag schuiven naar **[!UICONTROL Translation Integration]**

![chlimage_1-65](assets/chlimage_1-65.png)

* Selecteer **[!UICONTROL Show Configurations]**

![chlimage_1-66](assets/chlimage_1-66.png)

* Selecteren `[+]` pictogram naast **[!UICONTROL Available Configurations]** om een nieuwe configuratie te creëren

#### Configuratiedialoogvenster maken {#create-configuration-dialog}

![chlimage_1-67](assets/chlimage_1-67.png)

* **[!UICONTROL Parent Configuration]**
(Vereist) Verlaat gewoonlijk als gebrek. Standaard is 
`/etc/cloudservices/translation`.

* **[!UICONTROL Title]**
(Vereist) Voer de gewenste weergavetoewijzing in. Geen standaardwaarde.

* **[!UICONTROL Name]**
(Optioneel) Voer een naam in voor de configuratie. De standaardwaarde is een knooppuntnaam die op de Titel wordt gebaseerd.

* Selecteer **[!UICONTROL Create]**

#### Dialoogvenster Config voor vertaling {#translation-config-dialog}

![chlimage_1-68](assets/chlimage_1-68.png)

Voor gedetailleerde instructies gaat u naar [Een configuratie voor vertaalintegratie maken](../../help/sites-administering/tc-tic.md#creating-a-translation-integration-configuration)

* **[!UICONTROL Sites]** tab: kan als gebrek verlaten
* **[!UICONTROL Communities]** tab:
   * **[!UICONTROL Translation Provider]**
Selecteer de vertaalprovider in de vervolgkeuzelijst. Standaard is 
`microsoft`, de testservice.

   * **[!UICONTROL Content Category]**
Selecteer een categorie die de inhoud beschrijft die wordt vertaald. Standaard is 
`General.`

   * **[!UICONTROL Choose A Locale...]**
(Optioneel) Als u een landinstelling selecteert voor het opslaan van UGC, worden posts van alle taalkopieën in één algemeen gesprek weergegeven. Kies bij conventie de landinstelling voor de [basistaal](sites-console.md#translation) voor de website. Kiezen `No Common Store` schakelt algemene vertaling uit. Globale vertaling is standaard uitgeschakeld.

* **[!UICONTROL Assets]** tab: kan als gebrek verlaten
* Selecteer **[!UICONTROL OK]**

#### Activering {#activation}

De nieuwe vertaalintegratie-cloudservice moet worden geactiveerd voor de publicatieomgeving. Als de activeringsworkflow nog niet is geactiveerd en aan een website is gekoppeld, wordt gevraagd om deze cloudserviceconfiguratie te publiceren wanneer de pagina wordt gepubliceerd waaraan deze is gekoppeld.

## Vertaalinstellingen beheren {#managing-translation-settings}

>[!NOTE]
>
>**Voorkeurstaal**
>
>Om na te gaan of de post zich in een andere taal dan de voorkeurstaal bevindt, moet de voorkeurstaal van de bezoeker worden vastgesteld.
>
>De voorkeurstaal is de taalvoorkeur die is ingesteld in het profiel van de gebruiker, wanneer de bezoeker van de site is aangemeld en een taalvoorkeur heeft opgegeven.
>
>Wanneer de bezoeker van de site anoniem is of geen taalvoorkeur in hun profiel heeft gespecificeerd, is de aangewezen taal de basistaal van het paginasjabloon.

### Gebruikersvoorkeur {#user-preference}

#### Gebruikersprofiel {#user-profile}

Alle Communitysites bieden een gebruikersprofiel dat de ondertekenaars kunnen bewerken om zichzelf te identificeren voor de community en hun voorkeuren in te stellen.

Een van deze instellingen is of gemeenschapsinhoud altijd in de taal van uw voorkeur moet worden weergegeven. De instelling is standaard niet ingesteld en wordt standaard ingesteld op de systeeminstelling. De gebruiker kan de instelling wijzigen in Aan of Uit en zo de systeeminstelling overschrijven.

Wanneer de pagina&#39;s automatisch in de aangewezen taal van de gebruiker worden vertaald, wordt UI voor het tonen van de originele tekst en het verbeteren van de vertaling nog ter beschikking gesteld.

![chlimage_1-69](assets/chlimage_1-69.png)

### Site-instelling van community {#community-site-setting}

Wanneer een communautaire Plaats wordt gecreeerd, kan de vertaaloptie worden toegelaten en worden gevormd. De vertaalinstelling is van kracht voor inhoud die anonieme sitebezoekers kunnen bekijken, maar wordt overschreven door de profielinstelling van de gebruiker.
