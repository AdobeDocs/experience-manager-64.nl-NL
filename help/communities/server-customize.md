---
title: Aanpassing op de server
seo-title: Server-side Customization
description: Server-kant aanpassen in AEM Communities
seo-description: Customizing server-side in AEM Communities
uuid: 5e9bc6bf-69dc-414c-a4bd-74a104d7bd8f
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: df5416ec-5c63-481b-99ed-9e5a91df2432
exl-id: fbe2a617-e926-4842-a3bc-8d193bd367dc
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '927'
ht-degree: 0%

---

# Aanpassing op de server {#server-side-customization}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

| **[Essentiële ⇐](essentials.md)** | **[Aanpassing aan clientzijde☐](client-customize.md)** |
|---|---|
|  | **[SCF Handlebars Helpers](handlebars-helpers.md)** |

## Java API&#39;s {#java-apis}

>[!NOTE]
>
>De pakketlocatie van de communautaire API&#39;s kan veranderen wanneer u een upgrade uitvoert van de ene grote release naar de volgende.

### Interface van SocialComponent {#socialcomponent-interface}

Sociale componenten zijn POJO&#39;s die een bron voor een AEM Communities-functie vertegenwoordigen. Idealiter vertegenwoordigt elke SocialComponent een specifiek resourceType met blootgestelde GETters die gegevens aan de cliënt verstrekken zodat wordt het middel nauwkeurig vertegenwoordigd. Alle bedrijfslogica en meningslogica wordt ingekapseld in SocialComponent, met inbegrip van de zittingsinformatie van de plaatsbezoeker, indien nodig.

De interface bepaalt een basisreeks GETters die noodzakelijk zijn om een middel te vertegenwoordigen. Belangrijk, bepaalt de interface Kaart&lt;string object=&quot;&quot;> getAsMap() en String toJSONString() methoden die nodig zijn om Handlebars-sjablonen te renderen en GET JSON-eindpunten voor bronnen beschikbaar te maken.

Alle klassen SocialComponent moeten de interface uitvoeren `com.adobe.cq.social.scf.SocialComponent`

### Interface SocialCollectionComponent {#socialcollectioncomponent-interface}

De interface SocialCollectionComponent breidt de interface SocialComponent uit om middelen beter te vertegenwoordigen die inzamelingen van andere middelen zijn.

Alle klassen SocialCollectionComponent moeten de interface com.adobe.cq.social.scf.SocialCollectionComponent uitvoeren

### SocialComponentFactory-interface {#socialcomponentfactory-interface}

Een SocialComponentFactory (factory) registreert een SocialComponent met het framework. De fabriek biedt een manier om het kader te laten weten welke Sociale Componenten beschikbaar zijn voor een bepaald resourceType en hun prioritaire rangschikking&amp;ast; wanneer er meerdere sociale componenten zijn geïdentificeerd.

Een SocialComponentFactory is verantwoordelijk voor het creëren van een geval van geselecteerde SocialComponent die het mogelijk maakt om alle gebiedsdelen te injecteren nodig door SocialComponent van de fabriek gebruikend DI praktijken.

Een SocialComponentFactory is de dienst OSGi en heeft toegang tot andere diensten OSGi die tot SocialComponent door een aannemer kunnen worden overgegaan.

Alle klassen SocialComponentFactory moeten de interface implementeren `com.adobe.cq.social.scf.SocialComponentFactory`

Een implementatie van de methode SocialComponentFactory.getPriority() moet de hoogste waarde retourneren voordat de factory voor het opgegeven resourceType wordt gebruikt, zoals geretourneerd door getResourceType().

### SocialComponentFactoryManager-interface {#socialcomponentfactorymanager-interface}

De SocialComponentFactoryManager (manager) beheert alle sociale componenten die bij het framework zijn geregistreerd en is verantwoordelijk voor het selecteren van de SocialComponentFactory die voor een bepaalde resource (resourceType) moet worden gebruikt. Als geen fabrieken voor een specifieke resourceType worden geregistreerd, zal de manager een fabriek met het meest dichtbijgelegen super type voor de bepaalde middel terugkeren.

Een SocialComponentFactoryManager is de dienst OSGi en heeft toegang tot andere diensten OSGi die tot SocialComponent door een aannemer kunnen worden overgegaan.

Een handgreep van de OSGi-dienst wordt verkregen door een beroep te doen op `com.adobe.cq.social.scf.SocialComponentFactoryManager`

### HTTP API - POST-aanvragen {#http-api-post-requests}

#### PostOperation-klasse {#postoperation-class}

De eindpunten van de HTTP API-POST zijn PostOperation-klassen die worden gedefinieerd door de implementatie van de `SlingPostOperation`interface (pakket `org.apache.sling.servlets.post`).

De `PostOperation`eindpuntimplementatiesets `sling.post.operation`op een waarde waarop de bewerking zal reageren. Alle verzoeken van de POST met een:parameter van de verrichting die aan die waarde wordt geplaatst zullen aan deze implementatieklasse worden gedelegeerd.

