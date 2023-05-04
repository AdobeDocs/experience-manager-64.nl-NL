---
title: Welke testomgevingen zijn nodig?
seo-title: Which Test Environments are needed?
description: Verschillende omgevingen moeten worden beschouwd als onderdeel van tests
seo-description: Several environments should be considered as part of testing
uuid: bb725e50-edae-4c20-8107-d1c8df2e60e2
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: testing
content-type: reference
discoiquuid: db528b9b-3407-462d-8254-20b3cc2c3ccf
exl-id: c3c7c007-4814-4bd1-987e-534df4575a4a
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 0%

---

# Welke testomgevingen zijn nodig?{#which-test-environments-will-be-needed}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Als u wilt definiëren welke configuraties voor tests moeten worden gebruikt, moet u het volgende in overweging nemen:

**Ontwikkeling** - voor eenheid en bepaalde integratietests.

**Testen** - Voor het grootste deel van de tests.

**Live** - voor de eindprestaties en stresstests. Ook voor goedkeuringstests met de klant.

U moet ook bepalen welke instanties u nodig hebt (meestal ten minste één voor alle testniveaus):

**Auteur** - Met dit exemplaar kunnen auteurs inhoud invoeren en publiceren.

**Publiceren** - Dit exemplaar presenteert de website in zijn gepubliceerde formulier voor toegang van bezoekers.

Moet worden getest in combinatie met de Dispatcher.

Ten slotte moet de werkelijke hardware in overweging worden genomen: eventuele prestatietests moeten worden uitgevoerd op een systeem dat zo dicht mogelijk bij de uiteindelijke live omgeving ligt. Daarom wordt ook aanbevolen het project te starten in een:

**Zacht starten** - verminderde beschikbaarheid; die tijd voor prestatietests, afstelling en optimalisering in realistische omstandigheden op de productieomgeving mogelijk maakt.

**Hard starten** - Volledige beschikbaarheid.
