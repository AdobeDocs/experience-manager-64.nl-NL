---
title: Integreren met Adobe Campaign Standard
seo-title: Integrating with Adobe Campaign Standard
description: Integreren met Adobe Campaign Standard.
seo-description: Integrating with Adobe Campaign Standard.
uuid: ef31339e-d925-499c-b8fb-c00ad01e38ad
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: integration
content-type: reference
discoiquuid: 5c0fec99-7b1e-45d6-a115-e498d288e9e1
exl-id: d8d62c2f-3aa5-4fc9-8f42-86d75b6558ce
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1349'
ht-degree: 0%

---

# Integreren met Adobe Campaign Standard{#integrating-with-adobe-campaign-standard}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

>[!NOTE]
>
>In deze documentatie wordt beschreven hoe u AEM kunt integreren met Adobe Campaign Standard, de op abonnementen gebaseerde oplossing. Als u Adobe Campaign 6.1 gebruikt, zie [Integratie met Adobe Campaign 6.1](/help/sites-administering/campaignonpremise.md) voor die instructies.

Met Adobe Campaign kunt u inhoud en formulieren voor e-maillevering rechtstreeks in Adobe Experience Manager beheren.

Om beide oplossingen samen te gebruiken tezelfdertijd, moet u hen eerst vormen om met elkaar te verbinden. Dit omvat configuratiestappen in zowel Adobe Campaign als Adobe Experience Manager. Deze stappen worden in dit document uitgebreid beschreven.

Als u met Adobe Campaign in AEM werkt, kunt u e-mail en formulieren via Adobe Campaign verzenden. Dit wordt beschreven op [Werken met Adobe Campaign](/help/sites-authoring/campaign.md).

