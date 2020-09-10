---
title: AEM 6.4 Opmerkingen bij de release Cumulative Fix Pack Pack
description: Opmerkingen bij de release die specifiek zijn voor Adobe Experience Manager 6.4 Cumulative Fix Packs.
contentOwner: AK
mini-toc-levels: 1
translation-type: tm+mt
source-git-commit: 5989421ee1207880462fd1eaefc1a9714061307e
workflow-type: tm+mt
source-wordcount: '3306'
ht-degree: 0%

---


# AEM 6.4 Opmerkingen bij de release Cumulative Fix Pack {#aem-cumulative-fix-pack-release-notes}

## Geen informatie {#release-information}

| Producten | **Adobe Experience Manager (AEM) 6.4** |
|---|---|
| Versie | 6.4.8.2 |
| Type | Cumulatief reparatiepakket |
| Date | 3 september 2020 |
| Vereiste | [AEM 6.4 Service Pack 8 (6.4.8.0)](sp-release-notes.md) |
| URL downloaden | AEM 6.4.8.2 over [softwaredistributie](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq640/cumulativefixpack/aem-6.4.8-cfp-2.0.zip) |

## Wat is inbegrepen in AEM 6.4.8.2 {#what-s-included-in-aem}

AEM Cumulative Fix Pack 6.4.8.2 is een belangrijke update die verscheidene interne en klantenmoeilijke situaties sinds de algemene beschikbaarheid van AEM 6.4 Service Pack 8 (6.4.8.0) in Maart 2020 omvat.

AEM 6.4.8.2 is een Cumulatief Pak van de Fix (GVB) dat van AEM 6.4 Service Pack 8 afhankelijk is. Installeer het GVB na installatie AEM 6.4 Service Pack 8.

In AEM 6.4.8.2 wordt de ingebouwde opslagplaats (Apache Jackrabbit Oak) bijgewerkt naar versie 1.8.22.

Voor informatie over gestreken fijn papier en andere typen vrijkomende producten raadpleegt u [AEM Definities van vrijgave voor voertuigen bijwerken](../sites-deploying/update-release-vehicle-definitions.md)

Adobe Experience Manager 6.4.8.2 biedt oplossingen voor de volgende problemen.

### Sites {#sites-6482}

* Als het `RolloutConfigManagerFactoryImpl` niet een rollout config kan laden, probeert het niet om de ontbrekende vormen te laden. Het keert de caching configuraties (NPR-34091) terug.
* In de kerncomponent Text wordt na het gebruik van de HTML-bronbewerkingsoptie de klasse uit `em` tag verwijderd (NPR-34080).
* Wanneer u van Experience Manager 6.2 aan Experience Manager 6.5 bevordert, toont de component Parsys van statische malplaatjes niet correct. De hoogte van de component Parsys wordt geplaatst aan 0 en de componenten binnen het zijn niet zichtbaar (NPR-34044).
* De etiketinformatie wordt niet getoond van de toegestane componenten binnen van de Redacteur van het Malplaatje (NPR-33908).

   ![Ontbrekende labels in lay-outcontainer](assets/33908_missing_labels.png)

* De gebruikers kunnen geen componenten aan parsys na het vierde niveau van genestelde componenten (NPR-33873) toevoegen of uitgeven.
* Als de initiële inhoud van een bewerkbare sjabloon wordt gewijzigd en de sjabloon vervolgens wordt gepubliceerd, geven nieuwe pagina&#39;s die met deze sjabloon zijn gemaakt de gepubliceerde datum van de sjabloon weer, ook al worden de pagina&#39;s niet gepubliceerd (NPR-33822).
* De `cq:acLinks` eigenschappen en `cq:acUUID` eigenschappen voor [!DNL Adobe Campaign] de kopie worden tijdens kopiëren en plakken verwijderd (NPR-33793).
* Op het [!UICONTROL Live Usage] tabblad worden slechts 49 resultaten weergegeven. Het geeft niet alle gebruik van de component weer (NPR-33710).
* Een webpagina met `/` teken in de URL reageert niet tijdens het ontwerpen. Wanneer een component tijdens het ontwerpen wordt toegevoegd, neemt het CPU-gebruik toe en reageert de browser niet meer (NPR-33625).
* In de inline bewerkingsmodus in [!DNL RTE], werkt het slepen van een afbeelding niet voor de component Text (NPR-33579).
* Het is mogelijk om een component op een blauwdrukpagina met dezelfde naam als de paginanaam te maken. Tijdens het uitvoeren, wordt zulk een component anders genoemd door achtervoegsel `_msm_moved`. De component wordt echter naar het einde van de [!UICONTROL Paragraph System] (NPR-33534) verplaatst.
* De bevordering van de lancering publiceert geen pagina&#39;s wanneer het [!UICONTROL include subpages] bezit niet op de eerste inhoudswortel wordt gecontroleerd (NPR-33533).
* Omleiden naar [!DNL Experience Manager] pagina met anker werkt niet op instantie Auteur omdat een queryreeks wordt `PageRedirectServlets` geplaatst na een URL-fragment of een anker (NPR-34287).
* `PageRedirectServlet` voegt toe `.html` na het in kaart brengen van de Sling die tot verbindingsmislukkingen leidt (NPR-34271).
* U kunt de weergave [!DNL Live Copy] van een pagina opschorten en de overerving wordt verbroken in de modus Editor. In de Pagina-eigenschappen geeft het pictogram dat overerving vertegenwoordigt echter ten onrechte aan dat de overerving bestaat en niet wordt verbroken (NPR-34096).
* Probleem met weergave van toegestane componenten op de pagina Sjabloon bewerken (CQ-4297295).
* Nadat u Chrome en Firefox hebt bijgewerkt, werken de pop-upmenu&#39;s niet meer zoals u had verwacht. Bij het laden van de pagina-eigenschappen wordt het deelvenster niet weergegeven wanneer er gegevens in staan (CQ-4292995).

