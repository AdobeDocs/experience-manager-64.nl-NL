---
title: "DB2-database: Een proces wekelijks uitvoeren"
seo-title: "DB2 database: Running a process weekly"
description: Zie hoe u de prestaties van de database van de AEM formulieren DB2 kunt verbeteren.
seo-description: See how you can improve the performance of your AEM forms DB2 database.
uuid: 36070087-c250-41df-a841-aa922e777697
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/maintaining_the_aem_forms_database
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: fc0e8183-5d50-4fc0-997a-5f3168ba0d70
exl-id: f40fcfab-63e0-4e43-aac5-95426e3dd1fb
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 0%

---

# DB2-database: Een proces wekelijks uitvoeren{#db-database-running-a-process-weekly}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Als de database met AEM formulieren DB2 langzaam begint te lopen, kunt u de prestaties verbeteren door het volgende proces wekelijks uit te voeren:

1. Start DB2 Control Center:

   (Windows) Selecteer Start > Programma&#39;s > IBM DB2 > Algemene beheergereedschappen > Control Center.

   (Linux en UNIX) Typ de opdracht `db2jcc` gebruiken.

1. Klik in de objectstructuur van het DB2 Control Center op Alle databases.
1. Klik op de database die u voor AEM formulieren hebt gemaakt en klik op de map Tables.
1. Selecteer alle gegevensbestandlijsten in de inhoudruit, klik hen met de rechtermuisknop aan en selecteer de Statistieken van de Looppas.
1. Ga naar Statistieken > Indexstatistieken.
1. Selecteer Statistieken verzamelen voor alle indexen, selecteer Statistieken verzamelen voor indexen met Uitgebreide Gedetailleerde Statistieken, en klik dan O.K.

Er verschijnt een bericht wanneer het proces is voltooid. Sluit het bericht.
