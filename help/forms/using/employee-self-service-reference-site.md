---
title: Werknemerslijst voor zelfbedieningsverwijzingssite
seo-title: Zelfbediening door werknemer
description: Op de AEM Forms-referentiesite wordt uitgelegd hoe organisaties AEM Forms-functies kunnen gebruiken om wervingsprocessen voor werknemers en zelfbedieningsworkflows te implementeren.
seo-description: Op de AEM Forms-referentiesite wordt uitgelegd hoe organisaties AEM Forms-functies kunnen gebruiken om wervingsprocessen voor werknemers en zelfbedieningsworkflows te implementeren.
uuid: ecc98e0d-c964-44dc-b219-9ebe92632d22
topic-tags: introduction
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: d2695f71-5126-477c-ae6b-a964fb55728b
translation-type: tm+mt
source-git-commit: 8cbfa421443e62c0483756e9d5812bc987a9f91d
workflow-type: tm+mt
source-wordcount: '1626'
ht-degree: 0%

---


# Zelfbedieningsverwijzingssite voor werknemers doorloopt {#employee-self-service-reference-site-walkthrough}

## Vereiste {#prerequisite}

Stel de referentiesites in zoals beschreven in [AEM Forms-referentiesites instellen en configureren](/help/forms/using/setup-reference-sites.md).

## Overzicht {#overview}

De zelfdienstsystemen van de werknemer, over het algemeen ontvangen op het Intranet van het bedrijf, geven werknemers toegang tot een gastheer van informatie en de diensten die zij van hun bureaus kunnen genieten. Het geeft de werknemers de bevoegdheid en volledige controle om acties uit te voeren zoals toegang tot hun werkgelegenheidsdetails, het aanvragen van verlof, en het voorleggen van uitgavenverslagen. Anderzijds helpt het organisaties de efficiëntie van processen te verbeteren en de kosten te verlagen, terwijl werknemers op de hoogte worden gehouden en betrokken worden.

De de verwijzingsplaats van de zelfbediening van de werknemer toont hoe u hefboomwerking AEM Forms kunt hefboomwerking om werknemerszelf-dienstsysteem in uw organisatie uit te voeren.

>[!NOTE]
>
>De zelfbedieningstoepassingen van de werknemer zijn beschikbaar in zowel Wij.Finance als wij.Gov verwijzingsplaatsen. De voorbeelden, de beelden, en de beschrijvingen die in de analyses worden gebruikt gebruiken Web.Finance verwijzingsplaats. U kunt deze gebruiksgevallen echter ook uitvoeren en artefacten controleren met Web.Gov. Om dit te doen, moet u **wij-financiert** met **wij-gov** in bovengenoemde URLs vervangen.

## Belangenconflict Doorlichting {#conflict-of-interest-questionnaire-walkthrough}

Organisaties vragen hun werknemers van tijd tot tijd om een vragenlijst over belangenconflicten in te dienen en identificeren externe activiteiten of persoonlijke relaties van hun werknemers die mogelijk in strijd zijn met hun organisatie.

De afdeling Naleving van Sarah&#39;s organisatie heeft werknemers gevraagd de vragenlijst over belangenconflicten in te dienen.

### Sarah stuurt de vragenlijst over belangenconflicten {#sarah-submits-the-conflict-of-interest-questionnaire}

Sarah gaat naar het portaal van haar organisatie, logt binnen, en klikt Werknemer om tot het werknemersdashboard toegang te hebben. Ze vindt een vragenlijst over belangenconflicten op het dashboard voor werknemers en klikt op **[!UICONTROL Apply]**.

![we-finance-](assets/we-finance-home.png)
**homeFigure:** *Organisatie-portal*

![employee-](assets/employee-dashboard.png)
**dashboardFigure:** *Werknemerdashboard*

Sarah navigeert het formulier met de knop Volgende en leest door de secties Introductie en Definitie. Ze beantwoordt de vragen in de sectie Vragen. Tot slot ondertekent zij de vragenlijst en legt zij deze voor.

