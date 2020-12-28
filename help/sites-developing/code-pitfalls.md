---
title: Codevalkuilen
seo-title: Codevalkuilen
description: Gemeenschappelijke coderingsvalkuilen die worden vermeden bij het ontwikkelen voor AEM
seo-description: Gemeenschappelijke coderingsvalkuilen die worden vermeden bij het ontwikkelen voor AEM
uuid: e7413bdc-4889-45ff-bdcb-b0893d33a3b7
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: best-practices
discoiquuid: 01362026-a696-4a5d-94e9-ea784eaa6e4b
translation-type: tm+mt
source-git-commit: 835f1ba1f196c6c6303019f0cc310cad850e1682
workflow-type: tm+mt
source-wordcount: '99'
ht-degree: 0%

---


# Codevalkuilen{#code-pitfalls}

## Bindingen in Java-code {#avoid-sling-bindings-in-java-code} vermijden

Het verkopen Bindingen zijn een ongepaste manier om tot de dienst in 90% van gevallen toegang te krijgen. In plaats daarvan moet u *@Reference* of *@Inject* annotaties gebruiken.

## Vermijd thread.interrupt in code {#avoid-thread-interrupt-in-java-code} van Java

*Thread.* onderbrekt gevaarlijk omdat het dossiers, met inbegrip van Lucene- dossiers en blijvende geheim voorgeheugendossiers, wanneer geroepen op het verkeerde ogenblik kan sluiten.

## Vermijd het mengen van de synchronisatie van Java met ReadWriteLocks {#avoid-mixing-java-synchronization-with-readwritelocks}

Dit kan tot een rassenvoorwaarde leiden waarin de code uiteindelijk zal blokkeren.
