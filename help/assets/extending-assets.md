---
title: Elementen aanpassen en uitbreiden
description: Leer manieren waarop u Asset Share en Asset Editor kunt aanpassen en uitbreiden, waarmee gebruikers een specifiek op maat gemaakte interface en een set functies krijgen.
contentOwner: AG
feature: Developer Tools
role: Developer
exl-id: 0291690b-874a-483d-901f-f02cb6d8ab28
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 0%

---

# Elementen aanpassen en uitbreiden {#customizing-and-extending-assets}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

De Asset Editor is het belangrijkste toegangspunt waarmee gebruikers van een Adobe Enterprise Manager-website de digitale middelen in uw opslagplaats kunnen zoeken, bekijken en bewerken.

Als [!DNL Experience Manager] ontwikkelaar, kunt u de Redacteur van Activa op een aantal manieren aanpassen en uitbreiden, presenterend gebruikers met een specifiek op maat gemaakte interface en een reeks functionaliteit.

De volgende aspecten van de functionaliteit kunnen worden aangepast of verbeterd:

* [Editor van element uitbreiden](asseteditorx.md)
* [Zoeken naar elementen uitbreiden](searchx.md)
* [Middelen verwerken met behulp van mediafuncties en workflows](media-handlers.md)
* [Elementen integreren met activiteitsstroom](extending-activity-stream.md)
* [Ontwikkeling van proxy&#39;s](proxy.md)
* [Beste praktijken voor het Vormen ImageMagick](best-practices-for-imagemagick.md)

## De vormgeving aanpassen {#customizing-the-look-and-feel}

De volgende aspecten van de vormgeving van de Asset Editor kunnen worden aangepast:

* Logo: U kunt het logo van uw eigen organisatie aan de interface toevoegen.
* Kleuren en lettertypen: U kunt de kleuren en lettertypen wijzigen die in de interface worden gebruikt.
* HTML-code: Voor grondiger aanpassing kunt u de onderliggende code van HTML veranderen die de interfaces bepaalt.

## Uitvoeringen aanpassen {#customizing-renditions}

In [!DNL Experience Manager Assets] terminologie een uitvoering is de vorm waarin een actief wordt gepresenteerd. In het algemeen kan een bepaald actief meerdere uitvoeringen hebben. Zo kan een kleurenafbeelding met volledige kleuren bijvoorbeeld een uitvoering in de oorspronkelijke grootte hebben, een andere bij een verkleind formaat en een andere afbeelding die wordt verkleind en omgezet in grijswaarden.

De uitvoeringen waarin een bepaald element beschikbaar is, kunnen worden aangepast en nieuwe uitvoeringen worden gemaakt.
