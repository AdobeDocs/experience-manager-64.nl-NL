---
title: Metagegevens van meerdere elementen en verzamelingen bulksgewijs bewerken
description: Leer hoe u de metagegevens van veel elementen en verzamelingen tegelijk kunt bewerken om snel algemene wijzigingen in metagegevens door te geven.
contentOwner: AG
feature: Asset Management,Metadata,Collections
role: User
exl-id: 3541b50a-f226-4a6a-9c2a-03a5f47f1c23
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 12%

---

# Meerdere elementen en verzamelingen beheren {#managing-multiple-assets-and-collections}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Leer hoe u de metagegevens van meerdere elementen en verzamelingen tegelijk kunt bewerken om snel algemene wijzigingen in metagegevens door te geven.

Met de Adobe Enterprise Manager-middelen kunt u de metagegevens van meerdere elementen tegelijk bewerken, zodat u snel algemene wijzigingen in metagegevens in meerdere bestanden kunt doorgeven. U kunt de metagegevens voor meerdere verzamelingen ook bulksgewijs bewerken.

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
1. Klik op de werkbalk op **[!UICONTROL Properties]** om de pagina met eigenschappen voor de geselecteerde elementen te openen.
1. Wijzig de eigenschappen van metagegevens voor geselecteerde elementen onder de verschillende tabbladen.
1. Als u de metagegevens van een specifiek element wilt weergeven, annuleert u de selectie van de resterende elementen in de lijst. Als u de selectie van een aantal elementen op de knop [!UICONTROL Properties] , worden de metagegevens van dergelijke elementen niet bijgewerkt.
1. Als u een ander metagegevensschema voor de elementen wilt selecteren, klikt u op **[!UICONTROL Settings]** op de werkbalk en selecteer een schema. Klik op **[!UICONTROL Save & Close]**.
1. Selecteer **[!UICONTROL Append mode]** om de nieuwe metadata toe te voegen aan de bestaande metadata in velden die meerdere waarden bevatten. Als u deze optie niet selecteert, worden de bestaande metadata in de velden vervangen door de nieuwe metadata. Klik op **[!UICONTROL Submit]**.

![De bulk van het metagegevensschema is van toepassing op meerdere elementen](assets/metadata-schema-bulk-edit.gif)

>[!CAUTION]
>
>Voor velden met één waarde worden de nieuwe metadata niet toegevoegd aan de bestaande waarde in het veld, zelfs niet als u **[!UICONTROL Append mode]** selecteert.

## Limiet voor bijwerken van bulkmetagegevens configureren {#configure-limit-for-bulk-metadata-update}

Om situaties als DOS te voorkomen, [!DNL Experience Manager] Hiermee wordt het aantal parameters beperkt dat wordt ondersteund in een Sling-aanvraag. Wanneer u metagegevens van veel elementen in één keer bijwerkt, kunt u de limiet bereiken en worden de metagegevens niet bijgewerkt voor meer elementen. [!DNL Experience Manager] Hiermee genereert u de volgende waarschuwing in de logboeken:

`org.apache.sling.engine.impl.parameters.Util Too many name/value pairs, stopped processing after 10000 entries`

Om de grens te veranderen, toegang **[!UICONTROL Tools > Operations > Web Console]** en wijzigt u de waarde van [!UICONTROL Maximum POST Parameters] in [!UICONTROL Apache Sling Request Parameter Handling] OSGi-configuratie.

>[!MORELIKETHIS]
>
>* [Metagegevens van meerdere verzamelingen bulksgewijs bewerken](managing-collections-touch-ui.md#editing-collection-metadata-in-bulk)

