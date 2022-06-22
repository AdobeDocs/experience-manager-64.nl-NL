---
title: Uw digitale middelen beheren met [!DNL Experience Manager] Activa
description: Meer informatie over de verschillende taken voor middelenbeheer en -bewerking die u kunt uitvoeren met de geoptimaliseerde interface van Touch van [!DNL Experience Manager] Activa
contentOwner: AG
feature: Asset Management,Search,Renditions,Collaboration
role: User
mini-toc-levels: 3
exl-id: aa1a702b-18dd-496b-a6e0-aa593af6e57c
source-git-commit: 7c786e1326c8c65f00d799fed3207e4f0da04fa7
workflow-type: tm+mt
source-wordcount: '9818'
ht-degree: 1%

---

# Uw digitale middelen beheren {#managing-assets-with-the-touch-optimized-ui}

Meer informatie over de verschillende taken voor middelenbeheer en -bewerking die u kunt uitvoeren met de geoptimaliseerde interface van Touch van [!DNL Experience Manager] Elementen.

In dit artikel wordt beschreven hoe u elementen beheert en bewerkt met de gebruikersinterface die is geoptimaliseerd voor Adobe Experience Manager Assets Touch. Voor elementaire kennis van de gebruikersinterface raadpleegt u [Basisverwerking van aanraakinterface](/help/sites-authoring/basic-handling.md). Voor het beheren van inhoudsfragmenten raadpleegt u [Inhoudsfragmenten beheren](content-fragments-managing.md) activa.

## Mappen maken {#create-folders}

Bij het organiseren van een verzameling elementen, bijvoorbeeld alle `Nature` afbeeldingen kunt u mappen maken om ze bij elkaar te houden. U kunt mappen gebruiken om uw elementen te categoriseren en in te delen. [!DNL Experience Manager] Voor elementen hoeft u elementen niet in mappen te ordenen om beter te werken.

>[!NOTE]
>
>* Een map Middelen van het type `sling:OrderedFolder` wordt niet ondersteund bij delen naar Marketing Cloud. Als u een map wilt delen, selecteert u Niet geordend bij het maken van een map.
>* Experience Manager staat het gebruik niet toe `subassets` woord als de naam van een map. Het is een gereserveerd sleutelwoord voor knoop die subassets voor samengestelde activa bevatten.


1. Navigeer naar de plaats in de map met digitale elementen waar u een nieuwe map wilt maken.
1. Klik in het menu op **[!UICONTROL Create]**. Selecteer **[!UICONTROL New Folder]**.
1. In de **[!UICONTROL Title]** veld, geef een mapnaam op. Standaard gebruikt DAM de titel die u als mapnaam hebt opgegeven. Nadat de map is gemaakt, kunt u de standaardinstelling overschrijven en een andere mapnaam opgeven.
1. Klik op **[!UICONTROL Create]**. De map wordt weergegeven in de map met digitale middelen.

De volgende tekens (lijst met door spaties gescheiden tekens) worden niet ondersteund:

* de naam van het elementbestand mag geen elementen bevatten  `* / : [ \ \ ] | # % { } ? &`
* de naam van de elementenmap mag niet bevatten  `* / : [ \ \ ] | # % { } ? \" . ^ ; + & \t`

## Elementen uploaden {#uploading-assets}

U kunt verschillende typen elementen (zoals afbeeldingen, PDF-bestanden, RAW-bestanden, enzovoort) uploaden van uw lokale map of een netwerkstation naar [!DNL Experience Manager] Elementen.

>[!NOTE]
>
>In de modus Dynamic Media - Scene7 kunt u alleen elementen uploaden waarvan de bestandsgrootte 2 GB of minder is.

U kunt ervoor kiezen elementen te uploaden naar mappen waaraan al dan niet een verwerkingsprofiel is toegewezen.

Voor mappen waaraan een verwerkingsprofiel is toegewezen, wordt de profielnaam weergegeven op de miniatuur in de kaartweergave. In de lijstweergave wordt de profielnaam weergegeven in het dialoogvenster **[!UICONTROL Processing Profile]** kolom. Zie [Profielen verwerken](processing-profiles.md).

Voordat u een element uploadt, moet u ervoor zorgen dat het zich in een [ondersteunde indeling](assets-formats.md).

**Elementen uploaden**:

1. Navigeer in de middelenwebinterface naar de locatie waar u digitale elementen wilt toevoegen.
1. Voer een van de volgende handelingen uit om de elementen te uploaden:

   * Tik op de werkbalk op de knop **[!UICONTROL Create]** pictogram. Tik vervolgens in het menu op **[!UICONTROL Files]**. U kunt de naam van het bestand desgewenst wijzigen in het dialoogvenster dat verschijnt.
   * In browser die HTML5 steunt, sleep de activa direct op de interface. Het dialoogvenster voor het wijzigen van de naam van het bestand wordt niet weergegeven.

   ![create_menu](assets/create_menu.png)

   Als u meerdere bestanden wilt selecteren, drukt u op Ctrl/Command en selecteert u de elementen in het dialoogvenster Bestandenkiezer. Vanuit een iPad kunt u slechts één bestand tegelijk selecteren.

   U kunt het uploaden van grote elementen (groter dan 500 MB) pauzeren en later vanaf dezelfde pagina hervatten. Tik op de knop **[!UICONTROL Pause]** pictogram naast de voortgangsbalk die wordt weergegeven wanneer het uploaden start.

   ![chlimage_1-5](assets/chlimage_1-5.png)

   De omvang waarboven een actief als een groot actief wordt beschouwd, kan worden geconfigureerd. U kunt het systeem bijvoorbeeld zodanig configureren dat elementen boven 1000 MB (in plaats van 500 MB) als grote elementen worden beschouwd. In dit geval worden de **[!UICONTROL Pause]** in de voortgangsbalk wordt weergegeven wanneer bestanden van meer dan 1000 MB worden geüpload.

   De **[!UICONTROL Pause]** wordt niet weergegeven als een bestand van meer dan 1000 MB wordt geüpload met een bestand van minder dan 1000 MB. Als u echter het uploaden van bestanden van minder dan 1000 MB annuleert, wordt de knop **[!UICONTROL Pause]** wordt weergegeven.

   Om de groottegrens te wijzigen, vorm `chunkUploadMinFileSize` eigendom van de `fileupload`in de CRX-opslagplaats.

   Wanneer u op de knop **[!UICONTROL Pause]** pictogram, wordt geschakeld naar een **[!UICONTROL Play]** pictogram. Als u het uploaden wilt hervatten, klikt u op de knop **[!UICONTROL Play]** pictogram.

   ![chlimage_1-6](assets/chlimage_1-6.png)

   Als u een actieve upload wilt annuleren, klikt u op de knop `X` naast de voortgangsbalk. Wanneer u het uploaden annuleert, [!DNL Experience Manager] Met Elementen wordt het gedeeltelijk geüploade gedeelte van het element verwijderd.

   De mogelijkheid om het uploaden te hervatten is vooral handig in scenario&#39;s met lage bandbreedte en netwerkstoringen, waarbij het uploaden van een groot element veel tijd in beslag neemt. U kunt het uploaden pauzeren en verdergaan wanneer de situatie verbetert. Wanneer u het document hervat, begint het uploaden vanaf het punt waarop u het hebt gepauzeerd.

   Tijdens het uploaden [!DNL Experience Manager] Hiermee slaat u de delen van het element dat wordt geüpload op als stukjes gegevens in de CRX-opslagplaats. Wanneer het uploaden is voltooid, [!DNL Experience Manager] consolideert deze fragmenten tot één enkel gegevensblok in de gegevensopslagruimte.

   Ga naar om de opschoningstaak voor de onvoltooide taken voor het uploaden naar `https://[aem_server]:[port]/system/console/configMgr/org.apache.sling.servlets.post.impl.helper.ChunkCleanUpTask`.

   Als u een element uploadt met dezelfde naam als een element dat al beschikbaar is op de locatie waar u het element uploadt, wordt een waarschuwingsvenster weergegeven.

   U kunt een bestaand element vervangen, een andere versie maken of beide behouden door de naam van het nieuwe element dat wordt geüpload te wijzigen. Als u een bestaand element vervangt, worden de metagegevens voor het element en eerdere wijzigingen en de geschiedenis (bijvoorbeeld annotaties, uitsnijdingen, enzovoort) verwijderd. Als u ervoor kiest beide elementen te behouden, wordt de naam van het nieuwe element gewijzigd.

   ![chlimage_1-7](assets/chlimage_1-7.png)

   >[!NOTE]
   >
   >Wanneer u **[!UICONTROL Replace]** in de **[!UICONTROL Name Conflict]** wordt de element-id opnieuw gegenereerd voor het nieuwe element. Deze id verschilt van de id van het vorige element.
   >
   >Indien **[!UICONTROL Asset Insights]** is ingeschakeld om afbeeldingen bij te houden/op Adobe Analytics te klikken, maakt deze opnieuw gegenereerde element-id de gegevensopname voor het element op Adobe Analytics ongeldig.

   Als het element dat u uploadt bestaat in [!DNL Experience Manager] Elementen, de **[!UICONTROL Duplicates Detected]** Hiermee wordt u gewaarschuwd dat u probeert een gedupliceerd element te uploaden. Het dialoogvenster wordt alleen weergegeven als de waarde van de controlesom SHA 1 van de binaire waarde van het bestaande element overeenkomt met de waarde van de controlesom van het element dat u uploadt. In dit geval zijn de namen van activa niet van belang. Met andere woorden, het dialoogvenster kan zelfs worden weergegeven voor elementen met verschillende namen als de SHA 1-waarden voor hun binaire getallen gelijk zijn.

   >[!NOTE]
   >
   >De **[!UICONTROL Duplicates Detected]** wordt alleen weergegeven als **[!UICONTROL Duplicate Detection]** is ingeschakeld. Om het **[!UICONTROL Duplicate Detection]** functie, zie [Dubbele detectie inschakelen](duplicate-detection.md).

   ![chlimage_1-8](assets/chlimage_1-8.png)

   Tikken **[!UICONTROL Keep]** om het dubbele element te behouden in [!DNL Experience Manager] Elementen. Tikken  **[!UICONTROL Delete]** om het geüploade dubbele element te verwijderen.

   [!DNL Experience Manager] Met elementen wordt voorkomen dat elementen met verboden tekens in de bestandsnaam worden geüpload. Als u een element probeert te uploaden dat de niet-toegestane tekens bevat, [!DNL Experience Manager] Er verschijnt een waarschuwingsbericht over de aanwezigheid van verboden tekens in de bestandsnaam en het uploaden wordt gestopt totdat u deze tekens verwijdert of uploadt met een toegestane naam.

   Als u specifieke conventies voor de naamgeving van bestanden voor uw organisatie wilt aanpassen, kunt u de opdracht **[!UICONTROL Upload Assets]** kunt u lange namen opgeven voor de bestanden die u uploadt.

   ![chlimage_1-9](assets/chlimage_1-9.png)

   De volgende tekens (lijst met door spaties gescheiden tekens) worden echter niet ondersteund:
   * de naam van het elementbestand mag geen elementen bevatten  `* / : [ \ \ ] | # % { } ? &`
   * de naam van de elementenmap mag niet bevatten  `* / : [ \ \ ] | # % { } ? \" . ^ ; + & \t`

   Bovendien wordt in de interface Middelen het meest recente element weergegeven dat u uploadt of de map die u eerst maakt in alle weergaven (**[!UICONTROL Card view]**, **[!UICONTROL List view]**, en **[!UICONTROL Column view]**).

   Vaak, terwijl het uploaden van grote activa of veelvoudige activa gelijktijdig, laten de visuele indicatoren u toe om de vooruitgang te beoordelen. De **[!UICONTROL Upload Progress]** geeft het aantal bestanden weer dat is geüpload en de bestanden die niet zijn geüpload.

   ![chlimage_1-10](assets/chlimage_1-10.png)

   Als u het uploaden annuleert voordat de bestanden zijn geüpload, [!DNL Experience Manager] Elementen uploaden het huidige bestand wordt gestopt en de inhoud wordt vernieuwd. Bestanden die al zijn geüpload, worden echter niet verwijderd.

