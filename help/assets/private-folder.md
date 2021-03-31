---
title: Persoonlijke map delen
description: Leer hoe u een persoonlijke map maakt in de middelen van de Adobe Experience Manager (AEM) en deze deelt met andere gebruikers en hoe u hun verschillende rechten toekent.
contentOwner: AG
feature: Samenwerking
role: Zakelijke praktiserer
translation-type: tm+mt
source-git-commit: 4acf159ae1b9923a9c93fa15faa38c7f4bc9f759
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 6%

---


# Het delen van de privé omslag {#private-folder-sharing}

In de gebruikersinterface van Adobe Experience Manager (AEM) Assets kunt u een persoonlijke map maken die uitsluitend voor u beschikbaar is. U kunt deze privémap delen met andere gebruikers en hun verschillende rechten toewijzen. Op basis van het machtigingsniveau dat u toewijst, kunnen gebruikers verschillende taken op de map uitvoeren, bijvoorbeeld de middelen in de map weergeven of de elementen bewerken.

1. Tik in de middelenconsole op **[!UICONTROL Create]** op de werkbalk en kies **[!UICONTROL Folder]** in het menu.

   ![chlimage_1-411](assets/chlimage_1-411.png)

1. Voer in het dialoogvenster **[!UICONTROL Add Folder]** een titel en naam (optioneel) voor de map in en selecteer **[!UICONTROL Private]**.

   ![chlimage_1-412](assets/chlimage_1-412.png)

1. Tik of klik op **[!UICONTROL Create]**. Er wordt een privémap gemaakt in de gebruikersinterface.

   ![chlimage_1-413](assets/chlimage_1-413.png)

1. Als u de map wilt delen met andere gebruikers en aan de gebruikers rechten wilt toewijzen, selecteert u de map en klikt of tikt u op het pictogram **[!UICONTROL Properties]** op de werkbalk.

   ![chlimage_1-414](assets/chlimage_1-414.png)

   >[!NOTE]
   >
   >De map is pas zichtbaar voor andere gebruikers als u deze deelt.

1. Selecteer op de pagina Mapeigenschappen een gebruiker in de lijst **[!UICONTROL Add User]**, wijs een rol toe aan de gebruiker in uw persoonlijke map en klik op **[!UICONTROL Add]**.

   ![chlimage_1-415](assets/chlimage_1-415.png)

   >[!NOTE]
   >
   >U kunt verschillende rollen, zoals Editor, Eigenaar of Viewer, toewijzen aan de gebruiker met wie u de map deelt. Als u een rol van de Eigenaar aan de gebruiker toewijst, heeft de gebruiker de voorrechten van Redacteurs op de omslag. Bovendien kan de gebruiker de map met anderen delen. Als u een rol van de Editor toewijst, kan de gebruiker de elementen in uw persoonlijke map bewerken. Als u een Viewer-rol toewijst, kan de gebruiker alleen de elementen in uw persoonlijke map bekijken.

1. Klik op **[!UICONTROL Save]**. Afhankelijk van de rol die u toewijst, krijgt de gebruiker een reeks rechten toegewezen aan uw persoonlijke map wanneer de gebruiker zich aanmeldt bij AEM Assets.
1. Klik **[!UICONTROL Ok]** om het bevestigingsbericht te sluiten.
1. De gebruiker met wie u de map deelt, ontvangt een melding voor delen. Meld u aan bij AEM Assets met de gegevens van de gebruiker om het bericht te bekijken.

   ![chlimage_1-416](assets/chlimage_1-416.png)

1. Tik/klik op het pictogram Melding om de lijst met meldingen te openen.

   ![chlimage_1-417](assets/chlimage_1-417.png)

1. Klik of tik op de vermelding voor de privémap die door de beheerder wordt gedeeld om de map te openen.

>[!NOTE]
>
>Om een privé omslag te kunnen tot stand brengen, vereist u Gelezen en geeft ACL toestemmingen op de ouderomslag uit waaronder u een privé omslag wilt tot stand brengen. Als u geen beheerder bent, worden deze toestemmingen niet toegelaten voor u door gebrek op */content/dam*. In dit geval moet u eerst deze machtigingen voor uw gebruikers-id/groep verkrijgen voordat u probeert persoonlijke mappen te maken of mapinstellingen weer te geven.