Het organisatieportaal en de vragenlijst zijn responsief en mobiel. In de volgende workflow ziet u hoe Sarah door de vragenlijst navigeert en deze verzendt op haar mobiele apparaat.

![conflict-form-on-mobile](assets/conflict-form-on-mobile.png)

**Hoe werkt het**

Het organisatieportaal en het werknemersdashboard zijn AEM Sites-pagina&#39;s. Het dashboard bevat verschillende opties voor zelfbediening, zoals de vragenlijst voor belangenconflicten. De knop Toepassen is gekoppeld aan een adaptief formulier.

Het aangepaste formulier gebruikt regels voor het weergeven en verbergen van informatie op basis van het antwoord op het tabblad Vragen. Bovendien gebruikt het formulier de component Krabbelen voor ondertekening op het tabblad Declaratie. Controleer het adaptieve formulier op `https://[authorHost]:[authorPort]/editor.html/content/forms/af/we-finance/employee/self-service/conflict-of-interest.html`.

**Zie het zelf**

Ga naar `https://[publishHost]:[publishPort]/content/we-finance/global/en/self-service-forms.html` en meld u aan met `srose/srose` als gebruikersnaam/wachtwoord voor Sarah. Klik **[!UICONTROL Employee]** om tot het dashboard toegang te hebben en dan **[!UICONTROL Apply]** op de vragenlijst van het Conflict van Belang te klikken. Onderzoek de vragenlijst en dien deze in.

### Gloria herziet en keurt de indiening van de vragenlijst over belangenconflicten {#gloria-reviews-and-approves-the-conflict-of-interest-questionnaire-submission} goed

De vragenlijst over belangenconflicten die Sarah heeft ingediend, wordt ter beoordeling aan Gloria Rios toegewezen. Gloria werkt als nalevingsfunctionaris in de organisatie. Gloria meldt zich aan bij haar AEM Inbox en bekijkt de taken die aan haar zijn toegewezen. Zij keurt de vragenlijst van Sarah goed en voltooit de taak.

![conflict-](assets/conflict-inbox.png)
**inboxFigure:** *Gloria&#39;s inbox*

![conflict-](assets/conflict-approved.png)
**selectedFigure:** *Open taak*

**Hoe werkt het**

De verzendactie in de vragenlijst &quot;Conflict of Interest&quot; leidt tot een workflow die een taak in het postvak van Gloria voor goedkeuring creëert. Bekijk de Forms Workflow op `https://[authorHost]:[authorPort]/editor.html/conf/global/settings/workflow/models/we-finance/employee/self-service/we-finance-employee-conflict-of-interest.html`

![werknemer-self-service-reference-site](assets/employee-self-service-reference-site.png)

**Zie het zelf**

Ga naar `https://[publishHost]:[publishPort]/content/we-finance/global/en/login.html?resource=/aem/inbox.html` en meld u aan met `grios/password` als gebruikersnaam/wachtwoord voor Gloria Rios. Open de voor de vragenlijst voor belangenconflicten gecreëerde taak en keur deze goed.

## Doorlopen van toepassing voor bedrijfskaarten {#corporate-card-application-walkthrough}

Sarah reist veel voor zaken en heeft een bedrijfskrediet nodig om onderweg haar rekeningen te betalen. Ze vraagt een visitekaartje via het werknemersportaal van haar organisatie.

### Sarah verzendt de toepassing van de Collectieve Kaart {#sarah-submits-the-corporate-card-application}

Sarah gaat naar het portal van haar organisatie, meldt zich aan en klikt op **[!UICONTROL Employee]** om toegang te krijgen tot het werknemersdashboard. Ze vindt de toepassing Bedrijfskaart op het werknemersdashboard en klikt **[!UICONTROL Apply]**.

![wij-financier-home-1](assets/we-finance-home-1.png)
**Cijfer:** *Organisatieportaal*

