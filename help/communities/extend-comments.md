---
title: Component Opmerkingen uitbreiden
seo-title: Extend Comments Component
description: De component Comments uitbreiden om de weergave of het gedrag ervan voor specifieke toepassingen te wijzigen
seo-description: Extend the Comments component to alter its appearance or behavior for specific uses
uuid: 6f439097-b1d0-4e7d-afcf-01d8f43aa866
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: a07a4690-0e47-4a76-84cb-96abdc70b835
exl-id: f6722953-ff71-4fba-b76e-1d566f71f6d5
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 0%

---

# Component Opmerkingen uitbreiden {#extend-comments-component}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

De bedoeling van [verlenging](client-customize.md#extensions) een standaardcomponent is het wijzigen van de weergave of het gedrag van een component voor specifieke toepassingen.

Het pad naar de component is uniek en verwijst naar de standaardcomponent als een superbrontype. Er is minder risico omdat het bereik beperkt is in vergelijking met het mondiale bereik van een componentoverlay.

>[!NOTE]
>
>Een [bedeesd](client-customize.md#overlays) wordt niet ondersteund.

## Voorbeeld {#example}

Stel dat de koptekst van de commentaarcomponent op de ene site van de AEM instantie een andere weergave moet krijgen, terwijl de standaardweergave op een andere site wordt weergegeven. In plaats van de standaardopmerking te bedekken, waardoor de commentaarcomponent voor alle instanties wordt gewijzigd, kunt u beter ervoor zorgen dat er meerdere commentaarcomponenten beschikbaar zijn voor gebruik op verschillende sites.

Om deze oplossing uit te voeren, creeer een nieuwe component die (met voeten treedt) bestaande uitbreidt en het manuscript van Handlebars wijzigt. Het gebied van de site dat de nieuwe opmerkingen gebruikt, kan de uitgebreide versie gebruiken, terwijl de sites die de standaardweergave gebruiken, ongewijzigd blijven.

De commentaarcomponent is eigenlijk één van twee componenten die uit het commentaarsysteem bestaan. Er zijn dus twee onderdelen die moeten worden uitgebreid: *opmerkingen* en *opmerking*. Het script dat moet worden bewerkt, bevindt zich in de *comment *component `header.hbs` bestand, terwijl het bovenliggende bestand *opmerkingen* is wat een auteur daadwerkelijk aan de pagina toevoegt (het opmerkingensysteem).

Als u opmerkingen wilt uitbreiden, moet u:

1. [De componenten maken](extend-create-components.md)
1. [Opmerking toevoegen aan voorbeeldpagina](extend-sample-page.md)
1. [De vormgeving wijzigen](extend-alter-appearance.md)
