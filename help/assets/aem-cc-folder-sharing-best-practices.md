---
title: Experience Manager Assets-mappen delen met Creative Cloud
description: Configuratie en aanbevolen procedures om gebruikers van Adobe Experience Manager Assets in staat te stellen mappen met middelen uit te wisselen met gebruikers van Adobe Creative Cloud.
contentOwner: AG
feature: Collaboration
role: User,Admin
exl-id: 7e2adfcc-410d-4574-8f7e-39aceecfdd4b
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1114'
ht-degree: 0%

---

# [!DNL Experience Manager] tot [!DNL Creative Cloud] map delen, aanbevolen procedures {#aem-to-creative-cloud-folder-sharing-best-practices}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

>[!CAUTION]
>
>De functie voor het delen van mappen naar Creative Cloud is afgekeurd. Adobe raadt sterk aan om nieuwere mogelijkheden te gebruiken, zoals [Adobe-itemkoppeling](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/adobe-asset-link.ug.html) of [Experience Manager-bureaubladtoepassing](https://experienceleague.adobe.com/docs/experience-manager-desktop-app/using/using.html). Meer informatie in [Best practices op het gebied van Experience Manager- en Creative Cloud-integratie](/help/assets/aem-cc-integration-best-practices.md).

Adobe Experience Manager kan zo worden geconfigureerd dat gebruikers in Experience Manager Assets mappen kunnen delen met Creative Cloud-gebruikers, zodat ze beschikbaar zijn als gedeelde mappen in de Creative Cloud Assets-service. De functie kan worden gebruikt om bestanden uit te wisselen tussen creatieve teams en Experience Manager Assets-gebruikers, vooral wanneer creatieve gebruikers geen toegang hebben tot het Experience Manager Assets-exemplaar (ze bevinden zich niet op het bedrijfsnetwerk).

Dit type integratie kan in beide gebruiksgevallen worden gebruikt, met name wanneer u werkt met gebruikers die geen directe toegang hebben tot Experience Manager Assets:

* Een set specifieke middelen van Experience Manager Assets delen met gebruikers van Creative Cloud Files (bijvoorbeeld een creatieve samenvatting en een set goedgekeurde middelen voor ontwerpwerkzaamheden voor een nieuwe marketingactiviteit)
* Nieuwe bestanden ontvangen van Creative Cloud-gebruikers.

>[!NOTE]
>
>Voordat u dit document leest, kunt u de algemene [Best practices op het gebied van Experience Manager- en Creative Cloud-integratie](aem-cc-integration-best-practices.md) voor een overzicht op hoger niveau van het onderwerp.

## Overzicht {#overview}

Het delen van mappen naar Creative Cloud-mappen is afhankelijk van het delen van mappen en bestanden op de server tussen Experience Manager Assets- en Creative Cloud-accounts. Creatieve professionals die de Creative Cloud-bureaubladtoepassing op hun desktopcomputers gebruiken, kunnen de gedeelde mappen bovendien rechtstreeks op hun schijven beschikbaar stellen met behulp van Adobe CreativeSync-technologie.

Het volgende diagram geeft een overzicht van de integratie.

![chlimage_1-406](assets/chlimage_1-406.png)

De integratie omvat de volgende elementen:

* **[!DNL Assets]server** opgesteld in het ondernemingsnetwerk (beheerde diensten of op-gebouw): Hier wordt het delen van mappen gestart.
* **Adobe Marketing Cloud Assets Core-service**: Handelt als tussenpersoon tussen Experience Manager- en Creative Cloud-opslagdiensten. De beheerder van het bedrijf dat de integratie gebruikt, moet een vertrouwensrelatie tussen de Marketing Cloud organisatie en de instantie van Experience Manager Assets tot stand brengen. Ook [een lijst met erkende Creative Cloud-medewerkers definiëren](https://experienceleague.adobe.com/docs/core-services/interface/assets/t-admin-add-cc-user.html#assets), dat middelengebruikers ook mappen kunnen delen voor extra beveiliging.
* **Creative Cloud-middelen, webservices** (Interface voor opslag- en Creative Cloud-bestanden): Dit is waar specifieke gebruikers van de Creative Cloud, met wie een omslag van Activa werd gedeeld, de uitnodiging zouden kunnen goedkeuren en de omslag in hun de rekeningsopslag van de Creative Cloud zien.
* **Creative Cloud-bureaubladtoepassing**: (Optioneel) Hiermee hebt u rechtstreeks via synchronisatie met Creative Cloud Assets-opslag toegang tot gedeelde mappen/bestanden vanaf het bureaublad van de creatieve gebruiker.

## Kenmerken en beperkingen {#characteristics-and-limitations}

* **Eenvoudige doorgave van wijzigingen:** Bestandswijzigingen worden alleen in één richting doorgegeven - vanuit het systeem (Experience Manager- of Creative Cloud-elementen), waar het element oorspronkelijk is gemaakt (geüpload). De integratie biedt geen volledig geautomatiseerde synchronisatie in twee richtingen tussen de twee systemen.

* **Versioning:**

   * Experience Manager maakt bij updates alleen versies van een element als het bestand van oorsprong is uit de Experience Manager en daar wordt bijgewerkt.
   * Creative Cloud Assets biedt haar eigen [versiefunctie](https://helpx.adobe.com/creative-cloud/help/versioning-faq.html) dat is gericht op Werk in uitvoering updates (slaat updates in principe tot 10 dagen op)

* **Ruimtebeperkingen:** Grootte en volumes van uitgewisselde bestanden worden beperkt door de specifieke [Creative Cloud Assets-quota](https://helpx.adobe.com/creative-cloud/kb/file-storage-quota.html) voor creatieve gebruikers (afhankelijk van het abonnementsniveau) en een beperking van de maximale bestandsgrootte van 5 GB. De ruimte wordt bovendien beperkt door de quota van de activa die de organisatie in de kerndienst van Adobe Marketing Cloud Assets heeft.

* **Ruimtevereisten:** De dossiers in gedeelde omslagen moeten ook fysisch in Experience Manager en dan in de rekening van de Creative Cloud worden opgeslagen, met een caching exemplaar in de kerndienst van de Middelen van de Marketing Cloud.
* **Netwerken en bandbreedte:** De bestanden in gedeelde mappen en alle updates moeten via het netwerk tussen de systemen worden getransporteerd. Zorg ervoor dat alleen relevante bestanden en updates worden gedeeld.
* **Maptype**: Een map Middelen van het type `sling:OrderedFolder`, wordt niet ondersteund. Als u een map wilt delen, selecteert u bij het maken ervan in Experience Manager Assets de optie Besteld niet.

## Aanbevolen procedures {#best-practices}

De beste praktijken voor het leveraging van de Experience Manager aan de omslag van de Creative Cloud omvatten:

* **Overwegingen voor volume:** Experience Manager, het Delen van de Omslag van de Creative Cloud zou moeten worden gebruikt om kleiner aantal dossiers te delen, bijvoorbeeld, relevant voor een specifieke campagne of een activiteit. Als u grotere sets middelen wilt delen, zoals alle goedgekeurde middelen in de organisatie, gebruikt u andere distributiemethoden (bijvoorbeeld Experience Manager Assets Brand Portal) of de bureaubladtoepassing van de Experience Manager.
* **Vermijd het delen van diepe hiërarchieën:** Het delen werkt recursief en maakt het niet mogelijk selectief te verdelen. Gewoonlijk worden alleen mappen zonder submappen of met een zeer oppervlakkige hiërarchie, zoals 1 submapniveau, beschouwd als mappen die kunnen worden gedeeld.
* **Afzonderlijke mappen voor delen in één richting:** Afzonderlijke mappen moeten worden gebruikt voor het delen van de uiteindelijke middelen van Experience Manager Assets naar Creative Cloud-bestanden en voor het delen van creatieve middelen van Creative Cloud-bestanden naar [!DNL Assets]. Samen met een goede naamgevingsconventie voor deze mappen, creëert deze een beter te begrijpen werkomgeving voor zowel Experience Manager Assets- als Creative Cloud-gebruikers.
* **WIP in de gedeelde map vermijden:** Gedeelde map mag niet worden gebruikt voor Werk in uitvoering. Gebruik een aparte map in Creative Cloud-bestanden om werk uit te voeren waarvoor regelmatig wijzigingen in het bestand nodig zijn.
* **Nieuwe taken starten buiten de gedeelde map:** Nieuwe ontwerpen (creatieve bestanden) moeten worden gestart in de aparte WIP-map in Creative Cloud-bestanden. Wanneer deze klaar zijn om te worden gedeeld met Experience Manager Assets-gebruikers, moeten ze worden verplaatst of opgeslagen naar de gedeelde map.
* **Structuur voor delen vereenvoudigen:** Voor een beter te beheren werkende opstelling, denk over het vereenvoudigen van de het delen structuur. In plaats van met alle creatieve gebruikers te delen, zouden de omslagen van Experience Manager Assets met teamvertegenwoordiger(s) slechts, zoals een creatieve directeur of teammanager moeten worden gedeeld. De manager aan de creatieve kant zou definitieve activa ontvangen, over werktaken beslissen, en dan ontwerpers laten in hun eigen rekeningen van de Creative Cloud werken over activa WIP. Ze kunnen de samenwerkingsfuncties van Creative Cloud gebruiken om het werk te coördineren, en ten slotte elementen selecteren en plaatsen die klaar zijn om terug te delen naar Experience Manager Assets in hun creatief-klaar gedeelde map.

Het volgende diagram illustreert een voorbeeldconfiguratie voor het creëren van nieuwe ontwerpen die op bestaande definitieve activa van Experience Manager Assets worden gebaseerd.

![chlimage_1-407](assets/chlimage_1-407.png)
