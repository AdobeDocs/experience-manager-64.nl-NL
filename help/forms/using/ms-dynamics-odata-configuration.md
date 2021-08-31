---
title: Configuratie Microsoft Dynamics OData
seo-title: Microsoft Dynamics ODtata configuration
description: De diensten van de Dynamiek van Microsoft van de hefboomwerking, integreren, en werken met online en op-gebouw door het model van vormgegevens.
seo-description: Learn how to leverage integrate and work with online and on-premises Microsoft Dynamics services through form data model.
uuid: c9b2764f-9127-4a99-a469-b6ebcdee8fdf
topic-tags: integration
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 62f9d1de-c397-46b5-964e-19777ddd130c
feature: Form Data Model
exl-id: 18df57b6-789a-4b61-9418-fa12294b226f
source-git-commit: e608249c3f95f44fdc14b100910fa11ffff5ee32
workflow-type: tm+mt
source-wordcount: '1167'
ht-degree: 0%

---

# Configuratie Microsoft Dynamics OData {#microsoft-dynamics-odata-configuration}

De diensten van de Dynamiek van Microsoft van de hefboomwerking, integreren, en werken met online en op-gebouw door het model van vormgegevens.

![gegevensintegratie](assets/data-integeration.png)

De Dynamiek van Microsoft is een software van het Beheer van de Verhouding van de Klant (CRM) en van het Middel van de Onderneming van de Planning (ERP) die ondernemingsoplossingen voor het creëren van en het beheren van klantenrekeningen, contacten, lood, kansen, en gevallen verstrekt. [AEM Forms Data ](/help/forms/using/data-integration.md) Integration biedt een OData-cloudserviceconfiguratie om Forms te integreren met zowel de online server als de Microsoft Dynamics-server op locatie. Het laat u toe om vormgegevensmodel tot stand te brengen dat op de entiteiten, de attributen, en de diensten wordt gebaseerd die in de dienst van de Dynamiek van Microsoft worden bepaald. Met het gegevensmodel van het formulier kunt u adaptieve formulieren maken die interageren met de Microsoft Dynamics-server om werkstromen van bedrijven mogelijk te maken. Bijvoorbeeld:

* Query uitvoeren op Microsoft Dynamics-server voor gegevens en aangepaste formulieren vooraf invullen
* Gegevens naar Microsoft Dynamics schrijven bij het verzenden van aangepaste formulieren
* Schrijf gegevens in de Dynamiek van Microsoft door douaneentiteiten die in het model van vormgegevens worden bepaald en vice versa

Het AEM Forms-add-on-pakket bevat ook een referentie OData-configuratie die u kunt gebruiken om Microsoft Dynamics snel te integreren met AEM Forms.

Wanneer het pakket is geïnstalleerd, zijn de volgende entiteiten en services beschikbaar op uw AEM Forms-exemplaar:

* MS Dynamics OData Cloud Service (OData Service)
* Formuliergegevensmodel met vooraf geconfigureerde entiteiten en services voor dynamiek van Microsoft.

De Cloud Service OData en het model van vormgegevens met vooraf gevormde entiteiten en de diensten van de Dynamiek van Microsoft zijn beschikbaar op uw instantie van AEM Forms slechts als de looppaswijze voor de AEM instantie zoals `samplecontent` (gebrek) wordt geplaatst. Voor meer informatie bij het vormen looppaswijzen voor een AEM instantie, zie [Wijzen van de Looppas](/help/sites-deploying/configure-runmodes.md).

## Vereisten {#prerequisites}

Alvorens u begint opstelling en vormt de Dynamica van Microsoft, zorg ervoor dat u hebt:

