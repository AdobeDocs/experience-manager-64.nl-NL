---
title: Een bevestiging van het verzenden van een formulier verzenden via e-mail
seo-title: Sending a form submission acknowledgement via email
description: Met AEM Forms kunt u de handeling voor het verzenden van e-mail configureren. Hiermee wordt een bevestiging verzonden naar een gebruiker bij het verzenden van het formulier.
seo-description: AEM Forms allows you to configure the email submit action that sends an acknowledgement to a user on submitting the form.
uuid: 77b3c836-6011-48bd-831c-ebc214218efb
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: publish
discoiquuid: 7ffe6317-174b-4d80-9ac6-9bfb5eed7e29
exl-id: e850d2a5-cb5f-4bd4-81dd-57951923b6d3
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 0%

---

# Een bevestiging van het verzenden van een formulier verzenden via e-mail {#sending-a-form-submission-acknowledgement-via-email}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Aangepaste verzending van formuliergegevens {#adaptive-form-data-submission}

Adaptieve formulieren bieden verschillende kant-en-klare versies [acties verzenden](/help/forms/using/configuring-submit-actions.md) workflows voor het verzenden van de formuliergegevens naar verschillende eindpunten.

De **E-mailactie** Met een handeling verzenden wordt een e-mail verzonden wanneer een adaptief formulier met succes is verzonden. Het kan ook worden geconfigureerd om de formuliergegevens en de PDF in de e-mail te verzenden.

In dit artikel worden de stappen beschreven die nodig zijn om de e-mailactie in te schakelen voor een adaptief formulier en voor verschillende configuraties.

>[!NOTE]
>
>U kunt ook de opdracht **E-mailactie** om het ingevulde formulier per e-mail te verzenden als PDF-bijlage. De configuratieopties die beschikbaar zijn voor deze actie zijn gelijk aan de opties die beschikbaar zijn voor de e-mailactie. De actie Email PDF is alleen beschikbaar voor op XFA gebaseerde adaptieve formulieren

## E-mailactie {#email-action}

Met de e-mailactie kan een auteur automatisch e-mail verzenden naar een of meer ontvangers wanneer een adaptief formulier is verzonden.

>[!NOTE]
>
>Om de actie E-mail te gebruiken, moet u de AEM postdienst vormen zoals die in wordt beschreven [De mailservice configureren](/help/sites-administering/notification.md#configuring-the-mail-service).

### E-mailactie inschakelen op een adaptief formulier {#enabling-email-action-on-an-adaptive-form}

1. Open een adaptief formulier in de bewerkingsmodus.

1. Klikken **Bewerken** naast de **Begin van een adaptief formulier** werkbalk.

   Het dialoogvenster Component bewerken wordt geopend.

   ![Dialoogvenster van component bewerken voor een adaptief formulier](assets/start_of_adp_form.png)

1. Selecteer **Handelingen verzenden** en kiest u **E-mailactie** in de vervolgkeuzelijst Handeling verzenden.

   Op het tabblad vindt u de opties voor het configureren van de e-mailactie voor het huidige formulier.

   ![Tabblad Handelingen verzenden](assets/dialog.png)

1. Geef geldige e-mailadressen op in de velden Mailto, CC en BCC.

   Geef het onderwerp en de inhoud van de e-mail op in de sjabloonvelden Onderwerp en E-mail.

   U kunt ook variabele plaatsaanduidingen opgeven in de velden. In dat geval worden de waarden van de velden verwerkt wanneer het formulier met succes wordt verzonden door een eindgebruiker. Zie voor meer informatie [Aangepaste formulierveldnamen gebruiken om e-mailinhoud dynamisch te maken](/help/forms/using/form-submission-receipt-via-email.md#p-using-adaptive-form-field-names-to-dynamically-create-email-content-p).

   Selecteer Inclusief bijlagen als het formulier bestandsbijlagen bevat en u deze bestanden in de e-mail wilt bijvoegen.

   >[!NOTE]
   >
   >Als u **E-mailactie**, moet u de optie Bijlagen opnemen selecteren.

1. Klikken **OK** om de wijzigingen op te slaan.

### Aangepaste formulierveldnamen gebruiken om e-mailinhoud dynamisch te maken {#using-adaptive-form-field-names-to-dynamically-create-email-content}

De veldnamen in een adaptief formulier worden plaatsaanduidingen genoemd die worden vervangen door de waarde van dat veld nadat een gebruiker het formulier heeft verzonden.

Op het tabblad E-mailactie kunt u plaatsaanduidingen gebruiken die worden verwerkt wanneer de handeling wordt uitgevoerd. Dit betekent dat de kopteksten van de e-mail (zoals Mailto, CC, BCC, onderwerp) worden gegenereerd wanneer de gebruiker het formulier verzendt.

Als u een tijdelijke aanduiding wilt definiëren, geeft u `${<field name>}` in een veld op het tabblad Handelingen verzenden.

Als het formulier bijvoorbeeld het **E-mailadres** veld, naam `email_addr`Voor het vastleggen van de e-mailid van een gebruiker kunt u het volgende opgeven in de velden Mailto, CC of BCC.

`${email_addr}`

Wanneer een gebruiker het formulier verzendt, wordt een e-mail verzonden naar de e-mailid die is ingevoerd in het dialoogvenster `email_addr` van het formulier.

>[!NOTE]
>
>U kunt de naam van een veld vinden in het dialoogvenster **Bewerken** voor het veld.

U kunt ook plaatsaanduidingen voor variabelen gebruiken in het dialoogvenster **Onderwerp** en **E-mailsjabloon** velden.

Bijvoorbeeld:

`Hi ${first_name} ${last_name},`

`Your form has been received by our department. It usually takes ten business days to process the request.`

`Regards`

`Administrator`

>[!NOTE]
>
>Velden in herhaalbare deelvensters kunnen niet worden gebruikt als plaatsaanduidingen voor variabelen.
