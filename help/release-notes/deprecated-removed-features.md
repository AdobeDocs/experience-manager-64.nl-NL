---
title: Verouderde en verwijderde functies
description: Opmerkingen bij de release die specifiek betrekking hebben op vervangen en verwijderde functies in Adobe Experience Manager 6.4.
translation-type: tm+mt
source-git-commit: 5b00783e4471a6b142ab17a7bc4a647ab04aec5f
workflow-type: tm+mt
source-wordcount: '1281'
ht-degree: 3%

---


# Vervangen en verwijderde functies {#deprecated-and-removed-features}

Adobe evalueert continu de productfuncties, zodat oudere functies na verloop van tijd kunnen worden bijgewerkt of vervangen door modernere alternatieven om de algehele waarde voor de klant te verbeteren. Hierbij wordt altijd zorgvuldig gekeken naar compatibiliteit met oudere versies.

Om de aanstaande verwijdering/vervanging van AEM mogelijkheden mee te delen, zijn de volgende regels van toepassing:

1. Aankondiging van afkeuring komt voorop. Hoewel deze functie is afgekeurd, zijn de mogelijkheden nog steeds beschikbaar, maar worden ze niet verder uitgebreid.
1. Afgekeurde functies worden ten vroegste bij de volgende grote release verwijderd. De werkelijke streefdatum voor verwijdering wordt bekendgemaakt.

Dit proces biedt klanten minstens één releasecyclus om hun implementatie aan een nieuwe versie of opvolger van een vervangen capaciteit aan te passen, alvorens daadwerkelijke verwijdering.

## Verouderde functies {#deprecated-features}

De onderstaande tabel bevat een lijst met functies en mogelijkheden die zijn gemarkeerd als verouderd in AEM 6.4. In het algemeen worden functies die in een toekomstige versie moeten worden verwijderd, eerst vervangen door een alternatief.

Klanten wordt aangeraden na te gaan of zij in hun huidige implementatie gebruik maken van de functie/mogelijkheid en plannen te maken om hun implementatie te wijzigen en het geboden alternatief te gebruiken.

<!-- TBD: This MD table is a replacement of the HTML table below. However, it generates validation error hence commenting and replacing with inline text. Restore if required. -->

