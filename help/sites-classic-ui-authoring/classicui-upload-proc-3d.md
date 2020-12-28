---
title: Informatie over het uploaden en verwerken van 3D-elementen in AEM
seo-title: Informatie over het uploaden en verwerken van 3D-elementen in AEM
description: Adobe raadt u aan alle bestanden waarnaar wordt verwezen, te uploaden voordat of tegelijkertijd het primaire 3D-modelbestand wordt geüpload. Wanneer het uploaden is voltooid, worden uw 3D-bestanden geconverteerd en wordt extra verwerking toegepast om het element voor te bereiden op weergave en rendering.
seo-description: Adobe raadt u aan alle bestanden waarnaar wordt verwezen, te uploaden voordat of tegelijkertijd het primaire 3D-modelbestand wordt geüpload. Wanneer het uploaden is voltooid, worden uw 3D-bestanden geconverteerd en wordt extra verwerking toegepast om het element voor te bereiden op weergave en rendering.
uuid: 82ccfbf8-1f82-4960-b9e5-3ce65c16435a
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: authoring
content-type: reference
discoiquuid: 0be4a856-951b-4cb6-8103-8004052c63a0
translation-type: tm+mt
source-git-commit: e0ce860380a28a9dcaa6f8ce94ad278cdbe49fad
workflow-type: tm+mt
source-wordcount: '804'
ht-degree: 1%

---


# Informatie over het uploaden en verwerken van 3D-elementen in AEM{#about-the-uploading-and-processing-of-d-assets-in-aem}

Gebruik standaard upload- of synchronisatiemechanismen om 3D-elementen en de bijbehorende bestanden waarnaar wordt verwezen, over te brengen naar AEM Assets.

