---
title: Opmerkingen bij de release Smart Content Service
seo-title: Opmerkingen bij de release Smart Content Service
description: Overzicht van de Slimme Dienst van de Inhoud en bekende kwesties rond de dienst.
seo-description: Overzicht van de Slimme Dienst van de Inhoud en bekende kwesties rond de dienst.
uuid: 5f474b36-3451-48ea-8669-b2d793638b06
content-type: reference
products: SG_EXPERIENCEMANAGER
discoiquuid: 9f88c773-ddeb-4c66-ac07-7d3aa196c51b
translation-type: tm+mt
source-git-commit: f8ba597c62379ba413309303c2ad066ab7afce1e
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 1%

---


# Opmerkingen bij de release Smart Content Service {#smart-content-service-release-notes}

Overzicht van de Slimme Dienst van de Inhoud en bekende kwesties rond de dienst.

De organisaties vereisen dat hun digitale activa worden geëtiketteerd gebaseerd op de taxonomie die de werknemers, de partners, en de klanten gebruiken om naar digitale activa te verwijzen en te zoeken. In vergelijking met generieke tags zijn elementen die zijn gelabeld op basis van de taxonomie van het bedrijf gemakkelijker te identificeren en op te halen door zoekopdrachten op basis van tags.

De Smart Content Service maakt gebruik van uw zakelijke taxonomie van AEM Assets om digitale middelen automatisch te labelen, zodat de meest relevante middelen in zoekopdrachten worden weergegeven.

U moet de Slimme Dienst van de Inhoud op een gekromde reeks AEM activa en markeringen opleiden om uw bedrijfstaxonomie te erkennen. Als de service eenmaal is getraind, kunnen deze tags op een vergelijkbare set elementen worden toegepast.

De Smart Content Service wordt aangedreven door het Adobe Sensei-platform, waarmee u het algoritme voor imageherkenning kunt trainen op uw bedrijfsconomie. Deze inhouds-informatie wordt vervolgens gebruikt om relevante tags toe te passen op vergelijkbare elementen.

## Belangrijke verbeteringen {#key-improvements}

De Smart Content Service bevat de volgende belangrijke verbeteringen:

* Algoritmeoptimalisaties om de precisie van het model verder te verbeteren, waarden terugroepen
* Ondersteuning voor het opnieuw instellen van modeltraining voor alle tags op huurdersniveau
* Verbeterde naamruimten voor slimme tags om conflicten te voorkomen
* Nieuw modelvervangingsbeleid om elke aantasting door omscholing te voorkomen
* Tenantgewijs toezicht op het gebruik van de service
* Oplossingen voor problemen rond het groeperen en verbinden, die de robuustheid van de dienst verbeteren

## {#fixed-issues} Opgeloste problemen

De volgende problemen zijn opgelost in deze release:

* Workflows voor labelen en training worden beëindigd als er geen verbinding kan worden gemaakt met de MySQL-server. CQ-4242886

* Nauwkeurige vertekende score wordt niet correct berekend. CQ-4241797

* Onjuiste PR-berekening voor model. CQ-4241381

* De trainingsworkflow mist voorbeeldmiddelen bij het verwerken ervan in de wachtrij CQ-4240901

* Verbeteringen in precisie-terugroeping. CQ-4239895

* Modelvervangingsbeleid. CQ-4239886

* Afbeeldingen voor het overhemd van mannen worden gelabeld met de vrouwenjasje-tag. CQ-4239650

* Trainingsvoorbeelden worden tijdens de implementatie van het werkgebied overgeslagen. CQ-4239483

* Validatie in een trainingsbaan moet plaatsvinden op een reeks activa die voor opleiding worden voorgelegd. CQ-4238834

* Maken van model mislukt voor negatief foerageergedrag, zelfs als er voor een tag minimale positieve/negatieve resultaten aanwezig zijn. CQ-4240741

* Misleidende vermeldingen voor negatief foerageergedrag in trainerlogboeken. CQ-4240738

* Probleem met de eerste opleiding als labels die voor training worden ingediend willekeurige negatieven van elkaar zijn. CQ-4240118

* Verbetert logboeken om de dienstgebruik per huurder te controleren. CQ-4239781

## Talen {#languages}

De service Slimme inhoud is beschikbaar voor de volgende landinstellingen:

* Engels
* Duits
* Frans
* Spaans
* Italiaans
* Portugees
* Japans
* Vereenvoudigd Chinees
* Koreaans

## Koppelingen {#links}

* [Adobe Experience Manager-productpagina op adobe.com](https://www.adobe.com/marketing-cloud/experience-manager.html)
* [Verbeterde documentatie voor slimme tags](/help/assets/enhanced-smart-tags.md)

## Toegang tot en ondersteuning voor producten (beperkt aantal sites) {#product-access-and-support-restricted-sites}

Deze sites zijn alleen beschikbaar voor klanten. Neem contact op met uw Adobe-accountmanager als u een klant bent en toegang nodig hebt.

* [Producttoegang](https://login.marketing.adobe.com)
* [Product downloaden op licensing.adobe.com](https://licensing.adobe.com/).
* Productupdates, patches en pakketten voor extra functionaliteit op [Softwaredistributie](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
* [Klantenondersteuning via Admin Console](https://adminconsole.adobe.com/). Zie [Nieuwe ervaring voor klantenondersteuning van Adobe](https://docs.adobe.com/content/help/en/customer-one/using/home.html) voor meer informatie.
