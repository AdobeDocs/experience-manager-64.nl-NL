---
title: Berichten configureren
seo-title: Configuring Messaging
description: Communityberichten
seo-description: Communities messaging
uuid: 35d98667-a82e-4ed1-b6a1-1ffbbe1d08b5
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 5cb571ae-eeb5-4943-a6b8-92e346e85be2
role: Admin
exl-id: 0e906f67-b908-4c41-b243-e4f90100ce5d
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '723'
ht-degree: 0%

---

# Berichten configureren {#configuring-messaging}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Overzicht {#overview}

Met de communicatiefunctie voor AEM Communities kunnen bezoekers van de aangemelde site (leden) berichten naar elkaar sturen die toegankelijk zijn wanneer ze zich op de site hebben aangemeld.

Het overseinen wordt toegelaten voor een communautaire plaats door een doos tijdens te controleren [site maken](sites-console.md).

Op deze pagina vindt u informatie over de standaardconfiguratie en mogelijke aanpassingen.

Voor meer informatie voor ontwikkelaars raadpleegt u [Grondbeginselen van berichten](essentials-messaging.md).

## Service voor berichtenverkeer {#messaging-operations-service}

De [AEM Communities Messaging Operations Service](http://localhost:4502/system/console/configMgr/com.adobe.cq.social.messaging.client.endpoints.impl.MessagingOperationsServiceImpl) identificeert het eindpunt dat overseinenverwante verzoeken behandelt, de omslagen de dienst voor het opslaan van berichten zou moeten gebruiken, en als de berichten dossiergehechtheid kunnen omvatten, welke dossiertypes worden toegestaan.

Voor gemeenschapssites die zijn gemaakt met de opdracht [Community Sites-console](sites-console.md), bestaat al een instantie van de service, met de inbox ingesteld op `/mail/community/inbox`.

### Community Messaging Operations Service {#community-messaging-operations-service}

Zoals hieronder getoond, bestaat een configuratie van de dienst voor plaatsen die met worden gecreeerd [wizard voor het maken van sites](sites-console.md). U kunt de configuratie weergeven of bewerken door het potloodpictogram naast de configuratie te selecteren:

![chlimage_1-63](assets/chlimage_1-63.png)

### Nieuwe configuratie {#new-configuration}

Als u een nieuwe configuratie wilt toevoegen, selecteert u de plusknop &#39;**+** pictogram naast de naam van de service:

![chlimage_1-64](assets/chlimage_1-64.png)

* **[!UICONTROL Message Fields Allowlist]**
Hiermee geeft u de eigenschappen op van de component Bericht samenstellen die gebruikers kunnen bewerken en behouden. Als nieuwe formulierelementen worden toegevoegd, moet de element-id desgewenst worden toegevoegd om te worden opgeslagen in SRP. Standaard zijn dit twee items: 
*onderwerp* en *content*.

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
*failureNotifier*.

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
*Vereist*) Het pad ten opzichte van het knooppunt van de gebruiker (/home/users/*gebruikersnaam*), te gebruiken voor de **`inbox`** map. Het pad mag NIET eindigen met een slash &#39;/&#39; achter het pad. Standaard is */mail/inbox* .

* **[!UICONTROL sentitems.path.name]**
(
*Vereist*) Het pad ten opzichte van het knooppunt van de gebruiker (/home/users/*gebruikersnaam*), te gebruiken voor de **`senditems`** map. Het pad mag NIET eindigen met een slash &#39;/&#39; achter het pad. Standaard is */mail/sentitems* .

* **[!UICONTROL supportAttachments.name]**
Als deze optie is ingeschakeld, kunnen gebruikers bijlagen toevoegen aan hun berichten. Standaard is 
*ingeschakeld*.

* **[!UICONTROL batchSize.name]**
Aantal berichten aan partij samen voor verzenden wanneer het verzenden naar een grote groep ontvangers. Standaard is 
*100*.

* **[!UICONTROL maxTotalAttachmentSize.name]**
Als supportAttachments wordt gecontroleerd, specificeert deze waarde de maximum toegestane totale grootte (in bytes) van alle gehechtheid. Standaard is 
*104857600* (100 MB).

* **[!UICONTROL attachmentTypeBlocklist.name]**
Een lijst van gewezen personen met bestandsextensies, vooraf ingesteld op &#39;
**.**&quot;, dat zal door het systeem worden verworpen. Als de extensie niet wordt gevoegd op lijst van gewenste personen, is deze toegestaan. Extensies kunnen worden toegevoegd of verwijderd met de &#39;**+**&#39; en &#39;**-** pictogrammen. Standaard is *STANDAARD*.

* **[!UICONTROL allowedAttachmentTypes.name]**

   **(*Actie vereist*)** Een lijst van gewenste personen van dossieruitbreidingen, het tegenovergestelde van de lijst van gewezen personen. Als u alle bestandsextensies wilt toestaan, behalve de gevoegde op lijst van gewenste personen extensies, gebruikt u de optie &quot;**-** pictogram om één leeg item te verwijderen.

* **[!UICONTROL serviceSelector.name]**
(*Vereist*) Een absolute weg (eindpunt) waardoor de dienst (een virtueel middel) wordt aangehaald. De hoofdmap van het gekozen pad moet zijn opgenomen in het dialoogvenster *Uitvoerpaden* configuratie-instelling van OSGi config [ `Apache Sling Servlet/Script Resolver and Error Handler`](http://localhost:4502/system/console/configMgr/org.apache.sling.servlets.resolver.SlingServletResolver), zoals `/bin/`, `/apps/`, en `/services/`. Om deze configuratie voor het overseineneigenschap van een plaats te selecteren, wordt dit eindpunt verstrekt als **`Service selector`** waarde voor de `Message List and Compose Message components` (zie [Berichtonderdeel](configure-messaging.md)). De standaardwaarde is */bin/messaging* .

* **[!UICONTROL fieldAllowlist.name]**
Gebruiken 
**Lijst van gewenste personen Berichtvelden**.

>[!CAUTION]
>
>Elke keer een `Messaging Operations Service` configuratie wordt geopend voor bewerking, als `allowedAttachmentTypes.name` is verwijderd, wordt een lege ingang opnieuw toegevoegd om het bezit configureerbaar te maken. Bij één leeg item worden bestandsbijlagen uitgeschakeld.
>
>Als u alle bestandsextensies wilt toestaan, behalve de gevoegde op lijst van gewenste personen extensies, gebruikt u de optie &quot;**-**&#39; pictogram naar (opnieuw) verwijder het enkele lege item voordat u op **[!UICONTROL Save]**.

## Problemen oplossen {#troubleshooting}

Één manier om problemen op te lossen is toe te laten [foutopsporingsberichten in het logbestand.](../../help/sites-administering/troubleshooting.md)

Zie ook [Loggers en schrijvers voor de Individuele Diensten](../../help/sites-deploying/configure-logging.md#loggers-and-writers-for-individual-services).

Het te controleren pakket is `com.adobe.cq.social.messaging`.
