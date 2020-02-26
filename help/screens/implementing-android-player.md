---
title: Android-speler implementeren
seo-title: Implementatie van Android Player
description: 'Volg deze pagina om de implementatie van Android Watchdog te leren, een oplossing om de speler te herstellen van vastlopen. '
seo-description: 'Volg deze pagina om de implementatie van Android Watchdog te leren, een oplossing om de speler te herstellen van vastlopen. '
uuid: 37527a6a-dcc5-4256-abeb-e1f95ff80be4
contentOwner: Jyotika syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/SCREENS
topic-tags: administering
discoiquuid: e6ec1641-4323-4c79-b932-b857feb1df21
translation-type: tm+mt
source-git-commit: 1ebe1e871767605dd4295429c3d0b4de4dd66939

---


# Android-speler implementeren {#implementing-android-player}

Een ***Watchdog*** is een oplossing om de speler te herstellen van crashes. Een toepassing moet zich bij de waakhond dienst registreren en dan periodiek berichten naar de dienst verzenden die het levend is. Als de waakhonddienst niet binnen een bepaalde tijd een bewaarde bericht ontvangt, probeert de dienst om het apparaat voor een schoon terugwinning (als het de voldoende voorrechten heeft) opnieuw op te starten of de toepassing opnieuw te beginnen.

## Android Watchdog implementeren {#implementing-android-watchdog}

Vanwege de architectuur van Android vereist het opnieuw opstarten van het apparaat dat de toepassing systeemrechten heeft. Hiervoor moet u de apk ondertekenen met de ondertekeningssleutels van de fabrikant. Als dit niet het geval is, wordt de speler opnieuw gestart door de controlehond en wordt het apparaat niet opnieuw opgestart.

### Handtekening van Android-apks met behulp van fabriekssleutels {#signage-of-android-apks-using-manufacturer-keys}

Als u toegang wilt tot enkele geprivilegieerde API&#39;s van Android, zoals *PowerManager* of *HDMIControlServices*, moet u de android-apk ondertekenen met de toetsen van de fabrikant.

>[!CAUTION]
>
>Voorwaarden:
>
>U zou Android SDK moeten hebben geïnstalleerd, alvorens u de volgende stappen uitvoert.

Volg de onderstaande stappen om de android-apk te ondertekenen met de toetsen van de fabrikant:

1. Download de app van Google Play of van de downloadpagina voor [AEM Screens Player](https://download.macromedia.com/screens/)
1. Vraag de platformtoetsen aan bij de fabrikant voor een *pk8* - en een *pem* -bestand

1. Zoek het hulpprogramma voor ondertekenaars in android-SDK met Zoeken ~/Library/Android/sdk/build-tools -name &quot;apksigner&quot;
1. &lt;pathto> /apksigner sign —key platform.pk8 —cert platform.x509.pem aemscreensplayer.apk
1. Het pad naar het gereedschap ZIP-uitlijning zoeken in android sdk
1. &lt;pathto> /zipalign -fv 4 aemscreensplayer.apk aemscreensaligensalig.apk
1. Installeer ***aemscreensalign.apk*** met adb-installatie op het apparaat

## Implementatie van Android Watchdog {#android-watchdog-implementation}

De cross-Android-waakhond-service wordt geïmplementeerd als een cordova-plug-in met *AlarmManager*.

In het volgende diagram wordt de implementatie van waakhond-service getoond:

![chlimage_1-43](assets/chlimage_1-43.png)

**1. Initialisatie** Op het moment van initialisatie van de cordova-plug-in worden de machtigingen gecontroleerd om te controleren of we over systeemrechten beschikken en dus of we de machtiging Opnieuw opstarten gebruiken. Als aan deze twee criteria wordt voldaan, wordt een hangende Intent voor Reboot gecreeerd, anders wordt een hangende Intent om de toepassing (die op zijn Activiteit van de Lancering wordt gebaseerd) opnieuw te beginnen gecreeerd.

**2. Alive Timer** A keep live timer wordt gebruikt om een gebeurtenis om de 15 seconden te activeren. In dat geval moet u de bestaande in behandeling zijnde intent annuleren (om de app opnieuw op te starten of te starten) en een nieuwe in behandeling zijnde intent in de toekomst voor dezelfde 60 seconden registreren (in feite om het opnieuw opstarten uit te stellen).

>[!NOTE]
>
>In Android wordt de *AlarmManager* gebruikt om de *pendingIntents* te registreren die kunnen worden uitgevoerd zelfs als de app is vastgelopen en de alarmlevering niet exact is vastgelegd in API 19 (Kitkat). Behoud wat ruimte tussen het interval van de tijdopnemer en het alarm van *AlarmManager* *pendingIntent* .

**3. Toepassing vastloopt** Als de toepassing vastloopt, wordt de in AlarmManager geregistreerde in behandeling zijndeIntent voor Reboot niet meer opnieuw ingesteld en wordt de app opnieuw opgestart of opnieuw opgestart (afhankelijk van de machtigingen die beschikbaar zijn op het moment van initialisatie van de cordova-plug-in).