De `PostOperation`roept de `SocialOperation`die de voor de bewerking vereiste handelingen uitvoert.

De `PostOperation`ontvangt het resultaat van de `SocialOperation`en retourneert de juiste reactie op de client.

#### Klasse SocialOperation {#socialoperation-class}

Elk `SocialOperation`Het eindpunt breidt de klasse AbstractSocialOperation uit en treedt de methode met voeten `performOperation().`Deze methode voert alle handelingen uit die nodig zijn om de bewerking te voltooien en een `SocialOperationResult`of anders een `OperationException`, in welk geval een HTTP-foutstatus met een bericht wordt geretourneerd, indien beschikbaar, in plaats van de normale JSON-respons of HTTP-successtatuscode.

Uitbreiden `AbstractSocialOperation`de mogelijkheid biedt om `SocialComponents`om JSON-reacties te verzenden.

#### SocialOperationResult, klasse {#socialoperationresult-class}

De `SocialOperationResult`wordt geretourneerd als het resultaat van de `SocialOperation`en bestaat uit een `SocialComponent`, HTTP-statuscode en HTTP-statusbericht.

De `SocialComponent`vertegenwoordigt de bron die door de bewerking is beïnvloed.

Voor een bewerking Maken `SocialComponent`opgenomen in de `SocialOperationResult`vertegenwoordigt het middel enkel gecreeerd en voor een verrichting van de Update, vertegenwoordigt het het middel dat door de verrichting werd veranderd. Nee `SocialComponent`wordt geretourneerd voor een verwijderbewerking.

De gebruikte HTTP-statuscodes voor succesmeldingen zijn:

* 201 voor bewerkingen maken
* 200 voor updatebewerkingen
* 204 voor verwijderingsbewerkingen

#### OperationException, klasse {#operationexception-class}

An `OperationExcepton`kan worden gegenereerd wanneer een bewerking wordt uitgevoerd als de aanvraag ongeldig is of als er zich een andere fout voordoet, zoals interne fouten, onjuiste parameterwaarden, onjuiste machtigingen, enz. An `OperationException`bestaat uit een HTTP-statuscode en een foutbericht die aan de client worden geretourneerd als reactie op de `PostOperatoin`.

#### OperationService-klasse {#operationservice-class}

In het kader van de sociale component wordt aanbevolen dat de bedrijfslogica die verantwoordelijk is voor de uitvoering van de bewerking, niet wordt geïmplementeerd binnen de `SocialOperation`klasse, maar in plaats daarvan gedelegeerd aan de dienst OSGi. Het gebruiken van de dienst OSGi voor bedrijfslogica staat een toe `SocialComponent`, die door een `SocialOperation`eindpunt, dat met andere code moet worden geïntegreerd en verschillende toegepaste bedrijfslogica hebben.

Alles `OperationService`klassen uitbreiden `AbstractOperationService`, waardoor extra extensies kunnen worden toegestaan die kunnen worden gekoppeld aan de uitgevoerde bewerking. Elke verrichting in de dienst wordt vertegenwoordigd door `SocialOperation`klasse. De `OperationExtensions`klasse kan tijdens verrichtingsuitvoering worden aangehaald door de methodes te roepen

* `performBeforeActions()`
Voorcontroles/voorbewerking en validaties zijn toegestaan
* `performAfterActions()`
Staat voor verdere wijziging van middelen toe of het aanhalen van douanegebeurtenissen, werkschema&#39;s, enz.

#### OperationExtension-klasse {#operationextension-class}

`OperationExtension`de klassen zijn douanestukken van code die in een verrichting kunnen worden ingespoten die voor aanpassing van verrichtingen toestaat om aan bedrijfsbehoeften te voldoen. De consumenten van de component kunnen dynamisch en oplopend functionaliteit toevoegen aan de component. Met het extensie-/haakpatroon kunnen ontwikkelaars zich uitsluitend richten op de extensies zelf. Bovendien is het overbodig om volledige bewerkingen en componenten te kopiëren en te overschrijven.

## Voorbeeldcode {#sample-code}

Voorbeeldcode is beschikbaar in het dialoogvenster [Adobe Marketing Cloud GitHub](https://github.com/Adobe-Marketing-Cloud) opslagplaats. Zoeken naar projecten met `aem-communities` of `aem-scf`.

## Best practices voor {#best-practices}

De weergave van [Codeerrichtlijnen](code-guide.md) voor verschillende coderingsrichtlijnen en aanbevolen procedures voor AEM Communities-ontwikkelaars.

Zie ook [Storage Resource Provider (SRP) voor UGC](srp.md) voor meer informatie over het benaderen van door de gebruiker gegenereerde inhoud.

| **[Essentiële ⇐](essentials.md)** | **[Aanpassing aan clientzijde☐](client-customize.md)** |
|---|---|
|  | **[SCF Handlebars Helpers](handlebars-helpers.md)** |
