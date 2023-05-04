---
title: Problemen met AEM bij ontwerpen oplossen
seo-title: Troubleshooting AEM when Authoring
description: Sommige problemen die u bij het gebruik van AEM tegenkomt
seo-description: Some issues that you might encounter when using AEM
uuid: 99af51ea-8628-4811-83f2-ab3f88f0279e
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: page-authoring
content-type: reference
discoiquuid: da0a5644-2e1d-4394-a6aa-11bb41406ba6
exl-id: b0890070-c9e8-4ce4-9149-00c8c38298ce
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 9%

---

# Problemen met AEM bij ontwerpen oplossen{#troubleshooting-aem-when-authoring}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

De volgende sectie behandelt sommige kwesties die u wanneer het gebruiken van AEM zou kunnen ontmoeten, samen met suggesties op hoe te om hen problemen op te lossen.

>[!NOTE]
>
>Wanneer u problemen ondervindt, is het ook de moeite waard om de lijst met [Bekende problemen](/help/release-notes/known-issues.md) voor uw instantie (release- en servicepacks).

>[!NOTE]
>
>Gebruikers die beheerdersrechten hebben en die problemen met AEM willen oplossen, kunnen de in [AEM voor probleemoplossing (voor beheerders)](/help/sites-administering/troubleshoot.md). Als u niet voldoende rechten hebt, raadpleegt u uw systeembeheerder over AEM voor probleemoplossing.

## Oude paginaversie blijft op gepubliceerde site staan {#old-page-version-still-on-published-site}

* **Probleem**:

   * U hebt wijzigingen aangebracht in een pagina en de pagina gerepliceerd naar de publicatiesite, maar de *oud* Er wordt nog steeds een versie van de pagina weergegeven op de publicatiesite.

* **Reden**:

   * Dit kan verscheidene oorzaken hebben, meestal het geheime voorgeheugen (of uw lokale browser of de Verzender), hoewel het soms een kwestie met de replicatierij kan zijn.

* **Oplossingen**:

   * Hier zijn verschillende mogelijkheden:
   * Controleer of de pagina correct is gerepliceerd. Controleer de paginastatus en, indien nodig, de status van de replicatiewachtrij.
   * Wis de cache in uw lokale browser en open de pagina opnieuw.
   * Toevoegen `?` tot het einde van de pagina-URL. Bijvoorbeeld:

      * `http://localhost:4502/sites.html/content?`
      * Hiermee wordt de pagina rechtstreeks bij AEM aangevraagd en wordt de Dispatcher overgeslagen. Als u de bijgewerkte pagina ontvangt, geeft dit aan dat u de cache van de Dispatcher moet wissen.
   * Neem contact op met uw systeembeheerder als er problemen zijn met de replicatiestijden.


## Componenthandelingen niet zichtbaar op werkbalk {#component-actions-not-visible-on-toolbar}

* **Probleem**:

   * Het volledige bereik van toepasselijke componentacties is niet zichtbaar wanneer u een inhoudspagina bewerkt in de auteursomgeving.

* **Reden**:

   * In zeldzame gevallen kan een eerdere actie gevolgen hebben voor de werkbalk.

* **Oplossing**:

   * Vernieuw de pagina.
