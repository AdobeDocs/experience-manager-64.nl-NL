---
title: Creeer en wijs Middelen toe Enablement
seo-title: Create and Assign Enablement Resources
description: Bronnen voor inschakelen toevoegen
seo-description: Add enablement resources
uuid: da940242-0c9b-4ad8-8880-61fd41461c3b
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: introduction
content-type: reference
discoiquuid: 8fe97181-600e-42ac-af25-d5d4db248740
exl-id: 9f447a54-4512-41ab-b8d3-327e751eda58
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '684'
ht-degree: 1%

---

# Creeer en wijs Middelen toe Enablement {#create-and-assign-enablement-resources}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Een Enablement Resource toevoegen {#add-an-enablement-resource}

Om een enablement middel aan de nieuwe communautaire plaats toe te voegen:

* Instantie van auteur
   * Bijvoorbeeld: [http://localhost:4502/](http://localhost:4503/)
* Aanmelden als systeembeheerder
* Selecteer bij globale navigatie de optie **Gemeenschappen > [Bronnen](resources.md)**

   ![chlimage_1-199](assets/chlimage_1-199.png)
   ![chlimage_1-200](assets/chlimage_1-200.png)
* Selecteer de communitysite waaraan de activeringsbronnen worden toegevoegd
   * Selecteer `Enablement Tutorial`
* Selecteer in het menu ` Create`
* Selecteer **[!UICONTROL Resource]**

![chlimage_1-201](assets/chlimage_1-201.png)

### Basisinformatie {#basic-info}

Vul de basisinformatie voor de Middel in:

* **[!UICONTROL Site Name]**: ingesteld op de naam van de geselecteerde communitysite: Zelfstudie inschakelen
* **[!UICONTROL Resource Name&ast;]**: Skiles 1
* **[!UICONTROL Tags]**: Zelfstudie: Sport/Skieten
* **[!UICONTROL Show in Catalog]**: Aan
* **[!UICONTROL Description]**: Sneeuw schuiven voor beginners
* **[!UICONTROL Add Image]**: Voeg een beeld toe om het Middel aan het lid in hun mening van Toewijzingen te vertegenwoordigen
   ![chlimage_1-202](assets/chlimage_1-202.png)
* Selecteer **[!UICONTROL Next]**

### Inhoud toevoegen {#add-content}

Terwijl het lijkt alsof de veelvoudige Middelen zouden kunnen worden geselecteerd, wordt slechts één toegestaan.

Selecteer `'+' icon`, in de rechterbovenhoek, om het proces te beginnen om het Middel te kiezen door de bron te identificeren.

![chlimage_1-203](assets/chlimage_1-203.png) ![chlimage_1-204](assets/chlimage_1-204.png)

Upload een resource. Als een videobron een aangepaste afbeelding uploadt om weer te geven voordat de video wordt afgespeeld, of als een miniatuur wordt gegenereerd van de video (kan een paar minuten duren - het is niet nodig om te wachten).

![chlimage_1-205](assets/chlimage_1-205.png)

* selecteren **[!UICONTROL Next]**

### Instellingen {#settings}

* **[!UICONTROL Social Settings]**
Laat de standaardinstellingen ongewijzigd om het maken van opmerkingen en het beoordelen van activeringsbronnen door studenten te ervaren.
* **[!UICONTROL Due Date]**

   *(Optioneel)* Een datum waarop de toewijzing moet zijn voltooid, kan worden geselecteerd.
* **[!UICONTROL Resource Author]**

   *(Optioneel)* Leeg laten.
* **[!UICONTROL Resource Contact&ast;]**

   *(Vereist)* Gebruik het keuzemenu om lid te selecteren `Quinn Harper`.
* **[!UICONTROL Resource Expert]**

   *(Optioneel)* Leeg laten.
   **Opmerking**: als gebruikers of groepen niet zichtbaar zijn, controleert u of zij aan `Community Enable Members` groep en *Opgeslagen* op het publicatieexemplaar.
   ![chlimage_1-206](assets/chlimage_1-206.png)
* Selecteer **[!UICONTROL Next]**

### Toewijzingen {#assignments}

* **[!UICONTROL Add Assignees]**
Laat de set ongedaan omdat deze activeringsbron wordt toegevoegd aan een leerpad. Als een leerling aan het individuele enablement middel evenals een learningpPath wordt toegewezen die het enablement middel bevat, zal de leerling tweemaal aan het enablement middel worden toegewezen.

![chlimage_1-207](assets/chlimage_1-207.png)

* Selecteer **[!UICONTROL Create]**

![chlimage_1-208](assets/chlimage_1-208.png)

Succesvolle verwezenlijking van het Middel keert aan de console van Middelen met het pas gecreëerde Middel geselecteerd terug. Vanuit deze console is het mogelijk studenten te publiceren, toe te voegen en andere instellingen te wijzigen.

Om een nieuwe versie van het enablement middel te uploaden, wordt het geadviseerd om een nieuw Middel tot stand te brengen, en dan leden van de oude versie uit te schrijven en hen in de nieuwe versie in te schrijven.

### De bron publiceren {#publish-the-resource}

Voordat ingeschreven personen de toegewezen cursus kunnen zien, moet deze worden gepubliceerd:

* Selecteer de wereld `Publish`pictogram

Activering wordt bevestigd met een succesbericht:

![chlimage_1-209](assets/chlimage_1-209.png)

## Een tweede Enablement Resource toevoegen {#add-a-second-enablement-resource}

Herhaal de bovenstaande stappen om een tweede gerelateerde enablement-resource te maken en te publiceren waaruit een leerpad wordt gemaakt.

![chlimage_1-210](assets/chlimage_1-210.png)

**Publiceren** de tweede resource.

Keer terug naar de lijst van de Leergids van Enablement van de Middelen van het.

*Tip: als beide Bronnen niet zichtbaar zijn, vernieuwt u de pagina.*

![chlimage_1-211](assets/chlimage_1-211.png)

## Een leerpad toevoegen {#add-a-learning-path}

Een leerpad is een logische groepering van bronnen voor activering die een cursus vormen.

* Van de console van Middelen, selecteer `+ Create`
* Selecteer **[!UICONTROL Learning Path]**

![chlimage_1-212](assets/chlimage_1-212.png)

Voeg de **[!UICONTROL Basic Info]**:

* **[!UICONTROL Learning Path Name]**: Ski Lessen
* **[!UICONTROL Tags]**: Zelfstudie: Skieten
* **[!UICONTROL Show in Catalog]**: ongecontroleerd laten
* **[!UICONTROL Upload an image]** om de het leren weg in de console van Middelen te vertegenwoordigen

![chlimage_1-213](assets/chlimage_1-213.png)

* Selecteer **[!UICONTROL Next]**

Sla het volgende deelvenster over omdat er geen in de eerste plaats leerpaden zijn die u wilt toevoegen.

* Selecteer **[!UICONTROL Next]**

In het deelvenster Bronnen toevoegen

* Selecteren `+ Add Resources` om de 2 ski lessies middelen te selecteren om aan de het leren weg toe te voegen

   Opmerking: Alleen **gepubliceerd** Bronnen kunnen worden geselecteerd.

>[!NOTE]
>
>U kunt alleen de bronnen selecteren die beschikbaar zijn op hetzelfde niveau als het leerpad. Bijvoorbeeld, voor een leerweg die in een groep wordt gecreeerd slechts zijn de middelen van het groepsniveau beschikbaar; voor een leerpad dat in een gemeenschapssite is gemaakt, zijn de bronnen in die site beschikbaar voor toevoeging aan het leerpad.

* Selecteer **[!UICONTROL Submit]**.

![chlimage_1-214](assets/chlimage_1-214.png) ![chlimage_1-215](assets/chlimage_1-215.png)

* Selecteer **[!UICONTROL Next]**

![chlimage_1-216](assets/chlimage_1-216.png)

* **[!UICONTROL Add Assignees]**
Gebruik het keuzemenu om het 
`Community Ski Class` groep, waarvan de leden deel moeten uitmaken `Riley Taylor` en `Sidney Croft.`

* **[!UICONTROL Learning Path Contact&ast;]**

   *(Vereist)* Gebruik het keuzemenu om lid te selecteren `Quinn Harper`.

* Selecteer **[!UICONTROL Create]**

![chlimage_1-217](assets/chlimage_1-217.png)

De succesvolle verwezenlijking van de het leren weg keert aan de console van Middelen met de pas gecreëerde het leren weg geselecteerd terug. Vanuit deze console is het mogelijk studenten te publiceren, toe te voegen en andere instellingen te wijzigen.

**Publiceren** het leerpad.
