---
title: Workflowmodellen maken
seo-title: Workflowmodellen maken
description: U maakt een workflowmodel om de reeks stappen te definiëren die worden uitgevoerd wanneer een gebruiker de workflow start.
seo-description: U maakt een workflowmodel om de reeks stappen te definiëren die worden uitgevoerd wanneer een gebruiker de workflow start.
uuid: 53d94176-4d5f-4ab3-9628-6b7d44f81139
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: extending-aem
content-type: reference
discoiquuid: 9d2dba11-0d2d-4aed-b941-c8ade9bb7bfa
translation-type: tm+mt
source-git-commit: 93d0bb274c87ecb272583aaf2cb04b0f5df9f4f7
workflow-type: tm+mt
source-wordcount: '2233'
ht-degree: 1%

---


# Workflowmodellen maken{#creating-workflow-models}

>[!CAUTION]
>
>Voor gebruik van de klassieke interface raadpleegt u de documentatie [van](https://helpx.adobe.com/experience-manager/6-3/sites-developing/workflows-models.html) AEM 6.3 ter referentie.

U maakt een [workflowmodel](/help/sites-developing/workflows.md#model) om de reeks stappen te definiëren die worden uitgevoerd wanneer een gebruiker de workflow start. U kunt ook modeleigenschappen definiëren, zoals of de workflow van voorbijgaande aard is of meerdere bronnen gebruikt.

Wanneer een gebruiker een workflow start, wordt een instantie gestart; Dit is het corresponderende runtimemodel dat is gemaakt toen u uw wijzigingen [synchroniseerde](#sync-your-workflow-generate-a-runtime-model) .

## Nieuwe workflow maken {#creating-a-new-workflow}

Wanneer u voor het eerst een nieuw workflowmodel maakt, bevat dit model:

* De stappen **[!UICONTROL Flow Start]** en **[!UICONTROL Flow End]**.

   Deze vertegenwoordigen het begin en einde van de workflow. Deze stappen zijn vereist en kunnen niet worden bewerkt of verwijderd.

* Een voorbeeldstap van de **Deelnemer** genoemd **Stap 1**.

   Deze stap wordt gevormd om een het werkpunt aan de werkschemainitiatiefnemer toe te wijzen. Bewerk of verwijder deze stap en voeg desgewenst stappen toe.

Een nieuwe workflow maken met de editor:

1. Open de **[!UICONTROL Workflow Models]** console; door middel van **[!UICONTROL Tools]**, **[!UICONTROL Workflow]****[!UICONTROL Models]** of, bijvoorbeeld:

   [http://localhost:4502/aem/workflow](http://localhost:4502/aem/workflow)

1. Selecteer **[!UICONTROL Create]**, dan **[!UICONTROL Create Model]**.
1. The **[!UICONTROL Add Workflow Model]** dialog box appears. Voer de **[!UICONTROL Title]** en **[!UICONTROL Name]** (optioneel) in voordat u gaat selecteren **[!UICONTROL Done]**.
1. Het nieuwe model wordt vermeld in de **[!UICONTROL Workflow Models]** console.
1. Selecteer uw nieuwe werkschema, dan gebruik [**[!UICONTROL Edit]** om het voor configuratie](#editing-a-workflow)te openen:

   ![wf-01](assets/wf-01.png)

>[!NOTE]
>
>Als u met programmacode modellen maakt (met behulp van een crx-pakket), kunt u ook een submap maken binnen:
>
>`/var/workflow/models`
>
>Bijvoorbeeld, `/var/workflow/models/prototypes`
>
>Deze map kan vervolgens worden gebruikt voor het [beheer van de toegang tot de modellen in die map](/help/sites-administering/workflows-managing.md#create-a-subfolder-in-var-workflow-models-and-apply-the-acl-to-that).

## Een workflow bewerken {#editing-a-workflow}

U kunt elk bestaand workflowmodel bewerken in:

* [stappen](#adding-a-step-to-a-model) en de bijbehorende [parameters definiëren](#configuring-a-workflow-step)

* workfloweigenschappen configureren, inclusief [stadia](#configuring-workflow-stages-that-show-workflow-progress), [of de workflow van voorbijgaande aard](#creating-a-transient-workflow) is en/of meerdere bronnen [gebruikt](#configuring-a-workflow-for-multi-resource-support)

Het bewerken van een [**standaard- of verouderde **workflow](#editing-a-default-or-legacy-workflow-for-the-first-time)(out-of-the-box) heeft een extra stap om ervoor te zorgen dat er een[veilige kopie](/help/sites-developing/workflows-best-practices.md#locations-workflow-models)wordt gemaakt voordat de wijzigingen worden aangebracht.

Wanneer updates van uw werkstroom voltooid zijn, moet u **[!UICONTROL Sync]** aan **[!UICONTROL Generate a Runtime Model]**. Zie [Uw workflow](#sync-your-workflow-generate-a-runtime-model) synchroniseren voor meer informatie.

### Uw workflow synchroniseren - Een runtimemodel genereren {#sync-your-workflow-generate-a-runtime-model}

**Met Sync** (rechts op de editor-werkbalk) wordt een [runtimemodel](/help/sites-developing/workflows.md#runtime-model)gegenereerd. Het runtimemodel is het model dat daadwerkelijk wordt gebruikt wanneer een gebruiker een workflow start. Als u **[!UICONTROL Sync]** uw wijzigingen niet aanbrengt, zijn de wijzigingen niet beschikbaar tijdens de runtime.

Wanneer u (of een andere gebruiker) wijzigingen aanbrengt in de workflow, moet u een runtimemodel genereren, zelfs wanneer afzonderlijke dialoogvensters (bijvoorbeeld voor stappen) hun eigen opslagopties hebben. **[!UICONTROL Sync]**

Wanneer de wijzigingen worden gesynchroniseerd met het (opgeslagen) runtimemodel, **[!UICONTROL Synched]** wordt dit weergegeven.

Sommige stappen hebben verplichte velden en/of ingebouwde validatie. Wanneer niet aan deze voorwaarden wordt voldaan, wordt een fout weergegeven wanneer u naar **[!UICONTROL Sync]** het model probeert te gaan. Wanneer bijvoorbeeld geen deelnemer is gedefinieerd voor een **[!UICONTROL Participant]** stap:

![wf-21](assets/wf-21.png)

### Een standaardworkflow of oudere workflow voor het eerst bewerken {#editing-a-default-or-legacy-workflow-for-the-first-time}

Wanneer u een [standaardmodel en/of verouderd model](/help/sites-developing/workflows.md#workflow-types) opent voor bewerking:

* De **[!UICONTROL Steps]** browser is niet beschikbaar (links).
* De werkbalk bevat een **[!UICONTROL Edit]** handeling (rechterkant).
* In eerste instantie worden het model en de eigenschappen ervan in de modus Alleen-lezen weergegeven als:

   * Standaardworkflows bevinden zich in `/libs`
   * Oudere workflows bevinden zich in `/etc`

Selecteren **[!UICONTROL Edit]** zal:

* neem een kopie van de workflow naar `/conf`
* de **[!UICONTROL Steps]** browser beschikbaar stellen
* laten u toe om veranderingen aan te brengen

>[!NOTE]
>
>Zie [Locations of Workflow Models](/help/sites-developing/workflows-best-practices.md#locations-workflow-models) voor meer informatie.

![wf-22](assets/wf-22.png)

### Een stap toevoegen aan een model {#adding-a-step-to-a-model}

U moet stappen aan uw model toevoegen om de uit te voeren activiteit te vertegenwoordigen - elke stap voert een specifieke activiteit uit. Een selectie van stapcomponenten is beschikbaar in een standaard AEM instantie.

Wanneer u een model bewerkt, worden de beschikbare stappen weergegeven in de verschillende groepen van de **[!UICONTROL Steps]** browser. Bijvoorbeeld:

![wf-10](assets/wf-10.png)

>[!NOTE]
>
>Voor informatie over de primaire stapcomponenten die met AEM geïnstalleerd zijn, zie de Verwijzing [van de Stappen van het](/help/sites-developing/workflows-step-ref.md)Werkschema.

**Een stap toevoegen aan een model**:

1. Open een bestaand workflowmodel voor bewerking. Van de **[!UICONTROL Workflows Model]** console, selecteer het vereiste model, dan **[!UICONTROL Edit]**.
1. Open de **[!UICONTROL Steps]** browser; helemaal links van **[!UICONTROL Toggle Side Panel]** de bovenste werkbalk. Hier kunt u:

   * **[!UICONTROL Filter]** voor specifieke stappen.
   * Gebruik de keuzelijst om de selectie te beperken tot een specifieke groep stappen.
   * Selecteer het pictogram Beschrijving tonen ![wf-stepinfo-icon](assets/wf-stepinfo-icon.png) om meer details over de aangewezen stap te tonen.

   ![wf-02](assets/wf-02.png)

1. Sleep de desbetreffende stap(en) naar de gewenste locatie in het model.

   Bijvoorbeeld een **[!UICONTROL Participant Step]**.

   Nadat het aan de stroom wordt toegevoegd kunt u de stap [](#configuring-a-workflow-step)vormen.

   ![wf-03](assets/wf-03.png)

1. Voeg zo veel stappen, of andere updates toe, zoals vereist.

   Tijdens de uitvoering worden de stappen uitgevoerd in de volgorde waarin ze in het model worden weergegeven. Nadat u de onderdelen met stappen hebt toegevoegd, kunt u deze naar een andere locatie in het model slepen.

   U kunt ook bestaande stappen kopiëren, knippen, plakken, groeperen of verwijderen. zoals in de [paginaeditor.](/help/sites-authoring/editing-content.md)

   Gesplitste stappen kunnen ook worden samengevouwen/uitgevouwen met de werkbalkoptie: ![wf-collapse-toolbar-icon](assets/wf-collapseexpand-toolbar-icon.png)

1. Bevestig de wijzigingen met **[!UICONTROL Sync]** (editor-werkbalk) om het runtimemodel te genereren.

   Zie [Uw workflow](#sync-your-workflow-generate-a-runtime-model) synchroniseren voor meer informatie.

### Een workflowstap configureren {#configuring-a-workflow-step}

U kunt het gedrag van een workflowstap **configureren** en aanpassen in de **[!UICONTROL Step Properties]** dialoogvensters.

1. U opent als volgt het **[!UICONTROL Step Properties]** dialoogvenster voor een stap:

   * Tik op de stap in het workflowmodel en selecteer deze op de werkbalk **[!UICONTROL Configure]** van de component.
   * Dubbelklik op de stap.

   >[!NOTE]
   >
   >Voor informatie over de primaire stapcomponenten die met AEM geïnstalleerd zijn, zie de Verwijzing [van de Stappen van het](/help/sites-developing/workflows-step-ref.md)Werkschema.

1. de **[!UICONTROL Step Properties]** vereiste configuratie; Welke eigenschappen beschikbaar zijn, is afhankelijk van het type stap. Er kunnen ook verschillende tabbladen beschikbaar zijn. De standaardinstelling is bijvoorbeeld **[!UICONTROL Participant Step]** in een nieuwe workflow aanwezig als `Step 1`:

   ![wf-11](assets/wf-11.png)

1. Bevestig uw updates met de tik.
1. Bevestig de wijzigingen met **[!UICONTROL Sync]** (editor-werkbalk) om het runtimemodel te genereren.

   Zie [Uw workflow](#sync-your-workflow-generate-a-runtime-model) synchroniseren voor meer informatie.

### Een tijdelijke workflow maken {#creating-a-transient-workflow}

U kunt een [tijdelijk](/help/sites-developing/workflows.md#transient-workflows) workflowmodel maken bij het maken van een nieuw model of door een bestaand model te bewerken:

1. Open het workflowmodel voor [bewerking](#editing-a-workflow).
1. Select **[!UICONTROL Workflow Model Properties]** from the toolbar.
1. Activeer **[!UICONTROL Transient Workflow]** (of deactiveer desgewenst) in het dialoogvenster:

   ![wf-07](assets/wf-07.png)

1. Bevestig de wijziging met **[!UICONTROL Save & Close]**; gevolgd door **[!UICONTROL Sync]** (editor toolbar) om het runtimemodel te genereren.

   Zie [Uw workflow](#sync-your-workflow-generate-a-runtime-model) synchroniseren voor meer informatie.

>[!NOTE]
>
>Wanneer u een workflow uitvoert in de modus [Overgang](/help/sites-developing/workflows.md#transient-workflows) , slaat AEM geen historie van de workflow op. Daarom wordt in de [tijdlijn](/help/sites-authoring/basic-handling.md#timeline) geen informatie over die workflow weergegeven. [](/help/sites-authoring/basic-handling.md#timeline)

### Workflowmodellen beschikbaar stellen in Touch UI {#make-workflow-models-available-in-touchui}

Als een workflowmodel aanwezig is in de klassieke gebruikersinterface, maar ontbreekt in het pop-upmenu voor selectie in de **[!UICONTROL Timeline]** Touch-gebruikersinterface, volgt u de configuratie om het beschikbaar te maken. De volgende stappen illustreren het gebruiken van het geroepen werkschemamodel **[!UICONTROL Request for Activation]**.

1. Bevestig dat het model niet beschikbaar is in een interface met aanraakbediening. Een element openen met `/assets.html/content/dam` pad. Selecteer een element. Openen **[!UICONTROL Timeline]** in linkerspoor. Klik **[!UICONTROL Start Workflow]** en bevestig dat het **[!UICONTROL Request for Activation]** model niet aanwezig is in de popup lijst.

1. Navigeer door **[!UICONTROL Tools > General > Tagging]**. Selecteer **[!UICONTROL Workflow]**.

1. Selecteer **[!UICONTROL Create > Create Tag]**. Instellen **[!UICONTROL Title]** als `DAM` en **[!UICONTROL Name]** als `dam`. Selecteer **[!UICONTROL Submit]**.
   ![Tag maken in workflowmodel](assets/workflow_create_tag.png)

1. Ga naar **[!UICONTROL Tools > Workflow > Models]**. Selecteer **[!UICONTROL Request for Activation]** en selecteer vervolgens **[!UICONTROL Edit]**.

1. Selecteer **[!UICONTROL Edit]** , open dan **[!UICONTROL Workflow Model Properties]**. Go to the **[!UICONTROL Basic]** tab.

1. Toevoegen `Workflow : DAM` aan **[!UICONTROL Tags]** veld. Bevestig de selectie met de controle (kruis).

1. Bevestig de toevoeging van de tag met **[!UICONTROL Save & Close]**.
   ![Pagina-eigenschappen van model bewerken](assets/workflow_model_edit_activation1.png)

1. Voltooi het proces met **[!UICONTROL Sync]**. De workflow is nu beschikbaar in de interface voor aanraakbediening.

### Een workflow configureren voor ondersteuning van meerdere bronnen {#configuring-a-workflow-for-multi-resource-support}

U kunt een workflowmodel configureren voor [Multi Resource Support](/help/sites-developing/workflows.md#multi-resource-support) bij het maken van een nieuw model of door een bestaand model te bewerken:

1. Open het workflowmodel voor [bewerking](#editing-a-workflow).
1. Select **[!UICONTROL Workflow Model Properties]** from the toolbar.

1. Activeer **[!UICONTROL Multi Resource Support]** (of deactiveer desgewenst) in het dialoogvenster:

   ![wf-08](assets/wf-08.png)

1. Bevestig de wijziging met **[!UICONTROL Save & Close]**; gevolgd door **[!UICONTROL Sync]** (editor toolbar) om het runtimemodel te genereren.

   Zie [Uw workflow](#sync-your-workflow-generate-a-runtime-model) synchroniseren voor meer informatie.

### Werkstroomfasen configureren (die de voortgang van de workflow weergeven) {#configuring-workflow-stages-that-show-workflow-progress}

[Workflowfasen](/help/sites-developing/workflows.md#workflow-stages) helpen u de voortgang van een workflow bij het uitvoeren van taken te visualiseren.

>[!CAUTION]
>
>Als werkstroomfasen zijn gedefinieerd in **[!UICONTROL Page Properties]**, maar niet worden gebruikt voor een van de werkstroomstappen, wordt op de voortgangsbalk geen voortgang weergegeven (ongeacht de huidige werkstroomstap).

De stadia die beschikbaar moeten zijn, worden gedefinieerd in de workflowmodellen; bestaande workflowmodellen kunnen worden bijgewerkt met werkgebieddefinities. U kunt een willekeurig aantal fasen voor het workflowmodel definiëren.

U definieert als volgt **[!UICONTROL Stages]** voor uw workflow:

1. Open uw workflowmodel voor bewerking.
1. Select **[!UICONTROL Workflow Model Properties]** from the toolbar. Open vervolgens het **[!UICONTROL Stages]** tabblad.
1. Voeg uw vereiste gegevens toe (en plaats deze) **[!UICONTROL Stages]**. U kunt een willekeurig aantal fasen voor het workflowmodel definiëren.

   Bijvoorbeeld:

   ![wf-08-1](assets/wf-08-1.png)

1. Klik **[!UICONTROL Save & Close]** om de eigenschappen op te slaan.
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

1. Bevestig de wijzigingen met **[!UICONTROL Sync]** (editor-werkbalk) om het runtimemodel te genereren.

   Zie [Uw workflow](#sync-your-workflow-generate-a-runtime-model) synchroniseren voor meer informatie.

## Een workflowmodel exporteren in een pakket {#exporting-a-workflow-model-in-a-package}

1. Een nieuw pakket maken met [Pakketbeheer](/help/sites-administering/package-manager.md#package-manager):

   1. Navigeer aan de Manager van het Pakket als **[!UICONTROL Tools]**, **[!UICONTROL Deployment]**, **[!UICONTROL Packages]**.
   1. Klik op **[!UICONTROL Create Package]**.
   1. Geef de **[!UICONTROL Package Name]** gegevens en eventuele andere gegevens op.
   1. Klik op **[!UICONTROL OK]**.

1. Klik op **[!UICONTROL Edit]** de werkbalk van het nieuwe pakket.

1. Open het **[!UICONTROL Filters]** tabblad.

1. Selecteer **[!UICONTROL Add Filter]** en geef het pad van het *ontwerp* van het workflowmodel op:

   `/conf/global/settings/workflow/models/<*your-model-name*>`

   Klik op **[!UICONTROL Done]**.

1. Selecteer **[!UICONTROL Add Filter]** en geef het pad van het workflowmodel van de *runtime* op:

   `/var/workflow/models/<*your-model-name*>`

   Klik op **[!UICONTROL Done]**.

1. Voeg extra filters toe voor om het even welke douanescripts die door uw model worden gebruikt.
1. Klik **[!UICONTROL Save]** om uw filterdefinities te bevestigen.
1. Selecteer een optie **[!UICONTROL Build]** op de werkbalk van de pakketdefinitie.
1. Selecteer **[!UICONTROL Download]** de pakketwerkbalk.

## Workflows gebruiken om formulierverzendingen te verwerken {#using-workflows-to-process-form-submissions}

U kunt een formulier configureren voor verwerking door de geselecteerde workflow. Wanneer gebruikers het formulier verzenden, wordt een nieuwe werkstroominstantie gemaakt met de gegevens van het verzenden van het formulier als lading.

U configureert als volgt de workflow die met het formulier moet worden gebruikt:

1. Maak een nieuwe pagina en open deze voor bewerking.
1. Voeg een **[!UICONTROL Form]** component aan de pagina toe.
1. Configureer de **[!UICONTROL Form Start]** component die op de pagina werd weergegeven.
1. Kies **[!UICONTROL Start Workflow]** de gewenste workflow uit de beschikbare opties:

   ![wf-12](assets/wf-12.png)

1. Bevestig de nieuwe formulierconfiguratie met de tik.

## Testworkflows {#testing-workflows}

Het is een goede praktijk wanneer het testen van een werkschema om een verscheidenheid van ladingstypes te gebruiken; met inbegrip van typen die verschillen van de soorten waarvoor zij is ontwikkeld. Als u bijvoorbeeld van plan bent om in uw workflow te werken met Elementen, test u deze door een Pagina in te stellen als een payload en controleer of er geen fouten optreden.

Test bijvoorbeeld de nieuwe workflow als volgt:

1. [Start uw workflowmodel](/help/sites-administering/workflows-starting.md) vanaf de console.
1. Definieer het **[!UICONTROL Payload]** en bevestig het bestand.

1. Voer de vereiste handelingen uit zodat de workflow doorgaat.
1. Controleer de logbestanden terwijl de workflow wordt uitgevoerd.

U kunt ook AEM configureren om **[!UICONTROL DEBUG]** berichten in de logbestanden weer te geven. Zie [Logging](/help/sites-deploying/configure-logging.md) voor verdere informatie en wanneer de ontwikkeling wordt gebeëindigd, plaats de **[!UICONTROL Log Level]** terug aan **[!UICONTROL Info]**.

## Voorbeelden {#examples}

### Voorbeeld: Een (eenvoudige) workflow maken om een publicatieaanvraag te accepteren of af te wijzen {#example-creating-a-simple-workflow-to-accept-or-reject-a-request-for-publication}

In het volgende voorbeeld wordt een variatie in de `Publish Example` workflow gemaakt om enkele mogelijkheden voor het maken van een workflow te illustreren.

1. [Maak een nieuw workflowmodel](#creating-a-new-workflow).

   De nieuwe workflow bevat:

   * **[!UICONTROL Flow Start]**
   * `Step 1`
   * **[!UICONTROL Flow End]**

1. Verwijderen `Step 1` (omdat dit het verkeerde staptype is voor dit voorbeeld):

   * Klik op de stap en selecteer deze in de **[!UICONTROL Delete]** werkbalk van de component. Bevestig de handeling.

1. Sleep vanuit de **[!UICONTROL Workflow]** selectie van de stappenbrowser een bestand **[!UICONTROL Participant Step]** naar de workflow en plaats het tussen **[!UICONTROL Flow Start]** en **[!UICONTROL Flow End*]*.
1. U opent als volgt het dialoogvenster Eigenschappen:

   * Klik op de deelnemersstap en selecteer deze op de **[!UICONTROL Configure]** werkbalk van de component.
   * Dubbelklik op de stap voor deelnemers.

1. Voer op het **[!UICONTROL Common]** tabblad `Validate Content` voor zowel de **[!UICONTROL Title]** als **[!UICONTROL Description]**.
1. Open het **[!UICONTROL User/Group]** tabblad:

   * Activeer **[!UICONTROL Notify user via email]**.
   * Selecteer `Administrator` ( `admin`) voor het **[!UICONTROL User/Group]** veld.

   >[!NOTE]
   >
   >De gegevens van [de mailservice en gebruikersaccount moeten geconfigureerd](/help/sites-administering/notification.md)zijn voor het verzenden van e-mails.

1. Bevestig de updates met de tik.

   U wordt teruggestuurd naar het overzicht van het workflowmodel, waar de naam van de deelnemer is gewijzigd in `Validate Content`.

1. Sleep een **[!UICONTROL Or Split]** element naar de werkstroom en plaats deze tussen `Validate Content` en **[!UICONTROL Flow End]**.
1. Open het bestand **[!UICONTROL Or Split]** voor configuratie.
1. Configureren:

   * **[!UICONTROL Common]**: select **[!UICONTROL 2 Branches]**
   * **[!UICONTROL Branch 1]**: select **[!UICONTROL Default Route]**.
   * **[!UICONTROL Branch 2]**: ervoor zorgen **[!UICONTROL Default Route]** dat deze niet is geselecteerd.

1. Bevestig uw updates aan de **[!UICONTROL OR Split]**.
1. Sleep een **[!UICONTROL Participant Step]** naar de linkervertakking, open de eigenschappen, geef de volgende waarden op en bevestig de wijzigingen:

   * **[!UICONTROL Title]**: `Reject Publish Request`
   * **[!UICONTROL User/Group]**: bijvoorbeeld: `projects-administrators`
   * **[!UICONTROL Notify user via email]**: Activeer deze functie om de gebruiker per e-mail op de hoogte te stellen.

1. Sleep een **[!UICONTROL Process Step]** naar de rechtervertakking, open de eigenschappen, geef de volgende waarden op en bevestig de wijzigingen:

   * **[!UICONTROL Title]**: `Publish Page as Requested`
   * **[!UICONTROL Process]**: select `Activate Page`. Dit proces publiceert de geselecteerde pagina naar de uitgeversinstanties.

1. Klik op **[!UICONTROL Sync]** (editor-werkbalk) om het runtimemodel te genereren.

   Zie [Uw workflow](#sync-your-workflow-generate-a-runtime-model) synchroniseren voor meer informatie.

   Uw nieuwe workflowmodel ziet er als volgt uit:

   ![wf-13](assets/wf-13.png)

1. Pas deze workflow toe op de pagina, zodat gebruikers die naar **[!UICONTROL Complete]** de **[!UICONTROL Validate Content]** stap gaan, kunnen kiezen of ze **[!UICONTROL Publish Page as Requested]** of **[!UICONTROL Reject Publish Request]**.

   ![chlimage_1-182](assets/chlimage_1-182.png)

### Voorbeeld: Een regel definiëren voor een OR-splitsing {#example-defining-a-rule-for-an-or-split}

**[!UICONTROL OR Split]** Met de stappen kunt u voorwaardelijke verwerkingspaden in uw workflow opnemen.

Een OR-regel definiëren:

1. Maak twee scripts en sla deze op in de repository, bijvoorbeeld onder:

   `/apps/myapp/workflow/scripts`

   >[!NOTE]
   >
   >De scripts moeten een [functie hebben `check()`](#function-check) die een Booleaanse waarde retourneert.

1. Bewerk de workflow en voeg de code toe **[!UICONTROL OR Split]** aan het model.
1. Bewerk de eigenschappen van **[!UICONTROL Branch 1]** de **[!UICONTROL OR Split]**:

   * Definieer dit als de **[!UICONTROL Default Route]** voorinstelling door de waarde **[!UICONTROL Value]** in te stellen op `true`.
   * Stel het pad **[!UICONTROL Rule]** in op het script. Bijvoorbeeld:

      `/apps/myapp/workflow/scripts/myscript1.ecma`
   >[!NOTE]
   >
   >U kunt de vertakkingsvolgorde desgewenst wijzigen.

1. Bewerk de eigenschappen van de **[!UICONTROL Branch 2]** van de **[!UICONTROL OR Split]**.

   * Stel het pad **[!UICONTROL Rule]** in op het andere script. Bijvoorbeeld:

      `/apps/myapp/workflow/scripts/myscript2.ecma`

1. Stel de eigenschappen van de afzonderlijke stappen in elke vertakking in. Zorg ervoor dat het **[!UICONTROL User/Group]** is ingesteld.
1. Klik op **Synchroniseren** (editor-werkbalk) om uw wijzigingen in het runtimemodel voort te zetten.

   Zie [Uw workflow](#sync-your-workflow-generate-a-runtime-model) synchroniseren voor meer informatie.

#### Functie check() {#function-check}

>[!NOTE]
>
>Zie [ECMAScript](/help/sites-developing/workflows-customizing-extending.md#using-ecmascript)gebruiken.

Het volgende voorbeeldscript retourneert `true` als het knooppunt zich onder een `JCR_PATH` locatie bevindt `/content/we-retail/us/en`:

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

Bijvoorbeeld, **[!UICONTROL Request for Activation]**. Deze workflow wordt gebruikt voor het publiceren van pagina&#39;s binnen **[!UICONTROL Sites]** en wordt automatisch geactiveerd wanneer een auteur van inhoud niet de juiste replicatierechten heeft. Zie [Paginaontwerp aanpassen - De activeringsaanvraag](/help/sites-developing/customizing-page-authoring-touch.md#customizing-the-request-for-activation-workflow) aanpassen voor meer informatie.
