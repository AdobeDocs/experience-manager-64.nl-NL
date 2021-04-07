---
title: Informatie over het uploaden en verwerken van 3D-elementen in AEM
seo-title: Informatie over het uploaden en verwerken van 3D-elementen in AEM
description: Aanbevolen procedures voor het uploaden en verwerken van 3D-elementen.
seo-description: Aanbevolen procedures voor het uploaden en verwerken van 3D-elementen.
uuid: d8abf460-adff-4f0f-92ae-2c8651a17488
contentOwner: Rick Brough
topic-tags: 3D
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
discoiquuid: a0319701-21eb-4b7f-8b2e-ac81a7a75875
exl-id: 4b8b0247-0978-40b5-92e2-319cfa44b34e
feature: 3D-middelen
role: Business Practitioner
translation-type: tm+mt
source-git-commit: f9faa357f8de92d205f1a297767ba4176cfd1e10
workflow-type: tm+mt
source-wordcount: '862'
ht-degree: 1%

---

# Informatie over het uploaden en verwerken van 3D-elementen in AEM {#about-the-uploading-and-processing-of-d-assets-in-aem}

>[!IMPORTANT]
>
>AEM 3D in AEM 6.4 wordt niet meer ondersteund. Adobe raadt u aan de functie 3D-elementen in [AEM te gebruiken als een Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/assets-3d.html#dynamicmedia) of [AEM 6.5.3 of hoger.](https://experienceleague.adobe.com/docs/experience-manager-65/assets/dynamic/assets-3d.html#dynamic).

Gebruik standaard upload- of synchronisatiemechanismen om 3D-elementen en de bijbehorende bestanden waarnaar wordt verwezen, over te brengen naar AEM Assets.

Zie [Elementen uploaden](managing-assets-touch-ui.md#uploading-assets).

Adobe raadt u aan alle bestanden waarnaar wordt verwezen, te uploaden voordat of tegelijkertijd het primaire 3D-modelbestand wordt geüpload. Dit is echter geen vereiste.

Wanneer het uploaden is voltooid, worden uw 3D-bestanden geconverteerd en wordt extra verwerking toegepast om het element voor te bereiden op weergave en rendering.

## Aanbevolen procedures voor het uploaden van 3D-elementen {#best-practices-for-uploading-d-assets}

* Over het algemeen gelden er geen beperkingen voor het uploaden van 3D-inhoud in de AEM Assets-maphiërarchie. AEM de geautomatiseerde oplossing van bestandsafhankelijkheden in 3D heeft echter bereikbeperkingen om te bepalen hoe lang het duurt om grote opslagplaatsen voor bedrijfsmiddelen te doorzoeken. Daarom raadt Adobe aan dat wanneer u 3D-elementen en hun bestandsafhankelijke bestanden uploadt, u dit doet binnen een redelijke afstand van elk bestand (algemene map op de achtergrond). Nadat de bestandsafhankelijkheden zijn opgelost, kunt u zowel het 3D-element als de afhankelijke elementen overal in de opslagplaats verplaatsen zonder de bestaande relaties te verliezen.
* Adobe raadt u aan een consistente mapstructuur voor 3D-inhoud te kiezen *voordat* u uploadt. De volgende tips zijn enkele aanbevolen benaderingen die u kunt kiezen:

   * **Een aparte map bijhouden voor elk 3D-element dat u uploadt**.

      De map bevat zowel het primaire 3D-modelbestand als alle afhankelijke bestanden. Hoewel het eenvoudig is om alle middelen en afhankelijke personen in één map te plaatsen, is het lastig om naar inhoud te bladeren. Het maakt ook het delen van afhankelijke elementen (structuurafbeeldingen) tussen modellen ingewikkelder.

   * **Bewaar de modellen in één map en de afhankelijke personen in een secundaire of submap**.

      Deze aanpak ondersteunt gemakkelijk het delen van afhankelijkheden tussen modellen. Het kan echter moeilijk worden om specifieke afhankelijke personen te vinden als het aantal activa groot is.

   * **Afzonderlijke, parallelle maphiërarchieën voor modellen en afhankelijkheden**.

      U kunt deze aanpak modelleren voor 3D-ontwerptoepassingen zoals Autodesk Maya, die inhoud liever opslaan.

* Afhankelijke elementen mogen alleen worden verwijderd als de bijbehorende 3D-elementen of elementen waarnaar ze verwijzen, ook worden verwijderd. U kunt 3D-elementen echter wel vrij verwijderen zonder dat u de afhankelijke elementen hoeft te verwijderen. Als een gebiedsdeel per ongeluk wordt verloren, kunt u het gebiedsdeel gemakkelijk oplossen om het te herstellen.

   Zie Bestandsafhankelijkheden oplossen.

## Prestatieaspecten bij het uploaden van 3D-bestanden {#performance-considerations-when-uploading-d-files}

Het omzetten en verwerken van 3D-bestanden verbruikt doorgaans aanzienlijke CPU- en geheugenbronnen op een server. Het kost ook veel tijd. De verwerkingstijden variëren vaak sterk afhankelijk van de grootte van het model en de mogelijkheden van de server. Een typisch klein model met minder dan 100 k vlakken is bijvoorbeeld meestal klaar om in minder dan één minuut te worden bekeken; het wordt volledig verwerkt in 2-3 minuten. Terwijl een groot model met meer dan een miljoen gezichten tientallen minuten kan duren om volledig te verwerken.

Conversie-, verwerkings- en rendertaken worden zo nodig in een wachtrij geplaatst om te voorkomen dat de server te veel wordt vertraagd. Het bericht &quot;Wachten op verwerking...&quot; wordt soms weergegeven in de **[!UICONTROL Card View]** op het moment dat u elementen uploadt. Deze status geeft aan dat andere verwerkings- of rendertaken moeten zijn voltooid voordat het huidige element wordt verwerkt.

Er zijn mechanismen beschikbaar om het CPU-gebruik voor innameverwerking en voor rendering te beperken. Zie [Geavanceerde configuratiemontages](advanced-config-3d.md) voor informatie over hoe te om de grenzen van cpu te vormen.

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
   <td>Grondschaduw maken</td> 
   <td>Optioneel. Hiermee kunt u een omgevingsslagschaduw genereren op het grondvlak onder het 3D-object. Zie <a href="/help/assets/advanced-config-3d.md">Geavanceerde configuratie-instellingen</a> om deze verwerking in of uit te schakelen.</td> 
  </tr> 
  <tr> 
   <td>5<br /> </td> 
   <td>Lichtmaps maken</td> 
   <td>Optioneel. Hiermee kunt u de kwaliteit van de interactieve voorvertoning verhogen en de rendering versnellen met de standaardrenderer. Zie <a href="/help/assets/advanced-config-3d.md">Geavanceerde configuratie-instellingen</a> om deze verwerking in of uit te schakelen.</td> 
  </tr> 
  <tr> 
   <td>6<br /> </td> 
   <td>Animatie maken</td> 
   <td>Optioneel. Hiermee kunt u een eenvoudige animatie renderen die vervolgens wordt gebruikt als een visuele miniatuur in de Kaartweergave. Zie <a href="/help/assets/advanced-config-3d.md">Geavanceerde configuratie-instellingen</a> om deze verwerking in of uit te schakelen.</td> 
  </tr> 
  <tr> 
   <td>7<br /> </td> 
   <td>Wachten op verwerking</td> 
   <td>Wordt weergegeven wanneer andere 3D-elementen verwerkingsprioriteit hebben. Elementen die bijvoorbeeld eerder zijn geüpload maar nog niet zijn verwerkt.</td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>U kunt een 3D-element weergeven in **[!UICONTROL Detail View]** of renderen nadat het voorvertoningswerkgebied maken is voltooid. U hoeft niet te wachten tot alle verwerkingsfasen zijn voltooid.
