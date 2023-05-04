---
title: Analytische configuratie voor functies van Gemeenschappen
seo-title: Analytics Configuration for Communities Features
description: Analyses configureren voor Gemeenschappen
seo-description: Configure analytics for Communities
uuid: 625a253f-b198-40e8-b34c-dff337fb0eff
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 36ea97a4-4e13-4e89-866b-495f3c30cb94
role: Admin
exl-id: cb2f61df-73bb-47f7-86ce-feda4772c8d0
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '2736'
ht-degree: 1%

---

# Analytische configuratie voor functies van Gemeenschappen {#analytics-configuration-for-communities-features}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Overzicht {#overview}

Adobe Analytics en Adobe Experience Manager (AEM) zijn beide oplossingen van Adobe Marketing Cloud.

Adobe Analytics kan voor AEM Communities zodanig worden geconfigureerd dat, als lid communiceert met ondersteunde functies van de Gemeenschappen, gebeurtenissen worden verzonden naar Adobe Analytics waaruit rapporten worden gegenereerd.

Bijvoorbeeld, wanneer een lid van een enablement communautaire plaats een videobron bekijkt die aan hen wordt toegewezen, zal de middelspeler gebeurtenissen naar Analytics, met inbegrip van videohartslaggegevens verzenden. Van de communautaire plaats, kunnen de beheerders diverse rapporten zien betreffende het spelen van de video.

Daarnaast is een analyse nodig voor:

* In de publicatieomgeving:

   * Rapportage over de gemeenschap [trends](trends.md)
   * Toestaan dat sitebezoekers sorteren op &quot;meest bekeken&quot;, &quot;meest actief&quot; en &quot;meest geliefd&quot;
   * Tellingen van UGC-lijsten weergeven

* In de ontwerpomgeving:

   * Weergave van deelnemingsgegevens in de [beheerconsole voor leden](members.md) (weergaven, berichten, volgen, zoals)
   * Trend summary, video hartslag en video device for enablement resource [rapporten](reports.md)

Tot de ondersteunde Gemeenschappen behoren:

* [Middelen inschakelen](resources.md)
* [Forum](forum.md)
* [QnA](working-with-qna.md)
* [Blog](blog-feature.md)
* [Bestandsbibliotheek](file-library.md)
* [Kalender](calendar.md)

In deze sectie van de documentatie wordt beschreven hoe u een serie Analytics-rapporten kunt koppelen aan de functies van Communities. De basisstappen zijn:

1. [De cryptotoets dupliceren](#replicate-the-crypto-key) om ervoor te zorgen dat codering/decodering op de juiste wijze plaatsvindt op alle AEM
1. Een Adobe Analytics voorbereiden [rapportsuite](#adobe-analytics-report-suite-for-video-reporting)
1. Een AEM analyse maken [cloudservice](#aem-analytics-cloud-service-configuration) en [kader](#aem-analytics-framework-configuration)
1. [Analyse inschakelen](#enable-analytics-for-a-community-site) voor een community-site
1. [Verifiëren](#verify-analytics-to-aem-variable-mapping) Analyse naar AEM variabele toewijzing
1. Identificeren [primaire uitgever](#primary-publisher)
1. [Publiceren](#publish-community-site-and-analytics-cloud-service) de site van de gemeenschap
1. Configureren [invoer van rapportgegevens](#obtaining-reports-from-analytics) van Adobe Analytics naar de communitysite

## Vereisten {#prerequisites}

Als u Analytics voor Community-functies wilt configureren, moet u samenwerken met uw accountvertegenwoordiger om een Adobe Analytics-account in te stellen en [rapportsuite](#adobe-analytics-report-suite-for-video-reporting). Zodra dit is vastgesteld, moet de volgende informatie beschikbaar zijn:

* Bedrijfsnaam

   Het bedrijf dat is gekoppeld aan de Adobe Analytics-account
* Gebruikersnaam

   De aanmeldingsgebruikersnaam voor de gebruiker die gemachtigd is om de account Analytics te beheren

   (Mogen toegangsrechten voor webservices bevatten)

* Wachtwoord

   Het aanmeldingswachtwoord voor de geautoriseerde gebruiker

* Analysecentrum

   De URL van het datacenter Analytics voor de account

* Rapportsuite

   De naam van de te gebruiken analytische rapportsuite

## Adobe Analytics Report Suite for Video Reporting {#adobe-analytics-report-suite-for-video-reporting}

De Adobe Marketing Cloud gebruiken [Report Suite Manager](https://experienceleague.adobe.com/docs/analytics/admin/manage-report-suites/new-report-suite/new-report-suite.html)kunnen analytische rapportreeksen zodanig worden geconfigureerd dat een communitysite rapporten kan leveren voor de functies van Gemeenschappen.

Door u aan te melden bij [Adobe Marketing Cloud](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html) with [Bedrijfsnaam en gebruikersnaam](analytics.md#prerequisites), is het mogelijk om een nieuwe of bestaande rapportreeks te vormen om te hebben:

* [11 Conversievariabelen](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html) (avars)

   * **`evar1`** doorheen **`evar11`** enabled
   * Kan bestaande gebeurtenissen opnieuw gebruiken (naam wijzigen) of nieuwe gebeurtenissen maken die kunnen worden gebruikt voor communautaire functies

* [7 succesgebeurtenissen](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/success-events/success-event.html) (gebeurtenissen)

   * **`event1`** doorheen **`event7`** enabled
   * Type **`Counter`**

      * niet **`Counter (no subrelations)`**
   * Kan bestaande gebeurtenissen opnieuw gebruiken (naam wijzigen) of nieuwe gebeurtenissen maken die kunnen worden gebruikt voor communautaire functies


* [Videobeheer](https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html)

   * Video Reporting-console

      * Inschakelen `Video Core`
      * Selecteer Opslaan
   * Video Core-meetconsole

      * Selecteer `Use Solution Variables`
      * Selecteer Opslaan


Als u een **nieuwe rapportsuite** Houd er rekening mee dat een nieuwe rapportsuite slechts 4 gebeurtenissen en 6 gebeurtenisvariabelen kan bevatten, terwijl voor Gemeenschappen 11 gebeurtenissen en 7 gebeurtenisvars vereist zijn.

Als u een **bestaande rapportsuite** kan het nodig zijn [de variabele-toewijzing wijzigen](#modifying-analytics-variable-mapping) voordat het Analyseframework voor een communitysite wordt geactiveerd. Neem contact op met uw accountvertegenwoordiger voor eventuele problemen met betrekking tot de variabelen die voor Gemeenschappen zijn bestemd.

>[!CAUTION]
>
>**Als u een bestaande rapportsuite gebruikt die al variabelen gebruikt binnen**
>
>* **`evar1`** doorheen **`evar11`**
>* **`event1`** doorheen **`event7`**
>
>**Voordat de site van de community wordt gepubliceerd,** Het is belangrijk om de reeds bestaande afbeelding te herstellen door de AEM variabelen te verplaatsen die automatisch aan de variabelen van de Analyse werden toegewezen toen Analytics voor een communautaire plaats werd toegelaten.
>
>Als u de bestaande toewijzing wilt herstellen en AEM variabelen wilt verplaatsen naar andere variabelen van Analytics, raadpleegt u de sectie over [Variabele-toewijzing Analytics wijzigen](#modifying-analytics-variable-mapping).
>
>Als u dit niet doet, kan dit leiden tot onherstelbaar gegevensverlies.

### Video-hartslaganalyse {#video-heartbeat-analytics}

Als er een licentie is voor Video Heartbone Analytics, wordt een `Marketing Cloud Org Id` is toegewezen.

Video-hartslagrapportage inschakelen na [het vormen van de het rapportreeks van Analytics voor videorapportering](#adobe-analytics-report-suite-for-video-reporting):

* Een [Analytics-cloudservice](#aem-analytics-cloud-service-configuration)
* Inschakelen [Analyses voor een communitysite](#enable-analytics-for-a-community-site)
* Koppel de `Marketing Cloud Org Id` met de site van de gemeenschap

De `Marketing Cloud Org Id` kan worden ingevoerd op het tijdstip van [site maken](sites-console.md#enablement) of later [wijzigen](sites-console.md#modifying-site-properties) de eigenschappen van de site van de gemeenschap. [](#aem-analytics-cloud-service-configuration)

![chlimage_1-264](assets/chlimage_1-264.png)

Wanneer Video Heartbone Analytics wordt toegelaten, concretiseert de code Javascript (van JS) voor de videospeler de video hartslagbibliotheekcode (ook in JS) die al logica voor het verzenden van videostatusupdates naar de Analytics video volgende servers om de 10 seconden (niet configureerbaar) behandelt en uiteindelijk verzendt een cumulatief rapport van de videozitting naar de belangrijkste servers van Analytics.

Als deze optie niet is ingeschakeld, wordt de videohartslagcode nooit geïnstantieerd en wordt alleen de videovoortgang en het volgen van de hervattingspositie voortgezet in SRP voor rapportage.

## Configuratie van Analytics Cloud-service AEM {#aem-analytics-cloud-service-configuration}

Om een nieuwe Integratie van Analytics tot stand te brengen, die Adobe Analytics met de AEM communautaire plaats integreert, gebruikend standaard UI op de auteursinstantie:

* Vanuit globale navigatie: **[!UICONTROL Tools > Deployment > Cloud Services]**
* Omlaag schuiven naar **[!UICONTROL Adobe Analytics]**
* Selecteer **[!UICONTROL Configure Now]** of **[!UICONTROL Show Configurations]**

![chlimage_1-265](assets/chlimage_1-265.png)

### Configuratiedialoogvenster maken {#create-configuration-dialog}

* Selecteren `[+]` pictogram naast **[!UICONTROL Available Configurations]** om een nieuwe configuratie te creëren

In het dialoogvenster Configuratie maken identificeren de waarden die moeten worden ingevoerd de configuratie.

![chlimage_1-266](assets/chlimage_1-266.png)

* **[!UICONTROL Title]**

   (Vereist) Een weergavetitel voor de configuratie.

   Voer bijvoorbeeld *Community Analytics inschakelen*

* **[!UICONTROL Name]**

   (Optioneel) Indien niet opgegeven, wordt de naam standaard ingesteld op een geldige knooppuntnaam die is afgeleid van de titel.

   Voer bijvoorbeeld *gemeenschappen*


* **[!UICONTROL Template]**

   Selecteer `Adobe Analytics Configuration`

* Selecteer **[!UICONTROL Create]**
   * De configuratiepagina van lanceert en opent `Analytics Settings` dialoogvenster

### Dialoogvenster Analyse-instellingen {#analytics-settings-dialog}

Het eerste ontwerp van een nieuwe analytische configuratie resulteert in de weergave van de configuratie en een nieuw dialoogvenster voor het invoeren van de Analytische instellingen. Voor dit dialoogvenster is het [vereiste accountgegevens](#prerequisites) verkregen van de rekeningvertegenwoordiger.

![chlimage_1-267](assets/chlimage_1-267.png)

* **[!UICONTROL Company]**

   Het bedrijf dat is gekoppeld aan de Adobe Analytics-account

* **[!UICONTROL Username]**

   De aanmeldingsgebruikersnaam voor de gebruiker die gemachtigd is om de account Analytics te beheren

* **[!UICONTROL Password]**

   Het aanmeldingswachtwoord voor de geautoriseerde gebruiker

* **[!UICONTROL Data Center]**

   Selecteer het datacenter Analytics dat als host fungeert voor de rapportsuite

* **[!UICONTROL Do not add tracking tag to page]**

   Als standaard behouden (uitgeschakeld)

* **[!UICONTROL Use AppMeasurement]**

   Als standaard behouden (uitgeschakeld)

* **[!UICONTROL Do not import page impressions nightly (author)]**

   Als standaard behouden (uitgeschakeld)

* **[!UICONTROL Do not import page impressions nightly (publish)]**

   Als standaard behouden (ingeschakeld)

De instellingen opslaan:


* Selecteer **[!UICONTROL Connect to Analytics]**

   * Indien niet gelukt,

      * Verifieer de ingangen geen belangrijke ruimten bevatten
      * Probeer een ander datacenter
      * Neem contact op met uw accountvertegenwoordiger

* Selecteer **[!UICONTROL OK]**


![chlimage_1-268](assets/chlimage_1-268.png)

### Framework maken {#create-framework}

Nadat de basisverbinding met Adobe Analytics met succes is geconfigureerd, moet u een framework voor de communitysite maken of bewerken. Het doel van het kader is om de eigenschapvariabelen van de Gemeenschappen (AEM) aan (rapportreeks) variabelen Analytics in kaart te brengen.

* Selecteren `[+]` pictogram naast **[!UICONTROL Available Frameworks]** om een nieuw kader te creëren

![chlimage_1-269](assets/chlimage_1-269.png)

* **[!UICONTROL Title]**

   (Vereist) Een titel voor het weergeven van het framework

   Voer bijvoorbeeld *Communautair kader inschakelen*

* **[!UICONTROL Name]**

   (Optioneel) Indien niet opgegeven, wordt de naam standaard ingesteld op een geldige knooppuntnaam die is afgeleid van de titel.

   Voer bijvoorbeeld *gemeenschappen*

* **[!UICONTROL Template]**

   Selecteer `Adobe Analytics Framework`

* Selecteer **[!UICONTROL Create]**

Het creëren van het Kader van Analytics opent het kader voor configuratie.

## Configuratie van AEM Analytics Framework {#aem-analytics-framework-configuration}

Het doel van het kader is AEM variabelen toe te wijzen aan analytische variabelen (gebeurtenissen en gebeurtenissen). De beschikbare variabelen voor Analytics zijn: [gedefinieerd in de rapportsuite](#adobe-analytics-report-suite-for-video-reporting).

![chlimage_1-270](assets/chlimage_1-270.png)

### Rapportsuite selecteren {#select-report-suite}

Selecteer de rapportsuite die is ingesteld voor videoverslag.

Zie de vorige sectie als er nog geen rapportsuite is gemaakt of niet juist is ingesteld:\
[Adobe Analytics Report Suite for Video Reporting](#adobe-analytics-report-suite-for-video-reporting)

De Sidetrap is niet nodig en kan worden geminimaliseerd zodat het de toegang tot de montages van de Suites van het Rapport niet belemmert.

#### Dialoogvenster Suitten rapporteren vóór en na het selecteren van Item toevoegen {#report-suites-dialog-before-and-after-selecting-add-item}

![chlimage_1-271](assets/chlimage_1-271.png)

1. Selecteren **[!UICONTROL Add Item +]** er verschijnen twee keuzelijsten
1. Kies een `Report suite` de aan de bedrijfsrekening gekoppelde rapportensuites moeten beschikbaar zijn voor selectie
1. Selecteren **[!UICONTROL Yes]** in het dialoogvenster dat wordt geopend: ```Load default server settings? Do you want to load the default server settings and overwrite current values in the Server section?```
1. Kies een `Run Mode`\
   Kies **[!UICONTROL publish]**

![chlimage_1-272](assets/chlimage_1-272.png)

De analytische cloudservice en het framework zijn nu voltooid. De toewijzingen worden gedefinieerd zodra een communitysite is gemaakt en deze Analytics-service is ingeschakeld.

## Analyses inschakelen voor een Community-site {#enable-analytics-for-a-community-site}

### Inschakelen voor nieuwe Community-site {#enable-for-new-community-site}

De cloudservice Analytics toevoegen terwijl [het creëren van een nieuwe communautaire plaats](sites-console.md):


* In stap 3
* Onder de [TABBLAD ANALYTICA](sites-console.md#analytics):

   * Controleer de **[!UICONTROL Enable Analytics]** selectievakje
   * Het framework kiezen in het keuzemenu

* U kunt desgewenst terugkeren naar de configuratie van het analyseframework om de variabele toewijzingen aan te passen.

### Inschakelen voor bestaande communautaire site {#enable-for-existing-community-site}

De cloudservice Analytics toevoegen aan een [bestaande community-site](sites-console.md#modifying-site-properties):


* Ga naar de **[!UICONTROL Communities > Sites]** console
* Het pictogram Site bewerken van de site van de community selecteren
* De instellingen selecteren
* In de sectie Analytics:

   * Controleer de **[!UICONTROL Enable Analytics]** selectievakje
   * Het framework kiezen in het keuzemenu


* U kunt desgewenst terugkeren naar de configuratie van het analyseframework om de variabele toewijzingen aan te passen.

### Inschakelen voor aangepaste sites {#enable-for-customized-sites}

Als u wilt dat Analytics tracking en import correct werken voor een communitysite, moet u een pagina-element gebruiken met de `scf-js-site-title` klasse- en href-kenmerken moeten aanwezig zijn. Er mag slechts één dergelijk element op de pagina voorkomen, zoals in een ongewijzigd `sitepage.hbs` script voor een communitysite. De waarde van `siteUrl` wordt geëxtraheerd en naar Adobe Analytics verzonden als de *sitepad*.

```xml
# present in default sitepage.hbs

>[!CAUTION]
>
>AEM 6.4 has reached the end of extended support and this documentation is no longer updated. For further details, see our [technical support periods](https://helpx.adobe.com/support/programs/eol-matrix.html). Find the supported versions [here](https://experienceleague.adobe.com/docs/).
# only one scf-js-site-title class should be included

>[!CAUTION]
>
>AEM 6.4 has reached the end of extended support and this documentation is no longer updated. For further details, see our [technical support periods](https://helpx.adobe.com/support/programs/eol-matrix.html). Find the supported versions [here](https://experienceleague.adobe.com/docs/).
# this example sets it to be hidden as it serves no visual purpose

>[!CAUTION]
>
>AEM 6.4 has reached the end of extended support and this documentation is no longer updated. For further details, see our [technical support periods](https://helpx.adobe.com/support/programs/eol-matrix.html). Find the supported versions [here](https://experienceleague.adobe.com/docs/).
<div
    class="navbar-brand scf-js-site-title"
    href="{{siteUrl}}.html"
    style="visibility: hidden;"
>
</div>
```

Voor een **aangepaste communitysite** die de `sitepage.hbs` -script, moet u controleren of het element aanwezig is. De `siteUrl`variabele wordt ingesteld wanneer deze op de server wordt gerenderd voordat de client wordt ingeschakeld.

Voor een **algemene AEM** die onderdelen van de Gemeenschappen omvat, maar niet is gemaakt met de [wizard voor het maken van sites](sites-console.md), moet het element worden toegevoegd. De waarde van de href moet het pad naar de site zijn. Als het sitepad bijvoorbeeld `/content/my/company/en`en vervolgens gebruiken:

```xml
<div
    class="navbar-brand scf-js-site-title"
    href="/content/my/company/en.html"
    style="visibility: hidden;"
>
</div>
```

## Analyses voor functies van Gemeenschappen {#analytics-for-communities-features}

Analytics wordt automatisch gebruikt voor verschillende functies van de Gemeenschappen.

De omgeving van de auteur [OSGi-configuratie](../../help/sites-deploying/configuring-osgi.md), `AEM Communities Analytics Component Configuration`, bevat een lijst met de componenten die van instrumenten zijn voorzien voor Analytics. De automatische toewijzing van variabelen wordt bepaald door de vermelde componenten.

Als nieuwe douanecomponenten worden gecreeerd die voor Analytics van instrumenten worden voorzien, zouden zij aan deze lijst van gevormde componenten moeten worden toegevoegd.

### Componentconfiguratie {#component-configuration}

![chlimage_1-273](assets/chlimage_1-273.png)

Opmerking: de `journal` worden gebruikt om de blogfunctie te implementeren.

### Analyses toegewezen aan AEM variabelen {#mapped-analytics-to-aem-variables}

Zodra de communautaire plaats met toegelaten Analytics en geselecteerd wolkenconfig kader wordt bewaard, zullen de AEM variabelen automatisch aan de gebeurtenissen en gebeurtenissen worden in kaart gebracht die van Analytics met evar1 en event1 beginnen, respectievelijk, en het verhogen met 1.

Als het gebruiken van een bestaande rapportreeks die om het even welke variabelen binnen evar1 door evar11 en event1 door event7 in kaart bracht, zal het noodzakelijk zijn om [opnieuw toewijzen van de AEM variabelen](#modifying-analytics-variable-mapping) en herstelt u de oorspronkelijke toewijzing.

Hier volgt een voorbeeld van standaardtoewijzingen na het volgen van de [aan de slag - zelfstudie](getting-started-enablement.md):

![chlimage_1-274](assets/chlimage_1-274.png)

#### Kaart met eVars die met elke gebeurtenis worden verzonden {#map-of-evars-sent-with-each-event}

|  | Resourcetype Enablement | Titel site | Type functie | Groepsnaam | Pad groeperen | Type UGC | UGC-titel | Gebruiker (lid) | UGC-pad | Sitepad |
|------------------------|------------------------|-----------|--------------|------------|-----------|---------|----------|--------------|---------|----------|
|  | **eVar1** | **eVar2** | **eVar3** | **eVar4** | **eVar5** | **eVar6** | **eVar7** | **eVar8** | **eVar9** | **eVar10** |
| event1Resource Play | a) | - | - | - | - | - | - | - | i) | - |
| event2SCFView | a) | b) | c) | d) | e) | f) | g) | h) | i) | j) |
| event3SCFCreate (Post) | - | b) | c) | d) | e) | f) | g) | h) | i) | j) |
| event4SCFFollow | - | b) | c) | d) | e) | f) | g) | h) | i) | j) |
| event5SCFVoteUp | - | b) | c) | d) | e) | f) | g) | h) | i) | j) |
| event6SCFVoteDown | - | b) | c) | d) | e) | f) | g) | h) | i) | j) |
| event7SCFRate | - | b) | c) | d) | e) | f) | g) | h) | i) | j) |

