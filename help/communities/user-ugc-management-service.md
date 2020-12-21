---
title: Gebruikersbeheer en UGC-beheerservice in AEM Communities
seo-title: Gebruikersbeheer en UGC-beheerservice in AEM Communities
description: 'Gebruik API''s om door gebruikers gegenereerde inhoud in bulk te verwijderen en te exporteren en gebruikersaccount uit te schakelen. '
seo-description: 'Gebruik API''s om door gebruikers gegenereerde inhoud in bulk te verwijderen en te exporteren en gebruikersaccount uit te schakelen. '
uuid: f4663825-eac8-4ef5-8253-46875e0cd71d
contentOwner: mgulati
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
discoiquuid: f564759f-fb56-4f70-a7b1-286a223755c6
translation-type: tm+mt
source-git-commit: 77cca35f74db2ced556b71c3192058b7c352ab4d
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 0%

---


# Gebruikers- en UGC-beheerservice in AEM Communities {#user-and-ugc-management-service-in-aem-communities}

>[!IMPORTANT]
>
>GDPR wordt in de onderstaande secties als voorbeeld gebruikt, maar de betreffende details zijn van toepassing op alle regels inzake gegevensbescherming en privacy; zoals GDPR, CCPA enz.

AEM Communities maakt API&#39;s offline beschikbaar voor het beheer van gebruikersprofielen en het bulksgewijs beheren van door gebruikers gegenereerde inhoud (UGC). Zodra toegelaten, laat de **UserUgcManagement** dienst de bevoorrechte gebruikers (communautaire beheerders en moderatoren) toe om gebruikersprofielen onbruikbaar te maken, en bulkschrapping of bulkuitvoer UGC voor specifieke gebruikers. Deze API&#39;s stellen ook de verwerkingsverantwoordelijken en verwerkers van klantgegevens in staat om te voldoen aan de algemene gegevensbeschermingsregels van de Europese Unie (GDPR) en andere op GDPR geïnspireerde privacymandaten.

Zie de [GDPR-pagina in het Adobe Privacy Center](https://www.adobe.com/privacy/general-data-protection-regulation.html) voor meer informatie.

>[!NOTE]
>
>Als u [Adobe Analytics hebt geconfigureerd op de AEM Communities](analytics.md)-site, worden de vastgelegde gebruikersgegevens verzonden naar de Adobe Analytics-server. Adobe Analytics biedt API&#39;s waarmee u toegang hebt tot gebruikersgegevens, deze kunt exporteren en verwijderen en die voldoen aan GDPR. Zie [Toegang verzenden en Verzoeken verwijderen](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/gdpr-submit-access-delete.html) voor meer informatie.

Om deze APIs aan gebruik te zetten, moet u het `/services/social/ugcmanagement` eindpunt toelaten door de dienst te activeren UserUgcManagement. Om deze service te activeren, installeert u de [voorbeeldservlet](https://github.com/Adobe-Marketing-Cloud/aem-communities-ugc-migration/tree/main/bundles/communities-ugc-management-servlet) die beschikbaar is op [GitHub.com](https://github.com/Adobe-Marketing-Cloud/aem-communities-ugc-migration/tree/main/bundles/communities-ugc-management-servlet). Dan, druk het eindpunt op publiceer geval van uw communautaire plaats met aangewezen parameters gebruikend een HTTP- verzoek, gelijkend op het volgende:

`http://localhost:port/services/social/ugcmanagement?user=<authorizable ID>&operation<getUgc>`

U kunt echter ook een gebruikersinterface (gebruikersinterface) maken voor het beheer van gebruikersprofielen en door de gebruiker gegenereerde inhoud in het systeem.

Met deze API&#39;s kunnen de volgende functies worden uitgevoerd.

## De UGC van een gebruiker {#retrieve-the-ugc-of-a-user} ophalen

`getUserUgc(ResourceResolver resourceResolver, String user, OutputStream outputStream)` Hiermee kunt u alle UGC van een gebruiker uit het systeem exporteren.

* **gebruiker**: autoriseerbare id van een gebruiker.
* **outputStream**: Het resultaat wordt geretourneerd als een uitvoerstream. Dit is een ZIP-bestand met daarin de door de gebruiker gegenereerde inhoud (als JSON-bestand) en bijlagen (inclusief afbeeldingen of video&#39;s die door de gebruiker zijn geüpload).

Als u bijvoorbeeld de UGC wilt exporteren van een gebruiker met de naam Weston McCall, die weston.mccall@dodgit.com als geautoriseerde id gebruikt om u aan te melden bij de communitysite, kunt u een http-verzoek verzenden dat lijkt op het volgende:

`http://localhost:port/services/social/ugcmanagement?user=weston.mccall@dodgit.com&operation=getUgc`

## De UGC van een gebruiker {#delete-the-ugc-of-a-user} verwijderen

**deleteUserUgc (ResourceResolver resourceResolver, de gebruiker van het Koord)** helpt schrapping al UGC voor een gebruiker van het systeem.

* **gebruiker**: autoriseerbare id van de gebruiker.

Als u bijvoorbeeld de UGC wilt verwijderen van een gebruiker met de machtigbare id weston.mccall@dodgit.com via de HTTP-POST-aanvraag, gebruikt u de volgende parameters:

* user= weston.mccall@dodgit.com
* operation= deleteUgc

### UGC verwijderen uit Adobe Analytics {#delete-ugc-from-analytics}

Volg de GDPR Analytics-workflow om gebruikersgegevens uit de Adobe Analytics te verwijderen. omdat de API geen gebruikersgegevens van Adobe Analytics verwijdert.

Raadpleeg de volgende afbeelding voor Adobe Analytics-variabeletoewijzingen die AEM Communities gebruikt:

![AEM gemeenschappen variabele mapping voor Adobe Analytics](assets/Analytics-Communities-Mapping.png)

## Gebruikersaccount {#disable-a-user-account} uitschakelen

**deleteUserAccount(ResourceResolver resourceResolver, String user)** helpt een gebruikersaccount onbruikbaar maken.

* **gebruiker**: autoriseerbare id van de gebruiker.

>[!NOTE]
>
>Als een gebruiker wordt uitgeschakeld, wordt alle door de gebruiker gegenereerde inhoud op de server verwijderd.

Als u bijvoorbeeld het profiel wilt verwijderen van een gebruiker met de machtigbare id weston.mccall@dodgit.com via de HTTP-POST-aanvraag, gebruikt u de volgende parameters:

* user= weston.mccall@dodgit.com
* operation= deleteUser

>[!NOTE]
>
>deleteUserAccount()-API schakelt alleen een gebruikersprofiel in het systeem uit en verwijdert de UGC. Als u echter een gebruikersprofiel uit het systeem wilt verwijderen, navigeert u naar **CRXDE Lite**: [https://&lt;server>/crx/de](http://localhost:4502/crx/de), zoek het gebruikersknooppunt en verwijder het.
