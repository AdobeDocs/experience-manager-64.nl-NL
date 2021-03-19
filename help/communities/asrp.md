---
title: ASRP - Adobe Storage Resource Provider
seo-title: ASRP - Adobe Storage Resource Provider
description: AEM Communities instellen om een relationele database te gebruiken als de algemene opslag
seo-description: AEM Communities instellen om een relationele database te gebruiken als de algemene opslag
uuid: 29826b44-633d-4586-8553-cd87ebe269a2
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 86349e4d-29ff-4baa-9fcd-c0ab1f0753e9
role: Beheerder
translation-type: tm+mt
source-git-commit: 75312539136bb53cf1db1de03fc0f9a1dca49791
workflow-type: tm+mt
source-wordcount: '799'
ht-degree: 0%

---


# ASRP - Adobe Storage Resource Provider {#asrp-adobe-storage-resource-provider}

## Info over ASRP {#about-asrp}

Wanneer AEM Communities wordt gevormd om ASRP als zijn gemeenschappelijke opslag te gebruiken, is de gebruiker geproduceerde inhoud (UGC) toegankelijk van alle auteur en publiceer instanties zonder de behoefte aan synchronisatie of replicatie.

Zie ook [Kenmerken van SRP Options](working-with-srp.md#characteristics-of-srp-options) en [Recommended Topologies](topologies.md).

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

Met de [Opslagconfiguratieconsole](srp-config.md) kunt u de standaardopslagconfiguratie selecteren, die aangeeft welke implementatie van SRP moet worden gebruikt.

**Op auteur**:

* Vanuit globale navigatie: **[!UICONTROL Tools > Communities > Storage Configuration]**

![chlimage_1-310](assets/chlimage_1-310.png)

* Selecteer **[!UICONTROL Adobe Storage Resource Provider (ASRP)]**
* De volgende informatie is afkomstig uit het inrichtingsproces

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

* **[!UICONTROL Test Config]** selecteren
voor elke auteur en publiceer instantie, test de verbinding aan het gegevenscentrum van de console van de Configuratie van de Opslag

* Ten slotte moet u ervoor zorgen dat de site-URL&#39;s voor profielgegevens vanuit het datacenter kunnen worden gerouteerd door koppelingen [extern te maken](#externalize-links).

### Repliceer de Crypto Sleutel {#replicate-the-crypto-key}

De Consumentensleutel en de Geheime Sleutel worden gecodeerd. De sleutels worden alleen correct gecodeerd/gedecodeerd als de primaire Crypto-sleutel van Granite op alle AEM gelijk is.

Volg de instructies bij [Repliceer Crypto Key](deploy-communities.md#replicate-the-crypto-key).

### Koppelingen {#externalize-links} extern maken

Voor correcte profiel en de verbindingen van het profielbeeld, ben zeker om [te vormen de Verbinding Externalzer](../../help/sites-developing/externalizer.md).

Ben zeker om de domeinen te plaatsen om URLs te zijn die van het Centrum URL van Gegevens (het eindpunt van ASRP) routable zijn.

### Tijdsynchronisatie {#time-synchronization}

Opdat de authentificatie met het eindpunt van ASRP succesvol is, moeten de machines die uw ontvangen AEM Communities in werking stellen tijd gesynchroniseerd zijn, zoals met [het Protocol van de Tijd van het Netwerk (NTP)](https://www.ntp.org/).

### De configuratie {#publishing-the-configuration} publiceren

ASRP moet als gemeenschappelijke opslag op alle auteur en publiceer instanties worden geïdentificeerd.

De identieke configuratie beschikbaar stellen in de publicatieomgeving:

* **Op auteur**:

   * Navigeer van hoofdmenu aan **[!UICONTROL Tools > Operations > Replication]**
   * Selecteer **[!UICONTROL Activate Tree]**
   * **[!UICONTROL Start Path]**:

      * Bladeren naar `/etc/socialconfig/srpc/`
   * **[!UICONTROL Only Modified]** uitschakelen
   * Selecteer **[!UICONTROL Activate]**


## Bijwerken vanaf AEM 6.0 {#upgrading-from-aem}

>[!CAUTION]
>
>Als u ASRP op een gepubliceerde communautaire plaats toelaat, zal om het even welke UGC die reeds in [JCR](jsrp.md) wordt opgeslagen niet meer zichtbaar zijn aangezien er geen synchronisatie van gegevens tussen op-premise opslag en wolkenopslag is.

**`AEM Communities Extension`** werd eerder in AEM 6.0 sociale gemeenschappen geïntroduceerd als cloudservice. Vanaf AEM 6.1 Communities is geen cloudconfiguratie nodig. Selecteer eenvoudig ASRP in de [opslagconfiguratieconsole](srp-config.md).

Vanwege de nieuwe opslagstructuur is het nodig om de [upgrade](upgrade.md#adobe-cloud-storage) instructies te volgen wanneer u een upgrade uitvoert van sociale gemeenschappen naar Gemeenschappen.

## Gebruikersgegevens {#managing-user-data} beheren

Voor informatie over *gebruikers*, *gebruikersprofielen* en *gebruikersgroepen*, vaak ingevoerd in de publicatieomgeving, gaat u naar

* [Gebruikerssynchronisatie](sync.md)
* [Gebruikers en gebruikersgroepen beheren](users.md)

## Problemen oplossen {#troubleshooting}

### UGC verdwijnt na upgrade {#ugc-disappears-after-upgrade}

Als een upgrade wordt uitgevoerd vanaf een bestaande AEM 6.0-site voor de sociale gemeenschap, moet u de [upgrade-instructies](upgrade.md#adobe-cloud-storage) volgen. Anders wordt *weergegeven* om te worden verloren.

### Verificatiefouten {#authentication-errors}

Als het ontvangen van authentificatiefouten tegen het Centrum URL van Gegevens, en AEM error.log berichten over stabiele timestamps bevat, dan verifieer dat tijdsynchronisatie plaatsvindt.

Het wordt aanbevolen een hulpprogramma zoals [Network Time Protocol (NTP)](https://www.ntp.org/) te gebruiken om alle AEM auteur- en publicatieservers op tijd te synchroniseren.

### Nieuwe inhoud wordt niet weergegeven in zoekopdrachten {#new-content-does-not-appear-in-searches}

De Adobe-infrastructuur voor cloudopslag gebruikt *uiteindelijke consistentie* om de schaalings- en prestatiedoelstellingen te helpen bereiken. Daarom is nieuwe inhoud niet direct beschikbaar en kan het enkele seconden duren voordat deze in de zoekresultaten wordt weergegeven.

Terwijl het interval dat invloed heeft op de uiteindelijke consistentie wordt gecontroleerd, neemt u contact op met uw accountvertegenwoordiger als het langer dan een paar seconden duurt voordat nieuwe inhoud in zoekopdrachten wordt weergegeven.

### UGC niet zichtbaar in ASRP {#ugc-not-visible-in-asrp}

Zorg ervoor ASRP is gevormd om de standaardleverancier te zijn door de configuratie van de opslagoptie te controleren. Door gebrek, is de leverancier van het opslagmiddel JSRP, niet ASRP.

Ga bij alle auteur- en publiceer AEM naar de opslagconfiguratieconsole of controleer de AEM opslagplaats:

* In JCR, als [/etc/socialconfig](http://localhost:4502/crx/de/index.jsp#/etc/socialconfig/)

   * Bevat geen [srpc](http://localhost:4502/crx/de/index.jsp#/etc/socialconfig/srpc)-knooppunt, het betekent dat de opslagprovider JSRP is
   * Als het srpc-knooppunt bestaat en knooppunt [default configuration](http://localhost:4502/crx/de/index.jsp#/etc/socialconfig/srpc/defaultconfiguration) bevat, moeten de eigenschappen van de standaardconfiguratie ASRP definiëren als de standaardprovider

