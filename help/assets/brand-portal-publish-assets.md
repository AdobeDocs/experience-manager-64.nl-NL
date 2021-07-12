---
title: Mappen publiceren naar Brand Portal
description: Leer hoe u middelen publiceert en publiceert naar Brand Portal.
contentOwner: VG
feature: Brand Portal
role: User
exl-id: 6b78124d-4022-452f-8d0f-b667de337bf4
source-git-commit: 3c050c33a384d586d74bd641f7622989dc1d6b22
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 39%

---

# Assets publiceren naar Brand Portal {#publish-assets-to-brand-portal}

Als beheerder van Adobe Experience Manager-middelen (AEM) kunt u elementen voor uw organisatie publiceren naar de AEM Assets Brand Portal-instantie (of de publicatieworkflow plannen op een latere datum of tijd). U moet echter eerst AEM Assets met Brand Portal configureren. Zie [AEM Assets configureren met Brand Portal](configure-aem-assets-with-brand-portal.md) voor meer informatie.

Nadat u een middel publiceert, is het beschikbaar aan gebruikers in Brand Portal.

Als u de oorspronkelijke elementen in AEM Assets daarna wijzigt, worden de wijzigingen pas in Brand Portal doorgevoerd als u het element opnieuw publiceert. Met deze functie zorgt u ervoor dat wijzigingen die momenteel worden uitgevoerd, niet beschikbaar zijn in Brand Portal. Alleen goedgekeurde wijzigingen die door een beheerder zijn gepubliceerd, zijn beschikbaar in Brand Portal.

Nadat de replicatie succesvol was, kunt u activa, omslagen, en inzamelingen aan Brand Portal publiceren. Voer de volgende stappen uit om elementen te publiceren naar Brand Portal:

>[!NOTE]
>
>Adobe raadt gefaseerde publicatie aan, bij voorkeur niet tijdens piekuren, zodat de AEM-auteur niet te veel bronnen in beslag neemt.

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