### Assets {#assets-6482}

* Het uitnemen van tekst voor de geüploade PDF-bestanden werkt niet en het zoeken naar bepaalde woorden in een PDF-bestand met volledige tekst kan dat PDF-bestand niet ophalen (NPR-34165).

   >[!NOTE]
   >Start de Adobe Experience Manager-instantie opnieuw nadat u Service Pack 6.4.8.2 hebt geïnstalleerd om deze oplossing te laten werken.

* Backslashes worden toegevoegd vóór speciale tekens in zoeksuggesties voor elementen, die speciale tekens in hun naam hebben (NPR-33833).

* De aangepaste filters die als slimme verzamelingen worden opgeslagen, worden niet correct toegepast op elementen. De zoekresultaten zijn daarom niet correct (NPR-33725).

* De tijdlijn van een element in een map waarvan de volgorde is gewijzigd, geeft aan dat het element is verplaatst (NPR-33580).

* Het ongedaan maken van de publicatie van de activa in bulk van [!DNL Brand Portal] leidt tot een `Request-URI Too Long` fout (NPR-34158).

* Als de gebruiker in de kolomweergave een [!UICONTROL Filter] optie selecteert nadat een set elementen is geselecteerd (de elementen worden uitgeschakeld), en vervolgens een andere set elementen selecteert die moeten worden verplaatst, worden de eerder geselecteerde elementen ook naar de nieuwe locatie verplaatst (NPR-34018).

* De schuifbalk is niet zichtbaar in de lijstweergave, zelfs niet als er veel elementen zijn die in de pagina passen (NPR-34156).

* De [!UICONTROL Manage Publication] pagina voor elementen is verbroken en de opties daarin werken niet (CQ-4302509).

**Dynamic Media**

* De functie Slim uitsnijden mislukt met een fout wanneer een afbeeldingsprofiel wordt toegevoegd aan een map met meerdere (bijvoorbeeld 11) hoogte-breedteverhoudingen (NPR-34083).

* Wijzigingen in voorinstellingen voor afbeeldingen worden [!UICONTROL Adobe Experience Manager] niet gesynchroniseerd met Scene7 Publishing System (NPR-34284, CQ-4299713).

* Het [!UICONTROL PANORAMICVIEW_AUTOROTATE] modifier-label ontbreekt op het [!UICONTROL Behavior] tabblad op [!UICONTROL Viewer Preset Editor] pagina (CQ-4302043).

### Platform {#platform-6482}

* De standaardwaarden voor de **[!UICONTROL Connect Timeout]** **[!UICONTROL Socket Timeout]** en de montages voor de StandaardConfiguratie van de Agent (publiceren) worden niet gespecificeerd (NPR-33708).
* De onderhoudstaakplanner begint en stopt te vaak onderhoudstaken dan gevormd (NPR-33520).
* Kan logboeken niet downloaden met het gereedschap Diagnostiek op een geüpgrade Experience Manager-instantie (NPR-34419).

### Integrations {#integrations-6482}

