---
title: Werken met Adobe Dimension-middelen
description: Werken met Adobe Dimension-elementen in AEM 3D.
contentOwner: Rick Brough
topic-tags: 3D
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
content-type: reference
translation-type: tm+mt
source-git-commit: 6be46f6986d1631f711cfd4464cc4f2d17014681
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 0%

---


# Werken met Adobe Dimension-elementen {#working-with-adobe-dimension-assets}

>[!IMPORTANT]
>
>Het AEM 3D-functiepakket in AEM 6.4 wordt niet meer ondersteund. Adobe raadt u aan de functie 3D-elementen in [AEM te gebruiken als een Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/assets-3d.html#dynamicmedia) of [AEM 6.5.3 of hoger.](https://experienceleague.adobe.com/docs/experience-manager-65/assets/dynamic/assets-3d.html#dynamic) wanneer u werkt met Adobe Dimension-middelen.

Het AEM 3D-functiepakket biedt ondersteuning voor Adobe Dimension-elementen (`.dn` bestanden) in AEM Assets, AEM Sites en AEM Screens.

Een nieuwe 3D-viewer die is gebaseerd op de open glTF-standaard biedt mogelijkheden voor voorvertoning en weergave op sites voor Adobe Dimension-middelen.

## Informatie over de conversieservice {#about-the-cloud-based-conversion-service} in de cloud

Wanneer een Dimension-element wordt geüpload naar AEM, wordt een kopie van het bestand doorgestuurd naar een door de Adobe beheerde cloudservice die wordt gehost in Amazon AWS. Deze service converteert van de bestandsindeling Adobe-eigen Dimension naar de open standaard glTF-indeling. Het omgezette 3D model wordt verpakt als binaire glTF (`.glb`). AEM slaat het omgezette model met het primaire Dimension-element op als een uitvoering.

U kunt het `.glb` omzettingsformaat vormen gebruikend één van twee manieren (zie [Installeren en het vormen AEM 3D](install-config-3d.md) voor instructies):

* Neem Adobe-specifieke extensies op om de visuele kwaliteit te maximaliseren wanneer u de Adobe glTF-viewer gebruikt om Dimension-elementen in AEM Assets, AEM Sites of AEM Screens weer te geven. Hierdoor zijn de `.glb`-uitvoeringen niet compatibel met de meeste toepassingen van derden.
* Sluit Adobe-specifieke uitbreidingen uit om verenigbaarheid van de `.glb` vertoning met derdetoepassingen te bereiken. Dit beperkt de visuele kwaliteit bij weergave in AEM Assets, AEM Sites of AEM Screens (bijvoorbeeld geen IBL-belichting) om de kwaliteit van gangbare toepassingen van derden te simuleren.

De overdracht van de Dimension/glTF-bestanden van of naar Amazon AWS en de tijdelijke opslag ervan in AWS zijn volledig beveiligd. Deze bestanden blijven minimaal in Amazon AWS aanwezig; doorgaans niet meer dan een paar minuten bij normale bewerkingen.

Als u ondersteuning voor Dimension-elementen wilt inschakelen, moet u aanmeldingsgegevens van Adobe verkrijgen voor toegang tot de conversieservice. Zie [AEM 3D](install-config-3d.md) installeren en configureren.

>[!NOTE]
>
>Als u de geleverde gegevens installeert en gebruikt, begrijpt en gaat u ermee akkoord dat uw Adobe Dimension 3D-middelen worden overgebracht naar (en verwerkt door) de door de Adobe beheerde, cloud gebaseerde conversieservice die wordt gehost in Amazon AWS.

### Weergeven op AEM Assets {#viewing-on-aem-assets}

Het AEM 3D-functiepakket bevat een nieuwe viewer op basis van de open glTF-standaard die wordt gebruikt om Adobe Dimension-elementen weer te geven. Deze viewer wordt automatisch geselecteerd wanneer u een Dimension-bestand of een gecomprimeerde glTF opent in de Gedetailleerde weergave in AEM Assets of met de 3D-component in AEM Sites.

De gebruikersinterface van de glTF-viewer wijkt enigszins af van de standaard 3D-viewer die wordt gebruikt voor alle andere 3D-elementtypen.

#### Zie ook het volgende: {#see-also-the-following}

* [AEM 3D-releaseopmerkingen ](/help/release-notes/aem3d-release-notes.md) voor beperkingen en beperkingen die van toepassing zijn op Dn-elementen en de glTF-viewer.
* [Werken met de component 3D-sites ](using-the-3d-sites-component.md) voor componenteigenschappen die specifiek zijn voor Adobe Dimension-elementen.
* [Installeren en configureren AEM 3](install-config-3d.md) DH om de op cloud gebaseerde conversieservice te configureren.

