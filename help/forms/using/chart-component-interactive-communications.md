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
translation-type: tm+mt
source-git-commit: f86765084981cda1e255834bf83be0ff8a7a2a02
workflow-type: tm+mt
source-wordcount: '2391'
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

## Voeg en vorm grafiek in een Interactieve Communicatie toe {#add-and-configure-chart-in-an-interactive-communication}

Voltooi de volgende stappen om een grafiek aan een Interactieve Mededeling toe te voegen:

1. Sleep vanuit de component Components in het AEM zijpaneel de component Chart in een van de volgende vormen van afdrukken of webkanaal van een interactieve communicatie:

   * Kanaal afdrukken: Doelgebied en afbeeldingsveld
   * Webkanaal: Deelvenster en Doelgebied

   De gelaten vallen component van de Grafiek, leidt tot placeholder voor een grafiek.

1. Tik de grafiekcomponent in de Interactieve Communicatie redacteur en van de toolbar van de Component uitgezocht **[!UICONTROL Configure (]** configure_icon ![](assets/configure_icon.png)).

   De zijbalk Eigenschappen wordt weergegeven met de eigenschappen Standaard van het diagram in de focus.

   ![Basiseigenschappen van een lijntekstdiagram in een afdrukkanaal](assets/chart_basicproperties.png)
   **Afbeelding:** *Basiseigenschappen van een lijntekstdiagram in een afdrukkanaal*

   ![Basiseigenschappen van een lijntekstdiagram in een webkanaal](assets/basicpropertieswebchannel.png)
   **Afbeelding:** *Basiseigenschappen van een lijntekstdiagram in een webkanaal*

