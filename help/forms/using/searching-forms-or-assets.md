---
title: Zoeken naar formulieren en middelen
seo-title: Searching for forms and assets
description: U kunt formulieren en elementen in uw AEM zoeken met AEM zoekopdracht. Met basis- en geavanceerd zoeken kunt u snel uw middelen vinden.
seo-description: You can search forms and assets in your AEM instance using AEM search. Basic and advanced search allows you to quickly locate your assets.
uuid: db6970aa-910a-4190-9790-9ffbbdc8adcc
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-manager
discoiquuid: f7f19679-cfc2-4ac0-9a26-685fad09276f
role: Admin
exl-id: c6e5c19a-9d93-470f-916e-7ef06c3de141
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '720'
ht-degree: 0%

---

# Zoeken naar formulieren en middelen {#searching-for-forms-and-assets}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

U kunt naar uw formulieren of formulierelementen zoeken met behulp van een tekenreeks of tekenreeks, samen met jokertekens. U kunt uw zoekopdracht ook beperken aan de hand van de criteria die beschikbaar zijn in verschillende categorieën in het deelvenster Zoeken.

Wanneer u een of meer criteria selecteert en ook een tekenreeks opgeeft, wordt het snijpunt van de tekst en criteria geretourneerd als zoekresultaten. De zoekresultaten zijn net zo goed als de metagegevens voor formulieren en middelen die worden verstrekt.

Klikken ![aem6forms_search](assets/aem6forms_search.png)om het zoekvenster weer te geven of te verbergen.

## Basiszoekopdracht {#basic-search}

Een basiszoekopdracht is de standaardzoekopdracht, uitgevoerd zonder filters op te geven. AEM Forms voert een volledige tekstzoekopdracht uit naar eigenschappen van metagegevens.

Als u een standaardzoekopdracht wilt uitvoeren, voert u de zoekquery in het tekstveld in en kiest u Enter. U kunt ook het jokerteken (&amp;ast;) invoeren, zodat dit overeenkomt met een willekeurig aantal tekens.

Adobe Experience Manager zoekt naar de ingevoerde tekst in eigenschappen van metagegevens en retourneert de corresponderende resultaten. Als u meer dan één woord typt, komt de zoekbewerking overeen met de volledige zoektekst.

Neem nota van de volgende punten over het basisonderzoek:

* De zoekopdracht wordt uitgevoerd met de metagegevenseigenschappen van het formulier en het element.
* Als u meer dan één woord typt, komt de zoekbewerking overeen met de volledige zoektekst.
* Zoeken is niet hoofdlettergevoelig. Wanneer u bijvoorbeeld `geometrixx`, elementen met titels `Geometrixx`, `GEOMETRIXX`, en `GeoMetRixx` worden weergegeven in de zoekresultaten.

* Gedeeltelijke overeenkomsten van een woord worden niet ondersteund. Gebruik &amp;ast om te zoeken met gedeeltelijke tekenreeksen. jokerteken. Als de zoekquery echter overeenkomt met een volledig woord, wordt het bijbehorende formulier of element weergegeven.
* Extra spaties worden gerespecteerd en worden niet bijgesneden tijdens het zoeken. Bijvoorbeeld: `My form` is niet dezelfde zoekquery als `My form`.

* Als de gegevens en weergavewaarden van de velden in metagegevenseigenschappen verschillend zijn, kunt u geen weergavewaarden gebruiken als zoekparameters. U kunt bijvoorbeeld niet zoeken op basis van een status, zoals Gewijzigd of Gepubliceerd, omdat deze eigenschappen in een andere indeling zijn opgeslagen.

## Geavanceerd zoeken {#advanced-search}

Naast de query kunt u in de zoekcriteria enkele zoekparameters opgeven om de standaardzoekopdracht efficiënter en gerichter te maken.

![Zoekveld en parameters of filters voor AEM zoeken in formulieren en middelen](assets/search_forms_assets.png)

### Middelpad {#asset-path}

Met het filter elementpad kunt u de zoekresultaten beperken tot de huidige map. Als de optie Zoeken in huidige map niet is geselecteerd, bevatten de zoekresultaten elementen uit de basismap. Als de huidige pagina geen map is en de optie &quot;Zoeken in huidige map&quot; is geselecteerd, retourneert de zoekopdracht de elementen in de bovenliggende map.

### Wijziging van element {#asset-modification}

Selecteer een van de volgende opties om te zoeken in alle elementen die binnen een bepaalde tijdsperiode zijn gewijzigd.

| **Optie** | **Beschrijving** |
|---|---|
| Twee uur geleden | Zoeken in alle elementen die in de afgelopen twee uur zijn gewijzigd. |
| Een week geleden | Zoeken in alle elementen die de afgelopen week zijn gewijzigd. |
| Een maand geleden | Zoeken in alle elementen die in de afgelopen maand zijn gewijzigd. |
| Een jaar geleden | Zoeken in alle elementen die in het afgelopen jaar zijn gewijzigd. |

### Status van element {#asset-status}

U kunt naar elementen zoeken met een van de volgende statussen:

* **Gepubliceerd**: Zoeken in alle elementen die na publicatie zijn gepubliceerd en niet zijn gewijzigd.

* **Ongepubliceerd**: Zoeken in alle elementen die nooit zijn gepubliceerd.

* **Gewijzigd**: Zoeken in alle elementen die na publicatie zijn gewijzigd of niet zijn gepubliceerd.

### Elementtype {#asset-type}

U kunt een willekeurig aantal elementtypen selecteren. De zoekopdracht retourneert de samenvoeging van alle geselecteerde elementtypen.

<table> 
 <tbody>
  <tr>
   <th>Optie</th> 
   <th>Beschrijving</th> 
  </tr>
  <tr>
   <td>Formuliersjabloon<br /> </td> 
   <td>Zoeken in alle formuliersjablonen.<br /> </td> 
  </tr>
  <tr>
   <td>PDF-formulier</td> 
   <td>Doorzoek alle PDF-documenten.</td> 
  </tr>
  <tr>
   <td>Document</td> 
   <td>Zoeken in alle documenten.</td> 
  </tr>
  <tr>
   <td>Adaptief formulier<br /> </td> 
   <td>Zoeken in alle adaptieve formulieren.</td> 
  </tr>
  <tr>
   <td>Resource</td> 
   <td>Zoeken in alle bronnen.<br /> </td> 
  </tr>
 </tbody>
</table>

### Tags {#tags}

Tags zijn labels die zijn gekoppeld aan elementen ter identificatie. Selecteer tijdens het zoeken een willekeurig aantal tags in de vervolgkeuzelijst of voeg indien nodig aangepaste tags toe. Een zoekresultaat bevat de doorsnede van de geselecteerde tags.
