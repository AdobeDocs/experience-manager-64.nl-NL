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
source-git-commit: 13d890d08a032fe4eef1dac793dcf2a3e682a52c

---


# Berichten configureren {#configuring-messaging}

## Overzicht {#overview}

De berichtenfunctie voor AEM Communities biedt de mogelijkheid voor ingetekende sitebezoekers (leden) om berichten naar elkaar te verzenden die toegankelijk zijn wanneer ze zich op de site hebben aangemeld.

Het overseinen wordt toegelaten voor een communautaire plaats door een doos tijdens de verwezenlijking [van de](sites-console.md)communautaire plaats te controleren.

Op deze pagina vindt u informatie over de standaardconfiguratie en mogelijke aanpassingen.

Voor extra informatie voor ontwikkelaars, zie de Hoofdzaak van het [Overseinen](essentials-messaging.md).

## Service voor berichtenverkeer {#messaging-operations-service}

De dienst [van de Verrichtingen van het Overseinen van](http://localhost:4502/system/console/configMgr/com.adobe.cq.social.messaging.client.endpoints.impl.MessagingOperationsServiceImpl) Gemeenschappen AEM identificeert het eindpunt dat overseinengerelateerde verzoeken behandelt, de omslagen de dienst voor het opslaan van berichten zou moeten gebruiken, en als de berichten dossiergehechtheid kunnen omvatten, welke dossiertypes worden toegestaan.

Voor communautaire plaatsen die gebruikend de console [van Plaatsen van](sites-console.md)Gemeenschappen worden gecreeerd, bestaat een geval van de dienst reeds, met inbox die aan `/mail/community/inbox`wordt geplaatst.

### Community Messaging Operations Service {#community-messaging-operations-service}

Zoals hieronder getoond, bestaat een configuratie van de dienst voor plaatsen die met de tovenaar [van de](sites-console.md)plaatsverwezenlijking worden gecreeerd. U kunt de configuratie weergeven of bewerken door het potloodpictogram naast de configuratie te selecteren:

![chlimage_1-63](assets/chlimage_1-63.png)

### Nieuwe configuratie {#new-configuration}

Als u een nieuwe configuratie wilt toevoegen, selecteert u het plusteken &#39;**+**&#39; naast de naam van de service:

![chlimage_1-64](assets/chlimage_1-64.png)

* **[!UICONTROL Whitelist van de Gebieden van het bericht]** specificeert de eigenschappen van de samenstellen de componentengebruikers van het Bericht kunnen uitgeven en voortzetten. Als nieuwe formulierelementen worden toegevoegd, moet de element-id desgewenst worden toegevoegd om te worden opgeslagen in SRP. Standaard zijn dit twee items: *onderwerp* en *inhoud*.

* **[!UICONTROL Grootte van berichtvenster is beperkt]** Het maximum aantal bytes in het berichtvenster van elke gebruiker. De standaardwaarde is *1073741824* (1 GB).

* **[!UICONTROL Limiet]** voor aantal berichten Het totale aantal berichten dat per gebruiker is toegestaan. De waarde -1 geeft aan dat een onbeperkt aantal berichten is toegestaan, afhankelijk van de groottelimiet van het berichtvenster. De standaardwaarde is *10000* (10 kB).

* **[!UICONTROL De leveringsmislukking]** van het berichtIndien gecontroleerd, bericht afzender als de berichtlevering aan sommige ontvangers ontbreekt. Standaard is *ingeschakeld*.

* **[!UICONTROL Identiteitskaart]** Naam van afzender van mislukte levering die in levering ontbroken bericht verschijnt. De standaardwaarde is *failureNotifier*.

* **[!UICONTROL Het weg van het berichtmalplaatje]** van de mislukking Absolute weg aan de levering ontbrak de wortel van het berichtmalplaatje. De standaardwaarde is */etc/notification/messaging/default*.

* **[!UICONTROL maxRetries.name]** Aantal keren om het opnieuw verzenden van berichten te proberen die niet kunnen worden geleverd. De standaardwaarde is *3*.

* **[!UICONTROL minWaitBetweenRetries.name]** Aantal seconden om tussen pogingen te wachten om bericht op mislukking opnieuw te verzenden. De standaardwaarde is *100 *(seconden).

* **[!UICONTROL De grootte]** van de de updatepool van de telling Aantal gezamenlijke draden die voor tellerupdate worden gebruikt. De standaardwaarde is *10*.

* **[!UICONTROL inbox.path.name]**(*Required*) The path, relative to the user&#39;s node (/home/users/*username*), to use for the **`inbox`** folder. Het pad mag NIET eindigen met een slash &#39;/&#39; achter het pad. Standaard is dit */e-mail/inbox* .

* **[!UICONTROL sentitems.path.name]**(*Required*) De weg, met betrekking tot de knoop van de gebruiker (/home/users/*username*), aan gebruik voor de **`senditems`** omslag. Het pad mag NIET eindigen met een slash &#39;/&#39; achter het pad. Standaard is dit */e-mail/sentimenten* .

* **[!UICONTROL supportAttachments.name]** Als deze optie is ingeschakeld, kunnen gebruikers bijlagen toevoegen aan hun berichten. Standaard is *ingeschakeld*.

* **[!UICONTROL batchSize.name]** Aantal berichten aan partij samen voor verzenden wanneer het verzenden naar een grote groep ontvangers. De standaardwaarde is *100*.

* **[!UICONTROL maxTotalAttachmentSize.name]** Als supportAttachments wordt gecontroleerd, specificeert deze waarde de maximum toegestane totale grootte (in bytes) van alle gehechtheid. De standaardwaarde is *104857600* (100 MB).

* **[!UICONTROL BijlageTypeBlacklist.name]** Een zwarte lijst met bestandsextensies, voorafgegaan door &#39;**.**&quot;, dat zal door het systeem worden verworpen. Als de extensie niet op de zwarte lijst staat, is deze toegestaan. Extensies kunnen worden toegevoegd of verwijderd met de pictogrammen &#39;**+**&#39; en &#39;**-**&#39;. Standaard is dit *STANDAARD*.

* **[!UICONTROL allowedAttachmentTypes.name]**
   **(*Actie vereist*)** Een whitelist van bestandsextensies, het tegenovergestelde van de zwarte lijst. Als u alle bestandsextensies wilt toestaan, behalve de extensies die op de zwarte lijst staan, gebruikt u het pictogram &#39;**-**&#39; om één leeg item te verwijderen.

* **[!UICONTROL serviceSelector.name]**(*Vereist*) Een absolute weg (eindpunt) waardoor de dienst (een virtueel middel) wordt aangehaald. De wortel van de gekozen weg moet één inbegrepen in de configuratie van de Wegen *van de* Uitvoering van OSGi config [ , zoals `Apache Sling Servlet/Script Resolver and Error Handler`](http://localhost:4502/system/console/configMgr/org.apache.sling.servlets.resolver.SlingServletResolver), `/bin/`, en `/apps/``/services/`zijn. Om deze configuratie voor het overseineneigenschap van een plaats te selecteren, wordt dit eindpunt verstrekt als **`Service selector`** waarde voor `Message List and Compose Message components` (zie de Eigenschap [van het](configure-messaging.md)Bericht). De standaardwaarde is */bin/messaging* .

* **[!UICONTROL fieldWhitelist.name]** Use **Message Fields Whitelist**.

>[!CAUTION]
>
>Telkens wanneer een `Messaging Operations Service` configuratie voor uitgeven wordt geopend, als `allowedAttachmentTypes.name` was verwijderd, wordt een lege ingang opnieuw toegevoegd om het bezit configureerbaar te maken. Bij één leeg item worden bestandsbijlagen uitgeschakeld.
>
>Als u alle bestandsextensies wilt toestaan, met uitzondering van extensies die op de zwarte lijst staan, gebruikt u het pictogram &#39;**-**&#39; om (opnieuw) één leeg item te verwijderen voordat u op **[!UICONTROL Opslaan]** klikt.

## Problemen oplossen {#troubleshooting}

Één manier om problemen op te lossen is het toelaten van [het zuiveren berichten in het logboek.](../../help/sites-administering/troubleshooting.md)

Zie ook [Loggers en Schrijvers voor de Individuele Diensten](../../help/sites-deploying/configure-logging.md#loggers-and-writers-for-individual-services).

Het te controleren pakket is `com.adobe.cq.social.messaging`.
