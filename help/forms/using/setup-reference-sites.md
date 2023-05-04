---
title: AEM Forms-referentiesites instellen en configureren
seo-title: Set up and configure AEM Forms reference sites
description: AEM Forms-referentiesites laten zien hoe u AEM Forms kunt gebruiken om end-to-end workflow in een organisatie te implementeren.
seo-description: AEM Forms reference sites showcase how you can use AEM Forms to implement end-to-end workflow in an organization.
uuid: 087d58a1-d84e-49ac-a82d-4e7fc708f00f
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: introduction
discoiquuid: 2feb4a9c-57ad-4c6b-a572-0047bc409bbb
exl-id: 9c5d956c-06bc-4428-afcd-02b4f81b802f
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '2777'
ht-degree: 0%

---

# AEM Forms-referentiesites instellen en configureren {#set-up-and-configure-aem-forms-reference-sites}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

AEM Forms biedt implementatie van referentiesite om aan te tonen hoe AEM Forms organisaties van de Financial Services Industry en de overheid helpt om hun complexe transacties om te zetten in eenvoudige en aantrekkelijke digitale ervaringen op elk apparaat, waar en wanneer dan ook.

Wij.Financiën en Wij.Gov de verwijzingsplaatsen trekken echte gebruiksgevallen om met bestaande en potentiële klanten, van het punt van eerste aanraking tot het beheren van correspondentie en transacties op een gepersonaliseerde en rendabele manier in dienst te nemen.

Met de referentiesites kunt u de volgende belangrijke mogelijkheden van AEM Forms verkennen en weergeven.

* Vereenvoudigde ontwerpervaring met aantrekkelijke en responsieve adaptieve formulieren en interactieve communicatie.
* Interactieve Mededelingen om interactieve, gepersonaliseerde, en ontvankelijke klantenmededelingen tot stand te brengen die aan het apparaat het plaatsen en de lay-out aanpassen.
* Gegevensintegratie om verbinding te maken met verschillende gegevensbronnen om formuliergegevens vooraf in te vullen en te verzenden via een formuliergegevensmodel.
* Forms-workflow om bedrijfsprocessen en workflows te automatiseren.
* Geavanceerde mogelijkheden voor gegevensbeheer en -verwerking door gebruikers.
* Integratie met Acrobat Sign om adaptieve formulieren veilig te ondertekenen en te verzenden.
* Integratie met Adobe Target voor gerichte aanbevelingen en A/B-tests om het rendement van investeringen vanuit een formulier te maximaliseren.
* Integratie met Adobe Analytics om de prestaties van een formulier of campagne te meten en geïnformeerde beslissingen te nemen.
* Verbeterde functionaliteit voor het invullen van formulieren.

De referentiesites bieden herbruikbare elementen die u als sjablonen kunt gebruiken om uw eigen elementen te maken.

* Integratie met Acrobat Sign om adaptieve formulieren veilig te ondertekenen en te verzenden.

* Integratie met Acrobat Sign om adaptieve formulieren veilig te ondertekenen en te verzenden.

## Vereisten en stappen voor het instellen van referentiesites {#prerequisites-and-steps-to-set-up-reference-sites}

Voordat u de referentiesite instelt, moet u het volgende doen:

* **AEM**

   AEM QuickStart-, AEM Forms-add-on-pakket en referentiesite-pakketten. Zie [AEM Forms-releases](https://helpx.adobe.com/aem-forms/kb/aem-forms-releases.html) voor de pakketgegevens van invoegtoepassingen en referentiesites.

* **Een SMTP-service**
U kunt elke SMTP-service gebruiken.

* **Acrobat Sign-ontwikkelaarsaccount en Acrobat Sign API-toepassing**

   Acrobat Sign-ontwikkelaarsaccount is vereist om digitale ondertekeningsmogelijkheden te gebruiken. Zie [Acrobat Sign](https://acrobat.adobe.com/us/en/why-adobe/developer-form.html).

* Een actieve versie van Microsoft Dynamics 365 voor integratie met AEM Forms. Als u de referentiesite wilt uitvoeren, importeert u de voorbeeldgegevens in de instantie Microsoft Dynamics om de interactieve communicatie die in de referentiesite wordt gebruikt, vooraf in te vullen.
* Een actieve instantie van AEM 6.4 met Forms-invoegtoepassing. Zie voor meer informatie [AEM Forms installeren en configureren](installing-configuring-aem-forms-osgi.md).

Voer de volgende stappen in de geadviseerde opeenvolging uit aan opstelling en vorm de verwijzingsplaatsen.

<table> 
 <tbody> 
  <tr> 
   <th><strong>Stap</strong></th> 
   <th><strong>Configureren</strong></th> 
   <th><strong>Notities</strong></th> 
  </tr> 
  <tr> 
   <td><a href="#installaemforms">AEM Forms installeren en configureren</a></td> 
   <td>Auteur en publicatie</td> 
   <td>Installeer en configureer de AEM Forms-auteur en publiceer instanties.</td> 
  </tr> 
  <tr> 
   <td><a href="#ssl">SSL configureren</a></td> 
   <td>Auteur en publicatie<br /> </td> 
   <td>Schakel HTTP via SSL in voor veilige communicatie met Acrobat Sign.</td> 
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
   <td><a href="/help/forms/using/setup-reference-sites.md#configure-oauth-cloud-service-for-microsoft-dynamics">OAuth-cloudservice voor Microsoft Dynamics configureren</a></td> 
   <td>Auteur en publicatie</td> 
   <td>Configureer de OAuth-cloudservice in AEM Forms om communicatie tussen AEM Forms en Microsoft Dynamics mogelijk te maken. </td> 
  </tr> 
  <tr> 
   <td><a href="#scheduler">Acrobat Sign Scheduler configureren</a></td> 
   <td>Auteur en publicatie<br /> </td> 
   <td>Verander de configuratie van de planner om status om de twee minuten te controleren.</td> 
  </tr> 
  <tr> 
   <td><a href="#sign-service">Referentie-site Acrobat Sign-Cloud Service configureren</a></td> 
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

## AEM Forms installeren en configureren {#install-and-configure-aem-forms}

AEM Forms installeren en implementeren zoals beschreven in [AEM Forms installeren en configureren op OSGi](/help/forms/using/installing-configuring-aem-forms-osgi.md).

>[!NOTE]
>
>Vorm replicatie en omgekeerde replicatieagenten als er meer dan één publiceer instanties zijn of de auteur en publiceer instanties zijn op verschillende machines.

## SSL configureren {#ssl}

SSL-configuratie is vereist voor communicatie met Acrobat Sign-servers. Voor gedetailleerde stappen raadpleegt u [HTTP via SSL inschakelen](/help/sites-administering/ssl-by-default.md).

>[!CAUTION]
>
>Geen geforceerde SSL configureren `/etc/map` map.

## Configuratie van externe-alizer van de koppeling voor dag-CQ configureren {#externalizer}

In AEM **ExternalAlizer** is de dienst OSGI die u toestaat om een middelweg (bijvoorbeeld, /path/to/my/page) in een externe en absolute URL (bijvoorbeeld, https://www.mycompany.com/path/to/my/page) programmatically om te zetten door de weg met pre-gevormde DNS te bevestigen. Zie [URL&#39;s extern maken](/help/sites-developing/externalizer.md).

>[!CAUTION]
>
>Voer geen externalisatie naar HTTPS URL uit als u een zelfondertekend certificaat voor SSL gebruikt.
>
>Gebruik ook localhost in plaats van de hostnaam voor de lokale server.

Voer de volgende stappen uit op zowel auteur- als publicatieinstanties:

1. Ga naar OSGi Configuration op https://&lt;*hostnaam>*:&lt;*poort>*/system/console/configMgr.
1. Zoeken en tikken **[!UICONTROL Day CQ Link Externalizer]** configuratie.

   Het dialoogvenster Externalzer van de koppeling Day CQ wordt geopend voor het bewerken van de configuratie.

1. In het dialoogvenster Day CQ Link Externalzer, in het veld Domains:

   * Geef voor de instantie van de auteur een publicatie-URL op die toegankelijk is via een extern systeem. Bijvoorbeeld een hostnaam of een publicatiewebserver.
   * Geef in de publicatie-instantie zowel de auteur als publicatie-URL&#39;s op.

1. Controleer in beide instanties of de URL van de lokale server is opgegeven in het veld Domains.
1. Tik op **[!UICONTROL Save]**. Wacht een tijdje op alle diensten opnieuw te beginnen.

## CQ-mailservice op dag configureren {#cqmail}

Voor de implementatie van een referentiesite moeten e-mails naar voorbeeldgebruikers worden verzonden wanneer deze formulieren invullen en verzenden. Door CQ-mailservice op de dag te configureren, kunt u SMTP-servicedetails leveren om geautomatiseerde e-mails naar klanten te verzenden. Zie [E-mailmeldingen configureren](/help/sites-administering/notification.md).

Voer de volgende stappen uit om de postdienst op te vormen publiceer instantie:

1. Ga naar OSGi Configuration op https://&lt;*hostnaam>*:&lt;*poort>*/system/console/configMgr.
1. Zoeken en tikken **[!UICONTROL Day CQ Mail Service]** om het voor configuratie te openen.
1. Geef hostnaam en poortwaarden voor SMTP-servers op.
1. Tik op **[!UICONTROL Save]**.

>[!NOTE]
>
>U kunt uw collectieve dienst SMTP of openbare diensten zoals Gmail gebruiken. Voor het vormen van de dienst SMTP, zie de de dienstdocumentatie SMTP.

## Standaard XSS-configuratie overschrijven {#xss}

De e-mailsjablonen voor de website Web.Finance bevatten persoonlijke links in e-mails. Deze koppelingen hebben een tijdelijke aanduiding als `${placeholder}`. Deze plaatsaanduidingen worden vervangen door werkelijke waarden voordat ze e-mails verzenden. De standaard XSS-beveiligingsconfiguratie voor AEM staat accolades niet toe (**{ }**) in de URL in HTML-inhoud. U kunt de standaardconfiguratie echter negeren door de volgende stappen uit te voeren bij een publicatie-instantie:

1. Kopiëren `/libs/cq/xssprotection/config.xml` tot `/apps/cq/xssprotection/config.xml`.
1. Open `/apps/cq/xssprotection/config.xml`.
1. In de `common-regexps` de sectie wijzigen `onsiteURL` Voer de volgende gegevens in en sla het bestand op.

   `<regexp name="onsiteURL" value="([\p{L}\p{N}\\\.\#@\$\{\}%\+&;\-_~,\?=/!\*\(\)]*|\#(\w)+)"/>`

>[!NOTE]
>
>accolades (**{ }**) worden als geaccepteerde tekens opgenomen in de URL in HTML-inhoud.

Nadat u de SMTP-server hebt geconfigureerd, probeert u een formulier in te vullen met de persona Sarah Rose en het op te slaan als concept. Wanneer u opslaat als concept, krijgt u een optie om het concept via e-mail te ontvangen. Als u op de knop **E-mail verzenden** als u een e-mailbericht ontvangt met een koppeling naar het concept van de toepassing, is de configuratie van uw e-mail voltooid. Zorg ervoor dat u zich aanmeldt met de gegevens van Sarah om het concept te zien.

## AEM DS-instellingen configureren {#aemds}

AEM de montages van de Dienst van DS worden vereist op de Publish instantie voor e-mailmededelingen in de gevallen van het het gebruik van de verwijzingsplaats. Voor gedetailleerde stappen om AEM de opstelling van de Dienst te vormen DS op de Publish instantie, zie [AEM DS-instellingen configureren](/help/forms/using/configuring-the-processing-server-url-.md).

Voor AEM Forms-referentiesites geeft u in de AEM DS Settings Service de URL van de publicatieserver op in plaats van de URL van de verwerkingsserver.

>[!CAUTION]
>
>Niet plaatsen `/lc` in de URL van de verwerkingsserver als u deze voor AEM Forms OSGi configureert.

## Referentiesites implementeren {#refsite}

Installeer de volgende referentiesites met gebruik van Software Distribution.

* [AEM-FORMS-6.4-FSI-REF-SITE](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq640/fd/AEM-FORMS-6.4-FSI-REF-SITE)
* [AEM-FORMS-6.4-GOV-REF-SITE](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq640/fd/AEM-FORMS-6.4-GOV-REF-SITE)

Ga voor meer informatie over het gebruik van pakketten naar [Werken met pakketten](/help/sites-administering/package-manager.md).

Nadat u de pakketten hebt geïnstalleerd en de auteur hebt gestart en exemplaren hebt gepubliceerd, gaat u naar de volgende URL&#39;s in uw browser:

* `https://[server]:[port]/wegov`
* `https://[server]:[port]/wefinance`

Als uw installatie succesvol is, kunt u tot de Web.Gov en Wij.Finance verwijzingsplaatsen toegang hebben die pagina&#39;s landen.

## (Optioneel) Voorbeeldgegevens importeren in Microsoft Dynamics {#optional-import-sample-data-into-microsoft-dynamics}

De toepassing van de huishypotheek en de plaatsen van de de toepassingsverwijzing van de autoverzekering worden gevormd om verslagen van de Dynamiek van Microsoft te gebruiken. Het referentiesite-pakket installeert een aangepaste entiteit en voorbeeldrecords die u in Microsoft Dynamics kunt importeren om de referentiesite uit te voeren. Voer de volgende stappen uit om de voorbeeldgegevens te migreren en in te stellen:

U kunt als volgt de aangepaste entiteit importeren voor de toepassing voor automatische verzekering:

1. Download de **WeFinanceAutoInsurance_1_0.zip** oplossingspakket van `https://[server]:[port]/content/aemforms-refsite-collaterals/we-finance/auto-insurance/ms-dynamics/WeFinanceAutoInsurance_1_0.zip` op uw AEM auteur.
1. Ga in de instantie Microsoft Dynamics naar **[!UICONTROL Solutions]** in de **[!UICONTROL Settings]** menu en klik op **[!UICONTROL Import]**. Selecteer en importeer het pakket.

U kunt als volgt de aangepaste entiteit importeren voor de toepassing voor automatische verzekering:

1. Download de **AEMFormsFSIRefsite_1_0.zip** pakket van https://[auteur]:[poort]/content/aemforms-refsite-collaterals/we-finance/home-mortgage/ms-dynamics/AEMFormsFSIRefsite_1_0.zip. Selecteer en importeer het pakket.

1. Ga in de instantie Microsoft Dynamics naar **[!UICONTROL Solutions]** in de **[!UICONTROL Settings]** menu en klik op **[!UICONTROL Import]**. Selecteer en importeer het pakket.

De gegevens van de klant en het verzekeringspolis importeren:

1. Download de **We.Finance Customers.csv, We.Finance Auto Insurance Renewals.csv**, en **woninghypotheek** gegevensbestanden van de volgende locaties op de AEM auteurinstantie:

   * `https://[server]:[port/content/aemforms-refsite-collaterals/we-finance/auto-insurance/ms-dynamics/We.Finance Customers.csv`
   * `https://[server]:[port/content/aemforms-refsite-collaterals/we-finance/auto-insurance/ms-dynamics/We.Finance Auto Insurance Renewals.csv`
   * `https://[server]:[port]/content/aemforms-refsite-collaterals/we-finance/home-mortgage/ms-dynamics/Sarah%20Rose%20Contact.csv`

1. Ga als volgt te werk in de instantie Microsoft Dynamics:

   * Ga naar **[!UICONTROL Sales > We.Finance Customers]** en klik op **[!UICONTROL Import]**.
   * Ga naar **[!UICONTROL Sales > We.Finance Auto Insurance]** en klik op **[!UICONTROL Import]**.
   * Ga naar **[!UICONTROL Sales > We.Finance Home Mortgage]**  en klik op **[!UICONTROL Import]**.

## OAuth-cloudservice voor Microsoft Dynamics configureren {#configure-oauth-cloud-service-for-microsoft-dynamics}

Configureer de OAuth-cloudservice in AEM Forms om communicatie tussen AEM Forms en Microsoft Dynamics mogelijk te maken. Voer de volgende stappen uit om de Cloud Service OAuth op AEM auteur te vormen en instanties te publiceren:

1. Ga bij AEM auteur naar **[!UICONTROL Tools > Cloud Services > Data Sources > global]**. Tikken **[!UICONTROL Refsite Dynamics Integration]** pictogram en tik **[!UICONTROL Properties]**.
1. Ga naar Microsoft Azure Active Directory-account. Voeg de gekopieerde URL voor de configuratie van de cloudservice toe in het dialoogvenster **[!UICONTROL Reply URL]** instellen voor uw geregistreerde toepassing. Sla de configuratie op.
1. Geef op het tabblad Verificatie-instellingen **[!UICONTROL Service Root]**, **[!UICONTROL Client Id]**, **[!UICONTROL Client Secret]**, en **[!UICONTROL Resource URL]** voor uw Microsoft Dynamics-instantie. Klikken **[!UICONTROL Connect to OAuth]** die wordt doorgestuurd naar de aanmeldingspagina voor Microsoft Dynamics.
1. Geef uw aanmeldingsgegevens op. Nadat u zich hebt aangemeld, wordt u omgeleid naar de configuratiepagina van de AEM Forms-cloudservice. Klik op **[!UICONTROL Save & Close]**. De configuratie van de cloudservice wordt opgeslagen.
1. Ga naar **[!UICONTROL Forms > Data Integrations > We.Finance]**. Selecteer Automatische verzekering (dynamiek) en klik op Bewerken. Entiteiten van Microsoft Dynamics worden vermeld onder het tabblad Gegevensbronnen. Wacht tot alle entiteiten zijn opgehaald van de Dynamica van Microsoft en vermeld onder het lusje van gegevensbronnen.
1. Selecteer **[!UICONTROL AutoInsuranceRenewal entity]** en klik op **[!UICONTROL Test Model Object]**. Geef in de sectie met invoerverzoeken de waarde voor de klant-id op als &quot;900001&quot; en klik op **[!UICONTROL Test]**. De sectie van de Output toont de verslagen die van de Dynamica van Microsoft voor klantenidentiteitskaart 900001 worden gehaald.
1. Geef in de sectie met invoerverzoeken de waarde voor de klant-id op als &quot;900001&quot; en klik op **[!UICONTROL Test]**. De sectie van de Output toont de verslagen die van de Dynamica van Microsoft voor klantenidentiteitskaart 900001 worden gehaald.
1. Herhaal stap 1-6 op de publicatie-instantie.

## Acrobat Sign Scheduler configureren {#scheduler}

Doe het volgende op zowel auteur als publicatieinstanties:

1. Ga naar AEM webconfiguratieconsole op `https://[server]:[host]/system/console/configMgr`.
1. Zoeken en tikken **[!UICONTROL Acrobat Sign Configuration Service]** om het voor configuratie te openen.
1. Configureren **[!UICONTROL Status Update Scheduler Expression]** als **0 0/2 &amp;ast; &amp;asteren; &amp;asteren; ?**.

   >[!NOTE]
   >
   >De bovenstaande plannerconfiguratie controleert de status van de dienst van Acrobat Sign om de twee minuten.

1. Tik op **[!UICONTROL Save]**.

## Referentiesite Acrobat Sign Cloud Service configureren {#sign-service}

Doe het volgende op zowel auteur als publicatieinstanties:

1. Ga naar **[!UICONTROL Tools > Cloud Services > Acrobat Sign > global]**. Selecteren **[!UICONTROL AEM Forms Reference Site Sign]** en tikken **[!UICONTROL Properties]**.

   >[!CAUTION]
   >
   >Zorg ervoor dat https://[host]:[ssl_port]/mnt/overlay/adobesign/cloudservices/adobesign/properties.html URL wordt toegevoegd aan de lijst met omleidings-URL&#39;s van de OAuth-configuratie van de Acrobat Sign API-toepassing.

1. Geef de client-id en het geheim van de OAuth-configuratie van de Acrobat Sign-toepassing op.
1. (Optioneel) Selecteer de optie **[!UICONTROL Enable Acrobat Sign for attachments also]** en tikken **[!UICONTROL Connect to Acrobat Sign]**. De bestanden die zijn gekoppeld aan een adaptief formulier, worden toegevoegd aan het corresponderende Acrobat Sign-document dat ter ondertekening is verzonden.
1. Tikken **[!UICONTROL Connect to Acrobat Sign]** en meld u aan met uw Acrobat Sign-gebruikersgegevens.

## Forms Common Configuration Service configureren {#anonymous}

Ga als volgt te werk op de publicatie-instantie om toegang tot anonieme gebruikers toe te staan:

1. Ga naar AEM webconfiguratieconsole op `https://[server]:[port]/system/console/configMgr`.
1. Zoeken en tikken **[!UICONTROL Forms Common Configuration Service]** om het voor configuratie te openen.
1. Configureer de **[!UICONTROL Allow]** veld voor **[!UICONTROL All Users]**.
1. Tik op **[!UICONTROL Save]**.

## Rest Service wijzigen voor formuliergegevensmodel {#fdm}

Doe het volgende op zowel auteur als publicatieinstanties:

1. Ga naar CRXDE bij `https://[server]:[port]/crx/de/index.jsp`.
1. Navigeren naar **/conf/global/settings/cloudconfigs/fdm/roi-rest/jcr:content/swaggerFile** en open het gummetje.
1. Werk de host- en poortinstellingen naar wens bij in uw omgeving.
1. Sla de instellingen op.
1. (**Alleen instantie van auteur**) Ga naar **[!UICONTROL Tools]** > **[!UICONTROL Cloud Services]** > **[!UICONTROL Data Sources]** > **[!UICONTROL global]**. Selecteren **[!UICONTROL roi-rest]** en tikken **[!UICONTROL Properties]**. Tikken **[!UICONTROL Authentication Settings]** en instellen **[!UICONTROL Authentication Type]** tot **[!UICONTROL Basic Authentication]**. Opgeven `admin`/ `admin`als de gebruikersnaam/het wachtwoord voor toegang tot de service. Tik op **[!UICONTROL Save & Close]**.

## Integreren met Marketing Cloud {#integrate-with-marketing-cloud}

U kunt de AEM Forms integreren met Adobe Analytics en Adobe Target. Hoewel Adobe Analytics u helpt rapporten te genereren en de prestaties van adaptieve formulieren te analyseren, helpt Adobe Target u om persoonlijke ervaringen op te doen en A/B-tests uit te voeren voor adaptieve formulieren.

Ga als volgt te werk om Adobe Analytics en Adobe Target in AEM Forms te configureren.

### Adobe Analytics configureren {#configure-adobe-analytics}

Dankzij de AEM Forms-integratie met Adobe Analytics kunt u controleren en analyseren hoe uw klanten omgaan met uw formulieren en documenten. Hiermee kunt u probleemgebieden herkennen en corrigeren en de conversiesnelheid verhogen.

Om deze functionaliteit in verwijzingsplaats te ervaren, vorm uw account Analytics zoals die in wordt beschreven [Analyses en rapporten configureren](/help/forms/using/configure-analytics-forms-documents.md).

Om een rapport te produceren, worden de zaadgegevens gebundeld met de verwijzingsplaatsen. Voer de volgende handelingen uit voordat u zaadgegevens gebruikt:

1. Zorg ervoor dat wij.Finance en We.Gov analytische configuraties beschikbaar zijn in de AEM Cloud Services. U kunt cloudservices op een van de volgende manieren vinden:

   * Navigeren naar **[!UICONTROL Tools>Cloud Services>Legacy Cloud Services]** of blader aan https://&lt;host>:&lt;port>/libs/cq/core/content/tools/cloudservices.html.
   * In de **[!UICONTROL Cloud Services]** pagina, onder **[!UICONTROL Adobe Analytics]** sectie, klikt u op `Show Configurations`. U kunt de beschikbare configuraties We.Finance en We.Gov zien. Klik om de configuratie te openen. Klik op de configuratiepagina op **[!UICONTROL Edit]**. Geef een geldig bedrijf, gebruikersnaam, gedeeld geheim (wachtwoord) en datacenter op en klik op **[!UICONTROL Connect to Analytics]**. Als het dialoogvenster Verbinding is gelukt, klikt u op **[!UICONTROL OK]** in het configuratiedialoogvenster. Configureer het framework in de configuratie Analytics, zoals beschreven in het dialoogvenster [Analyses en rapporten configureren](/help/forms/using/configure-analytics-forms-documents.md).

1. Ga naar https://&lt;*host*>:&lt;*poort*>/system/console/configMgr en voer de volgende handelingen uit:

   * In de **[!UICONTROL Web Console Configuration]** pagina, zoeken en klikken **[!UICONTROL AEM Forms Analytics Configuration]**.
   * In de **[!UICONTROL SiteCatalyst Framework]** in het dialoogvenster AEM Forms Analytics Configuration (Configuratie van-analysemogelijkheden) selecteert u &#39;wij-finance&#39; (wij-financieren) of &#39;we-gov&#39;.
   * Klikken **[!UICONTROL Save]** en laat de pagina verfrissen.

1. Ga naar formulierbeheer op https://&lt;host>:&lt;port>/aem/forms en voer de volgende handelingen uit:

   * Open de map We.Finance of We.Gov en selecteer het formulier waarvoor u het rapport wilt weergeven.
   * Klik op Analyses inschakelen op de werkbalk Handelingen. Nadat u analyses voor het formulier hebt ingeschakeld, klikt u op Analyserapport. Er wordt een leeg rapport gegenereerd. Nadat een leeg rapport wordt geproduceerd, moet u zaadgegevens verstrekken die van refsite pakket worden verscheept om analytische rapport voor demodoel te produceren.

   Referentiesites bieden analyses die gegevens bevatten over de aanvraag van een creditcard, de hypotheek op woningen en de gebruiksgevallen van kinderondersteuning. Voor configuratie van zaadgegevens, zie [We.Financiële referentiesite doorlopen](/help/forms/using/finance-reference-site-walkthrough.md) en [We.Gov-referentiesite doorloopt](/help/forms/using/gov-reference-site-walkthrough.md).

### Doel configureren {#configure-target}

De referentiesite laat de integratie zien van AEM Forms met Adobe Target, waarmee u gerichte en gepersonaliseerde inhoud kunt opnemen in adaptieve documenten. Ook kunnen er A/B-tests voor adaptieve formulieren worden gemaakt.

Ga als volgt te werk om Doel in AEM te configureren voor de integratie in de verwijzingssite:

1. De auteur snel starten met het argument jvm `-Dabtesting.enabled=true` om A/B-tests op de server in te schakelen.

   **Opmerking**: Als de AEM-instantie wordt uitgevoerd op JBoss, die is gestart als een service van de Turnkey-installatie, voegt u de `-Dabtesting.enabled=true` parameter in de volgende vermelding in de `jboss\bin\standalone.conf.bat` bestand,

   `set "JAVA_OPTS=%JAVA_OPTS% -Dadobeidp.serverName=server1 -Dfile.encoding=utf8 -Djava.net.preferIPv4Stack=true -Dabtesting.enabled=true"`

1. Ga naar https://&lt;*hostnaam*>:&lt;*poort*>/libs/cq/core/content/tools/cloudservices.html.

1. In de **[!UICONTROL Adobe Target]** sectie, klikt u op **[!UICONTROL Show Configurations]**. U kunt de beschikbare Configuratie van het Doel van Web zien. Klik om de configuratie te openen. Klik op de configuratiepagina op **[!UICONTROL Edit]**. De **[!UICONTROL Edit Component]** wordt geopend voor de configuratie.

1. Geef uw clientcode, e-mail en wachtwoord op die aan uw doelaccount zijn gekoppeld. API-type selecteren als **[!UICONTROL REST]**.
1. Klik op **[!UICONTROL Connect to Adobe target]**. Klik op **[!UICONTROL OK]**. U kunt zien de verpakte configuratie een Kader van het Doel heeft.

1. Ga naar https://&lt;*hostnaam*>:&lt;*poort*>/system/console/configMgr.

1. Klik op **[!UICONTROL AEM Forms Target Configuration]**.
1. Selecteer een doelframework.
1. In de **[!UICONTROL Target URLs]** -veld, geeft u de URL voor AEM Forms op. Bijvoorbeeld: https://&lt;*hostnaam*>:&lt;*poort*>.

1. Klik op **[!UICONTROL Save]**.

In gevallen waarin gebruik wordt gemaakt van creditcardaanvragen en Home Mortgauge wordt getoond hoe een A/B-test kan worden uitgevoerd en een rapport kan worden weergegeven voor demodoeleinden. Voor analyses, zie [We.Financiële referentiesite doorlopen](/help/forms/using/finance-reference-site-walkthrough.md).

## Volgende stap {#next-step}

Nu bent u allen klaar om de verwijzingsplaats te onderzoeken. Zie voor meer informatie over de workflow en stappen van de verwijzingssite:

* [We.Financiële referentiesite doorlopen](/help/forms/using/finance-reference-site-walkthrough.md)
* [We.Gov-referentiesite doorloopt](/help/forms/using/gov-reference-site-walkthrough.md)

* [Werknemerslijst voor zelfbedieningsverwijzingssite](/help/forms/using/employee-self-service-reference-site.md)
