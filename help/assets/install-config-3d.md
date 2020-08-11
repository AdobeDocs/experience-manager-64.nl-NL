---
title: AEM 3D installeren en configureren
seo-title: AEM 3D installeren en configureren
description: Leer hoe u AEM 3D installeert en configureert
seo-description: Leer hoe u AEM 3D installeert en configureert
uuid: a60732ff-fd66-4f29-b901-42a3cfd58b65
contentOwner: Rick Brough
topic-tags: 3D
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
discoiquuid: 5898d084-4b45-41bc-ad2e-2fcc65b0392c
translation-type: tm+mt
source-git-commit: 11b65cf2d180f04168d4c5d0929957c95a372e3c
workflow-type: tm+mt
source-wordcount: '1584'
ht-degree: 0%

---


# AEM 3D installeren en configureren {#installing-and-configuring-aem-d}

>[!IMPORTANT]
>
>AEM 3D in AEM 6.4 wordt niet meer ondersteund. Adobe raadt u aan de functie 3D-elementen in [AEM te gebruiken als Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/dynamicmedia/assets-3d.html) of [AEM 6.5.3 of hoger.](https://docs.adobe.com/content/help/en/experience-manager-65/assets/dynamic/assets-3d.html)

De installatie en configuratie van AEM 3D (versie 3.0) omvat het volgende:

1. De Autodesk® FBX® SDK-bibliotheek installeren.
1. Het native 3D-codepakket downloaden en installeren.
1. De 3D-workflow voor het opnemen van elementen configureren en AEM opnieuw starten.
1. De instellingen van AEM 3D valideren.

Zie ook [Werken met 3D-elementen](assets-3d.md).

Zie ook [AEM opmerkingen bij](/help/release-notes/aem3d-release-notes.md) de release 3D Assets voor voorwaarden, ondersteunde browsers en andere belangrijke informatie over releases.

Zie ook [Werken met de component](using-the-3d-sites-component.md)3D-sites.

>[!NOTE]
>
>Voordat u het 3D-pakket downloadt en installeert, moet u controleren of u alle vereiste AEM hebt geïnstalleerd. Zie de [AEM 3D-releaseopmerkingen.](install-config-3d.md)

## De Autodesk FBX SDK-bibliotheek installeren {#installing-the-autodesk-fbx-sdk-library}

De native AEM 3D-code vereist de Autodesk FBX-bibliotheek om de FBX-bestandsindeling te ondersteunen. (Adobe kan deze bibliotheek momenteel niet opnieuw distribueren.)

Zie ook [Geavanceerde configuratie-instellingen](advanced-config-3d.md).

1. Meld u aan bij de host waarop AEM is geïnstalleerd.

   * Als dit een plaatsing van de Server van Vensters is, registreer op de server als Beheerder.
   * Als dit een Desktop van MAC of van Vensters is, zorg ervoor u beheerdervoorrechten hebt.

1. Gebruik de koppeling die geschikt is voor uw besturingssysteem om **FBX SDK versie 2016.1.2 te downloaden**

   * **Windows**

      [https://download.autodesk.com/us/fbx_release_older/2016.1.2/fbx20161_2_fbxsdk_vs2010_win.exe](https://download.autodesk.com/us/fbx_release_older/2016.1.2/fbx20161_2_fbxsdk_vs2010_win.exe)

   * **OS X**

      [https://download.autodesk.com/us/fbx_release_older/2016.1.2/fbx20161_2_fbxsdk_clang_mac.pkg.tgz](https://download.autodesk.com/us/fbx_release_older/2016.1.2/fbx20161_2_fbxsdk_clang_mac.pkg.tgz)

   * **Linux**

      [https://download.autodesk.com/us/fbx_release_older/2016.1.2/fbx20161_2_fbxsdk_linux.tar.gz](https://download.autodesk.com/us/fbx_release_older/2016.1.2/fbx20161_2_fbxsdk_linux.tar.gz)

1. De FBX SDK installeren:

   * Windows. Installeer op hetzelfde station als AEM.
   * Mac. Installeren naar dezelfde partitie waar AEM zich bevindt.
   * Linux. Pak het gedownloade pakket uit en volg de instructies in `<yourFBXSDKpath>/Install_FbxFileSdk.txt`. Installeer de SDK waarop `/usr`.

## Het native 3D-codepakket downloaden en installeren {#downloading-and-installing-the-native-d-code-package}

>[!NOTE]
>
>Alvorens u met de installatie en de configuratie van AEM 3D te werk gaat, adviseert Adobe dat u om het even welke toepasselijke de dienstpakken en andere verwante eigenschapspakken opstelt. Zie [AEM opmerkingen bij de 3D-release](/help/release-notes/aem3d-release-notes.md).

Zie ook [Geavanceerde configuratie-instellingen](advanced-config-3d.md).

**U installeert als volgt het native 3D-codepakket**:

1. Voer een van de volgende handelingen uit:

   * Als dit een plaatsing van de Server van Vensters is, login aan de server als Beheerder.
   * Als dit een Mac- of Windows-bureaublad is, controleert u of u beheerdersrechten hebt.

1. Zorg ervoor dat er een ondersteunde browser beschikbaar is voor toegang tot AEM.

   Zie [Systeemvereisten](/help/release-notes/aem3d-release-notes.md#system-requirements).

1. Toegang tot [softwaredistributieportal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html). Zoek versie 3.0.1 van het `AEM-6.4-DynamicMedia-3D` functiepakket en download dit.

1. Klik in AEM op **[!UICONTROL Tools > Administration > Deployment > Package Manager]**.

1. Upload het gedownloade functiepakket naar AEM. Zoek het bestand en klik op **[!UICONTROL Install]**.

1. Vouw in het **[!UICONTROL Install Package]** dialoogvenster **Geavanceerde instellingen** uit en stel vervolgens in **[!UICONTROL Access Control Handling]** op **Samenvoegen**.
1. Klik **[!UICONTROL Install]** om de installatie van het pakket te starten.

   Het bestand `sample-3D-content.zip` wordt in de **[!UICONTROL Assets]** hoofdmap geplaatst. Zie De [instellingen van AEM 3D](#validating-the-setup-of-aem-d) valideren voor meer informatie.

## De workflow voor het opnemen van 3D-elementen configureren en AEM opnieuw starten {#configuring-the-d-asset-ingestion-workflow-and-restarting-aem}

**De workflow** voor het opnemen van 3D-elementen configureren:

1. Klik AEM op het AEM logo om de globale navigatieconsole te openen, klik vervolgens op het **[!UICONTROL Tools]** pictogram en navigeer naar **[!UICONTROL Workflow > Models]**.
1. Houd de muisaanwijzer boven de **[!UICONTROL Workflow Models]** workflow op de **[!UICONTROL DAM Update Asset]** pagina en selecteer het vinkje wanneer het selectievakje wordt weergegeven.

1. On the toolbar, click **[!UICONTROL Edit]**.
1. Klik op het **[!UICONTROL DAM Update Asset]** scherm in het zwevende deelvenster AEM op het **[!UICONTROL Plus]** pictogram rechts van Workflow om de lijst uit te vouwen. Selecteer **[!UICONTROL Process Step]** in de lijst.
1. Sleep **[!UICONTROL Process Step]** en zet het neer in het werkschema vlak voor **[!UICONTROL DAM Update Asset Workflow Completed]** component dichtbij het eind van het werkschema.

   ![3d_process_step_underaem6-4](assets/3d_process_step_underaem6-4.png)

1. Dubbelklik op de zojuist toegevoegde processtap.
1. Voer in het **[!UICONTROL Step Properties]** dialoogvenster onder het **[!UICONTROL Common]** tabblad in het **[!UICONTROL Title]** veld een geschikte beschrijving in voor het proces, zoals `Process 3D content`.
1. Click the **[!UICONTROL Process]** tab.

1. Selecteer in het **[!UICONTROL Process]** vervolgkeuzemenu de optie **[!UICONTROL Geometric 3D Object Service]** en selecteer vervolgens het **[!UICONTROL Handler Advance]** selectievakje.

   ![3d_install-process-steppropertiesdlg](assets/3d_install-process-steppropertiesdlg.png)

1. Klik in de rechterbovenhoek van het dialoogvenster op het pictogram van het vinkje om terug te keren naar de pagina Element voor DAM-update.
1. Klik in de rechterbovenhoek van de **[!UICONTROL DAM Update Asset]** pagina **[!UICONTROL Sync]** om het bewerkte workflowmodel op te slaan.
1. Start AEM opnieuw.

   Na het opnieuw opstarten kunt u 3D-inhoud uploaden en deze AEM verwerken.

   Ga verder met het [valideren van de instellingen van AEM 3D](#validating-the-setup-of-aem-d).

## De instellingen van AEM 3D valideren {#validating-the-setup-of-aem-d}

1. Klik in AEM op **[!UICONTROL Tools > Assets]**, download `sample-3D-content.zip`en vouw het gedownloade bestand uit. (U kunt nu verwijderen `sample-3D-content.zip` in AEM.)

   Zorg ervoor dat u in de resterende stappen bent om feedback over uploads en verwerking weer **[!UICONTROL Card View]** te geven.

1. Maak een map met de naam `test3d` om testinhoud te ontvangen.
1. Upload alle bestanden van `sample-3D-content/images` naar de `test3d` map.
1. Wacht tot het uploaden en verwerken is voltooid. Mogelijk moet u de browser vernieuwen.

   Upload de drie `.fbx` bestanden van `sample-3D-content/` naar de `test3d` map.

   Upload nog niet de .ma modeldossiers.

1. In de Mening van de Kaart, zie de berichtbanners die op 3d activakaarten worden getoond.

   Elk element gaat door verschillende verwerkingsstappen. Wanneer de **[!UICONTROL Creating Preview...]** verwerkingsstap is voltooid, wordt de kaart bijgewerkt met een miniatuurafbeelding. Wanneer de eindverwerking is voltooid, wordt de banner vervangen door de **[!UICONTROL NEW]** indicator.

   >[!NOTE]
   >
   >Verwacht een zeer hoog CPU-gebruik terwijl de 3D-verwerking bezig is. Afhankelijk van de beschikbare CPU-capaciteit kan het een aanzienlijke hoeveelheid tijd duren om alle verwerking te voltooien.

   ![screenshot_2017-01-2518-29-32](assets/screenshot_2017-01-2518-29-32.png)

1. Nu leert u hoe u bestandsafhankelijkheden kunt oplossen.

   Klik in de **[!UICONTROL Unresolved Dependencies]** banner voor de `stage-helipad.fbx` kaart op het **[!UICONTROL Exclamation Point]** pictogram om naar de eigenschappen van het element te navigeren en open het tabblad **Afhankelijkheden** .

   ![chlimage_1-372](assets/chlimage_1-372.png)

1. Klik op het **[!UICONTROL Folder/Magnifying Glass]** pictogram rechts van de bestandsnaam om de elementenbrowser te openen en de afhankelijkheden als volgt op te lossen:

   ![chlimage_1-373](assets/chlimage_1-373.png)

1. Klik op **[!UICONTROL Save]** en **[!UICONTROL Close]** om de verwerking van het element te voltooien en terug te keren naar **[!UICONTROL Card View]** het element.
1. Wanneer de verwerking volledig is, ziet u het volgende in **[!UICONTROL Card View]**:

   ![chlimage_1-374](assets/chlimage_1-374.png)

1. Klik op de pagina test3d op de `logo-sphere.fbx` kaart om het model te openen in **[!UICONTROL Detail View]**.

   Klik in de rechterbovenhoek van de pagina logo-sphere.fbx op het pictogram Werkgebiedspotlight om het vervolgkeuzemenu uit te vouwen en selecteer `stage-spotlights.fbx`.

   ![chlimage_1-375](assets/chlimage_1-375.png)

1. Selecteer in de vervolgkeuzelijst **[!UICONTROL Stage Spotlight]** de optie `stage-helipad.fbx`.

   De weergave aanpassen met de linkermuisknop. De achtergrond- en modelbelichting worden aangepast aan de nieuwe selectie in het werkgebied.

   ![chlimage_1-375](assets/chlimage_1-376.png)

## Ondersteuning voor Adobe Dimension-elementen configureren {#configuring-support-for-adobe-dimension-assets}

>[!NOTE]
>
>Deze configuratietaak is optioneel.

U kunt desgewenst ondersteuning configureren in AEM 3D voor Adobe Dimension-elementen.

U moet een externe conversieservice configureren om het invoegen, voorvertonen en publiceren van Adobe Dimension 3D-elementen in AEM toe te staan. De service converteert van de eigen Adobe Dimension-indeling (`.dn`) naar een variant van glTF (opgemaakt als een `.glb` bestand) die als uitvoering met het Dn-element wordt opgeslagen. De `.glb` vertoning wordt gebruikt voor webweergave van het 3D-element in AEM Assets, Sites en Schermen en is ook beschikbaar voor downloaden voor gebruik met toepassingen van derden.

>[!NOTE]
>
>De conversieservice wordt gehost door Adobe in Amazon AWS. Nadat de service correct is geconfigureerd, worden naar AEM geüploade `.dn` bestanden vervolgens veilig naar de conversieservice gekopieerd via tijdelijke opslag in Amazon S3. Het omzettingsresultaat wordt naar AEM overgedragen door middel van tijdelijke S3-opslag. Alle overdrachten en opslag worden beveiligd. Bovendien blijft de inhoud in S3 en de conversieservice slechts kort bestaan (doorgaans niet meer dan een paar minuten).

**Ondersteuning voor Adobe Dimension-elementen** configureren:

1. Neem contact op met uw Adobe AEM accountmanager, inrichtingsdeskundige of ondersteuningsmedewerker om referenties voor **AEM3D-services** aan te vragen.

   >[!NOTE]
   >
   >Er is slechts één set referenties vereist voor elke organisatie, ongeacht het aantal AEM instanties waarop de referenties zijn geïnstalleerd.

1. Controleer of u de volgende gegevens hebt ontvangen:

   * accountId
   * customerId
   * password
   * identityPoolId
   * userPoolId
   * clientId

1. Als Beheerder, registreer in uw AEM auteursinstantie waar u de geloofsbrieven geïnstalleerd wilt, dan open **[!UICONTROL CRXDE Lite]**.
1. Vorm de nieuwe geloofsbrieven door het volgende in CRXDE Lite te doen:

   1. Navigeer naar de nieuwe waarde `/libs/settings/dam/v3D/services/dncr` en stel de `clientId` eigenschap in.
   1. Navigeer naar `/libs/settings/dam/v3D/services/aws` en stel de eigenschappen `accountId`, `customerId`, `identityPoolId`en `userPoolId` in op de nieuwe waarden.
   1. Laad de nieuwe wachtwoordwaarde in de `encryptedPassword` eigenschap. Deze waarde wordt automatisch gecodeerd wanneer u tikt **[!UICONTROL Save All]**.
   1. Tik op de pagina **[!UICONTROL Save All]** en laad de pagina opnieuw en controleer vervolgens of de `encryptedPassword` eigenschap een andere tekenreeks tussen accolades weergeeft. Deze weergave geeft aan dat het wachtwoord correct is gecodeerd en beveiligd is.

1. Geef de indeling van de `.glb` conversie-uitvoering op door het volgende te doen in **[!UICONTROL CRXDE Lite]**:

   1. Navigeer naar `/libs/settings/dam/v3D/services/dncr` binnen **[!UICONTROL CRXDE Lite]**.
   1. Stel de `outputFormat` eigenschap in op `Dn` of `generic`.

      Wanneer deze optie is ingesteld op `Dn`, bevat de `.glb` conversie Adobe-specifieke extensies, zoals IBL-verlichting, voor de beste kwaliteit bij het bekijken van Dn-elementen in AEM. De omgezette .glb-uitvoering kan echter niet goed worden gerenderd in toepassingen van derden.

      Wanneer ingesteld op `generic`, is de `.glb` vertoning algemeen zonder Adobe-specifieke extensies. Met deze instelling kan het bestand worden gebruikt in toepassingen van derden, terwijl weergave met de AEM 3D-viewer visueel suboptimaal is.

1. Schakel de Dn-bestandsindeling als volgt in **[!UICONTROL CRXDE Lite]**:

   1. Ga naar `/libs/settings/dam/v3D/assetTypes/Dn`.
   1. Stel de `Enabled` eigenschap in op true.

1. Valideer de configuratie door het volgende te doen:

   1. Open AEM Assets.
   1. Uploaden `logo_sphere.dn` naar de `test3d` map. Het bestand bevindt zich in `sample-3D-content/models`.

      Let op: `sample-3D-content.zip` is eerder gedownload voor validatie van de standaard 3D-functionaliteit.
   1. Keer terug naar de **[!UICONTROL Card View]** en bekijk de berichtbanner die op het geüploade element wordt getoond. De **[!UICONTROL Converting Format...]** banner wordt weergegeven terwijl het conversieproces wordt uitgevoerd.
   1. Nadat alle verwerking is voltooid, opent u het element in **[!UICONTROL Detail View]** om te controleren of het omgezette element correct wordt weergegeven en of de navigatiebesturingselementen van de viewer bruikbaar zijn.

   ![image2018-11-2_15-51-19](assets/image2018-11-2_15-51-19.png)

   Als er **[!UICONTROL Card View]** na 10-15 minuten een verwerkingsfout wordt weergegeven op het Dn-element, is de conversie mislukt.

   Als dat het geval is, kunt u de omzetting problemen oplossen door het volgende te doen:

   * Verwijder het element en upload het vervolgens opnieuw.
   * Zorg ervoor dat u alle configuratieparameters correct hebt ingesteld in **[!UICONTROL CRXDE Lite]**.
   * Verifieer dat geen firewall toegang tot de omzettingsdienst en eindpunten van AWS blokkeert.
