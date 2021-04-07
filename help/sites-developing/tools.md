---
title: Gereedschappen voor testen en bijhouden
seo-title: Gereedschappen voor testen en bijhouden
description: AEM biedt een raamwerk voor het testen van de interface van componenten en een mechanisme voor het testen en opsporen van fouten in componenten
seo-description: AEM biedt een raamwerk voor het testen van de interface van componenten en een mechanisme voor het testen en opsporen van fouten in componenten
uuid: 29c43202-0a4e-41ba-9176-92fa77c627d5
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: testing
content-type: reference
discoiquuid: 0f977264-fe58-4478-bd38-aca5c75f36aa
exl-id: 9387cdb4-f8de-4229-90d1-59218ac17561
translation-type: tm+mt
source-git-commit: bd94d3949f0117aa3e1c9f0e84f7293a5d6b03b4
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 0%

---

# Gereedschappen voor testen en bijhouden{#testing-and-tracking-tools}

## Testen {#testing}

AEM biedt:

* [een framework voor het testen van de gebruikersinterface](/help/sites-developing/hobbes.md) van componenten.
* [een mechanisme voor het testen van en het opsporen van fouten in componenten](/help/sites-developing/developer-mode.md).

Hieronder vindt u twee Open Source Testing-gereedschappen:

**Selenium**

Selenium wordt gebruikt voor functietests in een browser met één gebruiker per activiteit. Hierbij worden teststappen (klikken) vastgelegd als HTML-tabellen of Java-klassen.

Zie [https://www.seleniumhq.org/](https://www.seleniumhq.org/) voor meer informatie.

**JMeter**

JMeter wordt gebruikt om aanvragen te volgen en kan worden gebruikt voor functionele, prestatie- en stresstests.

Zie [http://jakarta.apache.org/jmeter/](http://jakarta.apache.org/jmeter/) voor meer informatie.

Er zijn ook veel bedrijfseigen instrumenten om tests te automatiseren en testplannen te beheren.

## {#tracking} bijhouden

De volgende gereedschappen zijn gemakkelijk beschikbaar. Nochtans is een zeer belangrijke kwestie in alle gevallen de beschikbaarheid van de gegevens aan alle leden van het projectteam - partner en klant.

**Bugzilla**

Een bug-volgsysteem dat aan uw eigen vereisten kan worden gevormd.

**Werkbladen**

Hoewel spreadsheets niet specifiek voor foutopsporing worden gebruikt, zijn ze gemakkelijk te begrijpen en hebben de meeste gebruikers ervaring met hun functionaliteit.

Als deze voor het volgen dan worden gebruikt:

* zij moeten eenvoudig worden gehouden .
* het aantal afzonderlijke spreadsheets moet tot een minimum worden beperkt .
* zij moeten regelmatig worden bijgewerkt .
* slechts één master kopie moet worden bewaard en iedereen moet weten waar de master kopie is.
* zij moeten toegankelijk zijn voor alle projectleden .
* als de veiligheid een kwestie is ( vaak voorkomt bij grote bedrijven ) en gemeenschappelijke toegang niet mogelijk is , kunnen kopieën worden verspreid zolang iedereen begrijpt dat het kopieën zijn en niet kunnen worden bijgewerkt .

Ook hier zijn er veel bedrijfseigen hulpmiddelen voor het bijhouden van fouten en eigenschapvereisten.
