---
title: Tips en trucs voor een efficiënte vertaling van middelen
description: Aanbevolen procedures voor efficiënt beheer van middelen om verschillende vertaalde versies te synchroniseren en vertaalworkflows te stroomlijnen.
contentOwner: AG
feature: Vertaling
role: Business Practitioner,Administrator
exl-id: 15162b80-ddef-4ec0-9db6-36695c93ebb1
translation-type: tm+mt
source-git-commit: bd94d3949f0117aa3e1c9f0e84f7293a5d6b03b4
workflow-type: tm+mt
source-wordcount: '502'
ht-degree: 0%

---

# Aanbevolen procedures om elementen efficiënt te vertalen {#best-practices-for-translating-assets-efficiently}

Adobe Experience Manager (AEM)-middelen ondersteunen meertalige workflows om binaire gegevens, metagegevens en tags voor digitale middelen naar meerdere landinstellingen te vertalen en de vertaalde middelen te beheren. Zie [Meertalige elementen](multilingual-assets.md) voor meer informatie.

Voor efficiënt beheer van middelen om ervoor te zorgen dat verschillende vertaalde versies gesynchroniseerd blijven, creeer [taalexemplaren](preparing-assets-for-translation.md) van activa alvorens vertaalwerkschema&#39;s in werking te stellen.

Een taalkopie van een element of een groep elementen is een op hetzelfde niveau staande taal (of een versie van het element of de elementen in een cognattaal) met een vergelijkbare inhoudshiërarchie.

Elke taalkopie is een onafhankelijk middel. Daarom kan het omzetten van middelen in meerdere landinstellingen de grootte van de CRX-opslagplaats drastisch verhogen. Bijvoorbeeld, kan het vertalen van activa met een gecombineerde grootte van 10 GB in twee talen de bewaarplaatgrootte met ongeveer 20 GB (10 GB voor elke taal) verhogen.

Middelenbinaire getallen nemen veel meer opslagruimte in beslag dan metagegevens en tags. Als het vertalen van metagegevens en tags alleen uw doel dient, laat u daarom weg om de binaire getallen te vertalen. U kunt de originele kopie van de binaire bestanden in de opslagplaats behouden, zodat u ze kunt koppelen aan metagegevens en tags die naar verschillende landinstellingen zijn vertaald. Door één kopie van binaire bestanden te onderhouden in plaats van meerdere vertaalde versies, wordt de invloed op de grootte van de opslagplaats tot een minimum beperkt.

Bestandsgegevensopslag en Amazon S3 Data Store bieden een opslaginfrastructuur die het meest geschikt is voor deze scenario&#39;s. In deze opslagopslagopslagruimten wordt één kopie van de binaire elementen (inclusief uitvoeringen) opgeslagen die door metagegevens en tags in meerdere landinstellingen kunnen worden gedeeld. Daarom heeft het maken van kopieën van de taal van het middel en het vertalen van metagegevens en tags geen invloed op de grootte van de opslagplaats.

U kunt ook enkele configuratiewijzigingen aanbrengen in een aantal workflows en het vertaalintegratieframework om het proces verder te stroomlijnen.

1. Voer een van de volgende handelingen uit:

   * [Bestandsgegevensopslag instellen](/help/sites-deploying/data-store-config.md)
   * [Amazon S3 Data Store instellen](/help/sites-deploying/data-store-config.md)

1. [DAM MetaData Writeback](/help/sites-administering/workflow-offloader.md#disable-offloading)-workflow uitschakelen

   Zoals de naam suggereert, worden de metagegevens in de *DAM-metagegevensterugdraaiworkflow* opnieuw genoteerd naar het binaire bestand. Omdat de metagegevens na de vertaling veranderen, wordt bij het terugschrijven naar het binaire bestand een andere binaire waarde voor een taalkopie gegenereerd.

   >[!NOTE]
   >
   >Als u de *DAM MetaData Writeback*-workflow uitschakelt, wordt XMP terugschrijven van metagegevens op binaire elementen uitgeschakeld. Daarom worden toekomstige wijzigingen in metagegevens niet meer opgeslagen in de elementen. Evalueer de gevolgen voordat u deze workflow uitschakelt.

1. Schakel de *Laatst gewijzigde datum instellen*-workflow in.

   Met de *DAM MetaData Writeback*-workflow configureert u de laatste gewijzigde datum voor een element. Omdat u deze workflow in stap 2 uitschakelt, kan AEM Assets de laatste gewijzigde datum van de elementen niet meer up-to-date houden. Schakel daarom de *Laatste gewijzigde datum instellen*-workflow in om ervoor te zorgen dat de laatste gewijzigde datums van de elementen up-to-date zijn. Elementen met verouderde datums die als laatste zijn gewijzigd, kunnen fouten veroorzaken.

1. [Configureer het ](/help/sites-administering/tc-tic.md) framework voor vertaalintegratie om het vertalen van binaire bestanden met middelen te stoppen. Schakel de optie Vertaalactiva uit onder het tabblad Elementen om de vertaling van binaire middelen te stoppen.
1. Metagegevens/tags van elementen vertalen met [Workflows van meerdere bedrijfsmiddelen](multilingual-assets.md).
