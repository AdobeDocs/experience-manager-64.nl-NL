---
title: Berichten configureren
seo-title: Berichten configureren
description: Communityberichten
seo-description: Communityberichten
uuid: 35d98667-a82e-4ed1-b6a1-1ffbbe1d08b5
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 5cb571ae-eeb5-4943-a6b8-92e346e85be2
translation-type: tm+mt
source-git-commit: 9fa89ca34843d41a5ab5711c1090fcc7a1077760
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 0%

---


# Berichten configureren {#configuring-messaging}

## Overzicht {#overview}

De overseineneigenschap voor AEM Communities biedt de capaciteit voor ondertekende plaatsbezoekers (leden) om berichten naar elkaar te verzenden die wanneer ondertekend op de plaats toegankelijk zijn.

Het overseinen wordt toegelaten voor een communautaire plaats door een doos tijdens de verwezenlijking [van de](sites-console.md)communautaire plaats te controleren.

Op deze pagina vindt u informatie over de standaardconfiguratie en mogelijke aanpassingen.

Voor extra informatie voor ontwikkelaars, zie de Hoofdzaak van het [Overseinen](essentials-messaging.md).

## Service voor berichtenverkeer {#messaging-operations-service}

De dienst [van de Verrichtingen van het Overseinen van](http://localhost:4502/system/console/configMgr/com.adobe.cq.social.messaging.client.endpoints.impl.MessagingOperationsServiceImpl) AEM Communities identificeert het eindpunt dat overseinen verwante verzoeken behandelt, de omslagen de dienst voor het opslaan van berichten zou moeten gebruiken, en als de berichten dossiergehechtheid kunnen omvatten, welke dossiertypes worden toegestaan.

Voor communautaire plaatsen die gebruikend de console [van Plaatsen van](sites-console.md)Gemeenschappen worden gecreeerd, bestaat een geval van de dienst reeds, met inbox die aan `/mail/community/inbox`wordt geplaatst.

### Community Messaging Operations Service {#community-messaging-operations-service}

Zoals hieronder getoond, bestaat een configuratie van de dienst voor plaatsen die met de tovenaar [van de](sites-console.md)plaatsverwezenlijking worden gecreeerd. U kunt de configuratie weergeven of bewerken door het potloodpictogram naast de configuratie te selecteren:

![chlimage_1-63](assets/chlimage_1-63.png)

### Nieuwe configuratie {#new-configuration}

Als u een nieuwe configuratie wilt toevoegen, selecteert u het plusteken &#39;**+**&#39; naast de naam van de service:

![chlimage_1-64](assets/chlimage_1-64.png)

* **[!UICONTROL Message Fields Allowlist]**
Hiermee geeft u de eigenschappen op van de component Bericht samenstellen die gebruikers kunnen bewerken en behouden. Als nieuwe formulierelementen worden toegevoegd, moet de element-id desgewenst worden toegevoegd om te worden opgeslagen in SRP. Standaard zijn dit twee items: *onderwerp* en *inhoud*.

* **[!UICONTROL Message box size limit]**
Het maximum aantal bytes in het berichtvenster van elke gebruiker. De standaardwaarde is *1073741824* (1 GB).

* **[!UICONTROL Message count limit]**
Het totale aantal toegestane berichten per gebruiker. De waarde -1 geeft aan dat een onbeperkt aantal berichten is toegestaan, afhankelijk van de groottelimiet van het berichtvenster. De standaardwaarde is *10000* (10 kB).

* **[!UICONTROL Notify delivery failure]**
Als deze optie is ingeschakeld, stuurt u een melding naar de afzender als de berichtlevering bij sommige ontvangers mislukt. Standaard is *ingeschakeld*.

* **[!UICONTROL Failure delivery sender id]**
Naam van afzender die in ontbroken bericht verschijnt levering. De standaardwaarde is *failureNotifier*.

* **[!UICONTROL Failure message template path]**
Absolute weg aan de levering ontbrak de wortel van het berichtmalplaatje. De standaardwaarde is */etc/notification/messaging/default*.

* **[!UICONTROL maxRetries.name]**
Aantal keren dat het opnieuw verzenden van een bericht moet worden uitgevoerd. De standaardwaarde is *3*.

* **[!UICONTROL minWaitBetweenRetries.name]**
Aantal seconden te wachten tussen pogingen om bericht op gebrek opnieuw te verzenden. De standaardwaarde is *100 *(seconden).

* **[!UICONTROL Count update pool size]**
Aantal gezamenlijke draden die voor tellerupdate worden gebruikt. De standaardwaarde is *10*.

* **[!UICONTROL inbox.path.name]**
(*Vereist*) Het pad, relatief ten opzichte van het knooppunt van de gebruiker (/home/users/*gebruikersnaam*), dat moet worden gebruikt voor de **`inbox`** map. Het pad mag NIET eindigen met een slash &#39;/&#39; achter het pad. Standaard is dit */e-mail/inbox* .

* **[!UICONTROL sentitems.path.name]**
(*Vereist*) Het pad, relatief ten opzichte van het knooppunt van de gebruiker (/home/users/*gebruikersnaam*), dat moet worden gebruikt voor de **`senditems`** map. Het pad mag NIET eindigen met een slash &#39;/&#39; achter het pad. Standaard is dit */e-mail/sentimenten* .

* **[!UICONTROL supportAttachments.name]**
Als deze optie is ingeschakeld, kunnen gebruikers bijlagen toevoegen aan hun berichten. Standaard is *ingeschakeld*.

* **[!UICONTROL batchSize.name]**
Aantal berichten aan partij samen voor verzenden wanneer het verzenden naar een grote groep ontvangers. De standaardwaarde is *100*.

* **[!UICONTROL maxTotalAttachmentSize.name]**
Als supportAttachments wordt gecontroleerd, specificeert deze waarde de maximum toegestane totale grootte (in bytes) van alle gehechtheid. De standaardwaarde is *104857600* (100 MB).

* **[!UICONTROL attachmentTypeBlocklist.name]**
Een blocklist met bestandsextensies, vooraf ingesteld op &#39;**.**&quot;, dat zal door het systeem worden verworpen. Als de extensie niet wordt geblokkeerd, is deze toegestaan. Extensies kunnen worden toegevoegd of verwijderd met de pictogrammen &#39;**+**&#39; en &#39;**-**&#39;. Standaard is dit *STANDAARD*.

* **[!UICONTROL allowedAttachmentTypes.name]**
   **(*Handeling vereist*)** Een toegestane lijst met bestandsextensies, het tegenovergestelde van de blocklist. Als u alle bestandsextensies wilt toestaan, met uitzondering van die gebloste extensies, gebruikt u het pictogram &#39;**-**&#39; om één leeg item te verwijderen.

* **[!UICONTROL serviceSelector.name]**
(*Vereist*) een absolute weg (eindpunt) waardoor de dienst (een virtueel middel) wordt aangehaald. De wortel van de gekozen weg moet één inbegrepen in de configuratie van de Wegen *van de* Uitvoering van OSGi config [ , zoals `Apache Sling Servlet/Script Resolver and Error Handler`](http://localhost:4502/system/console/configMgr/org.apache.sling.servlets.resolver.SlingServletResolver), `/bin/`, en `/apps/``/services/`zijn. Om deze configuratie voor het overseineneigenschap van een plaats te selecteren, wordt dit eindpunt verstrekt als **`Service selector`** waarde voor `Message List and Compose Message components` (zie de Eigenschap [van het](configure-messaging.md)Bericht). De standaardwaarde is */bin/messaging* .

* **[!UICONTROL fieldAllowlist.name]**
Gebruik **berichtenlijst**.

>[!CAUTION]
>
>Telkens wanneer een `Messaging Operations Service` configuratie voor uitgeven wordt geopend, als `allowedAttachmentTypes.name` was verwijderd, wordt een lege ingang opnieuw toegevoegd om het bezit configureerbaar te maken. Bij één leeg item worden bestandsbijlagen uitgeschakeld.
>
>Als u alle bestandsextensies wilt toestaan, behalve de extensies die geblokkeerd zijn, gebruikt u het pictogram &#39;**-**&#39; om (opnieuw) de enkele lege invoer te verwijderen voordat u klikt **[!UICONTROL Save]**.

## Problemen oplossen {#troubleshooting}

Één manier om problemen op te lossen is het toelaten van [het zuiveren berichten in het logboek.](../../help/sites-administering/troubleshooting.md)

Zie ook [Loggers en Schrijvers voor de Individuele Diensten](../../help/sites-deploying/configure-logging.md#loggers-and-writers-for-individual-services).

Het te controleren pakket is `com.adobe.cq.social.messaging`.
