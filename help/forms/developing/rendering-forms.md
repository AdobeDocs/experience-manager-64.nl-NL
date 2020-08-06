---
title: Forms renderen
seo-title: Forms renderen
description: 'null'
seo-description: 'null'
uuid: 68d7b7bc-7730-4a83-b7b9-ebe2a29d6c51
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/performing_service_operations_using_apis
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: operations
discoiquuid: f8749793-e53f-4812-a093-8278f480e6a8
translation-type: tm+mt
source-git-commit: d0bb877bb6a502ad0131e4f1a7e399caa474a7c9
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 0%

---


# Forms renderen {#rendering-forms}

**Informatie over de Forms-service**

Met de Forms-service kunt u interactieve toepassingen voor het vastleggen van gegevens maken die formulieren valideren, verwerken, transformeren en leveren die normaal gesproken in Designer zijn gemaakt. Formulierauteurs kunnen één formulierontwerp ontwikkelen dat de Forms-service in verschillende browseromgevingen weergeeft in PDF, SWF of HTML.

Wanneer een eindgebruiker een formulier aanvraagt, stuurt een clienttoepassing de aanvraag naar de Forms-service, die het formulier in de juiste indeling retourneert. Zodra de Forms-service een aanvraag ontvangt, worden gegevens met een formulierontwerp samengevoegd en wordt het formulier in de gewenste indeling geleverd. De uitvoer van de formulierservice is een interactief formulier, meestal een PDF-document. Met een interactief formulier kunnen gebruikers de velden op het formulier invullen.

Afhankelijk van het type clienttoepassing kunt u het formulier naar een clientwebbrowser schrijven of het formulier opslaan als een PDF-bestand. Een webtoepassing kan het formulier naar een webbrowser schrijven. Een bureaubladtoepassing kan het formulier opslaan als een PDF-bestand. Als u wilt zien hoe u wegschrijft naar een webbrowser en een PDF-bestand, wordt de snelstarthandleiding in de sectie Forms ** renderen op de volgende manier geordend:

* De sterk getypte Java API-voorbeelden (SOAP-modus) zijn een Java-servlet.
* De voorbeelden van de webservice (Java Base64) zijn een Java-servlet.
* De voorbeelden van de Webdienst (MTOM) zijn een consoletoepassing (niet alle snelle begin hebben een voorbeeld MTOM).

   >[!NOTE]
   >
   >Voor informatie over het creëren van een Webtoepassing die Java servlets gebruikt om de dienst van Forms aan te halen, zie het [Creëren van de Toepassingen van het Web die Forms](/help/forms/developing/creating-web-applications-renders-forms.md)teruggeven.

   U kunt op twee manieren een formulierontwerp (een XDP-bestand) of een PDF-document doorgeven aan de Forms-service:

* U kunt naar het formulierontwerp verwijzen met een URL-waarde. Bij deze methode wordt een `URLSpec` object gebruikt. De inhoudsbasis wordt aan de Forms-service doorgegeven met de `URLSpec` methode van het `setContentRootURI` object. De naam van het formulierontwerp ( `formQuery`) wordt doorgegeven als een aparte parameter. De twee waarden worden samengevoegd om de absolute verwijzing naar het formulierontwerp te verkrijgen. (De meeste snelstarthandleidingen in de sectie *Rendering Forms* gebruiken deze aanpak.)
* U kunt een formulier met het formulierontwerp doorgeven aan de Forms-service. `com.adobe.idp.Document` Twee nieuwe methoden noemen `renderPDFForm2` en `renderHTMLForm2` accepteren een `com.adobe.idp.Document` object dat een formulierontwerp bevat. (Zie Documenten [doorgeven aan de Forms-service](/help/forms/developing/passing-documents-forms-service.md)

U kunt deze taken uitvoeren met de Forms-service:

* Interactieve PDF forms renderen. (Zie Interactieve PDF forms [renderen](/help/forms/developing/rendering-interactive-pdf-forms.md).)
* Formulieren weergeven op de client. (Zie Forms [renderen op de client](/help/forms/developing/rendering-forms-client.md).)
* Formulieren weergeven op basis van fragmenten. (Zie Forms [renderen op basis van fragmenten](/help/forms/developing/rendering-forms-based-fragments.md).)
* Formulieren met rechten weergeven. (Zie Forms [met](/help/forms/developing/rendering-rights-enabled-forms.md)renderrechten.)
* Formulieren weergeven als HTML. (Zie Forms [renderen als HTML](/help/forms/developing/rendering-forms-html.md).)
* HTML Forms renderen met aangepaste CSS-bestanden (HTML Forms[renderen met aangepaste CSS-bestanden](/help/forms/developing/rendering-html-forms-using-custom.md).)
* Ingevulde formulieren verwerken. (Zie Verzendde Forms [](/help/forms/developing/handling-submitted-forms.md)verwerken.)
* PDF-documenten maken met verzonden XML-gegevens. (Zie PDF-documenten [maken met verzonden XML-gegevens](/help/forms/developing/creating-pdf-documents-submitted-xml.md).)
* Formulieren vooraf invullen. (Zie Forms [vooraf vullen met stroombare indelingen](/help/forms/developing/prepopulating-forms-flowable-layouts.md).)
* Documenten doorgeven. (Zie Documenten [doorgeven aan de Forms-service](/help/forms/developing/passing-documents-forms-service.md)
* Formuliergegevens berekenen. (Zie Formuliergegevens [berekenen](/help/forms/developing/calculating-form-data.md).)
* Optimaliseer een toepassing. (Zie De prestaties van de Forms-service [optimaliseren](/help/forms/developing/optimizing-performance-forms-service.md).)

   ***Tip **: De website van de Ontwikkelaar van Adobe bevat het volgende artikel dat bespreekt hoe te om een toepassing tot stand te brengen ASP.NET die de dienst van Forms aanhaalt en vormen teruggeeft. Zie[Formulier genereren ASP.NET-toepassingen](https://www.adobe.com/devnet/livecycle/articles/asp_net.html)maken.*

