---
title: Certificaatintrekkingslijsten beheren
seo-title: Managing certificate revocationlists
description: Leer hoe u lijsten voor certificaatintrekking beheert.
seo-description: Learn how to manage certificate revocation lists.
uuid: d8c4b64c-a273-4f5d-8b71-f6ea455c0f0a
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/managing_certificates_and_credentials
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 9744cc2d-5e6b-4341-9270-43d479bdca04
exl-id: 45741270-2d57-4d6d-92ef-65b6c1deb448
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 0%

---

# Certificaatintrekkingslijsten beheren{#managing-certificate-revocationlists}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Met Betrouwbaarheidswinkelbeheer kunt u lijsten voor certificaatintrekking importeren, bewerken en verwijderen. Base64- en DER-gecodeerde certificaatintrekkingslijsten worden ondersteund.

## Een CRL importeren {#import-a-crl}

1. Klik in de beheerconsole op Instellingen > Betrouwbaarheidsopslagbeheer > Certificaatintrekkingslijsten en klik vervolgens op Importeren.
1. Typ in het vak Alias een id voor het CRL.
1. Klik doorbladeren om van CRL de plaats te bepalen en dan O.K. te klikken.

## Een CRL exporteren {#export-a-crl}

1. Klik in de beheerconsole op Instellingen > Betrouwbaarheidsopslagbeheer > Certificaatintrekkingslijsten.
1. Klik op de naam van de alias van de CRL die u wilt exporteren en klik vervolgens op Exporteren.
1. Volg de aanwijzingen om de CRL te exporteren. CRLs wordt uitgevoerd in het coderen Base64.
1. Klik op OK.

## CRL verwijderen {#delete-a-crl}

1. Klik in de beheerconsole op Instellingen > Betrouwbaarheidsopslagbeheer > Certificaatintrekkingslijsten.
1. Selecteer de selectievakjes voor de CRL&#39;s die u wilt verwijderen, klik op Verwijderen en klik vervolgens op OK.
