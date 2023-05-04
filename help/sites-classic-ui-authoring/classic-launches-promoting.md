---
title: Lanceringen promoten
seo-title: Promoting Launches
description: U moet opstartiepagina's promoten om de inhoud vóór publicatie weer naar de bron (productie) te verplaatsen. Wanneer een startpagina wordt bevorderd, wordt de bijbehorende pagina van de bronpagina's vervangen door de inhoud van de gepromoveerde pagina.
seo-description: You need to promote launch pages to move the content back into the source (production) before publishing. When a launch page is promoted, the corresponding page of the source pages is replaced with the content of the promoted page.
uuid: 91f1c6ac-8c4e-4459-aaab-feaa32befc45
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: site-features
discoiquuid: 8d38c6f7-8fea-4d27-992d-03b604b9541f
legacypath: /content/docs/en/aem/6-0/author/site-page-features/launches
exl-id: 793c44fa-9dd1-45f2-b1ab-219b436fcb54
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 2%

---

# Lanceringen promoten{#promoting-launches}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

U moet opstartiepagina&#39;s promoten om de inhoud vóór publicatie weer naar de bron (productie) te verplaatsen. Wanneer een startpagina wordt bevorderd, wordt de bijbehorende pagina van de bronpagina&#39;s vervangen door de inhoud van de gepromoveerde pagina. De volgende opties zijn beschikbaar bij het promoten van een startpagina:

* Of alleen de huidige pagina of de volledige lancering wordt bevorderd.
* Of de onderliggende pagina&#39;s van de huidige pagina worden bevorderd.
* Of de volledige lancering of slechts pagina&#39;s wordt bevorderd die zijn veranderd.

## Startpagina&#39;s promoten {#promoting-launch-pages}

Als u pagina&#39;s wilt promoten, voert u de volgende stappen uit tijdens het bewerken van de startpagina die u wilt promoten:

1. Op de **Pagina** tab in Sidetrap, klik op **Starten bevorderen**.
1. Geef de pagina&#39;s op die u wilt promoten:

   * (Standaard) Als u alleen de huidige pagina wilt promoten, selecteert u **Paginawijzigingen doorvoeren naar productieversie**.
   * Selecteer **Inclusief subpagina&#39;s**.
   * Selecteer **Volledige introductie naar productieversie bevorderen**.

1. Als u de productiepagina&#39;s aan een workflowpakket wilt toevoegen, selecteert u **Toevoegen aan workflowpakket** en selecteer vervolgens het workflowpakket.
1. Klikken **Bevorderen**.

## Promotiepagina&#39;s verwerken met AEM-workflow {#processing-promoted-pages-using-aem-workflow}

Gebruik workflowmodellen voor bulkverwerking van geconverteerde startpagina&#39;s:

1. Maak een workflowpakket.
1. Wanneer auteurs startpagina&#39;s promoten, slaan ze deze op in het workflowpakket.
1. Start een workflowmodel met het pakket als de payload.

Als u automatisch een workflow wilt starten wanneer pagina&#39;s worden geconverteerd, [configureren van een workflow](/help/sites-administering/workflows-starting.md#workflows-launchers) voor het pakketknooppunt.

U kunt bijvoorbeeld automatisch aanvragen voor paginanactivering genereren wanneer auteurs pagina&#39;s starten promoten. Configureer een werkstroomstartprogramma om de workflow voor activering van aanvragen te starten wanneer het pakketknooppunt wordt gewijzigd.

![chlimage_1-136](assets/chlimage_1-136.png)
