---
title: 'Zelfstudie: Een adaptief formulier maken'
seo-title: Create an adaptive form
description: Leer een adaptief formulier te maken, in te delen en voor te vertonen. Leer ook verzendhandelingen te configureren.
seo-description: Learn to create, layout, and preview an adaptive form. Also, learn to configure submit actions.
page-status-flag: de-activated
uuid: 0010d274-a683-499e-9fa6-ce355d7898a0
discoiquuid: 55c08940-8c25-4938-8e49-25bce20aaf22
feature: Adaptive Forms
exl-id: 144f7c0a-66af-4a8f-8d8c-f960cb612104
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1433'
ht-degree: 0%

---

# Zelfstudie: Een adaptief formulier maken {#do-not-publish-tutorial-create-an-adaptive-form}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

![02-create-adaptive-form-main-image](assets/02-create-adaptive-form-main-image.png)

Deze zelfstudie is een stap in de [Uw eerste adaptieve formulier maken](/help/forms/using/create-your-first-adaptive-form.md) reeks. U wordt aangeraden de reeks in chronologische volgorde te volgen om het volledige gebruik van de zelfstudie te begrijpen, uit te voeren en aan te tonen.

## Over de zelfstudie {#about-the-tutorial}

Adaptieve formulieren zijn formulieren van de nieuwe generatie die dynamisch zijn en reageren. U kunt adaptieve formulieren gebruiken om persoonlijke ervaringen te bieden. U kunt ook adaptieve formulieren integreren met Adobe Analytics voor gebruiksstatistieken en Adobe Campaign voor campagnebeheer. Voor meer informatie over adaptieve formuliermogelijkheden raadpleegt u [Inleiding tot het ontwerpen van adaptieve formulieren](/help/forms/using/introduction-forms-authoring.md).

Het is eenvoudiger om formulieren te maken en te beheren wanneer een correct proces wordt gevolgd. In dit artikel leert u hoe u:

* [Een adaptief formulier maken waarmee een klant een verzendadres kan toevoegen](/help/forms/using/create-adaptive-form.md#step-create-the-adaptive-form)

* [Indelingsvelden van een adaptief formulier voor het weergeven en accepteren van informatie van een klant](/help/forms/using/create-adaptive-form.md#step-add-header-and-footer)

* [Verzendactie maken om een e-mail met formulierinhoud te verzenden](/help/forms/using/create-adaptive-form.md#step-add-components-to-capture-and-display-information)
* [Een adaptief formulier voorvertonen en verzenden](/help/forms/using/create-adaptive-form.md)

Aan het einde van het artikel hebt u een formulier dat vergelijkbaar is met het volgende:

    [ ![](do-not-localize/form-preview-mobile.gif)](assets/form-preview-mobile.gif)

## Stap 1: Het adaptieve formulier maken {#step-create-the-adaptive-form}

1. Meld u aan bij de AEM auteur en navigeer naar **Adobe Experience Manager** > **Forms** > **Forms &amp; Documenten**. De standaard-URL is [http://localhost:4502/aem/forms.html/content/dam/formsanddocuments](http://localhost:4502/aem/forms.html/content/dam/formsanddocuments).
1. Tikken **Maken** en selecteert u **Adaptief formulier**. Er verschijnt een optie voor het selecteren van een sjabloon. Tik op de knop **Leeg** sjabloon om te selecteren en te tikken **Volgende**.

1. Een optie voor **Eigenschappen toevoegen** wordt weergegeven. De **Titel** en **Naam** velden zijn verplicht:

   * **Titel:** Opgeven `Add new or update shipping address` in het veld Titel. In het titelveld wordt de weergavenaam van het formulier opgegeven. Met de titel kunt u het formulier identificeren in de gebruikersinterface van AEM Forms.
   * **Naam:** Opgeven `shipping-address-add-update-form` in het veld Naam. In het veld Naam wordt de naam van het formulier opgegeven. Er wordt een knooppunt met de opgegeven naam gemaakt in de repository. Wanneer u een titel begint te typen, wordt automatisch een waarde voor het naamveld gegenereerd. U kunt de voorgestelde waarde wijzigen. Het naamveld mag alleen alfanumerieke tekens, afbreekstreepjes en onderstrepingstekens bevatten. Alle ongeldige invoer wordt vervangen door een afbreekstreepje.

1. Tikken **Maken**. Er wordt een adaptief formulier gemaakt en er wordt een dialoogvenster weergegeven om het formulier te openen voor bewerking. Tikken **Openen** om het nieuwe formulier te openen op een nieuw tabblad. Het formulier wordt geopend voor bewerking. De zijbalk wordt ook weergegeven om het nieuwe formulier aan te passen aan de behoeften.

   Voor informatie over de adaptieve interface voor formulierontwerp en de beschikbare componenten raadpleegt u [Inleiding tot het ontwerpen van adaptieve formulieren](/help/forms/using/creating-adaptive-form.md).

   ![nieuw aanpasbare vorm](assets/newly-created-adaptive-form.png)

## Stap 2: Kop- en voettekst toevoegen {#step-add-header-and-footer}

AEM Forms biedt veel componenten om informatie op een adaptief formulier weer te geven. De componenten Koptekst en Voettekst geven een formulier een consistent uiterlijk. Een koptekst bevat doorgaans het logo van een bedrijf, de titel van het formulier en het overzicht. Een voettekst bevat doorgaans copyrightinformatie en koppelingen naar andere pagina&#39;s.

1. Tikken ![schakelen tussen zijpaneel](assets/toggle-side-panel.png) > ![uitvouwen](assets/treeexpandall.png). De componentbrowser wordt geopend. Sleep de **Koptekst** van componentbrowser naar het adaptieve formulier.
1. Tikken **Logo**. De werkbalk wordt weergegeven. Tikken ![aem_6_3_edit](assets/aem_6_3_edit.png) op de werkbalk typt u **Wij.Detailhandel** en tikken ![aem_6_3_forms_save](assets/aem_6_3_forms_save.png).

1. Tik op de afbeelding. De werkbalk wordt weergegeven. Tikken ![cmppr](assets/cmppr.png). De eigenschappenbrowser wordt links van het scherm geopend. **Bladeren** en uploadt u de logoafbeelding. Tikken ![aem_6_3_forms_save](assets/aem_6_3_forms_save.png). De afbeelding wordt in de koptekst weergegeven.

   Tik op Bestand ophalen om het logo te downloaden dat in dit artikel wordt gebruikt als u er geen hebt.

[Bestand ophalen](assets/logo.png)

1. Sleep de **Voettekst** component van ![uitvouwen](assets/treeexpandall.png) op het adaptieve formulier. In dit stadium ziet het formulier er als volgt uit:

   ![adaptieve vorm met kop- en voetteksten](assets/adaptive-form-with-headers-and-footers.png)

## Stap 3: Componenten toevoegen om gegevens vast te leggen en weer te geven {#step-add-components-to-capture-and-display-information}

Componenten zijn bouwstenen van een adaptief formulier. AEM Forms biedt veel componenten om informatie in een adaptieve vorm vast te leggen en weer te geven. U kunt de componenten slepen vanuit ![uitvouwen](assets/treeexpandall.png) op een formulier. Voor meer informatie over beschikbare componenten en de bijbehorende functionaliteit raadpleegt u [Inleiding tot het ontwerpen van adaptieve formulieren](/help/forms/using/introduction-forms-authoring.md).

1. Sleep de component Numerieke box naar het aangepaste formulier. Plaats het voor de voettekstcomponent. Eigenschappen van component openen, wijzigen **Titel** van de component **`Customer ID`**, wijzigen **Elementnaam** tot **`customer_ID`** de **Vereist veld** , schakelt u de optie **HTML5-getalinvoertype gebruiken** en tikken ![aem_6_3_forms_save](assets/aem_6_3_forms_save.png).
1. Sleep drie tekstvakcomponenten naar het aangepaste formulier. Plaats deze voor de voettekstcomponent. Stel de volgende eigenschappen in voor deze tekstvakken.:

<table> 
 <tbody> 
  <tr> 
   <td>Eigenschap</td> 
   <td>Tekstvak 1<br /> </td> 
   <td>Tekstvak 2<br /> </td> 
   <td>Tekstvak 3</td> 
  </tr> 
  <tr> 
   <td>Titel</td> 
   <td>Naam<br /> </td> 
   <td>Verzendadres</td> 
   <td>Staat</td> 
  </tr> 
  <tr> 
   <td>Elementnaam</td> 
   <td>customer_Name<br /> </td> 
   <td>customer_Shipping_Address</td> 
   <td>customer_State</td> 
  </tr> 
  <tr> 
   <td>Vereist veld</td> 
   <td>Ingeschakeld</td> 
   <td>Ingeschakeld</td> 
   <td>Ingeschakeld</td> 
  </tr> 
  <tr> 
   <td>Meerdere regels toestaan<br /> </td> 
   <td>Uitgeschakeld</td> 
   <td>Ingeschakeld</td> 
   <td>Uitgeschakeld</td> 
  </tr> 
 </tbody> 
</table>

1. Sleep een **Numeriek vak** voor de voettekstcomponent. Open eigenschappen van de component, stel waarden in die in de onderstaande tabel worden vermeld, en tik ![aem_6_3_forms_save](assets/aem_6_3_forms_save.png).

   | Eigenschap | Waarde |
   |---|---|
   | Titel | Postcode |
   | Elementnaam | customer_ZIPCode |
   | Maximum aantal cijfers | 6 |
   | Vereist veld | Ingeschakeld |
   | Type weergavepatroon | Geen patroon |

1. Sleep een **E-mail** voor de voettekstcomponent. Open eigenschappen van de component, stel waarden in die in de onderstaande tabel worden vermeld en tik ![aem_6_3_forms_save](assets/aem_6_3_forms_save.png).

   | Eigenschap | Waarde |
   |---|---|
   | Titel | E-mail |
   | Elementnaam | customer_Email |
   | Vereist veld | Ingeschakeld |

1. Sleep een **Bestandsbijlage** voor de voettekstcomponent. Open eigenschappen van de component, stel waarden in die in de onderstaande tabel worden vermeld en tik ![aem_6_3_forms_save](assets/aem_6_3_forms_save.png).

<table> 
 <tbody> 
  <tr> 
   <td>Eigenschap</td> 
   <td>Waarde</td> 
  </tr> 
  <tr> 
   <td>Titel</td> 
   <td>Door de overheid goedgekeurd adresbewijs<br /> </td> 
  </tr> 
  <tr> 
   <td>Elementnaam</td> 
   <td>customer_Address_Proof</td> 
  </tr> 
  <tr> 
   <td>Vereist veld</td> 
   <td>Ingeschakeld</td> 
  </tr> 
 </tbody> 
</table>

1. Sleep een **Verzendknop** aan het adaptieve formulier. Plaats het voor de voettekstcomponent. Eigenschappen van component openen, elementnaam wijzigen in **address_adding_update_submit**, tikken ![aem_6_3_forms_save](assets/aem_6_3_forms_save.png). De indeling van het formulier is voltooid en het formulier ziet er als volgt uit:

   ![adaptief-form-with-all-the-components](assets/adaptive-form-with-all-the-components.png)

## Stap 4: Verzendactie configureren voor het aangepaste formulier {#step-configure-submit-action-for-the-adaptive-form}

Een verzendactie wordt geactiveerd wanneer een gebruiker op de knop Verzenden tikt op een adaptief formulier. Met een verzendactie kunt u formuliergegevens opslaan in de lokale gegevensopslagruimte, formuliergegevens verzenden naar een REST-eindpunt, formuliergegevens verzenden als e-mail, enzovoort. Aangepaste formulieren bieden een paar extra verzendacties die buiten de box vallen. Zie voor meer informatie [De handeling Verzenden configureren](/help/forms/using/configuring-submit-actions.md).

Met de volgende stappen kunt u de handeling voor het verzenden van e-mail configureren en demo-verzendactie van het formulier configureren:

1. Configureer de e-mailserver. Zie voor meer informatie [E-mailmelding configureren](/help/sites-administering/notification.md).

   /content/help/en/experience-manager/6-4/sites-administering/notification.html

1. Tikken **Formuliercontainer** in de Inhoudsbrowser en tik op ![cmppr](assets/cmppr.png). De eigenschappenbrowser wordt aan de linkerkant geopend.
1. Ga naar **Indiening** >  **Handeling verzenden**. Selecteren **E-mail verzenden**. Geef de volgende waarden op en tik op ![aem_6_3_forms_save](assets/aem_6_3_forms_save.png).

   | Eigenschap | Waarde |
   |--- |--- |
   | Van | `donotreply@weretail.com` |
   | Naar | `${customer_Email}` |
   | Onderwerp | Bevestiging: Je hebt een verzendadres toegevoegd op de website We.Retail. |
   | E-mailsjabloon | Hallo `${customer_Name}`, Het volgende adres wordt toegevoegd als het verzendadres voor je account: <br>`${customer_Name}`, `${customer_Shipping_Address}`, `${customer_State}`, `${customer_ZIPCode}`<br> Met vriendelijke groeten, wij.Retail |
   | Bijlagen opnemen | Ingeschakeld |

   Uw formulier is klaar. U kunt nu een voorbeeld van het formulier bekijken en de functionaliteit testen. Als u de naam gebruikt die in de zelfstudie wordt genoemd en het formulier opent op de computer waarop de AEM Forms-server wordt uitgevoerd, is het formulier beschikbaar op [http://localhost:4502/editor.html/content/forms/af/shipping-address-add-update-form.html](http://localhost:4502/editor.html/content/forms/af/shipping-address-add-update-form.html).

## Stap 5: Het adaptieve formulier voorvertonen en verzenden {#step-preview-and-submit-the-adaptive-form}

U kunt de **Voorvertoning, optie** om de weergave en het gedrag van een formulier te evalueren. U kunt een formulier verzenden in de voorbeeldmodus en ook de validaties controleren die op een formulier zijn toegepast. Als bijvoorbeeld een fout wordt weergegeven wanneer een verplicht veld leeg blijft.

Aangepaste formulieren bieden ook een optie om een formulier voor verschillende apparaten te emuleren. Bijvoorbeeld iPhone, iPad en Desktop. U kunt beide **Voorvertoning** en **Emulator** ![liniaal](assets/ruler.png) in combinatie met elkaar een voorbeeld van een formulier bekijken voor apparaten van verschillende schermgrootten.

1. Tik op de knop **Voorvertoning** aan de rechterkant van de formuliereditor. Het formulier wordt geopend in de voorbeeldmodus. Als u de in de zelfstudie vermelde naam hebt gebruikt, wordt een voorbeeld van de URL van het formulier weergegeven met [http://localhost:4502/content/dam/formsanddocuments/shipping-address-add-update-form/jcr:content?wcmmode=disabled](http://localhost:4502/content/dam/formsanddocuments/shipping-address-addition-updation-form/jcr:content?wcmmode=disabled)
1. Gebruiken ![liniaal](assets/ruler.png) om te zien hoe het formulier er op verschillende apparaten uitziet.
1. Vul velden van het formulier in en tik op **Verzenden**. Het formulier wordt verzonden en u wordt omgeleid naar de standaardversie **Bedankt** pagina. U kunt ook een aangepaste pagina voor bedankt opgeven. Zie voor meer informatie [Omleidingspagina configureren](/help/forms/using/configuring-redirect-page.md).

Het aangepaste formulier voor het toevoegen van een adres is gereed. Als u de naam gebruikt die in de zelfstudie wordt genoemd en het formulier opent op de computer waarop de AEM Forms-server wordt uitgevoerd, is het formulier beschikbaar op [http://localhost:4502/editor.html/content/forms/af/shipping-address-add-update-form.html](http://localhost:4502/editor.html/content/forms/af/shipping-address-add-update-form.html).
