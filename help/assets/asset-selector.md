---
title: Asset Selector
description: Leer hoe u met de kiezer voor middelen metagegevens voor elementen in Adobe Experience Manager-middelen (AEM) kunt zoeken, filteren, doorbladeren en ophalen. Leer ook hoe u de interface van de elementenkiezer kunt aanpassen.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 1de8efce9cd5cf47163cba8f0c962a9e2fc5116c
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 0%

---


# Elementkiezer {#asset-selector}

>[!NOTE]
>
>De Asset Selector werd [Asset picker](https://helpx.adobe.com/experience-manager/6-2/assets/using/asset-picker.html) genoemd in eerdere versies van AEM.

Met de elementkiezer kunt u elementen in [!DNL Adobe Experience Manager] Elementen zoeken en filteren. U kunt ook de metagegevens ophalen van elementen die u selecteert met de elementenkiezer. Als u de interface van de elementenkiezer wilt aanpassen, kunt u deze starten met ondersteunde aanvraagparameters. Met deze parameters wordt de context van de elementenkiezer voor een bepaald scenario ingesteld.

Momenteel kunt u de verzoekparameters `assettype` (*Image/Video/Text*) en selectie `mode` (*Single/Multiple*) als contextuele informatie voor de activaselecteur overgaan, die door de selectie intact blijft.

De elementenkiezer gebruikt het HTML5 **Window.postMessage**-bericht om gegevens voor het geselecteerde element naar de ontvanger te verzenden.

De assetkiezer is gebaseerd op de woordenlijst van de grondkiezer van Granite. De elementenkiezer werkt standaard in de modus Bladeren. U kunt echter filters toepassen met behulp van de ervaring van Omngonderzoek om uw zoekopdracht naar bepaalde elementen te verfijnen.

U kunt elke webpagina (ongeacht of deze deel uitmaakt van de CQ-container) integreren met de elementenkiezer (`https://[AEM_server]:[port]/aem/assetpicker.html`).

## Contextuele parameters {#contextual-parameters}

U kunt de volgende aanvraagparameters in een URL doorgeven om de elementenkiezer in een bepaalde context te starten:

| Naam | Waarden | Voorbeeld | Doel |
|---|---|---|---|
| bronachtervoegsel (B) | Het pad van de map als het bronachtervoegsel in de URL:`http://localhost:4502/aem/`<br>`assetpicker.html/<folder_path>` | Als u de elementenkiezer wilt starten terwijl een bepaalde map is geselecteerd, bijvoorbeeld met de map `/content/dam/we-retail/en/activities` geselecteerd, moet de URL de volgende vorm hebben: `http://localhost:4502/aem/assetpicker.html`<br>`/content/dam/we-retail/en/activities?assettype=images` | Als u wilt dat een bepaalde map wordt geselecteerd wanneer de elementenkiezer wordt gestart, geeft u deze door als een bronachtervoegsel. |
| mode | enkelvoudig, meerdere | `http://localhost:4502/aem/assetpicker.html`<br>`?mode=multiple` <br> `http://localhost:4502/aem/assetpicker.html`<br>`?mode=single` | In meerdere modi kunt u meerdere elementen tegelijk selecteren met de elementkiezer. |
| dialoogvenster | true, false | `http://localhost:4502/aem/assetpicker.html`<br>`?dialog=true` | Gebruik deze parameters om de elementenkiezer te openen als granietdialoogvenster. Deze optie is alleen van toepassing wanneer u de elementenkiezer start via Granite Path Field en deze configureert als pickerSrc URL. |
| basis | `<folder_path>` | `http://localhost:4502/aem/`<br>`assetpicker.html?assettype=images`<br>`&root=/content/dam/we-retail/en/activities` | Gebruik deze optie om de hoofdmap voor de elementenkiezer op te geven. In dit geval kunt u met de elementenkiezer alleen onderliggende elementen (direct/indirect) in de hoofdmap selecteren. |
| viewmode | zoeken |  | De elementenkiezer starten in de zoekmodus met parameters assettype en mimetype. |
| assettype (S) | afbeeldingen, documenten, multimedia, archieven | <ul><li>`http://localhost:4502/aem/assetpicker.html?viewmode=search&assettype=images`</li> <li>`http://localhost:4502/aem/assetpicker.html?viewmode=search&assettype=documents`</li> <li>`http://localhost:4502/aem/assetpicker.html?viewmode=search&assettype=multimedia`</li> <li>`http://localhost:4502/aem/assetpicker.html?viewmode=search&assettype=archives`</li> | Gebruik deze optie om elementtypen te filteren op basis van de doorgegeven waarde. |
| mimetype | mimetype(s) (`/jcr:content/metadata/dc:format`) van een element (jokerteken wordt ook ondersteund) | <ul><li>`http://localhost:4502/aem/assetpicker.html?viewmode=search&mimetype=image/png`</li>  <li>`http://localhost:4502/aem/assetpicker.html?viewmode=search&?mimetype=*png`</li>  <li>`http://localhost:4502/aem/assetpicker.html?viewmode=search&mimetype=*presentation`</li>  <li>`http://localhost:4502/aem/assetpicker?viewmode=search&mimetype=*presentation&mimetype=*png`</li></ul> | Hiermee kunt u elementen filteren op basis van MIME-typen |

## Elementkiezer {#using-the-asset-selector} gebruiken

1. Ga naar `https://[AEM_server]:[port]/aem/assetpicker` om de interface van de elementenkiezer te openen.
1. Navigeer naar de gewenste map en selecteer een of meer elementen.

   ![chlimage_1-441](assets/chlimage_1-441.png)

   U kunt ook naar het gewenste element zoeken in het vak Universeel zoeken en het vervolgens selecteren.

   ![chlimage_1-442](assets/chlimage_1-442.png)

   Als u naar elementen zoekt met het vak OmniSearch, kunt u verschillende filters selecteren in het venster **[!UICONTROL Filters]** om uw zoekopdracht te verfijnen.

   ![chlimage_1-443](assets/chlimage_1-443.png)

1. Tik/klik op **[!UICONTROL Select]** op de werkbalk.