![employee-dashboard-1](assets/employee-dashboard-1.png)
**Figuur:** *Werknemerdashboard*

Ze klikt op **[!UICONTROL Apply]** op de toepassing Corporate Card. Er wordt een toepassing van één pagina geopend. Ze vult alle details en klikt op **[!UICONTROL Apply]** om de toepassing te verzenden.

![kaartvorm](assets/card-form.png)

**Hoe werkt het**

Het organisatieportaal en het werknemersdashboard zijn AEM Sites-pagina&#39;s. Het dashboard bevat een lijst met verschillende opties voor zelfbediening, zoals de toepassing voor de bedrijfskaart. De knop Toepassen op de toepassing is gekoppeld aan een adaptief formulier.

Het adaptieve formulier voor bedrijfskaarttoepassingen is een eenvoudig, responsief adaptief formulier van één pagina. Hierbij worden standaard adaptieve formuliercomponenten gebruikt, zoals tekst, telefoon, numeriek vak en numerieke stapfunctie. Herzie het adaptieve formulier op:\
`https://[authorHost]:[authorPort]/editor.html/content/forms/af/we-finance/employee/self-service/corporate-card.html`.

**Zie het zelf**

Ga naar `https://[publishHost]:[publishPort]/content/we-finance/global/en/self-service-forms.html` en meld u aan met `srose/srose` als gebruikersnaam/wachtwoord voor Sarah. Klik **[!UICONTROL Employee]** om tot het dashboard toegang te hebben en dan **[!UICONTROL Apply]** op Collectieve toepassing van de Kaart te klikken. Vul de gegevens in en verzend de aanvraag.

### Gloria beoordeelt en keurt de bedrijfskaarttoepassing {#gloria-reviews-and-approves-the-corporate-card-application} goed

De door Sarah ingediende aanvraag voor een bedrijfskaart wordt ter beoordeling aan Gloria Rios toegewezen. Gloria meldt zich aan bij haar AEM Inbox en bekijkt de taken die aan haar zijn toegewezen. Zij keurt de aanvraag van Sarah goed en voltooit de taak.

![corporate-card-](assets/corporate-card-inbox.png)
**inboxFigure:** *Gloria&#39;s inbox*

![corporate-card-](assets/corporate-card-approved.png)
**authorisedFigure:** *Open taak*

**Hoe werkt het**

De verzendworkflow in de toepassing Corporate Card leidt tot een Forms-workflow die een taak maakt in Gloria&#39;s inbox voor goedkeuring. Bekijk de Forms Workflow op `https://[authorHost]:[authorPort]/editor.html/conf/global/settings/workflow/models/we-finance/employee/self-service/we-finance-employee-corporate-card.html`

![bedrijfskaart-workflowmodel](assets/corporate-card-workflow-model.png)

**Zie het zelf**

Ga naar `https://[publishHost]:[publishPort]/content/we-finance/global/en/login.html?resource=/aem/inbox.html` en meld u aan met `grios/password` als gebruikersnaam/wachtwoord voor Gloria Rios. Open de taak die voor de toepassing Bedrijfs van de Kaart wordt gecreeerd en keur het goed.

## Doorloop voor verzending van kostendapport {#expense-report-submission-walkthrough}

Aangezien Sarah tijdens bedrijfsreizen doorbrengt, moet zij uitgavenrapporten ter goedkeuring voorleggen. De optie voor zelfbediening in haar organisatie stelt haar in staat het onkostenrapport online in te dienen.

### Sarah legt de toepassing van het Rapport van de Uitgaven {#sarah-submits-the-expense-report-application} voor

Sarah gaat naar het portal van haar organisatie, meldt zich aan en klikt op **[!UICONTROL Employee]** om toegang te krijgen tot het werknemersdashboard. Zij vindt de toepassing van het Rapport van de Uitgaven op het werknemersdashboard en klikt **[!UICONTROL Apply]**.

