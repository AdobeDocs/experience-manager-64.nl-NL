---
title: AEM 3D installeren en configureren
seo-title: AEM 3D installeren en configureren
description: Leer AEM 3D installeren en configureren
seo-description: Leer AEM 3D installeren en configureren
uuid: a60732ff-fd66-4f29-b901-42a3cfd58b65
contentOwner: Rick Brough
topic-tags: 3D
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
discoiquuid: 5898d084-4b45-41bc-ad2e-2fcc65b0392c
translation-type: tm+mt
source-git-commit: e2bb2f17035e16864b1dc54f5768a99429a3dd9f

---


# AEM 3D installeren en configureren {#installing-and-configuring-aem-d}

De installatie en configuratie van AEM 3D (versie 3.0) omvat het volgende:

1. De Autodesk® FBX® SDK-bibliotheek installeren.
1. Het native 3D-codepakket downloaden en installeren.
1. De workflow voor het opnemen van 3D-elementen configureren en AEM opnieuw starten.
1. De instellingen van AEM 3D valideren.

Zie ook [Werken met 3D-elementen](assets-3d.md).

Zie ook de opmerkingen [bij de release van](/help/release-notes/aem3d-release-notes.md) AEM 3D Assets voor voorwaarden, ondersteunde browsers en andere belangrijke informatie over releases.

Zie ook [Werken met de component](using-the-3d-sites-component.md)3D-sites.

>[!NOTE]
>
>Voordat u het 3D-pakket downloadt en installeert, moet u controleren of alle vereiste AEM-pakketten correct zijn geïnstalleerd. Zie de opmerkingen bij de release van [AEM 3D.](install-config-3d.md)

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

   * Windows. Installeer op hetzelfde station als waar AEM zich bevindt.
   * Mac. Installeer op dezelfde partitie als AEM.
   * Linux. Pak het gedownloade pakket uit en volg de instructies in `<yourFBXSDKpath>/Install_FbxFileSdk.txt`. Installeer de SDK waarop `/usr`.

## Het native 3D-codepakket downloaden en installeren {#downloading-and-installing-the-native-d-code-package}

>[!NOTE]
>
>Voordat u verdergaat met de installatie en configuratie van AEM 3D, raadt Adobe u aan eventuele toepasselijke servicepacks en andere gerelateerde functiepakketten te implementeren. Zie Opmerkingen bij de [release van AEM 3D](/help/release-notes/aem3d-release-notes.md).

Zie ook [Geavanceerde configuratie-instellingen](advanced-config-3d.md).

**U installeert als volgt het native 3D-codepakket**:

1. Voer een van de volgende handelingen uit:

   * Als dit een plaatsing van de Server van Vensters is, login aan de server als Beheerder.
   * Als dit een Mac- of Windows-bureaublad is, controleert u of u beheerdersrechten hebt.