* [AEM 6.4 Forms add-on package](https://helpx.adobe.com//experience-manager/6-4/forms/using/installing-configuring-aem-forms-osgi.html) is geïnstalleerd
* De gevormde Dynamica 365 van Microsoft online of installeerde een geval van één van de volgende versies van de Dynamica van Microsoft:

   * Microsoft Dynamics 365 op locatie
   * Microsoft Dynamics 2016 op locatie

* [Registered the application for Microsoft Dynamics online service with Microsoft Azure Active Directory](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/developer/walkthrough-register-dynamics-365-app-azure-active-directory). Noteer de waarden voor de client-id (ook toepassings-id genoemd) en het clientgeheim voor de geregistreerde service. Deze waarden worden gebruikt terwijl [het vormen van de wolkendienst voor uw dienst van de Dynamiek van Microsoft](/help/forms/using/ms-dynamics-odata-configuration.md#configure-cloud-service-for-your-microsoft-dynamics-service).

## Reactie-URL instellen voor geregistreerde toepassing Microsoft Dynamics {#set-reply-url-for-registered-microsoft-dynamics-application}

Ga als volgt te werk om Reactie URL voor geregistreerde toepassing van de Dynamiek van Microsoft te plaatsen:

>[!NOTE]
>
>Gebruik deze procedure alleen tijdens de integratie van AEM Forms met de online Microsoft Dynamics-server.

1. Ga naar Microsoft Azure Active Directory-account en voeg de volgende URL voor de configuratie van de cloudservice toe in **[!UICONTROL Reply URLs]**-instellingen voor uw geregistreerde toepassing:

   `https://[server]:[port]/libs/fd/fdm/gui/components/admin/fdmcloudservice/createcloudconfigwizard/cloudservices.html`

   ![azure_directory](assets/azure_directory.png)

1. Sla de configuratie op.

## Microsoft Dynamics voor IFD configureren {#configure-microsoft-dynamics-for-ifd}

De Dynamiek van Microsoft gebruikt op beweringen-gebaseerde authentificatie om toegang tot gegevens op de server van CRM van de Dynamica van Microsoft aan externe gebruikers te verlenen. Om dit toe te laten, doe het volgende om de Dynamica van Microsoft voor Internet-Onder ogen ziet plaatsing (IFD) te vormen en claimmontages te vormen.

>[!NOTE]
>
>Gebruik deze procedure slechts terwijl het integreren van AEM Forms met de server van de Dynamiek van Microsoft op-gebouw.

1. Vorm de Dynamica van Microsoft op-gebouw instantie voor IFD zoals die in [vorm IFD voor de Dynamica van Microsoft](https://technet.microsoft.com/en-us/library/dn609803.aspx) wordt beschreven.
1. Stel de volgende bevelen in werking gebruikend Vensters PowerShell om claimmontages op IFD-Toegelaten Dynamiek van Microsoft te vormen:

   ```
   Add-PSSnapin Microsoft.Crm.PowerShell 
    $ClaimsSettings = Get-CrmSetting -SettingType OAuthClaimsSettings 
    $ClaimsSettings.Enabled = $true 
    Set-CrmSetting -Setting $ClaimsSettings
   ```

   Zie [Toepassingsregistratie voor CRM op-gebouw (IFD)](https://msdn.microsoft.com/sl-si/library/dn531010(v=crm.7).aspx#bkmk_ifd) voor meer informatie.

## OAuth-client configureren op AD FS-computer {#configure-oauth-client-on-ad-fs-machine}

Doe het volgende om een cliënt OAuth op de Actieve machine van de Diensten van de Federatie van de Folder (AD FS) te registreren en toegang op de machine van het ADS te verlenen:

>[!NOTE]
>
>Gebruik deze procedure slechts terwijl het integreren van AEM Forms met de server van de Dynamiek van Microsoft op-gebouw.

1. Voer de volgende opdracht uit:

   `Add-AdfsClient -ClientId “<Client-ID>” -Name "<name>" -RedirectUri "<redirect-uri>" -GenerateClientSecret`

   Waar:

   * `Client-ID` is een cliëntidentiteitskaart u het gebruiken van om het even welke generator kunt produceren GUID.
   * `redirect-uri` is URL aan de de wolkendienst van de Dynamiek van Microsoft OData op AEM Forms. De standaardcloudservice die wordt geïnstalleerd met het AEM Forms-pakket, wordt geïmplementeerd op de volgende URL:

      ```
      http://[server]:[port]/libs/fd/fdm/gui/components/admin/fdmcloudservice/createcloudconfigwizard/cloudservices.html
      ```

1. Voer de volgende opdracht uit om toegang te verlenen op de AD FS-computer:

   `Grant-AdfsApplicationPermission -ClientRoleIdentifier “<Client-ID>” -ServerRoleIdentifier <resource> -ScopeNames openid`

   Waar:

   * `resource` is de organisatie URL van de Dynamiek van Microsoft.

1. Microsoft Dynamics gebruikt HTTPS-protocol. Als u AD FS-eindpunten wilt aanroepen vanaf de Forms-server, installeert u het certificaat van de Microsoft Dynamics-site in de Java-certificaatopslag met de opdracht `keytool` op de computer waarop AEM Forms wordt uitgevoerd.

## De cloudservice voor uw Microsoft Dynamics configureren {#configure-cloud-service-for-your-microsoft-dynamics-service}

De **MS Dynamics OData Cloud Service (OData Service)** configuratie wordt geleverd met standaard OData configuratie. Om het te vormen om met uw dienst van de Dynamiek van Microsoft te verbinden, doe het volgende.

1. Navigeer naar **[!UICONTROL Tools > Cloud Services > Data Sources]** en tik op de configuratiemap `global`.
1. Selecteer **[!UICONTROL MS Dynamics OData Cloud Service (OData Service)]** configuratie en tik **[!UICONTROL Properties]**. Het dialoogvenster voor de configuratie-eigenschap van de cloudservice wordt geopend.

   Op het tabblad **[!UICONTROL Authentication Settings]**:

   1. Voer de waarde in voor het veld **[!UICONTROL Service Root]**. Ga naar de instantie van de Dynamiek en navigeer aan **[!UICONTROL Developer Resources]** om de waarde voor het gebied van de Wortel van de Dienst te bekijken. Bijvoorbeeld https://&lt;huurder-name>/api/data/v9.1/
   1. Vervang de standaardwaarden in **[!UICONTROL Client Id]** (ook genoemd als **[!UICONTROL Application ID]**), **[!UICONTROL Client Secret]**, **[!UICONTROL OAuth URL]**, **[!UICONTROL Refresh Token URL]**, **[!UICONTROL Access Token URL]**, en **[!UICONTROL Resource]** gebieden met waarden van uw de dienstconfiguratie van de Dynamiek van Microsoft. Het is verplicht de URL van de dynamische instantie op te geven in het veld **[!UICONTROL Resource]** om Microsoft Dynamics te configureren met een formuliergegevensmodel. Gebruik de URL van de hoofdmap van de service om de URL van de dynamische instantie af te leiden. Bijvoorbeeld [https://org.crm.dynamics.com](https://org.crm.dynamics.com/).
   1. Geef **[!UICONTROL openid]** op in het veld **[!UICONTROL Authorization Scope]** voor het autorisatieproces in Microsoft Dynamics.

   ![dynamics_authentication_settings](assets/dynamics_authentication_settings.png)

1. Klik op **[!UICONTROL Connect to OAuth]**. U wordt opnieuw gericht aan de login van de Dynamica van Microsoft pagina.
1. Meld u aan met de referenties voor Microsoft Dynamics en accepteer de configuratie van de cloudservice om verbinding te maken met de Microsoft Dynamics-service. Het is een eenmalige taak om verbinding tot stand te brengen tussen de cloudservice en de service.

   Vervolgens wordt u omgeleid naar de configuratiepagina van de cloudservice, die een bericht weergeeft dat de OData-configuratie is opgeslagen.

De de wolkendienst van de Cloud Service van de Dynamica van MS (OData Service) wordt gevormd en met uw dienst van de Dynamica verbonden.

## Formuliergegevensmodel maken {#create-form-data-model}

Wanneer u het pakket van AEM Forms installeert, wordt een model van vormgegevens, **de Dynamica FDM van Microsoft**, opgesteld op uw AEM instantie. Door gebrek, gebruikt het model van vormgegevens de dienst van de Dynamiek van Microsoft die in de Cloud Service van de Dynamiek van MS (OData Dienst) als zijn gegevensbron wordt gevormd.

Bij het openen van het model van vormgegevens voor het eerst, verbindt het met de gevormde dienst van de Dynamiek van Microsoft en haalt entiteiten van uw instantie van de Dynamiek van Microsoft. De &quot;contact&quot;en &quot;lood&quot;entiteiten van de Dynamiek van Microsoft worden reeds toegevoegd in het model van vormgegevens.

Ga naar **[!UICONTROL Forms > Data Integrations]** om het formuliergegevensmodel te bekijken. Selecteer **[!UICONTROL Microsoft Dynamics FDM]** en klik **[!UICONTROL Edit]** om het model van vormgegevens in Edit wijze te openen. U kunt het formuliergegevensmodel ook rechtstreeks openen via de volgende URL:

`https://[*server*]:[*port*]/aem/fdm/editor.html/content/dam/formsanddocuments-fdm/ms-dynamics-fdm`

![default-fdm-1](assets/default-fdm-1.png)

Vervolgens kunt u een adaptief formulier maken op basis van het formuliergegevensmodel en dit gebruiken in verschillende aangepaste gevallen voor formuliergebruik, zoals:

* Aanpasbaar formulier vooraf invullen door informatie op te vragen bij Microsoft Dynamics entities and services
* De serverbewerkingen van Microsoft Dynamics aanroepen die zijn gedefinieerd in een formuliergegevensmodel met behulp van adaptieve formulierregels
* Verzonden formuliergegevens naar Microsoft Dynamics-entiteiten schrijven

Het wordt aanbevolen een kopie te maken van het formuliergegevensmodel dat bij het AEM Forms-pakket wordt geleverd en gegevensmodellen en -services naar wens te configureren. Zo weet u zeker dat toekomstige updates van het pakket het gegevensmodel van het formulier niet overschrijven.

Zie [Gegevensintegratie](/help/forms/using/data-integration.md) voor meer informatie over het maken en gebruiken van formuliergegevensmodellen in zakelijke workflows.
