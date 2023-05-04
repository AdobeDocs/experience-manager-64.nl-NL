---
title: Publikaties
seo-title: Communities Notifications
description: AEM Communities heeft meldingen die gebeurtenissen weergeven die van belang zijn voor het aanmeldingscommunity-lid
seo-description: AEM Communities has notifications that display events of interest to the signed-in community member
uuid: d6ef12f1-7367-49a5-b891-56800a38b2ab
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 47201e2d-338d-40e0-af82-c681a552807b
role: Admin
exl-id: f6c6619e-b386-4d34-9d17-654d7c97aedd
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '557'
ht-degree: 0%

---

# Publikaties {#communities-notifications}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Overzicht {#overview}

AEM Communities biedt een meldingssectie waarin gebeurtenissen worden weergegeven die van belang zijn voor de ondertekenaars in het community-lid.

Meldingen lijken op [activiteiten](essentials-activities.md) en [abonnementen](subscriptions.md) die het gevolg zijn van

* Het lid dat inhoud plaatst
* Het lid dat ervoor kiest een ander lid te volgen
* Het lid dat ervoor kiest om specifieke onderwerpen, artikelen en andere draden van inhoud te volgen

Wat maakt onderscheid tussen meldingen en activiteiten en abonnementen?

* Een koppeling naar de sectie Meldingen staat altijd in de koptekst van een communitysite
   * De activiteiten vereisen [activity stream, functie](functions.md#activity-stream-function) op te nemen in de structuur van de site van de gemeenschap
   * Abonnementen vereist [configuratie van e-mail](email.md)
* De implementatie van meldingen verloopt via schaalbare en pluggable kanalen
   * Activiteiten zijn alleen beschikbaar op het web
   * Abonnementen zijn alleen beschikbaar via e-mail

Vanaf Gemeenschappen [FP1](deploy-communities.md#latestfeaturepack), de beschikbare kennisgevingskanalen

* Het webkanaal, toegankelijk via de `Notifications` link
* Het e-mailkanaal is beschikbaar wanneer e-mail correct is geconfigureerd

Toekomstige kanalen zijn mobiel en desktop.

### Vereisten {#requirements}

**E-mail configureren**

E-mail moet worden gevormd om het e-mailkanaal voor berichten functioneel te zijn.

Voor instructies over het instellen van e-mailberichten raadpleegt u [E-mail configureren](analytics.md).

**Volgen inschakelen**

Componenten moeten worden geconfigureerd om het volgende in te schakelen. Functies die het volgende toestaan, zijn [blog](blog-feature.md), [forum](forum.md), [QnA](working-with-qna.md), [kalender](calendar.md), [bestandsbibliotheek](file-library.md), en [opmerkingen](comments.md).

Let op:

* Onderdelen die binnen de gemeenschap worden gebruikt [sitesjablonen](sites.md) en [groepssjablonen](tools-groups.md) kan reeds worden gevormd om het volgende toe te staan

* De profielen van lidstaten worden reeds gevormd om andere leden toe te staan om te volgen

## Meldingen van: {#notifications-from-following}

![chlimage_1-254](assets/chlimage_1-254.png)

De **Volg** biedt een manier om vermeldingen als activiteiten, abonnementen en/of meldingen te volgen. Elke keer als **Volg** is geselecteerd, is het mogelijk om een selectie in of uit te schakelen. De `Email Subscriptions` selectie is alleen aanwezig als dit is geconfigureerd.

Als een van de volgende methoden is geselecteerd, verandert de tekst van de knop in **volgende**. Voor het gemak is het mogelijk om `Unfollow All` om alle methoden uit te schakelen.

De **Volg** wordt weergegeven

* Wanneer het bekijken van het profiel van een ander lid
* Op een hoofdpagina met functies, zoals forums, QnA en blogs
   * Volg alle activiteiten voor die algemene functie
* Voor een specifiek bericht, zoals een forumonderwerp, een QnA-vraag of een blogartikel
   * Hiermee wordt alle activiteit voor die specifieke vermelding gevolgd

## Meldingsinstellingen beheren {#managing-notification-settings}

Als u de koppeling Instellingen kennisgeving op de pagina Meldingen selecteert, kan elk lid bepalen hoe meldingen worden ontvangen.

Het webkanaal is altijd ingeschakeld.

![chlimage_1-255](assets/chlimage_1-255.png)

Het e-mailkanaal, dat afhankelijk is van de juiste [configuratie van e-mail](email.md)biedt dezelfde instellingen als voor het webkanaal.

Het e-mailkanaal is standaard uitgeschakeld.

![chlimage_1-256](assets/chlimage_1-256.png)

Het kan door een lid worden aangezet, maar nog hangt van e-mail af die wordt gevormd.

![chlimage_1-257](assets/chlimage_1-257.png)

## Meldingen weergeven {#viewing-notifications}

### Webmeldingen {#web-notifications}

A [wizard heeft een communitysite gemaakt](sites-console.md) bevat nu een koppeling naar de `Notifications` in de koptekstbalk van de site boven de banner. In tegenstelling tot berichten, worden de berichten gecreeerd voor elke communautaire plaats, terwijl de berichten tijdens het proces van de plaatsverwezenlijking moeten worden toegelaten.

Als u de gepubliceerde site wilt bezoeken, selecteert u de optie `Notifications` via de koppeling worden alle meldingen voor het lid weergegeven .

![chlimage_1-258](assets/chlimage_1-258.png)

### E-mailmeldingen {#email-notifications}

Wanneer het e-mailkanaal is ingeschakeld, ontvangt het lid een e-mail met een koppeling naar de inhoud op het web.

![chlimage_1-259](assets/chlimage_1-259.png)
