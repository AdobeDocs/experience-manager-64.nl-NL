---
title: AEM Assets-mappen delen met Creative Cloud
description: Configuratie en aanbevolen procedures om gebruikers van Adobe Experience Manager Assets in staat te stellen mappen met middelen uit te wisselen met gebruikers van Adobe Creative Cloud.
contentOwner: AG
translation-type: tm+mt
source-git-commit: e64f5b0e1333d511eaf450072756a95399e838d0
workflow-type: tm+mt
source-wordcount: '1061'
ht-degree: 0%

---


# AEM naar map Creative Cloud om beste werkwijzen te delen {#aem-to-creative-cloud-folder-sharing-best-practices}

>[!CAUTION]
>
>De functie Mappen delen AEM naar Creative Cloud is vervangen. Adobe raadt u ten zeerste aan nieuwere mogelijkheden te gebruiken, zoals [Adobe Asset Link](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/adobe-asset-link.ug.html) of [AEM desktop app](https://experienceleague.adobe.com/docs/experience-manager-desktop-app/using/using.html). Leer meer in [AEM en de integratie van Creative Cloud beste praktijken](/help/assets/aem-cc-integration-best-practices.md).

Adobe Experience Manager (AEM) kan zo worden geconfigureerd dat gebruikers in AEM Assets mappen kunnen delen met Creative Cloud-gebruikers, zodat ze beschikbaar zijn als gedeelde mappen in de service Creative Cloud Assets. De functie kan worden gebruikt om bestanden uit te wisselen tussen creatieve teams en AEM Assets-gebruikers, vooral wanneer creatieve gebruikers geen toegang hebben tot het AEM Assets-exemplaar (ze bevinden zich niet op het bedrijfsnetwerk).

Dit type integratie kan in beide gebruiksgevallen worden gebruikt, met name wanneer u werkt met gebruikers die geen directe toegang hebben tot AEM Assets:

* Een set specifieke middelen van AEM Assets delen met gebruikers van Creative Cloud Files (bijvoorbeeld een creatieve samenvatting en een set goedgekeurde middelen voor ontwerpwerkzaamheden voor een nieuwe marketingactiviteit)
* Nieuwe bestanden ontvangen van Creative Cloud-gebruikers.

>[!NOTE]
>
>Alvorens dit document te lezen, kunt u algemene [AEM en de integratie beste praktijken ](aem-cc-integration-best-practices.md) voor een overzicht op hoger niveau van het onderwerp herzien.

## Overzicht {#overview}

Het delen van mappen en bestanden tussen AEM Assets- en Creative Cloud-accounts is afhankelijk van het delen van mappen en bestanden aan de serverzijde AEM naar de map Creative Cloud. Creatieve professionals die de Creative Cloud-bureaubladtoepassing op hun desktopcomputers gebruiken, kunnen de gedeelde mappen bovendien rechtstreeks op hun schijven beschikbaar stellen met behulp van Adobe CreativeSync-technologie.

Het volgende diagram geeft een overzicht van de integratie.

![chlimage_1-406](assets/chlimage_1-406.png)

De integratie omvat de volgende elementen:

* **AEM Assets-** server die wordt geïmplementeerd in het bedrijfsnetwerk (beheerde services of on-premise): Hier wordt het delen van mappen gestart.
* **Adobe Marketing Cloud Assets Core-service**: Handelt als tussenpersoon tussen AEM- en Creative Cloud-opslagdiensten. De beheerder van het bedrijf dat de integratie gebruikt, moet een vertrouwensrelatie tussen de Marketing Cloud organisatie en de instantie van AEM Assets tot stand brengen. Zij [bepalen ook een lijst van erkende medewerkers van Creative Cloud](https://experienceleague.adobe.com/docs/core-services/interface/assets/t-admin-add-cc-user.html?lang=en#assets), die de gebruikers van AEM Assets omslagen ook voor extra veiligheid kunnen delen.
* **Webservices**  voor Creative Cloud-middelen (interface voor opslag en Creative Cloud-bestanden): In dit geval kunnen specifieke Creative Cloud-gebruikers, met wie een AEM Assets-map werd gedeeld, de uitnodiging accepteren en de map weergeven in hun Creative Cloud-accountopslag.
* **Creative Cloud-bureaubladtoepassing**: (Optioneel) Hiermee hebt u rechtstreeks via synchronisatie met Creative Cloud Assets-opslag toegang tot gedeelde mappen/bestanden vanaf het bureaublad van de creatieve gebruiker.

## Kenmerken en beperkingen {#characteristics-and-limitations}

* **Eenvoudige doorgave van wijzigingen:** Bestandswijzigingen worden alleen in één richting doorgegeven - vanuit het systeem (AEM of Creative Cloud-elementen), waar het element oorspronkelijk is gemaakt (geüpload). De integratie biedt geen volledig geautomatiseerde, tweezijdige synchronisatie tussen de twee systemen.

* **Versioning:**

   * AEM maakt bij updates alleen versies van een element als het bestand afkomstig is van AEM en daar wordt bijgewerkt.
   * Creative Cloud Assets verstrekt zijn eigen [versioning eigenschap](https://helpx.adobe.com/creative-cloud/help/versioning-faq.html) die voor Werk in Voortgang updates (hoofdzakelijk, slaat updates tot 10 dagen op) wordt gericht

* **Ruimtebeperkingen:** Grootte en volumes van uitgewisselde bestanden worden beperkt door het specifieke quotum voor  [ ](https://helpx.adobe.com/creative-cloud/kb/file-storage-quota.html) Creative Cloud-middelen voor creatieve gebruikers (afhankelijk van het abonnementsniveau) en een beperking van de maximale bestandsgrootte van 5 GB. De ruimte wordt bovendien beperkt door de quota van de activa die de organisatie in de kerndienst van Adobe Marketing Cloud Assets heeft.

* **Ruimtevereisten:** De bestanden in gedeelde mappen moeten ook fysiek worden opgeslagen in AEM en vervolgens in een Creative Cloud-account, met een kopie in cache in de kernservice Marketing Cloud Assets.
* **Netwerk en bandbreedte:** De bestanden in gedeelde mappen en alle updates moeten via het netwerk tussen de systemen worden getransporteerd. Zorg ervoor dat alleen relevante bestanden en updates worden gedeeld.
* **Maptype**: Het delen van een map Middelen van het type  `sling:OrderedFolder`wordt niet ondersteund. Als u een map wilt delen, selecteert u bij het maken ervan in AEM Assets de optie Besteld niet.

## Aanbevolen werkwijzen {#best-practices}

De beste werkwijzen voor het doorvoeren van AEM naar het delen van mappen in Creative Cloud:

* **Overwegingen bij het volume:** AEM/Creative Cloud delen van mappen moet worden gebruikt om een kleiner aantal bestanden te delen, bijvoorbeeld voor een specifieke campagne of activiteit. Als u grotere sets middelen wilt delen, zoals alle goedgekeurde middelen in de organisatie, gebruikt u andere distributiemethoden (bijvoorbeeld AEM Assets Brand Portal) of AEM bureaubladtoepassing.
* **Vermijd het delen van diepe hiërarchieën:** het delen werkt recursief en staat niet voor selectieve unsharing toe. Gewoonlijk worden alleen mappen zonder submappen of met een zeer oppervlakkige hiërarchie, zoals 1 submapniveau, beschouwd als mappen die kunnen worden gedeeld.
* **Afzonderlijke mappen voor delen in één richting:** Afzonderlijke mappen moeten worden gebruikt voor het delen van uiteindelijke middelen van AEM Assets naar Creative Cloud-bestanden en voor het delen van creatieve middelen van Creative Cloud-bestanden naar AEM Assets. Samen met een goede naamgevingsconventie voor deze mappen, creëert deze een beter te begrijpen werkomgeving voor zowel AEM Assets- als Creative Cloud-gebruikers.
* **WIP in de gedeelde map vermijden:** Gedeelde map mag niet worden gebruikt voor Werk in uitvoering - gebruik een aparte map in Creative Cloud-bestanden om werk uit te voeren waarvoor regelmatig wijzigingen in het bestand nodig zijn.
* **Nieuwe taken starten buiten de gedeelde map:** Nieuwe ontwerpen (creatieve bestanden) moeten worden gestart in de aparte WIP-map in Creative Cloud-bestanden. Wanneer ze klaar zijn om te worden gedeeld met AEM Assets-gebruikers, moeten ze naar de gedeelde map worden verplaatst of opgeslagen.
* **Vereenvoudig het delen structuur:** voor een meer handelbare werkende opstelling, denk over het vereenvoudigen van de het delen structuur. In plaats van met alle creatieve gebruikers te delen, zouden de omslagen van AEM Assets met teamvertegenwoordiger(s) slechts, zoals een creatieve directeur of teammanager moeten worden gedeeld. De manager aan de creatieve kant zou definitieve activa ontvangen, over werktaken beslissen, en dan ontwerpers laten in hun eigen rekeningen van de Creative Cloud werken over activa WIP. Ze kunnen de samenwerkingsfuncties van Creative Cloud gebruiken om het werk te coördineren, en ten slotte elementen selecteren en plaatsen die klaar zijn om terug te delen naar AEM Assets in hun creatief-klaar gedeelde map.

Het volgende diagram illustreert een voorbeeldconfiguratie voor het creëren van nieuwe ontwerpen die op bestaande definitieve activa van AEM Assets worden gebaseerd.

![chlimage_1-407](assets/chlimage_1-407.png)
