---
title: Adobe-campagnecomponenten
seo-title: Adobe-campagnecomponenten
description: Wanneer u integreert met Adobe Campagne, hebt u componenten beschikbaar voor wanneer het werken met nieuwsbrieven en met vormen
seo-description: Wanneer u integreert met Adobe Campagne, hebt u componenten beschikbaar voor wanneer het werken met nieuwsbrieven en met vormen
uuid: d1fb8649-8aae-49a5-8663-1b7cb74ee0e7
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: personalization
discoiquuid: f328cd1e-30a3-42d2-88b7-64455ee9eb1f
translation-type: tm+mt
source-git-commit: 1ebe1e871767605dd4295429c3d0b4de4dd66939

---


# Adobe-campagnecomponenten{#adobe-campaign-components}

Wanneer u integreert met Adobe Campagne, hebt u componenten beschikbaar voor wanneer het werken met nieuwsbrieven en met vormen. Beide worden in dit document beschreven.

## Adobe Campagne Newsletter-componenten {#adobe-campaign-newsletter-components}

Alle componenten van de Campagne volgen de beste praktijken die in [Beste praktijken voor E-mailMalplaatjes](/help/sites-administering/best-practices-for-email-templates.md) worden geschetst en zijn gebaseerd op de de prijsverhogingstaal van Adobe [HTML](https://helpx.adobe.com/experience-manager/htl/using/overview.html).

Wanneer u een nieuwsbrief/e-mail opent die wordt gevormd om met de Campagne van Adobe te integreren, zou u de volgende componenten in de de nieuwsbrief **van de Campagne van** Adobe moeten zien:

* Kop (campagne)
* Afbeelding (campagne)
* Koppeling (campagne)
* Scene7 het Malplaatje van het Beeld (Campagne)
* Gerichte referentie (campagne)
* Tekst en afbeelding (campagne)
* Tekst en persoonlijke voorkeur (campagne)

Een beschrijving van deze componenten vindt u in de volgende sectie.

De componenten zijn als volgt:

![chlimage_1-105](assets/chlimage_1-105.png)

### Kop (campagne) {#heading-campaign}

De kopcomponent kan:

* Geef de naam van de huidige pagina weer door het veld **Titel** leeg te laten.
* Geef een tekst weer die u opgeeft in het veld **Titel** .

U bewerkt de component **Kop (Campagne)** rechtstreeks. Laat leeg als u de paginatitel wilt gebruiken.

![chlimage_1-106](assets/chlimage_1-106.png)

U kunt het volgende configureren:

* **Titel** Als u een andere naam dan de paginatitel wilt gebruiken, voert u deze hier in.

* **Kopniveau (1, 2, 3, 4)** Het kopniveau op basis van de HTML-kopgrootten 1-4.

In het volgende voorbeeld ziet u een component Kop (Campagne) die wordt weergegeven.

![chlimage_1-107](assets/chlimage_1-107.png)

### Afbeelding (campagne) {#image-campaign}

In de afbeeldings-(campagne)component wordt een afbeelding en de bijbehorende tekst weergegeven volgens de opgegeven parameters.

U kunt een afbeelding uploaden, deze vervolgens bewerken en bewerken (bijvoorbeeld uitsnijden, roteren, koppeling/titel/tekst toevoegen).

U kunt een afbeelding van de [Asset Browser](/help/sites-authoring/author-environment-tools.md#assets-browser) rechtstreeks naar de component slepen of het dialoogvenster [Configureren](/help/sites-authoring/editing-content.md#edit-configure-copy-cut-delete-paste)ervan. U kunt een beeld van de Configure dialoog ook uploaden; dit dialoogvenster bevat ook alle definities en bewerkingen van de afbeelding :

![chlimage_1-108](assets/chlimage_1-108.png)

>[!NOTE]
>
>U moet informatie invoeren in het veld **Alt-tekst** , anders kan de afbeelding niet worden opgeslagen.

Nadat de afbeelding is geüpload (en niet eerder) kunt u desgewenst [op plaats bewerken](/help/sites-authoring/editing-content.md#edit-configure-copy-cut-delete-paste) om de afbeelding uit te snijden of te roteren:

![](do-not-localize/chlimage_1-10.png)

>[!NOTE]
>
>De editor op locatie gebruikt de oorspronkelijke grootte en hoogte-breedteverhouding van de afbeelding tijdens het bewerken. U kunt ook de eigenschappen voor hoogte en breedte opgeven. Beperkingen voor grootte en hoogte-breedteverhouding die in de eigenschappen zijn gedefinieerd, worden toegepast wanneer u de bewerkingswijzigingen opslaat.
>
>Afhankelijk van uw exemplaar, kunnen de minimum en maximumbeperkingen ook door het [ontwerp van de pagina](/help/sites-developing/designer.md)worden opgelegd; deze worden ontwikkeld tijdens de uitvoering van het project .

In de modus Volledig scherm zijn verschillende aanvullende opties beschikbaar. bijvoorbeeld toewijzen en zoomen:

![](do-not-localize/chlimage_1-11.png)

Wanneer een beeld wordt geladen, kunt u het volgende vormen:

* **Kaart**

   Als u een afbeelding wilt toewijzen, selecteert u Kaart. U kunt opgeven hoe u de afbeelding met hyperlinks wilt maken (rechthoek, veelhoek enzovoort) en waar het gebied naartoe moet wijzen.

* **Uitsnijden**

   Selecteer Uitsnijden om een afbeelding uit te snijden. Gebruik de muis om de afbeelding uit te snijden.

* **Roteren**

   Selecteer Roteren als u een afbeelding wilt roteren. Herhaal deze bewerking totdat de afbeelding op de gewenste manier is geroteerd.

* **Wissen**

   Verwijder de huidige afbeelding.

* Zoombalk (alleen klassiek)

   Als u wilt in- of uitzoomen op de afbeelding, gebruikt u de schuifbalk onder de afbeelding (boven de knoppen OK en Annuleren)

* **Titel**

   De titel van de afbeelding.

* **Alt-tekst**

   Een alternatieve tekst die kan worden gebruikt bij het maken van toegankelijke inhoud.

* **Koppelen naar**

   Maak een koppeling naar elementen of andere pagina&#39;s binnen uw website.

* **Beschrijving**

   Een beschrijving van de afbeelding.

* **Grootte**

   Hiermee stelt u de hoogte en de breedte van de afbeelding in.

>[!NOTE]
>
>U moet informatie invoeren in het veld **Alt-tekst** op het tabblad **Geavanceerd** , anders kan de afbeelding niet worden opgeslagen en wordt het volgende foutbericht weergegeven:
>
>`Validation failed. Verify the values of the marked fields.`


In het volgende voorbeeld ziet u een component Image (Campaign) die wordt weergegeven.

![chlimage_1-109](assets/chlimage_1-109.png)

### Koppeling (campagne) {#link-campaign}

Met de component Koppeling (Campagne) kunt u een koppeling naar uw nieuwsbrief toevoegen.

U kunt het volgende configureren op de tabbladen **Weergave**, **URL-info** of **Geavanceerd** :

* **Bijschrift koppelen**

   Het bijschrift voor de koppeling. Dit is de tekst die gebruikers zien.

* **Knopinfo Koppeling**

   Hiermee voegt u aanvullende informatie toe over het gebruik van de koppeling.

* **LinkType**

   Selecteer in de vervolgkeuzelijst tussen een **aangepaste URL** en een **adaptief document**. Dit veld is verplicht. Als u Aangepaste URL selecteert, kunt u de URL van de koppeling opgeven. Als u Aangepast document selecteert, kunt u het documentpad opgeven.

* **Aanvullende URL-parameter**

   Voeg aanvullende URL-parameters toe. Klik op Item toevoegen om meerdere items toe te voegen.

>[!NOTE]
>
>U moet informatie invoeren in het veld **Koppelingstype** op het tabblad **URL-informatie** , anders kan de component niet opslaan en wordt het volgende foutbericht weergegeven:
>
>`Validation failed. Verify the values of the marked fields.`


In het volgende voorbeeld ziet u een component Link (Campagne) die wordt weergegeven.

![chlimage_1-110](assets/chlimage_1-110.png)

### Scene7 het Malplaatje van het Beeld (Campagne) {#scene-image-template-campaign}

[Scene7 de Malplaatjes](https://help.adobe.com/en_US/scene7/using/WS60B68844-9054-4099-BF69-3DC998A04D3C.html) van het Beeld zijn gelaagde beelddossiers, waar de inhoud en de eigenschappen voor variabiliteit kunnen worden bepaald. Met de sjablooncomponent **Afbeelding** kunt u Scene7-sjablonen gebruiken in nieuwsbrieven en de waarden van sjabloonparameters wijzigen. Daarnaast kunt u metagegevensvariabelen voor Adobe Campagne binnen de parameters gebruiken, zodat elke gebruiker de afbeelding op een persoonlijke manier ervaart.

![chlimage_1-111](assets/chlimage_1-111.png)

Klik op **Bewerken** om de component te configureren. U kunt de instellingen configureren die in deze sectie worden beschreven. Dit malplaatje van het Beeld Scene7 wordt in detail beschreven in de component [van het Malplaatje van het Beeld](/help/assets/scene7.md#image-template)Scene7.

Bovendien maakt het parameterpaneel een lijst van alle malplaatjeparameters die voor het malplaatje in Scene7 zijn bepaald. Voor elk van deze parameters kunt u de waarde aanpassen, variabelen invoegen of de standaardwaarde ervan herstellen.

![chlimage_1-112](assets/chlimage_1-112.png)

### Gerichte referentie (campagne) {#targeted-reference-campaign}

Met de component Doelverwijzing (Campagne) kunt u een verwijzing naar een doelalinea maken.

In deze component navigeert u naar de doelalinea om deze te selecteren.

Klik op het mappictogram om naar de alinea te navigeren waarnaar u wilt verwijzen. Klik op het vinkje als u klaar bent.

### Tekst en afbeelding (campagne) {#text-image-campaign}

Met de component Tekst en afbeelding (campagne) voegt u een tekstblok en een afbeelding toe.

Wanneer u klikt om de component te vormen, selecteert u Tekst of Beeld.

![chlimage_1-113](assets/chlimage_1-113.png)

Als u **Tekst** selecteert, wordt een inline-editor weergegeven:

![](do-not-localize/chlimage_1-12.png)

Als u **Afbeelding** selecteert, wordt de interne editor voor afbeeldingen weergegeven:

![](do-not-localize/chlimage_1-13.png)

Zie de component [](#image-campaign) Afbeelding (Campagne) voor meer informatie over het werken met afbeeldingen. Zie de component [](#text-personalization-campaign) Tekst en personalisatie (Campagne) voor meer informatie over het werken met tekst.

Net als bij de componenten Text &amp; Personalization (Campaign) en Image (Campaign) kunt u het volgende configureren:

* **Tekst**

   Voer tekst in. Met de werkbalk kunt u de opmaak wijzigen, lijsten maken en koppelingen toevoegen.

* **Afbeelding**

   Sleep een afbeelding vanuit de zoekfunctie voor inhoud of klik om naar een afbeelding te bladeren. Uitsnijden of roteren naar wens.

* **Afbeeldingseigenschappen** (**geavanceerde afbeeldingseigenschappen**)

   Hier kunt u het volgende opgeven:

   * **Titel**

      de titel van het blok; wordt weergegeven door mouseover.

   * **Alt-tekst**

      Alternatieve tekst die moet worden weergegeven als de afbeelding niet kan worden weergegeven.

   * **Koppelen naar**

      Maak een koppeling naar elementen of andere pagina&#39;s binnen uw website.

   * **Beschrijving**

      Een beschrijving van de afbeelding.

   * **Grootte**

      Hiermee stelt u de hoogte en breedte van de afbeelding in.

>[!NOTE]
>
>Het veld **Alt-tekst** op het tabblad **Geavanceerd** is vereist of de component kan niet worden opgeslagen. Het volgende foutbericht wordt weergegeven:
>
>`Validation failed. Verify the values of the marked fields.`


In het volgende voorbeeld ziet u een component Text &amp; Image (Campaign) die wordt weergegeven.

![chlimage_1-114](assets/chlimage_1-114.png)

### Tekst en persoonlijke voorkeur (campagne) {#text-personalization-campaign}

Met de component Tekst en personalisatie (Campagne) kunt u een tekstblok invoeren met een WYSIWYG-editor, met functionaliteit die wordt geboden door de [Rich Text Editor](/help/sites-authoring/rich-text-editor.md). Bovendien kunt u met deze component contextvelden en verpersoonlijkingsblokken gebruiken die beschikbaar zijn in Adobe Campaign. Zie ook [Personalisatie](/help/sites-authoring/campaign.md#inserting-personalization)invoegen.

Met de selectie van pictogrammen kunt u tekst opmaken, inclusief lettertypekenmerken, uitlijning, koppelingen, lijsten en inspringing. De functionaliteit is in wezen het zelfde in [beide UIs](/help/sites-authoring/editing-content.md), hoewel het blik-en-gevoel verschillend is:

![chlimage_1-115](assets/chlimage_1-115.png)

In de Inplace redacteur kunt u tekst toevoegen, de rechtvaardiging veranderen, verbindingen toevoegen en verwijderen, contextgebieden of verpersoonlijkingsblokken toevoegen, en volledig-schermwijze ingaan. Wanneer u klaar bent met het toevoegen van tekst/personalisatie, selecteert u het vinkje om de wijzigingen op te slaan (of x om te annuleren). Zie Bewerken [](/help/sites-authoring/editing-content.md#edit-configure-copy-cut-delete-paste) plaatsen voor meer informatie.

>[!NOTE]
>
>* Welke verpersoonlijkingsgebieden beschikbaar zijn hangt van welke malplaatje van de Campagne van Adobe af uw bulletin met wordt verbonden.
>* Nadat u een persoon van ContextHub selecteert, worden de verpersoonlijkingsgebieden automatisch vervangen door gegevens van het geselecteerde profiel.
>
>
Zie [Persoonlijke instellingen](/help/sites-authoring/campaign.md#inserting-personalization)invoegen.

![chlimage_1-116](assets/chlimage_1-116.png)

>[!NOTE]
>
>Alleen de velden die zijn gedefinieerd in het schema **nms:seedMember** of een van de extensies worden in aanmerking genomen. De kenmerken van de tabellen die gekoppeld zijn aan **nms:seedMember** zijn niet beschikbaar.

## Adobe Campagne-formuliercomponenten {#adobe-campaign-form-components}

Met de componenten van Adobe Campagne kunt u een formulier maken dat gebruikers invullen om zich te abonneren op een nieuwsbrief, zich af te melden bij een nieuwsbrief of hun gebruikersprofielen bij te werken. Zie [Adobe Campagne Forms](/help/sites-authoring/adobe-campaign-forms.md) maken voor meer informatie.

Elk deelveld kan worden gekoppeld aan een databaseveld van Adobe Campagne. De beschikbare velden verschillen afhankelijk van het type gegevens dat ze bevatten, zoals wordt beschreven in de sectie [Componenten en Gegevenstype](#components-and-data-type). Als u het ontvangende schema in de Campagne van Adobe uitbreidt, zullen de nieuwe gebieden in de componenten beschikbaar zijn de waarvan gegevenstypes aanpassen.

Wanneer u een formulier opent dat is geconfigureerd voor integratie met Adobe Campagne, worden de volgende componenten weergegeven in de sectie **Adobe Campagne** :

* Selectievakje (campagne)
* Datumveld (campagne) en Datumveld/HTML5 (campagne)
* Gecodeerde primaire sleutel (campagne)
* Foutweergave (campagne)
* Verborgen afstemmingssleutel (campagne)
* Numeriek veld (campagne)
* Optieveld (campagne)
* Checklist voor abonnementen (campagne)
* Tekstveld (campagne)

De componenten zijn als volgt:

![chlimage_1-117](assets/chlimage_1-117.png)

In deze sectie wordt elke component gedetailleerd beschreven.

### Componenten en gegevenstype {#components-and-data-type}

In de volgende tabel worden de componenten beschreven die beschikbaar zijn om Adobe Campagne-profielgegevens weer te geven en te wijzigen. Elke component kan worden toegewezen aan een Adobe Campagne-profielveld om de waarde ervan weer te geven en het veld bij te werken wanneer het formulier wordt verzonden. De verschillende componenten kunnen slechts aan gebieden van een aangewezen gegevenstype worden aangepast.

<table> 
 <tbody> 
  <tr> 
   <td><p><strong>Component</strong></p> </td> 
   <td><p><strong>Gegevenstype van Adobe Campagne-veld</strong></p> </td> 
   <td><p><strong>Voorbeeldveld</strong></p> </td> 
  </tr> 
  <tr> 
   <td><p>Selectievakje (campagne)</p> </td> 
   <td><p>boolean</p> </td> 
   <td><p>Geen contact meer (via een kanaal)</p> </td> 
  </tr> 
  <tr> 
   <td><p>Datumveld (campagne)</p> <p>Datumveld/HTML 5 (campagne)</p> </td> 
   <td><p>date</p> </td> 
   <td><p>Geboortedatum</p> </td> 
  </tr> 
  <tr> 
   <td><p>Numeriek veld (campagne)</p> </td> 
   <td><p>numeriek (byte, short, long, double)</p> </td> 
   <td><p>Leeftijd</p> </td> 
  </tr> 
  <tr> 
   <td><p>Optieveld (campagne)</p> </td> 
   <td><p>byte met gekoppelde waarden</p> </td> 
   <td><p>Geslacht</p> </td> 
  </tr> 
  <tr> 
   <td><p>Tekstveld (campagne)</p> </td> 
   <td><p>string</p> </td> 
   <td><p>E-mail</p> </td> 
  </tr> 
 </tbody> 
</table>

### Instellingen die door de meeste componenten worden gebruikt {#settings-common-to-most-components}

De componenten van de Campagne van Adobe hebben montages die in alle componenten (behalve de Versleutelde Primaire Sleutel en Verborgen Belangrijkste componenten van de Reconstructie) gemeenschappelijk zijn.

In de meeste componenten, kunt u het volgende vormen:

#### Titel en tekst {#title-and-text}

![chlimage_1-118](assets/chlimage_1-118.png)

* **Titel**

   Als u een andere naam dan de elementnaam wilt gebruiken, voert u deze hier in.

* **Titel verbergen**

   Schakel dit selectievakje in als u de titel niet zichtbaar wilt maken.

* **Beschrijving**

   Voeg een beschrijving aan het gebied toe om meer informatie voor gebruikers te verstrekken.

* **Alleen waarde tonen**

   Hiermee wordt alleen de waarde weergegeven als er een is

#### Adobe-campagne {#adobe-campaign}

U kunt het volgende configureren:

* **Toewijzing**

   Selecteer indien nodig een Adobe Campagne-aanpassingsveld.

* **Afstemmingssleutel**

   Schakel dit selectievakje in als dit veld deel uitmaakt van de afstemmingssleutel.

![chlimage_1-119](assets/chlimage_1-119.png)

#### Restricties {#constraints}

* **Vereist**

   Schakel dit selectievakje in om dit onderdeel verplicht te maken. gebruikers moeten dus een waarde invoeren.

* **Vereist bericht**

   Voeg desgewenst een bericht toe met de mededeling dat het veld verplicht is.

![chlimage_1-120](assets/chlimage_1-120.png)

#### Stijlen {#styling}

* **CSS** Voer de CSS-klassen in die u voor deze component wilt gebruiken.

![chlimage_1-121](assets/chlimage_1-121.png)

### Selectievakje (campagne) {#checkbox-campaign}

Met de component CheckBox (Campagne) kan de gebruiker Adobe Campagne-profielvelden van een Booleaans gegevenstype wijzigen. U kunt bijvoorbeeld een component CheckBox (Campagne) hebben waarmee de ontvanger kan opgeven dat hij of zij niet via een kanaal mag worden benaderd.

U kunt instellingen [configureren die de meeste Adobe Campagne-componenten](#settings-common-to-most-components) gemeen hebben in de component CheckBox (Campagne).

In het volgende voorbeeld wordt een component CheckBox (Campagne) weergegeven.

![chlimage_1-122](assets/chlimage_1-122.png)

### Datumveld (campagne) en Datumveld/HTML 5 (campagne) {#date-field-campaign-and-date-field-html-campaign}

Gebruik het datumveld om ontvangers toe te staan een datum te zoeken. U wilt bijvoorbeeld dat de ontvangers hun geboortedatum opgeven. De datumnotatie komt overeen met de notatie die wordt gebruikt in uw Adobe Campagne-instantie.

Naast de [instellingen die de meeste Adobe Campagne-componenten](#settings-common-to-most-components)gemeen hebben, kunt u het volgende configureren:

* **Restricties - Vervolgkeuzelijst Restrictie**

   U kunt - **niets** of **Datum**- selecteren om de beperking van een datum of geen beperking toe te voegen. Als u datum selecteert, moeten de antwoordgebruikers in het veld een datumnotatie invoeren.

* **Restrictiebericht**

   Bovendien kunt u een beperkingsbericht toevoegen zodat de gebruikers weten hoe te om hun antwoorden behoorlijk te formatteren.
* **Stijl - Breedte** Pas de breedte van het veld aan door op de pictogrammen **+** en **-** te klikken of door een getal in te voeren.

In het volgende voorbeeld wordt een component Date Field (Campaign) weergegeven met de breedte aangepast.

![chlimage_1-123](assets/chlimage_1-123.png)

### Gecodeerde primaire sleutel (campagne) {#encrypted-primary-key-campaign}

Deze component definieert de naam van de URL-parameter die de id van een Adobe Campagne-profiel (**hoofd-id** of **gecodeerde primaire sleutel** in respectievelijk Adobe Campagnestandaard en 6.1) zal bevatten.

Elk formulier dat de gegevens van het Adobe Campagne-profiel weergeeft en wijzigt, **moet** een gecodeerde primaire sleutel bevatten.

U kunt het volgende in de Encrypted Primaire (Campagne) component vormen:

* **Titel en tekst - Naam element**

   Wordt standaard ingesteld op encryptedPK. U hoeft de elementnaam alleen te wijzigen als deze conflicteert met de naam van een ander element op het formulier. Geen twee formuliervelden kunnen dezelfde elementnaam hebben.
* **Adobe-campagne - URL-parameter** Voeg de URL-parameter voor de EPK toe. U kunt bijvoorbeeld de waarde **epk** gebruiken.

In het volgende voorbeeld ziet u een component Encrypted Primary Key (Campaign) die wordt weergegeven.

![chlimage_1-124](assets/chlimage_1-124.png)

### Foutweergave (campagne) {#error-display-campaign}

Met deze component kunt u back-endfouten weergeven. De foutafhandeling van het formulier moet zijn ingesteld op Volgende om de component correct te laten werken.

In het volgende voorbeeld ziet u een component Error Display (Campaign) die wordt weergegeven.

![chlimage_1-125](assets/chlimage_1-125.png)

### Verborgen afstemmingssleutel (campagne) {#hidden-reconciliation-key-campaign}

Met de component Verborgen afstemmingssleutel (Campagne) kunt u verborgen velden toevoegen als onderdeel van de afstemmingssleutel aan een formulier.

U kunt het volgende configureren in de component Verborgen afstemmingssleutel (Campagne):

* **Titel en tekst - Naam element**

   Is standaard ingesteld op reconcilKey. U hoeft de elementnaam alleen te wijzigen als deze conflicteert met de naam van een ander element op het formulier. Geen twee formuliervelden kunnen dezelfde elementnaam hebben.
* **Adobe-campagne - Toewijzing** aan een Adobe Campagne-verpersoonlijkingsveld.

In het volgende voorbeeld ziet u een component Verborgen afstemmingssleutel (Campagne) die wordt weergegeven.

![chlimage_1-126](assets/chlimage_1-126.png)

### Numeriek veld (campagne) {#numeric-field-campaign}

Gebruik het numerieke veld om ontvangers toe te staan getallen in te voeren, bijvoorbeeld hun leeftijd.

Naast de [instellingen die de meeste Adobe Campagne-componenten](#settings-common-to-most-components)gemeen hebben, kunt u het volgende configureren:

* **Restricties - Vervolgkeuzelijst Restrictie**

   U kunt - **niets** of **Numeriek** - selecteren om de beperking van of een aantal of geen beperking toe te voegen. Als u een getal selecteert, moeten de antwoordgebruikers een numeriek getal invoeren in het veld.

* **Restrictiebericht**

   Bovendien kunt u een beperkingsbericht toevoegen zodat de gebruikers weten hoe te om hun antwoorden behoorlijk te formatteren.
* **Stijl - Breedte** Pas de breedte van het veld aan door op de pictogrammen **+** en **-** te klikken of door een getal in te voeren.

In het volgende voorbeeld wordt een component Numeriek veld (Campagne) weergegeven met de geconfigureerde breedte.

![chlimage_1-127](assets/chlimage_1-127.png)

### Optieveld (campagne) {#option-field-campaign}

In deze vervolgkeuzelijst kunt u een optie selecteren. bijvoorbeeld het geslacht of de status van een ontvanger.

U kunt instellingen [configureren die door de meeste Adobe-componenten](#settings-common-to-most-components) Campagne worden gebruikt in de component Optieveld (Campagne). Als u de vervolgkeuzelijst wilt vullen, selecteert u het desbetreffende veld in de aanpassingsvelden van de Adobe Campagne door op het Adobe Campagne-symbool te klikken of hierop te tikken en naar het veld te navigeren.

![chlimage_1-128](assets/chlimage_1-128.png)

In het volgende voorbeeld ziet u een component Option Field (Campaign) die wordt weergegeven.

![chlimage_1-129](assets/chlimage_1-129.png)

### Checklist voor abonnementen (campagne) {#subscriptions-checklist-campaign}

Met de component **Controlelijst voor abonnementen (Campagne)** kunt u de abonnementen wijzigen die aan een Adobe Campagne-profiel zijn gekoppeld.

Wanneer deze component aan een formulier wordt toegevoegd, worden alle beschikbare abonnementen als selectievakjes weergegeven en kan de gebruiker de gewenste abonnementen selecteren. Wanneer gebruikers het formulier verzenden, abonneert deze component de gebruiker op de geselecteerde services of meldt deze de gebruiker af, afhankelijk van het type formulieractie (**Adobe-campagne: Abonneren op Services** of **Adobe-campagne: Abonnement op Services** opzeggen).

>[!NOTE]
>
>De component controleert niet welke services de gebruiker al heeft geabonneerd op of zich niet heeft geabonneerd op.

U kunt instellingen [configureren die gelden voor de meeste Adobe Campagne-componenten](#settings-common-to-most-components) in de component Checklist (Campagne) voor abonnementen. (Er zijn geen Adobe Campagne-configuraties beschikbaar voor deze component.)

In het volgende voorbeeld ziet u een component Subscriptions Checklist (Campaign) die wordt weergegeven.

![chlimage_1-130](assets/chlimage_1-130.png)

### Tekstveld (campagne) {#text-field-campaign}

De component van het Gebied van de Tekst (Campagne) die u tekenreekstype gegevens, zoals een voornaam, een familienaam, een adres, een e-mailadres, enz. laat ingaan.

Naast de [instellingen die de meeste Adobe Campagne-componenten](#settings-common-to-most-components)gemeen hebben, kunt u het volgende configureren:

* **Restricties - Vervolgkeuzelijst Restrictie**

   U kunt - **niets, E-mail,** of **Naam (geen umlauts)**- selecteren om de beperking van of een e-mailadres, naam, of geen beperking toe te voegen. Als u e-mail selecteert, moeten de antwoordgebruikers in het veld een e-mailadres zijn. Als u een naam selecteert, moet deze een naam zijn (umlauts zijn niet toegestaan).

* **Restrictiebericht**

   Bovendien kunt u een beperkingsbericht toevoegen zodat de gebruikers weten hoe te om hun antwoorden behoorlijk te formatteren.

* **Stijlen - breedte**

   Pas de breedte van het veld aan door op de pictogrammen **+** en **-** te klikken of door een getal in te voeren.

In het volgende voorbeeld wordt een component Text Field (Campaign) weergegeven.

![chlimage_1-135](assets/chlimage_1-131.png)

