---
title: Integreren met Adobe Search&Promote
seo-title: Integreren met Adobe Search&Promote
description: Leer hoe u kunt integreren met Adobe Search&Promote.
seo-description: Leer hoe u kunt integreren met Adobe Search&Promote.
uuid: ddc4510a-9bd1-4238-a8a8-5f4f563edd8d
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: integration
content-type: reference
discoiquuid: 87e62346-98d5-40ec-a3ef-904adf667425
exl-id: 2bbcc8d0-c1c7-4901-836f-44b8a2153a46
translation-type: tm+mt
source-git-commit: bd94d3949f0117aa3e1c9f0e84f7293a5d6b03b4
workflow-type: tm+mt
source-wordcount: '842'
ht-degree: 0%

---

# Integreren met Adobe Search&amp;Promote{#integrating-with-adobe-search-promote}

Voer de volgende taken uit om de service Adobe Search&amp;Promote van uw website aan te roepen:

1. Geef de URL van de cloud op.
1. Configureer de verbinding met de service Search&amp;Promote.
1. Voeg Search&amp;Promote-componenten toe aan [!UICONTROL Sidekick].
1. Gebruik de componenten om de inhoud te ontwerpen. (Zie [Search&amp;Promote toevoegen aan een webpagina](/help/sites-authoring/search-and-promote.md).)
1. Voeg banners toe aan uw pagina&#39;s. Bannerafbeeldingen zijn gevoelig voor Search&amp;Promote-gegevens.
1. Genereer een site-overzicht voor de service Search&amp;Promote die u wilt gebruiken.

