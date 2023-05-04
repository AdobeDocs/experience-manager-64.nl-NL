---
title: Naamconventies voor het testen van elementen
seo-title: Naming conventions for assets
description: Nodes in de opslagplaats zijn onderworpen aan naamconventies van de Java Content Repository. Adobe Experience Manager stelt echter andere conventies op voor de naam van elementknooppunten.
seo-description: Nodes in the repository are subject to naming conventions of the Java Content Repository. However, Adobe Experience Manager imposes further conventions for the name of asset nodes.
uuid: 6b622a60-90e8-461e-9b67-42c11c7038f9
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: authoring
content-type: reference
discoiquuid: 55e66c66-0120-4ed4-94c5-d65a434bb59b
exl-id: 3dc38c37-f2a0-44f5-90f6-fee8c6f84ff4
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 0%

---

# Naamconventies voor het testen van elementen{#naming-conventions-for-assets-testing}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Knooppunten in de gegevensopslagruimte zijn onderworpen aan de naamconventies van de [Java Content Repository](/help/sites-developing/the-basics.md#java-content-repository). Adobe Experience Manager stelt echter andere conventies op voor de naam van elementknooppunten.

## Klassieke interface {#classic-ui}

De klassieke gebruikersinterface legt strengere beperkingen op:

* Valideert de elementnaam wanneer een expliciete knooppuntnaam:

   * er is een elementtitel opgegeven voor conversie naar de knooppuntnaam
   * een expliciete nodenaam wordt verstrekt

* Geldige tekens (alleen deze tekens zijn geldig wanneer een element wordt gemaakt vanuit de klassieke interface):

   * &#39;a&#39; naar &#39;z&#39;
   * &#39;A&#39; naar &#39;Z&#39;
   * 0 tot en met 9
   * _ (onderstrepingsteken)
   * `-` (streepje/min)
