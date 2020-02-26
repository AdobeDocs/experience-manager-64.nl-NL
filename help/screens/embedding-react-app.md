---
title: Een REACT-toepassing insluiten met de AEM SPA Editor en integreren met AEM Screens Analytics
seo-title: Een REACT-toepassing insluiten met de AEM SPA Editor en integreren met AEM Screens Analytics
description: Volg deze pagina om te leren hoe te om een interactieve enige paginatoepassing in te bedden gebruikend REACT (of Hoekig) gebruikend de redacteur van AEM SPA die door bedrijfsberoeps in AEM kan worden gevormd en ook hoe te om uw interactieve toepassing met off-line Analytics van Adobe te integreren.
seo-description: Volg deze pagina om te leren hoe te om een interactieve enige paginatoepassing in te bedden gebruikend REACT (of Hoekig) gebruikend de redacteur van AEM SPA die door bedrijfsberoeps in AEM kan worden gevormd en ook hoe te om uw interactieve toepassing met off-line Analytics van Adobe te integreren.
uuid: 02ae67bb-058a-4aa9-b484-0c60a8d897ad
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.4/SCREENS
content-type: reference
topic-tags: developing
discoiquuid: 70fdeeb8-0c82-44f3-a6fa-ee4dfb32a90b
translation-type: tm+mt
source-git-commit: cdec5b3c57ce1c80c0ed6b5cb7650b52cf9bc340

---


# Een REACT-toepassing insluiten met de AEM SPA Editor en integreren met AEM Screens Analytics{#embedding-a-react-application-using-the-aem-spa-editor-and-integrating-with-aem-screens-analytics}

In deze sectie wordt beschreven hoe u een interactieve toepassing met één pagina insluit met REACT (of Angular) met behulp van de AEM SPA-editor die door zakelijke professionals in AEM kan worden geconfigureerd, en hoe u uw interactieve toepassing integreert met offline Adobe Analytics.

## De AEM SPA Editor gebruiken {#using-the-aem-spa-editor}

Voer de onderstaande stappen uit om de AEM SPA Editor te gebruiken:

1. Clone the AEM SPA Editor repo at [https://github.com/adobe/aem-spa-project-archetype.](https://github.com/adobe/aem-spa-project-archetype)

   >[!NOTE]
   >
   >Dit archetype leidt tot een minimaal project van de Manager van de Ervaring van Adobe als uitgangspunt voor uw eigen projecten van het KUUROORD. De eigenschappen die moeten worden verstrekt wanneer het gebruiken van dit archetype staat toe om als gewenst alle delen van dit project te noemen.

1. Volg de readme instructies om een project tot stand te brengen van de redacteursarchetype van AEM SPA:

   ```
   mvn clean install archetype:update-local-catalog
   mvn archetype:crawl
   
   mvn archetype:generate \
   -DarchetypeCatalog=internal \
   -DarchetypeGroupId=com.adobe.cq.spa.archetypes \
   -DarchetypeArtifactId=aem-spa-project-archetype \
   -DarchetypeVersion=1.0.3-SNAPSHOT \
   ```

   >[!NOTE]
   >
   >Wij gebruiken **GroupId** als ***com.adobe.aem.screens*** en **ArtifactId** als ***Mijn SteekproefSPA*** (die de gebreken is). U kunt zo nodig uw eigen keuze maken.

1. Zodra het project wordt gecreeerd, of gebruik winde of redacteur van uw keus en voer het geproduceerde Geweven project in.
1. Implementeer naar uw lokale AEM-instantie met de opdracht ***mvn clean install -PautoInstallPackage***.

### Inhoud bewerken in de REACT-app {#editing-content-in-the-react-app}

De inhoud in de REACT-app bewerken:

1. Navigeer naar ***http://localhost:4502/editor.html/content/mysamplespa/en/home.html*** (vervang de hostnaam, poort en projectnaam, indien van toepassing).
1. U zou de tekst moeten kunnen uitgeven die in de Hello wereldtoepassing wordt getoond.

### De interactieve REACT-app toevoegen aan AEM-schermen {#adding-the-interactive-react-app-to-aem-screens}

Voer de onderstaande stappen uit om de interactieve REACT-app toe te voegen aan AEM-schermen:

1. Maak een nieuw AEM Screens-project. Raadpleeg [Projecten](/help/screens/creating-a-screens-project.md) maken en beheren voor meer informatie.

   >[!NOTE]
   >
   >Maak een **sequentiekanaal** terwijl u een kanaal maakt in de map **Kanalen** van uw project Screens.
   >
   >Raadpleeg Kanalen [](/help/screens/managing-channels.md) maken en beheren voor meer informatie.

   ![screen_shot_2019-02-15at100330am](assets/screen_shot_2019-02-15at100330am.png)

1. Bewerk een willekeurig volgnummer en sleep en zet een ingesloten pagina-component neer.

   Raadpleeg [Componenten toevoegen aan een kanaal](/help/screens/adding-components-to-a-channel.md) voor meer informatie.

   >[!NOTE]
   >
   >Voeg de gebruikersinteractiegebeurtenis toe wanneer u het kanaal toewijst aan de weergave.

1. Klik op **Bewerken** op de actiebalk om de eigenschappen van het reekskanaal te bewerken.

   ![screen_shot_2019-02-15at100555am](assets/screen_shot_2019-02-15at100555am.png)

1. Sleep de component **Ingesloten pagina** en zet deze neer en selecteer de startpagina onder de mijnvoorbeeldtoepassing, bijvoorbeeld ***/content/mysamplespa/nl/home***.

   ![screen_shot_2019-02-15at101104am](assets/screen_shot_2019-02-15at101104am.png)

1. Registreer een speler tegen dit project en u moet nu de interactieve toepassing kunnen zien die op AEM-schermen wordt uitgevoerd.

   Raadpleeg [Apparaatregistratie](/help/screens/device-registration.md) voor meer informatie over het registreren van een apparaat.

## De SPA integreren met Adobe Analytics met offlinemogelijkheden via AEM-schermen {#integrating-the-spa-with-adobe-analytics-with-offline-capability-through-aem-screens}

Voer de onderstaande stappen uit om de SPA met Adobe Analytics te integreren met offline mogelijkheden via AEM Screens:

1. Adobe-analysemogelijkheden configureren in AEM-schermen.

   Raadpleeg Adobe Analytics [configureren met AEM-schermen](/help/screens/configuring-adobe-analytics-aem-screens.md) voor meer informatie over het uitvoeren van sequencing in Adobe Analytics met AEM Screens en het verzenden van aangepaste gebeurtenissen met behulp van offline Adobe Analytics.

1. Bewerk uw reactie-app in de IDE/editor van uw keuze (met name de tekstcomponent of andere component die u wilt gebruiken om gebeurtenissen uit te zenden).
1. Voeg bij de klikgebeurtenis of andere gebeurtenis die u voor uw component wilt vastleggen de analysegegevens toe met behulp van het standaardgegevensmodel.

   Zie Adobe Analytics [configureren met AEM-](/help/screens/configuring-adobe-analytics-aem-screens.md)schermen voor meer informatie.

1. Roep de API voor analyse van AEM-schermen aan om de gebeurtenis offline op te slaan en in bursts naar Adobe Analytics te verzenden.

   Bijvoorbeeld,

   ```
   handleClick() {
       if ((window.parent) && (window.parent.CQ) && (window.parent.CQ.screens) && (window.parent.CQ.screens.analytics))
       {
           var analyticsEvent = {};
           analyticsEvent['event.type'] = 'play'; // Type of event
    analyticsEvent['event.coll_dts'] = new Date().getTime(); // Start of collecting the event
    analyticsEvent['event.dts_start'] = new Date().getTime(); // Event start
    analyticsEvent['content.type'] = 'Washing machine'; // Mime Type or product category
    analyticsEvent['content.action'] = 'Path to the washing machine asset in AEM'; // Path in AEM to relevant asset
    analyticsEvent['trn.product'] = 'Washing machine Model number'; // Product being explored
    analyticsEvent['trn.amount'] = 1000; // Product pricing or other numeric value or weight
    analyticsEvent['event.dts_end'] = new Date().getTime(); // Event end
    analyticsEvent['event.count'] = 100; // Numeric value that may count a number of clicks or keystrokes or wait time in seconds for example
    analyticsEvent['event.value'] = 'My favorite analytics event';
           analyticsEvent['trn.quantity'] = 10; // Quantity of product selection
    analyticsEvent['event.subtype'] = 'end'; // Event subtype if applicable
    window.parent.CQ.screens.analytics.sendTrackingEvent(analyticsEvent);
       }
   }
   ```

   >[!NOTE]
   >
   >De spelerfirmware voegt automatisch meer informatie over de speler en de bijbehorende runtimeomgeving toe aan de aangepaste analysegegevens die u verzendt. Daarom hoeft u wellicht geen informatie op laag niveau over het besturingssysteem en het apparaat op te nemen, tenzij dit absoluut noodzakelijk is. U hoeft zich alleen te richten op de bedrijfsanalysegegevens.

