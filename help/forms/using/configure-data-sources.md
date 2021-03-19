---
title: Gegevensbronnen configureren
seo-title: Gegevensbronnen configureren
description: Leer hoe u verschillende typen gegevensbronnen configureert en hoe u modellen met formuliergegevens maakt.
seo-description: Leer hoe u verschillende typen gegevensbronnen configureert en hoe u modellen met formuliergegevens maakt.
uuid: 292217c2-8110-4232-a78b-edea212765d2
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: integration
discoiquuid: 1dafd400-16c0-416d-9e81-7bf53b761f98
feature: Formuliergegevensmodel
translation-type: tm+mt
source-git-commit: 75312539136bb53cf1db1de03fc0f9a1dca49791
workflow-type: tm+mt
source-wordcount: '1318'
ht-degree: 0%

---


# Gegevensbronnen {#configure-data-sources} configureren

Leer hoe u verschillende typen gegevensbronnen configureert en hoe u modellen met formuliergegevens maakt.

![](do-not-localize/data-integeration.png)

Met AEM Forms Data Integration kunt u verschillende gegevensbronnen configureren en verbinden. De volgende types worden gesteund uit-van-de-doos. Met weinig aanpassing kunt u echter ook andere gegevensbronnen integreren.

* Relationele databases - MySQL, Microsoft SQL Server, IBM DB2 en Oracle RDBMS
* Gebruikersprofiel AEM
* RESTful-webservices
* SOAP-webservices
* OData-diensten

De integratie van gegevens steunt OAuth2.0, Basisauthentificatie, en API Zeer belangrijke authentificatietypes out-of-the-box, en staat het uitvoeren van douaneauthentificatie voor de toegang tot van de Webdiensten toe. Terwijl RESTful, op ZEEP-Gebaseerde, en de diensten OData in de Diensten van de Wolk van AEM worden gevormd, JDBC voor relationele gegevensbestanden en schakelaar voor AEM gebruikersprofiel worden gevormd in AEM Webconsole.

## Relationele database {#configure-relational-database} configureren

U kunt relationele gegevensbestanden vormen gebruikend AEM de Configuratie van de Console van het Web. Ga als volgt te werk:

1. Ga naar AEM webconsole op `https://[server]:[host]/system/console/configMgr`.
1. Zoek naar configuratie **[!UICONTROL Apache Sling Connection Pooled DataSource]**. Tik om de configuratie te openen in de bewerkingsmodus.
1. In de configuratiedialoog, specificeer de details voor het gegevensbestand u, zoals wilt vormen:

   * Naam van de gegevensbron
   * Het bezit van de gegevensbrondienst dat de naam van de gegevensbron opslaat
   * Java-klassenaam voor het JDBC-stuurprogramma
   * URI voor JDBC-verbinding
   * Gebruikersnaam en wachtwoord om verbinding te maken met het JDBC-stuurprogramma

   >[!NOTE]
   >
   >Zorg ervoor dat u gevoelige informatie zoals wachtwoorden codeert alvorens de gegevensbron te vormen. Coderen:
   >
   >1. Ga naar `https://[server]:[port]/system/console/crypto`.
   >1. Geef in het veld **[!UICONTROL Plain Text]** het wachtwoord of een tekenreeks op die u wilt coderen en klik op **[!UICONTROL Protect]**.

   >
   >De gecodeerde tekst wordt weergegeven in het veld Beveiligde tekst dat u in de configuratie kunt opgeven.

1. Schakel **[!UICONTROL Test on Borrow]** of **[!UICONTROL Test on Return]** in om op te geven dat de objecten worden gevalideerd voordat ze van en naar de pool worden geleend of geretourneerd.
1. Geef een SQL SELECT-query op in het veld **[!UICONTROL Validation Query]** om verbindingen vanuit de pool te valideren. De query moet ten minste één rij retourneren. Geef op basis van uw database een van de volgende opties op:

   * SELECT 1 (MySQL en MS SQL)
   * SELECTEER 1 uit twee items (Oracle)

1. Tik **[!UICONTROL Save]** om de configuratie op te slaan.

## AEM gebruikersprofiel {#configure-aem-user-profile} configureren

U kunt AEM gebruikersprofiel vormen gebruikend de Configuratie van de Verbinding van het Profiel van de Gebruiker in AEM Console van het Web. Ga als volgt te werk:

