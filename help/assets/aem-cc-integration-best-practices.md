---
title: Best practices op het gebied van Experience Manager- en Creative Cloud-integratie
description: Tips en trucs om een [!DNL Experience Manager] implementatie met Adobe Creative Cloud om workflows voor de overdracht van bedrijfsmiddelen te stroomlijnen en maximale efficiëntie te bereiken
contentOwner: AG
feature: Collaboration,Adobe Asset Link,Desktop App
role: User,Admin
exl-id: cb9bea05-3359-4fb4-b935-59e522a5f387
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '3524'
ht-degree: 14%

---

# [!DNL Experience Manager] en [!DNL Creative Cloud] best practices voor integratie {#aem-and-creative-cloud-integration-best-practices}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

<!-- TBD: Reconcile with 6.5 article that's ahead of this article now in terms of content streamlining and structuring.
-->

Adobe Experience Manager Assets is een DAM-oplossing (Digital Asset Management) die met Adobe Creative Cloud kan worden geïntegreerd om DAM-gebruikers te helpen samen te werken met creatieve teams en de samenwerking bij het maken van inhoud te stroomlijnen.

Adobe Creative Cloud biedt creatieve teams een ecosysteem van oplossingen en services om ze te helpen digitale middelen te maken. Het omvat desktop- en mobiele toepassingen, cloudservices zoals opslag met desktopsynchronisatie of webervaring, en markten zoals Adobe Stock.

Lees verder om te weten welke integraties u kunt kiezen tussen desktop en DAM op bedrijfsniveau op basis van uw gebruiksscenario en wat de bijbehorende beste werkwijzen zijn voor de verbindingsworkflows.

