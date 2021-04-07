---
title: Zoeken&amp toevoegen;amp;Functies promoveren op uw pagina
seo-title: Zoeken&amp toevoegen;amp;Functies promoveren op uw pagina
description: Integreer Zoeken&amp;Promote mogelijkheden op uw website, kunt u het &Zoeken gebruiken;amp;Promote componenten om functies aan uw pagina's toe te voegen, zoals trefwoordzoekopdracht, zoekresultaten, zoekactie en banners.
seo-description: Integreer Zoeken&amp;Promote mogelijkheden op uw website, kunt u het &Zoeken gebruiken;amp;Promote componenten om functies aan uw pagina's toe te voegen, zoals trefwoordzoekopdracht, zoekresultaten, zoekactie en banners.
uuid: 8831aa56-9d7f-44ca-9d32-5901bf762154
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: site-features
discoiquuid: 277d7e67-5778-48cb-89bb-29bcc734a485
exl-id: 69a1e149-8706-42a5-ab84-2ffcfd1ec3cc
translation-type: tm+mt
source-git-commit: bd94d3949f0117aa3e1c9f0e84f7293a5d6b03b4
workflow-type: tm+mt
source-wordcount: '1184'
ht-degree: 0%

---

# Search&amp;Promote toevoegen aan uw pagina {#adding-search-promote-features-to-your-page}

Als u Search&amp;Promote-mogelijkheden wilt integreren in uw website, gebruikt u de [!UICONTROL Search&Promote]-componenten om de volgende functies aan uw pagina&#39;s toe te voegen:

* Trefwoordzoekopdracht
* Pagina met zoekresultaten
* Zoekverfijning
* Banners

Merk op dat u de mogelijkheden van de Search&amp;Promote slechts kunt gebruiken als uw AEM beheerder hen heeft toegelaten. Zie [Integreren met Adobe Search&amp;Promote](/help/sites-administering/search-and-promote.md).

Facetten worden gevormd op de server van de Search&amp;Promote, zoals de informatie die elke component verstrekt. De volgende tabel bevat een korte beschrijving van elke component. De volgende secties verstrekken gedetailleerde informatie over hun gebruik.

<table> 
 <tbody> 
  <tr> 
   <th>component Search&amp;Promote</th> 
   <th>Beschrijving</th> 
  </tr> 
  <tr> 
   <td>Banners</td> 
   <td>Hiermee geeft u banneradvertenties weer. Banners worden geselecteerd op basis van gegevens die via Search&amp;Promote zijn verzameld.<br /> </td> 
  </tr> 
  <tr> 
   <td>Broodkruimels</td> 
   <td>Geeft het zoekwoord en de reeks filters weer die de gebruiker op de zoekresultaten heeft toegepast.</td> 
  </tr> 
  <tr> 
   <td>Selectievakje List-Facet</td> 
   <td>Een lijst met selectievakjes voor het selecteren van facetten voor het filteren van zoekresultaten.</td> 
  </tr> 
  <tr> 
   <td>Vervolgkeuzefactor</td> 
   <td>Een vervolgkeuzelijst met facetten voor het filteren van zoekresultaten.</td> 
  </tr> 
  <tr> 
   <td>Koppelingslijstfacet</td> 
   <td>Een lijst met facetkoppelingen voor het filteren van zoekresultaten.</td> 
  </tr> 
  <tr> 
   <td>Paginering</td> 
   <td>Hiermee regelt u het navigeren door pagina's met zoekresultaten.</td> 
  </tr> 
  <tr> 
   <td>Resultaten</td> 
   <td>Geeft de resultaten van een trefwoordzoekopdracht weer.</td> 
  </tr> 
  <tr> 
   <td>Zoeken</td> 
   <td>Hiermee voegt u een zoekveld aan de pagina toe.</td> 
  </tr> 
 </tbody> 
</table>

## De pagina {#creating-the-search-results-page} met zoekresultaten maken

Gebruik de console van Websites WCM om een pagina tot stand te brengen voor het tonen van onderzoeksresultaten. De resultaten van een zoekopdracht vanuit een zoekcomponent kunnen op deze pagina worden weergegeven als deze dezelfde Search&amp;Promote-service gebruikt.

