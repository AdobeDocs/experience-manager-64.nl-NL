---
title: Afdrukwaarden instellen voor gebruik met Acrobat Reader DC-extensies
seo-title: Setting timeout values for use with Acrobat Reader DC extensions
description: Leer hoe u time-outwaarden instelt voor gebruik met Acrobat Reader DC-extensies.
seo-description: Learn how to set timeout values for use with Acrobat Reader DC extensions.
uuid: d6d072a0-0a30-417a-98b1-df8b4ff8f911
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_acrobat_reader_dc_extensions
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: a9aeeb89-45e9-4d5d-aa25-8145c89b64f2
exl-id: e7de9971-3eac-4248-8709-0da7dd709d1b
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 0%

---

# Afdrukwaarden instellen voor gebruik met Acrobat Reader DC-extensies  {#setting-timeout-values-for-use-with-acrobat-reader-dc-extensions}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Wanneer u werkt aan veel PDF-bestanden in Acrobat Reader DC-extensies, moet u ervoor zorgen dat de volgende time-outwaarden op de juiste wijze zijn ingesteld om te voorkomen dat taken op het juiste moment worden uitgevoerd en mislukken:

**Tijdslimiet voor verwijdering van document**

Deze waarde kan in beleidsconsole worden geplaatst. Klik op Instellingen > Core System Settings > Configurations en geef een waarde op voor Default Document Disposal Timeout.

**Tijdslimiet voor AEM van gebruikersbeheer:** Deze waarde kan worden ingesteld door het bestand config.xml te bewerken. Klik in de beheerconsole op Instellingen > Gebruikersbeheer > Configuratie > Configuratiebestanden importeren en exporteren en klik vervolgens op Exporteren. Open het geëxporteerde bestand config.xml en bewerk de volgende regels:

&lt;entry key=&quot;assertionValidityInMinutes&quot; value=&quot;600&quot;/>

&lt;entry key=&quot;SessionTimeout&quot; value=&quot;600&quot;/>

Sla het bestand config.xml op en importeer het vervolgens weer in de beheerconsole.

**Time-out sessie toepassingsserver:** Deze waarde kan op de toepassingsserver worden ingesteld. Raadpleeg de documentatie bij de toepassingsserver voor meer informatie.
