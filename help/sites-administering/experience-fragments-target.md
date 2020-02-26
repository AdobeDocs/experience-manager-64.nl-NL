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

---


# Doelintegratie met ervaringsfragmenten{#target-integration-with-experience-fragments}

>[!NOTE]
>
>Voor deze functionaliteit is de toepassing van [AEM 6.4 Service Pack 2 (6.4.2.0)](/help/release-notes/sp-release-notes.md) of hoger vereist.

U kunt [Experience Fragments](/help/sites-authoring/experience-fragments.md), gemaakt in Adobe Experience Manager (AEM), exporteren naar Adobe Target. Zij kunnen dan als aanbiedingen in de activiteiten van het Doel worden gebruikt, om ervaringen op schaal te testen en te personaliseren. Hiermee kunt u het gebruiksgemak en de kracht van AEM combineren met de krachtige mogelijkheden voor Automated Intelligence (AI) en Machine Learning (ML) in Target.

## Vereisten {#prerequisites}

Er zijn verschillende acties vereist:

1. U moet AEM met Doel integreren. Zie [Integratie met Adobe Target](/help/sites-administering/target.md) voor meer informatie.
1. De Fragmenten van de ervaring worden uitgevoerd van de auteursinstantie, zodat moet u de Verbinding Externalzer [op de auteursinstantie](/help/sites-developing/externalizer.md) vormen om ervoor te zorgen dat om het even welke verbindingen voor de publicatieinstantie worden geexternaliseerd.

## Cloudconfiguratie toevoegen {#add-the-cloud-configuration}

Voordat u een fragment exporteert, moet u de **cloudconfiguratie** voor **Adobe Target** toevoegen aan het fragment of de map:

1. Navigeer naar de **console van de Fragmenten** van de Ervaring.
1. Open **Pagina-eigenschappen** voor de juiste map of het juiste fragment.

   >[!NOTE]
   >
   >Als u de wolkenconfiguratie aan de ouderomslag van het Fragment van de Ervaring toevoegt, wordt de configuratie geërft door alle kinderen.
   >
   >Als u de wolkenconfiguratie aan het Fragment van de Ervaring zelf toevoegt, wordt de configuratie geërft door alle variaties.

1. Selecteer het tabblad **Cloud Services** .

1. Selecteer in **Cloud Service Configuration** de optie **Adobe Target** in de vervolgkeuzelijst.
1. Selecteer onder **Adobe Target** de juiste configuratie.

1. **Opslaan en sluiten**.

## Een ervaringsfragment naar doel exporteren {#exporting-an-experience-fragment-to-target}

>[!NOTE]
>
>Voor media-elementen, zoals afbeeldingen, wordt alleen een verwijzing naar Doel geëxporteerd. Het element zelf blijft opgeslagen in AEM Assets en wordt geleverd vanuit de AEM-publicatie-instantie.
>
>Daarom moet het ervaringsfragment, met alle gerelateerde elementen, worden gepubliceerd voordat het naar Target kan worden geëxporteerd.

Een ervaringsfragment exporteren van AEM naar Target (na het opgeven van de Cloud Configuration):

1. Navigeer naar de Experience Fragment-console.
1. Selecteer het ervaringsfragment dat u naar doel wilt exporteren.

   >[!NOTE]
   >
   >Het moet een variant van het Web van het Fragment van de Ervaring zijn.

1. Tik/klik op **Exporteren naar Adobe Target**.

   >[!NOTE]
   >
   >Als het ervaringsfragment al is geëxporteerd, selecteert u **Bijwerken in Adobe Target**.

1. Tik/klik op **Exporteren zonder publiceren** of **Publiceren** naar wens.

   >[!NOTE]
   >
   >Als u** Publiceren** selecteert, wordt het ervaringsfragment meteen gepubliceerd en naar Target verzonden.

1. Tik/klik op **OK** in het bevestigingsvenster.

   Het ervaringsfragment moet nu in Doel staan.

>[!NOTE]
>
>U kunt het exporteren ook vanuit de pagina-editor uitvoeren met behulp van vergelijkbare opdrachten in het menu [Pagina-informatie](/help/sites-authoring/author-environment-tools.md#page-information) .

## Het gebruiken van uw Fragmenten van de Ervaring in Doel {#using-your-experience-fragments-in-target}

Na het uitvoeren van de voorafgaande taken, toont het ervaringsfragment op de pagina van Aanbiedingen in Doel. Raadpleeg de [specifieke doeldocumentatie](https://experiencecloud.adobe.com/resources/help/en_US/target/target/aem-experience-fragments.html) voor meer informatie over wat u daar kunt bereiken.

## Een ervaringsfragment verwijderen dat al naar Doel is geëxporteerd {#deleting-an-experience-fragment-already-exported-to-target}

Als u een ervaringsfragment verwijdert dat al naar Target is geëxporteerd, kan dit problemen veroorzaken als het fragment al in een aanbieding in Target wordt gebruikt. Als u het fragment verwijdert, wordt de aanbieding onbruikbaar omdat de fragmentinhoud door AEM wordt geleverd.

Om dergelijke situaties te voorkomen:

* Als het ervaringsfragment momenteel niet in een activiteit wordt gebruikt, staat AEM de gebruiker toe om het fragment zonder een waarschuwingsbericht te schrappen.
* Als het ervaringsfragment momenteel door een activiteit in Doel wordt gebruikt, wordt de gebruiker van AEM gewaarschuwd over mogelijke gevolgen dat het schrappen van het fragment op de activiteit zal hebben.

   Het foutbericht in AEM belet de gebruiker niet (geforceerd) het ervaringsfragment te verwijderen. Als het ervaringsfragment wordt verwijderd:

   * De doelaanbieding met AEM Experience Fragment kan ongewenste werking vertonen

      * De aanbieding wordt waarschijnlijk nog steeds weergegeven, aangezien de Experience Fragment-HTML naar Target werd geduwd
      * Eventuele verwijzingen in het ervaringsfragment werken mogelijk niet correct als de middelen waarnaar wordt verwezen ook in AEM worden verwijderd.
   * Natuurlijk zijn verdere wijzigingen in het ervaringsfragment onmogelijk, omdat het ervaringsfragment niet meer bestaat in AEM.


