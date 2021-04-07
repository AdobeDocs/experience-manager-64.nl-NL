---
title: Forms-toepassingen en -taken beheren in AEM Postvak In
seo-title: Forms-toepassingen en -taken beheren in AEM Postvak In
description: Met AEM Inbox kunt u op Forms gerichte workflows starten door toepassingen in te dienen en taken te beheren.
seo-description: Met AEM Inbox kunt u op Forms gerichte workflows starten door toepassingen in te dienen en taken te beheren.
uuid: 5173558a-542a-4130-8bb6-5ac555ecc507
contentOwner: vishgupt
products: SG_EXPERIENCEMANAGER/6.3/FORMS
topic-tags: document_services, publish
discoiquuid: c1515c58-7d9a-4a36-9390-f6d6b980b801
exl-id: 7076807a-40ad-4f3b-beb0-70c1577a8ee7
translation-type: tm+mt
source-git-commit: bd94d3949f0117aa3e1c9f0e84f7293a5d6b03b4
workflow-type: tm+mt
source-wordcount: '923'
ht-degree: 0%

---

# Forms-toepassingen en -taken beheren in AEM Postvak IN {#manage-forms-applications-and-tasks-in-aem-inbox}

Een van de vele manieren om een Forms-centric workflow te starten of activeren is via toepassingen in AEM Inbox. U moet een workflowtoepassing maken om een Forms-workflow als toepassing beschikbaar te maken in Inbox. Voor meer informatie over werkschematoepassing en andere manieren om de werkschema&#39;s van Forms te lanceren, zie [Een Forms-centric werkschema op OSGi](/help/forms/using/aem-forms-workflow.md#launch) lanceren.

Daarnaast consolideert AEM Inbox meldingen en taken van verschillende AEM, waaronder Forms-workflows. Wanneer een formulierwerkstroom met een taakstap Toewijzen wordt geactiveerd, wordt de bijbehorende toepassing weergegeven als een taak in het Postvak In van de ontvanger. Als de toegewezen persoon een groep is, wordt de taak in het Postvak In van alle groepsleden weergegeven totdat een persoon de taak aanvraagt of delegeert.

De gebruikersinterface van Inbox verstrekt lijst en kalendermeningen om taken te bekijken. U kunt ook de weergave-instellingen configureren. U kunt taken filteren op basis van verschillende parameters. Voor meer informatie over mening en filters, zie [Uw Inbox](/help/sites-authoring/inbox.md).

Samenvattend kunt u met Inbox een nieuwe toepassing maken en toegewezen taken beheren.

>[!NOTE]
>
>U moet lid van de werkstroom-gebruikers groep zijn om AEM Inbox te kunnen gebruiken.

## Toepassing {#create-application} maken

1. Ga naar AEM Inbox bij `https://[server]:[port]/aem/inbox`.
1. Tik in de gebruikersinterface van het Postvak IN op **[!UICONTROL Create > Application]**. De pagina Select Application (Toepassing selecteren) wordt weergegeven.
1. Selecteer een toepassing en klik op **[!UICONTROL Create]**. Het adaptieve formulier dat aan de toepassing is gekoppeld, wordt geopend. Vul de formulieren in en tik **[!UICONTROL Submit]**. De bijbehorende workflow wordt gestart en er wordt een taak gemaakt in het Postvak In van de ontvanger.

## Taken beheren {#manage-tasks}

Wanneer een Forms-workflow wordt geactiveerd en u bent een ontvanger of onderdeel van de groep waaraan u bent toegewezen, wordt een taak weergegeven in uw Postvak In. U kunt taakdetails bekijken en beschikbare acties op de taak van binnen Inbox uitvoeren.

### Taken aanvragen of delegeren {#claim-or-delegate-tasks}

De taken die aan een groep worden toegewezen verschijnen in Inbox van alle groepsleden. Om het even welk groepslid kan die taak beweren of het aan een ander groepslid delegeren. Daartoe:

1. Tik om de miniatuur van de taak te selecteren. Opties voor het openen of delegeren van de taak worden bovenaan weergegeven.

   ![selecteren-taak](assets/select-task.png)

1. Voer een van de volgende handelingen uit:

   * Tik op **[!UICONTROL Delegate]** om de taak te delegeren. Het dialoogvenster Item delegeren wordt geopend. Selecteer een gebruiker, voeg desgewenst een opmerking toe en tik op **[!UICONTROL OK]**.

   ![gedelegeerde](assets/delegate.png)

   * Tik **[!UICONTROL Open]** om de taak op te eisen. Het dialoogvenster Toewijzen aan zelf wordt geopend. Tik **[!UICONTROL Proceed]** om de taak op te eisen. De geclaimde taak wordt met u weergegeven als de toegewezen persoon in uw Postvak IN.

   ![vordering](assets/claim.png)

