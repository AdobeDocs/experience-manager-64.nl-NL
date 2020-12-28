---
title: Veelgestelde vragen AEM
seo-title: AEM 6.4 veelgestelde vragen
description: Gebruik deze veelgestelde vragen om algemene workflows of problemen in AEM te begrijpen, te configureren en op te lossen.
seo-description: Gebruik deze veelgestelde vragen om algemene workflows of problemen in AEM te begrijpen, te configureren en op te lossen.
uuid: af197bcc-2c61-4c64-b781-f24d83c27c82
contentOwner: jsyal
discoiquuid: c66b65af-443f-4fc2-b775-9f4e3c60285a
translation-type: tm+mt
source-git-commit: f5b45b2c8bfcf9d82ddc08b05b5fff22937fa9fd
workflow-type: tm+mt
source-wordcount: '1545'
ht-degree: 0%

---


# Veelgestelde vragen AEM{#aem-faqs}

Volg deze pagina om antwoorden op sommige AEM het oplossen van problemen en configuratiekwesties te krijgen.

## Sites {#sites}

### Hoe vorm ik binair-minder distributie? {#how-do-i-configure-binary-less-distribution}

Binaire distributie zonder beperkingen wordt ondersteund voor implementaties via een gedeelde gegevensopslag en betreft agents die gebruikmaken van de exportfunctie van het Vault Distribution Package (factory PID: `org.apache.sling.distribution.serialization.impl.vlt.VaultDistributionPackageBuilderFactory`) package builder.

Met binair-geen toegelaten wijze, bevatten de verdeelde inhoudspakketten verwijzingen naar binaire getallen eerder dan de daadwerkelijke binaire getallen.

### Hoe laat ik binair-minder distributie toe? {#how-do-i-enable-binary-less-distribution}

Om binair-minder distributie toe te laten, stel met een gedeelde blob opslag op.\
Controleer `useBinaryReferences` bezit in de configuratie OSGI met fabriek PID ( `org.apache.sling.distribution.serialization.impl.vlt.VaultDistributionPackageBuilderFactory`*)* die uw agent gebruikt.

### Hoe kan ik de foutenmeldingen aanpassen terwijl het navigeren van paginahiërarchie in AEM plaatsenconsole? {#how-can-i-customize-the-error-messages-while-navigating-page-hierarchy-in-aem-sites-console}

Controleer het deelvenster Netwerk (van de Chrome-browser) waar een persoonlijke setup (JS) niet is geminiateerd.

Bekijk `Initiator` kolom om te bepalen wat de initiatiefnemer van een verzoek was. Het verstrekt de dossiers en de lijnaantallen van waar de AJAX vraag wordt gemaakt. Later kunt u de functie voor foutafhandeling overtrekken en het foutbericht naar wens wijzigen.

### Hoe te om toestemmingen toe te laten terwijl het creëren van het Exemplaar van de Taal voor tevreden-Auteurs in AEM? {#how-to-enable-permissions-while-creating-language-copy-for-content-authors-in-aem}

Voor het maken van de functie voor het kopiëren van talen hebben inhoudsauteurs machtigingen nodig op de locatie `/content/projects`.

Als de auteurs ook projecten moeten beheren, dan moet de oplossing de auteur aan `project-administrators` groep toevoegen.

### Hoe te om het formaat te veranderen terwijl het creëren van het Exemplaar van de Taal voor een project? {#how-to-change-the-format-while-creating-language-copy-for-a-project}

Creeer een taalwortel en taalexemplaar binnen de wortel, alvorens een vertaalproject tot stand te brengen.

Bijvoorbeeld,\
Creeer een taalwortel bij `/content/geometrixx` met naam als `fr_LU` (en titel als Frans (Luxemburg)). Maak vervolgens een taalkopie van de pagina in het venster Referenties en navigeer naar de optie `Create structure only` in `Create & Translate`. Tot slot creeer een vertaalproject en voeg dan de taalexemplaar aan de vertaalbaan toe.

Raadpleeg de volgende aanvullende bronnen voor meer informatie:

* [Inhoud voorbereiden voor vertaling](/help/sites-administering/tc-prep.md)
* [Vertaalprojecten beheren](/help/sites-administering/tc-manage.md)

