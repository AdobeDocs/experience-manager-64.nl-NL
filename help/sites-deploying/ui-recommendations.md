---
title: Gebruikersinterface Recommendations voor klanten
seo-title: Gebruikersinterface Recommendations voor klanten
description: 'Een lijst met aanbevelingen voor de klassieke en geoptimaliseerde gebruikersinterfaces. '
seo-description: 'Een lijst met aanbevelingen voor de klassieke en geoptimaliseerde gebruikersinterfaces. '
uuid: c661fb10-4dbc-4f8b-93be-3e77af1ad095
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: best-practices
discoiquuid: 42bf42cb-0c6c-4390-8170-2c540c4d3ed3
translation-type: tm+mt
source-git-commit: 5b00783e4471a6b142ab17a7bc4a647ab04aec5f
workflow-type: tm+mt
source-wordcount: '808'
ht-degree: 0%

---


# Gebruikersinterface Recommendations voor klanten{#user-interface-recommendations-for-customers}

Adobe Experience Manager 6.4 wordt geleverd met twee UI&#39;s: de Unified Experience Cloud UI en de Klassieke UI.

Dit document is bedoeld om klanten te helpen een keuze te maken over welke interface ze moeten gebruiken, afhankelijk van hun situatie.

Belangenvoorwaarden:

* **UI (of standaard UI)**
Modern gebruikersinterface die in 5.6.0 als technologievoorproef werd geïntroduceerd en in verdere versies werd uitgebreid. De interface is gebaseerd op de ervaring van één gebruiker voor de Adobe Experience Cloud, die voorheen wel een interface met aanraakbediening of een interface met aanraakbediening werd genoemd.

* **Klassieke interface**
UIUser gebaseerd op technologie ExtJS die met CQ 5.1 in 2008 werd geïntroduceerd.

* **Site-**
beheermogelijkheden om de sitehiërarchie te beheren (verwijzingen verplaatsen, activeren, beheren) en nieuwe pagina&#39;s te maken.

* **Page**
AuthoringCapabilities om de inhoud van een pagina toe te voegen of te bewerken.

* **DAM/Assets**
AdminCapabilities voor het beheren van digitale elementen (waaronder afbeeldingen, video, documenten, downloads).

* ****
ContextHubCapabilities om informatie over de bezoeker samen te voegen en het voor diverse doeleinden te gebruiken. Verstrekt een gebruikersinterface om personen te simuleren die de plaats bezoeken. Beginnend AEM 6.2, vervangt ContextHub de vorige technologie, de Context van de Cliënt.

## Algemeen {#general}

In de afgelopen jaren heeft Adobe alle Adobe Experience Cloud-oplossingen bijgewerkt met één gebruikersinterface. Gebruikers in de Experience Cloud-oplossingen genieten van een consistente ervaring met gangbare patronen voor het gebruik en het gebruik van de toepassingen. Met elke versie, heeft Adobe het gebruikersinterface verfijnd die op terugkoppelen van klanten wordt gebaseerd die over de diverse oplossingen werken.

De oorspronkelijke gebruikersinterface voor Adobe Experience Manager (voorheen CQ5 genoemd), die in 2008 werd geïntroduceerd en door klanten met versies 5.0-5.6.1 werd gebruikt, staat in AEM 6.4. Dit garandeert dat klanten een update naar versie 6.4 kunnen uitvoeren en kunnen profiteren van een bijgewerkt platform met nieuwe mogelijkheden en dezelfde gebruikersinterface kunnen blijven gebruiken.

Adobe raadt klanten aan om in 2018/2019 over te schakelen naar de nieuwe interface. Dit kan of tijdens de update aan 6.4 - of in een afzonderlijke projecten na de update worden gedaan, die de noodzakelijke aanpassingen aan de aanpassingen en componentendialogen zou omvatten.

Adobe is niet van plan om vanaf AEM 6.4 verdere verbeteringen aan te brengen in de klassieke gebruikersinterface. Merk op dat Klassieke UI volledig wordt gesteund terwijl wordt afgekeurd.

## Regels en Recommendations {#rules-and-recommendations}

Hieronder volgt een lijst met aanbevelingen van Product Management voor Adobe Experience Manager 6.4:

<table> 
 <tbody> 
  <tr> 
   <th>Mijn project...</th> 
   <th>Recommendations</th> 
  </tr> 
  <tr> 
   <td>Adobe Experience Manager begint net te gebruiken.</td> 
   <td>Gebruik de standaardinterface.</td> 
  </tr> 
  <tr> 
   <td><p>Heeft AEM een tijdje gebruikt.</p> <p>Gebruikt de productUI uit-van-de-doos en ontwikkelde douanecomponenten voor de plaatsen.<br /> </p> </td> 
   <td> 
    <ol> 
     <li>Bijwerken naar 6.4</li> 
     <li>De standaardinterface gebruiken voor sitebeheer, elementen, ... etc.<br /> </li> 
     <li>Configureer de actie Pagina bewerken om de klassieke UI-pagina-editor te openen. Zie <a href="#selecting-your-ui">Uw interface selecteren</a>.</li> 
    </ol> <p>In een tweede fase:</p> 
    <ol> 
     <li>Werk uw componentendialogen bij om het Coral 3 dialoogvakje formaat te gebruiken. Adobe raadt aan de <a href="/help/sites-developing/modernization-tools.md">AEM Moderniseringsgereedschappen</a> te gebruiken om de componenten bij te werken.</li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td>Heeft een site gemaakt die de ClientContext met integratie gebruikt.<br /> </td> 
   <td> 
    <ol> 
     <li>Bijwerken naar 6.4</li> 
     <li>De standaardinterface gebruiken voor sitebeheer, elementen, ... enz.</li> 
     <li>Configureer de actie Pagina bewerken om de klassieke UI-pagina-editor te openen. Zie <a href="#selecting-your-ui">Uw interface selecteren</a>.</li> 
    </ol> <p>In een tweede fase:</p> 
    <ol> 
     <li>Werk uw componentendialogen bij om het Coral 3 dialoogvakje formaat te gebruiken. Adobe raadt aan de <a href="/help/sites-developing/modernization-tools.md">AEM Moderniseringsgereedschappen</a> te gebruiken om de componenten bij te werken.</li> 
     <li>Vorm ContextHub (de vervanging voor ClientContext) en werk de paginasjablonen bij om ContextHub te gebruiken. Merk op dat ContextHub een verenigbaarheidswijze heeft die het laden van douaneClientContext opslag toestaat.</li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td><p>Heeft CQ/AEM jarenlang gebruikt.</p> <p>De interface voor het product (bijvoorbeeld Sitebeheer) is uitgebreid en componenten met uitgebreide bewerkingsdialoogvensters zijn samengesteld.</p> </td> 
   <td><p>Update aan 6.4 en vorm klassieke UI als gebrek voor paginascreatie voor alle gebruikers. Zie <a href="#selecting-your-ui">Uw interface selecteren</a>.</p> <p>Start vervolgens een project om de deeldialoogvensters aan te passen en te optimaliseren in de indeling Coral 3. Zie <a href="#resources-to-help">Bronnen voor Help</a>.<br /> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Veelgestelde vragen {#faq}

Raadpleeg het Knowledge Base-artikel [Touch UI Authoring FAQ](https://helpx.adobe.com/experience-manager/kb/index/touchui_faq.html) voor meer informatie. met inbegrip van om het even welke informatie over het afschilderingsprogramma voor klassieke UI.

## UI {#selecting-your-ui} selecteren

Zie [Uw interface selecteren](/help/sites-authoring/select-ui.md) voor informatie over het configureren van uw systeem zoals vereist.

## Touch-Optimized UI Status {#touch-optimized-ui-status}

Zie [Nieuwe functies](/help/release-notes/release-notes.md#what-s-new) in de Opmerkingen bij de release voor meer informatie over de verbeteringen aan de interface met geoptimaliseerde aanrakingen in AEM 6.3.

Een volledig overzicht vindt u op de pagina [Status van aanraakinterface](/help/release-notes/touch-ui-features-status.md)

## Bronnen voor Help {#resources-to-help}

Voor achtergrondinformatie over basisverwerking:

* [Werken met de auteuromgeving](/help/sites-authoring/home.md).
* [Pagina&#39;s](/help/sites-authoring/author-environment-tools.md) ontwerpen.

Voor gedetailleerde ontwikkelingsinformatie:

* [Touch-geoptimaliseerde UI-architectuur](/help/sites-developing/touch-ui-concepts.md).
* Met de [AEM Moderniseringsgereedschappen](/help/sites-developing/modernization-tools.md) kunt u dialoogvensters voor het bewerken van componenten omzetten van de klassieke interface naar de interface voor het optimaliseren van aanrakingen.

* [Structuur van de geoptimaliseerde interface](/help/sites-developing/touch-ui-structure.md) voor aanrakingen.

* [De consoles aanpassen in de geoptimaliseerde gebruikersinterface](/help/sites-developing/customizing-consoles-touch.md)  voor aanraakfuncties (inclusief voorbeeldcode).

* [Het aanpassen van paginaontwerp in touch-geoptimaliseerde UI](/help/sites-developing/customizing-page-authoring-touch.md)  (omvat steekproefcode).

* [AEM Gem-sessie bij aanraakgeoptimaliseerde aanpassing](https://docs.adobe.com/content/ddc/en/gems/user-interface-customization-for-aem-6.html).
* [Granite UI-documentatie](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/granite-ui/api/index.html).