| Gebied | Functie | Vervanging |
|---|---|---|
| UI | Adobe is niet van plan om verdere verhogingen aan Klassieke UI te maken. AEM 6.4 heeft de klassieke gebruikersinterface inbegrepen, en klanten die van vroegere versies bevorderen kunnen het blijven gebruiken zoals is. Merk op dat Klassieke UI volledig wordt gesteund terwijl wordt afgekeurd. <ul> <li>`/libs/cq/core/content/welcome.html` </li> <li> `/siteadmin` </li> <li> `/damadmin` </li> <li> `/mcmadmin` </li> <li> `/inbox` </li> <li> `/tagging` </li> <li> `/cf#` (Pagina-editor) </li><li> `/libs/launches/content/admin.html` </li> <li> `/libs/cq/workflow/content/console.html` </li> </ul> | Klanten wordt aangeraden over te schakelen op de nieuwe AEM-interface. |
| Onderdelen | Adobe is niet van plan om verdere verhogingen aan de hieronder vermelde Componenten van de Stichting te maken. AEM 6.4 heeft inbegrepen de Componenten van de Stichting, en de klanten die van vroegere versies worden bevorderd kunnen hen blijven gebruiken zoals is. Merk op dat de Componenten van de Stichting volledig gesteund blijven terwijl wordt afgekeurd. <ul> <li> foundation/components/account/accountnaam </li> <li> stichting/componenten/account/handelingen </li> <li> foundation/components/account/wachtwoordreset </li> <li> stichting/componenten/account/aanvraag bevestigen </li> <li> stichting/componenten/adaptieve afbeelding </li> <li> foundation/components/assetsharepage </li> <li> foundation/components/breadcrumb </li> <li> stichting/componenten/formulier/creditcard </li> <li> stichting/componenten/listchildren </li> <li> basis/componenten/aanmelding </li> <li> foundation/components/logo </li> <li> foundation/components/mobilefooter </li> <li> foundation/components/mobileimage </li> <li> stichting/componenten/mobilist </li> <li> stichting/onderdelen/mobiel logo </li> <li> stichting/componenten/mobilereferentie </li> <li> stichting/componenten/mobiletextimage </li> <li> stichting/componenten/mobiletopnav </li> <li> basis/componenten/zoekopdracht </li> <li> stichting/componenten/sitemap </li> <li> basis/componenten/tabel </li> <li> foundation/components/toolbar </li> <li> foundation/components/topnav </li> <li> foundation/components/userinfo </li> </ul> | De klanten worden geadviseerd om de Componenten van de Kern voor toekomstige projecten te gebruiken. Bestaande sites hoeven niet te worden gewijzigd. |
| Onderdelen | Adobe is niet van plan om verdere verhogingen aan de hieronder vermelde Componenten van de Stichting te maken. AEM 6.4 heeft inbegrepen de Componenten van de Stichting, en de klanten die van vroegere versies worden bevorderd kunnen hen blijven gebruiken zoals is. Merk op dat de Componenten van de Stichting volledig gesteund blijven terwijl wordt afgekeurd. <ul><li>stichting/componenten/timing</li></ul> | Adobe is niet van plan om een vervangend item aan te bieden. |
| Portal Director | De Portal Director is een reeks functies waarmee u via Portlet AEM inhoud kunt hosten op servers van derden. Adobe is niet van plan om verdere verbeteringen aan te brengen in de functie Portal Director onder de hieronder vermelde locatie. AEM 6.4 heeft het Portaal Director inbegrepen, en klanten die van vroegere versies bevorderen kunnen het blijven gebruiken zoals is. Let erop dat Portal Direct volledig wordt ondersteund terwijl het wordt afgekeurd. <ul><li>/libs/portal/director</li></ul> | Adobe is niet van plan om een vervangend item aan te bieden. |
| Portlet-component | Portlet-componenten onder /foundation/components/portlet maken het hosten van JSR Portlets in AEM als onderdelen mogelijk. Adobe is niet van plan de functie Portlet-component verder te verbeteren. AEM 6.4 is voorzien van de Portlet-component en klanten die een upgrade uitvoeren van eerdere versies, kunnen deze blijven gebruiken zoals ze zijn. Portlet-component wordt nog steeds volledig ondersteund wanneer deze wordt vervangen. | Adobe is niet van plan om een vervangend item aan te bieden. |
| Forms | Ondersteuning voor de Adobe Central Migration Bridge-service is afgekeurd omdat het Adobe Central-product niet meer wordt ondersteund. | Geen vervanging |
| Forms | Vervangen gebruik van JSONObject in Vraag en OperationOptions. De volgende API&#39;s zijn afgekeurd: <ul><li>`setArguments(JSONObject arguments)`</li><li> `JSONObject getArguments()`</li><li>`OperationOptions(String operationId, JSONObject arguments)`</li><li>`JSONObject getArguments()`</li><li> `void setArguments(JSONObject arguments)`</li></ul> | De `IValueMap`-API gebruiken |
| Forms | Vervangen Central Migration Bridge-service. | Er wordt geen vervanging aangeboden. |
| Assets | Offloading van activa is vanaf AEM 6.4 afgekeurd. |  |
| Ontwikkelaars | Lodash-/onderstrepingsclientbibliotheek. Adobe is niet van plan om de Lodash/underscore-clientbibliotheek die als onderdeel van de distributie wordt verzonden, verder te onderhouden en bij te werken (Quickstart) | Adobe raadt klanten aan die nog steeds Lodash/onderstrepingsteken voor hun code nodig hebben om het in hun basis van de projectcode toe te voegen. |

<!-- Original HTML table that came from helpx during migration.

