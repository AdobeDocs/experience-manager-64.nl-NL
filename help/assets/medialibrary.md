---
title: Vergelijk de functies die beschikbaar zijn in AEM Assets en AEM Media Library
description: Veelgestelde vragen over AEM Assets en AEM Media Library, inclusief de verschillen.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 6a1013715c538c39eaf40a22dbffc7f2df36f968
workflow-type: tm+mt
source-wordcount: '551'
ht-degree: 0%

---


# AEM Assets vs. AEM MediaLibrary {#aem-assets-vs-aem-medialibrary}

Adobe Experience Manager (AEM) Activa maken integrerend deel uit van het AEM. Deze soepele integratie wordt gezien als een groot voordeel van AEM en zorgt voor consistentie in inhoudsbeheer en hoge productiviteit voor auteurs van inhoud.

## Veelgestelde vragen {#frequently-asked-questions}

### Wat is AEM Assets? {#what-is-aem-assets}

AEM Assets is een toepassing op het AEM-Platform waarmee onze klanten hun digitale middelen (afbeeldingen, video&#39;s, documenten en audioclips) kunnen beheren in een opslagplaats op internet. AEM Assets biedt ondersteuning voor metagegevens, uitvoeringen, de Digital Asset Management Finder en de beheerinterface van AEM Assets.

### Wat is de AEM-mediabibliotheek? {#what-is-the-aem-media-library}

De AEM Mediabibliotheek is een aangewezen onderdeel van de AEM WCM-inhoudsopslagruimte waar afbeeldingen en andere gedeelde bronnen worden opgeslagen. De mediabibliotheek gebruikt de Digital Asset Management-mogelijkheden van AEM WCM.

### Wat krijg ik van AEM Assets dat geen deel uitmaakt van AEM WCM? {#what-do-i-get-from-aem-assets-that-is-not-part-of-aem-wcm}

De unieke functies die alleen beschikbaar zijn voor klanten van AEM Assets zijn:

1. de mogelijkheid om andere metagegevens dan titel, tags en beschrijving te extraheren en te bewerken.
1. de AEM Assets Admin, beschikbaar bij het welkomstscherm door de tweede knoop naast `siteadmin` te klikken.
1. Alle workflowstappen met betrekking tot Digital Asset Management, namelijk het opnemen van AEM middelen, het verwijderen van AEM Assets, het afhandelen van AEM Assets-submiddelen, het extraheren van AEM Assets-metagegevens.
1. bibliotheken, inclusief `dam` im-pakketruimte.

Voor het gebruik van deze functies is een geldige AEM Assets-licentie vereist.

### Is AEM Assets beschikbaar als apart pakket? {#is-aem-assets-available-as-a-separate-package}

Nee. Om de installatie en implementatie te vereenvoudigen, worden alle AEM toepassingen en invoegtoepassingen geleverd in één pakket met alle functionaliteit inbegrepen. Dit betekent niet dat u toestemming hebt om alle functies in het pakket te gebruiken.

#### Ik wil metagegevens van digitale elementen bewerken. Heb ik AEM Assets nodig? {#i-want-to-edit-metadata-of-digital-assets-do-i-need-aem-assets}

Als u andere metagegevens dan titel, beschrijving en tags wilt bewerken, is een licentie voor AEM Assets vereist.

#### Ik wil afbeeldingen automatisch vergroten of verkleinen tijdens het importeren. Heb ik AEM Assets nodig? {#i-want-to-automatically-resize-images-upon-import-do-i-need-aem-assets}

Nee. Het wijzigen van het formaat en de automatische workflowgestuurde transformatie van statische afbeeldingen en de mogelijkheid om uitvoeringen te beheren maken deel uit van AEM Mediabibliotheek. Voor deze functies is geen AEM Assets-licentie vereist.

### Ik wil afbeeldingen vergroten of verkleinen met een aangepaste afbeeldingscomponent. Heb ik AEM Assets nodig? {#i-want-to-resize-images-using-a-customized-image-component-do-i-need-aem-assets}

De afbeeldingscomponent maakt deel uit van AEM WCM. De grafische bibliotheek die door de afbeeldingscomponent (maar ook door AEM Assets) wordt gebruikt, maakt deel uit van het AEM platform en heeft geen AEM Assets-licentie nodig.

### Hoe kan ik voorkomen dat mijn gebruikers AEM Assets gebruiken als ik geen licentie voor AEM Assets heb verleend? {#how-can-i-prevent-my-users-from-using-aem-assets-if-i-did-not-license-aem-assets}

U kunt alle AEM Assets-specifieke workflows, componenten, taxonomieën, opties en de AEM Assets-beheerder uit AEM verwijderen. Zo voorkomt u dat gebruikers per ongeluk AEM Assets-functies gebruiken waarvoor u geen licentie hebt verleend.

### Ik wil afbeeldingen aan een pagina toevoegen en deze afbeeldingen uitsnijden en vergroten of verkleinen. Heb ik AEM Assets nodig? {#i-want-to-add-images-to-a-page-and-want-to-crop-and-resize-these-images-do-i-need-aem-assets}

In dit geval is het niet verplicht om AEM Assets te kopen, zelfs als de mediabibliotheek niet hoeft te worden gebruikt om afbeeldingen op een website te gebruiken, omdat de component smart image het uploaden van afbeeldingen naar de pagina toestaat.

>[!MORELIKETHIS]
>
>* [Gedetailleerde lijst met functieverschillen](https://docs.adobe.com/content/help/en/experience-manager-65/assets/administer/medialibrary.html#listoffeatures)

