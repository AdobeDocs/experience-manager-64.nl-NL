---
title: Doelintegratie met ervaringsfragmenten
seo-title: Doelintegratie met ervaringsfragmenten
description: Doelintegratie met ervaringsfragmenten
seo-description: Doelintegratie met ervaringsfragmenten
uuid: 621f57d4-3b8d-49ea-b193-8530c8fbd74e
contentOwner: carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: integration
content-type: reference
discoiquuid: 6911c8e3-b12c-466e-8255-5dcd09557d35
translation-type: tm+mt
source-git-commit: 4e5d3c0ae71f601bcf39fa768c8b5ac86decc1eb
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 0%

---


# Doelintegratie met ervaringsfragmenten{#target-integration-with-experience-fragments}

>[!NOTE]
>
>Deze functionaliteit vereist de toepassing van [AEM 6.4 Service Pack 2 (6.4.2.0)](/help/release-notes/sp-release-notes.md) of later.

U kunt [Experience Fragments](/help/sites-authoring/experience-fragments.md), gemaakt in Adobe Experience Manager (AEM), exporteren naar Adobe Target. Zij kunnen dan als aanbiedingen in de activiteiten van het Doel worden gebruikt, om ervaringen op schaal te testen en te personaliseren. Hiermee kunt u het gebruiksgemak en de kracht van AEM combineren met de krachtige mogelijkheden van Automated Intelligence (AI) en Machine Learning (ML) in Target.

## Vereisten {#prerequisites}

Er zijn verschillende acties vereist:

1. U moet AEM integreren met Doel. Zie [Integreren met Adobe Target](/help/sites-administering/target.md) voor meer informatie.
1. De Fragmenten van de ervaring worden uitgevoerd van de auteursinstantie, zodat moet u [vorm de Verbinding Externalzer](/help/sites-developing/externalizer.md) op de auteursinstantie om ervoor te zorgen dat om het even welke verbindingen voor de publicatieinstantie worden geexternaliseerd.

## Cloudconfiguratie toevoegen {#add-the-cloud-configuration}

Voordat u een fragment exporteert, moet u **Cloud Configuration** for **Adobe Target** toevoegen aan het fragment of de map:

1. Navigeer naar de **Experience Fragments** console.
1. Open **Pagina-eigenschappen** voor de juiste map of het juiste fragment.

   >[!NOTE]
   >
   >Als u de wolkenconfiguratie aan de ouderomslag van het Fragment van de Ervaring toevoegt, wordt de configuratie geërft door alle kinderen.
   >
   >Als u de wolkenconfiguratie aan het Fragment van de Ervaring zelf toevoegt, wordt de configuratie geërft door alle variaties.

1. Selecteer het tabblad **Cloud Services**.

1. Selecteer **Adobe Target** in de vervolgkeuzelijst onder **Configuratie Cloud Service**.
1. Selecteer onder **Adobe Target** de juiste configuratie.

1. **Opslaan en sluiten**.

## Een ervaringsfragment exporteren naar doel {#exporting-an-experience-fragment-to-target}

>[!NOTE]
>
>Voor media-elementen, zoals afbeeldingen, wordt alleen een verwijzing naar Doel geëxporteerd. Het element zelf blijft opgeslagen in AEM Assets en wordt geleverd via de AEM-publicatie-instantie.
>
>Daarom moet het ervaringsfragment, met alle gerelateerde elementen, worden gepubliceerd voordat het naar Target kan worden geëxporteerd.

Een ervaringsfragment exporteren van AEM naar doel (na het opgeven van de cloudconfiguratie):

1. Navigeer naar de Experience Fragment-console.
1. Selecteer het ervaringsfragment dat u naar doel wilt exporteren.

   >[!NOTE]
   >
   >Het moet een variant van het Web van het Fragment van de Ervaring zijn.

1. Tik/klik **Exporteren naar Adobe Target**.

   >[!NOTE]
   >
   >Als het ervaringsfragment al is geëxporteerd, selecteert u **Bijwerken in Adobe Target**.

1. Tik/klik **Exporteren zonder publicatie** of **Publiceren** naar wens.

   >[!NOTE]
   >
   >Als u** Publiceren** selecteert, wordt het ervaringsfragment meteen gepubliceerd en naar Target verzonden.

1. Tik/klik **OK** in het bevestigingsdialoogvenster.

   Het ervaringsfragment moet nu in Doel staan.

>[!NOTE]
>
>U kunt het exporteren ook vanuit de paginaeditor uitvoeren met behulp van vergelijkbare opdrachten in het menu [Pagina-informatie](/help/sites-authoring/author-environment-tools.md#page-information).

## Het gebruiken van uw Fragmenten van de Ervaring in Doel {#using-your-experience-fragments-in-target}

Na het uitvoeren van de voorafgaande taken, toont het ervaringsfragment op de pagina van Aanbiedingen in Doel. Raadpleeg de [specifieke doeldocumentatie](https://experiencecloud.adobe.com/resources/help/en_US/target/target/aem-experience-fragments.html) voor meer informatie over wat u daar kunt bereiken.

## Een ervaringsfragment verwijderen dat al naar doel is geëxporteerd {#deleting-an-experience-fragment-already-exported-to-target}

Als u een ervaringsfragment verwijdert dat al naar Target is geëxporteerd, kan dit problemen veroorzaken als het fragment al in een aanbieding in Target wordt gebruikt. Als u het fragment verwijdert, wordt de aanbieding onbruikbaar omdat de fragmentinhoud door AEM wordt geleverd.

Om dergelijke situaties te voorkomen:

* Als het ervaringsfragment momenteel niet wordt gebruikt in een activiteit, AEM kan de gebruiker het fragment zonder een waarschuwingsbericht verwijderen.
* Als het ervaringsfragment momenteel door een activiteit in Doel wordt gebruikt, wordt de AEM gebruiker een foutbericht gegeven over de mogelijke gevolgen die het verwijderen van het fragment voor de activiteit zal hebben.

   Het foutbericht in AEM belet de gebruiker niet (geforceerd) het ervaringsfragment te verwijderen. Als het ervaringsfragment wordt verwijderd:

   * De aanbieding van het Doel met AEM Fragment van de Ervaring kan ongewenste gedrag tonen

      * De aanbieding wordt waarschijnlijk nog steeds weergegeven, aangezien de Experience Fragment-HTML naar Target werd geduwd
      * Eventuele verwijzingen in het ervaringsfragment werken mogelijk niet correct als middelen waarnaar wordt verwezen ook in AEM worden verwijderd.
   * Uiteraard zijn verdere wijzigingen van het ervaringsfragment niet mogelijk omdat het ervaringsfragment niet meer in AEM bestaat.


