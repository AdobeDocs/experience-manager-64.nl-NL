---
title: Veelgestelde vragen over AEM-schermen
seo-title: Veelgestelde vragen over AEM-schermen
description: Volg deze pagina om antwoorden te krijgen op veelgestelde vragen over een AEM-schermproject.
seo-description: Volg deze pagina om antwoorden te krijgen op veelgestelde vragen over een AEM-schermproject.
uuid: e394b1bd-1e63-4bd1-b669-923b2a298743
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.4/SCREENS
content-type: reference
topic-tags: troubleshoot
discoiquuid: 558a7c2f-b32e-428e-89f6-123d72ca1108
translation-type: tm+mt
source-git-commit: 9f505017b80fe54e228daea9b248fb0a7db93ca2

---


# Veelgestelde vragen over AEM-schermen {#aem-screens-faqs}

In de volgende sectie worden antwoorden gegeven op een aantal veelgestelde vragen over een AEM Screens-project.

## Kanaalbeheer {#channel-management}

### Wat is het verschil tussen een online en een off-line kanaal? {#what-is-the-difference-between-an-online-and-an-offline-channel}

Met een ***onlinekanaal*** wordt de bijgewerkte inhoud weergegeven in de real-time omgeving, terwijl met een ***offlinekanaal*** de inhoud in de cache wordt weergegeven.

### Hoe maak ik online een kanaal? {#how-do-i-make-a-channel-online}

Selecteer het kanaal en navigeer naar kanaaleigenschappen in de actiebalk. Schakel de modus **Ontwikkelaar in (forceer dat het kanaal online moet zijn)** onder het tabblad **Kanaal** om het kanaal online te maken.

### Wat is het gebruik van het gebied van de Rol van het Kanaal? {#what-is-the-use-of-the-channel-role-field}

De rol van het Kanaal, is de abstractie van het daadwerkelijke kanaal dat wordt in werking gesteld zodat de auteur zich op de generische ervaring kan direct concentreren. U kunt het zien als een soort tag die het kanaal op unieke wijze identificeert in zijn context (weergave of schema).

### Hoe gebeurt de werkelijke kanaalresolutie? {#how-does-actual-channel-resolution-happen}

Voor *statische verwijzingen* volgt de resolutie alleen het opgegeven pad.

Voor *dynamische verwijzingen*, komt de resolutie voor zodra het kanaal aan de vertoning (niet het programma) wordt toegewezen. Het weergavepad wordt de context voor het kanaal en de resolutie gebeurt als volgt (hoogste naar laagste prioriteit):

1. De weergave heeft een onderliggende node die overeenkomt met de kanaalnaam waarnaar wordt verwezen
1. De weergave heeft een knooppunt op hetzelfde niveau dat overeenkomt met de naam van het kanaal waarnaar wordt verwezen
1. De bovenliggende locatie van de weergave heeft een onderliggende node die overeenkomt met de kanaalnaam waarnaar wordt verwezen
1. De bovenliggende hoofdlocatie van de weergave heeft een onderliggende node die overeenkomt met de kanaalnaam waarnaar wordt verwezen

En zo verder, tot u de plaatsingsomslag bereikt en daar tegenhoudt op het ogenblik (zodat kunt u niet naar een kanaal verwijzen dat in de kanaalomslag bijvoorbeeld, slechts kanalen in de plaatssubboom zou zijn).

## Apparaatregistratie {#device-registration}

### Als ik eindpunten zoals verzoeken om apparaat het in- en uitstappen ontdekt, kan ik een groot aantal apparaten in een script opnemen en deze apparaten registreren. Is het mogelijk om deze verzoeken te beveiligen, naast het vergrendelen van dit aan een tak Wi-Fi? {#if-i-discover-endpoints-such-as-requests-for-device-onboarding-and-registration-i-can-script-a-large-number-of-devices-and-register-these-devices-besides-locking-this-to-a-branch-wi-fi-is-it-possible-to-secure-these-requests}

Registratie is momenteel alleen mogelijk op de instantie van de auteur. Hoewel de registratieservice niet is geverifieerd, wordt alleen een apparaat in behandeling in AEM gemaakt en wordt het apparaat niet daadwerkelijk geregistreerd en wordt er geen weergave toegewezen.

Als u een apparaat wilt registreren (wat betekent dat u een gebruiker voor het apparaat maakt in AEM), moet u zich nog steeds verifiëren bij AEM en de registratiewizard momenteel handmatig volgen om de registratie te voltooien. In theorie kan een kwaadwillige gebruiker meerdere apparaten in behandeling maken, maar zonder AEM-aanmelding kunnen geen apparaten worden geregistreerd.

### Is er een manier om HTTP KRIJGT verzoeken in HTTP POST met één of andere vorm van authentificatie om te zetten? {#is-there-a-way-to-transform-http-get-requests-into-http-post-with-some-form-of-authentication}

