---
title: Op AI gebaseerde codering configureren met behulp van de Smart Content Service
description: Leer hoe u slimme tags en verbeterde slimme tags kunt configureren in AEM met behulp van de Smart Content Service.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 90d39315207129aa4fc616e6fffb4bad5c450a7b

---


# Asset tagging configureren met behulp van de Smart Content Service {#configure-asset-tagging-using-the-smart-content-service}

Leer hoe u slimme tags en verbeterde slimme tags kunt configureren in AEM met behulp van de Smart Content Service.

U kunt Adobe Experience Manager (AEM) integreren met de Smart Content Service. Met deze configuratie hebt u vanuit AEM toegang tot de service Slimme inhoud en kunt u uw afbeeldingen automatisch labelen.

Het artikel detailleert de volgende zeer belangrijke taken uit die worden vereist om de Slimme Dienst van de Inhoud te vormen. Aan de achterkant verifieert de AEM-server uw servicegegevens met de Adobe IO-gateway voordat uw verzoek naar de Smart Content Service wordt doorgestuurd.

1. Creeer een Slimme configuratie van de Dienst van de Inhoud in AEM om een openbare sleutel te produceren. Overheidscertificaat verkrijgen voor OAuth-integratie.
1. Maak een integratie in Adobe I/O en upload de gegenereerde openbare sleutel.
1. Configureer uw AEM-instantie met behulp van de API-sleutel en andere referenties van Adobe I/O.
1. Schakel eventueel automatische labeling in bij het uploaden van elementen.

## Vereisten {#prerequisites}

Voordat u de Smart Content Service kunt gebruiken, moet u het volgende doen om een integratie in de Adobe I/O te maken:

* Een Adobe-id-account met beheerdersrechten voor de organisatie.
* De service Smart Content Service is ingeschakeld voor uw organisatie.

