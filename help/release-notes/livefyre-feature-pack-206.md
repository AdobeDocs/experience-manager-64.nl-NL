---
title: Opmerkingen bij de release van Livefyre Feature Pack 2.0.6
seo-title: Livefyre Feature Pack 2.0.6 Release Notes
description: Opmerkingen bij de release van Livefyre Feature Pack 2.0.6
seo-description: Livefyre Feature Pack 2.0.6 Release Notes
uuid: 81ee0527-72c3-4530-80f1-c802ddbe62d0
products: SG_EXPERIENCEMANAGER/6.4
contentOwner: alba
discoiquuid: d445bcfb-7712-472f-bfb4-a8811c2bc4f1
exl-id: e09d2d59-41f0-4cf2-bcf3-ec3dbc3b8474
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '679'
ht-degree: 0%

---

# Opmerkingen bij de release van Livefyre Feature Pack 2.0.6 {#livefyre-feature-pack-release-notes}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Geen informatie {#release-information}

| Producten | Livefyre Feature Pack 2.0.6 |
|--- |--- |
| Versie | 2.0.6 |
| Type | Functierelease |
| Datum | 31 augustus 2018 |
| URL downloaden | Neem contact op met uw beheerder |
| Compatibiliteit (*) | AEM 6.4 SP1, 6.4, 6.3 GA en 6.2 SP1 |
| Beschrijving | Met dit pakket kunt u de toonaangevende curatiemogelijkheden van Livefy integreren met uw AEM-instantie, zodat u in enkele minuten waardevolle door gebruikers gegenereerde inhoud (UGC) kunt publiceren van sociale netwerken naar uw site. |

## Wat bevat Livefyre Feature Pack 2.0.6 {#what-is-included-in-livefyre-feature-pack}

Met dit pakket worden de toonaangevende mogelijkheden van Livefyre voor het beperken van de systeemprestaties geïntegreerd met uw AEM-instantie, zodat u in enkele minuten waardevolle door gebruikers gegenereerde inhoud (UGC) kunt publiceren van sociale netwerken naar uw site. Dit pakket bestaat uit drie verschillende onderdelen:

**UGC-inhoud importeren in AEM Assets**

* Importeer Twitter- en Instagram door gebruikers gegenereerde inhoud (UGC) van Livefyre Studio naar AEM Assets met de UGC-importmodule.
* Open de bibliotheek van Livefy.
* Met LiveCycle Social Search kunt u in real-time zoeken op Twitter en Instagram.
* Rechten op de UGC beheren.

**Livefycomponenten toevoegen aan AEM Sites of Community**

* Creëer en pas onmiddellijk dynamische en boeiende ervaringen aan gebruikend een reeks Sociale Componenten met inbegrip van Kaarten, Galerieën, en de Walen van Media.
* Publiceer UGC in AEM Sites of Communities.

**Productcatalogi met AEM handel in LiveCyre importeren**

* Naadloos uw bestaande productcatalogus integreren in Livefyre om de betrokkenheid en conversie van gebruikers in uw sites te stimuleren, en om onvoorstelbare UGC-ervaringen te bieden.
* Bewerk of verwijder items in de catalogus met producten voor AEM handel en werk de wijzigingen in LiveCycle automatisch bij.

Voor hulp bij de installatie raadpleegt u [Integreren met Livefyre](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/livefyre.html).

### Aanvullende releasegegevens {#additional-release-information}

Vanwege updates die van invloed zijn op de aggregatie van inhoud van niet-zakelijke gebruikersaccounts in Instagram, kunnen we geen opmerkingen meer namens u plaatsen of automatisch controleren op antwoorden van de auteur. [Klik hier voor meer informatie](https://developers.facebook.com/blog/post/2018/04/04/facebook-api-platform-product-changes/).

>[!NOTE]
>
>Livefyre Feature Pack 2.0.6 biedt geen ondersteuning voor AEM Klassieke UI.

#### Nieuwe functie of verbetering {#new-feature-or-improvement}

* De mogelijkheid om UGC te doorzoeken voordat rechten worden ingesteld, is toegevoegd aan de mogelijkheid om sociale accounts aan te vragen in LiveCycle. U moet sociale accounts instellen om rechten aan te vragen of de aanvraag voor rechten overschrijven als u eigenaar bent van de inhoud.
* Instagram en Twitter [Workflow voor aanvraag van UGC-rechten](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/livefyre.html) is bijgewerkt om te voldoen aan de nieuwste API&#39;s.
* De status van rechten en de aangewezen acties worden nu getoond op het scherm van het rechtenverzoek.

#### Bugfixes {#bug-fixes}

* Probleem verholpen waarbij bij het verwijderen van een sociaal account in LiveCycle Studio dat wordt gebruikt voor rechtenaanvraag, een fout is opgetreden bij het laden van de UGC-bibliotheek in AEM.
* Probleem verholpen waarbij het aantal elementen in de Livefyre-studio niet overeenkwam met het aantal elementen in de AEM UGC-bibliotheek.
* Probleem verholpen in de UGC-bibliotheek waarbij gefilterde resultaten werden weergegeven nadat de filteropties opnieuw waren ingesteld.
* Probleem verholpen met AEM Commerce waarbij de vraag-aan-actie knopen gebruikers aan onjuiste URL opnieuw richtten.
* Probleem verholpen in AEM Sites waarbij het slepen en neerzetten van meerdere componenten in de tijdelijke aanduiding voor parsys ervoor zorgde dat deze verdwenen.
* Correctie van een probleem waarbij sociale accounts met een handicap konden worden geselecteerd bij het verzenden van een aanvraag voor rechten.
* Probleem verholpen waarbij het slepen en neerzetten van UGC van elementen naar sites tot een fout leidde.
* Probleem verholpen waarbij het slepen en neerzetten van Chat- en LiveBlog-componenten naar Sites de app niet maakten.
* Probleem verholpen waarbij de toepassing Opmerking een fout veroorzaakte toen gebruikers probeerden opmerkingen te maken.
* Probleem verholpen waarbij het toevoegen van de Livefyre Media Wall-app aan een site een extra knooppunt maakte in de Java Content Repository.
* Probleem verholpen dat pagina-einden en consolefouten veroorzaakte in Instagram UGC-zoekopdracht.
* Probleem verholpen waarbij Instagram-gebruikerspictogrammen API-fouten in Elementen genereerden.
* Probleem verholpen waarbij de app Revisies werd toegevoegd aan een site zonder vooraf gedefinieerde indeling.
* Probleem verholpen met de functie Touch UI en inline bewerken.
* Probleem verholpen die een fout veroorzaakt bij het importeren van bepaalde Instagram-afbeeldingselementen.
* Probleem verholpen waarbij de LiveCyre HTTP-client in AEM geen proxyconfiguratie ondersteunt.
