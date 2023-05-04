---
title: Workflows toepassen op pagina's
seo-title: Applying Workflows to Pages
description: Workflows kunnen worden gestart vanuit de websiteconsole of, wanneer u een pagina bewerkt, vanuit Sidetrap.
seo-description: Workflows can be started from either the Websites console or, when editing a page, from Sidekick.
uuid: 55f6f1d7-da54-4732-b9ff-b7479622db51
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: site-features
discoiquuid: 22712b73-90f2-4329-b32f-dbb7ce802d1d
exl-id: f10680e5-e8ae-49a0-ae52-3aa1f22b2d3e
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 9%

---

# Workflows toepassen op pagina&#39;s{#applying-workflows-to-pages}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Wanneer u de workflow toepast, geeft u de volgende informatie op:

* De workflow die moet worden toegepast.

   U kunt elke workflow toepassen (waartoe u toegang hebt, zoals is toegewezen door uw AEM-beheerder).
* Optioneel:

   * Een opmerking met informatie over de reden waarom u de workflow hebt gestart.
   * Een titel die helpt de werkstroominstantie in Inbox van een gebruiker identificeren.

>[!NOTE]
>
>AEM beheerders kunnen workflows starten met [diverse andere methoden](/help/sites-administering/workflows-starting.md).

## Workflows toepassen {#applying-workflows}

Workflows kunnen worden gestart vanuit de websiteconsole of, wanneer u een pagina bewerkt, vanuit Sidetrap.

De **Status** in de **Websites** De console wijst erop of een werkschema op een pagina is toegepast:

![workflowstatus](assets/workflowstatus.png)

### Een workflow starten vanuit de websiteconsole {#starting-a-workflow-from-the-websites-console}

1. Open de websiteconsole. ([http://localhost:4502/siteadmin](http://localhost:4502/siteadmin))
1. Selecteer in de boomstructuur Websites het bovenliggende element van de pagina waarop u de workflow wilt toepassen.
1. Selecteer de pagina in de paginalijst en klik op Workflow.
1. Selecteer in het dialoogvenster Workflow starten de workflow die u wilt toepassen. Voer eventueel een opmerking en een titel in. Klik vervolgens op Start.

### Workflow starten met Sidetrap {#starting-a-workflow-using-sidekick}

1. Open de websiteconsole.
1. Open de gewenste pagina.
1. Selecteer het tabblad Workflow in de Sidetrap.
1. Breid uit **Workflow** , zodat u het dialoogvenster **Workflow** en naar keuze **Werkstroomtitel** en **Opmerking**.

   ![workflowstartsidekick](assets/workflowstartsidekick.png)

1. Klikken **Workflow starten** om een nieuwe werkschemainstantie met de eigenschappen te beginnen u vormde en de huidige pagina als lading. De workflow wordt nu uitgevoerd.