![wij-financier-home-2](assets/we-finance-home-2.png)
**Cijfer:** *Organisatieportaal*

![employee-dashboard-2](assets/employee-dashboard-2.png)
**Figuur:** *Werknemerdashboard*

Zij klikt **[!UICONTROL Apply]** op de toepassing van het Rapport van de Kosten. Er wordt een toepassingsformulier geopend met twee tabbladen - Rapportnaam en Rapportdetails. Met het pictogram **+** op het tabblad Rapportdetails kan zij meer dan uitgaven toevoegen in één rapport.

Het organisatieportaal en de toepassingen zijn ontvankelijk en mobiel-vriendelijk. In de volgende workflow ziet u hoe Sarah door het onkostenrapport op haar mobiele apparaat navigeert en het verzendt.

![onkostenrapportering op mobiel](assets/expense-report-on-mobile.png)

**Hoe werkt het**

Het organisatieportaal en het werknemersdashboard zijn AEM Sites-pagina&#39;s. Het dashboard maakt een lijst van verscheidene zelfbedieningsopties zoals de toepassing van het Rapport van de Uitgaven. De knop Toepassen is gekoppeld aan een adaptief formulier.

De tabbladen Rapportnaam en Rapportdetails in het aangepaste formulier zijn deelvenstercomponenten. Het deelvenster Rapportdetails bevat het deelvenster Kosten. Het is een herhaalbaar paneel dat toestaat toevoegend veelvoudige uitgaven in het rapport. Controleer het adaptieve formulier en de configuraties ervan op `https://[authorHost]:[authorPort]/editor.html/content/forms/af/we-finance/employee/expense-report.html`.

**Zie het zelf**

Ga naar `https://[publishHost]:[publishPort]/content/we-finance/global/en/self-service-forms.html` en meld u aan met `srose/srose` als gebruikersnaam/wachtwoord voor Sarah. Klik **[!UICONTROL Employee]** om tot het dashboard toegang te hebben en dan **[!UICONTROL Apply]** op de toepassing van het Rapport van de Uitgaven te klikken. Vul de gegevens in en verzend de aanvraag.

### Gloria beoordeelt en keurt het uitgavenrapport {#gloria-reviews-and-approves-the-expense-report} goed

Het door Sarah ingediende onkostenverslag wordt ter controle aan Gloria Rios toegewezen. Gloria meldt zich aan bij haar AEM Inbox en bekijkt de taken die aan haar zijn toegewezen. Zij keurt de aanvraag van Sarah goed en voltooit de taak.

![last-report-](assets/expense-report-inbox.png)
**inboxFigure:** *Gloria&#39;s inbox*

![uitgave-rapport-](assets/expense-report-approved.png)
**goedgekeurdFigure:** *Open taak*

**Hoe werkt het**

De indieningsworkflow in de toepassing Rapport uitgave leidt tot een Forms-workflow die een taak maakt in Gloria&#39;s inbox voor goedkeuring. Bekijk de Forms Workflow op `https://[authorHost]:[authorPort]/editor.html/conf/global/settings/workflow/models/we-finance/employee/self-service/we-finance-employee-expense-report-workflow.html`

![corporate-card-last-report-workflow-model](assets/corporate-card-expense-report-workflow-model.png)

**Zie het zelf**

Ga naar `https://[publishHost]:[publishPort]/content/we-finance/global/en/login.html?resource=/aem/inbox.html` en meld u aan met `grios/password` als gebruikersnaam/wachtwoord voor Gloria Rios. Open de taak die voor de toepassing van het Rapport van de Uitgaven wordt gecreeerd en keur het goed.

## Toepassingsdoorloop {#leave-application-walkthrough} laten

Sarah is van plan volgende maand een gezinsvakantie te maken en wil een week verlof aanvragen.

### Sarah verzendt de aanvraag {#sarah-submits-the-leave-application}

