---
title: AEM 3D integreren met Autodesk 3ds Max
seo-title: AEM 3D integreren met AutoDesk 3ds Max
description: U kunt desgewenst AEM 3D integreren met Autodesk 3ds Max software om ondersteuning voor native 3ds Max-bestanden (.MAX) mogelijk te maken. Renderen via 3ds Max wordt momenteel niet ondersteund.
seo-description: U kunt desgewenst AEM 3D integreren met Autodesk 3ds Max software om ondersteuning voor native 3ds Max-bestanden (.MAX) mogelijk te maken. Renderen via 3ds Max wordt momenteel niet ondersteund.
uuid: 6c160ad3-6b6f-43f5-9e97-5b5d962a8d1a
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
content-type: reference
topic-tags: 3D
discoiquuid: 0d7fefc0-6923-4ac3-9e90-335c08fa56f0
exl-id: 2edecd53-0a2d-44bb-968a-d988c780e142
feature: 3D-middelen
role: Administrator,Business Practitioner
translation-type: tm+mt
source-git-commit: 13eb1d64677f6940332a2eeb4d3aba2915ac7bba
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 0%

---

# AEM 3D integreren met Autodesk 3ds Max {#integrating-aem-d-with-autodesk-ds-max}

>[!NOTE]
>
>Deze taak is optioneel en heeft alleen betrekking op Windows.

U kunt desgewenst AEM 3D integreren met Autodesk 3ds Max software om ondersteuning voor native 3ds Max-bestanden (.MAX) mogelijk te maken. Renderen via 3ds Max wordt momenteel niet ondersteund.

Zie [Geavanceerde configuratie-instellingen](advanced-config-3d.md).

Zie ook [AEM 3D integreren met AutoDesk Maya](integrate-maya-with-3d.md).

**AEM 3D integreren met Autodesk 3ds Max**:

1. Installeer Autodesk 3ds Max-software op dezelfde servers als waarop AEM Author-knooppunten zijn geïnstalleerd.

   Controleer na de installatie of u Maya kunt openen en gebruiken en of er geen licentieproblemen zijn.

   >[!NOTE]
   >
   >Om te voorkomen dat problemen worden geweigerd, installeert u 3ds Max met dezelfde beheerdersaccount als AEM.

1. Klik **[!UICONTROL Customize > Plug-in Manager]** in 3ds Max.

   Zoek `FBXMAX.DLU` en controleer of **[!UICONTROL Status]** **[!UICONTROL loaded]** is.

   Sluit **[!UICONTROL Plug-In Manager]** dialoogdoos en 3ds Max.

1. Werk het conversiescript bij.

   AEM gebruikt een manuscript van de bevellijn om het 3ds Max nut van de bevellijn `3dsmaxcmd.exe` aan te halen. U moet dit script bewerken als u een andere versie dan 3ds Max 2016 hebt geïnstalleerd, als u 3ds Max op een niet-standaardlocatie hebt geïnstalleerd of als u AEM op een andere partitie of een ander station hebt geïnstalleerd.

   1. Open CRXDE Lite en navigeer naar `/libs/settings/dam/v3D/scripts/max`.
   1. Dubbelklik op `export-fbx.bat` om deze te openen.
   1. Bewerk indien nodig de eerste regel van het script om de locatie van het hulpprogramma `3dsmaxcmd.exe` weer te geven. Als bijvoorbeeld 3ds Max 2017 wordt gebruikt en AEM is geïnstalleerd op een ander schijfstation:

   ![image2018-6-22_13-35-8](assets/image2018-6-22_13-35-8.png)

1. Tik in de linkerbovenhoek van de pagina CRXDE Lite op **[!UICONTROL Save All]**.

   Tik in de linkerbovenhoek van de pagina CRXDE Lite op **[!UICONTROL Save All]**.

1. Verwijder de werkmap (alleen nodig als er eerder is geprobeerd een .MAX-bestand in te voeren).

   1. Navigeer in CRXDE Lite naar `/libs/settings/dam/v3D/Paths/maxWorkPath`. Standaard is de waarde van deze instelling `./MaxWork`. Dit is relatief ten opzichte van de hoofdmap voor AEM installatie.
   1. Log naar de server zelf en gebruik File Explorer om naar de hoofdmap voor AEM installatie te navigeren.
   1. Verwijder de map **[!UICONTROL MaxWork]** (inclusief de volledige inhoud) als deze bestaat.

      De volgende keer dat een .MAX-bestand wordt ingevoegd, wordt de map automatisch opnieuw gemaakt.

1. Schakel 3ds Max voor opname in door het volgende te doen:

   1. Navigeer in CRXDE Lite naar `/libs/settings/dam/v3D/assetTypes/max` en stel de eigenschap **[!UICONTROL Enabled]** in op true:

   ![image2018-6-22_13-50-50](assets/image2018-6-22_13-50-50.png)

1. Tik in de linkerbovenhoek van de pagina CRXDE Lite op **[!UICONTROL Save All]**.

## De integratie van AEM 3D testen met Autodesk 3ds Max {#testing-the-integration-of-aem-d-with-autodesk-ds-max}

1. Open AEM Assets en upload het `.max`-bestand in `sample-3D-content/models` naar de map **[!UICONTROL test3d]**.

   U ziet dat sample-3D-content.zip eerder is gedownload voor validatie van de standaard 3D-functionaliteit.

1. Keer aan **[!UICONTROL Card]** mening terug en bekijk de berichtbanners die op de geupload activa worden getoond.

   De banner Converting Format wordt weergegeven terwijl 3ds Max de native 3ds Max-indeling naar .FBX converteert.

1. Nadat de verwerking is voltooid, opent u `logo-sphere.max` in de weergave **[!UICONTROL Detail]**.

   De ervaring van de Voorproef is het zelfde als met `logo_sphere.fbx`.