De registratieaanvraag is een POST-aanvraag.

Het wordt aanbevolen de apparaat-id op te halen uit de sessie in plaats van deze als parameter door te geven. Hierdoor zouden de serverlogboeken, browsercache enzovoort worden opgeschoond. Het is momenteel geen veiligheidskwestie. Houd er rekening mee dat semantisch GET wordt gebruikt wanneer er geen statuswijziging op de server plaatsvindt en POST wordt gebruikt wanneer er een statuswijziging plaatsvindt.

### Is er een manier om een verzoek tot registratie van een apparaat af te wijzen?

Je kunt de registratieaanvragen niet afwijzen. In plaats daarvan verlopen de registratieaanvragen na een time-out die is geconfigureerd in de webconsole van Adobe Experience Manager.

Deze waarde wordt standaard ingesteld op één dag en wordt opgeslagen in een geheugencache.

## Apparaatbewaking en statusrapporten {#device-monitoring-and-health-reports}

### Hoe los ik problemen op als mijn AEM Screens speler leeg scherm toont? {#how-do-i-troubleshoot-if-my-aem-screens-player-shows-blank-screen}

Controleer de volgende mogelijkheden om het probleem met het lege scherm op te lossen:

* AEM kan de offline inhoud niet verduwen
* Kanaal heeft geen inhoud
* Geen van de elementen wordt op het huidige tijdstip weergegeven

### Wat doe ik als de speler van AEM Screens niet kan registreren en zijn staat als Mislukking wordt getoond? {#what-do-i-do-if-aem-screens-player-cannot-register-and-its-state-is-displayed-as-failure}

U moet het filter Apache Sling Reference Filter Allow Empty inschakelen. Dit is vereist voor een optimale werking van het controleprotocol tussen AEM Screens Player en AEM Screens server.

1. Ga naar de webconsoleconfiguratie van **Adobe Experience Manager**
1. Controleer de optie **allow.empty **option.
1. Click **Save**.

### Hoe kan ik problemen oplossen als tijdens het registreren van een AEM Screens speler, het apparaat FAILURE toont en de console logboeken de fout ENAME_NOT_FOUND tonen? {#how-to-troubleshoot-if-while-registering-an-aem-screens-player-device-shows-failure-and-the-console-logs-display-ename-not-found-error}

Dit probleem kan zich voordoen als de speler de DNS van AEM Screens Server niet kan vinden. U kunt proberen gebruikend het IP adres om te verbinden. Om IP van server te verkrijgen, gebruik: *arp &lt;server_dns_name>*.

### ADT AMS het implementeren van een Android Watchdog op alle apparaten? Maakt de Watchdog (Cordova)-plug-in deel uit van de APK? {#does-ams-recommend-implementing-an-android-watchdog-on-all-devices-is-the-watchdog-cordova-plugin-included-as-part-of-the-apk}

Een Android-controlehond die alleen Android-API&#39;s gebruikt, maakt al deel uit van de apk. Er is geen extra software nodig, maar afhankelijk van het apparaat dat u gebruikt, moet u mogelijk de apk opnieuw ondertekenen om systeemrechten te verkrijgen voor een volledige energiecyclus (PowerManager-API). Als de toepassing niet opnieuw wordt ondertekend met de toetsen van de fabrikant, wordt de toepassing afgesloten en opnieuw gestart, maar niet met de energiecyclus.

Raadpleeg [**Android Player **](implementing-android-player.md)implementeren voor meer informatie over het implementeren van Android Player.

### Welke externe bewakings- en waarschuwingsprogramma&#39;s (software) raadt Adobe/AMS aan om elk apparaat te controleren?  {#what-third-party-remote-monitoring-and-alerting-tools-software-does-adobe-ams-recommend-for-monitoring-each-device}

Afhankelijk van wat u uit de controle en het alarm wenst, brengt een nieuwe eigenschap AEM de dienst van Berichten van het Scherm u op de hoogte als een apparaat niet in een tijd heeft gepingeld. De hulpmiddelen van derden zijn afhankelijk van uw besturingssysteem, de mogelijkheden en de specifieke behoeften van de klant.

Raadpleeg de [**AEM Screens Notifications Service **](screens-notifications-service.md)voor meer informatie over waar u de apparaatactiviteiten kunt controleren.

### Gebruikend publiceer apparatentopologie met Slimme Synchronisatie, zijn de apparaten nog direct verbonden met de auteursinstantie voor momentopnamen en hartslagfuncties?

Nee, de apparaten zijn niet rechtstreeks verbonden met de auteur. Ze rapporteren aan de publicatieinstanties en de auteur zal de publicatieinstanties controleren op updates.

## AEM-schermspeler {#aem-screens-player}

