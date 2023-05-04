---
title: Aangepast watermerk in PDF-voorvertoning letter
seo-title: Custom watermark in letter PDF preview
description: Leer hoe u een aangepast watermerk kunt maken in de PDF-voorvertoning.
seo-description: Learn how to create custom watermark in letter PDF preview.
uuid: f406de81-af94-40dd-97ec-9ca95620f961
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: correspondence-management
discoiquuid: a09e2c83-083d-427a-8336-0567e00c5712
feature: Correspondence Management
exl-id: 8aeabd95-948d-4a54-b593-1eda8ddd731b
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 0%

---

# Aangepast watermerk in PDF-voorvertoning letter {#custom-watermark-in-letter-pdf-preview}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Overzicht {#overview}

In de interface Correspondentie maken geven gebruikers van agents een voorvertoning weer van de correspondentie in de uiteindelijke vorm waarin deze wordt verzonden naar de naverwerking, bijvoorbeeld voor e-mailen of afdrukken.

Om ongeoorloofd gebruik van deze gegevens te voorkomen, kunnen organisaties een watermerk aan voorproef PDF opleggen. Het standaardwatermerk is &quot;VOORVERTONING&quot;, dat wordt weergegeven over de PDF.

Als u het watermerk wilt inschakelen in voorvertoning PDF, selecteert u de optie **[!UICONTROL Apply Watermark]** Tijdens voorvertoning, optie in **[!UICONTROL Correspondence Management Configurations]** om `https://[server]:[port]/system/console/configMgr`.

![default-watermark](assets/default-watermark.png)

U kunt de volgende stappen gebruiken om de tekst en de vormgeving van het watermerk aan te passen:

## Het watermerk aanpassen in de voorvertoning PDF in de gebruikersinterface voor het maken van correspondentie {#customizewatermark-}

1. Ga naar `https://[server]:[port]/[ContextPath]/crx/de` en aanmelden als beheerder.
1. Maak in de map Apps een map met de naam **[!UICONTROL previewwatermark]** met een pad/structuur die vergelijkbaar is met de map met het voorvertoningswatermerk in de map libs:

   1. Klik met de rechtermuisknop op de map **previewwatermark **bij het volgende pad en selecteer **Overlayknooppunt**:

      `/libs/fd/cm/configFiles/previewwatermark`

   1. Zorg ervoor dat het dialoogvenster Overlay-knooppunt de volgende waarden heeft:

      **Pad:** /libs/fd/cm/configFiles/previewwatermark

      **Locatie bedekking:** /apps/

      **Identieke knooppunttypen:** Ingeschakeld

      >[!NOTE]
      >
      >Breng geen veranderingen in de /libs tak aan. Alle wijzigingen die u aanbrengt, kunnen verloren gaan, omdat deze vertakking mogelijk wordt gewijzigd wanneer u:
      >
      >* Upgrade op uw exemplaar
      >* Een hotfix toepassen
      >* Een functiepakket installeren


   1. Klikken **OK** en klik vervolgens op **Alles opslaan**. De **[!UICONTROL previewwatermark]** wordt gemaakt in het opgegeven pad.

1. Kopieer en plak het ddx-bestand vanuit de map &quot;/libs/fd/cm/configFiles/previewwatermark&quot; naar de map &quot;/apps/fd/cm/configFiles/previewwatermark&quot; en klik op **[!UICONTROL Save All]**.
1. Breng de gewenste wijzigingen aan in het ddx-bestand onder /apps/fd/cm/configFiles/previewwatermark/.

   ```
   <DDX xmlns="https://ns.adobe.com/DDX/1.0/">
    <PDF result="output.pdf">
     <PDF source="input.pdf"/>
           <Watermark opacity="15%" rotation="45">
            <StyledText>
                     <p font-family="Georgia" font-size="70pt" color="black" font-weight="bold">
                         PREVIEW
                    </p>
            </StyledText>
           </Watermark>
    </PDF>
   </DDX>
   ```

   Zie Watermerken en achtergronden toevoegen en verwijderen in het dialoogvenster [De Verwijzing van de Assembler van de Dienst en DDX](https://help.adobe.com/en_US/livecycle/11.0/ddxRef.pdf) document.

   >[!NOTE]
   >
   >In het ddx-bestand moeten de verwijzingen naar het resultaat en de bron ongewijzigd blijven ten opzichte van output.pdf en input.pdf. De naam van de bestands-ddx mag ook niet worden gewijzigd.

1. Klikken **Alles opslaan**.
