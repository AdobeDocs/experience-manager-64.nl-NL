---
title: Interactieve communicatie configuratieeigenschappen
seo-title: Eigenschappen van interactieve communicatieconfiguratie
description: Standaardconfiguratieeigenschappen voor interactieve communicatie bewerken
seo-description: Standaardconfiguratieeigenschappen voor interactieve communicatie bewerken
uuid: 793da9c0-7e8b-464c-b41d-559a72fac9eb
contentOwner: anujkapo
products: SG_EXPERIENCEMANAGER/6.4/FORMS
content-type: reference
topic-tags: interactive-communications
discoiquuid: 1aef2a51-4391-4075-8841-a62ace5606f9
translation-type: tm+mt
source-git-commit: 13d364ec820b48fb8b80da2ffd30faeeb7813a28
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 5%

---


# Interactieve communicatie configuratieeigenschappen {#interactive-communications-configuration-properties}

Standaardconfiguratieeigenschappen voor interactieve communicatie bewerken

Interactieve communicatie bevat eigenschappen die automatisch worden geconfigureerd na het installeren van het [AEM Forms-invoegtoepassing](/help/forms/using/installing-configuring-aem-forms-osgi.md)-pakket. De interactieve auteurs van de Communicatie kunnen deze standaardconfiguratieeigenschappen uitgeven gebruikend **Adobe Experience Manager Web Console Configuration** pagina.

Open de pagina **Adobe Experience Manager Web Console Configuration** met de volgende URL:

https://&lt;server>:&lt;port>/&lt;contextPath>/system/console/configMgr

De configuratie-eigenschappen omvatten:

* [Configuratie van documentfragmenten](#document-fragments-configuration)
* [Correspondentenconfiguratie maken](#create-correspondence-configuration)
* [Adaptieve vorm en interactieve communicatie Webkanaalconfiguratie](#adaptive-form-and-interactive-communication-web-channel-configuration)
* [Adaptieve vorm en interactieve communicatie webkanaalthemaconfiguratie](#adaptive-form-and-interactive-communication-web-channel-theme-configuration)

## Configuratie van documentfragmenten {#document-fragments-configuration}

Tik **Documentfragmenten Configuratie** op de pagina **Adobe Experience Manager Web Console Configuration** om de configuratie-eigenschappen voor documentfragmenten weer te geven.

<table> 
 <tbody> 
  <tr> 
   <td>Eigenschap</td> 
   <td>Beschrijving</td> 
   <td>Standaard</td> 
   <td>Acceptabele waarden</td> 
  </tr> 
  <tr> 
   <td>Indelingen voor gegevensweergave</td> 
   <td>Landspecifieke weergave-indeling voor velden, variabelen en formuliergegevensmodelelementen die beschikbaar zijn tijdens het maken van een interactieve communicatie voor afdruk- en webkanalen.</td> 
   <td> 
    <ul> 
     <li>locale = en_US, de_DE, fr_FR en ja_JP</li> 
     <li>dateFormat = dd-MM-yyyy</li> 
     <li>numberDecimalSeparator = .</li> 
     <li>numberGroupSeparator = ,</li> 
     <li>numberUseGroupSeparator = true</li> 
    </ul> </td> 
   <td><p>—</p> </td> 
  </tr> 
  <tr> 
   <td>Inspringing</td> 
   <td>De breedte van één inspringingseenheid die wordt toegepast op tekst in documentfragmenten van de lijst.</td> 
   <td>12,7 mm</td> 
   <td>Getal</td> 
  </tr> 
  <tr> 
   <td>Roman Numbers Minimum Width</td> 
   <td>Minimumbreedte die moet worden toegepast op het opsommingsteken of nummerveld bij gebruik van Romeinse nummers in documentfragmenten van de lijst. </td> 
   <td>12,7 mm</td> 
   <td>Getal</td> 
  </tr> 
  <tr> 
   <td>Minimumbreedte aantal</td> 
   <td>Minimumbreedte die moet worden toegepast op het opsommingsteken of nummerveld bij het gebruik van genummerde lijsten behalve Romeinse nummers in documentfragmenten van de lijst.</td> 
   <td>8,0 mm</td> 
   <td>Getal</td> 
  </tr> 
 </tbody> 
</table>

## Correspondentenconfiguratie {#create-correspondence-configuration} maken

Tik **Correspondence Configuration** op de pagina **Adobe Experience Manager Web Console Configuration** om de configuratieeigenschappen voor de gebruikersinterface van de Agent weer te geven.

| Eigenschap | Beschrijving | Standaard | Acceptabele waarden |
|---|---|---|---|
| Opgeloste inhoud tonen voor bewerking | Schakel het selectievakje in om de gevonden inhoud (werkelijke waarden in plaats van plaatsaanduidingen) weer te geven tijdens het bewerken van de tekstmodule in de gebruikersinterface van de agent. | Niet geselecteerd | Niet van toepassing |
| Watermerk toepassen tijdens voorvertoning | Schakel het selectievakje in om watermerk toe te passen op het kanaal voor interactieve communicatie afdrukken in de modus Voorbeeld. | Niet geselecteerd | Niet van toepassing |

## Adaptieve vorm en interactieve Communicatie de Configuratie van het Kanaal van het Web {#adaptive-form-and-interactive-communication-web-channel-configuration}

Tik **Adaptieve vorm en interactieve communicatie Web Channel Configuration** op de **Adobe Experience Manager Web Console Configuration**-pagina om de configuratieeigenschappen voor Adaptive Forms en Interactive Communications Web Channel weer te geven. De volgende lijst beschrijft de eigenschappen met betrekking tot Interactieve Mededelingen:

| Eigenschap | Beschrijving | Standaard | Acceptabele waarden |
|---|---|---|---|
| Tijdelijke aanduiding tonen | Schakel het selectievakje in om de weergave van plaatsaanduidingen in te schakelen voor velden die zijn opgenomen in adaptieve formulieren en interactieve communicatie. | Geselecteerd | Niet van toepassing |
| Maximum aantal cacheitems | Stel het maximumaantal adaptieve formulieren en interactieve communicatie in dat kan worden opgehaald met behulp van het cachegeheugen. | 100 | Getal |
| Bestandsnaam uniek maken | Schakel het selectievakje in om unieke namen te hebben voor bestanden die als bijlagen zijn opgenomen in Adaptieve Forms en Interactieve communicatie. | Niet geselecteerd | Niet van toepassing |

## Adaptieve vorm en Interactieve Communicatie het Thema van het Kanaal van het Web {#adaptive-form-and-interactive-communication-web-channel-theme-configuration}

Tik **Adaptief formulier en Interactieve communicatie Web Channel Thema Configuration** op de pagina **Adobe Experience Manager Web Console Configuration** om de configuratieeigenschappen voor Adaptieve Forms en Interactive Communications Web Channel-thema&#39;s weer te geven.

<table> 
 <tbody> 
  <tr> 
   <td>Eigenschap</td> 
   <td>Beschrijving</td> 
   <td>Standaard</td> 
   <td>Acceptabele waarden</td> 
  </tr> 
  <tr> 
   <td>Naam lettertypenlijst</td> 
   <td>Lijst met lettertypen die beschikbaar zijn voor gebruik tijdens het maken van Adaptieve Forms en Interactieve communicatie.</td> 
   <td><p>Georgia</p> <p>Boek-antiaqua</p> <p>Times New Roman</p> <p>Arial</p> <p>Arial Black</p> <p>Gevolgen</p> <p>Palatino Linotype</p> </td> 
   <td>Alle geldige Adobe-serverlettertypen</td> 
  </tr> 
 </tbody> 
</table>

