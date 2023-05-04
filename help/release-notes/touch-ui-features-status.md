---
title: Status van TouchUI-functie
seo-title: Touch UI Feature Status
description: Opmerkingen bij de release specifiek voor Adobe Experience Manager 6.3 Touch UI.
seo-description: Release notes specific to Adobe Experience Manager 6.3 Touch UI.
uuid: dc335334-6c50-4cee-8a2e-183958742686
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4
topic-tags: release-notes
content-type: reference
discoiquuid: 482b5eb0-1b15-4f10-a9d8-3b72dd74acf8
exl-id: e1422581-143b-4fce-976e-e5aa3360e2d0
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1096'
ht-degree: 0%

---

# Status van TouchUI-functie {#touch-ui-feature-status}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

>[!CAUTION]
>
>Met versie 6.4 van AEM [Klassieke UI is afgekeurd](/help/release-notes/deprecated-removed-features.md). Adobe is niet van plan om verdere verbeteringen aan te brengen in de klassieke gebruikersinterface en gebruikers worden aangemoedigd om de krachtige nieuwe functies die beschikbaar zijn onder de interface met aanraakbediening te benutten.

Vanaf versie 6.0 introduceerde AEM een nieuwe gebruikersinterface die de &#39;touch-UI&#39; (ook wel &#39;touch-interface&#39; genoemd) wordt genoemd en die is uitgelijnd op de Adobe Marketing Cloud en de algemene richtlijnen voor de Adobe-gebruikersinterface. Met bijna functiepartijdigheid bereikt, is dit standaardUI in AEM met de erfenis geworden, Desktop-oriented interface die als &quot;klassieke UI wordt bedoeld.&quot;

Hoewel de meeste mogelijkheden aanwezig zijn in de interface met aanraakbediening, zijn er functies die nog niet zijn voltooid en in toekomstige versies zullen worden toegevoegd.

In de volgende lijst wordt de huidige status van de mogelijkheden weergegeven, zoals geïmplementeerd in AEM 6.4.

Voor aanbevelingen voor klanten die aan AEM 6.4 bevorderen, gelieve te zien [Gebruikersinterface Recommendations voor klanten](/help/sites-deploying/ui-recommendations.md) voor meer informatie.

>[!NOTE]
>
>Op deze pagina wordt alleen de pariteit van functies en klassieke gebruikersinterface besproken.
>
>Mogelijkheden die zijn toegevoegd aan en uniek zijn voor de interface met aanraakbediening en die niet aanwezig zijn in de klassieke interface, worden niet vermeld.

>[!NOTE]
>
>Deze lijst is volledig, maar mag niet als volledig worden beschouwd.

## Legenda {#legend}

* **Voltooid**: De functie is volledig beschikbaar in de interface met aanraakbediening
* **Meestal**: De functie is vooral beschikbaar in de interface met aanraakbediening.
* **Ontbreekt**: De functie is niet aanwezig in de interface met aanraakbediening. De klassieke interface moet hiervoor worden gebruikt.
* **Vervangen**: De functie is vervangen door een nieuwe implementatie die anders werkt.
* **Verwijderd**: De functie bestaat niet meer in de interface met aanraakbediening en wordt niet vervangen.

## Status van onderdeel: Sites-beheerder {#feature-status-sites-admin}

Dit is een lijst met mogelijkheden die de klassieke UI-sitebeheerder ( `/siteadmin`) heeft en de status in de interface met aanraakbediening ( `/sites.html`).

