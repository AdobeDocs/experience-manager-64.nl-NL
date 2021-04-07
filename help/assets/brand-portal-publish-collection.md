---
title: Verzamelingen publiceren naar Brand Portal
description: Leer hoe u verzamelingen publiceert en publiceert naar Brand Portal.
contentOwner: VG
feature: Brand Portal
role: Business Practitioner
exl-id: c2c6759e-f763-405e-9e45-5a90b9d32df2
translation-type: tm+mt
source-git-commit: bd94d3949f0117aa3e1c9f0e84f7293a5d6b03b4
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 22%

---

# Verzamelingen publiceren naar Brand Portal {#publish-collections-to-brand-portal}

Als beheerder van Adobe Experience Manager-middelen (AEM) kunt u verzamelingen publiceren naar de AEM Assets Brand Portal-instantie voor uw organisatie. U moet echter eerst AEM Assets integreren met Brand Portal. Zie [AEM Assets configureren met Brand Portal](configure-aem-assets-with-brand-portal.md) voor meer informatie.

Als u verdere wijzigingen in de originele inzameling in AEM Assets aanbrengt, worden de veranderingen niet weerspiegeld in het Portaal van het Merk tot u de inzameling opnieuw publiceert. Dit kenmerk zorgt ervoor dat wijzigingen in onderhanden werk niet beschikbaar zijn in Brand Portal. Alleen goedgekeurde wijzigingen die door een beheerder zijn gepubliceerd, zijn beschikbaar in Brand Portal.

>[!NOTE]
>
>Contentfragmenten kunnen niet naar Brand Portal worden gepubliceerd. Als u daarom inhoudsfragment(en) selecteert op AEM-auteur, is de actie **[Publiceren naar Brand Portal]** niet beschikbaar.
>
>Als verzamelingen met inhoudsfragmenten van AEM-auteur naar Brand Portal worden gepubliceerd, wordt alle inhoud van de map behalve inhoudsfragmenten gerepliceerd naar de Brand Portal-interface.

## Een verzameling publiceren naar Brand Portal {#publish-a-collection-to-brand-portal}

1. Tik in de gebruikersinterface van AEM Assets op het AEM. Ga vervolgens naar **[!UICONTROL Assets > Collections]** op de pagina **[!UICONTROL Navigation]**.
2. Van de console van Inzamelingen, selecteer de inzameling u aan het Portaal van de Merk wilt publiceren.

   ![select_collection](assets/select_collection.png)

3. Tik/klik op **[!UICONTROL Publish to Brand Portal]** op de werkbalk.

   ![publish_to_bp_icon](assets/publish_to_bp_icon.png)

4. Tik/klik op **[!UICONTROL Publish]** in het bevestigingsvenster.
5. Sluit het bevestigingsbericht.
6. Meld u als beheerder aan bij Brand Portal. De gepubliceerde verzameling is beschikbaar in de Collections-console.

   ![published_collection](assets/published_collection.png)

## De publicatie van verzamelingen ongedaan maken {#unpublish-collections}

U kunt de publicatie van verzamelingen die u publiceert van AEM Assets naar Brand Portal ongedaan maken. Nadat u de publicatie van de oorspronkelijke verzameling ongedaan hebt gemaakt, is de kopie ervan niet meer beschikbaar voor gebruikers van het Brand Portal.

1. Selecteer in de Collections-console van uw AEM Assets-instantie de verzameling die u wilt verwijderen.

   ![select_collection-1](assets/select_collection-1.png)

2. Tik op of klik op het pictogram **[!UICONTROL Remove from Brand Portal]** op de werkbalk.

   ![remove_from_bp_icon](assets/remove_from_bp_icon.png)

3. Tik/klik op **[!UICONTROL Unpublish]** in het dialoogvenster.
4. Sluit het bevestigingsbericht. De verzameling wordt verwijderd uit de Brand Portal-interface.
