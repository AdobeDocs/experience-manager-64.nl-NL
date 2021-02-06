---
title: AEM Forms-referentiesites instellen en configureren
seo-title: AEM Forms-referentiesites instellen en configureren
description: AEM Forms-referentiesites laten zien hoe u AEM Forms kunt gebruiken om end-to-end workflow in een organisatie te implementeren.
seo-description: AEM Forms-referentiesites laten zien hoe u AEM Forms kunt gebruiken om end-to-end workflow in een organisatie te implementeren.
uuid: 087d58a1-d84e-49ac-a82d-4e7fc708f00f
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: introduction
discoiquuid: 2feb4a9c-57ad-4c6b-a572-0047bc409bbb
translation-type: tm+mt
source-git-commit: 6a8fa45ec61014acebe09048066972ecb1284641
workflow-type: tm+mt
source-wordcount: '2752'
ht-degree: 0%

---


# AEM Forms-referentiesites instellen en configureren {#set-up-and-configure-aem-forms-reference-sites}

AEM Forms biedt implementatie van referentiesite om aan te tonen hoe AEM Forms organisaties van de Financial Services Industry en de overheid helpt om hun complexe transacties om te zetten in eenvoudige en aantrekkelijke digitale ervaringen op elk apparaat, waar en wanneer dan ook.

Wij.Financiën en Wij.Gov de verwijzingsplaatsen trekken echte gebruiksgevallen om met bestaande en potentiële klanten, van het punt van eerste aanraking tot het beheren van correspondentie en transacties op een gepersonaliseerde en rendabele manier in dienst te nemen.

Met de referentiesites kunt u de volgende belangrijke mogelijkheden van AEM Forms verkennen en weergeven.

* Vereenvoudigde ontwerpervaring met aantrekkelijke en responsieve adaptieve formulieren en interactieve communicatie.
* Interactieve Mededelingen om interactieve, gepersonaliseerde, en ontvankelijke klantenmededelingen tot stand te brengen die aan het apparaat het plaatsen en de lay-out aanpassen.
* Gegevensintegratie om verbinding te maken met verschillende gegevensbronnen om formuliergegevens vooraf in te vullen en te verzenden via een formuliergegevensmodel.
* Forms-workflow om bedrijfsprocessen en workflows te automatiseren.
* Geavanceerde mogelijkheden voor gegevensbeheer en -verwerking door gebruikers.
* Integratie met Adobe Sign om adaptieve formulieren veilig te ondertekenen en te verzenden.
* Integratie met Adobe Target voor gerichte aanbevelingen en A/B-tests om het rendement van investeringen vanuit een formulier te maximaliseren.
* Integratie met Adobe Analytics om de prestaties van een formulier of campagne te meten en geïnformeerde beslissingen te nemen.
* Verbeterde functionaliteit voor het invullen van formulieren.

De referentiesites bieden herbruikbare elementen die u als sjablonen kunt gebruiken om uw eigen elementen te maken.

* Integratie met Adobe Sign om adaptieve formulieren veilig te ondertekenen en te verzenden.

* Integratie met Adobe Sign om adaptieve formulieren veilig te ondertekenen en te verzenden.

## Vereisten en stappen voor het instellen van referentiesites {#prerequisites-and-steps-to-set-up-reference-sites}

Voordat u de referentiesite instelt, moet u het volgende doen:

* **AEM**

   AEM QuickStart-, AEM Forms-add-on-pakket en referentiesite-pakketten. Zie [AEM Forms releases](https://helpx.adobe.com/aem-forms/kb/aem-forms-releases.html) voor informatie over pakketten van invoegtoepassingen en referentiesites.

* **Een SMTP-**
serviceU kunt elke SMTP-service gebruiken.

* **Adobe Sign-ontwikkelaarsaccount en Adobe Sign API-toepassing**

   Adobe Sign-ontwikkelaarsaccount is vereist om digitale ondertekeningsmogelijkheden te gebruiken. Zie [Adobe Sign](https://acrobat.adobe.com/us/en/why-adobe/developer-form.html).

* Een lopende instantie van de Dynamica 365 van Microsoft om met AEM Forms te integreren. Om de verwijzingsplaats in werking te stellen, voert u de steekproefgegevens in de instantie van de Dynamiek van Microsoft in om de interactieve mededeling vooraf in te vullen die in de verwijzingsplaats wordt gebruikt.
* Een actieve instantie van AEM 6.4 met Forms-invoegtoepassing. Zie [AEM Forms installeren en configureren](installing-configuring-aem-forms-osgi.md) voor meer informatie.

Voer de volgende stappen in de geadviseerde opeenvolging uit aan opstelling en vorm de verwijzingsplaatsen.

<table> 
 <tbody> 
  <tr> 
   <th><strong>Stap</strong></th> 
   <th><strong>Configureren</strong></th> 
   <th><strong>Opmerkingen</strong></th> 
  </tr> 
  <tr> 
   <td><a href="#installaemforms">AEM Forms installeren en configureren</a></td> 
   <td>Auteur en publicatie</td> 
   <td>Installeer en configureer de AEM Forms-auteur en publiceer instanties.</td> 
  </tr> 
  <tr> 
   <td><a href="#ssl">SSL configureren</a></td> 
   <td>Auteur en publicatie<br /> </td> 
   <td>Schakel HTTP via SSL in voor veilige communicatie met Adobe Sign.</td> 
  </tr> 
  <tr> 
   <td><p><a href="#externalizer">Configuratie van externe-alizer van de koppeling voor dag-CQ configureren</a></p> </td> 
   <td>Auteur en publicatie<br /> </td> 
   <td><p>Verwijzingszaken voor gebruik op de site leveren e-mails voor verschillende transacties. Deze instelling is vereist voor levering via e-mail via nieuwsbrief. Hiermee zorgt u ervoor dat URL's en afbeeldingen verwijzen naar de publicatie-instantie. </p> </td> 
  </tr> 
  <tr> 
   <td><a href="#cqmail">CQ-mailservice op dag configureren</a></td> 
   <td>Auteur en publicatie</td> 
   <td>Vereist voor e-mailcommunicatie.</td> 
  </tr> 
  <tr> 
   <td><a href="#xss">Standaard XSS-configuratie overschrijven</a></td> 
   <td>Publicatie</td> 
   <td>Wordt gebruikt om $-, {- en }-tekens te overschrijven die door de XP-beveiliging worden geblokkeerd.</td> 
  </tr> 
  <tr> 
   <td><a href="#aemds">AEM DS-instellingen configureren</a></td> 
   <td>Auteur</td> 
   <td>Configureer AEM DS voor het verzenden van formulieren op een publicatie-instantie en verwerkingsworkflows op de auteurinstantie.</td> 
  </tr> 
  <tr> 
   <td><a href="#refsite">Referentiesites implementeren</a></td> 
   <td>Auteur</td> 
   <td>Implementeer pakketten met referentiesites op de auteur van AEM Forms.</td> 
  </tr> 
  <tr> 
   <td><a href="/help/forms/using/setup-reference-sites.md#optional-import-sample-data-into-microsoft-dynamics">Voorbeeldgegevens importeren in Microsoft Dynamics</a></td> 
   <td>Auteur en publicatie</td> 
   <td>Voorbeeldgegevens importeren voor toepassing via creditcard, hypotheektoepassing thuis en doorlopen van de toepassing voor thuisverzekering</td> 
  </tr> 
  <tr> 
   <td><a href="/help/forms/using/setup-reference-sites.md#configure-oauth-cloud-service-for-microsoft-dynamics">De OAuth-cloudservice voor Microsoft Dynamics configureren</a></td> 
   <td>Auteur en publicatie</td> 
   <td>Configureer de OAuth-cloudservice in AEM Forms om communicatie tussen AEM Forms en Microsoft Dynamics mogelijk te maken. </td> 
  </tr> 
  <tr> 
   <td><a href="#scheduler">Adobe Sign Scheduler configureren</a></td> 
   <td>Auteur en publicatie<br /> </td> 
   <td>Verander de configuratie van de planner om status om de twee minuten te controleren.</td> 
  </tr> 
  <tr> 
   <td><a href="#sign-service">Referentie-site Adobe Sign-Cloud Service configureren</a></td> 
   <td>Auteur en publicatie<br /> </td> 
   <td>Een configuratie die met de pakketten van verwijzingsplaatsen komt en herconfiguratie met geldige geloofsbrieven vereist.</td> 
  </tr> 
  <tr> 
   <td><a href="#anonymous">Forms Common Configuration Service configureren voor anonieme gebruikers</a></td> 
   <td>Publicatie</td> 
   <td>Met de configuratie kunnen anonieme gebruikers een record genereren voor verzending, ondertekening en het maken van een document.</td> 
  </tr> 
  <tr> 
   <td><a href="#fdm">Wijzig het Waggerbestand van de Rest Service voor het Model van de Gegevens van de Vorm</a></td> 
   <td>Auteur en publicatie<br /> </td> 
   <td>Wijzig de service voor uw omgeving.</td> 
  </tr> 
 </tbody> 
</table>

## AEM Forms {#install-and-configure-aem-forms} installeren en configureren

Installeer en implementeer AEM Forms zoals beschreven in [AEM Forms installeren en configureren op OSGi](/help/forms/using/installing-configuring-aem-forms-osgi.md).

>[!NOTE]
>
>Vorm replicatie en omgekeerde replicatieagenten als er meer dan één publiceer instanties zijn of de auteur en publiceer instanties zijn op verschillende machines.

## SSL {#ssl} configureren

SSL-configuratie is vereist voor communicatie met Adobe Sign-servers. Zie [HTTP inschakelen via SSL](/help/sites-administering/ssl-by-default.md) voor gedetailleerde stappen.

>[!CAUTION]
>
>Configureer geen geforceerde SSL in `/etc/map`-map.

## Configuratie {#externalizer} van de Verbinding van de Dag CQ

In AEM, is **ExternalAlizer** de dienst OSGI die u toestaat om een middelweg programmatically om te zetten (b.v. /path/to/my/page) in een externe en absolute URL (bijvoorbeeld, https://www.mycompany.com/path/to/my/page) door het pad vooraf in te stellen met een vooraf geconfigureerde DNS. Zie [URL&#39;s extern maken](/help/sites-developing/externalizer.md).

>[!CAUTION]
>
>Voer geen externalisatie naar HTTPS URL uit als u een zelfondertekend certificaat voor SSL gebruikt.
>
>Gebruik ook localhost in plaats van de hostnaam voor de lokale server.

Voer de volgende stappen uit op zowel auteur- als publicatieinstanties:

1. Ga naar configuratie OSGi op https://&lt;*hostname>*:&lt;*port>*/system/console/configMgr.
1. **[!UICONTROL Day CQ Link Externalizer]**-configuratie zoeken en tikken.

   Het dialoogvenster Day CQ Link Externalzer wordt geopend voor het bewerken van de configuratie.

1. In het dialoogvenster Day CQ Link Externalzer, in het veld Domains:

   * Geef voor de instantie van de auteur een publicatie-URL op die toegankelijk is via een extern systeem. Bijvoorbeeld een hostnaam of een publicatiewebserver.
   * Geef in de publicatie-instantie zowel de auteur als publicatie-URL&#39;s op.

1. Controleer in beide instanties of de URL van de lokale server is opgegeven in het veld Domains.
1. Tik op **[!UICONTROL Save]**. Wacht een tijdje op alle diensten opnieuw te beginnen.

## CQ-mailservice op dag configureren {#cqmail}

Voor de implementatie van een referentiesite moeten e-mails naar voorbeeldgebruikers worden verzonden wanneer deze formulieren invullen en verzenden. Door CQ-mailservice op de dag te configureren, kunt u SMTP-servicedetails leveren om geautomatiseerde e-mails naar klanten te verzenden. Zie [E-mailmeldingen configureren](/help/sites-administering/notification.md).

Voer de volgende stappen uit om de postdienst op te vormen publiceer instantie:

1. Ga naar configuratie OSGi op https://&lt;*hostname>*:&lt;*port>*/system/console/configMgr.
1. Zoek en tik **[!UICONTROL Day CQ Mail Service]** om het voor configuratie te openen.
1. Geef hostnaam en poortwaarden voor SMTP-servers op.
1. Tik op **[!UICONTROL Save]**.

>[!NOTE]
>
>U kunt uw collectieve dienst SMTP of openbare diensten zoals Gmail gebruiken. Voor het vormen van de dienst SMTP, zie de de dienstdocumentatie SMTP.

## Standaard XSS-configuratie {#xss} overschrijven

De e-mailsjablonen voor de website Web.Finance bevatten persoonlijke links in e-mails. Deze koppelingen hebben plaatsaanduiding als `${placeholder}`. Deze plaatsaanduidingen worden vervangen door werkelijke waarden voordat ze e-mails verzenden. De standaard XSS-beveiligingsconfiguratie voor AEM staat accolades (**{ }**) in de URL in HTML-inhoud niet toe. U kunt de standaardconfiguratie echter negeren door de volgende stappen uit te voeren bij een publicatie-instantie:

1. Kopieer `/libs/cq/xssprotection/config.xml` naar `/apps/cq/xssprotection/config.xml`.
1. Open `/apps/cq/xssprotection/config.xml`.
1. Wijzig in de sectie `common-regexps` de `onsiteURL`-vermelding als volgt en sla het bestand op.

   `<regexp name="onsiteURL" value="([\p{L}\p{N}\\\.\#@\$\{\}%\+&;\-_~,\?=/!\*\(\)]*|\#(\w)+)"/>`

>[!NOTE]
>
>accolades (**{ }**) worden als geaccepteerde tekens opgenomen in de URL in HTML-inhoud.

Nadat u de SMTP-server hebt geconfigureerd, probeert u een formulier in te vullen met de persona Sarah Rose en het op te slaan als concept. Wanneer u opslaat als concept, krijgt u een optie om het concept via e-mail te ontvangen. Als u op de knop **E-mail verzenden** tikt, is uw e-mailconfiguratie gelukt als u een e-mail ontvangt met een koppeling naar het concept van de toepassing. Zorg ervoor dat u zich aanmeldt met de gegevens van Sarah om het concept te zien.

## AEM DS-instellingen configureren {#aemds}

AEM de montages van de Dienst van DS worden vereist op de Publish instantie voor e-mailmededelingen in de gevallen van het het gebruik van de verwijzingsplaats. Voor gedetailleerde stappen om AEM de opstelling van de Dienst te vormen DS op de Publish instantie, zie [AEM montages DS](/help/forms/using/configuring-the-processing-server-url-.md) vormen.

Voor AEM Forms-referentiesites geeft u in de AEM DS Settings Service de URL van de publicatieserver op in plaats van de URL van de verwerkingsserver.

>[!CAUTION]
>
>Plaats `/lc` niet in de URL van de verwerkingsserver als u deze voor AEM Forms OSGi configureert.

## Verwijzingssitepakketten {#refsite} implementeren

Installeer de volgende referentiesites met gebruik van Software Distribution.

* [AEM-FORMS-6.4-FSI-REF-SITE](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/fd/AEM-FORMS-6.4-FSI-REF-SITE)
* [AEM-FORMS-6.4-GOV-REF-SITE](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/fd/AEM-FORMS-6.4-GOV-REF-SITE)

Meer over hoe te om pakketten te gebruiken, zie [Met Pakketten werken](/help/sites-administering/package-manager.md).

Nadat u de pakketten hebt geïnstalleerd en de auteur hebt gestart en exemplaren hebt gepubliceerd, gaat u naar de volgende URL&#39;s in uw browser:

* `https://[server]:[port]/wegov`
* `https://[server]:[port]/wefinance`

Als uw installatie succesvol is, kunt u tot de Web.Gov en Wij.Finance verwijzingsplaatsen toegang hebben die pagina&#39;s landen.

## (Optioneel) Voorbeeldgegevens importeren in Microsoft Dynamics {#optional-import-sample-data-into-microsoft-dynamics}

De toepassing van de huishypotheek en de plaatsen van de autoverzekeringstoepassing worden gevormd om verslagen van de Dynamiek van Microsoft te gebruiken. Het pakket van de verwijzingsplaats installeert een douaneentiteit en steekproefverslagen die u in de Dynamiek van Microsoft kunt invoeren om de verwijzingsplaats in werking te stellen. Voer de volgende stappen uit om de voorbeeldgegevens te migreren en in te stellen:

U kunt als volgt de aangepaste entiteit importeren voor de toepassing voor automatische verzekering:

1. Download het **WeFinanceAutoInsurance_1_0.zip** oplossingspakket van `https://[server]:[port]/content/aemforms-refsite-collaterals/we-finance/auto-insurance/ms-dynamics/WeFinanceAutoInsurance_1_0.zip` op uw AEM auteurinstantie.
1. Ga in de instantie Microsoft Dynamics naar **[!UICONTROL Solutions]** in het menu **[!UICONTROL Settings]** en klik op **[!UICONTROL Import]**. Selecteer en importeer het pakket.

U kunt als volgt de aangepaste entiteit importeren voor de toepassing voor automatische verzekering:

1. Download het **AEMFormsFSIRefsite_1_0.zip**-pakket van https://[auteur]:[port]/content/aemforms-refsite-collaterals/we-finance/home-mortgage/ms-dynamics/AEMFormsFSIRefsite_1_0.zip. Selecteer en importeer het pakket.

1. Ga in de instantie Microsoft Dynamics naar **[!UICONTROL Solutions]** in het menu **[!UICONTROL Settings]** en klik op **[!UICONTROL Import]**. Selecteer en importeer het pakket.

De gegevens van de klant en het verzekeringspolis importeren:

1. Download de **We.Finance Customers.csv, We.Finance Auto Insurance Renewals.csv**, en **home hypotheek** gegevensbestanden van de volgende plaatsen op uw AEM auteur:

   * `https://[server]:[port/content/aemforms-refsite-collaterals/we-finance/auto-insurance/ms-dynamics/We.Finance Customers.csv`
   * `https://[server]:[port/content/aemforms-refsite-collaterals/we-finance/auto-insurance/ms-dynamics/We.Finance Auto Insurance Renewals.csv`
   * `https://[server]:[port]/content/aemforms-refsite-collaterals/we-finance/home-mortgage/ms-dynamics/Sarah%20Rose%20Contact.csv`

1. Ga als volgt te werk in de instantie Microsoft Dynamics:

   * Ga naar **[!UICONTROL Sales > We.Finance Customers]** en klik **[!UICONTROL Import]**.
   * Ga naar **[!UICONTROL Sales > We.Finance Auto Insurance]** en klik **[!UICONTROL Import]**.
   * Ga naar **[!UICONTROL Sales > We.Finance Home Mortgage]** en klik **[!UICONTROL Import]**.

## OAuth-cloudservice configureren voor Microsoft Dynamics {#configure-oauth-cloud-service-for-microsoft-dynamics}

Configureer de OAuth-cloudservice in AEM Forms om communicatie tussen AEM Forms en Microsoft Dynamics mogelijk te maken. Voer de volgende stappen uit om de Cloud Service OAuth op AEM auteur te vormen en instanties te publiceren:

1. Ga bij AEM auteurinstantie naar **[!UICONTROL Tools > Cloud Services > Data Sources > global]**. Tik op **[!UICONTROL Refsite Dynamics Integration]** pictogram en tik **[!UICONTROL Properties]**.
1. Ga naar Microsoft Azure Active Directory-account. Voeg de gekopieerde URL voor de configuratie van de cloudservice toe in de **[!UICONTROL Reply URL]**-instelling voor uw geregistreerde toepassing. Sla de configuratie op.
1. Op het lusje van de Montages van de Authentificatie, specificeer **[!UICONTROL Service Root]**, **[!UICONTROL Client Id]**, **[!UICONTROL Client Secret]**, en **[!UICONTROL Resource URL]** voor uw instantie van de Dynamiek van Microsoft. Klik **[!UICONTROL Connect to OAuth]** die aan de login van de Dynamica van Microsoft pagina opnieuw richt.
1. Geef uw aanmeldingsgegevens op. Nadat u zich hebt aangemeld, wordt u omgeleid naar de configuratiepagina van de AEM Forms-cloudservice. Klik op **[!UICONTROL Save & Close]**. De configuratie van de cloudservice wordt opgeslagen.
1. Ga naar **[!UICONTROL Forms > Data Integrations > We.Finance]**. Selecteer Automatische verzekering (dynamiek) en klik op Bewerken. De entiteiten van de Dynamiek van Microsoft zijn vermeld onder de Bronnen van Gegevens tabel. Wacht tot alle entiteiten van de Dynamiek van Microsoft worden opgehaald en onder de gegevensbronnen tabel worden vermeld.
1. Selecteer **[!UICONTROL AutoInsuranceRenewal entity]** en klik **[!UICONTROL Test Model Object]**. Geef in de sectie met invoerverzoeken de waarde voor de klant-id op als &quot;900001&quot; en klik op **[!UICONTROL Test]**. De sectie van de Output toont de verslagen die van de Dynamica van Microsoft voor klantenidentiteitskaart 900001 worden gehaald.
1. Geef in de sectie met invoerverzoeken de waarde voor de klant-id op als &quot;900001&quot; en klik op **[!UICONTROL Test]**. De sectie van de Output toont de verslagen die van de Dynamica van Microsoft voor klantenidentiteitskaart 900001 worden gehaald.
1. Herhaal stap 1-6 op de publicatie-instantie.

## Adobe Sign Scheduler {#scheduler} configureren

Doe het volgende op zowel auteur als publicatieinstanties:

1. Ga naar AEM webconfiguratieconsole op `https://[server]:[host]/system/console/configMgr`.
1. Zoek en tik **[!UICONTROL Adobe Sign Configuration Service]** om het voor configuratie te openen.
1. **[!UICONTROL Status Update Scheduler Expression]** configureren als **0/2 &amp;ast; &amp;ast; &amp;ast; ?**.

   >[!NOTE]
   >
   >De bovenstaande plannerconfiguratie controleert de status van de dienst van Adobe Sign om de twee minuten.

1. Tik op **[!UICONTROL Save]**.

## Adobe Sign-cloudservice van de referentiesite configureren {#sign-service}

Doe het volgende op zowel auteur als publicatieinstanties:

1. Ga naar **[!UICONTROL Tools > Cloud Services > Adobe Sign > global]**. Selecteer **[!UICONTROL AEM Forms Reference Site Sign]** en tik **[!UICONTROL Properties]**.

   >[!CAUTION]
   >
   >Zorg ervoor dat de URL https://[host]:[ssl_port]/mnt/overlay/adobesign/cloudservices/adobesign/properties.html wordt toegevoegd aan de lijst met omleidings-URL&#39;s van OAuth-configuratie van de Adobe Sign API-toepassing.

1. Geef de client-id en het geheim van de OAuth-configuratie van de Adobe Sign-toepassing op.
1. (Optioneel) Selecteer de optie **[!UICONTROL Enable Adobe Sign for attachments also]** en tik **[!UICONTROL Connect to Adobe Sign]**. De bestanden die zijn gekoppeld aan een adaptief formulier, worden toegevoegd aan het corresponderende Adobe Sign-document dat ter ondertekening is verzonden.
1. Tik op **[!UICONTROL Connect to Adobe Sign]** en meld u aan met uw Adobe Sign-referenties.

## Forms Common Configuration Service {#anonymous} configureren

Ga als volgt te werk op de publicatie-instantie om toegang tot anonieme gebruikers toe te staan:

1. Ga naar AEM webconfiguratieconsole op `https://[server]:[port]/system/console/configMgr`.
1. Zoek en tik **[!UICONTROL Forms Common Configuration Service]** om het voor configuratie te openen.
1. Configureer het veld **[!UICONTROL Allow]** voor **[!UICONTROL All Users]**.
1. Tik op **[!UICONTROL Save]**.

## Rest Service wijzigen voor formuliergegevensmodel {#fdm}

Doe het volgende op zowel auteur als publicatieinstanties:

1. Ga naar CRXDE om `https://[server]:[port]/crx/de/index.jsp`.
1. Navigeer naar **/conf/global/settings/cloudconfigs/fdm/roi-rest/jcr:content/swaggerFile** en open het wagerbestand.
1. Werk de host- en poortinstellingen naar wens bij in uw omgeving.
1. Sla de instellingen op.
1. (**Alleen auteurinstantie**) Ga naar **[!UICONTROL Tools]** > **[!UICONTROL Cloud Services]** > **[!UICONTROL Data Sources]** > **[!UICONTROL global]**. Selecteer **[!UICONTROL roi-rest]** en tik **[!UICONTROL Properties]**. Tik **[!UICONTROL Authentication Settings]** en stel **[!UICONTROL Authentication Type]** in op **[!UICONTROL Basic Authentication]**. Geef `admin`/ `admin`op als gebruikersnaam/wachtwoord voor toegang tot de service. Tik op **[!UICONTROL Save & Close]**.

## Integreren met Marketing Cloud {#integrate-with-marketing-cloud}

U kunt de AEM Forms integreren met Adobe Analytics en Adobe Target. Hoewel Adobe Analytics u helpt rapporten te genereren en de prestaties van adaptieve formulieren te analyseren, helpt Adobe Target u om persoonlijke ervaringen op te doen en A/B-tests uit te voeren voor adaptieve formulieren.

Ga als volgt te werk om Adobe Analytics en Adobe Target in AEM Forms te configureren.

### Adobe Analytics {#configure-adobe-analytics} configureren

Dankzij de AEM Forms-integratie met Adobe Analytics kunt u controleren en analyseren hoe uw klanten omgaan met uw formulieren en documenten. Hiermee kunt u probleemgebieden herkennen en corrigeren en de conversiesnelheid verhogen.

Om deze functionaliteit in verwijzingsplaats te ervaren, vorm uw rekening Analytics zoals die in [Analytics en rapporten](/help/forms/using/configure-analytics-forms-documents.md) wordt beschreven vormt.

Om een rapport te produceren, worden de zaadgegevens gebundeld met de verwijzingsplaatsen. Voer de volgende handelingen uit voordat u zaadgegevens gebruikt:

1. Zorg ervoor dat wij.Finance en We.Gov analytische configuraties beschikbaar zijn in de AEM Cloud Services. U kunt cloudservices op een van de volgende manieren vinden:

   * Navigeer naar **[!UICONTROL Tools>Cloud Services>Legacy Cloud Services]** of blader naar https://&lt;host>:&lt;port>/libs/cq/core/content/tools/cloudservices.html.
   * Klik op **[!UICONTROL Cloud Services]** op de pagina onder **[!UICONTROL Adobe Analytics]** sectie. `Show Configurations` U kunt de beschikbare configuraties We.Finance en We.Gov zien. Klik om de configuratie te openen. Klik in de configuratiepagina op **[!UICONTROL Edit]**. Geef een geldig bedrijf, een geldige gebruikersnaam, een gedeeld geheim (wachtwoord) en datacenter op en klik op **[!UICONTROL Connect to Analytics]**. Wanneer het dialoogvenster Verbinding gelukt is, klikt u op **[!UICONTROL OK]** in het configuratiedialoogvenster. Vorm het kader onder de configuratie van Analytics zoals die in [het Vormen Analytics en Reports](/help/forms/using/configure-analytics-forms-documents.md) wordt beschreven.

1. Ga naar https://&lt;*host*>:&lt;*port*/system/console/configMgr en voer de volgende handelingen uit:

   * Zoek op de pagina **[!UICONTROL Web Console Configuration]** naar **[!UICONTROL AEM Forms Analytics Configuration]** en klik op .
   * Selecteer in het veld **[!UICONTROL SiteCatalyst Framework]** van het dialoogvenster AEM Forms Analytics Configuration (Configuratie van Analytics) de optie wij-finance (wij-finance) of we-gov (wij-gov).
   * Klik **[!UICONTROL Save]** en laat de pagina verfrissen.

1. Ga naar formulierbeheer op https://&lt;host>:&lt;port>/aem/forms en voer de volgende handelingen uit:

   * Open de map We.Finance of We.Gov en selecteer het formulier waarvoor u het rapport wilt weergeven.
   * Klik op Analyses inschakelen op de werkbalk Handelingen. Nadat u analyses voor het formulier hebt ingeschakeld, klikt u op Analyserapport. Er wordt een leeg rapport gegenereerd. Nadat een leeg rapport wordt geproduceerd, moet u zaadgegevens verstrekken die van refsite pakket worden verscheept om analytische rapport voor demodoel te produceren.

   Referentiesites bieden analyses die gegevens bevatten over de aanvraag van een creditcard, de hypotheek op woningen en de gebruiksgevallen van kinderondersteuning. Voor configuratie van zaadgegevens, zie [Wij.Finance verwijzingsplaatwalkthrough](/help/forms/using/finance-reference-site-walkthrough.md) en [Wij.Gov verwijzingsplaatwalkthrough](/help/forms/using/gov-reference-site-walkthrough.md).

### Doel {#configure-target} configureren

De referentiesite laat de integratie zien van AEM Forms met Adobe Target, waarmee u gerichte en gepersonaliseerde inhoud kunt opnemen in adaptieve documenten. Ook kunnen er A/B-tests voor adaptieve formulieren worden gemaakt.

Ga als volgt te werk om Doel in AEM te configureren voor de integratie in de verwijzingssite:

1. Start de auteur quickstart met het jvm-argument `-Dabtesting.enabled=true` om A/B-tests op de server in te schakelen.

   **Opmerking**: Als de AEM-instantie wordt uitgevoerd op JBoss, die is gestart als een service van de Turnkey-installatie, voegt u de  `-Dabtesting.enabled=true` parameter toe aan de volgende vermelding in het  `jboss\bin\standalone.conf.bat` bestand:

   `set "JAVA_OPTS=%JAVA_OPTS% -Dadobeidp.serverName=server1 -Dfile.encoding=utf8 -Djava.net.preferIPv4Stack=true -Dabtesting.enabled=true"`

1. Ga naar https://&lt;*hostnaam*>:&lt;*poort*>/libs/cq/core/content/tools/cloudservices.html.

1. Klik in de sectie **[!UICONTROL Adobe Target]** op **[!UICONTROL Show Configurations]**. U kunt de beschikbare Configuratie van het Doel van Web zien. Klik om de configuratie te openen. Klik in de configuratiepagina op **[!UICONTROL Edit]**. Het dialoogvenster **[!UICONTROL Edit Component]** voor de configuratie wordt geopend.

1. Geef uw clientcode, e-mail en wachtwoord op die aan uw doelaccount zijn gekoppeld. Selecteer API-type als **[!UICONTROL REST]**.
1. Klik op **[!UICONTROL Connect to Adobe target]**. Wanneer de doelaccount is geconfigureerd, klikt u op **[!UICONTROL OK]**. U kunt zien de verpakte configuratie een Kader van het Doel heeft.

1. Ga naar https://&lt;*hostnaam*>:&lt;*poort*/system/console/configMgr.

1. Klik op **[!UICONTROL AEM Forms Target Configuration]**.
1. Selecteer een doelframework.
1. Geef in het veld **[!UICONTROL Target URLs]** de URL naar AEM Forms op. Bijvoorbeeld: https://&lt;*hostnaam*>:&lt;*poort*>.

1. Klik op **[!UICONTROL Save]**.

In gevallen waarin gebruik wordt gemaakt van creditcardaanvragen en Home Mortgauge wordt getoond hoe een A/B-test kan worden uitgevoerd en een rapport kan worden weergegeven voor demodoeleinden. Voor analyses, zie [Wij.Financiën verwijzingsplaatsanalyse](/help/forms/using/finance-reference-site-walkthrough.md).

## Volgende stap {#next-step}

Nu bent u allen klaar om de verwijzingsplaats te onderzoeken. Zie voor meer informatie over de workflow en stappen van de verwijzingssite:

* [We.Financiële referentiesite doorlopen](/help/forms/using/finance-reference-site-walkthrough.md)
* [We.Gov-referentiesite doorloopt](/help/forms/using/gov-reference-site-walkthrough.md)

* [Werknemerslijst voor zelfbedieningsverwijzingssite](/help/forms/using/employee-self-service-reference-site.md)

