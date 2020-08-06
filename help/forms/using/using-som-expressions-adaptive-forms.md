---
title: SOM-expressies gebruiken in aangepaste formulieren
seo-title: SOM-expressies gebruiken in aangepaste formulieren
description: Leer hoe u SOM-expressies extraheert van een deelvenster met een adaptieve vorm.
seo-description: Leer hoe u SOM-expressies extraheert van een deelvenster met een adaptieve vorm.
uuid: 4bc80e2a-3563-48a3-996d-021b701bc2ee
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: develop
discoiquuid: 7dff7ef2-80d1-434a-b9b0-ac6654736602
translation-type: tm+mt
source-git-commit: 0797eeae57ac5a9676c6d308eaf2aaffab999d18
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 0%

---


# SOM-expressies gebruiken in aangepaste formulieren {#using-som-expressions-in-adaptive-forms}

Aangepaste formulieren worden gemodelleerd als AEM pagina die wordt weergegeven als JCR-inhoudsstructuur in AEM opslagplaats. Het belangrijkste element van de inhoudsstructuur is guideContainer-knooppunt. Onder guideContainer, is er rootPanel die genestelde paneel en gebieden kan bevatten.

U kunt een scriptobjectmodel (SOM) gebruiken om te verwijzen naar waarden, eigenschappen en methoden binnen een bepaald DOM (Document Object Model). Een DOM organiseert de geheugenvoorwerpen en de eigenschappen in een boomhiërarchie. Een SOM-expressie verwijst naar Velden/Elementen en deelvensters tekenen.

In de volgende afbeelding ziet u een knooppuntstructuur waarnaar een adaptief formulier wordt geconverteerd wanneer u componenten aan een formulier toevoegt. U kunt bijvoorbeeld een deelvenster toevoegen aan het hoofddeelvenster en een keuzerondje in het deelvenster dat tijdens de runtime wordt getransformeerd naar DOM. De SOM-expressie voor het veld keuzerondje in adaptieve vorm wordt opgegeven als `guide[0].guide1[0].guideRootPanel[0].panel1[0].radiobutton[0]`.

![DOM-structuur](assets/hierarchy-1.png)

Een SOM-expressie voor een element in een adaptieve vorm wordt vooraf ingesteld door `guide[0].guide1[0]`. De positie van een component in de hiërarchie van de knoopstructuur wordt gebruikt om zijn uitdrukking SOM af te leiden.

![DOM-structuur met twee keuzerondjes](assets/hierarchy_radio_button.png)

De SOM-expressie verandert wanneer u de positie van de keuzerondjes in het adaptieve formulier wijzigt. In de ontwerpmodus kunt u de SOM-expressie van een veld of element in AEM Forms weergeven met de optie SOM-expressie weergeven. De optie wordt weergegeven in het deelvenster en wanneer u met de rechtermuisknop op het veld of element klikt.

![SOM-expressies extraheren in een adaptieve vorm](assets/som-expressions.png)

In deelvensters hebt u toegang tot de functie via de werkbalk van het deelvenster. Met deze functie kunnen auteurs van adaptieve formulieren scripts schrijven.

![SOM-expressies extraheren met de werkbalk van het deelvenster](assets/som-expression.png)

Sommige API&#39;s die in [GuideBridge](https://helpx.adobe.com/aem-forms/6/javascript-api/GuideBridge.md) worden vermeld, gebruiken de SOM-expressie van een element. Als u bijvoorbeeld een bepaald veld in een adaptieve vorm de focus wilt geven, geeft u de overeenkomstige SOM-expressie door aan de `getFocus`API in `guideBridge`.

