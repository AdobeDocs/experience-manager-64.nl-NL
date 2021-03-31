---
title: Verwante activa
description: Leer hoe u elementen koppelt die bepaalde algemene kenmerken delen. U kunt de eigenschap ook gebruiken om bron/afgeleide verhoudingen tussen activa tot stand te brengen.
contentOwner: AG
feature: Middelenbeheer, Samenwerking
role: Zakelijke praktiserer
translation-type: tm+mt
source-git-commit: 29e3cd92d6c7a4917d7ee2aa8d9963aa16581633
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 0%

---


# Verwante activa {#related-assets}

Met de functie Verwante elementen kunt u elementen handmatig koppelen op basis van de behoeften van uw organisatie (AEM). U kunt bijvoorbeeld een licentiebestand koppelen aan een element of aan een afbeelding/video over een vergelijkbaar onderwerp. U kunt elementen die bepaalde algemene kenmerken delen, aan elkaar koppelen. U kunt de eigenschap ook gebruiken om bron/afgeleide verhoudingen tussen activa tot stand te brengen. Als u bijvoorbeeld een PDF-bestand hebt dat is gegenereerd vanuit een INDD-bestand, kunt u het PDF-bestand koppelen aan het INDD-bronbestand.

Op deze manier hebt u de flexibiliteit om een bestand met een lage resolutie (bijvoorbeeld PDF/JPG) te delen aan leveranciers/agentschappen en het bestand met een hoge resolutie (bijvoorbeeld INDD) alleen op verzoek beschikbaar te maken.

## Relatieve activa {#relating-assets}

1. Open vanuit de interface Middelen de pagina met eigenschappen voor een element dat u wilt koppelen.

   ![chlimage_1-272](assets/chlimage_1-272.png)

   U kunt ook het element selecteren in de lijstweergave.

   ![chlimage_1-273](assets/chlimage_1-273.png)

   U kunt het element ook selecteren in een verzameling.

   ![chlimage_1-274](assets/chlimage_1-274.png)

1. Als u een ander element wilt koppelen aan het element dat u hebt geselecteerd, klikt of tikt u op het pictogram **[!UICONTROL Relate]** op de werkbalk.

   ![chlimage_1-275](assets/chlimage_1-275.png)

1. Voer een van de volgende handelingen uit:

   * Als u het bronbestand voor het element wilt koppelen, selecteert u **[!UICONTROL Source]** in de lijst.
   * Als u een afgeleid bestand wilt koppelen, selecteert u **[!UICONTROL Derived]** in de lijst.
   * Selecteer **[!UICONTROL Others]** in de lijst om een relatie in twee richtingen tussen de elementen te maken.

   ![chlimage_1-276](assets/chlimage_1-276.png)

1. Navigeer in het scherm **[!UICONTROL Select Asset]** naar de locatie van het element dat u wilt koppelen en selecteer het.

   ![chlimage_1-277](assets/chlimage_1-277.png)

1. Klik/tik het **[!UICONTROL Confirm]** pictogram.
1. Klik/tik **[!UICONTROL OK]** om het dialoogvenster te sluiten. Afhankelijk van uw keuze voor relatie in stap 3, wordt het gerelateerde element vermeld onder een geschikte categorie in de sectie **[!UICONTROL Related]**. Als het element dat u hebt verwant bijvoorbeeld het bronbestand voor het huidige element is, wordt het weergegeven onder **[!UICONTROL Source]**.

   ![chlimage_1-278](assets/chlimage_1-278.png)

1. Als u de koppeling tussen een element wilt verbreken, klikt of tikt u op het pictogram **[!UICONTROL Unrelate]** op de werkbalk.

   ![chlimage_1-279](assets/chlimage_1-279.png)

1. Selecteer de elementen die u niet wilt koppelen in het dialoogvenster **[!UICONTROL Remove Relations]** en klik op **[!UICONTROL Unrelate]**.

   ![chlimage_1-280](assets/chlimage_1-280.png)

1. Klik/Tik **[!UICONTROL OK]** om het dialoogvenster te sluiten. De elementen waarvoor u relaties hebt verwijderd, worden verwijderd uit de lijst met verwante elementen onder de sectie **[!UICONTROL Related]**.

## Verwante activa {#translating-related-assets} vertalen

Het maken van bron-/afgeleide relaties tussen elementen met de functie Verwante elementen is ook handig in vertaalworkflows. Wanneer u een vertaalworkflow uitvoert op een afgeleid element, haalt AEM Assets automatisch alle elementen op waarnaar het bronbestand verwijst en die het bevat voor vertaling. Op deze manier wordt het element waarnaar door het bronelement wordt verwezen, samen met de bron en afgeleide elementen omgezet. Neem bijvoorbeeld een scenario waarin uw Engelse taalkopie een afgeleid element en het bronbestand van dat element bevat, zoals wordt weergegeven.

![chlimage_1-281](assets/chlimage_1-281.png)

Als het bronbestand is gerelateerd aan een ander element, haalt AEM Assets het element waarnaar wordt verwezen op en neemt het dit op voor vertaling.

![chlimage_1-282](assets/chlimage_1-282.png)

1. Vertaal de elementen in de bronmap naar een doeltaal door de stappen in [Een nieuw vertaalproject maken](translation-projects.md#create-a-new-translation-project) te volgen. In dit geval vertaalt u uw middelen bijvoorbeeld naar het Frans.
1. Open vanuit de pagina Projecten de vertaalmap.

   ![chlimage_1-283](assets/chlimage_1-283.png)

1. Klik/Tik de projecttegel om de detailspagina te openen.

   ![chlimage_1-284](assets/chlimage_1-284.png)

1. Klik op of tik op de ovalen onder de Vertaaltaak-kaart om de status van de vertaling weer te geven.

   ![chlimage_1-285](assets/chlimage_1-285.png)

1. Selecteer het element en klik/tik **[!UICONTROL Reveal in Assets]** op de werkbalk om de vertaalstatus voor het element weer te geven.

   ![chlimage_1-286](assets/chlimage_1-286.png)

1. Klik op het bronelement of tik erop om te controleren of de aan de bron gerelateerde elementen zijn omgezet.

   ![chlimage_1-287](assets/chlimage_1-287.png)

1. Selecteer het element dat betrekking heeft op de bron en klik op **[!UICONTROL Reveal in Assets]**. Het vertaalde gerelateerde element wordt weergegeven.

   ![chlimage_1-288](assets/chlimage_1-288.png)
