---
title: Een bevestiging van het verzenden van een formulier verzenden via e-mail
seo-title: Een bevestiging van het verzenden van een formulier verzenden via e-mail
description: Met AEM Forms kunt u de handeling voor het verzenden van e-mail configureren. Hiermee wordt een bevestiging verzonden naar een gebruiker bij het verzenden van het formulier.
seo-description: Met AEM Forms kunt u de handeling voor het verzenden van e-mail configureren. Hiermee wordt een bevestiging verzonden naar een gebruiker bij het verzenden van het formulier.
uuid: 77b3c836-6011-48bd-831c-ebc214218efb
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: publish
discoiquuid: 7ffe6317-174b-4d80-9ac6-9bfb5eed7e29
translation-type: tm+mt
source-git-commit: 36baba4ee20dd3d7d23bc50bfa91129588f55d32
workflow-type: tm+mt
source-wordcount: '586'
ht-degree: 0%

---


# Een bevestiging van het verzenden van een formulier verzenden via e-mail {#sending-a-form-submission-acknowledgement-via-email}

## Aangepaste verzending van formuliergegevens {#adaptive-form-data-submission}

Aangepaste formulieren bieden verschillende workflows voor het verzenden van formuliergegevens naar verschillende eindpunten voor het verzenden van [acties](/help/forms/using/configuring-submit-actions.md).

Met de verzendactie **E-mail** wordt bijvoorbeeld een e-mail verzonden wanneer een adaptief formulier met succes is verzonden. Het kan ook worden geconfigureerd om de formuliergegevens en de PDF in de e-mail te verzenden.

In dit artikel worden de stappen beschreven die nodig zijn om de e-mailactie in te schakelen voor een adaptief formulier en voor verschillende configuraties.

>[!NOTE]
>
>U kunt ook de **e-mailactie PDF** gebruiken om het ingevulde formulier per e-mail te verzenden als PDF-bijlage. De configuratieopties die beschikbaar zijn voor deze actie zijn gelijk aan de opties die beschikbaar zijn voor de e-mailactie. De actie PDF-bestand via e-mail is alleen beschikbaar voor op XFA gebaseerde adaptieve formulieren

## E-mailactie {#email-action}

Met de e-mailactie kan een auteur automatisch e-mail verzenden naar een of meer ontvangers wanneer een adaptief formulier is verzonden.

>[!NOTE]
>
>Om de actie E-mail te gebruiken, moet u de AEM postdienst vormen zoals die in [het Vormen van de postdienst](/help/sites-administering/notification.md#configuring-the-mail-service) wordt beschreven.

### E-mailactie inschakelen op een adaptief formulier {#enabling-email-action-on-an-adaptive-form}

1. Open een adaptief formulier in de bewerkingsmodus.

1. Klik op **Bewerken** naast de werkbalk **Begin van een adaptief formulier**.

   Het dialoogvenster Component bewerken wordt geopend.

   ![Dialoogvenster van component bewerken voor een adaptief formulier](assets/start_of_adp_form.png)

1. Selecteer het tabblad **Handelingen verzenden** en kies **Handeling e-mailen** in de vervolgkeuzelijst Handeling verzenden.

   Op het tabblad vindt u de opties voor het configureren van de e-mailactie voor het huidige formulier.

   ![Tabblad Handelingen verzenden](assets/dialog.png)

1. Geef geldige e-mailadressen op in de velden Mailto, CC en BCC.

   Geef het onderwerp en de inhoud van de e-mail op in de sjabloonvelden Onderwerp en E-mail.

   U kunt ook variabele plaatsaanduidingen opgeven in de velden. In dat geval worden de waarden van de velden verwerkt wanneer het formulier met succes wordt verzonden door een eindgebruiker. Zie [Aangepaste formulierveldnamen gebruiken om dynamisch e-mailinhoud te maken](/help/forms/using/form-submission-receipt-via-email.md#p-using-adaptive-form-field-names-to-dynamically-create-email-content-p) voor meer informatie.

   Selecteer Inclusief bijlagen als het formulier bestandsbijlagen bevat en u deze bestanden in de e-mail wilt bijvoegen.

   >[!NOTE]
   >
   >Als u de **e-mailactie PDF** kiest, moet u de Inclusief optie Bijlagen selecteren.

1. Klik **OK** om de wijzigingen op te slaan.

### Aangepaste formulierveldnamen gebruiken om e-mailinhoud dynamisch te maken {#using-adaptive-form-field-names-to-dynamically-create-email-content}

De veldnamen in een adaptief formulier worden plaatsaanduidingen genoemd die worden vervangen door de waarde van dat veld nadat een gebruiker het formulier heeft verzonden.

Op het tabblad E-mailactie kunt u plaatsaanduidingen gebruiken die worden verwerkt wanneer de handeling wordt uitgevoerd. Dit betekent dat de kopteksten van de e-mail (zoals Mailto, CC, BCC, onderwerp) worden gegenereerd wanneer de gebruiker het formulier verzendt.

Als u een tijdelijke aanduiding wilt definiëren, geeft u `${<field name>}` op in een veld op het tabblad Handelingen verzenden.

Als het formulier bijvoorbeeld het veld **E-mailadres** bevat met de naam `email_addr` voor het vastleggen van de e-mailid van een gebruiker, kunt u het volgende opgeven in de velden Mailto, CC of BCC.

`${email_addr}`

Wanneer een gebruiker het formulier verzendt, wordt een e-mail verzonden naar de e-mailid die is ingevoerd in het veld `email_addr` van het formulier.

>[!NOTE]
>
>U kunt de naam van een veld vinden in het dialoogvenster **Bewerken** voor het veld.

U kunt ook plaatsaanduidingen voor variabelen gebruiken in de velden **Onderwerp** en **E-mailsjabloon**.

Bijvoorbeeld:

`Hi ${first_name} ${last_name},`

`Your form has been received by our department. It usually takes ten business days to process the request.`

`Regards`

`Administrator`

>[!NOTE]
>
>Velden in herhaalbare deelvensters kunnen niet worden gebruikt als plaatsaanduidingen voor variabelen.

