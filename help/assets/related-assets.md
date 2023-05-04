---
title: Verwante activa
description: Leer hoe u elementen koppelt die bepaalde algemene kenmerken delen. U kunt de eigenschap ook gebruiken om bron/afgeleide verhoudingen tussen activa tot stand te brengen.
contentOwner: AG
feature: Asset Management,Collaboration
role: User
exl-id: d19544c4-c8e7-4a39-9c86-15a46dca848e
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 0%

---

# Verwante activa {#related-assets}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Met de functie Verwante elementen kunt u elementen handmatig koppelen op basis van de behoeften van uw organisatie. U kunt bijvoorbeeld een licentiebestand koppelen aan een element of aan een afbeelding/video over een vergelijkbaar onderwerp. U kunt elementen die bepaalde algemene kenmerken delen, aan elkaar koppelen. U kunt de eigenschap ook gebruiken om bron/afgeleide verhoudingen tussen activa tot stand te brengen. Als u bijvoorbeeld een PDF-bestand hebt dat is gegenereerd vanuit een INDD-bestand, kunt u het PDF-bestand koppelen aan het INDD-bronbestand.

Op deze manier kunt u een bestand met een lage resolutie (bijvoorbeeld PDF/JPG) delen met leveranciers/bureaus en het bestand met een hoge resolutie (bijvoorbeeld INDD) alleen op verzoek beschikbaar stellen.

## Relatieve activa {#relating-assets}

1. Open vanuit de interface Middelen de pagina met eigenschappen voor een element dat u wilt koppelen.

   ![chlimage_1-272](assets/chlimage_1-272.png)

   U kunt ook het element selecteren in de lijstweergave.

   ![chlimage_1-273](assets/chlimage_1-273.png)

   U kunt het element ook selecteren in een verzameling.

   ![chlimage_1-274](assets/chlimage_1-274.png)

1. Als u een ander element wilt koppelen aan het geselecteerde element, klikt of tikt u op het **[!UICONTROL Relate]** op de werkbalk.

   ![chlimage_1-275](assets/chlimage_1-275.png)

1. Voer een van de volgende handelingen uit:

   * Selecteer **[!UICONTROL Source]** in de lijst.
   * Selecteer **[!UICONTROL Derived]** in de lijst.
   * Selecteer **[!UICONTROL Others]** in de lijst.

   ![chlimage_1-276](assets/chlimage_1-276.png)

1. Van de **[!UICONTROL Select Asset]** , navigeert u naar de locatie van het element dat u wilt koppelen en selecteert u het.

   ![chlimage_1-277](assets/chlimage_1-277.png)

1. Klik/tik op de knop **[!UICONTROL Confirm]** pictogram.
1. Klikken/tikken **[!UICONTROL OK]** om het dialoogvenster te sluiten. Afhankelijk van uw keuze voor relatie in stap 3 wordt het gerelateerde actief vermeld onder een geschikte categorie in de categorie **[!UICONTROL Related]** sectie. Als het element dat u hebt verwant bijvoorbeeld het bronbestand voor het huidige element is, wordt het onder **[!UICONTROL Source]**.

   ![chlimage_1-278](assets/chlimage_1-278.png)

1. Als u de koppeling met een element wilt verbreken, klikt of tikt u op het **[!UICONTROL Unrelate]** op de werkbalk.

   ![chlimage_1-279](assets/chlimage_1-279.png)

1. Selecteer de elementen die u niet wilt koppelen van het dialoogvenster **[!UICONTROL Remove Relations]** en klikken/tikken **[!UICONTROL Unrelate]**.

   ![chlimage_1-280](assets/chlimage_1-280.png)

1. Klikken/tikken **[!UICONTROL OK]** om het dialoogvenster te sluiten. De activa waarvoor u betrekkingen schrapte worden geschrapt van de lijst van verwante activa onder **[!UICONTROL Related]** sectie.

## Verwante elementen vertalen {#translating-related-assets}

Het maken van bron-/afgeleide relaties tussen elementen met de functie Verwante elementen is ook handig in vertaalworkflows. Wanneer u een vertaalworkflow uitvoert op een afgeleid middel, [!DNL Experience Manager] Elementen halen automatisch elementen op waarnaar het bronbestand verwijst en nemen deze voor vertaling op. Op deze manier wordt het element waarnaar door het bronelement wordt verwezen, samen met de bron en afgeleide elementen omgezet. Neem bijvoorbeeld een scenario waarin uw Engelse taalkopie een afgeleid element en het bronbestand van dat element bevat, zoals wordt weergegeven.

![chlimage_1-281](assets/chlimage_1-281.png)

Als het bronbestand verwant is aan een ander element, [!DNL Experience Manager] Elementen halen het element waarnaar wordt verwezen en nemen dit op voor vertaling.

![chlimage_1-282](assets/chlimage_1-282.png)

1. Vertaal de elementen in de bronmap naar een doeltaal door de stappen in [Een nieuw vertaalproject maken](translation-projects.md#create-a-new-translation-project). In dit geval vertaalt u uw middelen bijvoorbeeld naar het Frans.
1. Open vanuit de pagina Projecten de vertaalmap.

   ![chlimage_1-283](assets/chlimage_1-283.png)

1. Klik/Tik de projecttegel om de detailspagina te openen.

   ![chlimage_1-284](assets/chlimage_1-284.png)

1. Klik op of tik op de ovalen onder de Vertaaltaak-kaart om de status van de vertaling weer te geven.

   ![chlimage_1-285](assets/chlimage_1-285.png)

1. Selecteer het element en klik/tik op **[!UICONTROL Reveal in Assets]** op de werkbalk om de vertaalstatus voor het element weer te geven.

   ![chlimage_1-286](assets/chlimage_1-286.png)

1. Klik op het bronelement of tik erop om te controleren of de aan de bron gerelateerde elementen zijn omgezet.

   ![chlimage_1-287](assets/chlimage_1-287.png)

1. Selecteer het element dat betrekking heeft op de bron en klik/tik op **[!UICONTROL Reveal in Assets]**. Het vertaalde gerelateerde element wordt weergegeven.

   ![chlimage_1-288](assets/chlimage_1-288.png)
