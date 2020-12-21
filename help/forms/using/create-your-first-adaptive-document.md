---
title: PUBLICEREN Uw eerste adaptieve document niet maken
seo-title: PUBLICEREN Uw eerste adaptieve document niet maken
description: 'null'
seo-description: 'null'
page-status-flag: de-activated
uuid: 2cb2bf82-130f-4d6b-a711-df0b97cb0504
discoiquuid: f3ca177f-7c0d-4b8b-ab4b-bf04668d634c
translation-type: tm+mt
source-git-commit: cdec5b3c57ce1c80c0ed6b5cb7650b52cf9bc340
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 0%

---


# NIET PUBLICEREN Uw eerste adaptieve document maken {#do-not-publish-create-your-first-adaptive-document}

## Hoofdlettergebruik {#use-case}

Wij Financiën is een toonaangevende organisatie op het gebied van de Financiële Diensten die uitvoerige en gepersonaliseerde financiële oplossingen aanbiedt om aan de vereisten van diverse klantenprofielen te voldoen.

Een van de automatische verzekeringscontracten van hun klanten verloopt en ze sturen haar een herinnering, die interactief is en een PDF bevat, met de vermelding voor verlenging. De mededeling bevat ook andere informatie, zoals loyaliteitsbeloningen en aanbiedingen van kortingen.

Het portaal loopt op Adobe AEM. Het welkomstkanaal voor het web en de afdruk wordt gemaakt met behulp van de kanaalmogelijkheden van Adaptief document.