### Seriële uploads {#serial-uploads}

Het uploaden van een groot aantal bedrijfsmiddelen kost veel systeembronnen, wat de prestaties van uw [!DNL Experience Manager] implementatie. Potentiële knelpunten kunnen zijn: uw internetverbinding, lees-schrijfbewerkingen op schijf, beperkingen van de webbrowser voor het aantal aanvragen van POSTEN voor het uploaden van gelijktijdig geplaatste elementen. Het uploaden van een lamp kan mislukken of voortijdig beëindigen. Met andere woorden: [!DNL Experience Manager] bepaalde bestanden worden mogelijk overgeslagen bij het opnemen van een aantal bestanden of het invoegen van een bestand wordt afgeremd.

Om deze situatie te verhelpen, [!DNL Experience Manager] Elementen nemen één element tegelijk in (seriële upload) tijdens een bulkuploadbewerking in plaats van alle elementen tegelijk in te nemen.

Seriële uploaden van elementen is standaard ingeschakeld. Als u de functie wilt uitschakelen en tegelijkertijd uploaden wilt toestaan, bedekt u de `fileupload` knooppunt in CRXDe en stel de waarde van de `parallelUploads` eigenschap aan `true`.

### Elementen uploaden met FTP {#uploading-assets-using-ftp}

Dynamic Media maakt het uploaden van bestanden in batches via FTP-server mogelijk. Als u grote bestanden (>1 GB) wilt uploaden of volledige mappen en submappen wilt uploaden, moet u FTP gebruiken. U kunt zelfs instellen dat FTP-upload wordt uitgevoerd op een terugkerende geplande basis.

>[!NOTE]
>
>In de modus Dynamic Media - Scene7 kunt u alleen elementen uploaden waarvan de bestandsgrootte 2 GB of minder is.

>[!NOTE]
>
>Elementen uploaden via FTP in Dynamic Media - Scene7 mode install feature pack (FP) 18912 on [!DNL Experience Manager] auteur. Neem contact op met de klantenondersteuning van Adobe voor toegang tot FP-18912 en voltooi de installatie van uw FTP-account. Zie [Functiepakket 18912 voor migratie van grote hoeveelheden bedrijfsmiddelen installeren](/help/assets/bulk-ingest-migrate.md).
>
>Als u FTP gebruikt voor het uploaden van elementen, worden de uploadinstellingen opgegeven in [!DNL Experience Manager] worden genegeerd. In plaats daarvan worden de regels voor bestandsverwerking gebruikt, zoals gedefinieerd in Dynamic Media Classic.

**Elementen uploaden met FTP**

