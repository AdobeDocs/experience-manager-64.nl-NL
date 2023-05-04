---
title: Tips en trucs voor een efficiënte vertaling van middelen
description: Aanbevolen procedures voor efficiënt beheer van middelen om verschillende vertaalde versies te synchroniseren en vertaalworkflows te stroomlijnen.
contentOwner: AG
feature: Translation
role: User,Admin
exl-id: 15162b80-ddef-4ec0-9db6-36695c93ebb1
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 0%

---

# Aanbevolen procedures om middelen efficiënt te vertalen {#best-practices-for-translating-assets-efficiently}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Adobe Experience Manager Assets biedt ondersteuning voor meertalige workflows om binaire gegevens, metagegevens en tags voor digitale middelen naar meerdere landinstellingen te vertalen en de vertaalde middelen te beheren. Zie voor meer informatie [Meertalige activa](multilingual-assets.md).

Voor een efficiënt beheer van middelen, zodat verschillende vertaalde versies gesynchroniseerd blijven, kunt u [taalkopieën](preparing-assets-for-translation.md) van elementen voordat u vertaalworkflows uitvoert.

Een taalkopie van een element of een groep elementen is een op hetzelfde niveau staande taal (of een versie van het element of de elementen in een cognattaal) met een vergelijkbare inhoudshiërarchie.

Elke taalkopie is een onafhankelijk middel. Daarom kan het omzetten van middelen in meerdere landinstellingen de grootte van de CRX-opslagplaats drastisch verhogen. Bijvoorbeeld, kan het vertalen van activa met een gecombineerde grootte van 10 GB in twee talen de bewaarplaatgrootte met ongeveer 20 GB (10 GB voor elke taal) verhogen.

Middelenbinaire getallen nemen veel meer opslagruimte in beslag dan metagegevens en tags. Als het vertalen van metagegevens en tags alleen uw doel dient, laat u daarom weg om de binaire getallen te vertalen. U kunt de originele kopie van de binaire bestanden in de opslagplaats behouden, zodat u ze kunt koppelen aan metagegevens en tags die naar verschillende landinstellingen zijn vertaald. Door één kopie van binaire bestanden te onderhouden in plaats van meerdere vertaalde versies, wordt de invloed op de grootte van de opslagplaats tot een minimum beperkt.

Bestandsgegevensopslag en Amazon S3 Data Store bieden een opslaginfrastructuur die het meest geschikt is voor deze scenario&#39;s. In deze opslagopslagopslagruimten wordt één kopie van de binaire elementen (inclusief uitvoeringen) opgeslagen die door metagegevens en tags in meerdere landinstellingen kunnen worden gedeeld. Daarom heeft het maken van kopieën van de taal van het middel en het vertalen van metagegevens en tags geen invloed op de grootte van de opslagplaats.

U kunt ook enkele configuratiewijzigingen aanbrengen in een aantal workflows en het vertaalintegratieframework om het proces verder te stroomlijnen.

1. Voer een van de volgende handelingen uit:

   * [Bestandsgegevensopslag instellen](/help/sites-deploying/data-store-config.md)
   * [Amazon S3 Data Store instellen](/help/sites-deploying/data-store-config.md)

1. De opdracht [DAM MetaData Writeback](/help/sites-administering/workflow-offloader.md#disable-offloading) werkstroom

   Zoals de naam suggereert, wordt *DAM-metagegevensterugkoppeling* de metagegevens worden opnieuw naar het binaire bestand geschreven. Omdat de metagegevens na de vertaling veranderen, wordt bij het terugschrijven naar het binaire bestand een andere binaire waarde voor een taalkopie gegenereerd.

   >[!NOTE]
   >
   >Het onbruikbaar maken van *DAM MetaData Writeback* Met workflow worden XMP metagegevens afgeschreven op binaire bestanden met elementen. Daarom worden toekomstige wijzigingen in metagegevens niet meer opgeslagen in de elementen. Evalueer de gevolgen voordat u deze workflow uitschakelt.

1. De optie *Laatst gewijzigde datum instellen* workflow.

   De *DAM MetaData Writeback* wordt de datum van de laatste wijziging voor een element geconfigureerd. Omdat u deze workflow in stap 2 uitschakelt, [!DNL Experience Manager Assets] kan de laatste gewijzigde datum van de activa niet meer actueel houden. Daarom moet de *Laatst gewijzigde datum instellen* workflow om ervoor te zorgen dat de laatste gewijzigde datums van de elementen up-to-date zijn. Elementen met verouderde datums die als laatste zijn gewijzigd, kunnen fouten veroorzaken.

1. [Het vertaalintegratieframework configureren](/help/sites-administering/tc-tic.md) om het vertalen van binaire elementen te stoppen. Schakel de optie Vertaalactiva uit onder het tabblad Elementen om de vertaling van binaire middelen te stoppen.
1. Metagegevens/tags van elementen vertalen met [Workflows met meerdere bedrijfsmiddelen](multilingual-assets.md).