>[!NOTE]
>
>Als u Search&amp;Promote met een configuratie van de douanevolmacht gebruikt, moet u zowel de volmachtsconfiguraties van de Cliënt van HTTP vormen aangezien sommige functionaliteiten van AEM de 3.x APIs en sommige anderen 4.x APIs gebruiken:
>
>* 3.x is geconfigureerd met [http://localhost:4502/system/console/configMgr/com.day.commons.httpclient](http://localhost:4502/system/console/configMgr/com.day.commons.httpclient)
>* 4.x wordt geconfigureerd met [http://localhost:4502/system/console/configMgr/org.apache.http.proxyconfigurator](http://localhost:4502/system/console/configMgr/org.apache.http.proxyconfigurator)

>



## De service-URL van de Search&amp;Promote wijzigen {#changing-the-search-promote-service-url}

De standaard URL die voor de dienst van de Search&amp;Promote wordt gevormd is `https://searchandpromote.omniture.com/px/`. Om de verschillende dienst te gebruiken, gebruik de console OSGi om een verschillende URL te specificeren.

**U wijzigt de service-URL** Search&amp;Promote als volgt:

1. Open de [!UICONTROL OSGi] console en tik **[!UICONTROL Configuration]** tabel. ([http://localhost:4502/system/console/configMgr.](http://localhost:4502/system/console/configMgr))

1. Klik op het item **[!UICONTROL Day CQ Search&Promote Configuration]**.
1. Voer in het tekstveld **[!UICONTROL Remote Server URI]** de URL in en tik op **[!UICONTROL Save]**.

## De verbinding met Search&amp;Promote {#configuring-the-connection-to-search-promote} configureren

Vorm één of meerdere verbindingen aan Search&amp;Promote zodat uw Web-pagina&#39;s met de dienst kunnen interactie aangaan. Als u verbinding wilt maken, hebt u de lididentificatie en het accountnummer van uw Search&amp;Promote-account nodig.

**De verbinding met Search&amp;Promote** configureren:

1. Selecteer **[!UICONTROL Cloud Services]** in het pictogram **[!UICONTROL Tools]** > **[!UICONTROL Deployment]**.

   Hiermee gaat u naar het dashboard van Cloud Services. Als de URL van het dashboard op een lokale machine er ongeveer als volgt uitziet:

   [http://localhost:4502/libs/cq/core/content/tools/cloudservices.html](http://localhost:4502/libs/cq/core/content/tools/cloudservices.html)

1. Tik op de pagina [!UICONTROL Cloud Services] op de koppeling **[!UICONTROL Adobe Search&Promote]** of op het pictogram **[!UICONTROL Search&Promote]**.

1. Als dit de eerste keer is dat u Adobe Search&amp;Promote configureert, tikt u op **[!UICONTROL Configure Now]** om het [!UICONTROL Create Configuration]-deelvenster te openen.

   Als u meer over Search&amp;Promote wilt leren klikt **[!UICONTROL Learn more]** in plaats daarvan.

   ![chlimage_1-409](assets/chlimage_1-409.png)

1. Voer een **[!UICONTROL Title]** in die herkenbaar is voor auteurs van pagina&#39;s en voer een unieke **[!UICONTROL Name]** in en tik vervolgens op **[!UICONTROL Create]**.

   Ook, verschijnt de pas gecreëerde Configuratie onder **[!UICONTROL Available Configurations]** op **[!UICONTROL Cloud Services dashboard]** de lijstitem van de Search&amp;Promote van de Adobe.

   ![chlimage_1-410](assets/chlimage_1-410.png)

1. Voeg in het dialoogvenster [!UICONTROL Edit Component] het volgende toe aan de velden:

   * **[!UICONTROL Member ID]**
   * **[!UICONTROL Account number]**

   >[!NOTE]
   >
   >Meld u aan bij het volgende om deze informatie zelf op te halen:
   >
   >[https://searchandpromote.omniture.com/center/](https://searchandpromote.omniture.com/center/)
   >
   >met uw geldige e-mail&amp;Promote referenties (e-mail/wachtwoord).
   >
   >Let op de URL in de adresbalk van de browser. Het zou iets gelijkaardig aan het volgende moeten kijken:
   >
   >[](https://searchandpromote.omniture.com/px/home/?sp_id=XXXXXXXX-spYYYYYYYY)
   >
   >[https://searchandpromote.omniture.com/px/home/?sp_id=XXXXXXXX-spYYYYYYYY](https://searchandpromote.omniture.com/px/home/?sp_id=XXXXXXXX-spYYYYYYYY)
   >
   >Waar **XXXXXXXX** overeenkomt met uw **[!UICONTROL Member id]** en **[!UICONTROL spYYYYYYYY]** komt overeen met uw accountnummer.

1. Tik op **[!UICONTROL Connect To Search&Promote]**.

   Tik **[!UICONTROL OK]** wanneer het bericht met het succes van de verbinding wordt weergegeven.

   (Na het verbinden, verandert de knooptekst in **[!UICONTROL Re-Connect To Search&Promote]**.)

1. Tik op **[!UICONTROL OK]**. De pagina Instellingen Search&amp;Promote wordt weergegeven voor de configuratie die u zojuist hebt gemaakt.

## Het vormen van het Centrum van Gegevens {#configuring-the-data-center}

Als uw Search&amp;Promote-account zich in Azië of Europa bevindt, moet u het standaarddatacenter zodanig wijzigen dat het naar het juiste datacenter wijst (het standaarddatacenter is voor Noord-Amerikaanse accounts).

**Het datacenter** configureren:

1. Navigeer naar de webconsole op `http://localhost:4502/system/console/configMgr/com.day.cq.searchpromote.impl.SearchPromoteServiceImpl`

   ![chlimage_1-411](assets/chlimage_1-411.png)

1. Wijzig afhankelijk van de locatie van de server de URI in een van de volgende:

   * Noord-Amerika: [https://center.atomz.com/px/](https://center.atomz.com/px/)
   * EMEA: [https://center.lon5.atomz.com/px/](https://center.lon5.atomz.com/px/)
   * APAC: [https://center.sin2.atomz.com/px/](https://center.sin2.atomz.com/px/)

1. Tik op **[!UICONTROL Save]**.

## Search&amp;Promote toevoegen aan Sidetrap {#adding-search-promote-components-to-sidekick}

Bewerk in de modus [!UICONTROL Design] een **[!UICONTROL par]**-component om de Search&amp;Promote-componenten toe te staan in [!UICONTROL Sidekick]. (Zie de documentatie [Components](/help/sites-developing/components.md) voor meer informatie.)

Voor informatie over het gebruiken van de componenten, zie [Search&amp;Promote eigenschappen toevoegen aan een Web-pagina](/help/sites-authoring/search-and-promote.md).

## De service Search&amp;Promote opgeven die uw pagina&#39;s gebruiken {#specifying-the-search-promote-service-that-your-pages-use}

Webpagina&#39;s configureren zodat deze een specifieke Search&amp;Promote-service gebruiken. Componenten van Search&amp;Promote gebruiken automatisch de service van hun hostpagina.

Wanneer u de Search&amp;Promote-eigenschappen voor een pagina configureert, nemen alle onderliggende pagina&#39;s de instellingen over. Indien nodig, kunt u kindpagina&#39;s vormen om de geërfte montages met voeten te treden.

>[!NOTE]
>
>De de dienstverbinding moet reeds worden gevormd. Zie [De verbinding aan Search&amp;Promote](#configuring-the-connection-to-search-promote) vormen.

1. Open het dialoogvenster **[!UICONTROL Page Properties]**. Klik bijvoorbeeld op de pagina **[!UICONTROL Websites]** met de rechtermuisknop op de pagina en klik op **[!UICONTROL Properties]**.

1. Klik op het tabblad **[!UICONTROL Cloud Services]**.

1. Als u de overerving van configuraties van cloudservices van een bovenliggende pagina wilt uitschakelen, klikt u op het hangslotpictogram naast het overervingspad.

   ![sandpinheritpadlock](assets/sandpinheritpadlock.png)

1. Klik **[!UICONTROL Add Service]**, selecteer **[!UICONTROL Adobe Search&Promote]**, dan klik **[!UICONTROL OK]**.

1. Selecteer de verbindingsconfiguratie voor uw Search&amp;Promote-account en klik op **[!UICONTROL OK]**.

## Productfeed {#product-feed}

Met de Search&amp;Promote-integratie kunt u het volgende doen:

* Gebruik de [!UICONTROL eCommerce] API, onafhankelijk van de onderliggende repository structuur en het handelsplatform.
* Gebruik de [!UICONTROL Index Connector] eigenschap van Search&amp;Promote om een productvoer in formaat van XML te verstrekken.
* Gebruik de [!UICONTROL Remote Control] eigenschap van Search&amp;Promote om op bestelling of geplande verzoeken van de productvoer uit te voeren.
* De productie van voer voor verschillende rekeningen van Search&amp;Promote, die als configuraties van de wolkendiensten worden gevormd.

Zie [Productfeed](/help/sites-administering/product-feed.md) voor meer informatie.
