---
title: Richtlijnen voor training voor Smart Content Service
description: De AI-service trainen om slimme tags toe te passen op elementen
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
uuid: 1c011496-be6e-470b-9da8-48db8c6d1108
contentOwner: AG
discoiquuid: a5aab094-8b2d-4a23-890f-be6f9e5137bd
feature: Tagging,Metadata,Smart Tags
role: User
exl-id: 14241f8d-fd0b-4bcf-b2bb-1d0e52bf7748
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 11%

---

# Richtlijnen voor training voor Smart Content Service {#smart-content-service-training-guidelines}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

De Smart Content Service vereist dat de trainingsafbeeldingen aan bepaalde richtlijnen voldoen om uw merkafbeeldingen effectief te kunnen labelen.

## Richtsnoeren voor opleiding {#guidelines-for-training}

Voor de beste resultaten moeten de afbeeldingen in de trainingsset voldoen aan de volgende richtlijnen:

**Hoeveelheid en grootte:****Minimaal 30 afbeeldingen per tag**. Minimaal 500 pixels aan de langere zijde.

**Coherentie**: Afbeeldingen voor een tag moeten visueel op elkaar lijken.

Het is bijvoorbeeld geen goed idee om al deze afbeeldingen van tags te voorzien *mijn-feestje* (voor training) omdat ze niet op elkaar lijken.

![Illustratieve afbeeldingen ter illustratie van de richtlijnen voor training](assets/do-not-localize/coherence.png)

**Dekking**: De beelden in de training moeten voldoende uiteenlopend zijn. Het is de bedoeling om een paar maar redelijk uiteenlopende voorbeelden te geven, zodat [!DNL Experience Manager] leert u te focussen op de juiste zaken . Als u dezelfde tag toepast op visueel verschillende afbeeldingen, moet u ten minste vijf voorbeelden van elke soort opnemen.

Bijvoorbeeld voor de tag *model-down-pose* neemt u meer trainingsafbeeldingen op die lijken op de gemarkeerde afbeelding hieronder, zodat u vergelijkbare afbeeldingen tijdens het labelen nauwkeuriger kunt identificeren.

![Illustratieve afbeeldingen ter illustratie van de richtlijnen voor training](assets/do-not-localize/coverage_1.png)

**Vervorming/obstructie**: De dienst rijdt beter op beelden die minder afleiding hebben (vooraanstaande achtergronden, niet-verwante begeleiding, zoals voorwerpen/personen met het hoofdonderwerp).

Bijvoorbeeld voor de tag *casual-shoe* Het tweede imago is geen goede kandidaat voor opleiding.

![Illustratieve afbeeldingen ter illustratie van de richtlijnen voor training](assets/do-not-localize/distraction.png)

**Volledigheid:** Als een afbeelding in aanmerking komt voor meer dan één tag, voegt u alle relevante tags toe voordat u de afbeelding opneemt voor training. Als het bijvoorbeeld gaat om tags zoals *regenjas* en *modelweergave*, voegt u beide tags toe aan de desbetreffende asset voordat u dit opneemt voor training.

![Illustratieve afbeeldingen ter illustratie van de richtlijnen voor training](assets/do-not-localize/completeness.png)

## Beperkingen {#limitations}

Verbeterde slimme tags zijn gebaseerd op leermodellen van merkafbeeldingen en hun tags. Deze modellen zijn niet altijd perfect bij het identificeren van tags. De huidige versie van de Smart Content Service heeft de volgende beperkingen:

* Kan subtiele verschillen in afbeeldingen niet herkennen. Bijvoorbeeld dunne en standaard gemonteerde hemden.
* Kan geen tags identificeren op basis van kleine patronen/delen van een afbeelding. Bijvoorbeeld logo&#39;s op T-shirts.
* Tags worden ondersteund in de landinstellingen die [!DNL Experience Manager] wordt ondersteund in. Voor een lijst met talen raadpleegt u [Opmerkingen bij de release Smart Content Services](/help/release-notes/smart-content-service-release-notes.md).

Als u wilt zoeken naar elementen met slimme tags (normaal of uitgebreid), gebruikt u de vanuit de gebruikersinterface uitgevoerde zoekopdracht (zoeken in volledige tekst). Er is geen afzonderlijke zoekvoorspelling voor slimme tags.

>[!NOTE]
>
>Of de Smart Content Service uw tags kan trainen en deze op andere afbeeldingen kan toepassen, hangt af van de kwaliteit van de afbeeldingen die u voor de training gebruikt.
>
>Voor de beste resultaten raadt Adobe u aan visueel vergelijkbare afbeeldingen te gebruiken om de service voor elke tag op te leiden.
