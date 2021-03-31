---
title: Vorm activa het etiketteren gebruikend de Slimme Dienst van de Inhoud.
description: Leer hoe u slimme tags en verbeterde slimme tags configureert in [!DNL Adobe Experience Manager] met de Smart Content Service.
contentOwner: AG
feature: Slimme tags,tags toepassen
role: Beheerder
translation-type: tm+mt
source-git-commit: 29e3cd92d6c7a4917d7ee2aa8d9963aa16581633
workflow-type: tm+mt
source-wordcount: '993'
ht-degree: 29%

---


# Asset tagging configureren met behulp van de Smart Content Service {#configure-asset-tagging-using-the-smart-content-service}

U kunt [!DNL Adobe Experience Manager] met de Slimme Dienst van de Inhoud integreren gebruikend [!DNL Adobe Developer Console]. Gebruik deze configuratie om tot de Slimme Dienst van de Inhoud van binnen [!DNL Experience Manager] toegang te hebben.

Het artikel detailleert de volgende zeer belangrijke taken uit die worden vereist om de Slimme Dienst van de Inhoud te vormen. Aan het achterste eind, verifieert de [!DNL Experience Manager] server uw de dienstgeloofsbrieven met de [!DNL Adobe Developer Console] gateway alvorens uw verzoek aan de Slimme Dienst van de Inhoud door:sturen.

