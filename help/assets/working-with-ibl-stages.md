---
title: Werken met IBL-fasen
seo-title: Werken met IBL-fasen
description: AEM 3D ondersteunt op afbeeldingen gebaseerde belichting (IBL) voor zowel interactieve weergave als rendering met de ingebouwde Adobe Rapid Refine™ renderer en renderers van derden.
seo-description: AEM 3D ondersteunt op afbeeldingen gebaseerde belichting (IBL) voor zowel interactieve weergave als rendering met de ingebouwde Adobe Rapid Refine™ renderer en renderers van derden.
uuid: 495ba9cc-02f5-4ce5-9503-9f61ca5482db
contentOwner: Rick Brough
topic-tags: 3D
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
discoiquuid: 658ff671-16b9-41bd-ba24-b77a32b3346b
exl-id: 074ab20f-02df-4f9e-9512-93a76f5d234f
feature: 3D-middelen
role: Business Practitioner
translation-type: tm+mt
source-git-commit: f9faa357f8de92d205f1a297767ba4176cfd1e10
workflow-type: tm+mt
source-wordcount: '840'
ht-degree: 0%

---

# Informatie over het werken met IBL-fasen {#about-working-with-ibl-stages}

AEM 3D ondersteunt op afbeeldingen gebaseerde belichting (IBL) voor zowel interactieve weergave als rendering met de ingebouwde Adobe Rapid Refine™ renderer en renderers van derden. U kunt IBL-fasen maken met algemene ontwerpgereedschappen, zoals Autodesk® Maya® of Autodesk® 3ds Max®.

## Afbeeldingen voor IBL {#images-for-ibl}

Voor het beste resultaat moeten afbeeldingen die worden gebruikt voor op afbeeldingen gebaseerde belichting HDR (High Dynamic Range) hebben. Zij moeten in lange of lange vorm worden opgesteld met een bolvormige toewijzing die het milieu volledig bestrijkt.

AEM 3D biedt momenteel alleen ondersteuning voor 32-bits TIFF-bestanden. Gebruik indien nodig Adobe Photoshop of een vergelijkbaar gereedschap om de HDR-afbeelding om te zetten in een TIFF met behulp van de volgende instellingen in het dialoogvenster Adobe Photoshop TIFF-export:

* **[!UICONTROL Bit depth]** - 32 bits (zwevend)
* **[!UICONTROL Pixel Order]** - Interleaved (RGBRGB)
* **[!UICONTROL Image Compression]** - LZW
* **[!UICONTROL Byte Order]** - IBM PC

Hoewel één HDR-afbeelding vaak voldoende is voor IBL-fasen, biedt AEM 3D extra controle over IBL-effecten door maximaal drie aparte afbeeldingen toe te staan:

* **Afbeelding**  met diffuse belichting - Dit type afbeelding moet een HDR-afbeelding zijn, maar kan relatief klein zijn, omdat de afbeelding sterk wordt gefilterd voordat deze wordt gebruikt voor diffuse belichting.
* **Afbeelding**  reflectieomgeving - Dit type afbeelding wordt gebruikt om reflecties te maken op objectoppervlakken. Dit kan een standaard 8-bits RGB-afbeelding met een grootte en resolutie zijn die de gewenste kwaliteit en scherpte van reflecties biedt. Als een HDR-afbeelding is opgegeven, zet AEM 3D deze om in 8-bits RGB voordat een eigen algoritme wordt gebruikt.
* **Afbeelding**  achtergrondomgeving - Dit type afbeelding wordt gebruikt als achtergrond. Dit kan een standaard 8-bits RGB-afbeelding zijn en moet een formaat/resolutie/detailniveau hebben dat u voor de achtergrond van het werkgebied wilt gebruiken. Als een HDR-afbeelding is opgegeven, zet AEM 3D deze om in 8-bits RGB met behulp van een eigen algoritme.

>[!NOTE]
>
>Het conversiealgoritme kan problemen hebben met bepaalde IBL-afbeeldingen. Dit kan resulteren in achtergronden die te helder of te verzadigd zijn in Voorvertoning of bij rendering met Rapid Refine. In dergelijke situaties raadt Adobe u aan Photoshop of een vergelijkbaar programma te gebruiken om de IBL-afbeelding handmatig om te zetten in een 8-bits RGB-afbeelding. Upload deze afbeelding afzonderlijk en koppel deze aan het werkgebied als achtergrondafbeelding in de omgeving. De afbeeldingen in de omgeving voor onscherpe belichting en reflectie moeten altijd 32-bits TIFF&#39;s zijn.