1. Ga naar AEM webconsole op `https://[server]:[host]/system/console/configMgr`.
1. Zoek **[!UICONTROL AEM Forms Data Integrations - User Profile Connector Configuration]** en tik om de configuratie in Edit wijze te openen.
1. In het dialoogvenster Configuratie gebruikersprofiel-aansluiting kunt u eigenschappen van gebruikersprofielen toevoegen, verwijderen of bijwerken. De opgegeven eigenschappen zijn beschikbaar voor gebruik in het formuliergegevensmodel. Gebruik de volgende indeling om gebruikersprofieleigenschappen op te geven:

   `name=[property_name_with_location_in_user_profile],type=[property_type]`

   Voorbeelden:

   * `name=profile/phoneNumber,type=string`
   * `name=profile/empLocation/*/city,type=string`

   >[!NOTE]
   >
   >Met **&amp;ast;** in het bovenstaande voorbeeld worden alle knooppunten onder het knooppunt `profile/empLocation/` in AEM gebruikersprofiel in de CRXDE-structuur aangegeven. Dit betekent dat het formuliergegevensmodel toegang heeft tot de eigenschap `city` van het type `string` in elk knooppunt onder het knooppunt `profile/empLocation/`. Nochtans, moeten de knopen die het gespecificeerde bezit bevatten een verenigbare structuur volgen.

1. Tik **[!UICONTROL Save]** om de configuratie op te slaan.

## Map configureren voor configuraties van cloudservices {#cloud-folder}

>[!NOTE]
>
>Configuratie voor map met cloudservices is vereist voor het configureren van cloudservices voor RESTful-, SOAP- en OData-services.

Alle configuraties van de cloudservice in AEM worden geconsolideerd in de map `/conf` in AEM opslagplaats. Standaard bevat de map `conf` de map `global` waarin u cloudserviceconfiguraties kunt maken. U moet deze echter handmatig inschakelen voor cloudconfiguraties. U kunt ook extra mappen maken in `conf` om configuraties voor cloudservices te maken en in te delen.

De map configureren voor configuraties van cloudservices:

1. Ga naar **[!UICONTROL Tools > General > Configuration Browser]**.
   * Zie de [documentatie van de Browser van de Configuratie](/help/sites-administering/configurations.md) voor meer informatie.
1. Ga als volgt te werk om de algemene map voor cloudconfiguraties in te schakelen of sla deze stap over om een andere map voor cloudserviceconfiguraties te maken en te configureren.

   1. Selecteer in **[!UICONTROL Configuration Browser]** de map `global` en tik **[!UICONTROL Properties]**.
   1. Schakel in het dialoogvenster **[!UICONTROL Configuration Properties]** **[!UICONTROL Cloud Configurations]** in.
   1. Tik **[!UICONTROL Save & Close]** om de configuratie op te slaan en het dialoogvenster af te sluiten.

1. Tik in **[!UICONTROL Configuration Browser]** op **[!UICONTROL Create]**.
1. Geef in het dialoogvenster **[!UICONTROL Create Configuration]** een titel op voor de map en schakel **[!UICONTROL Cloud Configurations]** in.
1. Tik **[!UICONTROL Create]** om de map te maken die geschikt is voor configuraties van cloudservices.

## RESTful-webservices {#configure-restful-web-services} configureren

