---
title: Zelfstudie - Uw eerste interactieve communicatie maken
seo-title: Create your first Interactive Communication
description: Leer om uw eerste Interactieve Communicatie tot stand te brengen.
seo-description: Learn to create your first Interactive Communication.
uuid: ed5003c6-ba3a-4fcb-8645-c7b607b22fb5
contentOwner: anujkapo
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: interactive-communications, introduction
discoiquuid: 954da8da-a30b-477d-bde7-3edd86a5be11
feature: Interactive Communication
exl-id: 4b2754dc-4b41-4d0d-a22c-d45595b36f84
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1079'
ht-degree: 0%

---

# Zelfstudie: Maak uw eerste interactieve communicatie {#tutorial-create-your-first-interactive-communication}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Leer om uw eerste Interactieve Communicatie tot stand te brengen.

![01-create-first-adaptive-form-hero-image](assets/01-create-first-adaptive-form-hero-image.png)

De interactieve Mededelingen centraliseert en beheert de verwezenlijking, de assemblage, en de levering van veilige, gepersonaliseerde, en interactieve correspondentie zoals bedrijfscorrespondentie, documenten, verklaringen, marketing post, rekeningen, en welkomstkits. Interactieve communicatie kan via twee kanalen worden aangeboden: Afdrukken en web. Het kanaal van de Druk wordt gebruikt om PDF en papiermededelingen tot stand te brengen, terwijl het kanaal van het Web wordt gebruikt om online ervaringen te leveren.

Deze zelfstudie biedt een end-to-end framework voor het maken van interactieve communicatie. De zelfstudie is ingedeeld in een gebruikscase en meerdere hulplijnen. Elke gids helpt u om eigenschappen tot stand te brengen die als bouwstenen worden gebruikt om een Interactieve Communicatie tot stand te brengen.

De volgende afbeelding illustreert de bouwstenen die nodig zijn om een interactieve communicatie te maken.

![werkstroom](assets/workflow.gif)

Aan het einde van deze zelfstudie kunt u het volgende doen:

* Bouwstenen maken (formuliergegevensmodel, documentfragmenten en sjablonen)
* Een interactieve communicatie maken
* Een interactieve communicatie testen en publiceren

## Hoofdletters gebruiken {#use-case}

De reis begint met het leren van het gebruiksgeval:

Een telecomoperator stuurt maandelijkse facturen naar de klanten via e-mail. De rekening is een Interactieve Communicatie. Het e-mailbericht bevat:

* Een met een wachtwoord beveiligde PDF, in deze zelfstudie wordt in dit document het kanaal Afdrukken genoemd. Het omvat klantgegevens, factureringsdetails, overzicht van kosten, geschikte wijzen van betaling van de rekening, en gebruiksdetails.
* Een koppeling naar de webversie van de factuur, in deze zelfstudie ook wel webkanaal genoemd. De webversie van de factuur biedt naast de gegevens die in de versie PDF worden vermeld, een grafische weergave van de gebruiksgegevens en persoonlijke aanbiedingen op basis van Adobe Target. De webversie bevat ook een online betalingsformulier. Het helpt om online betalingen te doen zonder het IC te verlaten.
* Een koppeling naar services met toegevoegde waarde, zoals onlineopslag, muziekabonnementen en video-abonnementen op aanvraag.

## Vereisten {#prerequisites}

