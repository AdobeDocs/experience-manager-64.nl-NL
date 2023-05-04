---
title: Slimme tags beheren
description: Onnauwkeurige slimme tags bijwerken of verwijderen om de relevantie van tags te verbeteren
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
uuid: fd3eedf0-f222-45bf-aac7-90da6b7b7087
contentOwner: AG
discoiquuid: 3394b56a-3054-419b-9547-5740f8c35071
feature: Smart Tags,Tagging,Search
role: User
exl-id: 05f43e43-ac72-4ab1-a373-687c137d2bed
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 2%

---

# Slimme tags beheren {#managing-smart-tags}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

U kunt slimme tags beheren om eventuele onjuiste tags te verwijderen die aan uw merkafbeeldingen zijn toegewezen, zodat alleen de meest relevante tags worden weergegeven.

Als u slimme tags modereert, kunt u zoekopdrachten op basis van tags naar afbeeldingen verder verfijnen door ervoor te zorgen dat de afbeelding in de zoekresultaten wordt weergegeven voor de meest relevante tags. In feite wordt hiermee de kans dat niet-verwante afbeeldingen in zoekresultaten worden weergegeven, verkleind.

U kunt ook een hogere rangorde aan een tag toewijzen om de relevantie ervan ten opzichte van een afbeelding te vergroten. Door een tag voor een afbeelding te promoten, neemt de kans toe dat de afbeelding in de zoekresultaten wordt weergegeven wanneer een zoekopdracht op basis van de desbetreffende tag wordt uitgevoerd.

1. Zoek in het vak Universeel zoeken naar elementen op basis van een tag.
1. Inspect de zoekresultaten om een afbeelding te identificeren die je niet relevant vindt voor je zoekopdracht.
1. Selecteer de afbeelding en klik op de knop **[!UICONTROL Manage Tags]** op de werkbalk.
1. Van de **[!UICONTROL Manage Tags]** pagina, controleert u de tags. Als u niet wilt dat de afbeelding wordt doorzocht op basis van een specifieke tag, selecteert u de tag en klikt of tikt u op de tag **[!UICONTROL Delete]** op de werkbalk. U kunt ook op de knop klikken of erop tikken (**[!UICONTROL X]**) die naast het label wordt weergegeven.
1. Als u een hogere rang aan een tag wilt toewijzen, selecteert u de tag en klikt of tikt u op de tag **[!UICONTROL Promote]** op de werkbalk. De tag die u promoot, wordt verplaatst naar de **[!UICONTROL Tags]** sectie.
1. Klik of tik op **[!UICONTROL Save]** en klik of tik vervolgens op **[!UICONTROL OK]** om het dialoogvenster Succes te sluiten.
1. Navigeer naar de pagina met eigenschappen voor de afbeelding. Let erop dat de tag die u hebt bevorderd een grote relevantie krijgt en daarom hoger wordt weergegeven in de zoekresultaten.

## Begrijpen [!DNL Experience Manager] zoekresultaten met slimme tags {#understand-search-results-with-smart-tags}

Standaard, [!DNL Experience Manager] zoektermen worden gecombineerd met een `AND` clausule. Het gebruik van slimme tags verandert dit standaardgedrag niet. Met slimme tags voegt u een extra `OR` gebruiken om een zoekterm in de zoektermen te zoeken, slimme tags toe. Kijk bijvoorbeeld naar `woman running`. Middelen met alleen `woman` of alleen `running` trefwoorden in de metagegevens worden niet standaard in de zoekresultaten weergegeven. Een element dat echter is gelabeld met een van de `woman` of `running` het gebruik van slimme tags wordt weergegeven in een dergelijke zoekopdracht. De zoekresultaten zijn dus een combinatie van:

* elementen met beide trefwoorden, `woman` en `running` in de metagegevens.
* elementen die zijn gelabeld met een van de trefwoorden.

De zoekresultaten die overeenkomen met alle zoektermen in metagegevensvelden worden eerst weergegeven, gevolgd door de zoekresultaten die overeenkomen met een van de zoektermen in de slimme tags. In het bovenstaande voorbeeld is de weergavevolgorde van zoekresultaten bij benadering:

1. overeenkomend met `woman running` in de verschillende metagegevensvelden.
1. overeenkomend met `woman running` in slimme tags.
1. overeenkomend met `woman` of van `running` in slimme tags.
