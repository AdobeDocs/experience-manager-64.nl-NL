---
title: ASRP - Adobe Storage Resource Provider
seo-title: ASRP - Adobe Storage Resource Provider
description: AEM-gemeenschappen instellen om een relationele database te gebruiken als de algemene opslag
seo-description: AEM-gemeenschappen instellen om een relationele database te gebruiken als de algemene opslag
uuid: 29826b44-633d-4586-8553-cd87ebe269a2
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 86349e4d-29ff-4baa-9fcd-c0ab1f0753e9
translation-type: tm+mt
source-git-commit: 565604feff7fa365a1c6b52b62a0b0eb681bb192

---


# ASRP - Adobe Storage Resource Provider {#asrp-adobe-storage-resource-provider}

## Info over ASRP {#about-asrp}

Wanneer de Gemeenschappen AEM wordt gevormd om ASRP als zijn gemeenschappelijke opslag te gebruiken, is de gebruiker geproduceerde inhoud (UGC) toegankelijk van alle auteur en publiceer instanties zonder de behoefte aan synchronisatie of replicatie.

Zie ook [Kenmerken van Opties](working-with-srp.md#characteristics-of-srp-options) SRP en [Aanbevolen Topologieën](topologies.md).

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

De console [van de Configuratie van de](srp-config.md) Opslag staat voor de selectie van de standaardopslagconfiguratie toe, die identificeert welke implementatie van SRP aan gebruik.

**Op auteur**:

* Vanuit globale navigatie: **[!UICONTROL Extra > Gemeenschappen > Opslagconfiguratie]**

![chlimage_1-310](assets/chlimage_1-310.png)

* Selecteer **[!UICONTROL Adobe Storage Resource Provider (ASRP)]**
* De volgende informatie is afkomstig uit het inrichtingsproces

   * **[!UICONTROL URL datacenter]**

      Afsluiten om het datacenter te selecteren dat door uw accountvertegenwoordiger is geïdentificeerd

   * **[!UICONTROL Standaardrapportsuite]**

      Ga de naam van de standaardrapportreeks in

   * **[!UICONTROL Consumentencode]**

      De sleutel voor de consument invoeren

   * **[!UICONTROL Geheim]**

      De geheime sleutel invoeren

* Selecteer **[!UICONTROL Verzenden]**

De publicatie-instanties voorbereiden:

* [De cryptotoets dupliceren](#replicate-the-crypto-key)
* [De configuratie dupliceren](#publishing-the-configuration)

Na het voorleggen van de configuratie, test de verbinding:

* Selecteer Config **[!UICONTROL voor elke auteur]** testen en publiceer instantie, test de verbinding aan het gegevenscentrum van de console van de Configuratie van de Opslag

* Ten slotte moet u ervoor zorgen dat de site-URL&#39;s voor profielgegevens vanuit het datacenter kunnen worden gerouteerd door [koppelingen](#externalize-links)te extern te maken.

### De cryptosleutel dupliceren {#replicate-the-crypto-key}

De Consumentensleutel en de Geheime Sleutel worden gecodeerd. De sleutel van Granite Crypto moet op alle AEM-instanties hetzelfde zijn, anders worden de sleutels niet correct gecodeerd/gedecodeerd.

Volg de instructies bij [Replicate de Sleutel](deploy-communities.md#replicate-the-crypto-key)van Crypto.

### Koppelingen extern maken {#externalize-links}

Voor correcte profiel en de verbindingen van het profielbeeld, ben zeker om de Verbinding Externalzer [behoorlijk te](../../help/sites-developing/externalizer.md)vormen.

Ben zeker om de domeinen te plaatsen om URLs te zijn die van het Centrum URL van Gegevens (het eindpunt van ASRP) routable zijn.

### Tijdsynchronisatie {#time-synchronization}

Opdat authentificatie met het eindpunt van ASRP om te slagen, moeten de machines die uw ontvangen Gemeenschappen in werking stellen AEM tijd gesynchroniseerd zijn, zoals met het Protocol van de Tijd van het [Netwerk (NTP)](https://www.ntp.org/).

### De configuratie publiceren {#publishing-the-configuration}

ASRP moet als gemeenschappelijke opslag op alle auteur en publiceer instanties worden geïdentificeerd.

De identieke configuratie beschikbaar stellen in de publicatieomgeving:

* **Op auteur**:

   * Navigeer van hoofdmenu aan **[!UICONTROL Hulpmiddelen > Verrichtingen > Replicatie]**
   * Boomstructuur **[!UICONTROL activeren selecteren]**
   * **[!UICONTROL Startpad]**:

      * Bladeren naar `/etc/socialconfig/srpc/`
   * Uitsluitend **[!UICONTROL gewijzigd uitschakelen]**
   * Selecteer **[!UICONTROL Activeren]**


## Upgrade uitvoeren vanaf AEM 6.0 {#upgrading-from-aem}

>[!CAUTION]
>
>Als u ASRP op een gepubliceerde communautaire plaats toelaat, zal om het even welke UGC die reeds in [JCR](jsrp.md) wordt opgeslagen niet meer zichtbaar zijn aangezien er geen synchronisatie van gegevens tussen op-premise opslag en wolkenopslag is.

**`AEM Communities Extension`** voorheen in de sociale gemeenschappen van AEM 6.0 geïntroduceerd als cloudservice. Vanaf AEM 6.1 Communities, is geen wolkenconfiguratie noodzakelijk, eenvoudig uitgezocht ASRP van de console [van de](srp-config.md)opslagconfiguratie.

Vanwege de nieuwe opslagstructuur is het nodig de [upgradeinstructies](upgrade.md#adobe-cloud-storage) te volgen wanneer de overstap van sociale gemeenschappen naar Gemeenschappen wordt verbeterd.

## Gebruikersgegevens beheren {#managing-user-data}

Voor informatie over *gebruikers*, *gebruikersprofielen* en *gebruikersgroepen*, die vaak worden ingevoerd in de publicatieomgeving, gaat u naar

* [Gebruikerssynchronisatie](sync.md)
* [Gebruikers en gebruikersgroepen beheren](users.md)

## Problemen oplossen {#troubleshooting}

### UGC verdwijnt na upgrade {#ugc-disappears-after-upgrade}

Als een upgrade wordt uitgevoerd vanaf een bestaande AEM 6.0-site voor sociale gemeenschappen, moet u de [upgradeinstructies](upgrade.md#adobe-cloud-storage)volgen, anders *lijkt* UGC verloren te gaan.

### Verificatiefouten {#authentication-errors}

Als het ontvangen van authentificatiefouten tegen het Centrum URL van Gegevens, en AEM error.log berichten over lange timestamps bevat, dan verifieer dat tijdsynchronisatie plaatsvindt.

Het wordt geadviseerd om een hulpmiddel zoals het Protocol van de Tijd van het [Netwerk (NTP)](https://www.ntp.org/) te gebruiken om alle auteur AEM en publicatieservers te synchroniseren.

### Nieuwe inhoud wordt niet weergegeven in zoekopdrachten {#new-content-does-not-appear-in-searches}

De Adobe-infrastructuur voor cloudopslag maakt gebruik van *uiteindelijke consistentie* om de schaalings- en prestatiedoelen te helpen bereiken. Daarom is nieuwe inhoud niet direct beschikbaar en kan het enkele seconden duren voordat deze in de zoekresultaten wordt weergegeven.

Terwijl het interval dat invloed heeft op de uiteindelijke consistentie wordt gecontroleerd, neemt u contact op met uw accountvertegenwoordiger als het langer dan een paar seconden duurt voordat nieuwe inhoud in zoekopdrachten wordt weergegeven.

### UGC niet zichtbaar in ASRP {#ugc-not-visible-in-asrp}

Zorg ervoor ASRP is gevormd om de standaardleverancier te zijn door de configuratie van de opslagoptie te controleren. Door gebrek, is de leverancier van het opslagmiddel JSRP, niet ASRP.

Ga bij alle auteurs naar de opslagconfiguratieconsole of controleer de AEM-opslagplaats op alle AEM-exemplaren en publiceer deze:

* In JCR, indien [/etc/socialconfig](http://localhost:4502/crx/de/index.jsp#/etc/socialconfig/)

   * Bevat geen [srpc](http://localhost:4502/crx/de/index.jsp#/etc/socialconfig/srpc) knoop, betekent het de opslagleverancier JSRP is
   * Als de srpc knoop bestaat en knoop [standaardconfiguratie](http://localhost:4502/crx/de/index.jsp#/etc/socialconfig/srpc/defaultconfiguration)bevat, zouden de eigenschappen van de standaardconfiguratie ASRP moeten bepalen om de standaardleverancier te zijn

