---
title: HTML5-voorbeeld van een XDP-formulier genereren
seo-title: HTML5-voorbeeld van een XDP-formulier genereren
description: Het tabblad Voorbeeld-HTML in LiveCycle Designer kan worden gebruikt om een voorbeeld van formulieren weer te geven zoals deze in een browser worden weergegeven.
seo-description: Het tabblad Voorbeeld-HTML in LiveCycle Designer kan worden gebruikt om een voorbeeld van formulieren weer te geven zoals deze in een browser worden weergegeven.
uuid: d004e75d-e569-4e85-8dfa-5c411bc959af
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: author
discoiquuid: c142d7b3-301b-447c-a715-452c905565d1
translation-type: tm+mt
source-git-commit: 801941c060e1a912f3969bca1e89962241e7fbe0
workflow-type: tm+mt
source-wordcount: '808'
ht-degree: 15%

---


# HTML5-voorbeeld van een XDP-formulier genereren {#generate-html-preview-of-an-xdp-form}

Tijdens het ontwerpen van een formulier in AEM Forms Designer kunt u, naast een voorbeeld van de PDF-uitvoering van een formulier, ook een voorbeeld van een HTML5-uitvoering bekijken. Op het tabblad **Voorbeeld-HTML** kunt u een voorbeeld van een formulier bekijken zoals het in een browser wordt weergegeven.

## HTML-voorbeeld voor XDP-formulieren inschakelen in Designer {#html-preview-of-forms-in-forms-designer}

Voer de volgende configuraties uit om Designer in staat te stellen een HTML-voorbeeld van XDP-formulieren te genereren:

* Apache Sling Authentication Service configureren
* Beveiligde modus uitschakelen
* Geef details van de AEM Forms-server op

### Apache Sling Authentication Service configureren {#configure-apache-sling-authentication-service}

1. Ga naar `https://[server]:[port]/system/console/configMgr` AEM Forms die op OSGi lopen of

   `https://[server]:[port]/lc/system/console/configMgr` op AEM Forms die op JEE lopen.

1. Zoek en klik op de configuratie van **Apache Sling Authentication Service** om deze te openen in de bewerkingsmodus.

1. Afhankelijk van of u AEM Forms op OSGi of JEE in werking stelt, voeg het volgende op het gebied van de Vereisten **van de** Authentificatie toe:

   * AEM Forms op JEE

      * -/content/xfaforms
      * -/etc/clientlibs
   * AEM Forms over OSGi

      * -/content/xfaforms
      * -/etc/clientlibs/fd/xfaforms
   >[!NOTE]
   >
   >Kopieer en plak de opgegeven waarde niet in het veld Verificatievereisten omdat de speciale tekens in de waarde hierdoor kunnen beschadigd raken. Typ in plaats daarvan de opgegeven waarde in het veld.

1. Geef een gebruikersnaam en wachtwoord op in respectievelijk **[!UICONTROL Anonymous User Name]** en **[!UICONTROL Anonymous User Password]** velden. De gespecificeerde geloofsbrieven worden gebruikt om anonieme authentificatie te behandelen en toegang tot anonieme gebruikers toe te staan.
1. Klik op **Opslaan** om de configuratie op te slaan.

### Beveiligde modus uitschakelen {#disable-protected-mode}

De [beveiligde modus](/help/forms/using/get-xdp-pdf-documents-aem.md) is standaard ingeschakeld. Houd het ingeschakeld voor de productieomgevingen. U kunt dit uitschakelen voor een ontwikkelomgeving om HTML5 Forms in Designer voor te vertonen. Voer de volgende stappen uit om het uit te schakelen:

1. Meld u als beheerder aan bij de AEM-webconsole.

   * URL voor AEM Forms op OSGi is `https://[server]:[port]/system/console/configMgr`
   * URL voor AEM Forms op JEE is `https://[server]:[port]/lc/system/console/configMgr`

1. Openen **[!UICONTROL Mobile Forms Configurations]** voor bewerken.
1. Schakel de **[!UICONTROL Protected Mode]** optie uit en klik op **[!UICONTROL Save]**.

### Geef details van de AEM Forms-server op {#provide-details-of-aem-forms-server}

