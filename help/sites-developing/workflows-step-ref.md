---
title: Referentie workflowstap
seo-title: Referentie workflowstap
description: 'null'
seo-description: 'null'
uuid: 72a64495-d1b1-49e7-8257-d6b2ed36961c
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: extending-aem
content-type: reference
discoiquuid: 25f0e0f7-9570-4748-81cb-ccec6492c0b4
translation-type: tm+mt
source-git-commit: b698a1348df3ec2ab455c236422784d10cbcf7c2
workflow-type: tm+mt
source-wordcount: '2597'
ht-degree: 0%

---


# Referentie workflowstap{#workflow-step-reference}

De modellen van het werkschema bestaan uit een reeks stappen van diverse types. Volgens het type, kunnen deze stappen met parameters en manuscripten worden gevormd en worden uitgebreid om de functionaliteit te verstrekken en de controle u vereist.

>[!NOTE]
>
>In deze sectie worden de standaardworkflowstappen beschreven.
>
>Zie ook voor modulespecifieke stappen:
>
>* [AEM Forms Workflow Step Reference](/help/forms/using/aem-forms-workflow-step-reference.md)
>* [Middelen verwerken met behulp van mediafuncties en workflows](/help/assets/media-handlers.md)

>



## Stap-eigenschappen {#step-properties}

Elke stapcomponent heeft een **[!UICONTROL Step Properties]** dialoogvenster waarin u de vereiste eigenschappen kunt definiëren en bewerken.

### Step Properties - Common tab {#step-properties-common-tab}

Voor de meeste workflowstapcomponenten is een combinatie van de volgende eigenschappen beschikbaar op het tabblad **[!UICONTROL Common]** van het dialoogvenster Eigenschappen:

* **[!UICONTROL Title]**

   De titel voor de stap.

* **[!UICONTROL Description]**

   Een beschrijving van de stap.

