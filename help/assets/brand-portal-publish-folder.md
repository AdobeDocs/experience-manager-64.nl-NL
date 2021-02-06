---
title: Mappen publiceren naar Brand Portal
description: Leer hoe u mappen naar Brand Portal publiceert en de publicatie ervan ongedaan maakt.
contentOwner: VG
translation-type: tm+mt
source-git-commit: 33210032c45e38963aed429e70eec4095c5d75f1
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 31%

---


# Mappen publiceren naar Brand Portal {#publish-folders-to-brand-portal}

Als beheerder van Adobe Experience Manager-middelen (AEM) kunt u elementen en mappen publiceren naar de AEM Assets Brand Portal-instantie (of de publicatieworkflow plannen op een latere datum of tijd) voor uw organisatie. U moet echter eerst AEM Assets integreren met Brand Portal. Zie [AEM Assets configureren met Brand Portal](configure-aem-assets-with-brand-portal.md) voor meer informatie.

Nadat u middelen of een omslag publiceert, is het beschikbaar aan gebruikers in het Portaal van het Merk.

Als u vervolgens wijzigingen aanbrengt in het oorspronkelijke element of de oorspronkelijke map in AEM Assets, worden de wijzigingen pas doorgevoerd in Brand Portal als u het element of de map opnieuw publiceert. Met deze functie zorgt u ervoor dat wijzigingen die momenteel worden uitgevoerd, niet beschikbaar zijn in Brand Portal. Alleen goedgekeurde wijzigingen die door een beheerder zijn gepubliceerd, zijn beschikbaar in Brand Portal.

## Mappen publiceren naar Brand Portal {#publish-folders-to-brand-portal-1}

1. Houd de muisaanwijzer in de AEM Assets-interface boven de gewenste map en selecteer de optie **[!UICONTROL Publish]** in de snelhandelingen.

   U kunt ook de gewenste map selecteren en de volgende stappen volgen.

   ![publish2bp](assets/publish2bp.png)

2. **Mappen nu publiceren**

   Voer een van de volgende handelingen uit om de geselecteerde mappen naar Brand Portal te publiceren:

   * Selecteer **[!UICONTROL Quick Publish]** in de werkbalk. Selecteer vervolgens **[!UICONTROL Publish to Brand Portal]** in het menu.
   * Selecteer **[!UICONTROL Manage Publication]** in de werkbalk.

3. Selecteer vervolgens **[!UICONTROL Action]** in **[!UICONTROL Publish to Brand Portal]** en selecteer **[!UICONTROL Scheduling]** **[!UICONTROL Now]**. Tik op **[!UICONTROL Next].**
4. Bevestig binnen **[!UICONTROL Scope]** uw selectie en tik **[!UICONTROL Publish to Brand Portal]**.

   Er verschijnt een bericht waarin wordt aangegeven dat de map in de wachtrij is geplaatst voor publicatie naar Brand Portal. Meld u aan bij de interface Brand Portal om de gepubliceerde map weer te geven.

   **Mappen later publiceren**

   De workflow voor publiceren naar Brand Portal van mappen met elementen naar een latere datum of tijd plannen:

   1. Als u middelen/mappen hebt geselecteerd om te publiceren, selecteert u **[!UICONTROL Manage Publication]** in de werkbalk boven in het scherm.
   2. Selecteer **[!UICONTROL Manage Publication]** op  pagina **[!UICONTROL Publish to Brand Portal]** van **[!UICONTROL Action]** en selecteer **[!UICONTROL Later]** van **[!UICONTROL Scheduling]**.

      ![publishlaterbp](assets/publishlaterbp.png)

   3. Selecteer een **[!UICONTROL Activation date]** en geef de tijd op. Tik op **[!UICONTROL Next]**.
   4. Bevestig uw selectie in **[!UICONTROL Scope]**. Tik op **[!UICONTROL Next]**.
   5. Geef een titel voor de workflow op onder **[!UICONTROL Workflows]**. Tik op **[!UICONTROL Publish Later]**.

      ![manageschedulepub](assets/manageschedulepub.png)

## De publicatie van mappen op Brand Portal ongedaan maken {#unpublish-folders-from-brand-portal}

U kunt elke elementmap die naar Brand Portal is gepubliceerd, verwijderen door de publicatie ongedaan te maken van de instantie AEM-auteur. Nadat u de publicatie van de oorspronkelijke map ongedaan hebt gemaakt, is de kopie ervan niet meer beschikbaar voor Brand Portal-gebruikers.

U kunt de publicatie van mappen op Brand Portal snel ongedaan maken of deze later plannen. De publicatie van mappen met assets op Brand Portal ongedaan maken:

1. Selecteer in de AEM Assets-interface van de AEM-auteur-instantie de map die u wilt verwijderen.

   ![publish2bp-1](assets/publish2bp-1.png)

2. Tik/klik op **[!UICONTROL Manage Publication]** op de werkbalk.

3. **Publiceren via Brand Portal nu ongedaan maken**

   U kunt de publicatie van de gewenste map snel ongedaan maken via Brand Portal:

   1. Selecteer **[!UICONTROL Unpublish from Brand Portal]** op **[!UICONTROL Manage Publication]** pagina en selecteer **[!UICONTROL Scheduling]** **[!UICONTROL Now]** op **[!UICONTROL Action]** pagina.
   2. Tik of klik op **[!UICONTROL Next].**
   3. Bevestig binnen **[!UICONTROL Scope]** uw selectie en tik **[!UICONTROL Unpublish from Brand Portal]**.

   ![confirm-unpublish](assets/confirm-unpublish.png)

   **Publiceren via Brand Portal later ongedaan maken**

   U kunt als volgt de publicatie van een map van Brand Portal naar een latere datum en tijd plannen:

   1. Selecteer op **[!UICONTROL Manage Publication]** pagina **[!UICONTROL Action]** **[!UICONTROL Unpublish from Brand Portal]** en selecteer **[!UICONTROL Scheduling]** **[!UICONTROL Later].**
   2. Selecteer een **[!UICONTROL Activation date]** en geef de tijd op. Tik op **[!UICONTROL Next]**.
   3. Bevestig binnen **[!UICONTROL Scope]** uw selectie en tik **[!UICONTROL Next]**.
   4. Geef een **[!UICONTROL Workflow title]** op onder **[!UICONTROL Workflows]**. Tik op **[!UICONTROL Unpublish Later].**

      ![unpublishworkflows](assets/unpublishworkflows.png)


>[!NOTE]
>
>De procedure voor het publiceren/openbaar maken van een middel van/naar Brand Portal is vergelijkbaar met de procedure voor een map.
