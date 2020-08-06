---
title: Nieuwe functies in AEM 6.4-gemeenschappen
seo-title: Nieuwe functies in AEM 6.4-gemeenschappen
description: 'null'
seo-description: 'null'
uuid: e4bf343c-59cd-48ac-bee4-85db109e4c65
contentOwner: mgulati
discoiquuid: 3e3c867f-afb0-4402-94f4-16e1a556ddee
translation-type: tm+mt
source-git-commit: 3d2b91565e14e85e9e701663c8d0ded03e5b430c
workflow-type: tm+mt
source-wordcount: '1008'
ht-degree: 0%

---


# Nieuwe functies in AEM 6.4-gemeenschappen {#what-s-new-in-aem-communities}

AEM Communities biedt bedrijven een kader aan om onder hun partners, klanten en werknemers samen te werken. Het draagt sociale mogelijkheden bij aan de structuur van websites en helpt bedrijven om kennis te vergaren en aan hun belanghebbenden uit te dragen om hun merkwaarde te verhogen.

AEM 6.4 De Gemeenschappen brengen functionaliteit in om de ervaringen van communautaire gebruikers te verbeteren, en de dagelijkse taken van communautaire beheerders, moderatoren, en managers te verlichten.

Lees verder voor een snelle inleiding tot nieuwe functies en verbeteringen. Zie ook AEM 6.4 [Opmerkingen](../release-notes/communities-release-notes.md)van de Gemeenschappen. Voor AEM 6.4 Community-documentatie gaat u naar [AEM 6.4 Community Guide](home.md).

## Subgemeenschappen of communautaire groepen beheren {#managing-sub-communities-or-community-groups}

Met AEM Communities kunnen gemeenschapsbeheerders groepen en subgroepen maken binnen de communitysite met behulp van vooraf gedefinieerde sjablonen in de auteuromgeving. Deze groepen dienen als subgemeenschappen, die vele configuraties, zoals thema&#39;s en het stileren van de ouderplaats kunnen erven. Nochtans, kunnen deze groepen van de ouderplaats verschillen, bijvoorbeeld hebbend een verschillende reeks groepsmoderators of kan in het veiligheidsniveau variëren. Deze groepen fungeren als onafhankelijke, volwaardige mini-gemeenschappen, die verder worden versterkt door de volgende verbeteringen.

### Groepen met meerdere landinstellingen maken in één stap {#create-multi-locale-groups-in-single-step}

Als onderdeel van een communitysite kunnen meertalige groepen in één bewerking worden gemaakt. **[!UICONTROL Additional Available Community Group Language(s)]** door het veld op de **[!UICONTROL Community Group Template]** pagina , dat beschikbaar is tijdens het maken van een [nieuwe communautaire groep](groups.md) binnen een communautaire site , is dit haalbaar .

![meertalige groep 1](assets/multilingualgroup-1.png)

Om dergelijke groepen tot stand te brengen, kunnen de gebruikers eenvoudig aan de Inzameling van de Groep van de gewenste communautaire plaats van de console van Plaatsen navigeren. Maak een groep en geef de gewenste talen op in **[!UICONTROL Additional Available Community Group Language(s)]** het veld **[!UICONTROL Community Group Template]** Pagina.

### communitygroepen verwijderen uit groepenconsole {#delete-community-groups-from-groups-console}