<table> 
 <tbody>
  <tr>
   <td>Area</td> 
   <td>Feature</td> 
   <td>Replacement</td> 
  </tr>
  <tr>
   <td>UI</td> 
   <td><p>Adobe does not plan to make further enhancements to the Classic UI. AEM 6.4 has the Classic UI included, and customers upgrading from earlier releases can keep using it as is. Note that Classic UI remains fully supported while being deprecated. </p> 
    <ul> 
     <li>/libs/cq/core/content/welcome.html</li> 
     <li>/siteadmin</li> 
     <li>/damadmin</li> 
     <li>/mcmadmin</li> 
     <li>/inbox</li> 
     <li>/tagging</li> 
     <li>/cf# (Page Editor)</li> 
     <li>/libs/launches/content/admin.html</li> 
     <li>/libs/cq/workflow/content/console.html</li> 
    </ul> </td> 
   <td><p>Customers are advised to switch to use the new AEM UI.</p> <p> </p> </td> 
  </tr>
  <tr>
   <td>Components</td> 
   <td><p>Adobe does not plan to make further enhancements to the Foundation Components listed below. AEM 6.4 has the Foundation Components included, and customers upgrading from earlier releases can keep using them as is. Note that Foundation Components remain fully supported while being deprecated. </p> 
    <ul> 
     <li>foundation/components/account/accountname</li> 
     <li>foundation/components/account/actions</li> 
     <li>foundation/components/account/passwordreset</li> 
     <li>foundation/components/account/requestconfirmation</li> 
     <li>foundation/components/adaptiveimage</li> 
     <li>foundation/components/assetsharepage</li> 
     <li>foundation/components/breadcrumb</li> 
     <li>foundation/components/form/creditcard</li> 
     <li>foundation/components/listchildren</li> 
     <li>foundation/components/login</li> 
     <li>foundation/components/logo</li> 
     <li>foundation/components/mobilefooter</li> 
     <li>foundation/components/mobileimage</li> 
     <li>foundation/components/mobilelist</li> 
     <li>foundation/components/mobilelogo</li> 
     <li>foundation/components/mobilereference</li> 
     <li>foundation/components/mobiletextimage</li> 
     <li>foundation/components/mobiletopnav</li> 
     <li>foundation/components/search</li> 
     <li>foundation/components/sitemap</li> 
     <li>foundation/components/table</li> 
     <li>foundation/components/toolbar</li> 
     <li>foundation/components/topnav</li> 
     <li>foundation/components/userinfo</li> 
    </ul> </td> 
   <td>Customers are advised to use the Core Components for future projects. Existing sites do not need to be changed.</td> 
  </tr>
  <tr>
   <td>Components</td> 
   <td><p>Adobe does not plan to make further enhancements to the Foundation Components listed below. AEM 6.4 has the Foundation Components included, and customers upgrading from earlier releases can keep using them as is. Note that Foundation Components remain fully supported while being deprecated.</p> 
    <ul> 
     <li>foundation/components/timing</li> 
    </ul> </td> 
   <td>At the point of writing, it's not planned to provide a replacement.</td> 
  </tr>
  <tr>
   <td>Portal Director</td> 
   <td><p>The Portal Director is a set of features, that enables the hosting of AEM content via Portlet in 3rd party servers.</p> <p>Adobe does not plan to make further enhancements to the Portal Director feature under the location listed below. AEM 6.4 has the Portal Director included, and customers upgrading from earlier releases can keep using it as is. Note that Portal Direct remains fully supported while being deprecated.</p> 
    <ul> 
     <li>/libs/portal/director</li> 
    </ul> </td> 
   <td>At the point of writing, it's not planned to provide a replacement.</td> 
  </tr>
  <tr>
   <td>Portlet Component</td> 
   <td><p>Portlet Components under /foundation/components/portlet enables the hosting of JSR Portlets in AEM as components.</p> <p>Adobe does not plan to make further enhancements to the Portlet Component feature. AEM 6.4 has the Portlet Component included, and customers upgrading from earlier releases can keep using it as is. Note that Portlet Component remains fully supported while being deprecated.</p> </td> 
   <td>At the point of writing, it's not planned to provide a replacement.</td> 
  </tr>
  <tr>
   <td>Forms</td> 
   <td><p>Support for Adobe Central Migration Bridge service has been deprecated as Adobe Central product is no longer supported.</p> </td> 
   <td>No replacement </td> 
  </tr>
    <tr>
   <td>Forms</td> 
   <td><p>Deprecated use of JSONObject in Query and OperationOptions. The following APIs are deprecated:
   <ul><li>setArguments(JSONObject arguments)</li><li>JSONObject getArguments()</li><li>OperationOptions(String operationId, JSONObject arguments</li><li>JSONObject getArguments()</li><li>void setArguments(JSONObject arguments)</li></ul>
   </p> </td> 
   <td>Use the IValueMap API </td> 
  </tr>
  <tr>
   <td>Forms</td> 
   <td><p>Deprecated Central Migration Bridge service</p> </td> 
   <td> No replacement </td> 
  </tr>
  <tr>
   <td>Assets</td> 
   <td><p>Assets Offloading has been deprecated starting with AEM 6.4</p> </td> 
   <td> </td> 
  </tr>
 </tbody>
</table>
-->

## Verwijderde functies {#removed-features}

In de onderstaande tabel staan de functies en mogelijkheden die uit AEM 6.4 zijn verwijderd. In eerdere versies waren deze mogelijkheden gemarkeerd als
afgekeurd.

| Gebied | Functie | Vervanging |
|---|---|---|
| Activity Map Analytics | De versie van de Activity Map die in AEM is opgenomen. | Vanwege beveiligingswijzigingen in de Adobe Analytics API is het niet langer mogelijk om de versie van de Activity Map te gebruiken die in AEM is opgenomen. De [ActivityMap-plug-in van Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/activity-map/getting-started/get-started-users/activitymap-install.html) moet nu worden gebruikt. |
| Components-Forms | Form Captcha (stichting/componenten/form/captcha) | Gebruik in plaats hiervan de component ReCaptcha door Google |
| Onderdelen | Presentatie (basis/componenten/presentatie) | Geen vervanging |
| Onderdelen | Flash (stichting/componenten/flits) | Geen vervanging |
| Onderdelen | Ondersteuning voor afspelen van SWF-bestanden in de video-component is verwijderd (basis/componenten/video) | Op geen flits gebaseerde video-indelingen gebruiken. |
| Onderdelen | Producttabel (handel/componenten/product_tabel) | Geen vervanging |
| Taakbeheer | Klassiek UI Taakbeheer (/libs/cq/taskmanagement/content/taskmanager.html) | Vervangen vanaf 6.0. Gebruik het nieuwe taakbeheer dat met werkschemaUI wordt gecombineerd. |
| Workflow | Gebruikte meldingsinterface tussen 5.6 en 6.2 (/libs/cq/workflow/content/notifications.html) | Workflow Inbox /aem/inbox |
| Forms | Export PDF naar PDF/E-1-indeling met PDF Generator is verwijderd. | PDF Generator blijft het exporteren van PDF naar PDF/A-1a/b, PDF/A-2a/b en PDF/A-3a/b-indelingen ondersteunen. |
| Forms | Ondersteuning voor afbeeldingen in documentfragmenten is verwijderd. | Interactieve communicatie biedt de mogelijkheid om afbeeldingen rechtstreeks in gedrukte en webkanalen te gebruiken. |
| Forms | Geen upgrade meer uitvoeren | Er is geen ondersteuning beschikbaar voor het uitvoeren van een upgrade op een andere plaats |
| Forms | Sidegrade voor TarMK naar DocumentMK-migraties | U kunt de gegevens van een ouder systeem exporteren en vervolgens importeren in een nieuw systeem. Raadpleeg de documentatie bij AEM Forms on JEE-upgrades voor gedetailleerde instructies |
| Forms | AEM Forms op JEE 32-bits installatieprogramma niet beschikbaar. | Adobe heeft de verzending van AEM Forms via het 32-bits installatieprogramma van JEE gestopt. U kunt AEM Forms in JEE blijven installeren met het 64-bits installatieprogramma. |
| Forms | Verwijderde ondersteuning voor het gebruik van DAM-afbeeldingen in Document Fragment Component. | U kunt de component van het Beeld en van het Grafiek in het de drukkanaal van interactieve mededeling gebruiken. Als u de documentfragmentcomponent van het adaptieve document in adaptieve formulieren gebruikt, werkt het niet meer nadat u de upgrade naar AEM 6.4 Forms hebt uitgevoerd. |
| Forms | De functie Adaptieve documenten is verwijderd | Met de functie voor interactieve communicatie kunt u afgedrukte en webgebaseerde communicatie maken. Als u Adaptieve documenten gebruikt, installeert u het compatibiliteitspakket om door te gaan met het gebruik van bestaande adaptieve documenten |
| Forms | AEM Forms is verwijderd op JEE-specifieke bestemmingspagina. | AEM Forms op JEE-landingspagina wordt vervangen door AEM landingspagina (/aem/start.html) |
| Forms | Verwijderde ondersteuning voor standaard Captcha | Gebruik de reCAPTCHA-service van Google. |
| Forms | Ondersteuning voor Flash-velden in AEM Designer is verwijderd. AEM Designer kan Flash-velden die in een formulier worden gebruikt, niet bewerken. | U kunt dergelijke formulieren bewerken met AEM Designer dat is uitgebracht voor een vorige versie. |
| Gemeenschappen | Ondersteuning voor Captcha-verificatie is verwijderd. | Gebruik aangepaste Captcha-integratie (zoals reCAPTCHA door Google) voor verificatie. |

## Vooraankondiging voor volgende release {#pre-announcement-for-next-release}

De onderstaande tabel bevat een lijst met wijzigingen voor toekomstige release die niet zijn verouderd, maar gevolgen kunnen hebben voor klanten. Deze worden verstrekt voor planningsdoeleinden.

| Gebied | Functie | Aankondiging |
|---|---|---|
| Browserondersteuning | Microsoft Internet Explorer | AEM 6.4 is de laatste versie die Microsoft Internet Explorer 11 ondersteunt. |
| Stichting | UI Framework | Adobe heeft in 2019 de Coral UI 2-componenten afgekeurd. AEM 6.4 is volledig gebaseerd op Coral UI 3 (geïntroduceerd met AEM 6.2). Adobe raadt zijn klanten en partners aan die douane UIs met Koraal 2 hebben gebouwd om deze aan Koraal 3 te refactored. Adobe biedt een gereedschap om de dialoogvensters Koraal 2 om te zetten in koraal 3 - [Meer informatie.](/help/sites-developing/modernization-tools.md) |