1. [Creeer een Slimme Configuratie van de ](#obtain-public-certificate) Dienst van de Inhoud in  [!DNL Experience Manager] om een openbare sleutel te produceren. [Verkrijg een openbaar certificaat voor OAuth-integratie.](#obtain-public-certificate)

1. [Maak een integratie in Adobe Developer Console en upload de gegenereerde openbare sleutel.](#create-adobe-i-o-integration)

1. [Configureer uw ](#configure-smart-content-service) implementatie met behulp van de API-sleutel en andere referenties van  [!DNL Adobe Developer Console].

1. [Test de configuratie](#validate-the-configuration).

1. Schakel desgewenst automatische labeling in bij het uploaden van elementen](#enable-smart-tagging-in-the-update-asset-workflow-optional).[

## Vereisten {#prerequisites}

Voordat u de service Slimme inhoud gebruikt, moet u het volgende doen om een integratie te maken op [!DNL Adobe Developer Console]:

* Een Adobe ID-account met beheerdersrechten voor de organisatie.

* De Slimme Dienst van de Inhoud wordt toegelaten voor uw organisatie.

Om Verbeterde Slimme Markeringen toe te laten, naast het bovenstaande, installeer ook het recentste [de dienstpak van de Experience Manager](https://helpx.adobe.com/experience-manager/aem-releases-updates.html).

## Configuratie van Smart Content Service maken om een openbaar certificaat op te vragen {#obtain-public-certificate}

Met een openbaar certificaat kunt u uw profiel verifiëren op [!DNL Adobe Developer Console].

1. Ga in de [!DNL Experience Manager]-gebruikersinterface naar **[!UICONTROL Tools]** > **[!UICONTROL Cloud Services]** > **[!UICONTROL Legacy Cloud Services]**.

1. Klik op **[!UICONTROL Configure Now]** onder **[!UICONTROL Assets Smart Tags]** op de pagina Cloud Services.

1. Geef in het dialoogvenster **[!UICONTROL Create Configuration]** een titel en naam op voor de configuratie van slimme tags. Klik op **[!UICONTROL Create]**.

1. Gebruik de volgende waarden in het dialoogvenster **[!UICONTROL AEM Smart Content Service]**:

   **[!UICONTROL Service URL]**: `https://mc.adobe.io/marketingcloud/smartcontent`

   **[!UICONTROL Authorization Server]**:  `https://ims-na1.adobelogin.com`

   Laat de overige velden voorlopig leeg (later te verstrekken). Klik op **[!UICONTROL OK]**.

   ![Het dialoogvenster Experience Manager Smart Content Service om de contentservice-URL op te geven](assets/aem_scs.png)


   *Afbeelding: Het dialoogvenster Smart Content Service om de URL van de inhoudsservice te bieden*

   >[!NOTE]
   >
   >De URL die als [!UICONTROL Service URL] wordt opgegeven, is niet toegankelijk via de browser en genereert een fout van 404. De configuratie werkt O.K. met de zelfde waarde van de [!UICONTROL Service URL] parameter. Zie [https://status.adobe.com](https://status.adobe.com) voor het algemene servicestatus en onderhoudsplan.

1. Klik **[!UICONTROL Download Public Certificate for OAuth Integration]**, en download het openbare certificaatdossier `AEM-SmartTags.crt`.

   ![Een voorstelling van de instellingen die voor de service voor slimme tags zijn gemaakt](assets/smart-tags-download-public-cert.png)


   *Afbeelding: Instellingen voor service voor slimme tags*

### Opnieuw configureren wanneer een certificaat verloopt {#certrenew}

Nadat een certificaat is verlopen, wordt het niet meer vertrouwd. U kunt een verlopen certificaat niet verlengen. Voer de onderstaande stappen uit om een nieuw certificaat toe te voegen.

1. Meld u als beheerder aan bij uw [!DNL Experience Manager]-implementatie. Klik op **[!UICONTROL Tools]** > **[!UICONTROL Security]** > **[!UICONTROL Users]**.

1. Zoek en klik op **[!UICONTROL dam-update-service]**-gebruiker. Klik op het tabblad **[!UICONTROL Keystore]**. 

1. Verwijder het bestaande **[!UICONTROL similaritysearch]**-sleutelarchief met het verlopen certificaat. Klik op **[!UICONTROL Save & Close]**.

   ![Verwijder het bestaande zoekitem voor gelijkenis in Keystore om een nieuw beveiligingscertificaat toe te voegen](assets/smarttags_delete_similaritysearch_keystore.png)

   *Afbeelding: Verwijder de bestaande `similaritysearch`-vermelding in het sleutelarchief om een nieuw beveiligingscertificaat toe te voegen.*

1. Ga naar **[!UICONTROL Tools]** > **[!UICONTROL Cloud Services]** > **[!UICONTROL Legacy Cloud Services]**. Klik op **[!UICONTROL Asset Smart Tags]** > **[!UICONTROL Show Configuration]** > **[!UICONTROL Available Configurations]**. Klik op de gewenste configuratie.

1. Als u een openbaar certificaat wilt downloaden, klikt u op **[!UICONTROL Download Public Certificate for OAuth Integration]**.

1. Open [https://console.adobe.io](https://console.adobe.io) en navigeer naar de bestaande Smart Content Services op de pagina **[!UICONTROL Integrations]**. Upload het nieuwe certificaat. Zie de instructies in [Integratie van de Adobe Developer Console maken](#create-adobe-i-o-integration) voor meer informatie.

## Integratie van Adobe-ontwikkelaarsconsole maken {#create-adobe-i-o-integration}

Als u API&#39;s voor Smart Content Service wilt gebruiken, maakt u een integratie in de Adobe Developer Console voor [!UICONTROL API Key] (gegenereerd in [!UICONTROL CLIENT ID]-veld voor integratie van Adobe Developer Console), [!UICONTROL TECHNICAL ACCOUNT ID], [!UICONTROL ORGANIZATION ID] en [!UICONTROL CLIENT SECRET] voor [!UICONTROL Assets Smart Tagging Service Settings] van cloudconfiguratie in [!DNL Experience Manager].

1. Open [https://console.adobe.io](https://console.adobe.io/) in uw browser. Selecteer het gewenste account en verifieer dat de bijbehorende organisatierol is ingesteld op systeembeheerder.

1. Maak een project een geef het de gewenste naam. Klik op **[!UICONTROL Add API]**.

1. Selecteer op de pagina **[!UICONTROL Add an API]** **[!UICONTROL Experience Cloud]** en selecteer **[!UICONTROL Smart Content]**. Klik op **[!UICONTROL Next]**.

1. Selecteer **[!UICONTROL Upload your public key]**. Geef het certificaatbestand op dat u hebt gedownload van [!DNL Experience Manager]. Er wordt een [!UICONTROL Public key(s) uploaded successfully]-bericht weergegeven. Klik op **[!UICONTROL Next]**.

   De pagina [!UICONTROL Create a new Service Account (JWT) credential] toont de openbare sleutel voor het serviceaccount dat u zojuist hebt geconfigureerd. 

1. Klik op **[!UICONTROL Next]**.

1. Ga naar de pagina **[!UICONTROL Select product profiles]** en selecteer **[!UICONTROL Smart Content Services]**. Klik op **[!UICONTROL Save configured API]**.

   De pagina die verschijnt biedt meer informatie over de configuratie. Laat deze pagina open om deze waarden in [!UICONTROL Assets Smart Tagging Service Settings] van de wolkenconfiguratie in [!DNL Experience Manager] te kopiëren en toe te voegen om slimme markeringen te vormen.

   ![Op het tabblad Overview kunt u de informatie bekijken die is opgegeven voor de integratie.](assets/integration_details.png)

   *Afbeelding: Gegevens over de integratie in de Adobe Developer Console*

## Smart Content Service {#configure-smart-content-service} configureren

Om de integratie te vormen, gebruik de waarden van [!UICONTROL TECHNICAL ACCOUNT ID], [!UICONTROL ORGANIZATION ID], [!UICONTROL CLIENT SECRET], en [!UICONTROL CLIENT ID] gebieden van de integratie van de Console van de Ontwikkelaar van Adobe. Het creëren van een Slimme wolkenconfiguratie van Markeringen staat authentificatie van API verzoeken van de [!DNL Experience Manager] plaatsing toe.

1. Navigeer in [!DNL Experience Manager] naar **[!UICONTROL Tools > Cloud Service > Legacy Cloud Services]** om de [!UICONTROL Cloud Services]-console te openen.

1. Open onder **[!UICONTROL Assets Smart Tags]** de hierboven gemaakte configuratie. Klik op **[!UICONTROL Edit]** op de pagina met service-instellingen.

1. Gebruik in het dialoogvenster **[!UICONTROL AEM Smart Content Service]** de vooraf ingevulde waarden voor de velden **[!UICONTROL Service URL]** en **[!UICONTROL Authorization Server]**.

1. Voor de velden [!UICONTROL Api Key], [!UICONTROL Technical Account ID], [!UICONTROL Organization ID], en [!UICONTROL Client Secret], kopieer en gebruik de volgende waarden die in [de integratie van de Console van de Adobe worden geproduceerd ](#create-adobe-i-o-integration).

   | [!UICONTROL Assets Smart Tagging Service Settings] | [!DNL Adobe Developer Console] integratievelden |
   |--- |--- |
   | [!UICONTROL Api Key] | [!UICONTROL CLIENT ID] |
   | [!UICONTROL Technical Account ID] | [!UICONTROL TECHNICAL ACCOUNT ID] |
   | [!UICONTROL Organization ID] | [!UICONTROL ORGANIZATION ID] |
   | [!UICONTROL Client Secret] | [!UICONTROL CLIENT SECRET] |

## De configuratie valideren {#validate-the-configuration}

Nadat u de configuratie hebt voltooid, gebruik een JMX MBean om de configuratie te bevestigen. Voer de volgende stappen uit om te valideren.

1. Open uw [!DNL Experience Manager]-server op `https://[aem_server]:[port]`.

1. Ga naar **[!UICONTROL Tools > Operations > Web Console]** om de console te openen OSGi. Klik op **[!UICONTROL Main > JMX]**.

1. Klik op **[!UICONTROL com.day.cq.dam.similaritysearch.internal.impl]**. Het opent **[!UICONTROL SimilaritySearch Miscellaneous Tasks]**.

1. Klik op **[!UICONTROL validateConfigs()]**. Klik in het dialoogvenster **[!UICONTROL Validate Configurations]** op **[!UICONTROL Invoke]**.

   De validatieresultaten worden in hetzelfde dialoogvenster weergegeven.

## Slimme tags toepassen inschakelen in de DAM Update Asset-workflow (optioneel) {#enable-smart-tagging-in-the-update-asset-workflow-optional}

1. Ga in [!DNL Experience Manager] naar **[!UICONTROL Tools]** > **[!UICONTROL Workflow]** > **[!UICONTROL Models]**.

1. Selecteer op de pagina **[!UICONTROL Workflow Models]** het **[!UICONTROL DAM Update Asset]**-workflowmodel.

1. Klik op **[!UICONTROL Edit]** op de werkbalk.

1. Vouw het zijpaneel uit om de stappen weer te geven. Sleep de stap **[!UICONTROL Smart Tag Asset]** die beschikbaar is in de DAM-workflowsectie en plaats deze na de stap **[!UICONTROL Process Thumbnails]**.

   ![De stap Asset met slimme tag toevoegen na de stap met de procesminiaturen in de DAM Update Asset-workflow](assets/smart-tag-in-dam-update-asset-workflow.png)

   *Afbeelding: Voeg de stap Slimme tag-elementen toe na de stap met de procesminiaturen in de  [!UICONTROL DAM Update Asset] workflow.*

1. Open de stap in de bewerkingsmodus. Ga naar **[!UICONTROL Advanced Settings]** en controleer of de optie **[!UICONTROL Handler Advance]** is ingeschakeld.

   ![Workflow van DAM-updatemiddelen configureren en stap voor slimme tags toevoegen](assets/smart-tag-step-properties-workflow1.png)


   *Afbeelding: Workflow van DAM-updatemiddelen configureren en stap voor slimme tags toevoegen*

1. Selecteer **[!UICONTROL Arguments]** op het tabblad **[!UICONTROL Ignore Errors]** als u de workflow wilt voltooien, zelfs als de stap voor automatische labeling mislukt.

   ![De DAM Update Asset-workflow configureren om een stap voor slimme tags toe te voegen en de voortgang van de handler te selecteren](assets/smart-tag-step-properties-workflow2.png)


   *Afbeelding: De DAM Update Asset-workflow configureren om een stap voor slimme tags toe te voegen en de voortgang van de handler te selecteren*

   Als u assets tijdens het uploaden wilt voorzien van een tag (ongeacht of slimme tags zijn ingeschakeld voor mappen), moet u de optie **[!UICONTROL Ignore Smart Tag Flag]** inschakelen.

   ![Workflow van DAM Update Asset configureren om stap Smart Tag toe te voegen en markering Smart Tag negeren te selecteren](assets/smart-tag-step-properties-workflow3.png)


   *Afbeelding: Workflow van DAM Update Asset configureren om stap Smart Tag toe te voegen en markering Smart Tag negeren te selecteren*

1. Klik op **[!UICONTROL OK]** om de processtap te sluiten en sla de workflow op.

>[!MORELIKETHIS]
>
>* [Slimme tags beheren](managing-smart-tags.md)
>* [Overzicht van slimme tags en hoe deze kunnen worden getraind](enhanced-smart-tags.md)
>* [Richtlijnen en regels voor de opleiding van de Smart Content Service](smart-tags-training-guidelines.md)

