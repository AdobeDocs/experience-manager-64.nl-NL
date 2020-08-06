---
title: Aangepaste speciale tekens in Correspondentenbeheer
seo-title: Aangepaste speciale tekens in Correspondentenbeheer
description: Leer hoe u aangepaste speciale tekens toevoegt in Correspondentiebeheer.
seo-description: Leer hoe u aangepaste speciale tekens toevoegt in Correspondentiebeheer.
uuid: ac4f1353-f1ef-43b7-8e80-aba56a155e3f
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: correspondence-management
discoiquuid: 1b5e6746-3618-46fe-ba2d-ec76bb79de1d
translation-type: tm+mt
source-git-commit: 36baba4ee20dd3d7d23bc50bfa91129588f55d32
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 1%

---


# Aangepaste speciale tekens in Correspondentenbeheer {#custom-special-characters-in-correspondence-management}

## Overzicht {#overview}

Correspondence Management biedt ingebouwde standaardondersteuning voor 210 speciale tekens die u eenvoudig in letters kunt invoegen.

U kunt bijvoorbeeld de volgende speciale tekens invoegen:

* Valutasymbolen zoals €, ¥ en £
* Wiskundige symbolen zoals A, Ö, ∂ en ^
* Interpunctiesymbolen als ‟ en&quot;

U kunt speciale tekens in letters invoegen:

