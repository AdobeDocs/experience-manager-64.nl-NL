---
title: Forms-centric workflow voor OSGi - Step Reference
seo-title: Forms-centric workflow voor OSGi - Step Reference
description: Met een Forms-gerichte workflow voor OSGi-stappen kunt u snel adaptieve formulieren op basis van workflows maken.
seo-description: Met een Forms-gerichte workflow voor OSGi-stappen kunt u snel adaptieve formulieren op basis van workflows maken.
uuid: 57c872d6-c6ca-4f78-a98c-f9487f1d673c
contentOwner: aheimoz
discoiquuid: f2bd4d96-55a5-4fbd-bede-1747c2ec63c8
exl-id: f8e25989-6ed3-4b35-95e5-fbfd7c51d622
translation-type: tm+mt
source-git-commit: bd94d3949f0117aa3e1c9f0e84f7293a5d6b03b4
workflow-type: tm+mt
source-wordcount: '4560'
ht-degree: 0%

---

# Forms-centric workflow op OSGi - Step Reference {#forms-centric-workflow-on-osgi-step-reference}

## Stappen {#forms-workflow-steps} Forms Workflows

Forms-workflowstappen voeren AEM Forms-specifieke bewerkingen uit in een AEM workflow. Met deze stappen kunt u snel adaptieve formulieren maken op basis van Forms-centric workflow voor OSGi. Deze workflows kunnen worden gebruikt voor het ontwikkelen van basis revisie- en goedkeurings-workflows, interne en interne bedrijfsprocessen binnen de firewall. U kunt ook de stappen van de Forms Workflow gebruiken om documentservices te starten, te integreren met de Adobe Sign-handtekeningworkflow en andere AEM Forms-bewerkingen uit te voeren. U hebt [AEM Forms add-on](https://www.adobe.com/go/learn_aemforms_documentation_63) nodig om deze stappen in een workflow te gebruiken.

## Taakstap {#assign-task-step} toewijzen

De taakstap toewijzen maakt een taak en wijst deze toe aan een gebruiker of groep. Naast het toewijzen van de taak geeft de component ook het adaptieve of niet-interactieve PDF-formulier voor de taak op. Het adaptieve formulier is vereist om invoer van gebruikers te accepteren en niet-interactieve PDF of een alleen-lezen adaptief formulier wordt gebruikt voor workflows die alleen voor revisie zijn.

U kunt de component ook gebruiken om het gedrag van de taak te controleren. Bijvoorbeeld, creërend een automatisch document van verslag, toewijzend de taak aan een specifieke gebruiker of een groep, specificerend de weg van de voorgelegde gegevens, specificerend de weg van te vullen gegevens, en specificerend standaardacties. De stap Taak toewijzen heeft de volgende eigenschappen:

* **Titel:** Titel van de taak. De titel wordt weergegeven in AEM Postvak IN.
* **Beschrijving:** Uitleg van de bewerkingen die in de taak worden uitgevoerd. Deze informatie is nuttig voor andere procesontwikkelaars wanneer u in een gedeelde ontwikkelomgeving werkt.

* **Miniatuurpad:** pad van de taakminiatuur. Als er geen pad is opgegeven, wordt voor een aangepaste standaardminiatuur van het formulier weergegeven en voor Document of Record, een standaardpictogram weergegeven.
* **Werkstroomwerkgebied:** een werkstroom kan meerdere fasen hebben. Deze stadia worden getoond in AEM Inbox. U kunt deze fasen definiëren in de eigenschappen van het model (Selecteren > Pagina > Pagina-eigenschappen > Staven).
* **Prioriteit:** Geselecteerde prioriteit wordt getoond in AEM Inbox. De beschikbare opties zijn Hoog, Normaal en Laag. De standaardwaarde is Normaal.
* **Vervaldatum:** Geef het aantal dagen of uren op waarna de taak achterstallig is. Als u **Uit** selecteert, dan is de taak nooit duidelijk achterstallig. U kunt ook een time-outhandler opgeven om specifieke taken uit te voeren nadat de taak is uitgevoerd.

* **Dagen:** het aantal dagen voordat de taak moet worden voltooid. Het aantal dagen wordt geteld nadat de taak aan een gebruiker is toegewezen. Als een taak niet volledig is en het aantal dagen overschrijdt specificeert op het gebied van Dagen, dan, als geselecteerd, wordt een onderbrekingsmanager teweeggebracht na de vervaldatum.
* **Uren:** het aantal uren voordat de taak moet worden voltooid. Het aantal uren wordt geteld nadat de taak aan een gebruiker wordt toegewezen. Als een taak niet volledig is en het aantal uren overschrijdt specificeert op het gebied van Uren, dan, als geselecteerd, wordt een onderbrekingsmanager teweeggebracht na de verschuldigde uren.
* **Vertraging na Vervaldatum:** selecteer deze optie om het selectieveld Tijdelijke handler in te schakelen.
* **Timeout-handler:** selecteer het script dat moet worden uitgevoerd wanneer de taakstap toewijzen de juiste datum overschrijdt. Scripts die in de CRX-opslagplaats op [apps]/fd/dashboard/scripts/timeoutHandler worden geplaatst, zijn beschikbaar voor selectie. Het opgegeven pad bestaat niet in de crx-gegevensopslagruimte. Een beheerder maakt het pad voordat het wordt gebruikt.
* **Markeer de handeling en de opmerking van de laatste taak in Taakdetails:** selecteer deze optie om de laatste actie weer te geven die is uitgevoerd en de opmerking die is ontvangen in de sectie met taakdetails van een taak.
* **Type:** kies het type document dat moet worden ingevuld wanneer de werkstroom wordt gestart. U kunt een adaptief formulier, een alleen-lezen adaptief formulier of een niet-interactief PDF-document kiezen.
* **Adaptief formulier gebruiken:** Geef de methode op waarmee het invoeradaptieve formulier wordt gezocht. U kunt het adaptieve formulier gebruiken dat beschikbaar is op een absoluut pad, wordt verzonden als een payload naar de workflow of beschikbaar is op een pad dat is berekend met een variabele. U kunt een variabele van het type String gebruiken om het pad op te geven.
* **Adaptief formulierpad**: Geef het pad van het adaptieve formulier op. Het veld is beschikbaar wanneer u in het veld Type de optie Aangepast formulier gebruiken of Alleen-lezen gebruikt in combinatie met de optie Absoluut pad in het veld Aangepast formulier gebruiken.
* **PDF-pad:het pad van een niet-interactief PDF-document** opgeven. Het veld is beschikbaar wanneer u een niet-interactief PDF-document kiest in het veld Type. Het pad is altijd relatief ten opzichte van de lading. Bijvoorbeeld [Payload_Directory]/Workflow/PDF/credit-card.pdf. Het pad bestaat niet in crx-repository. Een beheerder maakt het pad voordat het wordt gebruikt. U hebt een optie Document of Record ingeschakeld of op een formuliersjabloon gebaseerde adaptieve formulieren nodig om de optie PDF-pad te kunnen gebruiken.
* **Voor voltooide taak geeft u het adaptieve formulier weer als**: Als een taak is gemarkeerd als voltooid, kunt u het adaptieve formulier weergeven als een alleen-lezen adaptief formulier of als een PDF-document. U hebt een optie Document of Record ingeschakeld of op een formuliersjabloon gebaseerde adaptieve formulieren nodig om het adaptieve formulier weer te geven als Document of Record.
* **Te vullen informatie:** de volgende velden dienen als input voor de taak:

   * **Pad gegevensbestand:** pad van invoergegevensbestand (.json of .xml). Het pad is altijd relatief ten opzichte van de lading. Het bestand bevat bijvoorbeeld de gegevens die via een AEM Inbox-toepassing voor het formulier zijn verzonden. Een voorbeeldpad is [Payload_Directory]/workflow/data.
   * **Bijlagepad:de op de locatie beschikbare** bijlagen zijn gekoppeld aan het formulier dat aan de taak is gekoppeld. Het pad is altijd relatief ten opzichte van de lading. Een voorbeeldpad is [Payload_Directory]/attachments/

* **Verzonden informatie:** De volgende hieronder vermelde gebieden dienen als outputplaatsen aan de taak:

   * **Pad gegevensbestand:** pad van gegevensbestand (.json of .xml). Het gegevensbestand bevat informatie die via het bijbehorende formulier is verzonden. Het pad is altijd relatief ten opzichte van de lading. Bijvoorbeeld [Payload_Directory]/Workflow/data, waarbij de gegevens een bestand zijn.
   * **Pad bijlage:** pad om de formulierbijlagen in een taak op te slaan.
   * **Document van het Pad van het Verslag:** Weg om een Document van het dossier van het Verslag te bewaren. Bijvoorbeeld [Payload_Directory]/DocumentofRecord/credit-card.pdf. Het document of record wordt niet gegenereerd als het padveld leeg blijft. Het pad is altijd relatief ten opzichte van de lading.

* **Wijs opties toe:** specificeer de methode om de taak aan een gebruiker toe te wijzen. U kunt de taak dynamisch toewijzen aan een gebruiker of groep met behulp van het script Deelnemerkiezer of u kunt de taak toewijzen aan een specifieke AEM gebruiker of groep.
* **Deelnemerkiezer:** de optie is beschikbaar wanneer de optie  **Dynamisch naar een gebruiker of** groep is geselecteerd in het veld Opties toewijzen. U kunt een ECMAScript of de dienst gebruiken om een gebruiker of een groep dynamisch te selecteren. Zie [Workflows dynamisch toewijzen aan gebruikers](https://helpx.adobe.com/experience-manager/kb/HowToAssignAWorkflowDynamicallyToParticipants.html) en [Een aangepaste stap Adobe Experience Manager Dynamic Participant maken.](https://helpx.adobe.com/experience-manager/using/dynamic-steps.html)

* **Deelnemers:** het veld is beschikbaar wanneer de  **[!UICONTROL com.adobe.granite.workflow.core.process.RandomParticipantChooser]** optie is geselecteerd in het veld Deelnemerkiezer. In het veld kunt u gebruikers of groepen selecteren voor de optie RandomParticipantChooser.

* **Argumenten:** Het veld is beschikbaar wanneer een ander script dan het script RandomParticipantChoose is geselecteerd in het veld Deelnemerkiezer. In het veld kunt u een lijst met door komma&#39;s gescheiden argumenten opgeven voor het script dat is geselecteerd in het veld Deelnemerkiezer.

* **Gebruiker of Groep:** De taak wordt toegewezen aan geselecteerde gebruiker of groep. De optie is beschikbaar wanneer **Aan een specifieke gebruiker of groepoptie** op het Assign optiesgebied wordt geselecteerd. In het veld worden alle gebruikers en groepen van de groep met workflowgebruikers weergegeven.

* **De geadresseerde per e-mail op de hoogte stellen:** Selecteer deze optie om e-mailberichten naar de ontvanger te verzenden. Deze meldingen worden verzonden wanneer een taak aan een gebruiker wordt toegewezen. Schakel de meldingen van AEM webconsole in voordat u deze optie gebruikt. Zie [E-mailmeldingen configureren voor de taakstap toewijzen voor stapsgewijze instructies.](/help/forms/using/aem-forms-workflow.md)

* **HTML-e-mailsjabloon**: Selecteer een e-mailsjabloon voor het e-mailbericht. Als u een sjabloon wilt bewerken, wijzigt u het bestand op /libs/fd/dashboard/templates/email/htmlEmailTemplate.txt in de crx-repository.
* **Delegatie toestaan aan:** AEM InBox biedt een optie voor de aangemelde gebruiker om de toegewezen workflow te delegeren aan een andere gebruiker. U kunt delegeren binnen dezelfde groep of aan de werkschemagebruiker van een andere groep. Als de taak aan één enkele gebruiker wordt toegewezen en **sta delegatie aan leden van de bestemmingsgroep** optie wordt geselecteerd, dan is het niet mogelijk om de taak aan een andere gebruiker of een groep te delegeren.

* **Standaardhandelingen:** uit het vak, acties Verzenden, Opslaan en Herstellen zijn beschikbaar. Standaard zijn alle standaardhandelingen ingeschakeld.
* **De Variabele van de route:** Naam van de routevariabele. De routevariabele vangt douaneacties die een gebruiker in AEM Inbox selecteert.
* **Routes:** Een taak kan zich aan verschillende routes vertakken. Wanneer geselecteerd in AEM Inbox, keert de route een waarde en de werkschematakken terug die op de geselecteerde route worden gebaseerd.
* **Titel**: Specificeer de titel voor de route. Deze wordt weergegeven in AEM Postvak IN.
* **Koraalpictogram**: Geef het HTML-kenmerk van een koraalpictogram op. De Adobe CorelUI-bibliotheek biedt een uitgebreide set aanraakpictogrammen. U kunt een pictogram voor de route kiezen en gebruiken. Deze wordt samen met de titel in AEM Inbox weergegeven.
* **Toestaan dat de ontvanger commentaar** toevoegt: Selecteer deze optie als u opmerkingen voor de taak wilt inschakelen. Een toegewezen persoon kan de opmerkingen toevoegen vanuit AEM Postvak In op het moment dat de taak wordt verzonden.
* **Toestaan dat de ontvanger een of meer bijlagen aan de taak** toevoegt: Selecteer deze optie om bijlagen in te schakelen voor de taak. Een toegewezen persoon kan de bijlagen toevoegen vanuit AEM Postvak In op het moment dat de taak wordt verzonden.
* **Uitvoerpad van taakbijlagen**: Geef de locatie van de map met bijlagen op. De locatie is relatief ten opzichte van de lading.
* **Aangepaste metagegevens gebruiken:** selecteer deze optie om het veld Aangepaste metagegevens in te schakelen. Aangepaste metagegevens worden gebruikt in e-mailsjablonen.
* **Aangepaste metagegevens:** selecteer aangepaste metagegevens voor de e-mailsjablonen. De aangepaste metagegevens zijn beschikbaar in de crx-gegevensopslagruimte op apps/fd/dashboard/scripts/metadataScripts. Het opgegeven pad bestaat niet in de crx-gegevensopslagruimte. Een beheerder maakt het pad voordat het wordt gebruikt. U kunt ook een service gebruiken voor de aangepaste metagegevens. U kunt de `WorkitemUserMetadataService` interface ook uitbreiden om douanemetagegevens te verstrekken.

* **Gegevens uit vorige stappen** tonen: Schakel deze optie in als u wilt dat toewijzen vorige toewijzingen, reeds uitgevoerde handelingen, aan de taak toegevoegde opmerkingen en het document met de record van de voltooide taak, indien beschikbaar, kunnen weergeven.
* **Gegevens uit volgende stappen tonen:** selecteer deze optie om de huidige ontvanger in staat te stellen de actie te bekijken die is uitgevoerd en de opmerkingen die aan de taak zijn toegevoegd door volgende toewijzingen. Ook kan de huidige toegewezen persoon een document bekijken waarin de voltooide taak is vastgelegd, indien beschikbaar.
* **Zichtbaarheid van gegevenstype:** standaard kan een toegewezen persoon een document met record weergeven, toewijzingen, actie die is uitgevoerd en opmerkingen die door eerdere en volgende toewijzingen zijn toegevoegd. Gebruik de zichtbaarheid van de optie Gegevenstype om het type gegevens te beperken dat zichtbaar is voor de ontvangers.

## E-mailstap {#send-email-step} verzenden

Met de stap E-mail kunt u een e-mail verzenden, bijvoorbeeld een e-mail met een recorddocument, een koppeling van een adaptief formulier, een koppeling van een interactieve communicatie of met een bijgevoegd PDF-document. De stap E-mail verzenden ondersteunt [HTML-e-mail](https://en.wikipedia.org/wiki/HTML_email). HTML-e-mailberichten reageren en passen zich aan de e-mailclient en schermgrootte van de ontvangers aan. U kunt een HTML-e-mailsjabloon gebruiken om de weergave, het kleurenschema en het gedrag van het e-mailadres te definiëren.

In de e-mailstap wordt de Day CQ Mail Service gebruikt om e-mailberichten te verzenden. Controleer voordat u de e-mailstap gebruikt of [e-mailservice](/help/forms/using/aem-forms-workflow.md) is geconfigureerd. De e-mailstap heeft de volgende eigenschappen:

**Titel:** Titel van de stap helpt de stap in de werkstroomeditor te identificeren.

**Beschrijving:** Uitleg is nuttig voor andere procesontwikkelaars wanneer u in een gedeelde ontwikkelomgeving werkt.

**E-mailonderwerp:** Onderwerp kan uit een werkschemameta-gegevens worden teruggewonnen of manueel worden gespecificeerd. Selecteer de optie **Letterlijk** om handmatig een onderwerp op te geven of selecteer de optie **Ophalen uit werkstroommetagegevens** om het onderwerp op te halen uit een eigenschap metadata.

**HTML-e-mailsjabloon**: HTML-sjabloon voor e-mail. U kunt variabelen in een e-mailsjabloon opgeven. De E-mailstap extraheert en geeft alle variabelen weer die in een sjabloon zijn opgenomen voor invoer.

**Metagegevens van e-mailsjabloon: de** waarde van de sjabloonvariabelen van de e-mail kan een door de gebruiker opgegeven waarde zijn, het pad van een element op de auteur of de publicatieserver, afbeelding of metagegevenseigenschap van de workflow.

* **Letterlijk:** gebruik de optie wanneer u precies weet welke waarde u moet opgeven. Bijvoorbeeld [example@example.com](mailto:example@example.com).

* **Werkstroommetagegevens:** gebruik de optie wanneer de te gebruiken waarde wordt opgeslagen in een werkstroommetagegevenseigenschap. Nadat u de optie hebt geselecteerd, typt u de naam van de eigenschap metadata in het lege tekstvak onder de optie Metagegevens werkstroom. Bijvoorbeeld emailAddress.
* **URL van element:** gebruik de optie om een webkoppeling van een interactieve communicatie naar de e-mail in te sluiten. Nadat u de optie hebt geselecteerd, bladert u door de interactieve communicatie die u wilt insluiten en kiest u deze. Het element kan zich op de auteur of de publicatieserver bevinden.
* **Afbeelding:** gebruik de optie om een afbeelding in te sluiten in de e-mail. Blader en kies de afbeelding nadat u de optie hebt geselecteerd. De afbeeldingsoptie is alleen beschikbaar voor de afbeeldingstags (&lt;img src=&quot;&amp;ast;&quot;/>) die beschikbaar zijn in de e-mailsjabloon.

**E-mailadres van afzender/ontvanger:** selecteer de optie  **** Letterlijk om handmatig een e-mailadres op te geven of selecteer de optie  **Ophalen uit** werkstroommetagegevens om het e-mailadres op te halen uit een eigenschap metadata. U kunt ook een lijst met arrays met metagegevenseigenschappen opgeven voor de optie **Ophalen uit metagegevens van workflow**.

**Pad bestandsbijlage:** het element dat op de opgegeven locatie beschikbaar is, is als bijlage bij de e-mail gevoegd. Het pad van het element kan relatief zijn ten opzichte van de payload of het absolute pad. Een voorbeeldpad is [Payload_Directory]/attachments/

**Bestandsnaam:** naam van het bestand met e-mailbijlagen. Met de E-mailstap wijzigt u de oorspronkelijke bestandsnaam van de bijlage in de opgegeven bestandsnaam. De naam kan handmatig worden opgegeven of worden opgehaald uit een eigenschap voor metagegevens van een workflow. Gebruik de optie **Letterlijk** als u de exacte waarde kent die u wilt opgeven. Gebruik de optie **Ophalen uit een werkstroommetagegevens** wanneer de te gebruiken waarde is opgeslagen in een eigenschap voor werkstroommetagegevens.

## Document met recordstap {#generate-document-of-record-step} genereren

Wanneer een formulier wordt ingevuld of verzonden, kunt u het formulier afdrukken of in documentindeling registreren. Dit wordt bedoeld als Document van Verslag (DoR). Met de stap Document van record genereren kunt u een alleen-lezen of interactieve PDF-versie maken van een adaptief formulier. De PDF-versie bevat informatie die in het formulier is ingevuld en de indeling van het adaptieve formulier.

De stap Document of Record heeft de volgende eigenschappen:

**Adaptief formulier** gebruiken: Geef de methode op om het invoeradaptieve formulier te zoeken. U kunt het adaptieve formulier gebruiken dat beschikbaar is op een absoluut pad, wordt verzonden als een payload naar de workflow of beschikbaar is op een pad dat is berekend met een variabele. U kunt een variabele van het type String gebruiken om het pad op te geven.

**Adaptief formulierpad**: Geef het pad van het adaptieve formulier op. Het veld is beschikbaar wanneer u in het veld Type de optie Aangepast formulier gebruiken of Alleen-lezen gebruikt in combinatie met de optie Absoluut pad in het veld Aangepast formulier gebruiken.

**Invoergegevenspad:** Pad van de invoergegevens voor het adaptieve formulier. U kunt de gegevens op een plaats met betrekking tot de lading houden of een absolute weg van de gegevens specificeren. De invoergegevens worden samengevoegd met het aangepaste formulier om een recorddocument te maken.

**Pad invoerbijlage:pad** invoerbijlage: Pad van de bijlagen. Deze bijlagen worden opgenomen in het document of record. U kunt de bijlagen op een locatie ten opzichte van de lading plaatsen of een absoluut pad van de bijlagen opgeven.

Als u bijvoorbeeld het pad van een map opgeeft, worden alle bestanden die rechtstreeks in de map beschikbaar zijn, gekoppeld aan het document met records. Als er bestanden beschikbaar zijn in de mappen die rechtstreeks beschikbaar zijn in het opgegeven pad naar de bijlage, worden de bestanden als bijlagen opgenomen in Document of Record. Als er mappen in direct beschikbare mappen staan, worden deze overgeslagen.

**Gegenereerd document met opnamepad:** geef de locatie op waar u een document met een recordbestand wilt bewaren. U kunt ervoor kiezen om de payload-map te overschrijven of het document met de record op een locatie in de payload-map te plaatsen.

**Landinstelling**: Geef de taal van het recorddocument op.

## Service-stap {#invoke-form-data-model-service-step} voor formuliergegevensmodel aanroepen

Met [AEM Forms Data Integration](/help/forms/using/data-integration.md) kunt u verschillende gegevensbronnen configureren en verbinden. Deze gegevensbronnen kunnen een gegevensbestand, de Webdienst, de dienst van REST, de dienst van OData, en oplossing van CRM zijn. Met AEM Forms Data Integration kunt u een formuliergegevensmodel maken dat verschillende services omvat voor het ophalen, optellen en bijwerken van gegevens in de geconfigureerde database. Met de **Gegevensmodelservice aanroepen** kunt u een formuliergegevensmodel (FDM) selecteren en de services van de FDM gebruiken om gegevens op te halen, bij te werken of toe te voegen aan verschillende gegevensbronnen.

Om input voor gebieden van de stap te verklaren, worden de volgende gegevensbestandlijst en het dossier JSON gebruikt als voorbeeld:

**Voorbeeld van tabel met klantgegevens**

<table> 
 <tbody> 
  <tr> 
   <td>Eigenschap</td> 
   <td>Waarde<br /> </td> 
  </tr> 
  <tr> 
   <td>FirstName<br /> </td> 
   <td>Sarah<br /> </td> 
  </tr> 
  <tr> 
   <td>LastName</td> 
   <td>Roze</td> 
  </tr> 
  <tr> 
   <td>Klant-id</td> 
   <td>1</td> 
  </tr> 
  <tr> 
   <td>E-mailadres<br /> </td> 
   <td>srose@we.info</td> 
  </tr> 
 </tbody> 
</table>

**Voorbeeld-JSON-bestand**

```
{ 
  customer: { 
   firstName: "Sarah", 
   lastName:"Rose", 
   customerId: "1", 
   emailAddress:"srose@we.info" 
 }, 
  insurance: {
   customerId: "1", 
  policyType: "Premium,
  policyNumber: "Premium-521499",
  customerDetails: { 
   firstName: "Sarah",
   lastName: "Rose",
   customerId: "1",
   emailAddress: "srose@we.info" 
  }
 }
}
```

Voor de stap Service van het formuliergegevensmodel aanroepen worden de onderstaande velden weergegeven, waarmee bewerkingen in het formuliergegevensmodel worden vergemakkelijkt:

* **Titel:** Titel van de stap. Het helpt de stap in de werkschemaredacteur identificeren.
* **Beschrijving:** Uitleg nuttig voor andere procesontwikkelaars wanneer u in een gedeelde ontwikkelomgeving werkt.

* **Pad** formuliergegevensmodel: Blader naar een formuliergegevensmodel op de server en selecteer dit.

* **Service**: Lijst met services die worden geleverd door het geselecteerde formuliergegevensmodel.
* **Invoer voor services > Invoergegevens opgeven met letterlijke gegevens, workflowmetagegevens en een JSON-bestand**: Een service kan meerdere argumenten hebben. Selecteer de optie om de waarde van de de dienstargumenten van een werkschemabezit, een voorwerp van JSON te verkrijgen, of ga direct de waarde in het verstrekte tekstvakje in:

   * **Letterlijk:** gebruik de optie wanneer u precies weet welke waarde u moet opgeven. Bijvoorbeeld srose@we.info.
   * **Ophalen uit metagegevens van workflow:** gebruik de optie wanneer de te gebruiken waarde wordt opgeslagen in een eigenschap voor metagegevens van workflow. Bijvoorbeeld emailAddress.
   * **JSON-puntnotatie:** gebruik de optie wanneer de te gebruiken waarde zich in een JSON-bestand bevindt. Bijvoorbeeld, verzekering.customerDetails.emailAddress.De optie JSON-puntnotatie is alleen beschikbaar als de optie Kaart invoervelden van invoer JSON is geselecteerd.
   * **Wijs invoervelden toe vanuit invoer-JSON:** geef het pad van een JSON-bestand op om de invoerwaarde van sommige serviceargumenten op te halen uit het JSON-bestand. Het pad van het JSON-bestand kan relatief zijn ten opzichte van de lading of een absoluut pad.

* **Invoer voor services > Invoergegevens opgeven met behulp van een JSON-bestand:** selecteer de optie om waarden voor alle argumenten op te halen uit een JSON-bestand.
* **JSON-bestandspad** invoeren: Pad van het JSON-bestand met waarden voor alle serviceargumenten. Het pad van het JSON-bestand kan **relatief zijn ten opzichte van de payload** of een **absoluut pad**.

* **JSON-puntnotatie:** laat het veld leeg om alle objecten van het opgegeven JSON-bestand als invoer voor serviceargumenten te gebruiken. Als u een specifiek JSON-object uit het opgegeven JSON-bestand wilt lezen als invoer voor serviceargumenten, geeft u puntnotatie voor het JSON-object op. Als u bijvoorbeeld een JSON-object hebt dat vergelijkbaar is met de JSON-object dat aan het begin van de sectie wordt vermeld, geeft u Insurance.customerDetails op om alle details van een klant als invoer voor de service op te geven.
* **Uitvoer van service > Uitvoerwaarden toewijzen en schrijven naar metagegevens:** selecteer de optie om de uitvoerwaarden op te slaan als eigenschappen van het metagegevensknooppunt voor workflowinstanties in de crx-gegevensopslagruimte. Specificeer de naam van het meta-gegevensbezit en selecteer het overeenkomstige attribuut van de de dienstoutput dat met meta-gegevensbezit moet worden in kaart gebracht, bijvoorbeeld, phone_number dat door de outputdienst met het phone_number bezit van werkschemameta-gegevens is teruggekeerd.
* **Uitvoer van service > Uitvoer opslaan als JSON:** selecteer de optie om de uitvoerwaarden op te slaan in een JSON-bestand.
* **Uitvoer JSON-bestandspad:** Pad om het JSON-uitvoerbestand op te slaan. Het pad van het JSON-uitvoerbestand kan relatief zijn ten opzichte van de payload of een absoluut pad.

## Documentstap {#sign-document-step} ondertekenen

Met de stap Document ondertekenen kunt u Adobe Sign gebruiken om documenten te ondertekenen. De stap Document ondertekenen heeft de volgende eigenschappen:

* **Naam van overeenkomst:** geef de titel van de overeenkomst op. De naam van de overeenkomst wordt onderdeel van het onderwerp en de hoofdtekst van de e-mail die naar de ondertekenaars wordt verzonden.
* **Landinstelling:** geef de taal op voor de opties voor e-mail en verificatie.
* **Adobe Sign Cloud Configuration**: Kies een Adobe Sign Cloud-configuratie. Als u Adobe Sign for AEM Forms niet hebt geconfigureerd, raadpleegt u [Adobe Sign integreren met AEM Forms](/help/forms/using/adobe-sign-integration-adaptive-forms.md).

* **Te ondertekenen document:** u kunt een document kiezen op een locatie die relatief is ten opzichte van de lading, de lading gebruiken als het document of een absoluut pad van het document opgeven.
* **Dagen tot deadline:** Een document wordt opgemaakt als opeisbaar (verstreken deadline) nadat er geen activiteit op de taak is gedurende het aantal dagen dat is opgegeven in de  **dagen tot** aan-deadline. Het aantal dagen wordt geteld nadat het document is toegewezen aan een gebruiker voor ondertekening.

* **E-mailfrequentie herinnering:** U kunt een herinnering per dag of per week per e-mail verzenden. De week wordt geteld vanaf de dag waarop de documentatie aan een gebruiker is toegewezen voor ondertekening.
* **Handtekeningproces:** u kunt ervoor kiezen om een document in een opeenvolgende of parallelle volgorde te ondertekenen. Eén ondertekenaar ontvangt het document op volgorde voor ondertekening. Nadat de eerste ondertekenaar het ondertekenen van het document heeft voltooid, wordt het document verzonden naar de tweede ondertekenaar, enzovoort. Parallel hieraan kunnen meerdere ondertekenaars een document tegelijk ondertekenen.

* **URL omleiden:URL omleiden** opgeven. Nadat het document is ondertekend, kunt u de ontvanger omleiden naar een URL. Gewoonlijk bevat deze URL een bedankbericht of verdere instructies.
* **Werkstroomwerkgebied:** een werkstroom kan meerdere fasen hebben. Deze stadia worden getoond in AEM Inbox. U kunt deze fasen definiëren in de eigenschappen van het model (Selecteren > Pagina > Pagina-eigenschappen > Staven).
* **Selecteer Ondertekenaars:** Geef de methode op waarmee u ondertekenaars voor het document wilt kiezen. U kunt de workflow dynamisch toewijzen aan een gebruiker of groep of gegevens van een ondertekenaar handmatig toevoegen.
* **Script of service om ondertekenaars te selecteren:** de optie is alleen beschikbaar als de optie Dynamisch is geselecteerd in het veld Ondertekenaars selecteren. U kunt een ECMAScript of een dienst specificeren om ondertekenaars en verificatieopties voor een document te kiezen.

* **Details ondertekenaar:** de optie is alleen beschikbaar als de optie Handmatig is geselecteerd in het veld Ondertekenaars selecteren. Geef een e-mailadres op en kies een optioneel verificatiemechanisme. Voordat u een verificatiemechanisme met twee stappen selecteert, moet u controleren of de bijbehorende verificatieoptie is ingeschakeld voor de geconfigureerde Adobe Sign-account.
* **Statusvariabele:** Een door Adobe Sign ingeschakeld document slaat de ondertekeningsstatus van het document op in een variabele. Geef de naam van de statusvariabele op (adobeSignStatus). Een statusvariabele van een instantie is beschikbaar in CRXDE op /etc/workflow/instances/&lt;server>/&lt;date-time>/&lt;instance of workflow model>/workItems/&lt;node>/metaData bevat status van een variabele.
* **Ondertekend documentpad:** geef de locatie op waar u ondertekende documenten wilt behouden. U kunt ervoor kiezen het ladingsdossier te overschrijven of het ondertekende document bij een plaats binnen de ladingsfolder te plaatsen.

## Stappen voor Document Services {#document-services-steps}

AEM Document Services is een set services voor het maken, samenstellen en beveiligen van PDF-documenten. AEM Forms biedt een aparte stap voor AEM workflow voor elke documentservice:

### Tijdstempel document toepassen {#apply-document-time-stamp-step}

Tijdstempel toevoegen aan een document. U geeft documentgegevens op, zoals het pad van het invoerdocument, de naam van het invoerdocument en de locatie waar de geëxporteerde gegevens moeten worden opgeslagen. U kunt desgewenst het bestaande ladingsbestand overschrijven of een andere bestandsnaam kiezen om gegevens in een ander bestand op te slaan onder de ladingsmap.

### Omzetten in afbeeldingsstap {#convert-to-image-step}

Hiermee converteert u een PDF-document naar een afbeeldingsbestand. Ondersteunde afbeeldingsindelingen zijn JPEG, JPEG2000, PNG en TIFF. De volgende informatie is van toepassing op conversies naar TIFF-afbeeldingen:

* Er wordt een TIFF-bestand met meerdere pagina&#39;s gegenereerd.
* Niet alle annotaties zijn opgenomen in TIFF-afbeeldingen. Annotaties waarvoor Acrobat de weergave moet genereren, worden niet opgenomen.

### Converteren naar PDF/A-stap {#convert-to-pdf-a-step}

Hiermee wordt een PDF-document naar PDF/A-indeling geconverteerd met de beschikbare opties. De PDF/A-versie van Portable Document Format (PDF) is gespecialiseerd in het archiveren en het op lange termijn bewaren van documenten.

### Omzetten in PS-stap {#convert-to-ps-step}

Converteer PDF-documenten naar PostScript. Bij het converteren naar PostScript kunt u het brondocument met de conversiebewerking opgeven en of het document moet worden omgezet in PostScript-niveau 2 of 3. Het PDF-document dat u naar een PostScript-bestand converteert, moet niet-interactief zijn.

### PDF maken van opgegeven tekststap {#create-pdf-from-specified-type-step}

Genereer een PDF-document op basis van een invoerbestand. Het invoerdocument kan relatief zijn ten opzichte van de lading, een absoluut pad hebben of zelf worden geladen.

### PDF maken van URL/HTML/ZIP-stap {#create-pdf-from-url-html-zip-step}

Hiermee genereert u een PDF-document op basis van de opgegeven URL-, HTML- en ZIP-bestanden.

### Gegevensstap exporteren {#export-data-step}

Hiermee exporteert u gegevens uit een PDF forms- of XDP-bestand. Hiervoor moet u het bestandspad van Invoerdocument en de indeling Gegevens exporteren invoeren. De opties voor de Indeling van de Gegevens van de Uitvoer zijn Auto, XDP en XmlData.

### Export PDF naar opgegeven tekststap {#export-pdf-to-specified-type-step}

Hiermee converteert u een PDF-document naar een geselecteerde indeling.

### Niet-interactieve PDF-stap {#generate-non-interactive-pdf-step} genereren

Een niet-interactieve PDF genereren. Het biedt verschillende aanpassingsopties.

### Gegevensstap {#import-data-step} importeren

Hiermee voegt u formuliergegevens samen tot een PDF-formulier. U kunt formuliergegevens importeren in een PDF-formulier.

### DDX-stap {#invoke-ddx-step} aanroepen

Hiermee wordt het DDX-bestand uitgevoerd op de opgegeven kaart met invoerdocumenten en worden de gemanipuleerde PDF-documenten geretourneerd.

### Optimize PDF stap {#optimize-pdf-step}

Hiermee optimaliseert u PDF-bestanden door de grootte ervan te verkleinen. Het resultaat van deze conversie zijn PDF-bestanden die mogelijk kleiner zijn dan de oorspronkelijke versie. Met deze bewerking worden PDF-documenten ook geconverteerd naar de PDF-versie die is opgegeven in de optimalisatieparameters.

Optimalisatie-instellingen bepalen hoe bestanden worden geoptimaliseerd. Hier volgen voorbeelden van instellingen:

* Doelversie PDF
* Objecten zoals JavaScript-handelingen en ingesloten paginaminiaturen negeren
* Gebruikersgegevens zoals opmerkingen en bestandsbijlagen negeren
* Ongeldige of ongebruikte instellingen negeren
* Niet-gecomprimeerde gegevens comprimeren of efficiëntere compressiealgoritmen gebruiken
* Ingesloten lettertypen verwijderen
* Transparantiewaarden instellen

### PDF-formulierstap {#render-pdf-form-step} renderen

Hiermee maakt u een formulier dat is gemaakt in Form Designer (XDP), naar een PDF-formulier.

### Stap {#secure-document-step} voor beveiligd document

Een document versleutelen, ondertekenen en certificeren. AEM Forms ondersteunt zowel op wachtwoorden gebaseerde versleuteling als versleuteling op basis van certificaten. U kunt ook kiezen uit verschillende algoritmen voor het ondertekenen van documenten. Bijvoorbeeld SHA-256 en SH-512. U kunt de workflowstap ook gebruiken om PDF-documenten door te lezen. De workflowstap biedt opties voor het decoderen van streepjescodes, digitale handtekeningen, het importeren en exporteren van PDF-gegevens en andere opties.

### Verzenden naar printerstap {#send-to-printer-step}

Een document rechtstreeks naar een printer verzenden. De volgende toegangsmechanismen voor afdrukken worden ondersteund:

* **Direct toegankelijke printer**: Een printer die op dezelfde computer is geïnstalleerd, wordt een direct toegankelijke printer genoemd en de computer krijgt de naam van de printerhost. Dit type printer kan een lokale printer zijn die rechtstreeks op de computer is aangesloten.
* **Indirecte toegankelijke printer**: De printer die op een afdrukserver is geïnstalleerd, is toegankelijk vanaf andere computers. Technologieën zoals het algemene UNIX®-afdruksysteem (CUPS) en het Line Printer Daemon-protocol (LPD) zijn beschikbaar voor verbinding met een netwerkprinter. Als u toegang wilt tot een indirecte toegankelijke printer, geeft u de IP of hostnaam van de afdrukserver op. Met behulp van dit mechanisme kunt u een document naar een LPD URI verzenden wanneer het netwerk een LPD loopt. Met het mechanisme kunt u het document doorsturen naar elke printer die is aangesloten op het netwerk waarop een LPD-scherm wordt uitgevoerd.
