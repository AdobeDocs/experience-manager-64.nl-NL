---
title: 'Lesbestand NIET PUBLICEREN: Regels toepassen op aangepaste formuliervelden"'
seo-title: Apply rules to adaptive form fields
description: Maak regels om interactiviteit, bedrijfslogica en slimme validaties toe te voegen aan een adaptief formulier.
seo-description: Create rules to add interactivity, business logic, and smart validations to an adaptive form.
page-status-flag: de-activated
uuid: 60f142aa-81ca-4333-8614-85a01e23e917
products: SG_EXPERIENCEMANAGER/6.3/FORMS
discoiquuid: 982eddba-2350-40e7-8a42-db02d28cf133
feature: Adaptive Forms
exl-id: bb65b6d7-5bbf-4cc5-a468-9ea8465f7a07
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1058'
ht-degree: 0%

---

# Zelfstudie: Regels toepassen op aangepaste formuliervelden {#tutorial-apply-rules-to-adaptive-form-fields}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

![06-apply-rules-to-adaptive-form_main](assets/06-apply-rules-to-adaptive-form_main.png)

Deze zelfstudie is een stap in de [Uw eerste adaptieve formulier maken](/help/forms/using/create-your-first-adaptive-form.md) reeks. Adobe raadt u aan de reeks in chronologische volgorde te volgen om de volledige Gebruikssituatie van de zelfstudie te begrijpen, uit te voeren en te demonstreren.

## Over de zelfstudie {#about-the-tutorial}

Met regels kunt u interactiviteit, bedrijfslogica en slimme validaties toevoegen aan een adaptief formulier. Adaptieve formulieren hebben een ingebouwde regeleditor. De regelredacteur verstrekt belemmering-en-dalingsfunctionaliteit, gelijkend op geleide reizen. De methode slepen en neerzetten is de snelste en eenvoudigste methode om regels te maken. De regelredacteur verstrekt ook een codevenster voor gebruikers geinteresseerd in het testen van hun coderingsvaardigheden of het nemen van de regels aan het volgende niveau.

U kunt meer over de regelredacteur leren bij [Adaptieve Forms-regeleditor](/help/forms/using/rule-editor.md).

Aan het einde van de zelfstudie leert u regels maken voor:

* Een service van het formuliergegevensmodel aanroepen om gegevens uit de database op te halen
* Een service van het formuliergegevensmodel aanroepen om gegevens aan de database toe te voegen
* Een validatiecontrole uitvoeren en foutberichten weergeven

Met interactieve afbeeldingen van GIFFEN aan het einde van elke sectie van de zelfstudie kunt u de functionaliteit van het formulier dat u maakt, direct leren kennen en valideren.

## Stap 1: Een klantrecord ophalen uit de database {#retrieve-customer-record}

U hebt een formuliergegevensmodel gemaakt door het volgende te doen [formuliergegevensmodel maken](/help/forms/using/create-form-data-model.md) artikel. Nu, kunt u de regelredacteur gebruiken om de diensten van het Gegevensmodel van Forms aan te halen om informatie aan het gegevensbestand terug te winnen en toe te voegen.

Elke klant krijgt een uniek klant-id-nummer toegewezen, waarmee relevante klantgegevens in een database kunnen worden geïdentificeerd. In de onderstaande procedure wordt de klant-id gebruikt om gegevens op te halen uit de database:

1. Open het aangepaste formulier voor bewerking.

   [http://localhost:4502/editor.html/content/forms/af/change-billing-shipping-address.html](http://localhost:4502/editor.html/content/forms/af/change-billing-shipping-address.html)

1. Tik op de knop **[!UICONTROL Customer ID]** en tik op **[!UICONTROL Edit Rules]** pictogram. Het venster van de Redacteur van de Regel opent.
1. Tik op de knop **[!UICONTROL + Create]** om een regel toe te voegen. Het opent de Visuele Redacteur.

   In de Visuele Redacteur, **[!UICONTROL WHEN]** is standaard geselecteerd. Ook het formulierobject (in dit geval, **[!UICONTROL Customer ID]**) vanaf waar u de regeleditor hebt gestart, opgegeven in het dialoogvenster **[!UICONTROL WHEN]** instructie.

1. Tik op de knop **[!UICONTROL Select State]** vervolgkeuzelijst en selecteer **[!UICONTROL is changed]**.

   ![gewend](assets/whencustomeridischanged.png)

1. In de **[!UICONTROL THEN]** instructie, selecteren **[!UICONTROL Invoke Service]** van de **[!UICONTROL Select Action]** vervolgkeuzelijst.
1. Selecteer **[!UICONTROL Retrieve Shipping Address]** van de **[!UICONTROL Select]** vervolgkeuzelijst.
1. Sleep de **[!UICONTROL Customer ID]** van het tabblad Formulierobjecten naar het tabblad **[!UICONTROL Drop object or select here]** in het **[!UICONTROL INPUT]** doos.

   ![dropobjectstoinputfield-retrieve](assets/dropobjectstoinputfield-retrievedata.png)

1. Sleep de **[!UICONTROL Customer ID, Name, Shipping Address, State, and Zip Code]** van het tabblad Formulierobjecten naar het tabblad **[!UICONTROL Drop object or select here]** in het **[!UICONTROL OUTPUT]** doos.

   ![dropobjectstooutputfield-retrieve data](assets/dropobjectstooutputfield-retrievedata.png)

   Tikken **[!UICONTROL Done]** om de regel op te slaan. Tik in het regeleditorvenster op **[!UICONTROL Close]**.

1. Geef een voorvertoning weer van het adaptieve formulier. Voer een id in het dialoogvenster **[!UICONTROL Customer ID]** veld. Het formulier kan nu klantgegevens uit de database ophalen.

   ![ophalen-informatie](assets/retrieve-information.gif)

## Stap 2: Het bijgewerkte klantadres toevoegen aan de database {#updated-customer-address}

Nadat de klantgegevens uit de database zijn opgehaald, kunt u het verzendadres, de provincie en de postcode bijwerken. Met de onderstaande procedure wordt een service Formuliergegevensmodel aangeroepen om klantgegevens bij te werken naar de database:

1. Selecteer **[!UICONTROL Submit]** en tik op **[!UICONTROL Edit Rules]** pictogram. Het venster van de Redacteur van de Regel opent.
1. Selecteer **[!UICONTROL Submit - Click]** tikken op de **[!UICONTROL Edit]** pictogram. De opties voor het bewerken van de regel Verzenden worden weergegeven.

   ![submit-rule](assets/submit-rule.png)

   In de optie WHEN **[!UICONTROL Submit]** en **[!UICONTROL is clicked]** zijn al geselecteerd.

   ![submit-is-geklikt](assets/submit-is-clicked.png)

1. In de **[!UICONTROL THEN]** tikken op de knop **[!UICONTROL + Add Statement]** optie. Selecteren **[!UICONTROL Invoke Service]** van de **[!UICONTROL Select Action]** vervolgkeuzelijst.
1. Selecteer **[!UICONTROL Update Shipping Address]** van de **[!UICONTROL Select]** vervolgkeuzelijst.

   ![update-verzend-adres](assets/update-shipping-address.png)

1. ![dropobjectstoinputfield-updatedata](assets/dropobjectstoinputfield-updatedata.png)

   Sleep de **[!UICONTROL Shipping Address, State, and Zip Code]** veld van het tabblad Formulierobjecten naar de overeenkomstige eigenschap table.property (bijvoorbeeld customerdetails.ShippingAddress) van het tabblad **[!UICONTROL Drop object or select here]** in het **[!UICONTROL INPUT]** doos. Alle velden met een tabelnaam (bijvoorbeeld details van de klant in dit geval) fungeren als invoergegevens voor de updateservice. Alle inhoud die in deze velden wordt geleverd, wordt bijgewerkt in de gegevensbron.

   >[!NOTE]
   >
   >Sleep de **[!UICONTROL Name]** en **[!UICONTROL Customer ID]** velden naar de overeenkomstige tablename.property (bijvoorbeeld customerdetails.name). Zo voorkomt u per ongeluk dat de naam en id van de klant worden bijgewerkt.

1. Sleep de **[!UICONTROL Customer ID]** van het tabblad Formulierobjecten naar het veld Id in het dialoogvenster **[!UICONTROL INPUT]** doos. Velden zonder een vooraf ingestelde tabelnaam (bijvoorbeeld klantgegevens in dit geval) fungeren als zoekparameter voor de updateservice. De **[!UICONTROL id]** in dit gebruiksgeval wordt een record in de tabel met klantgegevens op unieke wijze geïdentificeerd.
1. Tikken **[!UICONTROL Done]** om de regel op te slaan. Tik in het regeleditorvenster op **[!UICONTROL Close]**.
1. Geef een voorvertoning weer van het adaptieve formulier. Haal de gegevens van een klant op, werk het verzendadres bij en verzend het formulier. Wanneer u de details van dezelfde klant opnieuw ophaalt, wordt het bijgewerkte verzendadres weergegeven.

## Stap 3: (sectie Bonus) Gebruik de code-editor om validaties uit te voeren en foutberichten weer te geven {#step-bonus-section-use-the-code-editor-to-run-validations-and-display-error-messages}

Voer de validatie op het formulier uit om te controleren of de gegevens in het formulier correct zijn en of een foutbericht wordt weergegeven als gegevens onjuist zijn. Als bijvoorbeeld een niet-bestaande klant-id in het formulier wordt ingevoerd, moet een foutbericht worden weergegeven.

Aangepaste formulieren bieden verschillende componenten ingebouwde validaties, zoals e-mail en numerieke velden die u kunt gebruiken voor veelvoorkomende gebruiksgevallen. Gebruik de regeleditor voor geavanceerde gebruiksgevallen bijvoorbeeld om een foutbericht weer te geven wanneer de database nul (0) records (geen records) retourneert.

De volgende procedure laat zien hoe u een regel maakt om een foutbericht weer te geven als de klant-id die u in het formulier hebt ingevoerd, niet bestaat in de database. De regel brengt ook de nadruk aan en stelt het gebied van identiteitskaart van de Klant opnieuw in. De regel gebruikt [de API dataIntegrationUtils van de service van het formuliergegevensmodel](/help/forms/using/invoke-form-data-model-services.md) om te controleren of de klant-id in de database aanwezig is.

1. Tik op de knop **[!UICONTROL Customer ID]** en tik op `Edit Rules` pictogram. Het venster van de Redacteur van de Regel opent.
1. Tik op de knop **[!UICONTROL + Create]** om een regel toe te voegen. Het opent de Visuele Redacteur.

   In de Visuele Redacteur, **[!UICONTROL WHEN]** is standaard geselecteerd. Ook het formulierobject (in dit geval, **[!UICONTROL Customer ID]**) vanaf waar u de regeleditor hebt gestart, opgegeven in het dialoogvenster **[!UICONTROL WHEN]** instructie.

1. Tik op de knop **[!UICONTROL Select State]** vervolgkeuzelijst en selecteer **[!UICONTROL is changed]**.

   ![gewend](assets/whencustomeridischanged.png)

   In de **[!UICONTROL THEN]** instructie, selecteren **[!UICONTROL Invoke Service]** van de **[!UICONTROL Select Action]** vervolgkeuzelijst.

1. Overschakelen van **[!UICONTROL Visual Editor]** tot **[!UICONTROL Code Editor]**. De schakelaarcontrole is op de rechterkant van het venster. De Redacteur van de Code opent, tonend code gelijkend op het volgende:

   ![code-editor](assets/code-editor.png)

1. Vervang de sectie met invoervariabelen door de volgende code:

   ```
   var inputs = {
       "id" : this
   };
   ```

1. Vervang de sectie guidelib.dataIntegrationUtils.executeOperation (operationInfo, inputs, outputs) door de volgende code:

   ```
   guidelib.dataIntegrationUtils.executeOperation(operationInfo, inputs, outputs, function (result) {
     if (result) {
         result = JSON.parse(result);
       customer_Name.value = result.name;
       customer_Shipping_Address = result.shippingAddress;
     } else {
       if(window.confirm("Invalid Customer ID. Provide a valid customer ID")) {
             customer_Name.value = " ";
            guideBridge.setFocus(customer_ID);
       }
     }
   });
   ```

1. Geef een voorvertoning weer van het adaptieve formulier. Voer een onjuiste klant-id in. Er verschijnt een foutbericht.

   ![display-validation-error](assets/display-validation-error.gif)