### Hoe te om AEM mogelijkheden zoals, login pogingen en ACL of toestemmingsveranderingen te controleren? {#how-to-audit-aem-capabilities-such-as-login-attempts-and-acl-or-permission-changes}

AEM heeft de capaciteit geïntroduceerd om administratieve veranderingen voor betere het oplossen van problemen en controle te registreren. Standaard wordt de informatie in het bestand `error.log` aangemeld. Om controle gemakkelijker te maken, adviseert men dat zij aan een afzonderlijk logboekdossier worden opnieuw gericht.\
Om de output aan een afzonderlijk logboekdossier om te leiden, zie [Hoe te de verrichtingen van het gebruikersbeheer in AEM](/help/sites-administering/audit-user-management-operations.md) controleren.

### Hoe te om SSL door gebrek toe te laten? {#how-to-enable-ssl-by-default}

Adobe Experience Manager (AEM) 6.4 wordt geleverd met de SSL-wizard en biedt een gebruikersinterface voor het configureren van Jetty- en Granite Jetty SSL-ondersteuning.

Om SSL door gebrek toe te laten, zie [SSL door gebrek](/help/sites-administering/ssl-by-default.md).

### Wat is de aanbevolen architectuur wanneer de Diensten van de Inhoud van AEM van een mobiele app, ideaal React Inheems gebruikt? {#what-is-the-recommended-architecture-when-using-aem-s-content-services-from-a-mobile-app-ideally-react-native}

De diensten van de Inhoud zijn gebaseerd op de het Verdelen Modellen en de AEM ontwikkelaars moeten een het Verdelen Model pojo voor elke component verstrekken die wordt uitgevoerd.

