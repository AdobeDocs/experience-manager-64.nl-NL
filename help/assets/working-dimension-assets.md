---
title: Werken met Adobe Dimension-middelen
seo-title: Werken met Adobe Dimension-middelen
description: Werken met Adobe Dimension-elementen in AEM 3D.
seo-description: Werken met Adobe Dimension-elementen in AEM 3D.
uuid: 476e6758-b3a1-42ba-a18d-bfc407c6a72e
contentOwner: Rick Brough
topic-tags: 3D
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
content-type: reference
discoiquuid: 4a601c2a-4ea1-4308-8ae8-704155f63c21
translation-type: tm+mt
source-git-commit: 5acb16b1734331767554261bbcf9640947f2e23f

---


# Werken met Adobe Dimension-middelen {#working-with-adobe-dimension-assets}

Het AEM 3D-functiepakket biedt ondersteuning voor Adobe Dimension-elementen (`.dn` bestanden) in AEM-middelen, AEM-sites en AEM-schermen.

Een nieuwe 3D-viewer die is gebaseerd op de open glTF-standaard biedt voorvertoningen en Sites en Schermen weergavemogelijkheden voor Adobe Dimension-elementen.

## Informatie over de conversieservice in de cloud {#about-the-cloud-based-conversion-service}

Wanneer een Dimension-element wordt geüpload naar AEM, wordt een kopie van het bestand doorgestuurd naar een door Adobe beheerde cloudservice die wordt gehost in Amazon AWS. Deze service converteert van de eigen Dimension-bestandsindeling van Adobe naar de open standaard glTF-indeling. Het omgezette 3D-model wordt verpakt als binaire glTF (`.glb`). AEM slaat het geconverteerde model met het primaire Dimension-element op als een uitvoering.

U kunt de `.glb` conversie-indeling op twee manieren configureren (zie AEM 3D [](install-config-3d.md) installeren en configureren voor instructies):

* Neem Adobe-specifieke extensies op om de visuele kwaliteit te maximaliseren wanneer u de Adobe glTF-viewer gebruikt om Dimension-elementen weer te geven in AEM-middelen, AEM-sites of AEM-schermen. Hierdoor zijn de `.glb` uitvoeringen niet compatibel met de meeste toepassingen van derden.
* Sluit Adobe-specifieke extensies uit om de `.glb` vertoning compatibel te maken met toepassingen van derden. Dit beperkt de visuele kwaliteit bij weergave in AEM-middelen, AEM-sites of AEM-schermen (bijvoorbeeld geen IBL-verlichting) om de kwaliteit van gangbare toepassingen van derden te simuleren.

De overdracht van de Dimension/glTF-bestanden van of naar Amazon AWS en de tijdelijke opslag ervan in AWS zijn volledig beveiligd. Deze bestanden blijven minimaal in Amazon AWS aanwezig; doorgaans niet meer dan een paar minuten bij normale bewerkingen.

Als u ondersteuning voor Dimension-elementen wilt inschakelen, moet u aanmeldingsgegevens van Adobe opvragen voor toegang tot de conversieservice. Zie AEM 3D [installeren en configureren](install-config-3d.md).

>[!NOTE]
>
>Als u de geleverde gegevens installeert en gebruikt, begrijpt en gaat u ermee akkoord dat uw Adobe Dimension 3D-middelen worden overgebracht naar (en verwerkt door) de door Adobe beheerde, cloudgebaseerde conversieservice die wordt gehost in Amazon AWS.

### Weergeven op AEM-elementen {#viewing-on-aem-assets}

Het AEM 3D-functiepakket bevat een nieuwe viewer op basis van de open glTF-standaard die wordt gebruikt om Adobe Dimension-elementen weer te geven. Deze viewer wordt automatisch geselecteerd wanneer u een Dimension-bestand of een gecomprimeerde glTF opent in de Gedetailleerde weergave in AEM Assets of met de 3D-component in AEM Sites.

De gebruikersinterface van de glTF-viewer wijkt enigszins af van de standaard 3D-viewer die wordt gebruikt voor alle andere 3D-elementtypen.

#### Zie ook het volgende: {#see-also-the-following}

* [Opmerkingen bij](/help/release-notes/aem3d-release-notes.md) de release AEM 3D voor beperkingen en beperkingen die van toepassing zijn op Dn-elementen en de glTF-viewer.
* [Werken met de component](using-the-3d-sites-component.md) 3D-sites voor componenteigenschappen die specifiek zijn voor Adobe Dimension-elementen.
* [AEM 3D](install-config-3d.md) installeren en configureren om de op cloud gebaseerde conversieservice te configureren.

