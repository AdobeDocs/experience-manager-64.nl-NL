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
role: Administrator
exl-id: 0e906f67-b908-4c41-b243-e4f90100ce5d
translation-type: tm+mt
source-git-commit: bd94d3949f0117aa3e1c9f0e84f7293a5d6b03b4
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 0%

---

# Het vormen Overseinen {#configuring-messaging}

## Overzicht {#overview}

Met de communicatiefunctie voor AEM Communities kunnen bezoekers van de aangemelde site (leden) berichten naar elkaar sturen die toegankelijk zijn wanneer ze zich op de site hebben aangemeld.

Het overseinen wordt toegelaten voor een communautaire plaats door een doos tijdens [de verwezenlijking van de communautaire plaats](sites-console.md) te controleren.

Op deze pagina vindt u informatie over de standaardconfiguratie en mogelijke aanpassingen.

Voor extra informatie voor ontwikkelaars, zie [Hoofdzaak van het Overseinen](essentials-messaging.md).

## Service voor berichtenverkeer {#messaging-operations-service}

[AEM Communities de Dienst van de Verrichtingen van het Overseinen van het Overseinen ](http://localhost:4502/system/console/configMgr/com.adobe.cq.social.messaging.client.endpoints.impl.MessagingOperationsServiceImpl) identificeert het eindpunt dat overseinen verwante verzoeken behandelt, de omslagen de dienst voor het opslaan van berichten zou moeten gebruiken, en als de berichten dossiergehechtheid kunnen omvatten, welke dossiertypes worden toegestaan.

Voor gemeenschapssites die zijn gemaakt met de [Community Sites console](sites-console.md), bestaat al een instantie van de service, met de inbox ingesteld op `/mail/community/inbox`.

### Community Messaging Operations Service {#community-messaging-operations-service}

Zoals hieronder wordt weergegeven, bestaat er een configuratie van de service voor sites die zijn gemaakt met de wizard [Site maken](sites-console.md). U kunt de configuratie weergeven of bewerken door het potloodpictogram naast de configuratie te selecteren:

![chlimage_1-63](assets/chlimage_1-63.png)

### Nieuwe configuratie {#new-configuration}

Als u een nieuwe configuratie wilt toevoegen, selecteert u de plusknop &#39;**+**&#39; naast de naam van de service:

![chlimage_1-64](assets/chlimage_1-64.png)

* **[!UICONTROL Message Fields Allowlist]**
Hiermee geeft u de eigenschappen op van de component Bericht samenstellen die gebruikers kunnen bewerken en behouden. Als nieuwe formulierelementen worden toegevoegd, moet de element-id desgewenst worden toegevoegd om te worden opgeslagen in SRP. Standaard zijn dit twee items: 
** subjectand  *content*.

* **[!UICONTROL Message box size limit]**
Het maximum aantal bytes in het berichtvenster van elke gebruiker. Standaard is 
*1073741824* (1 GB).

* **[!UICONTROL Message count limit]**
Het totale aantal toegestane berichten per gebruiker. De waarde -1 geeft aan dat een onbeperkt aantal berichten is toegestaan, afhankelijk van de groottelimiet van het berichtvenster. Standaard is 
*10000* (10 duodecies).

* **[!UICONTROL Notify delivery failure]**
Als deze optie is ingeschakeld, stuurt u een melding naar de afzender als de berichtlevering bij sommige ontvangers mislukt. Standaard is 
*ingeschakeld*.

* **[!UICONTROL Failure delivery sender id]**
Naam van afzender die in ontbroken bericht verschijnt levering. Standaard is 
*errorNotifier*.

* **[!UICONTROL Failure message template path]**
Absolute weg aan de levering ontbrak de wortel van het berichtmalplaatje. Standaard is 
*/etc/notification/messaging/default*.

* **[!UICONTROL maxRetries.name]**
Aantal keren dat het opnieuw verzenden van een bericht moet worden uitgevoerd. Standaard is 
*3*.

* **[!UICONTROL minWaitBetweenRetries.name]**
Aantal seconden te wachten tussen pogingen om bericht op gebrek opnieuw te verzenden. De standaardwaarde is *100 *(seconden).

* **[!UICONTROL Count update pool size]**
Aantal gezamenlijke draden die voor tellerupdate worden gebruikt. Standaard is 
*10*.

* **[!UICONTROL inbox.path.name]**
(
*Vereist*) Het pad, relatief ten opzichte van het knooppunt van de gebruiker (/home/users/*gebruikersnaam*), dat voor de  **`inbox`** map moet worden gebruikt. Het pad mag NIET eindigen met een slash &#39;/&#39; achter het pad. De standaardwaarde is */mail/inbox*.

* **[!UICONTROL sentitems.path.name]**
(
*Vereist*) Het pad, relatief ten opzichte van het knooppunt van de gebruiker (/home/users/*gebruikersnaam*), dat voor de  **`senditems`** map moet worden gebruikt. Het pad mag NIET eindigen met een slash &#39;/&#39; achter het pad. De standaardwaarde is */mail/sentitems*.

* **[!UICONTROL supportAttachments.name]**
Als deze optie is ingeschakeld, kunnen gebruikers bijlagen toevoegen aan hun berichten. Standaard is 
*ingeschakeld*.

* **[!UICONTROL batchSize.name]**
Aantal berichten aan partij samen voor verzenden wanneer het verzenden naar een grote groep ontvangers. Standaard is 
*100*.

* **[!UICONTROL maxTotalAttachmentSize.name]**
Als supportAttachments wordt gecontroleerd, specificeert deze waarde de maximum toegestane totale grootte (in bytes) van alle gehechtheid. Standaard is 
*104857600*  (100 MB).

* **[!UICONTROL attachmentTypeBlocklist.name]**
Een lijst van gewezen personen met bestandsextensies, vooraf ingesteld op &#39;
**.**&quot;, dat zal door het systeem worden verworpen. Als de extensie niet wordt gevoegd op lijst van gewenste personen, is deze toegestaan. Extensies kunnen worden toegevoegd of verwijderd met de pictogrammen &#39;**+**&#39; en &#39;**-**&#39;. De standaardwaarde is *DEFAULT*.

* **[!UICONTROL allowedAttachmentTypes.name]**

   **(*Actie vereist*)** Een lijst van gewenste personen van dossieruitbreidingen, het tegenovergestelde van de lijst van gewezen personen. Als u alle bestandsextensies wilt toestaan, behalve de gevoegde op lijst van gewenste personen extensies, gebruikt u het pictogram &#39;**-**&#39; om één leeg item te verwijderen.

* **[!UICONTROL serviceSelector.name]**
(*Vereist*) een absolute weg (eindpunt) waardoor de dienst (een virtueel middel) wordt aangehaald. De wortel van de gekozen weg moet één inbegrepen in *de configuratieplaatsen van Wegen van de Uitvoering* van OSGi config [ `Apache Sling Servlet/Script Resolver and Error Handler`](http://localhost:4502/system/console/configMgr/org.apache.sling.servlets.resolver.SlingServletResolver), zoals `/bin/`, `/apps/`, en `/services/` zijn. Om deze configuratie voor de het overseineneigenschap van een plaats te selecteren, wordt dit eindpunt verstrekt als **`Service selector`** waarde voor `Message List and Compose Message components` (zie [Berichteigenschap](configure-messaging.md)). De standaardwaarde is */bin/messaging*.

* **[!UICONTROL fieldAllowlist.name]**
Gebruiken 
**Lijst van gewenste personen** voor berichtvelden.

>[!CAUTION]
>
>Telkens wanneer een `Messaging Operations Service` configuratie voor uitgeven wordt geopend, als `allowedAttachmentTypes.name` was verwijderd, wordt een lege ingang opnieuw toegevoegd om het bezit configureerbaar te maken. Bij één leeg item worden bestandsbijlagen uitgeschakeld.
>
>Als u alle bestandsextensies wilt toestaan, behalve de gevoegde op lijst van gewenste personen extensies, gebruikt u het pictogram &#39;**-**&#39; om (opnieuw) één leeg item te verwijderen voordat u op **[!UICONTROL Save]** klikt.

## Problemen oplossen {#troubleshooting}

Één manier om problemen op te lossen is [het zuiveren berichten in het logboek toe te laten.](../../help/sites-administering/troubleshooting.md)

Zie ook [Loggers and Writers for Individual Services](../../help/sites-deploying/configure-logging.md#loggers-and-writers-for-individual-services).

Het te controleren pakket is `com.adobe.cq.social.messaging`.
