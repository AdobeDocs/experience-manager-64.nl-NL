---
title: Gebruikersbeheer en UGC-beheerservice in AEM Communities
seo-title: User and UGC Management Service in AEM Communities
description: Gebruik API's om door gebruikers gegenereerde inhoud in bulk te verwijderen en te exporteren en gebruikersaccount uit te schakelen.
seo-description: Use APIs to bulk delete and bulk export user generated content, and disable user account.
uuid: f4663825-eac8-4ef5-8253-46875e0cd71d
contentOwner: mgulati
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
discoiquuid: f564759f-fb56-4f70-a7b1-286a223755c6
role: Admin
exl-id: f4adc53d-6809-4d89-a3dd-5d783e938a63
source-git-commit: 0f4f8c2640629f751337e8611a2c8f32f21bcb6d
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 0%

---

# Gebruikersbeheer en UGC-beheerservice in AEM Communities {#user-and-ugc-management-service-in-aem-communities}

>[!IMPORTANT]
>
>GDPR wordt in de onderstaande secties als voorbeeld gebruikt, maar de betreffende details zijn van toepassing op alle regels inzake gegevensbescherming en privacy; zoals GDPR, CCPA enz.

AEM Communities maakt API&#39;s offline beschikbaar voor het beheer van gebruikersprofielen en het bulksgewijs beheren van door gebruikers gegenereerde inhoud (UGC). Wanneer deze optie is ingeschakeld, wordt de **UserUgcManagement** De dienst staat de bevoorrechte gebruikers (communautaire beheerders en moderatoren) toe om gebruikersprofielen onbruikbaar te maken, en bulkschrapping of bulkexport UGC voor specifieke gebruikers. Deze API&#39;s stellen ook de verwerkingsverantwoordelijken en verwerkers van klantgegevens in staat om te voldoen aan de algemene gegevensbeschermingsregels van de Europese Unie (GDPR) en andere op GDPR geïnspireerde privacymandaten.

Zie voor meer informatie [GDPR-pagina in het Adobe Privacy Center](https://www.adobe.com/privacy/general-data-protection-regulation.html).

>[!NOTE]
>
>Als u [Adobe Analytics in AEM Communities](analytics.md) de vastgelegde gebruikersgegevens naar de Adobe Analytics-server worden verzonden. Adobe Analytics biedt API&#39;s waarmee u toegang hebt tot gebruikersgegevens, deze kunt exporteren en verwijderen en die voldoen aan GDPR. Zie voor meer informatie [Toegang verzenden en verzoeken verwijderen](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/gdpr-submit-access-delete.html).

Om deze APIs aan gebruik te zetten, moet u toelaten `/services/social/ugcmanagement` eindpunt door de dienst UserUgcManagement te activeren. Installeer de [voorbeeldservet](https://github.com/Adobe-Marketing-Cloud/aem-communities-ugc-migration/tree/main/bundles/communities-ugc-management-servlet) beschikbaar op [GitHub.com](https://github.com/Adobe-Marketing-Cloud/aem-communities-ugc-migration/tree/main/bundles/communities-ugc-management-servlet). Dan, druk het eindpunt op publiceer geval van uw communautaire plaats met aangewezen parameters gebruikend een HTTP- verzoek, gelijkend op het volgende:

`http://localhost:port/services/social/ugcmanagement?user=<authorizable ID>&operation<getUgc>`

U kunt echter ook een gebruikersinterface (gebruikersinterface) maken voor het beheer van gebruikersprofielen en door de gebruiker gegenereerde inhoud in het systeem.

Met deze API&#39;s kunnen de volgende functies worden uitgevoerd.

## De UGC van een gebruiker ophalen {#retrieve-the-ugc-of-a-user}

`getUserUgc(ResourceResolver resourceResolver, String user, OutputStream outputStream)` Hiermee kunt u alle UGC van een gebruiker uit het systeem exporteren.

* **user**: autoriseerbare id van een gebruiker.
* **outputStream**: Het resultaat wordt geretourneerd als een uitvoerstream. Dit is een ZIP-bestand met daarin de door de gebruiker gegenereerde inhoud (als JSON-bestand) en bijlagen (inclusief afbeeldingen of video&#39;s die door de gebruiker zijn geüpload).

Als u bijvoorbeeld de UGC wilt exporteren van een gebruiker met de naam Weston McCall, die weston.mccall@dodgit.com als geautoriseerde id gebruikt om u aan te melden bij de communitysite, kunt u een http-verzoek verzenden dat lijkt op het volgende:

`http://localhost:port/services/social/ugcmanagement?user=weston.mccall@dodgit.com&operation=getUgc`

## De UGC van een gebruiker verwijderen {#delete-the-ugc-of-a-user}

**deleteUserUgc(ResourceResolver resourceResolver, String user)** helpt u alle UGC voor een gebruiker uit het systeem te verwijderen.

* **user**: autoriseerbare id van de gebruiker.

Als u bijvoorbeeld de UGC wilt verwijderen van een gebruiker met de machtigbare id weston.mccall@dodgit.com via de HTTP-POST-aanvraag, gebruikt u de volgende parameters:

* user= weston.mccall@dodgit.com
* operation= deleteUgc

### UGC verwijderen uit Adobe Analytics {#delete-ugc-from-analytics}

Volg de GDPR Analytics-workflow om gebruikersgegevens uit de Adobe Analytics te verwijderen. omdat de API geen gebruikersgegevens van Adobe Analytics verwijdert.

Raadpleeg de volgende afbeelding voor Adobe Analytics-variabeletoewijzingen die AEM Communities gebruikt:

![AEM gemeenschappen variabele mapping voor Adobe Analytics](assets/Analytics-Communities-Mapping.png)

## Gebruikersaccount uitschakelen {#disable-a-user-account}

**deleteUserAccount(ResourceResolver resourceResolver, String user)** Hiermee kunt u een gebruikersaccount uitschakelen.

* **user**: autoriseerbare id van de gebruiker.

>[!NOTE]
>
>Als een gebruiker wordt uitgeschakeld, wordt alle door de gebruiker gegenereerde inhoud op de server verwijderd.

Als u bijvoorbeeld het profiel wilt verwijderen van een gebruiker met de machtigbare id weston.mccall@dodgit.com via de HTTP-POST-aanvraag, gebruikt u de volgende parameters:

* user= weston.mccall@dodgit.com
* operation= deleteUser

>[!NOTE]
>
>deleteUserAccount()-API schakelt alleen een gebruikersprofiel in het systeem uit en verwijdert de UGC. Als u echter een gebruikersprofiel van het systeem wilt verwijderen, navigeert u naar **CRXDE Lite**: [https://&lt;server>/crx/de](http://localhost:4502/crx/de), zoek het gebruikersknooppunt en verwijder het.