Bovendien kunnen de volgende onderwerpen van belang zijn wanneer het integreren van AEM met [Adobe Campaign](https://docs.campaign.adobe.com/doc/standard/en/home.html):

* [Aanbevolen procedures voor e-mailsjablonen](/help/sites-administering/best-practices-for-email-templates.md)
* [Problemen met de integratie met Adobe Campaign oplossen](/help/sites-administering/troubleshooting-campaignintegration.md)

Als u uw integratie met Adobe Campaign uitbreidt, wilt u wellicht de volgende pagina&#39;s zien:

* [Aangepaste extensies maken](/help/sites-developing/extending-campaign-extensions.md)
* [Aangepaste formuliertoewijzingen maken](/help/sites-developing/extending-campaign-form-mapping.md)

## Adobe Campaign configureren {#configuring-adobe-campaign}

Bij het configureren van Adobe Campaign gaat het om het volgende:

1. Het vormen van **aemserver** gebruiker.
1. Een speciale externe account maken.
1. De optie AEMResourceTypeFilter controleren.
1. Een toegewezen leveringssjabloon maken.

>[!NOTE]
>
>Als u deze bewerkingen wilt uitvoeren, moet u beschikken over de **administratie** rol in Adobe Campaign.

### Vereisten {#prerequisites}

Zorg ervoor dat u de volgende elementen vooraf hebt:

* [Een AEM-ontwerpinstantie](/help/sites-deploying/deploy.md#getting-started)
* [Een AEM-publicatie-instantie](/help/sites-deploying/deploy.md#author-and-publish-installs)
* [Een Adobe Campaign-instantie](https://docs.adobe.com/content/docs/en/campaign/ACS.html)

>[!CAUTION]
>
>In de [Adobe Campaign configureren](#configuring-adobe-campaign) en [Adobe Experience Manager configureren](#configuring-adobe-experience-manager) -secties zijn nodig om de integratiefuncties tussen AEM en Adobe Campaign correct te laten werken.

### De servergebruiker configureren {#configuring-the-aemserver-user}

De **aemserver** gebruiker moet in Adobe Campaign zijn geconfigureerd. De **aemserver** is een technische gebruiker die zal worden gebruikt om de AEM server aan Adobe Campaign aan te sluiten.

Ga naar **Beheer** >  **Gebruikers en beveiliging** >  **Gebruikers** en selecteert u de **aemserver** gebruiker. Klik erop om de gebruikersinstellingen te openen.

* U moet een wachtwoord instellen voor deze gebruiker. Dit kan niet via UI worden gedaan. Deze configuratie moet in REST door een technische beheerder worden gedaan.
* U kunt specifieke rollen aan deze gebruiker toewijzen, zoals **deliveryPrepare**, waarmee de gebruiker leveringen kan maken en bewerken.

### Een externe Adobe Experience Manager-account configureren {#configuring-an-adobe-experience-manager-external-account}

U moet een externe account configureren waarmee u Adobe Campaign kunt verbinden met uw AEM.

>[!NOTE]
>
>Zorg er AEM voor dat u het wachtwoord voor de externe gebruiker van de campagne instelt. U moet dit wachtwoord instellen om Adobe Campaign te verbinden met AEM. Meld u aan als beheerder en in de beheerconsole van de gebruiker, zoek naar de externe gebruiker van de campagne en klik op **Wachtwoord instellen**.

Een AEM externe account configureren:

1. Ga naar **Beheer** > **Toepassingsinstellingen** > **Externe rekeningen**.

   ![chlimage_1-124](assets/chlimage_1-124.png)

1. Standaard selecteren **aemInstance** externe account of maak een nieuwe account door op de knop **Maken** knop.
1. Selecteren **Adobe Experience Manager** i n de **Type** en voer de toegangsparameters in die worden gebruikt voor uw AEM ontwerpinstantie: serveradres, accountnaam en wachtwoord.

   >[!NOTE]
   >
   >Zorg ervoor dat u geen einde toevoegt **/** slash aan het einde van de URL, anders werkt de verbinding niet.

1. Zorg ervoor dat de **Ingeschakeld** Selectievakje is geselecteerd en klik vervolgens op **Opslaan** om uw wijzigingen op te slaan.

### De optie AEMResourceTypeFilter controleren {#verifying-the-aemresourcetypefilter-option}

De **AEMResourceTypeFilter** wordt gebruikt om typen AEM te filteren die in Adobe Campaign kunnen worden gebruikt. Op deze manier kan Adobe Campaign AEM inhoud ophalen die specifiek is ontworpen voor gebruik in alleen Adobe Campaign.

Deze optie is vooraf geconfigureerd; als u deze optie wijzigt, kan dit echter tot een niet-functionerende integratie leiden.

Om het **AEMResourceTypeFilter** Deze optie is geconfigureerd:

1. Ga naar **Beheer** > **Toepassingsinstellingen** > **Opties**.
1. In de lijst kunt u ervoor zorgen dat **AEMResourceTypeFilter** wordt weergegeven en de paden correct zijn.

### Een AEM specifieke sjabloon voor e-maillevering maken {#creating-an-aem-specific-email-delivery-template}

Standaard is de functie AEM niet ingeschakeld in e-mailsjablonen van Adobe Campaign. U kunt een nieuwe sjabloon voor e-maillevering configureren die wordt gebruikt om e-mails met AEM inhoud te maken.

Een AEM-specifieke sjabloon voor e-maillevering maken:

1. Ga naar **Bronnen** > **Sjablonen** > **Afleveringssjablonen**.
1. **Selectie inschakelen** door op het vinkje op de actiebalk te klikken en de bestaande **Standaard-e-mail (e-mail)** standaardsjabloon, vervolgens dupliceren door op de knop **Kopiëren** pictogram en klikken **Bevestigen**.
1. Schakel de selectiemodus uit door op de knop **x** en opent u het nieuwe **Kopie van standaard-e-mail (e-mail)** sjabloon, selecteert u vervolgens **Eigenschappen bewerken** in de actiebalk van het sjabloondashboard.

   U kunt de sjablonen wijzigen **Label**.

1. In de eigenschappen **Inhoud** sectie, wijzigt u de **Inhoudsbron** tot **Adobe Experience Manager**. Selecteer vervolgens de externe account die eerder is gemaakt en klik op **Bevestigen**.

   Wijzigingen opslaan door op **Bevestigen** en klikken **Opslaan.**

   De functie AEM inhoud is ingeschakeld voor e-mailleveringen die zijn gemaakt op basis van deze sjabloon.

   ![chlimage_1-125](assets/chlimage_1-125.png)

## Adobe Experience Manager configureren {#configuring-adobe-experience-manager}

Om AEM te vormen, moet u het volgende doen:

* Configureer replicatie tussen instanties.
* Sluit AEM aan op Adobe Campaign.
* Configureer de externalizer.

### Replicatie tussen AEM instanties configureren {#configuring-replication-between-aem-instances}

Inhoud die is gemaakt van de AEM authoring instantie wordt eerst naar de publishing-instantie verzonden. Deze publicatie-instantie brengt de inhoud vervolgens over naar Adobe Campaign. De replicatieagent moet daarom worden gevormd om van de AEM auteursinstantie aan de AEM het publiceren instantie te herhalen.

>[!NOTE]
>
>Als u de replicatie-URL niet wilt gebruiken maar in plaats daarvan de openbare URL, kunt u de instelling **Openbare URL** in de volgende configuratie-instelling in de OSGi (**Gereedschappen** > **Webconsole** > **OSGi Configuration > AEM Campagne Integration - Configuration**):
**Openbare URL:** com.day.cq.mcm.campagne.impl.IntegrationConfigImpl#aem.mcm.campagne.publicUrl

Deze stap is ook nodig om bepaalde configuraties van ontwerpinstanties te repliceren in de publicatieinstantie.

Om replicatie tussen AEM instanties te vormen:

1. Selecteer in de ontwerpinstantie **AEM**> **Gereedschappen **pictogram > **Implementatie** > **Replicatie** > **Medewerkers op auteur** en klik vervolgens op **Standaardagent**.

   ![chlimage_1-126](assets/chlimage_1-126.png)

   >[!NOTE]
   Vermijd het gebruik van localhost (een lokale kopie van AEM) bij het configureren van uw integratie met Adobe Campaign, tenzij de publicatie- en auteurinstantie beide op dezelfde computer staan.

1. Klikken **Bewerken** Selecteer vervolgens de **Vervoer** tab.
1. URI configureren door vervangen **localhost** met het IP-adres of het adres van de AEM publicerende instantie.

   ![chlimage_1-127](assets/chlimage_1-127.png)

### AEM verbinden met Adobe Campaign {#connecting-aem-to-adobe-campaign}

Voordat u AEM en Adobe Campaign samen kunt gebruiken, moet u het verband tussen beide oplossingen tot stand brengen zodat zij kunnen communiceren.

1. Verbind met uw AEM authoring instantie.
1. Selecteren **Gereedschappen** > **Bewerkingen** > **Wolk** > **Cloud Services** vervolgens **Nu configureren** in de sectie Adobe Campaign.

   ![chlimage_1-128](assets/chlimage_1-128.png)

1. Maak een nieuwe configuratie door een **Titel** en klik op **Maken** of kies de bestaande configuratie die u met uw Adobe Campaign-instantie wilt koppelen.
1. Bewerk de configuratie zodat deze overeenkomt met de parameters van uw Adobe Campaign-instantie.

   * **Gebruikersnaam**: **aemserver**, de Adobe Campaign AEM Integration package operator gebruikt om het verband tussen de twee oplossingen tot stand te brengen.
   * **Wachtwoord**: Wachtwoord Adobe Campaign-beheerder. U moet het wachtwoord voor deze operator mogelijk rechtstreeks in Adobe Campaign opnieuw opgeven.
   * **API-eindpunt**: Adobe Campaign-instantie-URL.

1. Selecteren **Verbinding maken met Adobe Campaign** en klik op **OK**.

   ![chlimage_1-129](assets/chlimage_1-129.png)

   >[!NOTE]
   Na u [Maak uw e-mail en publiceer deze](/help/sites-authoring/campaign.md)moet u de configuratie opnieuw publiceren naar uw publicatieexemplaar.

   ![chlimage_1-130](assets/chlimage_1-130.png)

>[!NOTE]
Als de verbinding ontbreekt, zorg ervoor u het volgende controleert:
* Er kan een certificaatprobleem optreden wanneer u een beveiligde verbinding met een Adobe Campaign-instantie (https) gebruikt. U moet het Adobe Campaign-instantiecertificaat toevoegen aan het **cacerts **bestand van uw JDK.
* Zie ook [Problemen met de integratie van AEM/Adobe Campaign oplossen](/help/sites-administering/troubleshooting-campaignintegration.md).
>


### De externalizer configureren {#configuring-the-externalizer}

U moet [de extern alizer configureren](/help/sites-developing/externalizer.md) in AEM op uw auteurinstantie. ExternalAlizer is de dienst OSGi die u een middelweg in een externe en absolute URL laat omzetten. Deze service biedt een centrale plaats om die externe URL&#39;s te configureren en samen te stellen.

Zie [De externalizer configureren](/help/sites-developing/externalizer.md) voor algemene instructies. Voor de integratie met Adobe Campaign moet u de publicatieserver configureren op `https://<host>:<port>/system/console/configMgr/com.day.cq.commons.impl.ExternalizerImpl` verwijst niet naar `localhost:4503` maar aan een server die door de console van Adobe Campaign bereikbaar is.

Als deze naar `localhost:4503` of een andere server die Adobe Campaign niet kan bereiken, worden uw afbeeldingen niet weergegeven op de Adobe Campaign-console.

![chlimage_1-131](assets/chlimage_1-131.png)
