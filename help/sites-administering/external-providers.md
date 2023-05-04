---
title: Analyse met externe providers
seo-title: Analytics with External Providers
description: Meer informatie over Analytics met externe providers.
seo-description: Learn about Analytics with External Providers.
uuid: bea8ec38-a190-46f9-a5fa-8d65321fdf20
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: integration
content-type: reference
discoiquuid: bf8fd156-4be9-43f8-8948-cf7f91c25f1b
exl-id: 6d906c2b-c8bc-4d54-9887-8aaeb6cc83d3
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 0%

---

# Analyse met externe providers{#analytics-with-external-providers}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Analyses kunnen u belangrijke en interessante informatie geven over het gebruik van uw website.

Verschillende configuraties buiten de box zijn beschikbaar voor integratie met de juiste service, bijvoorbeeld:

* [Adobe Analytics](/help/sites-administering/adobeanalytics.md)
* [Adobe Target](/help/sites-administering/target.md)

U kunt ook uw eigen instantie van de **Algemene analyseclusters** om nieuwe de dienstconfiguraties te bepalen.

De informatie wordt vervolgens verzameld door middel van kleine codefragmenten die aan de webpagina&#39;s worden toegevoegd. Bijvoorbeeld:

>[!CAUTION]
>
>Scripts mogen niet zijn ingesloten in `script` -tags.

```
var _gaq = _gaq || [];
_gaq.push(['_setAccount', 'UA-XXXXX-X']);
_gaq.push(['_trackPageview']);

(function() {
    var ga = document.createElement('script'); ga.type = 'text/javascript'; ga.async = true;
    ga.src = ('https:' == document.location.protocol ? 'https://ssl' : 'https://www') + '.google-analytics.com/ga.js';
    var s = document.getElementsByTagName('script')[0]; s.parentNode.insertBefore(ga, s);
})();
```

Met dergelijke fragmenten kunnen gegevens worden verzameld en rapporten worden gegenereerd. De werkelijk verzamelde gegevens zijn afhankelijk van de provider en het gebruikte codefragment. Voorbeelden van statistieken zijn:

* hoeveel bezoekers in de loop der tijd
* hoeveel pagina&#39;s zijn bezocht
* zoektermen gebruikt
* landingspagina&#39;s

>[!CAUTION]
>
>De demosite Geometrixx-buiten is zo geconfigureerd dat de kenmerken die worden opgegeven in de Pagina-eigenschappen worden toegevoegd aan de HTML-broncode (net boven de `</html>` endtag) in de bijbehorende `js` script.
>
>
>Als u uw eigen `/apps` niet overerven van de standaardpagina-component ( `/libs/foundation/components/page`) moet u (of uw ontwikkelaars) ervoor zorgen dat de overeenkomstige `js` scripts worden opgenomen, bijvoorbeeld door `cq/cloudserviceconfigs/components/servicescomponents`of met een soortgelijk mechanisme.
>
>
>Zonder dit, zal geen van de diensten (Generic, Analytics, Target, etc.) werken.

## Een nieuwe service maken met een algemeen fragment {#creating-a-new-service-with-a-generic-snippet}

Voor de basisconfiguratie:

1. Open de **Gereedschappen** console.

1. Vanuit het linkervenster uitvouwen **Configuraties van Cloud Services**.

1. Dubbelklikken op **Generic Analytics-fragment** om de pagina te openen:

   ![analytics_general overview](assets/analytics_genericoverview.png)

1. Klik op + om een nieuwe configuratie toe te voegen gebruikend de dialoog; minimaal een naam toewijzen, bijvoorbeeld google analytics:

   ![analytics_addconfig](assets/analytics_addconfig.png)

1. Klikken **Maken**, wordt het dialoogvenster met fragmenten direct geopend. U kunt het juiste JavaScript-fragment in het veld plakken:

   ![analytics_snippet](assets/analytics_snippet.png)

1. Klikken **OK** om op te slaan.

## Uw nieuwe service op pagina&#39;s gebruiken {#using-your-new-service-on-pages}

Nadat u de de dienstconfiguratie hebt gecreeerd moet u nu de vereiste pagina&#39;s vormen om het te gebruiken:

1. Navigeer naar de pagina.

1. Open de **Pagina-eigenschappen** van sidekick, dan **Cloud Services** tab.

1. Klikken **Service toevoegen** selecteert u vervolgens de gewenste service; bijvoorbeeld **Generic Analytics-fragment**:

   ![analytics_selectservice](assets/analytics_selectservice.png)

1. Klikken **OK** om op te slaan.

1. U wordt teruggestuurd naar de **Cloud Services** tab. De **Generic Analytics-fragment** wordt nu vermeld met het bericht `Configuration reference missing`. Gebruik de drop-down lijst om uw specifiek de dienstgeval te selecteren; bijvoorbeeld google-analytics:

   ![analytics_selectspecificservice](assets/analytics_selectspecificservice.png)

1. Klikken **OK** om op te slaan.

   Het fragment kan nu worden weergegeven als u de paginabron voor de pagina bekijkt.

   Nadat een geschikte periode is verstreken, kunt u de verzamelde statistieken bekijken.

   >[!NOTE]
   >
   >Als de configuratie aan een pagina in bijlage is die kindpagina&#39;s heeft, wordt de dienst ook geërft door die.
