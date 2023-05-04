---
title: Opmerkingen bij de release van AEM Communities
seo-title: AEM Communities
description: Opmerkingen bij de release specifiek voor Adobe Experience Manager 6.4-gemeenschappen.
seo-description: Release notes specific to Adobe Experience Manager 6.4 Communities.
uuid: 2de9f511-2a61-4003-9b2c-d6728bc9d57a
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4
topic-tags: release-notes
content-type: reference
discoiquuid: 55a0b70e-5212-408b-8560-6e758bd8bb10
exl-id: 3a341e72-01c5-4c63-8942-6320e5b08440
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 0%

---

# Opmerkingen bij de release van AEM Communities {#aem-communities-release-notes}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Deze sectie bevat informatie over de verbeteringen die sinds de release 6.3 in AEM Communities zijn aangebracht. Voor meer informatie over de nieuwe functies raadpleegt u [Nieuwe functies in AEM 6.4-gemeenschappen](/help/communities/whats-new-aem-communities.md).

Voor de nieuwste release raadpleegt u de [Gemeenschappen inzetten](/help/communities/deploy-communities.md#latest-releases) van de documentatie.

## Belangrijkste verbeteringen {#main-improvements}

Communitysites:

* De communautaire Beheerders kunnen nu:

   * Community-sites permanent verwijderen
   * Selecteer een contextbewuste configuratiemap voor communitysites

Communautaire groepen:

* De communautaire Beheerders kunnen nu:

   * Gebruikersgroepen permanent verwijderen
   * Communitygroepen maken in meerdere talen
   * Inschakelingscatalogus en -toewijzingen toevoegen binnen groepen van gemeenschappen

* Enablement Managers kunnen nu

   * Bronnen en leerpaden maken en toewijzen binnen groepen van de Gemeenschap

Bestandsbibliotheek:

* De leden van de Gemeenschap hebben nu veelvoudige verhogingen aan de Bibliotheek van het Dossier, b.v. sorteervolgorden, het etiketteren...

Meldingen:

* De leden van de Gemeenschap ontvangen nu meldingen na goedkeuring van bijdragen die een moderniseringsproces hebben doorlopen

Moderatie:

* Filter voor automatische spamdetectie
* De Moderatoren van de Gemeenschap hebben extra filters van de Moderatie (b.v. beantwoorde/onbeantwoorde vragen)
* Moderatoren van de Gemeenschap kunnen een referentie maken en moderatie koppelen aan vooraf gedefinieerde filters (bijv. alle posten in afwachting van goedkeuring)

Algemene compatibiliteit met fundamentele wijzigingen in AEM 6.4.

Opmerking: al deze functies zijn ook beschikbaar voor AEM 6.3. Controleer de AEM Communities-releaseopmerkingen voor [6,3](https://helpx.adobe.com/experience-manager/6-3/release-notes.html).

## Bekende problemen {#known-issues}

* **Moderatie** - Kan bovenliggende post niet verwijderen als één enkele verwijderingsoperatie uit de bulkmoderatie-gebruikersinterface (CQ-4236797)
* **Console** - De koppeling Gebruikersnaam of Wachtwoord vergeten wordt doorgestuurd naar de aanmeldingspagina in plaats van het bijbehorende formulier voor het opvragen van wachtwoorden (CQ-4237682)

## Functies selecteren {#select-features}

Scores met experts (*Powered by Sensei*) - wordt gebruikt om gokactiviteiten mogelijk te maken, wat een effectieve manier is om waardevol gedrag van de gemeenschap aan te moedigen en te belonen. Het kan ook worden gebruikt om deskundigen voor aanbeveling- of marketingdoeleinden te identificeren.

## Demonstraties {#demonstrations}

Al deze functies kunnen worden gedemonstreerd met de [AEM demo-machine](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki) beschikbaar openbaar op GitHub.com wanneer het gebruiken van het de demoscenario van AEM Communities en ook binnen de nieuwe Web.Retail verwijzingsimplementatie.
