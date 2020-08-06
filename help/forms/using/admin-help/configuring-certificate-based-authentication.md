---
title: Op certificaten gebaseerde verificatie configureren
seo-title: Op certificaten gebaseerde verificatie configureren
description: Importeer een certificaat van certificeringsinstanties (CA) in het vertrouwde archief en maak een certificaattoewijzing voor verificatie op basis van een certificaat.
seo-description: Importeer een certificaat van certificeringsinstanties (CA) in het vertrouwde archief en maak een certificaattoewijzing voor verificatie op basis van een certificaat.
uuid: 9802a969-6d29-4b80-a4ed-06eb6e66e046
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_user_management
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: d958ae65-3008-4d68-9e11-4346e149827f
translation-type: tm+mt
source-git-commit: d04e08e105bba2e6c92d93bcb58839f1b5307bd8
workflow-type: tm+mt
source-wordcount: '747'
ht-degree: 0%

---


# Op certificaten gebaseerde verificatie configureren {#configuring-certificate-based-authentication}

Gebruikersbeheer voert meestal verificatie uit met een gebruikersnaam en wachtwoord. Gebruikersbeheer ondersteunt ook verificatie op basis van certificaten, waarmee u gebruikers kunt verifiëren via Acrobat of gebruikers programmatisch kunt verifiëren. Voor details over het voor authentiek verklaren van gebruikers programmatically, zie [Programmering met AEM vormen](https://www.adobe.com/go/learn_aemforms_programming_63).

Als u verificatie op basis van certificaten wilt gebruiken, importeert u een certificaat van certificeringsinstanties (CA) dat u vertrouwt in het vertrouwde archief en maakt u vervolgens een certificaattoewijzing.

## Het CA-certificaat importeren {#import-the-ca-certificate}

Selecteer tijdens het importeren van het certificaat de opties Vertrouwd op certificaatverificatie en Vertrouwen op identiteit en eventuele andere opties die u nodig hebt. Zie Certificaten [beheren voor meer informatie over het importeren van certificaten](/help/forms/using/admin-help/certificates.md#managing-certificates).

## Certificaattoewijzing configureren {#configuring-certificate-mapping}

Als u verificatie op basis van certificaten wilt inschakelen voor gebruikers, maakt u een certificaattoewijzing. Een *certificaattoewijzing* definieert een kaart tussen de kenmerken van een certificaat en de kenmerken van gebruikers in een domein. U kunt meerdere certificaten toewijzen aan hetzelfde domein.

Wanneer u een certificaat test, uploadt Gebruikersbeheer de certificaatcontroles om ervoor te zorgen dat het aan de volgende vereisten voldoet:

* Het certificaat is geldig.
* De uitgever u specificeerde kan het certificaat verifiëren.
* Het certificaat bevat het kenmerk dat is vereist voor toewijzing.
* Door de toewijzing die u hebt opgegeven, wordt het certificaat toegewezen aan slechts één gebruiker in de database met AEM formulieren. Zowel huidige als verouderde (verwijderde) gebruikers worden gecontroleerd om te bepalen of zij aan de toewijzingscriteria voldoen. Daarom ontbreekt de certificaattest als meer dan één gebruiker, met inbegrip van verouderde gebruikers, de attributenwaarde heeft die wordt overwogen.

>[!NOTE]
>
>U kunt een bestaande certificaattoewijzing niet bewerken.

**Certificaattoewijzing toevoegen**

1. Klik in de beheerconsole op Instellingen > Gebruikersbeheer > Configuratie > Certificaattoewijzing.
1. Klik op Nieuwe certificaattoewijzing en selecteer in de lijst Voor uitgever de certificaatalias zoals geconfigureerd in Betrouwbaarheidsopslagbeheer.
1. Wijs een van de kenmerken van het certificaat toe aan het kenmerk van een gebruiker. U kunt bijvoorbeeld de algemene naam van het certificaat toewijzen aan de aanmeldings-id van de gebruiker.

   Als de inhoud van het kenmerk in het certificaat afwijkt van de inhoud in het kenmerk van de gebruiker in de gebruikersbeheerdatabase, kunt u een reguliere Java-expressie (regex) gebruiken die overeenkomt met de twee kenmerken. Bijvoorbeeld, als de gemeenschappelijke namen van de certificaten namen zoals *Alex Pink (Authentificatie)* en *Alex Pink (Ondertekenen)* zijn en de gemeenschappelijke naam in het gegevensbestand van het Beheer van de Gebruiker *Alex Pink* is, gebruikt u een regex om het vereiste deel van het certificaatattribuut (in dit voorbeeld, *Alex Pink*.) te halen. De reguliere expressie die u opgeeft, moet voldoen aan de Java regex-specificatie.

   U kunt de expressie transformeren door de volgorde van de groepen op te geven in het vak Aangepaste volgorde. De aangepaste volgorde wordt gebruikt bij de `java.util.regex.Matcher.replaceAll()` methode. Het gedrag dat wordt weergegeven, komt overeen met het gedrag van die methode en de invoertekenreeks (de aangepaste volgorde) moet dienovereenkomstig worden opgegeven.

   Om regex te testen, ga een waarde in het vakje van de Parameter van de Test in en klik Test.

   U kunt de volgende tekens in de regex gebruiken:

   * . (any character)
   * &amp;ast; (0 or more occurrences)
   * () (geef de groep tussen haakjes op)
   * \ (wordt gebruikt om een regex-teken te verwijderen uit een normaal teken)
   * $n (wordt gebruikt om naar de negende groep te verwijzen)

   Examples of regular expressions:

   * To extract &quot;Alex Pink&quot; from &quot;Alex Pink (Authentication)&quot;

      **Regex:** (.&amp;ast;) \(Authentificatie\)

   * &quot;Alex Pink&quot; uit &quot;Alex (Authentication) Pink&quot; extraheren

      **Regex:** (.&amp;ast;)\(Authentificatie\) (.&amp;ast;)

   * Om &quot;Roze Alex&quot; te extraheren uit &quot;Alex (Authentication) Pink&quot;

      **Regex:** (.&amp;ast;)\(Authentificatie\) (.&amp;ast;)

      Aangepaste volgorde: $2 $1 (tweede groep retourneren, samengevoegd met eerste groep, vastgelegd door teken voor witruimte)

   * &quot;apink@sampleorg.com&quot; extraheren uit &quot;smtp:apink@sampleorg.com&quot;

      **Regex:** smtp:(.&amp;ast;)
   Zie [Java-zelfstudie over reguliere expressies](https://java.sun.com/docs/books/tutorial/essential/regex/)voor meer informatie over het gebruik van reguliere expressies.

1. Selecteer in de lijst Voor domein het domein van de gebruiker.
1. To test this configuration, click Browse to upload a sample user certificate, click Test Certificate and, if the configuration is correct, click OK.

**Een bestaande certificaattoewijzing bewerken**

1. In Administration Console, click Settings > User Management > Configuration.
1. Click Certificate Mapping.
1. Select the certificate mapping to edit and edit its configuration. You can update the regular expression and custom order.
1. To test your changes, click Browse to upload a sample certificate, click Test Certificate, and then click OK.

**Delete a certificate mapping**

1. In administration console, click Settings > User Management > Configuration > Certificate Mapping.
1. Select the check box for the certificate mapping to delete, click Delete, and then click OK.

