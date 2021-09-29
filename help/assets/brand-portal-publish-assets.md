---
title: Mappen publiceren naar Brand Portal
description: Leer hoe u middelen publiceert en publiceert naar Brand Portal.
contentOwner: VG
feature: Brand Portal
role: User
exl-id: 6b78124d-4022-452f-8d0f-b667de337bf4
source-git-commit: de5632ff0ee87a4ded88e792b57e818baf4c01a3
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 34%

---

# Assets publiceren naar Brand Portal {#publish-assets-to-brand-portal}

Als Adobe Experience Manager Assets-beheerder kunt u elementen publiceren naar de [!DNL Experience Manager Assets Brand Portal]-instantie (of de publicatieworkflow plannen op een latere datum/tijd) voor uw organisatie. Nochtans, moet u eerst [!DNL Assets] met [!DNL Brand Portal] vormen. Zie [Configureren [!DNL Assets] met [!DNL Brand Portal]](configure-aem-assets-with-brand-portal.md) voor meer informatie.

Nadat u een middel publiceert, is het beschikbaar aan gebruikers in Brand Portal.

Als u in [!DNL Assets] verdere wijzigingen in het oorspronkelijke element aanbrengt, worden de wijzigingen pas in Brand Portal doorgevoerd als u het element opnieuw publiceert. Met deze functie zorgt u ervoor dat wijzigingen die momenteel worden uitgevoerd, niet beschikbaar zijn in Brand Portal. Alleen goedgekeurde wijzigingen die door een beheerder zijn gepubliceerd, zijn beschikbaar in Brand Portal.

Nadat de replicatie slaagt, kunt u activa, omslagen, en inzamelingen aan [!DNL Brand Portal] publiceren. Voer de volgende stappen uit om elementen te publiceren naar Brand Portal:

>[!NOTE]
>
>Adobe raadt gefaseerde publicatie aan, bij voorkeur tijdens niet-piekuren, zodat de [!DNL Experience Manager]-auteur niet teveel bronnen in beslag neemt.

1. Houd de muisaanwijzer boven de gewenste elementen in de middelenconsole en selecteer de optie **[!UICONTROL Publish]** in de snelhandelingen.

   U kunt ook de elementen selecteren die u naar Brand Portal wilt publiceren.

   ![publish2bp-2](assets/publish2bp-2.png)

2. Voor het publiceren van de elementen naar Brand Portal zijn de volgende twee opties beschikbaar:
   * [Elementen direct publiceren](#publish-now)
   * [Assets later publiceren](#publish-later)

## Assets nu publiceren {#publish-now}

Voer een van de volgende handelingen uit om de geselecteerde assets naar Brand Portal te publiceren:

* Selecteer **[!UICONTROL Quick Publish]** in de werkbalk. Selecteer vervolgens **[!UICONTROL Publish to Brand Portal]** in het menu.

* Selecteer **[!UICONTROL Manage Publication]** in de werkbalk.

   1. Selecteer vervolgens **[!UICONTROL Action]** in **[!UICONTROL Publish to Brand Portal]** en selecteer **[!UICONTROL Scheduling]** **[!UICONTROL Now]**. Tik of klik op **[!UICONTROL Next].**

   2. Bevestig binnen **[!UICONTROL Scope]** uw selectie en tik/klik **[!UICONTROL Publish to Brand Portal]**.

Er verschijnt een bericht waarin wordt aangegeven dat de assets in de wachtrij zijn geplaatst voor publicatie naar Brand Portal. Meld u aan bij de Brand Portal-interface om de gepubliceerde middelen te bekijken.

## Assets later publiceren {#publish-later}

Voer de volgende handelingen uit om het publiceren van de assets naar Brand Portal op een latere datum of tijd te plannen:

1. Als u elementen/mappen hebt geselecteerd om te publiceren, selecteert u **[!UICONTROL Manage Publication]** in de werkbalk boven in het scherm.
2. Selecteer **[!UICONTROL Manage Publication]** op  pagina **[!UICONTROL Publish to Brand Portal]** van **[!UICONTROL Action]** en selecteer **[!UICONTROL Later]** van **[!UICONTROL Scheduling]**.

   ![publishlaterbp-1](assets/publishlaterbp-1.png)

3. Selecteer een **[!UICONTROL Activation date]** en geef de tijd op. Tik of klik op **[!UICONTROL Next]**.
4. Selecteer een **[!UICONTROL Activation date]** en geef de tijd op. Tik of klik op **[!UICONTROL Next]**.
5. Geef een titel voor de workflow op onder **[!UICONTROL Workflows]**. Tik of klik op **[!UICONTROL Publish Later]**.

   ![publishworkflow](assets/publishworkflow.png)

Meld u nu aan bij Brand Portal om te zien of de gepubliceerde middelen beschikbaar zijn op de interface van Brand Portal.

![bp_631_landing_page](assets/bp_landing_page.png)
