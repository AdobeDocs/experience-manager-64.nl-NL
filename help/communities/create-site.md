---
title: Auteur van een nieuwe communautaire site
seo-title: Author a New Community Site
description: Een nieuwe AEM Communities-site maken
seo-description: How to author a new AEM Communities site
uuid: b8557416-cae4-489e-ab3b-e94d56686b7a
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: introduction
content-type: reference
discoiquuid: bf182bb7-e305-45be-aadb-d71efd70f8cb
exl-id: 5d58f9c5-3210-48ef-94a3-805a1a57e3af
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1619'
ht-degree: 1%

---

# Auteur van een nieuwe communautaire site {#author-a-new-community-site}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Een nieuwe Community-site maken {#create-a-new-community-site}

De auteur-instantie gebruiken om een nieuwe communitysite te maken

* Aanmelden met beheerdersrechten
* Vanuit globale navigatie: **[!UICONTROL Navigation > Communities > Sites]**

De console van de Plaatsen van Gemeenschappen verstrekt een tovenaar om door de stappen te begeleiden om een communautaire plaats tot stand te brengen. Het is mogelijk verder te gaan naar de `Next`stap of `Back`naar de vorige stap voordat u de site in de laatste stap toewijst.

Ga als volgt te werk om een nieuwe communitysite te maken:

* Selecteer `Create` knop

![createcommunitysite](assets/createcommunitysite.png)

### Stap 1: Sitesjabloon {#step-site-template}

![createsitetemplate63](assets/createsitetemplate63.png)

