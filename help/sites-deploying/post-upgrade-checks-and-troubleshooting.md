---
title: Controles en probleemoplossing na upgrade
seo-title: Post Upgrade Checks and Troubleshooting
description: Leer hoe te om kwesties problemen op te lossen die na een verbetering zouden kunnen verschijnen.
seo-description: Learn how to troubleshoot issues that might appear after an upgrade.
uuid: 3f83e8fc-1c45-4ef0-b8da-d29ff483d3d5
contentOwner: sarchiz
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: upgrading
content-type: reference
discoiquuid: bc8c9aa2-f669-41f3-a526-6146ff5cf0cd
feature: Upgrading
exl-id: edd6e933-59ed-4d7e-8934-7e2ec485cfb9
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1907'
ht-degree: 0%

---

# Controles en probleemoplossing na upgrade{#post-upgrade-checks-and-troubleshooting}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Controles na upgrade {#post-upgrade-checks}

Na de [Upgrade op locatie](/help/sites-deploying/in-place-upgrade.md) de volgende activiteiten moeten worden uitgevoerd om de upgrade af te ronden . Men veronderstelt AEM met 6.4 jar is begonnen en dat de promotiecode basis is opgesteld.

* [Logbestanden controleren voor een upgrade](#verify-logs-for-upgrade-success)

* [OSGi-bundels verifiëren](#verify-osgi-bundles)

* [Oak-versie verifiëren](#verify-oak-version)

* [Inspect de map PreUpgradeBackup](#inspect-preupgradebackup-folder)

* [Eerste validatie van pagina&#39;s](#initial-validation-of-pages)
* [AEM servicepacks toepassen](#apply-aem-service-packs)

* [AEM migreren](#migrate-aem-features)

* [Configuraties voor gepland onderhoud controleren](#verify-scheduled-maintenance-configurations)

* [Replication-agents inschakelen](#enable-replication-agents)

* [Aangepaste geplande taken inschakelen](#enable-custom-scheduled-jobs)

* [Testplan uitvoeren](#execute-test-plan)

### Logboeken controleren voor upgrade voltooid {#verify-logs-for-upgrade-success}

**upgrade.log**

In het verleden was voor het inspecteren van de status van uw instantie na de upgrade zorgvuldige inspectie vereist van verschillende logbestanden, onderdelen van de opslagplaats en het startpad. Het genereren van een rapport na de upgrade kan u helpen defecte upgrades te detecteren voordat u live gaat.

Het belangrijkste doel van deze functie is om de behoefte aan handmatige interpretatie of complexe parseringslogica over veelvoudige eindpunten te verminderen die worden vereist om het succes van een verbetering te kwalificeren. De oplossing is bedoeld om ondubbelzinnige informatie te verschaffen aan externe automatiseringssystemen die reageren op het welslagen of de vastgestelde mislukking van een update.

Meer specifiek zorgt het ervoor dat:

* De mislukkingen van de verbetering die door het verbeteringskader worden ontdekt kunnen in één enkel verbeteringsrapport worden gecentraliseerd;
* Het verbeteringsrapport bevat indicatoren voor noodzakelijke handmatige interventie.

Hiervoor zijn wijzigingen aangebracht in de manier waarop logbestanden worden gegenereerd in het dialoogvenster `upgrade.log` bestand.

Hier is een steekproefrapport dat geen fouten tijdens verbetering toont:

![1487887443006](assets/1487887443006.png)

Hier is een steekproefrapport dat een bundel toont die niet tijdens het verbeteringsproces werd geïnstalleerd:

![1487887532730](assets/1487887532730.png)

**error.log**

error.log zou zorgvuldig tijdens en na de aanvang van AEM moeten worden herzien gebruikend de jar van de doelversie. Alle waarschuwingen of fouten moeten worden herzien. In het algemeen is het beter om op kwesties aan het begin van het logboek te zoeken. Fouten die zich later in het logbestand voordoen, kunnen in feite bijwerkingen zijn van een hoofdoorzaak die vroeg in het bestand wordt aangeroepen. Als zich herhaalde fouten en waarschuwingen voordoen, zie hieronder voor [Problemen analyseren met de upgrade](/help/sites-deploying/post-upgrade-checks-and-troubleshooting.md#analyzing-issues-with-upgrade).

### OSGi-bundels verifiëren {#verify-osgi-bundles}

Navigeer aan de console OSGi `/system/console/bundles` en controleer of er geen bundels zijn gestart. Als een bundel zich in een geïnstalleerde status bevindt, raadpleegt u de `error.log` om het hoofdprobleem te bepalen.

### Oak-versie verifiëren {#verify-oak-version}

Na de upgrade ziet u dat de versie van eikel is bijgewerkt naar **1.8.2.**. Om de versie te verifiëren van de eik navigeer aan de console OSGi en bekijk de versie verbonden aan de bundels van de eik: eiken kern, eiken komma&#39;s, eiken segmentteer.

### Inspect PreUpgradeBackup-map {#inspect-preupgradebackup-folder}

Tijdens de upgrade probeert AEM een back-up te maken van aanpassingen en deze onder `/var/upgrade/PreUpgradeBackup/<time-stamp-of-upgrade>`. Als u deze map in CRXDE Lite wilt weergeven, moet u mogelijk [tijdelijk CRXDE Lite inschakelen](/help/sites-administering/enabling-crxde-lite.md).

De map met het tijdstempel moet een eigenschap hebben met de naam `mergeStatus` met een waarde van `COMPLETED`. De **te verwerken** de map moet leeg zijn en de **overschreven** de knoop wijst op welke knopen tijdens de verbetering werden beschreven. Inhoud onder de **overblijfselen** de knoop wijst op inhoud die niet veilig tijdens de verbetering kon worden samengevoegd. Als uw implementatie afhankelijk is van een van de onderliggende knooppunten (en nog niet is geïnstalleerd door het aangepaste codepakket), moeten deze handmatig worden samengevoegd.

Schakel CRXDE Lite uit na deze bewerking als u een werkgebied of productieomgeving hebt.

### Eerste validatie van pagina&#39;s {#initial-validation-of-pages}

Voer een eerste validatie uit op meerdere pagina&#39;s in AEM. Als u een auteur-omgeving wilt upgraden, opent u de startpagina en de welkomstpagina ( `/aem/start.html`, `/libs/cq/core/content/welcome.html`). In zowel auteur- als publicatieomgevingen worden enkele toepassingspagina&#39;s en rooktests geopend die correct worden weergegeven. Als er problemen optreden raadpleegt u `error.log` om problemen op te lossen.

### AEM servicepacks toepassen {#apply-aem-service-packs}

Pas alle relevante AEM 6.4 Service Packs toe als deze zijn vrijgegeven.

### AEM migreren {#migrate-aem-features}

Verscheidene eigenschappen in AEM vereisen extra stappen na de verbetering. Een volledige lijst van deze functies en stappen om ze in AEM 6.4 te migreren vindt u op de [Code en aanpassingen bijwerken](/help/sites-deploying/upgrading-code-and-customizations.md) pagina.

### Configuraties voor gepland onderhoud controleren {#verify-scheduled-maintenance-configurations}

#### Opruiming gegevensopslag inschakelen {#enable-data-store-garbage-collection}

Als het gebruiken van een Opslag van de Gegevens van het Dossier ervoor zorgt dat de taak van de Inzameling van de Opslag van Gegevens wordt toegelaten en aan de Wekelijkse lijst van het Onderhoud toegevoegd. Instructies worden beschreven [hier](/help/sites-administering/data-store-garbage-collection.md).

>[!NOTE]
>
>Dit wordt niet geadviseerd voor de installaties van de douanegegevensopslag van S3 of wanneer het gebruiken van een gedeelde gegevensopslag.

#### Onlinerevisie-opruiming inschakelen {#enable-online-revision-cleanup}

Als u MongoMK of de nieuwe TarMK-segmentindeling gebruikt, zorgt u ervoor dat de taak Opruimen voor revisie is ingeschakeld en wordt toegevoegd aan de lijst Dagelijks onderhoud. Instructies omgeven [hier](/help/sites-deploying/revision-cleanup.md).

### Testplan uitvoeren {#execute-test-plan}

Gedetailleerd testplan uitvoeren ten opzichte van zoals gedefinieerd [Code en aanpassingen bijwerken](/help/sites-deploying/upgrading-code-and-customizations.md) onder de **Testprocedure** sectie.

### Replication-agents inschakelen {#enable-replication-agents}

Zodra publicatiemilieu volledig is bevorderd en bevestigd, laat replicatieagenten op het Milieu van de Auteur toe. Verifieer dat de agenten met respectieve Publish instanties kunnen verbinden. Zie [Upgradeprocedure](/help/sites-deploying/upgrade-procedure.md) voor meer informatie over de volgorde van gebeurtenissen.

### Aangepaste geplande taken inschakelen {#enable-custom-scheduled-jobs}

Om het even welke geplande banen als deel van de codebasis kunnen op dit punt worden toegelaten.

## Problemen analyseren met de upgrade {#analyzing-issues-with-upgrade}

Deze sectie bevat sommige probleemscenario&#39;s één langs de verbeteringsprocedure aan AEM 6.4 zou kunnen worden geconfronteerd.

Deze scenario&#39;s zouden moeten helpen om de worteloorzaak van kwesties met betrekking tot verbetering te volgen en zouden moeten helpen om project of productspecifieke kwesties te identificeren.

### Dynamic Media Cloud Configuration opnieuw maken na upgrade {#dynamic-media-cloud-configuration}

Na een upgrade naar AEM 6.4 van een eerdere versie, is de configuratie van Dynamic Media Cloud vanuit eerdere instellingen mogelijk niet meer toegankelijk via de AEM 6.4 TouchUI. U lost dit probleem op door CRXDE Lite te gebruiken om de eerdere instellingen te verwijderen en vervolgens een nieuwe Dynamic Media Cloud Configuration te maken. Zie ook [Herstructurering van de Dynamic Media-opslagplaats in AEM 6.4](/help/sites-deploying/dynamicmedia-repository-restructuring-in-aem-6-4.md).

### Migratie opslagplaats mislukt  {#repository-migration-failing-}

De gegevensmigratie van CRX2 naar eiken moet haalbaar zijn voor elk scenario dat begint met Broninstanties op basis van CQ 5.4. Zorg ervoor dat u de upgrade-instructies in dit document, waaronder de voorbereiding van de `repository.xml`zorgt u ervoor dat er geen aangepaste authenticator via JAAS wordt gestart en dat de instantie op inconsistenties is gecontroleerd voordat de migratie wordt gestart.

Als de migratie nog ontbreekt kunt u uitzoeken wat de worteloorzaak door is te inspecteren `upgrade.log`. Als het probleem nog niet bekend is, meld dit dan aan Customer Support.

### De upgrade is niet uitgevoerd {#the-upgrade-did-not-run}

Voordat u de voorbereidingsstappen start, moet u de **bron** instantie eerst door deze uit te voeren met de opdracht java -jar aem-quickstart.jar. Dit is vereist om ervoor te zorgen dat het bestand quickstart.properties op de juiste wijze wordt gegenereerd. Als deze ontbreekt, werkt de upgrade niet. U kunt ook controleren of het bestand aanwezig is door onder te kijken `crx-quickstart/conf` in de installatiemap van de broninstantie. Wanneer u AEM start om de upgrade uit te voeren, moet deze worden uitgevoerd met de opdracht java -jar aem-quickstart.jar. Het opstarten vanaf een beginscript start niet AEM in de upgrademodus.

### Pakketten en pakketten kunnen niet worden bijgewerkt  {#packages-and-bundles-fail-to-update-}

Als pakketten niet tijdens de upgrade worden geïnstalleerd, worden de bundels in de pakketten ook niet bijgewerkt. Deze categorie van kwesties wordt gewoonlijk veroorzaakt door wanconfiguratie van de gegevensopslag. Zij worden ook weergegeven als **FOUT** en **WAARSCHUWING** berichten in error.log. Aangezien in de meeste van deze gevallen standaardlogin kan ontbreken om te werken, kunt u CRXDE direct gebruiken om de configuratieproblemen te inspecteren en te vinden.

### Sommige AEM Bundels schakelen niet naar de Actieve Staat {#some-aem-bundles-are-not-switching-to-the-active-state}

Als bundels niet beginnen zou u om het even welke ontevreden gebiedsdelen moeten controleren.

Als dit probleem zich voordoet, maar het is gebaseerd op een mislukte pakketinstallatie die ertoe heeft geleid dat bundels niet werden bijgewerkt, worden zij onverenigbaar geacht voor de nieuwe versie. Voor meer informatie over hoe te om dit problemen op te lossen, zie **Pakketten en pakketten kunnen niet worden bijgewerkt** hierboven.

Het wordt ook aanbevolen de bundellijst van een nieuwe AEM 6.4-instantie te vergelijken met de bijgewerkte versie om de bundels te detecteren die niet zijn bijgewerkt. Hierdoor wordt het bereik vergroot van wat er moet worden gezocht in het dialoogvenster `error.log`.

### Aangepaste bundels die niet overschakelen op de actieve staat {#custom-bundles-not-switching-to-the-active-state}

Als uw aangepaste bundels niet naar de actieve status overschakelen, is het zeer waarschijnlijk dat er code is die geen wijziging-API importeert. Dit zal meestal leiden tot ontevreden afhankelijkheden.

API die is verwijderd, moet worden gemarkeerd als afgekeurd in een van de vorige releases. In dit bericht vindt u mogelijk instructies over een directe migratie van uw code. Adobe is bedoeld voor semantische versioning waar mogelijk, zodat de versies kunnen aangeven dat er wijzigingen zijn opgetreden.

Het is ook het beste om te controleren of de verandering die het probleem heeft veroorzaakt absoluut noodzakelijk was en het zo niet terug te draaien. Controleer ook of de versieverhoging van de pakketexport meer dan nodig is, na strikte semantische versiebewerking.

### Gebruikersinterface van onjuist functionerend Platform {#malfunctioning-platform-ui}

In het geval van bepaalde functionaliteit UI die niet behoorlijk na de verbetering werkt, zou u eerst douaneoverlays van de interface moeten controleren. Sommige structuren zijn mogelijk gewijzigd en de overlay moet mogelijk worden bijgewerkt of is verouderd.

Controleer vervolgens of er JavaScript-fouten optreden die kunnen worden bijgehouden bij aangepaste, toegevoegde extensies die zijn gekoppeld aan clientbibliotheken. Hetzelfde kan gelden voor aangepaste CSS die problemen kan veroorzaken voor de AEM-indeling.

Tot slot controleer misconfiguration dat Javascript niet zou kunnen behandelen. Dit is meestal het geval bij onjuist gedeactiveerde extensies.

### Onjuist functionerende aangepaste componenten, sjablonen of UI-extensies {#malfunctioning-custom-components-templates-or-ui-extensions}

In de meeste gevallen, zijn de worteloorzaken voor deze kwesties het zelfde als voor bundels die niet begonnen zijn of pakketten die niet met het enige verschil worden geïnstalleerd dat de kwesties beginnen op te duiken wanneer eerst het gebruiken van de componenten.

De manier om met onjuiste aangepaste code om te gaan is eerst rooktests uit te voeren om de oorzaak te achterhalen. Kijk eens naar de aanbevelingen in deze [link] van het artikel voor het corrigeren ervan.

### Ontbrekende aanpassingen onder enz. {#missing-customizations-under-etc}

`/apps` en `/libs` worden goed behandeld door de verbetering, maar veranderingen onder `/etc` moet mogelijk handmatig worden hersteld vanaf `/var/upgrade/PreUpgradeBackup` na de upgrade. Controleer deze locatie op alle inhoud die handmatig moet worden samengevoegd.

### De parameters error.log en upgrade.log analyseren {#analyzing-the-error-log-and-upgrade-log}

In de meeste gevallen moeten de logboeken worden geraadpleegd voor fouten om de oorzaak van een probleem te vinden. In het geval van upgrades is het echter ook nodig om afhankelijkheidskwesties te controleren, aangezien oude bundels mogelijk niet correct worden bijgewerkt.

De beste manier om dit te doen is onderaan error.log door van alle berichten te verwijderen die van geen verband met de kwestie worden verwacht u onder ogen ziet. U kunt dit doen door middel van hulpmiddel zoals grep, door te gebruiken:

```shell
grep -v UnrelatedErrorString
```

Sommige foutberichten zijn mogelijk niet direct expliciet. In dit geval kunt u door de context te bekijken waarin de fouten zich voordoen, beter begrijpen waar de fout is gemaakt. U kunt de fout scheiden met:

* `grep -B` voor het toevoegen van regels vóór de fout;

of

* `grep -A` voor het toevoegen van regels na.

In een paar gevallen kunnen er ook fouten worden gevonden in WARN-berichten, omdat er geldige gevallen kunnen zijn die tot deze status leiden en de toepassing niet altijd kan beslissen of dit een werkelijke fout is. Zorg ervoor dat u deze berichten ook raadpleegt.

### Contact opnemen met Adobe-ondersteuning {#contacting-adobe-support}

Als u het advies op deze pagina hebt doorgenomen en nog steeds problemen ziet, kunt u contact opnemen met de Adobe Support. Om zoveel mogelijk informatie aan de steuningenieur te verstrekken die aan uw geval werkt, te zorgen gelieve ervoor om het upgrade.log dossier van uw verbetering te omvatten.
