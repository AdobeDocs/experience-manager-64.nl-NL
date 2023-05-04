---
title: Mappen publiceren naar Brand Portal
description: Leer hoe u middelen publiceert en publiceert naar Brand Portal.
contentOwner: VG
feature: Brand Portal
role: User
exl-id: 6b78124d-4022-452f-8d0f-b667de337bf4
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 30%

---

# Assets publiceren naar Brand Portal {#publish-assets-to-brand-portal}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Als Adobe Experience Manager Assets-beheerder kunt u elementen publiceren naar de [!DNL Experience Manager Assets Brand Portal] -instantie (of de publicatieworkflow plannen naar een latere datum/tijd) voor uw organisatie. Nochtans, moet u eerst gevormd [!DNL Assets] with [!DNL Brand Portal]. Zie voor meer informatie [Configureren [!DNL Assets] with [!DNL Brand Portal]](configure-aem-assets-with-brand-portal.md).

Nadat u een middel publiceert, is het beschikbaar aan gebruikers in Brand Portal.

Als u volgende wijzigingen aanbrengt in het oorspronkelijke element in [!DNL Assets]worden de wijzigingen pas in Brand Portal doorgevoerd als u het element opnieuw publiceert. Met deze functie zorgt u ervoor dat wijzigingen die momenteel worden uitgevoerd, niet beschikbaar zijn in Brand Portal. Alleen goedgekeurde wijzigingen die door een beheerder zijn gepubliceerd, zijn beschikbaar in Brand Portal.

Nadat de replicatie succesvol was, kunt u activa, omslagen, en inzamelingen publiceren aan [!DNL Brand Portal]. Voer de volgende stappen uit om elementen te publiceren naar Brand Portal:

>[!NOTE]
>
>Adobe raadt gefaseerde publicatie aan, bij voorkeur tijdens niet-piekuren, zodat de [!DNL Experience Manager] de auteur neemt niet teveel middelen in beslag.

1. Houd de muisaanwijzer boven de gewenste elementen in de middelenconsole en selecteer **[!UICONTROL Publish]** van de snelle acties.

   U kunt ook de elementen selecteren die u naar Brand Portal wilt publiceren.

   ![publish2bp-2](assets/publish2bp-2.png)

2. Voor het publiceren van de elementen naar Brand Portal zijn de volgende twee opties beschikbaar:
   * [Elementen direct publiceren](#publish-now)
   * [Assets later publiceren](#publish-later)

## Assets nu publiceren {#publish-now}

Voer een van de volgende handelingen uit om de geselecteerde assets naar Brand Portal te publiceren:

* Selecteer **[!UICONTROL Quick Publish]** in de werkbalk. Selecteer vervolgens in het menu **[!UICONTROL Publish to Brand Portal]**.

* Selecteer **[!UICONTROL Manage Publication]** in de werkbalk.

   1. Vervolgens vanaf de **[!UICONTROL Action]** selecteren **[!UICONTROL Publish to Brand Portal]** en van **[!UICONTROL Scheduling]** selecteren **[!UICONTROL Now]**. Tik of klik op **[!UICONTROL Next].**

   2. Within **[!UICONTROL Scope]**, bevestig uw selectie en tik/klik op **[!UICONTROL Publish to Brand Portal]**.

Er verschijnt een bericht waarin wordt aangegeven dat de assets in de wachtrij zijn geplaatst voor publicatie naar Brand Portal. Meld u aan bij de Brand Portal-interface om de gepubliceerde middelen te bekijken.

## Assets later publiceren {#publish-later}

Voer de volgende handelingen uit om het publiceren van de assets naar Brand Portal op een latere datum of tijd te plannen:

1. Als u elementen/mappen hebt geselecteerd om te publiceren, selecteert u **[!UICONTROL Manage Publication]** in de werkbalk bovenaan.
2. Aan **[!UICONTROL Manage Publication]** pagina, selecteert u **[!UICONTROL Publish to Brand Portal]** van **[!UICONTROL Action]** en selecteert u **[!UICONTROL Later]** van **[!UICONTROL Scheduling]**.

   ![publishlaterbp-1](assets/publishlaterbp-1.png)

3. Selecteer een **[!UICONTROL Activation date]** en geef de tijd op. Tik of klik op **[!UICONTROL Next]**.
4. Selecteer een **[!UICONTROL Activation date]** en geef de tijd op. Tik of klik op **[!UICONTROL Next]**.
5. Geef een titel voor de workflow op onder **[!UICONTROL Workflows]**. Tik of klik op **[!UICONTROL Publish Later]**.

   ![publishworkflow](assets/publishworkflow.png)

Meld u nu aan bij Brand Portal om te zien of de gepubliceerde middelen beschikbaar zijn op de interface van Brand Portal.

![bp_631_landing_page](assets/bp_landing_page.png)
