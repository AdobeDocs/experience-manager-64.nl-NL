---
title: De interface Correspondentie maken integreren met uw aangepaste portal
seo-title: De interface Correspondentie maken integreren met uw aangepaste portal
description: Leer hoe u het maken van correspondentie-UI kunt integreren met uw aangepaste portal
seo-description: Leer hoe u het maken van correspondentie-UI kunt integreren met uw aangepaste portal
uuid: 4ae9c5fb-bb9d-46d8-be84-455f386ab443
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: correspondence-management
discoiquuid: cb232931-60b7-4956-bc77-10636c19325e
feature: Correspondentenbeheer
translation-type: tm+mt
source-git-commit: 75312539136bb53cf1db1de03fc0f9a1dca49791
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 3%

---


# De interface Correspondentie maken integreren met uw aangepaste portal {#integrating-create-correspondence-ui-with-your-custom-portal}

## Overzicht {#overview}

In dit artikel wordt beschreven hoe u de Correspondentieoplossing maken kunt integreren met uw omgeving.

## Oproepen op basis van URL {#url-based-invocation}

U kunt de toepassing Correspondentie maken aanroepen vanuit een aangepast portaal door de URL voor te bereiden met de volgende aanvraagparameters:

* de id voor de lettertypesjabloon (met de parameter cmLetterId) of de naam van de lettertypesjabloon (met de parameter cmLetterName)

* de URL naar de XML-gegevens die van de gewenste gegevensbron worden opgehaald (met de parameter cmDataUrl).

Het aangepaste portaal bereidt bijvoorbeeld de URL voor als\
`https://[server]:[port]/[contextPath]/aem/forms/createcorrespondence.html?random=[timestamp]&cmLetterId=[letter identifier]&cmDataUrl=[data URL]`, wat de href zou kunnen zijn van een link op het portaal.\
Als het portaal de sjabloonnaam Letter heeft, kan de URL\
`https://[server]:[port]/content/cm/createcorrespondence.html?cmLetterName=[letter name]&cmDataUrl=[data URL]`.

>[!NOTE]
>
>Op deze manier aanroepen is niet veilig omdat de noodzakelijke parameters als een verzoek van de GET worden doorgegeven, door het zelfde (duidelijk zichtbare) in URL toegankelijk te maken.

>[!NOTE]
>
>Voordat u de toepassing Correspondentie maken aanroept, slaat u de gegevens op en uploadt u deze om de interface Correspondentie maken op de opgegeven dataURL aan te roepen. Dit zou of van het douaneportaal zelf of door een ander achtereindeproces kunnen worden gedaan.

## Inline op gegevens gebaseerde aanroep {#inline-data-based-invocation}

Een andere (en veiligere) manier om de Create toepassing van de Correspondentie te roepen zou kunnen zijn eenvoudig URL bij `https://[server]:[port]/[contextPath]/aem/forms/createcorrespondence.html` te raken, terwijl het verzenden van de parameters en de gegevens om de Create toepassing van de Correspondentie als POST te roepen verzoek (die hen voor de eindgebruiker verbergen). Dit betekent ook dat u nu de XML-gegevens voor de toepassing Correspondentie maken inline kunt doorgeven (als onderdeel van hetzelfde verzoek, met de parameter cmData), wat niet mogelijk/ideaal was in de vorige aanpak.

### Parameters voor het opgeven van de letter {#parameters-for-specifying-letter}

<table> 
 <tbody>
  <tr>
   <td><strong>Naam</strong></td> 
   <td><strong>Type</strong></td> 
   <td><strong>Beschrijving</strong></td> 
  </tr>
  <tr>
   <td>cmLetterInstanceId</td> 
   <td>Tekenreeks</td> 
   <td>De id voor de letter-instantie.</td> 
  </tr>
  <tr>
   <td>cmLetterName</td> 
   <td>Tekenreeks</td> 
   <td><p>De id voor de lettertypesjabloon. </p> <p>Als er meerdere CM-letters met dezelfde naam op een server staan, genereert het gebruik van de parameter cmLetterName in de URL een fout "Er bestaan meerdere letters met naam". Gebruik in dat geval de parameter cmLetterId in de URL in plaats van cmLetterName.</p> </td> 
  </tr>
  <tr>
   <td>cmLetterId</td> 
   <td>Tekenreeks</td> 
   <td>De naam van de Letter-sjabloon.</td> 
  </tr>
 </tbody>
</table>

De volgorde van parameters in de tabel geeft de voorkeur aan parameters die worden gebruikt voor het laden van de letter.

### Parameters om de XML-gegevensbron {#parameters-for-specifying-the-xml-data-source} op te geven

<table> 
 <tbody>
  <tr>
   <td><strong>Naam</strong></td> 
   <td><strong>Type</strong></td> 
   <td><strong>Beschrijving</strong></td> 
  </tr>
  <tr>
   <td>cmDataUrl<br /> </td> 
   <td>URL</td> 
   <td>XML-gegevens uit een bronbestand met basisprotocollen zoals cq, ftp, http of file.<br /> </td> 
  </tr>
  <tr>
   <td>cmLetterInstanceId</td> 
   <td>Tekenreeks</td> 
   <td>XML-gegevens gebruiken die beschikbaar zijn in Letter Instance.</td> 
  </tr>
  <tr>
   <td>cmUseTestData</td> 
   <td>Boolean</td> 
   <td>De testgegevens in het gegevenswoordenboek opnieuw gebruiken.</td> 
  </tr>
 </tbody>
</table>

De volgorde van parameters in de tabel geeft de voorkeur aan parameters die worden gebruikt voor het laden van de XML-gegevens.

### Andere parameters {#other-parameters}

<table> 
 <tbody>
  <tr>
   <td><strong>Naam</strong></td> 
   <td><strong>Type</strong></td> 
   <td><strong>Beschrijving</strong></td> 
  </tr>
  <tr>
   <td>cmPreview<br /> </td> 
   <td>Boolean</td> 
   <td>True to open the letter in preview mode<br /> </td> 
  </tr>
  <tr>
   <td>Willekeurig</td> 
   <td>Tijdstempel</td> 
   <td>Oplossen van cacheproblemen met de browser.</td> 
  </tr>
 </tbody>
</table>

Als u het http- of cq-protocol voor cmDataURL gebruikt, moet de URL van http/cq anoniem toegankelijk zijn.
