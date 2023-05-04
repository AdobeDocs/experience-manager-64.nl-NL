---
title: Acrobat Sign in een adaptieve vorm gebruiken
seo-title: Using Acrobat Sign in an adaptive form
description: Workflows voor e-handtekeningen (Acrobat Sign) inschakelen voor een adaptief formulier om ondertekeningsworkflows te automatiseren, processen met één en meerdere handtekeningen te vereenvoudigen en formulieren van mobiele apparaten elektronisch te ondertekenen.
seo-description: Enable e-signature (Acrobat Sign) workflows for an adaptive form to automate signing workflows, simplify single and multi-signature processes, and to electronically sign forms from mobile devices.
uuid: 9c65dc44-c1a5-44df-8659-6efbe347575b
contentOwner: khsingh
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: develop
discoiquuid: 29fc297e-0a95-4d2a-bfe6-5676d53624db
noindex: true
feature: Adaptive Forms, Acrobat Sign
exl-id: 5922ea6e-8be9-4e65-89a6-67b6cc12c4ee
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '3515'
ht-degree: 0%

---

# Acrobat Sign in een adaptieve vorm gebruiken {#using-adobe-sign-in-an-adaptive-form}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Workflows voor e-handtekeningen (Acrobat Sign) inschakelen voor een adaptief formulier om ondertekeningsworkflows te automatiseren, processen met één en meerdere handtekeningen te vereenvoudigen en formulieren van mobiele apparaten elektronisch te ondertekenen.

Acrobat Sign maakt workflows voor e-handtekeningen mogelijk voor adaptieve formulieren. E-handtekeningen verbeteren werkstromen om documenten voor wettig, verkoop, loonlijst, personeelsbeheer, en meer gebieden te verwerken.

In een standaard Acrobat Sign- en adaptief formulierscenario vult een gebruiker een adaptief formulier om een service aan te vragen. Een hypotheek- en creditcardaanvraag vereist bijvoorbeeld wettelijke handtekeningen van alle kredietnemers en medekredietnemers. Als u workflows voor elektronische handtekeningen wilt inschakelen voor vergelijkbare scenario&#39;s, kunt u Acrobat Sign integreren met AEM Forms. Een paar andere voorbeelden zijn:

* Sluit overeenkomsten van om het even welk apparaat met volledig geautomatiseerde voorstel, citaat, en contractprocessen.
* Voltooi processen voor menselijke hulpbronnen sneller en geef uw werknemers de digitale ervaring.
* Verkort de duur van de contractcyclus en neem sneller aan boord van uw leveranciers.
* Maak digitale workflows waarmee algemene processen worden geautomatiseerd.

Acrobat Sign-integratie met AEM Forms ondersteunt:

* Workflows voor ondertekening van enkelvoudige en meervoudige gebruikers
* Workflows voor opeenvolgende en gelijktijdige ondertekening
* In-form en out-of-form ondertekeningservaringen
* Formulieren ondertekenen als anonieme of aangemelde gebruiker
* Dynamische ondertekeningsprocessen (integratie met AEM Forms-workflow)
* Verificatie via een kennisbasis, telefoon en sociale profielen

