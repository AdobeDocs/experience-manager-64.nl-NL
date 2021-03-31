---
title: Slimme tags beheren
description: Onnauwkeurige slimme tags bijwerken of verwijderen om de relevantie van tags te verbeteren
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
uuid: fd3eedf0-f222-45bf-aac7-90da6b7b7087
contentOwner: AG
discoiquuid: 3394b56a-3054-419b-9547-5740f8c35071
feature: Slimme tags,Tags,Zoeken
role: Zakelijke praktiserer
translation-type: tm+mt
source-git-commit: 29e3cd92d6c7a4917d7ee2aa8d9963aa16581633
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 2%

---


# Slimme tags beheren {#managing-smart-tags}

U kunt slimme tags beheren om eventuele onjuiste tags te verwijderen die aan uw merkafbeeldingen zijn toegewezen, zodat alleen de meest relevante tags worden weergegeven.

Als u slimme tags modereert, kunt u zoekopdrachten op basis van tags naar afbeeldingen verder verfijnen door ervoor te zorgen dat de afbeelding in de zoekresultaten wordt weergegeven voor de meest relevante tags. In feite wordt hiermee de kans dat niet-verwante afbeeldingen in zoekresultaten worden weergegeven, verkleind.

U kunt ook een hogere rangorde aan een tag toewijzen om de relevantie ervan ten opzichte van een afbeelding te vergroten. Door een tag voor een afbeelding te promoten, neemt de kans toe dat de afbeelding in de zoekresultaten wordt weergegeven wanneer een zoekopdracht op basis van de desbetreffende tag wordt uitgevoerd.

1. Zoek in het vak Universeel zoeken naar elementen op basis van een tag.
1. Inspect de zoekresultaten om een afbeelding te identificeren die je niet relevant vindt voor je zoekopdracht.
1. Selecteer de afbeelding en klik/tik op het pictogram **[!UICONTROL Manage Tags]** op de werkbalk.
1. Controleer de tags op de pagina **[!UICONTROL Manage Tags]**. Als u niet wilt dat de afbeelding wordt doorzocht op basis van een specifieke tag, selecteert u de tag en klikt of tikt u op het pictogram **[!UICONTROL Delete]** op de werkbalk. U kunt ook op het symbool (**[!UICONTROL X]**) naast het label klikken of tikken.
1. Als u een hogere rangorde aan een tag wilt toewijzen, selecteert u de tag en klikt of tikt u op het pictogram **[!UICONTROL Promote]** op de werkbalk. De tag die u promoot, wordt verplaatst naar de sectie **[!UICONTROL Tags]**.
1. Klik of tik op **[!UICONTROL Save]** en klik of tik vervolgens op **[!UICONTROL OK]** om het dialoogvenster Succes te sluiten.
1. Navigeer naar de pagina met eigenschappen voor de afbeelding. Let erop dat de tag die u hebt bevorderd een grote relevantie krijgt en daarom hoger wordt weergegeven in de zoekresultaten.

## AEM zoekresultaten begrijpen met slimme tags {#understand-search-results-with-smart-tags}

Standaard combineert AEM zoekopdracht de zoektermen met een `AND`-component. Het gebruik van slimme tags verandert dit standaardgedrag niet. Als u slimme tags gebruikt, wordt een extra `OR`-component toegevoegd om een zoekterm in de lijst te zoeken, past u slimme tags toe. U kunt bijvoorbeeld zoeken naar `woman running`. Elementen met alleen het trefwoord `woman` of `running` in de metagegevens worden niet standaard in de zoekresultaten weergegeven. Een element dat is gecodeerd met `woman` of `running` met slimme tags, wordt echter wel weergegeven in een dergelijke zoekquery. De zoekresultaten zijn dus een combinatie van:

* elementen met zowel trefwoorden als `woman` en `running` in de metagegevens.
* elementen die zijn gelabeld met een van de trefwoorden.

De zoekresultaten die overeenkomen met alle zoektermen in metagegevensvelden worden eerst weergegeven, gevolgd door de zoekresultaten die overeenkomen met een van de zoektermen in de slimme tags. In het bovenstaande voorbeeld is de weergavevolgorde van zoekresultaten bij benadering:

1. overeenkomend met `woman running` in de verschillende metagegevensvelden.
1. overeenkomsten van `woman running` in slimme markeringen.
1. overeenkomende met `woman` of `running` in slimme tags.