>[!NOTE]
>
>Map delen vanuit [!DNL Experience Manager] aan Creative Cloud is afgekeurd en wordt niet meer in deze handleiding behandeld. Adobe raadt u aan nieuwere mogelijkheden te gebruiken, zoals [Adobe-itemkoppeling](https://helpx.adobe.com/enterprise/using/adobe-asset-link.html) of [[!DNL Experience Manager] bureaubladtoepassing](https://experienceleague.adobe.com/docs/experience-manager-desktop-app/using/introduction.html) creatieve gebruikers toegang bieden tot middelen die worden beheerd in [!DNL Experience Manager].

## De behoeften van de samenwerking van creatieven, verkopers, en gebruikers DAM {#collaboration-needs-of-creatives-marketers-and-dam-users}

| Vereisten | Hoofdletters gebruiken | Betrokken oppervlakken |
|---|---|---|
| Ervaring voor creatieve producten op desktopcomputers vereenvoudigen | Toegang tot middelen van een DAM stroomlijnen ([!DNL Assets]) voor creatieve professionals, of meer in het algemeen, gebruikers op desktopcomputers die werken in toepassingen voor het maken van native elementen. Ze hebben een eenvoudige en eenvoudige manier nodig om wijzigingen te detecteren, te gebruiken (openen), te bewerken en op te slaan in [!DNL Experience Manager]en uploadt u nieuwe bestanden. | Win- of Mac-bureaublad; Creative Cloud-apps |
| Middelen van Adobe Stock van hoge kwaliteit en gebruiksklaar maken | Marketers helpen het proces voor het maken van inhoud te versnellen door hulp te bieden bij het aanschaffen en detecteren van bedrijfsmiddelen. Creatieve professionals gebruiken de goedgekeurde middelen direct vanuit hun creatieve gereedschappen. | [!DNL Assets]; Adobe Stock Marketplace metagegevensvelden |
| Elementen distribueren en delen door organisaties | De interne afdelingen/de lokale takken en de externe partners, de distributeurs, en de agentschappen gebruiken de goedgekeurde activa die door de ouderorganisatie worden gedeeld. De organisatie wil de gemaakte middelen veilig en naadloos delen voor breder hergebruik. | Brand Portal, Commentaar voor het delen van bedrijfsmiddelen |

## Adobe-aanbod ter ondersteuning van de behoefte aan samenwerking {#adobe-offerings-to-support-the-collaboration-need}

| Waardevoorstel voor de betreffende personen | Adobe-aanbieding | Betrokken oppervlakken |
|---|---|---|
| Creatieve gebruikers ontdekken elementen van [!DNL Experience Manager], openen en gebruiken, wijzigingen bewerken en uploaden naar [!DNL Experience Manager]en uploadt u nieuwe bestanden naar [!DNL Experience Manager], zonder Creative Cloud-apps te verlaten. | [Adobe-itemkoppeling](https://helpx.adobe.com/enterprise/using/adobe-asset-link.html) | Photoshop, Illustrator en InDesign |
| Zakelijke gebruikers vereenvoudigen het openen en gebruiken van middelen, het bewerken en uploaden van wijzigingen in [!DNL Experience Manager]en nieuwe bestanden uploaden naar [!DNL Experience Manager] in de desktopomgeving. Ze gebruiken een algemene integratie om elk elementtype in de native bureaubladtoepassing te openen, inclusief niet-Adobe toepassingen. | [[!DNL Experience Manager] bureaubladtoepassing](https://experienceleague.adobe.com/docs/experience-manager-desktop-app/using/using.html) | [!DNL Experience Manager] bureaubladtoepassing op Win- en Mac-bureaublad |
| Marketers en zakelijke gebruikers detecteren, voorvertonen, licentiëren en opslaan de Adobe Stock-middelen vanuit [!DNL Experience Manager]. Gelicentieerde en opgeslagen middelen bieden geselecteerde Adobe Stock-metagegevens voor beter beheer. | [Integratie van Experience Manager en Adobe Stock](aem-assets-adobe-stock.md) | [!DNL Experience Manager] webinterface |

Dit artikel richt zich hoofdzakelijk op de eerste twee aspecten van de samenwerkingsbehoeften. Distributie en sourcing van assets op schaal wordt kort als gebruiksscenario genoemd. Overweeg Adobe Brand Portal of Asset Share Commons voor dergelijke oplossingen. Alternatieve oplossingen, zoals [Brand Portal](https://helpx.adobe.com/nl/experience-manager/brand-portal/user-guide.html), oplossingen die op [Commentaar voor het delen van bedrijfsmiddelen](https://adobe-marketing-cloud.github.io/asset-share-commons/) componenten, [Delen van koppeling](/help/assets/link-sharing.md), gebruiken [Experience Manager Assets](/help/assets/managing-assets-touch-ui.md) moeten worden herzien op basis van specifieke eisen.

![Creative Cloud-verbindingen voor [!DNL Experience Manager]: Bepalen welke mogelijkheid moet worden gebruikt](assets/creative-connections-aem.png)

<!-- 
## Terms and definitions {#terms-and-definitions}

The terms used in this document may have a different meaning in other contexts. In particular, the following terms pertaining to the digital asset lifecycle are used when referring to workflows between a creative professional's desktop and DAM:

* **Work-in-progress or creative work-in-progress (WIP):** A phase in asset lifecycle where an asset undergoes multiple changes and is typically not yet ready to be shared with broader teams.
* **Creative-ready assets:** Assets that are ready to be shared with a broader team, or have been  selected / approved  by the creative team for sharing with marketing or LOB teams.
* **Asset approvals:** The approval process that runs for assets already uploaded to DAM, which typically includes brand approvals, legal approvals, and so on.
* **Final asset:** An asset that has gone through all  approvals/metadata  tagging and is ready to be used by the broader team. Such an asset is stored in DAM and made available to all (or all interested) users. It can be used in marketing channels or by creative teams to create designs.
* **Minor asset  update/change:** A quick and small change to a digital asset. It is often made in response to a retouching or minor editing request, asset review, or approval (for example, reposition, change text size, adjust saturation/brightness, color, and so on).
* **Major asset  update/change:** A change to a digital asset that requires considerable work, and sometimes must be done over a longer period of time. It typically includes multiple changes. The asset must be saved multiple times while being updated. Major asset updates typically cause the asset to enter a WIP stage.
* **DAM:** Digital asset management. In this document, it is synonymous with Experience Manager Assets, unless specifically mentioned otherwise.
* **Creative user:** A creative professional, who creates digital assets using Creative Cloud apps and services. In some cases, a creative user may be a member of a creative team who may use Creative Cloud, but does not create digital assets (like a creative director or creative team manager).
* **DAM user:** A typical user of a DAM system. Depending on the organization, a DAM user can be a marketing or a non-marketing user, for example a Line-of-Business (LOB) user, librarian, sales person, and so on.
-->

### Toewijzing van gebruiksgevallen

| Hoofdletters gebruiken | [!DNL Experience Manager] bureaubladtoepassing | Map delen | Andere oplossingen |
|---|---|---|---|
| Deel een kleiner aantal (1) DAM-middelen met Creative User | ✔ ✔ | ✔ |  |
| Groter aantal (2) DAM-middelen delen met Creative-gebruiker | ✔✔ | ✘ | [Brand Portal](https://experienceleague.adobe.com/docs/experience-manager-brand-portal/using/home.html) <br> [Delen van middelen](assets-finder-editor.md) |
| DAM-middelen delen met gebruikers die toegang hebben tot DAM | ✔✔ | ✔ | [Delen van koppeling](link-sharing.md) |
| DAM-middelen delen met gebruikers die geen toegang hebben tot DAM | ✘ | ✔✔ | [Brand Portal](https://experienceleague.adobe.com/docs/experience-manager-brand-portal/using/home.html) <br> [Delen van middelen](assets-finder-editor.md) |
| Kleiner aantal/volume middelen opslaan naar DAM | ✔✔ | ✔ | [Web UI Uploaden](managing-assets-touch-ui.md) |
| Groter aantal elementen opslaan naar DAM (3) | ✔✔ | ✘ | [Web UI Uploaden](managing-assets-touch-ui.md) <br> Aangepast script/gereedschap |
| Grote aantallen activa migreren naar DAM | ✘ | ✘ | [Migratiehandleiding](assets-migration-guide.md) |
| Snel middelen openen op het bureaublad | ✔✔ | ✘ |  |
| Snel middelen openen en wijzigen op desktop | ✔✔ | ✘ |  |

De legenda voor de symbolen:

* ✔ ✔: voorkeursoplossing
* ✔: aanvaardbare oplossing
* ✘: moet niet worden gebruikt voor de gebruikszaak

Aanvullende opmerkingen:

* (1) Kleiner aantal activa: bijvoorbeeld een kleine set elementen die verband houden met een project of campagne
* (2) Groter aantal activa: bijvoorbeeld alle goedgekeurde elementen in de organisatie
* (3) Gebruik [!DNL Experience Manager] mapfunctie voor uploaden bureaubladapp

Om het gebruik van middelen te steunen, zouden andere oplossingen moeten worden overwogen:

* [Brand Portal](https://helpx.adobe.com/nl/experience-manager/brand-portal/user-guide.html) voor configureerbaar, toe:voegen-aan SaaS aan [!DNL Experience Manager] Elementen om elementen te publiceren.
* Aangepaste oplossingen worden gemaakt op basis van [Commentaar voor het delen van bedrijfsmiddelen](https://adobe-marketing-cloud.github.io/asset-share-commons/) code base.
* [!DNL Experience Manager] [delen van koppeling](/help/assets/link-sharing.md) om elementen ad hoc te delen met behulp van koppelingen.
* [[!DNL Experience Manager] Elementen van webinterface](/help/assets/managing-assets-touch-ui.md) met gebieden voor externe partijen die door [!DNL Experience Manager] De opstelling van het Toegangsbeheer en met noodzakelijke aanpassingen van de IT/netwerkconfiguratie, die deze externe gebruikers toegang geven tot [!DNL Experience Manager].

## Belangrijkste concepten en gebruiksgevallen {#key-concepts-and-use-cases}

### Verklarende woordenlijst {#glossary-of-common-terms}

* **Werk in uitvoering of creatief werk in uitvoering (WIP):** Een fase in de levenscyclus van assets waarbij een asset meerdere wijzigingen ondergaat en doorgaans nog niet klaar is om te worden gedeeld met grotere teams.
* **Creatieve assets:** Assets die klaar zijn om te worden gedeeld met een groter team, of die zijn geselecteerd/goedgekeurd door het creatieve team om te delen met marketing- of LOB-teams.
* **Goedkeuring van assets:** Het goedkeuringsproces dat wordt uitgevoerd voor assets die reeds naar DAM zijn geüpload, en dat typisch merkgoedkeuringen, wettelijke goedkeuringen, enz. omvat.
* **Definitieve asset:** Een asset die alle goedkeuringen/metadatatagging heeft doorlopen en klaar is om door het grotere team te worden gebruikt. Een dergelijke asset wordt opgeslagen in DAM en beschikbaar gesteld aan alle (geïnteresseerde) gebruikers. Deze kan in marketingkanalen of door creatieve teams worden gebruikt om ontwerpen te maken.
* **Kleine update/wijziging van assets:** Een snelle en kleine wijziging in een digitale asset. Deze wordt vaak uitgevoerd als reactie op een retoucheerverzoek of een verzoek om kleine bewerkingen, een assetrevisie of goedkeuring (bijvoorbeeld om de positie te wijzigen, de tekstgrootte te wijzigen, de verzadiging/helderheid en kleur aan te passen, enz.).
* **Belangrijke update/wijziging van assets:** Een verandering in een digitale asset die aanzienlijk werk vereist, en soms over een langere periode moet worden uitgevoerd. Dit omvat doorgaans meerdere wijzigingen. De asset moet tijdens het bijwerken meerdere keren worden opgeslagen. De belangrijkste assetupdates leiden er doorgaans toe dat de asset een WIP-status krijgt.
* **DAM:** Beheer van digitale assets. In dit document is het synoniem met [!DNL Experience Manager Assets], tenzij uitdrukkelijk anders vermeld.
* **Creatieve gebruiker:** Een creatieve professional die digitale assets maakt met Creative Cloud-apps en -services. In sommige gevallen is een creatieve gebruiker lid van een creatief team dat mogelijk Creative Cloud gebruikt, maar geen digitale assets maakt (zoals een creatieve directeur of een creatieve teammanager).
* **DAM-gebruiker:** Een typische gebruiker van een DAM-systeem. Afhankelijk van de organisatie kan een DAM-gebruiker een marketing- of niet-marketinggebruiker zijn, bijvoorbeeld een LOB-gebruiker (Line-of-Business), bibliothecaris, verkoopmedewerker, enz. zijn.

### Overwegingen bij gebruik [!DNL Experience Manager] en Creative Cloud-integratie {#considerations-when-using-aem-and-creative-cloud-integration}

* Zie [best practices voor bureaubladtoepassingen](https://experienceleague.adobe.com/docs/experience-manager-desktop-app/using/troubleshoot.html#best-practices-to-prevent-troubles)
* Zie [Adobe Stock-integratie](aem-assets-adobe-stock.md)
* Zie [Adobe-itemkoppeling](https://helpx.adobe.com/enterprise/using/adobe-asset-link.html)

Dit is een korte samenvatting van beste praktijken voor Experience Manager en Creative Cloud integratie. Lees de rest van dit document voor een gedetailleerd begrip hiervan.

* **Voor creatieve gebruikers die in Photoshop, InDesign of Illustrator werken:** Adobe Asset Link biedt de beste gebruikerservaring, zoals een schone verwerking van het werk in uitvoering op assets die zijn uitgecheckt bij [!DNL Experience Manager]
* **Voor het vereenvoudigen van de toegang tot middelen van de Desktop voor om het even welke generische dossierformaat of toepassing:** gebruiken [!DNL Experience Manager] bureaubladtoepassing
* **Begrijpen waarom en wanneer assets in DAM moeten worden opgeslagen:** Updates die ter beschikking moeten worden gesteld aan een groter team in uw organisatie
* **Houd rekening met het volume van de gedeelde assets:** Als u gebruikmaakt van assetdistributie, kunnen governance en beveiliging de belangrijkste aspecten zijn. Overweeg om tools te gebruiken die bedoeld zijn om governance en beveiliging op grote schaal toe te passen, zoals de Brand Portal.
* **De levenscyclus van assets begrijpen:** Begrijp hoe assets in uw organisatie worden verwerkt door verschillende teams
* **Correct en regelmatig opslaan van assets:** Adobe Asset Link doet dit voor u met PS, AI, ID. Voer voor andere applicaties geen taken in uitvoering uit in een toegewezen/gedeelde map, tenzij u alle wijzigingen in DAM nodig hebt

### Toegang tot Adobe Stock-middelen van [!DNL Assets] {#access-to-adobe-stock-assets-from-aem-assets}

[[!DNL Experience Manager] en Adobe Stock-integratie](/help/assets/aem-assets-adobe-stock.md) verstrekt [!DNL Experience Manager] gebruikers met de mogelijkheid om middelen van Adobe Stock te zoeken, voor te vertonen, in licentie te geven en op te slaan in [!DNL Experience Manager]. Bij gelicentieerde en opgeslagen Adobe Stock-elementen zijn de metagegevens van de Stock geselecteerd. Deze kunnen worden gebruikt om met extra filters naar deze elementen te zoeken.

Een paar belangrijke punten over deze integratie:

* Wanneer elementen uit Adobe-voorraad worden opgeslagen naar [!DNL Experience Manager]worden ze regelmatig [!DNL Experience Manager] Elementen, met binair opgeslagen naar de [!DNL Experience Manager] opslagplaats. Sommige metagegevens die betrekking hebben op Adobe Stock, worden voor het element opgeslagen in [!DNL Experience Manager]Anders ziet het innameproces er hetzelfde uit als voor elk ander bestand. Als slimme tags bijvoorbeeld actief zijn, worden de tags bij het opslaan aan deze elementen toegevoegd.
* Het element dat is opgeslagen naar [!DNL Experience Manager] is een kopie, geen link terug naar Adobe Stock.

**Werken met middelen die zijn opgeslagen van Adobe Stock in [!DNL Experience Manager] in Creative Cloud**. Deze integratie is onafhankelijk van Adobe Asset Link, maar Adobe Asset Link herkent deze elementen die op die manier uit Stock zijn opgeslagen en geeft aanvullende metagegevens en voorraadpictogrammen voor deze elementen weer in de UI voor de uitbreiding van de Adobe Asset Link in Photoshop, Illustrator of InDesign. De bestanden zijn beschikbaar voor bladeren, openen enzovoort, omdat ze regelmatig zijn [!DNL Experience Manager] elementen wanneer deze worden opgeslagen naar [!DNL Experience Manager].
Creatieve gebruikers die werken in Creative Cloud-apps met de extensie Adobe Asset Link, hebben niet alleen toegang tot middelen met een licentie van Adobe Stock, maar ook tot [!DNL Experience Manager]kunt u ook het deelvenster Creative Cloud-bibliotheken gebruiken om Adobe Stock-elementen te zoeken, voor te vertonen en te licentiëren.
Activa van Adobe Stock in licentie gegeven en opgeslagen in [!DNL Experience Manager] beschikbaar worden voor de bredere teams die toegang hebben tot [!DNL Experience Manager] De plaatsing van activa, terwijl de creatieve vergunningen van activa van Adobe Stock via het paneel van de Bibliotheken van de Creative Cloud hen ter beschikking stellen slechts door gebrek in hun Creative Cloud rekening.

<!-- 
TBD: A condensed version of the below content is better placed in the Adobe DAM article.
-->

## Elementen opslaan in een DAM {#about-storing-assets-in-a-dam}

Om een efficiënte werkstroom tussen creatieve en marketing/lijn-van-zaken (LOB) teams te ontwerpen en de beste steunmogelijkheden te kiezen, is het belangrijk om te begrijpen wanneer en waarom de activa in DAM worden opgeslagen.

### Waarom elementen zijn opgeslagen in DAM {#why-assets-are-stored-in-dam}

Door middelen in DAM op te slaan, zijn ze gemakkelijk toegankelijk en te vinden. Het zorgt ervoor dat de activa door talrijke gebruikers over de organisatie of het ecosysteem kunnen worden gebruikt, dat partners, klanten, etc. omvat.

De meeste organisaties kiezen ervoor om activa slechts op te slaan die voor de stroomafwaartse marketing/LOB processen relevant zijn (het publiceren aan kanalen zoals Webkanaal via [!DNL Experience Manager] Sites of andere kanalen die door Adobe Experience Cloud, Advertising Cloud worden gediend, en door Analytics Cloud worden gemeten, die aan gebruikers/partners, etc. verstrekken). Bovendien slaan organisaties activa op die aan een overzicht/goedkeuringsprocedure in DAM kunnen worden onderworpen. Op deze manier slaat DAM vooral activa op die een hoge kans hebben om te worden gebruikt, en vermijdt het opslaan van niet-actieve activa.

De opslag van activa is ook onderworpen aan technische overwegingen en middelgebruik. DAM verleent de extra diensten rond opgeslagen activa, met inbegrip van het halen van meta-gegevens, het versioning, het produceren van voorproeven/het transcoderen, het beheren van verwijzingen, en het toevoegen van toegangsbeheerinformatie. Deze diensten verbruiken extra tijd en infrastructuurmiddelen.

Vaak is het niet wenselijk om alle elementen en updates op te slaan. Bijvoorbeeld, als de updates aan specifieke activa van slechte kwaliteit zijn en bovenmatige middelen verbruiken, kunnen de activa niet in DAM worden opgeslagen.

### Wanneer elementen zijn opgeslagen in DAM {#when-assets-are-stored-in-dam}

Creatieve teams (en organisaties) zijn gewoonlijk niet geïnteresseerd in het opslaan van middelen in elke fase van de levenscyclus van de middelen. In de volgende gevallen worden bijvoorbeeld geen elementen opgeslagen:

* Activa die nog moeten worden afgerond of die moeten worden getest
* Middelen die niet de cyclus van het creatieve/interne teamoverzicht doorstaan
* Vergeleken met de middelen in kwestie, heeft het team betere kandidaten om hun werk aan externe teams te vertegenwoordigen

Gewoonlijk worden de volgende klassenelementen opgeslagen in DAM:

* Activa die een bepaalde looptijd hebben bereikt en die klaar worden geacht om te worden gedeeld
* Elementen die vooraf zijn geselecteerd door het creatieve team
* Specifieke activaformaten die door marketing, afhankelijk van een specifiek contract of een overeenkomst (bijvoorbeeld JPG dossiers die van RAW dossiers, TIFF/beelden van PSD originelen worden omgezet worden gebruikt of worden gevraagd)

### Wanneer updates van elementen worden opgeslagen in DAM {#when-updates-to-assets-are-stored-in-dam}

Normaliter moeten alleen updates van middelen die relevant zijn voor de bredere reeks DAM-gebruikers in DAM worden opgeslagen. Hiermee zorgt u ervoor dat gebruikers (marketing en soortgelijke functies) alleen relevante versies in de tijdlijn van de DAM-middelen zien.

Doorgaans zijn er wijzigingen die betrekking hebben op belangrijke mijlpalen in de levenscyclus van de middelen. Het eerste creatieve bedrijfsmiddel of een officiële update op basis van een verzoek/revisie van het creatieve team moet bijvoorbeeld in DAM worden opgeslagen en gecontroleerd.

De update van het creatieve team voor revisie door het marketingteam na een verzoek om wijziging van het bestaande middel in DAM is een voorbeeld van een relevante update. Het zou in DAM voor verdere verwijzing of voor het terugkeren naar de vorige versie moeten worden opgeslagen en worden versioned.

Hieronder volgen voorbeelden van updates die doorgaans niet relevant zijn:

* Vroege versies van elementen die zijn geüpload voordat ze klaar zijn voor marketingcontrole
* Veelvoorkomende creatieve wijzigingen in het bedrijfsmiddel in de aan de gang zijnde fase voordat het creatieve team besluit dat het bedrijfsmiddel klaar is

### Toegang van gebruikers tot DAM {#user-access-to-dam}

[!DNL Experience Manager] Elementen ondersteunen twee soorten gebruikers op basis van hun toegang tot de [!DNL Experience Manager] Implementatie van middelen. Doorgaans hebben gebruikers binnen het bedrijfsnetwerk (firewall) rechtstreeks toegang tot DAM. Andere gebruikers buiten het ondernemingsnetwerk zouden geen directe toegang hebben. Het gebruikerstype bepaalt welke integraties vanuit technisch oogpunt kunnen worden gebruikt.

#### Creatieve gebruikers met directe toegang tot DAM {#creative-users-with-direct-access-to-dam}

Doorgaans hebben interne creatieve teams of agentschappen/creatieve professionals die aan het interne netwerk zijn toegewezen, toegang tot het DAM-exemplaar, waaronder [!DNL Experience Manager] aanmelden.

In dergelijke gevallen [!DNL Experience Manager] bureaubladtoepassing biedt eenvoudige toegang tot definitieve/goedgekeurde middelen en biedt u de mogelijkheid creatieve middelen op te slaan in DAM.

#### Creatieve gebruikers zonder toegang tot DAM {#creative-users-without-access-to-dam}

Externe agentschappen en freelancers zonder directe toegang tot het DAM-exemplaar hebben mogelijk toegang tot goedgekeurde activa nodig of willen hun nieuwe ontwerpen toevoegen aan het DAM.

In dergelijke gevallen kunt u de opdracht [!DNL Experience Manager]/Creative Cloud integratie om de workflow te verbeteren. De voorwaarde is dat creatieve gebruikers een Adobe ID hebben en een Creative Cloud-account met opslagservice.

Gebruik de volgende strategieën om toegang te verlenen tot definitieve/goedgekeurde middelen:

* U kunt als volgt toegang verlenen tot een groot aantal elementen: Gebruiken [[!DNL Experience Manager] Assets Brand Portal](https://experienceleague.adobe.com/docs/experience-manager-brand-portal/using/home.html)of de implementatie door de klant van [Delen van middelen](assets-finder-editor.md) op [!DNL Experience Manager] infrastructuur publiceren

* U kunt als volgt toegang tot enkele elementen bieden: [!DNL Experience Manager] het delen van mappen met Adobe Creative Cloud kan naast [!DNL Experience Manager] Assets Brand Portal of Asset Share. Er zijn bepaalde beperkingen met betrekking tot deze integratie, die in dit artikel nader worden beschreven.

### Gevallen gebruiken {#use-cases}

De volgende gebruiksgevallen beschrijven verschillende typen workflows tussen DAM en het bureaublad van de ontwerper.

#### Nieuwe ontwerpen maken met middelen van DAM {#creating-new-designs-using-assets-from-dam}

Het volgende diagram illustreert de levenscyclus van digitale elementen. Hierin wordt beschreven hoe creatieve gebruikers en DAM-gebruikers (marketers, LOB-gebruikers) bestaande middelen benutten en gebruiken om meer middelen te maken en deze ter goedkeuring verzenden.

![chlimage_1-301](assets/chlimage_1-301.png)

De levenscyclus van de middelen omvat de volgende stadia:

1. Goedgekeurde middelen delen op creatieve desktop: De definitieve activa van DAM worden ter beschikking gesteld aan de creatieve gebruiker (op Desktop)
1. Een nieuw ontwerp maken (creatief digitaal materiaal): Een nieuw dossier wordt opgeslagen in het werk-lopende gebied (WIP).
1. Gebruik (plaats) goedgekeurde elementen in een nieuw ontwerp: De creatieve gebruiker maakt een nieuw middel met behulp van bestaande goedgekeurde middelen in Creative Cloud-apps
1. WIP-updates vaak opslaan: De creatieve gebruiker herhaalt snel en slaat het dossier regelmatig op. In dit stadium kan de creatieve gebruiker samenwerken met anderen, maar de vaak opgeslagen updates zijn gewoonlijk niet van belang voor DAM-gebruikers.
1. Het element bereikt de creatieve kant-en-klare status en wordt opgeslagen in de map Creative Ready
1. Asset-update: Middelen bijwerken of een nieuw bestand is beschikbaar voor de gebruikers in DAM
1. Activa worden geproduceerd: Dit is een proces DAM, dat afhankelijk van de organisatie, het etiketteren, goedkeuring, en het veranderen van toegangsbeheer zou kunnen omvatten. In dit stadium wordt het middel als definitief beschouwd en kan het worden gebruikt door bredere teams die DAM gebruiken. Het kan ook door creatieve gebruikers worden gebruikt om andere activa tot stand te brengen.

Hier volgen enkele algemene aanbevelingen voor het beheer van middelen via dit proces:

* Gebruik een speciaal opslaggebied/systeem, zoals de gesynchroniseerde map met Adobe Creative Cloud Assets, voor de WIP-bestanden: Frequente updates die niet relevant zijn voor DAM-gebruikers kunnen het best worden uitgevoerd door een toegewijd systeem, en niet vanuit binnen [!DNL Experience Manager] Elementen. WIP-elementen kunnen met Adobe Creative Cloud-bureaubladtoepassing worden gesynchroniseerd op een lokale schijf, opgeslagen op een lokale opslaglocatie, enzovoort.
* Gebruik afzonderlijke mappen/shares voor definitieve elementen en elementen die naar DAM zijn geüpload: voor de duidelijkheid moeten de uiteindelijke middelen een eigen toegewezen/gedeelde map hebben (&quot;Definitief&quot; voorbeeld hierboven) en de middelen die naar DAM moeten worden geüpload, moeten een eigen map hebben (&quot;Creative Ready&quot;)

#### Bestaande elementen die worden beheerd in DAM wijzigen {#changing-existing-assets-managed-in-dam}

In sommige gevallen moeten de middelen in DAM mogelijk worden gewijzigd. Voorbeelden zijn:

* Verzoek om wijzigingen van activa van de evaluatie en goedkeuring gedaan in [!DNL Experience Manager] Activa
* Belangrijke updates van bestaande definitieve elementen
* Snelle bewerkingen voor een bestaand bestand (vooral voordat het definitief wordt goedgekeurd)

In dergelijke gevallen [!DNL Experience Manager] bureaubladtoepassing biedt de eenvoudigste manier om deze bewerkingen uit te voeren.

![chlimage_1-302](assets/chlimage_1-302.png)

Hier is de stroom van gebeurtenissen die in het diagram worden getoond:

<!-- TBD for formatting. 
This article will get fixed automatically when 6.5 content is ported to it.
And 6.5 content will be ported after updating it for [!DNL Experience Manager] desktop app 2.0 best practices.
And it will be updated for DA2.0 best practices after 6.5 repo is available for writers to edit content in.
-->

* **1:** U kunt de middelen van DAM delen op het bureaublad of deze rechtstreeks openen op het bureaublad in de toepassing waarin u ze kiest (bijvoorbeeld Adobe Photoshop, enzovoort). Uitchecken wordt aanbevolen als u het bestand wilt vergrendelen.
* **2:** Kleine update: Bewerk het bestand en sla de wijzigingen op.
* Alternatieve stroom naar stap 2

   * **A:** Belangrijke update: Als voor het bestand een uitgebreide set wijzigingen nodig is, moet het bestand periodiek worden opgeslagen en worden gekopieerd naar een WIP-map of -gebied.
   * **B:** Het bestand wordt verder bewerkt in de WIP-mappen. De opgeslagen wijzigingen worden niet gesynchroniseerd met de versie in DAM
   * **C:** Nadat de updates zijn voltooid, wordt het bestand weer gekopieerd of opgeslagen naar de toegewezen map

* **3:** Updates van bedrijfsmiddelen worden weergegeven in DAM. Schakel het element in om het te ontgrendelen.
* **4:** Activa worden geproduceerd.

Hier volgen enkele algemene aanbevelingen voor het beheer van middelen gedurende dit proces:

* Vermijd direct het opslaan van een dossier dat u van een netwerkaandeel in kaart bracht [!DNL Experience Manager] bureaubladtoepassing, tenzij u kleine wijzigingen in het bestand hebt aangebracht.
* Kopieer het bestand naar een aparte WIP-map als u er aanvullende wijzigingen in wilt aanbrengen, het bestand tijdelijk wilt opslaan of wilt samenwerken met het Creative-team.

#### Bulkupload naar DAM {#bulk-upload-to-dam}

In sommige gevallen moet u wellicht een groter aantal bestanden tegelijkertijd uploaden naar DAM, bijvoorbeeld:

* Resultaten van foto&#39;s of grotere projecten uploaden
* Door creatieve bureaus geleverde activa uploaden
* Geselecteerde elementen uploaden vanaf een grotere set als de selectie buiten DAM is uitgevoerd

Deze beschrijving verwijst naar het operationeel uploaden van bestanden (bijvoorbeeld elke week of met elke foto, enz.) als een normaal onderdeel van de workflow van de desktopgebruiker. De migratie van grote activa wordt hier niet behandeld.

U kunt de volgende mogelijkheden benutten als u elementen bulksgewijs wilt uploaden:

* Als u grote/hiërarchische mappen wilt uploaden, gebruikt u [!DNL Experience Manager] bureaubladtoepassing, die een [Map uploaden](https://helpx.adobe.com/experience-manager/desktop-app/aem-desktop-app.html#bulkupload) gebruiken. U kunt ook hiërarchische mapstructuren uploaden. Elementen worden op de achtergrond geüpload en zijn daarom niet gekoppeld aan een webbrowsersessie
* Als u enkele bestanden uit één map wilt uploaden, sleept u deze rechtstreeks van het bureaublad naar de webinterface of gebruikt u de optie Maken in het dialoogvenster [!DNL Experience Manager] Elementenwebinterface.

>[!NOTE]
>
>Afhankelijk van uw bedrijfsvereisten kunt u ook aangepaste uploader gebruiken.

#### Digitale middelen rechtstreeks vanaf het bureaublad beheren {#managing-digital-assets-directly-from-desktop}

Als u de Delen van het Dossier van het Netwerk gebruikt om digitale activa te beheren, enkel gebruikend het netwerkaandeel in kaart gebracht door [!DNL Experience Manager] bureaubladtoepassing kan worden beschouwd als een handige vervanging. Houd er rekening mee dat wanneer u overschakelt van gedeelde netwerkbestanden [!DNL Experience Manager] Web UI verstrekt een rijke reeks mogelijkheden van het Beheer van Digitale Middelen die veel verder gaan dan wat op een netwerkaandeel (onderzoek, inzamelingen, meta-gegevens, samenwerking, voorproeven, enz.) mogelijk is, en [!DNL Experience Manager] bureaubladtoepassing biedt een handige koppeling om de DAM-opslagplaats aan de serverzijde te verbinden met het werk op het bureaublad.

Vermijd het gebruik [!DNL Experience Manager] bureaubladtoepassing om elementen rechtstreeks te beheren in het netwerkaandeel van [!DNL Experience Manager] Elementen. Vermijd bijvoorbeeld het gebruik [!DNL Experience Manager] bureaubladtoepassing om meerdere bestanden te verplaatsen/kopiëren. Gebruik in plaats daarvan de [!DNL Experience Manager] Hiermee wordt de webinterface van middelen gebruikt om mappen van Finder/Explorer naar het netwerk te slepen. Kies hiervoor [!DNL Experience Manager] Functie voor uploaden naar middelenmap.

#### Migratie van middelen {#asset-migration}

Als u de migratie van middelen van een bestaand systeem naar een nieuw systeem wilt plannen en uitvoeren, of een grote hoeveelheid op servers opgeslagen middelen wilt migreren, raadpleegt u de [Migratiehandleiding](/help/assets/assets-migration-guide.md). [!DNL Experience Manager] bureaubladtoepassing en [!DNL Experience Manager] Creative Cloud-integratie dergelijke migraties niet ondersteunt. Vanwege de grote hoeveelheden in te nemen elementen en de extra vereisten met betrekking tot het in kaart brengen van metagegevens, transformatie en opname, moeten migraties met verschillende gereedschappen en benaderingen worden afgehandeld.

>[!MORELIKETHIS]
>
>* [Adobe-itemkoppeling](https://helpx.adobe.com/in/enterprise/admin-guide.html/in/enterprise/using/adobe-asset-link.ug.html)
>* [[!DNL Experience Manager] best practices voor bureaubladtoepassingen](https://experienceleague.adobe.com/docs/experience-manager-desktop-app/using/archive/best-practices-for-v1.html)
>* [[!DNL Experience Manager] Brand Portal](https://experienceleague.adobe.com/docs/experience-manager-brand-portal/using/introduction/brand-portal.html)
>* [[!DNL Experience Manager] en Adobe Stock-integratie](aem-assets-adobe-stock.md)