1. Meld u met uw keuze voor een FTP-client aan bij de FTP-server met de FTP-gebruikersnaam en -wachtwoord die u van de e-mail met de provisioning hebt ontvangen. Upload in de FTP-client bestanden of mappen naar de FTP-server.
1. Open de [Dynamic Media Classic-bureaubladtoepassing](https://experienceleague.adobe.com/docs/dynamic-media-classic/using/getting-started/signing-out.html#getting-started)Meld u vervolgens aan bij uw account met de gegevens die u hebt ontvangen van de e-mail met provisioning.
1. Tik op de algemene navigatiebalk op **[!UICONTROL Upload]**.
1. Op de **[!UICONTROL Upload]** tikt u in de linkerbovenhoek op de **[!UICONTROL Via FTP]** tab.
1. Kies links op de pagina een FTP-map waaruit u bestanden wilt uploaden. aan de rechterkant van de pagina kiest u een doelmap.
1. Tik in de rechterbenedenhoek van de pagina op **[!UICONTROL Job Options]** en stelt vervolgens de gewenste opties in op basis van de elementen in de map die u hebt geselecteerd.

   Zie [Opties voor uploaden](#upload-job-options).

   >[!NOTE]
   >
   >Wanneer u elementen uploadt via FTP, hebben de opties voor uploadtaken die u in Dynamic Media Classic hebt ingesteld, voorrang op de parameters voor elementverwerking die in AEM zijn ingesteld.

1. In de rechterbenedenhoek van het dialoogvenster **[!UICONTROL Upload Job Options]** dialoogvenster tikken **[!UICONTROL Save]**.
1. In de rechterbenedenhoek van het dialoogvenster **[!UICONTROL Upload]** pagina, tikken **[!UICONTROL Submit Upload]**.

   Tik op de algemene navigatiebalk op de knop om de voortgang van het uploaden weer te geven **[!UICONTROL Jobs]**. De **[!UICONTROL Jobs]** geeft de voortgang van het uploaden weer. U kunt blijven werken in [!DNL Experience Manager] en op elk moment terug naar de pagina Jobs in Dynamic Media Classic om een actieve baan te beoordelen.

   Tik op **[!UICONTROL Cancel]** naast de **[!UICONTROL Duration]** tijd.

#### Opties voor uploaden {#upload-job-options}

| Uploaden, optie | Suboptie | Beschrijving |
|---|---|---|
| Taaknaam |  | De standaardnaam die vooraf in het tekstveld is ingevuld, bevat het door de gebruiker ingevoerde gedeelte van de naam en de datum- en tijdstempel. U kunt de standaardnaam gebruiken of een naam invoeren van uw eigen ontwerp voor deze uploadtaak. <br>De baan en andere upload en het publiceren banen worden geregistreerd op de pagina van Banen, waar u de status van banen kunt controleren. |
| Publiceren na uploaden |  | Hiermee publiceert u automatisch de elementen die u uploadt. |
| Overschrijven in een willekeurige map, dezelfde naam van basiselement, ongeacht de extensie |  | Selecteer deze optie als u wilt dat de bestanden die u uploadt, bestaande bestanden met dezelfde naam vervangen. De naam van deze optie kan verschillen, afhankelijk van de instellingen in **[!UICONTROL Application Setup]** > **[!UICONTROL General Settings]** > **[!UICONTROL Upload to Application]** > **[!UICONTROL Overwrite Images]**. |
| ZIP- of TAR-bestanden decomprimeren tijdens het uploaden |  |  |
| Taakopties |  | Tikken/ klikken **[!UICONTROL Job Options]** om de [!UICONTROL Upload Job Options] en kiest u opties die van invloed zijn op de volledige uploadtaak. Deze opties zijn hetzelfde voor alle bestandstypen.<br>U kunt standaardopties kiezen voor het uploaden van bestanden die beginnen op de pagina Algemene instellingen van toepassing. Kies **[!UICONTROL Setup]** > **[!UICONTROL Application Setup]**. Tik op de knop **[!UICONTROL Default Upload Options]** om de [!UICONTROL Upload Job Options] in. |
|  | Wanneer | Selecteer Eenmalig of Herhalend. Als u een terugkerende taak wilt instellen, kiest u de optie Herhalen (Dagelijks, Wekelijks, Maandelijks of Aangepast) om op te geven wanneer de FTP-uploadtaak moet worden herhaald. Geef vervolgens de gewenste planningsopties op. |
|  | Inclusief submappen | Upload alle submappen in de map die u wilt uploaden. De namen van de map en de submappen die u uploadt, worden automatisch ingevoerd in [!DNL Experience Manager] Elementen. |
|  | Opties voor uitsnijden | Als u handmatig wilt uitsnijden aan weerszijden van een afbeelding, selecteert u het menu Uitsnijden en kiest u Handmatig. Voer vervolgens het aantal pixels in dat u aan elke zijde van de afbeelding wilt uitsnijden. Hoeveel van de afbeelding wordt uitgesneden, is afhankelijk van de ppi-instelling (pixels per inch) in het afbeeldingsbestand. Als de afbeelding bijvoorbeeld 150 ppi weergeeft en u 75 invoert in de tekstvakken Boven, Rechts, Onder en Links, wordt aan beide zijden een halve inch bijgesneden.<br> Als u pixels in witruimte automatisch wilt uitsnijden in een afbeelding, opent u het menu Uitsnijden, kiest u Handmatig en voert u pixelmetingen in in de velden Boven, Rechts, Onder en Links om van de zijkanten bij te snijden. U kunt ook Bijsnijden kiezen in het menu Uitsnijden en de volgende opties kiezen:<br> **Wegsnijden op basis van** <ul><li>**Kleur** - Kies de optie Kleur. Selecteer vervolgens het menu Hoek en kies de hoek van de afbeelding met de kleur die het beste overeenkomt met de kleur voor de witruimte die u wilt uitsnijden.</li><li>**Transparantie** - Kies de optie Transparantie.<br> **Tolerantie** - Sleep de schuifregelaar om een tolerantie tussen 0 en 1 op te geven. Geef voor bijsnijden op basis van kleur 0 op om alleen pixels bij te snijden als deze exact overeenkomen met de kleur die u in de hoek van de afbeelding hebt geselecteerd. De aantallen dichter aan 1 staan voor meer kleurenverschil toe.<br>Voor het bijsnijden op basis van transparantie geeft u 0 op om alleen pixels bij te snijden als deze transparant zijn. De aantallen dichter aan 1 staan voor meer transparantie toe.</li></ul><br>Deze opties voor uitsnijden zijn niet-destructief. |
|  | Opties voor kleurprofiel | Kies een kleurconversie wanneer u geoptimaliseerde bestanden maakt die worden gebruikt voor levering:<ul><li>Standaardkleurbehoud: De kleuren van de bronafbeelding blijven behouden wanneer de afbeeldingen kleurruimte-informatie bevatten. er is geen kleurconversie. In bijna alle afbeeldingen van vandaag is het juiste kleurprofiel al ingesloten. Als een CMYK-bronafbeelding echter geen ingesloten kleurprofiel bevat, worden de kleuren omgezet in de kleurruimte sRGB (standaard rood-groen-blauw). sRGB is de aanbevolen kleurruimte voor het weergeven van afbeeldingen op webpagina&#39;s.</li><li>Oorspronkelijke kleurruimte behouden: Behoudt de oorspronkelijke kleuren zonder kleurconversie op het punt. Voor afbeeldingen zonder ingesloten kleurprofiel wordt elke kleurconversie uitgevoerd met de standaardkleurprofielen die zijn geconfigureerd in de Publicatie-instellingen. De kleurprofielen worden mogelijk niet uitgelijnd met de kleur in de bestanden die met deze optie zijn gemaakt. Daarom wordt u aangeraden de optie Standaardkleurbehoud te gebruiken.</li><li>Aangepast van > tot<br> Hiermee opent u menu&#39;s, zodat u een optie kunt kiezen voor Omzetten van en Omzetten in kleurruimte. Deze geavanceerde optie negeert alle kleurinformatie die in het bronbestand is ingesloten. Selecteer deze optie als alle afbeeldingen die u verzendt, onjuiste of ontbrekende kleurprofielgegevens bevatten.</li></ul> |
|  | Beeldbewerkingsopties | U kunt de knipmaskers in afbeeldingen behouden en een kleurprofiel kiezen.<br> Zie [Opties voor het bewerken van afbeeldingen tijdens het uploaden instellen](#setting-image-editing-options-at-upload). |
|  | PostScript-opties | U kunt PostScript® rasteren, bestanden uitsnijden, transparante achtergronden behouden, een resolutie kiezen en een kleurruimte kiezen.<br> Zie [Uploadopties voor PostScript en Illustrator instellen](#setting-postscript-and-illustrator-upload-options). |
|  | Photoshop-opties | U kunt sjablonen maken van Adobe® Photoshop®-bestanden, lagen behouden, opgeven hoe lagen worden benoemd, tekst extraheren en opgeven hoe afbeeldingen in sjablonen worden verankerd.<br> Sjablonen worden niet ondersteund in AEM.<br> Zie [Photoshop-upopties instellen](#setting-photoshop-upload-options). |
|  | PDF-opties | U kunt de bestanden rasteren, zoekwoorden en koppelingen extraheren, automatisch een eCatalog genereren, de resolutie instellen en een kleurruimte kiezen.<br> E-catalogi worden niet ondersteund in AEM. <br> Zie [Opties voor het uploaden naar PDF instellen ](#setting-pdf-upload-options)<br>**Opmerking**: Het maximumaantal pagina&#39;s voor een PDF dat voor extractie in aanmerking komt, is 5000 voor nieuwe uploads. Deze limiet verandert in 100 pagina&#39;s op 31 december 2022. Zie ook [Dynamic Media-beperkingen](/help/assets/limitations.md). |
|  | Illustrator-opties | U kunt Adobe Illustrator®-bestanden rasteren, transparante achtergronden behouden, een resolutie kiezen en een kleurruimte kiezen.<br> Zie [Uploadopties voor PostScript en Illustrator instellen](#setting-postscript-and-illustrator-upload-options). |
|  | EVideo-opties | U kunt een videobestand transcoderen door een videovoorinstelling te kiezen.<br> Zie [Uploadopties voor eVideo instellen](#setting-evideo-upload-options). |
|  | Voorinstellingen batchset | Als u een Afbeeldingsset of Spin-set wilt maken van de geüploade bestanden, klikt u op de kolom Actief voor de voorinstelling die u wilt gebruiken. U kunt meerdere voorinstellingen selecteren. U maakt de voorinstellingen op de pagina Voorinstellingen voor toepassingsinstellingen/batchsets van Dynamic Media Classic.<br> Zie [Voorinstellingen voor batchsets configureren voor het automatisch genereren van afbeeldingssets en centrifuges](config-dms7.md#creating-batch-set-presets-to-auto-generate-image-sets-and-spin-sets) voor meer informatie over het maken van voorinstellingen voor batchsets.<br> Zie [Voorinstellingen voor batchset instellen bij uploaden](#setting-batch-set-presets-at-upload). |

#### Opties voor het bewerken van afbeeldingen tijdens het uploaden instellen {#setting-image-editing-options-at-upload}

Wanneer u afbeeldingsbestanden uploadt, zoals AI-, EPS- en PSD-bestanden, kunt u de volgende bewerkingen uitvoeren in het dialoogvenster **[!UICONTROL Upload Job Options]** dialoogvenster:

* Witruimte uitsnijden vanaf de rand van afbeeldingen (zie beschrijving in bovenstaande tabel).
* Handmatig uitsnijden vanaf de zijkanten van afbeeldingen (zie beschrijving in bovenstaande tabel).
* Kies een kleurprofiel (zie de beschrijving van de optie in de bovenstaande tabel).
* Maak een masker op basis van een uitknippad.
* Afbeeldingen verscherpen met onscherpe maskeropties
* Achtergrond uitnemen

| Optie | Suboptie | Beschrijving |
|---|---|---|
| Masker maken van uitknippad |  | Maak een masker voor de afbeelding op basis van de gegevens over het uitknippad. Deze optie is van toepassing op afbeeldingen die zijn gemaakt met beeldbewerkingstoepassingen waarin een uitknippad is gemaakt. |
| Onscherp maskeren |  | Hiermee kunt u een verscherpingsfiltereffect perfectioneren op de uiteindelijke gedownsampelde afbeelding, waarbij u de intensiteit van het effect, de straal van het effect (gemeten in pixels) en een drempel voor contrast instelt die wordt genegeerd.<br> Voor dit effect worden dezelfde opties gebruikt als voor het filter Onscherp masker van Photoshop. In tegenstelling tot wat de naam suggereert, is Onscherp masker een verscherpingsfilter. Stel onder Onscherp masker de gewenste opties in. De instellingsopties worden in het volgende beschreven: |
|  | Hoeveelheid | Hiermee bepaalt u de hoeveelheid contrast die wordt toegepast op de randpixels.<br> Beschouw het als de intensiteit van het effect. Het belangrijkste verschil tussen de waarden voor de hoeveelheid Onscherp masker in Dynamic Media en de waarden voor de hoeveelheid in Adobe Photoshop is dat Photoshop een bereik heeft van 1% tot 500%. In Dynamic Media is het waardebereik 0,0 tot 5,0. Een waarde van 5,0 is het ruwe equivalent van 500% in Photoshop; een waarde van 0,9 komt overeen met 90% enzovoort. |
|  | Radius | Hiermee bepaalt u de straal van het effect. Het waardebereik is 0-250.<br> Het effect wordt op alle pixels in een afbeelding uitgevoerd en wordt vanuit alle pixels in alle richtingen uitgestraald. De straal wordt gemeten in pixels. Als u bijvoorbeeld een vergelijkbaar verscherpingseffect wilt toepassen op een afbeelding van 2000 x 2000 pixels en een afbeelding van 500 x 500 pixels, stelt u een straal in van twee pixels op de afbeelding van 2000 x 2000 pixels en een straalwaarde van één pixel op de afbeelding van 500 x 500 pixels. Een hogere waarde wordt gebruikt voor een afbeelding met meer pixels. |
|  | Drempel | Drempel is een contrastbereik dat wordt genegeerd wanneer het filter Onscherp masker wordt toegepast. Het is belangrijk dat er geen &#39;ruis&#39; wordt toegevoegd aan een afbeelding wanneer dit filter wordt gebruikt. Het waardebereik is 0-255. Dit is het aantal helderheidsstappen in een grijswaardenafbeelding. 0=zwart, 128=50% grijs en 255=wit.<br> Een drempelwaarde van 12 negeert bijvoorbeeld kleine variaties door de helderheid van de huidskleur om ruis te voorkomen, maar voegt toch randcontrast toe aan contrasterende gebieden, zoals waar de wimpers de huid raken.<br> Als u bijvoorbeeld een foto van iemands gezicht hebt, heeft het filter Onscherp masker invloed op de contrasterende delen van de afbeelding, zoals waar de wimpers en de huid elkaar raken om een duidelijk contrastgebied te maken en op de zachte huid zelf. Zelfs de meest vloeiende skin vertoont subtiele wijzigingen in helderheidswaarden. Als u geen drempelwaarde gebruikt, accentueert het filter deze subtiele veranderingen in huidpixel. Er wordt op zijn beurt een lawaai en ongewenst effect gecreëerd terwijl het contrast op de wimpers wordt verhoogd, waardoor de scherpte wordt vergroot.<br> Om dit probleem te voorkomen, wordt een drempelwaarde geïntroduceerd die het filter vertelt om pixels te negeren die het contrast niet drastisch wijzigen, zoals een vloeiende skin.<br> Let op de structuur naast de ritssluiters in de afbeelding die u eerder hebt weergegeven. Ruis in de afbeelding wordt weergegeven omdat de drempelwaarden te laag waren om de ruis te onderdrukken. |
|  | Monochroom | Selecteer deze optie om de helderheid (intensiteit) van een afbeelding zonder scherp masker te wijzigen.<br> Schakel deze optie uit als u elke kleurcomponent afzonderlijk wilt ontscherpen. |
| Achtergrond uitnemen |  | Hiermee verwijdert u automatisch de achtergrond van een afbeelding wanneer u deze uploadt. Deze techniek is nuttig om de aandacht op een bepaald voorwerp te vestigen en het van een drukke achtergrond te maken. Selecteer deze optie om de functie Achtergrond uitnemen en de volgende subopties in te schakelen of in te schakelen: |
|  | Hoek | Vereist.<br> De hoek van de afbeelding die wordt gebruikt om de achtergrondkleur voor uitnemen te definiëren.<br> U kunt kiezen uit **Linksboven**, **Linksonder**, **Rechtsboven**, of **Rechtsonder**. |
|  | Vulmethode | Vereist.<br> Hiermee regelt u de pixeltransparantie vanaf de locatie Hoek die u instelt.<br> U kunt kiezen uit de volgende vulmethoden: <ul><li>**Flood Fill** - Hiermee worden alle pixels transparant gemaakt die overeenkomen met de hoek die u hebt opgegeven en waarop u bent aangesloten.</li><li>**Pixel afstemmen** - hiermee worden alle overeenkomende pixels transparant gemaakt, ongeacht de locatie van de pixels op de afbeelding.</li></ul> |
|  | Tolerantie | Optioneel.<br> Hiermee bepaalt u de toegestane hoeveelheid variatie in de overeenkomende pixelkleur op basis van de locatie van de hoek die u instelt.<br> Gebruik een waarde van 0,0 om de pixelkleuren exact overeen te laten komen of gebruik een waarde van 1,0 voor de grootste variatie. |

#### Uploadopties voor PostScript en Illustrator instellen {#setting-postscript-and-illustrator-upload-options}

Wanneer u PostScript- (EPS) of Illustrator-afbeeldingsbestanden (AI) uploadt, kunt u deze op verschillende manieren opmaken. U kunt de bestanden rasteren, de transparante achtergrond behouden, een resolutie kiezen en een kleurruimte kiezen. Opties voor de opmaak van PostScript- en Illustrator-bestanden vindt u in het dialoogvenster Taakopties uploaden onder PostScript-opties en Illustrator-opties.

| Optie | Suboptie | Beschrijving |
|---|---|---|
| Verwerking |  | Kies **[!UICONTROL Rasterize]** om vectorafbeeldingen in het bestand om te zetten in de bitmapindeling. |
| Transparante achtergrond behouden in gerenderde afbeelding |  | De achtergrondtransparantie van het bestand behouden. |
| Resolutie |  | Hiermee bepaalt u de resolutie-instelling. Deze instelling bepaalt hoeveel pixels per inch in het bestand worden weergegeven. |
| Kleurruimte |  | Selecteer het menu Kleurruimte en kies een van de volgende opties voor kleurruimte: |
|  | Automatisch detecteren | Hiermee behoudt u de kleurruimte van het bestand. |
|  | Krachten als RGB | Hiermee wordt de kleurruimte RGB omgezet. |
|  | Inschakelen als CMYK | Zet om in de CMYK-kleurruimte. |
|  | Forceren als grijswaarden | Hiermee wordt de grijswaardenkleurruimte omgezet. |

#### Photoshop-upopties instellen {#setting-photoshop-upload-options}

PSD-bestanden (Photoshop Document) worden meestal gebruikt om afbeeldingssjablonen te maken. Wanneer u een PSD-bestand uploadt, kunt u automatisch een afbeeldingssjabloon maken vanuit het bestand (selecteer de optie Sjabloon maken in het scherm Uploaden).

Dynamic Media maakt meerdere afbeeldingen van een PSD-bestand met lagen als u het bestand gebruikt om een sjabloon te maken. er wordt één afbeelding voor elke laag gemaakt.

Gebruik de **[!UICONTROL Crop Options]** en **[!UICONTROL Color Profile Options]**, zoals hierboven beschreven, met uploadopties voor Photoshop.

>[!NOTE]
>
>Sjablonen worden niet ondersteund in AEM.

| Optie | Suboptie | Beschrijving |
|---|---|---|
| Lagen behouden |  | Hiermee worden de lagen in de PSD, indien aanwezig, uitgelijnd op afzonderlijke elementen. De elementlagen blijven gekoppeld aan de PSD. U kunt deze weergeven door het PSD-bestand te openen in de gedetailleerde weergave en het deelvenster Lagen te selecteren. |
| Sjabloon maken |  | Hiermee maakt u een sjabloon op basis van de lagen in het PSD-bestand. |
| Tekst extraheren |  | Extraheert de tekst zodat gebruikers naar tekst in een viewer kunnen zoeken. |
| Lagen uitbreiden naar achtergrondgrootte |  | Hiermee vergroot u de grootte van de uitgesneden afbeeldingslagen tot de grootte van de achtergrondlaag. |
| Laagnaamgeving |  | Lagen in het PSD-bestand worden geüpload als aparte afbeeldingen. |
|  | Laagnaam | De afbeeldingen krijgen een naam na hun laagnamen in het PSD-bestand. Een laag met de naam Prijscode in het oorspronkelijke PSD-bestand wordt bijvoorbeeld een afbeelding met de naam Prijscode. Als de laagnamen in het PSD-bestand echter standaard Photoshop-laagnamen zijn (Achtergrond, Laag 1, Laag 2, enzovoort), krijgen de afbeeldingen een naam na hun laagnummers in het PSD-bestand en niet na hun standaardlaagnamen. |
|  | Photoshop en Layer Number | De afbeeldingen krijgen een naam na hun laagnummer in het PSD-bestand, waarbij de namen van de oorspronkelijke lagen worden genegeerd. Afbeeldingen krijgen de naam Photoshop en een toegevoegd laagnummer. De tweede laag van een bestand met de naam Voorjaar-Ad.psd krijgt bijvoorbeeld de naam Voorjaar-Ad_2, zelfs als deze in Photoshop een andere naam heeft dan de standaardnaam. |
|  | Photoshop- en laagnaam | De afbeeldingen krijgen een naam na het PSD-bestand gevolgd door de naam van de laag of het laagnummer. Het laagnummer wordt gebruikt als de laagnamen in het PSD-bestand standaard Photoshop-laagnamen zijn. Een laag met de naam Price Tag in een PSD-bestand met de naam SpringAd krijgt bijvoorbeeld de naam Spring Ad_Price Tag. Een laag met de standaardnaam Laag 2 wordt genoemd Lente Ad_2. |
| Anker |  | Geef op hoe afbeeldingen worden verankerd in sjablonen die worden gegenereerd op basis van de laagsamenstelling die uit het PSD-bestand is samengesteld. Standaard is het anker het middelpunt. Met een middelste anker kunnen vervangende afbeeldingen dezelfde ruimte het beste vullen, ongeacht de hoogte-breedteverhouding van de vervangende afbeelding. Afbeeldingen met een ander aspect dat deze afbeelding vervangt, nemen bij het verwijzen naar de sjabloon en het gebruik van parametervervanging in feite dezelfde ruimte in. Schakel over naar een andere instelling als de vervangende afbeeldingen de toegewezen ruimte in de sjabloon moeten vullen. |

#### Opties voor het uploaden naar PDF instellen {#setting-pdf-upload-options}

Wanneer u een PDF-bestand uploadt, kunt u het op verschillende manieren opmaken. U snijdt zijn pagina&#39;s bij, haalt zoekwoorden op, voert een pixel-per-duimresolutie in, en kiest een kleurenruimte. PDF-bestanden bevatten vaak een snijmarge, snijtekens, registratietekens en andere drukkersmarkeringen. U kunt deze markeringen vanaf de zijkanten van pagina&#39;s bijsnijden wanneer u een PDF-bestand uploadt.

Het maximumaantal pagina&#39;s voor een PDF dat voor extractie in aanmerking komt, is 5000 voor nieuwe uploads. Deze limiet verandert in 100 pagina&#39;s op 31 december 2022. Zie ook [Dynamic Media-beperkingen](/help/assets/limitations.md).

>[!NOTE]
>
>eCatalogs worden niet ondersteund in AEM.

Kies een van de volgende opties:

| Optie | Suboptie | Beschrijving |
|---|---|---|
| Verwerking | Rasteren | (Standaard) Hiermee worden de pagina&#39;s in het PDF-bestand weggesneden en worden vectorafbeeldingen omgezet in bitmapafbeeldingen. Kies deze optie om een eCatalog te maken. |
| Extraheren | Woorden zoeken | Extraheert woorden uit het PDF-bestand, zodat het bestand op trefwoord in een eCatalog-viewer kan worden doorzocht. |
|  | Koppelingen | Extraheert koppelingen uit de PDF-bestanden en converteert deze naar Afbeeldingen met hyperlinks die worden gebruikt in een eCatalog-viewer. |
| E-catalogus automatisch genereren op basis van PDF van meerdere pagina&#39;s |  | Hiermee wordt automatisch een eCatalog gemaakt op basis van het PDF-bestand. De eCatalog wordt genoemd naar het dossier van de PDF u uploadde. (Deze optie is alleen beschikbaar als u het PDF-bestand rastert terwijl u het uploadt.) |
| Resolutie |  | Hiermee bepaalt u de resolutie-instelling. Deze instelling bepaalt hoeveel pixels per inch in het PDF-bestand worden weergegeven. De standaardwaarde is 150. |
| Kleurruimte |  | Selecteer het menu Kleurruimte en kies een kleurruimte voor het PDF-bestand. De meeste PDF-bestanden hebben zowel RGB- als CMYK-kleurenafbeeldingen. De kleurruimte RGB heeft de voorkeur voor onlineweergave. |
|  | Automatisch detecteren | Hiermee behoudt u de kleurruimte van het PDF-bestand. |
|  | Krachten als RGB | Hiermee wordt de kleurruimte RGB omgezet. |
|  | Krachten als CMYK | Zet om in de CMYK-kleurruimte. |
|  | Krachtig maken als grijswaarden | Hiermee wordt de grijswaardenkleurruimte omgezet. |

#### Uploadopties voor eVideo instellen {#setting-evideo-upload-options}

U kunt een videobestand transcoderen door een keuze te maken uit verschillende videovoorinstellingen.

| Optie | Suboptie | Beschrijving |
|---|---|---|
| Adaptieve video |  | Eén coderingsvoorinstelling die met een willekeurige hoogte-breedteverhouding werkt voor het maken van video&#39;s voor levering op mobiele apparaten, tablets en desktops. Geüploade bronvideo&#39;s die met deze voorinstelling zijn gecodeerd, worden ingesteld met een vaste hoogte. De breedte wordt echter automatisch geschaald om de hoogte-breedteverhouding van de video te behouden. <br>Aangepaste videocodering wordt aanbevolen. |
| Enkele coderingsvoorinstellingen | Voorinstellingen voor codering sorteren | Selecteer Naam of Grootte om de coderingsvoorinstellingen onder Desktop, Mobiel en Tablet op naam of op resolutiegrootte te sorteren. |
|  | Desktop | Maak een MP4-bestand voor een streaming of progressieve videobeleving op bureaubladcomputers. Selecteer een of meer hoogte-breedteverhoudingen met de gewenste resolutiegrootte en gegevenssnelheid. |
|  | Mobiel | Maak een MP4-bestand voor levering op mobiele iPhone- of Android-apparaten. Selecteer een of meer hoogte-breedteverhoudingen met de gewenste resolutie- en doelgegevenssnelheid. |
|  | Tablet | Maak een MP4-bestand voor levering op iPad- of Android-tablets. Selecteer een of meer hoogte-breedteverhoudingen met de gewenste resolutie- en doelgegevenssnelheid. |

#### Voorinstellingen batchset instellen bij uploaden {#setting-batch-set-presets-at-upload}

Als u automatisch een set afbeeldingen of een set rotaties wilt maken van geüploade afbeeldingen, klikt u op de knop **[!UICONTROL Active]** voor de voorinstelling die u wilt gebruiken. U kunt meerdere voorinstellingen selecteren.

Zie [Voorinstellingen voor batchsets configureren voor het automatisch genereren van afbeeldingssets en centrifuges](config-dms7.md#creating-batch-set-presets-to-auto-generate-image-sets-and-spin-sets) voor meer informatie over het maken van voorinstellingen voor batchsets.

### Gestroomde uploads {#streamed-uploads}

Als u talrijke activa uploadt, I/O roept aan [!DNL Experience Manager] de server drastisch stijgt, wat uploadefficiency vermindert en zelfs het uit tijd kan veroorzaken. [!DNL Experience Manager] Elementen ondersteunen gestreamd uploaden van elementen. Gestroomd uploaden reduceert de schijf-I/O tijdens het uploaden door opslag van middelen in een tijdelijke map op de server te voorkomen voordat deze naar de opslagplaats wordt gekopieerd. In plaats daarvan worden de gegevens rechtstreeks naar de gegevensopslagruimte overgedragen. Op deze manier wordt de uploadtijd voor grote middelen en de mogelijkheid van time-outs verminderd. Uploaden via streaming is standaard ingeschakeld in [!DNL Experience Manager] Elementen.

Uploaden naar streaming is uitgeschakeld voor [!DNL Experience Manager] wordt uitgevoerd op JEE-server met servlet-api-versie lager dan 3.1.

### ZIP-archief met elementen extraheren {#extract-zip-archive-containing-assets}

U kunt ZIP-archieven net als alle andere ondersteunde elementen uploaden. Dezelfde regels voor bestandsnaam gelden voor ZIP-bestanden. [!DNL Experience Manager] kunt u een ZIP-archief extraheren naar een DAM-locatie.

Selecteer één ZIP-archief tegelijk en klik op **[!UICONTROL Extract Archive]** en selecteer een doelmap. Selecteer een optie om eventuele conflicten af te handelen. Als de elementen in het ZIP-bestand al in de doelmap staan, kunt u een van de volgende opties selecteren: extractie overslaan, bestaande bestanden vervangen, beide elementen behouden door een andere naam te geven of een nieuwe versie te maken.

Nadat de extractie is voltooid, [!DNL Experience Manager] brengt u op het berichtgebied op de hoogte. while [!DNL Experience Manager] Hiermee haalt u het ZIP-bestand uit. U kunt teruggaan naar uw werk zonder de extractie te onderbreken.

![Kennisgeving van de ZIP-extractie](assets/zip_extract_notification.png)

Enkele beperkingen van de functie zijn:

* Als er op de bestemming een map met dezelfde naam staat, worden de elementen uit het ZIP-bestand geëxtraheerd naar de bestaande map.

* Als u de extractie annuleert, worden de reeds geëxtraheerde elementen niet verwijderd.

* U kunt niet twee ZIP-bestanden tegelijk selecteren en extraheren. U kunt slechts één ZIP-archief tegelijk extraheren.

## Elementen voorvertonen {#previewing-assets}

**Elementen voorvertonen**:

1. Navigeer in de interface Elementen naar de locatie van het element waarvan u een voorvertoning wilt weergeven.
1. Tik op het gewenste element om het te openen.

1. In de voorvertoningsmodus zijn zoomopties beschikbaar voor [ondersteunde afbeeldingstypen](assets-formats.md#supported-raster-image-formats) (met interactieve bewerkingen).

   Tik op een element om in te zoomen **[!UICONTROL +]** (of tik op het vergrootglas op het middel). Tik op **[!UICONTROL -]**. Wanneer u inzoomt, kunt u elk gebied van de afbeelding nauwkeurig bekijken door te pannen. De **[!UICONTROL Reset Zoom]** terug naar de oorspronkelijke weergave.

   ![uplodicon](assets/uploadicon.png)

   Tik op de knop **[!UICONTROL Reset]** om de weergave weer in te stellen op de oorspronkelijke grootte.

   ![chlimage_1-11](assets/chlimage_1-11.png)

>[!MORELIKETHIS]
>
>* [Voorbeeld Dynamic Media-middelen bekijken](/help/assets/previewing-assets.md).
>* [Subelementen weergeven](managing-linked-subassets.md#viewing-subassets).


## Eigenschappen bewerken {#editing-properties}

1. Navigeer naar de locatie van het element waarvan u de metagegevens wilt bewerken.

1. Selecteer het element en tik op **[!UICONTROL Properties]** op de werkbalk om de eigenschappen van elementen weer te geven. U kunt ook de optie **[!UICONTROL Properties]** snelle actie op de asset card.

   ![properties_quickaction](assets/properties_quickaction.png)

1. In de **[!UICONTROL Properties]** pagina, bewerkt u de eigenschappen van de metagegevens onder verschillende tabbladen. Onder de **[!UICONTROL Basic]** , bewerkt u de titel, beschrijving, enzovoort.

   De indeling van de **[!UICONTROL Properties]** De beschikbare pagina- en metagegevenseigenschappen zijn afhankelijk van het onderliggende metagegevensschema. Leren hoe u de lay-out van de **[!UICONTROL Properties]** pagina, zie [Metagegevensschema&#39;s](metadata-schemas.md).

1. Gebruik de datumkiezer naast het veld **[!UICONTROL On Time]** om een bepaalde datum/tijd voor de activering van de asset te plannen.

   ![Op tijd instellen om elementen voor een vaste periode tussen aan- en uittijd beschikbaar te maken](assets/chlimage_1-12.png)

1. Als u het element na een bepaalde duur wilt deactiveren, kiest u de datum en tijd van deactivering in de datumkiezer naast de **[!UICONTROL Off Time]** veld.

   De deactiveringsdatum moet later zijn dan de activeringsdatum voor een element. Na de [!UICONTROL Off Time], een middel en de vertoningen ervan zijn niet beschikbaar via de Elementen-webinterface of via de HTTP-API.

   ![Verschuiving tijd voor activa om hun beschikbaarheid na een bepaalde periode tegen te houden](assets/chlimage_1-13.png)

1. In de **[!UICONTROL Tags]** veld, selecteert u een of meer tags. Als u een aangepaste tag wilt toevoegen, typt u de naam van de tag in het vak en drukt u op **[!UICONTROL Enter]**. De nieuwe tag wordt opgeslagen in AEM.

   YouTube vereist dat tags worden gepubliceerd en dat er een koppeling naar YouTube staat (als er een geschikte koppeling is gevonden).
Als u tags wilt maken, hebt u schrijfmachtigingen nodig voor `/content/cq:tags/default` in de CRX-opslagplaats.

1. Tik op de **[!UICONTROL Advanced]** tikt en vervolgens op de gewenste positie op de ster tikt om de gewenste classificatie toe te wijzen.

   ![ratings](assets/ratings.png)

   De beoordelingsscore die u aan het element toewijst, wordt onder weergegeven **[!UICONTROL Your Ratings]**. De gemiddelde ratingscore die het actief ontvangt van gebruikers die het actief hebben beoordeeld, wordt onder **[!UICONTROL Rating]**. Daarnaast wordt de opsplitsing van de ratingscores die bijdragen aan de gemiddelde ratingscore weergegeven onder **[!UICONTROL Rating Breakdown]**. U kunt middelen zoeken op basis van gemiddelde score.

1. Tik op het tabblad **[!UICONTROL Insights]** tab.

   De statistieken van het gebruik omvatten het volgende:

   * Aantal keer dat het element is weergegeven of gedownload.
   * Kanalen/apparaten waardoor het middel werd gebruikt.
   * Creatieve oplossingen waarbij het middel onlangs is gebruikt.

   Zie voor meer informatie [Assets Insights](touch-ui-asset-insights.md).

1. Tik op **[!UICONTROL Save & Close]**.
1. Navigeer naar de interface Elementen. De bewerkte eigenschappen van metagegevens, zoals titel, beschrijving, classificaties, enzovoort, worden weergegeven op de elementenkaart in de kaartweergave en onder de desbetreffende kolommen in de lijstweergave.

## Elementen kopiëren {#copying-assets}

Wanneer u een middel of een omslag kopieert, wordt het volledige middel of de omslag gekopieerd, samen met zijn inhoudsstructuur. Een gekopieerd middel of een omslag wordt gedupliceerd bij de doelplaats. Het element op de bronlocatie wordt niet gewijzigd.

Enkele kenmerken die uniek zijn voor een bepaalde kopie van een element, worden niet overgedragen. Enkele voorbeelden zijn:

* Element-id, aanmaakdatum en -tijd en versies en versiegeschiedenis. Sommige van deze eigenschappen worden aangegeven door de eigenschappen `jcr:uuid`, `jcr:created`, en `cq:name`.

* De aanmaaktijd en de paden waarnaar wordt verwezen, zijn uniek voor elk element en elke uitvoering ervan.

De andere eigenschappen en metagegevens blijven behouden. Er wordt geen gedeeltelijke kopie gemaakt wanneer een element wordt gekopieerd.

1. Selecteer een of meer elementen in de interface Elementen en tik vervolgens op de knop **[!UICONTROL Copy]** op de werkbalk. U kunt ook de optie **[!UICONTROL Copy]** snelle actie van de assetkaart.

   ![copy_icon](assets/copy_icon.png)

   >[!NOTE]
   >
   >Als u het **[!UICONTROL Copy]** snel kunt u slechts één element tegelijk kopiëren.

1. Navigeer naar de locatie waar u de elementen wilt kopiëren.

   >[!NOTE]
   >
   >Als u een element op dezelfde locatie kopieert, [!DNL Experience Manager] genereert automatisch een variatie in de naam. Als u bijvoorbeeld een element met de naam Vierkant kopieert, [!DNL Experience Manager] genereert automatisch de titel voor de kopie als Square1.

1. Tik op de knop **[!UICONTROL Paste]** middelenpictogram van de werkbalk:

   ![chlimage_1-14](assets/chlimage_1-14.png)

   De elementen worden naar deze locatie gekopieerd.

   >[!NOTE]
   >
   >De **[!UICONTROL Paste]** is beschikbaar op de werkbalk totdat de plakbewerking is voltooid.

## Elementen verplaatsen en hernoemen {#moving-or-renaming-assets}

Wanneer u elementen (of mappen) naar een andere locatie verplaatst, worden de elementen (of mappen) tijdens het kopiëren van het element niet gedupliceerd. De elementen (of mappen) worden op de doellocatie geplaatst en worden van de bronlocatie verwijderd. U kunt de naam van het element ook wijzigen wanneer u het naar de nieuwe locatie verplaatst. Als u een gepubliceerd element naar een andere locatie verplaatst, kunt u het element opnieuw publiceren. Door gebrek beweeg verrichting op gepubliceerde activa maakt automatisch het ongedaan. Verplaatst element wordt opnieuw gepubliceerd als de auteur het [!UICONTROL Republish] optie bij het verplaatsen van het element.

![U kunt een reeds gepubliceerd element opnieuw publiceren wanneer u het verplaatst](assets/republish-on-move.png)

Elementen of mappen verplaatsen:

1. Navigeer naar de locatie van het element dat u wilt verplaatsen.

![U kunt een reeds gepubliceerd element opnieuw publiceren wanneer u het verplaatst](assets/republish-on-move.png)

Elementen of mappen verplaatsen:

1. Navigeer naar de locatie van het element dat u wilt verplaatsen.

1. Selecteer het element en klik op **[!UICONTROL Move]** van de werkbalk.
   ![Optie Verplaatsen op de werkbalk Elementen](assets/do-not-localize/move_icon.png)

1. In de [!UICONTROL Move Assets] Voer een van de volgende handelingen uit:

   * Geef de naam voor het element op nadat het is verplaatst. Klik vervolgens op **[!UICONTROL Next]** om verder te gaan.

   * Klikken **[!UICONTROL Cancel]** om het proces te stoppen.
   >[!NOTE]
   >
   >* U kunt dezelfde naam opgeven voor het element als er geen element met die naam is op de nieuwe locatie. U moet echter een andere naam gebruiken als u het element verplaatst naar een locatie waar zich een element met dezelfde naam bevindt. Als u dezelfde naam gebruikt, genereert het systeem automatisch een variatie in de naam. Als uw element bijvoorbeeld de naam Vierkant heeft, genereert het systeem de naam Vierkant1 voor de kopie.
   >* Bij het wijzigen van de naam is witruimte niet toegestaan in de bestandsnaam.


1. Op de **[!UICONTROL Select Destination]** voert u een van de volgende handelingen uit:

   * Navigeer naar de nieuwe locatie voor de elementen en klik vervolgens op **[!UICONTROL Next]** om verder te gaan.

   * Klikken **[!UICONTROL Back]** om terug te keren naar de **[!UICONTROL Rename]** scherm.

1. Als de elementen die worden verplaatst, verwijzen naar pagina&#39;s, elementen of verzamelingen, wordt het **[!UICONTROL Adjust References]** wordt weergegeven naast de **[!UICONTROL Select Destination]** tab.

   Voer een van de volgende handelingen uit in het dialoogvenster **[!UICONTROL Adjust References]** scherm:

   * Geef de referenties op die u wilt aanpassen op basis van de nieuwe details en klik vervolgens op **[!UICONTROL Move]** om verder te gaan.

   * Van de **[!UICONTROL Adjust]** , selecteert of deselecteert u verwijzingen naar de elementen.
   * Klikken **[!UICONTROL Back]** om terug te keren naar de **[!UICONTROL Select Destination]** scherm.

   * Klikken **[!UICONTROL Cancel]** om de verplaatsingsbewerking te stoppen.

   Als u verwijzingen niet bijwerkt, blijven ze naar het vorige pad van het element wijzen. Als u de referenties aanpast, worden deze bijgewerkt naar het nieuwe middelenpad.

### Elementen verplaatsen met behulp van sleepbewerking {#move-using-drag}

U kunt elementen (of mappen) naar een map op hetzelfde niveau verplaatsen door deze naar de doellocatie te slepen in plaats van ze te gebruiken [!UICONTROL Move] in de gebruikersinterface. Deze bewerking is echter alleen mogelijk in de lijstweergave.

Elementen verplaatsen door ze te slepen, wordt niet geopend [!UICONTROL Move Asset] Daarom kunt u de naam van de elementen tijdens het verplaatsen niet wijzigen. Bovendien worden de reeds gepubliceerde elementen opnieuw gepubliceerd wanneer ze door slepen worden verplaatst, zonder dat de gebruiker toestemming moet vragen om ze opnieuw te publiceren.

![Elementen naar secundaire mappen verplaatsen door elementen te slepen](assets/move-by-drag.gif)

## Uitvoeringen beheren {#managing-renditions}

1. U kunt uitvoeringen voor een element toevoegen of verwijderen, behalve voor het origineel. Navigeer naar de locatie van het element waaraan u uitvoeringen wilt toevoegen of verwijderen.

1. Tik op het element om de elementpagina te openen.

   ![chlimage_1-15](assets/chlimage_1-15.png)

1. Tik op de knop **[!UICONTROL Global Navigation]** en selecteert u **[!UICONTROL Renditions]** in de lijst.

   ![renditions_menu](assets/renditions_menu.png)

1. In de **[!UICONTROL Renditions]** weergegeven.

   ![renditions_panel](assets/renditions_panel.png)

   >[!NOTE]
   >
   >Standaard, [!DNL Experience Manager] In de voorvertoningsmodus wordt de oorspronkelijke uitvoering van het element niet weergegeven. Als beheerder kunt u overlays gebruiken om [!DNL Experience Manager] Elementen waarmee originele uitvoeringen worden weergegeven in de voorvertoningsmodus.

1. Selecteer een vertoning om de vertoning weer te geven of te verwijderen.

   **Een vertoning verwijderen**

   Selecteer een vertoning in het menu **[!UICONTROL Renditions]** tikt u op de **[!UICONTROL Delete Rendition]** van het pictogram [werkbalk](/help/sites-authoring/basic-handling.md). Uitvoeringen kunnen niet bulksgewijs worden verwijderd nadat de verwerking van het element is voltooid. Voor afzonderlijke elementen kunt u uitvoeringen handmatig uit de gebruikersinterface verwijderen. Voor meerdere elementen kunt u de Experience Manager aanpassen om bepaalde uitvoeringen te verwijderen of om de elementen te verwijderen en de verwijderde elementen opnieuw te uploaden.

   ![delete_renditionicon](assets/delete_renditionicon.png)

   **Een nieuwe uitvoering uploaden**

   Navigeer naar de pagina met elementdetails voor het element en tik op de **[!UICONTROL Add Rendition]** op de werkbalk om een nieuwe uitvoering voor het element te uploaden.

   ![chlimage_1-16](assets/chlimage_1-16.png)

   >[!NOTE]
   >
   >Als u een uitvoering selecteert in het deelvenster **[!UICONTROL Renditions]**, verandert de context van de werkbalk en worden alleen die acties weergegeven die relevant zijn voor de uitvoering. Opties, zoals de **[!UICONTROL Upload Rendition]** wordt niet weergegeven. Ga naar de pagina met details voor de asset om deze opties in de werkbalk weer te geven.

   U kunt de afmetingen configureren voor de vertoning die u wilt weergeven op de detailpagina van een afbeelding of video-element. Op basis van de opgegeven afmetingen [!DNL Experience Manager] Met Elementen wordt de vertoning weergegeven met de exacte of dichtstbijzijnde afmetingen.

   Als u de vertoningsafmetingen van een afbeelding wilt configureren op het niveau van de elementdetails, bedekt u de **[!UICONTROL renditionpicker]** node `libs/dam/gui/content/assets/assetpage/jcr:content/body/content/content/items/assetdetail/items/col1/items/assetview/renditionpicker` en configureert u de waarde van de eigenschap width. Configureer de eigenschap **[!UICONTROL size (Long) in KB]** in plaats van de breedte om de weergave op de pagina met assetdetails aan te passen op basis van de afbeeldingsgrootte. Voor aanpassing op basis van grootte wijst de eigenschap **[!UICONTROL preferOriginal]** de voorkeur toe aan het origineel als de grootte van de overeenkomstige weergave groter is dan het origineel.

   Op dezelfde manier kunt u het **[!UICONTROL Annotation]** paginaafbeelding door bedekken `libs/dam/gui/content/assets/annotate/jcr:content/body/content/content/items/content/renditionpicker`.

   ![chlimage_1-17](assets/chlimage_1-17.png)

   Navigeer naar het deelvenster **[!UICONTROL videopicker]** knooppunt in de CRX-opslagplaats op de locatie `/libs/dam/gui/content/assets/assetpage/jcr:content/body/content/content/items/assetdetail/items/col1/items/assetview/videopicker`, bedekt het knooppunt en bewerkt vervolgens de desbetreffende eigenschap.

   >[!NOTE]
   >
   >Videoaantekeningen worden alleen ondersteund in browsers met video-indelingen die compatibel zijn met HTML5. Afhankelijk van de browser worden bovendien verschillende video-indelingen ondersteund.

Voor informatie over subassets raadpleegt u [submiddelen beheren](managing-linked-subassets.md).

## Elementen verwijderen {#deleting-assets}

Als u de inkomende verwijzingen van andere pagina&#39;s wilt oplossen of verwijderen, werkt u de relevante verwijzingen bij voordat u een element verwijdert.

Schakel ook de knop forceren verwijderen uit met behulp van een overlay, zodat gebruikers geen bestanden waarnaar wordt verwezen kunnen verwijderen en verbroken koppelingen behouden blijven.

U hebt verwijdermachtigingen voor dam/asset nodig om een element te kunnen verwijderen. Als u alleen over wijzigingsmachtigingen beschikt, kunt u alleen de metagegevens van de elementen bewerken en annotaties toevoegen aan het element. U kunt het element of de metagegevens echter niet verwijderen.

**Elementen verwijderen**:

1. Navigeer naar de locatie van de elementen die u wilt verwijderen.

1. Selecteer het element en tik op het **[!UICONTROL Delete]** op de werkbalk.

   ![delete_icon](assets/delete_icon.png)

1. Tik in het bevestigingsdialoogvenster op:

   * **[!UICONTROL Cancel]** om de handeling te stoppen
   * **[!UICONTROL Delete]** de actie bevestigen op basis van het volgende:

      * Als het element geen verwijzingen bevat, wordt het element verwijderd.
      * Als het element verwijzingen bevat, wordt u via een foutbericht geïnformeerd dat **[!UICONTROL One or more assets are referenced]**. U kunt **[!UICONTROL Force Delete]** of **[!UICONTROL Cancel]**.

   >[!NOTE]
   >
   >Als u de inkomende verwijzingen van andere pagina&#39;s wilt oplossen of verwijderen, werkt u de relevante verwijzingen bij voordat u een element verwijdert.
   >
   >Schakel ook de **[!UICONTROL Force Delete]** gebruiken van een bedekking, om gebruikers te verbieden om de middelen waarnaar wordt verwezen te verwijderen en verbroken koppelingen te behouden.

## Elementen downloaden {#downloading-assets}

Zie [Elementen downloaden van AEM](download-assets-from-aem.md)

## Elementen publiceren en publiceren ongedaan maken {#publish-assets}

Nadat u elementen hebt geüpload, verwerkt of bewerkt op [!DNL Experience Manager] auteur, publiceert u het element naar de publicatieserver. Door middel van publicatie wordt het middel openbaar gemaakt. Met de actie Unpublishing is het element van de publicatieserver verwijderd, maar niet van de publicatieserver.

Voor specifieke informatie [!DNL Dynamic Media], zie [publiceren [!DNL Dynamic Media] elementen](publishing-dynamicmedia-assets.md).

1. Navigeer naar de locatie van het element of de map met middelen die u wilt publiceren of die u uit de publicatieomgeving wilt verwijderen (publicatie ongedaan maken).

1. Selecteer het element of de map waarvan u de publicatie wilt ongedaan maken en klik op **[!UICONTROL Manage Publication]** ![publicatieoptie beheren](assets/do-not-localize/globe-publication.png) van de werkbalk. Als u snel wilt publiceren, selecteert u de optie **[!UICONTROL Quick Publish]** van de werkbalk. Als de map die u wilt publiceren een lege map bevat, wordt de lege map niet gepubliceerd.

1. Selecteer **[!UICONTROL Publish]** of **[!UICONTROL Unpublish]** naar wens.

   ![Handeling Unpublish](assets/unpublish_action.png)
   *Afbeelding: Publiceer- en publicatieopties en de planningsoptie.*

1. Selecteren **[!UICONTROL Now]** om direct op het middel te handelen of selecteer **[!UICONTROL Later]** om de actie te plannen. Selecteer een datum en tijd als u de optie **[!UICONTROL Later]** optie. Klik op **[!UICONTROL Next]**.

1. Als een element bij het publiceren naar andere elementen verwijst, worden de bijbehorende verwijzingen in de wizard weergegeven. Alleen die verwijzingen worden weergegeven die niet zijn gepubliceerd of zijn gewijzigd sinds de laatste publicatie. Kies de referenties die u wilt publiceren.

1. Wanneer u de publicatie ongedaan maakt, kiest u de referenties die u ongedaan wilt maken wanneer een element naar andere elementen verwijst. Klik op **[!UICONTROL Unpublish]**. Klik in het bevestigingsdialoogvenster op **[!UICONTROL Cancel]** om de handeling te stoppen of klik op **[!UICONTROL Unpublish]** om te bevestigen dat de activa op de vastgestelde datum niet gepubliceerd zullen worden.

De volgende beperkingen en tips voor het publiceren of verwijderen van middelen of mappen zijn beschikbaar:

* De optie [!UICONTROL Manage Publication] is beschikbaar slechts aan de gebruikersrekeningen die replicatiemachtigingen hebben.
* Als u de publicatie van een complex element ongedaan maakt, maakt u alleen het element openbaar. Verwijder de publicatie van de verwijzingen niet omdat er mogelijk naar wordt verwezen door andere gepubliceerde elementen.
* Lege mappen worden niet gepubliceerd.
* Als u elementen publiceert die worden verwerkt, wordt alleen de oorspronkelijke inhoud gepubliceerd. De uitvoeringen ontbreken. Wacht tot de verwerking is voltooid en publiceer het element of publiceer het opnieuw nadat de verwerking is voltooid.

## Een gesloten gebruikersgroep maken {#closed-user-group}

Een CUG (Closed User Group) wordt gebruikt om de toegang te beperken tot specifieke mappen met elementen die vanuit AEM worden gepubliceerd. Als u een CUG maakt voor een map, is de toegang tot de map (inclusief mapelementen en submappen) beperkt tot alleen toegewezen leden of groepen. Om tot de omslag toegang te hebben, moeten zij login gebruikend hun veiligheidsgeloofsbrieven.

CUG is een extra manier om de toegang tot uw elementen te beperken. U kunt ook een aanmeldingspagina voor de map configureren.

**Een gesloten gebruikersgroep maken**:

1. Selecteer een map in de interface Middelen en tik op de knop **[!UICONTROL Properties]** op de werkbalk om de pagina met eigenschappen weer te geven.
1. Van de **[!UICONTROL Permissions]** tabblad, leden of groepen toevoegen onder **[!UICONTROL Closed User Group]**.

   ![add_user](assets/add_user.png)

1. Als u een aanmeldingsscherm wilt weergeven wanneer gebruikers de map openen, selecteert u de optie **[!UICONTROL Enable]** optie. Selecteer vervolgens het pad naar een aanmeldingspagina in AEM en sla de wijzigingen op.

   ![login_page](assets/login_page.png)

   Als u het pad naar een aanmeldingspagina niet opgeeft, [!DNL Experience Manager] Hiermee geeft u de standaardaanmeldingspagina weer in de publicatie-instantie.

1. Publiceer de map en probeer deze vervolgens te openen vanuit de publicatie-instantie. Er wordt een aanmeldingsscherm weergegeven.
1. Als u lid van de GECG bent, ga uw veiligheidsgeloofsbrieven in. De map wordt weergegeven na [!DNL Experience Manager] verklaart u voor authentiek.

## Assets doorzoeken {#searching-assets}

De basiszoekopdracht wordt in het gedeelte [Zoeken en filteren](/help/sites-authoring/search.md#search-and-filter) sectie. Gebruik de **[!UICONTROL Search]** om te zoeken naar elementen, tags en metagegevens. U kunt delen van een tekenreeks zoeken met de jokertekenasterisk. Daarnaast kunt u de opdracht **[!UICONTROL Search]** deelvenster gebruiken [Zoeken in facetten](search-facets.md).

![filters_panel](assets/filters_panel.png)

Voor recent geüploade elementen zijn de metagegevens (waaronder titels, tags, enzovoort) niet direct beschikbaar in de lijst met suggesties die worden weergegeven wanneer u in het vak Zoeken typt.

Dit komt omdat [!DNL Experience Manager] Elementen wachten tot een time-outperiode (standaard één uur) is verstreken voordat een achtergrondtaak wordt uitgevoerd. Deze taak is dan bedoeld om de metagegevens voor alle nieuw geüploade of bijgewerkte elementen te indexeren en deze aan de lijst met suggesties toe te voegen.

## Snelle handelingen gebruiken {#quick-actions}

De snelle actiepictogrammen zijn beschikbaar voor één middel tegelijkertijd. Voer afhankelijk van het apparaat de volgende handelingen uit om de snelactiepictogrammen weer te geven:

* Aanraakapparaten: Raak aan en houd de muisknop ingedrukt. Op een iPad kunt u bijvoorbeeld tikken en een element vasthouden, zodat de snelle acties worden weergegeven.
* Niet-aanraakapparaten: Aanwijzer aanwijzen. Op een bureaubladapparaat wordt bijvoorbeeld de snelle actiebalk weergegeven als u de aanwijzer boven de elementminiatuur houdt.

### Navigeren naar elementen en deze selecteren {#navigating-and-selecting-assets}

U kunt elementen met een van de beschikbare weergaven (kaart, kolom, lijst) weergeven, doorbladeren en selecteren met de opdracht **[!UICONTROL Select]** pictogram. **[!UICONTROL Select]** verschijnt als een snelle actie in de kaartmening.

![select_quick_action](assets/select_quick_action.png)

In de lijstweergave **[!UICONTROL Select]** verschijnt wanneer u het muispictogram boven de miniatuur plaatst vóór de namen van de elementen/map in de lijst.

![select_quick_in_listview](assets/select_quick_in_listview.png)

Vergelijkbaar met de lijstweergave, **[!UICONTROL Select]** verschijnt wanneer u het muispictogram boven de miniatuur plaatst vóór de namen van de middelen of map in de kolomweergave.

![select_quick_in_columnView](assets/select_quick_in_columnview.png)

Zie voor meer informatie [Uw bronnen weergeven en selecteren](/help/sites-authoring/basic-handling.md#viewing-and-selecting-resources).

## Afbeeldingen bewerken {#editing-images}

De bewerkingsgereedschappen in het dialoogvenster [!DNL Experience Manager] Met de interface Middelen kunt u kleine bewerktaken uitvoeren op afbeeldingselementen. U kunt afbeeldingen uitsnijden, roteren, spiegelen en andere bewerkingstaken uitvoeren. U kunt ook afbeeldingen met hyperlinks toevoegen aan elementen.

Beeldbewerking wordt ondersteund voor bestanden met de volgende indelingen:

* BMP
* GIF
* PNG
* JPEG

Voor sommige componenten: **[!UICONTROL Full Screen]** Er zijn aanvullende opties beschikbaar in deze modus.

Als u een TXT-bestand wilt bewerken, stelt u **[!UICONTROL Day CQ Link Externalizer]** vanuit Configuratiebeheer.

U kunt ook afbeeldingen met hyperlinks toevoegen met de afbeeldingseditor. Zie voor meer informatie [Afbeeldingen met hyperlinks toevoegen](image-maps.md).

**Afbeeldingen bewerken**:

1. Voer een van de volgende handelingen uit om een element te openen in de bewerkingsmodus:

   * Selecteer het element en klik op de knop **[!UICONTROL Edit]** in de werkbalk.
   * Tikken **[!UICONTROL Edit]** optie die op een element in de kaartweergave wordt weergegeven.
   * Tik op de elementpagina op de **[!UICONTROL Edit]** in de werkbalk.

   ![edit_icon](assets/edit_icon.png)

1. Tik op **[!UICONTROL Crop]**.

   ![chlimage_1-22](assets/chlimage_1-22.png)

1. Selecteer de gewenste optie in de lijst. Het bijsnijdgebied wordt op basis van de gekozen optie weergegeven in de afbeelding. De **[!UICONTROL Free Hand]** Met deze optie kunt u de afbeelding uitsnijden zonder beperkingen voor de hoogte-breedteverhouding.

   ![chlimage_1-23](assets/chlimage_1-23.png)

1. Selecteer het gebied dat u wilt uitsnijden en wijzig de grootte of de positie van het gebied in de afbeelding.
1. Gebruik de **[!UICONTROL Finish]** in de rechterbovenhoek om de afbeelding uit te snijden. Tapping **[!UICONTROL Finish]** activeert ook het opnieuw genereren van uitvoeringen.

   ![chlimage_1-24](assets/chlimage_1-24.png)

1. Gebruik de **[!UICONTROL Undo]** en **[!UICONTROL Redo]** pictogrammen rechtsboven om terug te keren naar de niet-uitgesneden afbeelding of om de uitgesneden afbeelding respectievelijk te behouden.

   ![chlimage_1-25](assets/chlimage_1-25.png)

1. Tik op de juiste **[!UICONTROL Rotate]** om de afbeelding rechtsom of linksom te roteren.

   ![chlimage_1-26](assets/chlimage_1-26.png)

1. Tik op de juiste **[!UICONTROL Flip]** om de afbeelding horizontaal of verticaal om te draaien.

   ![chlimage_1-27](assets/chlimage_1-27.png)

1. Tik op de knop **[!UICONTROL Finish]** om de wijzigingen op te slaan.

   ![chlimage_1-28](assets/chlimage_1-28.png)

## De tijdlijn gebruiken {#timeline}

De **[!UICONTROL Timeline]** Hiermee kunt u verschillende gebeurtenissen voor een geselecteerd item weergeven, zoals actieve workflows voor een element, opmerkingen, annotaties, activiteitenlogbestanden en versies.

In de [Collectieconsole](managing-collections-touch-ui.md#navigating-the-collections-console)de **[!UICONTROL Show All]** biedt alleen opties voor het weergeven van opmerkingen en workflows. Bovendien wordt de chronologie getoond slechts voor top-level inzamelingen die in de console vermeld zijn. Deze wordt niet weergegeven als u in een van de verzamelingen navigeert.

**[!UICONTROL Timeline]** bevat diverse [specifieke opties voor inhoudsfragmenten](content-fragments-managing.md#timeline-for-content-fragments); deze functionaliteit vereist [[!DNL Experience Manager] 6.4 Service Pack 2 (6.4.2.0)](/help/release-notes/sp-release-notes.md) of hoger.

**Tijdlijn gebruiken**:

1. Open de elementpagina voor een element of selecteer het in de Elementeninterface.
1. Tik op de knop **[!UICONTROL Global Navigation]** en kies **[Tijdlijn]** in de lijst.

   ![tijdlijn](assets/timeline.png)

1. In de lijst die wordt weergegeven, gebruikt u de opdracht **[!UICONTROL Show All]** om de resultaten te filteren op basis van opmerkingen, versies, workflows en activiteiten.

   ![timeline_options](assets/timeline_options.png)

## Annotaties toevoegen {#annotating}

Annotaties zijn opmerkingen of toelichtingen die aan afbeeldingen of video&#39;s worden toegevoegd. Annotaties bieden marketers de mogelijkheid samen te werken en feedback over middelen te geven.

Videoannotaties worden alleen ondersteund in browsers met video-indelingen die compatibel zijn met HTML5. Video-indelingen die [!DNL Experience Manager] De ondersteuning voor elementen is afhankelijk van de browser.

Voor inhoudsfragmenten, [notities worden gemaakt in de editor](content-fragments-variations.md#annotating-a-content-fragment); deze functionaliteit vereist [[!DNL Experience Manager] 6.4 Service Pack 2 (6.4.2.0)](/help/release-notes/sp-release-notes.md) of hoger.

U kunt meerdere annotaties toevoegen voordat u ze opslaat.

U kunt notities toevoegen aan video-elementen. Tijdens het annoteren van video&#39;s pauzeert de speler zodat u notities kunt aanbrengen in een frame. Zie voor meer informatie [beheren, video-elementen](managing-video-assets.md).

U kunt ook annotaties toevoegen aan een verzameling. Als een verzameling onderliggende verzamelingen bevat, kunt u echter alleen annotaties of opmerkingen aan de bovenliggende verzameling toevoegen. De **[!UICONTROL Annotate]** is niet beschikbaar voor onderliggende verzamelingen.

**Annotaties toevoegen**:

1. Navigeer naar de locatie van het element waaraan u annotaties wilt toevoegen.
1. Tik op de knop **[!UICONTROL Annotate]** pictogram uit een van de volgende opties:

   * [Snelle acties](managing-assets-touch-ui.md#quick-actions)
   * Vanuit de werkbalk nadat u het element hebt geselecteerd of naar de elementpagina bent genavigeerd

   ![chlimage_1-29](assets/chlimage_1-29.png)

1. Voeg een opmerking toe in het vak **[!UICONTROL Comment]** onder aan de tijdlijn. U kunt ook een gebied in de afbeelding markeren en een annotatie toevoegen in het dialoogvenster **[!UICONTROL Add Annotation]** in.

   ![chlimage_1-30](assets/chlimage_1-30.png)

1. Als u een gebruiker op de hoogte wilt stellen van een aantekening, geeft u het e-mailadres van de gebruiker op en voegt u de opmerking toe. Als u bijvoorbeeld Aaron McDonald op de hoogte wilt stellen van een annotatie, voert u @aa in. Tips voor alle overeenkomende gebruikers worden weergegeven in een lijst. Selecteer het e-mailadres van Aaron in de lijst om hem de opmerking te geven. Op dezelfde manier kunt u meer gebruikers overal in de annotatie of ervoor of erna een tag toewijzen.

   >[!NOTE]
   >
   >Voor een gebruiker die geen beheerder is, worden suggesties alleen weergegeven als de gebruiker Leesmachtigingen heeft op `/home` in CRXDE.

   ![chlimage_1-31](assets/chlimage_1-31.png)

1. Tik na het toevoegen van de annotatie op **[!UICONTROL Add]** om het op te slaan. Een kennisgeving voor de aantekening wordt verzonden naar Aaron.

   ![chlimage_1-32](assets/chlimage_1-32.png)

1. Tikken **[!UICONTROL Close]** om af te sluiten **[!UICONTROL Annotation]** in.
1. Meld u aan bij [!DNL Experience Manager] Hier vindt u informatie met de gegevens van Aaron MacDonald en tik op de **[!UICONTROL Notifications]** pictogram om het bericht weer te geven.

1. Tik op de knop **[!UICONTROL Profile]** pictogram en tik **[!UICONTROL My Preferences]**.

   ![chlimage_1-33](assets/chlimage_1-33.png)

1. Geef de gewenste kleur op in het dialoogvenster **[!UICONTROL Annotation Color]** doos, dan tikken **[!UICONTROL Accept]**.

   ![chlimage_1-34](assets/chlimage_1-34.png)

### Opgeslagen notities weergeven {#viewing-saved-annotations}

U kunt slechts één annotatie tegelijk weergeven.

>[!NOTE]
>
>Als u meerdere annotaties selecteert, wordt de laatste annotatie weergegeven in de gebruikersinterface.
>
>Multi-select wordt alleen ondersteund voor het afdrukken van het geannoteerde element als PDF.

1. Als u opgeslagen annotaties voor een element wilt weergeven, navigeert u naar de locatie van het element en opent u de elementpagina voor het element.

1. Tik op de knop **[!UICONTROL Global Navigation]** en tikken **[!UICONTROL Timeline]** in de lijst.

   ![chlimage_1-35](assets/chlimage_1-35.png)

1. Selecteer in de lijst **[!UICONTROL Show All]** in de tijdlijn de optie **[!UICONTROL Comments]** om de resultaten te filteren op basis van annotaties.

   ![chlimage_1-36](assets/chlimage_1-36.png)

1. Tik op een opmerking in het dialoogvenster **[!UICONTROL Timeline]** om de bijbehorende annotatie in de afbeelding weer te geven.

   ![chlimage_1-37](assets/chlimage_1-37.png)

1. Tikken **[!UICONTROL Delete]** om een bepaalde opmerking te verwijderen.

### Annotaties afdrukken {#printing-annotations}

Als een element annotaties heeft of een revisiewerkstroom heeft ondergaan, kunt u het element samen met annotaties afdrukken en de status controleren als een PDF-bestand voor offline revisie.

U kunt ook alleen de annotaties of de revisiestatus afdrukken.

>[!NOTE]
>
>U kunt meerdere annotaties selecteren wanneer u het geannoteerde element afdrukt als PDF.

Lengte annotaties worden mogelijk niet correct weergegeven in het PDF-bestand. Voor een optimale rendering raadt Adobe aan om annotaties te beperken tot 50 woorden.

Tik op de knop **[!UICONTROL Print]** en volgt u de instructies in de wizard. De **[!UICONTROL Print]** wordt alleen op de werkbalk weergegeven als aan het element ten minste één aantekening of revisiestatus is toegewezen.

1. Open vanuit de interface Middelen de voorvertoningspagina voor een element.
1. Voer een van de volgende handelingen uit:

   * Ga naar stap 4 als u alle annotaties en de revisiestatus wilt afdrukken.
   * Als u specifieke annotaties en de revisiestatus wilt afdrukken, opent u het dialoogvenster [Tijdlijn](managing-assets-touch-ui.md#timeline) en ga vervolgens verder met stap 3.

1. Als u specifieke annotaties wilt afdrukken, selecteert u de annotaties in het menu **[!UICONTROL Timeline]**.

   ![chlimage_1-38](assets/chlimage_1-38.png)

   Als u alleen de revisiestatus wilt afdrukken, selecteert u deze in het menu **[!UICONTROL Timeline]**.

   ![chlimage_1-39](assets/chlimage_1-39.png)

1. Tik op de werkbalk op de knop **[!UICONTROL Print]** pictogram.

   ![chlimage_1-40](assets/chlimage_1-40.png)

1. Van de **[!UICONTROL Print]** kiest u de positie die de annotaties of revisiestatus op de PDF moet worden weergegeven. Als u bijvoorbeeld wilt dat de annotaties of status rechtsboven op de pagina met de afgedrukte afbeelding worden afgedrukt, gebruikt u de optie **[!UICONTROL Top-Left]** (standaardwaarde).

   ![chlimage_1-41](assets/chlimage_1-41.png)

   U kunt andere instellingen kiezen, afhankelijk van de positie waar u de annotaties of status wilt weergeven in de afgedrukte PDF. Als u de annotaties of status wilt weergeven op een pagina die los staat van het afgedrukte element, kiest u **[!UICONTROL Next Page]**.

1. Tik op **[!UICONTROL Print]**. Afhankelijk van de optie die u kiest in stap 2, geeft de gegenereerde PDF de annotaties of status op de opgegeven positie weer. Als u bijvoorbeeld zowel notities als de revisiestatus wilt afdrukken met de opdracht **[!UICONTROL Top-Left]** Wanneer u instelt, lijkt de gegenereerde uitvoer op het PDF-bestand dat hier wordt weergegeven.

   ![chlimage_1-42](assets/chlimage_1-42.png)

1. Download of druk de PDF af met de opties rechtsboven.

   ![chlimage_1-43](assets/chlimage_1-43.png)

   >[!NOTE]
   >
   >Als het element subelementen bevat, kunt u alle subelementen samen met de specifieke paginagewijze annotaties afdrukken.

   Als u de vormgeving van het gerenderde PDF-bestand wilt wijzigen, bijvoorbeeld de lettertypekleur, -grootte en -stijl, de achtergrondkleur van de opmerkingen en status, opent u het dialoogvenster **[!UICONTROL Annotation PDF configuration]** van **[!UICONTROL Configuration Manager]** en wijzigt u de gewenste opties. Als u bijvoorbeeld de weergavekleur van de goedgekeurde status wilt wijzigen, wijzigt u de kleurcode in het desbetreffende veld. Zie voor informatie over het wijzigen van de lettertypekleur van annotaties [Annotatie](managing-assets-touch-ui.md#annotating).

   ![chlimage_1-44](assets/chlimage_1-44.png)

   Ga terug naar het gerenderde PDF-bestand en vernieuw het. De vernieuwde PDF geeft de wijzigingen weer die u hebt aangebracht.

**Annotaties afdrukken in vreemde talen**: Als een element annotaties in vreemde talen bevat (met name niet-Latijnse talen), moet u eerst CQ-DAM-Handler-Gibson Font Manager Service configureren op de [!DNL Experience Manager] -server om deze annotaties af te drukken. Geef bij het configureren van de service CQ-DAM-Handler-Gibson Font Manager het pad op waar de lettertypen voor de gewenste talen zich bevinden.

1. Open de **[!UICONTROL CQ-DAM-Handler-Gibson Font Manager Service]** configuratiepagina via de URL [https://&lt;server>:&lt;port>/system/console/configMgr/com.day.cq.dam.handler.gibson.fontmanager.impl.FontManagerServiceImpl](http://localhost:4502/system/console/configMgr/com.day.cq.dam.handler.gibson.fontmanager.impl.FontManagerServiceImpl).
1. Om te vormen **[!UICONTROL CQ-DAM-Handler-Gibson Font Manager Service]** Voer een van de volgende handelingen uit:

   * In de **[!UICONTROL System Fonts]** Geef het volledige pad naar de map met lettertypen op uw systeem op. Als u bijvoorbeeld een Mac-gebruiker bent, kunt u het pad opgeven als `/Library/Fonts` in de **[!UICONTROL System Fonts]** directory, optie. [!DNL Experience Manager] haalt de lettertypen op uit deze map.
   * Een map maken met de naam **lettertypen** binnen **[!UICONTROL crx-quickstart]** map. **[!UICONTROL CQ-DAM-Handler-Gibson Font Manager Service]** haalt automatisch de lettertypen op de locatie op `crx-quickstart/fonts`. U kunt dit standaardpad overschrijven vanuit het dialoogvenster **[!UICONTROL Adobe Server Fonts]** directory, optie.
   * Maak een nieuwe map voor lettertypen op uw systeem en sla de gewenste lettertypen op in de map. Geef vervolgens het volledige pad naar die map op in het dialoogvenster **[!UICONTROL Customer Fonts]** directory, optie.

1. Toegang krijgen tot **[!UICONTROL Annotation PDF]** configuratie via de URL [https://&lt;server>:&lt;port>/system/console/configMgr/com.day.cq.dam.core.impl.annotation.pdf.AnnotationPdfConfig](http://localhost:4502/system/console/configMgr/com.day.cq.dam.core.impl.annotation.pdf.AnnotationPdfConfig).
1. Configureer de **[!UICONTROL Annotation PDF]** met de juiste set lettertypefamilies, als volgt:

   * De tekenreeks opnemen `<font_family_name_of_custom_font, sans-serif>` in de optie font-family. Als u bijvoorbeeld annotaties wilt afdrukken in CJK (Chinees, Japans en Koreaans), neemt u de tekenreeks op `Arial Unicode MS, Noto Sans, Noto Sans CJK JP, sans-serif` in de optie font-family. Als u annotaties wilt afdrukken in het Hindi, downloadt u het juiste lettertype en configureert u de lettertypefamilie als Arial Unicode MS, Noto Sans, Noto Sans CJK JP, Noto Sans Devanagari, sans-serif.

1. Start de [!DNL Experience Manager] -instantie.

Het volgende is een voorbeeld van hoe u vormt [!DNL Experience Manager] voor het afdrukken van annotaties in CJK (Chinees, Japans en Koreaans):

1. Download Google Noto CJK-lettertypen van de volgende koppelingen en sla deze op in de lettertypemap die is geconfigureerd in Font Manager Service.

   * All in One Super CJK font: [https://www.google.com/get/noto/help/cjk/](https://www.google.com/get/noto/help/cjk/)
   * Noto Sans (voor Europese talen): [https://www.google.com/get/noto/](https://www.google.com/get/noto/)
   * Geen lettertypen voor een taal van uw keuze: [https://www.google.com/get/noto/](https://www.google.com/get/noto/)

1. Configureer het PDF-bestand van de annotatie door de parameter font-family in te stellen op `Arial Unicode MS, Noto Sans, Noto Sans CJK JP, sans-serif`. Deze configuratie is standaard beschikbaar en werkt voor alle Europese en CJK-talen.
1. Als de taal van uw keuze afwijkt van de talen die in stap 2 worden genoemd, voegt u een geschikt item (gescheiden door komma&#39;s) toe aan de standaardlettertypefamilie.

## Elementversie maken {#asset-versioning}

Met Versioning maakt u een momentopname van digitale elementen op een bepaald tijdstip. Versioning helpt bij het terugzetten van elementen naar een vorige status op een later tijdstip. Als u bijvoorbeeld een wijziging in een element ongedaan wilt maken, herstelt u de onbewerkte versie van het element.

Hieronder vindt u scenario&#39;s waarin u versies maakt:

* U wijzigt een afbeelding in een andere toepassing en uploadt deze naar [!DNL Experience Manager] Elementen. Er wordt een versie van de afbeelding gemaakt, zodat de oorspronkelijke afbeelding niet wordt overschreven.
* U bewerkt de metagegevens van een element.
* U gebruikt [!DNL Experience Manager] bureaubladtoepassing om een bestaand middel uit te checken en uw wijzigingen op te slaan. Telkens wanneer het element wordt opgeslagen, wordt een nieuwe versie gemaakt.

U kunt automatische versioning ook inschakelen via een workflow. Wanneer u een versie voor een element maakt, worden de metagegevens en de uitvoeringen samen met de versie opgeslagen. Uitvoeringen zijn alternatieven voor dezelfde afbeeldingen, bijvoorbeeld een PNG-uitvoering van een geüpload JPEG-bestand.

Met de versiefunctionaliteit kunt u het volgende doen:

* Maak een versie van een element.
* De huidige revisie voor een element weergeven.
* Herstel het element naar een vorige versie.

**Elementversiebeheer maken**:

1. Navigeer naar de locatie van het element waarvoor u een versie wilt maken en klik erop om de elementpagina te openen.

1. Klik op de knop **[!UICONTROL Global Navigation]** en kiest u **[!UICONTROL Timeline]** in het menu.

   ![timeline-1](assets/timeline-1.png)

1. Klikken **[!UICONTROL Actions]** onder aan om de beschikbare acties weer te geven die u op het element kunt uitvoeren.

1. Klikken **[!UICONTROL Save as Version]** om een versie voor het element te maken.

   ![chlimage_1-46](assets/chlimage_1-46.png)

1. Voeg een label en een opmerking toe en klik vervolgens op **[!UICONTROL Create]** om een versie te maken. Of tik op **[!UICONTROL Cancel]** om de bewerking af te sluiten.

   ![chlimage_1-47](assets/chlimage_1-47.png)

1. Als u de nieuwe versie wilt weergeven, opent u de **[!UICONTROL Show All]** in de tijdlijn vanaf de pagina met elementdetails of de [!DNL Assets] en kiest u **[!UICONTROL Versions]**.

   ![version_option](assets/versions_option.png)

1. Selecteer een specifieke versie voor het element om er een voorvertoning van weer te geven of schakel de optie in voor weergave in de interface Middelen.

   ![select_version](assets/select_version.png)

   >[!NOTE]
   >
   >U kunt ook het element selecteren in het menu [Lijstweergave](/help/sites-authoring/basic-handling.md#viewing-and-selecting-resources) of de [Kolomweergave](/help/sites-authoring/basic-handling.md#viewing-and-selecting-resources).

1. Voeg een label en een opmerking voor de versie toe om terug te keren naar de specifieke versie in de interface Middelen.

   ![save_version](assets/save_version.png)

1. Als u een voorvertoning voor de versie wilt genereren, klikt u op **[!UICONTROL Preview Version]**.
1. Selecteer **[!UICONTROL Revert to this Version]**.
1. Als u twee versies wilt vergelijken, gaat u naar de elementpagina van het element en klikt u op de versie die u wilt vergelijken met de huidige versie.

   ![Selecteer een vorige versie van het element die u met de huidige versie wilt vergelijken](assets/select_version_tocompare.png)

1. Selecteer in de tijdlijn de versie die u wilt vergelijken en sleep de schuifregelaar naar links om deze versie over de huidige versie heen te plaatsen en te vergelijken.

   ![compare_versions](assets/compare_versions.png)

### Een workflow op een element starten {#starting-a-workflow-on-an-asset}

Zie [een workflow toepassen op een [!DNL Experience Manager] element](/help/assets/assets-workflow.md#apply-a-workflow-to-an-aem-asset).

## Informatie over verzamelingen {#collections}

Een verzameling is een geordende set elementen. Gebruik verzamelingen om elementen tussen gebruikers te delen.

* Een verzameling kan elementen van verschillende locaties bevatten, omdat deze alleen verwijzingen naar deze elementen bevatten. Bij elke verzameling blijft de referentiële integriteit van de elementen behouden.
* U kunt verzamelingen delen met meerdere gebruikers met verschillende machtigingsniveaus, zoals bewerken, weergeven, enzovoort.

Een gebruiker kan toegang hebben tot meerdere verzamelingen. De inzamelingen zijn van de volgende types, die op de manier worden gebaseerd zij activa sorteren:

* Een verzameling met een **statische referentielijst** van elementen, mappen en andere verzamelingen.

* Een verzameling die een **zoekcriteria** en worden elementen dynamisch gevuld op basis van de criteria. Dit wordt een **Slimme verzameling**.

Zie [Verzamelingen beheren](managing-collections-touch-ui.md) voor meer informatie over verzamelingsbeheer.

>[!NOTE]
>
>U hebt de juiste toegangsrechten voor uw account nodig om elementen te maken of te bewerken.
