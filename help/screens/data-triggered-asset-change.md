---
title: Gegevensgestuurde wijziging van bedrijfsmiddelen
seo-title: Gegevensgestuurde wijziging van bedrijfsmiddelen
description: Volg dit gebruiksvoorbeeld om te leren hoe u gepersonaliseerde inhoud kunt bereiken op basis van een bepaalde voorwaarde (bijvoorbeeld het weer van uw locatie).
seo-description: Volg dit gebruiksvoorbeeld om te leren hoe u gepersonaliseerde inhoud kunt bereiken op basis van een bepaalde voorwaarde (bijvoorbeeld het weer van uw locatie).
uuid: 8e557e4c-a6e2-4e4a-87bd-e01e2ff0043d
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.4/SCREENS
content-type: example
topic-tags: use-case-examples
discoiquuid: 878a2354-0990-4b21-b1ab-b9b33b50e353
translation-type: tm+mt
source-git-commit: cdec5b3c57ce1c80c0ed6b5cb7650b52cf9bc340

---


# Gegevensgestuurde wijziging van bedrijfsmiddelen{#data-triggered-asset-change}

## Omschrijving hoofdletter gebruiken {#use-case-description}

In dit gebruiksvoorbeeld wordt beschreven hoe u persoonlijke inhoud kunt maken op basis van het weer op uw locatie.

De volgende AEM schermt projecthefboomwerkingen AEM verpersoonlijking die ContextHub, de motor van de Segmentatie en de Inhoud richtend UI omvat.

Dit gebruiksgeval levert inhoud die op het huidige weer op elke plaats wordt gepersonaliseerd, als het weer:

* *zonnig, er zijn zomerkleding*
* *kou , winterkleding*

>[!NOTE]
>
>Voor demonstratiedoeleinden legt u met dit gebruiksgeval uw Geo-locatie vast om de update van de inhoud weer te geven. U kunt de weergave Geo-locatie van de uitvoer handmatig bijwerken in verschillende scenario&#39;s.

### Voorwaarden {#preconditions}

Zorg ervoor dat u begrijpt voordat u deze kwestie gaat gebruiken:

* [Personalisatie](/help/sites-administering/personalization.md)
* [ContextHub configureren](/help/sites-administering/contexthub-config.md)
* [Het vormen Segmentatie met ContextHub](/help/sites-administering/segmentation.md)
* [Authoring van getargete content met targetingmodus](/help/sites-authoring/content-targeting-touch.md)

### Primaire acteurs {#primary-actors}

Inhoudsauteurs

## Basisstroom: Het project instellen {#basic-flow-setting-up-the-project}

Voer de onderstaande stappen uit om een project op te zetten met daarin een overzicht van de wijzigingen in elementen die worden veroorzaakt door gegevens:

1. Maak een AEM-schermproject met de naam **DataTriggerAsset**, zoals hieronder wordt weergegeven.

   ![screen_shot_2019-02-28at120427pm](assets/screen_shot_2019-02-28at120427pm.png)

1. **Een volgend kanaal maken**

   1. Selecteer de map **Kanalen** en klik op **Maken** om de wizard te openen en een kanaal te maken.
   1. Selecteer het Kanaal **van de** Volgorde van de tovenaar en creeer het kanaal genoemd als **DataTrigger**.
   ![screen_shot_2019-02-28at120710pm](assets/screen_shot_2019-02-28at120710pm.png)

1. **Inhoud toevoegen aan Volgkanaal**

   1. Selecteer de **DataTrigger** van het kanaal.
   1. Klik op **Bewerken** op de actiebalk om de editor te openen. Sleep enkele elementen naar uw kanaal.
   ![screen_shot_2019-02-28at21511pm](assets/screen_shot_2019-02-28at21511pm.png)

   >[!NOTE]
   >
   >U moet de standaardafbeeldingen alleen aan de editor toevoegen. De beelden die u wilt worden vervangen, moeten aan de redacteur worden toegevoegd wanneer u op richtingswijze in stap (6) schakelt.

1. **Het plaatsen van ContextHub en het richten Configuraties**

   1. Navigeer naar **DataTriggerAsset** —> **Kanalen** —> **DataTrigger** en klik op **Eigenschappen** op de actiebalk.
   1. Klik op het tabblad **Aanpassing** .
   ![screen_shot_2019-02-28at10644pm](assets/screen_shot_2019-02-28at10644pm.png)

1. **ContextHub toevoegen en configuraties richten**

   1. Download het onderstaande inhoudspakket voor demo-doeleinden.
   1. Zodra u het pakket aan uw instantie AEM hebt gedownload, moet u de Weg van ContextHub en van Segmenten plaatsen:
   * Voor **ContextHub**, plaats de weg aan: ***/libs/settings/cloudsettings/legacy/contexthub***
   * Voor **Segmentpad** stelt u het pad in op: ***/conf/data-triggers/settings/wcm/segments***
   Gegevenstriggers

   [Bestand ophalen](assets/data-triggers-1_00.zip)

   >[!NOTE]
   >
   >Om over het vormen ContextHub en Segmentatie te leren, verwijs naar:
   >
   >* [ContextHub configureren](/help/sites-administering/contexthub-config.md)
   >* [Het vormen Segmentatie met ContextHub](/help/sites-administering/segmentation.md)


   ![screen_shot_2019-02-28at31502pm](assets/screen_shot_2019-02-28at31502pm.png)

   Klik op **Opslaan en sluiten**.

1. **Schakelen naar doelmodus**

   1. Navigeer naar **DataTriggerAsset** > **Kanalen** > **DataTrigger** en klik op **Bewerken** op de actiebalk.
   1. Selecteer **Doel** in de menubalk onder **Bewerken**.
   ![screen_shot_2019-02-28at21849pm](assets/screen_shot_2019-02-28at21849pm.png)

1. **De doelinhoud toevoegen**

   1. Selecteer **Data Triggers** in **BRAND** en **Seizoensgebonden Data-Trigger **in **ACTIVITEIT**.
   1. Klik op Doelgroep **starten**
   ![screen_shot_2019-02-28at31953pm](assets/screen_shot_2019-02-28at31953pm.png)

1. **De doelcomponent definiëren**

   1. Selecteer de component waarvoor u doelinhoud wilt hebben.
   1. Klik op de knop **Doel** om het aanwijzen voor die component in te schakelen.
   1. Definieer de inhoud voor elke variatie door de variatie in het **publiek** in de zijrail te selecteren en de inhoud zo nodig aan te passen.
   >[!NOTE]
   >
   >Als u het deelvenster **Elementen** in de editor wilt verbergen, moet u op de linkerpijl in het rechterzijpaneel klikken, zoals in de onderstaande afbeelding wordt getoond.

   ![target](assets/target.gif)

## De resultaten bekijken {#viewing-the-results}

Nadat u de voorgaande stappen hebt uitgevoerd, volgt u de stappen om een voorvertoning weer te geven van de resultaten:

1. Klik op **Voorvertoning** in de editor.

   ![target2](assets/target2.gif)

1. Om te tonen, hoe het beeld, afhankelijk van de plaats en verdere temperatuur van uw gebied zal veranderen, kunt u het pictogram ContextHub manueel klikken, zoals hieronder getoond.

   Zodra u de locatie bijwerkt, wordt de temperatuur van dat gebied vastgelegd en wordt de afbeelding bijgewerkt met de winterselectie en wordt de zomerselectie vervangen.

   ![target3](assets/target3.gif)

