---
title: Het gebruiken van grafieken in Interactieve Mededelingen
seo-title: De component van de grafiek in Interactieve Mededelingen
description: 'Met diagrammen in een interactieve communicatie kunt u grote hoeveelheden informatie comprimeren tot een eenvoudig te analyseren en te begrijpen visuele indeling  '
seo-description: AEM Forms verstrekt een grafiekcomponent die u kunt gebruiken om grafieken in uw Interactieve Communicatie tot stand te brengen. Dit document verklaart basis en agentenconfiguraties van de grafiekcomponent.
uuid: dedd670c-030b-4497-bbcb-3ad935cebcda
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: interactive-communications
discoiquuid: 16c7e698-258d-4e63-9828-f538dc7d3294
feature: Interactieve communicatie
translation-type: tm+mt
source-git-commit: 75312539136bb53cf1db1de03fc0f9a1dca49791
workflow-type: tm+mt
source-wordcount: '2393'
ht-degree: 0%

---


# Het gebruiken van grafieken in Interactieve Mededelingen {#using-charts-in-interactive-communications}

Met diagrammen in een interactieve communicatie kunt u grote hoeveelheden informatie comprimeren tot een eenvoudig te analyseren en te begrijpen visuele indeling

Een grafiek of grafiek is een visuele weergave van gegevens. Het versleept grote hoeveelheden informatie in gemakkelijk-aan-begrijpelijke visuele formaat, toelatend de ontvangers van de Interactieve Mededeling om complexe gegevens beter te visualiseren, te interpreteren en te analyseren.

Terwijl het creëren van een Interactieve Communicatie, kunt u grafieken toevoegen om tweedimensionale gegevens van het de vormgegevensmodel van de Interactieve Communicatie visueel te vertegenwoordigen. Met de component Chart kunt u de volgende typen grafieken toevoegen en configureren:

* Schijf
* Kolom
* Donut
* Bar (alleen webkanaal)
* Lijn
* Lijn en punt
* Punt
* Gebied

## Grafiek toevoegen en configureren in een interactieve communicatie {#add-and-configure-chart-in-an-interactive-communication}

Voltooi de volgende stappen om een grafiek aan een Interactieve Mededeling toe te voegen:

1. Sleep vanuit de component Components in het AEM zijpaneel de component Chart in een van de volgende vormen van afdrukken of webkanaal van een interactieve communicatie:

   * Kanaal afdrukken: Doelgebied en afbeeldingsveld
   * Webkanaal: Deelvenster en Doelgebied

   De gelaten vallen component van de Grafiek, leidt tot placeholder voor een grafiek.

1. Tik op de diagramcomponent in de Interactieve Communication-editor en selecteer **[!UICONTROL Configure (]** ![configure_icon](assets/configure_icon.png) op de werkbalk Component).

   De zijbalk Eigenschappen wordt weergegeven met de eigenschappen Standaard van het diagram in de focus.

   ![Basiseigenschappen van een lijntekstdiagram in een afdrukkanaal](assets/chart_basicproperties.png)
   **Figuur:** *Basiseigenschappen van een lijntypegrafiek in drukkanaal*

   ![Basiseigenschappen van een lijntekstdiagram in een webkanaal](assets/basicpropertieswebchannel.png)
   **Figuur:** *Basiseigenschappen van een lijntypegrafiek in Webkanaal*

