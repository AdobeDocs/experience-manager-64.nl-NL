---
title: Uw digitale middelen inchecken en uitchecken voor bewerking
description: Leer hoe u middelen kunt uitchecken om deze te bewerken en weer in te checken nadat de wijzigingen zijn voltooid.
contentOwner: AG
feature: Asset Management
role: User
exl-id: 0c79ed42-0acd-426e-8e14-412bb4117585
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 3%

---

# Bestanden in elementen inchecken en uitchecken {#check-in-and-check-out-files-in-assets}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Met Adobe Experience Manager Assets kunt u elementen uitchecken om ze te bewerken en weer inchecken nadat u de wijzigingen hebt aangebracht. Nadat u een element hebt uitgecheckt, kunt u het element alleen bewerken, annoteren, publiceren, verplaatsen of verwijderen. Als u een element uitcheckt, vergrendelt u het element. Andere gebruikers kunnen geen van deze bewerkingen op het element uitvoeren totdat u het element weer incheckt bij [!DNL Experience Manager] Elementen. Ze kunnen echter wel de metagegevens van het vergrendelde element wijzigen.

Om activa te kunnen uitchecken of inchecken, hebt u schrijftoegang op hen nodig.

Met deze functie voorkomt u dat andere gebruikers de wijzigingen overschrijven die door een auteur zijn aangebracht en waarbij meerdere gebruikers samenwerken aan het bewerken van workflows in verschillende teams.

## Elementen uitchecken {#checking-out-assets}

1. Selecteer in de interface Elementen het element dat u wilt uitchecken. U kunt ook meerdere elementen selecteren om uit te checken.

   ![chlimage_1-468](assets/chlimage_1-468.png)

1. Klik/tik op de werkbalk op de knop **[!UICONTROL Checkout]** pictogram.

   ![chlimage_1-469](assets/chlimage_1-469.png)

   Waarnemen dat de **[!UICONTROL Checkout]** schakelen tussen pictogrammen **[!UICONTROL Checkin]** met open slot.

   ![chlimage_1-470](assets/chlimage_1-470.png)

   Meld u aan als een andere gebruiker om te controleren of andere gebruikers het uitgecheckte element kunnen bewerken. Er verschijnt een vergrendelingspictogram op de miniatuur van het element dat u hebt uitgecheckt.

   ![chlimage_1-471](assets/chlimage_1-471.png)

   Selecteer het element. Op de werkbalk worden geen opties weergegeven waarmee u elementen kunt bewerken, notities kunt aanbrengen, kunt publiceren of verwijderen.

   ![chlimage_1-472](assets/chlimage_1-472.png)

   U kunt echter op de knop **[!UICONTROL View Properties]** pictogram om de metagegevens voor het vergrendelde element te bewerken.

1. Klik of tik op het pictogram Bewerken om het element in de bewerkingsmodus te openen.

   ![chlimage_1-473](assets/chlimage_1-473.png)

1. Bewerk het element en sla de wijzigingen op. Snijd bijvoorbeeld de afbeelding bij en sla deze op.

   ![chlimage_1-474](assets/chlimage_1-474.png)

   U kunt er ook voor kiezen om het element te annoteren of te publiceren.

1. Selecteer de bewerkte asset in de asset-interface en klik of tik op het pictogram **[!UICONTROL Checkin]** op de werkbalk.

   ![chlimage_1-475](assets/chlimage_1-475.png)

   Het gewijzigde element is ingecheckt bij [!DNL Assets] en is beschikbaar voor andere gebruikers om te bewerken.

## Geforceerd inchecken {#forced-check-in}

Beheerders kunnen elementen inchecken die door andere gebruikers zijn uitgecheckt.

1. Aanmelden bij [!DNL Assets] als beheerder.
1. Selecteer in de interface Elementen een of meer elementen die door andere gebruikers zijn uitgecheckt.

   ![chlimage_1-476](assets/chlimage_1-476.png)

1. Klik/tik op de werkbalk op de knop **[!UICONTROL Release Lock]** pictogram. Het element is ingecheckt en kan worden bewerkt aan andere gebruikers.

   ![chlimage_1-477](assets/chlimage_1-477.png)
