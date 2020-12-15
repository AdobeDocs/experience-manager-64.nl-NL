---
title: Metagegevens van meerdere elementen en verzamelingen bulksgewijs bewerken
description: Leer hoe u de metagegevens van veel elementen en verzamelingen tegelijk kunt bewerken om snel algemene wijzigingen in metagegevens door te geven.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 97bb17ce719f82449e28f9b32eb651b632b0f8b5
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 11%

---


# Meerdere elementen en verzamelingen beheren {#managing-multiple-assets-and-collections}

Leer hoe u de metagegevens van meerdere elementen en verzamelingen tegelijk kunt bewerken om snel algemene wijzigingen in metagegevens door te geven.

Met de Middelen AEM Enterprise Manager van Adobe kunt u de metagegevens van meerdere elementen tegelijk bewerken, zodat u snel algemene wijzigingen in metagegevens in meerdere bestanden kunt doorgeven. U kunt de metagegevens voor meerdere verzamelingen ook bulksgewijs bewerken.

Gebruik de eigenschappenpagina om wijzigingen in metagegevens uit te voeren voor meerdere elementen of verzamelingen:

* Eigenschappen van metagegevens wijzigen in een algemene waarde
* Tags toevoegen of wijzigen

Gebruik de Schema-editor om de pagina met metagegevenseigenschappen aan te passen, inclusief het toevoegen, wijzigen of verwijderen van eigenschappen van metagegevens.

>[!NOTE]
>
>De bulkbewerkingsmethoden werken voor elementen die beschikbaar zijn in een map of een verzameling. Voor de elementen die beschikbaar zijn in verschillende mappen of die voldoen aan een algemeen criterium, is het mogelijk de metagegevens bulksgewijs bij te werken op basis van zoekresultaten met middelen.

## Eigenschappen van metagegevens van meerdere elementen bewerken {#editing-metadata-properties-of-multiple-assets}

1. Navigeer in de gebruikersinterface Elementen naar de locatie van de elementen die u wilt bewerken.
1. Selecteer de elementen waarvan u de algemene eigenschappen wilt bewerken.
1. Tik op of klik op het pictogram **[!UICONTROL Properties]** op de werkbalk om de pagina met eigenschappen voor de geselecteerde elementen te openen.

   >[!NOTE]
   >
   >Wanneer u meerdere elementen selecteert, wordt het laagste gebruikelijke bovenliggende formulier geselecteerd voor de elementen. Met andere woorden, op de eigenschappenpagina worden alleen metagegevensvelden weergegeven die gemeenschappelijk zijn op de eigenschappenpagina&#39;s van alle afzonderlijke elementen.

1. Wijzig de eigenschappen van metagegevens voor geselecteerde elementen onder de verschillende tabbladen.
1. Schakel de overige elementen in de lijst uit als u de metagegevenseditor voor een bepaald element wilt weergeven. De gebieden van de meta-gegevensredacteur zijn bevolkt met de meta-gegevens voor het bepaalde middel.

   >[!NOTE]
   >
   >* Op de pagina met eigenschappen kunt u elementen uit de lijst met elementen verwijderen door ze te deselecteren. In de lijst met elementen zijn standaard alle elementen geselecteerd. De metagegevens voor elementen die u uit de lijst verwijdert, worden niet bijgewerkt.
   >* Selecteer boven aan de lijst met elementen het selectievakje bij **Titel** om te schakelen tussen het selecteren van de elementen en het wissen van de lijst.


1. Als u een ander metagegevensschema voor de elementen wilt selecteren, tikt u op het pictogram **[!UICONTROL Settings]** op de werkbalk en selecteert u het gewenste schema.
1. Sla de wijzigingen op.
1. Selecteer **[!UICONTROL Append mode]** om de nieuwe metadata toe te voegen aan de bestaande metadata in velden die meerdere waarden bevatten. Als u deze optie niet selecteert, worden de bestaande metadata in de velden vervangen door de nieuwe metadata. Tik of klik op **[!UICONTROL Submit]**.

   >[!CAUTION]
   >
   >Voor velden met één waarde worden de nieuwe metadata niet toegevoegd aan de bestaande waarde in het veld, zelfs niet als u **[!UICONTROL Append mode]** selecteert.

## Limiet voor bijwerken van bulkmetagegevens configureren {#configure-limit-for-bulk-metadata-update}

Om DOS als situatie te verhinderen, beperkt AEM het aantal parameters die in een het Verdelen verzoek worden gesteund. Wanneer u metagegevens van veel elementen in één keer bijwerkt, kunt u de limiet bereiken en worden de metagegevens niet bijgewerkt voor meer elementen. AEM genereert de volgende waarschuwing in de logboeken:

`org.apache.sling.engine.impl.parameters.Util Too many name/value pairs, stopped processing after 10000 entries`

Als u de limiet wilt wijzigen, opent u **[!UICONTROL Tools > Operations > Web Console]** en wijzigt u de waarde van [!UICONTROL Maximum POST Parameters] in de OSGi-configuratie [!UICONTROL Apache Sling Request Parameter Handling].

>[!MORELIKETHIS]
>
>* [Metagegevens van meerdere verzamelingen bulksgewijs bewerken](managing-collections-touch-ui.md#editing-collection-metadata-in-bulk)