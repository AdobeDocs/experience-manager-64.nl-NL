---
title: Adobe Sign in een adaptief formulier gebruiken
seo-title: Adobe Sign in een adaptief formulier gebruiken
description: 'Workflows voor e-handtekeningen (Adobe Sign) inschakelen voor een adaptief formulier om workflows voor ondertekening te automatiseren, processen met één en meerdere handtekeningen te vereenvoudigen en formulieren van mobiele apparaten elektronisch te ondertekenen. '
seo-description: Workflows voor e-handtekeningen (Adobe Sign) inschakelen voor een adaptief formulier om workflows voor ondertekening te automatiseren, processen met één en meerdere handtekeningen te vereenvoudigen en formulieren van mobiele apparaten elektronisch te ondertekenen.
uuid: 9c65dc44-c1a5-44df-8659-6efbe347575b
contentOwner: khsingh
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: develop
discoiquuid: 29fc297e-0a95-4d2a-bfe6-5676d53624db
noindex: true
translation-type: tm+mt
source-git-commit: f6b6d8559bb0b899a78afd6410eb316626ecaa18
workflow-type: tm+mt
source-wordcount: '3409'
ht-degree: 0%

---


# Adobe Sign in een adaptief formulier gebruiken {#using-adobe-sign-in-an-adaptive-form}

Workflows voor e-handtekeningen (Adobe Sign) inschakelen voor een adaptief formulier om workflows voor ondertekening te automatiseren, processen met één en meerdere handtekeningen te vereenvoudigen en formulieren van mobiele apparaten elektronisch te ondertekenen.

Met Adobe Sign kunnen workflows voor e-handtekeningen worden gebruikt voor adaptieve formulieren. E-handtekeningen verbeteren werkstromen om documenten voor wettig, verkoop, loonlijst, personeelsbeheer, en meer gebieden te verwerken.

In een standaard Adobe-scenario voor ondertekenen en aanpassen van formulieren vult een gebruiker een adaptief formulier in om een aanvraag voor een service in te dienen. Een hypotheek- en creditcardaanvraag vereist bijvoorbeeld wettelijke handtekeningen van alle kredietnemers en medekredietnemers. Als u workflows voor elektronische handtekeningen wilt inschakelen voor vergelijkbare scenario&#39;s, kunt u Adobe Sign with AEM Forms integreren. Een paar voorbeelden hiervan zijn:

* Sluit overeenkomsten van om het even welk apparaat met volledig geautomatiseerde voorstel, citaat, en contractprocessen.
* Voltooi processen voor menselijke hulpbronnen sneller en geef uw werknemers de digitale ervaring.
* Verkort de duur van de contractcyclus en neem sneller aan boord van uw leveranciers.
* Maak digitale workflows waarmee algemene processen worden geautomatiseerd.

Adobe Sign-integratie met AEM Forms ondersteunt:

* Workflows voor ondertekening van enkelvoudige en meervoudige gebruikers
* Workflows voor opeenvolgende en gelijktijdige ondertekening
* In-form en out-of-form ondertekeningservaringen
* Formulieren ondertekenen als anonieme of aangemelde gebruiker
* Dynamische ondertekeningsprocessen (integratie met AEM Forms-workflow)
* Verificatie via een kennisbasis, telefoon en sociale profielen

## Vereisten {#prerequisites}

Voordat u Adobe Sign in een adaptief formulier gebruikt:

* Zorg ervoor dat de cloudservice AEM Forms is geconfigureerd voor gebruik van Adobe Sign. Zie [Adobe Sign with AEM Forms](/help/forms/using/adobe-sign-integration-adaptive-forms.md)integreren voor meer informatie.
* Behoud de lijst met ondertekenaars klaar. U hebt voor elke ondertekenaar ten minste een e-mailadres nodig.

## Adobe-ondertekening voor een adaptief formulier configureren {#configure-adobe-sign-for-an-adaptive-form}

Voer de volgende stappen uit om Adobe Sign for an adaptive form te configureren:

1. [Aangepaste formuliereigenschappen bewerken voor Adobe-ondertekening](#enableadobesign)
1. [Adobe-handtekeningvelden toevoegen aan een adaptief formulier](#addadobesignfieldstoanadaptiveform)
1. [Adobe Sign inschakelen voor een adaptief formulier](#enableadobsignforanadaptiveform)
1. [Selecteer Adobe Sign Cloud Service voor een adaptief formulier](#selectadobesigncloudserviceforanadaptiveform)

1. [Adobe-ondertekenaars toevoegen aan een adaptief formulier](#addsignerstoanadaptiveform)
1. [Selecteer Handeling verzenden voor een adaptief formulier](#selectsubmitactionforanadaptiveform)

![ondertekenaar-details](assets/signer-details.png)

### Aangepaste formuliereigenschappen bewerken voor Adobe Sign {#enableadobesign}

Configureer adaptieve formuliereigenschappen voor Adobe Sign voor een bestaand of een nieuw adaptief formulier.

[Maak een adaptief formulier voor Adobe Sign](/help/forms/using/working-with-adobe-sign.md#create-an-adaptive-form-for-adobe-sign) en beschrijf de stappen voor het maken van een standaard adaptief formulier. Zie [Een adaptief formulier](/help/forms/using/creating-adaptive-form.md) maken voor andere beschikbare opties terwijl u een adaptief formulier maakt.

#### Een adaptief formulier maken voor Adobe Sign {#create-an-adaptive-form-for-adobe-sign}

Voer de volgende stappen uit om een adaptief formulier te maken voor ondertekening door Adobe:

1. Ga naar **[!UICONTROL Adobe Experience Manager]** > **[!UICONTROL Forms]** > **[!UICONTROL Forms & Documents]**.
1. Tik **[!UICONTROL Create]** en selecteer **[!UICONTROL Adaptive Form]**. Er wordt een lijst met sjablonen weergegeven. Selecteer de sjabloon en tik op **[!UICONTROL Next]**.
1. Op het **[!UICONTROL Basic]** tabblad:

   1. Geef de **naam** en de **titel** op voor het adaptieve formulier.
   1. Selecteer de [configuratiecontainer](/help/forms/using/adobe-sign-integration-adaptive-forms.md#configure-adobe-sign-with-aem-forms) die u hebt gemaakt tijdens de configuratie van Adobe Sign with AEM Forms.

1. In the **[!UICONTROL Form Model]** tab, select one of the following options:

   * Selecteer de **[!UICONTROL Associate form template as the Document of Record template]** optie en selecteer een Document van het malplaatje van het Verslag. Als u een op een formuliersjabloon gebaseerd adaptief formulier gebruikt, worden alleen de velden weergegeven die zijn gebaseerd op de bijbehorende formuliersjabloon. Niet alle velden van het adaptieve formulier worden weergegeven.
   * Selecteer de **[!UICONTROL Generate Document of Record]** optie. Als u een adaptief formulier met de optie Document of Record gebruikt, worden in het document dat wordt verzonden voor ondertekening alle velden van het adaptieve formulier weergegeven.

1. Tik op een adaptief formulier voor gebarentaal dat geschikt is voor ondertekening en dat kan worden gebruikt om Adobe-handtekeningvelden toe te voegen. **[!UICONTROL Create.]**

#### Een adaptief formulier bewerken voor Adobe Sign {#editafsign}

Voer de volgende stappen uit om Adobe Sign in een bestaand adaptief formulier te gebruiken:

1. Ga naar **[!UICONTROL Adobe Experience Manager]** > **[!UICONTROL Forms]**> **[!UICONTROL Forms & Documents]**.
1. Selecteer het adaptieve formulier en tik op **[!UICONTROL Properties]**.
1. Selecteer op het **[!UICONTROL Basic]** tabblad de [configuratiecontainer](/help/forms/using/adobe-sign-integration-adaptive-forms.md#configure-adobe-sign-with-aem-forms) die u hebt gemaakt tijdens de configuratie van Adobe Sign with AEM Forms.
1. In the **[!UICONTROL Form Model]** tab, select one of the following options:

   * Selecteer de **[!UICONTROL Associate form template as the Document of Record template]** optie en selecteer een Document van het malplaatje van het Verslag. Als u een op een formuliersjabloon gebaseerd adaptief formulier gebruikt, worden alleen de velden weergegeven die zijn gebaseerd op de bijbehorende formuliersjabloon. Niet alle velden van het adaptieve formulier worden weergegeven.
   * Selecteer de **[!UICONTROL Generate Document of Record]** optie. Als u een adaptief formulier met de optie Document of Record gebruikt, worden in het document dat wordt verzonden voor ondertekening alle velden van het adaptieve formulier weergegeven.

1. Tik op **[!UICONTROL Save & Close]**. Het adaptieve formulier is ingeschakeld voor Adobe-ondertekening.

### Adobe-handtekeningvelden toevoegen aan een adaptief formulier {#addadobesignfieldstoanadaptiveform}

Adobe Sign heeft verschillende velden die op een adaptief formulier kunnen worden geplaatst. Deze velden accepteren verschillende gegevenstypen, zoals handtekeningen, initialen, bedrijf of titel, en helpen bij het verzamelen van extra informatie tijdens het ondertekenen, samen met de handtekeningen. Met de component Adobe Sign Block kunt u Adobe Sign-velden op verschillende locaties in een adaptief formulier plaatsen.

Voer de volgende stappen uit om velden toe te voegen aan een adaptief formulier en verschillende opties aan te passen met betrekking tot deze velden:

1. Sleep de component **Adobe Sign Block** van de componentbrowser naar het aangepaste formulier. De Adobe-component Blok ondertekenen bevat alle ondersteunde Adobe-handtekeningvelden. Standaard wordt een veld **Handtekening** toegevoegd aan het aangepaste formulier.

   ![sign-block](assets/sign-block.png)

   Standaard is het Adobe Sign Block niet zichtbaar in het gepubliceerde adaptieve formulier. Deze is alleen zichtbaar in de ondertekenende documenten. U kunt de zichtbaarheid van Adobe Sign Block wijzigen vanuit de eigenschappen van de Adobe Sign Block-component.

   >[!NOTE]
   >
   >* Het gebruik van het Adobe-handtekeningblok is niet verplicht als u Adobe Sign in een adaptief formulier wilt gebruiken. Als u het blok van het Ondertekenen van Adobe niet gebruikt en gebieden voor de ondertekenaars toevoegt, dan wordt het standaardhandtekeningsgebied getoond bij de bodem van de het ondertekenen documenten.
   >* Gebruik het Adobe-handtekeningblok alleen voor de aanvullende formulieren die automatisch een Document of Record genereren. Als u een aangepaste XDP gebruikt voor het genereren van een op een formuliersjabloon gebaseerd adaptief formulier voor Document of Record, is een Adobe-handtekeningblok niet vereist.


1. Selecteer de **Adobe-component Blok** ondertekenen en tik op het pictogram **Aem_6_3_edit** _ ![](assets/aem_6_3_edit.png) name. Er worden opties weergegeven voor het toevoegen van velden en het opmaken van de weergave van een veld.

   ![adobe-sign-block-select-fields](assets/adobe-sign-block-select-fields.png)

   **A.** Selecteer Adobe-handtekeningvelden en voeg deze toe. **B.** Het Adobe-handtekeningblok uitbreiden naar de volledige schermweergave

1. Tik op het pictogram **Adobe Sign Field** ![name_6_3_adobesign](assets/aem_6_3_adobesign.png) . Er worden opties weergegeven voor het selecteren en toevoegen van Adobe-handtekeningvelden.

   Vouw het vervolgkeuzeveld **Type** uit om een Adobe-ondertekeningsveld te selecteren en tik op het pictogram Done ![name_6_3_forms_save](assets/aem_6_3_forms_save.png) om het geselecteerde veld toe te voegen aan het Adobe-ondertekeningsblok. Het vervolgkeuzeveld **Type** bevat de typen Handtekening, Ondertekenaarinformatie en Gegevensveld. Adobe Sign integration with AEM Forms support fields indicated in the Type drop-down box only. Raadpleeg de documentatie bij [Adobe Sign voor meer informatie over Adobe Sign-velden](https://helpx.adobe.com/sign/help/field-types.html).

   ![adobe-sign-block-fields-options](assets/adobe-sign-block-fields-options.png)

   U moet een unieke naam opgeven voor een veld. U kunt ook de vereiste optie selecteren om een verplicht veld te markeren. Naast de optie **Naam** en **Vereist** , hebben sommige velden van het Ondertekenen van Adobe meer opties. Bijvoorbeeld masker en meerdere regels. Bovendien geeft u voor elk Adobe-handtekeningveld een unieke naam op, of de velden zich in dezelfde of andere Adobe-ondertekeningsblokken bevinden.

### Adobe Sign inschakelen voor een adaptief formulier {#enableadobsignforanadaptiveform}

Adobe Sign is niet beschikbaar voor een adaptief formulier. Voer de volgende stappen uit om het in te schakelen:

1. Tik in de browser Inhoud op **Formuliercontainer** en tik op het pictogram **Configureren** ![configureren](assets/configure.png) . De eigenschappenbrowser wordt geopend en de eigenschappen van de container Adaptief formulier worden weergegeven.
1. Vouw in de eigenschappenbrowser de accordeon **Elektronische handtekening** uit en selecteer de optie Adobe-handtekening **** inschakelen. Adobe Sign wordt ingeschakeld voor een adaptief formulier.

### Adobe Sign Cloud Service en handtekeningvolgorde selecteren {#selectadobesigncloudserviceforanadaptiveform}

U kunt meerdere Adobe-ondertekeningsservices configureren voor een exemplaar van AEM Forms. Het is raadzaam voor elke functie een aparte reeks diensten te hebben (Human Resources, Finance, enzovoort). Hierdoor wordt het bijhouden en rapporteren van ondertekende documenten eenvoudiger. Een bank heeft bijvoorbeeld meerdere afdelingen. U kunt een afzonderlijke configuratie voor elke afdeling hebben voor het beter volgen van de documenten.

Een document kan ook meerdere ondertekenaars hebben. Een creditcardtoepassing kan bijvoorbeeld meerdere aanvragers hebben. Een bank vereist handtekeningen van alle aanvragers voordat de aanvraag wordt verwerkt. Voor scenario&#39;s met meerdere ondertekenaars kunt u ervoor kiezen het document in volgorde van opeenvolgende of gelijktijdige ondertekening te ondertekenen.

Voer de volgende stappen uit om een cloudservice en de volgorde van ondertekening te selecteren:

![cloudservice](assets/cloud-service.png)

1. Tik in de browser Inhoud op **Formuliercontainer** en tik op het pictogram **Configureren** ![configureren](assets/configure.png) . De eigenschappenbrowser wordt geopend en de eigenschappen van de container Adaptief formulier worden weergegeven.
1. Vouw in de eigenschappenbrowser de accordeon **Elektronische handtekening** uit en selecteer de optie Adobe-handtekening **** inschakelen. Adobe Sign wordt ingeschakeld voor een adaptief formulier.
1. Selecteer een cloudservice in de lijst met Cloud Servicen voor ondertekening van Adobe die al is geconfigureerd.

   Als de lijst **Adobe Sign Cloud Service** leeg is, volgt u het artikel Adobe Sign with AEM Forms [](/help/forms/using/adobe-sign-integration-adaptive-forms.md) configureren om de service te configureren.

1. Selecteer de handtekeningvolgorde in het dialoogvenster **Ondertekenaars kunnen ondertekenen** . Ondertekenaars van Adobe kunnen een adaptief formulier **opeenvolgend** ondertekenen - een voor een andere ondertekenaar of **tegelijkertijd** - in willekeurige volgorde.

   Eén ondertekenaar ontvangt het formulier voor ondertekening achtereenvolgens in de volgorde. Nadat een ondertekenaar het ondertekenen van het document heeft voltooid, wordt het formulier verzonden naar de volgende ondertekenaar, enzovoort.

   Meerdere ondertekenaars kunnen tegelijkertijd een formulier ondertekenen.

1. [Voeg ondertekenaars toe aan een adaptief formulier](#addsignerstoanadaptiveform) en tik op het pictogram Done om de wijzigingen op te slaan.

### Ondertekenaars toevoegen aan een adaptief formulier {#addsignerstoanadaptiveform}

U kunt slechts één ondertekenaar of meerdere ondertekenaars hebben voor een adaptief formulier. Wanneer u een ondertekenaar toevoegt, kunt u ook verificatiedetails voor de ondertekenaar configureren. U kunt ook selecteren of de invuller en zanger van het formulier dezelfde persoon zijn. Voer de volgende stappen uit om diverse details over een ondertekenaar toe te voegen en te verstrekken:

1. Tik in de browser Inhoud op **Formuliercontainer** en tik op het pictogram **Configureren** ![configureren](assets/configure.png) . De eigenschappenbrowser wordt geopend met de eigenschappen van de container Adaptief formulier.
1. Vouw in de eigenschappenbrowser de accordeon **Elektronische handtekening** uit en selecteer de optie Adobe-handtekening **** inschakelen. Adobe Sign wordt ingeschakeld voor een adaptief formulier.
1. Tik op Ondertekenaar **** toevoegen onder Configuratie **ondertekenaar.** Er wordt een ondertekenaar toegevoegd aan het adaptieve formulier. U kunt meerdere Adobe-ondertekenaars toevoegen aan een adaptief formulier.
1. ![telefoongegevens](assets/phone-details.png)

   Klik op het pictogram **Aem_6_3_edit** _ ![](assets/aem_6_3_edit.png) om de volgende informatie over de ondertekenaar op te geven:

   * **Titel:** Geef een titel op om een ondertekenaar op unieke wijze te identificeren.
   * **Is de ondertekenaar en de persoon die het formulier invult hetzelfde?** Selecteer **Ja** als de invuller van het formulier en de eerste ondertekenaar dezelfde persoon zijn. Als de optie is ingesteld op **Nee,** gebruikt u de component voor de handtekeningstap niet in het adaptieve formulier. Als het formulier een component Handtekeningstap bevat, wordt het veld automatisch ingesteld op Ja.
   * **E-mailadres ondertekenaar:** Geef het e-mailadres van de ondertekenaar op. Ondertekenaar ontvangt om ondertekende documenten/formulier te zijn op het opgegeven e-mailadres. U kunt een e-mailadres gebruiken dat wordt opgegeven in een formulierveld, in het AEM-gebruikersprofiel van de aangemelde gebruiker, of handmatig een e-mailadres invoeren. Het is een verplichte stap. Houd er ook rekening mee dat als u slechts één ondertekenaar hebt geconfigureerd, het e-mailadres van de ondertekenaar niet hetzelfde is als het Adobe Sign-account dat wordt gebruikt om AEM cloud services te configureren.
   * **Verificatiemethode ondertekenaar:** Geef de methode op voor het verifiëren van een gebruiker voordat u een formulier voor ondertekening opent. U kunt tussen telefoon, kennisbasis, en sociale op identiteit-gebaseerde authentificatie kiezen.
   >[!NOTE]
   >
   >* Standaard biedt verificatie op basis van sociale identiteiten een optie voor verificatie via Facebook, Google en LinkedIn. U kunt contact opnemen met de ondersteuning van Adobe Sign om andere providers van sociale verificatie in te schakelen.


   * **Adobe-velden ondertekenen om in te vullen of te ondertekenen:** Selecteer Adobe-handtekeningvelden voor de ondertekenaar. Een adaptief formulier kan meerdere Adobe-handtekeningvelden hebben. U kunt specifieke velden inschakelen voor een ondertekenaar. In het veld worden alle beschikbare Adobe-ondertekeningsblokken weergegeven. Wanneer u een blok selecteert, worden alle velden van het blok geselecteerd. U kunt het X-pictogram gebruiken om de selectie van een veld op te heffen.
   ![signer-details-1](assets/signer-details-1.png)

   De bovenstaande afbeelding bevat twee voorbeelden van Adobe-blokken voor ondertekening: Persoonlijke gegevens en kantoorgegevens

   Tik op het pictogram Done ![name_6_3_forms_save](assets/aem_6_3_forms_save.png) . De ondertekenaar wordt toegevoegd en geconfigureerd.

### Selecteer Handeling verzenden voor een adaptief formulier {#selectsubmitactionforanadaptiveform}

Nadat u Adobe Sign-velden hebt toegevoegd aan een adaptief formulier, Adobe Sign vanuit formuliercontainer hebt ingeschakeld, Adobe Sign Cloud Service hebt geselecteerd en Adobe Sign Signers hebt toegevoegd, selecteert u een geschikte verzendactie voor het adaptieve formulier. Zie De handeling Verzenden [configureren voor meer informatie over adaptieve formulieren die handelingen verzenden](/help/forms/using/configuring-submit-actions.md).

Bovendien wordt een adaptief formulier dat geschikt is voor Adobe Sign alleen verzonden nadat alle ondertekenaars het formulier hebben ondertekend. Gedeeltelijk ondertekend formulier vindt u in de sectie Ondertekenen in behandeling van de portal Formulieren. Adobe Sign Configuration Service houdt regelmatig [](/help/forms/using/adobe-sign-integration-adaptive-forms.md) opiniepeilingen over de Adobe Sign-server om de status van handtekeningen te controleren. Als alle ondertekenaars het ondertekenen van het formulier hebben voltooid, wordt de verzendactieservice gestart en wordt het formulier verzonden. Als u een aangepaste verzendactie gebruikt en het formulier Adobe Sign gebruikt, werkt u de aangepaste verzendactie bij om de verzendactieservice te gebruiken.

>[!NOTE]
>
>Gegevens van het adaptieve formulier worden tijdelijk opgeslagen op Forms Portal. U wordt aangeraden [aangepaste opslag te gebruiken voor Forms Portal](/help/forms/using/configuring-draft-submission-storage.md). Hiermee zorgt u ervoor dat de PII-gegevens (persoonlijk identificeerbare gegevens) niet op AEM-servers worden opgeslagen.

Uw ervaring voor het ondertekenen van formulieren is gereed. U kunt een voorbeeld van het formulier bekijken om de ondertekeningservaring te verifiëren. In het gepubliceerde formulier worden de velden voor het blokkeren van Adobe-handtekeningen weergegeven wanneer een ondertekenaar het formulier ontvangt voor ondertekening via een e-mail. Deze ervaring wordt ook wel bekend als een ondertekeningservaring in de vorm van een out-of-form. U kunt ook een ondertekeningservaring in formulieren configureren voor de eerste ondertekenaar. Zie Ondertekening in formulieren [maken voor meer informatie](/help/forms/using/working-with-adobe-sign.md#create-in-form-signing-experience).

## Cloud-handtekeningen configureren voor een adaptief formulier {#configure-cloud-signatures-for-an-adaptive-form}

Digitale handtekeningen op basis van cloud of externe handtekeningen zijn een nieuwe generatie digitale handtekeningen die op verschillende computers, mobiele apparaten en het web werken en voldoen aan de hoogste standaarden en waarborgen voor ondertekenaarsverificatie. U kunt een adaptief formulier ondertekenen met digitale handtekeningen op basis van de cloud.

Nadat u de adaptieve formuliereigenschappen voor Adobe-ondertekening [hebt](#enableadobesign)bewerkt, voert u de volgende stappen uit om het handtekeningveld voor de cloud toe te voegen aan een adaptief formulier:

1. Sleep de component **Adobe Sign Block** van de componentbrowser naar het aangepaste formulier. De Adobe-component Blok ondertekenen bevat alle ondersteunde Adobe-handtekeningvelden. Standaard wordt een veld **Handtekening** toegevoegd aan het aangepaste formulier.

   ![sign-block](assets/sign-block.png)

1. Selecteer de **Adobe-component Blok** ondertekenen en tik op het pictogram **Aem_6_3_edit** _ ![](assets/aem_6_3_edit.png) name. Er worden opties weergegeven voor het toevoegen van velden en het opmaken van de weergave van een veld.

   ![adobe-sign-block-select-fields](assets/adobe-sign-block-select-fields.png)

   **A.** Selecteer Adobe-handtekeningvelden en voeg deze toe. **B.** Het Adobe-handtekeningblok uitbreiden naar de volledige schermweergave

1. Tik op het pictogram **Adobe Sign Field** ![name_6_3_adobesign](assets/aem_6_3_adobesign.png) . Er worden opties weergegeven voor het selecteren en toevoegen van Adobe-handtekeningvelden.

   Vouw het vervolgkeuzeveld **Type** uit om **Digitale handtekening** te selecteren en tik op het pictogram Gereed ![aem_6_3_forms_save](assets/aem_6_3_forms_save.png) om het geselecteerde veld toe te voegen aan het Adobe-handtekeningblok.

   ![digital_signatures](assets/digital_signatures.png)

   U moet een unieke naam opgeven voor een veld.

   Digitale handtekeningen toepassen op het adaptieve formulier met:

   * Wolkhandtekeningen: Onderteken met een [digitale id](https://helpx.adobe.com/sign/kb/digital-certificate-providers.html) die wordt gehost door een vertrouwde serviceprovider.
   * Adobe Acrobat of Reader: Download en open het document met Adobe Acrobat of Reader om het te ondertekenen met een smartcard, een USB-token of een digitale id op basis van een bestand.
   Nadat u het handtekeningveld voor de cloud aan het adaptieve formulier hebt toegevoegd, voert u de volgende stappen uit om het configuratieproces te voltooien:

   * [Adobe Sign inschakelen voor een adaptief formulier](#enableadobsignforanadaptiveform)
   * [Selecteer Adobe Sign Cloud Service voor een adaptief formulier](#selectadobesigncloudserviceforanadaptiveform)
   * [Adobe-ondertekenaars toevoegen aan een adaptief formulier](#addsignerstoanadaptiveform)
   * [Selecteer Handeling verzenden voor een adaptief formulier](#selectsubmitactionforanadaptiveform)


## Ervaring voor ondertekenen in formulieren maken {#create-in-form-signing-experience}

Een gebruiker kan ook een adaptief formulier ondertekenen terwijl het formulier wordt ingevuld. Deze ervaring wordt ook wel &#39;in-form signing experience&#39; genoemd. De ondertekeningservaring in formulieren is alleen beschikbaar voor de eerste ondertekenaar in een omgeving met meerdere ondertekenaars. Voer de volgende stappen uit om een ondertekeningservaring in formulieren te maken voor een adaptief formulier:

1. [Voeg en vorm de component](#add-and-configure-the-signature-step-component)van de Stap van de Handtekening toe.
1. [Voeg de component](#configure-the-thank-you-page-or-summary-step-component)Samenvattingsstap toe.

![in-form-signing-experience](assets/in-form-signing-experience.png)

### De component voor de stap Handtekening toevoegen en configureren {#add-and-configure-the-signature-step-component}

Gebruik de component Handtekeningstap om een gebied op te geven voor de elektronische ondertekening van het ingevulde formulier. Wanneer de sectie met de component Signature Step wordt weergegeven, wordt een ondertekenbare PDF-versie van het ingevulde formulier weergegeven. De component voor de stap Handtekening gebruikt de volledige breedte die beschikbaar is voor het formulier. Het wordt aanbevolen geen andere component op te nemen in de sectie die de component voor de stap Handtekening bevat.

Voer de volgende stappen uit om de component van de Stap van de Handtekening te vormen:

1. Sleep de component **Handtekeningstap** van de browser Components naar het formulier.
1. Selecteer de zojuist toegevoegde component van de stap van de Handtekening en tik het **Configure** ![configure](assets/configure.png) pictogram. De eigenschappenbrowser wordt geopend en de eigenschappen voor stap Handtekening worden weergegeven. Configureer de volgende eigenschappen:

   * **Elementnaam**: Geef de naam van de component op.
   * **Titel:** Geef de unieke titel van de component op.
   * **Sjabloonbericht:** Geef het bericht op dat moet worden weergegeven wanneer de PDF van de handtekening wordt geladen. Het duurt enige tijd om PDF-handtekening voor te bereiden en te laden.
   * **Ondertekeningsservice:** Selecteer de optie **Adobe-handtekening** .
   * **Verouderde E-sign component** gebruiken: Als u het respectievelijke adaptieve formulier gebruikt in de werkruimte [](/help/forms/using/introduction-html-workspace.md)AEM Forms, de app AEM Forms of als het onderliggende adaptieve formulier een verouderde e-sign component heeft, selecteert u de optie **Oude E-sign component** gebruiken.
   * **Configuratie**: Selecteer een configuratie (Adobe Sign Cloud Service). De vervolgkeuzelijst is alleen beschikbaar als de optie **Oude E-sign component** gebruiken is ingeschakeld.
   Tik op het pictogram Done ![name_6_3_forms_save](assets/aem_6_3_forms_save.png) om de wijzigingen op te slaan.

   ![handtekening-stap](assets/signature-step.png)

   >[!NOTE]
   >
   >* Wanneer u de **[!UICONTROL Signature Step]** component naar het formulier sleept, wordt de **[!UICONTROL Is the signer and the person filling the form same?]** optie automatisch ingesteld op **Ja**. U moet het formulier blijven gebruiken.
   >* Aangepaste formulieren die zijn ingeschakeld voor Adobe Sign, ondersteunen niet het gebruik van de knop Verzenden in de sectie of het deelvenster met de component Stap handtekening. U kunt een summiere stap toevoegen nadat de stap Handtekening voor de handmatige verzending is geactiveerd of nadat de intervalset is geactiveerd met de [Adobe-ondertekeningsconfiguratieservice](/help/forms/using/adobe-sign-integration-adaptive-forms.md#configure-adobe-sign-scheduler-to-sync-the-signing-status).


### De component voor de prullenbak of overzichtsstap configureren {#configure-the-thank-you-page-or-summary-step-component}

De component **Samenvattingsstap** verzendt automatisch het formulier, vult de informatie in de aangepaste overzichtspagina in en geeft de samenvatting van het verzonden formulier weer. Het krijgt ook de vereiste informatie in de terugkeerkaart. De component SummaryStep gebruikt de volledige breedte die beschikbaar is voor het formulier. Men adviseert om geen andere component op de sectie te hebben die de Summiere component van de Stap bevat.

De ervaring voor het ondertekenen van formulieren is nu gereed. U kunt een voorbeeld van het formulier bekijken om de ondertekeningservaring te verifiëren.

## Veelgestelde vragen {#frequently-asked-questions}

**V: U kunt een adaptief formulier insluiten in een ander adaptief formulier. Kan het ingesloten adaptieve formulier zijn ingeschakeld voor Adobe Sign?**

**Ans:** Nee, AEM Forms ondersteunt het gebruik van een adaptief formulier dat een adaptief formulier insluit dat geschikt is voor Adobe Sign niet voor ondertekening.

**V: Wanneer ik een adaptief formulier maak met de geavanceerde sjabloon en dit open voor bewerking, wordt het foutbericht &quot;Elektronische handtekeningen of ondertekenaars zijn niet correct geconfigureerd&quot; weergegeven. wordt weergegeven. Hoe kan ik het foutbericht oplossen?**

**Ans:** Adaptief formulier dat is gemaakt met de geavanceerde sjabloon is geconfigureerd voor gebruik van Adobe Sign. U lost de fout op door een cloudconfiguratie voor Adobe Sign te maken en te selecteren en een Adobe Sign-ondertekenaar voor het aangepaste formulier te configureren.

**V: Kan ik Adobe Sign-tekstcodes gebruiken in een statisch tekstonderdeel van een adaptief formulier?**

**Ans:** Ja, u kunt tekstcodes in een tekstcomponent gebruiken om Adobe-handtekeningvelden toe te voegen aan een [Document of Record](/help/forms/using/generate-document-of-record-for-non-xfa-based-adaptive-forms.md) (alleen automatisch gegenereerd document met de optie Alleen record) voor een adaptief formulier. Zie [Adobe-documentatie](https://helpx.adobe.com/sign/help/text-tags.html)ondertekenen voor meer informatie over de procedure en regels voor het maken van een tekstcode. Houd er rekening mee dat adaptieve formulieren beperkte ondersteuning bieden voor tekstcodes. Met de tekstcodes kunt u alleen die velden maken die door Adobe Sign Block worden ondersteund.

**V: AEM Forms bieden componenten voor blok Adobe Sign en de stap Handtekening. Kunnen deze gelijktijdig in een adaptieve vorm worden gebruikt?**

**Ans:** U kunt beide componenten tegelijkertijd in een formulier gebruiken. Hier volgen enkele aanbevelingen voor het gebruik van deze componenten:

**Adobe-handtekeningblok:** Met het Adobe-handtekeningblok kunt u overal in het adaptieve formulier Adobe-handtekeningvelden toevoegen. Het helpt ook om specifieke gebieden aan ondertekenaars toe te wijzen. Wanneer een adaptief formulier wordt voorvertoond of gepubliceerd, is Adobe Sign Block standaard niet zichtbaar. Deze blokken zijn alleen beschikbaar in het ondertekenende document. In het ondertekenende document worden alleen de velden ingeschakeld die zijn toegewezen aan een ondertekenaar. U kunt het Adobe-handtekeningblok gebruiken met de eerste en volgende ondertekenaars.

**Ondertekeningsstapcomponent:** U kunt de component voor het verzenden van handtekeningen gebruiken om in formulieren ondertekenen te maken. Hiermee kan alleen de eerste ondertekenaar ondertekenen terwijl het formulier wordt ingevuld. Wanneer de sectie met de component Signature Step wordt weergegeven, wordt een ondertekenbare PDF-versie van het formulier weergegeven. Het is doorgaans de laatste of voorlaatste sectie, gevolgd door een overzichtscomponent van een formulier.

