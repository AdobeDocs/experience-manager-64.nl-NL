---
title: Middelen verwerken met behulp van media-handlers en workflows
description: Meer informatie over verschillende mediafuncties en hoe u deze kunt gebruiken in workflows om taken uit te voeren op elementen.
contentOwner: AG
feature: Workflow,uitvoeringen
role: Business Practitioner
exl-id: 7694c68d-0a17-4052-8fbe-9bf45b229e81
translation-type: tm+mt
source-git-commit: bd94d3949f0117aa3e1c9f0e84f7293a5d6b03b4
workflow-type: tm+mt
source-wordcount: '2171'
ht-degree: 2%

---

# Elementen verwerken met behulp van media-handlers en workflows {#processing-assets-using-media-handlers-and-workflows}

Adobe Experience Manager Assets biedt een set standaardworkflows en mediahandlers voor het verwerken van elementen. Een workflow definieert een typische middelenbeheer- en verwerkingstaak en delegeert de specifieke taken aan de mediafunctionarissen, bijvoorbeeld het genereren van miniaturen of het uitnemen van metagegevens.

Er kan een workflow worden gedefinieerd die automatisch wordt uitgevoerd wanneer een element van een bepaald type of een bepaalde indeling naar de server wordt geüpload. De verwerkingsstappen worden gedefinieerd als een reeks van Experience ManagerAssets-media-handlers. Adobe Experience Manager biedt enkele [ingebouwde handlers,](#default-media-handlers) en meer kunnen [aangepast zijn ontwikkeld](#creating-a-new-media-handler) of worden gedefinieerd door het proces te delegeren aan een [opdrachtregelprogramma](#command-line-based-media-handler).

Mediahandlers zijn services binnen Experience Manager Assets die specifieke handelingen uitvoeren op elementen. Wanneer bijvoorbeeld een MP3-audiobestand naar de Experience Manager wordt geüpload, wordt met een workflow een MP3-handler geactiveerd die de metagegevens extraheert en een miniatuur genereert. Mediahandlers worden gebruikt bij workflows. De meeste gangbare MIME-typen worden ondersteund in Experience Manager. U kunt specifieke taken op elementen uitvoeren door een van de volgende handelingen uit te voeren

* Workflows uitbreiden of maken.
* Mediahandlers uitbreiden of maken.
* Media-handlers uitschakelen of inschakelen.

>[!NOTE]
>
>Zie [Ondersteunde indelingen voor elementen](assets-formats.md) pagina voor een beschrijving van alle indelingen die worden ondersteund door Experience Manager Assets en functies die worden ondersteund voor elke indeling.

## Standaardmediahandlers {#default-media-handlers}

De volgende media managers zijn beschikbaar binnen de Elementen van de Experience Manager en behandelen de gemeenschappelijkste types MIME:

| Naam handler | Servicenaam (in de systeemconsole) | Ondersteunde MIME-typen |
|---|---|---|
| [!UICONTROL TextHandler] | com.day.cq.dam.core.impl.handler.TextHandler | text/plain |
| [!UICONTROL PdfHandler] | com.day.cq.dam.handler.standard.pdf.PdfHandler | <ul><li>application/pdf</li><li>toepassing/illustrator</li></ul> |
| [!UICONTROL JpegHandler] | com.day.cq.dam.core.impl.handler.JpegHandler | image/jpeg |
| [!UICONTROL Mp3Handler] | com.day.cq.dam.handler.standard.mp3.Mp3Handler | audio/mpeg<br><b>Belangrijk</b> - Wanneer u een MP3-bestand uploadt, wordt het [verwerkt met behulp van een externe bibliotheek](http://www.zxdr.it/programmi/SistEvolBDD/LibJava/doc/de/vdheide/mp3/MP3File.html). De bibliotheek berekent een onnauwkeurige benaderende lengte als MP3 veranderlijke bitrate (VBR) heeft. |
| [!UICONTROL ZipHandler] | com.day.cq.dam.handler.standard.zip.ZipHandler | <ul><li>application/java-archive </li><li> application/zip</li></ul> |
| [!UICONTROL PictHandler] | com.day.cq.dam.handler.standard.pict.PictHandler | image/pict |
| [!UICONTROL StandardImageHandler] | com.day.cq.dam.core.impl.handler.StandardImageHandler | <ul><li>image/gif </li><li> image/png </li> <li>toepassing/photoshop </li> <li>image/jpeg </li><li> image/tiff </li> <li>image/x-ms-bmp </li><li> image/bmp</li></ul> |
| [!UICONTROL MSOfficeHandler] | com.day.cq.dam.handler.standard.msoffice.MSOfficeHandler | application/msword |
| [!UICONTROL MSPowerPointHandler] | com.day.cq.dam.handler.standard.msoffice.MSPowerPointHandler | application/vnd.ms-powerpoint |
| [!UICONTROL OpenOfficeHandler] | com.day.cq.dam.handler.standard.ooxml.OpenOfficeHandler | <ul><li>application/vnd.openxmlformats-officedocument.wordprocessingml.document</li><li> application/vnd.openxmlformats-officedocument.spreadsheetml.sheet</li><li> application/vnd.openxmlformats-officedocument.presentationml.presentation</li></ul> |
| [!UICONTROL EPubHandler] | com.day.cq.dam.handler.standard.epub.EPubHandler | application/epub+zip |
| [!UICONTROL GenericAssetHandler] | com.day.cq.dam.core.impl.handler.GenericAssetHandler | fallback als er geen andere handler is gevonden om gegevens uit een element te extraheren |

Alle managers voeren de volgende taken uit:

* alle beschikbare metagegevens uit het element extraheren.
* een miniatuurafbeelding maken van het element.

Het is mogelijk om de actieve media managers te bekijken:

1. Navigeer in uw browser naar `http://localhost:4502/system/console/components`.
1. Klik op de koppeling `com.day.cq.dam.core.impl.store.AssetStoreImpl`.
1. Er wordt een lijst weergegeven met alle actieve mediamanagers. Bijvoorbeeld:

![chlimage_1-437](assets/chlimage_1-437.png)

## Mediahandlers gebruiken in workflows om taken uit te voeren op Elementen {#using-media-handlers-in-workflows-to-perform-tasks-on-assets}

De managers van media zijn de diensten die met werkschema&#39;s worden gebruikt.

Experience Manager heeft enkele standaardworkflows om elementen te verwerken. Open de workflowconsole en klik op het tabblad **[!UICONTROL Models]** om deze weer te geven: de workflowtitels die beginnen met Experience Manager Assets zijn de assets-specifieke titels.

Bestaande workflows kunnen worden uitgebreid en nieuwe workflows kunnen worden gemaakt om elementen volgens specifieke vereisten te verwerken.

In het volgende voorbeeld wordt getoond hoe u de **[!UICONTROL AEM Assets Synchronization]**-workflow kunt verbeteren, zodat subelementen worden gegenereerd voor alle elementen behalve PDF-documenten.

### Een mediafunctie uitschakelen/inschakelen {#disabling-enabling-a-media-handler}

De media-handlers kunnen worden uitgeschakeld of ingeschakeld via de Apache Felix Web Management Console. Wanneer de media-handler is uitgeschakeld, worden de taken niet uitgevoerd op de elementen.

Een media-handler in- en uitschakelen:

1. Navigeer in uw browser naar `https://<host>:<port>/system/console/components`.
1. Klik **[!UICONTROL Disable]** naast de naam van de media manager. Bijvoorbeeld: `com.day.cq.dam.handler.standard.mp3.Mp3Handler`.
1. De pagina vernieuwen: naast de mediafunctie wordt een pictogram weergegeven dat aangeeft dat het is uitgeschakeld.
1. Als u de mediafunctie wilt inschakelen, klikt u op **[!UICONTROL Enable]** naast de naam van de mediafunctie.

### Een mediafunctie {#creating-a-new-media-handler} maken

Voor ondersteuning van een nieuw mediatype of voor het uitvoeren van specifieke taken op een element, is het nodig een mediafunctie te maken. In dit gedeelte wordt beschreven hoe u verder kunt gaan.

#### Belangrijke klassen en interfaces {#important-classes-and-interfaces}

De beste manier om een implementatie te beginnen is van een verstrekte abstracte implementatie te erven die de meeste dingen behandelt en redelijk standaardgedrag verstrekt: de klasse `com.day.cq.dam.core.AbstractAssetHandler`.

Deze klasse verstrekt reeds een abstracte de dienstbeschrijver. Dus als u overerft van deze klasse en de maven-sling-plugin gebruikt, zorg ervoor dat u de inherit vlag aan `true` plaatst.

Voer de volgende methodes uit:

* `extractMetadata()`: extraheert alle beschikbare metagegevens.
* `getThumbnailImage()`: Hiermee maakt u een miniatuurafbeelding van het doorgegeven element.
* `getMimeTypes()`: retourneert de MIME-typen van het element.

Hier volgt een voorbeeldsjabloon:

`package my.own.stuff; /** * @scr.component inherit="true" * @scr.service */ public class MyMediaHandler extends com.day.cq.dam.core.AbstractAssetHandler { // implement the relevant parts } `

De interface en de klassen omvatten:

* `com.day.cq.dam.api.handler.AssetHandler` interface: Deze interface beschrijft de dienst die steun voor specifieke types MIME toevoegt. Als u een MIME-type wilt toevoegen, moet u deze interface implementeren. De interface bevat methoden voor het importeren en exporteren van de specifieke documenten, voor het maken van miniaturen en het uitnemen van metagegevens.
* `com.day.cq.dam.core.AbstractAssetHandler` klasse: Deze klasse fungeert als basis voor alle andere implementaties van elementenhandlers en biedt veelgebruikte functionaliteit.
* `com.day.cq.dam.core.AbstractSubAssetHandler`-klasse:
   * Deze klasse fungeert als basis voor alle andere implementaties van assethandlers en biedt veelgebruikte functionaliteit plus veelgebruikte functionaliteit voor het extraheren van subassets.
   * De beste manier om een implementatie te beginnen is van een verstrekte abstracte implementatie te erven die de meeste dingen behandelt en redelijk standaardgedrag verstrekt: de klasse com.day.cq.dam.core.AbstractAssetHandler.
   * Deze klasse verstrekt reeds een abstracte de dienstbeschrijver. Dus als u overerft van deze klasse en de gemaven-sling-plugin gebruikt, zorg ervoor dat u de overervingsvlag aan waar plaatst.

De volgende methoden moeten worden toegepast:

* `extractMetadata()`: met deze methode worden alle beschikbare metagegevens geëxtraheerd.
* `getThumbnailImage()`: met deze methode maakt u een miniatuurafbeelding van het doorgegeven element.
* `getMimeTypes()`: Deze methode retourneert de MIME-typen van het element.

Hier volgt een voorbeeldsjabloon:

pakket my.own.stuff; /&amp;ast;&amp;ast; &amp;ast; @scr.component inherit=&quot;true&quot;&amp;ast; @scr.service&amp;ast;/ openbare klasse MyMediaHandler breidt com.day.cq.dam.core.AbstractAssetHandler { // implementeert de relevante onderdelen }

De interface en de klassen omvatten:

* `com.day.cq.dam.api.handler.AssetHandler` interface: Deze interface beschrijft de dienst die steun voor specifieke mime types toevoegt. Als u een MIME-type wilt toevoegen, moet u deze interface implementeren. De interface bevat methoden voor het importeren en exporteren van de specifieke documenten, voor het maken van miniaturen en het uitnemen van metagegevens.
* `com.day.cq.dam.core.AbstractAssetHandler` klasse: Deze klasse fungeert als basis voor alle andere implementaties van elementenhandlers en biedt veelgebruikte functionaliteit.
* `com.day.cq.dam.core.AbstractSubAssetHandler` klasse: Deze klasse fungeert als basis voor alle andere implementaties van elementenhandlers en biedt veelgebruikte functionaliteit plus veelgebruikte functionaliteit voor het extraheren van subelementen.

#### Voorbeeld: een specifieke teksthandler maken {#example-create-a-specific-text-handler}

In deze sectie gaat u een specifieke teksthandler maken die miniaturen met een watermerk genereert.

Ga als volgt te werk:

Raadpleeg [Development Tools](../sites-developing/dev-tools.md) om Eclipse te installeren en in te stellen met een Maven-plug-in en voor het instellen van de afhankelijkheden die nodig zijn voor het Maven-project.

Nadat u de volgende procedure hebt uitgevoerd en een tekstbestand in de Experience Manager laadt, worden de metagegevens van het bestand geëxtraheerd en worden twee miniaturen met een watermerk gegenereerd.

1. In Eclipse, creeer `myBundle` Geweven project:

   1. Klik in de menubalk op **[!UICONTROL File > New > Other]**.
   1. Vouw in het dialoogvenster de map Geweven uit, selecteer Geweven project en klik op **[!UICONTROL Next]**.
   1. Schakel de selectievakjes **[!UICONTROL Create a simple project]** en **[!UICONTROL Use default Workspace locations]** in en klik op **[!UICONTROL Next]**.
   1. Definieer het Maven-project met de volgende waarden:

      * Groep-id: com.day.cq5.myhandler
      * Artefact-id: myBundle
      * Naam: Mijn Experience Manager
      * Omschrijving: Dit is mijn Experience Manager bundel
   1. Klik op **[!UICONTROL Finish]**.


1. Stel de Java™ Compiler in op versie 1.5:

   1. Klik met de rechtermuisknop op het `myBundle`-project en selecteer Eigenschappen.
   1. Selecteer Java™ Compiler en stel de volgende eigenschappen in op 1.5:

      * Compatibiliteitsniveau compiler
      * Compatibiliteit van gegenereerde .class-bestanden
      * Broncompatibiliteit
   1. Klik op **[!UICONTROL OK]**. Klik in het dialoogvenster op Ja.


1. Vervang de code in het bestand pom.xml door de volgende code:

   ```xml
   <project xmlns="https://maven.apache.org/POM/4.0.0" xmlns:xsi="https://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="https://maven.apache.org/POM/4.0.0 https://maven.apache.org/maven-v4_0_0.xsd">
    <modelVersion>4.0.0</modelVersion> 
    <!-- ====================================================================== --> 
    <!-- P A R E N T P R O J E C T D E S C R I P T I O N --> 
    <!-- ====================================================================== -->
    <parent>
     <groupId>com.day.cq.dam</groupId>
     <artifactId>dam</artifactId>
     <version>5.2.14</version>
     <relativePath>../parent</relativePath>
    </parent> 
    <!-- ====================================================================== --> 
    <!-- P R O J E C T D E S C R I P T I O N --> 
    <!-- ====================================================================== -->
    <groupId>com.day.cq5.myhandler</groupId>
    <artifactId>myBundle</artifactId>
    <name>My CQ5 bundle</name>
    <version>0.0.1-SNAPSHOT</version>
    <description>This is my CQ5 bundle</description>
    <packaging>bundle</packaging> 
    <!-- ====================================================================== --> 
    <!-- B U I L D D E F I N I T I O N --> 
    <!-- ====================================================================== -->
    <build>
     <plugins>
      <plugin>
       <groupId>org.apache.felix</groupId>
       <artifactId>maven-scr-plugin</artifactId>
      </plugin>
      <plugin>
       <groupId>org.apache.sling</groupId>
       <artifactId>maven-sling-plugin</artifactId>
       <configuration>
        <slingUrlSuffix>/libs/dam/install/</slingUrlSuffix>
       </configuration>
      </plugin>
      <plugin>
       <groupId>org.apache.felix</groupId>
       <artifactId>maven-bundle-plugin</artifactId>
       <extensions>true</extensions>
       <configuration>
        <instructions>
         <Bundle-Category>cq5</Bundle-Category>
         <Export-Package> com.day.cq5.myhandler </Export-Package>
        </instructions>
       </configuration>
      </plugin>
     </plugins>
    </build> 
    <!-- ====================================================================== --> 
    <!-- D E P E N D E N C I E S --> 
    <!-- ====================================================================== -->
    <dependencies>
     <dependency>
      <groupId>com.day.cq.dam</groupId>
      <artifactId>cq-dam-api</artifactId>
      <version>5.2.10</version>
      <scope>provided</scope>
     </dependency>
     <dependency>
      <groupId>com.day.cq.dam</groupId>
      <artifactId>cq-dam-core</artifactId>
      <version>5.2.10</version>
      <scope>provided</scope>
     </dependency>
     <dependency>
      <groupId>com.day.cq</groupId>
      <artifactId>cq-commons</artifactId>
     </dependency>
     <dependency>
      <groupId>javax.jcr</groupId>
      <artifactId>jcr</artifactId>
     </dependency>
     <dependency>
      <groupId>org.apache.felix</groupId>
      <artifactId>org.osgi.compendium</artifactId>
     </dependency>
     <dependency>
      <groupId>org.slf4j</groupId>
      <artifactId>slf4j-api</artifactId>
     </dependency>
     <dependency>
      <groupId>commons-lang</groupId>
      <artifactId>commons-lang</artifactId>
     </dependency>
     <dependency>
      <groupId>commons-collections</groupId>
      <artifactId>commons-collections</artifactId>
     </dependency>
     <dependency>
      <groupId>commons-io</groupId>
      <artifactId>commons-io</artifactId>
     </dependency>
     <dependency>
      <groupId>com.day.commons</groupId>
      <artifactId>day-commons-gfx</artifactId>
     </dependency>
     <dependency>
      <groupId>com.day.commons</groupId>
      <artifactId>day-commons-text</artifactId>
     </dependency>
     <dependency>
      <groupId>com.day.cq.workflow</groupId>
      <artifactId>cq-workflow-api</artifactId>
     </dependency>
     <dependency>
      <groupId>com.day.cq.wcm</groupId>
      <artifactId>cq-wcm-foundation</artifactId>
      <version>5.2.22</version>
     </dependency>
    </dependencies>
   ```

1. Maak het pakket `com.day.cq5.myhandler` dat de Java™-klassen bevat onder `myBundle/src/main/java`:

   1. Klik onder myBundle met de rechtermuisknop op `src/main/java`, selecteer Nieuw en vervolgens Pakket.
   1. Geef deze `com.day.cq5.myhandler` een naam en klik op Voltooien.

1. Maak de Java™-klasse `MyHandler`:

   1. Klik in Eclipse onder `myBundle/src/main/java` met de rechtermuisknop op het pakket `com.day.cq5.myhandler`, selecteer Nieuw en vervolgens Klasse.
   1. Geef in het dialoogvenster de naam Java™ Class MyHandler en klik op Voltooien. Eclipse maakt en opent het bestand MyHandler.java.
   1. Vervang in `MyHandler.java` de bestaande code door het volgende en sla de wijzigingen op:

   ```java
   package com.day.cq5.myhandler; 
   import java.awt.Color; 
   import java.awt.Rectangle; 
   import java.awt.image.BufferedImage; 
   import java.io.IOException; 
   import java.io.InputStream; 
   import java.io.InputStreamReader; 
   import javax.jcr.Node; 
   import javax.jcr.RepositoryException; 
   import javax.jcr.Session; 
   import org.apache.commons.io.IOUtils; 
   import org.slf4j.Logger; 
   import org.slf4j.LoggerFactory; 
   import com.day.cq.dam.api.metadata.ExtractedMetadata; 
   import com.day.cq.dam.core.AbstractAssetHandler; 
   import com.day.image.Font; 
   import com.day.image.Layer; 
   import com.day.cq.wcm.foundation.ImageHelper; 
   
   /** 
    * The <code>MyHandler</code> can extract text files 
    * @scr.component inherit="true" immediate="true" metatype="false" 
    * @scr.service 
    * 
    **/ 
   
   public class MyHandler extends AbstractAssetHandler { 
    /** * Logger instance for this class. */ 
    private static final Logger log = LoggerFactory.getLogger(MyHandler.class); 
    /** * Music icon margin */ 
    private static final int MARGIN = 10; 
    /** * @see com.day.cq.dam.api.handler.AssetHandler#getMimeTypes() */ 
    public String[] getMimeTypes() {
     return new String[] {"text/plain"}; 
    }
   
    public ExtractedMetadata extractMetadata(Node asset) { 
     ExtractedMetadata extractedMetadata = new ExtractedMetadata(); 
     InputStream data = getInputStream(asset); 
     try { 
      // read text data 
      InputStreamReader reader = new InputStreamReader(data); 
      char[] buffer = new char[4096]; 
      String text = ""; 
      while (reader.read(buffer) != -1) { 
       text += new String(buffer); 
      } 
      reader.close(); 
      long wordCount = this.wordCount(text); 
      extractedMetadata.setProperty("text", text); 
      extractedMetadata.setMetaDataProperty("Word Count",wordCount); 
      setMimetype(extractedMetadata, asset); 
     } catch (Throwable t) { 
      log.error("handling error: " + t.toString(), t); 
     } finally { 
      IOUtils.closeQuietly(data); 
     } 
     return extractedMetadata; } 
    // ----------------------< helpers >---------------------------------------- 
    protected BufferedImage getThumbnailImage(Node node) { 
     ExtractedMetadata metadata = extractMetadata(node); 
     final String text = (String) metadata.getProperty("text"); 
     // create text layer 
     final Layer layer = new Layer(500, 600, Color.WHITE); 
     layer.setPaint(Color.black); 
     Font font = new Font("Arial", 12); 
     String displayText = this.getDisplayText(text, 600, 12); 
     if(displayText!=null && displayText.length() > 0) {
      // commons-gfx Font class would throw IllegalArgumentException on empty or null text 
      layer.drawText(10, 10, 500, 600, displayText, font, Font.ALIGN_LEFT, 0, 0); 
     } 
     // create watermark and merge with text layer 
     Layer watermarkLayer; 
     try { 
      final Session session = node.getSession(); 
      watermarkLayer = ImageHelper.createLayer(session, "/content/dam/geometrixx/icons/certificate.png"); 
      watermarkLayer.setX(MARGIN); 
      watermarkLayer.setY(MARGIN); 
      layer.merge(watermarkLayer); 
     } catch (RepositoryException e) { 
      // TODO Auto-generated catch block 
      e.printStackTrace(); 
     } catch (IOException e) { 
      // TODO Auto-generated catch block 
      e.printStackTrace(); } 
     layer.crop(new Rectangle(510, 600)); 
     return layer.getImage(); } 
    // ---------------< private >----------------------------------------------- 
    /** 
     * This method cuts lines if the text file is too long..
     * * @param text
     * * text to check
     * * @param height
     * * text box height (px)
     * * @param fontheight
     * * font height (px) 
     * * @return the text which will fit into the box 
     */ 
    private String getDisplayText(String text, int height, int fontheight) { 
     String trimmedText = text.trim(); 
     int numOfLines = height / fontheight; 
     String lines[] = trimmedText.split("\n"); 
     if (lines.length <= numOfLines) { 
      return trimmedText; 
     } else { 
      String cuttetText = ""; 
      for (int i = 0; i < numOfLines; i++) { 
       cuttetText += lines[i] + "\n"; 
      } 
      return cuttetText; 
     } 
    } 
    /**
     * * This method counts the number of words in a string 
     * * @param text the String whose words would like to be counted
     * * @return the number of words in the string
     * */ 
    private long wordCount(String text) { 
     // We need to keep track of the last character, if we have two whitespace in a row we don't want to double count.
     // The starting of the document is always a whitespace.
     boolean prevWhiteSpace = true; 
     boolean currentWhiteSpace = true; 
     char c; long numwords = 0; 
     int j = text.length(); 
     int i = 0; 
     while (i < j) { 
      c = text.charAt(i++); 
      if (c == 0) { break; } 
      currentWhiteSpace = Character.isWhitespace(c); 
      if (currentWhiteSpace && !prevWhiteSpace) { numwords++; } 
      prevWhiteSpace = currentWhiteSpace; 
     } 
     // If we do not end with a whitespace then we need to add one extra word.
     if (!currentWhiteSpace) { numwords++; } 
     return numwords; 
    } 
   }
   ```

1. Compileer de Java™-klasse en maak de bundel:

   1. Klik met de rechtermuisknop op het myBundle-project, selecteer **[!UICONTROL Run As]** en **[!UICONTROL Maven Install]**.
   1. De bundel `myBundle-0.0.1-SNAPSHOT.jar` (die de gecompileerde klasse bevat) wordt gecreeerd onder `myBundle/target`.

1. Maak in CRX Explorer een knooppunt onder `/apps/myApp`. Naam = `install`, Type = `nt:folder`.
1. Kopieer de bundel `myBundle-0.0.1-SNAPSHOT.jar` en bewaar deze onder `/apps/myApp/install` (bijvoorbeeld met WebDAV). De nieuwe teksthandler is nu actief in Experience Manager.
1. Open de Apache Felix Web Management Console in uw browser. Selecteer het tabblad Componenten en schakel de standaardteksthandler `com.day.cq.dam.core.impl.handler.TextHandler` uit.

## Op opdrachtregel gebaseerde mediafunctie {#command-line-based-media-handler}

Met Experience Manager kunt u elk opdrachtregelprogramma binnen een workflow uitvoeren om elementen (zoals ImageMagick) om te zetten en de nieuwe uitvoering aan het element toe te voegen. Installeer het opdrachtregelprogramma op de schijf die als host fungeert voor de Experience Manager-server en voeg een processtap toe aan de workflow en configureer deze. Het aangeroepen proces, met de naam `CommandLineProcess`, filtert volgens specifieke MIME-typen en maakt meerdere miniaturen op basis van de nieuwe uitvoering.

De volgende conversies kunnen automatisch worden uitgevoerd en opgeslagen in Experience Manager Assets:

* EPS- en AI-transformatie met [ImageMagick](https://www.imagemagick.org/script/index.php) en [Ghostscript](https://www.ghostscript.com/)
* FLV-videotranscodering met [Mpeg](https://ffmpeg.org/)
* MP3-codering met [LAME](http://lame.sourceforge.net/)
* Audio-verwerking met behulp van [SOX](http://sox.sourceforge.net/)

>[!NOTE]
>
>Op niet-Windows-systemen retourneert het FFMpeg-gereedschap een fout tijdens het genereren van uitvoeringen voor een video-element met één aanhalingsteken (&#39;) in de bestandsnaam. Als de naam van het videobestand één aanhalingsteken bevat, verwijdert u dit voordat u het bestand uploadt naar de Experience Manager.

Met het proces `CommandLineProcess` worden de volgende bewerkingen uitgevoerd in de volgorde waarin ze worden weergegeven:

* Hiermee wordt het bestand gefilterd op basis van specifieke mime-typen, indien opgegeven.
* Maakt een tijdelijke map op de schijf die als host fungeert voor de Experience Manager-server.
* Hiermee wordt het oorspronkelijke bestand gestroomd naar de tijdelijke map.
* Voert de opdracht uit die door de argumenten van de stap wordt gedefinieerd. De opdracht wordt uitgevoerd in de tijdelijke map met de machtigingen van de gebruiker die de Experience Manager uitvoert.
* Streamt het resultaat terug naar de vertoningsomslag van de server van de Experience Manager.
* Hiermee verwijdert u de tijdelijke map.
* Hiermee maakt u miniaturen op basis van deze uitvoeringen, indien opgegeven. Het aantal en de afmetingen van de miniaturen worden bepaald door de argumenten van de stap.

### Een voorbeeld met ImageMagick {#an-example-using-imagemagick}

In het volgende voorbeeld ziet u hoe u de processtap van de opdrachtregel instelt. Telkens wanneer een element met het MIME-type gif of tiff aan `/content/dam` op de server van de Experience Manager wordt toegevoegd, wordt een gespiegelde afbeelding van het origineel gemaakt samen met drie andere miniaturen (140x100, 48x48 en 10x250).

Gebruik ImageMagick om deze processtap uit te voeren. Installeer ImageMagick op de schijf die als host fungeert voor de Experience Manager-server:

1. Installeer ImageMagick. Zie [documentatie ImageMagick](https://www.imagemagick.org/script/download.php) voor meer informatie.
1. Stel het gereedschap zo in dat u `convert` op de opdrachtregel kunt uitvoeren.
1. Als u wilt controleren of het gereedschap op de juiste wijze is geïnstalleerd, voert u de volgende opdracht `convert -h` uit op de opdrachtregel.

   Er wordt een Help-scherm weergegeven met alle mogelijke opties van het gereedschap Omzetten.

   >[!NOTE]
   >
   >In sommige versies van Windows® (bijvoorbeeld Windows® SE) kan de opdracht Converteren niet worden uitgevoerd omdat dit een conflict veroorzaakt met het native conversiehulpprogramma dat onderdeel is van de installatie van Windows®. Vermeld in dit geval het volledige pad voor het hulpprogramma ImageMagick dat wordt gebruikt om afbeeldingsbestanden om te zetten in miniaturen. Bijvoorbeeld, `"C:\Program Files\ImageMagick-6.8.9-Q16\convert.exe" -define jpeg:size=319x319 ${filename} -thumbnail 319x319 cq5dam.thumbnail.319.319.png`.

1. Als u wilt zien of het gereedschap correct wordt uitgevoerd, voegt u een JPG-afbeelding toe aan de werkmap en voert u de opdracht `convert <image-name>.jpg -flip <image-name>-flipped.jpg` uit op de opdrachtregel.

   Er wordt een gespiegelde afbeelding aan de map toegevoegd.

Voeg vervolgens de processtap van de opdrachtregel toe aan de workflow **[!UICONTROL DAM Update Asset]**:

1. Ga naar de **[!UICONTROL Workflow]** console.
1. Bewerk op het tabblad **[!UICONTROL Models]** het model **[!UICONTROL DAM Update Asset]**.
1. Wijzig de instellingen van de stap **[!UICONTROL Web enabled rendition]** als volgt:

   `mime:image/gif,mime:image/tiff,tn:140:100,tn:48:48,tn:10:250,cmd:convert ${directory}/${filename} -flip ${directory}/${basename}.flipped.jpg`

1. Sla de workflow op.

Voeg een element toe aan `/content/dam` om de gewijzigde workflow te testen.

1. Haal in het bestandssysteem een TIFF-afbeelding van uw keuze op. Wijzig de naam in `myImage.tiff` en kopieer het naar `/content/dam`, bijvoorbeeld door WebDAV te gebruiken.
1. Ga naar de **[!UICONTROL CQ5 DAM]** console, bijvoorbeeld `http://localhost:4502/libs/wcm/core/content/damadmin.html`.
1. Open het element `myImage.tiff` en controleer of de gespiegelde afbeelding en de drie miniaturen zijn gemaakt.

#### Vorm de CommandLineProcess stap {#configuring-the-commandlineprocess-process-step}

In deze sectie wordt beschreven hoe u **[!UICONTROL Process Arguments]** van `CommandLineProcess` instelt. Scheid de waarden van [!UICONTROL Process Arguments] met een komma en start geen waarde met een spatie.

| Argument-formaat | Beschrijving |
|---|---|
| mime:&lt;mime-type> | Optioneel argument. Het proces wordt toegepast als het element hetzelfde MIME-type heeft als de argumenten. <br>Er kunnen verschillende MIME-typen worden gedefinieerd. |
| tn:&lt;width>:&lt;height> | Optioneel argument. Het proces leidt tot een duimnagel met de afmetingen die in het argument worden bepaald. <br>Er kunnen verschillende miniaturen worden gedefinieerd. |
| cmd: &lt;command> | Definieert de opdracht die wordt uitgevoerd. De syntaxis hangt van het hulpmiddel van de bevellijn af. Er kan slechts één opdracht worden gedefinieerd. <br>De volgende variabelen kunnen worden gebruikt om de opdracht te maken:<br>`${filename}`: naam van het invoerbestand, bijvoorbeeld original.jpg  <br> `${file}`: volledige padnaam van het invoerbestand, bijvoorbeeld /tmp/cqdam0816.tmp/original.jpg  <br> `${directory}`: directory van het invoerbestand, bijvoorbeeld /tmp/cqdam0816.tmp  <br>`${basename}`: naam van het invoerbestand zonder de extensie, bijvoorbeeld origineel  <br>`${extension}`: extensie van het invoerbestand, bijvoorbeeld jpg |

Als ImageMagick bijvoorbeeld is geïnstalleerd op de schijf waarop de Experience Manager-server wordt gehost en u een processtap maakt met **CommandLineProcess** als Implementatie en de volgende waarden als **Procesargumenten**:

`mime:image/gif,mime:image/tiff,tn:140:100,tn:48:48,tn:10:250,cmd:convert ${directory}/${filename} -flip ${directory}/${basename}.flipped.jpg`

Wanneer de workflow vervolgens wordt uitgevoerd, is de stap alleen van toepassing op elementen die `image/gif` of `mime:image/tiff` als mime-type hebben. Het maakt een gespiegelde afbeelding van het origineel, zet deze om in .jpg en maakt drie miniaturen met de afmetingen: 140x100, 48x48 en 10x250.

Gebruik het volgende [!UICONTROL Process Arguments] om de drie standaardduimnagels tot stand te brengen gebruikend ImageMagick:

`mime:image/tiff,mime:image/png,mime:image/bmp,mime:image/gif,mime:image/jpeg,cmd:convert ${filename} -define jpeg:size=319x319 -thumbnail "319x319>" -background transparent -gravity center -extent 319x319 -write png:cq5dam.thumbnail.319.319.png -thumbnail "140x100>" -background transparent -gravity center -extent 140x100 -write cq5dam.thumbnail.140.100.png -thumbnail "48x48>" -background transparent -gravity center -extent 48x48 cq5dam.thumbnail.48.48.png`

Gebruik het volgende [!UICONTROL Process Arguments] om de Web-Toegelaten vertoning tot stand te brengen gebruikend ImageMagick:

`mime:image/tiff,mime:image/png,mime:image/bmp,mime:image/gif,mime:image/jpeg,cmd:convert ${filename} -define jpeg:size=1280x1280 -thumbnail "1280x1280>" cq5dam.web.1280.1280.jpeg`

>[!NOTE]
>
>De stap `CommandLineProcess` is alleen van toepassing op elementen (knooppunten van het type `dam:Asset`) of afstammingen van een element.