Sarah gaat naar het portal van haar organisatie, meldt zich aan en klikt op **[!UICONTROL Employee]** om toegang te krijgen tot het werknemersdashboard. Zij vindt verlaten toepassing op het werknemersdashboard en klikt **[!UICONTROL Apply]**.

![wij-financier-home-3](assets/we-finance-home-3.png)
**Cijfer:** *Organisatieportaal*

![employee-dashboard-3](assets/employee-dashboard-3.png)
**Figure:** *Werknemerdashboard*

De verloftoepassing wordt geopend met de naam van Sarah en de werknemer ID vooraf ingevuld in het formulier. Het toont ook haar verlofbalans en geschiedenis. Zij vult de verlofgegevens in en dient de aanvraag tot goedkeuring in.

Het organisatieportaal en de toepassingen zijn ontvankelijk en mobiel-vriendelijk. In de volgende workflow ziet u hoe Sarah door de toepassing navigeert en deze verzendt op haar mobiele apparaat.

![verlaat-vorm-op-mobiel](assets/leave-form-on-mobile.png)

**Hoe werkt het**

Het organisatieportaal en het werknemersdashboard zijn AEM Sites-pagina&#39;s. Het dashboard bevat een lijst met verschillende zelfbedieningsopties, zoals de toepassing Verlaten. De knop Toepassen is gekoppeld aan een adaptief formulier.

Het adaptieve formulier voor de verloftoepassing is gebaseerd op het model Formuliergegevens door werknemer. In de sectie Balans verlaten wordt de tabel Balans gevuld met de service `getLeavesOf` Formuliergegevensmodel. In de datumvelden Begin en Einde worden regels gebruikt om te controleren of de datumwaarden gelijk zijn of na de huidige datum. De duur van het verlof wordt berekend met behulp van de functie `calcBusinessDays`.

U kunt het adaptieve formulier en het formuliergegevensmodel op de volgende locaties bekijken:

`https://[authorHost]:[authorPort]/editor.html/content/forms/af/we-finance/employee/self-service/leave-application.html`

`https://[authorHost]:[authorPort]/aem/fdm/editor.html/content/dam/formsanddocuments-fdm/db`

**Zie het zelf**

Ga naar `https://[publishHost]:[publishPort]/content/we-finance/global/en/self-service-forms.html` en meld u aan met `srose/srose` als gebruikersnaam/wachtwoord voor Sarah. Klik **[!UICONTROL Employee]** om tot het dashboard toegang te hebben en dan **[!UICONTROL Apply]** op de Toepassing van het Verlof te klikken. Vul de gegevens in en verzend de aanvraag.

### Gloria beoordeelt en keurt de aanvraag {#gloria-reviews-and-approves-the-leave-application} goed

Het door Sarah ingediende verzoek om verlof wordt ter beoordeling aan Gloria Rios toegewezen. Gloria meldt zich aan bij haar AEM Inbox en bekijkt de taken die aan haar zijn toegewezen. Zij keurt de aanvraag van Sarah goed en voltooit de taak.

![leave-](assets/leave-inbox.png)
**inboxFigure:** *Gloria&#39;s inbox*

![leave-](assets/leave-approved.png)
**selectedFigure:** *Open taak*

**Hoe werkt het**

De verzendworkflow in de aanvraag om verlof zorgt voor een Forms-workflow die een taak maakt in Gloria&#39;s inbox voor goedkeuring. Bekijk de Forms Workflow op `https://[authorHost]:[authorPort]/editor.html/conf/global/settings/workflow/models/we-finance/employee/self-service/we-finance-employee-leave-application.html`

![corporate-card-leave-application-workflow-model](assets/corporate-card-leave-application-workflow-model.png)

**Zie het zelf**

Ga naar `https://[publishHost]:[publishPort]/content/we-finance/global/en/login.html?resource=/aem/inbox.html` en meld u aan met `grios/password` als gebruikersnaam/wachtwoord voor Gloria Rios. Open de taak die u voor de verloftoepassing hebt gemaakt en keur deze goed.
