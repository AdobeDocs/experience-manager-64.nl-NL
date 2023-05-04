---
title: Referentie metagegevensschema
description: Leer meer over standaardconventies voor het beschrijven van metagegevens van elementen, zoals Dublin Core, IPTC en ander metagegevensschema.
contentOwner: AG
feature: Metadata
role: User,Admin
exl-id: 883bebc6-8bbc-43b1-91e5-9e2bf2470b6e
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 0%

---

# Referentie metagegevensschema {#metadata-schemata-reference}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

De volgende naslaggids bevat informatie over een bepaald metagegevensschema (in alfabetische volgorde) en een lijst met eigenschappen en de bijbehorende definities.

## Dublin Core {#dublin-core}

De meta-gegevens van de Kern van Dublin verstrekt een gestandaardiseerde reeks overeenkomsten voor het beschrijven van activa om hen gemakkelijker te maken te vinden. In [!DNL Experience Manager] Middelen, de Dublin Core beschrijft digitale activa met inbegrip van video, geluid, beelden, en documenten.

De eenvoudige Dublin Core Metadata Element Set (DCMES) bevat 15 metagegevenselementen die in de volgende tabel worden vermeld. Elk Dublin Core-element is optioneel en kan worden herhaald. U kunt Dublin Core-metagegevens toevoegen of verwijderen op dezelfde manier als voor mediatype-specifieke metagegevens.

Naast het DCMES zijn er andere metagegevenselementen die door het Dublin Core-initiatief zijn gecreëerd. Zie de [Dublin Core-initiatief](https://dublincore.org/) voor meer informatie .

| Eigenschap | Beschrijving |
|---|---|
| contribuant | De persoon die of het bedrijf dat verantwoordelijk is voor het leveren van bijdragen aan de inhoud. |
| dekking | De geografische locatie of tijdsperiode waarop het actief betrekking heeft. |
| schepper | De persoon of het bedrijf die verantwoordelijk is voor het maken van de inhoud. |
| date | Datum of periode die aan het element is gekoppeld. |
| beschrijving | Meer informatie over het element. |
| format | De bestandsindeling, het fysieke medium of de afmetingen van het element. [!DNL Experience Manager] gebruikt dc:format om het mime-type van het element aan te geven. |
| id | Een unieke verwijzing naar het element. |
| taal | De taal van het element (bijvoorbeeld en voor Engels). |
| uitgever | De persoon of het bedrijf die verantwoordelijk is voor het ter beschikking stellen van het actief. |
| relatie | Een gerelateerd actief. |
| rechten | Informatie over wie de rechten op dit actief heeft. |
| bron | Een gerelateerd actief waarvan het actief is afgeleid. |
| onderwerp | Het onderwerp van de activa. |
| titel | Een naam voor het element. |
| type | De aard of het genre van het actief. |

## IPTC {#iptc}

De International Press Telecommunications Council (IPTC) is een consortium van nieuwsagentschappen over de hele wereld - een van de doelstellingen is het ontwikkelen en handhaven van technische normen. In de IPTC is een reeks standaarden voor fotometagegevens gedefinieerd voor afbeeldingen die vrijwel overal door fotografen worden geaccepteerd. Deze metagegevensstandaarden maakten deel uit van de bredere standaard die bekend staat als het IPTC Information Interchange Model (IIM) dat in de jaren negentig is gemaakt.

Hoewel de IPTC-headerinformatie meestal is vervangen door XMP, zijn een IPTC-kernschema en een extensieschema beschikbaar voor XMP. In afbeeldingsprogramma&#39;s worden zowel XMP- als IPTC-eigenschappen gesynchroniseerd.