**Voorbeelden voor waarden van eVar:**

* [MIME-type](https://www.iana.org/assignments/media-types): video/mp4
* [Titel van communautaire site](sites-console.md#step13asitetemplate): Geometrixx
* [Communautaire functienaam](functions.md): Forum
* [Communautaire groepsnaam](creating-groups.md#creating-a-new-group): Hiking
* Pad naar inhoud groep van gemeenschappen: /content/sites/community/nl/groups/hiking
* [Resourcetype van UGC-component](essentials.md): sociaal/forum/componenten/hbs/onderwerp
* Titel van UGC-component: Wikingonderwerpen
* Aanmelden (toegestane id): aaron.mcdonald@mailinator.com
* SRP-pad naar UGC: /content/usergenerated/asi/.../forum/jmtz-topic3 of *pad van te volgen component*: /content/sites/community/nl/jcr:content/content/primary/forum
* Pad naar community-site-inhoud: /content/sites/community/nl

### Variabele-toewijzing Analytics wijzigen {#modifying-analytics-variable-mapping}

De toewijzing van gebeurtenissen en gebeurtenissen van Analytics aan AEM variabelen is zichtbaar van de kaderconfiguratie nadat Analytics voor een communautaire plaats wordt toegelaten.

Nadat Analytics is toegelaten en alvorens de communautaire plaats wordt gepubliceerd, kan de afbeelding in het kader worden veranderd door de gewenste Analytics evar of de gebeurtenis van de linkerspoorstaaf te slepen en het neer te zetten in de relevante rij in de mappingstabel.

Als u dubbele toewijzingen wilt voorkomen, moet u de vervangen Analytics verwijderen uit de rij door de muis erboven te plaatsen en de X te selecteren die rechts van het variabele-element Analytics wordt weergegeven.

Als de gebeurtenissen van de Gemeenschappen en de gebeurtenissen afbeeldingen beschrijven die in de rapportreeks reeds bestonden, dan om gegevensverlies te vermijden, wijs de AEM variabelen voor de eigenschappen van de Gemeenschappen aan andere gebeurtenissen en/of gebeurtenissen van Analytics toe en herstel de originele afbeeldingen.

>[!CAUTION]
>
>Het is belangrijk om opnieuw toe te wijzen voordat de site van de community [gepubliceerd](#publishing-the-community-site) Als Analytics is ingeschakeld, is er anders een risico op gegevensverlies.

#### Voorbeeld, stap 1: Analytics evar14 naar toewijzingstabel slepen {#example-step-dragging-analytics-evar-into-mapping-table}

![chlimage_1-275](assets/chlimage_1-275.png)

#### Voorbeeld stap 2: Vervangen evar11 verwijderen door &#39;x&#39; te selecteren {#example-step-selecting-x-to-remove-replaced-evar}

![chlimage_1-276](assets/chlimage_1-276.png)

#### Voorbeeld stap 3: AEM var eventData.siteId opnieuw toegewezen aan Analytics evar14 {#example-step-aem-var-eventdata-siteid-remapped-to-analytics-evar}

![chlimage_1-277](assets/chlimage_1-277.png)

## De website van de Gemeenschap publiceren {#publishing-the-community-site}

### Analyses controleren op AEM variabele toewijzing {#verify-analytics-to-aem-variable-mapping}

Het is verstandig om de variabeletoewijzing te controleren voordat de communitysite wordt gepubliceerd, die ook de cloudservice en het framework Analytics publiceert.

Zie secties:

* [Analyses toegewezen aan AEM variabelen](#mapped-analytics-to-aem-variables)
* [Variabele-toewijzing Analytics wijzigen](#modifying-analytics-variable-mapping)

>[!CAUTION]
>
>**Als u een bestaande rapportsuite gebruikt die al variabelen gebruikt binnen**
>
>* **`evar1`** doorheen **`evar11`**
>* **`event1`** doorheen **`event7`**
>
>**Voordat de site van de community wordt gepubliceerd,** Het is belangrijk om de reeds bestaande mapping te herstellen en de Gemeenschappen AEM variabelen die automatisch werden toegewezen (toen Analytics voor de communautaire plaats werd toegelaten) te verplaatsen naar andere analytische variabelen. Deze nieuwe toewijzing moet voor alle onderdelen van de Gemeenschappen consistent zijn.
>
>Als u dit niet doet, kan dit leiden tot onherstelbaar gegevensverlies.

### Primaire uitgever {#primary-publisher}

Wanneer de gekozen implementatie een [publicatiebedrijf](topologies.md#tarmk-publish-farm), dan moet één AEM publicatieexemplaar als primaire uitgever voor het opiniepeilen Adobe Analytics voor rapportgegevens worden geïdentificeerd om te schrijven [SRP](working-with-srp.md).

Standaard worden de `AEM Communities Publisher Configuration` De configuratie OSGi identificeert zijn publicatiegeval als primaire uitgever, dusdanig dat alle publiceer instanties in een publicatielandbouwbedrijf zich als primair zou identificeren.

Daarom is het noodzakelijk om de configuratie op alle secundaire publiceer instanties uit te geven om te controleren **Primaire uitgever** selectievakje.

Voor specifieke instructies raadpleegt u de sectie primaire uitgever van [Gemeenschappen inzetten](deploy-communities.md#primary-publisher).

>[!CAUTION]
>
>Het is belangrijk dat de primaire uitgever wordt gevormd om het opiniepeilen van veelvoudige publicatieinstanties te verhinderen.

### De cryptosleutel dupliceren {#replicate-the-crypto-key}

De Adobe Analytics-referenties worden versleuteld. Om de replicatie of verzending van gecodeerde analysegegevens tussen auteur en uitgever te vergemakkelijken, moeten alle AEM instanties dezelfde primaire coderingssleutel delen.

Volg hiervoor de instructies op [De cryptosleutel dupliceren](deploy-communities.md#replicate-the-crypto-key).

### Community Site en Analytics Cloud Service publiceren {#publish-community-site-and-analytics-cloud-service}

Zodra de Analytics-cloudservice is ingeschakeld voor een communitysite en, indien nodig, de [de toewijzing van analyses aan AEM variabelen is aangepast](#mapped-analytics-to-aem-variables), moet de configuratie worden gerepliceerd naar de publicatieomgeving door [(re)publiceren van de communitysite](sites-console.md#publishing-the-site).

## Rapporten van Analytics verkrijgen {#obtaining-reports-from-analytics}

### Rapportbeheer {#report-management}

De auteur en de primaire uitgever [OSGi-configuratie](../../help/sites-deploying/configuring-osgi.md), `AEM Communities Analytics Report Management`, wordt gebruikt om een query op Analytics uit te voeren.

Bij de auteur zijn de vragen bestemd voor real-time rapporten.

Voor de primaire uitgever, worden de vragen gebruikt om informatie ter voorbereiding van de de gegevensinvoer van de Importeur van het Rapport Analytische te verstrekken.

Het vraaginterval blijft aan 10 seconden in gebreke.

### Rapportimportmodule {#report-importer}

Nadat een voor Analytics geschikte communitysite is gepubliceerd, worden de primaire uitgevers [OSGi-configuratie](../../help/sites-deploying/configuring-osgi.md), `AEM Communities Analytics Report Importer`, kan worden gevormd om het standaardopiniepeilingsinterval voor die configuraties te plaatsen die niet individueel in CRXDE worden gevormd.

Het opiniepeilingsinterval bepaalt de frequentie van aanvragen aan Adobe Analytics voor gegevens die moeten worden opgehaald en opgeslagen in [SRP](working-with-srp.md).

Wanneer de gegevens als &quot;grote gegevens&quot; kunnen worden gecategoriseerd, kan een frequentere opiniepeiling een grote belasting op de plaats van de gemeenschap veroorzaken.

De standaardopiniepeiling **Importinterval** wordt ingesteld op 12 uur.

![chlimage_1-278](assets/chlimage_1-278.png)

### Componentrapport aanpassen {#component-report-customization}

Momenteel, om de metriek aan spoor aan te passen, worden de knopen gecreeerd in de bewaarplaats die tijdsperioden bepalen waarvoor om een rapport over dat metrisch te produceren.

Het forumonderwerp is momenteel het enige voorbeeld van deze aanpassing:

* Op de primaire uitgever
* Aanmelden met beheerdersrechten
* Navigeren naar [CRXDE Lite](../../help/sites-developing/developing-with-crxde-lite.md)

   * Bijvoorbeeld: [http://localhost:4503/crx/de](http://localhost:4503/crx/de)

* Onder de `jcr:content` knooppunt van de taalhoofdmap

   * Bijvoorbeeld, `/content/sites/engage/en/jcr:content`

* Navigeer naar de component die is geconfigureerd voor Analytics-rapportage

   * Bijvoorbeeld, `analytics/reportConfigs/social_forum_components_hbs_topic`

* Let op de gemaakte tijdsperioden

   * `last30Days`
   * `last90Days`
   * `thisYear`

* Let op: `total`node

   * Het wijzigen van `interval` eigenschap zal het interval van de rapportimportmodule overschrijven
   * De waarde is in seconden en wordt ingesteld op 4 uur (14400 seconden)

![chlimage_1-279](assets/chlimage_1-279.png)

## Gebruikersgegevens beheren in Analytics {#manage-user-data-in-analytics}

Adobe Analytics biedt API&#39;s waarmee u gebruikersgegevens kunt openen, exporteren en verwijderen. Zie voor meer informatie [Toegang verzenden en verzoeken verwijderen](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/gdpr-submit-access-delete.html).

## Bronnen {#resources}

* Adobe Marketing Cloud: [Help en naslaggids voor analysemogelijkheden](https://experienceleague.adobe.com/docs/analytics/landing/home.html)
* AEM: [Integreren met Adobe Analytics](../../help/sites-administering/adobeanalytics.md)
* AEM: [Analyse met externe providers](../../help/sites-administering/external-providers.md)