De componenten waarmee gebruikers zoekresultaten kunnen bekijken, zijn Resultaten en Paginering. De **[!UICONTROL Results]** component heeft geen configureerbare eigenschappen op [!UICONTROL Edit] of [!UICONTROL Design] wijze. De component Resultaten geeft alleen de zoekresultaten weer, die koppelingen naar andere pagina&#39;s bevatten, en geeft het aantal resultaten voor het trefwoord Zoeken weer.

![srchresultscomp](assets/srchresultscomp.png)

Met de component **[!UICONTROL Pagination]** kunnen gebruikers door meerdere pagina&#39;s met zoekresultaten navigeren. De gebruiker kan het aantal pagina&#39;s zien, naar de volgende of vorige pagina gaan, een pagina selecteren om te openen, of alle resultaten op één pagina consolideren.

![semafoonlaag](assets/srchpagination.png)

U kunt de volgende componenteneigenschappen op [!UICONTROL Edit] wijze vormen om runtime gedrag te controleren:

* **[!UICONTROL Hide single result page]** - Selecteer deze optie om de besturingselementen voor paginanavigatie te verbergen wanneer de zoekopdracht op één pagina met resultaten wordt uitgevoerd.
* **[!UICONTROL Hide First/Last]** - Selecteer deze optie om te voorkomen dat gebruikers naar de eerste of laatste pagina met resultaten gaan.
* **[!UICONTROL Hide Previous/Next]** - Hiermee bepaalt u of gebruikers door resultatenpagina&#39;s kunnen navigeren ten opzichte van de huidige pagina.
* **[!UICONTROL Hide view all]** - Hiermee wordt bepaald of de gebruiker alle zoekresultaten op één pagina kan samenvoegen. Gewoonlijk maakt het verstrekken van gepagineerde gegevens efficiënter gebruik van servermiddelen. Selecteer deze optie als u wilt voorkomen dat grote gegevenssets in één antwoordbericht worden overgedragen.

## Filteren van resultaten op facetten {#enabling-the-filtering-of-results-by-facets} inschakelen

U kunt gebruikers toestaan om onderzoeksresultaten door facetten te filtreren. Met de componenten **[!UICONTROL Checkbox List Facet]**, **[!UICONTROL Dropdown Facet]** en **[!UICONTROL Link List Facet]** kunnen gebruikers een of meer facetten selecteren om te filteren. Wanneer u deze componenten gebruikt, moet u ook de **[!UICONTROL Breadcrumbs]**-component opnemen. Broodkruimels geven de huidige filters aan die worden gebruikt.

De **[!UICONTROL Checkbox List Facet]**, **[!UICONTROL Dropdown Facet]**, en **[!UICONTROL Link List Facet]** componenten hebben elk de volgende eigenschappen die u op **[!UICONTROL Edit]** wijze vormt:

* **[!UICONTROL Facet Name]** - De naam van het facet dat wordt gebruikt voor filters.

De component **[!UICONTROL Checkbox List Facet]** toont een lijst van facetten met een begeleidende checkbox. Gebruik een **[!UICONTROL Checkbox List Facet]** zodat gebruikers een subset van resultaten kunnen weergeven die items van meerdere facetten bevatten. Het merk is bijvoorbeeld geschikt omdat meerdere merken hetzelfde type product leveren.

Er wordt een selectievakje weergegeven voor elk facet dat aan een zoekresultaat is gekoppeld. Wanneer een gebruiker een selectievakje selecteert, wordt de pagina opnieuw geladen met een bijgewerkte resultatenset. Alle selectievakjes blijven op de pagina aanwezig, zodat klanten op elk gewenst moment facetten aan het filter kunnen toevoegen of eruit kunnen verwijderen:

![sandpcheckboxComp](assets/sandpcheckboxcomp.png)

Met de component **[!UICONTROL Dropdown Facet]** kunnen klanten een facetitem in een vervolgkeuzelijst selecteren. Deze component is handig wanneer u wilt dat klanten zich tegelijk op één facetitem richten. Bijvoorbeeld, is het facet van het Departement aangewezen voor het toelaten van klanten om productonderzoeken door geslacht te beperken. John zoekt naar *jeans* en filtert dan op de afdeling van Mannen.

De vervolgkeuzelijst wordt gevuld met de facetten die aan alle zoekresultaten zijn gekoppeld. Als u een item in de vervolgkeuzelijst selecteert, wordt de pagina opnieuw geladen met een bijgewerkte resultatenset. De punten in de drop-down lijst veranderen niet zodat de klanten van facet aan facet op elk ogenblik kunnen schakelen.