## De weergave van het IBL-werkgebied aanpassen {#adjusting-the-ibl-stage-appearance}

U kunt de weergave van het IBL-werkgebied verfijnen met de volgende eigenschappen van het werkgebied:

<table> 
 <tbody> 
  <tr> 
   <td><strong>Eigenschap</strong><br /> </td> 
   <td><strong>Beschrijving</strong></td> 
  </tr> 
  <tr> 
   <td>IBL Sun - Gegevens</td> 
   <td><p>Hiermee kunt u de richting en sterkte van de aanvullende lichtbron die de zon simuleert, aanpassen. <span class="diff-html-added">Met deze lichtbron verhoogt u de helderheid van de belichting en wordt een slagschaduw op het grondvlak geplaatst. Schaduwcasting wordt ondersteund bij rendering met Rapid Refine en bij voorvertonen met Google Chrome. het wordt momenteel echter niet ondersteund door andere browsers.</span></p> 
    <ul> 
     <li><strong>lat</strong> - de verticale positie van de lichtbron van de zon (<code>0.0</code>-<code>1.0</code>).<br /> Een instelling van  <code>0.0</code> bevindt zich aan de horizon (verticaal middelpunt van de afbeelding voor onscherpe belichting);  <code>1.0</code> bevindt zich op de zenith (bovenrand van de afbeelding voor onscherpe belichting).</li> 
     <li><strong>long</strong> : de horizontale positie van de zonlichtbron (<code>0.0</code>-<code>1.0</code>).<br /> Een instelling van 0,0 komt overeen met de linkerinstelling; 1.0 komt overeen met de rechterrand van de afbeelding voor onscherpe belichting.<br /> </li> 
     <li><strong>helder</strong>  - De helderheid van de lichtbron van de zon. Verhoog deze waarde om de zonlichtbron lichter te maken. Verlaag deze waarde om donkerder te maken. <br /> Met een instelling van  <code>0</code> schakelt u aanvullende belichting uit en schakelt u gegoten schaduwen uit. De parameter heeft geen invloed op omgevingsreflecties.<br /> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>Hoogte IBL-camera</td> 
   <td>Als de IBL-achtergrond bij de horizon vervormd lijkt, is het mogelijk om de vervorming te verminderen of te elimineren door deze eigenschap aan te passen. <br /> </td> 
  </tr> 
  <tr> 
   <td>Omgevingsbelichting</td> 
   <td><p><span class="diff-html-added">Hiermee kunt u de diffuse belichting besturen. Mogelijk moet u deze eigenschap handmatig aanpassen om de helderheid van de belichting te corrigeren als de afbeelding voor onscherpe belichting ongebruikelijk helder of donker is (bijvoorbeeld nachtscènes).</span></p> 
    <ul> 
     <li><strong>r, g, b</strong> - Momenteel niet gebruikt.</li> 
     <li><strong>helderheid</strong> -  <span class="diff-html-added">helderheidsvermenigvuldiger. Als u deze waarde verhoogt of verlaagt, neemt de totale lichtintensiteit toe of af (zowel de standaard-IBL-belichting als de helderheid van de zonlichtbron).</span></li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## De bolvormige achtergronddiameter van een IBL-werkgebied vergroten {#increasing-the-spherical-background-diameter-of-an-ibl-stage}

De stadia van IBL gebruiken sferische achtergrondbeelden die door gebrek 20 meters diameter zijn. Dergelijke stadia werken goed voor voorwerpen tot 10 meters. Als u echter grotere objecten weergeeft, kunt u de bolvormige achtergronddiameter van een IBL-werkgebied vergroten.

**De bolvormige achtergronddiameter van een IBL-fase** vergroten:

1. Navigeer in CRXDE Lite naar het werkgebied waarvan u de bolvormige achtergronddiameter wilt vergroten. Bijvoorbeeld,

   `/content/dam/test3d/stage-helipad.fbx`

1. Vouw het werkgebiedknooppunt uit tot `jcr:content/metadata`.
1. Stel de eigenschap `dam:gPlaneRadius` in op de gewenste waarde in millimeter.

   Adobe raadt u aan deze waarde te beperken tot ongeveer de grootste afmeting van het grootste object dat u in het werkgebied wilt weergeven.

   Een straalvliegtuigmodel dat 20 meter lang is, wordt bijvoorbeeld goed weergegeven als `dam:gPlaneRadius=20000`.

1. Tik in de linkerbovenhoek van de pagina CRXDE Lite op **[!UICONTROL Save All]**.
