---
title: ASRP - Adobe Storage Resource Provider
seo-title: ASRP - Adobe Storage Resource Provider
description: AEM Communities instellen om een relationele database te gebruiken als de algemene opslag
seo-description: Set up AEM Communities to use a relational database as its common store
uuid: 29826b44-633d-4586-8553-cd87ebe269a2
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 86349e4d-29ff-4baa-9fcd-c0ab1f0753e9
role: Admin
exl-id: 136c0913-c8b8-451d-bb28-3c3285c172a1
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '816'
ht-degree: 0%

---

# ASRP - Adobe Storage Resource Provider {#asrp-adobe-storage-resource-provider}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Info over ASRP {#about-asrp}

Wanneer AEM Communities wordt gevormd om ASRP als zijn gemeenschappelijke opslag te gebruiken, is de gebruiker geproduceerde inhoud (UGC) toegankelijk van alle auteur en publiceer instanties zonder de behoefte aan synchronisatie of replicatie.

Zie ook [Kenmerken van SRP-opties](working-with-srp.md#characteristics-of-srp-options) en [Aanbevolen topologieën](topologies.md).

## Vereisten {#requirements}

Een extra vergunning wordt vereist voor het gebruik van ASRP.

Als u uw AEM Communities-site wilt configureren voor gebruik van ASRP voor UGC, neemt u contact op met uw accountvertegenwoordiger voor:

* Het Centrum URL van gegevens (adres van het eindpunt van ASRP)
* Consumentencode
* Geheime sleutel
* ID(&#39;s) van rapportsuite

De consument en geheime sleutels worden gedeeld over alle rapportseries voor een bedrijf. Er is één rapportsuite per huurder.

## Configuratie {#configuration}

### Selecteer ASRP {#select-asrp}

De [Opslagconfiguratieconsole](srp-config.md) maakt het mogelijk de standaardopslagconfiguratie te selecteren, die aangeeft welke implementatie van SRP moet worden gebruikt.

**Op auteur**:

* Vanuit globale navigatie: **[!UICONTROL Tools > Communities > Storage Configuration]**

![chlimage_1-310](assets/chlimage_1-310.png)

* Selecteer **[!UICONTROL Adobe Storage Resource Provider (ASRP)]**
* De volgende informatie is afkomstig van het inrichtingsproces

   * **[!UICONTROL Data Center URL]**

      Afsluiten om het datacenter te selecteren dat door uw accountvertegenwoordiger is geïdentificeerd

   * **[!UICONTROL Default Report Suite]**

      Ga de naam van de standaardrapportreeks in

   * **[!UICONTROL Consumer Key]**

      De sleutel voor de consument invoeren

   * **[!UICONTROL Secret]**

      De geheime sleutel invoeren

* Selecteer **[!UICONTROL Submit]**

De publicatie-instanties voorbereiden:

* [De cryptotoets dupliceren](#replicate-the-crypto-key)
* [De configuratie dupliceren](#publishing-the-configuration)

Na het voorleggen van de configuratie, test de verbinding:

* Selecteren **[!UICONTROL Test Config]**
voor elke auteur en publiceer instantie, test de verbinding aan het gegevenscentrum van de console van de Configuratie van de Opslag

* Tot slot moet u ervoor zorgen dat de site-URL&#39;s voor profielgegevens vanuit het datacenter kunnen worden gerouteerd door [externe koppelingen](#externalize-links).

### De cryptosleutel dupliceren {#replicate-the-crypto-key}

De Consumentensleutel en de Geheime Sleutel worden gecodeerd. De sleutels worden alleen correct gecodeerd/gedecodeerd als de primaire Crypto-sleutel van Granite op alle AEM gelijk is.

Volg de instructies op [De cryptosleutel dupliceren](deploy-communities.md#replicate-the-crypto-key).

### Koppelingen extern maken {#externalize-links}

Voor correcte profiel- en profielafbeeldingskoppelingen moet u controleren of deze correct zijn [Vorm de Verbinding Externalzer](../../help/sites-developing/externalizer.md).

Ben zeker om de domeinen te plaatsen om URLs te zijn die van het Centrum URL van Gegevens (het eindpunt van ASRP) routable zijn.

### Tijdsynchronisatie {#time-synchronization}

Om authentificatie met het eindpunt van ASRP te slagen, moeten de machines die uw ontvangen AEM Communities in werking stellen tijd gesynchroniseerd zijn, zoals met [Netwerktijdprotocol (NTP)](https://www.ntp.org/).

### De configuratie publiceren {#publishing-the-configuration}

ASRP moet als gemeenschappelijke opslag op alle auteur en publiceer instanties worden geïdentificeerd.

De identieke configuratie beschikbaar stellen in de publicatieomgeving:

* **Op auteur**:

   * Navigeren van hoofdmenu naar **[!UICONTROL Tools > Operations > Replication]**
   * Selecteer **[!UICONTROL Activate Tree]**
   * **[!UICONTROL Start Path]**:

      * Bladeren naar `/etc/socialconfig/srpc/`
   * Uitschakelen **[!UICONTROL Only Modified]**
   * Selecteer **[!UICONTROL Activate]**


## Upgrade uitvoeren vanaf AEM 6.0 {#upgrading-from-aem}

>[!CAUTION]
>
>Als u ASRP op een gepubliceerde communautaire plaats toelaat, om het even welke UGC die reeds in wordt opgeslagen [JCR](jsrp.md) niet meer zichtbaar is omdat er geen synchronisatie van gegevens plaatsvindt tussen on-premise opslag en cloudopslag.

**`AEM Communities Extension`** werd eerder in AEM 6.0 sociale gemeenschappen geïntroduceerd als cloudservice. Vanaf AEM 6.1 Gemeenschappen is geen wolkenconfiguratie noodzakelijk, eenvoudig uitgezocht ASRP van [opslagconfiguratieconsole](srp-config.md).

Gezien de nieuwe opslagstructuur is het noodzakelijk de [upgrade](upgrade.md#adobe-cloud-storage) instructies bij de opwaardering van sociale gemeenschappen naar gemeenschappen.

## Gebruikersgegevens beheren {#managing-user-data}

Voor informatie over *gebruikers*, *gebruikersprofielen* en *gebruikersgroepen*, die vaak in de publicatieomgeving worden ingevoerd, gaat u naar

* [Gebruikerssynchronisatie](sync.md)
* [Gebruikers en gebruikersgroepen beheren](users.md)

## Problemen oplossen {#troubleshooting}

### UGC verdwijnt na upgrade {#ugc-disappears-after-upgrade}

Als u een upgrade uitvoert van een bestaande AEM 6.0-site voor de sociale gemeenschap, moet u de [upgradeinstructies](upgrade.md#adobe-cloud-storage), anders zal UGC *verschijnen* om verloren te gaan.

### Verificatiefouten {#authentication-errors}

Als het ontvangen van authentificatiefouten tegen het Centrum URL van Gegevens, en AEM error.log berichten over stabiele timestamps bevat, dan verifieer dat tijdsynchronisatie plaatsvindt.

U wordt aangeraden een hulpprogramma te gebruiken, zoals de [Netwerktijdprotocol (NTP)](https://www.ntp.org/) om alle AEM auteur- en publicatieservers te synchroniseren.

### Nieuwe inhoud wordt niet weergegeven in zoekopdrachten {#new-content-does-not-appear-in-searches}

De Adobe-cloudopslaginfrastructuur gebruikt *uiteindelijke consistentie* helpen zijn schaalings- en prestatiedoelstellingen te bereiken. Daarom is nieuwe inhoud niet direct beschikbaar en kan het enkele seconden duren voordat deze in de zoekresultaten wordt weergegeven.

Terwijl het interval dat invloed heeft op de uiteindelijke consistentie wordt gecontroleerd, neemt u contact op met uw accountvertegenwoordiger als het langer dan een paar seconden duurt voordat nieuwe inhoud in zoekopdrachten wordt weergegeven.

### UGC niet zichtbaar in ASRP {#ugc-not-visible-in-asrp}

Zorg ervoor ASRP is gevormd om de standaardleverancier te zijn door de configuratie van de opslagoptie te controleren. Door gebrek, is de leverancier van het opslagmiddel JSRP, niet ASRP.

Ga bij alle auteur- en publiceer AEM naar de opslagconfiguratieconsole of controleer de AEM opslagplaats:

* In JCR, als [/etc/socialconfig](http://localhost:4502/crx/de/index.jsp#/etc/socialconfig/)

   * Bevat geen [srpc](http://localhost:4502/crx/de/index.jsp#/etc/socialconfig/srpc) node, it means the storage provider is JSRP
   * Als het srpc-knooppunt bestaat en het knooppunt bevat [standaardconfiguratie](http://localhost:4502/crx/de/index.jsp#/etc/socialconfig/srpc/defaultconfiguration), zouden de eigenschappen van de standaardconfiguratie ASRP moeten bepalen om de standaardleverancier te zijn
