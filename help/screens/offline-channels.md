---
title: Offlinekanalen
seo-title: Offlinekanalen
description: 'De AEM Screens Player biedt offline ondersteuning voor kanalen door gebruik te maken van de ContentSync-technologie. Volg deze pagina voor meer informatie over updatehandlers en het inschakelen van offlineconfiguratie voor een kanaal.  '
seo-description: 'De AEM Screens Player biedt offline ondersteuning voor kanalen door gebruik te maken van de ContentSync-technologie. Volg deze pagina voor meer informatie over updatehandlers en het inschakelen van offlineconfiguratie voor een kanaal.  '
uuid: 25766e79-a5a5-4b84-b235-e3050f725fbe
contentOwner: Jyotika Syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/SCREENS
topic-tags: developing
discoiquuid: 609d5405-138f-47f7-9ac0-efaa32f8715b
translation-type: tm+mt
source-git-commit: cdec5b3c57ce1c80c0ed6b5cb7650b52cf9bc340

---


# Offlinekanalen{#offline-channels}

De schermspeler biedt offline ondersteuning voor de kanalen door gebruik te maken van de ***ContentSync*** -technologie.

De spelers gebruiken een lokale http server om de ongezipte inhoud te dienen.

Wanneer een kanaal wordt gevormd om *online* in werking te stellen, dient de speler de kanaal-middelen door tot de server toegang te hebben AEM maar wanneer het kanaal wordt gevormd om *off-line* in werking te stellen, dient de speler de kanaal-middelen van een lokale server http.

De workflow voor het proces is als volgt:

1. De gewenste pagina(&#39;s) parseren
1. Alle gerelateerde activa verzamelen
1. Alles verpakken in een ZIP-bestand
1. Het postvak downloaden en lokaal uitpakken
1. Lokale kopie van de inhoud weergeven

## Handlers bijwerken {#update-handlers}

De ***ContentSync*** gebruikt updatemanagers om alle noodzakelijke pagina&#39;s en activa voor een specifiek project te ontleden en te verzamelen. In AEM-rasters worden de volgende updatehandlers gebruikt:

### Algemene opties {#common-options}

* *type*: het updatehandlertype dat moet worden gebruikt
* *pad*: pad naar de bron
* *[targetRootDirectory]*: doelmap in het ZIP-bestand

<table> 
 <tbody>
  <tr>
   <td><strong>Type</strong></td> 
   <td><strong>Beschrijving</strong></td> 
   <td><strong>Opties</strong></td> 
  </tr>
  <tr>
   <td> kanalen</td> 
   <td>verzamelt een kanaal</td> 
   <td>extensie: uitbreiding van de bron die moet worden verzameld<br /> [pathSuffix='']: achtervoegsel voor toevoegen aan kanaalpad<br /> [deep=true]: of onderliggende pagina's recursief<br /> moeten worden geparseerd [includeImages=true]: neemt alle afbeeldingen op in het kanaal<br /> [includeVideos=true]: Alle video's opnemen in het kanaal<br /> [includeProducts=true]: alle producten in het kanaal opnemen</td> 
  </tr>
  <tr>
   <td>clientlib</td> 
   <td>de opgegeven clientbibliotheek verzamelen</td> 
   <td>[extension='']: kan css of js zijn, om alleen de eerste of alleen de laatste te verzamelen</td> 
  </tr>
  <tr>
   <td>assetrendities</td> 
   <td>de rendities van het element verzamelen</td> 
   <td>[renditions=[]]: lijst met te verzamelen vertoningen. Wordt standaard ingesteld op de oorspronkelijke uitvoering</td> 
  </tr>
  <tr>
   <td>kopiëren</td> 
   <td>de opgegeven structuur kopiëren vanuit het pad</td> 
   <td> </td> 
  </tr>
 </tbody>
</table>

### Configuratie van ContentSync testen {#testing-contentsync-configuration}

Voer de onderstaande stappen uit om de ContentSync-configuratie te testen:

1. Open [http://localhost:4502/libs/cq/contentsync/content/console.html](http://localhost:4502/libs/cq/contentsync/content/console.html)
1. Selecteer uw config in de lijst
1. Klik op Cache wissen
1. Klik op Cache bijwerken
1. Klik op Volledige download
1. Het ZIP-bestand extraheren
1. Een lokale server starten in de uitgepakte map
1. De startpagina openen en de status van uw app controleren

## Offlineconfig voor een kanaal inschakelen {#enabling-offline-config-for-a-channel}

Volg de onderstaande stappen om offline config voor een kanaal toe te laten:

1. Controleer de kanaalinhoud en controleer of deze wordt opgevraagd bij een AEM-instantie (Online).

   ![chlimage_1-15](assets/chlimage_1-15.png)

1. Navigeer naar het kanaaldashboard en klik op **... **in het** venster INFORMATIE OVER KANAAL **Panel om de eigenschappen te wijzigen.

   ![chlimage_1-16](assets/chlimage_1-16.png)

1. Navigeer naar de kanaaleigenschappen en controleer of het selectievakje is uitgeschakeld onder het tabblad **Kanaal** . Klik op **Opslaan en sluiten**.

   ![screen_shot_2017-12-19at122422pm](assets/screen_shot_2017-12-19at122422pm.png)

   Klik op Offlineinhoud **** bijwerken voordat de inhoud correct op het apparaat wordt geïmplementeerd.

   ![screen_shot_2017-12-19at122637pm](assets/screen_shot_2017-12-19at122637pm.png)

   De status **Off line** onder **EIGENSCHAPPEN** wordt ook dienovereenkomstig bijgewerkt.

   ![screen_shot_2017-12-19at124735pm](assets/screen_shot_2017-12-19at124735pm.png)

1. Controleer de kanaalinhoud en controleer of deze wordt opgevraagd bij de lokale Player-Cache.

   ![chlimage_1-17](assets/chlimage_1-17.png)

