---
title: Auteur van een nieuwe communautaire site
seo-title: Auteur van een nieuwe communautaire site
description: Een nieuwe AEM Communities-site maken
seo-description: Een nieuwe AEM Communities-site maken
uuid: b8557416-cae4-489e-ab3b-e94d56686b7a
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: introduction
content-type: reference
discoiquuid: bf182bb7-e305-45be-aadb-d71efd70f8cb
translation-type: tm+mt
source-git-commit: 3d2b91565e14e85e9e701663c8d0ded03e5b430c
workflow-type: tm+mt
source-wordcount: '1596'
ht-degree: 1%

---


# Auteur een Nieuwe Communautaire Plaats {#author-a-new-community-site}

## Een nieuwe communautaire site maken {#create-a-new-community-site}

De auteur-instantie gebruiken om een nieuwe communitysite te maken

* Aanmelden met beheerdersrechten
* Vanuit globale navigatie: **[!UICONTROL Navigation > Communities > Sites]**

De console van de Plaatsen van Gemeenschappen verstrekt een tovenaar om door de stappen te begeleiden om een communautaire plaats tot stand te brengen. U kunt naar de `Next`stap of `Back`vorige stap gaan voordat u de site in de laatste stap toewijst.

Ga als volgt te werk om een nieuwe communitysite te maken:

* Selecteer de knop `Create`

![createcommunitysite](assets/createcommunitysite.png)

### Stap 1: Sitesjabloon {#step-site-template}

![createsitetemplate63](assets/createsitetemplate63.png)

