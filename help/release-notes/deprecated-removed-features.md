---
title: Verouderde en verwijderde functies
seo-title: Verouderde en verwijderde functies
description: Opmerkingen bij de release die specifiek betrekking hebben op vervangen en verwijderde functies in Adobe Experience Manager 6.4.
seo-description: Opmerkingen bij de release die specifiek betrekking hebben op vervangen en verwijderde functies in Adobe Experience Manager 6.4.
uuid: 2619039b-72b4-4c6c-a813-90eed622b423
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4
topic-tags: release-notes
content-type: reference
discoiquuid: 15819d42-4897-40fa-a013-e019d1580fa2
translation-type: tm+mt
source-git-commit: 3316dbc8ef268be2b305d22da9003ae40414b4e1

---


# Verouderde en verwijderde functies {#deprecated-and-removed-features}

Adobe evalueert voortdurend de productmogelijkheden, zodat oudere functies na verloop van tijd opnieuw kunnen worden uitgevonden of vervangen door modernere alternatieven om de algehele waarde van de klant te verbeteren, waarbij altijd zorgvuldig moet worden gekeken naar compatibiliteit met oudere versies.

Om de dreigende verwijdering/vervanging van de mogelijkheden van AEM mee te delen, zijn de volgende regels van toepassing:

1. Aankondiging van afkeuring komt voorop. Hoewel deze afgekeurd zijn, zijn de capaciteiten nog steeds beschikbaar, maar ze zullen niet verder worden uitgebreid.
1. Afgekeurde functies worden ten vroegste bij de volgende grote release verwijderd. De werkelijke streefdatum voor verwijdering wordt bekendgemaakt.

Dit proces biedt klanten minstens één releasecyclus om hun implementatie aan een nieuwe versie of opvolger van een vervangen capaciteit aan te passen, alvorens daadwerkelijke verwijdering.

## Verouderde functies {#deprecated-features}

Deze sectie bevat een lijst met functies en mogelijkheden die zijn gemarkeerd als verouderd in AEM 6.4. In het algemeen worden functies die in een toekomstige release verwijderd moeten worden, eerst vervangen, met een alternatief dat beschikbaar is.

Klanten wordt aangeraden na te gaan of zij in hun huidige implementatie gebruik maken van de functie/mogelijkheid en plannen te maken om hun implementatie te wijzigen en het geboden alternatief te gebruiken.

