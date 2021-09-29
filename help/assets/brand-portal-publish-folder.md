---
title: Mappen publiceren naar Brand Portal
description: Leer hoe u mappen publiceert en publiceert naar Brand Portal.
contentOwner: VG
feature: Brand Portal
role: User
exl-id: f41ab750-5780-42ae-a131-5bc748280215
source-git-commit: de5632ff0ee87a4ded88e792b57e818baf4c01a3
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 31%

---

# Mappen publiceren naar Brand Portal {#publish-folders-to-brand-portal}

Als beheerder van Adobe Experience Manager-middelen kunt u elementen en mappen publiceren naar het [!DNL Experience Manager Assets Brand Portal]-exemplaar (of de publicatieworkflow plannen op een latere datum/tijd) voor uw organisatie. U moet [!DNL Experience Manager Assets] echter eerst integreren met [!DNL Brand Portal]. Zie [Configureren [!DNL Experience Manager Assets] met Brand Portal](configure-aem-assets-with-brand-portal.md) voor meer informatie.

Nadat u een middel of een omslag publiceert, is het beschikbaar aan gebruikers in Brand Portal.

Als u in [!DNL Assets] de oorspronkelijke bron- of mapwijzigingen doorvoert, worden de wijzigingen pas in Brand Portal doorgevoerd als u het element of de map opnieuw publiceert. Met deze functie zorgt u ervoor dat wijzigingen die momenteel worden uitgevoerd, niet beschikbaar zijn in Brand Portal. Alleen goedgekeurde wijzigingen die door een beheerder zijn gepubliceerd, zijn beschikbaar in Brand Portal.

## Mappen publiceren naar Brand Portal {#publish-folders-to-brand-portal-1}

1. Houd de muisaanwijzer boven de gewenste map in de interface [!DNL Assets] en selecteer de optie **[!UICONTROL Publish]** in de snelle handelingen.

   U kunt ook de gewenste map selecteren en de volgende stappen volgen.

   ![publish2bp](assets/publish2bp.png)

2. **Mappen nu publiceren**

   Voer een van de volgende handelingen uit om de geselecteerde mappen naar Brand Portal te publiceren:

   * Selecteer **[!UICONTROL Quick Publish]** in de werkbalk. Selecteer vervolgens **[!UICONTROL Publish to Brand Portal]** in het menu.
   * Selecteer **[!UICONTROL Manage Publication]** in de werkbalk.

3. Selecteer vervolgens **[!UICONTROL Action]** in **[!UICONTROL Publish to Brand Portal]** en selecteer **[!UICONTROL Scheduling]** **[!UICONTROL Now]**. Tik op **[!UICONTROL Next].**
4. Bevestig binnen **[!UICONTROL Scope]** uw selectie en tik **[!UICONTROL Publish to Brand Portal]**.

   Er verschijnt een bericht waarin wordt aangegeven dat de map in de wachtrij is geplaatst voor publicatie naar Brand Portal. Meld u aan bij de Brand Portal-interface om de gepubliceerde map weer te geven.

   **Mappen later publiceren**

   U kunt als volgt de publicatieworkflow van mappen met elementen naar Brand Portal plannen op een latere datum of tijd:

   1. Als u middelen/mappen hebt geselecteerd om te publiceren, selecteert u **[!UICONTROL Manage Publication]** in de werkbalk boven in het scherm.
   2. Selecteer **[!UICONTROL Manage Publication]** op  pagina **[!UICONTROL Publish to Brand Portal]** van **[!UICONTROL Action]** en selecteer **[!UICONTROL Later]** van **[!UICONTROL Scheduling]**.

      ![publishlaterbp](assets/publishlaterbp.png)

   3. Selecteer een **[!UICONTROL Activation date]** en geef de tijd op. Tik op **[!UICONTROL Next]**.
   4. Bevestig uw selectie in **[!UICONTROL Scope]**. Tik op **[!UICONTROL Next]**.
   5. Geef een titel voor de workflow op onder **[!UICONTROL Workflows]**. Tik op **[!UICONTROL Publish Later]**.

      ![manageschedulepub](assets/manageschedulepub.png)

## De publicatie van mappen op Brand Portal ongedaan maken {#unpublish-folders-from-brand-portal}

U kunt elke elementmap die naar Brand Portal is gepubliceerd, verwijderen door de publicatie ongedaan te maken van de instantie [!DNL Experience Manager] Auteur. Nadat u de publicatie van de oorspronkelijke map ongedaan hebt gemaakt, is de kopie ervan niet meer beschikbaar voor Brand Portal-gebruikers.

U kunt de publicatie van mappen in Brand Portal snel ongedaan maken of deze later plannen. De publicatie van mappen met assets op Brand Portal ongedaan maken:

1. Selecteer in de [!DNL Assets]-interface in [!DNL Experience Manager]-instantie Auteur de map die u wilt verwijderen.

   ![publish2bp-1](assets/publish2bp-1.png)

2. Tik/klik op **[!UICONTROL Manage Publication]** op de werkbalk.

3. **Publiceren vanuit Brand Portal nu ongedaan maken**

   U kunt de publicatie van de gewenste map snel ongedaan maken vanuit Brand Portal:

   1. Selecteer **[!UICONTROL Unpublish from Brand Portal]** op **[!UICONTROL Manage Publication]** pagina en selecteer **[!UICONTROL Scheduling]** **[!UICONTROL Now]** op **[!UICONTROL Action]** pagina.
   2. Tik of klik op **[!UICONTROL Next].**
   3. Bevestig binnen **[!UICONTROL Scope]** uw selectie en tik **[!UICONTROL Unpublish from Brand Portal]**.

   ![confirm-unpublish](assets/confirm-unpublish.png)

   **Publiceren vanuit Brand Portal later ongedaan maken**

   U kunt als volgt de publicatie van een map van Brand Portal naar een latere datum en tijd plannen:

   1. Selecteer op **[!UICONTROL Manage Publication]** pagina **[!UICONTROL Action]** **[!UICONTROL Unpublish from Brand Portal]** en selecteer **[!UICONTROL Scheduling]** **[!UICONTROL Later].**
   2. Selecteer een **[!UICONTROL Activation date]** en geef de tijd op. Tik op **[!UICONTROL Next]**.
   3. Bevestig binnen **[!UICONTROL Scope]** uw selectie en tik **[!UICONTROL Next]**.
   4. Geef een **[!UICONTROL Workflow title]** op onder **[!UICONTROL Workflows]**. Tik op **[!UICONTROL Unpublish Later].**

      ![unpublishworkflows](assets/unpublishworkflows.png)


>[!NOTE]
>
>De procedure voor het publiceren/ongedaan maken van een middel van of naar Brand Portal is vergelijkbaar met de procedure voor het publiceren van een map.
