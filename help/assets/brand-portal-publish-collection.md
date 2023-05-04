---
title: Verzamelingen publiceren naar Brand Portal
description: Leer hoe u verzamelingen publiceert en publiceert naar Brand Portal.
contentOwner: VG
feature: Brand Portal
role: User
exl-id: c2c6759e-f763-405e-9e45-5a90b9d32df2
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 21%

---

# Verzamelingen publiceren naar Brand Portal {#publish-collections-to-brand-portal}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Als Adobe Experience Manager Assets-beheerder kunt u verzamelingen publiceren naar de [!DNL Experience Manager Assets Brand Portal] -instantie voor uw organisatie. U moet echter eerst Middelen integreren met Brand Portal. Zie [ Assets configureren met Brand Portal](configure-aem-assets-with-brand-portal.md) voor meer informatie.

Als u de oorspronkelijke verzameling in Elementen wijzigt, worden de wijzigingen pas in Brand Portal doorgevoerd als u de verzameling opnieuw publiceert. Dit kenmerk zorgt ervoor dat wijzigingen in onderhanden werk niet beschikbaar zijn in Brand Portal. Alleen goedgekeurde wijzigingen die door een beheerder zijn gepubliceerd, zijn beschikbaar in Brand Portal.

>[!NOTE]
>
>Contentfragmenten kunnen niet naar Brand Portal worden gepubliceerd. Als u daarom inhoudsfragment(en) selecteert op [!DNL Experience Manager] Auteur, vervolgens **[Publiceren naar Brand Portal]** actie is niet beschikbaar.
>
>Als verzamelingen met inhoudsfragmenten worden gepubliceerd vanuit [!DNL Experience Manager] Auteur naar Brand Portal, dan wordt alle inhoud van de map behalve inhoudsfragmenten gerepliceerd naar de Brand Portal-interface.

## Een verzameling publiceren naar Brand Portal {#publish-a-collection-to-brand-portal}

1. Tik in de interface Middelen op de knop [!DNL Experience Manager] logo. Ga vervolgens naar **[!UICONTROL Assets > Collections]** van de **[!UICONTROL Navigation]** pagina.
2. Selecteer in de Collections-console de verzameling die u naar Brand Portal wilt publiceren.

   ![select_collection](assets/select_collection.png)

3. Tik/klik op de werkbalk **[!UICONTROL Publish to Brand Portal]**.

   ![publish_to_bp_icon](assets/publish_to_bp_icon.png)

4. Tik/klik in het bevestigingsdialoogvenster op **[!UICONTROL Publish]**.
5. Sluit het bevestigingsbericht.
6. Meld u als beheerder aan bij Brand Portal. De gepubliceerde verzameling is beschikbaar in de Collections-console.

   ![published_collection](assets/published_collection.png)

## De publicatie van verzamelingen ongedaan maken {#unpublish-collections}

U kunt de publicatie van verzamelingen die u van Middelen naar Brand Portal publiceert, ongedaan maken. Nadat u de publicatie van de oorspronkelijke verzameling hebt ongedaan gemaakt, is de kopie ervan niet meer beschikbaar voor Brand Portal-gebruikers.

1. Van de console van Inzamelingen van uw [!DNL Assets] en selecteer de verzameling waarvan u de publicatie ongedaan wilt maken.

   ![select_collection-1](assets/select_collection-1.png)

2. Tik op de werkbalk of klik op de knop **[!UICONTROL Remove from Brand Portal]** pictogram.

   ![remove_from_bp_icon](assets/remove_from_bp_icon.png)

3. Tik/klik in het dialoogvenster op **[!UICONTROL Unpublish]**.
4. Sluit het bevestigingsbericht. De verzameling wordt verwijderd uit de Brand Portal-interface.
