---
title: De geglobaliseerde sitestructuur in 'We' uitproberen.Handelsversie
seo-title: Trying out the Globalized Site Structure in We.Retail
description: De geglobaliseerde sitestructuur in 'We' uitproberen.Handelsversie
seo-description: null
uuid: 5e5a809d-578f-4171-8226-cb65aa995754
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: best-practices
discoiquuid: d674458c-d5f3-4dee-a673-b0777c02ad30
exl-id: e26e8e58-3aa4-4e7a-ac9e-f274c4af0041
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 0%

---

# De geglobaliseerde sitestructuur in &#39;We&#39; uitproberen.Handelsversie{#trying-out-the-globalized-site-structure-in-we-retail}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

We.Retail is gebouwd met een geglobaliseerde sitestructuur die een taalstramien biedt die live kan worden gekopieerd naar landspecifieke websites. Alles is ingesteld op een &#39;out-of-the-box&#39; zodat u kunt experimenteren met deze structuur en de ingebouwde vertaalmogelijkheden.

## Uitproberen {#trying-it-out}

1. De siteconsole openen vanuit **Algemene navigatie -> Sites**.
1. Schakelaar aan kolommening (als niet reeds actief) en selecteer Wij.Retail. Neem nota van de voorbeeldlandstructuur met Zwitserland, de Verenigde Staten, Frankrijk, enz., langs de taalmeesters.

   ![chlimage_1-87](assets/chlimage_1-87.png)

1. Selecteer Zwitserland en bekijk de taalwortels voor de talen van dat land. Er is nog geen inhoud onder deze wortels.

   ![chlimage_1-88](assets/chlimage_1-88.png)

1. Ga naar de lijstweergave en controleer of de taalkopieën voor de landen allemaal live kopieën zijn.

   ![chlimage_1-89](assets/chlimage_1-89.png)

1. Ga terug naar de kolomweergave, klik op de Master taal en bekijk de master taalbasis met inhoud. Alleen Engels heeft inhoud.

   Wij.Retail wordt niet geleverd met vertaalde inhoud, maar de structuur en configuratie zijn zodanig ingesteld dat u de vertaalservices kunt demonstreren.

   ![chlimage_1-90](assets/chlimage_1-90.png)

1. Selecteer de Master taal en open het dialoogvenster **Verwijzingen** rail in de locatieconsole en selecteer **Taalkopieën**.

   ![chlimage_1-91](assets/chlimage_1-91.png)

1. Schakel het selectievakje naast het **Taalkopieën** om alle taalkopieën te selecteren. In de **Taalkopieën bijwerken** van de spoorstaaf de optie om **Een nieuw vertaalproject maken**. Geef een naam op voor het project en klik op **Bijwerken**.

   ![chlimage_1-92](assets/chlimage_1-92.png)

1. Voor elke taalvertaling wordt een project gemaakt. Bekijk ze onder **Navigatie -> Projecten**.

   ![chlimage_1-93](assets/chlimage_1-93.png)

1. Klik op het Duits om de details van het vertaalproject te bekijken. De status is in **Concept**. Als u de vertaling wilt starten met de vertaalservice van Microsoft, klikt u op het chevron naast de **Vertaaltaak** kop en selecteer **Start**.

   ![chlimage_1-94](assets/chlimage_1-94.png)

1. Het vertaalproject begint. Klik op de ovaal onder aan de kaart met het label Vertaaltaak om de details weer te geven. Pagina&#39;s met de status **Gereed voor revisie** zijn al vertaald door de vertaaldienst.

   ![chlimage_1-95](assets/chlimage_1-95.png)

1. Een van de pagina&#39;s in de lijst selecteren en vervolgens **Voorvertoning in sites** opent u de vertaalde pagina in de pagina-editor op de werkbalk.

   ![chlimage_1-96](assets/chlimage_1-96.png)

>[!NOTE]
>
>Deze procedure heeft de ingebouwde integratie met Microsoft-machinevertaling aangetoond. Met de [AEM Omzettingsintegratiekader](/help/sites-administering/translation.md), kunt u met vele standaardvertaaldiensten integreren om de vertaling van AEM te ordenen.

## Aanvullende informatie {#further-information}

Raadpleeg het ontwerpdocument voor meer informatie [Inhoud vertalen voor meertalige sites](/help/sites-administering/translation.md) voor volledige technische details.
