---
title: Uitvoerservice
seo-title: Output Service
description: Beschrijft de Dienst van de Output, die deel van AEM Diensten van het Document uitmaakt
seo-description: Describes Output Service, which is part of AEM Document Services
uuid: acd64bbb-91df-49bc-9216-2e860812bbe9
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: document_services
discoiquuid: 8b96ba2d-007e-472a-875f-2caedd35ecf4
exl-id: ccc291fc-f4c5-4d14-816a-c57f56a95663
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '548'
ht-degree: 0%

---

# Uitvoerservice {#output-service}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Overzicht {#overview}

De dienst van de output is de dienst OSGi die deel van AEM Diensten van het Document uitmaakt. De uitvoerservice ondersteunt verschillende uitvoerindelingen en functies voor het ontwerpen van uitvoer van AEM Forms Designer. De uitvoerservice kan XFA-sjablonen en XML-gegevens converteren om afdrukdocumenten in verschillende indelingen te genereren.

Met uitvoerservice kunt u toepassingen maken waarmee u:

* Definitieve formulierdocumenten genereren door sjabloonbestanden te vullen met XML-gegevens.
* Uitvoerformulieren genereren in verschillende indelingen, waaronder niet-interactieve PDF-, PostScript-, PCL- en ZPL-afdrukstromen.
* Afdruk-PDF genereren op basis van XFA-formulier-PDF.
* Genereer bulksgewijs PDF-, PostScript-, PCL- en ZPL-documenten door meerdere gegevenssets samen te voegen met de meegeleverde sjablonen.

>[!NOTE]
>
>De uitvoerservice is een 32-bits toepassing. In Microsoft Windows mag een 32-bits toepassing maximaal 2 GB geheugen gebruiken. De limiet geldt ook voor de uitvoerservice.

## Niet-interactieve formulierdocumenten maken {#creating-non-interactive-form-documents}

![usingoutput_modified](assets/usingoutput_modified.png)

Gewoonlijk maakt u sjablonen met AEM Forms Designer. De `generatePDFOutput` en `generatePrintedOutput` Met API&#39;s van de Output-service kunt u deze sjablonen rechtstreeks converteren naar verschillende indelingen, zoals PDF, PostScript, ZPL en PCL.

De `generatePDFOutput` bewerking genereert PDF terwijl de `generatePrintedOutput` Deze bewerking genereert PostScript-, ZPL- en PCL-indelingen. De eerste parameter van beide bewerkingen accepteert de naam van het sjabloonbestand (bijvoorbeeld `ExpenseClaim.xdp`) of een object Document dat de sjabloon bevat. Wanneer u de naam van het sjabloonbestand opgeeft, geeft u ook de hoofdmap van de inhoud op als het pad naar de map die de sjabloon bevat. U kunt de hoofdmap van de inhoud opgeven met de `PDFOutputOptions` of de `PrintedOutputOptions` parameter. Zie Javadoc voor meer informatie over andere opties die u met deze parameters kunt opgeven.

De tweede parameter accepteert een XML-document dat met de sjabloon wordt samengevoegd tijdens het genereren van het uitvoerdocument.

De `generatePDFOutput` Deze bewerking kan ook een op XFA gebaseerd PDF-formulier accepteren als invoer en een niet-interactieve versie van het PDF-formulier retourneren als uitvoer.

## Niet-interactieve formulierdocumenten genereren {#generating-non-interactive-form-documents}

Overweeg een scenario waar u één of meerdere malplaatjes en veelvoudige verslagen van de gegevens van XML voor elke malplaatje hebt.

Gebruik de `generatePDFOutputBatch` en `generatePrintedOutputBatch` bewerkingen van de uitvoerservice om een afdrukdocument voor elke record te genereren.

U kunt de records ook in één document combineren. Beide bewerkingen hebben vier parameters.

De eerste parameter is een Kaart die een willekeurige tekenreeks als sleutel en de naam van het sjabloonbestand als waarde bevat.

De tweede parameter is een andere map waarvan de waarde een object Document is dat XML-gegevens bevat. De sleutel is het zelfde als dat u voor de eerste parameter specificeert.

De derde parameter voor `generatePDFOutputBatch` of `generatePrintedOutputBatch` is van type `PDFOutputOptions` of `PrintedOutputOptions` respectievelijk.

De parametertypen zijn hetzelfde als de typen parameters voor de parameter `generatePDFOutput` en `generatePrintedOutput` en hebben hetzelfde effect.

De vierde parameter is van het type `BatchOptions`, die u gebruikt om op te geven of voor elke record een afzonderlijk bestand kan worden gegenereerd. De standaardwaarde van deze parameter is false.

Beide `generatePrintedOutputBatch` en `generatePDFOutputBatch` Hiermee wordt een waarde van het type geretourneerd `BatchResult`. De waarde bevat een lijst met gegenereerde documenten. Het bevat ook een metagegevensdocument in XML-indeling dat informatie bevat die betrekking heeft op elk document dat wordt gegenereerd.
