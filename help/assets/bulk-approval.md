---
title: Map-assets en verzamelingen reviewen
description: Stel revisieworkflows in voor elementen in een map of verzameling en deel deze met revisoren of creatieve partners om feedback te zoeken.
contentOwner: AG
feature: Collaboration, Collections
role: User
exl-id: 4c62e0cd-eaa5-456e-85f3-06f7a9f160f5
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '799'
ht-degree: 20%

---

# Map-assets en verzamelingen reviewen {#review-folder-assets-and-collections}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Stel revisieworkflows in voor elementen in een map of verzameling en deel deze met revisoren of creatieve partners om feedback te zoeken.

Met Adobe Experience Manager Assets kunt u een workflow voor ad-hocrevisies instellen voor elementen in een map of verzameling en deze delen met revisoren of creatieve partners om feedback te zoeken.

U kunt de revisiewerkstroom aan een project koppelen of een onafhankelijke revisietaak maken.

Nadat u de middelen hebt gedeeld, kunnen revisoren deze goedkeuren of afwijzen. Meldingen worden in verschillende fasen van de workflow verzonden om beoogde ontvangers op de hoogte te stellen van de voltooiing van verschillende taken. Als u bijvoorbeeld een map of verzameling deelt, ontvangt de controleur een melding dat een map of verzameling is gedeeld voor revisie.

Nadat de controleur de controle heeft voltooid (activa goedkeurt of verwerpt), ontvangt u een bericht van de revisievoltooiing.

## Een revisietaak voor mappen maken {#creating-a-review-task-for-folders}

1. Selecteer in de gebruikersinterface Middelen de map waarvoor u een revisietaak wilt maken.
1. Tik of klik op het pictogram **[!UICONTROL Create Review Task]** op de werkbalk om de pagina **[!UICONTROL Review Task]** te openen. Als u het pictogram niet ziet op de werkbalk, tikt of klikt u op **[!UICONTROL More]** en vervolgens selecteert u het pictogram.

   ![chlimage_1-403](assets/chlimage_1-403.png)

1. (Optioneel) Van de **[!UICONTROL Project]** selecteert u het project waaraan u de revisietaak wilt koppelen. Standaard worden de **[!UICONTROL None]** is geselecteerd. Als u geen project aan de overzichtstaak wilt associëren, behoud deze selectie.

   >[!NOTE]
   >
   >Slechts zijn de projecten waarvoor u de (of hogere) toestemmingen op het niveau van de Redacteur hebt zichtbaar in **[!UICONTROL Projects]** lijst.

1. Voer een naam in voor de revisietaak en selecteer een fiatteur in het menu **[!UICONTROL Assign To]** lijst.

   >[!NOTE]
   >
   >De leden/groepen van het geselecteerde project zijn beschikbaar als fiatteurs in **[!UICONTROL Assign To]** lijst.

1. Voer een beschrijving, de prioriteit van de taak en de vervaldatum voor de controletaak in.

   ![task_details](assets/task_details.png)

1. Voer op het tabblad Geavanceerd een label in dat u wilt gebruiken om de URI te maken.

   ![review_name](assets/review_name.png)

1. Tik of klik op **[!UICONTROL Submit]** en tik of klik vervolgens op **[!UICONTROL Done]** om het bevestigingsbericht te sluiten. Er wordt een bericht voor de nieuwe taak naar de goedkeurder verzonden.
1. Aanmelden bij [!DNL Experience Manager] Middelen als fiatteur en navigeer naar de interface Middelen. Als u elementen wilt goedkeuren, klikt u op **[!UICONTROL Notifications]** en selecteert u vervolgens de revisietaak in de lijst.

   ![melding](assets/notification.png)

1. Controleer op de pagina **[!UICONTROL Review Task]** de details van de revisietaak en tik of klik vervolgens op **[!UICONTROL Review]**.
1. Selecteer assets op de pagina **[!UICONTROL Review Task]** en tik of klik op het pictogram **[!UICONTROL Approve/Reject]** om deze desgewenst goed te keuren of af te wijzen.

   ![review_task](assets/review_task.png)

