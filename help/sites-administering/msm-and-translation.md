---
title: Websitebeheer
seo-title: Website Administration
description: Leer hoe u meertalige websites in AEM beheert.
seo-description: Learn how to manage multilingual websites in AEM.
uuid: a32d458b-a5ad-46ef-a68c-4717c63b4bdd
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: site-features
content-type: reference
discoiquuid: fabaa3e8-1657-4ed4-abb2-990117bec39c
exl-id: e8f83d21-b55e-4415-a581-8df1b71a84b1
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 0%

---

# Websitebeheer{#website-administration}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

De volgende beheergereedschappen zijn beschikbaar voor het beheer van websites en pagina&#39;s:

* Met MSM (Multi Site Manager) kunt u dezelfde site-inhoud op meerdere locaties gebruiken, terwijl variaties mogelijk zijn:

   * [Inhoud opnieuw gebruiken: Beheer van meerdere sites en Live Copy](/help/sites-administering/msm.md)

* Met vertaling kunt u de vertaling van pagina-inhoud, elementen en door de gebruiker gegenereerde inhoud automatiseren om meertalige websites te maken en te onderhouden:

   * [Inhoud vertalen voor meertalige sites](/help/sites-administering/translation.md)

* Deze twee functies kunnen worden gecombineerd om te kunnen werken met websites die beide [Meertalig en meertalig](#multinational-and-multilingual-sites).

## Meertalige en meertalige sites {#multinational-and-multilingual-sites}

U kunt op efficiënte wijze inhoud maken voor multinationale en meertalige sites door het gecombineerde gebruik van de Multi-Site Manager en de vertaalworkflow. Maak een master site in één taal, voor een specifiek land, en gebruik die inhoud als basis voor de andere sites, waar nodig met vertaling:

* [Vertalen](/help/sites-administering/translation.md) de master site in verschillende talen.

* Gebruiken [Beheer van meerdere sites](/help/sites-administering/msm.md) tot:

   * Gebruik inhoud van de master site en de vertalingen opnieuw om sites te maken voor andere landen en culturen.
   * Zorg ervoor dat u het gebruik van Multi-Site Manager beperkt tot inhoud binnen één taal, bijvoorbeeld master Engels -> vertakkingen van Engelse talen in landsites, master Frans -> vertakkingen van Franse talen in landsites.
   * Koppel zo nodig elementen van de live kopieën los om lokalisatiegegevens toe te voegen.

In het volgende diagram ziet u hoe de hoofdconcepten elkaar snijden (maar niet alle niveaus/elementen in kwestie weergeven):

![chlimage_1-71](assets/chlimage_1-71.png)

>[!NOTE]
>
>In dit, en vergelijkbaar, scenario&#39;s MSM beheert niet de verschillende taalversies als dusdanig.
>
>* [MSM](/help/sites-administering/msm.md) beheert de implementatie van vertaalde inhoud van een blauwdruk (bijvoorbeeld een wereldwijd master) tot de live kopieën (bijvoorbeeld de lokale sites), binnen de grenzen van een taal.
>* De [vertalen](/help/sites-administering/translation.md) de integratiemogelijkheden van AEM, in combinatie met de vertaaldiensten van derden, beheren de talen en vertalen van inhoud in deze verschillende talen.
>
>Voor geavanceerdere gebruiksgevallen kan MSM ook voor alle taalmeesters worden gebruikt.

>[!NOTE]
>
>Voor alle gebruiksgevallen is het raadzaam de volgende aanbevolen procedures te lezen:
>
>* [Beste praktijken voor MSM](/help/sites-administering/msm-best-practices.md); met name:
   >
   >   * [Site maken](/help/sites-administering/msm-best-practices.md#create-site)
   >   * [MSM- en meertalige websites](/help/sites-administering/msm-best-practices.md#msm-and-multilingual-websites)
>
>* [Aanbevolen procedures voor vertaling](/help/sites-administering/tc-bp.md)

