---
title: Duurzame verbeteringen
seo-title: Sustainable Upgrades
description: Leer over duurzame verbeteringen in AEM 6.4.
seo-description: Learn about sustainable upgrades in AEM 6.4.
uuid: 59d64af5-6ee0-40c8-b24a-c06848f70daa
contentOwner: sarchiz
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: upgrading
discoiquuid: 5ca8dd7a-4efd-493e-8022-d2f10903b0a2
feature: Upgrading
exl-id: 765efa8d-1548-4db3-ba87-baa02075eaf6
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '841'
ht-degree: 0%

---

# Duurzame verbeteringen{#sustainable-upgrades}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Customization Framework {#customization-framework}

### Architectuur (functioneel / infrastructuur / inhoud / toepassing)  {#architecture-functional-infrastructure-content-application}

De functie van het Kader van de Aanpassing wordt ontworpen om de schendingen in niet verlengbare gebieden van de code (zoals APIS) of inhoud (zoals overlays) te helpen verminderen die niet verbeteringsvriendelijk zijn.

Er zijn twee componenten van het aanpassingskader: de **API-oppervlak** en de **Inhoudsclassificatie**.

#### API-oppervlak {#api-surface}

In eerdere versies van AEM vele API&#39;s werden deze via Uber Jar weergegeven. Sommige van deze API&#39;s waren niet bedoeld voor gebruik door klanten, maar werden blootgesteld aan ondersteuning voor AEM functionaliteit in verschillende bundels. In de toekomst worden de Java API&#39;s gemarkeerd als Public of Private om aan klanten aan te geven welke API&#39;s veilig kunnen worden gebruikt in de context van upgrades. Andere bijzonderheden zijn:

* Java API&#39;s gemarkeerd als `Public` kan worden gebruikt en van verwijzingen voorzien door de bundels van de douaneimplementatie.

* De openbare API&#39;s zijn achterwaarts compatibel met de installatie van een compatibiliteitspakket.
* Het compatibiliteitspakket bevat een compatibiliteitspakket van Uber JAR om achterwaartse compatibiliteit te garanderen
* Java API&#39;s gemarkeerd als `Private` zijn alleen bedoeld voor gebruik door AEM interne bundels en mogen niet door aangepaste bundels worden gebruikt.

>[!NOTE]
>
>Het begrip `Private` en `Public` in dit verband mag niet worden verward met Java-noties van publieke en private klassen.

![image2018-2-12_23-52-48](assets/image2018-2-12_23-52-48.png)

#### Inhoudsclassificaties {#content-classifications}

AEM gebruikt al lang de principal of overlays en Sling Resource Merger om klanten toe te staan AEM functionaliteit uit te breiden en aan te passen. De vooraf bepaalde functionaliteit die de AEM consoles en UI van kracht maakt wordt opgeslagen in **/libs**. Klanten mogen niets wijzigen **/libs** maar kan hieronder extra inhoud toevoegen **/apps** om de in **/libs** (Zie Ontwikkelen met overlays voor meer informatie.) Dit heeft nog steeds veel problemen veroorzaakt bij het upgraden van AEM als de inhoud in **/libs** kan veranderen waardoor de overlayfunctie op onverwachte manieren wordt onderbroken. Klanten kunnen ook AEM componenten uitbreiden via overerving via `sling:resourceSuperType`of gewoon verwijzen naar een component in **/libs** rechtstreeks via sling:resourceType. Vergelijkbare upgradeproblemen kunnen optreden met verwijzing en gebruikstoepassingen negeren.

Om het voor klanten veiliger en gemakkelijker te maken te begrijpen welke gebieden **/libs** zijn veilig te gebruiken en de inhoud te bedekken in **/libs** is ingedeeld met de volgende mengsels:

* **Public (granite:PublicArea)** - Definieert een knooppunt als &#39;public&#39;, zodat het kan worden bedekt, overgeërfd ( `sling:resourceSuperType`) of rechtstreeks gebruikt ( `sling:resourceType`). De knopen onder /libs duidelijk als Openbaar zullen veilig zijn om met de toevoeging van een Pakket van de Verenigbaarheid te bevorderen. In het algemeen moeten klanten alleen knooppunten gebruiken die zijn gemarkeerd als Public.

