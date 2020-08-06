---
title: Problemen met AEM Forms-app oplossen
seo-title: Problemen met AEM Forms-app oplossen
description: 'Meer informatie over algemene problemen met de AEM Forms-app en hoe u deze kunt oplossen. '
seo-description: 'Meer informatie over algemene problemen met de AEM Forms-app en hoe u deze kunt oplossen. '
uuid: a5cc3065-0ebf-48c0-a8fe-f1061632ca90
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-app
discoiquuid: 2f45a965-590b-43b1-95c6-df4b74ad15b9
translation-type: tm+mt
source-git-commit: de440f57091d814a0a7ff48e9a0383c5415a0a5b
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 0%

---


# Problemen met AEM Forms-app oplossen {#troubleshoot-aem-forms-app}

In dit artikel worden de foutberichten beschreven die kunnen worden weergegeven tijdens het ontwikkelen van de AEM Forms-app en de stappen die moeten worden uitgevoerd om deze op te lossen.

De volgende secties in dit artikel zijn beschikbaar:

* [Bijlageverlies voor iOS-gebruikers](/help/forms/using/issues-aem-forms-app.md#attachment-loss-for-ios-users)
* [Concepten van HTML5-formulieren die worden verzonden door gebruikers van werkruimten zijn niet zichtbaar op de portal](/help/forms/using/issues-aem-forms-app.md#html-form-drafts-submitted-by-workspace-users-are-not-visible-on-the-portal)
* [HTML5-formulieren (niet in cache geplaatst) worden niet geladen in AEM Forms-app](/help/forms/using/issues-aem-forms-app.md#html-forms-not-cached-fail-to-load-in-aem-forms-app)
* [AEM Forms synchroniseert niet in Windows](/help/forms/using/issues-aem-forms-app.md#aem-forms-do-not-sync-on-windows)
* [Niet-ondersteunde versie van Gradle](/help/forms/using/issues-aem-forms-app.md#unsupported-version-of-gradle)
* [Compatibiliteitsproblemen met de insteekmodule Gredle en Android Gradle](/help/forms/using/issues-aem-forms-app.md#gradle-and-android-gradle-plug-in-compatibility-issues)

## Bijlageverlies voor iOS-gebruikers {#attachment-loss-for-ios-users}

De AEM Forms-app voor iOS die is geconfigureerd voor synchronisatie met AEM Forms op OSGi ondersteunt alleen bijlagen op veldniveau. Alle bijlagen moeten unieke namen hebben. Als meerdere bijlagen dezelfde naam hebben, wordt slechts één bijlage bewaard en gaan alle andere bijlagen met dezelfde naam verloren. Voer de volgende stappen uit om te voorkomen dat gebruikers op iOS-apparaten gegevens verliezen:

1. Navigeer op de verbonden server naar **Adobe Experience Manager > Gereedschappen > Bewerkingen > Webconsole**.
1. Zoek en klik op **Adaptive Form Configuration Service**.
1. Schakel in het dialoogvenster Adaptieve formulierconfiguratieservice de optie **Bestandsnamen uniek** maken in.

   Als de instelling **Bestandsnamen uniek** maken is uitgeschakeld, ervaren gebruikers gegevensverlies als ze adaptieve formulieren met meerdere bijlagen proberen te verzenden.

1. Click **Save**.

## Concepten van HTML5-formulieren die worden verzonden door gebruikers van werkruimten zijn niet zichtbaar op de portal {#html-form-drafts-submitted-by-workspace-users-are-not-visible-on-the-portal}

Voor HTML5-formulieren die zijn ingeschakeld in de AEM Forms-toepassing met **Opslaan als concept** -HTML-renderprofiel, zijn de opgeslagen concepten niet zichtbaar voor gebruikers in de werkruimte. Voer de volgende stappen uit om opgeslagen concepten van HTML5-formulieren te bekijken die door werkruimtefuncties op de portal zijn verzonden:

1. Open CRXDE en login met beheerdergeloofsbrieven.

   URL: `https://<server>:<port>/lc/crx/de/index.jsp`

1. Klik in het hoofdpad van de CRXDE in de lijst Toegangsbeheer onder Toegangsbeheer op **+**.
1. Klik in het dialoogvenster **Nieuw bericht** toevoegen op de zoekknop voor groep in het veld Principal.
1. Typ in het veld Naam van het dialoogvenster Opdrachtgever selecteren `PERM_WORKSPACE_USER` en klik op **Zoeken**.
1. Selecteer `PERM_WORKSPACE_USER` groep in het dialoogvenster Opdrachtgever selecteren en klik op **OK**.
1. In het dialoogvenster Nieuw bericht toevoegen wordt de `PERM_WORKSPACE_USER` groep geselecteerd in het veld Principal.

   Schakel `jcr:read` rechten voor de gebruikersgroep in.

1. Click **OK**.

## HTML5-formulieren (niet in cache geplaatst) worden niet geladen in AEM Forms-app {#html-forms-not-cached-fail-to-load-in-aem-forms-app}

Wanneer de AEM Forms-app is verbonden met een oudere versie van de AEM Forms-server, kunnen niet in de cache opgeslagen HTML5-formulieren niet worden geladen in de AEM Forms-app.

Voer de volgende stappen uit om het probleem op te lossen:

1. Ga in de ontwerpversie naar **Adobe Experience Manager > Tools > Configure Workspace App Offline Service > Configure Now**.
1. Klik op de pagina **Workspace App Offline Service** op **Handmatige broncache**.

   URL: https://&lt;server>:&lt;port>/libs/fd/workspace-offline/content/config.html

1. Klik op het tabblad **Handmatige broncache** op de knop **+** om een CRX-pad toe te voegen.
1. Typ in het veld **Een nieuwe bron** toevoegen: /etc.clientlibs/fd/xfaforms/I18N/en_US.js en klik op **Toevoegen**.
1. Click **Save**.

## AEM Forms synchroniseert niet in Windows {#aem-forms-do-not-sync-on-windows}

In de AEM Forms App in Windows synchroniseert een formulier niet met de verbonden server als het pad van het formulier of een van de bronnen ervan meer dan 256 tekens bevat.

Wijzig het pad van het formulier en de bijbehorende bronnen om het aantal tekens te beperken tot minder dan 256 tekens.

## Niet-ondersteunde versie van Gradle {#unsupported-version-of-gradle}

**Foutbericht:** Het project gebruikt een niet-ondersteunde versie van Gradle.

Het foutbericht wordt weergegeven wanneer u een AEM Forms-app maakt in Android Studio. Het probleem treedt op als de versie van Gradle die niet wordt ondersteund op het systeem.

**Resolutie:** Klik op **Omloop verhelpen en importeer het project** opnieuw om het probleem op te lossen.

![gradle_unsupported_version](assets/gradle_unsupported_version.png)

## Compatibiliteitsproblemen met de insteekmodule Gredle en Android Gradle {#gradle-and-android-gradle-plug-in-compatibility-issues}

**Foutbericht:** De versies van de insteekmodule Android Gradle en Gradle zijn niet compatibel.

Het foutbericht wordt weergegeven wanneer u de optie APK **** maken selecteert in het menu **Samenstellen** in de gebruikersinterface van Android Studio.

![gradle_plugin_compatibility](assets/gradle_plugin_compatibility.png)

**Resolutie:** Open het bestand **Gradle Scripts** > **gradle-wrapper.properties** en bewerk de eigenschap **distributionUrl** .

De Android Studio-console raadt u bijvoorbeeld aan de verloopversie te verlagen naar 3.5. Bewerk de versie in **distributionUrl** van **het bestand gradle-wrapper.properties** .

Selecteer nogmaals **Build** > **Build APK** om de fout op te lossen en het .apk-bestand te genereren.

![gradle_wrapper_properties](assets/gradle_wrapper_properties.png)

