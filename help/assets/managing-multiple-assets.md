---
title: Metagegevens van meerdere elementen en verzamelingen bulksgewijs bewerken
description: Leer hoe u de metagegevens van veel elementen en verzamelingen tegelijk kunt bewerken om snel algemene wijzigingen in metagegevens door te geven.
contentOwner: AG
feature: Middelenbeheer, metagegevens, verzamelingen
role: Zakelijke praktiserer
translation-type: tm+mt
source-git-commit: 29e3cd92d6c7a4917d7ee2aa8d9963aa16581633
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 13%

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
1. Klik in de werkbalk op **[!UICONTROL Properties]** om de pagina met eigenschappen voor de geselecteerde elementen te openen.
1. Wijzig de eigenschappen van metagegevens voor geselecteerde elementen onder de verschillende tabbladen.
1. Als u de metagegevens van een specifiek element wilt weergeven, annuleert u de selectie van de resterende elementen in de lijst. Als u de selectie van een paar elementen op de pagina [!UICONTROL Properties] annuleert, worden de metagegevens van dergelijke elementen niet bijgewerkt.
1. Als u een ander metagegevensschema voor de elementen wilt selecteren, klikt u op **[!UICONTROL Settings]** op de werkbalk en selecteert u een schema. Klik op **[!UICONTROL Save & Close]**.
1. Selecteer **[!UICONTROL Append mode]** om de nieuwe metadata toe te voegen aan de bestaande metadata in velden die meerdere waarden bevatten. Als u deze optie niet selecteert, worden de bestaande metadata in de velden vervangen door de nieuwe metadata. Klik op **[!UICONTROL Submit]**.

![De bulk van het metagegevensschema is van toepassing op meerdere elementen](assets/metadata-schema-bulk-edit.gif)

>[!CAUTION]
>
>Voor velden met één waarde worden de nieuwe metadata niet toegevoegd aan de bestaande waarde in het veld, zelfs niet als u **[!UICONTROL Append mode]** selecteert.

## Limiet voor bijwerken van bulkmetagegevens configureren {#configure-limit-for-bulk-metadata-update}

Om DOS als situatie te verhinderen, beperkt AEM het aantal parameters die in een het Verdelen verzoek worden gesteund. Wanneer u metagegevens van vele elementen in één keer bijwerkt, kunt u de limiet bereiken en worden de metagegevens niet bijgewerkt voor meer elementen. AEM genereert de volgende waarschuwing in de logboeken:

`org.apache.sling.engine.impl.parameters.Util Too many name/value pairs, stopped processing after 10000 entries`

Als u de limiet wilt wijzigen, opent u **[!UICONTROL Tools > Operations > Web Console]** en wijzigt u de waarde van [!UICONTROL Maximum POST Parameters] in de OSGi-configuratie [!UICONTROL Apache Sling Request Parameter Handling].

>[!MORELIKETHIS]
>
>* [Metagegevens van meerdere verzamelingen bulksgewijs bewerken](managing-collections-touch-ui.md#editing-collection-metadata-in-bulk)