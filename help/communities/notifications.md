---
title: Publikaties
seo-title: Publikaties
description: AEM Communities heeft meldingen die gebeurtenissen weergeven die van belang zijn voor het aanmeldingscommunity-lid
seo-description: AEM Communities heeft meldingen die gebeurtenissen weergeven die van belang zijn voor het aanmeldingscommunity-lid
uuid: d6ef12f1-7367-49a5-b891-56800a38b2ab
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 47201e2d-338d-40e0-af82-c681a552807b
translation-type: tm+mt
source-git-commit: 5ddbcb2addff2d6e3a3e9d7e100a6d9ba89fdd60
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 0%

---


# Communitymeldingen {#communities-notifications}

## Overzicht {#overview}

AEM Communities biedt een meldingssectie waarin gebeurtenissen worden weergegeven die van belang zijn voor de ondertekenaars in het community-lid.

Meldingen zijn vergelijkbaar met [activiteiten](essentials-activities.md) en [abonnementen](subscriptions.md) omdat ze mogelijk het resultaat zijn van

* Het lid dat inhoud plaatst
* Het lid dat ervoor kiest een ander lid te volgen
* Het lid dat ervoor kiest om specifieke onderwerpen, artikelen en andere draden van inhoud te volgen

Wat maakt onderscheid tussen meldingen en activiteiten en abonnementen?

* Een koppeling naar de sectie Meldingen staat altijd in de koptekst van een communitysite
   * Voor activiteiten moet de functie [activity stream](functions.md#activity-stream-function) worden opgenomen in de structuur van de site van de community
   * Abonnementen vereisen [configuratie van e-mail](email.md)
* De implementatie van meldingen verloopt via schaalbare en pluggable kanalen
   * Activiteiten zijn alleen beschikbaar op het web
   * Abonnementen zijn alleen beschikbaar via e-mail

Vanaf de Gemeenschappen [FP1](deploy-communities.md#latestfeaturepack) zijn de beschikbare kennisgevingskanalen

* Het webkanaal, geopend via de koppeling `Notifications`
* Het e-mailkanaal is beschikbaar wanneer e-mail correct is geconfigureerd

Toekomstige kanalen zijn mobiel en desktop.

### Vereisten {#requirements}

**E-mail configureren**

E-mail moet worden gevormd om het e-mailkanaal voor berichten functioneel te zijn.

Zie [E-mail configureren](analytics.md) voor instructies voor het instellen van e-mail.

**Volgen inschakelen**

Componenten moeten worden geconfigureerd om het volgende in te schakelen. Functies die het volgende toestaan, zijn [blog](blog-feature.md), [forum](forum.md), [QnA](working-with-qna.md), [agenda](calendar.md), [bestandsbibliotheek](file-library.md) en [commentaren](comments.md).

Let op:

* Componenten die worden gebruikt binnen de community [sitesjablonen](sites.md) en [groepssjablonen](tools-groups.md) kunnen al zijn geconfigureerd om het volgende toe te staan

* De profielen van lidstaten worden reeds gevormd om andere leden toe te staan om te volgen

## Meldingen van volgende {#notifications-from-following}

![chlimage_1-254](assets/chlimage_1-254.png)

Met de knop **Follow** kunt u items opvolgen als activiteiten, abonnementen en/of meldingen. Telkens wanneer de **Follow** knoop wordt geselecteerd, is het mogelijk om of van een selectie van een knevel te voorzien. De `Email Subscriptions` selectie is slechts aanwezig wanneer gevormd.

Als een methode van het volgende wordt geselecteerd, verandert de tekst van de knoop in **volgend**. Voor het gemak, is het mogelijk om `Unfollow All` te selecteren om alle methodes van een knevel te voorzien.

De knop **Volg** verschijnt

* Wanneer het bekijken van het profiel van een ander lid
* Op een hoofdpagina met functies, zoals forums, QnA en blogs
   * Volg alle activiteiten voor die algemene functie
* Voor een specifiek bericht, zoals een forumonderwerp, een QnA-vraag of een blogartikel
   * Hiermee wordt alle activiteit voor die specifieke vermelding gevolgd

## Meldingsinstellingen {#managing-notification-settings} beheren

Als u de koppeling Instellingen kennisgeving op de pagina Meldingen selecteert, kan elk lid bepalen hoe meldingen worden ontvangen.

Het webkanaal is altijd ingeschakeld.

![chlimage_1-255](assets/chlimage_1-255.png)

Het e-mailkanaal, dat afhankelijk is van de juiste [configuratie van e-mail](email.md), biedt dezelfde instellingen als voor het webkanaal.

Het e-mailkanaal is standaard uitgeschakeld.

![chlimage_1-256](assets/chlimage_1-256.png)

Het kan door een lid worden aangezet, maar nog hangt van e-mail af die wordt gevormd.

![chlimage_1-257](assets/chlimage_1-257.png)

## Meldingen {#viewing-notifications} weergeven

### Webmeldingen {#web-notifications}

Een [wizard heeft een communitysite](sites-console.md) gemaakt en bevat nu een koppeling naar de functie `Notifications` in de kopbalk van de site boven de banner. In tegenstelling tot berichten, worden de berichten gecreeerd voor elke communautaire plaats, terwijl de berichten tijdens het proces van de plaatsverwezenlijking moeten worden toegelaten.

Als u de gepubliceerde site bezoekt en de koppeling `Notifications` selecteert, worden alle meldingen voor het lid weergegeven.

![chlimage_1-258](assets/chlimage_1-258.png)

### E-mailmeldingen {#email-notifications}

Wanneer het e-mailkanaal is ingeschakeld, ontvangt het lid een e-mail met een koppeling naar de inhoud op het web.

![chlimage_1-259](assets/chlimage_1-259.png)

