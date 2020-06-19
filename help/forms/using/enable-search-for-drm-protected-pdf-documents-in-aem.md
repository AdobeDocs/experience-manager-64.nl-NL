---
title: AEM inschakelen om te zoeken naar met documentbeveiliging beveiligde PDF-documenten
seo-title: AEM inschakelen om te zoeken naar met documentbeveiliging beveiligde PDF-documenten
description: 'Leer hoe u native AEM-zoekopdrachten kunt inschakelen om met volledige tekst te zoeken op DRM beveiligde PDF-documenten.  '
seo-description: 'Leer hoe u native AEM-zoekopdrachten kunt inschakelen om met volledige tekst te zoeken op DRM beveiligde PDF-documenten.  '
uuid: c743cda3-252f-4c1f-8d94-e6d26d91dcd8
contentOwner: khsingh
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
geptopics: SG_AEMFORMS/categories/working_with_document_security
discoiquuid: 759068fa-dc1b-4cf5-bc7b-62b8c5464831
translation-type: tm+mt
source-git-commit: a3e7cd30ba6933e6f36734d3b431db41365b6e20
workflow-type: tm+mt
source-wordcount: '685'
ht-degree: 0%

---


# AEM inschakelen om te zoeken naar met documentbeveiliging beveiligde PDF-documenten {#enable-aem-to-search-document-security-protected-pdf-documents}

Bij zoeken in AEM kunt u zoeken naar AEM-elementen en zoeken naar tekst op verschillende veelgebruikte documentindelingen, zoals bestanden met onbewerkte tekst, Microsoft Office-documenten en PDF-documenten. U kunt de oorspronkelijke zoekopdracht ook uitbreiden om volledige tekst te zoeken op [PDF-documenten die zijn beveiligd met de beveiliging](/help/forms/using/admin-help/document-security.md)van AEM-documenten. Voer de volgende stappen uit om AEM in staat te stellen volledige tekst op dergelijke documenten te zoeken:

1. Een veilige verbinding tot stand brengen
1. Een PDF-document indexeren dat met een voorbeeldbeleid is beveiligd

## Vereisten {#prerequisites}

* Als u AEM Forms gebruikt op OSGi:

   * Installeer het pakket [](https://helpx.adobe.com/aem-forms/kb/aem-forms-releases.html) AEM Forms Document Security Index op de AEM Forms-server.
   * Zorg ervoor dat er een AEM Forms op de JEE-server actief is en dat documentbeveiliging is geïnstalleerd op de corresponderende AEM Forms op de JEE-server. Het AEM-formulier op de JEE-server is vereist om het beveiligde document te indexeren.

* Als u alleen AEM Forms op de JEE-server gebruikt, is het indexeerpakket al geïnstalleerd.
* Zorg ervoor dat alle bundels aan de slag zijn. Als alle bundels niet actief zijn, wacht u tot alle bundels actief zijn.

   * Voor AEM Forms op OSGi, zijn de bundels vermeld bij `https://[server]:[port]/system/console/bundles`.
   * Voor AEM Forms op JEE worden de bundels vermeld bij `https://[server]:[port]/[context-path]/system/console/bundles`. Bijvoorbeeld `http://localhost:8080/lc/system/console/bundles`.

* Voeg het pakket *sun.util.agenda* toe aan de allowlist. Voer de volgende stappen uit om het pakket aan de toegestane lijst toe te voegen:

   1. Open AEM-webconsole. De URL is `https://[server]:[port]/system/console/configMgr`.
   1. Zoek en open Configuratie van **Deserialization Firewall**.
   1. Voeg het pakket sun.util.agenda toe aan het veld Voorvoegsels van Whitelisted of Pakket en klik op **Opslaan**.

## Vestig een veilige verbinding tussen AEM Forms JEE en OSGi stapels {#establish-a-secure-connection-between-aem-forms-jee-and-osgi-stacks}

U kunt een van de volgende methoden gebruiken om de beveiligde verbinding tot stand te brengen:

* Adobe LiveCycle Client SDK-bundel configureren met AEM Forms op JEE-beheerdersreferenties
* Adobe LiveCycle Client SDK-bundel configureren met wederzijdse verificatie

### Adobe LiveCycle Client SDK-bundel configureren met AEM Forms op JEE-beheerdersreferenties {#configure-adobe-livecycle-client-sdk-bundle-with-aem-forms-on-jee-admin-credentials}

1. Open AEM-webconsole. De URL is `https://[server]:[port]/system/console/configMgr`.
1. Zoek en open de **Adobe LiveCycle Client SDK-bundel**. Geef waarde op voor de volgende velden:

   * **Server-URL:** Geef HTTPS-URL van AEM Forms op de JEE-server op. Start de server opnieuw op met de parameter -Djavax.net.ssl.trustStore=&lt;path of AEM Forms on JEE keystore file> om communicatie via https mogelijk te maken.
   * **Servicenaam**: Voeg RightsManagementService aan de lijst van de gespecificeerde diensten toe.
   * **Gebruikersnaam:** Geef de gebruikersnaam op van de AEM Forms op de JEE-account die moeten worden gebruikt om aanroepen vanuit de AEM-server te starten. De opgegeven account moet beschikken over machtigingen om documentservices te starten op de AEM Forms op de JEE-server.
   * **Wachtwoord**: Geef het wachtwoord op van de AEM Forms op de JEE-account die in het veld Gebruikersnaam worden vermeld.
   Click **Save**. AEM is ingeschakeld om te zoeken in met documentbeveiliging beveiligde PDF-documenten.

### Adobe LiveCycle Client SDK-bundel configureren met wederzijdse verificatie {#configure-adobe-livecycle-client-sdk-bundle-using-mutual-authentication}

1. Schakel wederzijdse authenticatie in voor AEM Forms op JEE. Voor gedetailleerde informatie, zie [CAC en Wederzijdse Authentificatie](https://helpx.adobe.com/livecycle/kb/cac-mutual-authentication.html).
1. Open AEM-webconsole. De URL is `https://[server]:[port]/system/console/configMgr`.
1. Zoek en open de **Adobe LiveCycle Client SDK** -bundel. Geef waarde op voor de volgende eigenschappen:

   * **Server-URL**: Geef HTTPS-URL van AEM Forms op de JEE-server op. Start de AEM-server opnieuw met de parameter -Djavax.net.ssl.trustStore=&lt;path of AEM Forms on JEE keystore file> om communicatie via https mogelijk te maken.
   * **2-wegs SSL** inschakelen: Schakel de optie 2-wegs SSL inschakelen in.
   * **URL** sleutelarchiefbestand: Geef de URL van het sleutelarchiefbestand op.
   * **TrustStore-bestands-URL**: Geef de URL van het bestand truststore op.
   * **Wachtwoord** sleutelarchief: Geef het wachtwoord voor het sleutelarchiefbestand op.
   * **TrustStorePassword**: Geef het wachtwoord voor het bestand truststore op.
   * **Servicenaam**: Voeg RightsManagementService aan de lijst van de gespecificeerde diensten toe.
   Click **Save**. AEM is ingeschakeld om te zoeken naar met documentbeveiliging beveiligde PDF-documenten

## Een PDF-document indexeren dat met een voorbeeldbeleid is beveiligd {#index-a-sample-policy-protected-pdf-document}

1. Meld u als beheerder aan bij AEM Assets.
1. Maak een map in AEM Digital Asset Manager en upload de PDF-documenten die met een beleid zijn beveiligd naar de nieuwe map.

   U kunt nu met AEM zoeken naar documenten die met een beleid zijn beveiligd.