<table> 
 <tbody>
  <tr>
   <td><strong>Functie<br /> </strong></td> 
   <td><strong>Status<br /> </strong></td> 
   <td><strong>Opmerking</strong></td> 
  </tr>
  <tr>
   <td>Navigeren door sitehiërarchie</td> 
   <td>Voltooid<br /> </td> 
   <td>AEM 6.4 <a href="/help/sites-authoring/basic-handling.md#content-tree">inhoudsstructuurweergave</a>.</td> 
  </tr>
  <tr>
   <td>Workflow starten</td> 
   <td>Voltooid<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Nieuwe pagina maken</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Nieuwe site maken</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Nieuwe start maken</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Nieuwe bibliotheek maken <br /> </td> 
   <td>Voltooid<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Map maken</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Publicatiestatus tonen</td> 
   <td>Meestal</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Zoeken</td> 
   <td>Voltooid<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Pagina kopiëren/plakken (dupliceren)</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Pagina('s) verplaatsen</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Pagina('s) publiceren</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Pagina('s) zonder replicatierechten publiceren</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Later publiceren</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Boomstructuur publiceren</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Publicatie van pagina('s) ongedaan maken</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Publicatie van pagina('s) zonder replicatierechten ongedaan maken</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Later verwijderen</td> 
   <td>Voltooid<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Verwijderen</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Vergrendelen/Ontgrendelen</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Eigenschappen weergeven/bewerken</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Machtigingen instellen op pagina('s)</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Versiehistorie</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Versie herstellen</td> 
   <td>Voltooid<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Structuur herstellen en verwijderde pagina's herstellen</td> 
   <td>Ontbreekt</td> 
   <td>Klassieke UI gebruiken.</td> 
  </tr>
  <tr>
   <td>Verschil tonen tussen oude en huidige versie<br /> </td> 
   <td>Voltooid<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Livecopy-acties (uitrollen)</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Zie taalkopieën</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Zoeken en vervangen</td> 
   <td>Ontbreekt<br /> </td> 
   <td>Klassieke UI gebruiken.</td> 
  </tr>
  <tr>
   <td>Notification Inbox (JCR-gebeurtenissen)</td> 
   <td>Ontbreekt</td> 
   <td>Klassieke UI gebruiken. Wordt vervangen door een andere implementatie.</td> 
  </tr>
  <tr>
   <td>Verwijzingen</td> 
   <td>Meestal</td> 
   <td>De weergave van inkomende paginakoppelingen wordt toegevoegd in de release van 2019 van AEM.</td> 
  </tr>
 </tbody>
</table>

## Status van onderdeel: Pagina-editor {#feature-status-page-editor}

Dit is een lijst met mogelijkheden in de klassieke UI Page Editor ( `/cf#`) heeft en de status in de aanraakbediening ( `/editor.html`).

<table> 
 <tbody>
  <tr>
   <td><strong>Functie</strong></td> 
   <td><strong>Status</strong></td> 
   <td><strong>Opmerking</strong></td> 
  </tr>
  <tr>
   <td>Webpagina's bewerken</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Mobiele webpagina's bewerken<br /> </td> 
   <td>Voltooid<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Inhoud bewerken die is geïmporteerd via Design Importer<br /> </td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>E-mails bewerken</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Mobiele apps bewerken</td> 
   <td>Voltooid<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Forms bewerken</td> 
   <td>Voltooid<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Aanbiedingen bewerken</td> 
   <td>Voltooid<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Workflowmodellen bewerken<br /> </td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Code: Bewerken en voorvertonen</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Responsieve voorvertoning<br /> </td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Modus: Ontwerp bewerken</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Modus: Basisstructuur</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Modus: Status van live kopiëren<br /> </td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Annotaties toevoegen</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Eigenschappen bewerken<br /> </td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Uitrolpagina</td> 
   <td>Voltooid<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Workflow starten en weergeven</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Workflowpakket verwerken</td> 
   <td>Meestal</td> 
   <td>Volledig toegankelijk in interface met aanraakbediening. Er wordt nog steeds een lading van meerdere werkstromen weergegeven in een klassieke gebruikersinterface.<br /> </td> 
  </tr>
  <tr>
   <td>Pagina vergrendelen/ontgrendelen</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Pagina publiceren <br /> </td> 
   <td>Voltooid<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Publicatie van pagina ongedaan maken</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Pagina kopiëren</td> 
   <td>Verwijderd<br /> </td> 
   <td>Sitebeheerder gebruiken voor <a href="/help/sites-authoring/managing-pages.md#copying-and-pasting-a-page">pagina's kopiëren</a>.<br /> </td> 
  </tr>
  <tr>
   <td>Pagina verplaatsen</td> 
   <td>Verwijderd</td> 
   <td>Sitebeheerder gebruiken voor <a href="/help/sites-authoring/managing-pages.md#moving-or-renaming-a-page">pagina's verplaatsen</a>.<br /> </td> 
  </tr>
  <tr>
   <td>Pagina verwijderen</td> 
   <td>Verwijderd</td> 
   <td>Sitebeheerder gebruiken voor <a href="/help/sites-authoring/managing-pages.md#deleting-a-page">pagina's verwijderen</a>.<br /> </td> 
  </tr>
  <tr>
   <td>Referenties tonen</td> 
   <td>Verwijderd</td> 
   <td>Sitebeheerder gebruiken voor <a href="/help/sites-authoring/author-environment-tools.md#references">zie de gedetailleerde referentielijst</a>.<br /> </td> 
  </tr>
  <tr>
   <td>Controlelogboek</td> 
   <td>Verwijderd</td> 
   <td>Sitebeheer en <a href="/help/sites-authoring/author-environment-tools.md#events-timeline">open-activiteitspoor</a>.<br /> </td> 
  </tr>
  <tr>
   <td>Versie maken</td> 
   <td>Verwijderd</td> 
   <td>Sitebeheerder gebruiken voor <a href="/help/sites-authoring/working-with-page-versions.md#creating-a-new-version">nieuwe versies maken</a>.<br /> </td> 
  </tr>
  <tr>
   <td>Versie herstellen</td> 
   <td>Verwijderd</td> 
   <td>Sitebeheerder gebruiken voor <a href="/help/sites-authoring/working-with-page-versions.md#reverting-to-a-page-version">versies herstellen</a>.</td> 
  </tr>
  <tr>
   <td>Starten wisselen</td> 
   <td>Verwijderd</td> 
   <td>Sitebeheerder gebruiken voor <a href="/help/sites-authoring/launches-promoting.md">schakelaar tussen lanceringen</a>.<br /> </td> 
  </tr>
  <tr>
   <td>Pagina vertalen</td> 
   <td>Verwijderd</td> 
   <td>Sitebeheerder gebruiken voor <a href="/help/sites-administering/tc-manage.md">pagina toevoegen aan vertaalprojecten</a>.<br /> </td> 
  </tr>
  <tr>
   <td>Tijdlijn verdraaien (kies datum/tijd en blader de site zoals deze vervolgens werd weergegeven)<br /> </td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Machtigingen instellen</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Interface voor clientcontext<br /> </td> 
   <td>Vervangen</td> 
   <td>Gebruik de <a href="/help/sites-authoring/ch-previewing.md">ContextHub</a> UI gaat verder.</td> 
  </tr>
  <tr>
   <td>Inhoudszoeker voor de verschillende mediatypen<br /> </td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Componentlijst</td> 
   <td>Voltooid<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Componenten kopiëren en plakken<br /> </td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Lijst met componenten op het klembord</td> 
   <td>Ontbreekt</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Ongedaan maken/Opnieuw</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Inhoud slepen en neerzetten in tijdelijke aanduiding voor onderdeel</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Inhoud rechtstreeks slepen en neerzetten in tijdelijke aanduiding voor systeem met automatische componentontwerp<br /> </td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
 </tbody>
</table>

## Status van onderdeel: Tekst-, tabel- en afbeeldingseditors {#feature-status-text-table-and-image-editors}

Dit is een lijst van mogelijkheden de klassieke Tekst UI, Lijst, en de Redacteur van het Beeld hebben en de status in touch-Toegelaten UI.

<table> 
 <tbody>
  <tr>
   <td><strong>Functie</strong></td> 
   <td><strong>Status </strong></td> 
   <td><strong>Opmerking<br /> </strong></td> 
  </tr>
  <tr>
   <td>RTF-editor</td> 
   <td>Voltooid</td> 
   <td>Geschikt op locatie, in dialoogvenster en op volledig scherm.</td> 
  </tr>
  <tr>
   <td>RTE-plug-ins in-/uitschakelen</td> 
   <td>Voltooid<br /> </td> 
   <td>Kan worden uitgevoerd met de <a href="/help/sites-authoring/templates.md">Sjablooneditor</a>.</td> 
  </tr>
  <tr>
   <td>RTE gebruiken voor normale tekst</td> 
   <td>Voltooid<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE-plug-in: Koppelingen en anker</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE-plug-in: Tekentoewijzing</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE-plug-in: Kopiëren/plakken</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE-plug-in: Plakken vanuit Microsoft Word<br /> </td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE-plug-in: Zoeken en vervangen</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE-plug-in: Tekstopmaak (vet, ...)</td> 
   <td>Voltooid<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE-plug-in: Subscript en superscript</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE-plug-in: Uitvullen</td> 
   <td>Voltooid<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE-plug-in: Lijsten (opsommingstekens / nummers)</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE-plug-in: Alineaopmaak</td> 
   <td>Voltooid<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE-plug-in: Tekststijlen</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE-plug-in: Broneditor (HTML bewerken)<br /> </td> 
   <td>Voltooid<br /> </td> 
   <td>Alleen beschikbaar in dialoogvenster en volledig scherm.<br /> </td> 
  </tr>
  <tr>
   <td>RTE-plug-in: Spellingcontrole</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE-plug-in: Tabel (ingesloten tabeleditor)</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE-plug-in: Ongedaan maken/Opnieuw<br /> </td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE-plug-in: In-line afbeeldingen toestaan</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Tabeleditor</td> 
   <td>Voltooid</td> 
   <td>Geschikt op locatie, in dialoogvenster en op volledig scherm.<br /> </td> 
  </tr>
  <tr>
   <td>Afbeelding naar tabelcel slepen<br /> </td> 
   <td>Voltooid</td> 
   <td>In regel bruikbaar</td> 
  </tr>
  <tr>
   <td>Afbeeldingseditor<br /> </td> 
   <td>Voltooid</td> 
   <td>Geschikt op locatie, in dialoogvenster en op volledig scherm.<br /> </td> 
  </tr>
  <tr>
   <td>IPE-plug-ins in-/uitschakelen</td> 
   <td>Voltooid</td> 
   <td>Er is nu een interface in het dialoogvenster <a href="/help/sites-authoring/templates.md">Sjablooneditor</a>.</td> 
  </tr>
  <tr>
   <td>IPE-plug-in: Uitsnijden</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>IPE-plug-in: Omdraaien</td> 
   <td>Voltooid<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>IPE-plug-in: Ongedaan maken/Opnieuw</td> 
   <td>Voltooid<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>IPE-plug-in: Afbeeldingskaart</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>IPE-plug-in: Roteren</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>IPE-plug-in: Zoomen</td> 
   <td>Voltooid<br /> </td> 
   <td> </td> 
  </tr>
 </tbody>
</table>

## Status van onderdeel: Gereedschappen {#feature-status-tools}

Dit is een lijst met verschillende gereedschappen die de klassieke UI heeft en de status in de interface met aanraakbediening.

<table> 
 <tbody>
  <tr>
   <td><strong>Functie<br /> </strong></td> 
   <td><strong>Status<br /> </strong></td> 
   <td><strong>Opmerking</strong></td> 
  </tr>
  <tr>
   <td>Taakbeheer</td> 
   <td>Vervangen</td> 
   <td>6.0 geïntroduceerd <a href="/help/sites-authoring/projects.md">Projecten en taken</a>.<br /> </td> 
  </tr>
  <tr>
   <td>Workflow Inbox<br /> </td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Workflow naar paginasjabloonconfiguratie (<code>/etc/workflow/wcm/templates.html</code>)</td> 
   <td>Ontbreekt<br /> </td> 
   <td>Klassieke UI gebruiken.</td> 
  </tr>
  <tr>
   <td>Tagbeheer-interface<br /> </td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>MSM/Blueprint Control Center</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Gebruikersinterface van Blauwdrukbeheer</td> 
   <td>Voltooid</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>UI voor configuratie van uitrol</td> 
   <td>Ontbreekt</td> 
   <td>Klassieke UI gebruiken.</td> 
  </tr>
  <tr>
   <td>Gebruikersinterface, groepen en machtigingen<br /> </td> 
   <td>Meestal voltooid<br /> </td> 
   <td>Gebruik voor geavanceerde bewerkingen met bevoegdheden de klassieke gebruikersinterface.<br /> </td> 
  </tr>
  <tr>
   <td>Purperen (<code>/etc/versioning/purge.html</code>)</td> 
   <td>Ontbreekt</td> 
   <td>Klassieke UI gebruiken.</td> 
  </tr>
  <tr>
   <td>Controle van externe koppelingen (<code>/etc/linkchecker.html</code>)</td> 
   <td>Ontbreekt</td> 
   <td>Klassieke UI gebruiken.<br /> </td> 
  </tr>
  <tr>
   <td>Bulkeditor (<code>/etc/importers/bulkeditor.html</code>)</td> 
   <td>Ontbreekt<br /> </td> 
   <td>Klassieke UI gebruiken.</td> 
  </tr>
 </tbody>
</table>
