---
title: Windows 10 Player implementeren
seo-title: Windows 10 Player implementeren
description: 'Volg deze pagina voor meer informatie over het configureren van AEM Screens Windows 10 player. '
seo-description: 'Volg deze pagina voor meer informatie over het configureren van AEM Screens Windows 10 player. '
uuid: cdd7e9f1-f836-4d52-8026-80537a6623ca
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.4/SCREENS
topic-tags: administering
content-type: reference
discoiquuid: 9b66225a-a893-491b-b47c-ae7b3048ed80
translation-type: tm+mt
source-git-commit: c8694726dc29b391a157db3ef230f21517c957bd

---


# Windows 10 Player implementeren{#implementing-windows-player}

In deze sectie wordt beschreven hoe u AEM Screens Windows 10 Player configureert. Het verstrekt informatie van het configuratiedossier en de beschikbare opties en aanbevelingen met betrekking tot welke montages voor ontwikkeling en het testen te gebruiken.

## Windows Player installeren {#installing-windows-player}

Installeer Windows Player voor AEM-schermen om Windows Player voor AEM-schermen te implementeren.

Ga naar de pagina [**AEM 6.4 Player Downloads **](https://download.macromedia.com/screens/).

### Ad hoc-methode {#ad-hoc-method}

De ad hoc methode om de recentste Speler van Vensters (*.exe*) te installeren, bezoek [**AEM 6.4 Player downloadt **](https://download.macromedia.com/screens/)pagina.

Nadat u de toepassing hebt gedownload, voert u de stappen op de speler uit om de ad-hocinstallatie te voltooien:

1. Druk op de linkerbovenhoek om het beheerpaneel te openen.
1. Navigeer naar **Configuratie** van het linkeractiemenu en ga de plaats (adres) van de instantie AEM in u wenst om te verbinden met en klik **sparen**.

1. Klik op de koppeling **Registratie** in het linkeractiemenu om het registratieproces van het apparaat te voltooien.

### Meerdere Windows 10-spelers registreren met één configuratie {#registering-multiple-windows-players-with-one-configuration}

Nadat u de Windows-speler hebt geïnstalleerd, kunt u meerdere spelers registreren met één configuratie.

>[!NOTE]
>
>**Bulkregistratie van Windows Player**
>
>Wanneer u de venstersspeler implementeert, hoeft u niet elke speler handmatig te configureren. In plaats daarvan kunt u het JSON-configuratiebestand bijwerken nadat het is getest en klaar is voor implementatie.
>
>De configuratie zal ervoor zorgen dat alle spelers de zelfde server pingelen die in het configuratiedossier wordt verstrekt. U moet elke speler nog steeds handmatig registreren.

Voer de onderstaande stappen uit om Windows 10 Player te configureren:

1. Installeer Windows Player.
1. Zoek het configuratiebestand onder ***%appdata%\com.adobe.aem.screens.player\config.json***.
1. Werk de configuratie-JSON bij met behulp van de onderstaande informatie en kopieer vervolgens dezelfde map naar alle systemen waar de speler zich bevindt.

### Beleidskenmerken {#policy-attributes}

De volgende lijst vat de beleidsattributen met een voorbeeldbeleid JSON ter verwijzing samen:

| **Beleidsnaam** | **Doel** |
|---|---|
| server | De URL naar de AEM-server (Adobe Experience Manager). |
| resolutie | De resolutie van het apparaat. |
| rebootSchedule | Het programma om de speler opnieuw op te starten. |
| enableAdminUI | Schakel de interface van Admin in om het apparaat op de site te configureren. Ingesteld op false zodra deze volledig is geconfigureerd en in productie is. |
| enableOSD | Schakel de interface van de kanaalschakelaar voor gebruikers in om kanalen op het apparaat te schakelen. Denk na plaatsend aan vals zodra het volledig en in productie wordt gevormd. |
| enableActivityUI | Schakel deze optie in om de voortgang van activiteiten zoals downloaden en synchroniseren weer te geven. Laat voor het oplossen van problemen toe en maak onbruikbaar zodra het volledig en in productie wordt gevormd. |

#### JSON-bestand met voorbeeldbeleid {#example-policy-json-file}

```
{
    "server": "http://localhost:4502",
    "resolution": "auto",
    "rebootSchedule": "at 4:00 am",
    "enableAdminUI": false,
    "enableOSD": false,
    "enableActivityUI": false
}
```