### Details weergeven en handelingen uitvoeren op taken {#view-details-and-perform-actions-on-tasks}

Wanneer u een taak opent, kunt u taakdetails bekijken en beschikbare acties uitvoeren. De acties die beschikbaar zijn voor een taak worden gedefinieerd in de taakstap Toewijzen van de bijbehorende Forms-workflow.

1. Tik om de miniatuur van de taak te selecteren. Opties voor het openen of delegeren van de geselecteerde taak worden bovenaan weergegeven.
1. Tik **[!UICONTROL Open]** om taakdetails te bekijken en acties te ondernemen. De gedetailleerde taakweergave wordt geopend. In deze weergave kunt u taakdetails weergeven en acties ondernemen voor de taak.

   >[!NOTE]
   >
   >Als een taak aan een groep wordt toegewezen, moet u beweren het in gedetailleerde mening kan openen.

![taakdetails](assets/task-details.png)

De gedetailleerde taakmening omvat de volgende secties:

* Taakdetails
* formulier
* Workflowdetails
* Werkbalk Handelingen

#### Taakdetails {#task-details}

In de sectie Taakdetails wordt informatie over de taak weergegeven. De weergegeven informatie is afhankelijk van de configuratie-instellingen van de [Taakstap toewijzen](/help/sites-developing/workflows-step-ref.md) in de workflow. In het bovenstaande voorbeeld worden de beschrijving, de status, de begindatum en de workflow weergegeven die voor de taak worden gebruikt. U kunt hiermee ook een bestand aan de taak koppelen.

#### formulier {#form}

Op het tabblad Formulier in het hoofdinhoudsgebied worden het verzonden formulier en eventuele bijlagen op veldniveau weergegeven.

#### Workflowdetails {#workflow-details}

Het tabblad Workflowdetails bovenaan geeft de voortgang van de taak in verschillende fasen van de workflow weer. Het toont voltooide, huidige, en hangende stadia voor de taak. De stadia voor een werkschema worden bepaald in [Wijs taakstap](/help/sites-developing/workflows-step-ref.md) van het bijbehorende werkschema toe.

Bovendien geeft het tabblad de taakgeschiedenis weer voor elk voltooid werkgebied in de workflow. U kunt **[!UICONTROL View Details]** voor een voltooid stadium tikken om details over dat stadium te kennen. Er worden opmerkingen, formulier- en taakbijlagen, status, begin- en einddatums enzovoort over de taak weergegeven.

![workflowdetails](assets/workflow-details.png)

#### Werkbalk Handelingen {#actions-toolbar}

Op de werkbalk Handelingen staan alle beschikbare opties voor de taak. Terwijl sparen, het Terugstellen, en de Afgevaardigde standaardacties zijn, worden andere beschikbare acties gevormd in [taakstap toewijzen](/help/sites-developing/workflows-step-ref.md). In het bovenstaande voorbeeld worden Goedkeuren en Afwijzen geconfigureerd in de workflow.

Wanneer u de taak uitvoert, gaat deze verder in de workflow.

### Voltooide taken {#view-completed-tasks} weergeven

AEM In Postvak In worden alleen actieve taken weergegeven. Voltooide taken worden niet in de lijst weergegeven. U kunt echter Inbox-filters gebruiken om taken te filteren op basis van verschillende parameters, zoals taaktype, status, begin- en einddatum enzovoort. Voltooide taken weergeven:

1. Tik in AEM Inbox op ![toggle-side-panel1](assets/toggle-side-panel1.png) om de filterkiezer te openen.
1. Tik op **[!UICONTROL Task Status]** accordeon en selecteer **[!UICONTROL Complete]**. Alle voltooide taken worden weergegeven.

   ![filter-1](assets/filter-1.png)

1. Tik om een taak te selecteren en klik op **[!UICONTROL Open]**.

De taak wordt geopend om het document of het adaptieve formulier weer te geven dat aan de taak is gekoppeld. Voor een adaptief formulier wordt het alleen-lezen adaptieve formulier of het bijbehorende PDF-document met record weergegeven, zoals geconfigureerd op het tabblad Formulier/Document van de stappen [Taakworkflow toewijzen](/help/sites-developing/workflows-step-ref.md).

In de sectie met taakdetails wordt informatie weergegeven zoals de ondernomen actie, taakstatus, begindatum en einddatum.

![voltooide taak](assets/completed-task.png)

Op het tabblad **[!UICONTROL Workflow Details]** wordt elke stap van de workflow weergegeven. Tik **[!UICONTROL View details]** voor een stap voor gedetailleerde informatie.

![voltooid-taak-werkschema](assets/completed-task-workflow.png)
