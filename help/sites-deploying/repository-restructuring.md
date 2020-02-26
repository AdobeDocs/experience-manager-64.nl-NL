---
title: Repositoregeling herstructurering in AEM 6.4
seo-title: Repositoregeling herstructurering in AEM 6.4
description: Meer informatie over de grondbeginselen en de redenering achter de herstructurering van de opslagplaats in AEM 6.4
seo-description: Meer informatie over de grondbeginselen en de redenering achter de herstructurering van de opslagplaats in AEM 6.4
uuid: e9cd3e88-e352-44a8-9b97-69488d3267cb
contentOwner: chaikels
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: repo_restructuring
discoiquuid: fc879b0b-823b-4bdc-aaa6-36f53a33fb22
translation-type: tm+mt
source-git-commit: 7b39a715166eeefdf20eb22a4449068ff1ed0e42

---


# Repositoregeling herstructurering in AEM 6.4{#repository-restructuring-in-aem}

## Inleiding {#introduction}

Vóór AEM 6.4, werd de klantencode opgesteld in onvoorspelbare gebieden van JCR die onderhevig waren aan verandering op verbeteringen. Daarom was het gebruikelijk voor formele AEM-versies om aangepaste code, configuratie of inhoud te overschrijven. Bovendien overschrijven wijzigingen door klanten soms de AEM-productcode of -inhoud, waardoor de productfunctionaliteit wordt verbroken.

Door hiërarchieën voor AEM productcode en klantencode duidelijk te bepalen, kunnen deze conflicten worden vermeden.

Te dien einde wordt, vanaf AEM 6.4 en om in toekomstige versies te worden voortgezet, de inhoud van /etc naar andere mappen in de opslagplaats geherstructureerd, samen met richtlijnen over waar de inhoud naartoe gaat, met inachtneming van de volgende regels op hoog niveau:

* AEM-productcode wordt altijd in /libs geplaatst, die niet door aangepaste code mag worden overschreven
* De aangepaste code moet worden geplaatst in /apps, /content en /conf

## Effect op 6,4 upgrades {#impact-on-upgrades}

Wanneer u een upgrade uitvoert naar AEM 6.4, wordt een grote subset van de inhoud onder /etc. gedupliceerd in andere mappen in de opslagplaats. Deze nieuwe locaties zijn de voorkeurslocaties voor de inhoud. Nochtans, is elke poging gemaakt om AEM 6.4 verbetering achterwaarts compatibel met de vorige plaatsen in de /etc omslag te zijn en zo in de meeste gevallen zullen de oude plaatsen door AEM code blijven worden van verwijzingen voorzien tot de veranderingen actief — en in veel gevallen manueel — in de toepassing van een klant worden gemaakt. Vanuit een tijdlijnperspectief zijn er twee categorieën wijzigingen:

* Met 6.4 Verbetering - een handjevol van de /etc-herstructureringen zijn niet achterwaarts compatibel en daarom zouden aanpassingen als deel van de verbetering van AEM 6.4 moeten worden gepland en uitgevoerd.
* Voorafgaand aan 6.5 Verbetering - het overgrote deel van de /etc-herstructureringsveranderingen kan tot enige tijd in de toekomstige post-verbetering worden uitgesteld. Zoals eerder vermeld, zal de code AEM 6.4 de oude plaatsen blijven van verwijzingen voorzien tot de wijzigingen als deel van een klantenversie worden uitgevoerd. Hoewel er geen geforceerde tijdlijn is waarvoor de veranderingen zouden moeten worden aangebracht, wordt geadviseerd dat zij vóór de verbetering 6.5 worden gemaakt aangezien de toekomstige eigenschappen zich op de nieuwe plaatsen kunnen baseren die worden van verwijzingen voorzien. Bovendien zal de documentatie voor een bepaalde eigenschap door conventie naar de nieuwe plaatsen verwijzen en het zou daarom verwarrend kunnen zijn als de oude plaatsen nog worden gebruikt.

### Herstructureringsrichtsnoeren {#restructuring-guidance}

Bij de planning voor een upgrade naar AEM 6.4 moeten de volgende pagina&#39;s per oplossing worden vermeld om de werkinspanning te beoordelen:

* [Herstructurering van de opslagplaats, gemeenschappelijk voor alle AEM-oplossingen](/help/sites-deploying/all-repository-restructuring-in-aem-6-4.md)
* [Herstructurering van de AEM-sitecentra](/help/sites-deploying/sites-repository-restructuring-in-aem-6-4.md)
* [Herstructurering van de AEM Assets-opslagplaats](/help/sites-deploying/assets-repository-restructuring-in-aem-6-4.md)
* [Herstructurering van de opslagplaats van AEM Assets Dynamic Media](/help/sites-deploying/dynamicmedia-repository-restructuring-in-aem-6-4.md)
* [Herstructurering van de opslagplaats van AEM Forms](/help/sites-deploying/forms-repository-restructuring-in-aem-6-4.md)
* [Herstructurering van de opslagplaats van AEM](/help/sites-deploying/communities-repository-restructuring-in-aem-6-4.md)
* [Herstructurering van de opslagplaats van AEM](/help/sites-deploying/ecommerce-repository-restructuring-in-aem-6-4.md)

Elke pagina bevat twee secties die overeenkomen met de urgentie van de noodzakelijke wijzigingen. Alles wat onder de sectie &quot;Met 6.4 upgrade&quot; valt, moet worden aangepakt als onderdeel van het upgradeproject voor AEM 6.4. Alles onder de &quot;Voorafgaande 6.5-upgrade&quot; kan optioneel worden uitgesteld tot na de upgrade.

Elke vermelding op de pagina bevat een veld &quot;Herstructureringshulplijnen&quot;, waarin de aanbevolen technische strategie voor het uitlijnen op het nieuwe model van de opslagplaats 6.4 wordt beschreven, zodat naar de nieuwe locaties wordt verwezen voor inhoud die zich eerder in de map /etc bevond. Een extra veld Notities biedt een extra handige context.