Op de [Sjabloonstap voor site](sites-console.md#step2013asitetemplate)Voer een titel, beschrijving, naam voor de URL in en selecteer een sjabloon voor een community-site, bijvoorbeeld:

* **[!UICONTROL Community Site Title]**: `Getting Started Tutorial`

* **[!UICONTROL Community Site Description]**: `A site for engaging with the community.`

* **[!UICONTROL Community Site Root]**: (leeg laten voor standaardhoofdmap `/content/sites`)

* **[!UICONTROL Cloud Configurations]**: (leeg laten als er geen cloudconfiguraties zijn opgegeven) het pad naar de opgegeven cloudconfiguraties bieden.
* **[!UICONTROL Community Site Base Language]**: (ongewijzigd laten voor één taal: Engels) gebruik het keuzemenu om één te kiezen *of meer* basistalen uit de beschikbare talen: Duits, Italiaans, Frans, Japans, Spaans, Portugees (Brazilië), Chinees (traditioneel) en Chinees (vereenvoudigd). Er wordt één communitysite gemaakt voor elke toegevoegde taal en deze site bestaat in dezelfde sitemap volgens de in [Inhoud vertalen voor meertalige sites](../../help/sites-administering/translation.md). De hoofdpagina van elke site bevat een onderliggende pagina met de taalcode van een van de geselecteerde talen, zoals &#39;en&#39; voor Engels of &#39;fr&#39; voor Frans.

* **[!UICONTROL Community Site Name]**: aangaan

   * Controleer de naam tweemaal omdat deze na het maken van de site niet gemakkelijk kan worden gewijzigd
   * De eerste URL wordt onder de naam van de communautaire site weergegeven
   * Voeg voor een geldige URL een basistaalcode + &quot;.html&quot; toe
   * *Bijvoorbeeld*, http://localhost:4502/content/sites/ `engage/en.html`

* **[!UICONTROL Template]**: naar beneden halen om te kiezen `Reference Site`

Selecteer **[!UICONTROL Next]**

### Stap 2: Ontwerp {#step-design}

De stap Ontwerp wordt in twee secties weergegeven voor het selecteren van het thema en de brandingbanner:

#### COMMUNAUTAIR SITE-THEMA {#community-site-theme}

Selecteer de gewenste stijl die u op de sjabloon wilt toepassen. Als deze optie is geselecteerd, wordt het thema bedekt met een vinkje.

![sitethema](assets/sitetheme.png)

#### COMMUNAUTAIRE SITOBRANDING {#community-site-branding}

(Optioneel) Upload een bannerafbeelding voor weergave op de sitepagina&#39;s. De banner is vastgezet aan de linkerrand van browser, tussen de communautaire plaatsheader en menu (navigatiekoppelingen). De bannerhoogte wordt bijgesneden tot 120 pixels. Er wordt geen grootte van de banner aangepast aan de breedte van de browser en de hoogte van 120 pixels.

![chlimage_1-353](assets/chlimage_1-353.png) ![chlimage_1-354](assets/chlimage_1-354.png)

Selecteer **[!UICONTROL Next]**.

### Stap 3: Instellingen {#step-settings}

Selecteer in de stap Instellingen voordat u `Next`Er zijn zeven secties die toegang bieden tot configuraties met gebruikersbeheer, codering, moderatie, groepsbeheer, analyse, vertaling en activering.

Ga naar [Aan de slag met AEM Communities for Enablement](getting-started-enablement.md) zelfstudie voor het werken met de functies voor activering.

#### GEBRUIKERSBEHEER {#user-management}

Alle selectievakjes inschakelen voor [Gebruikersbeheer](sites-console.md#user-management)

* Sitebezoekers toestaan zich te registreren
* Site-bezoekers toestaan de site weer te geven zonder zich aan te melden
* Leden toestaan berichten van andere leden van de gemeenschap te verzenden en te ontvangen
* Aanmelden met Facebook toestaan in plaats van zich te registreren en een profiel te maken
* Aanmelden met Twitter toestaan in plaats van zich te registreren en een profiel te maken

>[!NOTE]
>
>Voor een productieomgeving is het nodig om aangepaste Facebook- en Twitter-toepassingen te maken. Zie [Sociale aanmelding met Facebook en Twitter](social-login.md).

![creaties](assets/createsitesettings.png)

#### TAGS {#tagging}

De tags die kunnen worden toegepast op community-inhoud, worden beheerd door AEM naamruimten te selecteren die eerder zijn gedefinieerd via de [Tagingsconsole](../../help/sites-administering/tags.md#tagging-console) (zoals de [Naamruimte voor zelfstudie](setup.md#create-tutorial-tags)).

Het zoeken naar naamruimten is eenvoudig met &#39;type-ahead&#39;-zoekopdracht. Bijvoorbeeld,

* Type &#39;tut&#39;
* Selecteer `Tutorial`

![chlimage_1-355](assets/chlimage_1-355.png)

#### ROLES {#roles}

[Rol van leden van de Gemeenschap](users.md) worden toegewezen via de instellingen in de sectie Rollen.

Als u een lid van de gemeenschap (of groep leden) de site wilt laten ervaren als gemeenschapsbeheerder, gebruikt u de typecontrole en selecteert u de naam van het lid of de groep in de keuzelijst.

Bijvoorbeeld,

* Type &quot;q&quot;
* Selecteren [Quinn Harper](enablement-setup.md#publishcreateenablementmembers)

>[!NOTE]
>
>[Tunneldienst](https://helpx.adobe.com/experience-manager/6-3/communities/using/deploy-communities.html#tunnel-service-on-author) Hiermee kunt u leden en groepen selecteren die alleen in de publicatieomgeving aanwezig zijn.

![community_rollen-1](assets/community_roles-1.png)

#### MODERING {#moderation}

Accepteer de standaard algemene instellingen voor [gematigd](sites-console.md#moderation) door de gebruiker gegenereerde inhoud (UGC).

![chlimage_1-356](assets/chlimage_1-356.png)

#### ANALYSE {#analytics}

Als Adobe Analytics een licentie heeft en er een cloudservice en -framework voor Analytics zijn geconfigureerd, is het mogelijk Analytics in te schakelen en het framework te selecteren.

Zie [Analytische configuratie voor functies van Gemeenschappen](analytics.md).

![chlimage_1-357](assets/chlimage_1-357.png)

#### VERTALING {#translation}

De [Vertaalinstellingen](sites-console.md#translation) de basistaal voor de site en of UGC al dan niet kan worden vertaald en in welke taal, indien dat het geval is.

* Controleren **[!UICONTROL Allow Machine Translation]**
* Laat standaardtalen geselecteerd blijven voor vertaling door de standaardvertaalservice voor machines
* Standaard vertaalprovider en config laten staan
* Er is geen behoefte aan een globale opslag omdat er geen taalexemplaren zijn
* Selecteer **[!UICONTROL Translate entire page]**
* De optie Standaardpersistentie behouden

![chlimage_1-358](assets/chlimage_1-358.png)

#### UITSCHAKELING {#enablement}

Laat leeg als u een betrokkenheidsgemeenschap maakt.

Voor een vergelijkbare zelfstudie kunt u snel een [enablement community](overview.md#enablement-community), zie [Aan de slag met AEM Communities for Enablement](getting-started-enablement.md).

Selecteer **[!UICONTROL Next]**.

### Stap 4: Communitysite maken {#step-create-communities-site}

Selecteer **[!UICONTROL Create]**.

![chlimage_1-359](assets/chlimage_1-359.png)

Wanneer het proces is voltooid, wordt de map voor de nieuwe site weergegeven in de console Communities - Sites.

![communautiessitesconsole](assets/communitiessitesconsole.png)

## De nieuwe Community-site publiceren {#publish-the-new-community-site}

De gecreeerde plaats zou van de Gemeenschappen - de console van Plaatsen moeten worden beheerd, de zelfde console van waar de nieuwe plaatsen kunnen worden gecreeerd.

Nadat u de map van de communitysite hebt geselecteerd om deze te openen, houdt u de muisaanwijzer boven het sitepictogram, zodat er vier actiepictogrammen worden weergegeven:

![site-actionicons-1](assets/siteactionicons-1.png)

Als u het vierde ovalenpictogram selecteert (Meer handelingen), worden de opties Site exporteren en Site verwijderen weergegeven.

![site-actionsnew-1](assets/siteactionsnew-1.png)

Van links naar rechts zijn ze:

* **Site openen**
Selecteer het potloodpictogram om de gemeenschapssite te openen in de modus Bewerken door auteur om paginacomponenten toe te voegen en/of te configureren

* **Site bewerken**
Selecteer het eigenschappenpictogram om de communitysite te openen voor wijziging van eigenschappen, zoals de titel of om het thema te wijzigen

* **Site publiceren**
Selecteer het wereldpictogram om de communitysite te publiceren (bijvoorbeeld als uw publicatieserver op uw lokale computer wordt uitgevoerd en vervolgens standaard naar localhost:4503)

* **Site exporteren**
Selecteer het exportpictogram om een pakket te maken van de communitysite waarin beide zijn opgeslagen [pakketbeheer](../../help/sites-administering/package-manager.md) en gedownload.

   UGC is niet opgenomen in het sitepakket.

* **Site verwijderen**

   selecteer het verwijderpictogram om de community-site te verwijderen van binnenuit **[!UICONTROL Communities > Sites console]**. Met deze actie verwijdert u alle items die aan de site zijn gekoppeld, zoals UGC, gebruikersgroepen, elementen en databaserecords.

![site-1](assets/siteactions-1.png)

>[!NOTE]
>
>Als het gebruiken van standaardhaven 4503 voor publiceer instantie, dan geef de standaard replicatieagent uit om het havenaantal aan de correcte waarde te plaatsen.
>
>In de auteurinstantie, van het belangrijkste menu
>
>1. Navigeren naar **[!UICONTROL Tools > Operations > Replication]** menu
>1. Selecteer **[!UICONTROL Agents on author]**
>1. Selecteer **[!UICONTROL Default Agent (publish)]**
>1. Volgende tot **[!UICONTROL Settings]** selecteren **[!UICONTROL Edit]**
>1. In pop-up dialoog voor de Montages van de Agent, het uitgezochte lusje van het Vervoer
>1. Wijzig in URI het poortnummer 4503 in het gewenste poortnummer

>
>Als u bijvoorbeeld poort 6103 wilt gebruiken: `http://localhost:6103/bin/receive?sling:authRequestLogin=1`
>
>1. Selecteer **[!UICONTROL OK]**
>1. (Optioneel) Selecteer `Clear` of `Force Retry` om de replicatiewachtrij opnieuw in te stellen


### Publiceren selecteren {#select-publish}

Nadat u ervoor hebt gezorgd dat de publicatieserver actief is, selecteert u het wereldpictogram om de communitysite te publiceren.

![chlimage_1-360](assets/chlimage_1-360.png)

Wanneer de community-site is gepubliceerd, wordt kort een bericht weergegeven:

![chlimage_1-361](assets/chlimage_1-361.png)

### Nieuwe gebruikersgroepen in de Gemeenschap melden {#notice-new-community-user-groups}

Samen met de nieuwe communautaire plaats, worden de nieuwe gebruikersgroepen gecreeerd die de aangewezen toestemmingen hebben die voor diverse administratieve functies worden geplaatst. Ga voor meer informatie naar [Gebruikersgroepen voor communitysites](users.md#usergroupsforcommunitysites).

Voor deze nieuwe communautaire plaats, gezien de plaatsnaam &quot;verbind&quot;in Stap 1, kunnen de vier nieuwe gebruikersgroepen van worden gezien [Groepsconsole](members.md) (globale navigatie: Gemeenschappen, groepen):

* Community Engineeringmanagers
* Community Engineering Group-beheerders
* Samenvoegingsleden van gemeenschap
* Maatschappelijke experts
* Gemoonde leden van Community Engineering
* Community Engineering Sitecontentmanager

Let op: [Aaron McDonald](tutorials.md#demo-users) lid is van

* Community Engineeringmanagers
* Maatschappelijke experts
* Community Engage-leden (indirect als lid van de groep Moderatoren)

![chlimage_1-362](assets/chlimage_1-362.png)

#### http://localhost:4503/content/sites/engage/en.html {#http-localhost-content-sites-engage-en-html}

![chlimage_1-363](assets/chlimage_1-363.png)

## Configureren voor verificatiefout {#configure-for-authentication-error}

Nadat een site is geconfigureerd en geduwd op publiceren, [aanmeldingstoewijzing configureren](sites-console.md#configure-for-authentication-error) ( `Adobe Granite Login Selector Authentication Handler`) op het publicatieexemplaar. Het voordeel is dat wanneer aanmeldingsgegevens niet correct worden ingevoerd, de verificatiefout de aanmeldingspagina van de communautaire site opnieuw weergeeft met een foutbericht.

Voeg een `Login Page Mapping` als

* /content/sites/engc/nl/sign:/content/sites/engc/nl

## Optionele stappen {#optional-steps}

### De standaardstartpagina wijzigen {#change-the-default-home-page}

Als u met de publicatiesite werkt voor demonstratiedoeleinden, is het handig om de standaardstartpagina te wijzigen in de nieuwe site.

Hiervoor is het gebruik van [CRXDE](http://localhost:4503/crx/de) Lite om de [resourcetoewijzing](../../help/sites-deploying/resource-mapping.md) publicatietabel.

Aan de slag:

1. Meld u bij publicatie aan met beheerdersrechten
1. Bladeren naar [http://localhost:4503/crx/de](http://localhost:4503/crx/de)
1. Vouw in de projectbrowser uit `/etc/map`
1. Selecteer `http` node

   * Selecteer **[!UICONTROL Create Node]**

      * **Naam** localhost.4503

         (do *niet* gebruiken `:`)

      * **Type** [schuintrekken:toewijzen](https://sling.apache.org/documentation/the-sling-engine/mappings-for-resource-resolution.html)

1. Met nieuw gemaakt `localhost.4503` knooppunt geselecteerd

   * Eigenschap toevoegen

      * **Naam** sling:match
      * **Type** String
      * **Waarde** localhost.4503/\$

         (moet eindigen met &#39;$&#39; teken)
   * Eigenschap toevoegen

      * **Naam** sling:internalRedirect
      * **Type** String
      * **Waarde** /content/sites/engage/en.html


1. Selecteer **[!UICONTROL Save All]**
1. (optioneel) De browsergeschiedenis verwijderen
1. Bladeren naar http://localhost:4503/

   * Ga naar http://localhost:4503/content/sites/engage/en.html

>[!NOTE]
>
>Als u wilt uitschakelen, voegt u de opdracht `sling:match` eigenschapswaarde met een &#39;x&#39; - `xlocalhost.4503/$` - en **[!UICONTROL Save All]**.

![chlimage_1-364](assets/chlimage_1-364.png)

#### Problemen oplossen: Fout bij opslaan van kaart {#troubleshooting-error-saving-map}

Als u de wijzigingen niet kunt opslaan, moet u controleren of de knooppuntnaam `localhost.4503`, met een &#39;punt&#39;-scheidingsteken, en niet `localhost:4503` met een &#39;dubbele punt&#39;-scheidingsteken, als `localhost`is geen geldig naamruimtevoorvoegsel.

![chlimage_1-365](assets/chlimage_1-365.png)

#### Problemen oplossen: Doorsturen mislukt {#troubleshooting-fail-to-redirect}

De &#39;**$**&#39; aan het einde van de reguliere expressie `sling:match`tekenreeks is van cruciaal belang, zodat alleen `http://localhost:4503/` wordt toegewezen, anders wordt de omleidingswaarde prepended aan om het even welk weg die na server zou kunnen bestaan:haven in URL. Wanneer AEM probeert om naar de aanmeldingspagina om te leiden, mislukt dit.

### De site wijzigen {#modify-the-site}

Nadat de site voor het eerst is gemaakt, kunnen auteurs de opdracht [Site openen, pictogram](sites-console.md#authoring-site-content) standaardinstellingen voor AEM ontwerpactiviteiten uit te voeren.

Daarnaast kunnen beheerders de opdracht [Site-pictogram bewerken](sites-console.md#modifying-site-properties) om eigenschappen van de site te wijzigen, zoals de titel.

Vergeet niet om na elke wijziging **opslaan** en **opnieuw publiceren** de site.

>[!NOTE]
>
>Als u niet bekend bent met AEM, kunt u de documentatie raadplegen op [basisbehandeling](../../help/sites-authoring/basic-handling.md) en [snelle handleiding voor het ontwerpen van pagina&#39;s](../../help/sites-authoring/qg-page-authoring.md).
