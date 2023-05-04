---
title: JSRP - JCR Storage Resource Provider
seo-title: JSRP - JCR Storage Resource Provider
description: JSRP is over het algemeen het meest geschikt voor demonstratie- of ontwikkelomgevingen van één publicatie-instantie en één auteur-instantie
seo-description: JSRP is generally best suited for demonstration or development environments of one publish instance and one author instance
uuid: 358a43c1-4137-4300-8443-c0d7166968ad
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: f5316a73-84e2-4a18-98c1-a384eeaa77cf
role: Admin
exl-id: 73c59497-43fe-4e15-afda-e3cf5264696e
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 1%

---

# JSRP - JCR Storage Resource Provider {#jsrp-jcr-storage-resource-provider}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Info over JSRP {#about-jsrp}

Wanneer AEM Communities JSRP als opslagoptie gebruikt (de standaardinstelling), wordt inhoud van de community opgeslagen in JCR en door de gebruiker gegenereerde inhoud (UGC) is alleen toegankelijk van de auteur of de publicatieinstantie waarnaar deze is gepost.

Wegens de eenvoud van plaatsing, is JSRP over het algemeen best geschikt voor demonstratie of ontwikkelingsmilieu&#39;s van één publiceer instantie en één auteursinstantie.

Zie ook [Kenmerken van SRP-opties](working-with-srp.md#characteristics-of-srp-options) en [Aanbevolen topologieën](topologies.md).

## Configuratie {#configuration}

### JSRP selecteren {#select-jsrp}

Standaard is JSRP de opslagoptie voor UGC.

De [Opslagconfiguratieconsole](srp-config.md) maakt het mogelijk de standaardopslagconfiguratie te selecteren, die aangeeft welke implementatie van SRP moet worden gebruikt.

In de auteursomgeving, om de console van de Configuratie van de Opslag te bereiken

* Vanuit globale navigatie: **[!UICONTROL Tools > Communities > Storage Configuration]**

![chlimage_1-234](assets/chlimage_1-234.png)

* Selecteer **[!UICONTROL JCR Storage Resource Provider (JSRP)]**
* Selecteer **[!UICONTROL Submit]**

### De configuratie publiceren {#publishing-the-configuration}

Terwijl JSRP de standaardconfiguratie is, om ervoor te zorgen dat de identieke configuratie in het publicatiemilieu wordt geplaatst:

* Op auteur:

   * Vanuit globale navigatie: **[!UICONTROL Tools > Deployment > Replication]**
   * Selecteer **[!UICONTROL Activate Tree]**
   * **[!UICONTROL Start Path]**:

      * Bladeren naar `/conf/global/settings/community/srpc/`
   * Selecteer **[!UICONTROL Activate]**


## Gebruikersgegevens beheren {#managing-user-data}

Voor informatie over *gebruikers*, *gebruikersprofielen* en *gebruikersgroepen*, die vaak in de publicatieomgeving worden ingevoerd, gaat u naar

* [Gebruikerssynchronisatie](sync.md)
* [Gebruikers en gebruikersgroepen beheren](users.md)

## Problemen oplossen {#troubleshooting}

### UGC niet zichtbaar in JCR {#ugc-not-visible-in-jcr}

Zorg ervoor JSRP is gevormd om de standaardleverancier te zijn door de configuratie van de opslagoptie te controleren. Standaard is de leverancier van de opslagbron JSRP.

Ga bij alle auteur- en publiceer AEM naar de opslagconfiguratieconsole of controleer de AEM opslagplaats:

* in JCR, als [/conf/global/settings/community](http://localhost:4502/crx/de/index.jsp#/conf/global/settings/community)

   * Bevat geen [srpc](http://localhost:4502/crx/de/index.jsp#/conf/global/settings/community/srpc) node, it means the storage provider is JSRP
   * Als het srpc-knooppunt bestaat en het knooppunt bevat [standaardconfiguratie](http://localhost:4502/crx/de/index.jsp#/conf/global/settings/community/srpc/defaultconfiguration), zouden de eigenschappen van de standaardconfiguratie JSRP moeten bepalen om de standaardleverancier te zijn

### UGC niet zichtbaar op instantie Auteur {#ugc-not-visible-on-author-instance}

Dit is geen bug. Een kenmerk van JSRP is dat communautaire inhoud die in de publicatieomgeving wordt ingevoerd, alleen zichtbaar is in de publicatieomgeving.

### UGC niet zichtbaar bij publicatie-instantie {#ugc-not-visible-on-publish-instance}

Als één enkele publiceer instantie of als een publicatiecluster wordt opgesteld, dan volg instructies voor [UGC niet zichtbaar in JCR](#ugc-not-visible-in-jcr).

Als een publicatielandbouwbedrijf wordt opgesteld, is een kenmerk van JSRP dat de communautaire inhoud slechts op publicatiegeval zichtbaar zal zijn waaraan het werd gepost.

Om ervoor te zorgen dat UGC zichtbaar is vanuit elke publicatie-instantie, is een publicatiecluster vereist.