<table> 
 <tbody>
  <tr>
   <td>Gebied</td> 
   <td>Functie</td> 
   <td>Vervanging</td> 
  </tr>
  <tr>
   <td>UI</td> 
   <td><p>Adobe is niet van plan verdere verbeteringen aan te brengen in de klassieke gebruikersinterface. AEM 6.4 heeft de Klassieke inbegrepen UI, en de klanten die van vroegere versies bevorderen kunnen het blijven gebruiken zoals is. Merk op dat Klassieke UI volledig wordt gesteund terwijl wordt afgekeurd. </p> 
    <ul> 
     <li>/libs/cq/core/content/welcome.html</li> 
     <li>/site-beheerder</li> 
     <li>/damadmin</li> 
     <li>/mcmadmin</li> 
     <li>/inbox</li> 
     <li>/tagging</li> 
     <li>/cf# (Pagina-editor)</li> 
     <li>/libs/launches/content/admin.html</li> 
     <li>/libs/cq/workflow/content/console.html</li> 
    </ul> </td> 
   <td><p>Klanten wordt aangeraden over te schakelen op de nieuwe AEM-interface.</p> <p> </p> </td> 
  </tr>
  <tr>
   <td>Onderdelen</td> 
   <td><p>Adobe is niet van plan verdere verbeteringen aan te brengen in de hieronder vermelde Foundation Components. AEM 6.4 heeft de inbegrepen Componenten van de Stichting, en de klanten die van vroegere versies worden bevorderd kunnen hen blijven gebruiken zoals is. Merk op dat de Componenten van de Stichting volledig gesteund blijven terwijl wordt afgekeurd. </p> 
    <ul> 
     <li>foundation/components/account/accountnaam</li> 
     <li>stichting/componenten/account/handelingen</li> 
     <li>foundation/components/account/wachtwoordreset</li> 
     <li>stichting/componenten/account/aanvraag bevestigen</li> 
     <li>stichting/componenten/adaptieve afbeelding</li> 
     <li>foundation/components/assetsharepage</li> 
     <li>foundation/components/breadcrumb</li> 
     <li>stichting/componenten/formulier/creditcard</li> 
     <li>stichting/componenten/listchildren</li> 
     <li>basis/componenten/aanmelding</li> 
     <li>foundation/components/logo</li> 
     <li>foundation/components/mobilefooter</li> 
     <li>foundation/components/mobileimage</li> 
     <li>stichting/componenten/mobilist</li> 
     <li>stichting/onderdelen/mobiel logo</li> 
     <li>stichting/componenten/mobilereferentie</li> 
     <li>stichting/componenten/mobiletextimage</li> 
     <li>stichting/componenten/mobiletopnav</li> 
     <li>basis/componenten/zoekopdracht</li> 
     <li>stichting/componenten/sitemap</li> 
     <li>basis/componenten/tabel</li> 
     <li>foundation/components/toolbar</li> 
     <li>foundation/components/topnav</li> 
     <li>foundation/components/userinfo</li> 
    </ul> </td> 
   <td>De klanten worden geadviseerd om de Componenten van de Kern voor toekomstige projecten te gebruiken. Bestaande sites hoeven niet te worden gewijzigd.</td> 
  </tr>
  <tr>
   <td>Onderdelen</td> 
   <td><p>Adobe is niet van plan verdere verbeteringen aan te brengen in de hieronder vermelde Foundation Components. AEM 6.4 heeft de inbegrepen Componenten van de Stichting, en de klanten die van vroegere versies worden bevorderd kunnen hen blijven gebruiken zoals is. Merk op dat de Componenten van de Stichting volledig gesteund blijven terwijl wordt afgekeurd.</p> 
    <ul> 
     <li>stichting/componenten/timing</li> 
    </ul> </td> 
   <td>Op het moment van schrijven, is het niet van plan om een vervanging te verstrekken.</td> 
  </tr>
  <tr>
   <td>Portal Director</td> 
   <td><p>De Portal Director is een reeks functies waarmee u AEM-inhoud via Portlet kunt hosten op servers van derden.</p> <p>Adobe is niet van plan om verdere verbeteringen aan de functie Portal Director aan te brengen onder de hieronder vermelde locatie. AEM 6.4 heeft de Portaaldirecteur inbegrepen, en de klanten die van vroegere versies bevorderen kunnen het blijven gebruiken zoals is. Let erop dat Portal Direct volledig wordt ondersteund terwijl het wordt afgekeurd.</p> 
    <ul> 
     <li>/libs/portal/director</li> 
    </ul> </td> 
   <td>Op het moment van schrijven, is het niet van plan om een vervanging te verstrekken.</td> 
  </tr>
  <tr>
   <td>Portlet-component</td> 
   <td><p>Portlet-componenten onder /foundation/components/portlet maken het hosten van JSR Portlets in AEM als onderdelen mogelijk.</p> <p>Adobe is niet van plan de functie Portlet-component verder te verbeteren. AEM 6.4 heeft de Portlet Component inbegrepen, en klanten die van vroegere versies bevorderen kunnen het blijven gebruiken zoals is. Portlet-component wordt nog steeds volledig ondersteund wanneer deze wordt vervangen.</p> </td> 
   <td>Op het moment van schrijven, is het niet van plan om een vervanging te verstrekken.</td> 
  </tr>
  <tr>
   <td>Formulieren</td> 
   <td><p>De ondersteuning voor de Adobe Central Migration Bridge-service is verouderd omdat het Adobe Central-product niet meer wordt ondersteund.</p> </td> 
   <td>Geen vervanging </td> 
  </tr>
    <tr>
   <td>Formulieren</td> 
   <td><p>Vervangen gebruik van JSONObject in Vraag en OperationOptions. De volgende API's zijn afgekeurd:
   <ul><li>setArguments(JSONObject arguments)</li><li>JSONObject getArguments()</li><li>OperationOptions(String operationId, JSONObject arguments</li><li>JSONObject getArguments()</li><li>void setArguments (JSONObject-argumenten)</li></ul>
   </p> </td> 
   <td>De IValueMap-API gebruiken </td> 
  </tr>
  <tr>
   <td>Assets</td> 
   <td><p>Offloading van middelen is vanaf AEM 6.4 afgekeurd</p> </td> 
   <td> </td> 
  </tr>
 </tbody>
</table>

## Verwijderde functies {#removed-features}

Deze sectie bevat een lijst met functies en mogelijkheden die zijn verwijderd uit AEM 6.4. In eerdere versies waren deze mogelijkheden gemarkeerd als afgekeurd.

<table> 
 <tbody>
  <tr>
   <td><strong>Gebied</strong></td> 
   <td><strong>Functie</strong></td> 
   <td><strong>Vervanging</strong></td> 
  </tr>
  <tr>
   <td>Activiteitenkaart voor analyse</td> 
   <td>De versie van de activiteitenkaart die in AEM is opgenomen.</td> 
   <td>Vanwege beveiligingswijzigingen in de API voor Adobe Analytics is het niet langer mogelijk de versie van Activity Map te gebruiken die in AEM is opgenomen.<br><br>De <a href="https://docs.adobe.com/content/help/en/analytics/analyze/activity-map/getting-started/get-started-users/activitymap-install.html">ActivityMap-plug-in van Adobe Analytics</a> moet nu worden gebruikt.</td> 
  </tr>
  <tr>
   <td>Onderdelen</td> 
   <td>Form Captcha<br /> (stichting/componenten/form/captcha)</td> 
   <td>Gebruik in plaats hiervan de component ReCaptcha door Google</td> 
  </tr>
  <tr>
   <td>Onderdelen</td> 
   <td>Presentatie<br /> (basis/componenten/presentatie)</td> 
   <td>Geen vervanging</td> 
  </tr>
  <tr>
   <td>Onderdelen</td> 
   <td>Flash<br /> (basis/componenten/flash)</td> 
   <td>Geen vervanging</td> 
  </tr>
  <tr>
   <td>Onderdelen</td> 
   <td>Ondersteuning voor afspelen van SWF-bestanden in de videocomponent<br /> is verwijderd (basis/componenten/video)</td> 
   <td>Op geen flits gebaseerde video-indelingen gebruiken.</td> 
  </tr>
  <tr>
   <td>Onderdelen</td> 
   <td>Producttabel<br /> (handel/componenten/product_tabel)</td> 
   <td>Geen vervanging</td> 
  </tr>
  <tr>
   <td>Taakbeheer</td> 
   <td>Klassiek UI Taakbeheer<br /> (/libs/cq/taskmanagement/content/taskmanager.html)</td> 
   <td>Vervangen vanaf 6.0. Gebruik het nieuwe taakbeheer dat met werkschemaUI wordt gecombineerd.</td> 
  </tr>
  <tr>
   <td>Workflow</td> 
   <td>Gebruikte meldingsinterface tussen 5.6 en 6.2<br /> (/libs/cq/workflow/content/notifications.html)</td> 
   <td>Workflow Inbox /aem/inbox</td> 
  </tr>
  <tr>
   <td>Formulieren</td> 
   <td>Het exporteren van PDF naar PDF/E-1-indeling met PDF Generator is verwijderd.</td> 
   <td>PDF Generator blijft het exporteren van PDF naar PDF/A-1a/b, PDF/A-2a/b en PDF/A-3a/b-indelingen ondersteunen.</td> 
  </tr>
  <tr>
   <td>Formulieren</td> 
   <td>Ondersteuning voor de standaard AEM Captcha-service in adaptieve formulieren is verwijderd. </td> 
   <td>Gebruik in plaats hiervan ReCaptcha door Google.</td> 
  </tr>
  <tr>
   <td>Formulieren</td> 
   <td>Ondersteuning voor afbeeldingen in documentfragmenten is verwijderd. </td> 
   <td>Interactieve communicatie biedt de mogelijkheid om afbeeldingen rechtstreeks in gedrukte en webkanalen te gebruiken.<br /> </td> 
  </tr>
    <tr>
   <td>Formulieren</td> 
   <td> Geen upgrade meer uitvoeren </td> 
   <td>Er is geen ondersteuning beschikbaar voor het uitvoeren van een upgrade op een andere plaats <br/> </td> 
  </tr>
  <tr>
   <td>Formulieren</td> 
   <td> Sidegrade voor TarMK naar DocumentMK-migraties </td> 
   <td> U kunt de gegevens van een ouder systeem exporteren en vervolgens importeren in een nieuw systeem. Voor gedetailleerde instructies, zie de Vormen van AEM op JEE verbeteringsdocumentatie <br/> </td> 
  </tr>
    <tr>
   <td>Formulieren</td> 
 <td>AEM Forms on JEE 32-bits installatieprogramma is niet beschikbaar.</td> 
   <td>Adobe heeft het verzenden van AEM Forms gestopt in het 32-bits installatieprogramma van JEE. U kunt AEM Forms blijven installeren op JEE met het 64-bits installatieprogramma. </td>  
  </tr>
    <tr>
    <td>Formulieren</td> 
    <td>Verwijderde ondersteuning voor het gebruik van DAM-afbeeldingen in Document Fragment Component.</td> 
    <td> U kunt de component van het Beeld en van het Grafiek in het de drukkanaal van interactieve mededeling gebruiken. Als u de documentfragmentcomponent van het adaptieve document in adaptieve formulieren gebruikt, werkt het niet meer nadat u de upgrade naar AEM 6.4 Forms hebt uitgevoerd. </td>  
  </tr>
  <tr>
   <td>Formulieren</td> 
   <td> De functie Adaptieve documenten is verwijderd</td> 
   <td> Met de functie voor interactieve communicatie kunt u afgedrukte en webgebaseerde communicatie maken. Als u Adaptieve documenten gebruikt, installeert u het compatibiliteitspakket om door te gaan met het gebruik van bestaande adaptieve documenten<br/> </td> 
  </tr>
    <tr>
    <td>Formulieren</td> 
    <td>AEM-formulieren zijn verwijderd op JEE-specifieke bestemmingspagina.</td> 
    <td>AEM Forms on JEE landing page is replace with AEM landing page (/aem/start.html) </td>  
  </tr>
   <tr>
   <td>Formulieren</td> 
   <td>Verwijderde ondersteuning voor standaard Captcha</td> 
   <td>Gebruik de reCAPTCHA-service van Google.</td> 
  </tr>
   <tr>
   <td>Formulieren</td> 
   <td>Verwijderde ondersteuning voor standaard Captcha</td> 
   <td>Gebruik de reCAPTCHA-service van Google.</td> 
  </tr>
  <tr>
   <td>Gemeenschappen</td> 
   <td>Ondersteuning voor Captcha-verificatie is verwijderd.</td> 
   <td>Gebruik aangepaste Captcha-integratie (zoals reCAPTCHA door Google) voor verificatie.</td> 
  </tr>
 </tbody>
</table>

## Vooraankondiging voor volgende release {#pre-announcement-for-next-release}

Deze sectie wordt gebruikt om veranderingen in toekomstige versie vooraf aan te kondigen, die niet verouderd zijn, maar klanten zullen beïnvloeden. Deze worden verstrekt voor planningsdoeleinden.

<table> 
 <tbody>
  <tr>
   <td>Area<br /> </td> 
   <td>Functie<br /> </td> 
   <td>Aankondiging</td> 
  </tr>
  <tr>
   <td>Browserondersteuning</td> 
   <td>Microsoft Internet Explorer</td> 
   <td>AEM 6.4 is de laatste versie die Microsoft Internet Explorer 11 steunt.</td> 
  </tr>
  <tr>
   <td>Stichting</td> 
   <td>UI Framework</td> 
   <td>Adobe heeft in 2019 de Coral UI 2-componenten afgekeurd. AEM 6.4 is volledig gebaseerd op Coral UI 3 (geïntroduceerd met AEM 6.2). Adobe raadt haar klanten en partners die aangepaste UIs met Koraal 2 hebben gebouwd aan om deze aan Koral 3 te verfijnen. Adobe biedt een programma om de dialoogvensters voor koraal 2 om te zetten in koraal 3 - Meer <a href="/help/sites-developing/dialog-conversion.md">informatie</a>lezen.</td> 
  </tr>
 </tbody>
</table>
