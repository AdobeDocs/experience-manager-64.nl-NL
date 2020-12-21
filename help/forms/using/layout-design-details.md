---
title: Indelingsontwerp
seo-title: Indelingsontwerp
description: Layout Design Details legt uit hoe u lay-outs kunt maken die voor uw brieven of Interactieve Mededelingen moeten worden gebruikt.
seo-description: Layout Design Details legt uit hoe u lay-outs kunt maken die voor uw brieven of Interactieve Mededelingen moeten worden gebruikt.
uuid: b21af474-07f5-4bfe-af7d-0c322e2452ae
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: correspondence-management, interactive-communications
discoiquuid: 046b1bf9-1ac7-4e2e-ab37-6fe5422dfa20
translation-type: tm+mt
source-git-commit: a172fc329a2f73b563690624dc361aefdcb5397e
workflow-type: tm+mt
source-wordcount: '1301'
ht-degree: 0%

---


# Indelingsontwerp {#layout-design}

XFA-formuliersjablonen of XDP&#39;s zijn de sjablonen voor:

* [Letters](/help/forms/using/create-letter.md)
* [Kanaal ](/help/forms/using/web-channel-print-channel.md#printchannel) voor  [interactieve communicatie afdrukken](/help/forms/using/interactive-communications-overview.md)

* Lay-outfragmenten

Een XDP is ontworpen in Adobe Forms Designer. Dit artikel bevat informatie over hoe u XDP&#39;s kunt ontwerpen voor het maken van effectieve overeenkomsten/interactieve communicatie, zoals waar u formuliervelden of doelgebieden wilt gebruiken en wanneer u lay-outfragmenten wilt gebruiken.

## Een lay-out maken voor letters of voor het afdrukkanaal {#creating-a-layout-for-letters-or-for-interactive-communications-print-channel} van Interactieve communicatie

Een lay-out bepaalt de grafische lay-out van een brief/drukkanaal van een Interactieve Mededeling. De indeling kan typische formuliervelden bevatten, zoals &quot;Adres&quot; en &quot;Referentienummer&quot;. Het bevat ook lege subformulieren die doelgebieden aangeven. Maak de indeling in de formulierontwerper en wanneer deze is voltooid, uploadt de Application Specialist de indeling naar AEM server. Van daar, kunt u de lay-out selecteren wanneer het creëren van een correspondentiesjabloon of een drukkanaal van een Interactieve Mededeling.

![Designer: een lay-out maken](assets/claimsubrogationlayout.png)

Ga als volgt te werk om lay-outs voor letters/drukkanaal van Interactieve Mededelingen tot stand te brengen:

1. Analyseer de lay-out en bepaal de inhoud die over alle pagina&#39;s wordt herhaald; De koptekst en voettekst van de pagina passen meestal in deze categorie. Deze inhoud wordt op master layoutpagina&#39;s geplaatst. De resterende inhoud gaat naar de tekstpagina&#39;s van de layout. In een beleidsjasje, kunnen het embleem en bedrijfadres aan master paginakop en footer worden toegevoegd. Bericht van annulering gebruikt bijvoorbeeld dezelfde indeling.
1. Teken bij het ontwerpen van de tekstpagina&#39;s de pagina-inhoud op in secties. Elke sectie is ontworpen als een subformulier dat is ingesloten in de indeling zelf of als een fragmentindeling. Als de sectie tabel bevat, modelleert u de sectie als een lay-outfragment.
1. Een lay-out kan als volgt worden ontworpen:

   1. Maak elke sectie als een afzonderlijk subformulier dat alle elementen van de sectie bevat.
   1. Elk subformulier voor secties onderliggend maken van hetzelfde bovenliggende subformulier. De indeling van het bovenliggende subformulier is zo ingesteld dat de secties hieronder kunnen worden verplaatst als grote gegevens in vorige secties worden samengevoegd.
   1. Sectie Primaire verblijfplaats kan ook in andere indelingen worden hergebruikt. Maak het als een fragmentlay-out.
   1. Sectie Aanvullende interessdetails bevatten slechts twee elementen die onder elkaar zijn geplaatst, kunnen grote gegevens bevatten en zijn ontworpen als stroominhoud.
   1. Andere secties bevatten elementen op specifieke posities, zodat ze zijn ontworpen als gepositioneerde indeling.
   1. Een sectie onderverdelen in subformulieren als de sectie elementen op specifieke posities bevat, en deze elementen grote hoeveelheden gegevens bevatten. Rangschik de subformulieren vervolgens om het gewenste gedrag te bereiken.
   1. Voor de sectie Primaire woonplaats voegt u een plaatsaanduiding als doelgebied toe. Deze tijdelijke aanduiding is gebonden aan een fragment voor de primaire verblijfplaats op het moment dat er een letter/interactieve communicatie wordt ontworpen.
   1. Upload de lay-out (en het eventuele fragment dat de lay-out gebruikt) naar de AEM Forms-server.

## Schema {#using-schema} gebruiken

U kunt een schema in een lay-out- of lay-outfragment gebruiken, maar het is niet verplicht. Als u een schema gebruikt, zorg het volgende ervoor:

1. Layout en alle fragmentlay-outs die in een brief/Interactieve Communicatie worden gebruikt gebruiken het zelfde schema zoals de brief/Interactieve Communicatie.
1. Alle velden die moeten worden gevuld met gegevens, zijn gebonden aan het schema.

## Relateerbare velden {#creating-relatable-fields} maken

Standaard worden alle velden beschouwd als relatief ten opzichte van verschillende andere gegevensbronnen. Als uw layout velden bevat die niet kunnen worden vergeleken met een gegevensbron, geeft u het veld een naam met het achtervoegsel &quot;_int&quot; (internal); bijvoorbeeld pageCount_int.

Een relatable veld moet:

* een XFA &lt;field> of &lt;exclGroup> zijn
* hebben een XFA-bindingsverwijzing
* als het een &lt;exclGroup> is, moet het ten minste één onderliggend keuzerondje hebben; anders kan het waardetype niet worden bepaald

Een relatable veld moet:

* hebben een naam

Een relatable veld mag niet:

* Een achtervoegsel &quot;_int&quot; in de naam opnemen
* hebben binding ingesteld als &quot;none&quot;
* een onderliggend element zijn van een &lt;exclGroup>-element

Zolang een relatable gebied aan de hierboven beschreven criteria voldoet, kan het op om het even welke plaats en bij om het even welke het nesten diepte in de lay-out zijn. U kunt relatable gebieden binnen master pagina&#39;s gebruiken.

De lay-outconfiguratie van velden is flexibeler dan doelgebiedsubformulieren; deze zijn echter gekoppeld aan één waardetype. U kunt een veld groter maken of instellen op een vaste breedte en hoogte, enzovoort. Het opgeloste module of regelresultaat wordt in het veld geduwd.

## Bepalen wanneer subformulieren en tekstvelden worden gebruikt {#deciding-when-to-use-subforms-and-text-nbsp-fields}

Gebruik een subformulier als u meerdere moduleinhoud wilt vastleggen in een verticaal-stroomindeling (meerdere alinea&#39;s of afbeeldingen) van boven naar beneden. In uw indeling moet rekening worden gehouden met het feit dat het subformulier in hoogte wordt vergroot om de inhoud ervan te kunnen bevatten. Als u er niet zeker van kunt zijn dat de lengte van de inhoud die aan het subformulier/doel is gekoppeld nooit de ruimte overschrijdt die voor het subformulier is gereserveerd in de indeling, maakt u het subformulier als onderliggend subformulier in een container met stroomsubformulieren. Dit proces zorgt ervoor dat indelingsobjecten onder het subformulier naar beneden stromen naarmate het subformulier groter wordt.

Gebruik een veld als u gegevens uit de module of gegevenswoordenboekelementen wilt vastleggen in het schema van uw layout (omdat velden zijn gebonden aan gegevens) of als u moduleinhoud wilt weergeven op een master pagina. Houd er rekening mee dat de inhoud van een master pagina niet kan doorlopen met inhoud van de tekstpagina. Zorg er dus voor dat het afbeeldingsveld wordt gebruikt als een koptekstlogo. Deze tabel bevat meer criteria om te bepalen wanneer een subformulier of een veld in een indeling moet worden gebruikt.

<table> 
 <tbody> 
  <tr> 
   <td><p><strong>Een subformulier gebruiken wanneer</strong></p> </td> 
   <td><p><strong>Een tekstveld gebruiken wanneer</strong></p> </td> 
  </tr> 
  <tr> 
   <td><p>Het bevat een combinatie elementen, zoals een Achternaam en Voornaam</p> </td> 
   <td><p>Het bevat één element, zoals een Aantal van het Beleid.</p> </td> 
  </tr> 
  <tr> 
   <td><p>Dit omvat meerdere alinea's</p> </td> 
   <td><p>Tekst is omwikkeld en uitgevuld</p> </td> 
  </tr> 
  <tr> 
   <td><p>Herhalende, optionele en voorwaardelijke gegevensgroepen zijn gebonden aan subformulieren om het risico van ontwerpfouten te beperken die kunnen optreden als scripts worden gebruikt om dezelfde resultaten te bereiken</p> </td> 
   <td><p>Elementen zoals het logo en het adres van uw organisatie worden weergegeven op alle pagina's van een brief/interactieve communicatie. In dit geval maakt u formuliervelden voor deze elementen en plaatst u deze op de master pagina. Als u de veldbinding instelt op Geen gegevensbinding, worden de velden Geen weergegeven als relateerbare velden in de Letter/Interactive Communication Editor. Als u een bepaald type inhoud aan deze velden wilt koppelen, moeten deze gebonden zijn.</p> <p>Als uw bedrijfsadres meer dan één lijn van gegevens bevat, gebruik tekstgebied met de "Meerdere Lijnen van de Toestaan"optie om het adres op de lay-out te vertegenwoordigen.</p> <p>Als het gegevenstype van een tekstveld is ingesteld op onbewerkte tekst, wordt de onbewerkte tekstversie van de module-uitvoer gebruikt in plaats van de versie met tekstopmaak (alle opmaak wordt genegeerd). Als u de opmaak wilt behouden, stelt u het gegevenstype van het tekstveld in op RTF-tekst.</p> </td> 
  </tr> 
  <tr> 
   <td><p>Tekst loopt over</p> </td> 
   <td><p>Tekstvelden en afbeeldingsvelden worden gebruikt op master pagina's. Master pagina's kunnen subformulieren niet gebruiken als doelgebieden.</p> </td> 
  </tr> 
  <tr> 
   <td><p>Objecten worden gegroepeerd en ingedeeld zonder dat het subformulier wordt gebonden aan een gegevenselement</p> </td> 
   <td><p> </p> </td> 
  </tr> 
  <tr> 
   <td><p>Het subformulier bevat een tekstveld. Het subformulier kan groter worden en andere objecten eronder in de indeling niet overschrijven.</p> </td> 
   <td><p>U hebt eenvoudige toegang tot de gegevens nodig tijdens het postproces.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Herhalende elementen instellen {#setting-up-repetitive-elements}

Wanneer elementen zoals het logo en het adres van uw organisatie op alle pagina&#39;s van een brief/Interactieve Mededeling verschijnen, creeer vormgebieden voor die elementen en plaats hen op de master pagina. Gebruik de binding Naam (veldnaam) voor deze velden.

## De renderindeling van de server opgeven {#specify-the-server-nbsp-render-format}

Gebruik de serverrenderindeling van de indeling naar dynamisch XML-formulier; anders, kunnen om het even welke brieven/Interactieve Mededelingen die op deze lay-out worden gebaseerd niet correct teruggeven. Standaard wordt de indeling voor het renderen van de server in Forms Designer ingesteld op Dynamisch XML-formulier. U zorgt ervoor dat de juiste indeling wordt gebruikt:

* Klik in Designer op **[!UICONTROL File > Form Properties > Default]** en controleer of de instelling voor PDF renderen/indeling is ingesteld op Dynamisch XML-formulier.

