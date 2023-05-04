---
title: "Correspondentenbeheer: Problemen oplossen"
seo-title: Correspondence Management Troubleshooting
description: Problemen met Correspondentenbeheer oplossen
seo-description: Correspondence Management Troubleshooting
uuid: 25828cdd-110e-4a84-8f31-d82cd610a54f
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: correspondence-management
discoiquuid: cc473808-e71a-4834-bb30-91e6df783e60
feature: Correspondence Management
exl-id: 82a35d81-13d0-435f-875e-6fd0a6d574d5
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 0%

---

# Correspondentenbeheer: Problemen oplossen {#correspondence-management-troubleshooting}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Fouten bij het opslaan van een letter {#errors-when-saving-a-letter}

### Probleem {#issue}

Een van de volgende fouten wordt weergegeven bij het opslaan van een letter:

* Gegevensbinding niet aanwezig voor de tekstmodule
* Geef de benodigde eigenschapgegevens op voor het volgende:

### Reden {#reason}

Deze fouten kunnen optreden als gevolg van een van de volgende gebeurtenissen:

* Een gegevenswoordenboek is gebonden aan de letter, maar is niet aanwezig op de server.
* Een gegevenswoordenboek is gebonden aan de letter, maar heeft een onderstrepingsteken (_) in de naam.

### Workaround {#workaround}

Zorg ervoor dat het gegevenswoordenboek dat u in de letter gebruikt, aanwezig is op de server en geen onderstrepingsteken (_) in de naam heeft.

## Fout bij voorvertonen van een letter {#error-when-previewing-a-letter}

### Probleem {#issue-1}

Tijdens het voorvertonen van een letter geeft de fout &quot;Fout bij het laden van de letter: Kan element niet importeren uit XML-invoer.&quot; verschijnt zelfs wanneer een eerder niet-gepubliceerd tekstelement in de letter is gepubliceerd.

### Workaround {#workaround-1}

Stel de lettercache op de publicatieinstantie opnieuw in door de volgende stappen uit te voeren en probeer de letter vervolgens opnieuw weer te geven:

1. Ga naar **`https://[server]:[port]/[contextPath]/system/console/configMgr`** en meld u aan als Admin.
1. Selecteren **Correspondentiebeheerconfiguraties**.
1. In **Correspondentiebeheerconfiguraties**, uitschakelen **Lettercache inschakelen** en klik vervolgens op **Opslaan.**
1. Inschakelen **Lettercache inschakelen** en klik vervolgens op **Opslaan**.
1. Bekijk de brief opnieuw.
