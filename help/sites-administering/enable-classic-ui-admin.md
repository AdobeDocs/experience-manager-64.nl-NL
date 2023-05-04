---
title: Admin Consoles
seo-title: Admin Consoles
description: Leer hoe u de Admin Consoles gebruikt die beschikbaar zijn in AEM.
seo-description: Lear how to use the Admin Consoles available in AEM.
uuid: 701dc57c-f7b4-421e-a847-577ae2585e80
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: operations
content-type: reference
discoiquuid: 98ba3093-1edb-4891-abbe-47cf6e4f1feb
exl-id: f3c03562-aaeb-4d43-aee1-d92d661ee329
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 0%

---

# Admin Consoles{#admin-consoles}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

De mogelijkheid om via de beheerconsoles over te schakelen op de klassieke gebruikersinterface is standaard uitgeschakeld. Daarom worden de pop-uppictogrammen die werden gezien toen de muis over bepaalde consolepictogrammen beweegt, die toegang tot klassieke UI toestaan, niet meer getoond.

![screen_shot_2018-03-23at111956](assets/screen_shot_2018-03-23at111956.png)

Elke console die een Klassieke versie UI in heeft `/libs/cq/core/content/nav` kan individueel opnieuw worden toegelaten zodat **Klassieke interface** Deze optie wordt weer boven het consolepictogram weergegeven wanneer de muis erboven wordt geplaatst.

In dit voorbeeld, zijn wij re-toelatend Klassieke UI voor de console van Plaatsen.

1. Gebruikend CRXDE Lite, vind de knoop die de admin console beantwoordt waarvoor u Klassieke UI wilt re-toelaten. Deze zijn te vinden onder:

   `/libs/cq/core/content/nav`

   Bijvoorbeeld

   [ `http://localhost:4502/crx/de/index.jsp#/libs/cq/core/content/nav`](http://localhost:4502/crx/de/index.jsp#/libs/cq/core/content/nav)

1. Selecteer de knoop die aan de console beantwoordt waarvoor u Klassieke UI wilt re-toelaten. Voor ons voorbeeld, zullen wij klassieke UI voor de console van Plaatsen re-toelaten.

   `/libs/cq/core/content/nav/sites`

1. Een overlay maken met de opdracht **Overlayknooppunt** optie; bijvoorbeeld:

   * **Pad**: `/apps/cq/core/content/nav/sites`
   * **Overlay-locatie**: `/apps/`
   * **Identieke knooppunttypen**: actief (schakel het selectievakje in)

1. Voeg de volgende booleaanse eigenschap toe aan het bovenliggende knooppunt:

   `enableDesktopOnly = {Boolean}true`

1. De **Klassieke interface** deze optie is weer beschikbaar als een popover-optie in de beheerconsole.

   ![screen_shot_2018-03-23at111924](assets/screen_shot_2018-03-23at111924.png)

Herhaal deze stappen voor elke console waarvoor u toegang tot de Klassieke versie van UI wenst opnieuw toe te laten.
