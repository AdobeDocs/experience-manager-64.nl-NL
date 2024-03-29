---
title: Herstructurering van de depositaris in AEM 6.4
seo-title: Repository Restructuring in AEM 6.4
description: Meer informatie over de grondbeginselen en de redenering achter de herstructurering van de opslagplaats in AEM 6.4
seo-description: Learn about the basics and reasoning behind the repository restructuring in AEM 6.4
uuid: e9cd3e88-e352-44a8-9b97-69488d3267cb
contentOwner: chaikels
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: repo_restructuring
discoiquuid: fc879b0b-823b-4bdc-aaa6-36f53a33fb22
feature: Upgrading
exl-id: 6ff5a23a-c9b5-49ca-87b2-ba01eaf48a9f
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 0%

---

# Herstructurering van de depositaris in AEM 6.4{#repository-restructuring-in-aem}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Inleiding {#introduction}

Voorafgaand aan AEM 6.4, werd de klantencode opgesteld in onvoorspelbare gebieden van JCR die onderhevig waren aan verandering op verbeteringen. Daarom was het gebruikelijk voor formele AEM om aangepaste code, configuratie of inhoud te overschrijven. Daarnaast overschrijden wijzigingen door klanten soms AEM productcode of inhoud, waardoor de productfunctionaliteit wordt verbroken.

Door hiërarchieën voor AEM productcode en klantencode duidelijk te bepalen, kunnen deze conflicten worden vermeden.

Te dien einde, vanaf AEM 6.4 en om in toekomstige versies te worden voortgezet, wordt de inhoud van /etc naar andere omslagen in de bewaarplaats geherstructureerd, samen met richtlijnen over waar de inhoud gaat, die zich aan de volgende regels op hoog niveau houden:

* AEM productcode zal altijd in /libs worden geplaatst, die niet door douanecode moet worden beschreven
* De aangepaste code moet worden geplaatst in /apps, /content en /conf

## Effect op 6,4 upgrades {#impact-on-upgrades}

Wanneer u een upgrade uitvoert naar AEM 6.4, wordt een grote subset van de inhoud onder /etc. gedupliceerd in andere mappen in de opslagplaats. Deze nieuwe locaties zijn de voorkeurslocaties voor de inhoud. Nochtans, is elke poging gemaakt om AEM 6.4 verbetering achterwaarts compatibel met de vorige plaatsen in de /etc omslag te zijn en zo in de meeste gevallen zullen de oude plaatsen door AEM code blijven worden van verwijzingen voorzien tot de veranderingen actief — en in veel gevallen manueel — in de toepassing van een klant worden gemaakt. Vanuit een tijdlijnperspectief zijn er twee categorieën wijzigingen:

* Met 6.4 Verbetering - een handvol van de /etc-herstructureringen zijn niet achterwaarts compatibel en daarom zouden de aanpassingen als deel van AEM 6.4 verbetering moeten worden gepland en worden uitgevoerd.
* Voorafgaand aan 6.5 Verbetering - het overgrote deel van de /etc-herstructureringsveranderingen kan tot enige tijd in de toekomstige post-verbetering worden uitgesteld. Zoals eerder vermeld, zal AEM 6.4 code de oude plaatsen blijven van verwijzingen voorzien tot de wijzigingen als deel van een klantenversie worden uitgevoerd. Hoewel er geen geforceerde tijdlijn is waarvoor de veranderingen zouden moeten worden aangebracht, wordt geadviseerd dat zij vóór de verbetering 6.5 worden gemaakt aangezien de toekomstige eigenschappen zich op de nieuwe plaatsen kunnen baseren die worden van verwijzingen voorzien. Bovendien zal de documentatie voor een bepaalde eigenschap door conventie naar de nieuwe plaatsen verwijzen en het zou daarom verwarrend kunnen zijn als de oude plaatsen nog worden gebruikt.

### Herstructureringsrichtsnoeren {#restructuring-guidance}

Bij het plannen van een upgrade naar AEM 6.4 moet naar de volgende pagina&#39;s per oplossing worden verwezen om de werkinspanning te beoordelen:

* [Herstructurering van de opslagplaats gemeenschappelijk voor alle AEM oplossingen](/help/sites-deploying/all-repository-restructuring-in-aem-6-4.md)
* [Herstructurering van AEM Sites-opslagplaats](/help/sites-deploying/sites-repository-restructuring-in-aem-6-4.md)
* [Herstructurering van AEM Assets-opslagplaats](https://experienceleague.adobe.com/docs/experience-manager-64/deploying/restructuring/repository-restructuring.html)
* [Herstructurering van de AEM Assets Dynamic Media-opslagplaats](/help/sites-deploying/dynamicmedia-repository-restructuring-in-aem-6-4.md)
* [Herstructurering van AEM Forms-opslagplaats](/help/sites-deploying/forms-repository-restructuring-in-aem-6-4.md)
* [Herstructurering van AEM Communities-opslagplaats](/help/sites-deploying/communities-repository-restructuring-in-aem-6-4.md)
* [Herstructurering van de opslagplaats AEM](/help/sites-deploying/ecommerce-repository-restructuring-in-aem-6-4.md)

Elke pagina bevat twee secties die overeenkomen met de urgentie van de noodzakelijke wijzigingen. Om het even wat onder de &quot;Met 6.4 Verbetering&quot;sectie zou als deel van het AEM 6.4 verbeteringsproject moeten worden behandeld. Alles onder de &quot;Voorafgaande 6.5-upgrade&quot; kan optioneel worden uitgesteld tot na de upgrade.

Elke vermelding op de pagina bevat een veld &quot;Herstructureringshulplijnen&quot;, waarin de aanbevolen technische strategie voor het uitlijnen op het nieuwe model van de opslagplaats 6.4 wordt beschreven, zodat naar de nieuwe locaties wordt verwezen voor inhoud die zich eerder in de map /etc bevond. Een extra veld Notities biedt een extra handige context.