Aan het einde van de zelfstudie hebt u een adaptief document dat lijkt op het volgende:
[ ![ad-1](assets/ad-1.png)](https://blogs.adobe.com/contentcorner/files/2017/07/PAF_Mobile.pdf)    [ ![ad-2](assets/ad-2.png)](https://blogs.adobe.com/contentcorner/files/2017/07/PAF_Desktop.pdf)Het maken van uw eerste adaptieve documentzelfstudie wordt in stappen gecategoriseerd. Elke stap is een volledig artikel op zich.

<table> 
 <tbody>
  <tr>
   <th>U leert</th> 
   <th>
    <ul> 
     <li>Een adaptief document- en formuliergegevensmodel maken.</li> 
     <li>Sjablonen en thema's maken voor aangepaste documenten.</li> 
     <li>Gebruikend regelredacteur om bedrijfsregels te bouwen.<br /> </li> 
     <li>Een adaptief document publiceren. <br /> </li> 
    </ul> </th> 
  </tr>
  <tr>
   <td>Vereiste</td> 
   <td>
    <ul> 
     <li>Instellen AEM instantie van auteur. </li> 
     <li>AEM Forms-invoegtoepassing installeren. Zie <a href="/help/forms/using/installing-configuring-aem-forms-osgi.md" target="_blank">AEM Forms</a> installeren en configureren voor meer informatie.</li> 
     <li>Vraag het JAR-bestand (JDBC-databasestuurprogramma) aan bij de databaseprovider. De voorbeelden in de zelfstudie zijn gebaseerd op MySQL-database en gebruiken het databasestuurprogramma Oracle MySQL JDBC. </li> 
     <li>Stel een database in die klantgegevens bevat. Een databank is van essentieel belang om een adaptief document te maken. Deze zelfstudie gebruikt een database voor het weergeven van het formuliergegevensmodel en de persistentiemogelijkheden van AEM Forms. </li> 
     <li><a href="/help/forms/using/web-channel-print-channel.md">Sjablonen maken/importeren en inschakelen voor afdrukken en webkanaal</a>.</li> 
     <li>Zorg ervoor dat de <a href="/help/forms/using/document-fragments.md">Documentfragmenten op de FDM</a> zijn gebaseerd.</li> 
    </ul> </td> 
  </tr>
 </tbody>
</table>

## Stap 1: Formuliergegevensmodel {#step-create-form-data-model} maken

Met een formuliergegevensmodel kunt u een adaptief document aansluiten op verschillende gegevensbronnen. Bijvoorbeeld AEM gebruikersprofiel, RESTful Webdiensten, op SOAP-Gebaseerde Webdiensten, OData diensten, en relationele gegevensbestanden. Een gegevensmodel van de Vorm is een verenigd schema van de gegevensvertegenwoordiging van bedrijfsentiteiten en de diensten beschikbaar in verbonden gegevensbronnen. U kunt het formuliergegevensmodel met een adaptief document gebruiken om gegevens op te halen uit verbonden gegevensbronnen. Zie [AEM Forms Data Integration](/help/forms/using/data-integration.md) voor meer informatie over het formuliergegevensmodel.

Doelstellingen:

* Database-instantie (Microsoft Dynamics) configureren als gegevensbron
* Maak het formuliergegevensmodel met Microsoft Dynamics als gegevensbron
* Gegevensmodelobjecten toevoegen aan formuliergegevensmodel
* Lezen- en schrijfservices configureren voor het gegevensmodel van het formulier
* Formuliergegevensmodel testen en geconfigureerde services met testgegevens

## Stap 2: Een adaptief document {#step-create-an-adaptive-document} maken

De Mededelingen van de klant centraliseert en beheert de verwezenlijking, de assemblage, en de levering van veilige, gepersonaliseerde, en interactieve correspondentie zoals bedrijfscorrespondentie, brieven, documenten, verklaringen, voordeelberichten, het prospectus van het vermogensbeheer, marketing brievenpost, rekeningen, en welkomstkits.

Met behulp van adaptieve documenten kunt u klantcommunicatie maken die boeiend, responsief, dynamisch en adaptief van aard is. AEM Forms beschikt over een WYSIWYG-editor voor slepen en neerzetten waarmee u adaptieve documenten kunt maken.

<!--`For more information about adaptive documents, see [Introduction to authoring adaptive documents](/forms/using/introduction-ad-authoring.md).`-->

Doelstellingen:

* Maak afdrukken en webinvoer van een adaptief document op basis van het formuliergegevensmodel.
* Indelingsvelden van een adaptief formulier om informatie aan de klant weer te geven
* Maak regels voor het ophalen en weergeven van informatie van het formuliergegevensmodel naar het aangepaste document.

<!--![see-the-guide-sm](assets/see-the-guide-sm.png)-->

## Stap 3: Regels toepassen op aangepaste documentvelden (alleen webkanaal) {#step-apply-rules-to-adaptive-document-fields-web-channel-only}

Het adaptieve document biedt een editor voor het schrijven van regels voor adaptieve documentobjecten. Met deze regels worden handelingen gedefinieerd die op documentobjecten moeten worden geactiveerd op basis van vooraf ingestelde voorwaarden en gebruikersacties voor het document. Hierdoor wordt de nauwkeurigheid en snelheid van de gebruikerservaring in de webversie van het adaptieve document gegarandeerd. Zie [regeleditor](/help/forms/using/rule-editor.md) voor meer informatie over de adaptieve documentregels en regeleditor.

Doelstellingen:

* Regels maken en toepassen op de webkanaalvelden van het aangepaste document
* De regels van het gebruik om de modeldiensten van documentgegevens in Webkanaal teweeg te brengen

## Stap 4: Het aangepaste document opmaken (alleen webkanaal) {#step-style-the-adaptive-document-web-channel-only}

Aangepaste documenten bieden een editor voor het maken van thema&#39;s voor de aangepaste documenten en inline opmaak. Een thema bevat opmaakgegevens voor componenten en deelvensters en u kunt een thema opnieuw gebruiken op webkanalen van verschillende documenten. Stijlen omvatten eigenschappen zoals achtergrondkleuren, statuskleuren, transparantie, uitlijning en grootte. Wanneer u het thema toepast op uw document, weerspiegelt de opgegeven stijl de corresponderende componenten van het document. Zie [Thema&#39;s](/help/forms/using/themes.md) voor meer informatie.

Doelstellingen:

* Thema maken voor het webkanaal van het adaptieve document
* Thema toepassen op het webkanaal van het adaptieve document
* Weergave van het adaptieve documentwebkanaal valideren op mobiele apparaten en bureaublad

## Stap 5: Het aangepaste document {#step-publish-the-adaptive-document} publiceren

Wanneer u klaar bent met het maken van uw adaptieve document, moet u het publiceren zodat het beschikbaar is op uw publicatieexemplaar waar de agenten het adaptieve document kunnen gebruiken om de communicatie instanties tot stand te brengen die op het worden gebaseerd.

Om het adaptieve document te publiceren, moeten de auteurs van het document de vereiste toestemmingen hebben.