Om Verbeterde Slimme Markeringen toe te laten, naast bovenstaand, installeer ook het recentste de dienstpak [van](https://helpx.adobe.com/experience-manager/aem-releases-updates.html)AEM.

## Openbaar certificaat verkrijgen {#obtain-public-certificate}

Met een openbaar certificaat kunt u uw profiel verifiëren op Adobe I/O.

1. Tik in de AEM-gebruikersinterface op het AEM-logo en ga naar **[!UICONTROL Gereedschappen]** > **[!UICONTROL Cloud Services]** > **[!UICONTROL Oudere Cloud Services]**.

1. Tik/klik op **[!UICONTROL Nu]** configureren onder Slimme tags voor **[!UICONTROL middelen op de pagina Cloud Services]**.
1. Geef in het dialoogvenster Configuratie **** maken een titel en naam op voor de configuratie Slimme tags. Tik/klik op **[!UICONTROL Maken]**.
1. Gebruik de volgende waarden in het dialoogvenster **[!UICONTROL AEM Smart Content Service]** :

   **[!UICONTROL Service-URL]**: `https://mc.adobe.io/marketingcloud/smartcontent`

   **[!UICONTROL Autorisatieserver]**: `https://ims-na1.adobelogin.com`

   Laat de overige velden voorlopig leeg (later te verstrekken). Tik/klik op **[!UICONTROL OK]**.

   ![Dialoogvenster van de AEM Smart Content Service voor het aanbieden van de inhoudsservice-URL](assets/aem_scs.png)

   >[!NOTE]
   >
   >De URL die als [!UICONTROL service-URL] wordt opgegeven, is niet toegankelijk via de browser en genereert een fout van 404. De configuratie werkt O.K. met de zelfde waarde van de parameter van [!UICONTROL Dienst URL] . Zie [https://status.adobe.com](https://status.adobe.com)voor een algemeen overzicht van de status en het onderhoudsschema van de Adobe I/O-service.

1. Tik/klik op Openbaar certificaat **[!UICONTROL downloaden voor OAuth Integration]** en download het openbare certificaatbestand `AEM-SmartTags.crt`.

   ![Een voorstelling van de instellingen die voor de service voor slimme tags zijn gemaakt](assets/download_link.png)

## Adobe I/O-integratie maken {#create-adobe-i-o-integration}

Als u API&#39;s voor Smart Content Service wilt gebruiken, maakt u een integratie in Adobe I/O om API-sleutel, technische account-id, organisatie-id en clientgeheim te genereren.

1. Ga naar [https://console.adobe.io](https://console.adobe.io/).
1. Selecteer uw organisatie op de pagina **[!UICONTROL Integraties]** .
1. Tik/klik op **[!UICONTROL Nieuwe integratie]**.
1. Selecteer **[!UICONTROL Toegang tot een API]** op de **[!UICONTROL pagina Een nieuwe integratie]** maken. Tik/klik op **[!UICONTROL Doorgaan]**.
1. Selecteer onder **[!UICONTROL Experience Cloud]** de optie **[!UICONTROL Slimme inhoud]**. Tik/klik op **[!UICONTROL Doorgaan]**.

   ![Selecteer bij het maken van een nieuwe integratie de optie Slimme inhoud onder Experience Cloud met de beschikbare opties](assets/smart_content.png)

1. Selecteer **[!UICONTROL Nieuwe integratie]** op de volgende pagina. Tik/klik op **[!UICONTROL Doorgaan]**.
1. Voor de pagina van de Details **[!UICONTROL van de]** Integratie, specificeer een naam voor de integratiesgateway en voeg een beschrijving toe.
1. Upload in de certificaten **[!UICONTROL met]** openbare sleutels `AEM-SmartTags.crt` het bestand dat u hierboven hebt gedownload.
1. Tik/klik op **[!UICONTROL Integratie]** maken.
1. Tik op of klik op **[!UICONTROL Doorgaan naar integratiegegevens]** om de integratiegegevens weer te geven.

   ![Op het tabblad Overzicht kunt u de informatie bekijken die voor integratie is opgegeven.](assets/integration_details.png)

## Smart Content Service configureren {#configure-smart-content-service}

Als u de integratie wilt configureren, gebruikt u de waarden Technical Account ID, Organization ID, Client Secret, Authorization Server en API-sleutelvelden van de Adobe I/O-integratie. Door een cloud-configuratie met slimme tags te maken, kunnen API-aanvragen van de AEM-instantie worden geverifieerd.

1. Tik in de AEM-gebruikersinterface op het AEM-logo of klik erop. Ga naar **[!UICONTROL Extra > Cloud Service > Legacy Cloud Services]** om de Cloud Services-console te openen.
1. Open de hierboven gemaakte configuratie onder Slimme **[!UICONTROL elementtags]**. Klik op de pagina met service-instellingen op **[!UICONTROL Bewerken]**.
1. Gebruik in het dialoogvenster **[!UICONTROL AEM Smart Content Service]** de vooraf ingevulde waarden voor de velden **[!UICONTROL Service URL]** en **[!UICONTROL Authorization Server]** .
1. Gebruik bovenstaande waarden voor de velden API-sleutel, Technical Account ID, Organization-id en Client Secret.

## De configuratie valideren {#validate-the-configuration}

Nadat u de configuratie hebt voltooid, kunt u een JMX MBean gebruiken om de configuratie te bevestigen. Voer de volgende stappen uit om te valideren.

1. In AEM, om console te openen OSGi, klik **[!UICONTROL Hulpmiddelen > Verrichtingen > de Console]** van het Web. Klik op **[!UICONTROL Hoofd > JMX]**.
1. Klik op **[!UICONTROL com.day.cq.dam.similaritysearch.internal.impl]**. Het opent **[!UICONTROL GelijksoortigheidOnderzoek Diverse Taken.]**
1. Klik op **[!UICONTROL validateConfigs()]**. Klik in het dialoogvenster **[!UICONTROL Configuraties]** valideren op **[!UICONTROL Invoke]**.

   Het validatieresultaat wordt in hetzelfde dialoogvenster weergegeven.

## Slimme tags toepassen inschakelen in de DAM Update Asset-workflow (optioneel) {#enable-smart-tagging-in-the-update-asset-workflow-optional}

1. Tik in de AEM-gebruikersinterface of klik op het AEM-logo en ga naar **[!UICONTROL Gereedschappen > Workflow > Modellen]**.
1. Selecteer op de pagina **[!UICONTROL Workflowmodellen]** het workflowmodel **[!UICONTROL DAM Update Asset]** .
1. Tik/klik op **[!UICONTROL Bewerken]** op de werkbalk.
1. Vouw het zijpaneel uit om de stappen weer te geven. Sleep de stap **[!UICONTROL Slim tagelement]** die beschikbaar is in de DAM-workflowsectie en plaats deze na de stap Miniaturen **** verwerken.

   ![De stap Slim tagelement toevoegen na de stap met de procesminiaturen in de DAM Update Asset-workflow](assets/chlimage_1-105.png)

1. Open de stap in de bewerkingsmodus. Controleer of onder **[!UICONTROL Geavanceerde instellingen]** de optie **[!UICONTROL Handler Advance]** is geselecteerd.

   ![chlimage_1-106](assets/chlimage_1-106.png)

1. Selecteer op het tabblad **[!UICONTROL Argumenten]** de optie Fouten **** negeren als u wilt dat de workflow wordt voltooid, zelfs als de stap Automatisch labelen mislukt.

   ![chlimage_1-107](assets/chlimage_1-107.png)

   Als u elementen wilt labelen terwijl ze worden geüpload, ongeacht of slimme tags zijn ingeschakeld in mappen, selecteert u **[!UICONTROL Slimme tagmarkering]** negeren.

   ![chlimage_1-108](assets/chlimage_1-108.png)

1. Tik/klik op **[!UICONTROL OK]** om de processtap te sluiten en sla de workflow vervolgens op.

>[!MORELIKETHIS]
>
>* [Slimme tags in AEM-elementen begrijpen](https://helpx.adobe.com/experience-manager/kt/assets/using/smart-tags-feature-video-understand.html)
>* [Slimme tags gebruiken met AEM-elementen](https://helpx.adobe.com/experience-manager/kt/assets/using/smart-tags-feature-video-use.html)
>* [Uitgebreide slimme tags gebruiken met AEM-elementen](https://helpx.adobe.com/experience-manager/kt/assets/using/enhanced-smart-tags-feature-video-use.html)
>* [Verbeterde slimme tags instellen in AEM-elementen](https://helpx.adobe.com/experience-manager/kt/assets/using/enhanced-smart-tags-technical-video-setup.html)