1. Configureer de basiseigenschappen van het diagram voor afdrukkanaal en webkanaal. Naast de algemene eigenschappen zijn er eigenschappen die specifiek zijn voor afdrukken, webkanalen en het diagramtype.

   * **[!UICONTROL Name]**: Naam van het grafiekobject. De naam van de grafiek die u hier specificeert verschijnt niet in de grafiekoutput maar in regels wordt gebruikt om naar de grafiek te verwijzen.
   * **[!UICONTROL Chart Type]**: Geef het diagramtype op: Schijf, Kolom, Donut, Lijn, Lijn en Punt, Punt, of Gebied.
   * **[!UICONTROL Hide Object]**: Selecteer deze optie om het diagram in de uiteindelijke uitvoer te verbergen.
   * Geef het volgende op voor **[!UICONTROL x-axis]** en **[!UICONTROL y-axis]**:

      * **[!UICONTROL Title]**: Geef de titels voor de X- en Y-as op die moeten worden weergegeven in de interactieve communicatie.
      * **[!UICONTROL Data Model Object *]**: Blader door gegevensmodelobjecten voor de X- en Y-as van het diagram en selecteer deze in het formuliergegevensmodel dat u tijdens het maken van de interactieve communicatie hebt opgegeven. Kies twee eigenschappen voor verzamel-/arraytype van hetzelfde bovenliggende gegevensmodelobject die van betekenis zijn ten opzichte van elkaar om te plotten op de X- en Y-as van een grafiek.
      * **[!UICONTROL Function]**: Als u statistische functies wilt gebruiken om de waarden op de as te berekenen, selecteert u functie voor de X-/Y-as. Zie [Functies in diagram](#usefunction) en [Voorbeeld 2 gebruiken voor meer informatie over functies: Toepassing van de som en de gemiddelde functies in een lijngrafiek](#applicationsumfrequency).

   >[!NOTE]
   >
   >Voor een afdrukkanaal moet het gegevensmodelobject dat u koppelt op de X-as van het type Number, String of Date zijn. Op de Y-as moet het gegevensmodelobject dat u koppelt van het type Number zijn. U wordt aangeraden de rechterlegenda in het afdrukkanaal te gebruiken.

   Voor meer informatie over grafiekeigenschappen, zie [Basiseigenschappen in grafieken](#basicpropertiescharts).

1. (Alleen kanaal afdrukken) Geef in de Instellingen van de agent op of de agent dit diagram moet gebruiken. Als de optie **[!UICONTROL t Is Mandatory For the Agent To Use This Chart]** niet wordt geselecteerd, kan de agent het oogpictogram voor de grafiek op het lusje van de Inhoud van de UI van de Agent tikken om de grafiek te tonen/te verbergen.

   ![chart_agentproperties](assets/chart_agentproperties.png)

1. Tik in de zijbalk Eigenschappen op ![done_icon](assets/done_icon.png).

   Geef een voorvertoning weer om de weergave en de gegevens van het diagram weer te geven. Keer terug om de eigenschappen van de grafiek aan te passen, indien nodig.

1. Ga terug naar het aanbrengen van andere veranderingen in de Interactieve Mededeling.

## Voorbeeld 1: Uitvoer van diagram in afdruk en web {#chartoutputprintweb}

Op het tabblad Standaard definieert u het type grafiek, de eigenschappen van het gegevensmodel van het bronformulier die gegevens bevatten, de labels die moeten worden getekend op de x-as en y-as van het diagram en eventueel de statistische functie die de waarden voor tekenen op het diagram berekent.

Laten we de minimaal vereiste informatie in basiseigenschappen in detail begrijpen, met behulp van een creditcardverklaring die is gegenereerd met een interactieve communicatie. Bedenk dat u een grafiek wilt produceren om de hoeveelheid verschillende uitgaven in de verklaring te schilderen. U wilt verschillende soorten grafieken voor druk en Weboutput van de Interactieve Communicatie gebruiken.

Hiervoor moet u het volgende opgeven:

* **[!UICONTROL Chart Type]** - in dit voorbeeld, Kolom voor het gedrukte kanaal en Donut voor het Webkanaal
* **[!UICONTROL Data Model Objects]** als bron voor de X- en Y-as van het diagram - in dit voorbeeld, de hoeveelheid transacties voor de X-as en de naam van de kosten voor de Y-as
* **[!UICONTROL Title]** voor de X- en Y-as (alleen in dit voorbeeld voor Kolomtypeschema in het afdrukkanaal) - in dit voorbeeld Hoeveelheid ($) voor de X-as en Uitgaven voor de Y-as.
* **[!UICONTROL Label Direction]** (alleen in dit voorbeeld voor Kolomtypeschema in het afdrukkanaal) - in dit voorbeeld  `Tilt Left`

* **[!UICONTROL Tooltip]** om met de muis boven een uitgave weer te geven (alleen webkanaal) - in dit voorbeeld  `${x}: $ ${y}`, dat als  `[Expense Label: $ Amount]` (Voorbeeld: Bezoek themapark: $ 315)

![Kolomdiagram in de afdrukuitvoer van een interactieve ](assets/chartprintchannel.png)
**CommunicationFigure:** *Kolomgrafiek in de afdrukuitvoer van een interactieve communicatie*

**A.** Y-as - Hoeveelheid opgehaald uit de eigenschap van het formuliergegevensmodel en de eigenschap Titel ingesteld op Bedrag ($)  **B.** Labelrichting van X-as ingesteld op Linkeras  **C.** X - Beschrijving van kosten opgehaald uit de eigenschap van het formuliergegevensmodel en de eigenschap Titel ingesteld op Kosten

![Donut grafiek in de Weboutput van een Interactieve ](assets/chartwebchannel.png)
**CommunicationFigure:** *Donut grafiek in de Weboutput van een Interactieve Mededeling*

**A.** De eigenschap Binnenste straal van de donut wordt ingesteld  **B.** De eigenschap Legenda tonen is geselecteerd en de eigenschap Positie van de Legenda wordt ingesteld op Rechts  **C.** Knopinfo geeft de details van het item weer bij muisklik - Knopinfo wordt ingesteld op ${x}: ${y}

## Voorbeeld 2: Toepassing van de functies van de Som en van de Frequentie in een lijngrafiek {#applicationsumfrequency}

Door functies in een grafiek toe te passen, kunt u gegevens plotten die niet direct door het model van vormgegevens worden verstrekt. In dit voorbeeld, gebruiken wij een voorbeeld van de creditcardverklaring om te begrijpen hoe de functies van de Som en van de Frequentie op de grafiek kunnen worden toegepast.

![Regeldiagram zonder functie met drie ](assets/creditcarddatalinechartcopy.png)
**transacties &quot;Bed en Ontbijt&quot;Afbeelding:** *Lijndiagram zonder functie met drie transacties &quot;Bed en Ontbijt&quot;*

### Som, functie {#sum-function}

U kunt de functie sum toepassen om waarden van meerdere instanties van dezelfde gegevenseigenschap op te tellen en deze slechts eenmaal weer te geven. In de volgende grafiek wordt bijvoorbeeld de functie Som toegepast op de Y-as om de hoeveelheid van de drie Bed- en Ontbijttransacties ($99,45, $78 en $12) op te tellen en slechts één transactie ($189,45) weer te geven.

De functie van de som kan grafiek nuttiger maken wanneer u som voor vele instanties van het zelfde gegevensbezit wilt sorteren en tonen.

![creditcardchartsumfunctioncopy](assets/creditcardchartsumfunctioncopy.png)

### Frequentiefunctie {#frequency-function}

De functie Frequentie retourneert het aantal waarden op de X- of Y-as voor een bepaalde waarde op de andere as. Met de toepassing van de Frequentiefunctie op de y-as (Amount/TransAmount) toont de grafiek aan dat er drie gevallen van Bed- en Ontbijttransacties zijn geweest en één geval van rest van de soorten transacties.

![creditcardchartfrequentiefunctie](assets/creditcardchartfrequencyfunctioncopy.png)

## Basiseigenschappen in grafieken {#basicpropertiescharts}

Op het tabblad Standaard kunt u de volgende eigenschappen configureren:

**** NameAn-id voor het grafiekelement. De naam is niet zichtbaar op de grafiek maar helpt wanneer het verwijzen naar het element van andere componenten, manuscripten, en uitdrukkingen SOM.

**Titel (alleen kanaal afdrukken)** Hiermee geeft u de titel van het diagram op.

**Diagram** typeHiermee geeft u het type diagram op dat u wilt genereren. De beschikbare opties zijn Schijf, Kolom, Donut, Bar (alleen webkanaal), Lijn, Lijn en Punt, Punt en Gebied. Zie voorbeeld 1 voor meer informatie: Uitvoer van diagram in afdruk en web.

**X-as >** TitleHiermee geeft u de titel voor de x-as op.

**X-as > Gegevensmodelobject&amp;ast;** Geef de naam op van het gegevensmodelverzamelingsitem dat moet worden getekend op de x-as.

**X-as >** FunctionGeeft de statistische/aangepaste functie op die moet worden gebruikt voor het berekenen van de waarden op de x-as. Voor meer informatie over functies, zie de functies van het Gebruik in grafiek en Voorbeeld 2: Toepassing van de som en de gemiddelde functies in een lijngrafiek.

**X-as >** Labelrichting van het label op het diagram in het afdrukkanaal. Als u de richting van het label kiest als Aangepaste rotatie, wordt het veld Aangepaste rotatiehoek (graden) weergegeven. In het veld Aangepaste rotatiehoek (graden) kunt u een rotatiehoek kiezen in stappen van 15 graden.

**Y-as >** TitelHiermee geeft u de titel voor de y-as op.

**Y-as > Gegevensmodelobject&amp;ast;** geeft het verzamelitem van het formuliergegevensmodel op dat moet worden getekend op de y-as. In het kanaal van de Druk, zou het gegevensmodelvoorwerp voor de y-as van type Number moeten zijn.

**Y-as >** FunctionGeeft de statistische/aangepaste functie op die moet worden gebruikt voor het berekenen van de waarden op y-as. Voor meer informatie over functies, zie de functies van het Gebruik in grafiek en Voorbeeld 2: Toepassing van de som en de gemiddelde functies in een lijngrafiek.

**Legenda tonenHiermee geeft u een legenda voor de taart of het donutdiagram weer als deze optie is ingeschakeld.** 

**Positie legendaGeeft de positie van de legenda** ten opzichte van het diagram aan. De beschikbare opties zijn Rechts, Links, Boven en Onder.

**Hoogte (alleen kanaal afdrukken)** Hoogte van het diagram in pixels.

**Breedte (alleen kanaal afdrukken)** Breedte van het diagram in pixels.

>[!NOTE]
>
>U kunt de breedte van het diagram in het webkanaal bepalen met behulp van de stijllaag of door een thema toe te passen.

**Knopinfo (alleen webkanaal)** Hiermee geeft u de indeling op waarin de knopinfo wordt weergegeven op de muis over een gegevenspunt in het diagram in het webkanaal. De standaardwaarde is \${x} (\${y}). Afhankelijk van het grafiektype, wanneer u de muis op een punt, bar, of plak in de grafiek richt, worden de variabelen \$ {x} en \$ {y} dynamisch vervangen met de overeenkomstige waarden op x-as en y-as en getoond in tooltip.

Laat het veld Knopinfo leeg als u knopinfo wilt uitschakelen. Deze optie is niet van toepassing op lijngrafieken en vlakgrafieken. Zie bijvoorbeeld [Voorbeeld 1: Uitvoer van diagram in afdruk en web](#chartoutputprintweb).

**CSS-klasse (alleen webkanaal)** Geef de naam van een CSS-klasse op in het CSS-klassenveld om aangepaste opmaak toe te passen op het diagram.

**Verplicht pagina-einde voor (alleen kanaal afdrukken)** Selecteer deze optie om een verplicht pagina-einde toe te voegen vóór het diagram en het diagram boven op een nieuwe pagina te plaatsen.

**Verplicht pagina-einde na (alleen kanaal afdrukken)** Selecteer deze optie om een verplicht pagina-einde toe te voegen na het diagram en de inhoud van het diagram boven op een nieuwe pagina te plaatsen.

**Inspringing (alleen kanaal afdrukken)** Geef de inspringing van het diagram links op de pagina op.

**Grafiekspecifieke** configuratiesNaast gemeenschappelijke configuraties, zijn de volgende grafiek-specifieke configuratie beschikbaar:

* **Binnenstraal**: beschikbaar voor Donut-grafieken om de straal (in pixel) van de binnencirkel in de grafiek te specificeren.
* **Lijnkleur**: beschikbaar voor de grafieken van de Lijn, van de Lijn en van het Punt, en van het Gebied om de hexadecimale waarde van de kleur voor de lijn in de grafiek te specificeren.
* **Puntkleur**: beschikbaar voor de grafieken van het Punt en van de Lijn en van het Punt om de hexadecimale waarde van de kleur voor de punten in de grafiek te specificeren.

* **Gebiedskleur**: beschikbaar voor vlakgrafieken om de hexadecimale waarde van de kleur voor het gebied onder de regel in het diagram op te geven.

## Functies in diagram {#usefunction} gebruiken

U kunt een grafiek vormen om statistische functies te gebruiken om waarden van de brongegevens voor het tekenen op de grafiek te berekenen. Door functies in een grafiek toe te passen, kunt u gegevens plotten die niet direct door het model van vormgegevens worden verstrekt.

Terwijl de component van de Grafiek met sommige ingebouwde functies komt, kunt u uw eigen functies schrijven en hen voor gebruik in de grafiekconfiguratie in het kanaal van het Web ter beschikking stellen.

![functioneel](assets/functionchart.png)

>[!NOTE]
>
>U kunt functies gebruiken om waarden voor de X- of Y-as in een grafiek te berekenen.

### Standaardfuncties {#default-functions}

De volgende functies zijn standaard beschikbaar met de component Chart:

**Gemiddeld (gemiddeld)** Geeft het gemiddelde van de waarden op de X- of Y-as voor een bepaalde waarde op de andere as.

**** SumRetourneert de som van alle waarden op de X- of Y-as voor een bepaalde waarde op de andere as.

**** MaximumRetourneert het maximum van de waarden op de X- of Y-as voor een bepaalde waarde op de andere as.

**** FrequencyHiermee wordt het aantal waarden op de X- of Y-as van een bepaalde waarde op de andere as geretourneerd.

**** RangeGeeft het verschil tussen het maximum en het minimum van de waarden op de X- of Y-as voor een bepaalde waarde op de andere as.

**** MedianRetourneert de waarde die hogere en lagere waarden in de helft op de X- of Y-as scheidt voor een bepaalde waarde op de andere as.

**** MinimumGeeft als resultaat het minimum van de waarden op de X- of Y-as voor een bepaalde waarde op de andere as.

**** ModeHiermee wordt de waarde geretourneerd waarvan de meeste instanties zich op de X- of Y-as bevinden voor een bepaalde waarde op de andere as

### Aangepaste functies in webkanaal {#custom-functions-in-web-channel}

Naast het gebruik van de standaardfuncties in grafieken, kunt u douanefuncties in JavaScript™ schrijven en hen ter beschikking stellen in de lijst van functies in de component van de Grafiek voor Webkanaal.

Een functie neemt een array of waarden en een categorienaam als invoer en retourneert een waarde. Bijvoorbeeld:

```
Multiply(valueArray, category) {
 var val = 1;
 _.each(valueArray, function(value) {
 val = val * value;
 });
 return val;
}
```

Zodra u een douanefunctie hebt geschreven, doe het volgende om het voor gebruik in de grafiekconfiguratie beschikbaar te maken:

1. Voeg de douanefunctie in de cliëntbibliotheek toe verbonden aan de relevante Interactieve Communicatie. Zie [De handeling Verzenden configureren](/help/forms/using/configuring-submit-actions.md) en [Client-Side Libraries](/help/sites-developing/clientlibs.md) gebruiken voor meer informatie.

1. Als u de aangepaste functie wilt weergeven in de vervolgkeuzelijst Functie, maakt u in CRXDe Lite een `nt:unstructured`-knooppunt in de map apps met de volgende eigenschappen:

   * Voeg eigenschap `guideComponentType` toe met waarde als `fd/af/reducer`. (mandatory)
   * Voeg eigenschap `value` toe aan een volledig gekwalificeerde naam van de aangepaste JavaScript™-functie. (verplicht) en de waarde ervan instellen op de naam van de aangepaste functie, zoals Vermenigvuldigen.
   * Voeg eigenschap `jcr:description` toe met de waarde die u wilt weergeven als de naam van de aangepaste functie die wordt weergegeven in de vervolgkeuzelijst Functie. Bijvoorbeeld **Vermenigvuldigen**.
   * Voeg eigenschap `qtip` toe met waarde die een korte beschrijving van de aangepaste functie zal zijn. Het verschijnt als tooltip wanneer het hangen van wijzer over de functienaam in **Functie** drop-down lijst.

1. Klik **sparen allen** om de configuratie te bewaren.

De functie is nu beschikbaar voor gebruik in de Grafiek.