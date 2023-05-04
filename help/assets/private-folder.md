---
title: Persoonlijke map delen
description: Leer hoe u een persoonlijke map maakt in de Adobe Experience Manager Assets en deze deelt met andere gebruikers en hoe u deze map verschillende rechten toekent.
contentOwner: AG
feature: Collaboration
role: User
exl-id: b6aa3cba-4085-47ac-a249-7461baee2a00
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 5%

---

# Persoonlijke map delen {#private-folder-sharing}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

U kunt een persoonlijke map maken in de gebruikersinterface van Adobe Experience Manager Assets die exclusief voor u beschikbaar is. U kunt deze privémap delen met andere gebruikers en hun verschillende rechten toewijzen. Op basis van het machtigingsniveau dat u toewijst, kunnen gebruikers verschillende taken op de map uitvoeren, bijvoorbeeld de middelen in de map weergeven of de elementen bewerken.

1. Tik/klik in de middelenconsole op **[!UICONTROL Create]** op de werkbalk en kies vervolgens **[!UICONTROL Folder]** in het menu.

   ![chlimage_1-411](assets/chlimage_1-411.png)

1. In de **[!UICONTROL Add Folder]** voert u een titel en naam (optioneel) voor de map in en selecteert u **[!UICONTROL Private]**.

   ![chlimage_1-412](assets/chlimage_1-412.png)

1. Tik of klik op **[!UICONTROL Create]**. Er wordt een privémap gemaakt in de gebruikersinterface.

   ![chlimage_1-413](assets/chlimage_1-413.png)

1. Als u de map wilt delen met andere gebruikers en aan de gebruikers rechten wilt toewijzen, selecteert u de map en klikt of tikt u op het pictogram **[!UICONTROL Properties]** op de werkbalk.

   ![chlimage_1-414](assets/chlimage_1-414.png)

   >[!NOTE]
   >
   >De map is pas zichtbaar voor andere gebruikers als u deze deelt.

1. Selecteer op de pagina Mapeigenschappen een gebruiker in het menu **[!UICONTROL Add User]** een rol toewijzen aan de gebruiker in uw persoonlijke map en klikken **[!UICONTROL Add]**.

   ![chlimage_1-415](assets/chlimage_1-415.png)

   >[!NOTE]
   >
   >U kunt verschillende rollen, zoals Editor, Eigenaar of Viewer, toewijzen aan de gebruiker met wie u de map deelt. Als u een rol van de Eigenaar aan de gebruiker toewijst, heeft de gebruiker de voorrechten van Redacteurs op de omslag. Bovendien kan de gebruiker de map met anderen delen. Als u een rol van de Editor toewijst, kan de gebruiker de elementen in uw persoonlijke map bewerken. Als u een Viewer-rol toewijst, kan de gebruiker alleen de elementen in uw persoonlijke map bekijken.

1. Klik op **[!UICONTROL Save]**. Afhankelijk van de rol die u toewijst, wordt aan de gebruiker een reeks rechten toegewezen aan uw persoonlijke map wanneer de gebruiker zich aanmeldt bij [!DNL Experience Manager] Elementen.
1. Klikken **[!UICONTROL Ok]** om het bevestigingsbericht te sluiten.
1. De gebruiker met wie u de map deelt, ontvangt een melding voor delen. Aanmelden bij [!DNL Experience Manager] Hier kunt u de referenties van de gebruiker zien.

   ![chlimage_1-416](assets/chlimage_1-416.png)

1. Tik/klik op het pictogram Melding om de lijst met meldingen te openen.

   ![chlimage_1-417](assets/chlimage_1-417.png)

1. Klik of tik op de vermelding voor de privémap die door de beheerder wordt gedeeld om de map te openen.

>[!NOTE]
>
>Om een privé omslag te kunnen tot stand brengen, vereist u Gelezen en geeft ACL toestemmingen op de ouderomslag uit waaronder u een privé omslag wilt tot stand brengen. Als u geen beheerder bent, worden deze machtigingen standaard niet voor u ingeschakeld */content/dam*. In dit geval moet u eerst deze machtigingen voor uw gebruikers-id/groep verkrijgen voordat u probeert persoonlijke mappen te maken of mapinstellingen weer te geven.
