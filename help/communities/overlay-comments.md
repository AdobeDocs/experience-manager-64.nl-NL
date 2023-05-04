---
title: Component Opmerkingen bedekken
seo-title: Overlay Comments Component
description: Overzicht van de component Overlay Comments
seo-description: Overlay Comments component overview
uuid: 634240e2-99bb-4107-89f5-c66d53e2515d
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 4849da13-518c-40c8-b80e-1b2264d7f8f5
exl-id: 31528814-02bc-4978-87fa-5c8074b454ed
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 0%

---

# Component Opmerkingen bedekken {#overlay-comments-component}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

De bedoeling van [bedekken](client-customize.md#overlays) een standaardcomponent is het wijzigen van de weergave of het gedrag van een component in het algemeen voor alle relatieve verwijzingen naar de component. Het is afhankelijk van de aard van de sling om naar de map /apps op te lossen voordat u in de map /libs zoekt. Het pad naar de component is dus identiek aan het pad naar de standaardcomponent, behalve dat het pad zich in de map /apps bevindt en niet in de map /libs.

## Voorbeeld {#example}

Stel dat u de commentaarfunctie wilt wijzigen zodat deze overeenkomt met het ontwerp van uw website, door de koptekst van de opmerking te wijzigen zodat de avatar niet meer wordt weergegeven voor opmerkingen. De oplossingen voor het verbergen van de avatar maken gebruik van CSS of, zoals hier wordt beschreven, van de header.jsp in de map apps, zodat de HTML die de avatar bevat nooit naar de client wordt verzonden.

Als u opmerkingen wilt bedekken, moet u:

1. [Opmerkingen pagina](overlay-create-comments-page.md)
1. [Notities maken](overlay-create-nodes.md)
1. [De vormgeving wijzigen](overlay-alter-appearance.md)
