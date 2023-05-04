---
title: Mappen publiceren naar Brand Portal
description: Leer hoe u mappen publiceert en publiceert naar Brand Portal.
contentOwner: VG
feature: Brand Portal
role: User
exl-id: f41ab750-5780-42ae-a131-5bc748280215
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 28%

---

# Mappen publiceren naar Brand Portal {#publish-folders-to-brand-portal}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Als Adobe Experience Manager Assets-beheerder kunt u elementen en mappen publiceren naar de [!DNL Experience Manager Assets Brand Portal] -instantie (of de publicatieworkflow plannen naar een latere datum/tijd) voor uw organisatie. U moet echter eerst integreren [!DNL Experience Manager Assets] with [!DNL Brand Portal]. Zie voor meer informatie [Configureren [!DNL Experience Manager Assets] met Brand Portal](configure-aem-assets-with-brand-portal.md).

Nadat u een middel of een omslag publiceert, is het beschikbaar aan gebruikers in Brand Portal.

Als u volgende wijzigingen aanbrengt in het oorspronkelijke middel of de oorspronkelijke map in [!DNL Assets], worden de wijzigingen pas in Brand Portal doorgevoerd als u het element of de map opnieuw publiceert. Met deze functie zorgt u ervoor dat wijzigingen die momenteel worden uitgevoerd, niet beschikbaar zijn in Brand Portal. Alleen goedgekeurde wijzigingen die door een beheerder zijn gepubliceerd, zijn beschikbaar in Brand Portal.

## Mappen publiceren naar Brand Portal {#publish-folders-to-brand-portal-1}

1. Van de [!DNL Assets] interface, houd de muisaanwijzer boven de gewenste map en selecteer **[!UICONTROL Publish]** van de snelle acties.

   U kunt ook de gewenste map selecteren en de volgende stappen volgen.

   ![publish2bp](assets/publish2bp.png)

2. **Mappen nu publiceren**

   Voer een van de volgende handelingen uit om de geselecteerde mappen naar Brand Portal te publiceren:

   * Selecteer **[!UICONTROL Quick Publish]** in de werkbalk. Selecteer vervolgens in het menu **[!UICONTROL Publish to Brand Portal]**.
   * Selecteer **[!UICONTROL Manage Publication]** in de werkbalk.

3. Vervolgens vanaf de **[!UICONTROL Action]** selecteren **[!UICONTROL Publish to Brand Portal]** en van **[!UICONTROL Scheduling]** selecteren **[!UICONTROL Now]**. Tik op **[!UICONTROL Next].**
4. Within **[!UICONTROL Scope]**, bevestig uw selectie en tik op **[!UICONTROL Publish to Brand Portal]**.

   Er verschijnt een bericht waarin wordt aangegeven dat de map in de wachtrij is geplaatst voor publicatie naar Brand Portal. Meld u aan bij de Brand Portal-interface om de gepubliceerde map weer te geven.

   **Mappen later publiceren**

   U kunt als volgt de publicatieworkflow van mappen met elementen naar Brand Portal plannen op een latere datum of tijd:

   1. Als u middelen/mappen hebt geselecteerd om te publiceren, selecteert u **[!UICONTROL Manage Publication]** in de werkbalk bovenaan.
   2. Aan **[!UICONTROL Manage Publication]** pagina, selecteert u **[!UICONTROL Publish to Brand Portal]** van **[!UICONTROL Action]** en selecteert u **[!UICONTROL Later]** van **[!UICONTROL Scheduling]**.

      ![publishlaterbp](assets/publishlaterbp.png)

   3. Selecteer een **[!UICONTROL Activation date]** en geef de tijd op. Tik op **[!UICONTROL Next]**.
   4. Bevestig uw selectie in **[!UICONTROL Scope]**. Tik op **[!UICONTROL Next]**.
   5. Geef een titel voor de workflow op onder **[!UICONTROL Workflows]**. Tik op **[!UICONTROL Publish Later]**.

      ![manageschedulepub](assets/manageschedulepub.png)

## De publicatie van mappen op Brand Portal ongedaan maken {#unpublish-folders-from-brand-portal}

U kunt elke elementmap die naar Brand Portal is gepubliceerd, verwijderen door de publicatie ervan ongedaan te maken [!DNL Experience Manager] Instantie van auteur. Nadat u de publicatie van de oorspronkelijke map ongedaan hebt gemaakt, is de kopie ervan niet meer beschikbaar voor Brand Portal-gebruikers.

U kunt de publicatie van mappen in Brand Portal snel ongedaan maken of deze later plannen. De publicatie van mappen met assets op Brand Portal ongedaan maken:

1. Van de [!DNL Assets] interface in [!DNL Experience Manager]  Auteur-instantie, selecteer de map waarvan u de publicatie ongedaan wilt maken.

   ![publish2bp-1](assets/publish2bp-1.png)

2. Tik/klik op de werkbalk **[!UICONTROL Manage Publication]**.

3. **Publiceren vanuit Brand Portal nu ongedaan maken**

   U kunt de publicatie van de gewenste map snel ongedaan maken vanuit Brand Portal:

   1. Aan **[!UICONTROL Manage Publication]** pagina, van **[!UICONTROL Action]** selecteren **[!UICONTROL Unpublish from Brand Portal]** en van **[!UICONTROL Scheduling]** selecteren **[!UICONTROL Now]**.
   2. Tik of klik op **[!UICONTROL Next].**
   3. Within **[!UICONTROL Scope]**, bevestig uw selectie en tik op **[!UICONTROL Unpublish from Brand Portal]**.

   ![confirm-unpublish](assets/confirm-unpublish.png)

   **Publiceren vanuit Brand Portal later ongedaan maken**

   U kunt als volgt de publicatie van een map van Brand Portal naar een latere datum en tijd plannen:

   1. Aan **[!UICONTROL Manage Publication]** pagina, van **[!UICONTROL Action]** selecteren **[!UICONTROL Unpublish from Brand Portal]** en van **[!UICONTROL Scheduling]** selecteren **[!UICONTROL Later].**
   2. Selecteer een **[!UICONTROL Activation date]** en geef de tijd op. Tik op **[!UICONTROL Next]**.
   3. Within **[!UICONTROL Scope]**, bevestig uw selectie en tik op **[!UICONTROL Next]**.
   4. Geef een **[!UICONTROL Workflow title]** krachtens **[!UICONTROL Workflows]**. Tik op **[!UICONTROL Unpublish Later].**

      ![unpublishworkflows](assets/unpublishworkflows.png)


>[!NOTE]
>
>De procedure voor het publiceren/ongedaan maken van een middel van of naar Brand Portal is vergelijkbaar met de procedure voor het publiceren van een map.
