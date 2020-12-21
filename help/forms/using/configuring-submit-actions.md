---
title: De handeling Verzenden configureren
seo-title: De handeling Verzenden configureren
description: Met AEM Forms kunt u een verzendactie configureren om te definiëren hoe een adaptief formulier na verzending wordt verwerkt. U kunt ingebouwde verzendacties gebruiken of zelf schrijven.
seo-description: Met AEM Forms kunt u een verzendactie configureren om te definiëren hoe een adaptief formulier na verzending wordt verwerkt. U kunt ingebouwde verzendacties gebruiken of zelf schrijven.
uuid: aa261e65-a1ec-402b-80de-0ba8a294e315
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: author
discoiquuid: fea76f90-22d5-4836-9901-a35229401eb0
translation-type: tm+mt
source-git-commit: 35532245929f2e404a96425e4710e911e9ce5b40
workflow-type: tm+mt
source-wordcount: '1503'
ht-degree: 0%

---


# De handeling Verzenden configureren {#configuring-the-submit-action}

## Inleiding om acties {#introduction-to-submit-actions} te verzenden

Een verzendactie wordt geactiveerd wanneer een gebruiker op de knop Verzenden klikt op een adaptief formulier. U kunt de verzendactie configureren op het aangepaste formulier. Adaptieve formulieren bevatten een paar elementen uit het vak Acties verzenden. U kunt de standaardverzendacties kopiëren en uitbreiden om uw eigen verzendactie te maken. Op basis van uw vereisten kunt u echter uw eigen verzendactie schrijven en registreren om gegevens in het verzonden formulier te verwerken.

Wanneer een formulier vooraf wordt ingevuld of verzonden, worden de verzonden gegevens naar AEM gerouteerd voor gegevensmassaging naar tussenliggende indelingen. Gegevens worden niet opgeslagen op een AEM-exemplaar, behalve wanneer het adaptieve formulier gebruikmaakt van Adobe Sign, verify, Forms Portal Concept of submit, of AEM Workflows

U kunt een verzendactie configureren in de sectie **[!UICONTROL Submission]** van de eigenschappen van de container van adaptieve formulieren, in de zijbalk.

![Configureer Verzenden ](assets/thank-you-setting.png)
**ActionFiguur:Handeling Verzenden** *configureren*

De standaardverzendacties die beschikbaar zijn in aangepaste formulieren zijn:

* Verzenden naar REST-eindpunt
* E-mail verzenden
* PDF verzenden via e-mail
* Een Forms Workflow aanroepen
* Verzenden met gebruik van formuliergegevensmodel
* Forms Portal-verzendactie
* Een AEM-workflow aanroepen

>[!NOTE]
>
>PDF verzenden via e-mail verzenden is alleen van toepassing op adaptieve formulieren die XFA-sjabloon gebruiken als formuliermodel.

>[!NOTE]
>
>Zorg ervoor dat [AEM_Installation_Directory]\crx-quickstart\temp\datamanager\ASM folder exists. De map is vereist om bijlagen tijdelijk op te slaan. Als de map niet bestaat, maakt u deze.

>[!CAUTION]
>
>Als u [een formuliersjabloon, formuliergegevensmodel of op schema gebaseerd adaptief formulier met XML- of JSON-gegevensklacht vooraf invult in een schema (XML-schema, JSON-schema, formuliersjabloon of formuliergegevensmodel) dat geen &lt;afData>-, &lt;afBoundData>- en &lt;/afUnboundData>-tags bevat, dan de gegevens van niet-omsloten velden (Niet-omsloten) Gemengde velden zijn adaptieve formuliervelden zonder [bindref](/help/forms/using/prepopulate-adaptive-form-fields.md) eigenschap) van het adaptieve formulier dat verloren gaat.](/help/forms/using/prepopulate-adaptive-form-fields.md)

U kunt een aangepaste verzendactie schrijven voor aangepaste formulieren om aan uw gebruiksscenario te voldoen. Zie [Aangepaste handeling Verzenden schrijven voor adaptieve formulieren](/help/forms/using/custom-submit-action-form.md) voor meer informatie.

## Verzenden naar REST-eindpunt {#submit-to-rest-endpoint}

Met de verzendoptie **[!UICONTROL Submit to REST endpoint]** worden de gegevens die in het formulier zijn ingevuld, doorgegeven aan een geconfigureerde bevestigingspagina als onderdeel van de HTTP-aanvraag. U kunt de naam toevoegen van de velden die u wilt aanvragen. De indeling van het verzoek is:

`{fieldName}={request parameter name}`

Zoals in de onderstaande afbeelding wordt getoond, worden `param1` en `param2` doorgegeven als parameters met waarden die uit de velden **[!UICONTROL textbox]** en **[!UICONTROL numericbox]** voor de volgende actie worden gekopieerd.

