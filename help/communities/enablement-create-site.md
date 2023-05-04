---
title: Auteur van een nieuwe communautaire site voor activering
seo-title: Author a New Community Site for Enablement
description: Een communitysite maken voor activering
seo-description: Create a community site for enablement
uuid: 6822cc99-e272-4661-bddf-aa0800b88c41
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: introduction
content-type: reference
discoiquuid: aff8b79f-dd4e-486e-9d59-5d09dfe34f27
exl-id: 5b16c775-3bd0-4a55-ba9e-f326224e8bae
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1720'
ht-degree: 1%

---

# Auteur van een nieuwe communautaire site voor activering {#author-a-new-community-site-for-enablement}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Community-site maken {#create-community-site}

[Creatie van gemeenschapssite](sites-console.md) Hiermee gebruikt u een wizard die u door de stappen begeleidt bij het maken van een communitysite. Het is mogelijk verder te gaan naar de `Next`stap of `Back`naar de vorige stap voordat u de site in de laatste stap toewijst.

Ga als volgt te werk om een nieuwe communitysite te maken:

Met de [auteurinstantie](http://localhost:4502/)

* Aanmelden met beheerdersrechten
* Ga naar **[!UICONTROL Communities > Sites]**

* Selecteer **[!UICONTROL Create]**

### Stap 1: Sitesjabloon {#step-site-template}

![enablementsitetemplate](assets/enablementsitetemplate.png)

Op de **Sitesjabloon** Voer vervolgens een titel, beschrijving, naam voor de URL in en selecteer een sjabloon voor een community-site, bijvoorbeeld:

* **Titel van gemeenschapssite**: `Enablement Tutorial`

* **Beschrijving van community-site**: `A site for enabling the community to learn.`

* **Hoofdmap van gemeenschapssite**: (leeg laten voor standaardhoofdmap `/content/sites`)

* **Cloudconfiguraties**: (leeg laten als er geen cloudconfiguraties zijn opgegeven) het pad naar de opgegeven cloudconfiguraties bieden.
* **Basis van gemeenschapssite**: (ongewijzigd laten voor één taal: Engels) gebruik het keuzemenu om één te kiezen *of meer* basistalen uit de beschikbare talen: Duits, Italiaans, Frans, Japans, Spaans, Portugees (Brazilië), Chinees (traditioneel) en Chinees (vereenvoudigd). Er wordt één communitysite gemaakt voor elke toegevoegde taal en deze site bestaat in dezelfde sitemap volgens de in [Inhoud vertalen voor meertalige sites](../../help/sites-administering/translation.md). De hoofdpagina van elke site bevat een onderliggende pagina met de taalcode van een van de geselecteerde talen, zoals &#39;en&#39; voor Engels of &#39;fr&#39; voor Frans.

* **[!UICONTROL Community Site Name]**: `enable`

   * de eerste URL wordt onder de naam van de communautaire site weergegeven
   * voor een geldige URL voegt u een basistaalcode + &quot;.html&quot; toe

      *bijvoorbeeld*, http://localhost:4502/content/sites/ `enable/en.html`

* **[!UICONTROL Reference Site Template]**: naar beneden halen om te kiezen `Reference Structured Learning Site Template`

Selecteer **[!UICONTROL Next]**

### Stap 2: Ontwerp {#step-design}

De stap Ontwerp wordt in twee secties weergegeven voor het selecteren van het thema en de brandingbanner:

#### COMMUNAUTAIR SITE-THEMA {#community-site-theme}

Selecteer de gewenste stijl die u op de sjabloon wilt toepassen. Als deze optie is geselecteerd, wordt het thema bedekt met een vinkje.

![enablementsite-thema](assets/enablementsitetheme.png)

#### COMMUNAUTAIRE SITOBRANDING {#community-site-branding}

(optioneel) Upload een bannerafbeelding voor weergave op de sitepagina&#39;s. De banner is vastgezet aan de linkerrand van browser, tussen de communautaire plaatsheader en menu (navigatiekoppelingen). De bannerhoogte wordt bijgesneden tot 120 pixels. Er wordt geen grootte van de banner aangepast aan de breedte van de browser en de hoogte van 120 pixels.

![chlimage_1-284](assets/chlimage_1-284.png) ![chlimage_1](assets/chlimage_1.jpeg)

Selecteer **[!UICONTROL Next]**.

### Stap 3: Instellingen {#step-settings}

Selecteer in de stap Instellingen voordat u `Next`, merk op dat er zeven secties zijn die toegang tot configuraties verlenen die gebruikersbeheer, het etiketteren, rollen, moderatie, analyses, vertaling, en toelaat.

#### GEBRUIKERSBEHEER {#user-management}

Het wordt aanbevolen [gemeenschappen](overview.md#enablement-community) privé zijn.

Een gemeenschapssite is persoonlijk wanneer anonieme sitebezoekers geen toegang krijgen, zich mogelijk niet zelf registreren en geen gebruik maken van sociale aanmelding.

De meeste selectievakjes zijn uitgeschakeld [Gebruikersbeheer](sites-console.md#user-management):

* Websitebezoekers niet toestaan zich te registreren
* Anonieme sitebezoekers mogen de site niet bekijken
* Facultatief al dan niet overseinen onder communautaire leden toestaan
* Aanmelden met Facebook NIET toestaan
* Aanmelden met Twitter NIET toestaan

![chlimage_1-285](assets/chlimage_1-285.png)

#### TAGS {#tagging}

De tags die kunnen worden toegepast op community-inhoud, worden beheerd door AEM naamruimten te selecteren die eerder zijn gedefinieerd via de [Tagingsconsole](../../help/sites-administering/tags.md#tagging-console) (zoals de [Naamruimte voor zelfstudie](enablement-setup.md#create-tutorial-tags)).

Als u bovendien Tagnaamruimten selecteert voor de communitysite, beperkt u de selectie die wordt weergegeven bij het definiëren van catalogi en machtigingsbronnen. Zie [Tags toewijzen](tag-resources.md) voor belangrijke informatie.

Het zoeken naar naamruimten is eenvoudig met &#39;type-ahead&#39;-zoekopdracht. Bijvoorbeeld,

* Type &#39;tut&#39;
* Selecteer `Tutorial`

![chlimage_1-286](assets/chlimage_1-286.png)

### ROLES {#roles}

[Rol van leden van de Gemeenschap](users.md) worden toegewezen via de instellingen in de sectie Rollen.

Als u een lid van de gemeenschap (of groep leden) de site wilt laten ervaren als gemeenschapsbeheerder, gebruikt u de typecontrole en selecteert u de naam van het lid of de groep in de keuzelijst.

Bijvoorbeeld,

* Type &quot;q&quot;
* Selecteren [Quinn Harper](enablement-setup.md#publishcreateenablementmembers)

>[!NOTE]
>
>[Tunneldienst](deploy-communities.md#tunnel-service-on-author) Hiermee kunt u leden en groepen selecteren die alleen in de publicatieomgeving aanwezig zijn.

![community_rollen](assets/community_roles.png)

#### MODERING {#moderation}

Accepteer de standaard algemene instellingen voor [gematigd](sites-console.md#moderation) door de gebruiker gegenereerde inhoud (UGC).

![chlimage_1-287](assets/chlimage_1-287.png)

#### ANALYSE {#analytics}

Selecteer in het keuzemenu het cloudserviceframework Analytics dat voor deze communitysite is geconfigureerd.

De selectie in de schermafbeelding, `Communities`, is het kadervoorbeeld van de [configuratiedocumentatie.](analytics.md#aem-analytics-framework-configuration)

![chlimage_1-288](assets/chlimage_1-288.png)

#### VERTALING {#translation}

De [Vertaalinstellingen](sites-console.md#translation) specificeren of de UGC al dan niet vertaald kan worden en in welke taal, indien dat het geval is.

* Controleren **[!UICONTROL Allow Machine Translation]**
* De standaardinstellingen gebruiken

![chlimage_1-289](assets/chlimage_1-289.png)

#### UITSCHAKELING {#enablement}

Voor een machtigingsgemeenschap is het noodzakelijk om één of meerdere Communautaire Beheerders van Enablement te identificeren.

* **[!UICONTROL Enablement Managers]**
(vereist) Leden van de 
`Community Enablement Managers` Deze groep is beschikbaar om te worden geselecteerd voor het beheer van deze communitysite.

   * Type &quot;s&quot;
   * Selecteer `Sirius Nilson`

* **[!UICONTROL Marketing Cloud Org Id]**
(optioneel) De id van een Adobe Analytics-account die nodig is wanneer [Video-hartslaganalyse](analytics.md#video-heartbeat-analytics) in de rapportage over activering.

![chlimage_1-290](assets/chlimage_1-290.png)

Selecteer **[!UICONTROL Next]**.

### Stap 4: Community-site maken {#step-create-community-site}

Selecteer **[!UICONTROL Create]**.

![chlimage_1-291](assets/chlimage_1-291.png)

Wanneer het proces is voltooid, wordt de map voor de nieuwe site weergegeven in de console Communities - Sites.

![vereffening](assets/enablementsitecreated.png)

### De nieuwe Community-site publiceren {#publish-the-new-community-site}

De gecreeerde plaats zou van de Gemeenschappen - de console van Plaatsen moeten worden beheerd, de zelfde console van waar de nieuwe plaatsen kunnen worden gecreeerd.

Nadat u de map van de communitysite hebt geselecteerd, houdt u de muisaanwijzer boven het sitepictogram, zodat er vier actiepictogrammen worden weergegeven:

![locatiehandelingen](assets/siteactionicons.png)

Als u het pictogram Ovalen selecteert (pictogram Meer handelingen), worden de opties Site exporteren en Site verwijderen weergegeven.

![nieuwe sites](assets/siteactionsnew.png)

Van links naar rechts zijn ze:

* **Site openen**
Selecteer het potloodpictogram om de gemeenschapssite te openen in de modus Bewerken door auteur om paginacomponenten toe te voegen en/of te configureren

* **Site bewerken**
Selecteer het eigenschappenpictogram om de communitysite te openen voor wijziging van eigenschappen, zoals de titel of om het thema te wijzigen

* **Site publiceren**
Selecteer het wereldpictogram om de communitysite te publiceren (standaard op localhost:4503)

* **Site exporteren**
Selecteer het exportpictogram om een pakket te maken van de communitysite waarin beide zijn opgeslagen [pakketbeheer](../../help/sites-administering/package-manager.md) en gedownload.

   UGC is niet opgenomen in het sitepakket.

* **Site verwijderen**
Als u de communitysite wilt verwijderen, selecteert u het pictogram Site verwijderen dat verschijnt wanneer u de muisaanwijzer op de site in de Community Site Console plaatst. Met deze actie verwijdert u alle items die aan de site zijn gekoppeld, zoals UGC, gebruikersgroepen, elementen en databaserecords.

![inschakelen](assets/enablesiteactions.png)

#### Publiceren selecteren {#select-publish}

Selecteer het pictogram van de wereld om de communitysite te publiceren.

![chlimage_1-292](assets/chlimage_1-292.png)

Er wordt een indicatie gegeven dat de site is gepubliceerd.

![chlimage_1-293](assets/chlimage_1-293.png)

## Community-gebruikers en -gebruikersgroepen {#community-users-user-groups}

### Nieuwe gebruikersgroepen in de Gemeenschap melden {#notice-new-community-user-groups}

Samen met de nieuwe communautaire plaats, worden de nieuwe gebruikersgroepen gecreeerd die de aangewezen toestemmingen hebben die voor diverse administratieve functies worden geplaatst. Ga voor meer informatie naar [Gebruikersgroepen voor communitysites](users.md#usergroupsforcommunitysites).

Voor deze nieuwe communautaire plaats, op basis van de plaatsnaam &quot;laat&quot;toe in Stap 1, kunnen de nieuwe gebruikersgroepen die in het publicatiemilieu bestaan van de [Console leden en groepen van gemeenschappen](members.md#groups-console):

![chlimage_1-294](assets/chlimage_1-294.png)

### Leden toewijzen aan de groep van leden voor Community Enable {#assign-members-to-community-enable-members-group}

Op auteur, met de toegelaten tunneldienst, is het mogelijk om toe te wijzen [gebruikers die tijdens de eerste setup zijn gemaakt](enablement-setup.md#publishcreateenablementmembers) aan de communautaire ledengroep voor de nieuwe communautaire site.

Met behulp van de Community Group-console kunnen leden afzonderlijk worden toegevoegd of via lidmaatschap aan een groep worden toegevoegd.

In dit voorbeeld wordt de groep `Community Ski Class` wordt toegevoegd als lid van de groep `Community Enable Members` en lid `Quinn Harper`.

* Navigeren naar **[!UICONTROL Communities > Groups]** console
* Selecteren **[!UICONTROL Community Enable Members]** groep
* Enter `ski` in de **[!UICONTROL Add Members To Group]** zoekvak
* Selecteren **[!UICONTROL Community Ski Class]** (groep studenten)
* Enter `quinn` in het zoekvak
* Selecteren **[!UICONTROL Quinn Harper]** (resablement resource contact)

* Selecteer **[!UICONTROL Save]**

![chlimage_1-295](assets/chlimage_1-295.png)

## Configuraties bij publiceren {#configurations-on-publish}

### http://localhost:4503/content/sites/enable/en.html {#http-localhost-content-sites-enable-en-html}

![chlimage_1-296](assets/chlimage_1-296.png)

### Configureren voor verificatiefout {#configure-for-authentication-error}

Nadat een site is geconfigureerd en geduwd op publiceren, [aanmeldingstoewijzing configureren](sites-console.md#configure-for-authentication-error) ( `Adobe Granite Login Selector Authentication Handler`) op het publicatieexemplaar. Het voordeel is dat wanneer aanmeldingsgegevens niet correct worden ingevoerd, de verificatiefout de aanmeldingspagina van de communautaire site opnieuw weergeeft met een foutbericht.

Voeg een `Login Page Mapping` als

* /content/sites/enable/nl/sign:/content/sites/enable/nl

### (Optioneel) Wijzig de standaardstartpagina {#optional-change-the-default-home-page}

Als u met de publicatiesite werkt voor demonstratiedoeleinden, is het handig om de standaardstartpagina te wijzigen in de nieuwe site.

Hiervoor is het gebruik van [CRX|DE](http://localhost:4503/crx/de) Lite om de [resourcetoewijzing](../../help/sites-deploying/resource-mapping.md) publicatietabel.

Aan de slag

1. Bij publiceren, heb toegang tot CRXDE en login met beheerdervoorrechten

   * Blader bijvoorbeeld naar [http://localhost:4503/crx/de](http://localhost:4503/crx/de) en aanmelden met `admin/admin`

1. Vouw in de projectbrowser uit `/etc/map`
1. Selecteer `http` node

   * Selecteer **[!UICONTROL Create Node]**

      * **Naam** localhost.4503

         (Do *niet* gebruiken `:`)

      * **Type** [schuintrekken:toewijzen](https://sling.apache.org/documentation/the-sling-engine/mappings-for-resource-resolution.html)

1. Met nieuw gemaakt `localhost.4503` knooppunt geselecteerd

   * Eigenschap toevoegen

      * **Naam** sling:match
      * **Type** String
      * **Waarde** localhost.4503/\$

         (Moet eindigen met &#39;$&#39; teken)
   * Eigenschap toevoegen

      * **Naam** sling:internalRedirect
      * **Type** String
      * **Waarde** /content/sites/enable/en.html


1. Selecteer **[!UICONTROL Save All]**
1. (optioneel) De browsergeschiedenis verwijderen
1. Bladeren naar http://localhost:4503/

   * Ga naar http://localhost:4503/content/sites/enable/en.html

>[!NOTE]
>
>Als u wilt uitschakelen, voegt u de opdracht `sling:match` eigenschapswaarde met een &#39;x&#39; - `xlocalhost.4503/$` - en **[!UICONTROL Save All]**.

![chlimage_1-297](assets/chlimage_1-297.png)

#### Problemen oplossen: Fout bij opslaan van kaart {#troubleshooting-error-saving-map}

Als u de wijzigingen niet kunt opslaan, moet u controleren of de knooppuntnaam `localhost.4503`, met een &#39;punt&#39;-scheidingsteken, en niet `localhost:4503` met een &#39;dubbele punt&#39;-scheidingsteken, als `localhost`is geen geldig naamruimtevoorvoegsel.

![chlimage_1-298](assets/chlimage_1-298.png)

#### Problemen oplossen: Doorsturen mislukt {#troubleshooting-fail-to-redirect}

De &#39;**$**&#39; aan het einde van de reguliere expressie `sling:match`tekenreeks is van cruciaal belang, zodat alleen `http://localhost:4503/` wordt toegewezen, anders wordt de omleidingswaarde prepended aan om het even welk weg die na server zou kunnen bestaan:haven in URL. Wanneer AEM probeert om naar de aanmeldingspagina om te leiden, mislukt dit.

## Het aanpassen van de communautaire Plaats {#modifying-the-community-site}

Nadat de site voor het eerst is gemaakt, kunnen auteurs de opdracht [Site openen, pictogram](sites-console.md#authoring-site-content) standaardinstellingen voor AEM ontwerpactiviteiten uit te voeren.

Daarnaast kunnen beheerders de opdracht [Site-pictogram bewerken](sites-console.md#modifying-site-properties) om eigenschappen van de site te wijzigen, zoals de titel.

Vergeet niet om na elke wijziging **Opslaan** en re-**Publiceren** de site.

>[!NOTE]
>
>Als u niet bekend bent met AEM, kunt u de documentatie raadplegen op [basisbehandeling](../../help/sites-authoring/basic-handling.md) en [snelle handleiding voor het ontwerpen van pagina&#39;s](../../help/sites-authoring/qg-page-authoring.md).

### Een catalogus toevoegen {#add-a-catalog}

Het sjabloon voor de communitysite dat voor deze communitysite is gekozen, moet de catalogusfunctie bevatten.

Als dat niet het geval is, kan de catalogusfunctie eenvoudig worden toegevoegd. Hierdoor kunnen andere leden van de gemeenschap die niet zijn toegewezen aan bronnen voor activering of een leerpad, bronnen voor activering selecteren in een catalogus.

Als de sitestructuur al de catalogusfunctie bevat, kan de titel worden gewijzigd.

Als u de structuur van de site wilt wijzigen, navigeert u naar de **[!UICONTROL Communities, Sites]** console, opent `enable` en selecteert u de **Site bewerken** pictogram voor toegang tot de eigenschappen van `Enablement Tutorial`.

Selecteer het deelvenster STRUCTUUR om een catalogus toe te voegen of een bestaande catalogus te wijzigen:

* **Titel**: `Ski Catalog`

* **URL**: `catalog`

* **Alle naamruimten selecteren**: blijven staan.
* Selecteer **[!UICONTROL Save]**

![chlimage_1-299](assets/chlimage_1-299.png)

Gebruik het pictogram Positie om de functie Catalog naar de tweede positie te verplaatsen, na Toewijzingen.

![chlimage_1-300](assets/chlimage_1-300.png)

Selecteren **[!UICONTROL Save]** in de rechterbovenhoek om de wijzigingen in de communitysite op te slaan.

Dan re-**Publiceren** de site.