Zie [Elementen uploaden](/help/assets/managing-assets-touch-ui.md#uploading-assets).

Adobe raadt u aan alle bestanden waarnaar wordt verwezen, te uploaden voordat of tegelijkertijd het primaire 3D-modelbestand wordt geüpload. Dit is echter geen vereiste.

Wanneer het uploaden is voltooid, worden uw 3D-bestanden geconverteerd en wordt extra verwerking toegepast om het element voor te bereiden op weergave en rendering.

## Aanbevolen procedures voor het uploaden van 3D-elementen {#best-practices-for-uploading-d-assets}

* Over het algemeen gelden er geen beperkingen voor het uploaden van 3D-inhoud in de AEM Assets-maphiërarchie. AEM de geautomatiseerde oplossing van bestandsafhankelijkheden in 3D heeft echter bereikbeperkingen om te bepalen hoe lang het duurt om grote opslagplaatsen voor bedrijfsmiddelen te doorzoeken. Daarom raadt Adobe aan dat wanneer u 3D-elementen en hun bestandsafhankelijke bestanden uploadt, u dit doet binnen een redelijke afstand van elk bestand (algemene map op de achtergrond). Nadat de bestandsafhankelijkheden zijn opgelost, kunt u zowel het 3D-element als de afhankelijke elementen overal in de opslagplaats verplaatsen zonder de bestaande relaties te verliezen.
* Adobe raadt u aan een consistente mapstructuur voor 3D-inhoud *te kiezen voordat *u de inhoud uploadt. De volgende tips zijn enkele aanbevolen benaderingen die u kunt kiezen:

   * **Een aparte map bijhouden voor elk 3D-element dat u uploadt**.

      De map bevat zowel het primaire 3D-modelbestand als alle afhankelijke bestanden. Hoewel het eenvoudig is om alle middelen en afhankelijke personen in één map te plaatsen, is het lastig om naar inhoud te bladeren. Het maakt ook het delen van afhankelijke elementen (structuurafbeeldingen) tussen modellen ingewikkelder.

   * **Bewaar de modellen in één map en de afhankelijke personen in een secundaire of submap**.

      Deze aanpak ondersteunt gemakkelijk het delen van afhankelijkheden tussen modellen. Het kan echter moeilijk worden om specifieke afhankelijke personen te vinden als het aantal activa groot is.

   * **Afzonderlijke, parallelle maphiërarchieën voor modellen en afhankelijkheden**.

      U kunt deze aanpak modelleren voor 3D-ontwerptoepassingen zoals Autodesk Maya, die inhoud liever opslaan.

* Afhankelijke elementen mogen alleen worden verwijderd als de bijbehorende 3D-elementen of elementen waarnaar ze verwijzen, ook worden verwijderd. U kunt 3D-elementen echter wel vrij verwijderen zonder dat u de afhankelijke elementen hoeft te verwijderen. Als een gebiedsdeel per ongeluk wordt verloren, kunt u het gebiedsdeel gemakkelijk oplossen om het te herstellen.

   Zie [Bestandsafhankelijkheden oplossen](/help/assets/resolve-file-dependencies.md).

## Prestatieaspecten bij het uploaden van 3D-bestanden {#performance-considerations-when-uploading-d-files}

Het omzetten en verwerken van 3D-bestanden verbruikt doorgaans aanzienlijke CPU- en geheugenbronnen op een server. Het kost ook veel tijd. De verwerkingstijden variëren vaak sterk afhankelijk van de grootte van het model en de mogelijkheden van de server. Een typisch klein model met minder dan 100 k vlakken is bijvoorbeeld meestal klaar om in minder dan één minuut te worden bekeken; het wordt volledig verwerkt in 2-3 minuten. Terwijl een groot model met meer dan een miljoen gezichten tientallen minuten kan duren om volledig te verwerken.

Conversie-, verwerkings- en rendertaken worden zo nodig in een wachtrij geplaatst om te voorkomen dat de server te veel wordt vertraagd. Het bericht &quot;Wachten op verwerking...&quot; wordt soms weergegeven in de **[!UICONTROL Card View]** op het moment dat u elementen uploadt. Deze status geeft aan dat andere verwerkings- of rendertaken moeten zijn voltooid voordat het huidige element wordt verwerkt.

## De verwerkingsstatus van uw geüploade 3D-bestanden {#monitoring-the-processing-status-of-your-uploaded-d-files} controleren

Alleen in **[!UICONTROL Card View]** worden de verwerkingsstatus en progressie als een voortgangsbanner weergegeven op de kaart van het element. Elk geüpload 3D-model ondergaat doorgaans de volgende 4-6 geordende verwerkingsstadia:

<table> 
 <tbody> 
  <tr> 
   <td><strong>Verwerkingsfase</strong><br /> </td> 
   <td><strong>Namen verwerken</strong></td> 
   <td><strong>Beschrijving</strong></td> 
  </tr> 
  <tr> 
   <td>1</td> 
   <td>Verwerking</td> 
   <td>Basis eerste verwerking en extractie van metagegevens.</td> 
  </tr> 
  <tr> 
   <td>2</td> 
   <td>Converteren, indeling</td> 
   <td>Het 3D-model wordt omgezet van een native indeling (Autodesk® Maya® of Autodesk® 3ds Max®) naar een intermediaire indeling (FBX).</td> 
  </tr> 
  <tr> 
   <td>3</td> 
   <td>Voorvertoning maken</td> 
   <td>Het FBX- of OBJ-bestand wordt opgenomen en verwerkt. Bestandsafhankelijkheden worden waar mogelijk geëvalueerd en opgelost als elementverwijzingen.</td> 
  </tr> 
  <tr> 
   <td>4</td> 
   <td>Lichtmaps maken</td> 
   <td>Optioneel. Hiermee kunt u de kwaliteit van de interactieve voorvertoning verhogen en de rendering versnellen met de standaardrenderer.</td> 
  </tr> 
  <tr> 
   <td>5</td> 
   <td>Animatie maken</td> 
   <td>Optioneel. Hiermee kunt u een eenvoudige animatie renderen die vervolgens wordt gebruikt als een visuele miniatuur in de Kaartweergave.</td> 
  </tr> 
  <tr> 
   <td>6</td> 
   <td>Wachten op verwerking</td> 
   <td>Wordt weergegeven wanneer andere 3D-elementen verwerkingsprioriteit hebben. Elementen die bijvoorbeeld eerder zijn geüpload maar nog niet zijn verwerkt.</td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>U kunt een 3D-element weergeven in **[!UICONTROL Detail View]** of renderen nadat het voorvertoningswerkgebied maken is voltooid. U hoeft niet te wachten tot alle verwerkingsfasen zijn voltooid.