U kunt ook **[!UICONTROL Enable POST request]** opgeven en een URL opgeven om het verzoek te posten. Als u gegevens wilt verzenden naar de AEM server waarop het formulier zich bevindt, gebruikt u een relatief pad dat overeenkomt met het hoofdpad van de AEM server. Bijvoorbeeld /content/forms/af/SampleForm.html. Gebruik absoluut pad om gegevens naar een andere server te verzenden.

![Rest Endpoint-verzendhandeling configureren](assets/action-config.png)

Rest Endpoint-verzendhandeling configureren

>[!NOTE]
Als u de velden als parameters in een REST-URL wilt doorgeven, moeten alle velden verschillende elementnamen hebben, zelfs als de velden op verschillende deelvensters zijn geplaatst.

### Gegevens naar een bron of een extern eindpunt voor de rusttijd verzenden  {#post-submitted-data-to-a-resource-or-external-rest-end-point-nbsp}

Met de handeling **[!UICONTROL Submit to REST Endpoint]** kunt u de verzonden gegevens op een rest-URL plaatsen. De URL kan van een interne (de server waarop het formulier wordt gegenereerd) of van een externe server zijn.

Om gegevens aan een interne server te posten, verstrek weg van het middel. De gegevens worden gepost de weg van het middel. Bijvoorbeeld /content/restEndPoint. Voor dergelijke postverzoeken wordt de authenticatieinformatie van het verzendverzoek gebruikt.

Geef een URL op om gegevens naar een externe server te posten. De indeling van de URL is https:// host:port/path_to_rest_end_point. Zorg ervoor dat u de weg vormt om het verzoek van de POST anoniem te behandelen.

![Toewijzing voor veldwaarden die zijn doorgegeven als parameters voor de pagina Bedankt](assets/post-enabled-actionconfig.png)

In het bovenstaande voorbeeld wordt door de gebruiker ingevoerde informatie in `textbox` vastgelegd met parameter `param1`. De syntaxis voor het posten van gegevens die zijn vastgelegd met `param1` is:

`String data=request.getParameter("param1");`

De parameters die u gebruikt voor het posten van XML-gegevens en -bijlagen zijn `dataXml` en `attachments`.

U gebruikt deze twee parameters in uw script bijvoorbeeld om gegevens te parseren op een eindpunt in de rest. U gebruikt de volgende syntaxis om de gegevens op te slaan en te ontleden:

`String data=request.getParameter("dataXml");`\
`String att=request.getParameter("attachments");`

In dit voorbeeld slaat `data` de XML-gegevens op en `att` slaat bijlagegegevens op.

## E-mail {#send-email} verzenden

Met de verzendactie **[!UICONTROL Send Email]** wordt een e-mail naar een of meer ontvangers verzonden wanneer het formulier met succes is verzonden. Het gegenereerde e-mailbericht kan formuliergegevens in een vooraf gedefinieerde indeling bevatten.

>[!NOTE]
Alle formuliervelden moeten verschillende elementnamen hebben, zelfs als ze op verschillende deelvensters zijn geplaatst), om formuliergegevens op te nemen in een e-mailbericht.

## PDF verzenden via e-mail {#send-pdf-via-email}

Met de handeling **[!UICONTROL Send PDF via Email]** wordt een e-mail met een PDF met formuliergegevens verzonden naar een of meer ontvangers wanneer het formulier met succes is verzonden.

**Opmerking:** *Deze verzendactie is beschikbaar voor op XFA gebaseerde adaptieve formulieren en op XSD gebaseerde aanpassingsformulieren die beschikken over de sjabloon Document of Record.*

## Een formulierwerkstroom aanroepen {#invoke-a-forms-workflow}

Met de verzendoptie **[!UICONTROL Submit to Forms workflow]** worden een gegevens-xml en bestandsbijlagen (indien aanwezig) naar een bestaande Adobe-LiveCycle of AEM Forms verzonden bij een JEE-proces.

Zie [Formulierwerkstromen verzenden en de formuliergegevens verwerken met werkstromen](/help/forms/using/submit-form-data-livecycle-process.md) voor informatie over het configureren van de verzendactie Verzenden naar formulieren.

## Verzenden met gebruik van formuliergegevensmodel {#submit-using-form-data-model}

Met de handeling **[!UICONTROL Submit using Form Data Model]** submit worden verzonden adaptieve formuliergegevens voor het opgegeven gegevensmodelobject in een formuliergegevensmodel naar de gegevensbron. Wanneer het vormen van voorlegt actie, kunt u een voorwerp van het gegevensmodel kiezen waarvan voorgelegde gegevens u terug naar zijn gegevensbron wilt schrijven.

Daarnaast kunt u een formulierbijlage verzenden met behulp van een formuliergegevensmodel en een Document of Record (DoR) naar de gegevensbron.

Zie [AEM Forms Data Integration](/help/forms/using/data-integration.md) voor informatie over het formuliergegevensmodel.

## Forms Portal verzendt handeling {#forms-portal-submit-action}

Met de optie **[!UICONTROL Forms Portal Submit Action]** worden formuliergegevens beschikbaar via een AEM Forms-portal.

