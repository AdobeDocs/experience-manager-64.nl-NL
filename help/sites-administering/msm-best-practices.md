---
title: Aanbevolen MSM-procedures
seo-title: MSM Best Practices
description: Zoek naar beste praktijken die door Adobe engineering en consultancyteams worden gecompileerd helpen om met de AEM MultiManager van de Plaats in gebruik te worden.
seo-description: Find best practices compiled by Adobe engineering and consulting teams to help get up and running with the AEM Multi Site Manager.
uuid: cbb598bb-ec8f-4985-97af-7c87f5891c66
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: site-features, best-practices
content-type: reference
discoiquuid: 04344537-7485-40a9-ad14-804ba448f1e2
feature: Multi Site Manager
exl-id: f23a1c62-0191-4b5b-90be-d66d51e38f83
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1558'
ht-degree: 0%

---

# Aanbevolen MSM-procedures{#msm-best-practices}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Algemeen {#general}

MSM is een configureerbaar framework voor het automatiseren van de implementatie van inhoud. Bij implementaties gaat het vaak om grote delen van een website en meerdere organisaties en geografische gebieden. Daarom wordt u ten zeerste aangeraden MSM-implementaties net zo zorgvuldig te plannen als uw website:

* zorgvuldig **planstructuur en inhoudsstromen** voordat de implementatie wordt gestart.
* **Pas de aanpassingen zoveel als nodig is, maar zo weinig mogelijk.** Hoewel MSM een hoge mate van aanpassing (bijvoorbeeld rollout configuraties) steunt, typisch is de beste praktijken voor de prestaties, de betrouwbaarheid en de upgradeability van uw website aanpassing minimaliseren.
* Een **bestuur** model in een vroeg stadium, en de gebruikers dienovereenkomstig trainen, om succes te verzekeren. Een goede praktijk vanuit bestuurlijk oogpunt is: **de autoriteit die producenten van lokale inhoud hebben** inhoud toewijzen/verbinden aan andere lokale gebruikers en hun respectievelijke live kopieën. Dit komt omdat onbestuurde, geketende overerving de complexiteit van een MSM-structuur aanzienlijk kan verhogen en de prestaties en betrouwbaarheid ervan in gevaar kan brengen.

* Zodra er een plan voor uw structuur, inhoudsstromen, automatisering en bestuur bestaat - **prototype maken en uw systeem grondig testen**, voordat wordt begonnen met de live implementatie.
* Houd er rekening mee dat **Adobe Consulting en toonaangevende systeemintegrators** hebben diepe ervaring planning en het uitvoeren van inhoudautomatisering met MSM, zodat kunnen zij u zowel beginnen met uw project MSM als door zijn volledige implementatie helpen.