RESTful Webdienst kan worden beschreven gebruikend [de Specificaties van de Wager](https://swagger.io/specification/) in formaat JSON of YAML in een Swagger definitiedossier. Als u de RESTful-webservice in AEM-cloudservices wilt configureren, moet u ervoor zorgen dat het Swagger-bestand zich op uw bestandssysteem bevindt of de URL waar het bestand wordt gehost.

Doe het volgende de diensten RESTful vormen:

1. Ga naar **[!UICONTROL Tools > Cloud Services > Data Sources]**. Tik om de map te selecteren waarin u een cloudconfiguratie wilt maken.

   Zie [Map configureren voor configuraties van cloudservices](/help/forms/using/configure-data-sources.md#cloud-folder) voor informatie over het maken en configureren van een map voor configuraties van cloudservices.

1. Tik **[!UICONTROL Create]** om **[!UICONTROL Create Data Source Configuration dialog]** te openen. Geef een naam en eventueel een titel voor de configuratie op, selecteer **[!UICONTROL RESTful Service]** in de vervolgkeuzelijst **[!UICONTROL Service Type]**, blader optioneel naar een miniatuurafbeelding voor de configuratie en selecteer **[!UICONTROL Next]**.
1. Specificeer de volgende details voor de RESTful dienst:

   * Selecteer URL of Dossier van de Bron van de Wagger drop-down, en specificeer dienovereenkomstig Swagger URL aan het de definitiedossier van de Wagger of upload het dossier van de Swagger van uw lokaal dossiersysteem.
   * Selecteer het authentificatietype — niets, OAuth2.0, Basisauthentificatie, API Sleutel, of de Authentificatie van de Douane — om tot de dienst toegang te hebben RESTful, en dienovereenkomstig details voor authentificatie te verstrekken.

1. Tik **[!UICONTROL Create]** om de cloudconfiguratie voor de RESTful-service te maken.

## SOAP-webservices configureren {#configure-soap-web-services}

Webservices op basis van SOAP worden beschreven met de [WSDL-specificaties (Web Services Description Language)](https://www.w3.org/TR/wsdl). Als u op SOAP gebaseerde webservice wilt configureren in AEM-cloudservices, moet u de WSDL-URL voor de webservice hebben en het volgende doen:

1. Ga naar **[!UICONTROL Tools > Cloud Services > Data Sources]**. Tik om de map te selecteren waarin u een cloudconfiguratie wilt maken.

   Zie [Map configureren voor configuraties van cloudservices](/help/forms/using/configure-data-sources.md#cloud-folder) voor informatie over het maken en configureren van een map voor configuraties van cloudservices.

1. Tik **[!UICONTROL Create]** om **[!UICONTROL Create Data Source Configuration dialog]** te openen. Geef een naam en eventueel een titel voor de configuratie op, selecteer **[!UICONTROL SOAP Web Service]** in de vervolgkeuzelijst **[!UICONTROL Service Type]**, blader optioneel naar een miniatuurafbeelding voor de configuratie en selecteer **[!UICONTROL Next]**.
1. Geef het volgende op voor de SOAP-webservice:

   * WSDL-URL voor de webservice.
   * Service Endpoint. Specificeer een waarde op dit gebied om het de diensteindpunt met voeten te treden dat in WSDL wordt vermeld.
   * Selecteer het authentificatietype — niets, OAuth2.0, BasisAuthentificatie, de Authentificatie van de Douane, of Token X509 — om tot de dienst van de ZEEP toegang te hebben, en dienovereenkomstig de details voor authentificatie te verstrekken.

      Als u Token X509 als Type van Authentificatie selecteert, vorm het X509- certificaat. Zie [Certificaten instellen](install-configure-document-services.md#set-up-certificates-for-reader-extension-and-encryption-service) voor meer informatie.
Geef de alias KeyStore voor het X509-certificaat op in het veld **[!UICONTROL Key Alias]**. Geef de tijd in seconden op tot het verificatieverzoek geldig blijft in het veld **[!UICONTROL Time To Live]**. Selecteer desgewenst om de berichttekst, de tijdstempelkop of beide te ondertekenen.

1. Tik op **[!UICONTROL Create]** om de wolkenconfiguratie voor de SOAP-webservice te maken.

## OData-services configureren {#config-odata}

De dienst OData wordt geïdentificeerd door zijn de dienstwortel URL. Als u een OData-service in AEM-cloudservices wilt configureren, moet u ervoor zorgen dat u over de URL van de servicehoofdmap voor de service beschikt en moet u het volgende doen:

>[!NOTE]
>
>Voor geleidelijke gids om de Dynamica 365 van Microsoft, online of op-gebouw te vormen, zie [Configuratie van de Dynamica OData van Microsoft](/help/forms/using/ms-dynamics-odata-configuration.md).

1. Ga naar **[!UICONTROL Tools > Cloud Services > Data Sources]**. Tik om de map te selecteren waarin u een cloudconfiguratie wilt maken.

   Zie [Map configureren voor configuraties van cloudservices](/help/forms/using/configure-data-sources.md#cloud-folder) voor informatie over het maken en configureren van een map voor configuraties van cloudservices.

1. Tik **[!UICONTROL Create]** om **[!UICONTROL Create Data Source Configuration dialog]** te openen. Geef een naam en eventueel een titel voor de configuratie op, selecteer **[!UICONTROL OData Service]** in de vervolgkeuzelijst **[!UICONTROL Service Type]**, blader optioneel naar een miniatuurafbeelding voor de configuratie en selecteer **[!UICONTROL Next]**.
1. Specificeer de volgende details voor de dienst OData:

   * Service Root URL voor de OData-service die moet worden geconfigureerd.
   * Selecteer het authentificatietype — niets, OAuth2.0, Basisauthentificatie, of de Authentificatie van de Douane — om tot de dienst toegang te hebben OData, en dienovereenkomstig de details voor authentificatie te verstrekken.

   >[!NOTE]
   >
   >U moet OAuth 2.0 authentificatietype selecteren om met de diensten van de Dynamiek van Microsoft te verbinden gebruikend eindpunt OData als de dienstwortel.

1. Tik **Maak** om de cloudconfiguratie voor de OData-service te maken.

## Volgende stappen {#next-steps}

U hebt de gegevensbronnen geconfigureerd. Vervolgens kunt u een formuliergegevensmodel maken of als u al een formuliergegevensmodel zonder gegevensbron hebt gemaakt, kunt u dit koppelen aan de zojuist geconfigureerde gegevensbronnen. Zie [Formuliergegevensmodel maken](/help/forms/using/create-form-data-models.md) voor meer informatie.
