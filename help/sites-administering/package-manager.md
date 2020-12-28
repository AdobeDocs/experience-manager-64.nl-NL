---
title: Werken met pakketten
seo-title: Werken met pakketten
description: Leer de basisbeginselen van het werken met pakketten in AEM.
seo-description: Leer de basisbeginselen van het werken met pakketten in AEM.
uuid: e9eb4f88-9df6-4019-92e0-2aafcffe1aab
contentOwner: Chiradeep Majumdar
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: content
content-type: reference
discoiquuid: 8e568c59-5455-422f-94a6-baf6d2aae070
translation-type: tm+mt
source-git-commit: be46329cfe5c6fee28f616f2257e215df402e94d
workflow-type: tm+mt
source-wordcount: '5365'
ht-degree: 0%

---


# Hoe te met Pakketten te werken{#how-to-work-with-packages}

Pakketten maken het importeren en exporteren van inhoud in de opslagplaats mogelijk. U kunt bijvoorbeeld pakketten gebruiken om nieuwe functionaliteit te installeren, inhoud tussen instanties over te brengen, en een back-up van inhoud in de opslagplaats te maken.

Pakketten kunnen op de volgende pagina&#39;s worden geopend en/of onderhouden:

* [Pakketbeheer](#package-manager), waarmee u de pakketten in uw lokale AEM-instantie kunt beheren.

* [Het Aandeel](#package-share) van het pakket, een gecentraliseerde server die zowel openbaar beschikbare pakketten als die privé aan uw bedrijf houdt. De openbare pakketten kunnen hotfixes, nieuwe functionaliteit, documentatie, enz. bevatten.

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

## Pakketinformatie {#package-information}

Een pakketdefinitie bestaat uit verschillende soorten informatie:

* [Pakketinstellingen](#package-settings)
* [Pakketfilters](#package-filters)
* [Schermafbeeldingen verpakken](#package-screenshots)
* [Pakketpictogrammen](#package-icons)

### Pakketinstellingen {#package-settings}

U kunt een verscheidenheid van de Montages van het Pakket uitgeven om aspecten zoals de pakketbeschrijving, verwante insecten, gebiedsdelen en leveranciersinformatie te bepalen.

Het dialoogvenster **Pakketinstellingen** is beschikbaar via de knop **Bewerken** wanneer [een pakket maken](#creating-a-new-package) of [bewerken](#viewing-and-editing-package-information) en drie tabbladen voor configuratie bevat. Nadat er wijzigingen zijn aangebracht, klikt u op **OK** om deze op te slaan.

![packagesedit](assets/packagesedit.png)

| **Veld** | **Beschrijving** |
|---|---|
| Naam | De naam van het pakket. |
| Groeperen | De naam van de groep waaraan het pakket moet worden toegevoegd, voor het ordenen van pakketten. Typ de naam van een nieuwe groep of selecteer een bestaande groep. |
| Versie | Tekst die voor de aangepaste versie moet worden gebruikt. |
| Beschrijving | Een korte beschrijving van het pakket. HTML-opmaak kan worden gebruikt voor opmaak. |
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
   <td>Vereist<br /> </td> 
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
     <li><strong>Negeer</strong>  - behoud ACLs in de bewaarplaats</li> 
     <li><strong>Overschrijf</strong>  ACLs in de bewaarplaats</li> 
     <li><strong>De fusie</strong> - voegt beide reeksen ACLs samen</li> 
     <li><strong>Wis</strong>  - duidelijke ACLs</li> 
     <li><strong>MergePreserve</strong>  - fusie toegangsbeheer in de inhoud met die voorzien van het pakket door de toegangsbeheeringangen van hoofden toe te voegen niet aanwezig in de inhoud</li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

![pakketafhankelijkheden](assets/packagesdependencies.png)

| **Veld** | **Beschrijving** | **Indeling/Voorbeeld** |
|---|---|---|
| Getest met | De productnaam en versie van dit pakket zijn bedoeld voor of zijn compatibel met. | *AEM6* |
| Opgeloste problemen | Een tekstveld waarin u details kunt weergeven van bugs die zijn gecorrigeerd voor dit pakket. Vermeld elke bug op een aparte regel. | Overzicht van bug-nr |
| Afhankelijk van | Hiermee geeft u informatie over afhankelijkheden weer die moet worden gerespecteerd wanneer andere pakketten nodig zijn om het huidige pakket op de verwachte manier te laten uitvoeren. Dit veld is belangrijk bij het gebruik van hotfixes. | groupId:name:version |
| Vervangen | Een lijst met vervangen pakketten die door dit pakket worden vervangen. Controleer vóór de installatie of dit pakket alle benodigde inhoud uit de verouderde pakketten bevat, zodat er geen inhoud wordt overschreven. | groupId:name:version |

### Pakketfilters {#package-filters}

Filters identificeren de knooppunten in de opslagplaats die in het pakket moeten worden opgenomen. A **Filter Definition** geeft de volgende informatie op:

* Het **Basispad** van de inhoud die moet worden opgenomen.
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
     <li>de map <i>en</i> alle bestanden en mappen in die map opnemen (d.w.z. de volledige substructuur)</li> 
     <li><strong>Neem </strong> geen andere bestanden of mappen vanaf onder het opgegeven hoofdpad op</li> 
    </ul> </td> 
   <td>/libs/sling/install(/.*)? </td> 
  </tr> 
  <tr> 
   <td> uitsluiten</td> 
   <td>U kunt een pad opgeven of een reguliere expressie gebruiken om alle knooppunten op te geven die u wilt uitsluiten.<br /> <br /> Als u een map uitsluit, worden die map  <i></i> en alle bestanden en mappen in die map (dus de volledige substructuur) uitgesloten.<br /> </td> 
   <td>/libs/wcm/foundation/components(/.*)?</td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Eén pakket kan meerdere filterdefinities bevatten, zodat knooppunten van verschillende locaties gemakkelijk in één pakket kunnen worden gecombineerd.

Pakketfilters worden meestal gedefinieerd wanneer u het pakket [maakt, maar kunnen ook op een later tijdstip worden bewerkt (waarna het pakket opnieuw moet worden samengesteld).](#creating-a-new-package)

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

De pakketmanager beheert de pakketten op uw lokale AEM installatie. Nadat u [de noodzakelijke toestemmingen](#permissions-needed-for-using-the-package-manager) hebt toegewezen kunt u de Manager van het Pakket voor diverse acties, met inbegrip van het vormen, het bouwen, het downloaden en het installeren van uw pakketten gebruiken. De belangrijkste te vormen elementen zijn:

* [Pakketinstellingen](#package-settings)
* [Pakketfilters](#package-filters)

### Toestemmingen nodig voor het gebruiken van de Manager {#permissions-needed-for-using-the-package-manager} van het Pakket

Om gebruikers het recht te verlenen om pakketten tot stand te brengen, te wijzigen, te uploaden en te installeren, moet u hen de aangewezen toestemmingen bij de volgende plaatsen geven:

* **/etc/packages** (volledige rechten m.u.v. schrapping)
* het knooppunt dat de pakketinhoud bevat

Zie [Machtigingen instellen](/help/sites-administering/security.md) voor instructies over het wijzigen van machtigingen.

### Een nieuw pakket maken {#creating-a-new-package}

Een nieuwe pakketdefinitie maken:

1. Voor het AEM Welkome scherm, klik **Pakketten** (of van de **console Tools** tweemaal klikken op **Pakketten**).

1. Selecteer vervolgens **Pakketbeheer**.
1. Klik **Pakket maken**.

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
   Klik **OK** om het pakket te maken.

1. AEM maakt een lijst van het nieuwe pakket in de aangewezen groepsomslag.

   ![packageItem](assets/packagesitem.png)

   Klik op het pictogram of de pakketnaam om te openen.

   ![packagesitemclick](assets/packagesitemclicked.png)

   >[!NOTE]
   >
   >U kunt desgewenst later terugkeren naar deze pagina.

1. Klik **Bewerken** om de [pakketinstellingen te bewerken](#package-settings).

   Hier kunt u informatie toevoegen en/of bepaalde instellingen definiëren. Dit zijn bijvoorbeeld een beschrijving, het pictogram [icon](#package-icons), verwante bugs en voeg providerdetails toe.

   Klik **OK** nadat u klaar bent met het bewerken van de instellingen.

1. Voeg **[Screenshots](#package-screenshots)** aan het pakket toe zoals vereist. Eén instantie is beschikbaar wanneer het pakket wordt gemaakt. Voeg indien nodig meer toe met **Package Screenshot** van sidekick.

   Voeg de feitelijke afbeelding toe door te dubbelklikken op de afbeeldingscomponent in het gebied **Screenshots**, een afbeelding toe te voegen en te klikken op **OK**.

1. Definieer de **[Pakketfilters](#package-filters)** door instanties van de **Definitie van filter** van het hulpstuk te slepen, en dan te dubbelklikken om voor het uitgeven te openen:

   ![packagefilter](assets/packagesfilter.png)

   Geef het volgende op:

   * **basispadDe**
inhoud die moet worden verpakt; dit kan de basis van een substructuur zijn.
   * ****
Regels zijn facultatief; voor eenvoudige pakketdefinities is het niet nodig regels op te nemen of uit te sluiten .

      Indien nodig kunt u [**Include** of **Exclude** regels](#package-filters) bepalen om de pakketinhoud precies te bepalen.

      Voeg regels toe met het symbool **+**, of verwijder regels met het symbool **-**. Regels worden toegepast op basis van hun volgorde, zodat ze op de gewenste positie worden geplaatst met de knoppen **Omhoog** en **Omlaag**.
   Klik vervolgens op **OK** om het filter op te slaan.

   >[!NOTE]
   >
   >U kunt zoveel filterdefinities gebruiken als u nodig hebt, maar zorg ervoor dat deze geen conflict veroorzaken. Gebruik **Voorvertoning** om te bevestigen wat de inhoud van het pakket zal zijn.

1. Om te bevestigen wat het pakket zal houden kunt u **Voorproef** gebruiken. Dit voert een droge looppas van het bouwstijlproces uit en maakt een lijst van alles die aan het pakket zal worden toegevoegd wanneer het eigenlijk wordt gebouwd.
1. U kunt nu [Build](#building-a-package) uw pakket.

   >[!NOTE]
   >
   >Het is niet verplicht om het pakket op dit moment te bouwen, het kan op een later tijdstip gebeuren.

### Een pakket maken {#building-a-package}

Een pakket wordt vaak gebouwd tezelfdertijd aangezien u [de pakketdefinitie ](#creating-a-new-package) creeert, maar u kunt op een later punt in tijd terugkeren om of het pakket te bouwen, of te herbouwen. Dit kan handig zijn als de inhoud in de opslagplaats is gewijzigd.

>[!NOTE]
>
>Voordat u het pakket gaat maken, is het handig een voorvertoning van de inhoud van het pakket te bekijken. Klik **Voorvertoning** om dit te doen.

1. Open de pakketdefinitie van **Package Manager** (klik op het pakketpictogram of de naam).

1. Klik **Bouwstijl**. Er wordt een dialoogvenster weergegeven waarin u moet bevestigen dat u het pakket wilt maken.

   >[!NOTE]
   >
   >Dit is met name van belang wanneer u een pakket opnieuw opstelt omdat de inhoud van het pakket wordt overschreven.

1. Klik **OK**. AEM bouwt het pakket en geeft alle inhoud weer die aan het pakket is toegevoegd. Na voltooiing AEM wordt bevestigd dat het pakket is gemaakt en (wanneer u het dialoogvenster sluit) worden de gegevens in de pakketlijst bijgewerkt.

### Een pakket {#rewrapping-a-package} opnieuw inpakken

Nadat een pakket is gemaakt, kan het indien nodig opnieuw worden verpakt.

Als u de pakketgegevens opnieuw inpakt, worden deze gewijzigd - *zonder* de pakketinhoud te wijzigen. Pakketgegevens zijn de miniatuur, beschrijving, enzovoort, met andere woorden alles wat u kunt bewerken met het dialoogvenster **Pakketinstellingen** (om deze klik te openen **Bewerken**).

Een belangrijk gebruiksgeval voor omloop is wanneer het voorbereiden van een pakket voor het pakketaandeel. U hebt bijvoorbeeld een bestaand pakket en u wilt dit delen met anderen. Hiervoor wilt u een miniatuur toevoegen en een beschrijving toevoegen. In plaats van het hele pakket opnieuw te maken met al zijn functionaliteit (wat enige tijd kan duren en het risico inhoudt dat het pakket niet meer identiek is aan het origineel), kunt u het pakket terugzetten en alleen de miniatuur en beschrijving toevoegen.

1. Open de pakketdefinitie van **Package Manager** (klik op het pakketpictogram of de naam).

1. Klik **Bewerken** en werk de **[Pakketinstellingen](#package-settings)** naar wens bij. Klik **OK** om op te slaan.

1. Klik **Omloop**, zal een dialoog om bevestiging vragen.

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

1. Als het pakket al is samengesteld, klikt u op **Inhoud**, wordt een venster geopend met daarin de volledige inhoud van het pakket:

### Inhoud van pakket weergeven en installatie testen {#viewing-package-contents-and-testing-installation}

Nadat een pakket is gemaakt, kunt u de inhoud weergeven:

1. Navigeer in Pakketbeheer naar het pakket dat u wilt weergeven.
1. Klik op het pakketpictogram van het pakket dat u wilt weergeven. Hiermee wordt de pakketpagina geopend met informatie over de pakketdefinitie.

1. Als u de inhoud wilt weergeven en op **Inhoud** wilt klikken, wordt een venster geopend waarin de volledige inhoud van het pakket wordt weergegeven:

   ![pakkettenContent](assets/packgescontents.png)

1. Klik **Installatie testen** om de installatie op een droge manier uit te voeren. Nadat u de actie hebt bevestigd, wordt een venster geopend en worden de resultaten weergegeven alsof de installatie is uitgevoerd:

   ![packagestestinstall](assets/packagestestinstall.png)

### Pakketten downloaden naar uw bestandssysteem {#downloading-packages-to-your-file-system}

In deze sectie wordt beschreven hoe u een pakket van AEM naar uw bestandssysteem kunt downloaden met **Package Manager**.

>[!NOTE]
>
>Zie [Delen van pakketten](#package-share) voor informatie over het downloaden van hotfixes, functiepakketten en pakketten vanuit de openbare ruimte en het interne gebied van pakketdeling van uw bedrijf.
>
>Vanuit Pakket delen kunt u:
>
>* download pakketten van [Deel van het Pakket direct in uw lokale AEM instantie](#downloading-and-installing-packages-from-package-share).\
   >  Na het downloaden wordt het pakket geïmporteerd in uw opslagplaats, waarna u het pakket direct op uw lokale instantie kunt installeren met de **Package Manager**. Deze pakketten bevatten hotfixes en andere gedeelde pakketten.
   >
   >
* U kunt pakketten downloaden van [Delen van pakketten naar uw bestandssysteem](#downloading-packages-to-your-file-system-from-package-share).

>



1. Voor het AEM Welkome scherm, klik **Pakketten**, dan selecteer **de Manager van het Pakket**.
1. Navigeer naar het pakket dat u wilt downloaden.

   ![packagedownload](assets/packagesdownload.png)

1. Klik op de koppeling die wordt gevormd door de naam van het ZIP-bestand (onderstreept) voor het pakket dat u wilt downloaden; bijvoorbeeld `export-for-offline.zip`.

   AEM downloadt het pakket naar de computer (via een standaarddialoogvenster voor het downloaden van browsers).

### Pakketten uploaden vanuit uw bestandssysteem {#uploading-packages-from-your-file-system}

Met een pakketupload kunt u een pakket van uw bestandssysteem uploaden naar AEM Package Manager.

>[!NOTE]
>
>Zie [Pakketten uploaden naar het bedrijf-interne Delen van het Pakket](#uploading-a-package) om een pakket aan het privé gebied van uw bedrijf van het Aandeel van het Pakket te uploaden.

Een pakket uploaden:

1. Navigeer aan **de Manager van het Pakket**. Vervolgens naar de groepsmap waarin u het pakket wilt uploaden.

   ![packagesuploadknop](assets/packagesuploadbutton.png)

1. Klik **Pakket uploaden**.

   ![packagesuploaddialog](assets/packagesuploaddialog.png)

   * **Bestand**

      U kunt de bestandsnaam rechtstreeks typen of **Bladeren gebruiken..** om het vereiste pakket in uw lokale bestandssysteem te selecteren (klik na de selectie op **OK**).

   * **Uploaden forceren**

      Als er al een pakket met deze naam bestaat, kunt u hierop klikken om het uploaden te forceren (en het bestaande pakket te overschrijven).
   Klik **OK** zodat het nieuwe pakket wordt geüpload en in de lijst van de Manager van het Pakket wordt vermeld.

   >[!NOTE]
   >
   >Als u de inhoud beschikbaar wilt maken voor AEM, moet u [het pakket ](#installing-packages) installeren.

### Pakketten {#validating-packages} valideren

Voordat u een pakket installeert, dient u de inhoud ervan te controleren. Omdat de pakketten overlay dossiers onder `/apps` kunnen wijzigen en/of ACLs toevoegen wijzigen en verwijderen, is het vaak nuttig om deze veranderingen te bevestigen alvorens te installeren.

#### Validatieopties {#validation-options}

Het validatiemechanisme kan de volgende kenmerken van het pakket controleren:

* OSGi-pakket importeren
* Bedekkingen
* ACLs

Deze opties worden hieronder beschreven.

* **OSGi-pakketinvoer valideren**

   **Wat wordt gecontroleerd**

   Deze bevestiging inspecteert het pakket voor alle JAR dossiers (bundels OSGi), haalt hun `manifest.xml` (die de versioned gebiedsdelen bevat waarop genoemde OSGi bundel baseert) en verifieert de AEM instantie uitvoert genoemde gebiedsdelen met de correcte versies.

   **Hoe het is gemeld**

   Om het even welke versioned gebiedsdelen die niet door de AEM instantie kunnen worden tevredengesteld zijn vermeld in **Activiteitenlogboek** van de Manager van het Pakket.

   **Foutstatussen**

   Als de gebiedsdelen ontevreden zijn, dan zullen de bundels OSGi in het pakket met die gebiedsdelen niet beginnen. Dit resulteert in een gebroken toepassingsplaatsing aangezien om het even wat die op de niet-begonnen bundel OSGi baseert zal beurtelings niet behoorlijk functioneren.

   **Foutresolutie**

   Om fouten als gevolg van ontevreden OSGi-bundels op te lossen, moet de afhankelijkheidsversie in de bundel met ontevreden invoer worden aangepast.

* **Bedekkingen valideren**

   **Wat wordt gecontroleerd**

   Deze validatie bepaalt of het pakket dat wordt geïnstalleerd een bestand bevat dat al wordt bedekt in de AEM.

   Als u bijvoorbeeld een bestaande overlay op `/apps/sling/servlet/errorhandler/404.jsp` hebt, een pakket dat `/libs/sling/servlet/errorhandler/404.jsp` bevat, zodat het bestaande bestand op `/libs/sling/servlet/errorhandler/404.jsp` wordt gewijzigd.

   **Hoe het is gemeld**

   Dergelijke overlays worden beschreven in het **Activiteitenlogboek** van het Pakketbeheer.

   **Foutstatussen**

   Een foutstatus houdt in dat het pakket probeert een bestand te implementeren dat al is bedekt. De wijzigingen in het pakket worden dus overschreven (en dus &quot;verborgen&quot;) door de bedekking en worden niet van kracht.

   **Foutresolutie**

   Om dit probleem op te lossen, moet de beheerder van het overlaybestand in `/apps` de wijzigingen in het overlay-bestand in `/libs` controleren en de wijzigingen naar wens opnemen in de overlay ( `/apps`) en het overlay-bestand opnieuw implementeren.

   >[!NOTE]
   >
   >Het validatiemechanisme biedt geen enkele manier om te combineren als de overlay-inhoud correct is opgenomen in het overlaybestand. Daarom zal deze validatie ook na de nodige wijzigingen over conflicten blijven rapporteren.

* **ACLs bevestigen**

   **Wat wordt gecontroleerd**

   Deze bevestiging controleert welke toestemmingen worden toegevoegd, hoe zij zullen worden behandeld (samenvoegen/vervangen), en als de huidige toestemmingen zullen worden beïnvloed.

   **Hoe het is gemeld**

   De toestemmingen worden beschreven in **Activiteitenlogboek** van de Manager van het Pakket.

   **Foutstatussen**

   Er kunnen geen expliciete fouten worden opgegeven. De bevestiging wijst eenvoudig erop of om het even welke nieuwe ACL toestemmingen zullen worden toegevoegd of beïnvloed door het pakket te installeren.

   **Foutresolutie**

   Gebruikend de informatie die door de bevestiging wordt verstrekt, kunnen de beïnvloede knopen in CRXDE worden herzien en ACLs kan in het pakket aanpassen zoals nodig.

   >[!CAUTION]
   >
   >Als beste praktijken wordt het geadviseerd dat de pakketten geen AEM-Verstrekte ACLs zouden moeten beïnvloeden aangezien dit in onverwacht productgedrag kan resulteren.

#### Validatie {#performing-validation} uitvoeren

De validatie van pakketten kan op twee verschillende manieren worden uitgevoerd:

* Via de interface van Package Manager
* Via HTTP-POST request zoals with cURL

>[!NOTE]
>
>Validatie moet altijd plaatsvinden na het uploaden van het pakket, maar voordat het wordt geïnstalleerd.

**Pakketvalidatie via pakketbeheer**

1. Open de Manager van het Pakket bij `https://<server>:<port>/crx/packmgr`
1. Selecteer het pakket in de lijst en selecteer **Meer** dropdown van de rubriek en dan **Valideren** van het drop-down menu.

   >[!NOTE]
   >
   >Dit moet gebeuren nadat u het inhoudspakket hebt geüpload, maar voordat u het pakket installeert.

1. In het modale dialoogvenster dat dan wordt weergegeven, gebruikt u de selectievakjes om het type of de typen validatie te selecteren en de validatie te starten door op **Valideren** te klikken. U kunt ook op **Annuleren** klikken.

1. De gekozen validatie(s) worden dan uitgevoerd. De resultaten worden getoond in het activiteitenlogboek van de Manager van het Pakket.

**Pakketvalidatie via HTTP-POST-aanvraag**

Het verzoek van de POST heeft de volgende vorm.

```
https://<host>:<port>/crx/packmgr/service.jsp?cmd=validate&type=osgiPackageImports,overlays,acls
```

>[!NOTE]
>
>De parameter `type` kan elke door komma&#39;s gescheiden niet-geordende lijst zijn die bestaat uit:
>
>* `osgiPackageImports`
>* `overlays`
>* `acls`

>
>
De waarde van `type` is standaard `osgiPackageImports` als deze niet wordt doorgegeven.

Hieronder ziet u een voorbeeld van het gebruik van cURL voor het uitvoeren van een pakketvalidatie.

1. Als u cURL gebruikt, voert u een instructie uit die vergelijkbaar is met het volgende:

   ```shell
   curl -v -X POST --user admin:admin -F file=@/Users/SomeGuy/Desktop/core.wcm.components.all-1.1.0.zip 'http://localhost:4502/crx/packmgr/service.jsp?cmd=validate&type=osgiPackageImports,overlays,acls'
   ```

1. De gevraagde validatie wordt uitgevoerd en het antwoord wordt teruggestuurd als een JSON-object.

>[!NOTE]
>
>De reactie op een aanvraag van een HTTP-validatie-POST is een JSON-object met de resultaten van de validatie.

### Pakketten {#installing-packages} installeren

Nadat u een pakket hebt geüpload, moet u de inhoud installeren. Om de pakketinhoud geïnstalleerd en functioneel te hebben, moet het allebei zijn:

* geladen in AEM (of [geüpload van uw bestandssysteem](#uploading-packages-from-your-file-system) of [gedownload van pakketshare](#downloading-and-installing-packages-from-package-share))

* geïnstalleerd

>[!CAUTION]
>
>Wanneer u een pakket installeert, kan bestaande inhoud worden overschreven of verwijderd. Upload een pakket alleen als u zeker weet dat de benodigde inhoud niet wordt verwijderd of overschreven.
>
>Als u de inhoud of de invloed van een pakket wilt zien, kunt u:
>
>* Voer een testinstallatie van de verpakking uit zonder de inhoud te wijzigen:\
   >  Open het pakket (klik op het pictogram of de naam van het pakket) en klik **Testen installeren**.
   >
   >
* Zie een lijst met pakketinhoud:\
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
   >  Gebruik de het menuoptie van Componenten van de console OSGi om `com.day.cq.workflow.launcher.impl.WorkflowLauncherImpl` te deactiveren.
   >
   >
* Vervolgens activeert u de WorkflowLauncher opnieuw wanneer de installatie is voltooid.
>
>
Als u de WorkflowLauncher deactiveert, zorgt u ervoor dat het framework voor het importeren van middelen de elementen niet (onbedoeld) manipuleert bij de installatie.

1. Navigeer in Pakketbeheer naar het pakket dat u wilt installeren.

   Een **Install** knoop wordt getoond aan de kant van Pakketten die nog niet geïnstalleerd zijn.

   >[!NOTE]
   >
   >U kunt het pakket ook openen door op het bijbehorende pictogram te klikken om de knop **Installeren** daar te openen.

1. Klik **Installeren** om de installatie te starten. In een dialoogvenster wordt bevestiging gevraagd en worden alle aangebrachte wijzigingen vermeld. Wanneer gebeëindigd klik **Close** op de dialoog.

   Het woord **Installed** verschijnt naast het pakket nadat het is geïnstalleerd.

### Uploaden en installeren op basis van bestandssysteem {#file-system-based-upload-and-installation}

U kunt pakketten op een andere manier naar uw exemplaar uploaden en installeren. In uw dossiersysteem, hebt u een `crx-quicksart` omslag naast uw jar en `license.properties` dossier. U moet een map maken met de naam `install` onder `crx-quickstart`. Dan heb je iets als dit: `<aem_home>/crx-quickstart/install`

In deze installatiemap kunt u uw pakketten rechtstreeks toevoegen. Deze worden automatisch geüpload en geïnstalleerd op uw exemplaar. Wanneer het wordt gedaan, kunt u de pakketten in de Manager van het Pakket zien.

Als uw instantie wordt uitgevoerd en u een pakket aan de map `install` toevoegt, wordt het uploaden en de installatie op de instantie direct gestart. Als de instantie niet wordt uitgevoerd, worden de pakketten die u in de map `install` plaatst, bij het opstarten in alfabetische volgorde geïnstalleerd.

>[!NOTE]
>
>U kunt dit ook doen voordat u de instantie voor de eerste keer start. Hieronder moet u de map `crx-quickstart` handmatig maken, de map `install` maken en de pakketten daar plaatsen. Wanneer u uw exemplaar vervolgens voor het eerst start, worden de pakketten in alfabetische volgorde geïnstalleerd.

### Pakketten {#uninstalling-packages} verwijderen

Met AEM kunt u pakketten verwijderen. Deze actie keert de inhoud van de bewaarplaats terug die aan de momentopname wordt beïnvloed die onmiddellijk voorafgaand aan de pakketinstallatie wordt gemaakt.

>[!NOTE]
>
>Na de installatie wordt een pakket met momentopnamen gemaakt dat de inhoud bevat die wordt overschreven.
>
>Dit pakket wordt opnieuw geïnstalleerd wanneer u het pakket verwijdert.

1. Navigeer in Pakketbeheer naar het pakket dat u wilt verwijderen.
1. Klik op het pakketpictogram van het pakket dat u wilt verwijderen.
1. Klik op **Verwijderen** om de inhoud van dit pakket uit de opslagplaats te verwijderen. In een dialoogvenster wordt bevestiging gevraagd en worden alle aangebrachte wijzigingen vermeld. Wanneer gebeëindigd klik **Close** op de dialoog.

### Pakketten {#deleting-packages} verwijderen

Een pakket verwijderen uit de lijst(en) in Package Manager:

>[!NOTE]
>
>De geïnstalleerde bestanden/knooppunten uit het pakket worden **niet** verwijderd.

1. Vouw in de **Tools**-console de map **Packages** uit om het pakket weer te geven in het rechterdeelvenster.

1. Klik op het pakket dat u wilt verwijderen, zodat het wordt gemarkeerd en vervolgens op een van de volgende manieren:

   * Klik **Delete** in het toolbarmenu.
   * Klik met de rechtermuisknop en selecteer **Delete**.

   ![packagesdelete](assets/packagesdelete.png)

1. AEM vraagt om bevestiging dat u het pakket wilt schrappen. Klik **OK** om de verwijdering te bevestigen.

>[!CAUTION]
>
>Als dit pakket al is geïnstalleerd, wordt de *geïnstalleerde*-inhoud **not** verwijderd.

### Pakketten {#replicating-packages} dupliceren

Kopieer de inhoud van een pakket en installeer het naar de publicatie-instantie:

1. Navigeer in **Pakketbeheer** naar het pakket dat u wilt repliceren.

1. Klik op het pictogram of de naam van het pakket dat u wilt repliceren om het uit te vouwen.
1. Selecteer **Repliceren** in het vervolgkeuzemenu **Meer** op de werkbalk.

## Package Share {#package-share}

Het Aandeel van het Pakket is een gecentraliseerde server die openbaar wordt gemaakt om inhoud-Pakketten te delen.

Met Pakket delen kunt u deze pakketten downloaden, waaronder officiële hotfixes, functiesets, updates of voorbeeldinhoud die door andere gebruikers is gegenereerd.

U kunt pakketten ook uploaden en delen binnen uw bedrijf.

### Toegang tot pakket delen {#access-to-package-share}

Er is geen anonieme toegang tot het Aandeel van het Pakket; dat wil zeggen dat alleen geregistreerde gebruikers pakketten mogen weergeven, downloaden en uploaden.

De toegang tot het Aandeel van het Pakket is beschikbaar voor onze partners en klanten. Er moeten registratiegegevens worden ingediend om toegangsrechten te kunnen toewijzen.

Toegang krijgen tot delen pakket:

* [Aanmelden gebruiken op pagina](#signing-in-to-package-share)
* De eerste keer dat u de aanmeldpagina gebruikt, moet u:

   * [Registreren voor een Adobe-](#registering-for-package-share) id en/of uw bestaande Adobe ID  [valideren](#validating-your-adobe-id)
   * zodat uw [Pakket delen-account](#package-share-account) kan worden gemaakt

>[!NOTE]
>
>Om het even welke gebruiker van het Aandeel van het Pakket die niet aan een klant is toegewezen, moet zich bij een gemeenschap aansluiten om die middelen te zien door **toetreden** naast het pakket te klikken deelt login.

#### Aanmelden bij Delen van pakket {#signing-in-to-package-share}

1. Klik in het AEM welkomstscherm op **Tools** -> **Implementatie**
1. Selecteer vervolgens **Delen van pakket**. U moet:

   * aanmelden bij uw Adobe ID
   * [Een Adobe ID maken](#registering-for-package-share)

   >[!NOTE]
   >
   >De eerste keer dat u zich aanmeldt bij uw Adobe ID, moet u de [validatie van uw e-mailadres](#validating-your-adobe-id) voltooien.

   >[!NOTE]
   >
   >Als u uw wachtwoord bent vergeten, gebruikt u **Problemen met aanmelden?** in het dialoogvenster Aanmelden.

#### Uw Adobe ID {#validating-your-adobe-id} valideren

De eerste keer dat u zich aanmeldt bij Delen via pakket met uw Adobe ID, wordt uw e-mailadres gevalideerd.

1. U ontvangt een e-mail met een koppeling.
1. Klik op deze koppeling.
1. Er wordt een webpagina geopend.

   De handeling waarbij deze webpagina wordt geopend, wordt uitgevoerd als validatie.

1. Aanmelden gaat door.

1. U ontvangt een e-mail met een koppeling.
1. Klik op deze koppeling.
1. Er wordt een webpagina geopend. De handeling waarbij deze webpagina wordt geopend, wordt uitgevoerd als validatie.
1. Aanmelden gaat door.

#### Registreren voor delen pakket {#registering-for-package-share}

Als u toegang tot het Delen van pakketten nodig hebt, moet u zich registreren voor een Adobe ID:

* De [Inlogpagina voor delen van pakketten](#signing-in-to-package-share) biedt een koppeling voor het registreren van een Adobe ID.
* U kunt zich vanuit bepaalde Adobe-desktopsoftware registreren voor een Adobe ID.
* U kunt zich ook online registreren op [Adobe Sign op pagina](https://www.adobe.com/cfusion/membership/index.cfm?nf=1&amp;nl=1).

Een Adobe ID kan worden gemaakt door het volgende op te geven:

* uw e-mailadres
* een wachtwoord naar keuze
* aanvullende informatie zoals uw naam en land van verblijf

#### Account voor delen pakket {#package-share-account}

De geldigheid van de toepassing wordt gecontroleerd voordat:

* Uw gebruikersaccount is gemaakt met de vereiste/toegestane machtigingen.
* Je account wordt toegevoegd aan de groep van je bedrijf.

>[!NOTE]
>
>Een gebruiker van één van onze partnerbedrijven kan ook een lid van zijn/haar klantengroepen zijn.

#### Netwerkoverwegingen {#network-considerations}

**IPv6**

U kunt problemen ervaren wanneer het proberen om tot het Aandeel van het Pakket van een zuivere milieu toegang te hebben IPv6.

Dit komt doordat pakketshare service is die wordt gehost op een server, wat betekent dat uw verbinding tot stand wordt gebracht via verschillende netwerken op internet. Er kan niet worden gegarandeerd dat alle aangesloten netwerken IPv6 ondersteunen; als niet de verbinding zou kunnen ontbreken.

Om deze kwestie te vermijden, kunt u tot het Aandeel van het Pakket van een IPv4 netwerk toegang hebben, het pakket downloaden en dan het uploaden aan het milieu IPv6.

**HTTP-proxy**

Delen van pakket is momenteel niet beschikbaar als uw bedrijf een http-proxy uitvoert waarvoor verificatie is vereist.

Delen van pakketten is alleen beschikbaar als uw AEM server toegang heeft tot internet zonder dat verificatie is vereist. Om de volmacht voor alle diensten te vormen die de HTTP- cliënt (met inbegrip van pakketaandeel) gebruiken de [OSGi configuratie van de Client 3.1 van de Commons van de Dag Cliënt van HTTP 3.1 bundel](/help/sites-deploying/osgi-configuration-settings.md).

### Binnen pakket delen {#inside-package-share}

In de pakketten van het Aandeel van het Pakket worden geschikt in boomsubstructuren:

* Adobe pakketten verstrekt door Adobe.
* Gedeelde pakketten die door andere bedrijven zijn geleverd en door Adobe zijn gepubliceerd.
* Uw bedrijfspakketten die privé zijn.

![chlimage_1-346](assets/chlimage_1-346.png)

### Pakketten zoeken en filteren {#searching-and-filtering-packages}

Delen via pakket biedt een zoekbalk die u kunt gebruiken voor het zoeken naar specifieke trefwoorden of tags. Trefwoorden en tags ondersteunen meerdere waarden.

* Als u naar meerdere trefwoorden wilt zoeken, moet u elk trefwoord door een spatie scheiden.
* Als u naar meerdere tags wilt zoeken, moet u elk label in de pakketstructuur selecteren.

U kunt de voorwaardelijke operator ook wijzigen van OR in AND aan de rechterkant van de filteroverzichtbalk.

### Pakketten downloaden en installeren vanuit pakketdeling {#downloading-and-installing-packages-from-package-share}

Om pakketten van het Aandeel van het Pakket te downloaden en hen op uw lokale instantie te installeren, is het gemakkelijker om tot het Aandeel van het Pakket van uw AEM instantie toegang te hebben. Hiermee wordt het pakket gedownload en onmiddellijk geregistreerd in uw Package Manager, vanwaar het kan worden geïnstalleerd.

1. Van het AEM Welkome scherm, klik **Hulpmiddelen**, dan uitgezocht **Deel van het Pakket** om de pagina van het Aandeel van het Pakket te openen.
1. Meld u aan bij Pakket delen met uw accountgegevens. De landingspagina wordt weergegeven met een lijst met de map Adobe, de map Gedeeld en een specifieke pagina voor uw bedrijf.

   >[!NOTE]
   >
   >Voordat u pakketten begint te downloaden van Package Share, moet u ervoor zorgen dat u de [vereiste toegang hebt](#access-to-package-share).

1. Navigeer naar het pakket dat u wilt downloaden en klik op **Downloaden**.

1. Ga terug of navigeer aan **de Manager van het Pakket** op uw AEM instantie. Navigeer vervolgens naar het pakket dat u net hebt gedownload.

   >[!NOTE]
   >
   >Als u het pakket wilt zoeken dat u hebt gedownload, volgt u hetzelfde pad als in Pakket delen. Bijvoorbeeld, als u een pakket van de volgende weg in het Aandeel van het Pakket downloadt:
   >
   >**Pakketten**  >  **Openbaar**  >  **Hotfixes**
   Vervolgens wordt het pakket in Package Manager op uw lokale instantie ook weergegeven onder:
   **Pakketten**  >  **Openbaar**  >  **Hotfixes**

1. Klik **Installeren** om het pakket te installeren op uw lokale AEM.

   >[!NOTE]
   Als het pakket al op uw instantie is geïnstalleerd, wordt de **Installed**-indicator naast het pakket weergegeven in plaats van de **Install**-knop.

   >[!CAUTION]
   Door een pakket te installeren, kan bestaande inhoud in de opslagplaats worden overschreven. Daarom adviseren wij dat u **Test eerst installeert** uitvoert. Op deze manier kunt u controleren of de inhoud van het pakket conflicten oplevert met uw bestaande inhoud.

### Pakketten downloaden naar uw bestandssysteem vanuit pakketdeling {#downloading-packages-to-your-file-system-from-package-share}

[Het downloaden en ](#downloading-and-installing-packages-from-package-share) installeren is heel handig, maar u kunt het pakket desgewenst ook downloaden en opslaan in uw lokale bestandssysteem:

1. Klik in Pakket delen op het pictogram of de naam van het pakket.
1. Klik op het tabblad **Middelen**.
1. Klik **Downloaden naar schijf**.

### Een pakket {#uploading-a-package} uploaden

Met het Aandeel van het Pakket, kunt u pakketten uploaden aan uw bedrijf-intern gebied van pakketaandeel. Hierdoor kunnen ze worden gedeeld binnen uw bedrijf.

Deze pakketten zijn *niet* beschikbaar aan de algemene AEM gemeenschap, maar zijn beschikbaar aan alle gebruikers die bij uw bedrijf worden geregistreerd.

Om pakketten te uploaden uw bedrijf-interne Delen van het Pakket:

>[!CAUTION]
Als u een pakket wilt uploaden naar Package Share, moet u eerst een groepsmap maken die naar uw bedrijf in uw lokale pakketbeheer wordt genoemd. Bijvoorbeeld geometrixx. Alle pakketten die voor delen moeten worden geüpload, moeten in deze groepsmap worden geplaatst.
Pakketten in de thuislijst van Package Manager of in andere mappen kunnen niet worden gedeeld.

1. Open **Pakketbeheer** en navigeer naar het pakket dat u wilt uploaden.

1. Klik op het pakketpictogram om het te openen.
1. Klik **Delen** om het dialoogvenster voor het uploaden van het pakket naar Delen in pakket te openen.
1. Als u nog niet bent aangemeld bij Delen van pakket, moet u uw aanmeldingsgegevens invoeren.

   Wanneer u bent aangemeld, geeft AEM details weer over het te uploaden pakket:

   ![chlimage_1-347](assets/chlimage_1-347.png)

1. Klik **Delen** om het pakket te uploaden naar het interne Delen van het pakket van uw bedrijf.

   AEM geeft de status weer en geeft aan wanneer het pakket klaar is met uploaden, waarna u op **x** (rechterbovenhoek) kunt klikken om het venster **Pakket delen** te sluiten.

1. Nadat het uploaden is voltooid, kunt u naar de interne map van uw bedrijf navigeren om het pakket te zien dat u net hebt gedeeld.

>[!NOTE]
Als u een pakket wilt wijzigen dat beschikbaar is in Package Share, moet u het downloaden, opnieuw samenstellen en vervolgens opnieuw uploaden naar Package Share.

### Een pakket {#deleting-a-package} verwijderen

U kunt alleen pakketten verwijderen die u hebt geüpload door als volgt te werk te gaan:

1. Controleer in uw bedrijfsstructuur de pakketgroep die het pakket bevat.
1. Klik op het pakket.
1. Klik op de knop Verwijderen.

   ![](do-not-localize/chlimage_1-30.png)

1. Klik **Verwijderen** om te bevestigen dat u het pakket wilt verwijderen.

### Pakketten semiprivé maken {#making-packages-semi-private}

U kunt pakketten delen buiten uw organisatie, maar niet openbaar. Deze pakketten worden als semi-particulier beschouwd. Als u deze semi-private pakketten wilt delen, hebt u hulp nodig van Adobe Support. Om dit te doen, open een kaartje met de Steun van Adobe die om een pakket verzoekt wordt ter beschikking gesteld buiten uw organisatie. Ze vragen je om een lijst met Adobe ID die je toegang wilt geven tot je pakketten.

