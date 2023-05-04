---
title: Digitale middelen downloaden van [!DNL Adobe Experience Manager].
description: Leer hoe u elementen kunt downloaden van [!DNL Adobe Experience Manager] en schakelt u de downloadfunctionaliteit in of uit.
contentOwner: AG
feature: Asset Management,Asset Distribution
role: User
exl-id: bfe4d597-1080-4de5-a100-73a5175863d7
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '819'
ht-degree: 0%

---

# Elementen downloaden van [!DNL Adobe Experience Manager] {#download-assets-from-aem}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

U kunt elementen downloaden, zoals statische en dynamische uitvoeringen. U kunt ook e-mails met koppelingen naar middelen rechtstreeks verzenden vanuit [!DNL Adobe Experience Manager Assets]. Gedownloade elementen worden gebundeld in een ZIP-bestand. Het gecomprimeerde ZIP-bestand heeft een maximale bestandsgrootte van 1 GB voor de exporttaak. Er zijn maximaal 500 totale elementen per exporttaak toegestaan.

>[!NOTE]
>
>Ontvangers van e-mails moeten lid zijn van de `dam-users` groep voor toegang tot de ZIP-downloadkoppeling in het e-mailbericht. Om de elementen te kunnen downloaden, moeten de leden machtigingen hebben om workflows te starten die het downloaden van elementen activeren.

De elementtypen Afbeeldingssets, Spin-sets, Gemengde mediasets en Carousel-sets kunnen niet worden gedownload.

Voer de volgende stappen uit om elementen te downloaden:

1. Tik in de linkerbovenhoek van AEM op de knop [!DNL Experience Manager] logo, dan in de linkerspoorstaaf, tap **[!UICONTROL Navigation]**.
1. Tik op de navigatiepagina op **[!UICONTROL Assets]** > **[!UICONTROL Files.]**
1. Navigeer naar een map die elementen bevat die u wilt downloaden.
1. Selecteer de map of selecteer een of meer middelen in de map.
1. Tik op de werkbalk op **[!UICONTROL Download.]**

   ![Beschikbare opties voor het downloaden van middelen van Experience Manager Assets](/help/assets/assets/asset_download_dialog.png)

   *Afbeelding: Opties in het dialoogvenster Downloaden.*

1. Selecteer in het dialoogvenster Downloaden de gewenste downloadopties.

   | De optie Exporteren of downloaden | Beschrijving |
   |---|---|
   | **[!UICONTROL Create separate folder for each asset]** | Selecteer deze optie om elk element dat u downloadt, inclusief elementen, op te nemen in onderliggende mappen die onder de bovenliggende map van het element zijn genest in één map op uw lokale computer. Als deze optie niet standaard is geselecteerd, wordt de maphiërarchie genegeerd en worden alle elementen naar één map op uw lokale computer gedownload. |
   | **[!UICONTROL Email]** | Er wordt een e-mailbericht verzonden naar de gebruiker. De standaard e-mailsjablonen zijn beschikbaar op de volgende locaties:<ul><li>`/libs/settings/dam/workflow/notification/email/downloadasset`.</li><li>`/libs/settings/dam/workflow/notification/email/transientworkflowcompleted`.</li></ul> De malplaatjes die u tijdens plaatsing aanpast zijn beschikbaar bij de volgende plaatsen: <ul><li>`/apps/settings/dam/workflow/notification/email/downloadasset`.</li><li>`/apps/settings/dam/workflow/notification/email/transientworkflowcompleted`.</li></ul>U kunt huurdersspecifieke douanemalplaatjes bij de volgende plaatsen opslaan:<ul><li>`/conf/<tenant_specific_config_root>/settings/dam/workflow/notification/email/downloadasset`.</li><li>`/conf/<tenant_specific_config_root>/settings/dam/workflow/notification/email/transientworkflowcompleted`.</li></ul> |
   | **[!UICONTROL Assets]** | Selecteer deze optie als u het element in de oorspronkelijke vorm zonder vertoningen wilt downloaden.<br>De optie Subassets is beschikbaar als het oorspronkelijke element subassets heeft. |
   | **[!UICONTROL Renditions]** | Een vertoning is de binaire representatie van een element. Elementen hebben een primaire representatie, namelijk die van het geüploade bestand. Zij kunnen om het even welk aantal vertegenwoordiging hebben. <br> Met deze optie kunt u de uitvoeringen selecteren die u wilt downloaden. Welke uitvoeringen beschikbaar zijn, is afhankelijk van het element dat u selecteert. De optie is beschikbaar als het element uitvoeringen heeft. |
   | **[!UICONTROL Dynamic Renditions]** | Selecteer deze optie als u een reeks alternatieve vertoningen in real-time wilt genereren. Wanneer u deze optie selecteert, selecteert u ook de uitvoeringen die u dynamisch wilt maken door een optie in het menu [Voorinstelling afbeelding](image-presets.md) lijst. <br>Bovendien kunt u de grootte en maateenheid, de indeling, de kleurruimte, de resolutie en eventuele optionele afbeeldingsaanpassingen selecteren, zoals het omkeren van de afbeelding. De optie is alleen beschikbaar als u [!DNL Dynamic Media] ingeschakeld. |

