---
title: Developing and Page Diff
seo-title: Developing and Page Diff
description: 'null'
seo-description: 'null'
uuid: 48bbeca3-fe16-48ef-bb4d-ac605fe0ca76
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: introduction
content-type: reference
discoiquuid: 13e8cbef-698f-4e69-9f8c-f9bee82e9fd1
translation-type: tm+mt
source-git-commit: 6de5e6f12f123ca2ec45358a138becc410c89e4e
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 0%

---


# Developing and Page Diff{#developing-and-page-diff}

## Overzicht van functies {#feature-overview}

Het maken van inhoud is een herhalend proces. Om efficiënt te kunnen ontwerpen moet u kunnen zien wat er van de ene iteratie naar de andere is veranderd. Het weergeven van de ene pagina en de andere is inefficiënt en vatbaar voor fouten. Een auteur wil de huidige pagina met een vorige versie naast elkaar kunnen vergelijken met de gemarkeerde verschillen.

Met het paginagecheiding kan een gebruiker de huidige pagina vergelijken met opstarters, vorige versies, enzovoort. Zie [Paginadiff](/help/sites-authoring/page-diff.md) voor meer informatie over deze gebruikersfunctie.

## Bewerkingsdetails {#operation-details}

Wanneer u versies van een pagina vergelijkt, wordt de vorige versie die de gebruiker wil vergelijken opnieuw gemaakt door op de achtergrond AEM te plaatsen om het afschuiven te vergemakkelijken. Dit is nodig om de inhoud [te kunnen weergeven voor vergelijking naast elkaar](/help/sites-authoring/page-diff.md#presentation-of-differences).

Deze recreatiebewerking wordt intern AEM uitgevoerd en is transparant voor de gebruiker en vereist geen interventie. Nochtans zou een beheerder die de bewaarplaats bijvoorbeeld in CRX DE Lite bekijkt deze ontspannen versies binnen de inhoudsstructuur zien.

Afhankelijk van het AEM flardniveau, is het gedrag verschillend en kan bepaalde toestemmingen vereisen om behoorlijk te werken.

### Vóór AEM 6.4.3 {#prior-to-aem}

Wanneer de inhoud wordt vergeleken, wordt de hele structuur tot aan de te vergelijken pagina opnieuw gemaakt op de volgende locatie:

`/content/versionhistory/<userId>/<site structure>`

Omdat bij het gebruik van het mechanisme voor pagina-afbreking AEM de vorige versie van de pagina opnieuw wordt gemaakt, moet de gebruiker bepaalde JCR-machtigingen hebben om deze functie te kunnen gebruiken.

>[!CAUTION]
>
>Als u de functie voor pagina-diff wilt gebruiken, moet de gebruiker de **machtiging Wijzigen/Maken/Verwijderen** op het knooppunt `/content/versionhistory` hebben.

### Vanaf AEM 6.4.3 {#as-of-aem}

Wanneer de inhoud wordt vergeleken, wordt de hele structuur tot aan de te vergelijken pagina opnieuw gemaakt op de volgende locatie:

`/tmp/versionhistory/`

Deze inhoud wordt gecreeerd door een de dienstgebruiker met toestemmingen die zicht tot de huidige gebruiker beperken. Daarom zijn geen speciale machtigingen vereist.

Er wordt automatisch een opschoningstaak uitgevoerd om deze tijdelijke inhoud op te schonen.

## Ontwikkelaarsbeperkingen {#developer-limitations}

Eerder, in Klassieke UI, moest de speciale ontwikkelingsoverweging worden gemaakt om AEM het verschillen (zoals het gebruiken van `cq:text` markeringslib, of douane te vergemakkelijken die de `DiffService` OSGi dienst in componenten integreert). Dit is niet meer nodig voor de nieuwe functie voor Diff, aangezien het diff cliënt-kant via DOM vergelijking voorkomt.

Er zijn echter een aantal beperkingen die door de ontwikkelaar in overweging moeten worden genomen.

* Deze functie gebruikt CSS-klassen die geen naamruimte zijn met de AEM Product. Als andere aangepaste CSS-klassen of CSS-klassen van derden met dezelfde namen op de pagina worden opgenomen, kan dit van invloed zijn op de weergave van het diff.

   * `html-added`
   * `html-removed`
   * `cq-component-added`
   * `cq-component-removed`
   * `cq-component-moved`
   * `cq-component-changed`

* Omdat het diff cliënt-kant is en op paginading uitvoert, zullen om het even welke aanpassingen aan DOM nadat de cliënt-zijdiff dienst is in werking gesteld niet administratief worden verwerkt. Dit kan

   * Componenten die AJAX gebruiken om inhoud op te nemen
   * Toepassingen voor één pagina
   * Op JavaScript gebaseerde componenten die het DOM op gebruikersinteractie manipuleren.

