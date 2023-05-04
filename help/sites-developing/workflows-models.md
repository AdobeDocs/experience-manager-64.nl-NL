---
title: Workflowmodellen maken
seo-title: Creating Workflow Models
description: U maakt een workflowmodel om de reeks stappen te definiëren die worden uitgevoerd wanneer een gebruiker de workflow start.
seo-description: You create a workflow model to define the series of steps executed when a user starts the workflow.
uuid: 53d94176-4d5f-4ab3-9628-6b7d44f81139
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: extending-aem
content-type: reference
discoiquuid: 9d2dba11-0d2d-4aed-b941-c8ade9bb7bfa
exl-id: d9c9db5f-9788-460f-ac09-88dd3c911edd
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '2248'
ht-degree: 1%

---

# Workflowmodellen maken{#creating-workflow-models}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

>[!CAUTION]
>
>Voor gebruik van de klassieke interface raadpleegt u de [AEM 6.3-documentatie](https://helpx.adobe.com/experience-manager/6-3/sites-developing/workflows-models.html) ter referentie.

U maakt een [workflowmodel](/help/sites-developing/workflows.md#model) om de reeks stappen te definiëren die worden uitgevoerd wanneer een gebruiker de workflow start. U kunt ook modeleigenschappen definiëren, zoals of de workflow van voorbijgaande aard is of meerdere bronnen gebruikt.

Wanneer een gebruiker een workflow start, wordt een instantie gestart; dit is het corresponderende runtimemodel dat is gemaakt toen u [Synchroniseren](#sync-your-workflow-generate-a-runtime-model) uw wijzigingen.

## Nieuwe workflow maken {#creating-a-new-workflow}

Wanneer u voor het eerst een nieuw workflowmodel maakt, bevat dit model:

* de stappen, **[!UICONTROL Flow Start]** en **[!UICONTROL Flow End]**.

   Deze vertegenwoordigen het begin en einde van de workflow. Deze stappen zijn vereist en kunnen niet worden bewerkt of verwijderd.

* Een voorbeeld **Deelnemer** stap benoemd **Stap 1**.

   Deze stap wordt gevormd om een het werkpunt aan de werkschemainitiatiefnemer toe te wijzen. Bewerk of verwijder deze stap en voeg desgewenst stappen toe.

Een nieuwe workflow maken met de editor:

1. Open de **[!UICONTROL Workflow Models]** console; door **[!UICONTROL Tools]**, **[!UICONTROL Workflow]**, **[!UICONTROL Models]** of, bijvoorbeeld:

   [http://localhost:4502/aem/workflow](http://localhost:4502/aem/workflow)

1. Selecteren **[!UICONTROL Create]** vervolgens **[!UICONTROL Create Model]**.
1. De **[!UICONTROL Add Workflow Model]** wordt weergegeven. Voer de **[!UICONTROL Title]** en **[!UICONTROL Name]** (optioneel) voordat u selecteert **[!UICONTROL Done]**.
1. Het nieuwe model wordt vermeld in **[!UICONTROL Workflow Models]** console.
1. Selecteer uw nieuwe workflow en gebruik [**[!UICONTROL Edit]**openen voor configuratie](#editing-a-workflow):

   ![wf-01](assets/wf-01.png)

>[!NOTE]
>
>Als u met programmacode modellen maakt (met behulp van een crx-pakket), kunt u ook een submap maken binnen:
>
>`/var/workflow/models`
>
>Bijvoorbeeld, `/var/workflow/models/prototypes`
>
>Deze map kan vervolgens worden gebruikt voor [toegang tot de modellen in die map beheren](/help/sites-administering/workflows-managing.md#create-a-subfolder-in-var-workflow-models-and-apply-the-acl-to-that).

## Een workflow bewerken {#editing-a-workflow}

U kunt elk bestaand workflowmodel bewerken in:

* [stappen definiëren](#adding-a-step-to-a-model) en hun [parameters](#configuring-a-workflow-step)

* workfloweigenschappen configureren, waaronder [stadia](#configuring-workflow-stages-that-show-workflow-progress), [of de workflow van voorbijgaande aard is](#creating-a-transient-workflow) en/of [gebruikt meerdere bronnen](#configuring-a-workflow-for-multi-resource-support)

Een [**Standaard of Verouderd** (out-of-the-box) workflow](#editing-a-default-or-legacy-workflow-for-the-first-time) een extra stap heeft om ervoor te zorgen dat een [veilige kopie](/help/sites-developing/workflows-best-practices.md#locations-workflow-models) wordt gebruikt voordat de wijzigingen worden aangebracht.

Wanneer updates van uw workflow zijn voltooid, moet u **[!UICONTROL Sync]** tot **[!UICONTROL Generate a Runtime Model]**. Zie [Uw workflow synchroniseren](#sync-your-workflow-generate-a-runtime-model) voor meer informatie.

### Uw workflow synchroniseren - Een runtimemodel genereren {#sync-your-workflow-generate-a-runtime-model}

**Synchroniseren** (rechts op de editor-werkbalk) genereert een [runtimemodel](/help/sites-developing/workflows.md#runtime-model). Het runtimemodel is het model dat daadwerkelijk wordt gebruikt wanneer een gebruiker een workflow start. Als u dat niet doet **[!UICONTROL Sync]** uw wijzigingen, dan zijn de wijzigingen niet beschikbaar bij uitvoering.

Wanneer u (of een andere gebruiker) wijzigingen aanbrengt in de workflow, moet u **[!UICONTROL Sync]** om een runtimemodel te genereren - zelfs als afzonderlijke dialoogvensters (bijvoorbeeld voor stappen) hun eigen opslagopties hebben.

Wanneer de wijzigingen worden gesynchroniseerd met het (opgeslagen) runtimemodel, **[!UICONTROL Synched]** wordt weergegeven.

Sommige stappen hebben verplichte velden en/of ingebouwde validatie. Wanneer niet aan deze voorwaarden wordt voldaan, wordt een fout weergegeven wanneer u probeert **[!UICONTROL Sync]** het model. Wanneer bijvoorbeeld geen deelnemer is gedefinieerd voor een **[!UICONTROL Participant]** stap:

![wf-21](assets/wf-21.png)

### Een standaardworkflow of oudere workflow voor het eerst bewerken {#editing-a-default-or-legacy-workflow-for-the-first-time}

Wanneer u een [Standaard en/of verouderd model](/help/sites-developing/workflows.md#workflow-types) voor bewerking:

* De **[!UICONTROL Steps]** browser is niet beschikbaar (linkerkant).
* Er is een **[!UICONTROL Edit]** in de werkbalk (rechts) beschikbaar.
* In eerste instantie worden het model en de eigenschappen ervan in de modus Alleen-lezen weergegeven als:

   * Standaardworkflows bevinden zich in `/libs`
   * Oudere workflows bevinden zich in `/etc`

Selecteren **[!UICONTROL Edit]** zal:

* neem een kopie van de workflow naar `/conf`
* de **[!UICONTROL Steps]** browser beschikbaar
* laten u toe om veranderingen aan te brengen

>[!NOTE]
>
>Zie [Locaties van workflowmodellen](/help/sites-developing/workflows-best-practices.md#locations-workflow-models) voor nadere informatie.

![wf-22](assets/wf-22.png)

### Een stap toevoegen aan een model {#adding-a-step-to-a-model}

U moet stappen aan uw model toevoegen om de uit te voeren activiteit te vertegenwoordigen - elke stap voert een specifieke activiteit uit. Een selectie van stapcomponenten is beschikbaar in een standaard AEM instantie.

Wanneer u een model bewerkt, worden de beschikbare stappen weergegeven in de verschillende groepen van de **[!UICONTROL Steps]** browser. Bijvoorbeeld:

![wf-10](assets/wf-10.png)

>[!NOTE]
>
>Voor informatie over de primaire stapcomponenten die met AEM worden geïnstalleerd, zie [Referentie workflowstappen](/help/sites-developing/workflows-step-ref.md).

**Een stap toevoegen aan een model**:

1. Open een bestaand workflowmodel voor bewerking. Van de **[!UICONTROL Workflows Model]** -console, selecteert u het vereiste model en **[!UICONTROL Edit]**.
1. Open de **[!UICONTROL Steps]** browser; gebruiken **[!UICONTROL Toggle Side Panel]** helemaal links van de bovenste werkbalk. Hier kunt u:

   * **[!UICONTROL Filter]** voor specifieke stappen.
   * Gebruik de keuzelijst om de selectie te beperken tot een specifieke groep stappen.
   * Selecteer het pictogram Beschrijving tonen ![wf-stepinfo-icon](assets/wf-stepinfo-icon.png) voor meer informatie over de juiste stap.

   ![wf-02](assets/wf-02.png)

1. Sleep de desbetreffende stap(en) naar de gewenste locatie in het model.

   Bijvoorbeeld een **[!UICONTROL Participant Step]**.

   Nadat het aan de stroom is toegevoegd kunt u [vorm de stap](#configuring-a-workflow-step).

   ![wf-03](assets/wf-03.png)

1. Voeg zo veel stappen, of andere updates toe, zoals vereist.

   Tijdens de uitvoering worden de stappen uitgevoerd in de volgorde waarin ze in het model worden weergegeven. Nadat u de onderdelen met stappen hebt toegevoegd, kunt u deze naar een andere locatie in het model slepen.

   U kunt ook bestaande stappen kopiëren, knippen, plakken, groeperen of verwijderen. zoals bij de [pagina-editor.](/help/sites-authoring/editing-content.md)

   Gesplitste stappen kunnen ook worden samengevouwen/uitgevouwen met de werkbalkoptie: ![wf-collapse-toolbar-icon](assets/wf-collapseexpand-toolbar-icon.png)

1. Wijzigingen bevestigen met **[!UICONTROL Sync]** (editor-werkbalk) om het runtimemodel te genereren.

   Zie [Uw workflow synchroniseren](#sync-your-workflow-generate-a-runtime-model) voor meer informatie.

### Een workflowstap configureren {#configuring-a-workflow-step}

U kunt **Configureren** en pas het gedrag van een werkschemastap aan gebruikend **[!UICONTROL Step Properties]** dialoogvensters.

1. Als u het dialoogvenster **[!UICONTROL Step Properties]** een van de volgende stappen:

   * Tik op de stap in het workflowmodel en selecteer **[!UICONTROL Configure]** op de werkbalk van de component.
   * Dubbelklik op de stap.

   >[!NOTE]
   >
   >Voor informatie over de primaire stapcomponenten die met AEM worden geïnstalleerd, zie [Referentie workflowstappen](/help/sites-developing/workflows-step-ref.md).

1. Configureer de **[!UICONTROL Step Properties]** indien nodig; Welke eigenschappen beschikbaar zijn, is afhankelijk van het type stap. Er kunnen ook verschillende tabbladen beschikbaar zijn. De standaardinstelling **[!UICONTROL Participant Step]**, in een nieuwe workflow presenteren als `Step 1`:

   ![wf-11](assets/wf-11.png)

1. Bevestig uw updates met de tik.
1. Wijzigingen bevestigen met **[!UICONTROL Sync]** (editor-werkbalk) om het runtimemodel te genereren.

   Zie [Uw workflow synchroniseren](#sync-your-workflow-generate-a-runtime-model) voor meer informatie.

### Een tijdelijke workflow maken {#creating-a-transient-workflow}

U kunt een [Voorzichtig](/help/sites-developing/workflows.md#transient-workflows) workflowmodel bij het maken van een nieuw model of bij het bewerken van een bestaand model:

1. Het workflowmodel openen voor [bewerken](#editing-a-workflow).
1. Selecteren **[!UICONTROL Workflow Model Properties]** op de werkbalk.
1. Activeer in het dialoogvenster **[!UICONTROL Transient Workflow]** (of deactiveren indien vereist):

   ![wf-07](assets/wf-07.png)

1. De wijziging bevestigen met **[!UICONTROL Save & Close]**; gevolgd door **[!UICONTROL Sync]** (editor-werkbalk) om het runtimemodel te genereren.

   Zie [Uw workflow synchroniseren](#sync-your-workflow-generate-a-runtime-model) voor meer informatie.

>[!NOTE]
>
>Wanneer u een workflow uitvoert in [transient](/help/sites-developing/workflows.md#transient-workflows) AEM slaat geen workflowgeschiedenis op. Daarom [Tijdlijn](/help/sites-authoring/basic-handling.md#timeline) geeft geen informatie weer die betrekking heeft op die workflow. [](/help/sites-authoring/basic-handling.md#timeline)

### Workflowmodellen beschikbaar stellen in Touch UI {#make-workflow-models-available-in-touchui}

Als een workflowmodel aanwezig is in de klassieke gebruikersinterface, maar ontbreekt in het pop-upmenu Selectie in het dialoogvenster **[!UICONTROL Timeline]** rail van Touch UI, dan volg de configuratie om het ter beschikking te stellen. De volgende stappen illustreren het gebruiken van het geroepen werkschemamodel **[!UICONTROL Request for Activation]**.

1. Bevestig dat het model niet beschikbaar is in een interface met aanraakbediening. Middelen benaderen met `/assets.html/content/dam` pad. Selecteer een element. Openen **[!UICONTROL Timeline]** in linkerspoor. Klikken **[!UICONTROL Start Workflow]** en bevestigt dat de **[!UICONTROL Request for Activation]** model is niet aanwezig in de pop-uplijst.

1. Navigeren door **[!UICONTROL Tools > General > Tagging]**. Selecteer **[!UICONTROL Workflow]**.

1. Selecteer **[!UICONTROL Create > Create Tag]**. Set **[!UICONTROL Title]** als `DAM` en **[!UICONTROL Name]** als `dam`. Selecteer **[!UICONTROL Submit]**.
   ![Tag maken in workflowmodel](assets/workflow_create_tag.png)

1. Ga naar **[!UICONTROL Tools > Workflow > Models]**. Selecteren **[!UICONTROL Request for Activation]** selecteert u vervolgens **[!UICONTROL Edit]**.

1. Selecteren **[!UICONTROL Edit]** en vervolgens openen **[!UICONTROL Workflow Model Properties]**. Ga naar de **[!UICONTROL Basic]** tab.

1. Toevoegen `Workflow : DAM` tot **[!UICONTROL Tags]** veld. Bevestig de selectie met de controle (kruis).

1. De toevoeging van de tag bevestigen met **[!UICONTROL Save & Close]**.
   ![Pagina-eigenschappen van model bewerken](assets/workflow_model_edit_activation1.png)

1. Voltooi het proces met **[!UICONTROL Sync]**. De workflow is nu beschikbaar in de interface voor aanraakbediening.

### Een workflow configureren voor ondersteuning van meerdere bronnen {#configuring-a-workflow-for-multi-resource-support}

U kunt een workflowmodel configureren voor [Ondersteuning voor meerdere bronnen](/help/sites-developing/workflows.md#multi-resource-support) bij het maken van een nieuw model of door een bestaand model te bewerken:

1. Het workflowmodel openen voor [bewerken](#editing-a-workflow).
1. Selecteren **[!UICONTROL Workflow Model Properties]** op de werkbalk.

1. Activeer in het dialoogvenster **[!UICONTROL Multi Resource Support]** (of deactiveren indien vereist):

   ![wf-08](assets/wf-08.png)

1. De wijziging bevestigen met **[!UICONTROL Save & Close]**; gevolgd door **[!UICONTROL Sync]** (editor-werkbalk) om het runtimemodel te genereren.

   Zie [Uw workflow synchroniseren](#sync-your-workflow-generate-a-runtime-model) voor meer informatie.

### Werkstroomfasen configureren (die de voortgang van de workflow weergeven) {#configuring-workflow-stages-that-show-workflow-progress}

[Werkstroomfasen](/help/sites-developing/workflows.md#workflow-stages) Help de voortgang van een workflow bij het uitvoeren van taken te visualiseren.

>[!CAUTION]
>
>Als werkstroomfasen zijn gedefinieerd in **[!UICONTROL Page Properties]**, maar niet gebruikt voor de workflowstappen, wordt op de voortgangsbalk geen voortgang weergegeven (ongeacht de huidige workflowstap).

De stadia die beschikbaar moeten zijn, worden gedefinieerd in de workflowmodellen; bestaande workflowmodellen kunnen worden bijgewerkt met werkgebieddefinities. U kunt een willekeurig aantal fasen voor het workflowmodel definiëren.

Om te bepalen **[!UICONTROL Stages]** voor uw workflow:

1. Open uw workflowmodel voor bewerking.
1. Selecteren **[!UICONTROL Workflow Model Properties]** op de werkbalk. Open vervolgens het dialoogvenster **[!UICONTROL Stages]** tab.
1. Voeg (en plaats) uw vereiste toe **[!UICONTROL Stages]**. U kunt een willekeurig aantal fasen voor het workflowmodel definiëren.

   Bijvoorbeeld:

   ![wf-08-1](assets/wf-08-1.png)

1. Klikken **[!UICONTROL Save & Close]** om de eigenschappen op te slaan.
1. Wijs een werkgebied aan elk van de stappen in het werkschemamodel toe. Bijvoorbeeld:

   ![wf-09](assets/wf-09.png)

   Een werkgebied kan aan meerdere stappen worden toegewezen. Bijvoorbeeld:

   | **Stap** | **Werkgebied** |
   |---|---|
   | Stap 1 | Maken |
   | Stap 2 | Maken |
   | Stap 3 | Controleren |
   | Stap 4 | Goedkeuren |
   | Stap 5 | Goedkeuren |
   | Stap 6 | Voltooid |

1. Wijzigingen bevestigen met **[!UICONTROL Sync]** (editor-werkbalk) om het runtimemodel te genereren.

   Zie [Uw workflow synchroniseren](#sync-your-workflow-generate-a-runtime-model) voor meer informatie.

## Een workflowmodel exporteren in een pakket {#exporting-a-workflow-model-in-a-package}

1. Een nieuw pakket maken met de opdracht [Pakketbeheer](/help/sites-administering/package-manager.md#package-manager):

   1. Navigeer aan de Manager van het Pakket door **[!UICONTROL Tools]**, **[!UICONTROL Deployment]**, **[!UICONTROL Packages]**.
   1. Klik op **[!UICONTROL Create Package]**.
   1. Geef de **[!UICONTROL Package Name]** en alle andere gegevens die nodig zijn.
   1. Klik op **[!UICONTROL OK]**.

1. Klikken **[!UICONTROL Edit]** op de werkbalk van het nieuwe pakket.

1. Open de **[!UICONTROL Filters]** tab.

1. Selecteren **[!UICONTROL Add Filter]** en geef het pad van uw workflowmodel op *ontwerp*:

   `/conf/global/settings/workflow/models/<*your-model-name*>`

   Klik op **[!UICONTROL Done]**.

1. Selecteren **[!UICONTROL Add Filter]** en geef het pad van uw *runtime* workflowmodel:

   `/var/workflow/models/<*your-model-name*>`

   Klik op **[!UICONTROL Done]**.

1. Voeg extra filters toe voor om het even welke douanescripts die door uw model worden gebruikt.
1. Klikken **[!UICONTROL Save]** om uw filterdefinities te bevestigen.
1. Selecteren **[!UICONTROL Build]** op de werkbalk van de pakketdefinitie.
1. Selecteren **[!UICONTROL Download]** op de pakketwerkbalk.

## Workflows gebruiken om formulierverzendingen te verwerken {#using-workflows-to-process-form-submissions}

U kunt een formulier configureren voor verwerking door de geselecteerde workflow. Wanneer gebruikers het formulier verzenden, wordt een nieuwe werkstroominstantie gemaakt met de gegevens van het verzenden van het formulier als lading.

U configureert als volgt de workflow die met het formulier moet worden gebruikt:

1. Maak een nieuwe pagina en open deze voor bewerking.
1. Voeg een **[!UICONTROL Form]** naar de pagina.
1. Configureer de **[!UICONTROL Form Start]** die op de pagina werden weergegeven.
1. Gebruiken **[!UICONTROL Start Workflow]** om de gewenste workflow te selecteren uit de beschikbare werkstromen:

   ![wf-12](assets/wf-12.png)

1. Bevestig de nieuwe formulierconfiguratie met de tik.

## Testworkflows {#testing-workflows}

Het is een goede praktijk wanneer het testen van een werkschema om een verscheidenheid van ladingstypes te gebruiken; met inbegrip van typen die verschillen van de soorten waarvoor zij is ontwikkeld. Als u bijvoorbeeld van plan bent om in uw workflow te werken met Elementen, test u deze door een Pagina in te stellen als een payload en controleer of er geen fouten optreden.

Test bijvoorbeeld de nieuwe workflow als volgt:

1. [Uw workflowmodel starten](/help/sites-administering/workflows-starting.md) vanuit de console.
1. Definieer de **[!UICONTROL Payload]** en bevestigen.

1. Voer de vereiste handelingen uit zodat de workflow doorgaat.
1. Controleer de logbestanden terwijl de workflow wordt uitgevoerd.

U kunt ook AEM configureren voor weergave **[!UICONTROL DEBUG]** in de logbestanden. Zie [Logboekregistratie](/help/sites-deploying/configure-logging.md) voor meer informatie en wanneer de ontwikkeling is voltooid, stelt u de **[!UICONTROL Log Level]** terug naar **[!UICONTROL Info]**.

## Voorbeelden {#examples}

### Voorbeeld: Een (eenvoudige) workflow maken om een publicatieaanvraag te accepteren of af te wijzen {#example-creating-a-simple-workflow-to-accept-or-reject-a-request-for-publication}

Om enkele mogelijkheden voor het maken van een workflow te illustreren, maakt u in het volgende voorbeeld een variatie van de optie `Publish Example` workflow.

1. [Een nieuw workflowmodel maken](#creating-a-new-workflow).

   De nieuwe workflow bevat:

   * **[!UICONTROL Flow Start]**
   * `Step 1`
   * **[!UICONTROL Flow End]**

1. Verwijderen `Step 1` (omdat dit het verkeerde staptype voor dit voorbeeld is):

   * Klik op de stap en selecteer **[!UICONTROL Delete]** op de werkbalk van de component. Bevestig de handeling.

1. Van de **[!UICONTROL Workflow]** Selecteer de gewenste stappen in de browser en sleep een **[!UICONTROL Participant Step]** op de werkstroom te plaatsen en deze tussen **[!UICONTROL Flow Start]** en **[!UICONTROL Flow End*]*.
1. U opent als volgt het dialoogvenster Eigenschappen:

   * Klik op de deelnemersstap en selecteer **[!UICONTROL Configure]** op de werkbalk van de component.
   * Dubbelklik op de stap voor deelnemers.

1. In de **[!UICONTROL Common]** tabs openen `Validate Content` voor beide **[!UICONTROL Title]** en **[!UICONTROL Description]**.
1. Open de **[!UICONTROL User/Group]** tab:

   * Activeren **[!UICONTROL Notify user via email]**.
   * Selecteren `Administrator` ( `admin`) voor de **[!UICONTROL User/Group]** veld.

   >[!NOTE]
   >
   >Voor te verzenden e-mails: [de postdienst en de details van de gebruikersrekening moeten worden gevormd](/help/sites-administering/notification.md).

1. Bevestig de updates met de tik.

   U wordt teruggestuurd naar het overzicht van het workflowmodel, waar de naam van de deelnemer is gewijzigd in `Validate Content`.

1. Sleep een **[!UICONTROL Or Split]** op de werkstroom te plaatsen en deze tussen `Validate Content` en **[!UICONTROL Flow End]**.
1. Open de **[!UICONTROL Or Split]** voor configuratie.
1. Configureren:

   * **[!UICONTROL Common]**: selecteren **[!UICONTROL 2 Branches]**
   * **[!UICONTROL Branch 1]**: selecteren **[!UICONTROL Default Route]**.
   * **[!UICONTROL Branch 2]**: waarborgen **[!UICONTROL Default Route]** is niet geselecteerd.

1. Bevestig uw updates aan **[!UICONTROL OR Split]**.
1. Sleep een **[!UICONTROL Participant Step]** Open de eigenschappen in de linkervertakking, geef de volgende waarden op en bevestig de wijzigingen:

   * **[!UICONTROL Title]**: `Reject Publish Request`
   * **[!UICONTROL User/Group]**: bijvoorbeeld: `projects-administrators`
   * **[!UICONTROL Notify user via email]**: Activeer deze functie om de gebruiker per e-mail op de hoogte te stellen.

1. Sleep een **[!UICONTROL Process Step]** Open de eigenschappen op de rechtervertakking, geef de volgende waarden op en bevestig de wijzigingen:

   * **[!UICONTROL Title]**: `Publish Page as Requested`
   * **[!UICONTROL Process]**: selecteren `Activate Page`. Dit proces publiceert de geselecteerde pagina naar de uitgeversinstanties.

1. Klikken **[!UICONTROL Sync]** (editor-werkbalk) om het runtimemodel te genereren.

   Zie [Uw workflow synchroniseren](#sync-your-workflow-generate-a-runtime-model) voor meer informatie.

   Uw nieuwe workflowmodel ziet er als volgt uit:

   ![wf-13](assets/wf-13.png)

1. Pas deze workflow toe op de pagina, zodat wanneer de gebruiker naar **[!UICONTROL Complete]** de **[!UICONTROL Validate Content]** stap, kunnen ze selecteren of ze **[!UICONTROL Publish Page as Requested]**, of **[!UICONTROL Reject Publish Request]**.

   ![chlimage_1-182](assets/chlimage_1-182.png)

### Voorbeeld: Een regel definiëren voor een OR-splitsing {#example-defining-a-rule-for-an-or-split}

**[!UICONTROL OR Split]** Met de stappen kunt u voorwaardelijke verwerkingspaden in uw workflow opnemen.

Een OR-regel definiëren:

1. Maak twee scripts en sla deze op in de repository, bijvoorbeeld onder:

   `/apps/myapp/workflow/scripts`

   >[!NOTE]
   >
   >De scripts moeten een [function `check()`](#function-check) dat een booleaanse waarde retourneert.

1. De workflow bewerken en de **[!UICONTROL OR Split]** op het model.
1. Eigenschappen van **[!UICONTROL Branch 1]** van de **[!UICONTROL OR Split]**:

   * Hiermee definieert u dit als de **[!UICONTROL Default Route]** door de **[!UICONTROL Value]** tot `true`.
   * Als **[!UICONTROL Rule]**, stelt u het pad naar het script in. Bijvoorbeeld:

      `/apps/myapp/workflow/scripts/myscript1.ecma`
   >[!NOTE]
   >
   >U kunt de vertakkingsvolgorde desgewenst wijzigen.

1. De eigenschappen van het gereedschap **[!UICONTROL Branch 2]** van de **[!UICONTROL OR Split]**.

   * Als **[!UICONTROL Rule]**, stelt u het pad in op het andere script. Bijvoorbeeld:

      `/apps/myapp/workflow/scripts/myscript2.ecma`

1. Stel de eigenschappen van de afzonderlijke stappen in elke vertakking in. Zorg ervoor dat de **[!UICONTROL User/Group]** is ingesteld.
1. Klikken **Synchroniseren** (editor-werkbalk) om uw wijzigingen in het runtimemodel voort te zetten.

   Zie [Uw workflow synchroniseren](#sync-your-workflow-generate-a-runtime-model) voor meer informatie.

#### Functie check() {#function-check}

>[!NOTE]
>
>Zie [ECMAScript gebruiken](/help/sites-developing/workflows-customizing-extending.md#using-ecmascript).

Het volgende voorbeeldscript retourneert `true` als het knooppunt een `JCR_PATH` onder `/content/we-retail/us/en`:

```
function check() {
    if (workflowData.getPayloadType() == "JCR_PATH") {
      var path = workflowData.getPayload().toString();
      var node = jcrSession.getItem(path);

      if (node.getPath().indexOf("/content/we-retail/us/en") >= 0) {
       return true;
      } else {
       return false;
      } 
     } else {
      return false;
     }
}
```

### Voorbeeld: Aangepast verzoek om activering {#example-customized-request-for-activation}

U kunt om het even welke uit-van-de-doos workflows aanpassen. Voor aangepast gedrag bedekt u de details van de juiste workflow.

Bijvoorbeeld, **[!UICONTROL Request for Activation]**. Deze workflow wordt gebruikt voor het publiceren van pagina&#39;s binnen **[!UICONTROL Sites]** en wordt automatisch geactiveerd wanneer een auteur van de inhoud niet de juiste replicatierechten heeft. Zie [Paginaontwerp aanpassen - De activeringsworkflow aanpassen](/help/sites-developing/customizing-page-authoring-touch.md#customizing-the-request-for-activation-workflow) voor nadere bijzonderheden.
