---
title: Adobe Analytics configureren met AEM-schermen
seo-title: Adobe Analytics configureren met AEM-schermen
description: 'Volg deze sectie voor meer informatie over het ordenen en verzenden van aangepaste gebeurtenissen met Offline Adobe Analytics '
seo-description: 'Volg deze sectie voor meer informatie over het ordenen en verzenden van aangepaste gebeurtenissen met Offline Adobe Analytics '
uuid: 5c34a68d-6ac6-4713-bcb2-a0ba00977734
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/SCREENS
topic-tags: developing
discoiquuid: 05c5da91-d782-4623-8007-2a217fdf93dd
translation-type: tm+mt
source-git-commit: cdec5b3c57ce1c80c0ed6b5cb7650b52cf9bc340

---


# Adobe Analytics configureren met AEM-schermen{#configuring-adobe-analytics-with-aem-screens}

>[!CAUTION]
>
>Deze AEM-schermfunctionaliteit is alleen beschikbaar als u AEM 6.4.2 Feature Pack 2 en AEM 6.3.3 Feature Pack 4 hebt geïnstalleerd.

>Als u toegang wilt krijgen tot een van deze functiepakketten, neemt u contact op met de ondersteuning van Adobe en vraagt u om toegang. Als u beschikt over de juiste machtigingen, kunt u deze downloaden via Pakket delen.
>
In deze sectie worden de volgende onderwerpen behandeld:

* **Reeksvolgorde in Adobe Analytics met AEM-schermen**
* **Aangepaste gebeurtenissen verzenden met Offline Adobe-analysemogelijkheden**
* **Toewijzing aanvragen**


## Reeksvolgorde in Adobe Analytics met AEM-schermen {#sequencing-in-adobe-analytics-with-aem-screens}

Het ***volgordeproces*** begint met de service voor gegevensopslag waarmee de Adobe Analytics-service wordt geactiveerd. De inhoud van het kanaal verzendt de gebeurtenissen van de Analytics van Adobe met loonlijst, namelijk de gegevens testvangst aan Vensters I/O en de verblijfgebeurtenissen worden teweeggebracht. De gebeurtenissen worden opgeslagen in de index-DB en vervolgens in de objectopslag geplaatst. Gebaseerd op het programma, de beheerderreeksen, knipt het de gegevens van objecten opslag, en brengt het verder over in brokkenopslag. Er wordt geprobeerd maximale hoeveelheid gegevens te verzenden wanneer verbinding wordt gemaakt.

### Scheidingsdiagram {#sequencing-diagram}

In het volgende volgordediagram wordt de integratie van Adobe Analytics met AEM-schermen uitgelegd:

![analytics_chunking](assets/analytics_chunking.png)

## Aangepaste gebeurtenissen verzenden met Offline Adobe-analysemogelijkheden {#sending-custom-events-using-offline-adobe-analytics}

De volgende tabel geeft een overzicht van het standaardgegevensmodel voor gebeurtenissen. Hier worden alle velden weergegeven die naar Adobe Analytics zijn verzonden:

<table> 
 <tbody>
  <tr>
   <td><strong>Sectie</strong></td> 
   <td><strong>Eigenschappenlabel</strong></td> 
   <td><strong>Eigenschapnaam/sleutel</strong></td> 
   <td><strong>Vereist</strong></td> 
   <td><strong>Gegevenstype</strong></td> 
   <td><strong>Type eigenschap</strong><br /> </td> 
   <td><strong>Beschrijving</strong></td> 
  </tr>
  <tr>
   <td><strong><em>Kern/gebeurtenis</em></strong></td> 
   <td>GUID gebeurtenis</td> 
   <td>event.guid</td> 
   <td>aanbevolen</td> 
   <td>string</td> 
   <td>UUID</td> 
   <td>Unieke id die de instantie van een gebeurtenis identificeert</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Datum waarop de gebeurtenis is verzameld</td> 
   <td>event.coll_dts</td> 
   <td>optioneel</td> 
   <td>string</td> 
   <td>timestamp - UTC</td> 
   <td>Tijdstip van verzameling</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Datum van gebeurtenis (begin)</td> 
   <td>event.dts_start</td> 
   <td>aanbevolen</td> 
   <td>string</td> 
   <td>timestamp - UTC</td> 
   <td>Begindatum van gebeurtenis, als u dit NIET opgeeft, wordt de tijd van de gebeurtenis aangenomen op het tijdstip dat deze door de server is ontvangen</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Datum van gebeurtenis (einde)</td> 
   <td>event.dts_end</td> 
   <td>optioneel</td> 
   <td>string</td> 
   <td>timestamp - UTC</td> 
   <td>Einddatum van gebeurtenis</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Workflow</td> 
   <td>event.workflow</td> 
   <td>aanbevolen</td> 
   <td>string</td> 
   <td> </td> 
   <td>Werkstroomnaam (schermen)</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Hoofdcategorie DMe</td> 
   <td>event.category</td> 
   <td>required</td> 
   <td>string</td> 
   <td> </td> 
   <td>Hoofdcategorie (BUREAUBLAD, MOBIEL, WEB, PROCESS, SDK, SERVICE, ECOSYSTEM) - Groepering van gebeurtenistypen - <strong>We sturen Player</strong></td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Subcategorie</td> 
   <td>event.subcategory</td> 
   <td>aanbevolen</td> 
   <td>string</td> 
   <td> </td> 
   <td>Subcategorie - Sectie van een workflow of gebied van een scherm, enz. (Recente bestanden, CC-bestanden, mobiele ontwerpen enzovoort.)</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Type gebeurtenis/actie</td> 
   <td>event.type</td> 
   <td>required</td> 
   <td>string</td> 
   <td> </td> 
   <td>Type gebeurtenis (renderen, klikken, knijpen, zoomen) - Primaire gebruikershandeling</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Subtype</td> 
   <td>event.subtype</td> 
   <td>aanbevolen</td> 
   <td>string</td> 
   <td> </td> 
   <td>Subtype gebeurtenis (maken, bijwerken, verwijderen, publiceren, enz.) - Aanvullende details van de actie van de gebruiker</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Off line</td> 
   <td>event.offline</td> 
   <td>optioneel</td> 
   <td>boolean</td> 
   <td> </td> 
   <td>Gebeurtenis gegenereerd terwijl de handeling offline/online was (true/false)</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Gebruikersagent</td> 
   <td>event.user_agent</td> 
   <td>Aanbevolen (westeigenschappen)</td> 
   <td>string</td> 
   <td> </td> 
   <td>Gebruikersagent</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Taal/landinstelling</td> 
   <td>event.language</td> 
   <td>aanbevolen</td> 
   <td>string</td> 
   <td> </td> 
   <td>De landinstelling van de gebruiker is een tekenreeks die is gebaseerd op de conventies voor taaltags van RFC 3066 (bijvoorbeeld en-US, fr-FR of es-ES)</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Device GUID</td> 
   <td>event.device_guid</td> 
   <td>optioneel</td> 
   <td>string<br /> </td> 
   <td>UUID</td> 
   <td>Identificeert het Apparaat GUID (b.v. machine identiteitskaart of knoeiboel van IP adres + subnet masker + netwerk identiteitskaart + gebruikersagent) - hier zullen wij de gebruikersbenaming van de speler verzenden die bij registratietijd wordt geproduceerd.</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Count</td> 
   <td>event.count</td> 
   <td>optioneel</td> 
   <td>getal</td> 
   <td> </td> 
   <td>Aantal keer dat de gebeurtenis heeft plaatsgevonden - Hier wordt de videoduur verzonden</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Waarde</td> 
   <td>event.value</td> 
   <td>optioneel</td> 
   <td>string</td> 
   <td> </td> 
   <td>Waarde van de gebeurtenis (bijv. instellingen aan/uit)</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Pagename</td> 
   <td>event.pagename</td> 
   <td>vereist voor AA</td> 
   <td>string</td> 
   <td> </td> 
   <td>Ondersteuning voor Adobe Analytics voor aangepaste paginanaam</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>URL</td> 
   <td>event.url</td> 
   <td>optioneel</td> 
   <td>string</td> 
   <td> </td> 
   <td>URL van de webeigenschap of het mobiele schema - moet volledig gekwalificeerde URL omvatten</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Foutcode</td> 
   <td>event.error_code</td> 
   <td> </td> 
   <td>string</td> 
   <td> </td> 
   <td>Foutcode</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Fouttype</td> 
   <td>event.error_type</td> 
   <td> </td> 
   <td>string</td> 
   <td> </td> 
   <td>Type fout</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Beschrijving van fout</td> 
   <td>event.error_description</td> 
   <td> </td> 
   <td>string</td> 
   <td> </td> 
   <td>Beschrijving fout<br /> </td> 
  </tr>
  <tr>
   <td><strong><em>Bron/product van oorsprong</em></strong></td> 
   <td>Naam</td> 
   <td>source.name</td> 
   <td>required</td> 
   <td>string</td> 
   <td> </td> 
   <td>Toepassingsnaam (AEM-schermen)</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Versie</td> 
   <td>source.version</td> 
   <td>required</td> 
   <td>string</td> 
   <td> </td> 
   <td>Firmwareversie</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Platform</td> 
   <td>source.platform</td> 
   <td>required</td> 
   <td>string</td> 
   <td> </td> 
   <td>navigator.platform</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Apparaat</td> 
   <td>source.device</td> 
   <td>vereiste w/uitvoeringen</td> 
   <td>string</td> 
   <td> </td> 
   <td>Naam speler</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Versie besturingssysteem</td> 
   <td>source.os_version</td> 
   <td>vereiste w/uitvoeringen</td> 
   <td>string</td> 
   <td> </td> 
   <td>Versie besturingssysteem</td> 
  </tr>
  <tr>
   <td><strong><em>Inhoud</em></strong></td> 
   <td>Actie</td> 
   <td>content.action</td> 
   <td>required</td> 
   <td>string</td> 
   <td> </td> 
   <td>De URL naar het element inclusief de vertoning die daadwerkelijk is afgespeeld</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>MIME-type</td> 
   <td>content.mimetype</td> 
   <td>optioneel</td> 
   <td>string</td> 
   <td> </td> 
   <td>MIME-type van de inhoud</td> 
  </tr>
  <tr>
   <td><strong><em>Transactie</em></strong></td> 
   <td>Transactienummer</td> 
   <td>trn.number</td> 
   <td>required</td> 
   <td>string</td> 
   <td>UUID</td> 
   <td>Unieke id die bij voorkeur voldoet aan UUID v4</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Productbeschrijving</td> 
   <td>trn.product</td> 
   <td>required</td> 
   <td>string</td> 
   <td> </td> 
   <td>De URL naar het element (behalve uitvoering)</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Aantal</td> 
   <td>trn.quantity</td> 
   <td>required</td> 
   <td>string</td> 
   <td> </td> 
   <td>De afspeelduur</td> 
  </tr>
 </tbody>