1. Tik of klik op het pictogram **[!UICONTROL Complete]** op de werkbalk. Voer in het dialoogvenster een opmerking in en tik/klik op  **[!UICONTROL Complete]** ter bevestiging.
1. Navigeer naar de interface Middelen en open de map. De pictogrammen voor de goedkeuringsstatus van de elementen worden weergegeven in zowel de Kaart- als lijstweergave.

   **Kaartweergave**

   ![chlimage_1-404](assets/chlimage_1-404.png)

   **Lijstweergave**

   ![review_status_listview](assets/review_status_listview.png)

## Een revisietaak voor verzamelingen maken {#creating-a-review-task-for-collections}

1. Selecteer op de pagina Verzamelingen de verzameling waarvoor u een revisietaak wilt maken.
1. Tik of klik op het pictogram **[!UICONTROL Create Review Task]** op de werkbalk om de pagina **[!UICONTROL Review Task]** te openen. Als u het pictogram niet ziet op de werkbalk, tikt of klikt u op **[!UICONTROL More]** en vervolgens selecteert u het pictogram.

   ![chlimage_1-405](assets/chlimage_1-405.png)

1. (Optioneel) Van de **[!UICONTROL Project]** selecteert u het project waaraan u de revisietaak wilt koppelen. Standaard worden de **[!UICONTROL None]** is geselecteerd. Als u geen project aan de overzichtstaak wilt associëren, behoud deze selectie.

   >[!NOTE]
   >
   >Slechts zijn de projecten waarvoor u de (of hogere) toestemmingen op het niveau van de Redacteur hebt zichtbaar in **[!UICONTROL Projects]** lijst.

1. Voer een naam in voor de revisietaak en selecteer een fiatteur in het menu **[!UICONTROL Assign To]** lijst.

   >[!NOTE]
   >
   >De leden/groepen van het geselecteerde project zijn beschikbaar als fiatteurs in **[!UICONTROL Assign To]** lijst.

1. Voer een beschrijving, de prioriteit van de taak en de vervaldatum voor de controletaak in.

   ![task_details-collection](assets/task_details-collection.png)

1. Tik of klik op **[!UICONTROL Submit]** en tik of klik vervolgens op **[!UICONTROL Done]** om het bevestigingsbericht te sluiten. Er wordt een bericht voor de nieuwe taak naar de goedkeurder verzonden.
1. Aanmelden bij [!DNL Experience Manager] Middelen als fiatteur en navigeer naar de middelenconsole. Tik op de knop **[!UICONTROL Notifications]** en selecteert u vervolgens de revisietaak in de lijst.
1. Controleer op de pagina **[!UICONTROL Review Task]** de details van de revisietaak en tik of klik vervolgens op **[!UICONTROL Review]**.
1. Alle elementen in de verzameling zijn zichtbaar op de overzichtspagina. Selecteer de elementen en tik op de knop **[!UICONTROL Approve/Reject]** pictogram om elementen goed te keuren of af te wijzen, al naar het geval.

   ![review_task_collection](assets/review_task_collection.png)

1. Tik of klik op het pictogram **[!UICONTROL Complete]** op de werkbalk. Voer in het dialoogvenster een opmerking in en tik/klik op **[!UICONTROL Complete]** ter bevestiging.
1. Navigeer naar de verzamelingsconsole en open de verzameling. De pictogrammen voor de goedkeuringsstatus van de elementen worden weergegeven in zowel de Kaart- als lijstweergave.

   **Kaartweergave**

   ![collection_reviewStatusCard, weergave](assets/collection_reviewstatuscardview.png)

   **Lijstweergave**

   ![collection_reviewstatus listview](assets/collection_reviewstatuslistview.png)