1. Configureer de basiseigenschappen van het diagram voor afdrukkanaal en webkanaal. Naast de algemene eigenschappen zijn er eigenschappen die specifiek zijn voor afdrukken, webkanalen en het diagramtype.

   * **[!UICONTROL Name]**: Naam van het grafiekobject. De naam van de grafiek die u hier specificeert verschijnt niet in de grafiekoutput maar in regels wordt gebruikt om naar de grafiek te verwijzen.
   * **[!UICONTROL Chart Type]**: Geef het diagramtype op: Schijf, Kolom, Donut, Lijn, Lijn en Punt, Punt, of Gebied.
   * **[!UICONTROL Hide Object]**: Selecteer deze optie om het diagram in de uiteindelijke uitvoer te verbergen.
   * Geef het volgende op voor **[!UICONTROL x-axis]** en **[!UICONTROL y-axis]**:

      * **[!UICONTROL Title]**: Geef de titels voor de X- en Y-as op die moeten worden weergegeven in de interactieve communicatie.
      * **[!UICONTROL Data Model Object *]**: Blader door gegevensmodelobjecten voor de X- en Y-as van het diagram en selecteer deze in het formuliergegevensmodel dat u tijdens het maken van de interactieve communicatie hebt opgegeven. Kies twee eigenschappen voor verzamel-/arraytype van hetzelfde bovenliggende gegevensmodelobject die van betekenis zijn ten opzichte van elkaar om te plotten op de X- en Y-as van een grafiek.
      * **[!UICONTROL Function]**: Als u statistische functies wilt gebruiken om de waarden op de as te berekenen, selecteert u functie voor de X-/Y-as. Voor meer informatie over functies, zie de functies van het [Gebruik in grafiek](#usefunction) en [Voorbeeld 2: Toepassing van de som en de gemiddelde functies in een lijngrafiek](#applicationsumfrequency).

   >[!NOTE]
   >
   >Voor een afdrukkanaal moet het gegevensmodelobject dat u koppelt op de X-as van het type Number, String of Date zijn. Op de Y-as moet het gegevensmodelobject dat u koppelt van het type Number zijn. U wordt aangeraden de rechterlegenda in het afdrukkanaal te gebruiken.

   Voor meer informatie over grafiekeigenschappen, zie [Basis eigenschappen in grafieken](#basicpropertiescharts).

1. (Alleen kanaal afdrukken) Geef in de Instellingen van de agent op of de agent dit diagram moet gebruiken. Als deze **[!UICONTROL t Is Mandatory For the Agent To Use This Chart]** optie niet wordt geselecteerd, kan de agent het oogpictogram voor de grafiek op het lusje van de Inhoud van de UI van de Agent tikken om de grafiek te tonen/te verbergen.

   ![chart_agentproperties](assets/chart_agentproperties.png)

1. Tik op de zijbalk Eigenschappen op ![done_icon](assets/done_icon.png).

   Geef een voorvertoning weer om de weergave en de gegevens van het diagram weer te geven. Keer terug om de eigenschappen van de grafiek aan te passen, indien nodig.

1. Ga terug naar het aanbrengen van andere veranderingen in de Interactieve Mededeling.

## Voorbeeld 1: Uitvoer van diagram in afdruk en web {#chartoutputprintweb}

Op het tabblad Standaard definieert u het type grafiek, de eigenschappen van het gegevensmodel van het bronformulier die gegevens bevatten, de labels die moeten worden getekend op de x-as en y-as van het diagram en eventueel de statistische functie die de waarden voor tekenen op het diagram berekent.

Laten we de minimaal vereiste informatie in basiseigenschappen in detail begrijpen, met behulp van een creditcardverklaring die is gegenereerd met een interactieve communicatie. Bedenk dat u een grafiek wilt produceren om de hoeveelheid verschillende uitgaven in de verklaring te schilderen. U wilt verschillende soorten grafieken voor druk en Weboutput van de Interactieve Communicatie gebruiken.

Hiervoor moet u het volgende opgeven:

* **[!UICONTROL Chart Type]** - in dit voorbeeld, Kolom voor het gedrukte kanaal en Donut voor het Webkanaal
* **[!UICONTROL Data Model Objects]** als bron voor de X- en Y-as van het diagram - in dit voorbeeld, de hoeveelheid transacties voor de X-as en de naam van de kosten voor de Y-as
* **[!UICONTROL Title]** voor de X- en Y-as (alleen in dit voorbeeld voor Kolomtypeschema in het afdrukkanaal) - in dit voorbeeld Hoeveelheid ($) voor de X-as en Uitgaven voor de Y-as.
* **[!UICONTROL Label Direction]** (alleen in dit voorbeeld voor Kolomtypeschema in het afdrukkanaal) - in dit voorbeeld `Tilt Left`

* **[!UICONTROL Tooltip]** om met de muis boven een uitgave weer te geven (alleen webkanaal) - in dit voorbeeld `${x}: $ ${y}`, dat wordt weergegeven als `[Expense Label: $ Amount]` (Voorbeeld: Bezoek themapark: $ 315)

![De grafiek van de kolom in de drukoutput van een Interactieve Communicatie](assets/chartprintchannel.png)**Cijfer:** *Kolomdiagram in de afdrukuitvoer van een interactieve communicatie*

**A.** Y-as - Hoeveelheid opgehaald uit de eigenschap van het formuliergegevensmodel en de eigenschap Titel ingesteld op Bedrag ($) **B.** Labelrichting van X-as ingesteld op Linkerkant **C.** X-as kantelen - beschrijving van kosten die is opgehaald uit de eigenschap van het gegevensmodel van het formulier en de eigenschap Titel ingesteld op Kosten

![Donut grafiek in de Weboutput van een Interactieve Communicatie](assets/chartwebchannel.png)**Cijfer:** *Donut grafiek in de Weboutput van een Interactieve Mededeling*

**A.** De eigenschap Binnenste straal van de donut wordt ingesteld op **B.** De eigenschap Legend tonen is geselecteerd en de eigenschap Positie van Legend is ingesteld op **C.** De knopinfo geeft de details van het item weer bij muisklik. De knopinfo wordt ingesteld op ${x}: ${y}

## Voorbeeld 2: Toepassing van de functies van de Som en van de Frequentie in een lijngrafiek {#applicationsumfrequency}

Door functies in een grafiek toe te passen, kunt u gegevens plotten die niet direct door het model van vormgegevens worden verstrekt. In dit voorbeeld, gebruiken wij een voorbeeld van de creditcardverklaring om te begrijpen hoe de functies van de Som en van de Frequentie op de grafiek kunnen worden toegepast.

![Het diagram van de lijn zonder een functie met drie &quot;Bed en Ontbijt&quot;transacties](assets/creditcarddatalinechartcopy.png)**Figuur:** *Regeldiagram zonder functie met drie &quot;Bed and Breakfast&quot;-transacties*

### Sum, functie {#sum-function}

U kunt de functie sum toepassen om waarden van meerdere instanties van dezelfde gegevenseigenschap op te tellen en deze slechts eenmaal weer te geven. In de volgende grafiek wordt bijvoorbeeld de functie Som toegepast op de Y-as om de hoeveelheid van de drie Bed- en Ontbijttransacties ($99,45, $78 en $12) op te tellen en slechts één transactie ($189,45) weer te geven.

De functie van de som kan grafiek nuttiger maken wanneer u som voor vele instanties van het zelfde gegevensbezit wilt sorteren en tonen.

![creditcardchartsumfunctioncopy](assets/creditcardchartsumfunctioncopy.png)

### Frequentiefunctie {#frequency-function}

De functie Frequentie retourneert het aantal waarden op de X- of Y-as voor een bepaalde waarde op de andere as. Met de toepassing van de Frequentiefunctie op de y-as (Amount/TransAmount) toont de grafiek aan dat er drie gevallen van Bed- en Ontbijttransacties zijn geweest en één geval van rest van de soorten transacties.

![creditcardchartfrequentiefunctie](assets/creditcardchartfrequencyfunctioncopy.png)

## Basiseigenschappen in grafieken {#basicpropertiescharts}

Op het tabblad Standaard kunt u de volgende eigenschappen configureren:

**Geef** een id voor het diagramelement een naam. De naam is niet zichtbaar op de grafiek maar helpt wanneer het verwijzen naar het element van andere componenten, manuscripten, en uitdrukkingen SOM.

**Titel (alleen kanaal Afdrukken)** Hiermee geeft u de titel van het diagram op.

**Het type** grafiek geeft het type diagram op dat u wilt genereren. De beschikbare opties zijn Schijf, Kolom, Donut, Bar (alleen webkanaal), Lijn, Lijn en Punt, Punt en Gebied. Zie voorbeeld 1 voor meer informatie: Uitvoer van diagram in afdruk en web.

**X-as > Titel** geeft de titel voor de x-as op.

**X-as > Gegevensmodelobject&amp;ast;** Geef de naam op van het gegevensmodelverzamelingsitem dat op de x-as moet worden getekend.

**X-as > Functie** Geeft de statistische/aangepaste functie op die moet worden gebruikt voor het berekenen van de waarden op de x-as. Voor meer informatie over functies, zie de functies van het Gebruik in grafiek en Voorbeeld 2: Toepassing van de som en de gemiddelde functies in een lijngrafiek.

**X-as > Labelrichting** Richting van het label op het diagram in afdrukkanaal. Als u de richting van het label kiest als Aangepaste rotatie, wordt het veld Aangepaste rotatiehoek (graden) weergegeven. In het veld Aangepaste rotatiehoek (graden) kunt u een rotatiehoek kiezen in stappen van 15 graden.

**Y-as > Titel** geeft de titel voor de y-as op.

**Y-as > Gegevensmodelobject&amp;ast;** Hiermee geeft u het verzamelitem van het formuliergegevensmodel op dat op de y-as moet worden getekend. In het kanaal van de Druk, zou het gegevensmodelvoorwerp voor de y-as van type Number moeten zijn.

**Y-as > Functie** Geeft de statistische/aangepaste functie op die moet worden gebruikt voor het berekenen van de waarden op y-as. Voor meer informatie over functies, zie de functies van het Gebruik in grafiek en Voorbeeld 2: Toepassing van de som en de gemiddelde functies in een lijngrafiek.

**Legenda** tonen Hiermee geeft u een legenda voor de taart of het donutdiagram weer als deze optie is ingeschakeld.

**Positie** legenda geeft de positie van de legenda ten opzichte van het diagram aan. De beschikbare opties zijn Rechts, Links, Boven en Onder.

**Hoogte (alleen kanaal afdrukken)** Hoogte van het diagram in pixels.

**Breedte (alleen kanaal afdrukken)** Breedte van het diagram in pixels.

>[!NOTE]
>
>U kunt de breedte van het diagram in het webkanaal bepalen met behulp van de stijllaag of door een thema toe te passen.

**Knopinfo (alleen webkanaal)** Hiermee geeft u de indeling op waarin de knopinfo wordt weergegeven bij de muisaanwijzer op een gegevenspunt in het diagram in het webkanaal. De standaardwaarde is \${x} (\${y}). Afhankelijk van het grafiektype, wanneer u de muis op een punt, bar, of plak in de grafiek richt, worden de variabelen \$ {x} en \$ {y} dynamisch vervangen met de overeenkomstige waarden op x-as en y-as en getoond in tooltip.

Laat het veld Knopinfo leeg als u knopinfo wilt uitschakelen. Deze optie is niet van toepassing op lijngrafieken en vlakgrafieken. Zie bijvoorbeeld [voorbeeld 1: Uitvoer van diagram in afdruk en web](#chartoutputprintweb).

**CSS-klasse (alleen webkanaal)** Geef de naam van een CSS-klasse op in het veld CSS-klasse om aangepaste opmaak toe te passen op het diagram.

**Verplicht pagina-einde voor (alleen kanaal afdrukken)** Selecteer deze optie om een verplicht pagina-einde toe te voegen vóór het diagram en het diagram boven op een nieuwe pagina te plaatsen.

**Verplicht pagina-einde na (alleen kanaal afdrukken)** Selecteer deze optie om een verplicht pagina-einde toe te voegen na het diagram en de inhoud van het diagram boven op een nieuwe pagina te plaatsen.

**Inspringing (alleen kanaal afdrukken)** Geef de inspringing van het diagram links op de pagina op.

**De diagram-specifieke configuraties** naast gemeenschappelijke configuraties, zijn de volgende grafiek-specifieke configuratie beschikbaar:

* **Binnenstraal**: beschikbaar voor Donut-grafieken om de straal (in pixel) van de binnencirkel in de grafiek te specificeren.
* **Lijnkleur**: beschikbaar voor de grafieken van de Lijn, van de Lijn en van het Punt, en van het Gebied om de hexadecimale waarde van de kleur voor de lijn in de grafiek te specificeren.
* **Puntkleur**: beschikbaar voor de grafieken van het Punt en van de Lijn en van het Punt om de hexadecimale waarde van de kleur voor de punten in de grafiek te specificeren.

* **Gebiedskleur**: beschikbaar voor vlakgrafieken om de hexadecimale waarde van de kleur voor het gebied onder de regel in het diagram op te geven.

## Functies in diagram gebruiken {#usefunction}

U kunt een grafiek vormen om statistische functies te gebruiken om waarden van de brongegevens voor het tekenen op de grafiek te berekenen. Door functies in een grafiek toe te passen, kunt u gegevens plotten die niet direct door het model van vormgegevens worden verstrekt.

Terwijl de component van de Grafiek met sommige ingebouwde functies komt, kunt u uw eigen functies schrijven en hen voor gebruik in de grafiekconfiguratie in het kanaal van het Web ter beschikking stellen.

![functioneel](assets/functionchart.png)

>[!NOTE]
>
>U kunt functies gebruiken om waarden voor de X- of Y-as in een grafiek te berekenen.

### Standaardfuncties {#default-functions}

De volgende functies zijn standaard beschikbaar met de component Chart:

**Gemiddeld (gemiddeld)** Geeft als resultaat het gemiddelde van de waarden op de X- of Y-as voor een bepaalde waarde op de andere as.

**Sum** Geeft als resultaat de som van alle waarden op de X- of Y-as voor een bepaalde waarde op de andere as.

**Maximum** Geeft als resultaat het maximum van de waarden op de X- of Y-as voor een bepaalde waarde op de andere as.

**Frequentie** Geeft als resultaat het aantal waarden op de X- of Y-as voor een bepaalde waarde op de andere as.

**Bereik** Geeft het verschil tussen het maximum en het minimum van de waarden op de X- of Y-as voor een bepaalde waarde op de andere as.

**Mediaan** Geeft de waarde die hogere en lagere waarden in de helft op de X- of Y-as scheidt voor een bepaalde waarde op de andere as.

**Minimum** Geeft als resultaat het minimum van de waarden op de X- of Y-as voor een bepaalde waarde op de andere as.

**Modus** retourneert de waarde die de meeste keren voorkomt op de X- of Y-as voor een bepaalde waarde op de andere as

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

1. Voeg de douanefunctie in de cliëntbibliotheek toe verbonden aan de relevante Interactieve Communicatie. Voor meer informatie, zie het [Vormen van de Submit actie](/help/forms/using/configuring-submit-actions.md) en het [Gebruiken van cliënt-zij Bibliotheken](/help/sites-developing/clientlibs.md).

1. Als u de aangepaste functie wilt weergeven in de vervolgkeuzelijst Functie, maakt u in CRXDe Lite een `nt:unstructured` knooppunt in de map apps met de volgende eigenschappen:

   * Eigenschap toevoegen `guideComponentType` met waarde als `fd/af/reducer`. (mandatory)
   * Voeg eigenschap toe `value` aan een volledig gekwalificeerde naam van de aangepaste JavaScript™-functie. (verplicht) en de waarde ervan instellen op de naam van de aangepaste functie, zoals Vermenigvuldigen.
   * Voeg eigenschap toe `jcr:description` met de waarde die u wilt weergeven als de naam van de aangepaste functie die wordt weergegeven in de vervolgkeuzelijst Functie. Bijvoorbeeld, **vermenigvuldigen**.
   * Voeg een eigenschap toe `qtip` met een waarde die een korte beschrijving van de aangepaste functie is. Deze verschijnt als knopinfo wanneer u de aanwijzer boven de functienaam in de vervolgkeuzelijst **Functie** plaatst.

1. Klik op Alles **** opslaan om de configuratie op te slaan.

De functie is nu beschikbaar voor gebruik in de Grafiek.