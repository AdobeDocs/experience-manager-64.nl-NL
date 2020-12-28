---
title: Opmerkingen bij de 3D-release AEM
seo-title: Opmerkingen bij de 3D-release AEM
description: Release-aantekeningen die specifiek zijn voor 3D-inhoud in Adobe Experience Manager Assets.
seo-description: Release-aantekeningen die specifiek zijn voor 3D-inhoud in Adobe Experience Manager Assets.
uuid: 6675951f-86f0-4ec5-97e4-d247f6faf913
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4
topic-tags: release-notes, 3D
content-type: reference
discoiquuid: 9789d031-fb7e-415a-a9c3-8b8fde978238
translation-type: tm+mt
source-git-commit: 9710c9931b4f17073c712f5869a1843c1d99ee8e
workflow-type: tm+mt
source-wordcount: '1983'
ht-degree: 0%

---


# Opmerkingen bij de 3D-release AEM {#aem-d-release-notes}

>[!IMPORTANT]
>
>Het AEM 3D-functiepakket in AEM 6.4 wordt niet meer ondersteund. Adobe raadt u aan de functie 3D-elementen in [AEM te gebruiken als een Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/dynamicmedia/assets-3d.html) of [AEM 6.5.3 of hoger.](https://docs.adobe.com/content/help/en/experience-manager-65/assets/dynamic/assets-3d.html)

AEM-6.4-DynamicMedia-3D versie 3.1.0 (10 oktober 2018)

Met het AEM 3D-functiepakket kunt u ondersteuning bieden voor 3D-inhoud in AEM Assets. Het biedt mogelijkheden voor het uploaden, beheren, voorvertonen en renderen van 3D-elementen. Ondersteuning voor weergave en rendering is geoptimaliseerd voor afzonderlijke objecten (in plaats van complexe scènes met meerdere objecten).

AEM 3D biedt ondersteuning voor Adobe Dimension- (Dn) en glTF-elementtypen. De implementatie voor deze elementtypen verschilt aanzienlijk van die voor traditionele 3D-typen die in deze documentatie worden beschreven. Zie [Werken met Adobe Dimension-elementen](/help/assets/working-dimension-assets.md).

Ook inbegrepen zijn server-zijintegratie met Autodesk® Maya® (Vensters slechts). Wanneer u Maya installeert en configureert op dezelfde server als AEM, schakelt u ondersteuning in voor systeemeigen Maya-bestandsindelingen, waaronder renderen van hoge kwaliteit met de NVIDIA® plug-in mental ray® standalone voor Maya. Als u 3ds Max op de server installeert en configureert, wordt ondersteuning voor de native .max-bestandsindeling mogelijk.

Zie [Integreren met Autodesk Maya](/help/assets/integrate-maya-with-3d.md).

Zie ook [AEM 3D-elementen installeren en configureren](/help/assets/install-config-3d.md) en [Geavanceerde configuratie-instellingen](/help/assets/advanced-config-3d.md).

Zie ook [Werken met 3D-elementen](/help/assets/assets-3d.md).

## Systeemvereisten {#system-requirements}

**Vereisten**

* AEM 6.4.2 (AEM 6.4 met Service Pack 2)
* Autodesk® FBX® SDK 2016.1.2

**Ondersteunde besturingssystemen**

* Microsoft Windows 2012 Server of hoger
* Apple OS X El Capitan 10.6 of hoger
* RedHat Enterprise Linux 7.3

**Ondersteunde webbrowsers voor AEM Assets**

* Google Chrome 53 of hoger (aanbevolen).
* Apple Safari 9.1 of hoger.
* Firefox 48 of hoger.
* Microsoft Edge 25.10586 of hoger.

Andere browsers bieden mogelijk geen ondersteuning voor het interactief weergeven van 3D-inhoud in AEM. Alleen Google Chrome ondersteunt gegoten schaduwen in Voorvertoning.

**Hardwarevereisten en aanbevelingen**

* CPU - 3D-verwerking en -rendering is zeer veeleisend voor de CPU van een computer. Daarom wordt een hedendaagse server met minimaal acht CPU-cores aanbevolen.
* Geheugen - Een minimum van 32 GB wordt geadviseerd.
* Massaopslag - SSD-opslag met hoge bandbreedte wordt aanbevolen.

   Bij het uploaden worden 3D-elementen geconverteerd naar een eigen indeling voor snel, interactief weergeven. Afhankelijk van het type 3D-element is een opslagruimte van 2 tot 3 maal de grootte van het geüploade 3D-element vereist.

Zie ook [Werken met 3D-elementen](/help/assets/assets-3d.md).

## AEM 3D installeren en configureren {#installing-and-configuring-aem-d}

Zie [AEM 3D](/help/assets/install-config-3d.md) installeren en configureren.

Zie ook [AEM 3D integreren met Autodesk Maya](/help/assets/integrate-maya-with-3d.md) en [AEM 3D integreren met Autodesk 3ds Max](/help/assets/integrating-aem-3d-with-autodesk-3ds-max.md).

## Ondersteunde 3D-bestandsindelingen {#supported-d-file-formats}

| Format | Beschrijving | Platforms | Opmerkingen |
|--- |--- |--- |--- |
| DN | Adobe Dimension | Alles | Hiervoor is toegang tot een conversieservice in de cloud vereist. |
| GLTZ | Zipped gITF | Alles |  |
| GLB | Binaire gITF | Alles | Alleen downloaden (GLB-uitvoeringen worden gemaakt voor DN-elementen). |
| OBJ | Wavefront OBJ 3D | Alles |  |
| FBX | Autodesk FBX (Kaydara Filmbox) | Alles | De Autodesk FBX SDK moet op het knooppunt Auteur zijn geïnstalleerd. |
| MA, MB | Native Autodesk Maya | Alleen Windows | Autodesk Maya is vereist op het knooppunt Auteur om deze bestandsindelingen in te schakelen. Zie [AEM 3D integreren met Autodesk Maya](/help/assets/integrate-maya-with-3d.md). |
| JT | Siemens PLM Open CAD | Alleen Windows | Autodesk Maya is vereist op het knooppunt Auteur om deze bestandsindelingen in te schakelen. Zie [AEM 3D integreren met Autodesk Maya](/help/assets/integrate-maya-with-3d.md). |
| * | Extra 3D-invoerindelingen die door Autodesk Maya worden ondersteund, kunnen worden ingeschakeld. Zie [Extra indelingen inschakelen die worden ondersteund door Maya](/help/assets/integrate-maya-with-3d.md#enabling-additional-formats-supported-by-maya). | Alleen Windows | Autodesk Maya is vereist op het knooppunt Auteur om deze bestandsindelingen in te schakelen. Zie [AEM 3D integreren met Autodesk Maya](/help/assets/integrate-maya-with-3d.md). |
| MAX | Oorspronkelijke Autodesk 3ds Max | Alleen Windows | Autodesk 3ds Max is vereist op het auteurknooppunt om deze bestandsindeling in te schakelen. Zie [AEM 3D integreren met Autodesk 3ds Max](/help/assets/integrating-aem-3d-with-autodesk-3ds-max.md). |

## Verbeteringen en nieuwe functies {#enhancements-and-new-features}

Versie 3.0

* Ondersteuning voor Autodesk 3ds Max native bestandsindeling.
* Verschillende wijzigingen en foutoplossingen verbeteren de stabiliteit, kwaliteit en gebruikerservaring.
* Configuratie-instellingen verplaatst naar `/libs/settings/dam/v3d/`

Versie 3.1

* Beperkte ondersteuning voor de eigen Adobe Dimension-bestandsindeling (.dn).
* Een nieuwe 3D-viewer voor glTF-elementen.
* Een nieuwe interface naar een op cloud gebaseerde, door Adobe beheerde conversieservice die wordt gehost in Amazon AWS. Aanvankelijk, zet deze dienst slechts van formaten Dn in glTF om.

## Beperkingen en bekende problemen {#restrictions-and-known-issues}

### Adobe Dimension-ondersteuning {#adobe-dimension-support}

* Deze versie van AEM3D biedt beperkte ondersteuning voor .dn-bestanden die met Adobe Dimension zijn gemaakt.
* Tijdens uploadverwerking AEM gebruikt u een op cloud gebaseerde, op Adobe gehoste conversieservice om een glTF-uitvoering te maken van het native .dn-bestand. Toegang tot de conversieservice en het selecteren van Amazon AWS-eindpunten is vereist.
* Er is een nieuwe glTF-viewer beschikbaar die het weergeven van Dn-elementen in AEM Assets en op sites/schermen ondersteunt. De ondersteuning voor de fasen in de viewer is nog niet beschikbaar.
* Dn-modellen kunnen IBL-lichten en achtergronden insluiten die worden weergegeven, indien aanwezig. De viewer kan ook standaardbelichting of een standaardachtergrondkleur toepassen, of beide.
* Rendering van hoge kwaliteit voor Dn-elementen is nog niet beschikbaar.
* Afhankelijkheden zoals structuurafbeeldingen zijn ingesloten in Dn-elementen en kunnen niet expliciet in AEM worden beheerd.

### Compatibiliteit {#compatibility}

* **Het lopen als dienst van Vensters wordt niet gesteund (Vensters slechts)**  - dit kan werken maar het is niet getest.
* **Dynamic Media** (  `dynamicmedia-scene7` mode) - Compatibiliteit van AEM3D met de nieuwe Dynamic Media-oplossing die met AEM 6.4 wordt vrijgegeven, wordt nog niet volledig gecontroleerd. Als Dynamic Media en AEM3D samen worden geïmplementeerd, wordt u aangeraden 3D-middelen en hun afhankelijkheden alleen te plaatsen in een gebied van de AEM Assets-opslagplaats dat niet is toegewezen aan Dynamic Media. Deze aanbeveling is vooral van belang voor 32-bits TIFF-bestanden die vereist zijn voor 3D-fasen, maar die niet worden ondersteund door Dynamic Media.

### Algemeen {#general}

* **Sneltoets**  Afhankelijkheden oplossen - Deze sneltoets is beschikbaar in de Kaartweergave op 3D-middelen. De kaarten van activa in de Mening van de Kaart tonen de &quot;Onopgeloste banner van Afhankelijkheden&quot;. Met de sneltoets wordt het tabblad **Basiseigenschappen** geopend in plaats van het tabblad **Afhankelijkheden**. Oplossing: navigeer handmatig naar het tabblad Afhankelijkheden.

* **Werkgebiedkiezer niet beschikbaar**  - 3D-elementen met lichten worden automatisch gecodeerd als 3D-fasen AEM. Er is geen kiezer voor Fases beschikbaar in de gedetailleerde weergave. Als u een 3D-element wilt markeren als een 3D-object, navigeert u naar **Basiseigenschappen**, wijzigt u **Klasse van element** in **3D-object** en klikt u op **Opslaan**.

* **3D-elementen downloaden met afhankelijke en rendities** - Bij het downloaden van 3D-elementen van AEM met  **** optie Afhankelijkheid en  **Vertoning(en)** ingeschakeld, bevat de download niet alleen de uitvoeringen van het primaire 3D-element, maar ook de uitvoeringen van alle afhankelijke personen.

* **Autodesk 3ds Maximale integratie**  - Rendering met 3ds Max wordt momenteel niet ondersteund.

### Beperkingen voor bestandstypen {#file-type-restrictions}

* **Mathematica (.ma)-bestanden**  - Mathematica-bestanden gebruiken hetzelfde achtervoegsel als oorspronkelijke Maya-bestanden. Wanneer het Pak van de Eigenschap wordt geïnstalleerd en het Maya.ma- dossierformaat wordt toegelaten, AEM3D probeert om Mathematica dossiers in te gaan aangezien de dossiers van Maya ontbreken. Bij dergelijke elementen wordt een foutbanner weergegeven in de weergave Kaart.

* **Targa-afbeeldingsbestanden**  (.tga) - Oudere 3D-modelbestanden kunnen verwijzingen naar TGA-bestanden bevatten. Deze indeling wordt niet ondersteund door AEM. Adobe raadt u aan dergelijke bestanden om te zetten in een andere indeling voordat u de 3D-elementen in AEM uploadt.
* **HDR-afbeeldingen**  - HDR-afbeeldingen worden gebruikt voor fases met op afbeeldingen gebaseerde belichting (IBL). Momenteel worden voor dit doel alleen 32-bits TIFF-afbeeldingen ondersteund.
* **32-bits TIFF-afbeeldingen**  - 32-bits TIFF-afbeeldingen worden gebruikt voor fases met op afbeeldingen gebaseerde belichting. AEM ondersteunt het maken van uitvoeringen voor deze elementen niet. Dit leidt tot lege miniaturen en voorvertonen is niet mogelijk. Het element werkt nog steeds correct wanneer het wordt gebruikt in een IBL-fase.
* **Autodesk 3ds Max (.max) dossiers**  - als Autodesk 3ds Max geïnstalleerd en gevormd op de knopen van de Auteur is, AEM de opname en de omzetting van .max dossiers steunt. Het gebruik van .max-bestanden als stadia wordt momenteel niet ondersteund.

### Automatische afhankelijkheidsresolutie {#automatic-dependency-resolution}

* **Onopgeloste dossiergebiedsdelen na upload** - Wanneer 3D activa en hun gebiedsdelen met de zelfde uploadverrichting worden geupload, is het mogelijk dat sommige gebiedsdelen niet automatisch worden opgelost. Dit probleem treedt vaker op als de afhankelijke bestanden groot zijn. U verhelpt dit probleem door toegang te krijgen tot de pagina **Eigenschappen/afhankelijkheden** van het element met onopgeloste afhankelijkheden na het uploaden. De voorheen onopgeloste afhankelijkheden moeten nu worden weergegeven. Klik op **Opslaan** om het element te voltooien. Om dit probleem in de toekomst te voorkomen, kunt u alle afhankelijke personen in een afzonderlijke transactie uploaden voordat u de 3D-objecten uploadt.

* **Hoofdlettergevoeligheid**  - Automatische afhankelijkheidsresolutie probeert bestandsnamen op een hoofdlettergevoelige manier te benaderen. Als de oorspronkelijke afhankelijkheid in het 3D-element bijvoorbeeld `image.jpg` is, wordt de afhankelijkheid omgezet in een element met de naam `Image.jpg`, `image.JPG` of een andere variant van het type case.

### 3D-fasen {#d-stages}

* **Miniaturen voor fases**  - De automatisch gegenereerde miniaturen voor fases geven het werkgebied mogelijk niet correct weer.
* **Werkgebiedgeometrie voor niet-IBL-fasen**  - De renderer Rapid Refine renderer rendeert geen geometrie van stadia met niet-IBL-belichting, inclusief achtergronden en grondvlakken. Een dergelijke geometrie wordt nog steeds redelijk weergegeven in de weergave Details van het element (3D-voorvertoning).

* **FBX-fasen met IBL-belichting**  - U kunt FBX-fasen uploaden met IBL-belichting. De FBX-indeling bevat echter geen bepalingen om de IBL-afbeeldingsnaam over te dragen. Het oplossen van bestandsafhankelijkheden mislukt daarom. De IBL-afbeelding moet na het uploaden handmatig aan het werkgebied worden toegewezen. U kunt dezelfde 32-bits TIFF-afbeelding toewijzen aan de drie afhankelijkheden: **Afbeelding in diffuse belichtingsomgeving**, **Reflectie-omgeving Image** en **Achtergrondomgeving Image**, of er kunnen verschillende afbeeldingen worden toegewezen.

* **Achtergrondafbeelding van IBL-fasen**  - Voor sommige IBL-scènes kan de achtergrondafbeelding van slechte kwaliteit zijn, zoals te helder of te vaag. Om de visuele kwaliteit van de afbeeldingsachtergrond van IBL-fasen te maximaliseren, raadt Adobe u aan een aparte 8-bits JPEG-afbeelding met hoge resolutie voor te bereiden en deze aan het IBL-werkgebied te koppelen als de **achtergrondomgeving Image**.

* **Zwarte afbeelding bij weergave met Maya in een IBL-stadium**  - Dit probleem wordt waarschijnlijk veroorzaakt doordat Maya de IBL-afbeeldingsafhankelijkheid niet vindt omdat de oorspronkelijke IBL-afbeelding waarnaar in het werkgebied wordt verwezen, is vervangen door een afbeelding met een andere naam. Om dit probleem te voorkomen, moet u ervoor zorgen dat ten minste een van de drie afhankelijkheden waarnaar in het Maya IBL-werkgebied wordt verwezen, dezelfde naam heeft als de oorspronkelijke IBL-bestandsverwijzing in het Maya-bestand.
* **Omgekeerde achtergrondafbeelding voor IBL-werkgebied**  - De afbeeldingen voor IBL-fasen worden bewust horizontaal gespiegeld om overeen te komen met het gedrag van de NVIDIA-renderer voor mentale stralen die bij Autodesk Maya wordt geleverd. Oplossing: Draai de afbeeldingen die in Photoshop voor IBL-fasen worden gebruikt voordat u ze uploadt.
* **Helderheid van IBL-fasen**  - De automatische analyse van de IBL-afbeelding kan resulteren in een te donkere of te heldere scène. Als u de helderheid van de belichting van de IBL-fasen wilt aanpassen, navigeert u naar **Basiseigenschappen** en past u de **bright**-waarde van **Omgevingsbelichting** indien nodig aan.

### AEM Sites 3D-component {#aem-sites-d-component}

* **Eén 3D-component per pagina**  - Op dit moment is slechts één instantie van de 3D-component toegestaan op elke webpagina. Als meerdere 3D-componenten aan dezelfde pagina worden toegevoegd, werkt geen van de 3D-componenten correct.
* **3D-weergave ontbreekt bij voorvertonen in sites** . Als u  **** Voorvertoningssites gebruikt, moet de pagina opnieuw in de browser worden geladen om de 3D-viewer volledig te kunnen initialiseren. Dit is geen probleem wanneer u de webpagina rechtstreeks weergeeft (wanneer `edit.html` uit het pad wordt verwijderd) op de knooppunten Auteur of op de knooppunten Publiceren.

* **Modus Volledig scherm niet beschikbaar op iOS-apparaten**  - De knop Volledig scherm is niet beschikbaar op iOS-apparaten, ongeacht de gebruikte browser.

### 3D-inhoud publiceren {#publishing-d-content}

* **Configuratie**  3D-component: u moet het 3D-functiepakket installeren op alle actieve publicatieknooppunten en elk knooppunt moet zijn geconfigureerd met  **CRXDE** Liteto dezelfde configuratieopties bij  `/libs/settings/dam/v3D/WebGLSites`.

* **Ontbrekende structuren, achtergrond of belichting na publicatie**  - Het  **** publicatiemechanisme in AEM Sites publiceert automatisch de primaire afhankelijkheden van de pagina, inclusief het 3D-model en het 3D-werkgebied waarnaar wordt verwezen door de 3D-component. 3D-fasen en 3D-modellen zijn doorgaans afhankelijk van secundaire elementen voor IBL-afbeeldingen en structuurafbeeldingen, die het publicatiemechanisme Sites niet automatisch publiceert. Oplossing: Alle 3D-elementen van Elementen publiceren voordat u de webpagina van Sites publiceert. Dit zorgt ervoor dat alle afhankelijkheden voor 3D-elementen beschikbaar zijn op de publicatieknooppunten.
