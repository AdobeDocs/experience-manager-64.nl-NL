---
title: Offloader middelenwerkstroom
seo-title: Assets Workflow Offloader
description: Meer informatie over de Offloader voor de workflow Middelen.
seo-description: Learn about the Assets Workflow Offloader.
uuid: d1c93ef9-a0e1-43c7-b591-f59d1ee4f88b
contentOwner: Chiradeep Majumdar
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: content
content-type: reference
discoiquuid: 91f0fd7d-4b49-4599-8f0e-fc367d51aeba
exl-id: 2ca8e786-042b-44f6-ac60-834eca64f79f
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '628'
ht-degree: 0%

---

# Offloader middelenwerkstroom{#assets-workflow-offloader}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Met de Offloader van de workflow Middelen kunt u meerdere instanties van Adobe Experience Manager (AEM) Assets inschakelen om de verwerkingsbelasting van de primaire instantie (leader) te verminderen. De verwerkingsbelasting wordt verdeeld over de instantie leader en de verschillende instanties offloader (worker) die u eraan toevoegt. Door de verwerkingsbelasting van elementen te verdelen, verhoogt u de efficiëntie en snelheid waarmee AEM Assets elementen verwerkt. Daarnaast kunt u speciale bronnen toewijzen om elementen van een bepaald MIME-type te verwerken. Bijvoorbeeld, kunt u een specifieke knoop in uw topologie toewijzen om de activa van InDesign slechts te verwerken.

## Offloader-topologie configureren {#configure-offloader-topology}

Gebruik Configuration Manager om de URL voor de instantie leader en de hostnamen van instanties van offloader toe te voegen voor verbindingsaanvragen voor de instantie leader.

1. Tik/klik op het AEM en kies **Gereedschappen** > **Bewerkingen** > **Webconsole** om Configuration Manager te openen.
1. Selecteer in de webconsole de optie **Sling** >  **Topologiebeheer**.

   ![chlimage_1-44](assets/chlimage_1-44.png)

1. Tik of klik op de pagina Topology Management op de knop **Detectie configureren.Oak-service** koppeling.

   ![chlimage_1-45](assets/chlimage_1-45.png)

1. Geef op de pagina Configuratie van zoekservice de connector-URL voor de instantie leader op in het dialoogvenster **Topology Connector-URL&#39;s** veld.

   ![chlimage_1-46](assets/chlimage_1-46.png)

1. In de **Whitelist van de schakelaar van de topologie** veld, geef IP-adres of hostnamen op van instanties van offloader die verbinding mogen maken met de instantie leader. Tikken/klikken **Opslaan**.

   ![chlimage_1-47](assets/chlimage_1-47.png)

1. Ga naar **Gereedschappen** > **Implementatie** > **Topologie** en tik op of klik op de clusterweergave.

## Offloading uitschakelen {#disable-offloading}

1. Tik/klik op het AEM en kies **Gereedschappen** > **Implementatie** > **Verschuiven**. De **Browser verschuiven** De onderwerpen van paginavertoningen en de serverinstanties die de onderwerpen kunnen verbruiken.

   ![chlimage_1-48](assets/chlimage_1-48.png)

1. De opdracht *com/adobe/granite/workflow/offloading* onderwerp op de leaderinstanties waarmee gebruikers communiceren om AEM elementen te uploaden of te wijzigen.

   ![chlimage_1-49](assets/chlimage_1-49.png)

## Workflowdraagraketten configureren op de leaderinstantie {#configure-workflow-launchers-on-the-leader-instance}

Workflowdraagprogramma&#39;s configureren voor het gebruik van de **DAM Update Asset Offload** workflow op de instantie leader in plaats van op de **Dam Update-element** workflow.

1. Tik/klik op het AEM en kies **Gereedschappen** > **Workflow** > **Launchers** om de **Workflowstartprogramma&#39;s** console.

   ![chlimage_1-50](assets/chlimage_1-50.png)

1. Zoek de twee configuraties van Launcher met het gebeurtenistype **Knooppunt gemaakt** en **Knooppunt gewijzigd** die de **DAM Update-element** workflow.
1. Selecteer voor elke configuratie het selectievakje voor deze configuratie en tik op de knop **Eigenschappen weergeven** van de werkbalk om het pictogram weer te geven **Starteigenschappen** .

   ![chlimage_1-51](assets/chlimage_1-51.png)

1. Van de **Workflow** lijst, kiest u **DAM Update Asset Offload** en tik/klik **Opslaan**.

   ![chlimage_1-52](assets/chlimage_1-52.png)

1. Tik/klik op het AEM en kies **Gereedschappen** > **Workflow** > **Modellen** om de **Workflowmodellen** pagina.
1. Selecteer **DAM Update Asset Offload** workflow en tik/klik **Bewerken** op de werkbalk om de details weer te geven.

   ![chlimage_1-53](assets/chlimage_1-53.png)

1. Het contextmenu voor de **DAM-werkstroom verschuiven** stap en kies **Bewerken**. Controleer de invoer in het dialoogvenster **Taakonderwerp** van het **Algemene argumenten** tabblad van het configuratiedialoogvenster.

   ![chlimage_1-54](assets/chlimage_1-54.png)

## Workflowstartprogramma&#39;s uitschakelen op offloader-instanties {#disable-the-workflow-launchers-on-the-offloader-instances}

Schakel de workflowdraagprogramma&#39;s uit die de **DAM Update-element** workflow op de instantie leader.

1. Tik/klik op het AEM en kies **Gereedschappen** > **Workflow** > **Launchers** om de **Workflowstartprogramma&#39;s** console.

   ![chlimage_1-55](assets/chlimage_1-55.png)

1. Zoek de twee configuraties van Launcher met het gebeurtenistype **Knooppunt gemaakt** en **Knooppunt gewijzigd** die de **DAM Update-element** workflow.
1. Selecteer voor elke configuratie het selectievakje voor deze configuratie en tik op de knop **Eigenschappen weergeven** van de werkbalk om het pictogram weer te geven **Starteigenschappen** .

   ![chlimage_1-56](assets/chlimage_1-56.png)

1. Sleep in de sectie **Activeren **Sleep de schuifregelaar om de workflow voor het starten uit te schakelen en tik/klik op **Opslaan** om het uit te schakelen.

   ![chlimage_1-57](assets/chlimage_1-57.png)

1. Upload elk element van het type afbeelding bij de instantie leader. Verifieer de duimnagels die voor de activa door de geverschuiven instantie worden geproduceerd en worden teruggevoerd.