### Hoe installeert u ChromeOS-speler als Chrome Browser Plugin? {#how-to-install-chromeos-player-as-chrome-browser-plugin}

De ChromeOS-speler kan als Chrome Browser-insteekmodule worden geïnstalleerd in de modus voor ontwikkelaars zonder dat hiervoor een daadwerkelijk chrome speler-apparaat nodig is. Volg onderstaande stappen voor installatie:

1. Klik [hier](https://download.macromedia.com/screens/) om de nieuwste Chrome Player te downloaden.
1. Pak het uit en sla het op de schijf op.
1. Open Chrome-browser en klik op het menu met drie puntjes en selecteer **Meer gereedschappen** > **Extensies** in de rechterbovenhoek of navigeer rechtstreeks naar ***chrome://extensions***.
1. Schakel de modus **Ontwikkelaar** in de rechterbovenhoek in.
1. Klik op **Niet-verpakt laden **vanuit de linkerbovenhoek en geladen niet-gecomprimeerde Chrome Player.
1. Schakel de insteekmodule **AEM Screens Chrome Player** in als deze beschikbaar is in de lijst met extensies.
1. Open een nieuw tabblad en klik op het pictogram **Apps** linksboven of navigeer rechtstreeks naar ***chrome://apps***.
1. Klik op de insteekmodule **AEM-schermen** om Chrome Player te starten. Standaard wordt de speler gestart in de modus Volledig scherm. Druk op **esc** om de modus Volledig scherm af te sluiten.

### Hoe te om problemen op te lossen als de speler van de Schermen niet door te verifiëren instantie met douanefoutenmanager kan verifiëren? {#how-to-troubleshoot-if-screens-player-is-unable-to-authenticate-through-publish-instance-with-custom-error-handler}

Wanneer de AEM Screens speler begint, doet het een verzoek aan ***/content/screens/svc.ping.json***, wanneer de speler een fout van 404 krijgt. De speler start een verificatieaanvraag om te verifiëren op basis van de publicatie-instantie. Als er een aangepaste fouthandler is in de publicatieversie, moet u de 404-statuscode voor anonieme gebruiker retourneren op ***/content/screens/svc.ping.json***.

### Hoe kunt u instellen dat het scherm van het apparaat blijft ingeschakeld in een Android-speler?

Voer de onderstaande stappen uit om Op een Android-speler actief blijven in te schakelen:

1. Ga naar de instellingen voor de Android-speler -> **Info**
1. Tik 7 keer op het buildnummer om Developer Options in Settings in te schakelen
1. Navigeren naar opties voor **ontwikkelaars**
1. Schakel **Wachten inschakelen in**

### Als er een update van AEM wordt verzonden en de speler offline is, is er dan een nieuw mechanisme dat controleert of het apparaat weer online is om de bijgewerkte inhoud te leveren? En hoe lang probeert het?

Volgende pingel van het apparaat dat binnen komt zal een laatste wijzigingstijd zien die nieuwer is dan wat het heeft en zal deze nieuwe inhoud downloaden.
Het zal eeuwig proberen tot succesvol pingelt.

### Elementen gebruiken {#using-assets}

### Hoe kan ik video&#39;s gebruiken in een AEM-rasterkanaal dat groter is dan 2 GB? {#how-to-use-videos-in-an-aem-screens-channel-larger-than-gb}

Standaard kunt u met de AEM Assets Touch-interface geen elementen uploaden die groter zijn dan 2 GB vanwege een maximale bestandsgrootte in een AEM Screens-kanaal. Nochtans, kunt u deze grens overschrijven door in CRXDE Lite te gaan en een knoop onder de /apps folder te creëren.

Voor meer informatie over het configureren van een hogere bestandsgroottelimiet (bijvoorbeeld 30 GB) in de map */apps* , raadpleegt u *Configuratie om video-elementen te uploaden die groter zijn dan 2 GB* in [Video-elementen](/help/assets/managing-video-assets.md)beheren.

### Algemene tips voor probleemoplossing {#general-troubleshooting}

### Hoe te om Livefyre onbruikbaar te maken om Fout A/P van de Schermen te vermijden?

Om Livefyre onbruikbaar te maken om logboekfouten te vermijden:

**Livefyre-bundel uitschakelen:**

1. Navigeren naar `http://<host>:<port>/system/console/bundles`
1. Zoeken naar de AEM Livefyre-bundel:  *com.adobe.cq.social.cq-social-livefyre*
1. Klik op **Stoppen**.

**Livefyre-poller uitschakelen:**

1. Navigeer in CRXDE Lite naar */etc/importers/polling/livefyre-poller/jcr:content*
1. Een nieuwe eigenschap van het type Boolean toevoegen
1. Ingeschakelde eigenschap **** instellen op **false**