>[!NOTE]
>
>Meer informatie over het werken met MSM is te vinden in de artikelen in de Knowledge Base:
>
>* [Veelgestelde vragen over MSM](https://helpx.adobe.com/experience-manager/kb/index/msm_faq.html)
>* [Problemen met MSM oplossen](https://helpx.adobe.com/experience-manager/kb/troubleshooting-aem-msm-issues.html)
>


>[!NOTE]
>
>U kunt ook de opdracht [Referentiecomponent](/help/sites-authoring/default-components-foundation.md#reference) om één pagina of alinea opnieuw te gebruiken. Houd echter rekening met:
>
>* MSM is flexibeler en staat fijnkorrelige controle over toe welke inhoud wordt gesynchroniseerd en wanneer.
>* [Basiscomponenten](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html) worden nu aanbevolen voor de basiscomponenten.
>


## Live Copy-bronnen en configuraties voor blauwdrukken {#live-copy-sources-and-blueprint-configurations}

Houd er rekening mee dat een live kopie kan worden gemaakt met een van de volgende [gewone pagina&#39;s](/help/sites-administering/msm-livecopy.md#creating-a-live-copy-of-a-page) of [blauwdrukconfiguratie](/help/sites-administering/msm-livecopy.md#creating-a-live-copy-of-a-site-from-a-blueprint-configuration). Beide zijn geldige gebruiksgevallen.

De extra voordelen van het gebruiken van een blauwdrukconfiguratie zijn dat zij:

* Laat de auteur het **Uitrol** optie op een blauwdruk - naar (uitdrukkelijk) duw wijzigingen aan levende exemplaren die van dit blauwdruk erven.
* Laat de auteur gebruiken **Site maken**; hierdoor kan de gebruiker eenvoudig talen selecteren en de structuur van de live kopie configureren .
* Definieer een standaardrollout-configuratie voor live kopieën die een relatie hebben met de blauwdruk.

Als er niet naar een blauwdrukconfiguratie wordt verwezen, kunnen rollouts alleen worden geïnitieerd vanuit de live kopieën zelf, waarbij inhoud van de bron wordt opgehaald.

Wanneer het creëren van een nieuwe plaats met levende kopie, is het voordelig om blauwdrukconfiguraties tot stand te brengen om de beschikbaarheid van de volledige MSM eigenschapreeks te verzekeren.

>[!NOTE]
>
>U kunt CUG-groepen niet uitrollen naar Actieve kopieën van blauwdrukken. Plan dit probleem bij het configureren van Live Copy.

## Componenten en containersynchronisatie {#components-and-container-synchronization}

In het algemeen, is de rollout regel in MSM betreffende de synchronisatie van componenten:

* Componenten worden gesynchroniseerd met alle bronnen in de blauwdruk.
* Containers synchroniseren alleen de huidige bron.

Dit betekent dat componenten als aggregaat worden behandeld, en in een rollout worden de component zelf en al zijn kinderen vervangen met die in de blauwdrukken. Dit betekent dat als een bron lokaal aan een dergelijke component wordt toegevoegd, deze bij rollout verloren gaat aan de inhoud van de blauwdruk.

Om het nesten van componenten te steunen zodat de plaatselijk toegevoegde componenten in een rollout worden gehandhaafd, moet de component als container worden verklaard. Als voorbeeld, wordt standaard parsys verklaard als container zodat kan het plaatselijk-toegevoegde inhoud steunen.

>[!NOTE]
>
>De eigenschap toevoegen `cq:isContainer` aan de component om het als container aan te wijzen.

## Site maken {#create-site}

U ziet dat AEM twee hoofdbenaderingen heeft voor het maken van live kopieën:

* Wanneer [een actieve kopie maken](/help/sites-administering/msm-livecopy.md#creating-a-live-copy-of-a-page)

   Dit kan als generischere benadering worden beschouwd, toestaand u om levende exemplaren van om het even welke pagina tot stand te brengen. De inhoudsstructuur van een live kopie komt exact overeen met de bron.

* Wanneer [een site maken](/help/sites-administering/msm-livecopy.md#creating-a-live-copy-of-a-site-from-a-blueprint-configuration)

   Dit is een meer gespecialiseerde benadering, vooral voor het creëren van websites met een meertalige structuur.

Houd rekening met het volgende wanneer u een site maakt:

* Als u een nieuwe site wilt maken, hebt u een [blauwdrukconfiguratie](/help/sites-administering/msm-livecopy.md#managing-blueprint-configurations).
* Als u wilt dat de taalpaden op een nieuwe site kunnen worden geselecteerd, moeten de overeenkomstige taalwortels in de blauwdruk (bron) aanwezig zijn.
* Eenmaal [nieuwe site is gemaakt als een live kopie](/help/sites-administering/msm-livecopy.md#creating-a-live-copy-of-a-site-from-a-blueprint-configuration) (gebruiken **Maken** vervolgens **Site**), zijn de eerste twee niveaus van deze kopie *ondiep*. Onderliggende items van de pagina behoren niet tot de live-relatie, maar de rollout neemt wel af als een live-relatie wordt gevonden die overeenkomt met de trigger.

   Het helpt voorkomen:

   * handmatig talen toevoegen in de blauwdruk (onder het eerste niveau)
   * handmatig inhoud toevoegen direct onder de hoofdmap van de taal,
   * leidt er niet toe dat deze nieuwe inhoud automatisch bij de rollout naar de live kopie wordt overgedragen.

## MSM- en meertalige websites {#msm-and-multilingual-websites}

MSM kan op twee manieren helpen bij het maken van meertalige websites:

* Bij het maken van taalstramienen.

   * Terwijl MSM zelf **biedt geen vertaling van inhoud**, kan het met derde vertaalschakelaars worden geïntegreerd die doen. Houd er rekening mee dat:

      * Met MSM kunt u overerving op pagina- en/of componentniveau annuleren. Zo voorkomt u bij de volgende rollout dat vertaalde inhoud (van een live kopie met nog niet-vertaalde inhoud van een blauwdruk) wordt overschreven.
      * Sommige vertalingsconnectors van derden automatiseren dit beheer van MSM-overerving.

         Neem contact op met uw vertaalserviceprovider voor meer informatie.

      * Een alternatieve benadering voor het maken en vertalen van taalmeesters is het gebruik van taalkopieën in combinatie met AEM kader voor vertaalintegratie buiten de doos.

* Bij het uitrollen van inhoud van taalmeesters.

   * Bijvoorbeeld vanuit de Franse taal die master is voor landspecifieke sites, zoals Frankrijk/Frans, Canada/Frans, Zwitserland/Frans.

Zie voor meer informatie [Inhoud vertalen voor meertalige sites](/help/sites-administering/translation.md) en de [Aanbevolen werkwijzen voor vertaling](/help/sites-administering/tc-bp.md).

## Structuurwijzigingen en rollouts {#structure-changes-and-rollouts}

Wijzigingen in de inhoudsstructuur in een blauwdruk-/bronstructuur worden anders weerspiegeld in een live kopie. Dit is afhankelijk van het wijzigingstype:

* **Maken** nieuwe pagina&#39;s in een blauwdruk zullen ertoe leiden dat de overeenkomstige pagina&#39;s in levende exemplaren na rollout met de standaardrollout configuratie worden gecreeerd.

* **Verwijderen** De pagina&#39;s in een blauwdruk zullen in het overeenkomstige pagina&#39;s resulteren die uit levende exemplaren na rollout met de standaardrollout configuratie worden geschrapt.

* **Verplaatsen** pagina&#39;s in een blauwdruk **niet** resulterend in het verplaatsen van overeenkomstige pagina&#39;s in levende exemplaren na rollout met standaard rollout configuratie:

   * De reden voor dit gedrag is dat een paginabeweging impliciet een pagina-verwijdering bevat. Dit kan mogelijk leiden tot onverwacht gedrag bij het publiceren, omdat bij het verwijderen van pagina&#39;s bij de auteur de bijbehorende inhoud bij het publiceren automatisch wordt gedeactiveerd. Dit kan ook gevolgen hebben voor verwante punten zoals verbindingen, referenties, en anderen.
   * Inhoudsovererving op de respectievelijke pagina&#39;s met live kopieën wordt bijgewerkt om de nieuwe locatie van de bronnen in de blauwdruk te weerspiegelen.
   * Houd rekening met de volgende aanbevolen procedures om te zorgen dat een pagina van een blauwdruk naar live kopieën wordt verplaatst:

>[!NOTE]
>
>Dit werkt alleen met de [Bij rollout-trigger](https://helpx.adobe.com/experience-manager/6-3/sites/administering/using/msm-sync.html#rollout-triggers).

* Een aangepaste rollout-configuratie maken:

   * Deze nieuwe configuratie moet de actie omvatten:

      `PageMoveAction`

      Voeg geen andere acties aan deze configuratie toe.

* Plaats de nieuwe configuratie:

   * Als u de pagina volledig wilt uitrollen, verplaatst u de pagina&#39;s terwijl u de desbetreffende pagina&#39;s op hun oude locatie in de live kopie verwijdert:

      * Plaats de nieuw gecreëerde configuratie vóór de standaardrollout configuratie.

         De standaardrollout configuratie zal ervoor zorgen om de pagina&#39;s in hun oude plaats te schrappen.
   * Als u de pagina wilt uitrollen, verplaatst u de pagina&#39;s terwijl de respectievelijke pagina&#39;s op hun oude locatie in de live kopieën blijven staan (de inhoud wordt in feite gedupliceerd):

      * Plaats de nieuw gecreëerde configuratie na de standaardrollout configuratie.

         Zo voorkomt u dat inhoud wordt verwijderd uit de live kopie of gedeactiveerd uit publicatie.


## Rollen aanpassen {#customizing-rollouts}

MSM-rollout-configuraties zijn in hoge mate aanpasbaar. Het automatiseren van rollouts kan verstrekkende gevolgen hebben. Als beste praktijken, zou u moeten plannen *zeer* zorgvuldig vóór, bijvoorbeeld:

* het automatiseren van rollouts; bijvoorbeeld met [onModify-triggers](#onmodify),
* aanpassen [knooppunttypen/eigenschappen](#node-types-properties),
* volgende workflows starten,
* en/of inhoud activeren als onderdeel van rollouts.

### onModify {#onmodify}

Wanneer u de [rollout trigger](/help/sites-administering/msm-sync.md#rollout-triggers) `onModify` u dient in overweging te nemen dat :

* Rolouts automatiseren met `onModify` triggers kunnen een negatief effect hebben op de ontwerpprestaties omdat ze rollouts activeren na *elke* pagina wijzigen.

* Het rollout-resultaat kan afwijken van het verwachte resultaat:

   * U kunt de volgorde van de resulterende wijzigingsgebeurtenissen niet opgeven.
   * De op gebeurtenis-gebaseerde architectuur kan niet de opeenvolging van de gebeurtenissen waarborgen die tot de Manager van de Uitvoer worden overgegaan.

* Het gebruiken van zulk een rollout configuratie kon tot conflicten leiden als de gezamenlijke updates van het zelfde middel voorkomen.

Daarom wordt u aangeraden *alleen* gebruiken `onModify` veroorzaakt als de voordelen van automatische rollout initialisering om het even welke potentiële prestatieskwesties opwegen.

### Knooppunttypen/eigenschappen {#node-types-properties}

Houd er rekening mee dat:

* Naast het aanpassen van rollout acties, staat MSM u ook toe om knoopeigenschappen aan te passen die worden uitgerold. De [MSM OSGi configuratie staat u toe om knooptypes uit te sluiten](/help/sites-administering/msm-sync.md#excluding-properties-and-node-types-from-synchronization) van de bron naar de live kopie worden gekopieerd.

## Aanvullende informatie {#further-information}

Op deze en de volgende pagina&#39;s worden de gerelateerde kwesties besproken:

* [Actieve kopieën maken en synchroniseren](/help/sites-administering/msm-livecopy.md)
* [Console voor live kopiëren](/help/sites-administering/msm-livecopy-overview.md)
* [Synchronisatie van actieve kopie configureren](/help/sites-administering/msm-sync.md)
* [Conflicten MSM-rollout](/help/sites-administering/msm-rollout-conflicts.md)