* **Abstract (graniet:AbstractArea)** - Definieert een knooppunt als abstract. Knooppunten kunnen worden bedekt of overgeërfd ( `sling:resourceSupertype`) maar mag niet rechtstreeks worden gebruikt ( `sling:resourceType`).

* **Final (graniet:FinalArea)** - Definieert een knooppunt als definitief. Als definitief geclassificeerde knooppunten kunnen niet worden bedekt of overgeërfd. Uiteindelijke knooppunten kunnen rechtstreeks via `sling:resourceType`. Subknooppunten onder eindknooppunt worden standaard als intern beschouwd

* **Internal (granite:InternalArea)** - Definieert een knooppunt als internal. Als internal geclassificeerde knooppunten kunnen niet worden bedekt, overgeërfd of rechtstreeks worden gebruikt. Deze knooppunten zijn alleen bedoeld voor de interne functionaliteit van AEM

* **Geen aantekening** - Knooppunten nemen een classificatie over op basis van de boomhiërarchie. De /-hoofdmap is standaard Openbaar. **Knooppunten met een als intern of definitief ingedeelde ouder moeten ook als intern worden behandeld.**

>[!NOTE]
>
>Dit beleid wordt slechts afgedwongen tegen het Verdelen van onderzoekspad gebaseerde mechanismen. Andere gebieden van **/libs** zoals een clientbibliotheek kan worden gemarkeerd als `Internal`, maar kan nog steeds worden gebruikt met standaard clientlib inclusie. Het is belangrijk dat een klant in deze gevallen de interne classificatie blijft respecteren.

#### Type-indicatoren voor CRXDE Lite-inhoud {#crxde-lite-content-type-indicators}

De in CRXDE Lite toegepaste mengsels zullen inhoudsknopen en bomen tonen die als worden gemerkt `INTERNAL` als grijs. Voor `FINAL` alleen het pictogram wordt grijs weergegeven. De onderliggende knooppunten van deze knooppunten worden ook grijs weergegeven. In beide gevallen is de functie Overlayknooppunt uitgeschakeld.

**Openbaar**

![image2018-2-8_23-34-5](assets/image2018-2-8_23-34-5.png)

**Definitief**

![image2018-2-8_23-34-56](assets/image2018-2-8_23-34-56.png)

**Intern**

![image2018-2-8_23-38-23](assets/image2018-2-8_23-38-23.png)

**Controle van inhoudsstatus**

AEM 6.4 wordt verzonden met een health check om klanten te waarschuwen als overlay of inhoud waarnaar wordt verwezen wordt gebruikt op een manier die niet in overeenstemming is met de inhoudclassificatie.

De **Toegangscontrole voor verkoop/graniet** is een nieuwe health check die de repository controleert om te zien of de code van de klant de beveiligde nodes in AEM op onjuiste wijze benadert.

Deze scan **/apps** en duurt meestal enkele seconden.

Voor toegang tot deze nieuwe health check moet u het volgende doen:

1. Navigeer in het AEM Startscherm naar **Gereedschappen > Bewerkingen > Gezondheidsrapporten**
1. Klik op de knop **Toegangscontrole voor verkoop/graniet** zoals hieronder weergegeven:

   ![screen_shot_2017-12-14at55648pm](assets/screen_shot_2017-12-14at55648pm.png)

Nadat het aftasten volledig is, zal een lijst van waarschuwingen aan een eind - gebruiker op de hoogte brengen van de beschermde knoop die verkeerd referenced is:

![screenshot-2018-2-5health reports](assets/screenshot-2018-2-5healthreports.png)

Na het herstellen van de overtredingen keert het terug naar de groene staat:

![screenshot-2018-2-5health reports-violi](assets/screenshot-2018-2-5healthreports-violations.png)

De gezondheidscontrole toont informatie die door de achtergronddienst wordt verzameld die asynchroon controleert wanneer een bekleding of middeltype over alle Verschuivende onderzoekspaden wordt gebruikt. Als inhoudmix onjuist wordt gebruikt, wordt een schending gerapporteerd.