Zie [Aan de slag met AEM Content Services](https://helpx.adobe.com/experience-manager/kt/sites/using/content-services-tutorial-use.html) zelfstudie voor meer informatie over hoe u AEM inhoudsservices kunt gebruiken vanuit een React-toepassing.

Ook, als de ontwikkelaars een boom van componenten willen uitvoeren kunnen zij `ComponentExporter` en `ContainerExporter` interfaces ook uitvoeren evenals `ModelFactory` gebruiken om over de kindcomponenten te herhalen en hun modelvertegenwoordiging terug te keren. Zie de volgende bronnen:

[1] [Adobe-Marketing-Cloud/aem-core-wcm-componenten](https://github.com/Adobe-Marketing-Cloud/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/internal/models/v1/PageImpl.java#L245)

[2] [Apache Sling: Verkoopmodellen](https://sling.apache.org/documentation/bundles/models.html)

### Hoe te om AEM 6.4 enquête pop-up onbruikbaar te maken? {#how-to-disable-aem-survey-pop-up}

U kunt in de inzameling van gebruiksstatistieken door of Touch UI of de Console van het Web te gebruiken kiezen. Voor gedetailleerde instructies, zie [Opting in de inzameling van de samengevoegde gebruiksstatistieken](/help/sites-deploying/opt-in-aggregated-usage-statistics.md).

### Is er een goede bron die de belangrijkste eigenschappen voor bevordering aan AEM 6.4 benadrukt? {#is-there-a-good-resource-that-highlights-the-key-features-for-upgrading-to-aem}

Raadpleeg [Redenen voor upgrade AEM](https://helpx.adobe.com/experience-manager/kt/platform-repository/using/upgrade-aem-article-understand.html) voor een overzicht van de belangrijkste functies op hoog niveau voor klanten die een upgrade naar de nieuwste versie van Adobe Experience Manager overwegen.

### Hoe te om een AEM instantie te vormen om de filter te gebruiken PorterStem? {#how-to-configure-an-aem-instance-to-use-the-porterstem-filter}

PorterStem filter past het Algoritme van de Stemming van de Porter voor het Engels toe. De resultaten zijn gelijkaardig aan het gebruiken van de Stemmer van het Porter Snowball met het *language=&quot;Engels&quot;* argument. Maar deze stemmer is rechtstreeks gecodeerd in Java en is niet gebaseerd op Snowball. Het accepteert geen lijst met beschermde woorden en is alleen geschikt voor Engelse tekst.

Oak stelt een reeks lucene-verstrekt de configuratieelementen van de analysator voor gebruik in AEM bloot. Raadpleeg **Apache Oak Analyzers** in [Eenvoudige handleiding voor implementatie van zoekopdrachten](https://helpx.adobe.com/experience-manager/kt/sites/using/search-tutorial-develop.html) voor meer informatie over het gebruik van filters.

### Hoe om volledig uit te voeren opnieuw indexeert? {#how-to-perform-a-full-re-indexing}

Herindexering moet altijd met de nodige aandacht worden benaderd voor het effect ervan op AEM algehele prestaties en moet worden uitgevoerd tijdens perioden van lage activiteit of onderhoudsvensters.

Verwijs naar [Beste praktijken voor Vragen en het Indexeren](/help/sites-deploying/best-practices-for-queries-and-indexing.md) om de redenen voor het opnieuw indexeren te begrijpen.

### Ondersteunen wij geminificeerde bibliotheken van JS in de Importeur van het Ontwerp? {#do-we-support-minified-js-libs-in-design-importer}

U moet het JS bewerkergebrek veranderen vormt bezit van de Manager van de Bibliotheek van Adobe Granite HTML in ***min:gcc***. Als u het ontwerppakket wilt importeren, kunt u het beste vooraf geminiateerde bibliotheken van derden opnemen in onze Client-Side Libraries.

## Assets {#assets}

### Waarom wordt de middelenworkflow zichzelf herhaald tijdens het uploaden van MP4-bestanden (bijvoorbeeld met slepen en neerzetten)? {#why-the-assets-workflow-repeats-itself-while-uploading-mp-files-for-example-using-drag-and-drop-method}

Als de gebruiker, die de filmdossiers uploadt geen toestemmingen onder activaknoop schrapt, ontbreken de schrappingsbrokkenknopen en uploadt opnieuw begint.

### Wat is het maximumaantal digitale activa dat met AEM 6.4 tegelijk kan worden geëxploiteerd? {#what-is-the-maximum-number-of-digital-assets-that-can-be-operated-with-aem-at-a-time}

Met Adobe Experience Manager (AEM) 6.4 kunt u momenteel maximaal 2 GB aan middelen tegelijk uploaden.

Zie [Hulplijn voor het aanpassen van de grootte van elementen](/help/assets/assets-sizing-guide.md) voor meer informatie over het maximumaantal activa dat met AEM 6.4 kan worden gebruikt.

### Wat zijn de standaardmontages voor configuraties OTB terwijl het creëren van het Exemplaar van de Taal? {#what-are-the-default-settings-for-ootb-configurations-while-creating-language-copy}

Wanneer u taalkopieën maakt via een klassieke UI, worden Elementen niet onder de nieuwe taalhiërarchie geplaatst, maar vanuit de master taal gebruikt.

Terwijl, wanneer u een taalexemplaar door Touch UI (**References** -> **Update Language Copy**) creeert, wordt een nieuwe omslag DAM gecreeerd onder de nieuwe taal en de activa van daar van verwijzingen voorzien.

Dit is de standaardinstelling voor OOTB-configuraties. U kunt **Paginaelementen omzetten** = **Niet vertalen** in vertaalconfiguraties instellen.\
Voor AEM 6.4 **Tools** > **Cloud Services** > **Translation Cloud services**.

### Hoe te om een AEM component onbruikbaar te maken die exponentiële groei voor AEM SegmentStore (AEM 6.3.1.1) veroorzaakt? {#how-to-disable-an-aem-component-causing-exponential-growth-for-the-aem-segmentstore-aem}

U kunt de Disabler van de Component OSGi onbruikbaar maken. Zie [OSGi Component Disabler](https://adobe-consulting-services.github.io/acs-aem-commons/features/osgi-disablers/component-disabler/index.html) om deze service te gebruiken.

Als tussenoplossing kunt u de component ook handmatig uitschakelen via de gebruikersinterface of via een opdracht `curl` (voorbeeld hieronder), na elke AEM herstart.

`curl -u admin:$(pass CQ_Admin) 'http://localhost:4502/system/console/components/com.day.cq.analytics.sitecatalyst.impl.importer.ReportImporter' --data 'action=disable'`

### Hoe te om de Inzichten van Activa met AEM 6.4 instantie te vormen? {#how-to-configure-asset-insights-with-aem-instance}

Raadpleeg [Asset Insights instellen met AEM Assets](https://helpx.adobe.com/experience-manager/kt/assets/using/asset-insights-tutorial-setup.html) voor informatie over het instellen en configureren van Asset Insights voor Experience Manager die wordt geïmplementeerd via Adobe Activation (DTM).

### Hoe te om admin consoles aan te passen? {#how-to-customize-admin-consoles}

AEM biedt verschillende mechanismen waarmee u de consoles en de functionaliteit voor het schrijven van pagina&#39;s van de ontwerpinstantie kunt aanpassen.
Leer hoe te om een douaneconsole tot stand te brengen en een standaardmening voor een console aan te passen, verwijs naar [Aanpassen van Consoles](/help/sites-developing/customizing-consoles-touch.md).

### Wat is het verschil tussen CoralUI 2 en CoralUI op 3-Gebaseerde componenten? {#what-is-the-difference-between-coralui-and-coralui-based-components}

Er wordt een nieuwe set Sling-componenten van Granite UI Foundation gemaakt voor Coral3 en bevindt zich onder [/libs/granite/ui/components/koral/foundation.](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/granite-ui/api/jcr_root/libs/granite/ui/components/coral/foundation/server.html) Er is één set voor op CoralUI 2 gebaseerde componenten en één set voor op CoralUI 3 gebaseerde componenten. De nieuwe set is niet alleen een kopie-plakbewerking van de oude set, maar wordt opgeschoond (bijvoorbeeld het stroomlijnen, verwijderen van vervangen functies). Daarom wordt aanbevolen dat een pagina alleen gebruik maakt van op CoralUI 3 gebaseerde of op CoralUI 2 gebaseerde sets.

Raadpleeg [Migratiehandleiding naar CoralUI 3-gebaseerd](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/granite-ui/api/jcr_root/libs/granite/ui/components/legacy/coral2/migration.html) voor meer informatie.

### Hoe kan ik de zoekcomponent in AEM Assets aanpassen? {#how-to-customize-the-search-component-in-aem-assets}

Raadpleeg [Eenvoudige handleiding voor zoekfuncties](https://helpx.adobe.com/experience-manager/kt/sites/using/search-tutorial-develop.html) voor meer informatie over zoekresultaten/rangschikking en verdere implementatiegegevens.

De Eenvoudige onderzoeksimplementatie is de materialen van het laboratorium van de Top van 2017 AEM Gedetailleerd Onderzoek.

### Als een klant alleen Sites-licenties in AEM koopt, hebben ze dan nog steeds toegang tot Middelen? {#if-a-customer-buys-only-sites-license-in-aem-do-they-still-have-access-to-assets}

Nee, de klant heeft geen toegang tot middelen (of andere middelen dan Sites). Hoewel alle onderdelen van Adobe Experience Manager (AEM) Op locatie in de JAR zijn opgenomen, heeft de klant alleen toegang tot die onderdelen in de JAR waarvoor hij in zijn contract een licentie heeft. Als zij andere componenten willen onderzoeken, kunnen zij of het AEM proefprogramma voor maximaal 45 dagen gebruiken of een Bessering van de Verkoop ondertekenen $0 die hen machtigt om (geen productiegebruik) genoemde componenten zoals Middelen te evalueren.

Raadpleeg de volgende bronnen voor meer informatie over AEM On-premise software en Adobe Managed Services:

* [Adobe Experience Manager On-premise software](https://helpx.adobe.com/legal/product-descriptions/adobe-experience-manager-on-premise.html)

* [Adobe Experience Manager Managed Services](https://helpx.adobe.com/legal/product-descriptions/adobe-experience-manager-managed-services.html)

### Hoe kan een klant de standaardeigenschappen van een pagina of een element uitbreiden? {#how-to-extend-default-properties-page-or-asset}

Raadpleeg de volgende bronnen voor meer informatie over het uitbreiden van de standaardeigenschappen van een pagina of een element:

* [Metagegevensschema&#39;s in elementen](/help/assets/metadata-schemas.md)
* [Weergaven van pagina-eigenschappen aanpassen](/help/sites-developing/page-properties-views.md)
