---
title: "Zelfstudie: Formuliergegevensmodel maken "
seo-title: Create Form Data Model Tutorial
description: Met de AEM Forms-module voor gegevensintegratie kunt u een formuliergegevensmodel maken op basis van verschillende bronnen van back-endgegevens, zoals AEM gebruikersprofiel, RESTful-webservices, SOAP-webservices, OData-services en relationele databases. Leer hoe u MySQL-database configureert als gegevensbron, een formuliergegevensmodel maakt, configureert en test.
seo-description: AEM Forms data integration module allows you to create a form data model from disparate backend data sources such as AEM user profile, RESTful web services, SOAP-based web services, OData services, and relational databases. Learn how to configure MySQL database as data source, create, configure, and test a form data model.
page-status-flag: de-activated
uuid: 81d40278-4df9-4b61-93ad-eae2fce0a35c
contentOwner: khsingh
products: SG_EXPERIENCEMANAGER/6.3/FORMS
discoiquuid: 31e97723-d637-4a18-999d-36e00fbd031a
feature: Adaptive Forms
exl-id: 2f83e853-2468-4ea2-85f6-8cf7fe9de6a8
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1524'
ht-degree: 0%

---

# Zelfstudie: Formuliergegevensmodel maken  {#tutorial-create-form-data-model}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

![04-create-form-data-model-main](assets/04-create-form-data-model-main.png)

Deze zelfstudie is een stap in de [Uw eerste adaptieve formulier maken](/help/forms/using/create-your-first-adaptive-form.md) reeks. U wordt aangeraden de reeks in chronologische volgorde te volgen om het volledige gebruik van de zelfstudie te begrijpen, uit te voeren en aan te tonen.

## Over de zelfstudie {#about-the-tutorial}

Met de AEM Forms-module voor gegevensintegratie kunt u een formuliergegevensmodel maken op basis van verschillende bronnen van back-endgegevens, zoals AEM gebruikersprofiel, RESTful-webservices, SOAP-webservices, OData-services en relationele databases. U kunt gegevensmodelobjecten en -services configureren in een formuliergegevensmodel en deze koppelen aan een adaptief formulier. Adaptieve formuliervelden zijn gebonden aan objecteigenschappen van gegevensmodellen. Met deze services kunt u het adaptieve formulier vooraf invullen en verzonden formuliergegevens terugschrijven naar het gegevensmodelobject.

Voor meer informatie over de integratie van formuliergegevens en het formuliergegevensmodel raadpleegt u [AEM Forms-gegevensintegratie](/help/forms/using/data-integration.md).

Deze zelfstudie begeleidt u door de stappen voor het voorbereiden, maken, configureren en koppelen van een formuliergegevensmodel aan een adaptief formulier. Aan het einde van deze zelfstudie kunt u het volgende doen:

* [MySQL-database configureren als gegevensbron](#config-database)
* [Formuliergegevensmodel maken met MySQL-database](#create-fdm)
* [Formuliergegevensmodel configureren](#config-fdm)
* [Formuliergegevensmodel testen](#test-fdm)

Het formuliergegevensmodel ziet er ongeveer als volgt uit:

![form-data-model_l](assets/form-data-model_l.png)

**A.** Gevormde gegevensbronnen **B.** Gegevensbronschema&#39;s **C.** Beschikbare services **D.** Gegevensmodelobjecten **E.** Gevormde services

## Vereisten {#prerequisites}

Voordat u begint, moet u het volgende doen:

* MySQL-database met voorbeeldgegevens zoals vermeld in de sectie Voorwaarden van [Uw eerste adaptieve formulier maken](/help/forms/using/create-your-first-adaptive-form.md)
* OSGi-bundel voor MySQL JDBC-stuurprogramma, zoals wordt uitgelegd in [Het JDBC-databasestuurprogramma bundelen](/help/sites-developing/jdbc.md#bundling-the-jdbc-database-driver)
* Adaptief formulier, zoals uitgelegd in de eerste zelfstudie [Een adaptief formulier maken](/help/forms/using/create-adaptive-form.md)

## Stap 1: MySQL-database configureren als gegevensbron {#config-database}

U kunt verschillende typen gegevensbronnen configureren om een formuliergegevensmodel te maken. Voor dit leerprogramma, zullen wij het gegevensbestand vormen MySQL dat u met steekproefgegevens vormde en bevolkt. Voor informatie over andere gesteunde gegevensbronnen en hoe te om hen te vormen, zie [AEM Forms-gegevensintegratie](/help/forms/using/data-integration.md).

Ga als volgt te werk om uw MySQL-database te configureren:

1. Installeer het JDBC-stuurprogramma voor MySQL-database als een OSGi-bundel:

   1. Meld u als beheerder aan bij AEM Forms Author Instance en ga naar AEM bundels voor webconsoles. De standaard-URL is [http://localhost:4502/system/console/bundles](http://localhost:4502/system/console/bundles).

   1. Tikken **Installeren/bijwerken**. An **Bundels uploaden/installeren** wordt weergegeven.

   1. Tikken **Bestand kiezen** om te doorbladeren en de MySQL JDBC bestuurder OSGi bundel te selecteren. Selecteren **Bundel starten** en **Pakketten vernieuwen** en tikken **Installeren of bijwerken**. Zorg ervoor dat het JDBC-stuurprogramma voor MySQL van de Oracle Corporation actief is. Het stuurprogramma is geïnstalleerd.

1. MySQL-database configureren als gegevensbron:

   1. Ga naar AEM webconsole op [http://localhost:4502/system/console/configMgr](http://localhost:4502/system/console/configMgr).
   1. Zoeken **Apache Sling Connection Pooled DataSource** configuratie. Tik om de configuratie te openen in de bewerkingsmodus.
   1. Geef in het dialoogvenster Configuratie de volgende gegevens op:

      * **Naam gegevensbron:** U kunt elke gewenste naam opgeven. Geef bijvoorbeeld **WeRetailMySQL**.
      * **Eigenschapnaam van DataSource-service**: Specificeer naam van het de dienstbezit die de naam DataSource bevat. Het wordt gespecificeerd terwijl het registreren van de gegevensbroninstantie als dienst OSGi. Bijvoorbeeld: **datasource.name**.
      * **JDBC-stuurprogrammaklasse**: Geef de Java-klassenaam van het JDBC-stuurprogramma op. Voor MySQL-database geeft u **com.mysql.jdbc.Driver**.
      * **URI voor JDBC-verbinding**: Geef de verbindings-URL van de database op. Voor MySQL-database die wordt uitgevoerd op poort 3306 en schema weretail, is de URL: `jdbc:mysql://[server]:3306/weretail?autoReconnect=true&useUnicode=true&characterEncoding=utf-8`
      * **Gebruikersnaam:** Gebruikersnaam van de database. Het is vereist om JDBC-stuurprogramma in staat te stellen een verbinding met de database tot stand te brengen.
      * **Wachtwoord:** Wachtwoord van de database. Het is vereist om JDBC-stuurprogramma in staat te stellen een verbinding met de database tot stand te brengen.
      * **Testen op lenen:** De optie **Testen op lenen** optie.
      * **Testen op rendement:** De optie **Testen op rendement** optie.
      * **Validatiezoekopdracht:** Geef een SQL SELECT-query op om verbindingen vanuit de pool te valideren. De query moet ten minste één rij retourneren. Bijvoorbeeld: **&amp;last selecteren; van klantgegevens**.
      * **Transactieisolatie**: Stel de waarde in op **READ_COMTED**.

      Andere eigenschappen standaard laten staan [waarden](https://tomcat.apache.org/tomcat-7.0-doc/jdbc-pool.html) en tikken **Opslaan**.
   Er wordt een configuratie gemaakt die lijkt op de volgende configuratie.

   ![relationele database-data-source-configuration](assets/relational-database-data-source-configuration.png)

## Stap 2: Formuliergegevensmodel maken {#create-fdm}

AEM Forms biedt een intuïtieve gebruikersinterface voor [een formuliergegevensmodel maken](data-integration.md) van gevormde gegevensbronnen. U kunt meerdere gegevensbronnen gebruiken in een formuliergegevensmodel. Voor ons gebruiksgeval, zullen wij de gevormde gegevensbron gebruiken MySQL.

Ga als volgt te werk om het formuliergegevensmodel te maken:

1. Navigeer in AEM auteurinstantie naar **Forms** >  **Gegevensintegratie** s.
1. Tikken **Maken** >  **Formuliergegevensmodel**.
1. Geef in het dialoogvenster Formuliergegevensmodel maken een **name** voor het formuliergegevensmodel. Bijvoorbeeld: **klant-verzend-facturerings-details**. Tikken **Volgende**.
1. Het uitgezochte scherm van gegevensbron maakt een lijst van alle gevormde gegevensbronnen. Selecteren **WeRetailMySQL** gegevensbron en tik **Maken**.

   ![gegevensbron-selectie](assets/data-source-selection.png)

De **klant-verzend-facturerings-details** formuliergegevensmodel wordt gemaakt.

## Stap 3: Formuliergegevensmodel configureren {#config-fdm}

Het configureren van het formuliergegevensmodel omvat:

* toevoegen, gegevensmodelobject en -services
* het vormen lees en schrijf de diensten voor de voorwerpen van het gegevensmodel

Voer de volgende handelingen uit om het formuliergegevensmodel te configureren:

1. Navigeer bij AEM instantie van de auteur naar **Forms > Gegevensintegratie**. De standaard-URL is [http://localhost:4502/aem/forms.html/content/dam/formsanddocuments-fdm](http://localhost:4502/aem/forms.html/content/dam/formsanddocuments-fdm).
1. De **klant-verzend-facturerings-details** Hier wordt het formuliergegevensmodel weergegeven dat u eerder hebt gemaakt. Open het in bewerkingsmodus.

   De geselecteerde gegevensbron **WeRetailMySQL** is geconfigureerd in het formuliergegevensmodel.

   ![default-fdm](assets/default-fdm.png)

1. Vouw de WebRailMySQL-gegevensbronstructuur uit. Selecteer de volgende gegevensmodelvoorwerpen en de diensten van **wieg** >  **klantgegevens** schema naar formuliergegevensmodel:

   * **Gegevensmodelobjecten**:

      * id
      * name
      * ShippingAddress
      * stad
      * state
      * postcode
   * **Services:**

      * get
      * update

   Tikken **Geselecteerde toevoegen** Hiermee voegt u geselecteerde gegevensmodelobjecten en -services toe aan het formuliergegevensmodel.

   ![weretail-schema](assets/weretail-schema.png)

   >[!NOTE]
   >
   >De standaard krijgt, update, en neemt de diensten voor JDBC- gegevensbronnen op uit-van-de-doos met het model van vormgegevens.

1. Configureer lees- en schrijfservices voor het gegevensmodelobject.

   1. Selecteer **klantgegevens** gegevensmodelobject en tik **Eigenschappen bewerken**.
   1. Selecteren **get** in de vervolgkeuzelijst Leesservice. De **id** argument, de primaire sleutel in het gegevensmodelobject van de klant is, wordt automatisch toegevoegd. Tikken ![aem_6_3_edit](assets/aem_6_3_edit.png) en configureer het argument als volgt.

      ![standaard lezen](assets/read-default.png)

   1. Selecteer op dezelfde manier **update** als de schrijfservice. De **klantgegevens** object automatisch als een argument toegevoegd. Het argument is als volgt geconfigureerd.

      ![standaard schrijven](assets/write-default.png)

      Voeg en vorm toe **id** als volgt.

      ![id-arg](assets/id-arg.png)

   1. Tikken **Gereed** om de objecteigenschappen van het gegevensmodel op te slaan. Tik vervolgens op **Opslaan** om het formuliergegevensmodel op te slaan.

      De **get** en **update** de diensten worden toegevoegd als standaarddiensten voor het voorwerp van het gegevensmodel.

      ![data-model-object](assets/data-model-object.png)

1. Ga naar de **Services** tab en configure **get** en **update** diensten.

   1. Selecteer **get** service en tikken **Eigenschappen bewerken**. Het dialoogvenster Eigenschappen wordt geopend.
   1. Geef het volgende op in het dialoogvenster Eigenschappen bewerken:

      * **Titel**: Geef de titel van de service op. Bijvoorbeeld: Verzendadres ophalen.
      * **Beschrijving**: Geef een beschrijving op met een gedetailleerde werking van de service. Bijvoorbeeld:

         Deze service haalt het verzendadres en andere klantgegevens op uit MySQL-database

      * **Uitvoermodelobject**: Selecteer schema met klantgegevens. Bijvoorbeeld:

         customerdetail-schema
      * **Retourarray**: De opdracht **Retourarray** optie.
      * **Argumenten**: Benoemd argument selecteren **ID**.

      Tikken **Gereed**. De dienst om klantendetails van het gegevensbestand terug te winnen MySQL wordt gevormd.

      ![verzendadres-herwinning](assets/shiiping-address-retrieval.png)

   1. Selecteer **update** service en tikken **Eigenschappen bewerken**. Het dialoogvenster Eigenschappen wordt geopend.

   1. Geef het volgende op in het dialoogvenster Eigenschappen bewerken:

      * **Titel**: Geef de titel van de service op. Bijvoorbeeld Verzendadres bijwerken.

      * **Beschrijving**: Geef een beschrijving op met een gedetailleerde werking van de service. Bijvoorbeeld:

         Deze service werkt het verzendadres en verwante velden in de MySQL-database bij

      * **Invoermodelobject**: Selecteer schema met klantgegevens. Bijvoorbeeld:

         customerdetail-schema

      * **Uitvoertype**: Selecteren **BOOLEAN**.
      * **Argumenten**: Benoemd argument selecteren **ID** en **klantgegevens**.

      Tikken **Gereed**. De **update** de dienst om klantendetails in het MySQL gegevensbestand bij te werken wordt gevormd.

      ![send-address-update](assets/shiiping-address-update.png)



Het gegevensmodelvoorwerp en de diensten in het model van vormgegevens worden gevormd. U kunt nu het formuliergegevensmodel testen.

## Stap 4: Formuliergegevensmodel testen {#test-fdm}

U kunt het gegevensmodelobject en de services testen om te controleren of het formuliergegevensmodel correct is geconfigureerd.

Voer de volgende handelingen uit om de test uit te voeren:

1. Ga naar de **Model** selecteert u de **klantgegevens** gegevensmodelobject en tik **Model-object testen**.
1. In de **Testmodel/service** venster, selecteert u **Model-object lezen** van de **Model/service selecteren** vervolgkeuzelijst.
1. In de **klantgegevens** -sectie, geeft u een waarde op voor de **id** argument dat in het gevormde gegevensbestand MySQL bestaat en tikt **Testen**.

   De klantgegevens die aan opgegeven id zijn gekoppeld, worden opgehaald en weergegeven in het dialoogvenster **Uitvoer** zoals hieronder weergegeven.

   ![testmodel](assets/test-read-model.png)

1. Op dezelfde manier kunt u het Schrijven modelvoorwerp en de diensten testen.

   In het volgende voorbeeld werkt de updateservice de adresgegevens voor de id 7102715 in de database bij.

   ![test-schrijven-model](assets/test-write-model.png)

   Nu, als u de gelezen modeldienst opnieuw voor identiteitskaart 7107215 test, zal het de bijgewerkte klantendetails terugwinnen en tonen zoals hieronder getoond.

   ![lezen-bijgewerkt](assets/read-updated.png)