Voer in de stap [Sjabloon site](sites-console.md#step2013asitetemplate) een titel, beschrijving, naam voor de URL in en selecteer bijvoorbeeld een sjabloon voor een communitysite:

* **[!UICONTROL Community Site Title]**: `Getting Started Tutorial`

* **[!UICONTROL Community Site Description]**:  `A site for engaging with the community.`

* **[!UICONTROL Community Site Root]**: (leeg laten voor standaardhoofdmap  `/content/sites`)

* **[!UICONTROL Cloud Configurations]**: (leeg laten als er geen cloudconfiguraties zijn opgegeven) het pad naar de opgegeven cloudconfiguraties bieden.
* **[!UICONTROL Community Site Base Language]**: (ongewijzigd laten voor één taal: (Engels) gebruik het keuzemenu om één  *of* meer basistalen te kiezen uit de beschikbare talen: Duits, Italiaans, Frans, Japans, Spaans, Portugees (Brazilië), Chinees (Traditioneel) en Chinees (Vereenvoudigd). Er wordt één communitysite gemaakt voor elke toegevoegde taal en deze wordt in dezelfde sitemap gebruikt volgens de best practices die worden beschreven in [Inhoud vertalen voor meertalige sites](../../help/sites-administering/translation.md). De hoofdpagina van elke site bevat een onderliggende pagina met de taalcode van een van de geselecteerde talen, zoals &#39;en&#39; voor Engels of &#39;fr&#39; voor Frans.

* **[!UICONTROL Community Site Name]**: aangaan

   * Controleer de naam tweemaal omdat deze na het maken van de site niet gemakkelijk kan worden gewijzigd
   * De eerste URL wordt onder de naam van de communautaire site weergegeven
   * Voeg voor een geldige URL een basistaalcode + &quot;.html&quot; toe
   * *Bijvoorbeeld* http://localhost:4502/content/sites/  `engage/en.html`

* **[!UICONTROL Template]**: naar beneden halen om te kiezen  `Reference Site`

Selecteer **[!UICONTROL Next]**

### Stap 2: Ontwerp {#step-design}

De stap Ontwerp wordt in twee secties weergegeven voor het selecteren van het thema en de brandingbanner:

#### THEMA VAN COMMUNAUTAIRE SITE {#community-site-theme}

Selecteer de gewenste stijl die u op de sjabloon wilt toepassen. Als deze optie is geselecteerd, wordt het thema bedekt met een vinkje.

![sitethema](assets/sitetheme.png)

#### COMMUNAUTAIRE SITEBRANDING {#community-site-branding}

(Optioneel) Upload een bannerafbeelding voor weergave op de sitepagina&#39;s. De banner is vastgezet aan de linkerrand van browser, tussen de communautaire plaatsheader en menu (navigatiekoppelingen). De bannerhoogte wordt bijgesneden tot 120 pixels. Er wordt geen grootte van de banner aangepast aan de breedte van de browser en de hoogte van 120 pixels.

![chlimage_1-353](assets/chlimage_1-353.png) ![chlimage_1-354](assets/chlimage_1-354.png)

Selecteer **[!UICONTROL Next]**.

### Stap 3: Instellingen {#step-settings}

Voor de stap van Montages, alvorens `Next` te selecteren, merk er zeven secties zijn die toegang tot configuraties verlenen die gebruikersbeheer, etiketteren, moderatie, groepsbeheer, analyses, vertaling en enablement impliceren.

Bezoek de zelfstudie [Aan de slag met AEM Communities for Enablement](getting-started-enablement.md) om te werken met de functies voor activering.

#### GEBRUIKERSBEHEER {#user-management}

Schakel alle selectievakjes in voor [Gebruikersbeheer](sites-console.md#user-management)

* Sitebezoekers toestaan zich te registreren
* Site-bezoekers toestaan de site weer te geven zonder zich aan te melden
* Leden toestaan berichten van andere leden van de gemeenschap te verzenden en te ontvangen
* Aanmelden met Facebook toestaan in plaats van zich te registreren en een profiel te maken
* Aanmelden met Twitter toestaan in plaats van zich te registreren en een profiel te maken

>[!NOTE]
>
>Voor een productieomgeving moeten aangepaste Facebook- en Twitter-toepassingen worden gemaakt. Zie [Sociale aanmelding bij Facebook en Twitter](social-login.md).

![creaties](assets/createsitesettings.png)

#### TAGS {#tagging}

De tags die kunnen worden toegepast op community-inhoud, worden beheerd door AEM naamruimten te selecteren die eerder zijn gedefinieerd via de [Tagingconsole](../../help/sites-administering/tags.md#tagging-console) (zoals de [Zelfstudie-naamruimte](setup.md#create-tutorial-tags)).

Het zoeken naar naamruimten is eenvoudig met &#39;type-ahead&#39;-zoekopdracht. Bijvoorbeeld,

* Type &#39;tut&#39;
* Selecteer `Tutorial`

![chlimage_1-355](assets/chlimage_1-355.png)

#### ROLLEN {#roles}

[De communautaire ](users.md) leden worden toegewezen door de montages in de sectie van Rollen.

Als u een lid van de gemeenschap (of groep leden) de site wilt laten ervaren als gemeenschapsbeheerder, gebruikt u de typecontrole en selecteert u de naam van het lid of de groep in de keuzelijst.

Bijvoorbeeld,

* Type &quot;q&quot;
* Selecteer [Quinn Harper](enablement-setup.md#publishcreateenablementmembers)

>[!NOTE]
>
>[Met de tunnelservice ](https://helpx.adobe.com/experience-manager/6-3/communities/using/deploy-communities.html#tunnel-service-on-author) kunt u leden en groepen selecteren die alleen in de publicatieomgeving aanwezig zijn.

![community_rollen-1](assets/community_roles-1.png)

#### MODERING {#moderation}

Accepteer de standaard algemene instellingen voor [het modereren](sites-console.md#moderation) door de gebruiker gegenereerde inhoud (UGC).

![chlimage_1-356](assets/chlimage_1-356.png)

#### ANALYSE {#analytics}

Als Adobe Analytics een licentie heeft en er een cloudservice en -framework voor Analytics zijn geconfigureerd, is het mogelijk Analytics in te schakelen en het framework te selecteren.

Zie [Analyseconfiguratie voor Gemeenschappen-functies](analytics.md).

![chlimage_1-357](assets/chlimage_1-357.png)

#### TRANSLATION {#translation}

Met de [Vertaalinstellingen](sites-console.md#translation) wordt de basistaal voor de site opgegeven en wordt aangegeven of UGC al dan niet kan worden vertaald en in welke taal, indien dat het geval is.

* Vinkje **[!UICONTROL Allow Machine Translation]**
* Laat standaardtalen geselecteerd blijven voor vertaling door de standaardvertaalservice voor machines
* Standaard vertaalprovider en config laten staan
* Er is geen behoefte aan een globale opslag omdat er geen taalexemplaren zijn
* Selecteer **[!UICONTROL Translate entire page]**
* De optie Standaardpersistentie behouden

![chlimage_1-358](assets/chlimage_1-358.png)

#### INSCHAKELEN {#enablement}

Laat leeg als u een betrokkenheidsgemeenschap maakt.

Zie [Aan de slag met AEM Communities for Enablement](getting-started-enablement.md) voor een vergelijkbare zelfstudie om snel een [enablement community](overview.md#enablement-community) te maken.

Selecteer **[!UICONTROL Next]**.

### Stap 4: Communitysite {#step-create-communities-site} maken

Selecteer **[!UICONTROL Create]**.

![chlimage_1-359](assets/chlimage_1-359.png)

Wanneer het proces is voltooid, wordt de map voor de nieuwe site weergegeven in de console Communities - Sites.

![communautiessitesconsole](assets/communitiessitesconsole.png)

## De nieuwe communautaire site publiceren {#publish-the-new-community-site}

De gecreeerde plaats zou van de Gemeenschappen - de console van Plaatsen moeten worden beheerd, de zelfde console van waar de nieuwe plaatsen kunnen worden gecreeerd.

Nadat u de map van de communitysite hebt geselecteerd om deze te openen, houdt u de muisaanwijzer boven het sitepictogram, zodat er vier actiepictogrammen worden weergegeven:

![site-actionicons-1](assets/siteactionicons-1.png)

Als u het vierde ovalenpictogram selecteert (Meer handelingen), worden de opties Site exporteren en Site verwijderen weergegeven.

![site-actionsnew-1](assets/siteactionsnew-1.png)

Van links naar rechts zijn ze:

* **Open**
SiteSelecteer het potloodpictogram om de gemeenschapssite te openen in de modus Bewerken door auteur om paginacomponenten toe te voegen en/of te configureren

* **Site bewerkenSelecteer het eigenschappenpictogram om de site van de community te openen voor wijziging van eigenschappen, zoals de titel, of om het thema te wijzigen**


* **Publiceer**
SiteSelecteer het wereldpictogram om de communitysite te publiceren (bijvoorbeeld als uw publicatieserver op uw lokale computer wordt uitgevoerd en vervolgens standaard naar localhost:4503)

* **Exporteer**
SiteSelecteer het exportpictogram om een pakket van de communitysite te maken dat zowel in  [pakketbeheer wordt opgeslagen als wordt ](../../help/sites-administering/package-manager.md) gedownload.

   UGC is niet opgenomen in het sitepakket.

* **Site verwijderen**

   Selecteer het verwijderpictogram om de communitysite te verwijderen uit **[!UICONTROL Communities > Sites console]**. Met deze actie verwijdert u alle items die aan de site zijn gekoppeld, zoals UGC, gebruikersgroepen, elementen en databaserecords.

![site-1](assets/siteactions-1.png)

>[!NOTE]
>
>Als het gebruiken van standaardhaven 4503 voor publiceer instantie, dan geef de standaard replicatieagent uit om het havenaantal aan de correcte waarde te plaatsen.
>
>In de auteurinstantie, van het belangrijkste menu
>
>1. Naar menu **[!UICONTROL Tools > Operations > Replication]** gaan
>1. Selecteer **[!UICONTROL Agents on author]**
>1. Selecteer **[!UICONTROL Default Agent (publish)]**
>1. Naast **[!UICONTROL Settings]** selecteert u **[!UICONTROL Edit]**
>1. In pop-up dialoog voor de Montages van de Agent, het uitgezochte lusje van het Vervoer
>1. Wijzig in URI het poortnummer 4503 in het gewenste poortnummer

>
>
Als u bijvoorbeeld poort 6103 wilt gebruiken: `http://localhost:6103/bin/receive?sling:authRequestLogin=1`
>
>1. Selecteer **[!UICONTROL OK]**
>1. (Optioneel) Selecteer `Clear` of `Force Retry` om de replicatiewachtrij opnieuw in te stellen


### Publiceren {#select-publish} selecteren

Nadat u ervoor hebt gezorgd dat de publicatieserver actief is, selecteert u het wereldpictogram om de communitysite te publiceren.

![chlimage_1-360](assets/chlimage_1-360.png)

Wanneer de community-site is gepubliceerd, wordt kort een bericht weergegeven:

![chlimage_1-361](assets/chlimage_1-361.png)

### Nieuwe gebruikersgroepen van de Gemeenschap {#notice-new-community-user-groups} melden

Samen met de nieuwe communautaire plaats, worden de nieuwe gebruikersgroepen gecreeerd die de aangewezen toestemmingen hebben die voor diverse administratieve functies worden geplaatst. Voor details, bezoek [Gebruikersgroepen voor Communautaire Plaatsen](users.md#usergroupsforcommunitysites).

Voor deze nieuwe communautaire plaats, gezien de plaatsnaam &quot;verbind&quot;in Stap 1, kunnen de vier nieuwe gebruikersgroepen van de [console van Groepen](members.md) (globale navigatie: Gemeenschappen, groepen):

* Community Engineeringmanagers
* Community Engineering Group-beheerders
* Samenvoegingsleden van gemeenschap
* Maatschappelijke experts
* Gemoonde leden van Community Engineering
* Community Engineering Sitecontentmanager

Merk op dat [Aaron McDonald](tutorials.md#demo-users) lid is van

* Community Engineeringmanagers
* Maatschappelijke experts
* Community Engage-leden (indirect als lid van de groep Moderatoren)

![chlimage_1-362](assets/chlimage_1-362.png)

#### http://localhost:4503/content/sites/engage/en.html {#http-localhost-content-sites-engage-en-html}

![chlimage_1-363](assets/chlimage_1-363.png)

## Configureren voor verificatiefout {#configure-for-authentication-error}

Nadat een site is geconfigureerd en geduwd op publiceren, [configureert u de aanmeldingstoewijzing](sites-console.md#configure-for-authentication-error) ( `Adobe Granite Login Selector Authentication Handler`) op de publicatieinstantie. Het voordeel is dat wanneer aanmeldingsgegevens niet correct worden ingevoerd, de verificatiefout de aanmeldingspagina van de communautaire site opnieuw weergeeft met een foutbericht.

Een `Login Page Mapping` toevoegen als

* /content/sites/engc/nl/sign:/content/sites/engc/nl

## Optionele stappen {#optional-steps}

### De standaardstartpagina {#change-the-default-home-page} wijzigen

Als u met de publicatiesite werkt voor demonstratiedoeleinden, is het handig om de standaardstartpagina te wijzigen in de nieuwe site.

Hiervoor moet u [CRXDE](http://localhost:4503/crx/de) Lite gebruiken om de [bronnentoewijzing](../../help/sites-deploying/resource-mapping.md)-tabel bij publicatie te bewerken.

Aan de slag:

1. Meld u bij publicatie aan met beheerdersrechten
1. Bladeren naar [http://localhost:4503/crx/de](http://localhost:4503/crx/de)
1. Vouw `/etc/map` in de projectbrowser uit
1. Selecteer de `http` knoop

   * Selecteer **[!UICONTROL Create Node]**

      * **** Namelocalhost.4503

         (gebruik *not* `:`)

      * **** [lettertypen:toewijzen](https://sling.apache.org/documentation/the-sling-engine/mappings-for-resource-resolution.html)

1. Met nieuw aangemaakt `localhost.4503`-knooppunt geselecteerd

   * Eigenschap toevoegen

      * **** naamgeving:overeenkomst
      * **** TypeString
      * **** Valuelocalhost.4503/\$

         (moet eindigen met &#39;$&#39; teken)
   * Eigenschap toevoegen

      * **** naamgeving:internalRedirect
      * **** TypeString
      * **Waarde** /content/sites/engage/en.html


1. Selecteer **[!UICONTROL Save All]**
1. (optioneel) De browsergeschiedenis verwijderen
1. Bladeren naar http://localhost:4503/

   * Ga naar http://localhost:4503/content/sites/engage/en.html

>[!NOTE]
>
>Als u deze optie wilt uitschakelen, voegt u de waarde van de eigenschap `sling:match` gewoon aan met een &#39;x&#39; - `xlocalhost.4503/$` - en **[!UICONTROL Save All]**.

![chlimage_1-364](assets/chlimage_1-364.png)

#### Problemen oplossen: Fout bij opslaan van kaart {#troubleshooting-error-saving-map}

Als u wijzigingen niet kunt opslaan, moet u ervoor zorgen dat de knooppuntnaam `localhost.4503` is, met een &#39;punt&#39;-scheidingsteken en niet `localhost:4503` met een &#39;dubbele punt&#39;-scheidingsteken, omdat `localhost`geen geldig naamruimtevoorvoegsel is.

![chlimage_1-365](assets/chlimage_1-365.png)

#### Problemen oplossen: Kan {#troubleshooting-fail-to-redirect} niet omleiden

De tekenreeks &#39;**$**&#39; aan het einde van de reguliere expressie `sling:match`is van cruciaal belang, zodat alleen exact `http://localhost:4503/` wordt toegewezen. Anders wordt de omleidingswaarde toegevoegd aan elk pad dat mogelijk bestaat na de server:poort in de URL. Wanneer AEM probeert om naar de aanmeldingspagina om te leiden, mislukt dit.

### De site {#modify-the-site} wijzigen

Nadat de site voor het eerst is gemaakt, kunnen auteurs het [pictogram Open Site](sites-console.md#authoring-site-content) gebruiken om standaard AEM ontwerpactiviteiten uit te voeren.

Daarnaast kunnen beheerders het [Sitepictogram bewerken](sites-console.md#modifying-site-properties) gebruiken om eigenschappen van de site, zoals de titel, te wijzigen.

Na om het even welke wijziging, herinner aan **save** en **herpubliceer** de plaats.

>[!NOTE]
>
>Als u niet bekend bent met AEM, bekijkt u de documentatie over [basisverwerking](../../help/sites-authoring/basic-handling.md) en een [handleiding voor het schrijven van pagina&#39;s](../../help/sites-authoring/qg-page-authoring.md).