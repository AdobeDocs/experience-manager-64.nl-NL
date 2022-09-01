---
title: Vorm activa het etiketteren gebruikend de Slimme Dienst van de Inhoud.
description: Leer hoe u slimme tags en verbeterde slimme tags kunt configureren in [!DNL Adobe Experience Manager], met gebruik van de Smart Content Service.
contentOwner: AG
feature: Smart Tags,Tagging
role: Admin
exl-id: 11c5dd92-f824-41d2-9ab2-b32bdeae01b6
source-git-commit: bd65633e85226659df99da1d3834fa18a89de11e
workflow-type: tm+mt
source-wordcount: '1081'
ht-degree: 27%

---

# Asset tagging configureren met behulp van de Smart Content Service {#configure-asset-tagging-using-the-smart-content-service}

U kunt [!DNL Adobe Experience Manager] met de Smart Content Service [!DNL Adobe Developer Console]. Gebruik deze configuratie om tot de Slimme Dienst van de Inhoud van binnen toegang te hebben [!DNL Experience Manager].

>[!NOTE]
>
>* Smart Content Services is niet meer beschikbaar voor nieuwe [!DNL Experience Manager Assets] Klanten op locatie. Bestaande klanten op locatie, die deze mogelijkheid al hebben ingeschakeld, kunnen Smart Content Services blijven gebruiken.
>* Smart Content Services is beschikbaar voor bestaande [!DNL Experience Manager Assets] Managed Services-klanten die deze mogelijkheid al hebben ingeschakeld.
>* Nieuw [!DNL Experience Manager Assets] Managed Services-klanten kunnen de instructies in dit artikel volgen om Smart Content Services in te stellen.


Het artikel detailleert de volgende zeer belangrijke taken uit die worden vereist om de Slimme Dienst van de Inhoud te vormen. Aan het achterste uiteinde [!DNL Experience Manager] de server verifieert uw de dienstgeloofsbrieven met [!DNL Adobe Developer Console] gateway alvorens uw verzoek aan de Slimme Dienst van de Inhoud door:sturen.

