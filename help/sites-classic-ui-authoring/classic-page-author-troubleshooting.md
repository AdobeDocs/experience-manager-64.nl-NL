---
title: Problemen met AEM bij ontwerpen oplossen
seo-title: Problemen met AEM bij ontwerpen oplossen
description: De volgende sectie behandelt sommige kwesties die u wanneer het gebruiken van AEM zou kunnen ontmoeten, samen met suggesties op hoe te om hen problemen op te lossen.
seo-description: De volgende sectie behandelt sommige kwesties die u wanneer het gebruiken van AEM zou kunnen ontmoeten, samen met suggesties op hoe te om hen problemen op te lossen.
uuid: eb95e5ba-1eed-4ffb-80c1-9b8468820c22
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: page-authoring
content-type: reference
discoiquuid: 9b492b17-9029-46ae-9dc0-bb21e6b484df
translation-type: tm+mt
source-git-commit: 02aee2202a570320cd7eb40c2e566d886af4e163
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 6%

---


# Problemen met AEM bij ontwerpen oplossen{#troubleshooting-aem-when-authoring}

De volgende sectie behandelt sommige kwesties die u wanneer het gebruiken van AEM zou kunnen ontmoeten, samen met suggesties op hoe te om hen problemen op te lossen.

>[!NOTE]
>
>Wanneer het ervaren van problemen het ook de moeite waard is de lijst van [Bekende Kwesties](/help/release-notes/known-issues.md) voor uw instantie (versie en de dienstpakken) te controleren.

>[!NOTE]
>
>De gebruikers die beheerdervoorrechten hebben, en die problemen met AEM willen oplossen, kunnen de het oplossen van problemenmethodes gebruiken die in de AEM van het Oplossen van [problemen (voor Beheerders)](/help/sites-administering/troubleshoot.md)worden beschreven. Als u niet voldoende rechten hebt, raadpleegt u uw systeembeheerder over AEM voor probleemoplossing.

## Oude paginaversie blijft op gepubliceerde site staan {#old-page-version-still-on-published-site}

* **Probleem**:

   * U hebt wijzigingen aangebracht in een pagina en de pagina gekopieerd naar de publicatiesite, maar de *oude* versie van de pagina wordt nog wel weergegeven op de publicatiesite.

* **Reden**:

   * Dit kan verscheidene oorzaken hebben, meestal het geheime voorgeheugen (of uw lokale browser of de Verzender), hoewel het soms een kwestie met de replicatierij kan zijn.

* **Oplossingen**:

   * Hier zijn verschillende mogelijkheden:
   * Controleer of de pagina correct is gerepliceerd. Controleer de paginastatus en, indien nodig, de status van de replicatiewachtrij.
   * Wis de cache in uw lokale browser en open de pagina opnieuw.
   * Toevoegen `?` aan het einde van de pagina-URL. Bijvoorbeeld:

      `http://localhost:4502/sites.html/content?`

      Hiermee wordt de pagina rechtstreeks bij AEM aangevraagd en wordt de Dispatcher overgeslagen. Als u de bijgewerkte pagina ontvangt, geeft dit aan dat u de cache van de Dispatcher moet wissen.

   * Neem contact op met uw systeembeheerder als er problemen zijn met de replicatiestijden.

## Sidetrap niet zichtbaar {#sidekick-not-visible}

* **Probleem**:

   * Sidetrap is niet zichtbaar bij het bewerken van een inhoudspagina in de auteursomgeving.

* **Reden**:

   * In zeldzame gevallen zou u de kopbal van uw hulp buiten het werkingsgebied van uw huidig venster kunnen hebben geplaatst. Dit betekent dat u de positie niet opnieuw kunt wijzigen.

* **Oplossing**:

   * Log uit van uw huidige sessie en meld u opnieuw aan. Sidetrap keert terug naar de standaardpositie.

## Zoeken en vervangen - niet alle exemplaren worden vervangen {#find-replace-not-all-instances-are-replaced}

* **Probleem:**

   * Als u de optie **Zoeken en vervangen** gebruikt, kan het gebeuren dat niet alle exemplaren van de `find` term op een pagina worden vervangen.

* **Reden**:

   * De mogelijkheid **Zoeken en vervangen** is afhankelijk van de manier waarop de inhoud wordt opgeslagen en of er kan worden gezocht. Een blogtekst wordt bijvoorbeeld opgeslagen in een `jcr:text` eigenschap die niet is geconfigureerd om te worden doorzocht. Het standaardwerkingsgebied voor het vondst en vervangt servlet behandelt de volgende eigenschappen:

      * `jcr:title`
      * `jcr:description`
      * `jcr:text`
      * `text`

* **Oplossing**:

   * Deze definities kunnen met de configuratie voor **Dag CQ WCM Vondst vervangen Servlet** gebruikend de Console **van het** Web worden veranderd; bijvoorbeeld bij

      `http://localhost:4502/system/console/configMgr`