Meer informatie over [Aanbevolen procedures voor het gebruik van Acrobat Sign met adaptieve formulieren](https://medium.com/adobetech/using-adobe-sign-to-e-sign-an-adaptive-form-heres-the-best-way-to-do-it-dc3e15f9b684) voor betere ondertekeningservaringen.

## Vereisten {#prerequisites}

Voordat u Acrobat Sign in een adaptieve vorm gebruikt:

* Zorg ervoor dat de AEM Forms-cloudservice is geconfigureerd voor gebruik van Acrobat Sign. Zie voor meer informatie [Acrobat Sign integreren met AEM Forms](/help/forms/using/adobe-sign-integration-adaptive-forms.md).
* Behoud de lijst met ondertekenaars klaar. U hebt voor elke ondertekenaar ten minste een e-mailadres nodig.

## Acrobat Sign configureren voor een adaptief formulier {#configure-adobe-sign-for-an-adaptive-form}

Voer de volgende stappen uit om Acrobat Sign voor een adaptief formulier te configureren:

1. [Aangepaste formuliereigenschappen bewerken voor Acrobat Sign](#enableadobesign)
1. [Acrobat Sign-velden toevoegen aan een adaptief formulier](#addadobesignfieldstoanadaptiveform)
1. [Acrobat Sign inschakelen voor een adaptief formulier](#enableadobsignforanadaptiveform)
1. [Acrobat Sign-Cloud Service selecteren voor een adaptief formulier](#selectadobesigncloudserviceforanadaptiveform)

1. [Acrobat Sign-ondertekenaars toevoegen aan een adaptief formulier](#addsignerstoanadaptiveform)
1. [Selecteer Handeling verzenden voor een adaptief formulier](#selectsubmitactionforanadaptiveform)

![ondertekenaar-details](assets/signer-details.png)

### Aangepaste formuliereigenschappen bewerken voor Acrobat Sign {#enableadobesign}

Configureer adaptieve formuliereigenschappen voor Acrobat Sign voor een bestaand of een nieuw adaptief formulier.

[Een adaptief formulier maken voor Acrobat Sign](/help/forms/using/working-with-adobe-sign.md#create-an-adaptive-form-for-adobe-sign) beschrijft de stappen voor het maken van een adaptief basisformulier. Zie [Een adaptief formulier maken](/help/forms/using/creating-adaptive-form.md) voor andere opties beschikbaar wanneer u een adaptief formulier maakt.

#### Een adaptief formulier maken voor Acrobat Sign {#create-an-adaptive-form-for-adobe-sign}

Voer de volgende stappen uit om een adaptief formulier voor Acrobat Sign te maken:

1. Ga naar **[!UICONTROL Adobe Experience Manager]** > **[!UICONTROL Forms]** > **[!UICONTROL Forms & Documents]**.
1. Tikken **[!UICONTROL Create]** en selecteert u **[!UICONTROL Adaptive Form]**. Er wordt een lijst met sjablonen weergegeven. Selecteer de sjabloon en tik op **[!UICONTROL Next]**.
1. In de **[!UICONTROL Basic]** tab:

   1. Geef de **Naam** en **Titel** voor het adaptieve formulier.
   1. Selecteer [configuratiecontainer](/help/forms/using/adobe-sign-integration-adaptive-forms.md#configure-adobe-sign-with-aem-forms) gemaakt tijdens het configureren van Acrobat Sign met AEM Forms.

      >[!NOTE]
      >
      >De **[!UICONTROL Acrobat Sign Cloud Service]** in de vervolgkeuzelijst worden de cloudservices weergegeven die zijn geconfigureerd in de configuratiecontainer die u in dit veld selecteert. De **[!UICONTROL Acrobat Sign Cloud Service]** de vervolgkeuzelijst is beschikbaar in het dialoogvenster **[!UICONTROL Electronic Signature]** van de adaptieve formuliereigenschappen wanneer u de optie **[!UICONTROL Enable Acrobat Sign]** optie.

1. In de **[!UICONTROL Form Model]** selecteert u een van de volgende opties:

   * Selecteer **[!UICONTROL Associate form template as the Document of Record template]** en selecteert u een Document of Record-sjabloon. Als u een op een formuliersjabloon gebaseerd adaptief formulier gebruikt, worden alleen de velden weergegeven die zijn gebaseerd op de bijbehorende formuliersjabloon. Niet alle velden van het adaptieve formulier worden weergegeven.
   * Selecteer **[!UICONTROL Generate Document of Record]** optie. Als u een adaptief formulier met de optie Document of Record gebruikt, worden in het document dat wordt verzonden voor ondertekening alle velden van het adaptieve formulier weergegeven.

1. Tikken **[!UICONTROL Create.]** Er wordt een adaptief formulier voor gebarentaal gemaakt, dat kan worden gebruikt om Acrobat Sign-velden toe te voegen.

#### Een adaptief formulier bewerken voor Acrobat Sign {#editafsign}

Voer de volgende stappen uit om Acrobat Sign in een bestaande adaptieve vorm te gebruiken:

1. Ga naar **[!UICONTROL Adobe Experience Manager]** > **[!UICONTROL Forms]**> **[!UICONTROL Forms & Documents]**.
1. Selecteer het aangepaste formulier en tik op **[!UICONTROL Properties]**.
1. In de **[!UICONTROL Basic]** selecteert u de [configuratiecontainer](/help/forms/using/adobe-sign-integration-adaptive-forms.md#configure-adobe-sign-with-aem-forms) gemaakt tijdens het configureren van Acrobat Sign met AEM Forms.
1. In de **[!UICONTROL Form Model]** selecteert u een van de volgende opties:

   * Selecteer **[!UICONTROL Associate form template as the Document of Record template]** en selecteert u een Document of Record-sjabloon. Als u een op een formuliersjabloon gebaseerd adaptief formulier gebruikt, worden alleen de velden weergegeven die zijn gebaseerd op de bijbehorende formuliersjabloon. Niet alle velden van het adaptieve formulier worden weergegeven.
   * Selecteer **[!UICONTROL Generate Document of Record]** optie. Als u een adaptief formulier met de optie Document of Record gebruikt, worden in het document dat wordt verzonden voor ondertekening alle velden van het adaptieve formulier weergegeven.

1. Tik op **[!UICONTROL Save & Close]**. Het adaptieve formulier is ingeschakeld voor Acrobat Sign.

### Acrobat Sign-velden toevoegen aan een adaptief formulier {#addadobesignfieldstoanadaptiveform}

Acrobat Sign heeft verschillende velden die op een adaptief formulier kunnen worden geplaatst. Deze velden accepteren verschillende gegevenstypen, zoals handtekeningen, initialen, bedrijf of titel, en helpen bij het verzamelen van extra informatie tijdens het ondertekenen, samen met de handtekeningen. Met de Acrobat Sign Block-component kunt u Acrobat Sign-velden op verschillende locaties in een adaptief formulier plaatsen.

Voer de volgende stappen uit om velden toe te voegen aan een adaptief formulier en verschillende opties aan te passen met betrekking tot deze velden:

1. Slepen en neerzetten **Acrobat Sign Block** van de deelbrowser naar het aangepaste formulier. De Acrobat Sign Block-component heeft alle ondersteunde Acrobat Sign-velden. Standaard wordt een **Handtekening** aan het adaptieve formulier.

   ![sign-block](assets/sign-block.png)

   Het Acrobat Sign Block is standaard niet zichtbaar in het gepubliceerde adaptieve formulier. Deze is alleen zichtbaar in de ondertekenende documenten. U kunt de zichtbaarheid van Acrobat Sign Block wijzigen vanuit de eigenschappen van de Acrobat Sign Block-component.

   >[!NOTE]
   >
   >* Het gebruik van een Acrobat Sign-blok is niet verplicht om Acrobat Sign in een adaptieve vorm te gebruiken. Als u geen Acrobat Sign-blok gebruikt en geen velden toevoegt voor de ondertekenaars, wordt het standaardhandtekeningveld onder aan de ondertekenende documenten weergegeven.
   >* Gebruik Acrobat Sign-blok alleen voor aanvullende formulieren die automatisch Document of Record genereren. Als u een aangepaste XDP gebruikt voor het genereren van een Document of een op een formuliersjabloon gebaseerd adaptief formulier, is een Acrobat Sign-blok niet vereist.


1. Selecteer **Acrobat Sign Block** en tik op de **Bewerken** ![aem_6_3_edit](assets/aem_6_3_edit.png) pictogram. Er worden opties weergegeven voor het toevoegen van velden en het opmaken van de weergave van een veld.

   ![adobe-sign-block-select-fields](assets/adobe-sign-block-select-fields.png)

   **A.** Selecteer Acrobat Sign-velden en voeg deze toe. **B.** Acrobat Sign-blok uitbreiden naar volledige schermweergave

1. Tik op de knop **Acrobat Sign-veld** ![aem_6_3_adobesign](assets/aem_6_3_adobesign.png) pictogram. Er worden opties weergegeven voor het selecteren en toevoegen van Acrobat Sign-velden.

   Breid uit **Type** vervolgkeuzelijst om een Acrobat Sign-veld te selecteren en op Gereed te tikken ![aem_6_3_forms_save](assets/aem_6_3_forms_save.png) om het geselecteerde veld toe te voegen aan het Acrobat Sign-blok. De **Type** Het vervolgkeuzeveld bevat de typen Handtekening, Ondertekenaarinformatie en Gegevensveld. Acrobat Sign-integratie met AEM Forms-ondersteuningsvelden die alleen in de keuzelijst Type worden weergegeven. Zie voor meer informatie over Acrobat Sign-velden [Acrobat Sign-documentatie](https://helpx.adobe.com/sign/help/field-types.html).

   ![adobe-sign-block-fields-options](assets/adobe-sign-block-fields-options.png)

   U moet een unieke naam opgeven voor een veld. U kunt ook de vereiste optie selecteren om een verplicht veld te markeren. Naast de **Naam** en **Vereist** bepaalde Acrobat Sign-velden hebben meer opties. Bijvoorbeeld masker en meerdere regels. Geef bovendien voor elk Acrobat Sign-veld een unieke naam, ongeacht of de velden zich in dezelfde of in verschillende Acrobat Sign-blokken bevinden.

### Acrobat Sign inschakelen voor een adaptief formulier {#enableadobsignforanadaptiveform}

Acrobat Sign is niet ingeschakeld voor een adaptief formulier. Voer de volgende stappen uit om het in te schakelen:

1. Tik in de Inhoudsbrowser op **Formuliercontainer** en tik op de knop **Configureren** ![vormen](assets/configure.png) pictogram. De eigenschappenbrowser wordt geopend en de eigenschappen van de container Adaptief formulier worden weergegeven.
1. Vouw in de eigenschappenbrowser de **Elektronische handtekening** en selecteert u de **Acrobat Sign inschakelen** optie. Hiermee wordt Acrobat Sign ingeschakeld voor een adaptief formulier.

### Acrobat Sign-Cloud Service en -handtekeningvolgorde selecteren {#selectadobesigncloudserviceforanadaptiveform}

U kunt meerdere Acrobat Sign-services configureren voor een exemplaar van AEM Forms. Het is raadzaam voor elke functie een aparte reeks diensten te hebben (Human Resource, Finance, enzovoort). Hierdoor wordt het bijhouden en rapporteren van ondertekende documenten eenvoudiger. Een bank heeft bijvoorbeeld meerdere afdelingen. U kunt een afzonderlijke configuratie voor elke afdeling hebben voor het beter volgen van de documenten.

Een document kan ook meerdere ondertekenaars hebben. Een creditcardtoepassing kan bijvoorbeeld meerdere aanvragers hebben. Een bank vereist handtekeningen van alle aanvragers voordat de aanvraag wordt verwerkt. Voor scenario&#39;s met meerdere ondertekenaars kunt u ervoor kiezen het document in volgorde van opeenvolgende of gelijktijdige ondertekening te ondertekenen.

Voer de volgende stappen uit om een cloudservice en de volgorde van ondertekening te selecteren:

![cloudservice](assets/cloud-service.png)

1. Tik in de Inhoudsbrowser op **Formuliercontainer** en tik op de knop **Configureren** ![vormen](assets/configure.png) pictogram. De eigenschappenbrowser wordt geopend en de eigenschappen van de container Adaptief formulier worden weergegeven.
1. Vouw in de eigenschappenbrowser de **Elektronische handtekening** en selecteert u de **Acrobat Sign inschakelen** optie. Hiermee wordt Acrobat Sign ingeschakeld voor een adaptief formulier.
1. Selecteer een cloudservice in de lijst met Acrobat Sign-Cloud Services die al is geconfigureerd.

   Als de **Acrobat Sign Cloud Service** lijst is leeg, volgt de [Acrobat Sign configureren met AEM Forms](/help/forms/using/adobe-sign-integration-adaptive-forms.md) artikel om de service te configureren.

   In het vervolgkeuzemenu worden de cloudservices weergegeven die in het dialoogvenster `global` map in Gereedschappen > **[!UICONTROL Cloud Services]** > **[!UICONTROL Acrobat Sign]**. Daarnaast worden in het vervolgkeuzemenu ook de cloudservices weergegeven die aanwezig zijn in de map die u selecteert in het dialoogvenster **[!UICONTROL Configuration Container]** wanneer u een adaptief formulier maakt.

1. Selecteer de handtekeningvolgorde in het menu **Ondertekenaars kunnen ondertekenen** in. Acrobat Sign-zangers kunnen een adaptief formulier ondertekenen **Opeenvolgend** - een na een andere ondertekenaar, of **Gelijktijdig** - in willekeurige volgorde.

   Eén ondertekenaar ontvangt het formulier voor ondertekening achtereenvolgens in de volgorde. Nadat een ondertekenaar het ondertekenen van het document heeft voltooid, wordt het formulier verzonden naar de volgende ondertekenaar, enzovoort.

   Meerdere ondertekenaars kunnen tegelijkertijd een formulier ondertekenen.

1. [Ondertekenaars toevoegen aan een adaptief formulier](#addsignerstoanadaptiveform) en tik op het pictogram Done om de wijzigingen op te slaan.

### Ondertekenaars toevoegen aan een adaptief formulier {#addsignerstoanadaptiveform}

U kunt slechts één ondertekenaar of meerdere ondertekenaars hebben voor een adaptief formulier. Wanneer u een ondertekenaar toevoegt, kunt u ook verificatiedetails voor de ondertekenaar configureren. U kunt ook selecteren of de invuller en zanger van het formulier dezelfde persoon zijn. Voer de volgende stappen uit om diverse details over een ondertekenaar toe te voegen en te verstrekken:

1. Tik in de Inhoudsbrowser op **Formuliercontainer** en tik op de knop **Configureren** ![vormen](assets/configure.png) pictogram. De eigenschappenbrowser wordt geopend met de eigenschappen van de container Adaptief formulier.
1. Vouw in de eigenschappenbrowser de **Elektronische handtekening** en selecteert u de **Acrobat Sign inschakelen** optie. Hiermee wordt Acrobat Sign ingeschakeld voor een adaptief formulier.
1. Tikken **Ondertekenaar toevoegen** krachtens **Configuratie ondertekenaar.** Er wordt een ondertekenaar toegevoegd aan het adaptieve formulier. U kunt meerdere Acrobat Sign-ondertekenaars toevoegen aan een adaptief formulier.
1. ![telefoongegevens](assets/phone-details.png)

   Klik op de knop **Bewerken** ![aem_6_3_edit](assets/aem_6_3_edit.png) pictogram om de volgende informatie over de ondertekenaar op te geven:

   * **Titel:** Geef een titel op om een ondertekenaar op unieke wijze te identificeren.
   * **Is de ondertekenaar en de persoon die het formulier invult hetzelfde?** Selecteren **Ja**, als de invuller van het formulier en de eerste ondertekenaar dezelfde persoon zijn. Als de optie is ingesteld op **Nee,** gebruikt u de component voor de stap Handtekening vervolgens niet in het adaptieve formulier. Als het formulier een component Handtekeningstap bevat, wordt het veld automatisch ingesteld op Ja.
   * **E-mailadres ondertekenaar:** Geef het e-mailadres van de ondertekenaar op. Ondertekenaar ontvangt om ondertekende documenten/formulier te zijn op het opgegeven e-mailadres. U kunt een e-mailadres gebruiken dat wordt opgegeven in een formulierveld, in AEM gebruikersprofiel van de aangemelde gebruiker, of handmatig een e-mailadres invoeren. Het is een verplichte stap. Houd er ook rekening mee dat als u slechts één ondertekenaar hebt geconfigureerd, het e-mailadres van de ondertekenaar niet hetzelfde is als het Acrobat Sign-account dat wordt gebruikt om AEM-cloudservices te configureren.
   * **Verificatiemethode ondertekenaar:** Geef de methode op voor het verifiëren van een gebruiker voordat u een formulier voor ondertekening opent. U kunt tussen telefoon, kennisbasis, en sociale op identiteit-gebaseerde authentificatie kiezen.

   >[!NOTE]
   >
   >* Standaard biedt verificatie op basis van sociale identiteit een optie voor verificatie met behulp van Facebook, Google en LinkedIn. U kunt contact opnemen met Acrobat Sign-ondersteuning om andere providers van sociale verificatie in te schakelen.


   * **Acrobat Sign-velden die moeten worden ingevuld of ondertekend:** Selecteer Acrobat Sign-velden voor de ondertekenaar. Een adaptief formulier kan meerdere Acrobat Sign-velden hebben. U kunt specifieke velden inschakelen voor een ondertekenaar. In het veld worden alle beschikbare Acrobat Sign-blokken weergegeven. Wanneer u een blok selecteert, worden alle velden van het blok geselecteerd. U kunt het X-pictogram gebruiken om de selectie van een veld op te heffen.

   ![signer-details-1](assets/signer-details-1.png)

   De bovenstaande afbeelding heeft twee voorbeelden van Acrobat Sign Blocks: Persoonlijke gegevens en kantoorgegevens

   Tik op Gereed ![aem_6_3_forms_save](assets/aem_6_3_forms_save.png) pictogram. De ondertekenaar wordt toegevoegd en geconfigureerd.

### Selecteer Handeling verzenden voor een adaptief formulier {#selectsubmitactionforanadaptiveform}

Nadat u Acrobat Sign-velden hebt toegevoegd aan een adaptief formulier, Acrobat Sign inschakelen vanuit formuliercontainer, Acrobat Sign-Cloud Service selecteren en Acrobat Sign-ondertekenaars toevoegen, selecteert u een geschikte verzendactie voor het adaptieve formulier. Voor meer informatie over adaptieve formulieren die acties verzenden, raadpleegt u [De handeling Verzenden configureren](/help/forms/using/configuring-submit-actions.md).

Bovendien wordt een adaptief formulier dat geschikt is voor Acrobat Sign alleen verzonden nadat alle ondertekenaars het formulier hebben ondertekend. Gedeeltelijk ondertekend formulier vindt u in de sectie Ondertekenen in behandeling van de portal Formulieren. Acrobat Sign Configuration Service houdt opiniepeiling van Acrobat Sign-server bij [regelmatige intervallen](/help/forms/using/adobe-sign-integration-adaptive-forms.md) om de status van handtekeningen te verifiëren. Als alle ondertekenaars het ondertekenen van het formulier hebben voltooid, wordt de verzendactieservice gestart en wordt het formulier verzonden. Als u een aangepaste verzendactie gebruikt en het formulier Acrobat Sign gebruikt, werkt u de aangepaste verzendactie bij om de verzendactieservice te gebruiken.

>[!NOTE]
>
>Gegevens van het adaptieve formulier worden tijdelijk opgeslagen op Forms Portal. Het wordt aanbevolen [aangepaste opslag voor Forms Portal](/help/forms/using/configuring-draft-submission-storage.md). Het zorgt ervoor dat PII (persoonlijk identificeerbare informatie) gegevens niet op AEM servers wordt opgeslagen.

Uw ervaring voor het ondertekenen van formulieren is gereed. U kunt een voorbeeld van het formulier bekijken om de ondertekeningservaring te verifiëren. Op het gepubliceerde formulier worden de velden Acrobat Sign Block weergegeven wanneer een ondertekenaar het formulier voor ondertekening via een e-mail ontvangt. Deze ervaring wordt ook wel bekend als een ondertekeningservaring in de vorm van een out-of-form. U kunt ook een ondertekeningservaring in formulieren configureren voor de eerste ondertekenaar. Zie voor meer informatie [Ervaring voor ondertekenen in formulieren maken](/help/forms/using/working-with-adobe-sign.md#create-in-form-signing-experience).

## Cloud-handtekeningen configureren voor een adaptief formulier {#configure-cloud-signatures-for-an-adaptive-form}

Digitale handtekeningen op basis van cloud of externe handtekeningen zijn een nieuwe generatie digitale handtekeningen die op verschillende computers, mobiele apparaten en het web werken en voldoen aan de hoogste standaarden en waarborgen voor ondertekenaarsverificatie. U kunt een adaptief formulier ondertekenen met digitale handtekeningen op basis van de cloud.

Na [aanpassen formuliereigenschappen voor Acrobat Sign bewerken](#enableadobesign), voert u de volgende stappen uit om het veld voor een cloudhandtekening toe te voegen aan een adaptief formulier:

1. Slepen en neerzetten **Acrobat Sign Block** van de deelbrowser naar het aangepaste formulier. De Acrobat Sign Block-component heeft alle ondersteunde Acrobat Sign-velden. Standaard wordt een **Handtekening** aan het adaptieve formulier.

   ![sign-block](assets/sign-block.png)

1. Selecteer **Acrobat Sign Block** en tik op de **Bewerken** ![aem_6_3_edit](assets/aem_6_3_edit.png) pictogram. Er worden opties weergegeven voor het toevoegen van velden en het opmaken van de weergave van een veld.

   ![adobe-sign-block-select-fields](assets/adobe-sign-block-select-fields.png)

   **A.** Selecteer Acrobat Sign-velden en voeg deze toe. **B.** Acrobat Sign-blok uitbreiden naar volledige schermweergave

1. Tik op de knop **Acrobat Sign-veld** ![aem_6_3_adobesign](assets/aem_6_3_adobesign.png) pictogram. Er worden opties weergegeven voor het selecteren en toevoegen van Acrobat Sign-velden.

   Breid uit **Type** vervolgkeuzelijst die moet worden geselecteerd **Digitale handtekening** en tik op Gereed ![aem_6_3_forms_save](assets/aem_6_3_forms_save.png) om het geselecteerde veld toe te voegen aan het Acrobat Sign-blok.

   ![digital_signatures](assets/digital_signatures.png)

   U moet een unieke naam opgeven voor een veld.

   Digitale handtekeningen toepassen op het adaptieve formulier met:

   * Wolkhandtekeningen: Ondertekenen met een [digitale id](https://helpx.adobe.com/sign/kb/digital-certificate-providers.html) gehost door een vertrouwde serviceprovider.
   * Adobe Acrobat of Reader: Download en open het document met Adobe Acrobat of Reader om het te ondertekenen met een smartcard, USB-token of een digitale id op basis van een bestand.

   Nadat u het handtekeningveld voor de cloud aan het adaptieve formulier hebt toegevoegd, voert u de volgende stappen uit om het configuratieproces te voltooien:

   * [Acrobat Sign inschakelen voor een adaptief formulier](#enableadobsignforanadaptiveform)
   * [Acrobat Sign-Cloud Service selecteren voor een adaptief formulier](#selectadobesigncloudserviceforanadaptiveform)
   * [Acrobat Sign-ondertekenaars toevoegen aan een adaptief formulier](#addsignerstoanadaptiveform)
   * [Selecteer Handeling verzenden voor een adaptief formulier](#selectsubmitactionforanadaptiveform)


## Ervaring voor ondertekenen in formulieren maken {#create-in-form-signing-experience}

Een gebruiker kan ook een adaptief formulier ondertekenen terwijl het formulier wordt ingevuld. Deze ervaring wordt ook wel &#39;in-form signing experience&#39; genoemd. De ondertekeningservaring in formulieren is alleen beschikbaar voor de eerste ondertekenaar in een omgeving met meerdere ondertekenaars. Voer de volgende stappen uit om een ondertekeningservaring in formulieren te maken voor een adaptief formulier:

1. [De component voor de stap Handtekening toevoegen en configureren](#add-and-configure-the-signature-step-component).
1. [De component Summiere stap toevoegen](#configure-the-thank-you-page-or-summary-step-component).

![in-form-signing-experience](assets/in-form-signing-experience.png)

### De component voor de stap Handtekening toevoegen en configureren {#add-and-configure-the-signature-step-component}

Gebruik de component Handtekeningstap om een gebied op te geven voor de elektronische ondertekening van het ingevulde formulier. Wanneer de sectie met de component Signature Step wordt weergegeven, wordt een PDF-versie van het ingevulde formulier weergegeven. De component voor de stap Handtekening gebruikt de volledige breedte die beschikbaar is voor het formulier. Het wordt aanbevolen geen andere component op te nemen in de sectie die de component voor de stap Handtekening bevat.

Voer de volgende stappen uit om de component van de Stap van de Handtekening te vormen:

1. Sleep de **Handtekeningstap** van de browser Componenten naar het formulier.
1. Selecteer de nieuwe component voor de stap Handtekening en tik op de knop **Configureren** ![vormen](assets/configure.png) pictogram. De eigenschappenbrowser wordt geopend en de eigenschappen voor stap Handtekening worden weergegeven. Configureer de volgende eigenschappen:

   * **Elementnaam**: Geef de naam van de component op.
   * **Titel:** Geef de unieke titel van de component op.
   * **Sjabloonbericht:** Geef het bericht op dat moet worden weergegeven wanneer de PDF van de handtekening wordt geladen. Acrobat Sign-services hebben enige tijd nodig om de PDF van de handtekening voor te bereiden en te laden.
   * **Ondertekeningsservice:** Selecteer **Acrobat Sign** optie.
   * **Verouderde E-sign component gebruiken**: Als u het betreffende adaptieve formulier in [AEM Forms Workspace](/help/forms/using/introduction-html-workspace.md), AEM Forms-toepassing of het onderliggende adaptieve formulier heeft een verouderde e-sign component, selecteert u de **Verouderde E-sign component gebruiken** optie.
   * **Configuratie**: Selecteer een configuratie (Acrobat Sign Cloud Service). De vervolgkeuzelijst is alleen beschikbaar als de **Verouderde E-sign component gebruiken** is ingeschakeld.

   Tik op Gereed ![aem_6_3_forms_save](assets/aem_6_3_forms_save.png) om de wijzigingen op te slaan.

   ![handtekening-stap](assets/signature-step.png)

   >[!NOTE]
   >
   >* Wanneer u de **[!UICONTROL Signature Step]** aan het formulier, de **[!UICONTROL Is the signer and the person filling the form same?]** optie wordt automatisch ingesteld op **Ja**. U moet het formulier blijven gebruiken.
   >* Aangepaste formulieren die zijn ingeschakeld in Acrobat Sign, ondersteunen niet het gebruik van de knop Verzenden in de sectie of het deelvenster met de component Stap handtekening. U kunt een samenvattingsstap toevoegen nadat de stap Handtekening voor handmatige verzending is geactiveerd of nadat een automatische verzending is gestart met behulp van de intervalset [Acrobat Sign Configuration Service](/help/forms/using/adobe-sign-integration-adaptive-forms.md#configure-adobe-sign-scheduler-to-sync-the-signing-status).


### De component voor de prullenbak of overzichtsstap configureren {#configure-the-thank-you-page-or-summary-step-component}

De **Samenvattingsstap** wordt het formulier automatisch verzonden, wordt de informatie in de aangepaste overzichtspagina ingevuld en wordt de samenvatting van het verzonden formulier weergegeven. Het krijgt ook de vereiste informatie in de terugkeerkaart. De component SummaryStep gebruikt de volledige breedte die beschikbaar is voor het formulier. Men adviseert om geen andere component op de sectie te hebben die de Summiere component van de Stap bevat.

De ervaring voor het ondertekenen van formulieren is nu gereed. U kunt een voorbeeld van het formulier bekijken om de ondertekeningservaring te verifiëren.

## Veelgestelde vragen {#frequently-asked-questions}

**V: U kunt een adaptief formulier insluiten in een ander adaptief formulier. Kan het ingesloten adaptieve formulier Acrobat Sign inschakelen?**

**Ans:** Nee, AEM Forms biedt geen ondersteuning voor het gebruik van een adaptief formulier waarmee een adaptief formulier dat geschikt is voor Acrobat Sign, wordt ingesloten voor ondertekening.

**V: Wanneer ik een adaptief formulier maak met de geavanceerde sjabloon en dit open voor bewerking, wordt het foutbericht &quot;Elektronische handtekeningen of ondertekenaars zijn niet correct geconfigureerd&quot; weergegeven. wordt weergegeven. Hoe kan ik het foutbericht oplossen?**

**Ans:** Adaptief formulier dat is gemaakt met de geavanceerde sjabloon is geconfigureerd voor gebruik van Acrobat Sign. U lost de fout op door een Acrobat Sign-cloudconfiguratie te maken en te selecteren en een Acrobat Sign-ondertekenaar voor het aangepaste formulier te configureren.

**V: Kan ik Acrobat Sign-tekstcodes gebruiken in een statisch tekstonderdeel van een adaptief formulier?**

**Ans:** Ja, u kunt tekstcodes in een tekstcomponent gebruiken om Acrobat Sign-velden aan een [Document van record](/help/forms/using/generate-document-of-record-for-non-xfa-based-adaptive-forms.md) (Alleen automatisch gegenereerd document met opnameoptie) Aangepast formulier ingeschakeld. Ga voor meer informatie over de procedure en regels voor het maken van een tekstlabel naar [Acrobat Sign-documentatie](https://experienceleague.adobe.com/docs/document-cloud-learn/sign-learning-hub/admin-set-up/advanced-tasks-admins/adobe-sign-text-tagging.html). Houd er rekening mee dat adaptieve formulieren beperkte ondersteuning bieden voor tekstcodes. Met de tekstcodes kunt u alleen die velden maken die door Acrobat Sign Block worden ondersteund.

**V: AEM Forms biedt zowel Acrobat Sign-onderdelen voor blok- als handtekeningstappen. Kunnen deze gelijktijdig in een adaptieve vorm worden gebruikt?**

**Ans:** U kunt beide componenten tegelijkertijd in een formulier gebruiken. Hier volgen enkele aanbevelingen voor het gebruik van deze componenten:

**Acrobat Sign-blok:** Met het Acrobat Sign Block kunt u Acrobat Sign-velden overal op het adaptieve formulier toevoegen. Het helpt ook om specifieke gebieden aan ondertekenaars toe te wijzen. Wanneer een adaptief formulier wordt voorvertoond of gepubliceerd, is Acrobat Sign Block standaard niet zichtbaar. Deze blokken zijn alleen beschikbaar in het ondertekenende document. In het ondertekenende document worden alleen de velden ingeschakeld die zijn toegewezen aan een ondertekenaar. Acrobat Sign-blok kan worden gebruikt met eerste en volgende ondertekenaars.

**Ondertekeningsstapcomponent:** U kunt de component voor het verzenden van handtekeningen gebruiken om in formulieren ondertekenen te maken. Hiermee kan alleen de eerste ondertekenaar ondertekenen terwijl het formulier wordt ingevuld. Wanneer de sectie met de component Signature Step wordt weergegeven, wordt een ondertekenbare PDF-versie van het formulier weergegeven. Het is doorgaans de laatste of voorlaatste sectie, gevolgd door een overzichtscomponent van een formulier.