1. Ga in Designer naar **Gereedschappen** > **Opties**.
1. Selecteer in het venster Opties de pagina **Serveropties** , geef de volgende gegevens op en klik op **OK**.

   * **Server-URL**: AEM Forms-server-URL.
   * **HTTP-poortnummer**: AEM-serverpoort. De standaardwaarde is 4502.
   * **Context HTML-voorvertoning:** Pad van het profiel voor het weergeven van XFA-formulieren. De volgende standaardprofielen worden gebruikt voor een voorbeeld van het formulier in Designer. U kunt echter ook het pad naar een aangepast profiel opgeven.

      * `/content/xfaforms/profiles/default.html` (AEM Forms over OSGi)
      * `/lc/content/xfaforms/profiles/default.html` (AEM Forms JEE)
   * **Context van Forms Manager:** Contextpad waarop de interface van Forms Manager wordt geïmplementeerd. De standaardwaarden zijn:

      * `/aem/forms` (AEM Forms over OSGi)
      * `/lc/forms` (AEM Forms JEE)
   **Opmerking:** *Controleer of de AEM Forms-server actief is. The HTML preview connects to the CRX server to* generate *a preview.*

   ![AEM Forms Designer-opties ](assets/server_options.png)

   AEM Forms Designer-opties

1. Als u een voorbeeld van een formulier in HTML wilt bekijken, klikt u op het tabblad **Voorbeeld-HTML** .

   >[!NOTE]
   >
   >Als het tabblad HTML-voorbeeld is gesloten, drukt u op F4 om het tabblad Voorbeeld-HTML te openen. U kunt ook Voorvertoning HTML selecteren in het menu Weergave om het tabblad Voorbeeld-HTML te openen.

   >[!NOTE]
   >
   >De HTML-voorvertoning ondersteunt geen PDF-documenten, de HTML-voorvertoning is alleen voor XDP-documenten.

## Een voorbeeld van een formulier weergeven met behulp van voorbeeldgegevens {#to-preview-a-form-using-sample-data}

Designer biedt u de mogelijkheid een voorbeeld van formulieren weer te geven en formulieren te testen met XML-voorbeeldgegevens. Het verdient aanbeveling regelmatig uw formulier te testen met voorbeeldgegevens om ervoor te zorgen dat het formulier correct wordt weergegeven.

Als u geen voorbeeldgegevens hebt, kunt u die laten maken in Designer of deze zelf maken. (Zie [Voorbeeldgegevens automatisch genereren voor een voorbeeldweergave van een formulier](https://help.adobe.com/en_US/AEMForms/6.1/DesignerHelp/WS107c29ade9134a2c136ae6f212a1f379c94-8000.2.html#WS92d06802c76abadb-728f46ac129b395660c-7efe.2) en [Voorbeeldgegevens maken voor een voorbeeldweergave van uw formulier](https://help.adobe.com/en_US/AEMForms/6.1/DesignerHelp/WS107c29ade9134a2c136ae6f212a1f379c94-8000.2.html#WS92d06802c76abadb-728f46ac129b395660c-7eff.2).)

Als u een formulier test met een bron voor voorbeeldgegevens, weer u zeker dat de gegevens en de velden zijn gekoppeld en dat herhalende subformulieren op de verwachte manier worden herhaald. U kunt een evenwichtige formulierindeling maken met voldoende ruimte voor elk object om de samengevoegde gegevens weer te geven.

1. Select **File > Form Properties**.

1. Click the **Preview** tab and, in the Data File box, type the full path to your test data file. U kunt de Browse knoop ook gebruiken om aan het dossier te navigeren.

1. Click **OK**. The next time you preview the form in the **Preview HTML** tab, the data values from the sample XML file will appear in the respective objects.

## Formulieren voorvertonen in een gegevensopslagruimte {#html-preview-of-forms-in-forms-manager}

In AEM Forms kunt u formulieren en documenten voorvertonen in een gegevensopslagruimte. Aan de hand van een voorbeeld kunt u precies zien hoe de formulieren eruitzien en zich gedragen zoals ze worden gebruikt door eindgebruikers.

[**Contact opnemen met ondersteuning **](https://www.adobe.com/account/sign-in.supportportal.html)
