---
title: Metagegevens bewerken of toevoegen
description: Meer informatie over metagegevens van elementen in [!DNL Experience Manager] Elementen en verschillende manieren waarop u metagegevens van elementen kunt bewerken.
contentOwner: AG
feature: Metadata
role: User,Admin
exl-id: f0522343-f8a9-4d89-8ce8-b3357ae3fe70
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 6%

---

# Metagegevens bewerken of toevoegen {#how-to-edit-or-add-metadata}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Metagegevens zijn aanvullende informatie over het element die kan worden doorzocht. Deze wordt automatisch uitgepakt wanneer u een afbeelding uploadt. U kunt de bestaande metagegevens bewerken of nieuwe eigenschappen van metagegevens toevoegen aan bestaande velden (bijvoorbeeld wanneer een metagegevensveld leeg is).

Omdat bedrijven gecontroleerde en betrouwbare metagegevenswoordenboeken nodig hebben, [!DNL Experience Manager] De elementen staan niet toe dat nieuwe eigenschappen van metagegevens ad hoc worden toegevoegd. Hoewel auteurs geen nieuwe metagegevensvelden voor elementen kunnen toevoegen, kunnen ontwikkelaars dat wel. Zie [Nieuwe eigenschap metagegevens maken voor elementen](meta-edit.md#editing-metadata-schema).

## Metagegevens voor een element bewerken {#editing-metadata-for-an-asset}

Metagegevens bewerken:

1. Voer een van de volgende handelingen uit:

   * Selecteer het element in de interface Elementen en klik op het element **[!UICONTROL View Properties]** op de werkbalk.
   * Selecteer in de miniatuur van het element de optie **[!UICONTROL View Properties]** snelle actie.
   * Klik/tik op de elementpagina **[!UICONTROL View Properties]** pictogram ![infopictogram](assets/do-not-localize/info_icon.png) op de werkbalk.

   Op de elementpagina worden alle metagegevens van het element weergegeven. Deze metagegevens zijn automatisch geëxtraheerd wanneer deze werden geüpload (opgenomen) in [!DNL Experience Manager] Elementen.

   ![chlimage_1-169](assets/chlimage_1-169.png)

1. Bewerk desgewenst de metadata op de verschillende tabbladen en klik of tik wanneer u klaar bent op **[!UICONTROL Save]** op de werkbalk om de wijzigingen op te slaan. Klik of tik op **[!UICONTROL Close]** om terug te keren naar de webinterface voor assets.

   >[!NOTE]
   >
   >Als een tekstveld leeg is, is er geen bestaande metagegevensset. U kunt een waarde in het veld invoeren en deze opslaan om die eigenschap voor metagegevens toe te voegen.

Eventuele wijzigingen in de metagegevens van een element worden teruggeschreven naar het oorspronkelijke binaire bestand als onderdeel van de XMP gegevens. Dit gebeurt via AEM terugschrijfworkflow voor metagegevens. Wijzigingen in bestaande eigenschappen (zoals `dc:title`) worden overschreven en nieuwe eigenschappen gemaakt (inclusief aangepaste eigenschappen zoals `cq:tags`) worden samen met het schema toegevoegd.

XMP terugschrijven wordt ondersteund en ingeschakeld voor de platforms en bestandsindelingen die worden beschreven in [Technische voorschriften.](/help/sites-deploying/technical-requirements.md)

## Metagegevensschema bewerken {#editing-metadata-schema}

Voor meer informatie over het bewerken van het metagegevensschema raadpleegt u [Formulieren met metagegevensschema bewerken](metadata-schemas.md#editing-metadata-schema-forms).

## Een aangepaste naamruimte registreren binnen [!DNL Experience Manager] {#registering-a-custom-namespace-within-aem}

U kunt uw eigen naamruimten toevoegen binnen AEM. Net zoals er vooraf gedefinieerde naamruimten zijn, zoals cq, jcr en sling, kunt u een naamruimte hebben voor de metagegevens van de gegevensopslagruimte en de verwerking van de xml.

1. Naar de beheerpagina voor knooppunttypen `https://[AEM_server]:[port]/crx/explorer/nodetypes/index.jsp`.
1. Klikken of tikken **[!UICONTROL Namespaces]** boven aan de pagina. De pagina voor naamruimtebeheer wordt weergegeven in een venster.

1. Als u een naamruimte wilt toevoegen, klikt u of tikt u op **[!UICONTROL New]** onderaan.
1. Geef een aangepaste naamruimte op in de XML-naamruimteconventie (geef de id op in de vorm van een URI en een bijbehorend voorvoegsel voor de id) en klik of tik **[!UICONTROL Save]**.

## Tips en beperkingen {#best-practices-limitations}

* De metagegevensupdates via Touch-UI wijzigen de eigenschappen van de metagegevens in het dialoogvenster `dc` naamruimte. Wanneer updates via de HTTP-API worden uitgevoerd, veranderen de eigenschappen van de metagegevens in het dialoogvenster `jcr` naamruimte. Zie [hoe te om meta-gegevens bij te werken gebruikend HTTP API](/help/assets/mac-api-assets.md#update-asset-metadata).

>[!MORELIKETHIS]
>
>* [Informatie over metagegevens en de behoefte aan metagegevens in Middelen](metadata.md)