* De waarde van `library_path` wordt niet meegenomen bij het genereren van de URL van de [!DNL Adobe Launch] bibliotheek voor bibliotheken die zijn gemigreerd van [!DNL Adobe Dynamic Tag Management]. Bovendien gebruiken de gemigreerde bibliotheken een ander voorvoegsel dan [!DNL Adobe Launch] bibliotheken. (NPR-34238).
* De eigenschappen die van een cloudservice worden overgeërfd, blijven niet behouden bij het bijwerken van de pagina-eigenschappen (NPR-33865).

### User Interface {#ui-6482}

* De weergave van het aantal geselecteerde elementen op een zoekpagina is onjuist (NPR-33540).

### Gemeenschappen {#communities-6482}

* De bestaande gebruikers van een communautaire groep die via admin console wordt toegevoegd worden verwijderd uit de gebruikerslijst bij om het even welke wijziging in de communautaire groepsconsole (NPR-34312).

### Forms {#forms-6482}

>[!NOTE]
>
>[!DNL Experience Manager] Cumulatief Fix Pack bevat geen correcties voor [!DNL Experience Manager Forms]. Ze worden geleverd met een apart [!DNL Forms] invoegpakket. Daarnaast wordt een cumulatief installatieprogramma uitgebracht dat oplossingen voor [!DNL Experience Manager Forms] JEE bevat. Zie Het invoegpakket [AEM Forms](#install-aem-forms-add-on-package) installeren en het installatieprogramma [](#install-aem-forms-jee-installer)van AEM Forms JEE installeren voor meer informatie.

**Adaptieve Forms**

* Als er een ontbrekend adaptief formulierfragment is, kan het adaptieve formulier niet worden weergegeven (NPR-34303).

* In de beschrijving van Help-inhoud voor adaptieve formuliervelden wordt een alinea-HTML-tag weergegeven (NPR-34117).

* Wanneer u een Forms-container op een [!DNL Experience Manager Sites] pagina toevoegt, wordt het volgende foutbericht weergegeven en kunt u geen nieuwe componenten toevoegen (NPR-33858):

   `DevTools failed to load SourceMap: Could not load content for <Link>. HTTP error: status code 404, net::ERR_HTTP_RESPONSE_CODE_FAILURE`

* Wanneer u de **[!UICONTROL Revalidate on Server]** eigenschap selecteert en meerdere bijlagen uploadt, kan het adaptieve formulier niet worden verzonden (NPR-33701).

* Wanneer u de opties **[!UICONTROL Use Page Language]** en **[!UICONTROL Form covers entire width of the Page]** opties in de [!DNL Experience Manager Forms] component op een [!DNL Experience Manager Sites] pagina selecteert, kan de pagina niet worden vertaald (NPR-33641).

* Wanneer u een adaptief formulier voor analysemogelijkheden verzendt dat is ingesloten in een [!DNL Experience Manager Sites] pagina, werkt de analyse niet correct (NPR-31359).

* Geafhankelijkheden van [!DNL Lodash] en [!DNL backbone] bibliotheken zijn verwijderd (NPR-33458).

* De handeling **[!UICONTROL Submit to REST endpoint]** submit werkt niet voor een adaptief formulier (NPR-34513).

* Toegankelijkheid: Wanneer u een adaptief formulier probeert te verzenden zonder een bijlage voor een verplicht veld te uploaden, verschuift de focus niet automatisch naar het bijlageveld (NPR-34511).

**Workflow**

* [!DNL Experience Manager] De werkstroom leegmaken mislukt en geeft het volgende foutbericht weer (NPR-33576):

   `java.lang.UnsupportedOperationException: The query read more than 500000 nodes in memory`

* Wanneer u [!DNL Experience Manager] 6.4.8.1 installeert, wordt de [!UICONTROL To Do] lijst met items niet weergegeven als koppelingen. De tekst voor de [!UICONTROL To Do] items bevat HTML-tags (NPR-34318).

**BackendIntegration**

* Kan geen formuliergegevensmodel configureren in een door AWS gehoste [!DNL Experience Manager Forms Linux] omgeving (NPR-33617).

**Designer**

* Wanneer [!DNL Acrobat DC] deze optie op een [!DNL Experience Manager] Forms-server is geïnstalleerd, is deze **[!UICONTROL Distribute Form]** niet beschikbaar in [!DNL Experience Manager Designer] versie 6.x (NPR-34325).

**Documentbeveiliging**

* Kan de ondertekeningsbewerking met op HSM gebaseerde certificaten niet uitvoeren in een PDF-bestand na installatie van [!DNL Experience Manager] 6.4.8.0 (NPR-34309).

**Upgrade**

* Wanneer u de [!DNL JBoss] versie upgradet naar 7.0.9 voor [!DNL Experience Manager Forms] documentbeveiliging in een [!DNL Linux] omgeving, resulteert dit in een fout (CQ-4300546).

Voor informatie over veiligheidsupdates, zie de pagina [van bulletins van de](https://helpx.adobe.com/security/products/experience-manager.html)Experience Manager veiligheid.

## Hotfixes en de Pakken van de Eigenschap inbegrepen in vorige Cumulatieve Pakken van de Moeilijke situatie {#hotfixes-and-feature-packs-included-in-previous-cumulative-fix-packs}

### Adobe Experience Manager 6.4.8.1 {#experience-manager-6481}

AEM Cumulative Fix Pack 6.4.8.1 is een belangrijke update die verscheidene interne en klantenmoeilijke situaties sinds de algemene beschikbaarheid van AEM 6.4 Service Pack 8 (6.4.8.0) in Maart 2020 omvat.

AEM Cumulative Fix Pack 6.4.8.1 is afhankelijk van AEM 6.4 Service Pack 8. Daarom moet u het pakket AEM Cumulative Fix Pack 6.4.8.1 installeren nadat u AEM 6.4 Service Pack 8 hebt geïnstalleerd.

Enkele belangrijke punten van AEM 6.4.8.1 zijn:

* Anonieme toegang tot CRXDE Lite is niet toegestaan om de beveiliging te verbeteren. In plaats daarvan worden de gebruikers naar het aanmeldingsscherm geleid. Zie [zich ontwikkelen met CRXDE Lite](/help/sites-developing/developing-with-crxde-lite.md).
* Integratie met Adobe Experience Manager voor delen van pakket is verwijderd.
* De ingebouwde opslagplaats (Apache Jackrabbit Oak) wordt bijgewerkt naar versie 1.8.21.

Voor informatie over gestreken fijn papier en andere typen vrijkomende producten raadpleegt u [AEM Definities van vrijgave voor voertuigen bijwerken](../sites-deploying/update-release-vehicle-definitions.md)

Adobe Experience Manager 6.4.8.1 biedt oplossingen voor de volgende problemen.

#### Sites {#sites-6481}

* Anonieme gebruikers hebben toegang tot de functies van CRX DE Lite (NPR-33522).
* Wanneer de naam van een lokale component in een LiveCopy identiek is aan de naam van een component in de blauwdruk en de component uit blauwdruk wordt opgerold, wordt de term _msm_moving niet toegevoegd aan de naam van de lokale component (NPR-33207).
* De parameters die aan het oorspronkelijke verzoek zijn toegevoegd, zijn niet opgenomen in de omleidings-URL (NPR-33174).
* Als de optie Coral.Select de waarde emptyOption=true instelt of een standaarditems met waarde = &quot;&quot; bevat, wordt in het bestand dropdownshowhide.js een fout aangetroffen: Uncaught TypeError: component.getValue is geen functie (NPR-33163).
* Wanneer een component een andere component als data-SLUIT-middel omvat, wordt de placeholder van de oudercontainer componentencomponent vervangen met binnenste componentenplaceholder (NPR-33119).
* Wanneer u een inhoudsfragment baseert op een schema en het een verplicht tekstgebied of een weggebied bevat, kan het inhoudsfragment niet opslaan (NPR-33007)
* Wanneer u een aangepaste component maakt met de fragmentcomponent voor het weergeven van fragmenten in de doos en deze gebruikt op AEM Sites-pagina&#39;s, geeft AEM geen referenties (gebruik) weer voor de aangepaste component (NPR-32852).
* Wanneer een AEM Sites-pagina deel uitmaakt van een grote inhoudsset met meerdere live-kopieën, kan de voorvertoning van de paginaversiegeschiedenis niet worden geladen (NPR-32772).
* Wanneer u een lancering bevordert voegt het &quot;cq:LiveRelationship&quot;mengsel aan elke component toe die in de lancering wordt toegevoegd. Het heeft invloed op alle lanceringen ongeacht of een lancering met of zonder het selecteren van — de Inherit bron pagina levende gegevens — optie (NPR-32664) wordt gecreeerd.
* Wanneer de paginering begint, laadt de Plukker van de Fragmenten van de Ervaring niet alle punten (NPR-32605).
* Kan geen startpagina voor een AEM Sites-pagina maken. Het creëren van de lancering resulteert in een fout (NPR-32544).
* Beheer Publicatie omvat geen middelen waarnaar wordt verwezen in de activeringswerkstroom (NPR-32463).
* Met de health check van de verzender wordt een `Invalid cookie header` waarschuwingsbericht weergegeven in de logbestanden (NPR-33630).
* De integratie van Salesforce is kwetsbaar voor SSRF (NPR-32671).
* Gereflecteerde XSS in PreferencesServlet (NPR-33439).

#### Assets {#assets-6481}

* Het aantal activa verandert niet zoals in de verandering in selectie in Lijstmening (NPR-33285).

* De knop Volgende wordt niet ingeschakeld bij het selecteren van het bovenliggende knooppunt (waar een enkele onderliggende map zichtbaar is) en het selecteren van de onderliggende map (NPR-33284).

* De aanraakinterface kan niet worden weergegeven (met een fout) voor gebruikers die geen leestoegang hebben in de hoofdmap van de opslagplaats wanneer DMS7 of de hybride modus is ingeschakeld (NPR-33175).

* De GB18030-tekens in map- en elementnamen worden in de gedownloade ZIP-bestanden vervangen door leeg (NPR-33150).

* Er wordt een extra map gemaakt bij het slim uitsnijden van een element in een bovenliggende map met een puntteken in de naam (NPR-32755). `.`

* Lazy loading wordt niet geactiveerd en er worden maximaal 100 assets weergegeven bij het selecteren om de taken te bekijken vanuit de inbox met meldingen (NPR-32749).

* De koppelingspagina voor het delen van verzamelingen wordt verbroken vanwege wijzigingen in koraalinfo (NPR-32510).

* De verwerking van activa terwijl bulkupload vastloopt (CQ-4293916).

* SSRF-kwetsbaarheid in Experience Manager (NPR-33437).

#### Platform {#platform-6481}

* Het [!DNL Sling] filter wordt niet aangeroepen als het `sling:match` kaartitem wordt gemaakt onder `/etc/maps` (NPR-33308).
* Alle spoelmiddelen worden geactiveerd bij het deactiveren van een pagina (NPR-32941).
* Wanneer u de `ScriptProcessor` API gebruikt om een JavaScript-bibliotheek te miniateren, wordt in het logbestand een foutbericht weergegeven dat aangeeft dat de JavaScript-code niet compatibel is met de strikte modus. De API biedt geen optie om de strikte modus in of uit te schakelen. (NPR-32746).
* Wanneer een SQL vraag langere tijd, bijvoorbeeld 7 uren loopt, AEM ophoudt antwoordend (NPR-33043).

#### User Interface {#ui-6481}

* Wanneer u een pad doorzoekt of in een selectiedialoogvenster bladert, wordt in het dialoogvenster Selecteren alle inhoud van het geselecteerde JCR-knooppunt weergegeven in plaats van alleen de afbeeldingen weer te geven (NPR-32712).

#### Omzettingsprojecten {#tranlation-6481}

* Er is een `NullPointerException` fout opgetreden in de logboeken met een vertaaltaak (NPR-32220).

#### Integrations {#integrations-6481}

* Xxx-site scripting voor JSON (NPR-32745).

#### Gemeenschappen {#communities-6481}

* Auteurs worden na het maken van een nieuwe groep niet doorgestuurd naar de [!UICONTROL Community Group] sectie op [!DNL Internet Explorer] 11 (NPR-33202).
* Er treedt een fout op bij het openen van de [!UICONTROL Activity Stream] pagina (NPR-33152).
* Als u een [!DNL Communities] groep bewerkt en de miniatuurafbeelding wijzigt, wordt de groepminiatuurafbeelding niet bijgewerkt (NPR-32603).
* Tijdens het maken van een versie van meldingen en abonnementen op door gebruikers gegenereerde inhoud (UGC) wordt een onjuiste id van de bronpagina opgeslagen (CQ-4289703).
* Probleem met scripts die verwijzen naar andere sites (NPR-33212).

#### Workflow {#workflow-6481}

* Sommige componenten worden niet weergegeven in het dialoogvenster dat wordt weergegeven wanneer een gebruiker een workflow voltooit die een [!UICONTROL Dialog Participant step] (NPR-32989) bevat.

* De [!UICONTROL Timeline] optie in de linkerspoorstaaf neemt meer tijd om te laden dan verwacht (NPR-32850).

#### Forms {#forms-6481}

>[!NOTE]
>
>AEM Cumulative Fix Pack bevat geen correcties voor AEM Forms. Ze worden geleverd met een apart Forms-add-onpakket. Daarnaast wordt een cumulatief installatieprogramma uitgebracht dat oplossingen voor AEM Forms op JEE bevat. Zie Het invoegpakket [AEM Forms](#install-aem-forms-add-on-package) installeren en het installatieprogramma [](#install-aem-forms-jee-installer)van AEM Forms JEE installeren voor meer informatie.

* Correspondentenbeheer: Wanneer een gebruiker inhoud uit een [!DNL Word] document plakt, behoudt het tekstdocumentfragment de opmaak niet (NPR-33213).
* Adaptieve Forms: Een nieuwe regel naar een tekenreeks in een woordenboek voor adaptieve formulieren voegt `&#xa;` tekens toe aan het woordenboek (NPR-33265).
* Adaptieve Forms: De gebruiker kan geen adaptief formulier opslaan met meer dan één bijlage (NPR-33214).
* Adaptieve Forms: `AddInstance` en `RemoveInstance` methoden voor Instance Manager-klasse voegen geen dynamisch aantal instanties toe voor lazy load fragments op [!DNL Internet Explorer 11] (NPR-33201).
* Adaptieve Forms: Analyses die zijn ingeschakeld op een adaptief formulier dat is ingesloten in een [!DNL Sites] pagina, registreren geen gegevens voor gebeurtenissen Verzenden en Afbreken (NPR-31359).
* Adaptieve Forms: Wanneer een gebruiker de inhoud van een [!DNL Word] document in een adaptief formulier plakt en het verzendt, bevat het verzonden adaptieve formulier Unicode-tekens. Bovendien mislukt de conversie van PDF naar PDF/A vanwege Unicode-tekens (NPR-33348).
* BackendIntegration: De verzoeken van het het gegevensmodel van de vorm ontbreken aangezien verfrist teken wegens onjuiste inactieve staat (NPR-33168) verloopt.
* Documentservices: De conversie van PDF-service kan PDF-documenten niet converteren naar PostScript omdat Gibson-jars ontbreken voor [!DNL WebLogic] de [!DNL Linux] server (NPR-33515, CQ-4292239).
* Documentservices: Wanneer een gebruiker een tekstbestand naar een PDF converteert, worden Japanse tekens niet correct weergegeven (NPR-33239).
* Opgeslagen XSS met GuideSOMProviderServlet (NPR-32701).

## Installeren 6.4.8.2 {#install}

### Installatievereisten {#setup-requirements}

<!--

>[!NOTE]
>
>For successful installation of AEM 6.4.6.0 on the instance, it is strongly recommended to upgrade the version of com.adobe.granite.oak.s3connector to 1.8.4 for the customers who are on the older version of s3 connector.
>The process of upgrading the com.adobe.granite.oak.s3connector is available at [https://helpx.adobe.com/in/experience-manager/6-4/sites/deploying/using/data-store-config.html](https://helpx.adobe.com/in/experience-manager/6-4/sites/deploying/using/data-store-config.html).
>Download the latest version of com.adobe.granite.oak.s3connector from: [https://repo.adobe.com/nexus/content/groups/public/com/adobe/granite/com.adobe.granite.oak.s3connector/](https://repo.adobe.com/nexus/content/groups/public/com/adobe/granite/com.adobe.granite.oak.s3connector/)

-->

>[!CAUTION]
>
>Voor klanten met op AEM 6.4 geïnstalleerde de Pakken van de Eigenschap. De facultatieve die Packs van de Eigenschap door Adobe worden verstrekt hebben gebiedsdelen op de versieversie en de dienstpakken. Als u een Feature Pack hebt geïnstalleerd, neemt u contact op met het AEM Customer Care-team om de compatibiliteit van deze functiepakketten met dit cumulatieve reparatiepakket voor AEM 6.4 te valideren.

* AEM 6.4.8.2 vereist AEM 6.4.8.0. Ga naar de [upgradedocumentatie](../sites-deploying/upgrade.md) voor gedetailleerde instructies.
* Voor een plaatsing met MongoDB en veelvoudige instanties, installeer AEM 6.4.8.2 op één van de instanties van de Auteur gebruikend de Manager van het Pakket.
* Zorg ervoor dat u een momentopname of een nieuwe back-up van uw AEM hebt voordat u het cumulatieve reparatiepakket installeert.
* Start de instantie opnieuw voor de installatie. Hoewel dat alleen nodig is wanneer de instantie zich nog in de updatemodus bevindt (en dit is het geval wanneer de instantie zojuist is bijgewerkt vanaf een eerdere versie), wordt het doorgaans aanbevolen als de instantie langer actief was.

>[!NOTE]
>
>Adobe raadt u niet aan het pakket AEM 6.4.8.2 te verwijderen of te verwijderen.

### Het Cumulative Fix Pack installeren {#install-cumulative-fix-pack}

Voer de volgende stappen uit om het Cumulative Fix Pack op een bestaand AEM 6.4.8.0-exemplaar te installeren:

1. Klik op de koppeling [Softwaredistributie](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq640/cumulativefixpack/aem-6.4.8-cfp-2.0.zip) om het pakket te downloaden.

1. Open [Package Manager](http://localhost:4502/crx/packmgr/index.jsp) en klik **[!UICONTROL Upload Package]** om het pakket te uploaden.

1. Selecteer de pakketnaam en klik op **[!UICONTROL Install]**.

>[!NOTE]
>
>**Dialoogvenster over de UI van de Manager van het Pakket sluit soms ongeschikt tijdens installatie van 6.4.8.2**
>
>Daarom wordt aangeraden te wachten totdat de foutenlogboeken zich stabiliseren voordat u de instantie opent. De gebruiker moet op specifieke logboeken met betrekking tot het verwijderen van updaterbundel wachten alvorens wordt gewaarborgd dat de installatie succesvol is. Het gebeurt meestal in Safari, maar kan af en toe in elke browser gebeuren.

### Automatische installatie {#auto-installation}

Er zijn twee manieren om AEM 6.4.8.2 automatisch in een lopende instantie te installeren:

A. Plaats de verpakking in ...*/crx-quickstart/install* folder terwijl de server loopt. Het pakket wordt automatisch geïnstalleerd.

B. Gebruik de [HTTP API van de Manager](https://docs.adobe.com/content/docs/en/crx/2-3/how_to/package_manager.html) van het Pakket - zorg ervoor u gebruikt `cmd=install&recursive=true` - zodat wordt het genestelde pakket geïnstalleerd.

>[!NOTE]
>
>AEM 6.4.8.2 ondersteunt geen Bootstrap-installatie.

### Installatie valideren {#validate-install}

1. Op de pagina Productinformatie (*/system/console/productinfo*) moet nu de bijgewerkte versietekenreeks &quot;Adobe Experience Manager, Version 6.4.8.2&quot; onder Geïnstalleerde Producten worden weergegeven.
1. Alle OSGI-bundels zijn actief of FRAGMENT in de OSGI Console (Webconsole gebruiken: /systeem/console/bundels).
1. De OSGI-bundel org.apache.jackrabbit.oak-core bevindt zich op versie 1.8.17 of hoger (gebruik webconsole: /systeem/console/bundels).

Zie [Technische vereisten](../sites-deploying/technical-requirements.md)voor informatie over het gecertificeerde platform voor deze versie van AEM Sites en Assets.

>[!NOTE]
>Na een geslaagde installatie van het pakket wordt een informatief bericht weergegeven waarin wordt aangegeven dat het inhoudspakket is geïnstalleerd, zoals **&quot;Content Package AEM-6.4-Service-Pack-8 is geïnstalleerd.&quot;**

### Dynamische media-viewers bijwerken (5.10.1) {#update-dynamic-media-viewers}

AEM 6.4.8.2 bevat een nieuwe versie van Dynamic Media-viewers (5.10.1), waarmee op dubbele namen op de pagina Voorinstelling afbeelding kan worden gecontroleerd. Klanten met dynamische media wordt aangeraden de volgende opdracht uit te voeren om voorinstellingen van de viewer voor selectievakjes naar een actuele status over te brengen.

`curl -u admin:admin http://localhost:4502/libs/settings/dam/dm/presets/viewer.pushviewerpresets`

Hiermee worden nieuwe voorinstellingen van de viewer naar de locatie /conf gekopieerd.

### Invoegpakket voor AEM formulieren installeren {#install-aem-forms-add-on-package}

>[!NOTE]
>
>Sla dit over als u AEM Forms niet gebruikt. Correcties in AEM Forms worden geleverd via een afzonderlijk invoegpakket.

1. Controleer of u het AEM Cumulative Fix Pack hebt geïnstalleerd.
1. Download het overeenkomstige formulierinvoegpakket dat in [AEM Forms-releases](https://helpx.adobe.com/aem-forms/kb/aem-forms-releases.html) voor uw besturingssysteem wordt vermeld.
1. Installeer het formulierinvoegpakket zoals beschreven in [Invoegtoepassingspakketten](https://docs.adobe.com/content/help/en/experience-manager-64/forms/install-aem-forms/osgi-installation/installing-configuring-aem-forms-osgi.html#install-aem-forms-add-on-package)voor AEM formulieren installeren.

### AEM Forms JEE-installatieprogramma installeren {#install-aem-forms-jee-installer}

>[!NOTE]
>
>Sla dit over als u AEM Forms niet gebruikt op JEE. Correcties in AEM Forms JEE worden geleverd via een afzonderlijk installatieprogramma.

Zie [AEM Forms JEE Patch Installer 0019 voor informatie over de installatie van het cumulatieve installatieprogramma voor AEM Forms JEE en de configuratie na de implementatie](jee-patch-installer-64.md).

### Uber Jar {#uber-jar}

De Uber Jar voor AEM 6.4.8.2 is beschikbaar in de [Adobe Public Maven bewaarplaats](https://repo.maven.apache.org/maven2/com/adobe/aem/uber-jar/6.4.8.2-1.0/).

Om Uber Jar in een Geweven project te gebruiken, verwijs naar het artikel, [hoe te om de jar](../sites-developing/ht-projects-maven.md) van Uber te gebruiken en de volgende gebiedsdeel in uw projectPOM te omvatten:

```shell
<dependency>
      <groupId>com.adobe.aem</groupId>
      <artifactId>uber-jar</artifactId>
      <version>6.4.8.2-1.0</version>  
      <scope>provided</scope>
</dependency>
```

## Verwijderde/vervangen functies {#removed-deprecated-features}

Deze sectie bevat een lijst met functies en mogelijkheden die zijn verwijderd of verouderd uit AEM 6.4.

| Gebied | Functie | Vervanging | Versie |
|---|---|---|---|
| Assets | Tagactie beheren voor submiddelen | Geen vervanging | AEM 6.4.2.0 |
| Integratie van middelen en Adobe Creative Cloud | [AEM naar het delen](https://docs.adobe.com/content/help/en/experience-manager-64/assets/administer/aem-cc-folder-sharing-best-practices.html) van mappen in Creative Cloud is in AEM 6.2 geïntroduceerd als een manier om creatieve gebruikers toegang te geven tot middelen van AEM. Een nieuwe mogelijkheid die wordt vrijgegeven in de Creative Cloud-toepassing, de Adobe Asset Link, biedt een veel betere gebruikerservaring en een krachtigere toegang tot middelen van AEM rechtstreeks vanuit Photoshop, InDesign en Illustrator. Adobe zal geen verdere verhogingen aan de omslag het delen capaciteit maken. Hoewel de functie in AEM is opgenomen, wordt het klanten sterk aangeraden de vervangende functie te gebruiken. | Adobe Asset Link of desktop app. Zie voor meer informatie [AEM het](/help/assets/aem-cc-integration-best-practices.md) artikel over Creative Cloud-integratie. | AEM 6.4.4.0 |

## Bekende problemen {#known-issues}

* Als u van Experience Manager 6.4.8.2 aan Experience Manager 6.5 bevordert, zouden sommige bundels niet hun status kunnen tonen `Active`. Installeer de nieuwste Experience Manager 6.5 Service Pack 6 om het probleem op te lossen.

Voor informatie over AEM 6.4.8.0 Service Pack bekende kwesties, zie [AEM 6.4.8.0 de Nota&#39;s](sp-release-notes.md)van de Versie van het Service Pack van de Versie.

## OSGi-bundels en inhoudspakketten inbegrepen {#osgi-bundles-and-content-packages-included}

De volgende tekstdocumenten maken een lijst van de bundels OSGi en de Pakketten van de Inhoud inbegrepen in AEM 6.4.8.2.

Lijst van OSGi-bundels opgenomen in AEM 6.4.8.2

[Bestand ophalen](assets/6.4.8.2_osgi_bundles.txt)

Lijst van inhoudspakketten opgenomen in AEM 6.4.8.2

[Bestand ophalen](assets/6.4.8.2_content_packages.txt)

## Nuttige bronnen {#helpful-resources}

* [Opmerkingen bij de release AEM 6.4](../release-notes/release-notes.md)
* [AEM productpagina](https://www.adobe.com/solutions/web-experience-management.html)
* [AEM 6.4-documentatie](https://helpx.adobe.com/nl/support/experience-manager/6-4.html)
* Abonneren op [Adobe-productupdates met prioriteit](https://www.adobe.com/subscription/priority-product-update.html)

## Beperkte sites {#restricted-sites-new}

Deze sites zijn alleen beschikbaar voor klanten. Neem contact op met uw Adobe-accountmanager als u een klant bent en toegang nodig hebt.

* [Productdownload op licensing.adobe.com](https://licensing.adobe.com/)
* [Contact opnemen met de klantenondersteuning](https://docs.adobe.com/content/help/en/customer-one/using/home.html)