1. [Een Smart Content Service maken](#obtain-public-certificate) configuratie in [!DNL Experience Manager] om een openbare sleutel te produceren. [Verkrijg een openbaar certificaat voor OAuth-integratie.](#obtain-public-certificate)

1. [Maak een integratie in Adobe Developer Console en upload de gegenereerde openbare sleutel.](#create-adobe-i-o-integration)

1. [Uw implementatie configureren](#configure-smart-content-service) API-sleutel en andere gegevens van [!DNL Adobe Developer Console].

1. [Test de configuratie](#validate-the-configuration).

1. Optioneel [automatisch labelen inschakelen bij het uploaden van elementen](#enable-smart-tagging-in-the-update-asset-workflow-optional).

## Vereisten {#prerequisites}

Voordat u de service Slimme inhoud gebruikt, moet u het volgende doen om een integratie te maken op [!DNL Adobe Developer Console]:

* Een Adobe ID-account met beheerdersrechten voor de organisatie.

* De Slimme Dienst van de Inhoud wordt toegelaten voor uw organisatie.

Als u naast het bovenstaande de verbeterde slimme tags wilt inschakelen, installeert u ook de nieuwste [Experience Manager Service Pack](https://helpx.adobe.com/experience-manager/aem-releases-updates.html).

## Configuratie van Smart Content Service maken om een openbaar certificaat te verkrijgen {#obtain-public-certificate}

Met een openbaar certificaat kunt u uw profiel verifiëren op [!DNL Adobe Developer Console].

1. Ga in de [!DNL Experience Manager]-gebruikersinterface naar **[!UICONTROL Tools]** > **[!UICONTROL Cloud Services]** > **[!UICONTROL Legacy Cloud Services]**.

1. Klik op de pagina Cloud Services op **[!UICONTROL Configure Now]** krachtens **[!UICONTROL Assets Smart Tags]**.

1. In de **[!UICONTROL Create Configuration]** geeft u een titel en naam op voor de configuratie Slimme tags. Klik op **[!UICONTROL Create]**.

1. In de **[!UICONTROL AEM Smart Content Service]** gebruikt u de volgende waarden:

   **[!UICONTROL Service URL]**: `https://smartcontent.adobe.io/<region where your Experience Manager author instance is hosted>`

   Bijvoorbeeld, `https://smartcontent.adobe.io/apac`. U kunt `na`, `emea`, of `apac` als de gebieden waar uw Experience Manager auteur-instantie wordt gehost.

   >[!NOTE]
   >
   >Als de Experience Manager Beheerde Dienst vóór September 01, 2022 provisioned is, gebruik de volgende Dienst URL:
   >`https://mc.adobe.io/marketingcloud/smartcontent`

   **[!UICONTROL Authorization Server]**: `https://ims-na1.adobelogin.com`

   Laat de overige velden voorlopig leeg (later te verstrekken). Klik op **[!UICONTROL OK]**.

   ![Het dialoogvenster Experience Manager Smart Content Service om de contentservice-URL op te geven](assets/aem_scs.png)


   *Afbeelding: Het dialoogvenster Smart Content Service om de URL van de inhoudsservice te bieden*

   >[!NOTE]
   >
   >De opgegeven URL [!UICONTROL Service URL] is niet toegankelijk via de browser en genereert een fout van 404. De configuratie werkt OK met dezelfde waarde als de [!UICONTROL Service URL] parameter. Voor het algemene de dienststatus en onderhoudsplan, zie [https://status.adobe.com](https://status.adobe.com).

1. Klikken **[!UICONTROL Download Public Certificate for OAuth Integration]** en download het openbare certificaatbestand `AEM-SmartTags.crt`.

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

1. Toegang [https://console.adobe.io](https://console.adobe.io) en navigeer naar de bestaande Smart Content Services op de **[!UICONTROL Integrations]** pagina. Upload het nieuwe certificaat. Zie de instructies in [Integratie met Adobe Developer Console maken](#create-adobe-i-o-integration).

## Integratie met Adobe Developer Console maken {#create-adobe-i-o-integration}

Als u API&#39;s voor Smart Content Service wilt gebruiken, maakt u een integratie in Adobe Developer Console om [!UICONTROL API Key] (gegenereerd in [!UICONTROL CLIENT ID] gebied van de integratie van Adobe Developer Console), [!UICONTROL TECHNICAL ACCOUNT ID], [!UICONTROL ORGANIZATION ID], en [!UICONTROL CLIENT SECRET] for [!UICONTROL Assets Smart Tagging Service Settings] van cloudconfiguratie in [!DNL Experience Manager].

1. Open [https://console.adobe.io](https://console.adobe.io/) in uw browser. Selecteer het gewenste account en verifieer dat de bijbehorende organisatierol is ingesteld op systeembeheerder.

1. Maak een project een geef het de gewenste naam. Klik op **[!UICONTROL Add API]**.

1. Op de **[!UICONTROL Add an API]** pagina, selecteert u **[!UICONTROL Experience Cloud]** en selecteer vervolgens **[!UICONTROL Smart Content]**. Klik op **[!UICONTROL Next]**.

1. Selecteer **[!UICONTROL Upload your public key]**. Geef het certificaatbestand op dat u hebt gedownload van [!DNL Experience Manager]. Er wordt een [!UICONTROL Public key(s) uploaded successfully]-bericht weergegeven. Klik op **[!UICONTROL Next]**.

   De pagina [!UICONTROL Create a new Service Account (JWT) credential] toont de openbare sleutel voor het serviceaccount dat u zojuist hebt geconfigureerd. 

1. Klik op **[!UICONTROL Next]**.

1. Ga naar de pagina **[!UICONTROL Select product profiles]** en selecteer **[!UICONTROL Smart Content Services]**. Klik op **[!UICONTROL Save configured API]**.

   De pagina die verschijnt biedt meer informatie over de configuratie. Laat deze pagina open om deze waarden te kopiëren en toe te voegen in [!UICONTROL Assets Smart Tagging Service Settings] van cloudconfiguratie in [!DNL Experience Manager] om slimme tags te configureren.

   ![Op het tabblad Overview kunt u de informatie bekijken die is opgegeven voor de integratie.](assets/integration_details.png)

   *Afbeelding: Gegevens over de integratie in Adobe Developer Console*

## Smart Content Service configureren {#configure-smart-content-service}

Om de integratie te vormen, gebruik de waarden van [!UICONTROL TECHNICAL ACCOUNT ID], [!UICONTROL ORGANIZATION ID], [!UICONTROL CLIENT SECRET], en [!UICONTROL CLIENT ID] velden van de integratie met Adobe Developer Console. Het creëren van een Slimme wolkenconfiguratie van Markeringen staat authentificatie van API verzoeken van toe [!DNL Experience Manager] implementatie.

1. In [!DNL Experience Manager], navigeer naar **[!UICONTROL Tools > Cloud Service > Legacy Cloud Services]** om de [!UICONTROL Cloud Services] console.

1. Onder de **[!UICONTROL Assets Smart Tags]**, opent u de hierboven gemaakte configuratie. Klik op de pagina met service-instellingen op **[!UICONTROL Edit]**.

1. Gebruik in het dialoogvenster **[!UICONTROL AEM Smart Content Service]** de vooraf ingevulde waarden voor de velden **[!UICONTROL Service URL]** en **[!UICONTROL Authorization Server]**.

1. Voor de velden [!UICONTROL Api Key], [!UICONTROL Technical Account ID], [!UICONTROL Organization ID], en [!UICONTROL Client Secret]kopieert en gebruikt u de volgende waarden die zijn gegenereerd in [Integratie met Adobe Developer Console](#create-adobe-i-o-integration).

   | [!UICONTROL Assets Smart Tagging Service Settings] | [!DNL Adobe Developer Console] integratievelden |
   |--- |--- |
   | [!UICONTROL Api Key] | [!UICONTROL CLIENT ID] |
   | [!UICONTROL Technical Account ID] | [!UICONTROL TECHNICAL ACCOUNT ID] |
   | [!UICONTROL Organization ID] | [!UICONTROL ORGANIZATION ID] |
   | [!UICONTROL Client Secret] | [!UICONTROL CLIENT SECRET] |

## De configuratie valideren {#validate-the-configuration}

Nadat u de configuratie hebt voltooid, gebruik een JMX MBean om de configuratie te bevestigen. Voer de volgende stappen uit om te valideren.

1. Toegang tot uw [!DNL Experience Manager] server op `https://[aem_server]:[port]`.

1. Ga naar **[!UICONTROL Tools > Operations > Web Console]** om de OSGi-console te openen. Klik op **[!UICONTROL Main > JMX]**.

1. Klik op **[!UICONTROL com.day.cq.dam.similaritysearch.internal.impl]**. Wordt geopend **[!UICONTROL SimilaritySearch Miscellaneous Tasks]**.

1. Klik op **[!UICONTROL validateConfigs()]**. In de **[!UICONTROL Validate Configurations]** dialoogvenster, klikt u op **[!UICONTROL Invoke]**.

   De validatieresultaten worden in hetzelfde dialoogvenster weergegeven.

## Slimme tags toepassen inschakelen in de DAM Update Asset-workflow (optioneel) {#enable-smart-tagging-in-the-update-asset-workflow-optional}

1. Ga in [!DNL Experience Manager] naar **[!UICONTROL Tools]** > **[!UICONTROL Workflow]** > **[!UICONTROL Models]**.

1. Selecteer op de pagina **[!UICONTROL Workflow Models]** het **[!UICONTROL DAM Update Asset]**-workflowmodel.

1. Klik op **[!UICONTROL Edit]** op de werkbalk.

1. Vouw het zijpaneel uit om de stappen weer te geven. Sleep de stap **[!UICONTROL Smart Tag Asset]** die beschikbaar is in de DAM-workflowsectie en plaats deze na de stap **[!UICONTROL Process Thumbnails]**.

   ![De stap Asset met slimme tag toevoegen na de stap met de procesminiaturen in de DAM Update Asset-workflow](assets/smart-tag-in-dam-update-asset-workflow.png)

   *Afbeelding: Voeg de stap Slim tagelement toe na de stap met de procesminiaturen in het dialoogvenster [!UICONTROL DAM Update Asset] workflow.*

1. Open de stap in de bewerkingsmodus. Ga naar **[!UICONTROL Advanced Settings]** en controleer of de optie **[!UICONTROL Handler Advance]** is ingeschakeld.

   ![Workflow van DAM-updatemiddelen configureren en stap voor slimme tags toevoegen](assets/smart-tag-step-properties-workflow1.png)


   *Afbeelding: Workflow van DAM-updatemiddelen configureren en stap voor slimme tags toevoegen*

1. In de **[!UICONTROL Arguments]** tab, selecteert u **[!UICONTROL Ignore Errors]** als u wilt dat de workflow wordt voltooid, zelfs als de stap voor automatisch labelen mislukt.

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

