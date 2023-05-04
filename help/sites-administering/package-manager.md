---
title: Werken met pakketten
seo-title: How to Work With Packages
description: Leer de basisbeginselen van het werken met pakketten in AEM.
seo-description: Learn the basics of working with packages in AEM.
uuid: e9eb4f88-9df6-4019-92e0-2aafcffe1aab
contentOwner: Chiradeep Majumdar
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: content
content-type: reference
discoiquuid: 8e568c59-5455-422f-94a6-baf6d2aae070
exl-id: eebc10fa-1d49-4797-a9e6-b6615bfe0173
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '4057'
ht-degree: 0%

---

# Werken met pakketten{#how-to-work-with-packages}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Pakketten maken het importeren en exporteren van inhoud in de opslagplaats mogelijk. U kunt bijvoorbeeld pakketten gebruiken om nieuwe functionaliteit te installeren, inhoud tussen instanties over te brengen, en een back-up van inhoud in de opslagplaats te maken.

Pakketten kunnen op de volgende pagina&#39;s worden geopend en/of onderhouden:

* [Pakketbeheer](#package-manager), die u gebruikt om de pakketten in uw lokale AEM te beheren.

* [Pakket delen](#package-share), een gecentraliseerde server die zowel openbare pakketten als privé aan uw bedrijf houdt. De openbare pakketten kunnen hotfixes, nieuwe functionaliteit, documentatie, enz. bevatten.

U kunt pakketten overbrengen tussen de Manager van het Pakket, het Aandeel van het Pakket, en uw dossiersysteem.

## Wat zijn pakketten? {#what-are-packages}

Een pakket is een gecomprimeerd bestand met opslagplaats-inhoud in de vorm van een serialisatie van het bestandssysteem (de zogenaamde &#39;vault&#39;-serienummering). Dit biedt een eenvoudig te gebruiken en te bewerken weergave van bestanden en mappen.

Pakketten bevatten inhoud, zowel pagina-inhoud als projectgerelateerde inhoud, die met filters is geselecteerd.

Een pakket bevat ook vault meta-informatie, met inbegrip van de filterdefinities en de informatie van de de invoerconfiguratie. Extra inhoudseigenschappen (die niet worden gebruikt voor het uitpakken van pakketten) kunnen in het pakket worden opgenomen, zoals een beschrijving, een visuele afbeelding of een pictogram. deze eigenschappen zijn uitsluitend bestemd voor de consument van het inhoudspakket en voor informatieve doeleinden .

>[!NOTE]
>
>Pakketten vertegenwoordigen de huidige versie van de inhoud op het moment dat het pakket wordt gemaakt. Ze bevatten geen vorige versies van de inhoud die AEM in de opslagplaats bewaart.

U kunt de volgende handelingen uitvoeren op of met pakketten:

* Nieuwe pakketten maken; pakketinstellingen en -filters naar wens definiëren
* Voorvertoning van inhoud van pakket (vóór maken)
* Pakketten maken
* Pakketgegevens weergeven
* Pakketinhoud weergeven (na maken)
* De definitie van bestaande pakketten wijzigen
* Bestaande pakketten opnieuw samenstellen
* Pakketten terugbrengen
* Pakketten downloaden van AEM naar uw bestandssysteem
* Pakketten van uw dossiersysteem in uw lokale AEM instantie uploaden
* Inhoud van pakket valideren vóór installatie
* Een droge runtime installeren
* Pakketten installeren (AEM installeert pakketten niet automatisch na het uploaden)
* Pakketten verwijderen
* Download pakketten, zoals hotfixes, uit de bibliotheek van het Aandeel van het Pakket
* Pakketten uploaden naar het bedrijf-interne gedeelte van de bibliotheek van het Aandeel van het Pakket

## Pakketgegevens {#package-information}

Een pakketdefinitie bestaat uit verschillende soorten informatie:

* [Pakketinstellingen](#package-settings)
* [Pakketfilters](#package-filters)
* [Schermafbeeldingen verpakken](#package-screenshots)
* [Pakketpictogrammen](#package-icons)

### Pakketinstellingen {#package-settings}

U kunt een verscheidenheid van de Montages van het Pakket uitgeven om aspecten zoals de pakketbeschrijving, verwante insecten, gebiedsdelen en leveranciersinformatie te bepalen.

De **Pakketinstellingen** is beschikbaar via **Bewerken** knop wanneer [maken](#creating-a-new-package) of [bewerken](#viewing-and-editing-package-information) een pakket en bevat drie tabbladen voor configuratie. Nadat u wijzigingen hebt aangebracht, klikt u op **OK** om deze op te slaan.

![packagesedit](assets/packagesedit.png)

| **Veld** | **Beschrijving** |
|---|---|
| Naam | De naam van het pakket. |
| Groep | De naam van de groep waaraan het pakket moet worden toegevoegd, voor het ordenen van pakketten. Typ de naam van een nieuwe groep of selecteer een bestaande groep. |
| Versie | Tekst die voor de aangepaste versie moet worden gebruikt. |
| Beschrijving | Een korte beschrijving van het pakket. U kunt markeringen voor HTML gebruiken voor opmaak. |
| Miniatuur | Het pictogram dat bij de pakketvermelding wordt weergegeven. Klik op Bladeren om een lokaal bestand te selecteren. |

![chlimage_1-344](assets/chlimage_1-344.png)

<table> 
 <tbody> 
  <tr> 
   <th><strong>Veld</strong></th> 
   <th><strong>Beschrijving</strong></th> 
   <th><strong>Indeling/Voorbeeld</strong></th> 
  </tr> 
  <tr> 
   <td>Naam</td> 
   <td>De naam van de provider.</td> 
   <td><em>AEM Geometrixx<br /> </em></td> 
  </tr> 
  <tr> 
   <td>URL</td> 
   <td>URL van de provider.</td> 
   <td><em>https://www.aem-geometrixx.com</em></td> 
  </tr> 
  <tr> 
   <td>Koppeling</td> 
   <td>Pakketspecifieke koppeling naar een providerpagina.</td> 
   <td><em>https://www.aem-geometrixx.com/mypackage.html</em></td> 
  </tr> 
  <tr> 
   <td>Vereisten<br /> </td> 
   <td> 
    <ul> 
     <li>Beheerder: Selecteer wanneer het pakket alleen kan worden geïnstalleerd door een account met beheerdersrechten.</li> 
     <li>Opnieuw starten: Selecteer wanneer de server opnieuw moet worden gestart nadat het pakket is geïnstalleerd.</li> 
    </ul> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Wisselstroomverwerking</td> 
   <td><p>Geef op hoe de toegangsbeheerinformatie die in het pakket is gedefinieerd, wordt verwerkt wanneer het pakket wordt geïmporteerd:</p> 
    <ul> 
     <li><strong>Negeren</strong></li> 
     <li><strong>Overschrijven</strong></li> 
     <li><strong>Samenvoegen</strong></li> 
     <li><strong>Wissen</strong></li> 
     <li><strong>MergePreserve</strong></li> 
    </ul> <p>De standaardwaarde is <strong>Negeren</strong>.</p> </td> 
   <td> 
    <ul> 
     <li><strong>Negeren</strong> - behoud ACLs in de bewaarplaats</li> 
     <li><strong>Overschrijven</strong> - overschrijf ACLs in de bewaarplaats</li> 
     <li><strong>Samenvoegen</strong> - voeg beide reeksen ACLs samen</li> 
     <li><strong>Wissen</strong> - duidelijke ACLs</li> 
     <li><strong>MergePreserve</strong> - Voeg toegangsbeheer in de inhoud met die samen van het pakket door de ingangen van de toegangscontrole van hoofden toe te voegen niet aanwezig in de inhoud wordt voorzien</li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

![pakketafhankelijkheden](assets/packagesdependencies.png)

| **Veld** | **Beschrijving** | **Indeling/Voorbeeld** |
|---|---|---|
| Getest met | De productnaam en versie van dit pakket zijn bedoeld voor of zijn compatibel met. | *AEM6* |
| Opgeloste problemen | Een tekstveld waarin u details kunt weergeven van bugs die zijn gecorrigeerd voor dit pakket. Vermeld elke bug op een aparte regel. | Overzicht van bug-nr |
| Afhankelijk van | Hiermee geeft u informatie over afhankelijkheden weer die moet worden gerespecteerd wanneer andere pakketten nodig zijn om het huidige pakket op de verwachte manier te laten uitvoeren. Dit veld is belangrijk bij het gebruik van hotfixes. | groupId:name:versie |
| Vervangen | Een lijst met vervangen pakketten die door dit pakket worden vervangen. Controleer vóór de installatie of dit pakket alle benodigde inhoud uit de verouderde pakketten bevat, zodat er geen inhoud wordt overschreven. | groupId:name:versie |

### Pakketfilters {#package-filters}

Filters identificeren de knooppunten in de opslagplaats die in het pakket moeten worden opgenomen. A **Filterdefinitie** geeft de volgende informatie op:

* De **Hoofdpad** van de inhoud die moet worden opgenomen.
* **Regels** die specifieke knooppunten onder het hoofdpad bevatten of uitsluiten.

Filters kunnen nul of meer regels bevatten. Als er geen regels zijn gedefinieerd, bevat het pakket alle inhoud onder het hoofdpad.

U kunt een of meer filterdefinities definiëren voor een pakket. Gebruik meerdere filters om inhoud van meerdere hoofdpaden op te nemen.

![chlimage_1-345](assets/chlimage_1-345.png)

In de volgende tabel worden deze regels beschreven en worden voorbeelden gegeven:

<table> 
 <tbody> 
  <tr> 
   <th> Type regel</th> 
   <th>Beschrijving </th> 
   <th>Voorbeeld </th> 
  </tr> 
  <tr> 
   <td> include</td> 
   <td>U kunt een pad definiëren of een reguliere expressie gebruiken om alle knooppunten op te geven die u wilt opnemen.<br /> <br /> Als u een map opneemt, wordt: 
    <ul> 
     <li>opnemen in die map <i>en</i> alle bestanden en mappen in die map (d.w.z. de volledige substructuur)</li> 
     <li><strong>niet</strong> andere bestanden of mappen vanuit het opgegeven hoofdpad opnemen</li> 
    </ul> </td> 
   <td>/libs/sling/install(/.*)? </td> 
  </tr> 
  <tr> 
   <td> uitsluiten</td> 
   <td>U kunt een pad opgeven of een reguliere expressie gebruiken om alle knooppunten op te geven die u wilt uitsluiten.<br /> <br /> Als u een map uitsluit, wordt die map uitgesloten. <i>en</i> alle bestanden en mappen in die map (d.w.z. de volledige substructuur).<br /> </td> 
   <td>/libs/wcm/foundation/components(/.*)?</td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Eén pakket kan meerdere filterdefinities bevatten, zodat knooppunten van verschillende locaties gemakkelijk in één pakket kunnen worden gecombineerd.

Pakketfilters worden meestal gedefinieerd wanneer u het eerst [Maak het pakket](#creating-a-new-package), maar ze kunnen ook op een later tijdstip worden bewerkt (waarna het pakket opnieuw moet worden samengesteld).

### Schermafbeeldingen verpakken {#package-screenshots}

U kunt screenshots aan uw pakket vastmaken om een visuele vertegenwoordiging van te verstrekken wat de inhoud kijkt als; bijvoorbeeld door screenshots van nieuwe functionaliteit te geven.

### Pakketpictogrammen {#package-icons}

U kunt ook een pictogram aan het pakket toevoegen om een snelle visuele weergave van de inhoud van het pakket mogelijk te maken. Dit wordt vervolgens in de pakketlijst weergegeven en u kunt het pakket of de pakketklasse gemakkelijk herkennen.

Aangezien een pakket een pictogram kan bevatten, worden de volgende conventies gebruikt voor officiële pakketten:

>[!NOTE]
>
>Om verwarring te voorkomen, gebruikt u een beschrijvend pictogram voor uw pakket en geen van de officiële pictogrammen.

Officieel hotfix-pakket:

![](do-not-localize/chlimage_1-28.png)

Officiële AEM installatie of extensiepakket:

Officiële kenmerkpakketten:

![](do-not-localize/chlimage_1-29.png)

## Pakketbeheer {#package-manager}

De pakketmanager beheert de pakketten op uw lokale AEM installatie. Nadat u [toegewezen de noodzakelijke toestemmingen](#permissions-needed-for-using-the-package-manager) U kunt de Manager van het Pakket voor diverse acties gebruiken, met inbegrip van het vormen, het bouwen, het downloaden en het installeren van uw pakketten. De belangrijkste te vormen elementen zijn:

* [Pakketinstellingen](#package-settings)
* [Pakketfilters](#package-filters)

### Machtigingen nodig voor het gebruik van Package Manager {#permissions-needed-for-using-the-package-manager}

Om gebruikers het recht te verlenen om pakketten tot stand te brengen, te wijzigen, te uploaden en te installeren, moet u hen de aangewezen toestemmingen bij de volgende plaatsen geven:

* **/etc/packages** (volledige rechten behalve schrapping)
* het knooppunt dat de pakketinhoud bevat

Zie [Machtigingen instellen](/help/sites-administering/security.md) voor instructies voor het wijzigen van machtigingen.

### Een nieuw pakket maken {#creating-a-new-package}

Een nieuwe pakketdefinitie maken:

1. Klik in het welkomstscherm van AEM op **Pakketten** (of van de **Gereedschappen** console dubbelklikken aan **Pakketten**).

1. Selecteer vervolgens **Pakketbeheer**.
1. Klikken **Pakket maken**.

   >[!NOTE]
   >
   >Als uw instantie veel pakketten bevat, is er mogelijk een mapstructuur aanwezig, zodat u naar de vereiste doelmap kunt navigeren voordat u het nieuwe pakket maakt.

1. In het dialoogvenster:

   ![pakkettenNew](assets/packagesnew.png)

   Voer het volgende in:

   * **Groepsnaam**

      De naam van de doelgroep (of map). Groepen zijn bedoeld om u te helpen uw pakketten ordenen.

      Er wordt een map voor de groep gemaakt als deze nog niet bestaat. Als u de groepsnaam leeg laat, wordt het pakket gemaakt in de hoofdpakketlijst (Home > Pakketten).

   * **Pakketnaam**

      De naam van het nieuwe pakket. Selecteer een beschrijvende naam om (en anderen) de inhoud van het pakket gemakkelijk te identificeren.

   * **Versie**

      Een tekstveld waarmee u een versie kunt aangeven. Deze wordt aan de pakketnaam toegevoegd met de naam van het ZIP-bestand.
   Klikken **OK** om het pakket te maken.

1. AEM maakt een lijst van het nieuwe pakket in de aangewezen groepsomslag.

   ![packageItem](assets/packagesitem.png)

   Klik op het pictogram of de pakketnaam om te openen.

   ![packagesitemclick](assets/packagesitemclicked.png)

   >[!NOTE]
   >
   >U kunt desgewenst later terugkeren naar deze pagina.

1. Klikken **Bewerken** om de [pakketinstellingen](#package-settings).

   Hier kunt u informatie toevoegen en/of bepaalde instellingen definiëren. deze bevatten bijvoorbeeld een beschrijving van [pictogram](#package-icons), verwante fouten en voeg providergegevens toe.

   Klikken **OK** nadat u klaar bent met het bewerken van de instellingen.

1. Toevoegen **[Schermafbeeldingen](#package-screenshots)** naar de verpakking toe. Er is één instantie beschikbaar wanneer het pakket wordt gemaakt. Voeg indien nodig meer toe via **Schermafbeelding van pakket** van sidekick.

   Voeg de feitelijke afbeelding toe door te dubbelklikken op de afbeeldingscomponent in het dialoogvenster **Schermafbeeldingen** gebied, afbeelding toevoegen en klikken **OK**.

1. Definieer de **[Pakketfilters](#package-filters)** door instanties van de **Filterdefinitie** vanuit het zijpaneel, dubbelklikt u vervolgens om te openen voor bewerking:

   ![packagefilter](assets/packagesfilter.png)

   Geef het volgende op:

   * **Hoofdpad**
de inhoud die moet worden verpakt; dit kan de basis van een substructuur zijn.
   * **Regels**
Regels zijn facultatief; voor eenvoudige pakketdefinities is het niet nodig regels op te nemen of uit te sluiten .

      Indien nodig kunt u een van de [**Inclusief** of **Uitsluiten** regels](#package-filters) om de inhoud van het pakket precies te definiëren.

      Regels toevoegen met de opdracht **+** symbool, of verwijdert regels gebruikend **-** symbool. Regels worden toegepast volgens hun volgorde, zodat ze op de gewenste plaats worden geplaatst met behulp van de **Omhoog** en **Omlaag** knoppen.
   Klik vervolgens op **OK** om het filter op te slaan.

   >[!NOTE]
   >
   >U kunt zoveel filterdefinities gebruiken als u nodig hebt, maar zorg ervoor dat deze geen conflict veroorzaken. Gebruiken **Voorvertoning** om te bevestigen wat de inhoud van het pakket zal zijn.

1. Om te bevestigen wat het pakket zal bevatten kunt u gebruiken **Voorvertoning**. Dit voert een droge looppas van het bouwstijlproces uit en maakt een lijst van alles die aan het pakket zal worden toegevoegd wanneer het eigenlijk wordt gebouwd.
1. U kunt nu [Opbouwen](#building-a-package) uw pakket.

   >[!NOTE]
   >
   >Het is niet verplicht om het pakket op dit moment te bouwen, het kan op een later tijdstip gebeuren.

### Een pakket maken {#building-a-package}

Een pakket wordt vaak op hetzelfde moment als u gemaakt [de pakketdefinitie maken](#creating-a-new-package), maar u kunt op een later tijdstip terugkeren om het pakket te maken of opnieuw samen te stellen. Dit kan handig zijn als de inhoud in de opslagplaats is gewijzigd.

>[!NOTE]
>
>Voordat u het pakket gaat maken, is het handig een voorvertoning van de inhoud van het pakket te bekijken. Klik om dit te doen **Voorvertoning**.

1. De pakketdefinitie openen vanuit **Pakketbeheer** (klik op het pictogram of de naam van het pakket).

1. Klikken **Opbouwen**. Er wordt een dialoogvenster weergegeven waarin u moet bevestigen dat u het pakket wilt maken.

   >[!NOTE]
   >
   >Dit is met name van belang wanneer u een pakket opnieuw opstelt omdat de inhoud van het pakket wordt overschreven.

1. Klikken **OK**. AEM bouwt het pakket en geeft alle inhoud weer die aan het pakket is toegevoegd. Na voltooiing AEM wordt bevestigd dat het pakket is gemaakt en (wanneer u het dialoogvenster sluit) worden de gegevens in de pakketlijst bijgewerkt.

### Een pakket opnieuw inpakken {#rewrapping-a-package}

Nadat een pakket is gemaakt, kan het indien nodig opnieuw worden verpakt.

Als u het pakket opnieuw inpakt, worden de pakketgegevens gewijzigd - *zonder* de inhoud van het pakket wijzigen. Pakketgegevens zijn de miniatuur, beschrijving, enzovoort, met andere woorden alles wat u kunt bewerken met de **Pakketinstellingen** dialoogvenster (deze klik openen) **Bewerken**).

Een belangrijk gebruiksgeval voor omloop is wanneer het voorbereiden van een pakket voor het pakketaandeel. U hebt bijvoorbeeld een bestaand pakket en u wilt dit delen met anderen. Hiervoor wilt u een miniatuur toevoegen en een beschrijving toevoegen. In plaats van het hele pakket opnieuw te maken met alle functionaliteit (wat enige tijd kan duren en waarbij het risico bestaat dat het pakket niet meer identiek is aan het origineel), kunt u het pakket terugplaatsen en alleen de miniatuur en beschrijving toevoegen.

1. De pakketdefinitie openen vanuit **Pakketbeheer** (klik op het pictogram of de naam van het pakket).

1. Klikken **Bewerken** en de **[Pakketinstellingen](#package-settings)** zoals vereist. Klikken **OK** om op te slaan.

1. Klikken **Omloop**, wordt ter bevestiging een dialoogvenster geopend.

### Pakketgegevens weergeven en bewerken {#viewing-and-editing-package-information}

Informatie over een pakketdefinitie weergeven of bewerken:

1. Navigeer in Pakketbeheer naar het pakket dat u wilt weergeven.
1. Klik op het pakketpictogram van het pakket dat u wilt weergeven. Hiermee wordt de pakketpagina geopend met informatie over de pakketdefinitie:

   ![packagesitemclicked-1](assets/packagesitemclicked-1.png)

   >[!NOTE]
   >
   >U kunt ook bepaalde handelingen op het pakket bewerken en uitvoeren vanaf deze pagina.
   >
   >Welke knoppen beschikbaar zijn, is afhankelijk van het feit of het pakket al dan niet is gemaakt.

1. Als het pakket al is gemaakt, klikt u op **Inhoud**, wordt een venster geopend waarin de volledige inhoud van het pakket wordt weergegeven:

### Inhoud van pakket weergeven en installatie testen {#viewing-package-contents-and-testing-installation}

Nadat een pakket is gemaakt, kunt u de inhoud weergeven:

1. Navigeer in Pakketbeheer naar het pakket dat u wilt weergeven.
1. Klik op het pakketpictogram van het pakket dat u wilt weergeven. Hiermee wordt de pakketpagina geopend met informatie over de pakketdefinitie.

1. Als u de inhoud wilt weergeven, klikt u op **Inhoud**, wordt een venster geopend waarin de volledige inhoud van het pakket wordt weergegeven:

   ![pakkettenContent](assets/packgescontents.png)

1. Klik op **Installatie testen**. Nadat u de actie hebt bevestigd, wordt een venster geopend en worden de resultaten weergegeven alsof de installatie is uitgevoerd:

   ![packagestestinstall](assets/packagestestinstall.png)

### Pakketten naar uw bestandssysteem downloaden {#downloading-packages-to-your-file-system}

In deze sectie wordt beschreven hoe u een pakket van AEM naar uw bestandssysteem kunt downloaden met **Pakketbeheer**.

>[!NOTE]
>
>Zie [Pakket delen](#package-share) voor informatie over het downloaden van hotfixes, eigenschapspakketten, en pakketten van de openbare ruimte en het interne gebied van het pakketaandeel van uw bedrijf.
>
>Vanuit Pakket delen kunt u:
>
>* pakketten downloaden van [Delen van pakketten rechtstreeks in uw lokale AEM-instantie](#downloading-and-installing-packages-from-package-share).\
   >  Na het downloaden wordt het pakket geïmporteerd in uw opslagplaats, waarna u het pakket onmiddellijk op uw lokale instantie kunt installeren met de **Pakketbeheer**. Deze pakketten bevatten hotfixes en andere gedeelde pakketten.
>
>* pakketten downloaden van [Delen van pakketten naar uw bestandssysteem](#downloading-packages-to-your-file-system-from-package-share).
>


1. Klik in het welkomstscherm van AEM op **Pakketten** selecteert u vervolgens **Pakketbeheer**.
1. Navigeer naar het pakket dat u wilt downloaden.

   ![packagedownload](assets/packagesdownload.png)

1. Klik op de koppeling die wordt gevormd door de naam van het ZIP-bestand (onderstreept) voor het pakket dat u wilt downloaden; bijvoorbeeld `export-for-offline.zip`.

   AEM downloadt het pakket naar de computer (via een standaarddialoogvenster voor het downloaden van browsers).

### Pakketten uploaden vanuit uw bestandssysteem {#uploading-packages-from-your-file-system}

Met een pakketupload kunt u een pakket van uw bestandssysteem uploaden naar AEM Package Manager.

>[!NOTE]
>
>Zie [Pakketten uploaden naar het bedrijf-interne Delen van het Pakket](#uploading-a-package) om een pakket te uploaden naar het privégedeelte van uw bedrijf voor het delen van pakketten.

Een pakket uploaden:

1. Ga naar de **Pakketbeheer**. Vervolgens naar de groepsmap waarin u het pakket wilt uploaden.

   ![packagesuploadknop](assets/packagesuploadbutton.png)

1. Klikken **Pakket uploaden**.

   ![packagesuploaddialog](assets/packagesuploaddialog.png)

   * **Bestand**

      U kunt de bestandsnaam rechtstreeks typen of de **Bladeren...** het vereiste pakket in uw lokale bestandssysteem te selecteren (klik na de selectie op **OK**).

   * **Uploaden forceren**

      Als er al een pakket met deze naam bestaat, kunt u hierop klikken om het uploaden te forceren (en het bestaande pakket te overschrijven).
   Klikken **OK** zodat het nieuwe pakket wordt geüpload en wordt weergegeven in de lijst Pakketbeheer.

   >[!NOTE]
   >
   >Als u de inhoud beschikbaar wilt maken voor AEM, moet u [het pakket installeren](#installing-packages).

### Pakketten valideren {#validating-packages}

Voordat u een pakket installeert, dient u de inhoud ervan te controleren. Omdat pakketten bovenliggende bestanden onder kunnen wijzigen `/apps` en/of toevoegen, wijzigen, en verwijderen ACLs, is het vaak nuttig om deze veranderingen te bevestigen alvorens te installeren.

#### Validatieopties {#validation-options}

Het validatiemechanisme kan de volgende kenmerken van het pakket controleren:

* OSGi-pakket importeren
* Bedekkingen
* ACLs

Deze opties worden hieronder beschreven.

* **OSGi-pakketinvoer valideren**

   **Wat wordt gecontroleerd**

   Deze validatie inspecteert het pakket voor alle JAR-bestanden (OSGi-bundels), extraheert de bestanden `manifest.xml` (die de versioned gebiedsdelen bevat waarop genoemde OSGi bundel) steunt en verifieert de AEM instantie uitvoert genoemde gebiedsdelen met de correcte versies.

   **Hoe het is gemeld**

   Eventuele geversierde afhankelijkheden waaraan de AEM instantie niet kan voldoen, worden vermeld in het dialoogvenster **Activiteitenlogboek** van Package Manager.

   **Foutstatussen**

   Als de gebiedsdelen ontevreden zijn, dan zullen de bundels OSGi in het pakket met die gebiedsdelen niet beginnen. Dit resulteert in een gebroken toepassingsplaatsing aangezien om het even wat die op de niet-begonnen bundel OSGi baseert zal beurtelings niet behoorlijk functioneren.

   **Foutresolutie**

   Om fouten als gevolg van ontevreden OSGi-bundels op te lossen, moet de afhankelijkheidsversie in de bundel met ontevreden invoer worden aangepast.

* **Bedekkingen valideren**

   **Wat wordt gecontroleerd**

   Deze validatie bepaalt of het pakket dat wordt geïnstalleerd een bestand bevat dat al wordt bedekt in de AEM.

   Als u bijvoorbeeld een bestaande overlay hebt van `/apps/sling/servlet/errorhandler/404.jsp`, een pakket dat `/libs/sling/servlet/errorhandler/404.jsp`, zodat het bestaande bestand wordt gewijzigd in `/libs/sling/servlet/errorhandler/404.jsp`.

   **Hoe het is gemeld**

   Dergelijke overlays worden beschreven in het dialoogvenster **Activiteitenlogboek** van Package Manager.

   **Foutstatussen**

   Een foutstatus houdt in dat het pakket probeert een bestand te implementeren dat al is bedekt. De wijzigingen in het pakket worden dus overschreven (en dus &quot;verborgen&quot;) door de bedekking en worden niet van kracht.

   **Foutresolutie**

   Om dit probleem op te lossen, moet u de extensie van het overlaybestand in `/apps` moet de wijzigingen in het bovenliggende bestand in `/libs` en neemt de wijzigingen waar nodig op in de overlay ( `/apps`), en het overlappende bestand opnieuw gebruiken.

   >[!NOTE]
   >
   >Het validatiemechanisme biedt geen enkele manier om te combineren als de overlay-inhoud correct is opgenomen in het overlaybestand. Daarom zal deze validatie ook na de nodige wijzigingen over conflicten blijven rapporteren.

* **ACLs bevestigen**

   **Wat wordt gecontroleerd**

   Deze bevestiging controleert welke toestemmingen worden toegevoegd, hoe zij zullen worden behandeld (samenvoegen/vervangen), en als de huidige toestemmingen zullen worden beïnvloed.

   **Hoe het is gemeld**

   De machtigingen worden beschreven in de **Activiteitenlogboek** van Package Manager.

   **Foutstatussen**

   Er kunnen geen expliciete fouten worden opgegeven. De bevestiging wijst eenvoudig erop of om het even welke nieuwe ACL toestemmingen zullen worden toegevoegd of beïnvloed door het pakket te installeren.

   **Foutresolutie**

   Gebruikend de informatie die door de bevestiging wordt verstrekt, kunnen de beïnvloede knopen in CRXDE worden herzien en ACLs kan in het pakket aanpassen zoals nodig.

   >[!CAUTION]
   >
   >Als beste praktijken wordt het geadviseerd dat de pakketten geen AEM-Verstrekte ACLs zouden moeten beïnvloeden aangezien dit in onverwacht productgedrag kan resulteren.

#### Validatie uitvoeren {#performing-validation}

De validatie van pakketten kan op twee verschillende manieren worden uitgevoerd:

* Via de interface van Package Manager
* Via HTTP-POST request zoals with cURL

>[!NOTE]
>
>Validatie moet altijd plaatsvinden na het uploaden van het pakket, maar voordat het wordt geïnstalleerd.

**Pakketvalidatie via pakketbeheer**

1. Open Package Manager op `https://<server>:<port>/crx/packmgr`
1. Selecteer het pakket in de lijst en selecteer vervolgens **Meer** vervolgkeuzelijst vanaf de kop en vervolgens **Valideren** in het keuzemenu.

   >[!NOTE]
   >
   >Dit moet gebeuren nadat u het inhoudspakket hebt geüpload, maar voordat u het pakket installeert.

1. Gebruik in het modale dialoogvenster dat dan wordt weergegeven de selectievakjes om het type of de typen validatie te selecteren en de validatie te starten door op **Valideren**. U kunt ook op **Annuleren**.

1. De gekozen validatie(s) worden dan uitgevoerd. De resultaten worden getoond in het activiteitenlogboek van de Manager van het Pakket.

**Pakketvalidatie via HTTP-POST-aanvraag**

Het verzoek van de POST heeft de volgende vorm.

```
https://<host>:<port>/crx/packmgr/service.jsp?cmd=validate&type=osgiPackageImports,overlays,acls
```

>[!NOTE]
>
>De `type` parameter kan elke door komma&#39;s gescheiden niet-geordende lijst zijn die bestaat uit:
>
>* `osgiPackageImports`
>* `overlays`
>* `acls`
>
>De waarde van `type` standaardinstellingen `osgiPackageImports` indien niet geslaagd.

Hieronder ziet u een voorbeeld van het gebruik van cURL voor het uitvoeren van een pakketvalidatie.

1. Als u cURL gebruikt, voert u een instructie uit die vergelijkbaar is met het volgende:

   ```shell
   curl -v -X POST --user admin:admin -F file=@/Users/SomeGuy/Desktop/core.wcm.components.all-1.1.0.zip 'http://localhost:4502/crx/packmgr/service.jsp?cmd=validate&type=osgiPackageImports,overlays,acls'
   ```

1. De gevraagde validatie wordt uitgevoerd en het antwoord wordt teruggestuurd als een JSON-object.

>[!NOTE]
>
>De reactie op een aanvraag van een HTTP-validatie-POST is een JSON-object met de resultaten van de validatie.

### Pakketten installeren {#installing-packages}

Nadat u een pakket hebt geüpload, moet u de inhoud installeren. Om de pakketinhoud geïnstalleerd en functioneel te hebben, moet het allebei zijn:

* geladen in AEM [geüpload uit uw bestandssysteem](#uploading-packages-from-your-file-system) of [gedownload van pakketshare](#downloading-and-installing-packages-from-package-share))

* geïnstalleerd

>[!CAUTION]
>
>Wanneer u een pakket installeert, kan bestaande inhoud worden overschreven of verwijderd. Upload een pakket alleen als u zeker weet dat de benodigde inhoud niet wordt verwijderd of overschreven.
>
>Als u de inhoud of de invloed van een pakket wilt zien, kunt u:
>
>* Voer een testinstallatie van de verpakking uit zonder de inhoud te wijzigen:\
   >  Open het pakket (klik op het pictogram of de naam van het pakket) en klik op **Installeren testen**.
>
>* Zie een lijst met pakketinhoud:\
   >  Open het pakket en klik op **Inhoud**.
>


>[!NOTE]
>
>Onmiddellijk voor de installatie van het pakket wordt een pakket met momentopnamen gemaakt dat de inhoud bevat die wordt overschreven.
>
>Deze momentopname wordt opnieuw geïnstalleerd als/wanneer u het pakket verwijdert.

>[!CAUTION]
>
>Als u digitale elementen installeert, moet u:
>
>* Deactiveer eerst de WorkflowLauncher.\
   >  Gebruik de het menuoptie van Componenten van de console OSGi om te deactiveren `com.day.cq.workflow.launcher.impl.WorkflowLauncherImpl`.
>
>* Vervolgens activeert u de WorkflowLauncher opnieuw wanneer de installatie is voltooid.
>
>Als u de WorkflowLauncher deactiveert, zorgt u ervoor dat het framework voor het importeren van middelen de elementen niet (onbedoeld) manipuleert bij de installatie.

1. Navigeer in Pakketbeheer naar het pakket dat u wilt installeren.

   An **Installeren** de knoop wordt getoond bij de kant van Pakketten die nog niet geïnstalleerd zijn.

   >[!NOTE]
   >
   >U kunt het pakket ook openen door op het bijbehorende pictogram te klikken om het **Installeren** daar.

1. Klikken **Installeren** om de installatie te starten. In een dialoogvenster wordt bevestiging gevraagd en worden alle aangebrachte wijzigingen vermeld. Wanneer u klaar bent, klikt u op **Sluiten** in het dialoogvenster.

   Het woord **Geïnstalleerd** wordt weergegeven naast het pakket nadat het is geïnstalleerd.

### Uploaden en installeren op basis van bestandssysteem {#file-system-based-upload-and-installation}

U kunt pakketten op een andere manier naar uw exemplaar uploaden en installeren. In uw bestandssysteem hebt u een `crx-quicksart` samen met uw pot en `license.properties` bestand. U moet een map maken met de naam `install` krachtens `crx-quickstart`. Dan heb je iets als dit: `<aem_home>/crx-quickstart/install`

In deze installatiemap kunt u uw pakketten rechtstreeks toevoegen. Deze worden automatisch geüpload en geïnstalleerd op uw exemplaar. Wanneer het wordt gedaan, kunt u de pakketten in de Manager van het Pakket zien.

Als uw instantie wordt uitgevoerd, voegt u een pakket toe aan de `install` De uploadbewerking en de installatie worden direct gestart. Als de instantie niet wordt uitgevoerd, worden de pakketten die u in de `install` wordt bij het opstarten geïnstalleerd in alfabetische volgorde.

>[!NOTE]
>
>U kunt dit ook doen voordat u de instantie voor de eerste keer start. Om dat te doen, moet u creëren `crx-quickstart` map handmatig maken `install` en plaatst uw pakketten daar. Wanneer u uw exemplaar vervolgens voor het eerst start, worden de pakketten in alfabetische volgorde geïnstalleerd.

### Pakketten verwijderen {#uninstalling-packages}

Met AEM kunt u pakketten verwijderen. Deze actie keert de inhoud van de bewaarplaats terug die aan de momentopname wordt beïnvloed die onmiddellijk voorafgaand aan de pakketinstallatie wordt gemaakt.

>[!NOTE]
>
>Na de installatie wordt een pakket met momentopnamen gemaakt dat de inhoud bevat die wordt overschreven.
>
>Dit pakket wordt opnieuw geïnstalleerd wanneer u het pakket verwijdert.

1. Navigeer in Pakketbeheer naar het pakket dat u wilt verwijderen.
1. Klik op het pakketpictogram van het pakket dat u wilt verwijderen.
1. Klikken **Verwijderen** om de inhoud van dit pakket uit de opslagplaats te verwijderen. In een dialoogvenster wordt bevestiging gevraagd en worden alle aangebrachte wijzigingen vermeld. Wanneer u klaar bent, klikt u op **Sluiten** in het dialoogvenster.

### Pakketten verwijderen {#deleting-packages}

Een pakket verwijderen uit de lijst(en) in Package Manager:

>[!NOTE]
>
>De geïnstalleerde bestanden/knooppunten uit het pakket zijn: **niet** geschrapt.

1. In de **Gereedschappen** console, breid uit **Pakketten** om het pakket weer te geven in het rechterdeelvenster.

1. Klik op het pakket dat u wilt verwijderen, zodat het wordt gemarkeerd en vervolgens op een van de volgende manieren:

   * Klikken **Verwijderen** in het werkbalkmenu.
   * Klik met de rechtermuisknop en selecteer **Verwijderen**.

   ![packagesdelete](assets/packagesdelete.png)

1. AEM vraagt om bevestiging dat u het pakket wilt schrappen. Klikken **OK** om de schrapping te bevestigen.

>[!CAUTION]
>
>Als dit pakket al is geïnstalleerd, *geïnstalleerd* inhoud zal **niet** worden geschrapt.

### Pakketten repliceren {#replicating-packages}

Kopieer de inhoud van een pakket en installeer het naar de publicatie-instantie:

1. In de **Pakketbeheer** Navigeer naar het pakket dat u wilt repliceren.

1. Klik op het pictogram of de naam van het pakket dat u wilt repliceren om het uit te vouwen.
1. In de **Meer** op de werkbalk selecteert u **Repliceren**.

## Package Share {#package-share}

Het aandeel van het Pakket was een gecentraliseerde server die openbaar ter beschikking werd gesteld om inhoud-Pakketten te delen.

Het is vervangen door [Softwaredistributie.](#software-distribution)

## Softwaredistributie {#software-distribution}

[Softwaredistributie](https://downloads.experiencecloud.adobe.com) is de nieuwe gebruikersinterface die wordt ontworpen om het onderzoek en de download van AEM Pakketten te vereenvoudigen.

Kijk voor meer informatie naar de [Documentatie voor softwaredistributie.](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html)

>[!CAUTION]
>
>AEM pakketbeheer is momenteel niet bruikbaar voor softwaredistributie. U downloadt uw pakketten naar uw lokale schijf.
