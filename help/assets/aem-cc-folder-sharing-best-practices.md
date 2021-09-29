---
title: Experience Manager Assets-mappen delen met Creative Cloud
description: Configuratie en aanbevolen procedures om gebruikers van Adobe Experience Manager Assets in staat te stellen mappen met middelen uit te wisselen met gebruikers van Adobe Creative Cloud.
contentOwner: AG
feature: Collaboration
role: User,Admin
exl-id: 7e2adfcc-410d-4574-8f7e-39aceecfdd4b
source-git-commit: 1679bbab6390808a1988cb6fe9b7692c3db31ae4
workflow-type: tm+mt
source-wordcount: '1078'
ht-degree: 0%

---

# [!DNL Experience Manager] naar  [!DNL Creative Cloud] mappen waar aanbevolen procedures worden gedeeld {#aem-to-creative-cloud-folder-sharing-best-practices}

>[!CAUTION]
>
>De functie voor het delen van mappen naar Creative Cloud is afgekeurd. Adobe raadt u ten zeerste aan nieuwere mogelijkheden te gebruiken, zoals [Adobe Asset Link](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/adobe-asset-link.ug.html) of [Experience Manager desktop app](https://experienceleague.adobe.com/docs/experience-manager-desktop-app/using/using.html). Leer meer in [Experience Manager en de integratie van de Creative Cloud beste praktijken](/help/assets/aem-cc-integration-best-practices.md).

Adobe Experience Manager kan zo worden geconfigureerd dat gebruikers in Experience Manager Assets mappen kunnen delen met Creative Cloud-gebruikers, zodat ze beschikbaar zijn als gedeelde mappen in de Creative Cloud Assets-service. De functie kan worden gebruikt om bestanden uit te wisselen tussen creatieve teams en gebruikers van Experience Manager Assets, vooral wanneer creatieve gebruikers geen toegang hebben tot de instantie Experience Manager Assets (ze bevinden zich niet op het bedrijfsnetwerk).

Dit type integratie kan in beide gebruiksgevallen worden gebruikt, vooral wanneer het werken met gebruikers die geen directe toegang tot de Middelen van de Experience Manager hebben:

* Een set specifieke elementen delen van Experience Manager Assets met gebruikers van Creative Cloud-bestanden (bijvoorbeeld een creatieve samenvatting en een set goedgekeurde middelen voor ontwerpwerkzaamheden voor een nieuwe marketingactiviteit)
* Nieuwe bestanden ontvangen van Creative Cloud-gebruikers.

>[!NOTE]
>
>Voordat u dit document leest, kunt u de algemene [best practices voor Experience Manager- en Creative Cloud-integratie doornemen](aem-cc-integration-best-practices.md) voor een overzicht op een hoger niveau van het onderwerp.

## Overzicht {#overview}

Het delen van mappen naar Creative Cloud-mappen is afhankelijk van het delen van mappen en bestanden aan de serverzijde tussen Experience Manager-elementen en Creative Cloud-accounts. Creatieve professionals die de Creative Cloud-bureaubladtoepassing op hun desktopcomputers gebruiken, kunnen de gedeelde mappen bovendien rechtstreeks op hun schijven beschikbaar stellen met behulp van Adobe CreativeSync-technologie.

Het volgende diagram geeft een overzicht van de integratie.

![chlimage_1-406](assets/chlimage_1-406.png)

De integratie omvat de volgende elementen:

* **[!DNL Assets]** server die in het ondernemingsnetwerk (beheerde diensten of op-gebouw) wordt opgesteld: Hier wordt het delen van mappen gestart.
* **Adobe Marketing Cloud Assets Core-service**: Handelt als tussenpersoon tussen Experience Manager- en Creative Cloud-opslagdiensten. De beheerder van het bedrijf dat de integratie gebruikt moet een vertrouwensrelatie tussen de Marketing Cloud organisatie en de Experience Manager Assets instantie tot stand brengen. Zij [bepalen ook een lijst van erkende Creative Cloud medewerkers](https://experienceleague.adobe.com/docs/core-services/interface/assets/t-admin-add-cc-user.html#assets), die de gebruikers van Activa omslagen ook voor extra veiligheid kunnen delen.
* **Webservices**  voor Creative Cloud-middelen (interface voor opslag en Creative Cloud-bestanden): Dit is waar specifieke gebruikers van de Creative Cloud, met wie een omslag van Activa werd gedeeld, de uitnodiging zouden kunnen goedkeuren en de omslag in hun de rekeningsopslag van de Creative Cloud zien.
* **Creative Cloud-bureaubladtoepassing**: (Optioneel) Hiermee hebt u rechtstreeks via synchronisatie met Creative Cloud Assets-opslag toegang tot gedeelde mappen/bestanden vanaf het bureaublad van de creatieve gebruiker.

## Kenmerken en beperkingen {#characteristics-and-limitations}

* **Eenvoudige doorgave van wijzigingen:** Bestandswijzigingen worden alleen in één richting doorgegeven - vanuit het systeem (Experience Manager- of Creative Cloud-elementen), waar het element oorspronkelijk is gemaakt (geüpload). De integratie biedt geen volledig geautomatiseerde, tweezijdige synchronisatie tussen de twee systemen.

* **Versioning:**

   * Experience Manager maakt bij updates alleen versies van een element als het bestand van oorsprong is uit de Experience Manager en daar wordt bijgewerkt.
   * Creative Cloud Assets verstrekt zijn eigen [versioning eigenschap](https://helpx.adobe.com/creative-cloud/help/versioning-faq.html) die voor Werk in Voortgang updates (hoofdzakelijk, slaat updates tot 10 dagen op) wordt gericht

* **Ruimtebeperkingen:** Grootte en volumes van uitgewisselde bestanden worden beperkt door het specifieke quotum voor  [ ](https://helpx.adobe.com/creative-cloud/kb/file-storage-quota.html) Creative Cloud-middelen voor creatieve gebruikers (afhankelijk van het abonnementsniveau) en een beperking van de maximale bestandsgrootte van 5 GB. De ruimte wordt bovendien beperkt door de quota van de activa die de organisatie in de kerndienst van Adobe Marketing Cloud Assets heeft.

* **Ruimtevereisten:** De bestanden in gedeelde mappen moeten ook fysiek worden opgeslagen in Experience Manager en vervolgens in een Creative Cloud-account, met een kopie in cache in de kernservice Marketing Cloud Assets.
* **Netwerk en bandbreedte:** De bestanden in gedeelde mappen en alle updates moeten via het netwerk tussen de systemen worden getransporteerd. Zorg ervoor dat alleen relevante bestanden en updates worden gedeeld.
* **Maptype**: Het delen van een map Middelen van het type  `sling:OrderedFolder`wordt niet ondersteund. Als u een map wilt delen, selecteert u de optie Besteld niet wanneer u deze maakt in Experience Manager Assets.

## Aanbevolen procedures {#best-practices}

De beste praktijken voor het leveraging van de Experience Manager aan de omslag van de Creative Cloud omvatten:

* **Overwegingen bij het volume:** Experience Manager, Mappen delen van Creative Cloud moet worden gebruikt om een kleiner aantal bestanden te delen, bijvoorbeeld voor een specifieke campagne of activiteit. Om grotere reeksen activa, zoals alle goedgekeurde activa in de organisatie te delen, gebruik andere distributiemethodes (bijvoorbeeld, Experience Manager Assets Brand Portal) of Experience Manager Desktop app.
* **Vermijd het delen van diepe hiërarchieën:** het delen werkt recursief en staat niet voor selectieve unsharing toe. Gewoonlijk worden alleen mappen zonder submappen of met een zeer oppervlakkige hiërarchie, zoals 1 submapniveau, beschouwd als mappen die kunnen worden gedeeld.
* **Afzonderlijke mappen voor delen in één richting:** Afzonderlijke mappen moeten worden gebruikt voor het delen van definitieve elementen van Experience Manager-elementen naar Creative Cloud-bestanden en voor het delen van creatieve elementen van Creative Cloud-bestanden naar  [!DNL Assets]. Samen met een goede noemende overeenkomst voor deze omslagen, leidt het tot een gemakkelijker te begrijpen het werk milieu voor de Middelen van de Experience Manager en gebruikers van de Creative Cloud.
* **WIP in de gedeelde map vermijden:** Gedeelde map mag niet worden gebruikt voor Werk in uitvoering - gebruik een aparte map in Creative Cloud-bestanden om werk uit te voeren waarvoor regelmatig wijzigingen in het bestand nodig zijn.
* **Start nieuw werk buiten de gedeelde map:** Nieuwe ontwerpen (creatieve bestanden) moeten worden gestart in de aparte WIP-map in Creative Cloud-bestanden en wanneer ze klaar zijn om te worden gedeeld met gebruikers van Experience Manager Assets, moeten ze naar de gedeelde map worden verplaatst of opgeslagen.
* **Vereenvoudig het delen structuur:** voor een meer handelbare werkende opstelling, denk over het vereenvoudigen van de het delen structuur. In plaats van met alle creatieve gebruikers te delen, zouden de omslagen van de Middelen van de Experience Manager met teamvertegenwoordiger(s) slechts, zoals een creatieve directeur of teammanager moeten worden gedeeld. De manager aan de creatieve kant zou definitieve activa ontvangen, over werktaken beslissen, en dan ontwerpers laten in hun eigen rekeningen van de Creative Cloud werken over activa WIP. Ze kunnen de samenwerkingsfuncties van Creative Cloud gebruiken om het werk te coördineren, en ten slotte elementen selecteren en plaatsen die klaar zijn om terug te delen naar de Experience Manager Assets in hun creatief-klaar gedeelde map.

Het volgende diagram illustreert een voorbeeldconfiguratie voor het creëren van nieuwe ontwerpen die op bestaande definitieve activa van de Elementen van de Experience Manager worden gebaseerd.

![chlimage_1-407](assets/chlimage_1-407.png)
