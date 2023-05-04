---
title: Records uit de taakbeheerdatabase wissen
seo-title: Purge records from the Job Manager database
description: Grote procesgegevens kunnen resulteren in lagere AEM formulierprestaties. Het is een goede gewoonte om procesgegevens te wissen wanneer records niet meer nodig zijn.
seo-description: Large process data can result in lower AEM forms performance. It is good practice to purge process data when records are no longer necessary.
uuid: cf214498-36e9-4dcc-b4d4-e7c46f80dbab
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/health_monitor
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 69a406f2-4fa8-40bb-b671-7b0f5b6a2c4c
exl-id: be2e2a4b-5aac-4612-81b6-b4bbb3036d77
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 0%

---

# Records uit de taakbeheerdatabase wissen {#purge-records-from-the-job-manager-database}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Procesgegevens die worden gegenereerd wanneer een langdurig proces wordt aangeroepen, kunnen te groot worden, wat resulteert in lagere AEM formulierprestaties en het gebruik van overbodige schijfruimte. Het is een goede gewoonte om procesgegevens te wissen wanneer records niet meer nodig zijn.

U kunt beheerconsole gebruiken om een eenmalige verwijdering van verouderde records uit te voeren of om regelmatige automatische verwijdering te plannen. Andere methoden voor het verwijderen van overbodige records worden besproken in [Procesgegevens wissen](/help/forms/using/admin-help/purging-process-data.md#purging-process-data).

**De pagina Job Purge Scheduler openen**

1. Klik in de beheerconsole op Health Monitor in de rechterbovenhoek van de pagina.
1. Klik op het tabblad Planfunctie voor taakverwijdering.

De informatie over om het even welke momenteel geplande zuiveringen wordt getoond in de doos van de Informatie van de Planner van de Woorden van de Weg.

>[!NOTE]
>
>Als u op Planner stoppen klikt, worden in de toekomst geplande reinigingsprogramma&#39;s gestopt, maar wordt een taak die al wordt uitgevoerd, niet gestopt.

**Eenmalige verwijdering plannen**

1. Selecteer slechts één keer.
1. Geef in het gebied Filter Voltooide records wissen het aantal dagen of weken op waarna een record als verouderd en gereed voor verwijdering wordt beschouwd.

   >[!NOTE]
   >
   >Records die betrekking hebben op processen die niet zijn voltooid, worden niet gezuiverd, zelfs niet als ze ouder zijn dan de opgegeven leeftijd.

1. Geef op wanneer het leegmaken moet plaatsvinden. Schakel het selectievakje Huidige datum en tijd gebruiken in of schakel het selectievakje uit en klik op de pictogrammen Kalender en Klok om de datum en tijd op te geven waarop het leegmaken wordt uitgevoerd.

   >[!NOTE]
   >
   >Als u een begindatum en tijd opgeeft die in het verleden liggen, wordt de verwijdering onmiddellijk uitgevoerd wanneer u op Planner starten klikt.

1. Klik op Start Scheduler. Om het even welke eerder geplande plannermontages worden vervangen met de nieuwe montages.

**Een schema voor automatisch leegmaken configureren**

1. Selecteer Opnieuw uitvoeren om en geef het aantal dagen of weken tussen de purges op.
1. Geef in het gebied Filter Voltooide records wissen het aantal dagen of weken op waarna een record als verouderd en gereed voor verwijdering wordt beschouwd. U kunt de waarde niet instellen op `0`.

   >[!NOTE]
   >
   >Records die betrekking hebben op processen die niet zijn voltooid, worden niet gezuiverd, zelfs niet als ze ouder zijn dan de opgegeven leeftijd.

1. Geef op wanneer de purges moeten beginnen. Schakel het selectievakje Huidige datum en tijd gebruiken in of schakel het selectievakje uit en klik op de pictogrammen Kalender en Klok om de datum en tijd op te geven waarop het leegmaken wordt uitgevoerd.

   >[!NOTE]
   >
   >Als u een begindatum en -tijd opgeeft die in het verleden liggen, berekent AEM formulieren de logische volgende begindatum op basis van de opgegeven datum. Als u bijvoorbeeld plant dat de taak wekelijks wordt leeggemaakt vanaf 7 april en dat nu 9 april is, vindt de eerste leegloop plaats op 14 april.

1. Klik op Start Scheduler. Om het even welke eerder geplande plannermontages worden vervangen met de nieuwe montages.