* In de [teksteditor](/help/forms/using/document-fragments.md#createtext)
* In een [bewerkbare, inline module in een correspondentie](/help/forms/using/create-correspondence.md#managecontent)

![specialkarakteristiek linemodule](assets/specialcharactersinlinemodule.png)

De beheerder kan ondersteuning voor meer/aangepaste speciale tekens toevoegen door deze aan te passen. In dit artikel vindt u instructies voor het toevoegen van ondersteuning voor extra, aangepaste speciale tekens.

## Ondersteuning toevoegen of wijzigen voor aangepaste speciale tekens in Correspondentenbeheer {#creatingfolderstructure}

Gebruik de volgende stappen om ondersteuning voor aangepaste speciale tekens toe te voegen:

1. Ga naar Beheerder `https://[server]:[port]/[ContextPath]/crx/de` en meld u aan.
1. Maak in de map apps een map met de naam path/structure, vergelijkbaar met de map specialcharacters (in de map textEditorConfig onder libs): **[!UICONTROL specialcharacters]**

   1. Klik met de rechtermuisknop op de map met **speciale tekens** in het volgende pad en selecteer **Overlayknooppunt**:

      `/libs/fd/cm/ma/gui/configuration/textEditorConfig/specialcharacters`

   1. Zorg ervoor dat het dialoogvenster Overlay-knooppunt de volgende waarden heeft:

      **Pad:** /libs/fd/cm/ma/gui/configuration/textEditorConfig/specialcharacters

      **Locatie bedekking:** /apps/

      **Identieke knooppunttypen:** Ingeschakeld

      >[!NOTE]
      >
      >Breng geen veranderingen in de /libs tak aan. Alle wijzigingen die u aanbrengt, kunnen verloren gaan, omdat deze vertakking mogelijk wordt gewijzigd wanneer u:
      >
      >* Upgrade op uw exemplaar
      >* Een hotfix toepassen
      >* Een functiepakket installeren


   1. Klik op **OK** en vervolgens op Alles **** opslaan. De map met speciale tekens wordt gemaakt in het opgegeven pad.

      Controleer na het maken van de overlay de structuurcodes van de knooppunten. Elk knooppunt dat wordt gemaakt in /apps met behulp van de overlay, moet dezelfde klasse en eigenschappen hebben als gedefinieerd in /libs voor dat knooppunt. Als een eigenschap of tag ontbreekt in de nodestructuur onder de locatie /apps, synchroniseert u de tags met het corresponderende knooppunt in /libs.

1. Zorg ervoor dat het **[!UICONTROL textEditorConfig]** knooppunt de volgende eigenschappen en waarden heeft:

   | Naam | Type | Waarde |
   |---|---|---|
   | cmConfigurationType | Tekenreeks | cmTextEditorConfiguration |
   | cssPath | Tekenreeks | /libs/fd/cm/ma/gui/components/admin/createasset/textcontrol/clientlibs/textcontrol |

1. Klik met de rechtermuisknop op de **[!UICONTROL specialcharacters]** map op het volgende pad en selecteer **Maken > Onderliggend knooppunt** en klik vervolgens op Alles **** opslaan:

   /apps/fd/cm/ma/gui/configuration/textEditorConfig/specialcharacters/&lt;YourChildNode>

1. Vernieuw de Teksteditor\Create Correspondence UI page. Het knooppunt dat u hebt toegevoegd, is het laatste in de lijst met speciale tekens in de gebruikersinterface.
1. Klik op Alles **opslaan**.
1. Breng de gewenste wijzigingen aan in de speciale tekens:

<table> 
 <tbody> 
  <tr> 
   <td><strong>Naar...</strong></td> 
   <td><strong>Voer de volgende stappen uit</strong></td> 
  </tr> 
  <tr> 
   <td>Een aangepast speciaal teken toevoegen</td> 
   <td> 
    <ol> 
     <li>Voeg een onderliggende node toe onder "/apps/fd/cm/ma/gui/configuration/textEditorConfig/specialcharacters" met verplichte eigenschappen.</li> 
     <li>Klik op Alles opslaan</li> 
     <li>Vernieuw de Redacteur van de Tekst \ creeer Correspondentie UI om de veranderingen te zien.</li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td>De eigenschappen van een bestaand speciaal teken bijwerken</td> 
   <td> 
    <ol> 
     <li>Bedek het knooppunt dat moet worden bijgewerkt zoals hierboven beschreven en controleer de tags en klassen.</li> 
     <li>Wijzig alle waarden, zoals bijschrift, waarde, endValue en multipleCaption. </li> 
     <li>Klik op Alles opslaan. </li> 
     <li>Vernieuw de Redacteur van de Tekst \ creeer Correspondentie UI om de veranderingen te zien.</li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td>Een speciaal teken verbergen</td> 
   <td> 
    <ol> 
     <li>Plaats het knooppunt dat u wilt verbergen onder "/apps/fd/cm/ma/gui/configuration/textEditorConfig/specialcharacters"</li> 
     <li>Voeg de eigenschap sling:hideResource (Boolean) toe aan het knooppunt (onder apps) dat moet worden verborgen. </li> 
     <li>Klik op Alles opslaan. </li> 
     <li>Vernieuw de Redacteur van de Tekst \ creeer Correspondentie UI om de veranderingen te zien.<br /> </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td>Meerdere speciale tekens verbergen</td> 
   <td> 
    <ol> 
     <li>Voeg de eigenschap "sling:hideChildren (String of String[])" toe aan "/apps/fd/cm/ma/gui/configuration/textEditorConfig/specialcharacters". </li> 
     <li>Voeg knooppuntnamen (speciale tekens die moeten worden verborgen) toe als waarden voor de eigenschap "sling:hideChildren". </li> 
     <li>Klik op Alles opslaan. </li> 
     <li>Vernieuw de Redacteur van de Tekst \ creeer Correspondentie UI om de veranderingen te zien.<br /> </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td>Speciale tekens ordenen</td> 
   <td> 
    <ol> 
     <li>Voeg een onderliggende node toe onder "/apps/fd/cm/ma/gui/configuration/textEditorConfig/specialcharacters" met verplichte eigenschappen. </li> 
     <li>Voeg "sling:orderBefore (Koord)"bezit aan de onlangs-gecreeerde kindknoop toe. </li> 
     <li>Voeg knooppuntnaam als waarde toe voordat het toegevoegde speciale teken moet worden weergegeven. </li> 
     <li>Klik op Alles opslaan. </li> 
     <li>Vernieuw de Redacteur van de Tekst \ creeer Correspondentie UI om de veranderingen te zien.<br /> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

