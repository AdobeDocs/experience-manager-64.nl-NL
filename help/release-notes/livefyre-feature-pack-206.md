---
title: Opmerkingen bij de release van Livefyre Feature Pack 2.0.6
seo-title: Opmerkingen bij de release van Livefyre Feature Pack 2.0.6
description: Opmerkingen bij de release van Livefyre Feature Pack 2.0.6
seo-description: Opmerkingen bij de release van Livefyre Feature Pack 2.0.6
uuid: 81ee0527-72c3-4530-80f1-c802ddbe62d0
products: SG_EXPERIENCEMANAGER/6.4
contentOwner: alba
discoiquuid: d445bcfb-7712-472f-bfb4-a8811c2bc4f1
translation-type: tm+mt
source-git-commit: 715cff841252d79504d702817f91db92df919bfc

---


# Opmerkingen bij de release van Livefyre Feature Pack 2.0.6 {#livefyre-feature-pack-release-notes}

## Geen informatie {#release-information}

<table> 
 <tbody>
  <tr>
   <td>Producten</td> 
   <td>Livefyre Feature Pack 2.0.6</td> 
  </tr>
  <tr>
   <td>Versie</td> 
   <td>2.0.6</td> 
  </tr>
  <tr>
   <td>Type</td> 
   <td>Functierelease</td> 
  </tr>
  <tr>
   <td>Date</td> 
   <td>31 augustus 2018</td> 
  </tr>
  <tr>
   <td>URL downloaden<br /> </td> 
   <td>Neem contact op met uw beheerder</td> 
  </tr>
  <tr>
   <td>Compatibiliteit (*)</td> 
   <td>AEM 6.4 SP1, 6.4, 6.3 GA en 6.2 SP1</td> 
  </tr>
  <tr>
   <td>Beschrijving</td> 
   <td>Met dit pakket kunt u de toonaangevende curatiemogelijkheden van Livefy integreren met uw AEM-instantie, zodat u in enkele minuten waardevolle door gebruikers gegenereerde inhoud (UGC) kunt publiceren van sociale netwerken naar uw site.</td> 
  </tr>
 </tbody>
</table>

## Wat bevat Livefyre Feature Pack 2.0.6 {#what-is-included-in-livefyre-feature-pack}

Dit pakket integreert de toonaangevende mogelijkheden van Livefyre voor curatieve doeleinden met uw AEM-instantie, zodat u in enkele minuten waardevolle door gebruikers gegenereerde inhoud (UGC) kunt publiceren van sociale netwerken naar uw site. Dit pakket bestaat uit drie verschillende onderdelen:

**UGC-inhoud importeren in AEM-elementen**

* Importeer door gebruikers gegenereerde Twitter- en Instagram-inhoud (UGC) van Livefyre Studio naar AEM Assets met de UGC-importmodule.
* Open de bibliotheek van Livefy.
* Op Twitter en Instagram kunt u in real-time zoeken met LiveCycle Social Search.
* Rechten op de UGC beheren.

**Livefycomponenten toevoegen aan AEM-sites of -gemeenschappen**

* Creëer en pas onmiddellijk dynamische en boeiende ervaringen aan gebruikend een reeks Sociale Componenten met inbegrip van Kaarten, Galerieën, en de Walen van Media.
* UGC publiceren in AEM-sites of -gemeenschappen.

**Productcatalogi met AEM Commerce in Livefyre importeren**

* Naadloos uw bestaande productcatalogus integreren in Livefyre om de betrokkenheid en conversie van gebruikers in uw sites te stimuleren, en om onvoorstelbare UGC-ervaringen te bieden.
* Bewerk of verwijder items in uw AEM Commerce-productcatalogus en werk de wijzigingen in LiveCycle automatisch bij.

Zie [Integreren met Livefyre](https://https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/livefyre.html)voor hulp bij de installatie.

### Aanvullende releasegegevens {#additional-release-information}

Vanwege updates die van invloed zijn op de aggregatie van inhoud van niet-zakelijke gebruikersaccounts in Instagram, kunnen we geen opmerkingen meer namens u plaatsen of automatisch controleren op antwoorden van de auteur. [Klik hier voor meer](https://developers.facebook.com/blog/post/2018/04/04/facebook-api-platform-product-changes/)informatie.

>[!NOTE]
>
>Livefyre Feature Pack 2.0.6 biedt geen ondersteuning voor AEM Classic UI.

#### Nieuwe functie of verbetering {#new-feature-or-improvement}

* De mogelijkheid om UGC te doorzoeken voordat rechten worden ingesteld, is toegevoegd aan de mogelijkheid om sociale accounts aan te vragen in LiveCycle. U moet sociale accounts instellen om rechten aan te vragen of de aanvraag voor rechten overschrijven als u eigenaar bent van de inhoud.
* De workflow [voor het aanvragen van Instagram- en Twitter-](https://https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/livefyre.html) UGC-rechten is bijgewerkt en voldoet aan de nieuwste API&#39;s.
* De status van rechten en de aangewezen acties worden nu getoond op het scherm van het rechtenverzoek.

#### Bugfixes {#bug-fixes}

* Probleem verholpen waarbij bij het verwijderen van een sociaal account in LiveCyre Studio dat wordt gebruikt voor rechtenaanvraag, een fout is opgetreden bij het laden van de UGC-bibliotheek in AEM.
* Probleem verholpen waarbij het aantal elementen in de Livefyre-studio niet overeenkwam met het aantal elementen in de AEM UGC-bibliotheek.
* Probleem verholpen in de UGC-bibliotheek waarbij gefilterde resultaten werden weergegeven nadat de filteropties opnieuw waren ingesteld.
* Probleem verholpen met AEM Commerce waarbij de aanroep naar actie-knoppen gebruikers omleidden naar de onjuiste URL.
* Probleem verholpen in AEM-sites waarbij het slepen en neerzetten van meerdere componenten in de tijdelijke aanduiding voor het parsys ertoe leidde dat deze verdwijnde.
* Correctie van een probleem waarbij sociale accounts met een handicap konden worden geselecteerd bij het verzenden van een aanvraag voor rechten.
* Probleem verholpen waarbij het slepen en neerzetten van UGC van elementen naar sites tot een fout leidde.
* Probleem verholpen waarbij het slepen en neerzetten van Chat- en LiveBlog-componenten naar Sites de app niet maakten.
* Probleem verholpen waarbij de toepassing Opmerking een fout veroorzaakte toen gebruikers probeerden opmerkingen te maken.
* Probleem verholpen waarbij het toevoegen van de Livefyre Media Wall-app aan een site een extra knooppunt maakte in de Java Content Repository.
* Probleem verholpen waarbij pagina-einden en consolefouten werden veroorzaakt in UGC-zoekopdracht in Instagram.
* Probleem verholpen waarbij met pictogrammen voor gebruikers van Instagram API-fouten in Elementen werden gegenereerd.
* Probleem verholpen waarbij de app Revisies werd toegevoegd aan een site zonder vooraf gedefinieerde indeling.
* Probleem verholpen met de functie Touch UI en inline bewerken.
* Probleem verholpen die een fout veroorzaakt bij het importeren van bepaalde Instagram-afbeeldingselementen.
* Probleem verholpen waarbij de LiveCyre HTTP-client in AEM proxyconfiguratie niet ondersteunt.