</table>

## Toewijzing aanvragen {#request-mapping}

In de volgende tabel worden standaardgegevensmodelvelden voor analyses toegewezen aan AEM-rastergegevens:

<table> 
 <tbody>
  <tr>
   <td><strong>Kenmerk standaardgegevensmodel voor analyse</strong></td> 
   <td><strong>Schermgegevens toegewezen aan standaardgegevensmodel</strong></td> 
   <td><strong>Bevolkt door</strong></td> 
  </tr>
  <tr>
   <td>content.action</td> 
   <td><p>URL van de daadwerkelijke vertoning van het element dat wordt afgespeeld.</p> <p>Een video kan bijvoorbeeld veel uitvoeringen hebben. Dit wijst naar de daadwerkelijk afgespeelde vertoning.</p> </td> 
   <td>Kanaal</td> 
  </tr>
  <tr>
   <td>content.category</td> 
   <td>Weergave gekoppeld aan speler</td> 
   <td>Firmware</td> 
  </tr>
  <tr>
   <td>content.type</td> 
   <td>Type element dat wordt afgespeeld (afbeelding/video)</td> 
   <td>Kanaal</td> 
  </tr>
  <tr>
   <td>event.category</td> 
   <td>Speler</td> 
   <td>Firmware</td> 
  </tr>
  <tr>
   <td>event.colldts</td> 
   <td>Tijdstempel van verzameling van deze gebeurtenis</td> 
   <td>Kanaal</td> 
  </tr>
  <tr>
   <td>event.count</td> 
   <td>Duur van het spel</td> 
   <td>Kanaal</td> 
  </tr>
  <tr>
   <td>event.device_gui</td> 
   <td>De gebruikers-id van de speler in AEM</td> 
   <td>Firmware</td> 
  </tr>
  <tr>
   <td>event.dts_end</td> 
   <td>De tijdstempel van het einde van deze gebeurtenis</td> 
   <td>Kanaal</td> 
  </tr>
  <tr>
   <td>event.dts_start</td> 
   <td>De tijdstempel van het begin van deze gebeurtenis</td> 
   <td>Kanaal</td> 
  </tr>
  <tr>
   <td>event.language</td> 
   <td>De taalinstelling zoals opgegeven door de speler</td> 
   <td>Firmware</td> 
  </tr>
  <tr>
   <td>event.subtype</td> 
   <td>end (het einde van het afspelen van een element wordt aangegeven)</td> 
   <td>Kanaal</td> 
  </tr>
  <tr>
   <td>event.type</td> 
   <td>play (proefdrukken van afspelen wordt geweigerd)</td> 
   <td>Kanaal</td> 
  </tr>
  <tr>
   <td>event.user_agent</td> 
   <td>gebruikersagent van de speler</td> 
   <td>Firmware</td> 
  </tr>
  <tr>
   <td>event.value</td> 
   <td>Een tekenreeks die de duur van het afspelen beschrijft</td> 
   <td>Kanaal</td> 
  </tr>
  <tr>
   <td>event.workflow</td> 
   <td>Schermen</td> 
   <td>Firmware</td> 
  </tr>
  <tr>
   <td>source.device</td> 
   <td>De vriendschappelijke naam van de speler die is opgegeven bij de registratie van de speler</td> 
   <td>Firmware</td> 
  </tr>
  <tr>
   <td>source.name</td> 
   <td>AEM-schermen</td> 
   <td>Firmware</td> 
  </tr>
  <tr>
   <td>source.platform</td> 
   <td>Besturingssysteem van de speler</td> 
   <td>Firmware</td> 
  </tr>
  <tr>
   <td>source.version</td> 
   <td>Firmwareversie</td> 
   <td>Firmware</td> 
  </tr>
  <tr>
   <td>trn.amount</td> 
   <td>0 (voor het bewijs van spel)</td> 
   <td>Kanaal</td> 
  </tr>
  <tr>
   <td>trn.number</td> 
   <td>Unieke id van deze gebeurtenis</td> 
   <td>Firmware</td> 
  </tr>
  <tr>
   <td>trn.product</td> 
   <td>De URL van het oorspronkelijke element (geen uitvoering)</td> 
   <td>Kanaal</td> 
  </tr>
  <tr>
   <td>trn.quantity</td> 
   <td>Duur van het afspelen</td> 
   <td>Kanaal</td> 
  </tr>
 </tbody>
</table>

>[!NOTE]
De velden die zijn gemarkeerd als** In plaats van met een proefdruk te maken, moeten mogelijk worden ingevuld met een aangepast evenement in plaats van met een proefdruk. De speler voegt automatisch alle velden toe die door de firmware zijn ingesteld.

