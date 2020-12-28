---
title: Gegevens van paginaanalyse bekijken
seo-title: Gegevens van paginaanalyse bekijken
description: Gebruik pagina-analysegegevens om de doeltreffendheid van de pagina-inhoud te meten
seo-description: Gebruik pagina-analysegegevens om de doeltreffendheid van de pagina-inhoud te meten
uuid: 8dda89be-13e3-4a13-9a44-0213ca66ed9c
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: site-features
discoiquuid: 42d2195a-1327-45c0-a14c-1cf5ca196cfc
translation-type: tm+mt
source-git-commit: e99e29425578005ed9d215946d63f67e7229e8d6
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 0%

---


# Gegevens voor paginanalyse bekijken{#seeing-page-analytics-data}

Gebruik pagina-analysegegevens om de doeltreffendheid van de pagina-inhoud te meten.

## Analyse zichtbaar vanuit de console {#analytics-visible-from-the-console}

![aa-10](assets/aa-10.png)

De gegevens van de paginaanalyse worden getoond in [Lijstweergave](/help/sites-authoring/basic-handling.md#list-view) van de console van Plaatsen. Wanneer de pagina&#39;s in lijstformaat worden getoond, zijn de volgende kolommen beschikbaar door gebrek:

* Paginaweergaven
* Unieke bezoekers
* Tijd op pagina

In elke kolom wordt een waarde voor de lopende rapportageperiode weergegeven en wordt ook aangegeven of de waarde sinds de vorige rapportageperiode is gestegen of gedaald. De gegevens die u ziet, worden elke 12 uur bijgewerkt.

>[!NOTE]
>
>Als u de updateperiode wilt wijzigen, [configureert u het importinterval](/help/sites-administering/adobeanalytics-connect.md#configuring-the-import-interval).

1. Open de **Sites** console; bijvoorbeeld [http://localhost:4502/sites.html/content](http://localhost:4502/sites.html/content)
1. Rechtsboven op de werkbalk (in de rechterbovenhoek) klikt of tikt u op het pictogram om **Lijstweergave** te selecteren (het weergegeven pictogram is afhankelijk van de [huidige weergave](/help/sites-authoring/basic-handling.md#viewing-and-selecting-resources)).

1. Nogmaals, uiterst rechts op de werkbalk (rechterbovenhoek), klikt of tikt u op het pictogram en selecteert u **Instellingen weergeven**. Het dialoogvenster **Kolommen configureren** wordt geopend. Breng de vereiste wijzigingen aan en bevestig deze met **Update**.

   ![aa-04](assets/aa-04.png)

### De rapportageperiode {#selecting-the-reporting-period} selecteren

Selecteer de rapportperiode waarvoor de gegevens van Analytics op de console van Plaatsen verschijnen:

* Gegevens laatste 30 dagen
* Gegevens van afgelopen 90 dagen
* Gegevens van dit jaar

De huidige rapportageperiode wordt weergegeven op de werkbalk van de Sites-console (rechts van de bovenste werkbalk). Gebruik de vervolgkeuzelijst om de vereiste rapportageperiode te selecteren.\
![aa-05](assets/aa-05.png)

### Beschikbare gegevenskolommen {#configuring-available-data-columns} configureren

Leden van de analytische-beheerders gebruikersgroep kunnen de console van Plaatsen vormen om auteurs toe te laten om extra kolommen van Analytics te zien.

>[!NOTE]
>
>Wanneer een boomstructuur met pagina&#39;s onderliggende elementen bevat die zijn gekoppeld aan verschillende Adobe Analytics-wolkenconfiguraties, kunt u de beschikbare gegevenskolommen voor de pagina&#39;s niet configureren.

1. In de Mening van de Lijst, gebruik de meningsselecteurs (recht van toolbar), uitgezocht **de Montages van de Mening** en toen A **de Gegevens van de Analyse van de Douane toevoegen**.

   ![aa-15](assets/aa-15.png)

1. Selecteer de metriek die u aan auteurs in de console van Plaatsen wilt blootstellen, en dan **toevoegen** klikken.

   De kolommen die worden weergegeven, worden opgehaald uit Adobe Analytics.

   ![aa-16](assets/aa-16.png)

### Inhoudsgegevens van sites openen {#opening-content-insights-from-sites}

Open [Inzicht van inhoud](/help/sites-authoring/content-insights.md) van de console van Plaatsen om paginadoeltreffendheid verder te onderzoeken.

1. Selecteer in de Sites-console de pagina waarvoor u Inhoudsgegevens wilt weergeven.
1. Klik op het pictogram Analytics en Recommendations op de werkbalk.

   ![](do-not-localize/chlimage_1-16.png)

## Analyses zichtbaar in de Pagina-editor (Activity Map) {#analytics-visible-from-the-page-editor-activity-map}

>[!CAUTION]
>
>Vanwege beveiligingswijzigingen in de Adobe Analytics API is het niet langer mogelijk om de versie van de Activity Map te gebruiken die in AEM is opgenomen.
>
>De [ActivityMap-plug-in van Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/activity-map/getting-started/get-started-users/activitymap-install.html) moet nu worden gebruikt.