![sandpdropdowndepartement](assets/sandpdropdowndepartment.png)

Met de component **[!UICONTROL Link List Facet]** kunnen klanten hun focus geleidelijk beperken tot items die onder meerdere facetleden of facetten zijn gecategoriseerd.

De leden van Facet verschijnen als lijst van verbindingen. De tekst van elke koppeling is de naam van een facetlid dat is gekoppeld aan de huidige zoekresultaten. Wanneer een klant op een facetkoppeling klikt, wordt de pagina opnieuw geladen en wordt een subset van de zoekresultaten weergegeven. De lijst met koppelingen wordt dienovereenkomstig bijgewerkt, zodat de focus nog kleiner wordt.

![sandplinklistcomp](assets/sandplinklistcomp.png)

De koppelingen in de lijst veranderen ook wanneer een filter wordt toegepast vanuit een ander type component [!UICONTROL Search&Promote]. Het gebruik van meerdere typen filtercomponenten kan effectieve filtercombinaties opleveren.

Met de component **[!UICONTROL Breadcrumbs]** kunnen klanten de filters zien die momenteel op zoekresultaten worden toegepast, in de volgorde waarin ze zijn toegepast. Klanten kunnen op de items in de broodkruimel klikken om terug te keren naar die filtercombinatie.

![sandpbreadcrumbcomp](assets/sandpbreadcrumbcomp.png)

U kunt de volgende eigenschappen voor Breadcrubs op Edit wijze vormen om de blik van de component aan te passen:

* **[!UICONTROL Delimiter]** - Definieer de teken- of tekentekenreeks die moet fungeren als scheidingsteken tussen elke breadcrumb. In het veld Scheidingsteken worden alle tekenreeksen als invoer geaccepteerd. De standaardinstelling is: &quot;>&quot; (zonder aanhalingstekens)
* **[!UICONTROL Trailing Delimiter]** - Definieer een teken- of tekentekenreeks die aan het einde van de broodkruimels moet worden weergegeven. In het veld Sluitingsscheidingsteken worden alle tekens als invoer geaccepteerd. De standaardinstelling voor deze optie is &quot;leeg&quot; (er wordt dus niets weergegeven aan het einde van de regel voor het doorgeven van de inhoud)

## Zoekvakken {#adding-search-boxes} toevoegen

Met de component **[!UICONTROL Search]** kunnen klanten trefwoordzoekopdrachten uitvoeren. Voeg componenten van het Onderzoek aan elke pagina toe waar u toegang tot het zoeken wilt verlenen.

Vorm de volgende eigenschappen op **[!UICONTROL Edit]** wijze om runtime gedrag te controleren:

* **[!UICONTROL Result Page Path]** - Het pad naar de pagina waarop de zoekresultaten worden weergegeven.
* **[!UICONTROL Enable Auto-Complete]** - Selecteer deze optie om voorgestelde zoektrefwoorden weer te geven wanneer de klant in het zoekvak begint te typen.

![zandzoekopdracht](assets/sandpsearchcomp.png)

## banners {#adding-banners} toevoegen

De component **[!UICONTROL Banners]** geeft banneradvertenties weer volgens de zoekopdrachten van de klant in de Search&amp;Promote. De logica op de zoek&amp;vervangingsserver bepaalt welke banner moet worden weergegeven. Een zoekopdracht op spijkerbroeken kan bijvoorbeeld tot gevolg hebben dat een modebanner wordt weergegeven. Door te filteren op de afdeling Mannen kan de keuze van de banner verder worden verfijnd.

De **[!UICONTROL Banners]** component verstrekt één configureerbare bezit genoemd **[!UICONTROL Banner Area]**. Selecteer in de modus **[!UICONTROL Edit]** een van de eigenschapswaarden om op te geven hoe de banner wordt weergegeven. De service Search&amp;Promote bepaalt de lijst met waarden die u kunt selecteren.

## Voorbeeld van Search&amp;Promote-zoekpagina {#example-search-promote-search-page}

Dit diagram toont de componenten die aan een pagina worden toegevoegd om tot de volledig-functionele hieronder Search&amp;Promote resultatenpagina te leiden.

![1328213789109](assets/1328213789109.png) ![sandbox-voorbeeld](assets/sandppageexample.png)
