---
title: Component Opmerkingen bedekken
seo-title: Component Opmerkingen bedekken
description: Overzicht van de component Overlay Comments
seo-description: Overzicht van de component Overlay Comments
uuid: 634240e2-99bb-4107-89f5-c66d53e2515d
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 4849da13-518c-40c8-b80e-1b2264d7f8f5
translation-type: tm+mt
source-git-commit: 8f169bb9b015ae94b9160d3ebbbd1abf85610465

---


# Component Opmerkingen bedekken {#overlay-comments-component}

Het is de bedoeling om een standaardcomponent te [bedekken](client-customize.md#overlays) door de weergave of het gedrag van een component globaal te wijzigen voor alle relatieve verwijzingen naar de component. Het is afhankelijk van de aard van de sling om naar de map /apps op te lossen voordat u in de map /libs zoekt. Het pad naar de component is dus identiek aan het pad naar de standaardcomponent, behalve dat het pad zich in de map /apps bevindt en niet in de map /libs.

## Voorbeeld {#example}

Stel dat u de commentaarfunctie wilt wijzigen zodat deze overeenkomt met het ontwerp van uw website, door de koptekst van de opmerking te wijzigen zodat de avatar niet meer wordt weergegeven voor opmerkingen. De oplossingen voor het verbergen van de avatar maken gebruik van CSS of bedekken, zoals hier beschreven, header.jsp in de map apps, zodat de HTML die de avatar bevat nooit naar de client wordt verzonden.

Als u opmerkingen wilt bedekken, moet u:

1. [Opmerkingen pagina](overlay-create-comments-page.md)
1. [Notities maken](overlay-create-nodes.md)
1. [De vormgeving wijzigen](overlay-alter-appearance.md)

