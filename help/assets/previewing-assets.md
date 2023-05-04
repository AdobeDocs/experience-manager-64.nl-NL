---
title: Dynamic Media-assets vooraf bekijken
seo-title: Previewing Dynamic Media assets
description: Leer hoe u een voorvertoning van elementen kunt weergeven in Dynamic Media
seo-description: Learn how to preview assets in Dynamic Media
uuid: f0ff2fc4-a263-4dbe-ba46-b07077b49ae0
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
discoiquuid: 77296bff-8429-4240-af93-26076ae431ec
exl-id: ec05569a-6449-4430-9b9f-7ab051f44970
feature: Asset Management,Renditions
role: User
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1040'
ht-degree: 0%

---

# Dynamic Media-assets vooraf bekijken {#previewing-assets}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

U kunt **[!UICONTROL Preview]** om te zien hoe een Dynamic Media digitaal middel eruit ziet wanneer het door een klant in zijn eigen webbrowser wordt bekeken. De standaard ingesloten, apparaatoverschrijdende viewer die aan het element is toegewezen, wordt gebruikt voor de **[!UICONTROL Preview]**.

Een viewer is een verzameling van verschillende instellingen of &#39;voorinstellingen&#39;, zoals de weergavegrootte van de viewer, het zoomgedrag, kleurenschema&#39;s, randen, lettertypen enzovoort, die bepalen hoe gebruikers multimedia-elementen op hun computerschermen en mobiele apparaten weergeven.

Naast het gebruik van de specifieke voorvertoningsfunctie voor video, centrifuges en afbeeldingssets, kunt u ook een voorvertoning van een element weergeven met behulp van de door u gemaakte voorinstellingen voor de viewer. U kunt ook voorinstellingen voor afbeeldingen gebruiken om een voorvertoning van uitvoeringen van afbeeldingen weer te geven.

* [Voorinstellingen afbeelding toepassen](image-presets.md)
* [Viewer-voorinstellingen toepassen](viewer-presets.md)

>[!NOTE]
>
>Wanneer u een webpagina (sites) in AEM gebruikt, kunt u geen voorvertoning van elementen weergeven in **[!UICONTROL Edit]** in. Ga naar **[!UICONTROL Preview]** modus door te klikken **Voorvertoning** in de rechterbovenhoek.

**Elementen voorvertonen**:

1. Van **Adobe Experience Manager** over de **[!UICONTROL Navigation]** pagina, tikken **[!UICONTROL Asset]s** vervolgens **[!UICONTROL Files]** om toegang te krijgen tot elementen.
1. In de rechterbovenhoek van de pagina, vanaf de **[!UICONTROL View]** vervolgkeuzelijst, tikken **[!UICONTROL List View]**.
1. (Optioneel) Gebruik de opdracht **[!UICONTROL Type]** om de elementen te sorteren op het type waarvan u een voorvertoning wilt weergeven.
1. Onder de **[!UICONTROL Title]** klikt u op de titelnaam (niet op de miniatuurafbeelding) van het element waarvan u een voorvertoning wilt weergeven.
1. Voer afhankelijk van het type element waarop u hebt geklikt een van de volgende handelingen uit:

<table> 
 <tbody>
  <tr>
   <td><strong>Elementtype waarop u tikt</strong><br /> </td> 
   <td><strong>Kan een voorvertoning van een element weergeven in een bepaalde uitvoering?</strong></td> 
   <td><strong>Middelen voorvertonen in een bepaalde viewer?</strong></td> 
  </tr>
  <tr>
   <td><p>Afbeelding</p> </td> 
   <td>Ja</td> 
   <td>Ja</td> 
   <td><p><strong>Een voorvertoning van een element in een bepaalde uitvoering weergeven</strong></p> 
    <ul> 
     <li>Klik in de linkerbovenhoek van de pagina op het pictogram zodat de vervolgkeuzelijst wordt weergegeven. Klikken <strong>Uitvoeringen </strong>Selecteer vervolgens een bepaalde vertoning die u wilt voorvertonen in de lijst.</li> 
    </ul> <p><strong>Een voorvertoning van elementen weergeven in een bepaalde viewer</strong></p> 
    <ul> 
     <li>Klik in de linkerbovenhoek van de pagina op het pictogram zodat de vervolgkeuzelijst wordt weergegeven. Klikken <strong>Viewers</strong> Selecteer in de lijst een viewer die u op het element wilt toepassen.</li> 
    </ul> <p>Gebruik de <strong>+</strong> en <strong>- </strong>pictogrammen om respectievelijk het zoomen van de geselecteerde afbeelding te vergroten of te verkleinen. Klikken <strong>Herstellen</strong> om de oorspronkelijke zoomwaarde van de afbeelding te herstellen.<br /> Als u zich op een mobiel apparaat bevindt, dubbeltikt u op de afbeelding om stap voor stap in te zoomen. Als u het maximale zoomniveau hebt bereikt, dubbeltikt u nogmaals op de afbeelding om de zoomstatus opnieuw in te stellen. Sleep over de afbeelding om te pannen.</p> <p>Als u viewervoorinstellingen in de gebruikersinterface wilt in- of uitschakelen, raadpleegt u <a href="/help/assets/managing-viewer-presets.md">Viewer-voorinstellingen beheren</a>.<br /> </p> </td> 
  </tr>
  <tr>
   <td>Multimedia</td> 
   <td>Ja</td> 
   <td>Ja</td> 
   <td><p><strong>Een voorvertoning van een element in een bepaalde uitvoering weergeven</strong></p> 
    <ul> 
     <li>Klik in de linkerbovenhoek van de pagina op het pictogram zodat de vervolgkeuzelijst wordt weergegeven. Klikken <strong>Uitvoeringen </strong>Selecteer vervolgens een bepaalde vertoning die u wilt voorvertonen in de lijst.</li> 
    </ul> <p>Als u een video-uitvoering met een hogere resolutie selecteert die u wilt voorvertonen, kan de video afgebroken worden weergegeven. Dat komt omdat in de voorvertoning van de vertoning precies de resolutie wordt weergegeven die uw klanten zullen zien, allemaal in de context van de ingesloten viewer die wordt gebruikt voor de voorvertoning.</p> <p>Wanneer u een adaptieve videoset voorvertoont op het niveau Asset, worden de uitvoeringen gegroepeerd in één afspeelervaring. Dit betekent dat de aangepaste video op de juiste grootte is geplaatst voor weergave en wordt afgespeeld met de beste resolutie in de context van het weergaveapparaat en de verbindingssnelheid.<br /> </p> <p><strong>Een voorvertoning van een element weergeven in een bepaalde viewer</strong></p> 
    <ul> 
     <li>Klik in de linkerbovenhoek van de pagina op het pictogram zodat de vervolgkeuzelijst wordt weergegeven. Klikken <strong>Viewers</strong> Selecteer in de lijst een viewer die u op het element wilt toepassen.</li> 
    </ul> <p>Als u viewervoorinstellingen in de gebruikersinterface wilt in- of uitschakelen, raadpleegt u <a href="/help/assets/managing-viewer-presets.md">Viewer-voorinstellingen beheren</a>.</p> </td> 
  </tr>
  <tr>
   <td>Afbeeldingsset</td> 
   <td>Nee</td> 
   <td>Ja</td> 
   <td><p><strong>Een voorvertoning van een element weergeven in een bepaalde viewer</strong></p> 
    <ul> 
     <li>Klik in de linkerbovenhoek van de pagina op het pictogram zodat de vervolgkeuzelijst wordt weergegeven. Klikken <strong>Viewers</strong> Selecteer in de lijst een viewer die u op het element wilt toepassen.</li> 
    </ul> <p>Gebruik de <strong>+</strong> en <strong>- </strong>pictogrammen om respectievelijk het zoomen van de geselecteerde afbeelding te vergroten of te verkleinen. Klikken <strong>Herstellen</strong> om de oorspronkelijke zoomwaarde van de afbeelding te herstellen.<br /> Als u zich op een mobiel apparaat bevindt, dubbeltikt u op de afbeelding om stap voor stap in te zoomen. Als u het maximale zoomniveau hebt bereikt, dubbeltikt u nogmaals op de afbeelding om de zoomstatus opnieuw in te stellen. Sleep over de afbeelding om te pannen.</p> <p>Als u viewervoorinstellingen in de gebruikersinterface wilt in- of uitschakelen, raadpleegt u <a href="/help/assets/managing-viewer-presets.md">Viewer-voorinstellingen beheren</a>.</p> </td> 
  </tr>
  <tr>
   <td>Set draaien</td> 
   <td>Nee</td> 
   <td>Ja</td> 
   <td><p><strong>Een voorvertoning van een element weergeven in een bepaalde viewer</strong></p> 
    <ul> 
     <li>Klik in de linkerbovenhoek van de pagina op het pictogram zodat de vervolgkeuzelijst wordt weergegeven. Klikken <strong>Viewers</strong> Selecteer in de lijst een viewer die u op het element wilt toepassen.</li> 
    </ul> <p>Gebruik de <strong>+</strong> en <strong>- </strong>pictogrammen om respectievelijk het zoomen van de geselecteerde afbeelding te vergroten of te verkleinen. Klikken <strong>Herstellen</strong> om de oorspronkelijke zoomwaarde van de afbeelding te herstellen.<br /> Als u zich op een mobiel apparaat bevindt, dubbeltikt u op de afbeelding om stap voor stap in te zoomen. Als u het maximale zoomniveau hebt bereikt, dubbeltikt u nogmaals op de afbeelding om de zoomstatus opnieuw in te stellen. Sleep over de afbeelding om te pannen.</p> <p>Als u viewervoorinstellingen in de gebruikersinterface wilt in- of uitschakelen, raadpleegt u <a href="/help/assets/managing-viewer-presets.md">Viewer-voorinstellingen beheren</a>.</p> </td> 
  </tr>
  <tr>
   <td>Gemengde mediaset</td> 
   <td>Nee</td> 
   <td>Ja</td> 
   <td><p><strong>Een voorvertoning van een element weergeven in een bepaalde viewer</strong></p> 
    <ul> 
     <li>Klik in de linkerbovenhoek van de pagina op het pictogram zodat de vervolgkeuzelijst wordt weergegeven. Klikken <strong>Viewers</strong> Selecteer in de lijst een viewer die u op het element wilt toepassen.</li> 
    </ul> <p>Gebruik de <strong>+</strong> en <strong>- </strong>pictogrammen om respectievelijk het zoomen van de geselecteerde afbeelding te vergroten of te verkleinen. Klikken <strong>Herstellen</strong> om de oorspronkelijke zoomwaarde van de afbeelding te herstellen.<br /> Als u zich op een mobiel apparaat bevindt, dubbeltikt u op de afbeelding om stap voor stap in te zoomen. Als u het maximale zoomniveau hebt bereikt, dubbeltikt u nogmaals op de afbeelding om de zoomstatus opnieuw in te stellen. Sleep over de afbeelding om te pannen.</p> <p>Als u viewervoorinstellingen in de gebruikersinterface wilt in- of uitschakelen, raadpleegt u <a href="/help/assets/managing-viewer-presets.md">Viewer-voorinstellingen beheren</a>.</p> </td> 
  </tr>
  <tr>
   <td>Carousel-set</td> 
   <td>Nee</td> 
   <td>Ja</td> 
   <td><p><strong>Een voorvertoning van een element weergeven in een bepaalde viewer</strong></p> 
    <ul> 
     <li>Klik in de linkerbovenhoek van de pagina op het pictogram zodat de vervolgkeuzelijst wordt weergegeven. Selecteer een viewer die u op het element wilt toepassen.</li> 
    </ul> <p>Als u viewervoorinstellingen in de gebruikersinterface wilt in- of uitschakelen, raadpleegt u <a href="/help/assets/managing-viewer-presets.md">Viewer-voorinstellingen beheren</a>.</p> </td> 
  </tr>
 </tbody>
</table>
