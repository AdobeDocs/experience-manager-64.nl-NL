---
title: De indeling en positie van foutberichten van een adaptief formulier aanpassen
seo-title: Customize layout and positioning of error messages of an adaptive form
description: U kunt de lay-out en de positie van de foutberichten van een adaptief for aanpassen.
seo-description: You can customize layout and positioning of the error messages of an adaptive for.
uuid: 18b6d770-8b68-4aa0-b866-6325a6ceabcf
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: customization
discoiquuid: e1431ad9-3bae-4ac3-97e2-96dcbfce1f71
exl-id: a57bd3c4-2d50-4089-8279-1e403e9469bf
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 0%

---

# De indeling en positie van foutberichten van een adaptief formulier aanpassen {#customize-layout-and-positioning-of-error-messages-of-an-adaptive-form}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

U kunt de indeling en de positie van de foutberichten in een adaptief formulier aanpassen. U kunt de volgende aanpassingen uitvoeren:

* Locatie en lay-out van het bijschrift van een veld aanpassen zonder wijzigingen aan te brengen in de bijbehorende CSS-eigenschappen
* Positie van inline foutberichten aanpassen
* Inhoud van dynamische Help-indicator aanpassen
* De positie van de veldcomponenten (bijschrift, widget, korte beschrijving, lange beschrijving en Help-indicatorcomponenten) aanpassen zonder wijzigingen aan te brengen in de bijbehorende CSS-eigenschappen

## Lay-out van velden aanpassen {#customize-layout-of-fields}

U kunt de indeling van één veld of van alle velden aanpassen om de positie van bijschrift en foutberichten te wijzigen. Voer de volgende stappen uit om een aangepaste indeling toe te passen op een veld:

### Lay-out van één veld aanpassen {#customize-layout-of-a-single-field}

Voer de volgende stappen uit om een aangepaste indeling toe te passen op één veld:

1. Open het formulier in **Stijl** in. Als u het formulier in de stijlmodus wilt openen, tikt u op de paginaboolbalk ![canvas-drop-down](assets/canvas-drop-down.png) > **Stijl**.
1. In de zijbalk, onder **Formulierobjecten**, selecteert u het veld en tikt u op de knop Bewerken ![bewerken, knop](assets/edit-button.png).
1. Selecteer de status van het veld dat u wilt aanpassen en geef de opmaak voor die status op.

   ![Inline opmaak van een veld opgeven](assets/edit-error-state.png)

### De indeling van alle velden van een formulier aanpassen {#customize-layout-of-all-the-fields-of-a-form}

Met AEM Forms kunt u nu een thema maken en dit toepassen op uw formulier. Met de Thema-editor kunt u op één plaats opmaak van formuliercomponenten opgeven. Wanneer u een thema maakt, geeft u de stijl op componentniveau op. Voor meer informatie over thema&#39;s raadpleegt u [Thema&#39;s in AEM Forms](/help/forms/using/themes.md).

Maak een thema met de Thema-editor om de indeling van alle velden in het formulier aan te passen. Nadat u een thema hebt gemaakt, voert u de volgende stappen uit om het op een formulier toe te passen:

1. Open het formulier in de bewerkingsmodus.
1. Selecteer in de bewerkingsmodus een component en tik vervolgens op ![op veldniveau](assets/field-level.png) > **Aangepaste formuliercontainer** en tikt u vervolgens op ![cmppr](assets/cmppr.png).
1. Selecteer in het zijpaneel onder Adaptief formulierthema het thema dat u hebt gemaakt met de Thema-editor.

## Een aangepaste veldindeling maken {#create-a-custom-field-layout}

1. CRXDE-lijst openen. De standaard-URL is `https://[Server]:[Port]/crx/de`.
1. Kopieer een veldlay-out van het knooppunt /libs/fd/af/layouts/field (bijvoorbeeld defaultFieldLayout) naar het knooppunt /apps (bijvoorbeeld /apps/af-field-layout).
1. Wijzig de naam van het gekopieerde knooppunt en het bestand defaultFieldLayout.jsp. Bijvoorbeeld errorOnRight.jsp.

1. Waarde wijzigen van de eigenschappen qtip en jcr:description van het gekopieerde knooppunt. Wijzig bijvoorbeeld de waarde van de eigenschappen in Fout rechts

1. Om nieuwe stijlen en gedrag toe te voegen, creeer een cliëntbibliotheek in de /etc knoop.

   Creëer bijvoorbeeld op de locatie /etc/af-field-layout-clientlib de client-library van het knooppunt. Voeg de eigenschap Categorieën toe met het bestand value.field.errorOnRight en style.less met de volgende code:

   ```css
   .widgetErrorWrapper {
   
    height: 38px;
    margin: 5px;
   
    .guideFieldWidget{
    width: 60%;
    float: left; 
    }
   
    .guideFieldError{
    overflow:hidden;
    width:40%; 
    }
   
   }
   ```

1. Als u de weergave en het gedrag wilt verbeteren, neemt u de clientbibliotheek op die in het lay-outbestand is gemaakt (errorOnRight.jsp).
1. Open het dialoogvenster Bewerken van het veld en selecteer de optie **Stijlen** tab. In de **Veldlay-out configureren** keuzelijst, selecteert u de nieuwe lay-out en klikt u op **OK**.

Het pakket ErrorOnRight.zip bevat code waarmee foutberichten aan de rechterkant van velden worden weergegeven.

[Bestand ophalen](assets/erroronright.zip)
