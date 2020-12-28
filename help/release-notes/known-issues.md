---
title: Bekende problemen in AEM 6.4
seo-title: Bekende problemen in AEM 6.4
description: Bekende problemen in Adobe Experience Manager 6.4
seo-description: Bekende problemen in Adobe Experience Manager 6.4.
uuid: 1733f15e-9c4f-4db3-98ee-25c2ea606f0d
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4
topic-tags: release-notes
content-type: reference
discoiquuid: 266634ab-21d3-4aac-acfa-b799a7485507
translation-type: tm+mt
source-git-commit: f8ba597c62379ba413309303c2ad066ab7afce1e
workflow-type: tm+mt
source-wordcount: '1034'
ht-degree: 0%

---


# Bekende problemen {#known-issues}

Deze pagina bevat een lijst met bekende problemen die Adobe Experience Manager 6.4 in april 2018 heeft gepubliceerd. Voor meer informatie over bekende kwesties, [contacteer steun](https://helpx.adobe.com/support/experience-manager.html).

## Hybride apparaten {#hybrid-devices}

Hybride apparaten worden niet ondersteund. Er kunnen verschillende problemen optreden wanneer u dergelijke apparaten gebruikt. De volgende voorgestelde procedures helpen veel problemen op te lossen:

Als u Google Chrome als browser gebruikt:

* Typ `chrome://flags/` in de adresbalk en druk op Enter.
* Klik op Enable touch events > Disabled.
* Start de browser opnieuw (alle tabbladen en vensters).

Als u Mozilla Firefox als browser gebruikt:

* Typ `about:config` in de adresbalk en druk op Enter.
* Filter de instellingen naar `dom.w3c`.
* Zorg ervoor dat de instellingen `0` en `false` zijn.
* Start de browser opnieuw.

Als u Microsoft Edge als browser gebruikt:

* Typ `about:flags` in de adresbalk en druk op Return.
* Blader naar de experimentele functies en **[!UICONTROL Touch]**.
* Klik op **[!UICONTROL Enable touch events]**.
* Selecteer **[!UICONTROL Always Off]**.
* Start de browser opnieuw.

## Platform {#platform}

* **Operations-dashboard:** voortgangsbalk wordt niet weergegeven wanneer het back-upbestand de ZIP-extensie mist. (GRANITE-10713)
* **HTML:** JavaUse-object met navolgende witruimte in de pakketdeclaratie bevriest de SightlyJavaCompilerService (GRANITE-20836)
* **Apache Felix/Sling:** Config-bestand is nog steeds aanwezig in de opslagplaats, zelfs na configuration.delete() (GRANITE-20618)
* **Cloud-instellingen:** Console wordt verbroken na het bewerken van de configuratiecontainer (GRANITE-20726)
* **Beveiliging:** IMS-integratie mislukt met aangepast contextpad (GRANITE-20639)
* **Beveiliging:** Verbeter standaard JAAS-rangschikking van SSO, External en Default LoginModules (GRANITE-20590)
* **Gereedschap maken - CRX DE Lite:** Afstand van eigenschappen wordt steeds groter (GRANITE-12040)
* **Tooling - CRX DE Lite:** Kan veranderingen in &quot;Lange&quot;types van Waarde bewaren tenzij u op de Naam van het Bezit tweemaal klikt (GRANITE-12351)

* **Tooling - CRX DE Lite:** ctrl+F onderzoek op open tekstdossiers gaat geplakt op onderzoek RegExp (GRANITE-5996)

* **Gereedschappen - CRX DE Lite:** Node-eigenschap wordt niet weergegeven nadat de naam van het knooppunt is gewijzigd (GRANITE-7160)
* **UI:** Pulldown &quot;more...&quot; niet alle elementen tonen wanneer geopend bij een popover element op IE en Firefox (GRANITE-16326)
* **UI:De tooltip van** Info wordt verborgen wanneer het gebruiken van vaste kolomlay-out met 2 zij-aan-zij kolommen (GRANITE-16869)
* **UI:** Onverwerkte fout wanneer het nadoen als gebruiker die niet bestaat (GRANITE-23228). Oplossing door [een foutenmanager](/help/sites-developing/customizing-errorhandler-pages.md) uit te voeren om foutenmelding aan te passen.

* **OmnZoeken:** zoekopdrachten met backslash-oorzaak (GRANITE-11769)
* **Onderzoek:** Open &quot;de Montages van de Mening&quot;in lijstmening veroorzaken onderzoeksfilter om te veranderen (GRANITE-16524)
* **Omgaan met zoeken:** Onjuiste lijst met kolomconfiguraties die worden weergegeven bij het zoeken naar elementen vanuit sites (GRANITE-16527)

* **Omnissearch:** Left rail predicates getting together with the Omnissearch server request (GRANITE-20524)
* **Omnissearch:** Omnissearch biedt geen ondersteuning voor contextpaden (GRANITE-16044)

## Assets {#assets}

* **Zoeken**: De zoekopdracht retourneert geen resultaten als de zoekreeks begint met een whitespace  [OAK-4786](https://issues.apache.org/jira/browse/OAK-4786)

* **Zoeken**: In de klassieke gebruikersinterface en zijn codes niet zichtbaar in Zoeken (CQ-4235239)

* **UI**: De interface van het element reageert niet meer na Kopiëren-Plakken en Alles selecteren (CQ-4236142)

* **UI**: Kan elementen niet verplaatsen nadat het laden is mislukt (CQ-4236134)

* **Rapporten**: Fout bij het maken van het wijzigingsrapport van bedrijfsmiddelen (CQ-4239744)

* **Rapporten**: De geplande, regelmatige productie van het activarapport mislukt inconsistent (sommige rapporten blijven in de wachtrij) (CQ-4239089)

* **Metagegevens**: Wanneer u een tekstveld met meerdere waarden toevoegt aan het schema voor elementen, werkt de vereiste regel voor het trapsgewijs weergeven van velden niet (CQ-4239333)

* **BrandPortal**: Publiceren naar BrandPortal werkt niet voor verzamelingen (CQ-4238731)

* **Uploaden**: Wanneer u elementen uploadt met speciale tekens in de bestandsnaam, wordt het foutbericht over de niet-toegestane tekens niet voor elk element weergegeven. Hoewel deze alleen voor het eerste element wordt weergegeven, geeft de interface de gebruiker duidelijk aan dat de bestandsnaam van het opgegeven element niet is toegestaan. (CQ-4256876)

## Gemeenschappen {#communities}

* **Moderatie**  - Kan bovenliggende post niet verwijderen als één enkele verwijderingsbewerking uit de bulkmoderatie-UI (CQ-4236797)

* **Console**  - Forgot de verbinding van de Gebruikersnaam of van het Wachtwoord richt zich aan de Login Pagina in plaats van het overeenkomstige wachtwoord herwinningsvorm (CQ-4237682)

## Forms {#forms}

### Installatie en implementatie

* (Alleen AEM Forms JEE) Als het overvullen van JBoss-toepassingsserver tijdens het uitvoeren van Configuration Manager fouten in de aanroep en bootstrap van EJB retourneert. U kunt ze echter negeren. (Ref. CQ-4229793)
* Wanneer AEM Forms wordt gestart, wordt de waarschuwing `SAX Security Manager could not be setup` weergegeven. (CQ-4297403)

### Interactieve communicatie

* De agent UI neemt een tijdje om Interactieve Mededelingen te laden die grafiek of beeldelementen omvatten. (CQ-4236630)
* De indeling voor gegevensweergave in de afdrukvoorvertoning is dd-mm-jjjj, terwijl in de webvoorvertoning `dd-mmm-yy` is (CQ-4237045)
* Het Interactieve Kanaal van het Communicatie Web steunt slechts bevolen en ongeordende lijsten. In fragmenten van het lijstdocument, worden de samengestelde lijst en de inkeping niet gesteund voor het kanaal van het Web van de Interactieve Mededeling. (CQ-4233672)
* De volgende problemen worden waargenomen bij het synchroniseren van webkanalen met het afdrukkanaal:

   * Het webkanaal duurt even om te synchroniseren wanneer u voor het eerst van het afdrukkanaal overschakelt.
   * Het webkanaal synchroniseert niet als het afdrukkanaal een niet-geconfigureerde diagramcomponent bevat. Verwijder de diagramcomponent en synchroniseer opnieuw om het probleem op te lossen.
   * Synchroniseren mislukt soms met de fout &#39;&#39;Er is een fout opgetreden tijdens het synchroniseren van de fout voor Live kopie&#39;. Vernieuw de pagina om het probleem op te lossen.
   * De statische tekst in een layoutfragment wordt vervangen door de naam van een tabelcel als de eerste kolom in de tabel een kopkolom is in de sjabloon voor het afdrukkanaal.
   * Kan geen componenten of elementen toevoegen op een andere locatie dan de onderkant van een webkanaalcommunicatie. Als u het bestand op een andere locatie wilt plaatsen, voegt u een deelvenster onder aan het webkanaal toe en rangschikt u het opnieuw met de inhoudsstructuur.
   * Kan inhoud verplaatsen naar het overerfde doelgebied van een webkanaal zonder de overerving van de live kopie te verwijderen.

(CQ-4239780)

### Gegevensintegratie

* Verificatieconfiguraties voor SOAP-webservices zijn niet zichtbaar en kunnen dus niet worden geconfigureerd in cloudservices. U lost het probleem als volgt op:

   1. Ga in de console van CRXDE Lite naar het volgende knooppunt.\
      /libs/fd/fdm/gui/components/admin/fdmcloudservice/createcloudconfigwizard/cloudservices/\
      wsdlauthenticationsettings/items/fixed columns/items/container/items/wsdl/items/\
      selectAuthentication/items/custom.
   1. Werk de waarde van de eigenschap value bij tot hetzelfde als de waarde van de eigenschap text.
   1. Klik sparen allen om de configuratie te bewaren.

(CQ-4238462)

### Adobe Sign-integratie

* De planner van Adobe Sign werkt niet meer periodiek en daarom worden formulieren in afwachting van het teken niet naar verzending verplaatst. Start om het probleem op te lossen de bundel **Apache Sling Scheduler Support** opnieuw vanaf AEM webconsole op https://[*server*]:[*poort*]/system/console/bundles.

### Adaptieve Forms-authoring

* De component Diagram in adaptieve formulieren neemt meer ruimte in beslag dan normaal.
* Er wordt een uitzondering geretourneerd bij het opslaan van eigenschappen voor adaptieve formulieren, adaptieve formulierfragmenten of interactieve communicatie in de gebruikersinterface van Forms Manager.
* Het opgegeven maximum aantal tekens voor een adaptief tekstvak in een formulier wordt niet ondersteund op Android 6.0 Samsung-apparaten. (Ref. CQ-4235/2005)