1. Zorg ervoor dat er een ondersteunde browser beschikbaar is voor toegang tot AEM.

   Zie [Systeemvereisten](/help/release-notes/aem3d-release-notes.md#system-requirements).

1. Meld u met behulp van een ondersteunde browser aan bij AEM met beheerdersrechten.
1. Klik in AEM op het AEM-logo voor toegang tot de algemene navigatieconsole, klik vervolgens op het pictogram **[!UICONTROL Gereedschappen]** en navigeer naar **[!UICONTROL Beheer > Implementatie > Delen]** pakket.
1. Op de Adobe-pagina gebruikt u uw Adobe-id-gegevens om u aan te melden bij uw Adobe Creative Cloud-account.
1. Zoek op de pagina met Adobe-pakketten versie 3.0.1 van het `AEM-6.4-DynamicMedia-3D` functiepakket en download het.

1. Klik in AEM op **[!UICONTROL Gereedschappen > Beheer > Implementatie > Pakketbeheer]**.
1. Zoek het gedownloade functiepakket en klik op **[!UICONTROL Installeren]**.

1. Vouw in het dialoogvenster Pakket **** installeren de optie **Geavanceerde instellingen** uit en stel vervolgens de verwerking **[!UICONTROL van]** toegangsbeheer in op **Samenvoegen**.
1. Klik op **[!UICONTROL Installeren]** om de installatie van het pakket te starten.

   Het bestand `sample-3D-content.zip` wordt in de hoofdmap **[!UICONTROL Middelen]** geplaatst. Zie [De installatie van AEM 3D](#validating-the-setup-of-aem-d) valideren voor meer informatie.

## De workflow voor het opnemen van 3D-elementen configureren en AEM opnieuw starten {#configuring-the-d-asset-ingestion-workflow-and-restarting-aem}

**De workflow** voor het opnemen van 3D-elementen configureren:

1. Klik in AEM op het AEM-logo voor toegang tot de algemene navigatieconsole, klik vervolgens op het pictogram **[!UICONTROL Gereedschappen]** en navigeer naar **[!UICONTROL Workflow > Modellen]**.
1. Houd de muisaanwijzer op de pagina **[!UICONTROL Workflowmodellen]** boven de workflow **[!UICONTROL DAM Update Asset]** en selecteer het selectievakje wanneer het vinkje wordt weergegeven.

1. Klik op **[!UICONTROL Bewerken]** op de werkbalk.
1. Klik in het scherm **[!UICONTROL DAM Update Asset]** (element **[!UICONTROL DAM bijwerken) in het zwevende AEM-venster op het]** plustekenrechts van Workflow om de lijst uit te vouwen. Selecteer **[!UICONTROL Processtap]** in de lijst.
1. Sleep **[!UICONTROL de Stap]** van het Proces en laat vallen het in het werkschema net vóór de **[!UICONTROL component van de Werkstroom van het Activum van de Update van DAM voltooide]** component dichtbij het eind van het werkschema.

   ![3d_process_step_underaem6-4](assets/3d_process_step_underaem6-4.png)

1. Dubbelklik op de zojuist toegevoegde processtap.
1. Voer in het dialoogvenster **[!UICONTROL Step Properties]** onder het tabblad **[!UICONTROL Common]** in het veld **[!UICONTROL Title]** een geschikte beschrijving in voor het proces, zoals `Process 3D content`.
1. Klik op het tabblad **[!UICONTROL Proces]** .

1. Selecteer in het keuzemenu **[!UICONTROL Proces]** de optie **[!UICONTROL Geometrische 3D-objectservice]** en schakel vervolgens het selectievakje **[!UICONTROL Handler Advance]** in.

   ![3d_install-process-steppropertiesdlg](assets/3d_install-process-steppropertiesdlg.png)

1. Klik in de rechterbovenhoek van het dialoogvenster op het pictogram van het vinkje om terug te keren naar de pagina Element voor DAM-update.
1. Klik in de rechterbovenhoek van de pagina **[!UICONTROL DAM Update Asset]** op **[!UICONTROL Synchroniseren]** om het bewerkte workflowmodel op te slaan.
1. Start AEM opnieuw.

   Na het opnieuw opstarten kunt u 3D-inhoud uploaden en deze door AEM laten verwerken.

   Ga verder met het [valideren van de installatie van AEM 3D](#validating-the-setup-of-aem-d).

## De instellingen van AEM 3D valideren {#validating-the-setup-of-aem-d}

1. Klik in AEM op **[!UICONTROL Gereedschappen > Middelen]**, download `sample-3D-content.zip`en vouw het gedownloade bestand uit. (U kunt nu verwijderen `sample-3D-content.zip` in AEM.)

   Zorg ervoor dat u in de **[!UICONTROL Kaartweergave]** werkt om het uploaden en het verwerken van feedback in de resterende stappen te bekijken.

1. Maak een map met de naam `test3d` om testinhoud te ontvangen.
1. Upload alle bestanden van `sample-3D-content/images` naar de `test3d` map.
1. Wacht tot het uploaden en verwerken is voltooid. Mogelijk moet u de browser vernieuwen.

   Upload de drie `.fbx` bestanden van `sample-3D-content/` naar de `test3d` map.

   Upload nog niet de .ma modeldossiers.

1. In de Mening van de Kaart, zie de berichtbanners die op 3d activakaarten worden getoond.

   Elk element gaat door verschillende verwerkingsstappen. **[!UICONTROL Wanneer Voorvertoning]** maken... als de verwerking is voltooid, wordt de kaart bijgewerkt met een miniatuurafbeelding. Wanneer de uiteindelijke verwerking is voltooid, wordt de banner vervangen door de **[!UICONTROL NIEUWE]** indicator.

   >[!NOTE]
   >
   >Verwacht een zeer hoog CPU-gebruik terwijl de 3D-verwerking bezig is. Afhankelijk van de beschikbare CPU-capaciteit kan het een aanzienlijke hoeveelheid tijd duren om alle verwerking te voltooien.

   ![screenshot_2017-01-2518-29-32](assets/screenshot_2017-01-2518-29-32.png)

1. Nu leert u hoe u bestandsafhankelijkheden kunt oplossen.

   Voor de **[!UICONTROL Onopgeloste banner van Afhankelijkheden]** voor de `stage-helipad.fbx` kaart, klik het pictogram van het Punt **[!UICONTROL van de]** Uitroepie om aan de eigenschappen van de activa te navigeren en de **Afhankelijkheden** te openen tabel.

   ![chlimage_1-372](assets/chlimage_1-372.png)

1. Klik op het pictogram **[!UICONTROL Map/Vergrootglas]** rechts van de bestandsnaam om de elementenbrowser te openen en de afhankelijkheden als volgt op te lossen:

   ![chlimage_1-373](assets/chlimage_1-373.png)

1. Klik op **[!UICONTROL Opslaan]** en **[!UICONTROL Sluiten]** om de verwerking van het element te voltooien en terug te keren naar de **[!UICONTROL Kaartweergave]**.
1. Wanneer de verwerking is voltooid, ziet u het volgende in de **[!UICONTROL Kaartweergave]**:

   ![chlimage_1-374](assets/chlimage_1-374.png)

1. Klik op de pagina test3d op de `logo-sphere.fbx` kaart om het model te openen in de **[!UICONTROL gedetailleerde weergave]**.

   Klik in de rechterbovenhoek van de pagina logo-sphere.fbx op het pictogram Werkgebiedspotlight om het vervolgkeuzemenu uit te vouwen en selecteer `stage-spotlights.fbx`.

   ![chlimage_1-375](assets/chlimage_1-375.png)

1. Selecteer in de vervolgkeuzelijst **[!UICONTROL Werkgebiedspotlight]** de optie `stage-helipad.fbx`.

   De weergave aanpassen met de linkermuisknop. De achtergrond- en modelbelichting worden aangepast aan de nieuwe selectie in het werkgebied.

   ![chlimage_1-376](assets/chlimage_1-376.png)

## Ondersteuning voor Adobe Dimension-middelen configureren {#configuring-support-for-adobe-dimension-assets}

>[!NOTE]
>
>Deze configuratietaak is optioneel.

U kunt desgewenst ondersteuning configureren in AEM 3D voor Adobe Dimension-elementen.

U moet een externe conversieservice configureren om het invoegen, voorvertonen en publiceren van Adobe Dimension 3D-middelen in AEM toe te staan. De service converteert van de eigen Adobe Dimension-indeling (`.dn`) naar een variant van glTF (opgemaakt als een `.glb` bestand) die als uitvoering met het Dn-element wordt opgeslagen. De `.glb` vertoning wordt gebruikt voor webweergave van het 3D-element in AEM Assets, Sites en Screens en is ook beschikbaar voor downloaden voor gebruik met toepassingen van derden.

>[!NOTE]
>
>De conversieservice wordt door Adobe gehost in Amazon AWS. Nadat de service op de juiste wijze is geconfigureerd, worden naar AEM geüploade `.dn` bestanden vervolgens veilig naar de conversieservice gekopieerd via tijdelijke opslag in Amazon S3. Het omzettingsresultaat wordt door tijdelijke S3-opslag teruggezet naar AEM. Alle overdrachten en opslag worden beveiligd. Bovendien blijft de inhoud in S3 en de conversieservice slechts kort bestaan (doorgaans niet meer dan een paar minuten).

**Ondersteuning configureren voor Adobe Dimension-elementen**:

1. Neem contact op met uw Adobe AEM-accountmanager, inrichtingsdeskundige of ondersteuningsmedewerker om referenties aan te vragen voor **AEM3D Services**.

   >[!NOTE]
   >
   >Er is slechts één set referenties vereist voor elke organisatie, ongeacht het aantal AEM-instanties waarop de referenties zijn geïnstalleerd.

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
   1. Laad de nieuwe wachtwoordwaarde in de `encryptedPassword` eigenschap. Deze waarde wordt automatisch gecodeerd wanneer u op Alles **** opslaan tikt.
   1. Tik op Alles **** opslaan, laad de pagina opnieuw en controleer vervolgens of de `encryptedPassword` eigenschap een andere tekenreeks tussen accolades weergeeft. Deze weergave geeft aan dat het wachtwoord correct is gecodeerd en beveiligd is.

1. Geef de indeling van de `.glb` conversie-uitvoering op door het volgende te doen in **[!UICONTROL CRXDE Lite]**:

   1. Navigeer naar `/libs/settings/dam/v3D/services/dncr` in **[!UICONTROL CRXDE Lite]**.
   1. Stel de `outputFormat` eigenschap in op `Dn` of `generic`.

      Wanneer deze optie is ingesteld op `Dn`, bevat de `.glb` conversie Adobe-specifieke extensies, zoals IBL-belichting, voor de beste kwaliteit bij het weergeven van Dn-elementen in AEM. De omgezette .glb-uitvoering kan echter niet goed worden gerenderd in toepassingen van derden.

      Wanneer deze optie is ingesteld op `generic`, is de `.glb` vertoning algemeen zonder Adobe-specifieke extensies. Met deze instelling kan het bestand worden gebruikt in toepassingen van derden, terwijl weergave met de AEM 3D-viewer visueel suboptimaal is.

1. Schakel de Dn-bestandsindeling als volgt in **[!UICONTROL CRXDE Lite]** in:

   1. Navigeer naar `/libs/settings/dam/v3D/assetTypes/Dn`.
   1. Stel de `Enabled` eigenschap in op true.

1. Valideer de configuratie door het volgende te doen:

   1. Open AEM-elementen.
   1. Uploaden `logo_sphere.dn` naar de `test3d` map. Het bestand bevindt zich in `sample-3D-content/models`.

      Let op: `sample-3D-content.zip` is eerder gedownload voor validatie van de standaard 3D-functionaliteit.
   1. Keer terug naar de **[!UICONTROL Kaartweergave]** en bekijk de berichtenbanner die op het geüploade element wordt weergegeven. **[!UICONTROL De]** conversie-indeling... wordt de banner weergegeven terwijl het conversieproces wordt uitgevoerd.
   1. Nadat alle verwerking is voltooid, opent u het element in de **[!UICONTROL gedetailleerde weergave]** om te controleren of het omgezette element correct wordt weergegeven en of de navigatie-elementen van de viewer bruikbaar zijn.
   ![image2018-11-2_15-51-19](assets/image2018-11-2_15-51-19.png)

   Als er na 10-15 minuten een &quot;Verwerkingsfout&quot; wordt weergegeven op het Dn-element in de **[!UICONTROL kaartweergave]** , is de conversie mislukt.

   Als dat het geval is, kunt u de omzetting problemen oplossen door het volgende te doen:

   * Verwijder het element en upload het vervolgens opnieuw.
   * Zorg ervoor dat u correct alle configuratieparameters in **[!UICONTROL CRXDE Lite]** hebt geplaatst.
   * Verifieer dat geen firewall toegang tot de omzettingsdienst en eindpunten van AWS blokkeert.