* **[!UICONTROL Workflow Stage]**

   Een vervolgkeuzelijst om een [werkgebied](/help/sites-developing/workflows.md#workflow-stages) op de stap toe te passen.

* **[!UICONTROL Timeout]**

   De periode waarna de stap wordt &quot;uitgezet&quot;.

   U kunt kiezen tussen: **[!UICONTROL Off]**, **[!UICONTROL Immediate]**, **[!UICONTROL 1h]**, **[!UICONTROL 6h]**, **[!UICONTROL 12h]**, **[!UICONTROL 24h]**.

* **[!UICONTROL Timeout Handler]**

   De manager die het werkschema zal controleren wanneer de staptijden uit; bijvoorbeeld:

   `Auto Advancer`

* **[!UICONTROL Handler Advance]**

   Selecteer deze optie als u de workflow na de uitvoering automatisch wilt laten doorlopen naar de volgende stap. Als deze optie niet is geselecteerd, moet het implementatiescript de voortgang van de workflow afhandelen.

#### Step Properties - User/Group tab {#step-properties-user-group-tab}

De volgende eigenschappen zijn beschikbaar voor veel workflowstep-componenten op het tabblad **[!UICONTROL User/Group]** van het dialoogvenster Eigenschappen:

* **[!UICONTROL Notify user via email]**

   * U kunt deelnemers op de hoogte stellen door hen een e-mail te sturen wanneer de werkstroom de stap bereikt.
   * Indien ingeschakeld, wordt een e-mail verzonden naar de gebruiker die door de eigenschap **[!UICONTROL User/Group]** is gedefinieerd of naar elk lid van de groep als een groep is gedefinieerd.

* **[!UICONTROL User/Group]**

   * In een keuzelijst kunt u navigeren en een gebruiker of groep selecteren.
   * Als u de stap toewijst aan een specifieke gebruiker, kan alleen deze gebruiker actie ondernemen voor de stap.
   * Als u de stap toewijst aan een gehele groep, dan wanneer het werkschema deze stap bereikt zullen alle gebruikers in deze groep de actie in hun **[!UICONTROL Workflow Inbox]** hebben.
   * Zie [Deelnemen aan workflows](/help/sites-authoring/workflows-participating.md) voor meer informatie.

## EN splitsen {#and-split}

Met **[!UICONTROL AND Split]** wordt een splitsing in de workflow gemaakt, waarna beide vertakkingen actief zijn. U voegt workflowstappen naar wens toe aan elke vertakking. Met deze stap kunt u meerdere verwerkingspaden in de workflow opnemen. U kunt bijvoorbeeld toestaan dat bepaalde stappen van de revisie parallel worden uitgevoerd, zodat u tijd bespaart.

![wf-26](assets/wf-26.png)

### AND Split - Configuratie {#and-split-configuration}

* Bewerk de **[!UICONTROL AND Split]**-eigenschappen:

   * **[!UICONTROL Split Name]**: een naam voor verklarende doeleinden toewijzen.
   * Selecteer het aantal vereiste vertakkingen; 2, 3, 4 of 5.

* Voeg zo nodig workflowstappen toe aan de vertakkingen.

   ![wf-27](assets/wf-27.png)

## Containerstap {#container-step}

Met een stap **[!UICONTROL Container]** wordt een ander workflowmodel gestart dat als een onderliggende workflow wordt uitgevoerd.

Met deze **[!UICONTROL Container]** kunt u workflowmodellen opnieuw gebruiken om algemene stappen te implementeren. Een workflowmodel voor vertaling kan bijvoorbeeld worden gebruikt in meerdere bewerkingsworkflows.

![wf-28](assets/wf-28.png)

### Containerstap - configuratie {#container-step-configuration}

Om de stap te vormen, geef en gebruik de volgende lusjes uit:

* [**[!UICONTROL Common]**](#step-properties-common-tab)
* **[!UICONTROL Container]**

   * **[!UICONTROL Sub Workflow]**: Selecteer de workflow die u wilt starten.

## Ga naar stap {#goto-step}

Met **[!UICONTROL Goto Step]** kunt u de volgende stap in het workflowmodel opgeven die moet worden uitgevoerd, afhankelijk van het resultaat van een ECMAScript:

* `true`: De  **[!UICONTROL Goto Step]** voltooide bewerking en de workflow-engine voert de opgegeven stap uit.

* `false`: De  **[!UICONTROL Goto Step]** voltooide en normale verpletterende logica bepaalt de volgende stap uit te voeren.

**[!UICONTROL Goto Step]** laat u toe om geavanceerde verpletterende structuren in uw werkschemamodellen uit te voeren. Als u bijvoorbeeld een lus wilt implementeren, kunt u **[!UICONTROL Goto Step]** zo definiëren dat een eerdere stap in de workflow wordt uitgevoerd, waarbij het script een lusvoorwaarde evalueert.

### Ga naar stap - Configuratie {#goto-step-configuration}

Om de stap te vormen, geef en gebruik de volgende lusjes uit:

* [**[!UICONTROL Common]**](#step-properties-common-tab)
* **[!UICONTROL Process]**

   * **[!UICONTROL The step to go to]**: Selecteer de uit te voeren stap.
   * **[!UICONTROL Script Path]**: Het pad naar het ECMAScript dat bepaalt of het  **[!UICONTROL Goto Step]** moet worden uitgevoerd.
   * **[!UICONTROL Script]**: Het ECMAScript dat bepaalt of om het uit te voeren  **[!UICONTROL Goto Step]**.

>[!CAUTION]
>
>Geef **[!UICONTROL Script Path]** of **[!UICONTROL Script]** op. Beide opties kunnen niet tegelijkertijd worden gebruikt. Als u waarden voor beide eigenschappen opgeeft, wordt in de stap **[!UICONTROL Script Path]** gebruikt.

#### Een lus simuleren voor {#simulating-a-for-loop}

Wanneer u een lus for simuleert, moet u een telling bijhouden van het aantal herhalingen van lus dat is opgetreden:

* De telling vertegenwoordigt typisch een index van punten die op in het werkschema worden gehandeld.
* De telling wordt geëvalueerd als uitgangscriteria van de lijn.

Als u bijvoorbeeld een workflow wilt implementeren die een handeling uitvoert op verschillende JCR-knooppunten, kunt u een lusteller gebruiken als index voor de knooppunten. Als u het aantal wilt handhaven, slaat u een `integer`-waarde op in de gegevenskaart van de werkstroominstantie. Gebruik het manuscript van **[!UICONTROL Goto Step]** om de telling te verhogen evenals de telling te vergelijken met de uitgangscriteria.

```
function check(){
   var count=0;
   var keyname="loopcount"
   try{
      if (workflowData.getMetaDataMap().containsKey(keyname)){ 
        log.info("goto script: found loopcount key");
        count= parseInt(workflowData.getMetaDataMap().get(keyname))+1;
      } 
 
     workflowData.getMetaDataMap().put(keyname,count);
 
     }catch(err) {
         log.info(err.message);
         return false;
    }
   if (parseInt(count) <7){
       return true;
   } else {
      return false;
   }
}
```

## OF {#or-split} splitsen

Met **[!UICONTROL OR Split]** wordt een splitsing in de workflow gemaakt, waarna slechts één vertakking actief is. Met deze stap kunt u voorwaardelijke verwerkingspaden in uw workflow introduceren. U voegt workflowstappen naar wens toe aan elke vertakking.

>[!NOTE]
>
>Zie voor meer informatie over het maken van een OF-splitsing: [https://helpx.adobe.com/experience-manager/using/aem64_workflow_servlet.html](https://helpx.adobe.com/experience-manager/using/aem64_workflow_servlet.html)

![wf-29](assets/wf-29.png)

### OF Splitsen - Configuratie {#or-split-configuration}

* Bewerk de **[!UICONTROL OR Split]**-eigenschappen:

   * **[!UICONTROL Common]**

      * Selecteer het aantal vereiste vertakkingen; 2, 3, 4 of 5.
   * **[!UICONTROL Branch : *x *>]**

      * **[!UICONTROL Script Path]**: Het pad naar een bestand dat het script bevat.
      * **[!UICONTROL Script]**: Voeg het script toe in het vak.
      * **[!UICONTROL Default Route]**: De standaardvertakking wordt gevolgd wanneer meerdere vertakkingen true opleveren. U kunt slechts één vertakking als standaard opgeven.

   >[!NOTE]
   >
   >Er is een apart tabblad voor elke vertakking:
   >
   >* Het script van elke vertakking wordt één voor één geëvalueerd.
   >* De vertakkingen worden van links naar rechts geëvalueerd.
   >* Het eerste script dat true oplevert, wordt uitgevoerd.
   >* Als geen tak aan waar evalueert, dan gaat het werkschema niet vooruit.


   >[!CAUTION]
   >
   >Geef **[!UICONTROL Script Path]** of **[!UICONTROL Script]** op. Beide opties kunnen niet tegelijkertijd worden gebruikt. Als u waarden voor beide eigenschappen opgeeft, wordt in de stap **[!UICONTROL Script Path]** gebruikt.

   >[!NOTE]
   >
   >Zie [Een regel definiëren voor een OR-splitsing](/help/sites-developing/workflows-models.md#example-defining-a-rule-for-an-or-split).

* Voeg zo nodig workflowstappen toe aan de vertakkingen.

## Stappen en keuzen van deelnemers {#participant-steps-and-choosers}

### Stap {#participant-step} deelnemer

Met een **[!UICONTROL Participant Step]** kunt u de eigendom van een bepaalde handeling toewijzen. De workflow wordt alleen uitgevoerd wanneer de gebruiker de stap handmatig heeft bevestigd. Dit wordt gebruikt wanneer u iemand een actie op het werkschema wilt nemen; bijvoorbeeld een revisiestap.

Hoewel dit niet rechtstreeks verband houdt, moet bij de toewijzing van een actie rekening worden gehouden met de autorisatie van de gebruiker; de gebruiker moet toegang hebben tot de pagina die de nuttige werkstroom is.

#### Stap van de deelnemer - Configuratie {#participant-step-configuration}

Om de stap te vormen, geef en gebruik de volgende lusjes uit:

* [**[!UICONTROL Common]**](#step-properties-common-tab)
* [**[!UICONTROL User/Group]**](#step-properties-user-group-tab)

>[!NOTE]
>
>De aanvrager van de workflow wordt altijd op de hoogte gesteld wanneer:
>
>* De workflow is voltooid (voltooid).
>* De workflow is afgebroken (beëindigd).

>



>[!NOTE]
>
>Sommige eigenschappen moeten worden geconfigureerd om e-mailmeldingen in te schakelen. U kunt de e-mailsjabloon ook aanpassen of een e-mailsjabloon voor een nieuwe taal toevoegen. Zie [E-mailmelding configureren](/help/sites-administering/notification.md) om e-mailmeldingen in AEM te configureren.

### Stap {#dialog-participant-step} van deelnemer aan dialoogvenster

Gebruik een **[!UICONTROL Dialog Participant Step]** om informatie te verzamelen van de gebruiker aan wie het werkitem is toegewezen. Deze stap is nuttig om kleine hoeveelheden gegevens te verzamelen die later in het werkschema worden gebruikt.

Als de stap is voltooid, bevat het dialoogvenster **[!UICONTROL Complete Work Item]** de velden die u in het dialoogvenster definieert. De gegevens die in de velden worden verzameld, worden opgeslagen in knooppunten van de werkstroomlading. De volgende workflowstappen kunnen vervolgens de waarde van de repository lezen.

Om de stap te vormen, specificeert u de groep of de gebruiker om het het werkpunt aan toe te wijzen, en de weg aan de dialoog.

#### Stap van de Deelnemer van de dialoog - Configuratie {#dialog-participant-step-configuration}

Om de stap te vormen, geef en gebruik de volgende lusjes uit:

* [**[!UICONTROL Common]**](#step-properties-common-tab)
* [**[!UICONTROL User/Group]**](#step-properties-user-group-tab)
* **[!UICONTROL Dialog]**

   * **[!UICONTROL Dialog Path**]: Het pad naar het dialoogvenster van het [dialoogvenster dat u maakt](#dialog-participant-step-creating-a-dialog).

#### Stap van de Deelnemer van de dialoog - het Creëren van een dialoog{#dialog-participant-step-creating-a-dialog}

Een dialoogvenster maken:

* Bepaal waar de resulterende gegevens [worden opgeslagen in de lading](#dialog-participant-step-storing-data-in-the-payload).
* [De dialoog definiëren; dit omvat het definiëren van de velden die worden gebruikt voor het verzamelen (en opslaan) van de gegevens](#dialog-participant-step-dialog-definition).

#### Stap van de Deelnemer van de dialoog - het Opslaan van Gegevens in de Lading {#dialog-participant-step-storing-data-in-the-payload}

U kunt widgetgegevens opslaan in de werkstroomlading of in de meta-gegevens van het werkpunt. De indeling van de eigenschap `name` van het widgetknooppunt bepaalt waar de gegevens worden opgeslagen.

* **[!UICONTROL Store Data with the Payload]**

   * Als u widgetgegevens wilt opslaan als een eigenschap van de payload van de workflow, gebruikt u de volgende indeling voor de waarde van de eigenschap name van het widgetknooppunt:

      `./jcr:content/nodename`

   * De gegevens worden opgeslagen in het `nodename` bezit van de ladingsknoop. Als het knooppunt die eigenschap niet bevat, wordt de eigenschap gemaakt.
   * Wanneer opgeslagen met de lading, het verdere gebruik van de dialoog met de zelfde lading overschrijft de waarde van het bezit.

* **[!UICONTROL Store Data with the Work Item]**

   * Als u widgetgegevens wilt opslaan als een eigenschap van de metagegevens van het werkitem, gebruikt u de volgende indeling voor de waarde van de eigenschap name:

      `nodename`

   * De gegevens worden opgeslagen in het `nodename` bezit van het het werkpunt `metadata`. De gegevens blijven behouden als het dialoogvenster vervolgens wordt gebruikt met dezelfde payload.

#### Stap deelnemer van dialoogvenster - Dialoogdefinitie {#dialog-participant-step-dialog-definition}

1. **[!UICONTROL Dialog Structure]**

   De dialoogvensters voor de Stappen van de Deelnemer van de Dialoog zijn gelijkaardig aan dialogen die u voor auteurscomponenten creeert. Zij worden opgeslagen onder:

   `/apps/myapp/workflow/dialogs`

   Dialoogvensters voor de standaardinterface met aanraakbediening hebben de volgende knooppuntstructuur:

   ```xml
   newComponent (cq:Component)
     |- cq:dialog (nt:unstructured)
       |- content 
         |- layout 
           |- items 
             |- column 
               |- items 
                 |- component0
                 |- component1
                 |- ...
   ```

   >[!NOTE]
   >
   >Zie [Een dialoogvenster maken en configureren](/help/sites-developing/developing-components.md#creating-and-configuring-a-dialog) voor meer informatie.

1. **[!UICONTROL Dialog Path Property]**

   **[!UICONTROL Dialog Participant Step]** heeft de **[!UICONTROL Dialog Path]** bezit (samen met de eigenschappen van a [Stap van de Deelnemer](#participant-step)). De waarde van de eigenschap **[!UICONTROL Dialog Path]** is het pad naar het knooppunt `dialog` van het dialoogvenster.

   Het dialoogvenster is bijvoorbeeld opgenomen in een component met de naam `EmailWatch` die is opgeslagen in het knooppunt:

   `/apps/myapp/workflows/dialogs`

   Voor de interface met aanraakbediening wordt de volgende waarde gebruikt voor de eigenschap **[!UICONTROL Dialog Path]**:

   `/apps/myapp/workflow/dialogs/EmailWatch/cq:dialog`

   ![wf-30](assets/wf-30.png)

1. **Voorbeeld Dialoogdefinitie**

   Het volgende codefragment van XML vertegenwoordigt een dialoog die een `String` waarde in `watchEmail` knoop van de ladingsinhoud opslaat. Het titelknooppunt vertegenwoordigt de [component TextField](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/granite-ui/api/jcr_root/libs/granite/ui/components/coral/foundation/form/textfield/index.html):

   ```xml
   jcr:primaryType="nt:unstructured" 
       jcr:title="Watcher Email Address Dialog" 
       sling:resourceType="cq/gui/components/authoring/dialog">
       <content jcr:primaryType="nt:unstructured"
           sling:resourceType="granite/ui/components/foundation/container">
           <layout jcr:primaryType="nt:unstructured" 
               margin="false" 
               sling:resourceType="granite/ui/components/foundation/layouts/fixedcolumns"
           />
           <items jcr:primaryType="nt:unstructured">
               <column jcr:primaryType="nt:unstructured"
                   sling:resourceType="granite/ui/components/foundation/container">
                   <items jcr:primaryType="nt:unstructured">
                       <title jcr:primaryType="nt:unstructured" 
                           fieldLabel="Notification Email Address" 
                           name="./jcr:content/watchEmails"
                           sling:resourceType="granite/ui/components/foundation/form/textfield"
                       />
                   </items>
               </column>
           </items>
       </content>
   </cq:dialog>
   ```

   In het geval van de interface met aanraakbediening resulteert dit voorbeeld in een dialoogvenster zoals:

   ![chlimage_1-177](assets/chlimage_1-177.png)

### Dynamische deelnemersstap {#dynamic-participant-step}

De **[!UICONTROL Dynamic Participant Step]** component is gelijkaardig aan **[!UICONTROL Participant Step]** met het verschil dat de deelnemer automatisch bij runtime wordt geselecteerd.

Om de stap te vormen, selecteert u **[!UICONTROL Participant Chooser]** die de deelnemer identificeert om het het werkpunt aan, samen met een dialoog toe te wijzen.

#### Stap dynamische deelnemer - configuratie {#dynamic-participant-step-configuration}

Om de stap te vormen, geef en gebruik de volgende lusjes uit:

* [**[!UICONTROL Common]**](#step-properties-common-tab)
* **[!UICONTROL Participant Chooser]**

   * **[!UICONTROL Participant Chooser]**: De naam van de  [deelnemerkiezer die u maakt](#dynamic-participant-step-developing-the-participant-chooser).
   * **[!UICONTROL Arguments]**: Alle vereiste argumenten.
   * **[!UICONTROL Email]**: Of een e-mailbericht naar de gebruiker moet worden verzonden.

* **[!UICONTROL Dialog]**

   * **[!UICONTROL Dialog Path]**: Het pad naar het dialoogvenster van het  [dialoogvenster dat u maakt (zoals bij de stap **Deelnemer** dialoogvenster)](#dialog-participant-step-creating-a-dialog).

#### De dynamische Stap van de Deelnemer - ontwikkelt de deelnemerverkiezer {#dynamic-participant-step-developing-the-participant-chooser}

U maakt de deelnemerkiezer. Daarom kunt u om het even welke selectielogica of criteria gebruiken. Uw deelnemerkiezer kan bijvoorbeeld de gebruiker (binnen een groep) selecteren die de minste werkitems heeft. U kunt om het even welk aantal deelnemerverkiessers tot stand brengen om met verschillende instanties van de **Dynamische Stap** component van de Deelnemer in uw werkschemamodellen te gebruiken.

Creeer de dienst OSGi of een ECMAScript die een gebruiker selecteert om het het werkpunt aan toe te wijzen.

* **[!UICONTROL ECMAscript]**

   Scripts moeten een functie met de naam getParticipant bevatten die een gebruikers-id als een `String`-waarde retourneert. Sla uw aangepaste scripts op in bijvoorbeeld de map `/apps/myapp/workflow/scripts` of een submap.

   Een voorbeeldscript is opgenomen in een standaard AEM-instantie:

   `/libs/workflow/scripts/initiator-participant-chooser.ecma`

   >[!CAUTION]
   >
   >U *must* verandert niets in `/libs` weg.
   >
   >
   >Dit komt doordat de inhoud van `/libs` de volgende keer wordt overschreven dat u uw exemplaar bijwerkt (en kan worden overschreven wanneer u een hotfix of functiepakket toepast).

   Met dit script wordt de aanvrager van de workflow geselecteerd als de deelnemer:

   ```
   function getParticipant() {
       return workItem.getWorkflow().getInitiator();
   }
   ```

   >[!NOTE]
   >
   >De **[!UICONTROL Workflow Initiator Participant Chooser]** component breidt **[!UICONTROL Dynamic Participant Step]** uit en gebruikt dit manuscript als stapimplementatie.

* **[!UICONTROL OSGi service]**

   De diensten moeten [com.day.cq.workflow.exec.ParticipantStepChooser](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/workflow/exec/ParticipantStepChooser.html) interface uitvoeren. De interface definieert de volgende leden:

   * `SERVICE_PROPERTY_LABEL` veld: Gebruik dit veld om de naam van de deelnemerkiezer op te geven. De naam wordt weergegeven in een lijst met beschikbare deelnemerselecties in de eigenschappen **[!UICONTROL Dynamic Participant Step]**.
   * `getParticipant` methode: Retourneert de dynamisch opgeloste Principal-id als een  `String` waarde.

   >[!CAUTION]
   >
   >De `getParticipant` methode keert dynamisch gevormde Belangrijkste identiteitskaart terug. Dit kan een groep-id of een gebruikers-id zijn.
   >
   >
   >Nochtans, kan een groep identiteitskaart slechts voor **[!UICONTROL Participant Step]** worden gebruikt, wanneer een lijst van deelnemers is teruggekeerd. Voor een **[!UICONTROL Dynamic Participant Step]** is een lege lijst teruggekeerd en dit kan niet voor delegatie worden gebruikt.

   Als u uw implementatie beschikbaar wilt maken voor **[!UICONTROL Dynamic Participant Step]**-componenten, voegt u uw Java-klasse toe aan een OSGi-bundel die de service exporteert en implementeert u de bundel op de AEM server.

   >[!NOTE]
   >
   >**[!UICONTROL Random Participant Chooser]** is een voorbeeldservice waarmee u een willekeurige gebruiker (  `com.day.cq.workflow.impl.process.RandomParticipantChooser`) selecteert. Het voorbeeldformulier voor de stapcomponent **[!UICONTROL Random Participant Chooser]** breidt **[!UICONTROL Dynamic Participant Step]** uit en gebruikt deze service als de stapimplementatie.

#### Stap dynamische deelnemer - Voorbeeld van Kiezerservice deelnemer {#dynamic-participant-step-example-participant-chooser-service}

De volgende klasse Java implementeert de interface `ParticipantStepChooser`. De klasse retourneert de naam van de deelnemer die de workflow heeft gestart. De code gebruikt de zelfde logica die het steekproefmanuscript ( `initator-participant-chooser.ecma`) gebruikt.

Met de annotatie `@Property` wordt de waarde van het veld `SERVICE_PROPERTY_LABEL` ingesteld op `Workflow Initiator Participant Chooser`.

```java
package com.adobe.example;

import org.apache.felix.scr.annotations.Component;
import org.apache.felix.scr.annotations.Properties;
import org.apache.felix.scr.annotations.Property;
import org.apache.felix.scr.annotations.Service;
import org.osgi.framework.Constants;
import org.slf4j.Logger;
import org.slf4j.LoggerFactory;

import com.adobe.granite.workflow.WorkflowException;
import com.adobe.granite.workflow.WorkflowSession;
import com.adobe.granite.workflow.exec.ParticipantStepChooser;
import com.adobe.granite.workflow.exec.WorkItem;
import com.adobe.granite.workflow.metadata.MetaDataMap;

@Component
@Service
@Properties({
        @Property(name = Constants.SERVICE_DESCRIPTION, value = "An example implementation of a dynamic participant chooser."),
        @Property(name = ParticipantStepChooser.SERVICE_PROPERTY_LABEL, value = "Workflow Initiator Participant Chooser (service)") })
public class InitiatorParticipantChooser implements ParticipantStepChooser {

 private Logger logger = LoggerFactory.getLogger(this.getClass());

 public String getParticipant(WorkItem arg0, WorkflowSession arg1,
   MetaDataMap arg2) throws WorkflowException {

  String initiator = arg0.getWorkflow().getInitiator();
  logger.info("Assigning Dynamic Participant Step work item to {}",initiator);

  return initiator;
 }
}
```

In het dialoogvenster **[!UICONTROL Dynamic Participant Step]** eigenschappen bevat de lijst **[!UICONTROL Participant Chooser]** het item `Workflow Initiator Participant Chooser (script)`, dat deze service vertegenwoordigt.

&quot;Wanneer het werkschemamodel is begonnen, wijst het logboek op identiteitskaart van de gebruiker die het werkschema in werking stelde en wie het het werkpunt wordt toegewezen. In dit voorbeeld is de `admin`-gebruiker begonnen met de workflow.

`13.09.2015 15:48:53.037 *INFO* [10.176.129.223 [1347565733037] POST /etc/workflow/instances HTTP/1.1] com.adobe.example.InitiatorParticipantChooser Assigning Dynamic Participant Step work item to admin`

### Stap {#form-participant-step} voor deelnemer aan formulier

De **[!UICONTROL Form Participant Step]** presenteert een formulier wanneer het werkitem wordt geopend. Wanneer de gebruiker het formulier invult en verzendt, worden de veldgegevens opgeslagen in de knooppunten van het taakvenster van de werkstroom.

Als u de stap wilt configureren, geeft u de groep of gebruiker op waaraan het werkitem moet worden toegewezen en het pad naar het formulier.

>[!CAUTION]
>
>Deze sectie behandelt de [sectie van Forms van de Componenten van de Stichting voor de Authoring van de Pagina](/help/sites-authoring/default-components-foundation.md#form).

#### Stap van de deelnemer van de vorm - Configuratie {#form-participant-step-configuration}

Om de stap te vormen, geef en gebruik de volgende lusjes uit:

* [**[!UICONTROL Common]**](#step-properties-common-tab)
* [**[!UICONTROL User/Group]**](#step-properties-user-group-tab)
* **[!UICONTROL Form]**

   * **[!UICONTROL Form Path]**: Het pad naar het  [formulier dat u maakt](#form-participant-step-creating-the-form).

#### Stap van de Deelnemer van de vorm - Creërend de vorm {#form-participant-step-creating-the-form}

Maak een formulier voor gebruik met een **[!UICONTROL Form Participant Step]** als normaal. Formulieren voor een stap Formulierdeelnemer moeten echter de volgende configuraties hebben:

* Voor de **[!UICONTROL Start of Form]**-component moet de eigenschap **[!UICONTROL Action Type]** zijn ingesteld op `Edit Workflow Controlled Resource(s)`.

* De **[!UICONTROL Start of Form]** component moet een waarde voor `Form Identifier` bezit hebben.

* Voor de formuliercomponenten moet de eigenschap **Elementnaam** zijn ingesteld op het pad van het knooppunt waar de veldgegevens zijn opgeslagen. Het pad moet een knooppunt in de ladingsinhoud van de workflow vinden. De waarde gebruikt de volgende indeling:

   `./jcr:content/path_to_node`

* Het formulier moet een **[!UICONTROL Workflow Submit Button(s)]**-component bevatten. U vormt geen eigenschappen van de component.

De vereisten van uw workflow bepalen waar u veldgegevens moet opslaan. U kunt bijvoorbeeld veldgegevens gebruiken om de eigenschappen van pagina-inhoud te configureren. Met de volgende waarde van een eigenschap **[!UICONTROL Element Name]** worden veldgegevens opgeslagen als de waarde van de eigenschap `redirectTarget` van het knooppunt `jcr:content`:

`./jcr:content/redirectTarget`

In het volgende voorbeeld worden de veldgegevens gebruikt als de inhoud van een **[!UICONTROL Text]**-component op de ladingspagina:

`./jcr:content/par/text_3/text`

&quot;Het eerste voorbeeld kan worden gebruikt voor elke pagina die de component `cq:Page` weergeeft. Het tweede voorbeeld kan slechts worden gebruikt wanneer de ladingspagina een **component Text** omvat die een identiteitskaart van `text_3` heeft.

Het formulier kan overal in de gegevensopslagruimte worden gevonden, maar workflowgebruikers moeten worden gemachtigd om het formulier te lezen.

### Kiezer voor willekeurige deelnemers {#random-participant-chooser}

De stap **[!UICONTROL Random Participant Chooser]** is een deelnemerverkiezer die het geproduceerde het werkpunt aan een gebruiker toewijst die willekeurig uit een lijst wordt geselecteerd.

![wf-31](assets/wf-31.png)

#### Kiezer voor willekeurige deelnemers - Configuratie {#random-participant-chooser-configuration}

Om de stap te vormen, geef en gebruik de volgende lusjes uit:

* [**[!UICONTROL Common]**](#step-properties-common-tab)
* **[!UICONTROL Arguments]**

   * **[!UICONTROL Participants]**: Hier geeft u de lijst op met gebruikers die kunnen worden geselecteerd. Als u een gebruiker aan de lijst wilt toevoegen, klikt u op **[!UICONTROL Add Item]** en typt u het beginpad van het gebruikersknooppunt of de gebruikers-id. De volgorde van de gebruikers heeft geen invloed op de waarschijnlijkheid dat een werkitem wordt toegewezen.

### Kiezer {#workflow-initiator-participant-chooser} voor deelnemer aan workflowinitiator

De stap **[!UICONTROL Workflow Initiator Participant Chooser]** is een deelnemerverkiezer die het geproduceerde het werkpunt aan de gebruiker toewijst die de werkschema begon. Er zijn geen andere eigenschappen om te configureren dan de **[!UICONTROL Common]**-eigenschappen.

#### Deelnemerkiezer voor workflow-initiator - Configuratie {#workflow-initiator-participant-chooser-configuration}

Om de stap te vormen, geef het gebruiken van de volgende lusjes uit:

* [**[!UICONTROL Common]**](#step-properties-common-tab)

## Processtap {#process-step}

Een **[!UICONTROL Process Step]** stelt een ECMAScript in werking of roept de dienst OSGi om automatische verwerking uit te voeren.

![wf-32](assets/wf-32.png)

### Processtap - Configuratie {#process-step-configuration}

Om de stap te vormen, geef en gebruik de volgende lusjes uit:

* [**[!UICONTROL Common]**](#step-properties-common-tab)
* **[!UICONTROL Process]**

   * **[!UICONTROL Process]**: De uit te voeren procesimplementatie. Gebruik het drop-down menu om de dienst te selecteren ECMAScript of OSGi. Voor informatie over:

      * De standaard ECMAScripts en OSGi diensten, zie [Ingebouwde Processen voor de Stappen van het Proces](/help/sites-developing/workflows-process-ref.md).
      * Creërend ECMAScripts voor een **[!UICONTROL Process]** stap, zie [Uitvoerend een Stap van het Proces met een ECMAScript](/help/sites-developing/workflows-customizing-extending.md#using-ecmascript).
      * Creërend de diensten OSGi voor een **[!UICONTROL Process]** stap, zie [Implementerend een Stap van het Proces met een Klasse van Java](/help/sites-developing/workflows-customizing-extending.md#implementing-a-process-step-with-a-java-class).
   * **[!UICONTROL Handler Advance]**: Selecteer deze optie als u de workflow na de uitvoering automatisch wilt laten terugkeren naar de volgende stap. Als deze optie niet is geselecteerd, moet het implementatiescript de voortgang van de workflow afhandelen.
   * **[!UICONTROL Arguments]**: Argumenten die aan het proces moeten worden doorgegeven.


