---
title: Werken met AEM 3D-elementen
description: Leer hoe u met 3D-middelen werkt in AEM 3D
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: introduction
content-type: reference
exl-id: 3cee9b4f-c4be-4ffc-970c-5680c8ebba47
feature: 3D-middelen
role: Administrator,Business Practitioner
translation-type: tm+mt
source-git-commit: 13eb1d64677f6940332a2eeb4d3aba2915ac7bba
workflow-type: tm+mt
source-wordcount: '1167'
ht-degree: 0%

---

# Werken met AEM 3D-elementen {#working-with-d-assets}

>[!IMPORTANT]
>
>AEM 3D in AEM 6.4 wordt niet meer ondersteund. Adobe raadt u aan de functie 3D-elementen in [AEM te gebruiken als een Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/assets-3d.html) of [AEM 6.5.3 of hoger.](https://experienceleague.adobe.com/docs/experience-manager-65/assets/dynamic/assets-3d.html#dynamic)

Met AEM 3D (Adobe Experience Manager 3D) kunt u 3D-inhoud uploaden, beheren, weergeven en renderen. Ondersteuning voor weergave en rendering is geoptimaliseerd voor afzonderlijke objecten.

Zie ook [AEM Opmerkingen bij de 3D-release](/help/release-notes/aem3d-release-notes.md).

Zie ook [AEM 3D](install-config-3d.md) installeren en configureren.

## Modellen en fasen in AEM 3D {#about-models-and-stages-in-aem-d}

Met AEM 3D kunt u statische, zelfstandige 3D-modellen van hoge kwaliteit weergeven en renderen in vooraf gedefinieerde omgevingen die Stages worden genoemd. In feite biedt een werkgebied &#39;belichting&#39; voor de 3D-scène en de instellingen voor rendering in een native toepassing zoals Autodesk® Maya® of Autodesk 3ds Max®. Bovendien kan het werkgebied eventueel vooraf gedefinieerde camera&#39;s, achtergronden en geometrie van het grondvlak bevatten.

Geüploade 3D-bestanden met lichten worden als een werkgebied beschouwd. U kunt dergelijke elementen herstellen tot eenvoudige 3D-objecten door het element te openen op de pagina met elementdetails. Tik op **[!UICONTROL View Properties]** en tik vervolgens op de tab **[!UICONTROL Basic]**. Selecteer **[!UICONTROL 3D object]** onder de kop Metagegevens in de vervolgkeuzelijst Asset Class.

Houd rekening met het volgende wanneer u 3D-modellen maakt voor gebruik in AEM 3D:

* De 3D-modelbestanden mogen slechts één object bevatten, zonder achtergronden, grondvlakken, scènebelichting of camera&#39;s.
* Plaats het model boven het grondvlak. Deze positionering is vooral belangrijk wanneer u fasen bekijkt of rendert die een grondvlak verschaffen. Er is een configuratie-instelling beschikbaar (en standaard ingeschakeld) die ervoor zorgt dat het object boven het grondvlak wordt geplaatst wanneer een voorvertoning wordt weergegeven of wanneer het object wordt gerenderd met Rapid Refine. Deze instelling heeft geen invloed op de rendering met renderers van derden (bijvoorbeeld via Maya), zodat objecten die zich niet boven het grondvlak bevinden gedeeltelijk verborgen kunnen zijn.
* Plaats het model zodanig dat het redelijk zijwaarts is gecentreerd rond de oorsprong van het coördinatensysteem (0,0,0). Dit zorgt voor een goede interactieve kijkervaring voor u.
* Andere dan structuurmappen, externe bestandsverwijzingen worden ondersteund. Daarom moet u inhoud waarnaar wordt verwezen, insluiten in het primaire modelbestand voordat u deze uploadt naar AEM.

   Zie [Informatie over het uploaden en verwerken van 3D-elementen in AEM](upload-processing-3d-assets.md).

* De algemene scènebelichting wordt verzorgd door het werkgebied. Als zodanig adviseert Adobe niet dat u lichten met 3D modeldossiers omvat. U kunt lichten in het model opnemen. Zij moeten echter uitsluitend voor het model gelden. Het kan bijvoorbeeld nodig zijn extra belichting op te nemen om een deel van het object lichter te maken dat door andere onderdelen wordt verborgen. Het zou dus niet voldoende zichtbaar zijn met alleen de schijnwerpers.

## Ondersteunde bestanden in AEM 3D {#supported-files-in-aem-d}

Een normaal 3D-element heeft een primair modelbestand en een of meer bestanden waarnaar wordt verwezen. Bestanden waarnaar wordt verwezen, zijn bijvoorbeeld structuurafbeeldingen of **IBL (op afbeelding gebaseerde belichting)** afbeeldingen.

### Informatie over het primaire 3D-modelbestand {#about-the-primary-d-model-file}

Het primaire 3D-modelbestand bevat de werkelijke geometrie van het 3D-model en definities voor de (standaard)materialen die op de oppervlakken van het model zijn toegepast. AEM 3D ondersteunt de volgende primaire bestandsindelingen voor 3D-modellen:

* Wavefront OBJ-bestandsindeling (`.obj`)

   De indeling OBJ vereist een of meer afzonderlijke, externe MTL-bestanden (Material Template Library) (`.mtl`).

* Bestandsindeling Autodesk FBX (Filmbox) (`.fbx`)

   De Autodesk 3D-indeling voor het uitwisselen van bestanden; zowel binaire als ASCII-indelingen.

   Wanneer u FBX-bestanden maakt in toepassingen van derden, raadt Adobe de volgende configuratie-instellingen aan (zie onderstaande tabel). Deze instellingen kunnen u helpen de beste resultaten te bereiken voor 3D-bestanden die u in AEM wilt gebruiken. De optienamen worden overgenomen uit het dialoogvenster **[!UICONTROL Autodesk Maya FBX Export Options]**.

<table> 
 <tbody> 
  <tr> 
   <td><strong>Optie in het dialoogvenster Exporteren van Autodesk Maya FBX</strong></td> 
   <td><strong>Beschrijving</strong></td> 
  </tr> 
  <tr> 
   <td>Referenties behouden<br /> </td> 
   <td><p>Hef de selectie op.</p> <p>AEM 3D ondersteunt momenteel geen externe referenties.</p> </td> 
  </tr> 
  <tr> 
   <td>Vloeiend net<br /> </td> 
   <td>Selecteer .</td> 
  </tr> 
  <tr> 
   <td>NURBS-oppervlakken converteren naar</td> 
   <td><strong>Software rendernet</strong></td> 
  </tr> 
  <tr> 
   <td>Animatie</td> 
   <td><p>Selecteren of deselecteren.</p> <p>Als u deze optie selecteert, negeert AEM 3D de animatiegegevens in het bestand.</p> </td> 
  </tr> 
  <tr> 
   <td>Cameras</td> 
   <td><p>Selecteer deze optie voor <strong>3D-fasen</strong>.</p> <p>Schakel deze optie uit voor 3D-modellen.</p> </td> 
  </tr> 
  <tr> 
   <td>Lichten</td> 
   <td><p>Selecteer deze optie voor <strong>3D-fasen</strong>.</p> <p>Schakel deze optie uit voor <strong>3D-modellen</strong>.</p> </td> 
  </tr> 
  <tr> 
   <td>Eenheden - Automatisch</td> 
   <td>Selecteer . AEM 3D wordt tijdens het importeren geconverteerd.</td> 
  </tr> 
  <tr> 
   <td>Axis-conversie - Omhoog as</td> 
   <td><p><strong>Y-up</strong></p> <p>Y-up levert consistente resultaten op wanneer u exporteert uit Maya en is het voorkeurscoördinatensysteem voor FBX-bestanden in deze AEM 3D-versie.</p> </td> 
  </tr> 
  <tr> 
   <td>Media insluiten</td> 
   <td>Beide opties worden ondersteund. Als ingesloten is geselecteerd, extraheert AEM 3D de ingesloten media naar een aangrenzende map met dezelfde naam als het modelbestand waaraan <code>.fbm</code> is toegevoegd.</td> 
  </tr> 
  <tr> 
   <td>FBX-bestandsindeling - Type</td> 
   <td>Zowel <strong>Binair </strong>als <strong>ASCII </strong>worden ondersteund.</td> 
  </tr> 
  <tr> 
   <td>FBX-bestandsindeling - Versie</td> 
   <td>FBX 2014/2015 wordt aanbevolen. Andere versies werken mogelijk ook prima.</td> 
  </tr> 
 </tbody> 
</table>

De volgende aanvullende bestandsindelingen worden ondersteund als Autodesk Maya is geïnstalleerd en geconfigureerd op AEM ontwerpservers:

* Autodesk Maya

   Zowel ASCII `.ma` als binaire `.mb` formaten.

* `Jupiter Tesselation (ISO 14306-1).jt`.

   Een industriestandaard CAD-indeling voor gegevensuitwisseling, samenwerking en productvisualisatie.

### Ondersteuning voor structuurmapbestanden {#support-for-texture-map-files}

Materiaaldefinities in 3D-modelbestanden kunnen verwijzingen bevatten naar externe afbeeldingsbestanden die structuurafbeeldingen bevatten. AEM 3D ondersteunt de volgende typen structuurmapbestanden:

* Onscherpe kleurstructuren
* Spiegelende kleurstructuren
* Omgevingskleurstructuren
* Verplaatsingstoestellen (ook wel reliëfstructuren genoemd)
* Normale kaarten
* Dekkingsstructuren
* Roughness maps (ook wel glanzend, reflectiviteit of Cosinus Power maps genoemd)

De materialen in het primaire 3D modeldossier kunnen andere types van kaarten van verwijzingen voorzien die door AEM 3D worden genegeerd.

### IBL-afbeeldingen (op afbeeldingen gebaseerde belichting) {#ibl-image-based-lighting-images}

Een 3D-modelbestand dat een werkgebied definieert, kan verwijzen naar één IBL-omgevingsafbeelding. AEM 3D ondersteunt momenteel alleen 32-bits TIFF-afbeeldingen in lengte- en breedtegraad voor diffuse IBL en voor reflecties. Voor de bolvormige scèneachtergrond worden 8-bits RGB-afbeeldingen ook ondersteund.

Zie [Werken met IBL-fasen](working-with-ibl-stages.md).

>[!NOTE]
>
>Andere bestandsverwijzingen dan de hierboven beschreven verwijzingen die aanwezig zijn in het primaire 3D-modelbestand, worden momenteel genegeerd. AEM 3D ondersteunt geen verwijzingen naar secundaire 3D-modelbestanden.
Y-up is het voorkeurscoördinatensysteem voor FBX-bestanden in deze release.

## Materiaalarcering in een primair 3D-modelbestand {#material-shading-in-a-primary-d-model-file}

Het oorspronkelijke native modelbestand kan materiaaldefinities bevatten die worden gebruikt met arceringen zoals Blinn, Lambert of met procedurele arceringen. Deze potentieel complexe materialen worden gesteund slechts wanneer u het teruggeven gebruikend de overeenkomstige inheemse toepassing (zoals Autodesk Maya).

Voor weergavedoeleinden of wanneer u rendert met de standaard Rapid Refine™-renderer, worden alle materialen vereenvoudigd, vervangen of beide, zodat ze kunnen worden gebruikt met een Phong-achtige arcering. Deze arcering ondersteunt een beperkte set kenmerken. Andere kenmerken in de materiaaldefinitie worden genegeerd.

Zie [3D-elementen weergeven](viewing-3d-assets.md).

Zie [3D-elementen renderen](rendering-3d-assets.md).

## Materialen benoemen in een primair 3D-modelbestand {#naming-materials-in-a-primary-d-model-file}

Een *oppervlak* wordt gedefinieerd als het oppervlak van een 3D-model dat door hetzelfde materiaal wordt bedekt. Dit materiaal geeft ook de naam voor het oppervlak. Als zodanig raadt Adobe u aan de materialen in primaire 3D-modelbestanden een overeenkomstige naam te geven. Het gebruik van specifieke namen, zoals &#39;&#39;Body&#39;&#39;, &#39;&#39;Windows&#39;&#39;, &#39;&#39;Banden&#39;&#39; of &#39;&#39;Rims&#39;&#39;, heeft bijvoorbeeld de voorkeur boven het gebruik van vage namen, zoals &#39;&#39;Red&#39;&#39;, &#39;&#39;Glass&#39;&#39;, &#39;&#39;Rubber&#39;&#39; en &#39;&#39;Aluminium&#39;&#39;.