* Stel een AEM auteur-instantie in.
* Installeren [AEM Forms-invoegtoepassing](/help/forms/using/installing-configuring-aem-forms-osgi.md) op auteurinstantie
* De MYSQL-database instellen
* Vraag het JAR-bestand (JDBC-databasestuurprogramma) aan bij de databaseprovider. De voorbeelden in het leerprogramma zijn gebaseerd op gegevensbestand MySQL en gebruiken Oracle [MySQL JDBC-databasestuurprogramma](https://dev.mysql.com/downloads/connector/j/5.1.html).

## Stap 1: De interactieve communicatie plannen {#step-plan-the-interactive-communication}

![07-apply-rules-to-adaptive-form_small](assets/07-apply-rules-to-adaptive-form_small.png)

De eerste stap in het plannen van een Interactieve Mededeling is de inhoud van de Interactieve Mededeling te voltooien. Nadat de inhoud wordt voltooid, moet u het analyseren om de diverse activatypes te identificeren die worden vereist om de Interactieve Mededeling tot stand te brengen.

**Doelstellingen:**

Om een anatomie voor Interactieve Communicatie met de volgende wijzen van gegevensinput tot stand te brengen:

* Statische tekst
* Formuliergegevensmodel
* Gebruikersinterface van agent
* Voorwaardelijke gegevens
* Afbeeldingen

[ ](/help/forms/using/planning-interactive-communications.md)

## Stap 2: Formuliergegevensmodel maken {#step-create-form-data-model}

![03-create-adaptive-form-main-image_small](assets/03-create-adaptive-form-main-image_small.png)

Met een formuliergegevensmodel kunt u een interactieve communicatie met verschillende gegevensbronnen verbinden. Bijvoorbeeld AEM gebruikersprofiel, RESTful Webdiensten, op SOAP-Gebaseerde Webdiensten, OData diensten, en relationele gegevensbestanden. Een model van vormgegevens is een verenigd schema van de gegevensvertegenwoordiging van bedrijfsentiteiten en de diensten beschikbaar in verbonden gegevensbronnen. U kunt het model van formuliergegevens met een interactieve communicatie gebruiken om gegevens op te halen uit verbonden gegevensbronnen. Zie voor meer informatie over het formuliergegevensmodel [AEM Forms-gegevensintegratie](/help/forms/using/data-integration.md).

**Doelstellingen:**

* Database-instantie (MySQL-database) configureren als gegevensbron
* Maak het formuliergegevensmodel met MySQL-database als gegevensbron
* Gegevensmodelobjecten toevoegen aan formuliergegevensmodel
* Lezen- en schrijfservices configureren voor het gegevensmodel van het formulier
* Koppelingen maken tussen gegevensmodelobjecten
* Automatisch gegenereerde voorbeeldgegevens weergeven
* Voorbeeldgegevens bewerken
* Formuliergegevensmodel testen en geconfigureerde services met testgegevens

[ ](create-form-data-model-tutorial.md)

## Stap 3: Documentfragmenten maken {#step-create-document-fragments}

![05-create-form-data-model-main_small](assets/05-create-form-data-model-main_small.png)

Documentfragmenten zijn herbruikbare componenten van een correspondentie die worden gebruikt om een interactieve communicatie samen te stellen. De documentfragmenten zijn van het type: Tekst, Lijst en Voorwaarde.

**Doelstellingen:**

* Documentfragmenten maken
* Variabelen maken
* Regels maken en toepassen

[ ](/help/forms/using/create-document-fragments.md)

## Stap 4: Sjablonen maken {#step-create-templates}

![07-apply-rules-to-adaptive-form_small](assets/07-apply-rules-to-adaptive-form_small.png)

Om een Interactieve Mededeling tot stand te brengen, moet u malplaatjes beschikbaar op de AEM server voor de Kanalen van de Druk en van het Web hebben.

De sjablonen voor het kanaal Afdrukken worden gemaakt in Adobe Forms Designer en geüpload naar de AEM server. Deze malplaatjes zijn dan beschikbaar voor gebruik terwijl het creëren van een Interactieve Mededeling.

De malplaatjes voor het kanaal van het Web worden gecreeerd in AEM. Sjabloonauteurs en -beheerders kunnen websjablonen maken, bewerken en inschakelen. Zodra gecreeerd en toegelaten, zijn deze malplaatjes beschikbaar voor gebruik terwijl het creëren van een Interactieve Communicatie.

**Doelstellingen:**

* XDP-sjablonen maken voor het afdrukkanaal met Adobe Forms Designer
* De XDP-sjablonen uploaden naar de AEM Forms-server
* Sjablonen voor het webkanaal maken en inschakelen

[ ](/help/forms/using/create-templates-print-web.md)

## Stap 5: Een interactieve communicatie maken {#step-create-an-interactive-communication}

![09-stijl-uw-adaptief-vorm-klein](assets/09-style-your-adaptive-form-small.png)

Zodra u alle bouwstenen zoals het model van vormgegevens, documentfragmenten, en malplaatjes voor de Webversie creeert, kunt u beginnen tot een Interactieve Mededeling te leiden.

De interactieve Mededelingen kunnen door twee kanalen worden geleverd: Afdrukken en web. U kunt ook een interactieve communicatie maken met Afdrukkanaal als master kanaal. De optie Afdrukken als master optie voor het webkanaal zorgt ervoor dat de inhoud, overerving en gegevensbinding van het webkanaal worden afgeleid van het kanaal Afdrukken.

**Doelstellingen:**

* Interactieve communicatie maken voor het afdrukkanaal
* Interactieve communicatie voor het webkanaal maken
* Creeer Druk en Web Interactieve Mededelingen met Druk als Master
* Een dynamische tabel maken in de webversie van Interactieve communicatie
* Creeer een grafiek in de versie van het Web van Interactieve Communicatie
* Hyperlinks maken in de webversie van Interactieve communicatie

[ ](create-interactive-communication-tutorial.md)

## Stap 6: Interactieve communicatie testen {#step-test-your-interactive-communication}

![11-test-uw-adaptieve vorm](assets/11-test-your-adaptive-form.png)

Zodra u een Interactieve Communicatie hebt gecreeerd, is het belangrijk dat u elke verandering test die u in hen aanbrengt. Het testen van elk gebied van een Interactieve Mededeling is vervelend. AEM Forms biedt een SDK (Calvin SDK) waarmee het testen van interactieve communicatie in een webbrowser kan worden geautomatiseerd.

**Doelstellingen:**

* Testsuite maken
* Testcase maken
* Voer de testcase uit

## Stap 7: Uw interactieve communicatie publiceren {#step-publish-your-interactive-communication}

![12-publish-your-adaptive-form-_small](assets/12-publish-your-adaptive-form-_small.png)

Nadat u interactieve communicatie hebt gemaakt en getest met de kanalen Afdrukken en Web, kunt u deze elementen publiceren. Het gebruiksscenario dat in deze zelfstudie wordt beschreven, is gericht op het integreren van deze elementen met een e-mailclient. De e-mailclient fungeert als brug voor het verzenden van interactieve communicatie naar meerdere e-mailadressen.

**Doelstellingen:**

* Integreer Interactieve Mededelingen met een e-mailcliënt om een mededeling naar de klanten te kunnen verzenden
* Een PDF-document opnemen als bijlage (interactieve communicatie gemaakt in het afdrukkanaal)
* Neem een koppeling op naar de webversie van de interactieve communicatie