AEM 6.4 de Gemeenschappen verstrekt het pictogram van de Groep van de Schrapping op de bestaande communautaire groepen, in de inzameling van communautaire Groepen binnen de console van Plaatsen van de gemeenschap. Dit laat [groepsschrapping](groups.md#deleting-the-group) in één klik, samen met de schrapping van alle punten toe verbonden (zoals inhoud en gebruikerslidmaatschappen) met de groep.

![deletegrp](assets/deletegrp.png)

### Hulpmiddelen binnen groepen maken en toewijzen {#create-and-assign-enablement-resources-within-groups}

Leerinhoud kan nu worden gemaakt, beheerd en gepubliceerd voor een specifieke verzameling doelleden van de gemeenschap. Vanwege de beschikbaarheid van catalogus- en toewijzingsfuncties voor groepen uit de gebruikersgemeenschap (en niet alleen voor de hele site van de community), kunnen enablement-managers ook [actiemiddelen](resource.md) en leerpad toewijzen aan een kleine set personen.

![toewijzingscatalogus](assets/assignmentcatalog.png)

## Door gebruiker gegenereerde inhoud modereren {#moderating-user-generated-content}

AEM 6.4 De Europese Gemeenschappen bieden weinig verbeteringen aan in de gematigdheid, die het dagelijks leven van de gematigden in de gemeenschap helpen verlichten.

### Automatische spamdetectie  {#automatic-spam-detection}

De nieuwe motor van de spamopsporing helpt in het filtreren uit de ongewenste en ongevraagde gebruiker geproduceerde inhoud op communautaire plaatsen of groepen. Als deze functie is ingeschakeld, kan een deel van door de gebruiker gegenereerde inhoud worden gemarkeerd als spam of Not Spam op basis van een vooraf gedefinieerde set spamwoorden. De moderatoren kunnen op de inhoud verder handelen om het te ontkennen of toe te staan om op te verschijnen publiceer instantie. Deze moderatieacties kunnen worden uitgevoerd inline of door bulkmoderatieconsole.

![spamdetectie-1](assets/spamdetection-1.png)

[Spam-detector](moderate-ugc.md#spam-detection) zoekt en markeert een bepaald door de gebruiker gegenereerde inhoud met een nauwkeurigheid van 90%. Deze functionaliteit is echter niet standaard ingeschakeld. Om het toe te laten, moeten de communautaire beheerders aan configMgr op systeem/console navigeren en Spam- Proces toevoegen.

![spamprocess-1](assets/spamprocess-1.png)

### Nieuwe filters (Beantwoord/Onbeantwoord) voor QnA {#new-answered-unanswered-filters-for-qna}

AEM 6.4 voegt twee [nieuwe filters](moderation.md#filter-rail)toe, genoemd Beantwoord en niet Beantwoord voor vragen QnA, aan bulkmoderatieconsole. Deze filters zijn beschikbaar onder Status in de spoorstaaf van de Filter.

![statussen](assets/statuses.png)

Bij het selecteren van de Beantwoorde status, zijn alle beantwoorde vragen zichtbaar aan de moderator op inhoudsgebied. Terwijl, als slechts de niet Beantwoorde status wordt geselecteerd, dan zal de moderator al inhoud (voor alle inhoudstypes) behalve de beantwoorde vragen zien, omdat het bezit verantwoordelijk voor de Beantwoorde Vraag niet in het geval van niet-beantwoorde vragen en andere inhoud zoals forumonderwerp, blogartikel, of commentaren bestaat.

### Filters voor bladwijzermodernisering {#bookmark-moderation-filters}

AEM Communities verstrekt de capaciteit aan [referentie de vooraf bepaalde moderatiefilters](moderation.md#filter-rail) op moderatieconsole. Deze opgeslagen bladwijzers kunnen later opnieuw worden bewerkt en met andere gebruikers worden gedeeld.

De gebruikers moeten eenvoudig de gewenste filters van de Spoorlijn van de Filter in moderatieconsole selecteren, om gefilterde UGC te bekijken en referentie de filters op hun browsers. Deze filters worden toegevoegd aan het einde van de URL-tekenreeks en kunnen daarom later worden gedeeld, opnieuw worden gebruikt en herzien.

## Communautaire sites beheren {#managing-community-sites}

AEM 6.4 Communities biedt verbeteringen op het gebied van sitebeheer, die ervoor zorgen dat meerdere gemeenschapssites in verschillende talen gemakkelijk kunnen worden gemaakt, beheerd en verwijderd door sitebeheerders.

### Eenvoudige lokale communitysites maken {#create-multi-locale-community-sites-in-one-step}

Met AEM Communities kunt u in één keer een [meertalige communitysite](create-site.md) maken. Dit is mogelijk vanwege de beschikbaarheid van meerdere talen die u in het **[!UICONTROL Community Site Base Language]** veld op de **[!UICONTROL Site Template]** pagina kunt selecteren, terwijl u een nieuwe communitysite maakt via de siteconsole.

![multilocalesite](assets/multilocalesite.png)

Gebruikers kunnen configuratiemappen, branding en veel andere configuraties tegelijk selecteren voor al deze sites.

### communitysites verwijderen uit siteconsole {#delete-community-sites-from-sites-console}

AEM 6.4 Communities biedt het pictogram Site verwijderen op de bestaande communitysites in de community Sites-console. Hierdoor kunnen de site [en de bijbehorende items met één klik worden](create-site.md) verwijderd.

![sitehandelingen](assets/siteactions.png)

## UGC- en gebruikersprofielen beheren {#managing-ugc-and-user-profiles}

AEM Communities houdt de bescherming van gebruikersgegevens centraal in de ervaringen van gemeenschappen en maakt [API&#39;s offline](user-ugc-management-service.md) en [voorbeeldservlet](https://github.com/Adobe-Marketing-Cloud/aem-communities-ugc-migration/tree/master/bundles/communities-ugc-management-servlet)beschikbaar. Met deze API&#39;s kunt u in grote hoeveelheden door gebruikers gegenereerde inhoud beheren (bulkverwijderen en bulkexport) en gebruikersprofielen verwijderen. Deze API&#39;s zijn ook handig voor de verwerking van aanvragen voor GDPR-compatibiliteit in de EU.

## Wat is gewijzigd {#what-s-changed}

* De Captcha-verificatie is tijdens het maken van een nieuwe community-site niet meer beschikbaar in AEM 6.4-gemeenschappen. De Community-site kan echter worden aangepast en de [Google-component reCAPTCHA](https://helpx.adobe.com/experience-manager/using/aem_recaptcha.html) bevatten voor betere beveiliging.
* De optie voor het uploaden van een aangepaste CSS is verwijderd uit het thema voor communitysites en -groepen.
* Alleen inhoud en zoekpictogrammen zijn toegevoegd aan de interface Filterrail in bulkmodernisering.
* De filter van de Weg van de inhoud is toegevoegd in Rail van de Filter in Bulk UI van de Moderatie.
* De schakelaar aan bulkwijze en de bulkwijze van de Uitgang zijn verwijderd uit de Bulk Moderation UI. Als u de modus voor meerdere selecties wilt inschakelen, klikt u op het pictogram Selecteren ( ![selecteren](assets/selecticon.png)) op een post. Dit pictogram verschijnt wanneer u de muisaanwijzer op het bericht plaatst (bureaublad) of wanneer u met een vinger op het bericht drukt (mobiel).