Zie [Concepten en verzendingscomponent](/help/forms/using/draft-submission-component.md) voor meer informatie over de Forms Portal en de verzendactie.

## Een AEM-workflow {#invoke-an-aem-workflow} aanroepen

Met de verzendactie **[!UICONTROL Invoke an AEM Workflow]** wordt een adaptief formulier gekoppeld aan een AEM workflow. Wanneer een formulier wordt verzonden, wordt de bijbehorende workflow automatisch gestart op het verwerkingsknooppunt. Bovendien worden het gegevensbestand, de bijlagen, en het document van Verslag, indien van toepassing, bij de ladingsplaats van het werkschema geplaatst.

Voordat u de verzendhandeling **[!UICONTROL Invoke an AEM Workflow]** gebruikt, [configureert u de AEM DS-instellingen](/help/forms/using/configuring-the-processing-server-url-.md). Voor informatie over het creëren van een AEMWerkschema, zie [Formulier-centric werkschema&#39;s op OSGi](/help/forms/using/aem-forms-workflow.md).

## Revalidatie op de server in adaptieve vorm {#server-side-revalidation-in-adaptive-form}

In een systeem voor het vastleggen van online gegevens plaatsen ontwikkelaars gewoonlijk bepaalde JavaScript-validaties op de client om een aantal bedrijfsregels af te dwingen. Maar in moderne browsers, moeten de eindgebruikers die bevestigingen omzeilen en manueel bijdragen gebruikend diverse technieken, zoals Browser van het Web DevTools Console indienen. Dergelijke technieken gelden ook voor adaptieve formulieren. Een formulierontwikkelaar kan verschillende validatielogboeken maken, maar technisch kunnen eindgebruikers die validatielogboeken omzeilen en ongeldige gegevens naar de server verzenden. Ongeldige gegevens zouden de bedrijfsregels overtreden die een auteur van formulieren heeft afgedwongen.

Met de functie voor opnieuw valideren aan de serverzijde kunt u ook de validaties uitvoeren die door de auteur van een adaptief formulier zijn verstrekt tijdens het ontwerpen van een adaptief formulier op de server. Hierdoor wordt voorkomen dat bij het verzenden van gegevens en bij het valideren van formulieren inbreuk wordt gemaakt op de bedrijfsregels.

### Wat moet u op de server valideren? {#what-to-validate-on-server-br}

Alle OOTB-veldvalidaties (out-of-box) van een adaptief formulier die opnieuw op de server worden uitgevoerd, zijn:

* Vereist
* Clausule voor validatie
* Validatie-expressie

### Servervalidatie {#enabling-server-side-validation-br} inschakelen

Gebruik **Revalidate op server** onder Adaptieve formuliercontainer in de zijbalk om validatie op de server in of uit te schakelen voor het huidige formulier.

![Server-Side ](assets/revalidate-on-server.png)
**validatie inschakelenFiguur:Validatie** *op de server inschakelen*

Als de eindgebruiker deze validaties overslaat en de formulieren verzendt, wordt de validatie opnieuw uitgevoerd door de server. Als de validatie op het servereinde mislukt, wordt de verzendtransactie gestopt. De eindgebruiker krijgt het oorspronkelijke formulier opnieuw te zien. De vastgelegde gegevens en verzonden gegevens worden als een fout aan de gebruiker gepresenteerd.

### Aangepaste functies ondersteunen in validatie-expressies {#supporting-custom-functions-in-validation-expressions-br}

In het geval van **complexe validatieregels** bevindt het exacte validatiescript zich soms in aangepaste functies en de auteur roept deze aangepaste functies aan vanuit de expressie voor veldvalidatie. Om deze aangepaste functiebibliotheek bekend te maken en beschikbaar te maken tijdens het uitvoeren van servervalidaties, kan de auteur van het formulier de naam van AEM clientbibliotheek configureren onder het tabblad **[!UICONTROL Basic]** van Adaptief formuliercontainereigenschappen, zoals hieronder wordt weergegeven.

![Aangepaste functies ondersteunen in Validatie ](assets/clientlib-cat.png)
**ExpressionsFigure:Aangepaste functies** *ondersteunen in Validatie-expressies*

Auteurs kunnen aangepaste javascript-bibliotheek configureren per adaptief formulier. Houd in de bibliotheek alleen de herbruikbare functies die afhankelijk zijn van bibliotheken van derden jquery en underscore.js.

## Foutafhandeling bij verzendactie {#error-handling-on-submit-action}

Als deel van AEM veiligheid en het verharden richtlijnen, vorm de pagina&#39;s van de douanefout zoals 404.jsp en 500.jsp. Deze handlers worden aangeroepen wanneer een formulier 404- of 500-fouten worden verzonden. De handlers worden ook geroepen wanneer deze foutencodes op de Publish knoop worden teweeggebracht.

Zie [Pagina&#39;s aanpassen die worden weergegeven door de fouthandler](/help/sites-developing/customizing-errorhandler-pages.md) voor meer informatie.