1. Tik in het dialoogvenster op **[!UICONTROL Download.]**.

Wanneer u een map selecteert om te downloaden, wordt de volledige elementenhiërarchie onder de map gedownload. Selecteer **[!UICONTROL Create separate folder for each asset]**.

## Enable asset download servlet {#enable-asset-download-servlet}

De standaardserver [!DNL Experience Manager] Hiermee kunnen geverifieerde gebruikers willekeurig grote, gelijktijdige downloadaanvragen afgeven voor het maken van ZIP-bestanden met elementen die zichtbaar zijn voor hen die de server en het netwerk kunnen overbelasten. Om potentiële risico&#39;s van Dos te verlichten die door deze eigenschap worden veroorzaakt, `AssetDownloadServlet` De component OSGi is standaard uitgeschakeld voor publicatie-instanties.

Om het downloaden van activa van uw DAM toe te staan, bijvoorbeeld wanneer het gebruiken van iets zoals de Commons van het Aandeel van Activa of andere portaalachtige implementatie, laat manueel servlet via een configuratie OSGi toe. Adobe raadt u aan de toegestane downloadgrootte zo laag mogelijk in te stellen zonder dat dit van invloed is op de vereisten voor het dagelijks downloaden. Een hoge waarde kan van invloed zijn op de prestaties.

1. Een map maken met een naamgevingsconventie die is gericht op de publicatierunmode (`config.publish`): `/apps/<your-app-name>/config.publish`. Om configuratieeigenschappen voor een looppaswijze te bepalen, zie [Modi uitvoeren](/help/sites-deploying/configure-runmodes.md#defining-configuration-properties-for-a-run-mode).
1. Maak in de configuratiemap een bestand van het type `nt:file` benoemd `com.day.cq.dam.core.impl.servlet.AssetDownloadServlet.config`.
1. Vullen `com.day.cq.dam.core.impl.servlet.AssetDownloadServlet.config` met het volgende. Hiermee stelt u een maximale grootte (in bytes) in voor het downloaden als waarde van `asset.download.prezip.maxcontentsize`. In het onderstaande voorbeeld wordt de maximale grootte van de ZIP-download ingesteld op maximaal 100 kB.

   ```conf
   enabled=B"true"
   asset.download.prezip.maxcontentsize=I"102400"
   ```

## Asset Download-server uitschakelen {#disable-asset-download-servlet}

De `Asset Download Servlet` kan worden uitgeschakeld op een [!DNL Experience Manager] Publiceer instanties door de dispatcherconfiguratie bij te werken om het even welke verzoeken van de activadownload te blokkeren. servlet kan ook manueel via de console OSGi direct worden onbruikbaar gemaakt.

1. Als u aanvragen voor het downloaden van middelen wilt blokkeren via een dispatcherconfiguratie, bewerkt u de `dispatcher.any` configuratie en voeg een regel toe aan de [filtersectie](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html#configuring-access-to-content-filter). `/0100 { /type "deny" /url "*.assetdownload.zip/assets.zip*" }`

1. Om de component OSGi op een Publish instantie onbruikbaar te maken, heb toegang tot de Console OSGi bij `http://[aem_server]:[port]/system/console/components`. Zoeken `com.day.cq.dam.core.impl.servlet.AssetDownloadServlet` en klik op **[!UICONTROL Disable]**.

>[!MORELIKETHIS]
>
>* [Met DRM beveiligde middelen downloaden](drm.md).
>* [Elementen downloaden met de bureaubladtoepassing Experience Manager op Win- of Mac-computers](https://helpx.adobe.com/experience-manager/desktop-app/aem-desktop-app.html).
>* [Elementen downloaden met de Adobe Assets Link vanuit de ondersteunde Adobe Creative Cloud-apps](https://helpx.adobe.com/nl/enterprise/using/manage-assets-using-adobe-asset-link.html).

