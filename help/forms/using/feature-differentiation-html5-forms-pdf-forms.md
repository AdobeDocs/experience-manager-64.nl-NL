---
title: 'Verschil tussen functies in HTML5-formulieren en PDF forms '
seo-title: 'Verschil tussen functies in HTML5-formulieren en PDF forms '
description: Functie wordt ondersteund in HTML5-formulieren en -PDF forms
seo-description: Functie wordt ondersteund in HTML5-formulieren en -PDF forms
uuid: b0a96da5-31d3-4f99-b100-91ad51736ffb
contentOwner: robhagat
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: hTML5_forms
discoiquuid: 273096d0-b0e1-4519-8af6-11b3414cc172
feature: Mobile Forms
translation-type: tm+mt
source-git-commit: 75312539136bb53cf1db1de03fc0f9a1dca49791
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 2%

---


# Verschil tussen functies tussen HTML5-formulieren en PDF forms {#feature-differentiation-between-html-forms-and-pdf-forms}

In de volgende tabel vindt u ondersteuning van de functies die worden geboden voor HTML5-formulieren en -PDF forms:

<table> 
 <tbody>
  <tr>
   <th>Functie</th> 
   <th>HTML5 Forms</th> 
   <th>PDF</th> 
  </tr>
  <tr>
   <td>Streepjescodes<br /> </td> 
   <td>Niet beschikbaar op gebruikersinterfaceniveau. </td> 
   <td>Ondersteund</td> 
  </tr>
  <tr>
   <td>Handtekeningveld<br /> </td> 
   <td><strong>Digitale </strong> handtekeningen worden niet ondersteund, maar er wordt een nieuw veld voor  <strong>scriptbare </strong> handtekeningen toegevoegd. U kunt de handtekening van de handtekening op het formulier krabbelen met het veld <strong>Krabbelhandtekening</strong>. De handtekening wordt als een afbeelding op het formulier opgeslagen. U kunt gegevens over de geolocatie opslaan in het veld <strong>Krabbelen handtekening</strong>.</td> 
   <td>Handtekeningveld beschikbaar voor <strong>Digitale handtekeningen</strong>.</td> 
  </tr>
  <tr>
   <td>Gegevenssamenvoeging</td> 
   <td>Ondersteund</td> 
   <td>Ondersteund</td> 
  </tr>
  <tr>
   <td>Afbeeldingen</td> 
   <td>Het schema Data URI wordt gebruikt om afbeeldingen weer te geven. Alle moderne versies van browsers ondersteunen dit schema, maar er zijn verschillen in het bereik van afbeeldingsindelingen dat door elke browser wordt ondersteund.<br /> </td> 
   <td>De indelingen .gif, .png, .jpeg, .bmp en .tiff worden ondersteund.</td> 
  </tr>
  <tr>
   <td>Paginering<br /> </td> 
   <td><p>Een HTML5-formulier is onderverdeeld in deelvensters en vakken, zodat het er net zo uitziet als PDF forms. De grootte van de pagina wordt dynamisch berekend. Als alle inhoud van een pagina in een HTML5-formulier is verwijderd of gemarkeerd als verborgen, wordt de lege pagina verborgen en wordt er geen lege ruimte (spatie) weergegeven tussen pagina's boven en onder de lege pagina.</p> <p>Als gegevens worden samengevoegd of scripts inhoud aan een pagina toevoegen, wordt de lengte van de pagina aangepast aan de nieuwe inhoud. Er worden geen nieuwe pagina's aan het formulier toegevoegd voor de nieuwe inhoud. </p> <p><strong>Opmerking:</strong> Wanneer alle inhoud van een pagina in een HTML5-formulier wordt verwijderd of gemarkeerd als verborgen, blijft de lege pagina (lege ruimte) zichtbaar tussen de eerste en de tweede pagina, maar niet tussen andere pagina's.</p> </td> 
   <td>Paginering in PDF is afhankelijk van samengevoegde gegevensinhoud of van gebruikersinhoud en het aantal pagina's wordt op basis daarvan verhoogd/verlaagd.</td> 
  </tr>
  <tr>
   <td>Kopteksten/voetteksten </td> 
   <td>Ondersteund. <br /> <br /> Omdat mobiele HTML5-formulieren geen ondersteuning bieden voor pagina-einden, worden kop- en voetteksten slechts eenmaal weergegeven. U kunt ze echter instellen in de indeling, zodat ze op meerdere plaatsen in de voorvertoning van mobiele formulieren worden weergegeven.<br /> </td> 
   <td>Ondersteund.</td> 
  </tr>
  <tr>
   <td>Aangepaste widgets</td> 
   <td>U kunt widgets aanpassen om de gebruikerservaring op mobiele apparaten te verbeteren.<br /> </td> 
   <td>Alle widgets zijn vergrendeld en er kan geen aangepaste widget worden aangesloten.<br /> </td> 
  </tr>
  <tr>
   <td>XFA Script API</td> 
   <td>Ondersteunt de meestgebruikte XFA-scriptconstructies. Zie <a href="/help/forms/using/scripting-support.md">Scriptondersteuning</a> voor een gedetailleerde lijst met ondersteunde constructies.</td> 
   <td>Ondersteunt alle XFA-scriptconstructies.</td> 
  </tr>
  <tr>
   <td>Acrobat Script API's </td> 
   <td>HTML5-formulieren ondersteunen veelgebruikte API's. Zie <a href="/help/forms/using/scripting-support.md">Ondersteuning van scripts</a> voor meer informatie.</td> 
   <td>Als het PDF-bestand wordt geopend in Acrobat of Reader, worden ook alle script-API's van Acrobat ondersteund.</td> 
  </tr>
  <tr>
   <td>Ondersteuning voor talen die van rechts naar links worden geschreven </td> 
   <td>Ondersteund</td> 
   <td>Ondersteund</td> 
  </tr>
 </tbody>
</table>

Volg de aanbevolen procedures om een formuliersjabloon in te schakelen voor HTML5-uitvoeringen en zorg ervoor dat het gedrag en de weergave van HTML5-formulieren en op XFA gebaseerde PDF consistent zijn. Zie [Aanbevolen werkwijzen om een HTML5-formulier te ontwerpen voor een gedetailleerde lijst met aanbevolen werkwijzen.](/help/forms/using/best-practices-for-html5-forms.md)

